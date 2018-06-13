---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: リモート コマンドの実行
ms.assetid: d6938b56-7dc8-44ba-b4d4-cd7b169fd74d
ms.openlocfilehash: d21d1def1e25895f65b3578bf2892d56f14cc150
ms.sourcegitcommit: 01d6985ed190a222e9da1da41596f524f607a5bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34482881"
---
# <a name="running-remote-commands"></a><span data-ttu-id="3e33b-103">リモート コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="3e33b-103">Running Remote Commands</span></span>

<span data-ttu-id="3e33b-104">1 つの Windows PowerShell コマンドを使用し、1 台から数百台のコンピューターでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-104">You can run commands on one or hundreds of computers with a single Windows PowerShell command.</span></span> <span data-ttu-id="3e33b-105">Windows PowerShell は、WMI、RPC、WS-Management など、さまざまなテクノロジを使用してリモート コンピューティングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3e33b-105">Windows PowerShell supports remote computing by using various technologies, including WMI, RPC, and WS-Management.</span></span>

## <a name="remoting-in-powershell-core"></a><span data-ttu-id="3e33b-106">PowerShell Core のリモート処理</span><span class="sxs-lookup"><span data-stu-id="3e33b-106">Remoting in PowerShell Core</span></span>

<span data-ttu-id="3e33b-107">PowerShell Core は Windows、macOS、Linux で使える PowerShell の新しいバージョンです。WMI、WS-Management、SSH リモート処理に対応しています。</span><span class="sxs-lookup"><span data-stu-id="3e33b-107">PowerShell Core, the newer edition of PowerShell on Windows, macOS, and Linux, supports WMI, WS-Management, and SSH remoting.</span></span>
<span data-ttu-id="3e33b-108">(RPC のサポートは終了しました。)</span><span class="sxs-lookup"><span data-stu-id="3e33b-108">(RPC is no longer supported.)</span></span>

<span data-ttu-id="3e33b-109">設定方法については、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e33b-109">For more information on setting this up, see:</span></span>

