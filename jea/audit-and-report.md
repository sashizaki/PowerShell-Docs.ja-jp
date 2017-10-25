---
ms.date: 2017-06-12
author: rpsqrd
ms.topic: conceptual
keywords: "JEA, PowerShell, セキュリティ"
title: "JEA の監査とレポート"
ms.openlocfilehash: 60bc7a4213c75735628207bb21078bf90f7b1ca3
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="auditing-and-reporting-on-jea"></a>JEA の監査とレポート

> 適用先: Windows PowerShell 5.0

JEA の展開後、JEA 構成を定期的に監査することが推奨されます。
JEA エンドポイントに適切なユーザーがアクセスしていること、ロールの割り当てが適切であることを確認できます。

このトピックでは、JEA エンドポイントを監査するさまざまな方法について説明します。

## <a name="find-registered-jea-sessions-on-a-machine"></a>コンピューターに登録されている JEA セッションを見つける

コンピューターに登録されている JEA セッションを確認するには、[Get-PSSessionConfiguration](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) コマンドレットを使用します。

```powershell
# Filter for sessions that are configured as 'RestrictedRemoteServer' to find JEA-like session configurations
PS C:\> Get-PSSessionConfiguration | Where-Object { $_.SessionType -eq 'RestrictedRemoteServer' }


Name          : JEAMaintenance
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : CONTOSO\JEA_DNS_ADMINS AccessAllowed, CONTOSO\JEA_DNS_OPERATORS AccessAllowed, CONTOSO\JEA_DNS_AUDITORS AccessAllowed
```

エンドポイントに対して有効な権限は "Permission" プロパティで確認できます。
これらのユーザーには、JEA エンドポイントに接続する権限が与えられますが、アクセスできるロール (さらにはコマンド) は、エンドポイントの登録に使用された[セッション構成ファイル](session-configurations.md)の "RoleDefinitions" フィールドにより決定されます。

"RoleDefinitions" プロパティのデータを展開すると、登録されている JEA エンドポイントのロール マッピングを評価できます。

```powershell
# Get the desired session configuration
$jea = Get-PSSessionConfiguration -Name 'JEAMaintenance'

# Enumerate users/groups and which roles they have access to
$jea.RoleDefinitions.GetEnumerator() | Select-Object Name, @{ Name = 'Role Capabilities'; Expression = { $_.Value.RoleCapabilities } }
```

## <a name="find-available-role-capabilities-on-the-machine"></a>コンピューターで利用できるロール機能を見つける

有効な PowerShell モジュール内の "RoleCapabilities" フォルダーに保存されている場合、ロール機能ファイルは JEA のみで利用されます。
利用可能なモジュールの一覧を検索することで、コンピューターで利用できるすべてのロール機能を見つけることができます。

```powershell
function Find-LocalRoleCapability {
    $results = @()

    # Find modules with a "RoleCapabilities" subfolder and add any PSRC files to the result set
    Get-Module -ListAvailable | ForEach-Object {
        $psrcpath = Join-Path -Path $_.ModuleBase -ChildPath 'RoleCapabilities'
        if (Test-Path $psrcpath) {
            $results += Get-ChildItem -Path $psrcpath -Filter *.psrc
        }
    }

    # Format the results nicely to make it easier to read
    $results | Select-Object @{ Name = 'Name'; Expression = { $_.Name.TrimEnd('.psrc') }}, @{ Name = 'Path'; Expression = { $_.FullName }} | Sort-Object Name
}
```

> [!NOTE]
> この関数の結果の順序は、必ずしも、複数のロール機能で同じ名前が共有されているときのロール機能の選択順に一致しません。

## <a name="check-effective-rights-for-a-specific-user"></a>特定のユーザーに対して有効な権限を確認する

JEA エンドポイントを設定したら、JEA セッションで特定のユーザーが利用できるコマンドを確認することが推奨されます。
ユーザーが現在のグループ メンバーシップで JEA セッションを開始するのであれば、[Get-PSSessionCapability](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/Get-PSSessionCapability) を利用し、ユーザーに該当するすべてのコマンドを列挙できます。
`Get-PSSessionCapability` の出力は、JEA セッションで `Get-Command -CommandType All` を実行している指定ユーザーのそれと同じになります。

```powershell
Get-PSSessionCapability -ConfigurationName 'JEAMaintenance' -Username 'CONTOSO\Alice'
```

ユーザーが、追加 JEA 権限が与えられるグループの永続的なメンバーではないとき、このコマンドレットでこれらの追加のアクセス許可が反映されない場合があります。
一般的に、Just-In-Time の特権アクセス (必要なときに必要な許可を与える) 管理システムを利用し、セキュリティ グループに一時的に属することをユーザーに許可する場合がそれに該当します。
仕事を行うために必要な最小限のコマンドだけが与えられるように、ユーザーとロール (と各ロールのコンテンツ) のマッピングを常に注意深く評価してください。

