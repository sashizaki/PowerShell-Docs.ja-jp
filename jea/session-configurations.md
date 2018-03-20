---
ms.date: 2017-06-12
author: rpsqrd
ms.topic: conceptual
keywords: "JEA, PowerShell, セキュリティ"
title: "JEA セッションの構成"
ms.openlocfilehash: c475a90a59d91b074f954cfb656b00142444c052
ms.sourcegitcommit: 99227f62dcf827354770eb2c3e95c5cf6a3118b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="jea-session-configurations"></a>JEA セッションの構成

> 適用先: Windows PowerShell 5.0

JEA エンドポイントは、PowerShell セッション構成ファイルを特定の方法で作成して登録することにより、システムに登録されます。
セッションの構成によって、"*誰が*" JEA エンドポイントを使用でき、どのロールにアクセスできるかが決まります。
また、JEA セッション内の任意のロールのユーザーに適用されるグローバル設定も定義できます。

このトピックでは、PowerShell セッション構成ファイルを作成し、JEA エンドポイントを登録する方法について説明します。

## <a name="create-a-session-configuration-file"></a>セッション構成ファイルを作成する

JEA エンドポイントを登録するには、そのエンドポイントを構成する方法を指定する必要があります。
ここでは多くのオプションについて考慮する必要がありますが、最も重要なものは、JEA エンドポイントにアクセスできる必要があるユーザー、そのユーザーに割り当てられるロール、JEA が内部で使用する ID、JEA エンドポイントの名前です。
これらはすべて PowerShell セッション構成ファイルで定義されており、これは .pssc 拡張子の付いた PowerShell データ ファイルです。

JEA エンドポイントのスケルトン セッション構成ファイルを作成するには、次のコマンドを実行します。

```powershell
New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\MyJEAEndpoint.pssc
```

> [!TIP]
> 既定では、スケルトン ファイルには、最も一般的な構成オプションのみが含まれます。
> 適用できるすべての設定を生成される PSSC に含めるには、`-Full` スイッチを使います。