* <span data-ttu-id="3e33b-110">[PowerShell Core での SSH リモート処理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="3e33b-110">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
* <span data-ttu-id="3e33b-111">[PowerShell Core での WSMan リモート処理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="3e33b-111">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="remoting-without-configuration"></a><span data-ttu-id="3e33b-112">設定をしないリモート処理</span><span class="sxs-lookup"><span data-stu-id="3e33b-112">Remoting Without Configuration</span></span>

<span data-ttu-id="3e33b-113">多くの Windows PowerShell コマンドレットは、1 台以上のリモート コンピューターのデータの収集や設定の変更が可能な ComputerName パラメーターを持っています。</span><span class="sxs-lookup"><span data-stu-id="3e33b-113">Many Windows PowerShell cmdlets have the ComputerName parameter that enables you to collect data and change settings on one or more remote computers.</span></span> <span data-ttu-id="3e33b-114">Windows PowerShell がサポートするすべての Windows オペレーティング システムのさまざまな通信テクノロジや多くの作業を、特別な構成なしで利用します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-114">They use a variety of communication technologies and many work on all Windows operating systems that Windows PowerShell supports without any special configuration.</span></span>

<span data-ttu-id="3e33b-115">これらのコマンドレットには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="3e33b-115">These cmdlets include:</span></span>

* [<span data-ttu-id="3e33b-116">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="3e33b-116">Restart-Computer</span></span>](https://go.microsoft.com/fwlink/?LinkId=821625)
* [<span data-ttu-id="3e33b-117">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="3e33b-117">Test-Connection</span></span>](https://go.microsoft.com/fwlink/?LinkId=821646)
* [<span data-ttu-id="3e33b-118">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="3e33b-118">Clear-EventLog</span></span>](https://go.microsoft.com/fwlink/?LinkId=821568)
* [<span data-ttu-id="3e33b-119">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="3e33b-119">Get-EventLog</span></span>](https://go.microsoft.com/fwlink/?LinkId=821585)
* [<span data-ttu-id="3e33b-120">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="3e33b-120">Get-HotFix</span></span>](https://go.microsoft.com/fwlink/?LinkId=821586)
* [<span data-ttu-id="3e33b-121">Get-Process</span><span class="sxs-lookup"><span data-stu-id="3e33b-121">Get-Process</span></span>](https://go.microsoft.com/fwlink/?linkid=821590)
* [<span data-ttu-id="3e33b-122">Get-Service</span><span class="sxs-lookup"><span data-stu-id="3e33b-122">Get-Service</span></span>](https://go.microsoft.com/fwlink/?LinkId=821593)
* [<span data-ttu-id="3e33b-123">Set-Service</span><span class="sxs-lookup"><span data-stu-id="3e33b-123">Set-Service</span></span>](https://go.microsoft.com/fwlink/?LinkId=821633)
* [<span data-ttu-id="3e33b-124">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="3e33b-124">Get-WinEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=821529)
* [<span data-ttu-id="3e33b-125">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="3e33b-125">Get-WmiObject</span></span>](https://go.microsoft.com/fwlink/?LinkId=821595)

<span data-ttu-id="3e33b-126">通常、特別な構成なしでリモート処理をサポートするコマンドレットは、ComputerName パラメーターを指定し、Session パラメーター必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3e33b-126">Typically, cmdlets that support remoting without special configuration have the ComputerName parameter and do not have the Session parameter.</span></span> <span data-ttu-id="3e33b-127">セッションでこれらのコマンドレットを見つけるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-127">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | where { $_.parameters.keys -contains "ComputerName" -and $_.parameters.keys -notcontains "Session"}
```

## <a name="windows-powershell-remoting"></a><span data-ttu-id="3e33b-128">Windows PowerShell のリモート処理</span><span class="sxs-lookup"><span data-stu-id="3e33b-128">Windows PowerShell Remoting</span></span>

<span data-ttu-id="3e33b-129">Windows PowerShell のリモート処理では、WS-Management プロトコルを使用し、1 台以上のリモート コンピューターで Windows PowerShell コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-129">Windows PowerShell remoting, which uses the WS-Management protocol, lets you run any Windows PowerShell command on one or many remote computers.</span></span> <span data-ttu-id="3e33b-130">これにより、永続的な接続の確立、1:1 対話型のセッションの開始、および複数のコンピューターでのスクリプトの実行が可能になります。</span><span class="sxs-lookup"><span data-stu-id="3e33b-130">It lets you establish persistent connections, start 1:1 interactive sessions, and run scripts on multiple computers.</span></span>

<span data-ttu-id="3e33b-131">Windows PowerShell のリモート処理を使用するには、リモート管理のためにリモート コンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e33b-131">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span> <span data-ttu-id="3e33b-132">手順を含む詳細については、「[about_Remote_Requirements](https://technet.microsoft.com/library/dd315349.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e33b-132">For more information, including instructions, see [About Remote Requirements](https://technet.microsoft.com/library/dd315349.aspx).</span></span>

<span data-ttu-id="3e33b-133">Windows PowerShell のリモート処理を構成した後は、多くのリモート処理の戦略が使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="3e33b-133">After you have configured Windows PowerShell remoting, many remoting strategies are available to you.</span></span> <span data-ttu-id="3e33b-134">このドキュメントの残りの部分では、その一部だけを取り上げます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-134">The remainder of this document lists just a few of them.</span></span> <span data-ttu-id="3e33b-135">詳細については、[リモート コマンドに関するページ](https://technet.microsoft.com/library/dd347744.aspx)と[リモート コマンドの FAQ に関するページ](https://technet.microsoft.com/library/dd347744.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e33b-135">For more information, see [About Remote](https://technet.microsoft.com/library/dd347744.aspx) and [About Remote FAQ](https://technet.microsoft.com/library/dd347744.aspx).</span></span>

### <a name="start-an-interactive-session"></a><span data-ttu-id="3e33b-136">対話型セッションの開始</span><span class="sxs-lookup"><span data-stu-id="3e33b-136">Start an Interactive Session</span></span>

<span data-ttu-id="3e33b-137">1 台のリモート コンピューターとの対話型セッションを開始するには、[Enter-PSSession](https://go.microsoft.com/fwlink/?LinkId=821477) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-137">To start an interactive session with a single remote computer, use the [Enter-PSSession](https://go.microsoft.com/fwlink/?LinkId=821477) cmdlet.</span></span>
<span data-ttu-id="3e33b-138">たとえば、Server01 リモート コンピューターと対話型セッションを開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-138">For example, to start an interactive session with the Server01 remote computer, type:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="3e33b-139">コマンド プロンプトが、接続しているコンピューターの名前を表示するよう変更されます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-139">The command prompt changes to display the name of the computer to which you are connected.</span></span> <span data-ttu-id="3e33b-140">これ以降、プロンプトで入力したコマンドはリモート コンピューターで実行され、結果はローカル コンピューターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-140">From then on, any commands that you type at the prompt run on the remote computer and the results are displayed on the local computer.</span></span>

<span data-ttu-id="3e33b-141">対話型セッションを終了するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-141">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="3e33b-142">Enter-PSSession コマンドレットと Exit-PSSession コマンドレットの詳細については、「[Enter-PSSession](https://go.microsoft.com/fwlink/?LinkId=821477)」と「[Exit-PSSession](https://go.microsoft.com/fwlink/?LinkID=821478)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e33b-142">For more information about the Enter-PSSession and Exit-PSSession cmdlets, see [Enter-PSSession](https://go.microsoft.com/fwlink/?LinkId=821477) and [Exit-PSSession](https://go.microsoft.com/fwlink/?LinkID=821478).</span></span>

### <a name="run-a-remote-command"></a><span data-ttu-id="3e33b-143">リモート コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="3e33b-143">Run a Remote Command</span></span>

<span data-ttu-id="3e33b-144">1 台以上のリモート コンピューターでいずれかのコマンドを実行するには、[Invoke-Command](https://go.microsoft.com/fwlink/?LinkId=821493) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-144">To run any command on one or many remote computers, use the [Invoke-Command](https://go.microsoft.com/fwlink/?LinkId=821493) cmdlet.</span></span>
<span data-ttu-id="3e33b-145">たとえば、[Get-UICulture](https://go.microsoft.com/fwlink/?LinkId=821806) コマンドをリモート コンピューター Server01 と Server02 で実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-145">For example, to run a [Get-UICulture](https://go.microsoft.com/fwlink/?LinkId=821806) command on the Server01 and Server02 remote computers, type:</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-UICulture}
```

<span data-ttu-id="3e33b-146">コンピューターに出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-146">The output is returned to your computer.</span></span>

```output
LCID    Name     DisplayName               PSComputerName
----    ----     -----------               --------------
1033    en-US    English (United States)   server01.corp.fabrikam.com
1033    en-US    English (United States)   server02.corp.fabrikam.com
```

<span data-ttu-id="3e33b-147">Invoke-Command コマンドレットの詳細については、「[Invoke-Command](https://go.microsoft.com/fwlink/?LinkId=821493)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e33b-147">For more information about the Invoke-Command cmdlet, see [Invoke-Command](https://go.microsoft.com/fwlink/?LinkId=821493).</span></span>

### <a name="run-a-script"></a><span data-ttu-id="3e33b-148">スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="3e33b-148">Run a Script</span></span>

<span data-ttu-id="3e33b-149">1 台以上のリモート コンピューターでスクリプトを実行するには、Invoke-Command コマンドレットの FilePath パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-149">To run a script on one or many remote computers, use the FilePath parameter of the Invoke-Command cmdlet.</span></span> <span data-ttu-id="3e33b-150">スクリプトがローカル コンピューターでアクセス可能でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3e33b-150">The script must be on or accessible to your local computer.</span></span> <span data-ttu-id="3e33b-151">結果はローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-151">The results are returned to your local computer.</span></span>

<span data-ttu-id="3e33b-152">たとえば、次のコマンドは、リモート コンピューター Server01 と Server02 で DiskCollect.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-152">For example, the following command runs the DiskCollect.ps1 script on the Server01 and Server02 remote computers.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -FilePath c:\Scripts\DiskCollect.ps1
```

<span data-ttu-id="3e33b-153">Invoke-Command コマンドレットの詳細については、「[Invoke-Command](https://go.microsoft.com/fwlink/?LinkId=821493)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e33b-153">For more information about the Invoke-Command cmdlet, see [Invoke-Command](https://go.microsoft.com/fwlink/?LinkId=821493).</span></span>

### <a name="establish-a-persistent-connection"></a><span data-ttu-id="3e33b-154">永続的な接続の確立</span><span class="sxs-lookup"><span data-stu-id="3e33b-154">Establish a Persistent Connection</span></span>

<span data-ttu-id="3e33b-155">データを共有する一連の関連コマンドを実行するには、リモート コンピューターでセッションを作成し、Invoke-Command コマンドレットを使用して作成したセッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-155">To run a series of related commands that share data, create a session on the remote computer and then use the Invoke-Command cmdlet to run commands in the session that you create.</span></span> <span data-ttu-id="3e33b-156">リモート セッションを作成するには、New-PSSession コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-156">To create a remote session, use the New-PSSession cmdlet.</span></span>

<span data-ttu-id="3e33b-157">たとえば、次のコマンドは、コンピューター Server01 でリモート セッションを作成し、コンピューター Server02 で別のリモート セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-157">For example, the following command creates a remote session on the Server01 computer and another remote session on the Server02 computer.</span></span> <span data-ttu-id="3e33b-158">セッション オブジェクトは $s 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-158">It saves the session objects in the $s variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

<span data-ttu-id="3e33b-159">セッションが確立されたので、それらで任意のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-159">Now that the sessions are established, you can run any command in them.</span></span> <span data-ttu-id="3e33b-160">また、セッションは永続的であるため、1 つのコマンドでデータを収集し、後続のコマンドで利用することができます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-160">And because the sessions are persistent, you can collect data in one command and use it in a subsequent command.</span></span>

<span data-ttu-id="3e33b-161">たとえば、次のコマンドは $s 変数のセッションで Get-HotFix コマンドを実行し、結果を $h 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="3e33b-161">For example, the following command runs a Get-HotFix command in the sessions in the $s variable and it saves the results in the $h variable.</span></span> <span data-ttu-id="3e33b-162">$h 変数は $s のそれぞれのセッションで作成されますが、ローカル セッションには存在しません。</span><span class="sxs-lookup"><span data-stu-id="3e33b-162">The $h variable is created in each of the sessions in $s, but it does not exist in the local session.</span></span>

```powershell
Invoke-Command -Session $s {$h = Get-HotFix}
```

<span data-ttu-id="3e33b-163">これで、次のように、後続のコマンドで $h 変数のデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-163">Now you can use the data in the $h variable in subsequent commands, such as the following one.</span></span> <span data-ttu-id="3e33b-164">結果はローカル コンピューターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-164">The results are displayed on the local computer.</span></span>

```powershell
Invoke-Command -Session $s {$h | where {$_.InstalledBy -ne "NTAUTHORITY\SYSTEM"}}
```

### <a name="advanced-remoting"></a><span data-ttu-id="3e33b-165">高度なリモート処理</span><span class="sxs-lookup"><span data-stu-id="3e33b-165">Advanced Remoting</span></span>

<span data-ttu-id="3e33b-166">Windows PowerShell のリモート管理はこれだけではありません。</span><span class="sxs-lookup"><span data-stu-id="3e33b-166">Windows PowerShell remote management just begins here.</span></span> <span data-ttu-id="3e33b-167">Windows PowerShell と共にインストールされるコマンドレットを使用して、ローカルとリモートの両側からのリモート セッションの確立と構成、カスタマイズおよび制限されたセッションの作成、リモート セッションで実際に暗黙的に実行されるコマンドのリモート セッションからのユーザーによるインポート、リモート セッションのセキュリティの構成など、さまざまな処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-167">By using the cmdlets installed with Windows PowerShell, you can establish and configure remote sessions both from the local and remote ends, create customized and restricted sessions, allow users to import commands from a remote session that actually run implicitly on the remote session, configure the security of a remote session, and much more.</span></span>

<span data-ttu-id="3e33b-168">リモートの構成を容易にするために、Windows PowerShell には WSMan プロバイダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-168">To facilitate remote configuration, Windows PowerShell includes a WSMan provider.</span></span> <span data-ttu-id="3e33b-169">プロバイダーが作成する WSMAN: ドライブでは、ローカル コンピューターとリモート コンピューターの構成設定の階層内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="3e33b-169">The WSMAN: drive that the provider creates lets you navigate through a hierarchy of configuration settings on the local computer and remote computers.</span></span>
<span data-ttu-id="3e33b-170">WSMan プロバイダーの詳細については、「[WSMan Provider (WSMan プロバイダー)](https://technet.microsoft.com/library/dd819476.aspx)」および [WS-Management コマンドレットに関するページ](https://technet.microsoft.com/library/dd819481.aspx)を参照するか、Windows PowerShell コンソールで「get-help wsman」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="3e33b-170">For more information about the WSMan provider, see  [WSMan Provider](https://technet.microsoft.com/library/dd819476.aspx) and [About WS-Management Cmdlets](https://technet.microsoft.com/library/dd819481.aspx), or in the Windows PowerShell console, type "Get-Help wsman".</span></span>

<span data-ttu-id="3e33b-171">詳細については、次のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e33b-171">For more information, see:</span></span>

- [<span data-ttu-id="3e33b-172">about_Remote のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3e33b-172">About Remote FAQ</span></span>](https://technet.microsoft.com/library/dd315359.aspx)
- [<span data-ttu-id="3e33b-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="3e33b-173">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="3e33b-174">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="3e33b-174">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)

<span data-ttu-id="3e33b-175">リモート処理のエラーに関するヘルプは、「[about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e33b-175">For help with remoting errors, see [about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx).</span></span>

## <a name="see-also"></a><span data-ttu-id="3e33b-176">参照</span><span class="sxs-lookup"><span data-stu-id="3e33b-176">See Also</span></span>

- [<span data-ttu-id="3e33b-177">about_Remote</span><span class="sxs-lookup"><span data-stu-id="3e33b-177">about_Remote</span></span>](https://technet.microsoft.com/library/9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)
- [<span data-ttu-id="3e33b-178">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="3e33b-178">about_Remote_FAQ</span></span>](https://technet.microsoft.com/library/e23702fd-9415-4a98-9975-390a4d3adc42)
- [<span data-ttu-id="3e33b-179">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="3e33b-179">about_Remote_Requirements</span></span>](https://technet.microsoft.com/library/da213949-134c-4741-b307-81f4492ba1bd)
- [<span data-ttu-id="3e33b-180">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="3e33b-180">about_Remote_Troubleshooting</span></span>](https://technet.microsoft.com/library/2f890148-8578-49ed-85ea-79a489dd6317)
- [<span data-ttu-id="3e33b-181">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="3e33b-181">about_PSSessions</span></span>](https://technet.microsoft.com/library/7a9b4e0e-fa1b-47b0-92f6-6e2995d70acb)
- [<span data-ttu-id="3e33b-182">about_WS-Management_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e33b-182">about_WS-Management_Cmdlets</span></span>](https://technet.microsoft.com/library/6ed3370a-ea10-45a5-9493-696aeace27ed)
- [<span data-ttu-id="3e33b-183">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3e33b-183">Invoke-Command</span></span>](https://go.microsoft.com/fwlink/?LinkId=821493)
- [<span data-ttu-id="3e33b-184">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="3e33b-184">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)
- [<span data-ttu-id="3e33b-185">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="3e33b-185">New-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821498)
- [<span data-ttu-id="3e33b-186">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="3e33b-186">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="3e33b-187">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="3e33b-187">WSMan Provider</span></span>](https://technet.microsoft.com/library/66fe1241-e08f-49ca-832f-a84c33ca8735)

[wsman-remoting]: WSMan-Remoting-in-PowerShell-Core.md
[ssh-remoting]: SSH-Remoting-in-PowerShell-Core.md