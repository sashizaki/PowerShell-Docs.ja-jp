---
ms.date: 07/10/2019
keywords: JEA, PowerShell, セキュリティ
title: JEA の使用
description: この記事では、JEA エンドポイントに接続して使用できるさまざまな方法について説明します。
ms.openlocfilehash: b3d81cc0aa76549c81136e5a1a5af28df9c6fa7a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501543"
---
# <a name="using-jea"></a><span data-ttu-id="04426-104">JEA の使用</span><span class="sxs-lookup"><span data-stu-id="04426-104">Using JEA</span></span>

<span data-ttu-id="04426-105">この記事では、JEA エンドポイントに接続して使用できるさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04426-105">This article describes the various ways you can connect to and use a JEA endpoint.</span></span>

## <a name="using-jea-interactively"></a><span data-ttu-id="04426-106">JEA を対話的に使う</span><span class="sxs-lookup"><span data-stu-id="04426-106">Using JEA interactively</span></span>

<span data-ttu-id="04426-107">JEA の構成をテストする場合、またはユーザー用のシンプルなタスクがある場合は、通常の PowerShell リモート処理セッションと同じ方法で JEA を使用できます。</span><span class="sxs-lookup"><span data-stu-id="04426-107">If you're testing your JEA configuration or have simple tasks for users, you can use JEA the same way you would a regular PowerShell remoting session.</span></span> <span data-ttu-id="04426-108">複雑なリモート処理タスクには、[暗黙的なリモート処理](#using-jea-with-implicit-remoting)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04426-108">For complex remoting tasks, it's recommended to use [implicit remoting](#using-jea-with-implicit-remoting).</span></span> <span data-ttu-id="04426-109">暗黙的なリモート処理では、ユーザーがローカルでデータ オブジェクトを操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="04426-109">Implicit remoting allows users to operate with the data objects locally.</span></span>

<span data-ttu-id="04426-110">JEA を対話的に使用するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="04426-110">To use JEA interactively, you need:</span></span>

- <span data-ttu-id="04426-111">接続しているコンピューターの名前 (ローカル コンピューターにすることができます)</span><span class="sxs-lookup"><span data-stu-id="04426-111">The name of the computer you're connecting to (can be the local machine)</span></span>
- <span data-ttu-id="04426-112">そのコンピューターに登録されている JEA エンドポイントの名前</span><span class="sxs-lookup"><span data-stu-id="04426-112">The name of the JEA endpoint registered on that computer</span></span>
- <span data-ttu-id="04426-113">そのコンピューター上の JEA エンドポイントにアクセスできる資格情報</span><span class="sxs-lookup"><span data-stu-id="04426-113">Credentials that have access to the JEA endpoint on that computer</span></span>

<span data-ttu-id="04426-114">この情報を前提として、[New-PSSession](/powershell/module/microsoft.powershell.core/New-PSSession) または [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) コマンドレットを使って JEA セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="04426-114">Given that information, you can start a JEA session using the [New-PSSession](/powershell/module/microsoft.powershell.core/New-PSSession) or [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) cmdlets.</span></span>

```powershell
$nonAdminCred = Get-Credential
Enter-PSSession -ComputerName localhost -ConfigurationName JEAMaintenance -Credential $nonAdminCred
```

<span data-ttu-id="04426-115">現在のユーザー アカウントに JEA エンドポイントへのアクセス権がある場合は、**Credential** パラメーターを省略できます。</span><span class="sxs-lookup"><span data-stu-id="04426-115">If the current user account has access to the JEA endpoint, you can omit the **Credential** parameter.</span></span>

<span data-ttu-id="04426-116">PowerShell プロンプトが `[localhost]: PS>` に変わると、現在、リモート JEA セッションとやりとりしている状態であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="04426-116">When the PowerShell prompt changes to `[localhost]: PS>` you know that you're now interacting with the remote JEA session.</span></span> <span data-ttu-id="04426-117">`Get-Command` を実行して、使用できるコマンドを確認できます。</span><span class="sxs-lookup"><span data-stu-id="04426-117">You can run `Get-Command` to check which commands are available.</span></span> <span data-ttu-id="04426-118">使用できるパラメーターまたは許可されているパラメーター値に制限があるかどうかを確認するには、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="04426-118">Consult with your administrator to learn if there are any restrictions on the available parameters or allowed parameter values.</span></span>

<span data-ttu-id="04426-119">JEA セッションは NoLanguage モードで動作することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="04426-119">Remember, JEA sessions operate in NoLanguage mode.</span></span> <span data-ttu-id="04426-120">通常、お客様が使用している方法の中には、PowerShell を利用できないものがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="04426-120">Some of the ways you typically use PowerShell may not be available.</span></span> <span data-ttu-id="04426-121">たとえば、変数を使ってデータを格納したり、コマンドレットから返されたオブジェクトのプロパティを調べたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="04426-121">For instance, you can't use variables to store data or inspect the properties on objects returned from cmdlets.</span></span> <span data-ttu-id="04426-122">次の例では、NoLanguage モードで動作する同じコマンドを取得するための 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="04426-122">The following example shows two approaches to get the same commands to work in NoLanguage mode.</span></span>

```powershell
# Using variables is prohibited in NoLanguage mode. The following will not work:
# $vm = Get-VM -Name 'SQL01'
# Start-VM -VM $vm

# You can use pipes to pass data through to commands that accept input from the pipeline
Get-VM -Name 'SQL01' | Start-VM

# You can also wrap subcommands in parentheses and enter them inline as arguments
Start-VM -VM (Get-VM -Name 'SQL01')

# You can also use parameter sets that don't require extra data to be passed in
Start-VM -VMName 'SQL01'
```

<span data-ttu-id="04426-123">この方法が難しくなるさらに複雑なコマンド呼び出しの場合は、[暗黙的なリモート処理](#using-jea-with-implicit-remoting)を使用するか、または必要な機能をラップする[カスタム関数の作成](role-capabilities.md#creating-custom-functions)を検討します。</span><span class="sxs-lookup"><span data-stu-id="04426-123">For more complex command invocations that make this approach difficult, consider using [implicit remoting](#using-jea-with-implicit-remoting) or [creating custom functions](role-capabilities.md#creating-custom-functions) that wrap the functionality you require.</span></span>

## <a name="using-jea-with-implicit-remoting"></a><span data-ttu-id="04426-124">暗黙的なリモート処理での JEA の使用</span><span class="sxs-lookup"><span data-stu-id="04426-124">Using JEA with implicit remoting</span></span>

<span data-ttu-id="04426-125">PowerShell には、暗黙的なリモート処理モデルが用意されており、リモート マシンからプロキシ コマンドレットをインポートして、ローカル コマンドの場合と同じようにやりとりすることができます。</span><span class="sxs-lookup"><span data-stu-id="04426-125">PowerShell has an implicit remoting model that lets you import proxy cmdlets from a remote machine and interact with them as if they were local commands.</span></span> <span data-ttu-id="04426-126">暗黙的なリモート処理は、この **Hey, Scripting Guy!** の</span><span class="sxs-lookup"><span data-stu-id="04426-126">Implicit remoting is explained in this **Hey, Scripting Guy!**</span></span> <span data-ttu-id="04426-127">[ブログ記事](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="04426-127">[blog post](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/).</span></span>
<span data-ttu-id="04426-128">暗黙的なリモート処理は、全言語モードで JEA コマンドレットを使うことができるので、JEA を使用するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="04426-128">Implicit remoting is useful when working with JEA because it allows you to work with JEA cmdlets in a full language mode.</span></span> <span data-ttu-id="04426-129">タブ補完や変数を使用し、オブジェクトを操作し、ローカル スクリプトを使用して JEA エンドポイントに対してタスクを自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="04426-129">You can use tab completion, variables, manipulate objects, and even use local scripts to automate tasks against a JEA endpoint.</span></span> <span data-ttu-id="04426-130">プロキシ コマンドを呼び出すたびに、リモート マシン上の JEA エンドポイントにデータが送信されて、そこで実行されます。</span><span class="sxs-lookup"><span data-stu-id="04426-130">Anytime you invoke a proxy command, the data is sent to the JEA endpoint on the remote machine and executed there.</span></span>

<span data-ttu-id="04426-131">暗黙的なリモート処理は、既存の PowerShell セッションからコマンドレットをインポートすることによって動作します。</span><span class="sxs-lookup"><span data-stu-id="04426-131">Implicit remoting works by importing cmdlets from an existing PowerShell session.</span></span> <span data-ttu-id="04426-132">必要に応じて、各プロキシ コマンドレットの名詞の前に選択した文字列でプレフィックスを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="04426-132">You can optionally choose to prefix the nouns of each proxy cmdlet with a string of your choosing.</span></span> <span data-ttu-id="04426-133">プレフィックスによって、リモート システムに対するコマンドを区別することができます。</span><span class="sxs-lookup"><span data-stu-id="04426-133">The prefix allows you to distinguish the commands that are for the remote system.</span></span> <span data-ttu-id="04426-134">すべてのプロキシ コマンドを含む一時スクリプト モジュールが作成され、ローカル PowerShell セッションの間にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="04426-134">A temporary script module containing all the proxy commands is created and imported for the duration of your local PowerShell session.</span></span>

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Import the entire PSSession and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA'

# Invoke "Get-Command" on the remote JEA endpoint using the proxy cmdlet
Get-JEACommand
```

> [!IMPORTANT]
> <span data-ttu-id="04426-135">既定の JEA コマンドレットでの制約のため、一部のシステムでは JEA セッション全体をインポートできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="04426-135">Some systems may not be able to import an entire JEA session due to constraints in the default JEA cmdlets.</span></span> <span data-ttu-id="04426-136">これを回避するには、必要なコマンドの名前を `-CommandName` パラメーターで明示的に指定することで、そのコマンドだけを JEA セッションからインポートします。</span><span class="sxs-lookup"><span data-stu-id="04426-136">To get around this, only import the commands you need from the JEA session by explicitly providing their names to the `-CommandName` parameter.</span></span> <span data-ttu-id="04426-137">今後の更新で問題が解決され、JEA セッション全体を対象システムにインポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="04426-137">A future update will address the issue with importing entire JEA sessions on affected systems.</span></span>

<span data-ttu-id="04426-138">既定のパラメーターで JEA の制約があるため、JEA セッションをインポートできない場合は、次の手順に従って、既定のコマンドをインポートされるセットから除外します。</span><span class="sxs-lookup"><span data-stu-id="04426-138">If you're unable to import a JEA session because of JEA constraints on the default parameters, follow the steps below to filter out the default commands from the imported set.</span></span> <span data-ttu-id="04426-139">`Select-Object` のようなコマンドを引き続き使用できますが、リモートの JEA セッションからインポートされたものの代わりに、コンピューターにインストールされているローカル バージョンを使用するだけです。</span><span class="sxs-lookup"><span data-stu-id="04426-139">You can continue use commands like `Select-Object`, but you'll just use the local version installed on your computer instead of the one imported from the remote JEA session.</span></span>

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

<span data-ttu-id="04426-140">また、[Export-PSSession](/powershell/module/microsoft.powershell.utility/Export-PSSession) を使って、暗黙的なリモート処理からプロキシされたコマンドレットを保持することもできます。</span><span class="sxs-lookup"><span data-stu-id="04426-140">You can also persist the proxied cmdlets from implicit remoting using [Export-PSSession](/powershell/module/microsoft.powershell.utility/Export-PSSession).</span></span>
<span data-ttu-id="04426-141">暗黙的なリモート処理の詳細については、[Import-PSSession](/powershell/module/microsoft.powershell.utility/import-pssession) および [Import-Module](/powershell/module/microsoft.powershell.core/import-module) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04426-141">For more information about implicit remoting, see the documentation for [Import-PSSession](/powershell/module/microsoft.powershell.utility/import-pssession) and [Import-Module](/powershell/module/microsoft.powershell.core/import-module).</span></span>

## <a name="using-jea-programmatically"></a><span data-ttu-id="04426-142">JEA のプログラムでの使用</span><span class="sxs-lookup"><span data-stu-id="04426-142">Using JEA programmatically</span></span>

<span data-ttu-id="04426-143">JEA は、社内ヘルプデスク アプリや Web サイトなどのオートメーション システムやユーザー アプリケーションでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="04426-143">JEA can also be used in automation systems and in user applications, such as in-house helpdesk apps and websites.</span></span> <span data-ttu-id="04426-144">この方法は、制約のない PowerShell エンドポイントと通信するアプリをビルドするための方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="04426-144">The approach is the same as that for building apps that talk to unconstrained PowerShell endpoints.</span></span> <span data-ttu-id="04426-145">このプログラムは JEA によって課せられる制限を使用するように設計されていることを確実にします。</span><span class="sxs-lookup"><span data-stu-id="04426-145">Ensure the program is designed to work with limitation imposed by JEA.</span></span>

<span data-ttu-id="04426-146">シンプルな 1 回限りのタスクでは、[Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) を使って、コマンドを JEA セッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="04426-146">For simple, one-off tasks, you can use [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) to run commands in a JEA session.</span></span>

```powershell
Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Process; Get-Service }
```

<span data-ttu-id="04426-147">JEA セッションに接続しているときに使用できるコマンドを確認するには、`Get-Command` を実行し、結果を反復して指定できるパラメーターを確認します。</span><span class="sxs-lookup"><span data-stu-id="04426-147">To check which commands are available for use when you connect to a JEA session, run `Get-Command` and iterate through the results to check for the allowed parameters.</span></span>

```powershell
$allowedCommands = Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Command }
$allowedCommands | Where-Object { $_.CommandType -in 'Function', 'Cmdlet' } | Format-Table Name, Parameters
```

<span data-ttu-id="04426-148">C# アプリをビルドしている場合は、[WSManConnectionInfo](/dotnet/api/system.management.automation.runspaces.wsmanconnectioninfo) オブジェクトで構成名を指定することにより、JEA セッションに接続する PowerShell 実行空間を作成できます。</span><span class="sxs-lookup"><span data-stu-id="04426-148">If you're building a C# app, you can create a PowerShell runspace that connects to a JEA session by specifying the configuration name in a [WSManConnectionInfo](/dotnet/api/system.management.automation.runspaces.wsmanconnectioninfo) object.</span></span>

```csharp
// using System.Management.Automation;
var computerName = "SERVER01";
var configName   = "JEAMaintenance";
// See https://docs.microsoft.com/dotnet/api/system.management.automation.pscredential
var creds        = // create a PSCredential object here

WSManConnectionInfo connectionInfo = new WSManConnectionInfo(
    false,                 // Use SSL
    computerName,          // Computer name
    5985,                  // WSMan Port
    "/wsman",              // WSMan Path
                           // Connection URI with config name
    string.Format(CultureInfo.InvariantCulture, "http://schemas.microsoft.com/powershell/{0}", configName),
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

## <a name="using-jea-with-powershell-direct"></a><span data-ttu-id="04426-149">PowerShell Direct での JEA の使用</span><span class="sxs-lookup"><span data-stu-id="04426-149">Using JEA with PowerShell Direct</span></span>

<span data-ttu-id="04426-150">Windows 10 と Windows Server 2016 の Hyper-V には [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct) 機能があります。Hyper-V 管理者はこの機能を使用して、仮想マシンのネットワーク構成やリモート管理設定に関係なく、PowerShell で仮想マシンを管理できます。</span><span class="sxs-lookup"><span data-stu-id="04426-150">Hyper-V in Windows 10 and Windows Server 2016 offers [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct), a feature that allows Hyper-V administrators to manage virtual machines with PowerShell regardless of the network configuration or remote management settings on the virtual machine.</span></span>

<span data-ttu-id="04426-151">JEA と PowerShell Direct を使用して、Hyper-V 管理者にご利用の VM への制限付きアクセスを与えることができます。</span><span class="sxs-lookup"><span data-stu-id="04426-151">You can use PowerShell Direct with JEA to give a Hyper-V administrator limited access to your VM.</span></span>
<span data-ttu-id="04426-152">これは、ご利用の VM へのネットワーク接続が失われ、データセンター管理者にネットワーク設定を修正してもらう必要がある場合に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="04426-152">This can be useful if you lose network connectivity to your VM and need a datacenter admin to fix the network settings.</span></span>

<span data-ttu-id="04426-153">PowerShell Direct 経由で JEA を使用するために、追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="04426-153">No additional configuration is required to use JEA over PowerShell Direct.</span></span> <span data-ttu-id="04426-154">しかし、仮想マシン内で実行されているゲスト オペレーティング システムは、Windows 10、Windows Server 2016 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="04426-154">However, the guest operating system running inside the virtual machine must be Windows 10, Windows Server 2016, or higher.</span></span> <span data-ttu-id="04426-155">Hyper-V 管理者は、PSRemoting コマンドレットで `-VMName` または `-VMId` パラメーターを使って JEA エンドポイントに接続できます。</span><span class="sxs-lookup"><span data-stu-id="04426-155">The Hyper-V admin can connect to the JEA endpoint by using the `-VMName` or `-VMId` parameters on PSRemoting cmdlets:</span></span>

```powershell
# Entering a JEA session using PowerShell Direct when the VM name is unique
Enter-PSSession -VMName 'SQL01' -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'

# Entering a JEA session using PowerShell Direct using VM ids
$vm = Get-VM -VMName 'MyVM' | Select-Object -First 1
Enter-PSSession -VMId $vm.VMId -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'
```

<span data-ttu-id="04426-156">Hyper-V 管理者が使用するために、システムの管理に必要な最小の権限を持つ、専用のユーザー アカウントを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04426-156">It's recommended you create a dedicated user account with the minimum rights needed to manage the system for use by a Hyper-V administrator.</span></span> <span data-ttu-id="04426-157">制約のない PowerShell を使用する場合など、特権のないユーザーでも Windows コンピューターに既定でサインインできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="04426-157">Remember, even an unprivileged user can sign into a Windows machine by default, including using unconstrained PowerShell.</span></span> <span data-ttu-id="04426-158">これにより、ファイル システムを参照し、ご利用の OS 環境について詳しく知ることができます。</span><span class="sxs-lookup"><span data-stu-id="04426-158">That allows them to browse the file system and learn more about your OS environment.</span></span> <span data-ttu-id="04426-159">Hyper-V 管理者をロック ダウンし、PowerShell Direct と JEA を使用して VM だけにアクセスできるように制限するには、Hyper-V 管理者の JEA アカウントへのローカル ログオン権限を禁止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04426-159">To lock down a Hyper-V administrator and limit them to only access a VM using PowerShell Direct with JEA, you must deny local logon rights to the Hyper-V admin's JEA account.</span></span>
