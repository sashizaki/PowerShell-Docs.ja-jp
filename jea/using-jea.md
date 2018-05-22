---
ms.date: 06/12/2017
keywords: JEA, PowerShell, セキュリティ
title: JEA の使用
ms.openlocfilehash: 891e4be4c3fadceeff5ede7ac5cab04a5f80e5c1
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="using-jea"></a><span data-ttu-id="144f5-103">JEA の使用</span><span class="sxs-lookup"><span data-stu-id="144f5-103">Using JEA</span></span>

> <span data-ttu-id="144f5-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="144f5-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="144f5-105">このトピックでは、JEA エンドポイントに接続して使うさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="144f5-105">This topic describes the various ways you can connect to and use a JEA endpoint.</span></span>

## <a name="using-jea-interactively"></a><span data-ttu-id="144f5-106">JEA を対話的に使う</span><span class="sxs-lookup"><span data-stu-id="144f5-106">Using JEA interactively</span></span>

<span data-ttu-id="144f5-107">JEA の構成をテストする場合、またはユーザーが実行する単純なタスクがある場合は、通常の PowerShell リモート処理セッションと同じ方法で JEA を使用できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-107">If you are testing your JEA configuration or have simple tasks for users to perform, you can use JEA the same way you would a regular PowerShell remoting session.</span></span>
<span data-ttu-id="144f5-108">複雑なリモート処理タスクの場合は、代わりに[暗黙的なリモート処理](#using-jea-with-implicit-remoting)を使って、データ オブジェクトをローカルに操作することをユーザーに許可することで、ユーザーが容易にタスクを実行できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="144f5-108">For complex remoting tasks, it is recommended to use [implicit remoting](#using-jea-with-implicit-remoting) instead to make it easier for your users by allowing users to operate with the data objects locally.</span></span>

<span data-ttu-id="144f5-109">JEA を対話的に使うには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="144f5-109">To use JEA interactively, you will need:</span></span>
- <span data-ttu-id="144f5-110">接続しているコンピューターの名前 (ローカル コンピューターでもかまいません)</span><span class="sxs-lookup"><span data-stu-id="144f5-110">The name of the computer you are connecting to (can be the local machine)</span></span>
- <span data-ttu-id="144f5-111">そのコンピューターに登録されている JEA エンドポイントの名前</span><span class="sxs-lookup"><span data-stu-id="144f5-111">The name of the JEA endpoint registered on that computer</span></span>
- <span data-ttu-id="144f5-112">JEA エンドポイントにアクセスできるコンピューターの資格情報</span><span class="sxs-lookup"><span data-stu-id="144f5-112">Credentials for the computer that have access to the JEA endpoint</span></span>

<span data-ttu-id="144f5-113">以上の情報を用意した後、[New-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/New-PSSession) または [Enter-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/enter-pssession) を使って JEA セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-113">With that information in hand, you can start a JEA session using [New-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/New-PSSession) or [Enter-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/enter-pssession).</span></span>

```powershell
$nonAdminCred = Get-Credential
Enter-PSSession -ComputerName localhost -ConfigurationName JEAMaintenance -Credential $nonAdminCred
```

<span data-ttu-id="144f5-114">現在ログインに使っているアカウントに JEA エンドポイントへのアクセス権がある場合は、`-Credential` パラメーターを省略できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-114">If the account you're currently logged in as has access to the JEA endpoint, you can omit the `-Credential` parameter.</span></span>

<span data-ttu-id="144f5-115">PowerShell プロンプトが `[localhost]: PS>` に変わると、リモート JEA セッションと対話している状態であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="144f5-115">When the PowerShell prompt changes to `[localhost]: PS>` you will know that you are now interacting with the remote JEA session.</span></span>
<span data-ttu-id="144f5-116">`Get-Command` を実行して、使用できるコマンドを確認できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-116">You can run `Get-Command` to check which commands are available.</span></span>
<span data-ttu-id="144f5-117">使用できるパラメーターまたは指定できるパラメーター値に制限があるかどうか、管理者に問い合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="144f5-117">You will need to consult with your administrator to learn if there are any restrictions on the available parameters or allowable parameter values.</span></span>

<span data-ttu-id="144f5-118">JEA セッションは NoLanguage モードで動作するので、PowerShell の一般的な使い方の一部を利用できない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="144f5-118">As a reminder, JEA sessions operate in NoLanguage mode, so some of the ways you typically use PowerShell may not be available.</span></span>
<span data-ttu-id="144f5-119">たとえば、変数を使ってデータを格納したり、コマンドレットから返されたオブジェクトのプロパティを調べたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="144f5-119">For instance, you cannot use variables to store data or inspect the properties on objects returned from cmdlets.</span></span>
<span data-ttu-id="144f5-120">次の例では、今日 PowerShell を使って NoLanguage モードで動作する同じコマンドを取得する 2 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="144f5-120">The below example shows an example of how you may be using PowerShell today, and two approaches to get the same command working in NoLanguage mode.</span></span>

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

<span data-ttu-id="144f5-121">この方法が難しくなるさらに複雑なコマンド呼び出しの場合は、[暗黙的なリモート処理](#using-jea-with-implicit-remoting)を使うか、または必要な機能をラップする[カスタム関数の作成](role-capabilities.md#creating-custom-functions)を検討します。</span><span class="sxs-lookup"><span data-stu-id="144f5-121">For more complex command invocations that make this approach difficult, consider using [implicit remoting](#using-jea-with-implicit-remoting) or [creating custom functions](role-capabilities.md#creating-custom-functions) that wrap the functionality you desire.</span></span>

## <a name="using-jea-with-implicit-remoting"></a><span data-ttu-id="144f5-122">暗黙的なリモート処理での JEA の使用</span><span class="sxs-lookup"><span data-stu-id="144f5-122">Using JEA with implicit remoting</span></span>

<span data-ttu-id="144f5-123">PowerShell がサポートする代替リモート処理モデルでは、ローカル コンピューター上のリモート コンピューターからプロキシ コマンドレットをインポートして、ローカル コマンドの場合と同じように対話できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-123">PowerShell supports an alternative remoting model where you can import proxy cmdlets from a remote machine on your local computer and interact with them as if they were local commands.</span></span>
<span data-ttu-id="144f5-124">これは暗黙的なリモート処理と呼ばれ、[この *Hey, Scripting Guy!* ブログ投稿](https://blogs.technet.microsoft.com/heyscriptingguy/2013/09/08/remoting-the-implicit-way/)でわかりやすく説明されています。</span><span class="sxs-lookup"><span data-stu-id="144f5-124">This is called implicit remoting, and is explained well in [this *Hey, Scripting Guy!* blog post](https://blogs.technet.microsoft.com/heyscriptingguy/2013/09/08/remoting-the-implicit-way/).</span></span>
<span data-ttu-id="144f5-125">暗黙的なリモート処理は、全言語モードで JEA コマンドレットを使うことができるので、JEA を使う場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="144f5-125">Implicit remoting is particularly useful when working with JEA because it allows you to work with JEA cmdlets in a full language mode.</span></span>
<span data-ttu-id="144f5-126">これは、タブ補完や変数を使い、オブジェクトを操作し、ローカル スクリプトを使って、JEA エンドポイントを簡単に自動化できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="144f5-126">This means you can use tab completion, variables, manipulate objects, and even use local scripts to more easily automate against a JEA endpoint.</span></span>
<span data-ttu-id="144f5-127">プロキシ コマンドを呼び出すたびに、リモート コンピューター上の JEA エンドポイントにデータが送信されて、そこで実行されます。</span><span class="sxs-lookup"><span data-stu-id="144f5-127">Anytime you invoke a proxy command, the data will be sent to the JEA endpoint on the remote machine and executed there.</span></span>

<span data-ttu-id="144f5-128">暗黙的なリモート処理は、既存の PowerShell セッションからコマンドレットをインポートすることによって動作します。</span><span class="sxs-lookup"><span data-stu-id="144f5-128">Implicit remoting works by importing cmdlets from an existing PowerShell session.</span></span>
<span data-ttu-id="144f5-129">必要に応じて、各プロキシ コマンドレットの名詞の前に適切なプレフィックスを付けて、リモート システムに対するコマンドを区別できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-129">You can optionally choose to prefix the nouns of each proxy cmdlet with a string of your choosing to distinguish which commands are for the remote system.</span></span>
<span data-ttu-id="144f5-130">すべてのプロキシ コマンドを含む一時スクリプト モジュールが作成され、ローカル PowerShell セッションが終了するまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-130">A temporary script module containing all of the proxy commands will be created and can be used for the duration of your local PowerShell session.</span></span>

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Import the entire PSSession and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA'

# Invoke "Get-Command" on the remote JEA endpoint using the proxy cmdlet
Get-JEACommand
```

> [!IMPORTANT]
> <span data-ttu-id="144f5-131">既定の JEA コマンドレットでの制約のため、一部のシステムでは JEA セッション全体をインポートできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="144f5-131">Some systems may not be able to import an entire JEA session due to constraints in the default JEA cmdlets.</span></span>
> <span data-ttu-id="144f5-132">これを回避するには、必要なコマンドの名前を `-CommandName` パラメーターで明示的に指定することで、そのコマンドだけを JEA セッションからインポートします。</span><span class="sxs-lookup"><span data-stu-id="144f5-132">To get around this, only import the commands you need from the JEA session by explicitly providing their names to the `-CommandName` parameter.</span></span>
> <span data-ttu-id="144f5-133">今後の更新で問題が解決され、JEA セッション全体を対象システムにインポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="144f5-133">A future update will address the issue with importing entire JEA sessions on affected systems.</span></span>

<span data-ttu-id="144f5-134">既定の JEA パラメーターの制約により JEA セッションをインポートできない場合は、次の手順に従って、既定のコマンドをインポートされるセットから除外できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-134">If you are unable to import a JEA session due to constraints on the default JEA parameters, you can follow the steps below to filter out the default commands from the imported set.</span></span>
<span data-ttu-id="144f5-135">その場合でも、`Select-Object` のようなコマンドを使うことはできます。リモート バージョンの代わりにコンピューターにインストールされているローカル バージョンを JEA セッションで使うだけです。</span><span class="sxs-lookup"><span data-stu-id="144f5-135">You will still be able to use commands like `Select-Object` -- you'll just use the local version installed on your computer instead of the remote one in the JEA session.</span></span>

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

<span data-ttu-id="144f5-136">また、[Export-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.utility/Export-PSSession) を使って、暗黙的なリモート処理からプロキシされたコマンドレットを保持することもできます。</span><span class="sxs-lookup"><span data-stu-id="144f5-136">You can also persist the proxied cmdlets from implicit remoting using [Export-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.utility/Export-PSSession).</span></span>
<span data-ttu-id="144f5-137">暗黙的なリモート処理の詳細については、[Import-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.utility/import-pssession) および [Import-Module](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/import-module) のヘルプ ドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="144f5-137">For more information about implicit remoting, check out the help documentation for [Import-PSSession](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.utility/import-pssession) and [Import-Module](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/import-module).</span></span>

## <a name="using-jea-programatically"></a><span data-ttu-id="144f5-138">JEA のプログラムでの使用</span><span class="sxs-lookup"><span data-stu-id="144f5-138">Using JEA programatically</span></span>

<span data-ttu-id="144f5-139">JEA は、社内ヘルプデスク アプリや Web サイトなどのオートメーション システムやユーザー アプリケーションでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-139">JEA can also be used in automation systems and in user applications, such as in-house helpdesk apps and web sites.</span></span>
<span data-ttu-id="144f5-140">方法は制約のない PowerShell エンドポイントと対話するアプリの作成と同じですが、JEA ではリモート セッションで実行できるコマンドが制限されることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="144f5-140">The approach is the same as that for building apps that talk to unconstrained PowerShell endpoints, with the caveat that the program should be aware that JEA is limiting the commands that can be run in the remote session.</span></span>

<span data-ttu-id="144f5-141">簡単な 1 回限りのタスクでは、[Invoke-Command](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/invoke-command) コマンドを使って一連のコマンドを JEA で実行できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-141">For simple, one-off tasks, you can use [Invoke-Command](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/invoke-command) to run a set of commands using JEA.</span></span>

```powershell
Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Process; Get-Service }
```

<span data-ttu-id="144f5-142">JEA セッションに接続しているときに使用できるコマンドを確認するには、`Get-Command` を実行し、結果を反復して指定できるパラメーターを確認します。</span><span class="sxs-lookup"><span data-stu-id="144f5-142">To check which commands are available for use when you connect to a JEA session, run `Get-Command` and iterate through the results to check for the allowed parameters.</span></span>

```powershell
$allowedCommands = Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Command }
$allowedCommands | Where-Object { $_.CommandType -in 'Function', 'Cmdlet' } | Format-Table Name, Parameters
```

<span data-ttu-id="144f5-143">C# アプリを作成する場合は、[WSManConnectionInfo](https://msdn.microsoft.com/en-us/library/system.management.automation.runspaces.wsmanconnectioninfo(v=vs.85).aspx) オブジェクトで構成名を指定することにより、JEA セッションに接続する PowerShell 実行空間を作成できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-143">If you are building a C# app, you can create a PowerShell runspace that connects to a JEA session by specifying the configuration name in a [WSManConnectionInfo](https://msdn.microsoft.com/en-us/library/system.management.automation.runspaces.wsmanconnectioninfo(v=vs.85).aspx) object.</span></span>

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

## <a name="using-jea-with-powershell-direct"></a><span data-ttu-id="144f5-144">PowerShell Direct での JEA の使用</span><span class="sxs-lookup"><span data-stu-id="144f5-144">Using JEA with PowerShell Direct</span></span>

<span data-ttu-id="144f5-145">Windows 10 と Windows Server 2016 の Hyper-V には [PowerShell Direct](https://msdn.microsoft.com/en-us/virtualization/hyperv_on_windows/user_guide/vmsession) 機能があります。Hyper-V 管理者はこの機能を使用して、仮想マシンのネットワーク構成やリモート管理設定に関係なく、PowerShell で仮想マシンを管理できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-145">Hyper-V in Windows 10 and Windows Server 2016 offers [PowerShell Direct](https://msdn.microsoft.com/en-us/virtualization/hyperv_on_windows/user_guide/vmsession), a feature which allows Hyper-V administrators to manage virtual machines with PowerShell regardless of the network configuration or remote management settings on the virtual machine.</span></span>

<span data-ttu-id="144f5-146">JEA で PowerShell Direct を使うと、Hyper-V 管理者に VM への制限付きアクセスを提供できます。これは、VM へのネットワーク接続が失われ、データ センターの管理者がネットワークの設定を修正する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="144f5-146">You can use PowerShell Direct with JEA to give a Hyper-V administrator limited access to your VM, which can be useful if you lose network connectivity to your VM and need a datacenter admin to fix the network settings.</span></span>

<span data-ttu-id="144f5-147">PowerShell Direct で JEA を使うのに追加の構成は必要ありませんが、Windows 10 または Windows Server 2016 を仮想マシン内で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="144f5-147">No additional configuration is required to use JEA over PowerShell Direct, however the operating system running inside the virtual machine must be Windows 10 or Windows Server 2016.</span></span>
<span data-ttu-id="144f5-148">Hyper-V 管理者は、PSRemoting コマンドレットで `-VMName` または `-VMId` パラメーターを使って JEA エンドポイントに接続できます。</span><span class="sxs-lookup"><span data-stu-id="144f5-148">The Hyper-V admin can connect to the JEA endpoint by using the `-VMName` or `-VMId` parameters on PSRemoting cmdlets:</span></span>

```powershell
# Entering a JEA session using PowerShell Direct when the VM name is unique
Enter-PSSession -VMName 'SQL01' -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'

# Entering a JEA session using PowerShell Direct using VM ids
$vm = Get-VM -VMName 'MyVM' | Select-Object -First 1
Enter-PSSession -VMId $vm.VMId -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'
```

<span data-ttu-id="144f5-149">Hyper-V 管理者によるシステム管理用に、他の権限を持たない専用のローカル ユーザーを作成することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="144f5-149">It is strongly recommended that you create a dedicated local user with no other rights to manage the system for your Hyper-V administrators to use.</span></span>
<span data-ttu-id="144f5-150">制約のない PowerShell を使用する場合など、特権のないユーザーでも Windows コンピューターに既定でログインできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="144f5-150">Remember that even an unprivileged user can still log into a Windows machine by default, including using unconstrained PowerShell.</span></span>
<span data-ttu-id="144f5-151">これにより、ユーザーは、ファイル システム (の一部) を参照し、OS の環境について詳しく知ることができます。</span><span class="sxs-lookup"><span data-stu-id="144f5-151">That will allow them to browse (some of) the file system and learn more about your OS environment.</span></span>
<span data-ttu-id="144f5-152">Hyper-V 管理者が PowerShell Direct と JEA を使って VM だけにアクセスできるようにするには、Hyper-V 管理者の JEA アカウントへのローカル ログオン権限を禁止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="144f5-152">To lock down a Hyper-V administrator to only access a VM using PowerShell Direct with JEA, you will need to deny local logon rights to the Hyper-V admin's JEA account.</span></span>