セッション構成ファイルは、任意のテキスト エディターで開くことができます。
`-SessionType RestrictedRemoteServer` フィールドは、セッション構成がセキュリティ保護された管理のために JEA によって使われることを示します。
このようにして構成されたセッションは、[NoLanguage モード](https://technet.microsoft.com/library/dn433292.aspx)で動作し、次の 8 つの既定のコマンド (およびエイリアス) のみを使用できます。

- Clear-Host (cls、clear)
- Exit-PSSession (exsn、exit)
- Get-Command (gcm)
- Get-FormatData
- Get-Help
- Measure-Object (measure)
- Out-Default
- Select-Object (select)

PowerShell プロバイダーおよび外部プログラム (実行可能ファイル、スクリプトなど) は使用できません。

JEA セッションの構成には他にもいくつかフィールドがあります。
それについては以下のセクションで説明します。

### <a name="choose-the-jea-identity"></a>JEA ID を選択する

バックグラウンドで、接続ユーザーのコマンドの実行中に、JEA は使用する ID (アカウント) が必要です。
JEA が使う ID をセッション構成ファイルで決定します。

#### <a name="local-virtual-account"></a>ローカル仮想アカウント

この JEA エンドポイントによってサポートされるすべてのロールがローカル マシンの管理に使われ、ローカル管理者アカウントがコマンドを正常に実行するために十分である場合は、ローカル仮想アカウントを使うように JEA を構成する必要があります。
仮想アカウントは、特定のユーザーに固有の一時的なアカウントであり、PowerShell セッションの期間中にのみ存在します。
メンバー サーバーまたはワークステーションでは、仮想アカウントはローカル コンピューターの **Administrators** グループに属しており、最も多くのシステム リソースにアクセスできます。
Active Directory ドメイン コントローラーでは、仮想アカウントはドメインの **Domain Admins** グループに属しています。

```powershell
# Setting the session to use a virtual account
RunAsVirtualAccount = $true
```

セッション構成でサポートされているロールにこのような広範な権限が必要ない場合は、仮想アカウントが属するセキュリティ グループを必要に応じて指定できます。
メンバー サーバーまたはワークステーションでは、ドメインのグループではなくローカル グループからセキュリティ グループを指定する必要があります。

1 つまたは複数のセキュリティ グループを指定すると、仮想アカウントはローカル グループまたはドメイン管理者グループに属さなくなります。

```powershell
# Setting the session to use a virtual account that only belongs to the NetworkOperator and NetworkAuditor local groups
RunAsVirtualAccount = $true
RunAsVirtualAccountGroups = 'NetworkOperator', 'NetworkAuditor'
```

#### <a name="group-managed-service-account"></a>グループの管理されたサービス アカウント


JEA ユーザーが他のコンピューターや Web サービスなどのネットワーク リソースにアクセスする必要があるシナリオでは、グループ管理サービス アカウント (gMSA) の方が使うのに適した ID です。
gMSA アカウントで提供されるドメイン ID を使って、ドメイン内のコンピューター上のリソースに対する認証を行うことができます。
gMSA アカウントによって提供される権限は、アクセスするリソースによって決まります。
コンピューター/サービスの管理者が明示的に gMSA アカウントに管理者権限を付与しない限り、コンピューターまたはサービスに対する権限を自動的に持つことはありません。

```powershell
# Configure JEA sessions to use the gMSA account in the local computer's domain with the sAMAccountName of 'MyJEAgMSA'
GroupManagedServiceAccount = 'Domain\MyJEAgMSA'
```

いくつかの理由でネットワーク リソースへのアクセスが必要なときにのみ、gMSA アカウントを使う必要があります。

- すべてのユーザーが同じ実行 ID を共有しているため、gMSA アカウントを使うと、操作をユーザーまでトレースするのが困難になります。 PowerShell セッションのトランスクリプトとログを調べて、ユーザーと操作を関連付ける必要があります。

- GMSA アカウントが、接続しているユーザーがアクセスする必要のない多くのネットワーク リソースへのアクセス権を持っている場合があります。 常に最小限の特権の原則に従って、JEA セッションで有効なアクセス許可を制限してください。

> [!NOTE]
> グループ管理されたサービス アカウントは、ドメインに参加しているコンピューターにおいてのみ、Windows PowerShell 5.1 以降だけで使用できます。


#### <a name="more-information-about-run-as-users"></a>実行ユーザーに関する詳しい情報

実行 ID と、JEA セッションのセキュリティに対する実行 ID の関与の詳細については、「[security considerations](security-considerations.md)」 (JEA のセキュリティに関する考慮事項) をご覧ください。

### <a name="session-transcripts"></a>セッションのトランスクリプト

ユーザーのセッションのトランスクリプトを自動的に記録するように、JEA セッション構成ファイルを構成することをお勧めします。
PowerShell セッションのトランスクリプトには、接続しているユーザー、そのユーザーに割り当てられている実行 ID、そのユーザーによって実行されたコマンドに関する情報が含まれます。
システムに対して特定の変更を実行したユーザーを把握する必要がある監査チームに役に立ちます。

セッション構成ファイルで自動トランスクリプトを構成するには、トランスクリプトを保存するフォルダーへのパスを指定します。

```powershell
TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
```

指定するフォルダーは、その中のデータをユーザーが変更または削除できないように構成する必要があります。
トランスクリプトはローカル システム アカウントによってフォルダーに書き込まれるので、アカウントにはこのディレクトリの読み取りと書き込みのアクセス権が必要です。
標準ユーザーがこのフォルダーにアクセスできてはならず、限られた少数のセキュリティ管理者だけがトランスクリプトを監査するためにフォルダーにアクセスできる必要があります。

### <a name="user-drive"></a>ユーザー ドライブ

接続しているユーザーが、コマンドを実行するために、JEA エンドポイントとの間で双方向にファイルをコピーする必要がある場合は、セッション構成ファイルでユーザー ドライブを有効にできます。
ユーザー ドライブは、接続しているユーザーごとに固有のフォルダーにマップされた [PSDrive](https://msdn.microsoft.com/powershell/scripting/getting-started/cookbooks/managing-windows-powershell-drives) です。
このフォルダーは、ユーザーがシステムとの間でファイルをコピーするための場所として機能します。完全なファイル システムへのアクセス権は与えられず、FileSystem プロバイダーは公開されません。
ユーザー ドライブの内容は、ネットワーク接続が中断される場合に備えて、セッションの間は保持されます。

```powershell
MountUserDrive = $true
```

既定では、ユーザー ドライブを使用することで、ユーザーごとに最大 50 MB のデータを格納できます。
*UserDriveMaximumSize* フィールドで、ユーザーが使用できるデータの量を制限できます。

```powershell
# Enables the user drive with a per-user limit of 500MB (524288000 bytes)
MountUserDrive = $true
UserDriveMaximumSize = 524288000
```

ユーザー ドライブにデータを永続的に保持しないようにする場合は、システムにスケジュールされたタスクを構成して、毎晩フォルダーを自動的にクリーンアップできます。

> [!NOTE]
> ユーザー ドライブを使用できるのは、Windows PowerShell 5.1 以降のみです。

### <a name="role-definitions"></a>ロールの定義

セッション構成ファイルのロールの定義では、*ロール*への*ユーザー*のマッピングを定義します。
このフィールドに含まれるすべてのユーザーまたはグループには、登録時に JEA エンドポイントへのアクセス許可を自動的に付与されます。
各ユーザーまたはグループは、ハッシュ テーブルのキーとして含まれるのは 1 回だけですが、複数のロールを割り当てることができます。
ロール機能の名前は、ロール機能ファイルの名前から .psrc 拡張子を除いたものにする必要があります。

```powershell
RoleDefinitions = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}
```

ユーザーがロール定義の複数のグループに所属している場合、それぞれのロールのアクセス許可を付与されます。
2 つのロールで同じコマンドレットへのアクセスが許可されている場合、最も制限の少ないパラメーター セットがユーザーに付与されます。

ロール定義フィールドでローカル ユーザーまたはグループを指定する場合は、円記号の前に必ず (*localhost* や *.* ではなく) コンピューター名を指定してください。
コンピューター名を確認するには、`$env:computername` 変数を調べます。

```powershell
RoleDefinitions = @{
    'MyComputerName\MyLocalGroup' = @{ RoleCapabilities = 'DnsAuditor' }
}
```

### <a name="role-capability-search-order"></a>ロール機能の検索順序
上の例で示されているように、ロール機能はロール機能ファイルのフラット名 (拡張子を除いたファイル名) によって参照されます。
システムにおいて同じフラット名で複数のロール機能を使用できる場合、PowerShell は暗黙的な検索順序を使って有効なロール機能ファイルを選びます。
同じ名前のすべてのロール機能ファイルにアクセスできるようには**なりません**。

JEA は `$env:PSModulePath` 環境変数を使用して、ロール機能ファイルをスキャンするパスを決定します。
各パス内で、JEA は「RoleCapabilities」サブフォルダを含む有効な PowerShell モジュールを検索します。
モジュールのインポートと同様に、JEA は同じ名前のカスタム ロール機能よりも Windows に同梱されているロール機能を優先します。
他のすべての名前付け競合の優先順位は、Windows がディレクトリ内のファイルを列挙する順序 (アルファベット順とは限りません) によって決まります。
希望するファイル名と一致している、最初に検出されたロール機能ファイルが接続ユーザーに対して使われます。

2 つ以上のロール機能が同じ名前を共有していると、ロール機能の検索順序は確定的ではないため、コンピューター上のロール機能が固有の名前を持っているか確認することを**強くお勧め**します。

### <a name="conditional-access-rules"></a>条件付きアクセス規則

RoleDefinitions フィールドに含まれるすべてのユーザーとグループは、JEA エンドポイントへのアクセスを自動的に許可されます。
条件付きアクセス規則を使うと、このアクセスを調整して、ユーザーが割り当てられているロールに影響を与えない別のセキュリティ グループにユーザーが属していることを要求できます。
これは、"ジャスト イン タイム" 特権アクセス管理ソリューション、スマート カード認証、またはその他の多要素認証ソリューションを JEA と統合する場合に役立ちます。

条件付きアクセス規則は、セッション構成ファイルの RequiredGroups フィールドで定義します。
そこでは、"And" キーと "Or" キーを使って規則を作成するハッシュ テーブル (必要に応じて入れ子になっている) を指定できます。
このフィールドの活用方法について、次に例を示します。

```powershell
# Example 1: Connecting users must belong to a security group called "elevated-jea"
RequiredGroups = @{ And = 'elevated-jea' }

# Example 2: Connecting users must have signed on with 2 factor authentication or a smart card
# The 2 factor authentication group name is "2FA-logon" and the smart card group name is "smartcard-logon"
RequiredGroups = @{ Or = '2FA-logon', 'smartcard-logon' }

# Example 3: Connecting users must elevate into "elevated-jea" with their JIT system and have logged on with 2FA or a smart card
RequiredGroups = @{ And = 'elevated-jea', @{ Or = '2FA-logon', 'smartcard-logon' }}
```

> [!NOTE]
> 条件付きアクセス規則を使用できるのは、Windows PowerShell 5.1 以降のみです。

### <a name="other-properties"></a>他のプロパティ
セッション構成ファイルではロール機能ファイルで実行できるすべてのことを実行できますが、接続しているユーザーが別のコマンドにアクセスできるようにする機能だけはありません。
すべてのユーザーに特定のコマンドレット、関数、またはプロバイダーへのアクセスを許可する場合は、セッション構成ファイルで行うことができます。
セッション構成ファイルでサポートされているプロパティの一覧については、`Get-Help New-PSSessionConfigurationFile -Full` を実行してください。

## <a name="testing-a-session-configuration-file"></a>セッション構成ファイルのテスト

[Test-PSSessionConfigurationFile](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/test-pssessionconfigurationfile) コマンドレットを使って、セッション構成をテストできます。
テキスト エディターを使って手動で pssc ファイルを編集した場合は、セッション構成ファイルをテストして構文が正しいことを確認することを強くお勧めします。
セッション構成ファイルがこのテストに合格しない場合、システムに正しく登録することはできません。

## <a name="sample-session-configuration-file"></a>セッション構成ファイルのサンプル

JEA のセッション構成を作成して検証する方法を示す完全な例を次に示します。
使いやすさと読みやすさのため、作成したロール定義を `$roles` 変数に保存していることに注意してください。
ただし、必ずこのようにする必要はありません。

```powershell
$roles = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}

New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\JEAConfig.pssc -RunAsVirtualAccount -TranscriptDirectory 'C:\ProgramData\JEAConfiguration\Transcripts' -RoleDefinitions $roles -RequiredGroups @{ Or = '2FA-logon', 'smartcard-logon' }
Test-PSSessionConfigurationFile -Path .\JEAConfig.pssc # should yield True
```

## <a name="updating-session-configuration-files"></a>セッション構成ファイルの更新

ロールへのユーザーのマッピングなど、JEA セッション構成のプロパティを変更する必要がある場合は、JEA セッション構成を[登録解除](register-jea.md#unregistering-jea-configurations)してから[再登録](register-jea.md)する必要があります。
JEA セッション構成を再登録するときは、必要な変更を含む更新された PowerShell セッション構成ファイルを使います。

## <a name="next-steps"></a>次の手順

- [JEA 構成を登録する](register-jea.md)
- [ロール機能](role-capabilities.md)

