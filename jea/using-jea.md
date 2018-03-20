---
ms.date: 2017-06-12
author: rpsqrd
ms.topic: conceptual
keywords: "JEA, PowerShell, セキュリティ"
title: "JEA の使用"
ms.openlocfilehash: f0c22bf0f823b9fafa203e7f98049a6a6b3b7c05
ms.sourcegitcommit: 99227f62dcf827354770eb2c3e95c5cf6a3118b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="using-jea"></a>JEA の使用

> 適用先: Windows PowerShell 5.0

このトピックでは、JEA エンドポイントに接続して使うさまざまな方法について説明します。

## <a name="using-jea-interactively"></a>JEA を対話的に使う

JEA の構成をテストする場合、またはユーザーが実行する単純なタスクがある場合は、通常の PowerShell リモート処理セッションと同じ方法で JEA を使用できます。
複雑なリモート処理タスクの場合は、代わりに[暗黙的なリモート処理](#using-jea-with-implicit-remoting)を使って、データ オブジェクトをローカルに操作することをユーザーに許可することで、ユーザーが容易にタスクを実行できるようにすることをお勧めします。

JEA を対話的に使うには、次のものが必要です。
- 接続しているコンピューターの名前 (ローカル コンピューターでもかまいません)
- そのコンピューターに登録されている JEA エンドポイントの名前
- JEA エンドポイントにアクセスできるコンピューターの資格情報

以上の情報を用意した後、[New-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/New-PSSession) または [Enter-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/enter-pssession) を使って JEA セッションを開始できます。

```powershell
$nonAdminCred = Get-Credential
Enter-PSSession -ComputerName localhost -ConfigurationName JEAMaintenance -Credential $nonAdminCred
```

現在ログインに使っているアカウントに JEA エンドポイントへのアクセス権がある場合は、`-Credential` パラメーターを省略できます。

PowerShell プロンプトが `[localhost]: PS>` に変わると、リモート JEA セッションと対話している状態であることがわかります。
`Get-Command` を実行して、使用できるコマンドを確認できます。
使用できるパラメーターまたは指定できるパラメーター値に制限があるかどうか、管理者に問い合わせる必要があります。

JEA セッションは NoLanguage モードで動作するので、PowerShell の一般的な使い方の一部を利用できない場合があることに注意してください。
たとえば、変数を使ってデータを格納したり、コマンドレットから返されたオブジェクトのプロパティを調べたりすることはできません。
次の例では、今日 PowerShell を使って NoLanguage モードで動作する同じコマンドを取得する 2 つの方法を示します。

```powershell
# Using variables in NoLanguage mode is disallowed, so the following will not work
# $vm = Get-VM -Name 'SQL01'
# Start-VM -VM $vm

# You can use pipes to pass data through to commands that accept input from the pipeline
Get-VM -Name 'SQL01' | Start-VM

# You can also wrap subcommands in parentheses and enter them inline as arguments
Start-VM -VM (Get-VM -Name 'SQL01')

# Better yet, use parameter sets that don't require extra data to be passed in when possible
Start-VM -VMName 'SQL01'
```

この方法が難しくなるさらに複雑なコマンド呼び出しの場合は、[暗黙的なリモート処理](#using-jea-with-implicit-remoting)を使うか、または必要な機能をラップする[カスタム関数の作成](role-capabilities.md#creating-custom-functions)を検討します。

## <a name="using-jea-with-implicit-remoting"></a>暗黙的なリモート処理での JEA の使用

PowerShell がサポートする代替リモート処理モデルでは、ローカル コンピューター上のリモート コンピューターからプロキシ コマンドレットをインポートして、ローカル コマンドの場合と同じように対話できます。
これは暗黙的なリモート処理と呼ばれ、[この *Hey, Scripting Guy!* ブログ投稿](https://blogs.technet.microsoft.com/heyscriptingguy/2013/09/08/remoting-the-implicit-way/)でわかりやすく説明されています。
暗黙的なリモート処理は、全言語モードで JEA コマンドレットを使うことができるので、JEA を使う場合に特に役立ちます。
これは、タブ補完や変数を使い、オブジェクトを操作し、ローカル スクリプトを使って、JEA エンドポイントを簡単に自動化できることを意味します。
プロキシ コマンドを呼び出すたびに、リモート コンピューター上の JEA エンドポイントにデータが送信されて、そこで実行されます。

暗黙的なリモート処理は、既存の PowerShell セッションからコマンドレットをインポートすることによって動作します。
必要に応じて、各プロキシ コマンドレットの名詞の前に適切なプレフィックスを付けて、リモート システムに対するコマンドを区別できます。
すべてのプロキシ コマンドを含む一時スクリプト モジュールが作成され、ローカル PowerShell セッションが終了するまで使用できます。

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Import the entire PSSession and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA'

# Invoke "Get-Command" on the remote JEA endpoint using the proxy cmdlet
Get-JEACommand
```

> [!IMPORTANT]
> 既定の JEA コマンドレットでの制約のため、一部のシステムでは JEA セッション全体をインポートできない場合があります。
> これを回避するには、必要なコマンドの名前を `-CommandName` パラメーターで明示的に指定することで、そのコマンドだけを JEA セッションからインポートします。
> 今後の更新で問題が解決され、JEA セッション全体を対象システムにインポートできるようになります。

既定の JEA パラメーターの制約により JEA セッションをインポートできない場合は、次の手順に従って、既定のコマンドをインポートされるセットから除外できます。
その場合でも、`Select-Object` のようなコマンドを使うことはできます。リモート バージョンの代わりにコンピューターにインストールされているローカル バージョンを JEA セッションで使うだけです。

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Get a list of all the commands on the JEA endpoint
$commands = Invoke-Command -Session $jeasession -ScriptBlock { Get-Command }

# Filter out the default cmdlets
$jeaDefaultCmdlets = 'Clear-Host', 'Exit-PSSession', 'Get-Command', 'Get-FormatData', 'Get-Help', 'Measure-Object', 'Out-Default', 'Select-Object'
$filteredCommands = $commands.Name | Where-Object { $jeaDefaultCmdlets -notcontains $_ }

# Import only commands explicitly added in role capabilities and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA' -CommandName $filteredCommands 
```

また、[Export-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.utility/Export-PSSession) を使って、暗黙的なリモート処理からプロキシされたコマンドレットを保持することもできます。
暗黙的なリモート処理の詳細については、[Import-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.utility/import-pssession) および [Import-Module](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/import-module) のヘルプ ドキュメントをご覧ください。

## <a name="using-jea-programatically"></a>JEA のプログラムでの使用

JEA は、社内ヘルプデスク アプリや Web サイトなどのオートメーション システムやユーザー アプリケーションでも使用できます。
方法は制約のない PowerShell エンドポイントと対話するアプリの作成と同じですが、JEA ではリモート セッションで実行できるコマンドが制限されることに注意する必要があります。

簡単な 1 回限りのタスクでは、[Invoke-Command](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/invoke-command) コマンドを使って一連のコマンドを JEA で実行できます。

```powershell
Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Process; Get-Service }
```

JEA セッションに接続しているときに使用できるコマンドを確認するには、`Get-Command` を実行し、結果を反復して指定できるパラメーターを確認します。

```powershell
$allowedCommands = Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Command }
$allowedCommands | Where-Object { $_.CommandType -in 'Function', 'Cmdlet' } | Format-Table Name, Parameters
```

C# アプリを作成する場合は、[WSManConnectionInfo](https://msdn.microsoft.com/en-us/library/system.management.automation.runspaces.wsmanconnectioninfo(v=vs.85).aspx) オブジェクトで構成名を指定することにより、JEA セッションに接続する PowerShell 実行空間を作成できます。

```csharp

// using System.Management.Automation;
var computerName = "SERVER01";
var configName   = "JEAMaintenance";
var creds        = // create a PSCredential object here (https://msdn.microsoft.com/en-us/library/system.management.automation.pscredential(v=vs.85).aspx)

WSManConnectionInfo connectionInfo = new WSManConnectionInfo(
                    false,                 // Use SSL
                    computerName,          // Computer name
                    5985,                  // WSMan Port
                    "/wsman",              // WSMan Path
                    string.Format(CultureInfo.InvariantCulture, "http://schemas.microsoft.com/powershell/{0}", configName),  // Connection URI with config name
                    creds);                // Credentials
// Now, use the connection info to create a runspace where you can run the commands
using (Runspace runspace = RunspaceFactory.CreateRunspace(connectionInfo))
{
    // Open the runspace
    runspace.Open();

    using (PowerShell ps = PowerShell.Create())
    {
        // Set the PowerShell object to use the JEA runspace
        ps.Runspace = runspace;

        // Now you can add and invoke commands
        ps.AddCommand("Get-Command");
        foreach (var result in ps.Invoke())
        {
            Console.WriteLine(result);
        }
    }

    // Close the runspace
    runspace.Close();
}
```

## <a name="using-jea-with-powershell-direct"></a>PowerShell Direct での JEA の使用

Windows 10 と Windows Server 2016 の Hyper-V には [PowerShell Direct](https://msdn.microsoft.com/en-us/virtualization/hyperv_on_windows/user_guide/vmsession) 機能があります。Hyper-V 管理者はこの機能を使用して、仮想マシンのネットワーク構成やリモート管理設定に関係なく、PowerShell で仮想マシンを管理できます。

JEA で PowerShell Direct を使うと、Hyper-V 管理者に VM への制限付きアクセスを提供できます。これは、VM へのネットワーク接続が失われ、データ センターの管理者がネットワークの設定を修正する必要がある場合に便利です。

PowerShell Direct で JEA を使うのに追加の構成は必要ありませんが、Windows 10 または Windows Server 2016 を仮想マシン内で実行する必要があります。
Hyper-V 管理者は、PSRemoting コマンドレットで `-VMName` または `-VMId` パラメーターを使って JEA エンドポイントに接続できます。

```powershell
# Entering a JEA session using PowerShell Direct when the VM name is unique
Enter-PSSession -VMName 'SQL01' -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'

# Entering a JEA session using PowerShell Direct using VM ids
$vm = Get-VM -VMName 'MyVM' | Select-Object -First 1
Enter-PSSession -VMId $vm.VMId -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'
```

Hyper-V 管理者によるシステム管理用に、他の権限を持たない専用のローカル ユーザーを作成することを強くお勧めします。
制約のない PowerShell を使用する場合など、特権のないユーザーでも Windows コンピューターに既定でログインできることに注意してください。
これにより、ユーザーは、ファイル システム (の一部) を参照し、OS の環境について詳しく知ることができます。
Hyper-V 管理者が PowerShell Direct と JEA を使って VM だけにアクセスできるようにするには、Hyper-V 管理者の JEA アカウントへのローカル ログオン権限を禁止する必要があります。