## <a name="powershell-event-logs"></a>PowerShell イベント ログ

システムでモジュールやスクリプト ブロックのログ記録を有効にしている場合、ユーザーが JEA セッションで実行したコマンドごとに、Windows イベント ログでイベントを検索できます。
イベントを検索するには、Windows イベント ビューアーを起動し、**Microsoft-Windows-PowerShell/Operational** イベント ログに移動し、イベント ID が **4104** のイベントを探します。

各イベント ログ エントリに、コマンドを実行したセッションに関する情報が含まれます。
JEA セッションの場合、これには **ConnectedUser** と **RunAsUser** に関する重要な情報が含まれます。ConnectedUser は JEA セッションを実行した実際のユーザーであり、RunAsUser はコマンドの実行に利用されたアカウント JEA を識別します。
アプリケーション イベント ログには、RunAsUser により行われた変更が表示されます。そのため、トランスクリプトまたはモジュール/スクリプトのログ記録を有効にしておくことが、コマンドの呼び出しをユーザーにさかのぼって追跡するために重要です。

## <a name="application-event-logs"></a>アプリケーション イベント ログ

外部のアプリケーションやサービスと情報を交換する JEA セッションでコマンドを実行すると、そのようなアプリケーションやサービスでは、独自のイベント ログにイベントが記録されることがあります。
PowerShell のログやトランスクリプトとは異なり、他のログ記録メカニズムでは、JEA セッションの接続ユーザーが記録されず、代わりに、仮想実行ユーザーかグループの管理されたサービス アカウントのみが記録されます。
コマンドの実行ユーザーを判断するには、[セッション トランスクリプト](#session-transcripts)を確認するか、PowerShell イベント ログと、アプリケーション イベント ログに表示されている時刻とユーザーを関連付ける必要があります。

アプリケーション イベント ログの実行ユーザーと接続ユーザーを比較するとき、WinRM ログも役に立ちます。
**Microsoft-Windows-Windows Remote Management/Operational** ログのイベント ID **193** では、JEA セッションが作成されるたびに、接続ユーザーと実行ユーザーの両方に対して、セキュリティ識別子 (SID) とアカウント名が記録されます。

## <a name="session-transcripts"></a>セッションのトランスクリプト

ユーザー セッションごとにトランスクリプトを作成するように JEA を構成した場合、すべてのユーザーのアクションのテキスト コピーが指定のフォルダーに保存されます。

すべてのトランスクリプト ディレクトリを見つけるには、JEA で構成されているコンピューターで管理者として次のコマンドを実行します。

```powershell
Get-PSSessionConfiguration | Where-Object { $_.TranscriptDirectory -ne $null } | Format-Table Name, TranscriptDirectory
```

各トランスクリプトは、セッションの開始時刻、セッションに接続したユーザー、そのユーザーに割り当てられた JEA ID に関する情報で始まります。

```
**********************
Windows PowerShell transcript start
Start time: 20160710144736
Username: CONTOSO\Alice
RunAs User: WinRM Virtual Users\WinRM VA_1_CONTOSO_Alice
Machine: SERVER01 (Microsoft Windows NT 10.0.14393.0)
[...]
```

トランスクリプトの本文には、ユーザーが実行した各コマンドに関する情報が記録されています。
ユーザーが実行したコマンドの厳密な構文は、PowerShell リモート処理のためにコマンドが変換されるため、JEA セッションでは確認できません。ただし、実行された有効なコマンドを判断することはできます。
次は、JEA セッションでユーザーが `Get-Service Dns` を実行した場合のトランスクリプト例からの抜粋です。

```
PS>CommandInvocation(Get-Service): "Get-Service"
>> ParameterBinding(Get-Service): name="Name"; value="Dns"
>> CommandInvocation(Out-Default): "Out-Default"
>> ParameterBinding(Out-Default): name="InputObject"; value="Dns"

Running  Dns                DNS Server
```

ユーザーが実行するコマンドごとに、"CommandInvocation" 行が書き込まれます。これは、ユーザーが実行したコマンドレットまたは関数を意味します。
各 CommandInvocation の後ろに ParameterBindings が続きます。これは、コマンドと共に指定された各パラメーターとその値に関する情報です。
上記の例では、"Get-Service" コマンドレットでパラメーター "Name" に値 "Dns" が指定されていることを確認できます。

各コマンドの出力も CommandInvocation をトリガーします (通常は Out-Default に)。 Out-Default の InputObject は、コマンドから返される PowerShell オブジェクトです。
そのオブジェクトの詳細が数行下に出力されています。ユーザーに表示される内容と同様のものが表示されます。

## <a name="see-also"></a>関連項目

- [JEA セッションでユーザー アクションを監査する](audit-and-report.md)
- [*PowerShell ♥ the Blue Team* のセキュリティに関するブログ投稿](https://blogs.msdn.microsoft.com/powershell/2015/06/09/powershell-the-blue-team/)

