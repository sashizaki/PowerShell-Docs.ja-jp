---
ms.date: 08/21/2020
keywords: powershell,コマンドレット
title: リモート コマンドの実行
description: PowerShell を使用してリモート システムでコマンドを実行する方法について説明します。
ms.openlocfilehash: e9e07fec96cbd93d3bf06be2a1f98ec7aa7d8f19
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501356"
---
# <a name="running-remote-commands"></a><span data-ttu-id="44884-104">リモート コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="44884-104">Running Remote Commands</span></span>

<span data-ttu-id="44884-105">1 つの PowerShell コマンドを使用し、1 台から数百台のコンピューターでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="44884-105">You can run commands on one or hundreds of computers with a single PowerShell command.</span></span> <span data-ttu-id="44884-106">Windows PowerShell は、WMI、RPC、WS-Management など、さまざまなテクノロジを使用してリモート コンピューティングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="44884-106">Windows PowerShell supports remote computing by using various technologies, including WMI, RPC, and WS-Management.</span></span>

<span data-ttu-id="44884-107">PowerShell Core では、WMI、WS-Management、および SSH リモート処理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="44884-107">PowerShell Core supports WMI, WS-Management, and SSH remoting.</span></span> <span data-ttu-id="44884-108">PowerShell 6 では、RPC はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="44884-108">In PowerShell 6, RPC is no longer supported.</span></span> <span data-ttu-id="44884-109">PowerShell 7 以降では、RPC は Windows でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="44884-109">In PowerShell 7 and above, RPC is supported only in Windows.</span></span>

<span data-ttu-id="44884-110">PowerShell Core でのリモート処理の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44884-110">For more information about remoting in PowerShell Core, see the following articles:</span></span>

