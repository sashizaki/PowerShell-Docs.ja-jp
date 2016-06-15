# Just Enough Administration (JEA): 概要

## 目次
このドキュメントを読むと、Just Enough Administration (JEA) 展開を作成、展開、使用、保守、および監査できるようになります。
この入門ガイドで説明されているトピックを次に示します。

1.  [概要](#introduction): JEA を検討する必要がある理由を簡単に説明します

2.  [前提条件](#prerequisites): 環境を設定します

3.  [JEA の使用](#using-jea): JEA を使用するオペレーターのエクスペリエンスを理解することから始めます

4.  [デモを作り直す](#remake-the-demo-endpoint): JEA セッション構成を最初から作成します

5.  [ロール機能](#role-capabilities): ロール機能ファイルを使用して JEA の機能をカスタマイズする方法について説明します

6.  [End to End - Active Directory](#end-to-end---active-directory): Active Directory を管理するためのまったく新しいエンドポイントを作成します

7.  [複数のコンピューターの展開と保守](#multi-machine-deployment-and-maintenance): 規模によって展開と作成がどのように変化するかを理解します

8.  [JEA のレポート](#reporting-on-jea): JEA のすべての操作とインフラストラクチャの監査とレポート方法を理解します

9.  [付録](#appendix): 重要なスキルとディスカッション ポイントを示します

## はじめに

### 動機
システムに対する特権アクセスを誰かに付与することは、信頼の境界をその人物まで拡張することを意味します。
これにはリスクが伴います。なぜなら、管理者は、システムを攻撃する者になる可能性があるためです。
内部の関係者による攻撃と資格情報の盗難は、どちらも実際によくあることです。

これは新しい問題ではありません。
最小権限の原則を熟知し、ロール ベース アクセス制御 (RBAC) を何らかの形で使用してアプリケーションの管理を行っているかもしれません。
ただし、このソリューションの有効性と管理容易性は、多くの場合、その適用範囲の幅広さと不正確さによる限界があります。
さらに、RBAC には、その適用範囲にずれがあります。
たとえば、Windows では、特権アクセスの大部分はバイナリ スイッチであり、ユーザーを Administrators グループに追加するときに、不要なアクセス許可が強制的に付与されることになります。

Just Enough Administration (JEA) は、PowerShell リモート処理による RBAC プラットフォームを提供します。
*それは、特定のユーザーに管理者権限を与えることなく、そのユーザーが特定のサーバーで特定の管理タスクを実行できるようにします。*
これにより、既存の RBAC ソリューションのずれを補い、設定を容易に管理できるようにします。

## 前提条件

### 初期状態
このセクションの操作を開始する前に、次の状態になっていることを確認してください。

1. システムで JEA が利用可能である。 現在サポートされているオペレーティング システムと必要なダウンロードを[こちら](./README.md)で確認してください。
2. JEA を試そうとしているコンピューターの管理者権限を持っていること。
3. コンピューターがドメインに参加していること。
ドメインがない場合に新しいドメインをサーバー上にすぐにセットアップするには、「[ドメイン コントローラーの作成](#creating-a-domain-controller)」セクションを参照してください。

### PowerShell リモート処理を有効にする
JEA による管理は、PowerShell リモート処理を通して行われます。
Administrator PowerShell ウィンドウで次のコマンドを実行して、PowerShell リモート処理を有効にし、適切に構成されるようにします。

```PowerShell
Enable-PSRemoting 
```

PowerShell リモート処理に慣れていない場合は、`Get-Help about_Remote` を実行して、重要な基本概念について理解しておくことをお勧めします。

### ユーザーまたはグループを識別する
JEA の動作を示すために、このガイド全体で使用する管理者以外のユーザーとグループを識別する必要があります。
  
既存のドメインを使用している場合は、特権のないユーザーとグループを識別するか、そのようなユーザーとグループをいくつか作成してください。
これらの管理者以外のユーザーで、JEA にアクセスします。
スクリプトの一番上に `$NonAdministrator` 変数がある場合は、その変数に選択した管理者以外のユーザーまたはグループを常に割り当ててください。 

新しいドメインを最初から作成する場合は、はるかに簡単です。
付録の「[ユーザーとグループの設定](#set-up-users-and-groups)」セクションに従って、管理者以外のユーザーとグループを作成してください。
そのセクションに従って作成したグループの既定値は `$NonAdministrator` になります。

### メンテナンス ロール機能ファイルの設定
PowerShell で次のコマンドを実行して、次のセクションで使用するデモ用のロール機能ファイルを作成します。
このファイルが何をするかについては、このガイドの後半で説明します。

```PowerShell
# Fields in the role capability
$MaintenanceRoleCapabilityCreationParams = @{
    Author = 'Contoso Admin'
    CompanyName = 'Contoso'
    VisibleCmdlets = 'Restart-Service'
    FunctionDefinitions = 
            @{ Name = 'Get-UserInfo'; ScriptBlock = { $PSSenderInfo } }
}

# Create the demo module, which will contain the maintenance Role Capability File
New-Item -Path "$env:ProgramFiles\WindowsPowerShell\Modules\Demo_Module" -ItemType Directory
New-ModuleManifest -Path "$env:ProgramFiles\WindowsPowerShell\Modules\Demo_Module\Demo_Module.psd1"
New-Item -Path "$env:ProgramFiles\WindowsPowerShell\Modules\Demo_Module\RoleCapabilities" -ItemType Directory 

# Create the Role Capability file
New-PSRoleCapabilityFile -Path "$env:ProgramFiles\WindowsPowerShell\Modules\Demo_Module\RoleCapabilities\Maintenance.psrc" @MaintenanceRoleCapabilityCreationParams 
```
  
### デモ用のセッション構成ファイルを作成して登録する
次のコマンドを実行して、次のセクションで使用するデモ用のセッション構成ファイルを作成します。
このファイルが何をするかについては、このガイドの後半で説明します。

```PowerShell
# Determine domain
$domain = (Get-CimInstance -ClassName Win32_ComputerSystem).Domain

# Replace with your non-admin group name
$NonAdministrator = "$domain\JEA_NonAdmin_Operator"

# Specify the settings for this JEA endpoint
# Note: You will not be able to use a virtual account if you are using WMF 5.0 on Windows 7 or Windows Server 2008 R2
$JEAConfigParams = @{
    SessionType = 'RestrictedRemoteServer'
    RunAsVirtualAccount = $true
    RoleDefinitions = @{
        $NonAdministrator = @{ RoleCapabilities = 'Maintenance' }
    }
    TranscriptDirectory = "$env:ProgramData\JEAConfiguration\Transcripts"
}

# Set up a folder for the Session Configuration files
if (-not (Test-Path "$env:ProgramData\JEAConfiguration"))
{
    New-Item -Path "$env:ProgramData\JEAConfiguration" -ItemType Directory
}

# Specify the name of the JEA endpoint
$sessionName = 'JEA_Demo'

if (Get-PSSessionConfiguration -Name $sessionName -ErrorAction SilentlyContinue)
{
    Unregister-PSSessionConfiguration -Name $sessionName -ErrorAction Stop
}

New-PSSessionConfigurationFile -Path "$env:ProgramData\JEAConfiguration\JEADemo.pssc" @JEAConfigParams

# Register the session configuration
Register-PSSessionConfiguration -Name $sessionName -Path "$env:ProgramData\JEAConfiguration\JEADemo.pssc"
```
 
### PowerShell モジュールのログを有効にする (省略可能)
次の手順で、システム上のすべての PowerShell 操作のログを有効にします。
これは JEA を動作させるために有効にする必要はありませんが、「[JEA のレポート](#reporting-on-jea)」セクションで役に立ちます。

1. ローカル グループ ポリシー エディターを開きます。
2. "Computer Configuration\Administrative Templates\Windows Components\Windows PowerShell" に移動します。
3. [モジュール ログを有効にする] をダブルクリックします。
4. [有効] をクリックします。
5. [オプション] セクションで、モジュール名の横にある [表示] をクリックします。
6. ポップアップ ウィンドウに「*」と入力します。 これは、PowerShell がすべてのモジュールのコマンドを記録することを意味します。
7. [OK] をクリックしてポリシーを適用します。

注: グループ ポリシーを通してシステム全体の PowerShell トランスクリプトを有効にすることもできます。

**以上で、ご使用のコンピューターでデモ エンドポイントが構成され、JEA を使用する準備が整いました。**

## JEA の使用
このセクションの焦点は、*JEA の使用*というエンド ユーザー エクスペリエンスを理解することです。
「前提条件」セクションで、デモ用の JEA エンドポイントを作成しました。
このデモを使用して、JEA の動作を示します。
エンド ユーザー エクスペリエンスを可能にしている操作とファイルについては、このガイドの後半で説明します。

### 管理者以外のユーザーとして JEA を使用する
JEA の動作を示すには、管理者以外のユーザーとして PowerShell リモート処理を使用する必要があります。
新しい PowerShell ウィンドウで次のコマンドを実行します。   

```PowerShell
$NonAdminCred = Get-Credential
```

入力を求められたら、管理者以外のアカウントの資格情報を入力します。
「[ユーザーとグループの設定](#set-up-users-and-groups)」セクションに従っている場合、資格情報は次のようになります。
-   ユーザー名 = "OperatorUser"
-   パスワード = "pa$$w0rd"

次に、次のコマンドを実行して、指定した資格情報を使用するデモ エンドポイントに接続します。

```PowerShell
Enter-PSSession -ComputerName . -ConfigurationName JEA_Demo -Credential $NonAdminCred 
```

これで、ローカル コンピューターで対話型リモート PowerShell セッションに入りました。 "Credential" パラメーターの使用によって、OperatorUser (または使用したユーザー名の) アカウント*として*接続されています。
プロンプトが `[localhost]: PS>` に変化していることは、リモート セッションを操作していることを示します。  

リモート コマンド プロンプトで次のコマンドを実行して、自分が使用できるコマンドを表示します。

```PowerShell
Get-Command 
```

お察しのように、表示されるのは、通常の PowerShell ウィンドウで使用できるコマンド (多くの場合、数千のコマンドを含む可能性があります) の非常に限定されたサブセットです。
具体的には、JEA の 7 つの既定のコマンドレット (Clear-Host、Exit-PSSession、Get-Command、Get-FormatData、Get-Help、Measure-Object、Out-Default、Select-Object) と、メンテナンス ロール ファイルに明示的に含まれている 2 つのコマンドだけが表示されます。

次に、メンテナンス ロール機能ファイルに含まれるユーザー定義関数を呼び出して、このセッションが動作しているユーザー コンテキストを調べてみましょう。

```PowerShell
Get-UserInfo
```
 
この関数の出力は、"ConnectedUser" と "RunAsUser" を示します。
接続されたユーザー ("ConnectedUser") は、リモート セッションに接続されたアカウントです (例:自分のアカウント)。
接続されたユーザーは、管理者特権を持つ必要はありません。
"RunAs" アカウントは、特権操作を実際に実行するアカウントです。
アカウントをユーザーとして接続し、特権ユーザーとして実行することで、管理権限を与えることなく、ユーザーが特定の管理タスクを実行することを許可できます。

この動作の実例を示すために、次のコマンドを実行します。

```PowerShell
Restart-Service -Name Spooler -Verbose
```

通常、Restart-Service を実行するには、管理者特権が必要です。
ただし、JEA 仮想アカウントでは、権限のない資格情報を使用して、このコマンドを実行できます。

このように、JEA では、既に使用したコマンドを使用して作業を実行できます。
それでは、使用を*許可されていない*コマンドの場合はどうなるでしょうか。
JEA セッションで別のコマンド (`Restart-Computer` など) を実行してみてください。そのようなコマンドは JEA によって実行が禁止されることを確認してください。

```PowerShell
[localhost]: PS> Restart-Computer
The term 'Restart-Computer' is not recognized as the name of a cmdlet, function, script file, or
operable program. Check the spelling of the name, or if a path was included, verify that the path
is correct and try again.
    + CategoryInfo          : ObjectNotFound: (Restart-Computer:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException 
```

最後に、制約付きの JEA エンドポイントから離れるために、次のコマンドを実行します。

```PowerShell
Exit-PSSession
```

これで、リモート PowerShell セッションから切断されます。

## デモ エンドポイントを作り直す
このセクションでは、前のセクションで使用したデモ エンドポイントの完全なレプリカを生成する方法について説明します。
ここでは、PowerShell セッション構成とロール機能を含む、JEA を理解するために必要な中心概念について説明します。 

### PowerShell セッション構成
前のセクションで JEA を使用したとき、次のコマンドを実行することから始めました。

```PowerShell
Enter-PSSession -ComputerName . -ConfigurationName JEA_Demo -Credential $NonAdminCred
```

ほとんどのパラメーターは見ればわかりますが、*ConfigurationName* パラメーターは、最初はわかりにくいかもしれません。
そのパラメーターは、接続される PowerShell セッション構成を指定していました。 

*PowerShell セッション構成*は、PowerShell エンドポイントの別名です。
それは、ユーザーが接続して PowerShell の機能にアクセスする比喩的な "場所" です。
セッション構成の設定方法に基づいて、接続しているユーザーに異なる機能を提供できます。
JEA では、セッション構成を使用して、PowerShell の機能を限定されたセットに制限し、特権のある仮想アカウントとして実行します。

既にいくつかの PowerShell セッション構成がコンピューターに登録されていますが、それぞれの設定はわずかに異なります。
ほとんどは Windows に付属していますが、"JEA_Demo" セッション構成は「[前提条件](#prerequisites)」セクションで設定したものです。
Administrator PowerShell プロンプトで次のコマンドを実行することで、登録されているすべてのセッション構成を確認できます。

```PowerShell
Get-PSSessionConfiguration
```

### PowerShell セッション構成ファイル
新しいセッション構成は、新しい *PowerShell セッション構成ファイル*を登録することで作成できます。
セッション構成ファイルのファイル拡張子は ".pssc" です。
セッション構成ファイルは、New-PSSessionConfigurationFile コマンドレットを使用して生成できます。

この後、JEA 用の新しいセッション構成を作成して登録します。 

### PowerShell セッション構成を生成して変更する
次のコマンドを実行して、PowerShell セッション構成の "スケルトン" ファイルを生成します。

```PowerShell
New-PSSessionConfigurationFile -Path "$env:ProgramData\JEAConfiguration\JEADemo2.pssc"
```

> **ヒント:** 既定では、スケルトン ファイルには、最も一般的な構成設定のみが含まれます。
> `-Full` パラメーターを使用して、適用できるすべての設定を、生成される PSSC に含めてください。

PowerShell ISE または任意のテキスト エディターでファイルを開きます。

```PowerShell
ise "$env:ProgramData\JEAConfiguration\JEADemo2.pssc" 
```

ファイルの次のフィールドを、その下に示されている値に更新します。(管理者以外のセキュリティ グループに置き換えるのを忘れないでください)。 

```PowerShell
# OLD: SessionType = 'Default'
SessionType = 'RestrictedRemoteServer'

# OLD: TranscriptDirectory = 'C:\Transcripts\'
TranscriptDirectory = "C:\ProgramData\JEAConfiguration\Transcripts"

# OLD: # RunAsVirtualAccount = $true
RunAsVirtualAccount = $true

# OLD: RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }
RoleDefinitions = @{'CONTOSO\JEA_NonAdmin_Operator' = @{ RoleCapabilities =  'Maintenance' }}
```

各エントリの意味は次のとおりです。

1.  *SessionType* フィールドは、このエンドポイントで使用する事前設定された既定の設定を定義します。
*RestrictedRemoteServer* は、リモート管理を行うために必要な最小限の設定を定義します。 既定では、*RestrictedRemoteServer* エンドポイントは、Get-Command、Get-FormatData、Select-Object、Get-Help、Measure-Object、Exit-PSSession、Clear-Host、および Out-Default を公開します。
それは、*ExecutionPolicy* を *RemoteSigned* に設定し、*LanguageMode* を *NoLanguage* に設定します。
これらの設定の実際の効果は、エンドポイントを構成するためのセキュリティで保護された最小限の構成の開始点になることです。

2.  *RoleDefinitions* フィールドは、ロール機能を特定のグループに割り当てます。
これは、特権アカウントとして誰が何を実行できるかを定義します。
このフィールドを使用して、接続しているユーザーがグループ メンバーシップに基づいて利用できる機能を指定できます。
これは、JEA の RBAC 機能の核心です。
この例では、事前に作成された "デモ用の" ロール機能を "Contoso\JEA_NonAdmin_Operator" グループのメンバーに公開しています。

3.  *RunAsVirtualAccount* フィールドは、このエンドポイントで PowerShell を仮想アカウント "として (RunAs)" 実行する必要があることを示します。
既定では、仮想アカウントは、組み込み Administrators グループのメンバーです。
ドメイン コントローラーでは、既定では、Domain Administrators グループのメンバーです。
このガイドの後半で、仮想アカウントの特権をカスタマイズする方法について説明します。

4.  *TranscriptDirectory* フィールドは、各リモート セッションの後で "肩越しの" PowerShell トランスクリプトを保存する場所を定義します。
これらのトランスクリプトを使用して、各セッションで実行された操作を読みやすい方法で調べることができます。
PowerShell トランスクリプトについて詳しくは、[こちらのブログ投稿](http://blogs.msdn.com/b/powershell/archive/2015/06/09/powershell-the-blue-team.aspx)をご覧ください。
注: 標準の Windows Eventing も、各ユーザーが PowerShell で何を実行したかについての情報をキャプチャします。
トランスクリプトのほうが、少し読みやすくなっています。

最後に、変更を *JEADemo2.pssc* に保存します。

### PowerShell セッション構成を適用する 

セッション構成ファイルからエンドポイントを作成するには、ファイルを登録する必要があります。
これを行うには、次の情報が必要です。

1. セッション構成ファイルのパス。
2. 登録されるセッション構成の名前。 これは、ユーザーが `Enter-PSSession` または `New-PSSession` を使用してエンドポイントに接続するときに "ConfigurationName" パラメーターに指定する名前と同じです。

ローカル コンピューターにセッション構成を登録するには、次のコマンドを実行します。

```PowerShell
Register-PSSessionConfiguration -Name 'JEADemo2' -Path "$env:ProgramData\JEAConfiguration\JEADemo2.pssc"
```

以上で、 JEA エンドポイントが設定されました。

### エンドポイントをテストする
「[JEA の使用](#using-jea)」セクションに示されている手順をもう一度実行して、新しいエンドポイントが意図したとおりに動作していることを確認します。
Enter-pssession に構成名を指定するときに、新しいエンドポイント名 (JEADemo2) を必ず使用してください。

```PowerShell
Enter-PSSession -ComputerName . -ConfigurationName JEADemo2 -Credential $NonAdminCred
```

### 主要概念
**PowerShell セッション構成**: *PowerShell エンドポイント* と呼ばれることもあります。これは、ユーザーが接続して PowerShell の機能にアクセスする比喩的な "場所" です。
`Get-PSSessionConfiguration` を実行することで、システムに登録されているセッション構成を一覧表示できます。
特別な方法で構成した PowerShell セッション構成を *JEA エンドポイント*と呼ぶことができます。

**PowerShell セッション構成ファイル (.pssc)**: 登録すると、PowerShell セッション構成の設定を定義するファイルです。
エンドポイントに接続できるユーザー ロール、仮想アカウント "として (RunAs)" 実行するアカウントなどの仕様が含まれます。     

**ロール定義**: セッション構成ファイル内のフィールドであり、接続しているユーザーに与えられるロール機能を定義します。
これは、特権アカウントとして、*誰が**何を*実行できるかを定義します。
これは、JEA の RBAC 機能の核心です。

**SessionType**: セッション構成の既定の設定を表すセッション構成ファイル内のフィールドです。
JEA エンドポイントでは、このフィールドは RestrictedRemoteServer に設定する必要があります。

**PowerShell トランスクリプト**: PowerShell セッションの "肩越しの" ビューを含むファイルです。
TranscriptDirectory フィールドを使用して、JEA セッションのトランスクリプトを生成するように PowerShell を設定できます。
トランスクリプトについて詳しくは、[こちらのブログ投稿](https://technet.microsoft.com/en-us/magazine/ff687007.aspx)をご覧ください。

## ロール機能

### 概要
前のセクションで、"RoleDefinitions" フィールドは、どのグループがどのロール機能にアクセスできるかを定義することを説明しました。
"ロール機能とは何か" と思うかもしれません。
このセクションでは、その疑問に答えます。  

## PowerShell ロール機能の概要
PowerShell ロール機能は、ユーザーが JEA エンドポイントで "何を" 実行できるかを定義します。
それらは、表示されるコマンドやアプリケーションなどを示す詳細なホワイトリストです。
ロール機能は、拡張子が ".psrc" のファイルによって定義されます。

## ロール機能の内容
前に使用したデモ用のロール機能ファイルを調べて変更することから始めます。
環境全体にセッション構成を展開しているが、ユーザーに公開される機能の変更を求めるフィードバックを受けていると想像してください。
マシンを再起動する機能を要求しているオペレーターがいます。彼らは、ネットワーク設定に関する情報も取得できることを望んでいます。
セキュリティ チームから、制限なしでユーザーに "Restart-Service" の実行を許可することは容認できないという指示を受けています。
オペレーターが再起動できるサービスを制限する必要があります。

これらの変更を行うには、管理者として PowerShell ISE を実行し、次のファイルを開くことから始めます。

```
C:\Program Files\WindowsPowerShell\Modules\Demo_Module\RoleCapabilities\Maintenance.psrc
```

次に、ファイルの次の行を検索して更新します。 

```PowerShell
# OLD: VisibleCmdlets = 'Restart-Service'
VisibleCmdlets = 'Restart-Computer',
                 @{
                     Name = 'Restart-Service'
                     Parameters = @{ Name = 'Name'; ValidateSet = 'Spooler' }
                 },
                 'NetTCPIP\Get-*'

# OLD: VisibleExternalCommands = 'Item1', 'Item2'
VisibleExternalCommands = 'C:\Windows\system32\ipconfig.exe'
```

ここには、興味深い例がいくつか含まれています。

1.  オペレーターは -Name パラメーターを指定した場合のみ Restart-Service を使用でき、そのパラメーターの引数として "Spooler" だけを指定できるように、Restart-Service に制限を設定します。
必要に応じて、"ValidateSet" ではなく "ValidatePattern" を使用する正規表現を使用して、引数を制限することもできます。

2.  NetTCPIP モジュールの "Get"動詞を使用するすべてのコマンドを公開しています。
"Get" コマンドは、通常はシステム状態を変更しないため、これらは比較的安全な操作です。
とはいえ、JEA を介して公開するすべてのコマンドを注意深く調べることを強く推奨します。

3.  VisibleExternalCommands を使用する実行可能ファイル (ipconfig) を公開しています。
このフィールドを使用して、すべての PowerShell スクリプトを公開することもできます。
重要なのは、似たような名前の (不正の可能性がある) プログラムがユーザーのパスに配置されて代わりに実行されることがないように、外部コマンドの完全パスを常に指定することです。

ファイルを保存した後、変更が機能することを確認するために、デモ エンドポイントにもう一度接続します。

```PowerShell
Enter-PSSession -ComputerName . -ConfigurationName JEADemo2 -Credential $NonAdminCred
Get-Command
```
ロール機能ファイルのみを更新したため、セッション構成を再登録する必要はありません。
PowerShell は、ユーザーが接続するときに、更新されたロール機能を自動的に検索します。
ロール機能は、セッションの開始時に読み込まれるため、既存のセッションはロール機能ファイルの更新に影響されません。

次に、Restart-Computer を -WhatIf パラメーターを指定して実行することで、コンピューターを再起動できることを確認します (コンピューターを実際に再起動するのでない限り、このパラメーターを指定します)。

```PowerShell
Restart-Computer -WhatIf 
```

"Ipconfig" を実行できることを確認します。

```PowerShell
ipconfig
```

最後に、Restart-Service は Spooler サービスに対してのみ機能することを確認します。

```PowerShell
Restart-Service Spooler # This should work
Restart-Service WSearch # This should fail 
```

操作を終了したら、セッションを終了します。

```PowerShell
Exit-PSSession 
```

### ロール機能の作成
次のセクションで、AD ヘルプ デスク ユーザー用の JEA エンドポイントを作成します。
準備として、そのセクションで値を入力するための空白のロール機能ファイルを作成します。
ロール機能は、セッションの開始時に解決されるように、有効な PowerShell モジュールの "RoleCapabilities" フォルダー内に作成する必要があります。

PowerShell モジュールは、本質的には PowerShell 機能のパッケージです。
PowerShell 関数、コマンドレット、DSC リソース、ロール機能などを含めることができます。
PowerShell コンソールで `Get-Help about_Modules` を実行することで、モジュールに関する情報を見つけることができます。

空白のロール機能ファイルがある新しい PowerShell モジュールを作成するには、次のコマンドを実行します。  

```PowerShell
# Create a new folder for the module.
New-Item -Path 'C:\Program Files\WindowsPowerShell\Modules\Contoso_AD_Module' -ItemType Directory

# Add a module manifest to contain metadata for this module.
New-ModuleManifest -Path 'C:\Program Files\WindowsPowerShell\Modules\Contoso_AD_Module\Contoso_AD_Module.psd1' -RootModule Contoso_AD_Module.psm1

# Create a blank script module. You'll use this for custom functions in the next section.
New-Item -Path 'C:\Program Files\WindowsPowerShell\Modules\Contoso_AD_Module\Contoso_AD_Module.psm1' -ItemType File 

# Create a RoleCapabilities folder in the AD_Module folder. PowerShell expects Role Capabilities to be located in a "RoleCapabilities" folder within a module.
New-Item -Path 'C:\Program Files\WindowsPowerShell\Modules\Contoso_AD_Module\RoleCapabilities' -ItemType Directory

# Create a blank Role Capability in your RoleCapabilities folder. Running this command without any additional parameters just creates a blank template.
New-PSRoleCapabilityFile -Path 'C:\Program Files\WindowsPowerShell\Modules\Contoso_AD_Module\RoleCapabilities\ADHelpDesk.psrc' 
```

以上で、空白のロール機能ファイルが作成されました。
これは、次のセクションで使用します。

### 主要概念
**ロール機能 (.psrc)**: ユーザーが JEA エンドポイントで "何を" 実行できるかを定義するファイルです。
それは、表示されるコマンドやコンソール アプリケーションなどを示す詳細なホワイトリストです。
PowerShell でロール機能を検出するには、有効な PowerShell モジュールの "RoleCapabilities" フォルダーにそれらを配置する必要があります。

**PowerShell モジュール**: PowerShell 機能のパッケージです。
PowerShell 関数、コマンドレット、DSC リソース、ロール機能などを含めることができます。
PowerShell モジュールが自動的に読み込まれるようにするには、`$env:PSModulePath` のパスの下に配置する必要があります。 

## エンド ツー エンド - Active Directory
プログラムの適用範囲が拡大されたと思ってください。
Active Directory の操作を実行するために、ドメイン コントローラーに JEA を追加する必要があります。
ヘルプ デスクのスタッフは、JEA を使用して、アカウントのロック解除、パスワードのリセット、その他の類似する操作を実行することになります。

まったく新しいコマンド セットを、異なるユーザー グループに公開する必要があります。
それに加えて、公開する必要がある既存の Active Directory スクリプトが多数あります。
このセクションでは、このタスクを実行するためのセッション構成とロール機能の作成について説明します。

### 前提条件
このセクションの手順を実行するには、ドメイン コントローラーを操作する必要があります。
ドメイン コントローラーにアクセスしたことがなくても大丈夫です。
熟知している他のシナリオやロールでの作業を想像しながら、読み進めてください。
新しいドメイン コントローラーをすぐに設定する場合は、付録の「[ドメイン コントローラーの作成](#creating-a-domain-controller)」を参照してください。

### 新しいロール機能とセッション構成の作成手順

新しいロール機能の作成は、最初はやっかいな作業に思えるかもしれませんが、それは、次に示す非常に単純な手順に分解することができます。

1.  有効にする必要があるタスクを特定する
2.  必要に応じて、それらのタスクを制限する
3.  タスクが JEA で機能することを確認する
4.  タスクをロール機能ファイルに配置する
5.  ロール機能を公開するセッション構成を登録する

### 手順 1: 何を公開する必要があるかを識別する
新しいロール機能またはセッション構成を作成する前に、ユーザーが JEA エンドポイントで何を実行する必要があり、それらを PowerShell でどのように実行する必要があるかを、すべて識別する必要があります。
これには、相当量の要件の収集と調査が伴います。
このプロセスをどのように進めるかは、組織と目標によって決まります。
重要なのは、要件の収集と調査を、非常に意味のある作業として実施することです。
これは、JEA の採用プロセスの中で、最も困難な手順である可能性があります。

#### リソースを見つける
Active Directory 管理エンドポイントを作成するための調査で利用されている可能性があるオンライン リソースがあります。
-   [Active Directory PowerShell Overview (Active Directory PowerShell の概要)](http://blogs.msdn.com/b/adpowershell/archive/2009/03/05/active-directory-powershell-overview.aspx) 
-   [CMD to PowerShell Guide for Active Directory (Active Directory 用 PowerShell コマンド ガイド)](http://blogs.technet.com/b/ashleymcglone/archive/2013/01/02/free-download-cmd-to-powershell-guide-for-ad.aspx)

#### リストを作成する
このセクションの残りの部分で扱う 10 個の操作を次に示します。
これは単なる例であり、組織の要件によって異なる可能性があることに注意してください。

|操作                                                         |PowerShell コマンド                                             |
|---------------------------------------------------------------|---------------------------------------------------------------|
|アカウントのロック解除                                                 |`Unlock-ADAccount`                                             |
|パスワードのリセット                                                 |`Set-ADAccountPassword` および `Set-ADUser -ChangePasswordAtLogon`|
|ユーザーのタイトルの変更                                          |`Set-ADUser -Title`                                            |  
|ロックアウト済み、無効化、非アクティブなどの状態になっている AD アカウントの検索 |`Search-ADAccount`                                             | 
|グループへのユーザーの追加                                              |`Add-ADGroupMember -Identity (with whitelist) -Members`        | 
|グループからのユーザーの削除                                         |`Remove-ADGroupMember -Identity (with whitelist) -Members`     | 
|ユーザー アカウントの有効化                                          |`Enable-ADAccount`                                             |
|ユーザー アカウントの無効化                                         |`Disable-ADAccount`                                            |

### 手順 2: 必要に応じてタスクを制限する

操作リストができたら、各コマンドの機能を徹底的に検討する必要があります。
これを行う 2 つの重要な理由があります。

1.  意図以上の機能がユーザーに与えられる可能性があります。
たとえば、`Set-ADUser` は非常に強力で柔軟なコマンドです。
このコマンドで実行できるすべての操作をヘルプ デスクのユーザーに公開する必要はありません。  

2.  さらに悪いのは、ユーザーが JEA の制限を逃れることを可能にするコマンドが公開される可能性があることです。
これが発生した場合、JEA はセキュリティ境界として機能しなくなります。
コマンドは慎重に選択してください。
たとえば、Invoke-Expression は、ユーザーがコードを無制限に実行することを可能にします。
このトピックの詳細については、「コマンドを制限する際の考慮事項」セクションを参照してください。

各コマンドを検討した後、次のように制限することを決定したとします。

1.  `Set-ADUser`  は、"-Title" パラメーターが指定された場合のみ実行することを許可する 

2.  `Add-ADGroupMember`  と `Remove-ADGroupMember` は、特定のグループでのみ動作する必要がある

### 手順 3: タスクが JEAで動作することを確認する
これらのコマンドレットは、制限された JEA 環境では単純に使用できない場合があります。
JEA は *NoLanguage* モードで実行されますが、このモードは、なによりもユーザーが変数を使用することを禁止します。
スムーズなエンド ユーザー エクスペリエンスを実現するには、いくつかの事項を確認する必要があります。

例として、`Set-ADAccountPassword` を検討します。
"-NewPassword" パラメーターには、セキュリティで保護された文字列が必要です。
多くの場合、ユーザーは、セキュリティで保護された文字列を作成し、それを変数として渡します (下記参照)。

```PowerShell
$newPassword = (Read-Host -Prompt "Specify a new password" -AsSecureString)
Set-ADAccountPassword -Identity mollyd -NewPassword $newPassword -Reset
```

ただし、NoLanguage モードでは、変数は使用できません。
この制限は、次の 2 つの方法で回避できます。

1.  変数を割り当てずにコマンドを実行することをユーザーに要求する。
これは簡単に構成できますが、エンドポイントを使用するオペレーターにとってはわずらわしい操作になる可能性があります。
パスワードをリセットするたびに、この文字列を入力したいと思う人がいるでしょうか。
```PowerShell
Set-ADAccountPassword -Identity mollyd -NewPassword (Read-Host -Prompt "Specify a new password" -AsSecureString) -Reset
```

2.  エンド ユーザーに公開されるスクリプトまたは関数で複雑さをラップする。
公開するスクリプトと関数が実行されるコンテキストに制限はありません。変数の使用と他のコマンドの呼び出しがある関数を問題なく記述できます。
この方法は、エンド ユーザー エクスペリエンスを単純化し、エラーを防止し、PowerShell の知識が少なくても実行でき、余分な機能を意図せずに公開する可能性を低下させます。
唯一の欠点は、関数を作成して管理するコストが発生することです。

#### 追加情報: モジュールへの関数の追加
方法 2 を採用する場合は、`Reset-ContosoUserPassword` という名前の PowerShell 関数を記述します。
この関数は、ユーザーのパスワードをリセットするときに実行する必要があるすべての操作を実行します。
組織によっては、手の込んだ複雑な操作が必要な場合があります。
これは単なる例であるため、ここで説明するコマンドは、パスワードをリセットし、ログオン時にパスワードを変更することをユーザーに要求するだけです。
これを、最後のセクションで作成した Contoso_AD_Module モジュールに配置します。

1. PowerShell ISE で Contoso_AD_Module.psm1 を開きます。
```PowerShell
ISE 'C:\Program Files\WindowsPowerShell\Modules\Contoso_AD_Module\Contoso_AD_Module.psm1' 
```

2. Crtl + J キーを押して、スニペット メニューを開きます。

3. "function" が見つかるまでキーを押し続けて、Enter キーを押します。
これにより、関数の極めて基本的なスケルトンが格納されます。

4. 関数の名前を「Reset-ContosoUserPassword」に変更します。  

5. いずれかのパラメーターの名前を「Identity」にし、2 つ目を削除します。

6. 以下を関数の本文にコピーします。
```PowerShell
# Get the new password
$NewPassword = Read-Host -Prompt "Enter a new password" -AsSecureString
# Reset the password
Set-ADAccountPassword -Identity $Identity -NewPassword $NewPassword -Reset
# Require the user to reset at next logon
Set-ADUser -Identity $Identity -ChangePasswordAtLogon
```

7. ファイルを保存します。
最終的に、次のようなものになります。
```PowerShell
function Reset-ContosoUserPassword ($Identity)
{
# Get the new password
$NewPassword = Read-Host -Prompt "Enter a new password" -AsSecureString
# Reset the password
Set-ADAccountPassword -Identity $Identity -NewPassword $NewPassword -Reset
# Require the user to reset at next logon
Set-ADUser -Identity $Identity -ChangePasswordAtLogon
} 
```
これで、ユーザーは `Reset-ContosoUserPassword` を簡単に呼び出すことができ、安全なインライン文字列を作成する構文を覚えて置く必要もなくなりました。

### 手順 4: ロール機能ファイルを編集する
「[ロール機能の作成](#role-capability-creation)」セクションで、空のロール機能ファイルを作成しました。
このセクションでは、このファイルに値を設定します。

ISE でロール機能ファイルを開いて開始します。
```PowerShell
ise 'C:\Program Files\WindowsPowerShell\Modules\Contoso_AD_Module\RoleCapabilities\ADHelpDesk.psrc' 
```
ファイルを以下のように変更します。
```PowerShell
# OLD: VisibleCmdlets = 'Invoke-Cmdlet1', @{ Name = 'Invoke-Cmdlet2'; Parameters = @{ Name = 'Parameter1'; ValidateSet = 'Item1', 'Item2' }, @{ Name = 'Parameter2'; ValidatePattern = 'L*' } }
VisibleCmdlets =
    'Unlock-ADAccount',
    'Search-ADAccount',
    'Enable-ADAccount',
    'Disable-ADAccount',
    @{ Name = 'Set-ADUser'; Parameters = @{ Name = 'Title'; ValidateSet = 'Manager', 'Engineer' }},
    @{ Name = 'Add-ADGroupMember'; Parameters = 
        @{Name = 'Identity'; ValidateSet = 'TestGroup'},
        @{Name = 'Members'}},
    @{ Name = 'Remove-ADGroupMember'; Parameters = 
        @{Name = 'Identity'; ValidateSet = 'TestGroup'},
        @{Name = 'Members'}}
  
# OLD: VisibleFunctions = 'Invoke-Function1', @{ Name = 'Invoke-Function2'; Parameters = @{ Name = 'Parameter1'; ValidateSet = 'Item1', 'Item2' }, @{ Name = 'Parameter2'; ValidatePattern = 'L*' } }   
VisibleFunctions = 'Reset-ContosoUserPassword'
```

ここで、いくつかの注意点があります。
1.  PowerShell は、ロール機能に必要なモジュールの自動読み込みを試行します。
モジュールが自動的に読み込まれない問題が発生した場合、ModulesToImport フィールドにモジュール名を明示的にリストする必要がある場合があります。

2.  コマンドがコマンドレットまたは関数のいずれであるか分からない場合は、`Get-Command` を実行して、CommandType を確認します。

3.  一連の使用可能値を簡単に定義できない場合は、ValidatePattern により、正規表現を使って、パラメーター引数を制限できます。
1 つのパラメーターについて ValidatePattern と ValidateSet の両方を定義することはできません。

### 手順 5: 新しいセッション構成を登録する
次に、ロール機能を JEA_NonAdmin_HelpDesk グループのメンバーに公開する新しいセッション構成ファイルを作成します。 

まず、PowerShell ISE に新しい空のセッション構成ファイルを作成して、開きます。
```PowerShell
New-PSSessionConfigurationFile -Path "$env:ProgramData\JEAConfiguration\HelpDeskDemo.pssc" 
ise "$env:ProgramData\JEAConfiguration\HelpDeskDemo.pssc"
```
PSSC ファイル内の次のフィールドを変更します。
独自の環境で作業している場合は、CONTOSO\JEA_NonAdmins_Helpdesk を自身の管理者以外のユーザーまたはグループに置き換える必要があります。
```PowerShell
# OLD: Description = ''
Description = 'An endpoint for active directory tasks.' 

# OLD: SessionType = 'Default'
SessionType = 'RestrictedRemoteServer'

# OLD: TranscriptDirectory = 'C:\Transcripts\'
TranscriptDirectory = "C:\ProgramData\JEAConfiguration\Transcripts"

# OLD: RunAsVirtualAccount = $true
RunAsVirtualAccount = $true

# OLD: RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }
RoleDefinitions = @{ 'CONTOSO\JEA_NonAdmin_HelpDesk' = @{ RoleCapabilities =  'ADHelpDesk' }} 
```
セッション構成の保存と登録
```PowerShell
Register-PSSessionConfiguration -Name ADHelpDesk -Path "$env:ProgramData\JEAConfiguration\HelpDeskDemo.pssc" 
```
### テストしてみましょう。
管理者以外のユーザー資格情報を取得します。
```PowerShell
$HelpDeskCred = Get-Credential
```
「ユーザーとグループの設定」に従っている場合、資格情報は次のようになります。
-   ユーザー名 = HelpDeskUser
-   パスワード = "pa$$w0rd"

管理者以外の資格情報を使用して AD ヘルプデスクのエンドポイントにリモート接続します。
```PowerShell
Enter-PSSession -ComputerName . -ConfigurationName ADHelpDesk -Credential $HelpDeskCred 
```
Set-ADUser を使って、ユーザーの役職をリセットします。
```PowerShell
Set-ADUser -Identity OperatorUser -Title Engineer 
```
役職が変更されていることを確認します。
```PowerShell
Get-ADUser -Identity OperatorUser -Property Title 
```
ここで、Add-ADGroupMember を使って、ユーザーを TestGroup に追加します。
注: TestGroup は事前に作成しておいてください。
```PowerShell
Add-ADGroupMember TestGroup -Member OperatorUser -Verbose 
```
セッションを終了します。
```PowerShell
Exit-PSSession
```
### 主要概念
**NoLanguage モード**: PowerShell が NoLanguage モードの場合は、ユーザーが実行できるのはコマンドのみです。言語要素は使用できません。
詳細を確認するには、`Get-Help about_Language_Modes` を実行してください。

**PowerShell 関数**: PowerShell 関数は、名前で呼び出すことのできる PowerShell コードのビットです。
詳細を確認するには、`Get-Help about_Functions` を実行してください。

**ValidateSet/ValidatePattern**: コマンドの公開時に、特定のパラメーターに有効な引数を制限できます。
ValidateSet は、有効なコマンドの特定の一覧です。
ValidatePattern は、そのパラメーターの引数が一致する必要のある正規表現です。

## 複数のコンピューターの展開と保守
この時点で、JEA をローカル システムに何回か展開しています。
運用環境はおそらく複数のコンピューターで構成されているため、展開プロセスの重要な手順に従って、各コンピューターでこれらを繰り返すことが重要です。

### 大まかな手順:
1.  モジュールを (ロール機能により) 各ノードにコピーします。
2.  セッション構成ファイルを各ノードにコピーします。
3.  セッション構成を使用して `Register-PSSessionConfiguration` を実行します。
4.  セッション構成とツールキットのコピーを安全な場所に保管します。
変更を行う際は、"信頼できる唯一の情報源" を採用することをお勧めします。

### スクリプトの例
配置のスクリプトの例を次に示します。
これを自身の環境で使用する場合、実際のファイル共有とモジュールの名前とパスを使用する必要があります。
```PowerShell
# First, copy the session configuration and modules (containing role capability files) onto a file share you have access to.
Copy-Item -Path 'C:\Demo\Demo.pssc' -Destination '\\FileShare\JEA\Demo.pssc'
Copy-Item -Path 'C:\Program Files\WindowsPowerShell\Modules\SomeModule\' -Recurse -Destination '\\FileShare\JEA\SomeModule'

# Next, author a setup script (C:\JEA\Deploy.ps1) to run on each individual node
    # Contents of C:\JEA\Deploy.ps1
    New-Item -ItemType Directory -Path C:\JEADeploy
    Copy-Item -Path '\\FileShare\JEA\Demo.pssc' -Destination 'C:\JEADeploy\'
    Copy-Item -Path '\\FileShare\JEA\SomeModule' -Recurse -Destination 'C:\Program Files\WindowsPowerShell\Modules' # Remember, Role Capability Files are found in modules
    if (Get-PSSessionConfiguration -Name JEADemo -ErrorAction SilentlyContinue)
    {
        Unregister-PSSessionConfiguration -Name JEADemo -ErrorAction Stop
    }

    Register-PSSessionConfiguration -Name JEADemo -Path 'C:\JEADeploy\Demo.pssc'
    Remove-Item -Path 'C:\JEADeploy' # Don't forget to clean up!

# Now, invoke the script on all of the target machines.
# Note: this requires PowerShell Remoting be enabled on each machine. Enabling PowerShell remoting is a requirement to use JEA as well.
# You may need to provide the "-Credential" parameter if your current user account does not have admin permissions on these machines.
Invoke-Command –ComputerName 'Node1', 'Node2', 'Node3', 'NodeN' -FilePath 'C:\JEA\Deploy.ps1'

# Finally, delete the session configuration and role capability files from the file share.
Remove-Item -Path '\\FileShare\JEA\Demo.pssc'
Remove-Item -Path '\\FileShare\JEA\SomeModule' -Recurse
```
### 機能の変更
多くのコンピューターを扱う際、一貫した方法で変更を反映させることが重要です。
JEA に DSC リソースがあれば、環境を同期することができます。
それまでは、セッション構成のマスター コピーを保持し、変更を加えるたびに再展開することを強くお勧めします。

### 機能の削除
JEA 構成をシステムから削除するには、各コンピューターで次のコマンドを使用します。
```PowerShell
Unregister-PSSessionConfiguration -Name JEADemo 
```
## JEA のレポート
JEA では権限のないユーザーでも特権コンテキストを実行できるため、ログ記録と監査が極めて重要です。
このセクションでは、ログ記録とレポートに役立つツールを実行します。

### JEA 操作のレポート
#### Over-the-Shoulder トランスクリプト
PowerShell セッションで何が行われているかその概要を取得する最も簡単な方法の 1 つとして、入力している人を覗き見ることです。
使っているコマンド、そのコマンドによる出力がわかります。何も問題はありません。
または、あったとしても、少なくとも情報を得ることができます。
PowerShell トランスクリプションは、事後的に同類のビューを提供するように設計されています。

セッション構成で TranscriptDirectory フィールドを使用した場合、PowerShell は特定のセッションで実行されたすべてのアクションのトランスクリプトを自動的に記録します。
セッションのトランスクリプトは、次のドキュメントにあります: $env:ProgramData\JEAConfiguration\Transcripts。

おわかりのとおり、トランスクリプトは "接続されているユーザー"、RunAs ユーザー、セッションで実行されたコマンドなどを記録します。
PowerShell トランスクリプションについて詳しくは、[こちらのブログ投稿](http://blogs.msdn.com/b/powershell/archive/2015/06/09/powershell-the-blue-team.aspx)をご覧ください。

#### PowerShell イベント ログ
モジュールのログ記録を有効にした場合、すべての PowerShell アクションも正規の Windows イベント ログに記録されます。
これはトランスクリプトに比べて多少扱いにくいものの、詳細な情報が提供されるため便利です。

PowerShell の操作ログでは、モジュールのログ記録を有効にしている場合、呼び出された各コマンドがイベント ID 4104 によって記録されます。

#### その他のイベント ログ
PowerShell ログおよびトランスクリプトと異なり、他のログ記録メカニズムでは "接続されているユーザー" は取得されません。
他のログと PowerShell ログの整合性を図るには、これらを相互に関連付ける必要があります。

"Windows リモート管理" 操作ログでは、イベント ID 193 により、接続しているユーザーの SID と名前に加え、RunAs 仮想アカウントの SID が記録されこの関連付けがサポートされます。
RunAs 仮想アカウントの名前の末尾に、接続しているユーザーのドメインとユーザー名が含まれていることにお気付きかもしれません。

### JEA 構成のレポート
#### Get-PSSessionConfiguration
使用している環境の状態の正確なレポートを取得するために、コンピューターにセットアップした JEA エンドポイントの数を把握しておくことが重要です。
`Get-PSSessionConfiguration`  を使用できます。
 
#### Get-PSSessionCapability
JEA エンドポイントを介して特定のユーザーの機能を手動でレポートすることは、非常に複雑になる場合があります。
いくつかのロール機能の調査が必要になる場合があります。
幸い、ここでは Get-PSSessionCapability コマンドレットを使用できます。

これをテストするには、管理者の PowerShell プロンプトから次のコマンドを実行します。
```PowerShell
Get-PSSessionCapability -Username 'CONTOSO\OperatorUser' -ConfigurationName JEADemo
```
## まとめ 
このガイドを完了すると、独自の JEA エンドポイントを作成するためのツールと知識を習得したことになります。 お読みいただきありがとうございました。

## 付録

## このガイドで使用される主要概念
**PowerShell リモート処理**: PowerShell リモート処理では、リモート コンピューターに対して PowerShell コマンドを実行できます。
1 つまたは複数のコンピューターを操作し、一時的または永続的な接続を使用することができます。
このデモでは、対話型セッションによりローカル コンピューターにリモート接続します。
JEA では、PowerShell リモート処理で使用できる機能に制限があります。
PowerShell リモート処理について詳しくは、`Get-Help about_Remote` を実行してください。

**RunAs ユーザー**: JEA を使用すると、管理者以外のユーザーが、特権 "仮想アカウント" として実行されます。
仮想アカウントは、リモート セッションの間だけ持続します。
つまり、これは、ユーザーがエンドポイントに接続したときに作成され、ユーザーがセッションを終了したときに破棄されます。
既定では、仮想アカウントは、ローカル管理者グループのメンバーです。
ドメイン コントローラーでは、Domain Admins のメンバーです。
仮想アカウントはこれらが作成されるコンピューターに対してローカルで、そのコンピューターの外では効力を持ちません。
これは、これらが Active Directory に登録されない (RID が割り当てられない) ことを意味します。
さらに、許可されたコマンド/スクリプトがローカル コンピューターの外のリソースへのアクセスを試行する場合、これは、仮想アカウント ID ではなく、コンピューターの ID を使ってこれらのリソースにアクセスします。

**"接続されている" ユーザー**: JEA エンドポイントに接続し、ロールが割り当てられる管理者以外のユーザー。
このユーザーが実行するすべてのユーザーは、RunAs または仮想アカウントのコンテキストで実行されます。


### ドメイン コントローラーの作成

このドキュメントでは、お使いのコンピューターがドメインに参加していることを前提としています。
現在ドメインに参加していない場合は、このセクションを利用して、DSC を使ってドメイン コントローラーを簡単に立ち上げることができます。

#### 前提条件

1.  コンピューターが内部ネットワークにあること
2.  コンピューターが、既存のドメインに参加していないこと
3.  コンピューターが Windows Server 2016 を実行しているか、WMF 5.0 がインストールされていること

#### xActiveDirectory のインストール
コンピューターにアクティブなインターネット接続がある場合は、管理者特権の PowerShell ウィンドウで次のコマンドを実行します。
```PowerShell
Install-Module xActiveDirectory -Force 
```
インターネット接続がない場合は、xActiveDirectory を別のコンピューターにインストールしてから、xActiveDirectory フォルダーをコンピューターの C:\Program Files\WindowsPowerShell\Modules フォルダーにコピーします。

インストールに成功したか確認するには、次のコマンドを実行します。
```PowerShell
Get-Module xActiveDirectory -ListAvailable
``` 

#### DSC を使用したドメインのセットアップ
PowerShell で次のスクリプトをコピーして、お使いのコンピューターを新しいドメインのドメイン コントローラーにします。
**著者のメモ: 指定した資格情報が使用されないという既知の問題があります。  安全のため、ローカルの管理者パスワードを忘れないように。**

```PowerShell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value $env:COMPUTERNAME -Force 

# This "MetaConfiguration" sets the DSC Engine to automatically reboot if required
[DscLocalConfigurationManager()]
Configuration MetaConfiguration
{
    Node $env:Computername
    {
        Settings
        {
            RebootNodeIfNeeded = $true
        }
    }
    
}

MetaConfiguration
# Apply the MetaConfiguration
Set-DscLocalConfigurationManager .\MetaConfiguration

# Configure a domain controller of a new "Contoso" domain
configuration DomainController
{
    param
    (
        $node,
        $cred
    )
    Import-DscResource -ModuleName xActiveDirectory

    Node $node
    {
        WindowsFeature ADDS
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain Contoso
        {
            DomainName = 'contoso.com'
            DomainAdministratorCredential = $cred
            SafemodeAdministratorPassword = $cred
            DependsOn = '[WindowsFeature]ADDS'
        }

        file temp
        {
            DestinationPath = 'C:\temp.txt'
            Contents = 'Domain has been created'
            DependsOn = '[xADDomain]Contoso'
        }
    }
}

$ConfigData = @{
    AllNodes = @(
        @{
            NodeName = $env:Computername
            PSDscAllowPlainTextPassword = $true
        }
    )
}

# Enter your desired password for the domain administrator (note, this will be stored as plain text)
DomainController -cred (Get-Credential -Message "Enter desired credential for domain administrator") -node $env:Computername -configurationData $ConfigData

# Apply the configuration to create the domain controller
Start-DSCConfiguration -path .\DomainController -ComputerName $env:Computername -Wait -Force -Verbose
```
コンピューターが数回再起動します。
ドメインが作成されたことを伝える C:\temp.txt というファイルが表示されたら、プロセスは完了しています。 

#### ユーザーとグループの設定
次のコマンドは、ドメインにオペレーターとヘルプデスクのグループ、またそのグループのメンバーである対応する管理者以外のユーザーを設定します。
```PowerShell
# Make Groups
$NonAdminOperatorGroup = New-ADGroup -Name "JEA_NonAdmin_Operator" -GroupScope DomainLocal -PassThru
$NonAdminHelpDeskGroup = New-ADGroup -Name "JEA_NonAdmin_HelpDesk" -GroupScope DomainLocal -PassThru
$TestGroup = New-ADGroup -Name "Test_Group" -GroupScope DomainLocal -PassThru

# Make Users
$OperatorUser = New-ADUser -Name "OperatorUser" -AccountPassword (ConvertTo-SecureString "pa`$`$w0rd" -AsPlainText -Force) -PassThru
Enable-ADAccount -Identity $OperatorUser

$HelpDeskUser = New-ADUser -name "HelpDeskUser" -AccountPassword (ConvertTo-SecureString "pa`$`$w0rd" -AsPlainText -Force) -PassThru
Enable-ADAccount -Identity $HelpDeskUser

# Add Users to Groups
Add-ADGroupMember -Identity $NonAdminOperatorGroup -Members $OperatorUser
Add-ADGroupMember -Identity $NonAdminHelpDeskGroup -Members $HelpDeskUser
```

### ブラックリストへの登録
JEA を一通り試したら、コマンドをブラックリストに登録できるか気になるかもしれません。
これはもっともな要求ですが、現時点では次の理由で JEA ではその予定はありません。

1.  JEA では、オペレーターの操作を、オペレーターが必要なアクションにのみ制限しています。
ブラックリストは、その対極に位置します。

2.  PowerShell コマンドの設計者は、その設計時に JEA を念頭に置いていませんでした。
Windows Server 2016 の初期インストール時には、1520 個のコマンドを直ちに使用できるようになります。
これらのコマンドの脅威モデルには、ユーザーがより特権の高いアカウントとしてコマンドを実行するようになるという可能性は含まれていませんでした。
たとえば、特定のコマンドでは、設計上のコード インジェクションが許可されます (コア PowerShell モジュールの Add-Type や Invoke-Command など)。
マイクロソフトは、認識しているコマンドが公開されると JEA により警告を表示できますが、新しい脅威モデルに基づいて Windows の他のすべてのコマンドを再評価することはしていません。
JEA を通じて公開するコマンドの機能はご自身で把握している必要があります。  

3.  また、JEA がコード インジェクションの脆弱性によりすべてのコマンドをブロックしていても、悪意のあるユーザーがブラックリストに掲載された操作を他の関連するコマンドで実行できなくなるという保証はありません。
特定の操作を確実に実行されないようにするには、公開するすべてのコマンドを理解しておくことが不可欠です。
ホワイトリストまたはブラックリストの使用の有無にかかわらず、ご自身の判断のもと、公開するコマンドを選択してください。
ブラックリストで公開されるコマンドは管理することが困難なため、JEA は代わりにホワイトリストを使って実装されます。

### コマンドの制限時の考慮事項
この手順では、考慮すべき重量な点が 1 つあります。
JEA を通じて公開されるすべての機能は、管理者によって制限された領域に配置することが重要です。
管理者以外のユーザーは、JEA エンドポイント経由で使用されるスクリプトを変更する機能を持つことはできません。

関連する注意事項として、JEA ユーザーに、その JEA セッション内で JEA 構成やホワイトリストに載ったスクリプトを上書きする権限を付与しないでください。
`Copy-Item` のようなコマンドを公開するときは十分に注意してください。

### ロール機能のよくある落とし穴
本手順の実行時に陥りやすいいくつかの落とし穴について説明します。
エンドポイントの変更時、また新規作成時にこれらの問題を特定し、対処する方法の概要を以下に紹介します。

#### 関数とコマンドレット
PowerShell で記述された PowerShell コマンドを PowerShell 関数と呼びます。
特定の .NET クラスとして記述された PowerShell コマンドは、PowerShell コマンドレットです。
コマンドの種類を確認するには、`Get-Command` を実行します。

#### VisibleProviders 
コマンドに必要なすべてのプロバイダーを公開する必要があります。
最も一般的なプロバイダーとして FileSystem プロバイダーがありますが、他に Registry プロバイダーなどの公開が必要な場合もあります。
プロバイダーの概要については、[Hey, Scripting Guy のブログ投稿](http://blogs.technet.com/b/heyscriptingguy/archive/2015/04/20/find-and-use-windows-powershell-providers.aspx)をご覧ください。
プロバイダーの公開時の注意事項: JEA セッションで直接プロバイダーを公開するより、基盤となるプロバイダーを操作する独自の関数を定義するほうが適している場合もあります。
この方法でも、ファイル、レジストリ キーなどを操作する権限や、カスタムの検証ロジックを使用して **どの*ファイルやレジストリ キーを管理するか、それらに対するコントロールをユーザーに付与できます。

<!--HONumber=Jun16_HO1-->