- <span data-ttu-id="44884-111">[PowerShell Core での SSH リモート処理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="44884-111">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="44884-112">[PowerShell Core での WSMan リモート処理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="44884-112">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="windows-powershell-remoting-without-configuration"></a><span data-ttu-id="44884-113">構成なしでの Windows PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="44884-113">Windows PowerShell Remoting Without Configuration</span></span>

<span data-ttu-id="44884-114">多くの Windows PowerShell コマンドレットは、1 台以上のリモート コンピューターのデータの収集や設定の変更が可能な ComputerName パラメーターを持っています。</span><span class="sxs-lookup"><span data-stu-id="44884-114">Many Windows PowerShell cmdlets have the ComputerName parameter that enables you to collect data and change settings on one or more remote computers.</span></span> <span data-ttu-id="44884-115">これらのコマンドレットは、さまざまな通信プロトコルを使用して、特別な構成を行わなくてもすべての Windows オペレーティング システム上で動作します。</span><span class="sxs-lookup"><span data-stu-id="44884-115">These cmdlets use varying communication protocols and work on all Windows operating systems without any special configuration.</span></span>

<span data-ttu-id="44884-116">これらのコマンドレットには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="44884-116">These cmdlets include:</span></span>

- [<span data-ttu-id="44884-117">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="44884-117">Restart-Computer</span></span>](/powershell/module/microsoft.powershell.management/restart-computer)
- [<span data-ttu-id="44884-118">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="44884-118">Test-Connection</span></span>](/powershell/module/microsoft.powershell.management/test-connection)
- [<span data-ttu-id="44884-119">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="44884-119">Clear-EventLog</span></span>](/powershell/module/microsoft.powershell.management/clear-eventlog)
- [<span data-ttu-id="44884-120">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="44884-120">Get-EventLog</span></span>](/powershell/module/microsoft.powershell.management/get-eventlog)
- [<span data-ttu-id="44884-121">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="44884-121">Get-HotFix</span></span>](/powershell/module/microsoft.powershell.management/get-hotfix)
- [<span data-ttu-id="44884-122">Get-Process</span><span class="sxs-lookup"><span data-stu-id="44884-122">Get-Process</span></span>](/powershell/module/microsoft.powershell.management/get-process)
- [<span data-ttu-id="44884-123">Get-Service</span><span class="sxs-lookup"><span data-stu-id="44884-123">Get-Service</span></span>](/powershell/module/microsoft.powershell.management/get-service)
- [<span data-ttu-id="44884-124">Set-Service</span><span class="sxs-lookup"><span data-stu-id="44884-124">Set-Service</span></span>](/powershell/module/microsoft.powershell.management/set-service)
- [<span data-ttu-id="44884-125">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="44884-125">Get-WinEvent</span></span>](/powershell/module/microsoft.powershell.diagnostics/get-winevent)
- [<span data-ttu-id="44884-126">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="44884-126">Get-WmiObject</span></span>](/powershell/module/microsoft.powershell.management/get-wmiobject)

<span data-ttu-id="44884-127">通常、特別な構成なしでリモート処理をサポートするコマンドレットは、ComputerName パラメーターを指定し、Session パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="44884-127">Typically, cmdlets that support remoting without special configuration have the ComputerName parameter and don't have the Session parameter.</span></span> <span data-ttu-id="44884-128">セッションでこれらのコマンドレットを見つけるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="44884-128">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | where { $_.parameters.keys -contains "ComputerName" -and $_.parameters.keys -notcontains "Session"}
```

## <a name="windows-powershell-remoting"></a><span data-ttu-id="44884-129">Windows PowerShell のリモート処理</span><span class="sxs-lookup"><span data-stu-id="44884-129">Windows PowerShell Remoting</span></span>

<span data-ttu-id="44884-130">Windows PowerShell リモート処理では、WS-Management プロトコルを使用して、1 台以上のリモート コンピューターで Windows PowerShell コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="44884-130">Using the WS-Management protocol, Windows PowerShell remoting lets you run any Windows PowerShell command on one or more remote computers.</span></span> <span data-ttu-id="44884-131">永続的な接続の確立、対話型のセッションの開始、およびリモート コンピューターでのスクリプトの実行が可能です。</span><span class="sxs-lookup"><span data-stu-id="44884-131">You can establish persistent connections, start interactive sessions, and run scripts on remote computers.</span></span>

<span data-ttu-id="44884-132">Windows PowerShell のリモート処理を使用するには、リモート管理のためにリモート コンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44884-132">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span>
<span data-ttu-id="44884-133">手順を含む詳細については、「[about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44884-133">For more information, including instructions, see [About Remote Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span></span>

<span data-ttu-id="44884-134">Windows PowerShell のリモート処理を構成すると、それ以降は、多くのリモート処理の戦略が使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="44884-134">Once you have configured Windows PowerShell remoting, many remoting strategies are available to you.</span></span>
<span data-ttu-id="44884-135">この記事では、その一部のみを示します。</span><span class="sxs-lookup"><span data-stu-id="44884-135">This article lists just a few of them.</span></span> <span data-ttu-id="44884-136">詳細については、「[About Remote](/powershell/module/microsoft.powershell.core/about/about_remote)」(リモート処理について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44884-136">For more information, see [About Remote](/powershell/module/microsoft.powershell.core/about/about_remote).</span></span>

### <a name="start-an-interactive-session"></a><span data-ttu-id="44884-137">対話型セッションの開始</span><span class="sxs-lookup"><span data-stu-id="44884-137">Start an Interactive Session</span></span>

<span data-ttu-id="44884-138">1 台のリモート コンピューターとの対話型セッションを開始するには、[Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="44884-138">To start an interactive session with a single remote computer, use the [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) cmdlet.</span></span> <span data-ttu-id="44884-139">たとえば、Server01 リモート コンピューターと対話型セッションを開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="44884-139">For example, to start an interactive session with the Server01 remote computer, type:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="44884-140">コマンド プロンプトの画面が更新され、リモート コンピューターの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44884-140">The command prompt changes to display the name of the remote computer.</span></span> <span data-ttu-id="44884-141">プロンプトに入力されたコマンドはリモート コンピューターで実行され、結果はローカル コンピューターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="44884-141">Any commands that you type at the prompt run on the remote computer and the results are displayed on the local computer.</span></span>

<span data-ttu-id="44884-142">対話型セッションを終了するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="44884-142">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="44884-143">Enter-PSSession コマンドレットおよび Exit-PSSession コマンドレットの詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44884-143">For more information about the Enter-PSSession and Exit-PSSession cmdlets, see:</span></span>

- [<span data-ttu-id="44884-144">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="44884-144">Enter-PSSession</span></span>](/powershell/module/microsoft.powershell.core/enter-pssession)
- [<span data-ttu-id="44884-145">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="44884-145">Exit-PSSession</span></span>](/powershell/module/microsoft.powershell.core/exit-pssession)

### <a name="run-a-remote-command"></a><span data-ttu-id="44884-146">リモート コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="44884-146">Run a Remote Command</span></span>

<span data-ttu-id="44884-147">1 台または複数のコンピューターでコマンドを実行するには、[Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="44884-147">To run a command on one or more computers, use the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span> <span data-ttu-id="44884-148">たとえば、[Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture) コマンドをリモート コンピューター Server01 と Server02 で実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="44884-148">For example, to run a [Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture) command on the Server01 and Server02 remote computers, type:</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-UICulture}
```

<span data-ttu-id="44884-149">コンピューターに出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="44884-149">The output is returned to your computer.</span></span>

```output
LCID    Name     DisplayName               PSComputerName
----    ----     -----------               --------------
1033    en-US    English (United States)   server01.corp.fabrikam.com
1033    en-US    English (United States)   server02.corp.fabrikam.com
```

### <a name="run-a-script"></a><span data-ttu-id="44884-150">スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="44884-150">Run a Script</span></span>

<span data-ttu-id="44884-151">1 台または多数のリモート コンピューターでスクリプトを実行するには、`Invoke-Command` コマンドレットの FilePath パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="44884-151">To run a script on one or many remote computers, use the FilePath parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="44884-152">スクリプトがローカル コンピューターでアクセス可能でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="44884-152">The script must be on or accessible to your local computer.</span></span> <span data-ttu-id="44884-153">結果はローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="44884-153">The results are returned to your local computer.</span></span>

<span data-ttu-id="44884-154">たとえば、次のコマンドは、リモート コンピューター Server01 と Server02 で DiskCollect.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="44884-154">For example, the following command runs the DiskCollect.ps1 script on the remote computers, Server01 and Server02.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -FilePath c:\Scripts\DiskCollect.ps1
```

### <a name="establish-a-persistent-connection"></a><span data-ttu-id="44884-155">永続的な接続の確立</span><span class="sxs-lookup"><span data-stu-id="44884-155">Establish a Persistent Connection</span></span>

<span data-ttu-id="44884-156">`New-PSSession` コマンドレットを使用して、リモート コンピューター上に永続的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="44884-156">Use the `New-PSSession` cmdlet to create a persistent session on a remote computer.</span></span> <span data-ttu-id="44884-157">次の例では、Server01 および Server02 上にリモート セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="44884-157">The following example creates remote sessions on Server01 and Server02.</span></span> <span data-ttu-id="44884-158">セッション オブジェクトは、`$s` 変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="44884-158">The session objects are stored in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

<span data-ttu-id="44884-159">セッションが確立されたので、それらで任意のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="44884-159">Now that the sessions are established, you can run any command in them.</span></span> <span data-ttu-id="44884-160">また、セッションは永続的であるため、1 つのコマンドからデータを収集して、別のコマンドでそのデータを利用できます。</span><span class="sxs-lookup"><span data-stu-id="44884-160">And because the sessions are persistent, you can collect data from one command and use it in another command.</span></span>

<span data-ttu-id="44884-161">たとえば、次のコマンドは $s 変数のセッションで Get-HotFix コマンドを実行し、結果を $h 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="44884-161">For example, the following command runs a Get-HotFix command in the sessions in the $s variable and it saves the results in the $h variable.</span></span> <span data-ttu-id="44884-162">$h 変数は $s のそれぞれのセッションで作成されますが、ローカル セッションには存在しません。</span><span class="sxs-lookup"><span data-stu-id="44884-162">The $h variable is created in each of the sessions in $s, but it doesn't exist in the local session.</span></span>

```powershell
Invoke-Command -Session $s {$h = Get-HotFix}
```

<span data-ttu-id="44884-163">これで、同じセッション内の他のコマンドで、`$h` 変数のデータを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="44884-163">Now you can use the data in the `$h` variable with other commands in the same session.</span></span> <span data-ttu-id="44884-164">結果はローカル コンピューターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="44884-164">The results are displayed on the local computer.</span></span> <span data-ttu-id="44884-165">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="44884-165">For example:</span></span>

```powershell
Invoke-Command -Session $s {$h | where {$_.InstalledBy -ne "NTAUTHORITY\SYSTEM"}}
```

### <a name="advanced-remoting"></a><span data-ttu-id="44884-166">高度なリモート処理</span><span class="sxs-lookup"><span data-stu-id="44884-166">Advanced Remoting</span></span>

<span data-ttu-id="44884-167">Windows PowerShell のリモート管理はこれだけではありません。</span><span class="sxs-lookup"><span data-stu-id="44884-167">Windows PowerShell remote management just begins here.</span></span> <span data-ttu-id="44884-168">Windows PowerShell と共にインストールされるコマンドレットを使用して、ローカルとリモートの両側からのリモート セッションの確立と構成、カスタマイズおよび制限されたセッションの作成、リモート セッションで実際に暗黙的に実行されるコマンドのリモート セッションからのユーザーによるインポート、リモート セッションのセキュリティの構成など、さまざまな処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="44884-168">By using the cmdlets installed with Windows PowerShell, you can establish and configure remote sessions both from the local and remote ends, create customized and restricted sessions, allow users to import commands from a remote session that actually run implicitly on the remote session, configure the security of a remote session, and much more.</span></span>

<span data-ttu-id="44884-169">Windows PowerShell には、WSMan プロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44884-169">Windows PowerShell includes a WSMan provider.</span></span> <span data-ttu-id="44884-170">プロバイダーは、ローカル コンピューターとリモート コンピューターの構成設定の階層内を移動できる `WSMAN:` ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="44884-170">The provider creates a `WSMAN:` drive that lets you navigate through a hierarchy of configuration settings on the local computer and remote computers.</span></span>

<span data-ttu-id="44884-171">WSMan プロバイダーの詳細については、[WSMan Provider](https://technet.microsoft.com/library/dd819476.aspx) (WSMan プロバイダー) および [WS-Management コマンドレット関するページ](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets)を参照するか、Windows PowerShell コンソールで `Get-Help wsman` と入力してください。</span><span class="sxs-lookup"><span data-stu-id="44884-171">For more information about the WSMan provider, see [WSMan Provider](https://technet.microsoft.com/library/dd819476.aspx) and [About WS-Management Cmdlets](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets), or in the Windows PowerShell console, type `Get-Help wsman`.</span></span>

<span data-ttu-id="44884-172">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44884-172">For more information, see:</span></span>

- [<span data-ttu-id="44884-173">about_Remote のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="44884-173">About Remote FAQ</span></span>](https://technet.microsoft.com/library/dd315359.aspx)
- [<span data-ttu-id="44884-174">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="44884-174">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="44884-175">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="44884-175">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)

<span data-ttu-id="44884-176">リモート処理のエラーに関するヘルプは、「[about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44884-176">For help with remoting errors, see [about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx).</span></span>

## <a name="see-also"></a><span data-ttu-id="44884-177">参照</span><span class="sxs-lookup"><span data-stu-id="44884-177">See Also</span></span>

- [<span data-ttu-id="44884-178">about_Remote</span><span class="sxs-lookup"><span data-stu-id="44884-178">about_Remote</span></span>](https://technet.microsoft.com/library/9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)
- [<span data-ttu-id="44884-179">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="44884-179">about_Remote_FAQ</span></span>](https://technet.microsoft.com/library/e23702fd-9415-4a98-9975-390a4d3adc42)
- [<span data-ttu-id="44884-180">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="44884-180">about_Remote_Requirements</span></span>](https://technet.microsoft.com/library/da213949-134c-4741-b307-81f4492ba1bd)
- [<span data-ttu-id="44884-181">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="44884-181">about_Remote_Troubleshooting</span></span>](https://technet.microsoft.com/library/2f890148-8578-49ed-85ea-79a489dd6317)
- [<span data-ttu-id="44884-182">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="44884-182">about_PSSessions</span></span>](https://technet.microsoft.com/library/7a9b4e0e-fa1b-47b0-92f6-6e2995d70acb)
- [<span data-ttu-id="44884-183">about_WS-Management_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="44884-183">about_WS-Management_Cmdlets</span></span>](https://technet.microsoft.com/library/6ed3370a-ea10-45a5-9493-696aeace27ed)
- [<span data-ttu-id="44884-184">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="44884-184">Invoke-Command</span></span>](/powershell/module/microsoft.powershell.core/invoke-command)
- [<span data-ttu-id="44884-185">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="44884-185">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)
- [<span data-ttu-id="44884-186">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="44884-186">New-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821498)
- [<span data-ttu-id="44884-187">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="44884-187">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="44884-188">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="44884-188">WSMan Provider</span></span>](https://technet.microsoft.com/library/66fe1241-e08f-49ca-832f-a84c33ca8735)

[wsman-remoting]: WSMan-Remoting-in-PowerShell-Core.md
[ssh-remoting]: SSH-Remoting-in-PowerShell-Core.md
