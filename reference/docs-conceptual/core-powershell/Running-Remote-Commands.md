---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "リモート コマンドの実行"
ms.assetid: d6938b56-7dc8-44ba-b4d4-cd7b169fd74d
ms.openlocfilehash: c3bf002e7a3daa5afc8219dd846145808eef3c9b
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="running-remote-commands"></a><span data-ttu-id="8988b-103">リモート コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="8988b-103">Running Remote Commands</span></span>
<span data-ttu-id="8988b-104">1 つの Windows PowerShell コマンドを使用し、1 台から数百台のコンピューターでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8988b-104">You can run commands on one or hundreds of computers with a single Windows PowerShell command.</span></span> <span data-ttu-id="8988b-105">Windows PowerShell は、WMI、RPC、WS-Management など、さまざまなテクノロジを使用してリモート コンピューティングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8988b-105">Windows PowerShell supports remote computing by using various technologies, including WMI, RPC, and WS-Management.</span></span>

## <a name="remoting-without-configuration"></a><span data-ttu-id="8988b-106">設定をしないリモート処理</span><span class="sxs-lookup"><span data-stu-id="8988b-106">Remoting Without Configuration</span></span>
<span data-ttu-id="8988b-107">多くの Windows PowerShell コマンドレットは、1 台以上のリモート コンピューターのデータの収集や設定の変更が可能な ComputerName パラメーターを持っています。</span><span class="sxs-lookup"><span data-stu-id="8988b-107">Many Windows PowerShell cmdlets have the ComputerName parameter that enables you to collect data and change settings on one or more remote computers.</span></span> <span data-ttu-id="8988b-108">Windows PowerShell がサポートするすべての Windows オペレーティング システムのさまざまな通信テクノロジや多くの作業を、特別な構成なしで利用します。</span><span class="sxs-lookup"><span data-stu-id="8988b-108">They use a variety of communication technologies and many work on all Windows operating systems that Windows PowerShell supports without any special configuration.</span></span>

<span data-ttu-id="8988b-109">これらのコマンドレットには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="8988b-109">These cmdlets include:</span></span>

- [<span data-ttu-id="8988b-110">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="8988b-110">Restart-Computer</span></span>](https://technet.microsoft.com/en-us/library/dd315301.aspx)

- [<span data-ttu-id="8988b-111">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="8988b-111">Test-Connection</span></span>](https://technet.microsoft.com/en-us/library/dd315259.aspx)

- [<span data-ttu-id="8988b-112">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="8988b-112">Clear-EventLog</span></span>](https://technet.microsoft.com/en-us/library/dd347552.aspx)

- [<span data-ttu-id="8988b-113">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="8988b-113">Get-EventLog</span></span>](https://technet.microsoft.com/en-us/library/dd315250.aspx)

- [<span data-ttu-id="8988b-114">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="8988b-114">Get-HotFix</span></span>](https://technet.microsoft.com/en-us/library/e1ef636f-5170-4675-b564-199d9ef6f101)

 -   [<span data-ttu-id="8988b-115">Get-Process</span><span class="sxs-lookup"><span data-stu-id="8988b-115">Get-Process</span></span>](https://technet.microsoft.com/en-us/library/dd347630.aspx)

- [<span data-ttu-id="8988b-116">Get-Service</span><span class="sxs-lookup"><span data-stu-id="8988b-116">Get-Service</span></span>](https://technet.microsoft.com/en-us/library/dd347591.aspx)

- [<span data-ttu-id="8988b-117">Set-Service</span><span class="sxs-lookup"><span data-stu-id="8988b-117">Set-Service</span></span>](https://technet.microsoft.com/en-us/library/dd315324.aspx)

- [<span data-ttu-id="8988b-118">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="8988b-118">Get-WinEvent</span></span>](https://technet.microsoft.com/en-us/library/dd315358.aspx)

- [<span data-ttu-id="8988b-119">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="8988b-119">Get-WmiObject</span></span>](https://technet.microsoft.com/en-us/library/dd315295.aspx)

<span data-ttu-id="8988b-120">通常、特別な構成なしでリモート処理をサポートするコマンドレットは、ComputerName パラメーターを指定し、Session パラメーター必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8988b-120">Typically, cmdlets that support remoting without special configuration have the ComputerName parameter and do not have the Session parameter.</span></span> <span data-ttu-id="8988b-121">セッションでこれらのコマンドレットを見つけるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8988b-121">To find these cmdlets in your session, type:</span></span>

```
Get-Command | where { $_.parameters.keys -contains "ComputerName" -and $_.parameters.keys -notcontains "Session"}
```

## <a name="windows-powershell-remoting"></a><span data-ttu-id="8988b-122">Windows PowerShell のリモート処理</span><span class="sxs-lookup"><span data-stu-id="8988b-122">Windows PowerShell Remoting</span></span>
<span data-ttu-id="8988b-123">Windows PowerShell のリモート処理では、WS-Management プロトコルを使用し、1 台以上のリモート コンピューターで Windows PowerShell コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8988b-123">Windows PowerShell remoting, which uses the WS-Management protocol, lets you run any Windows PowerShell command on one or many remote computers.</span></span> <span data-ttu-id="8988b-124">これにより、永続的な接続の確立、1:1 対話型のセッションの開始、および複数のコンピューターでのスクリプトの実行が可能になります。</span><span class="sxs-lookup"><span data-stu-id="8988b-124">It lets you establish persistent connections, start 1:1 interactive sessions, and run scripts on multiple computers.</span></span>

<span data-ttu-id="8988b-125">Windows PowerShell のリモート処理を使用するには、リモート管理のためにリモート コンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8988b-125">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span> <span data-ttu-id="8988b-126">手順を含む詳細については、「[about_Remote_Requirements](https://technet.microsoft.com/en-us/library/dd315349.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8988b-126">For more information, including instructions, see [About Remote Requirements](https://technet.microsoft.com/en-us/library/dd315349.aspx).</span></span>

<span data-ttu-id="8988b-127">Windows PowerShell のリモート処理を構成した後は、多くのリモート処理の戦略が使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="8988b-127">After you have configured Windows PowerShell remoting, many remoting strategies are available to you.</span></span> <span data-ttu-id="8988b-128">このドキュメントの残りの部分では、その一部だけを取り上げます。</span><span class="sxs-lookup"><span data-stu-id="8988b-128">The remainder of this document lists just a few of them.</span></span> <span data-ttu-id="8988b-129">詳細については、[リモート コマンドに関するページ](https://technet.microsoft.com/en-us/library/dd347744.aspx)と[リモート コマンドの FAQ に関するページ](https://technet.microsoft.com/en-us/library/dd347744.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8988b-129">For more information, see [About Remote](https://technet.microsoft.com/en-us/library/dd347744.aspx) and [About Remote FAQ](https://technet.microsoft.com/en-us/library/dd347744.aspx).</span></span>

### <a name="start-an-interactive-session"></a><span data-ttu-id="8988b-130">対話型セッションの開始</span><span class="sxs-lookup"><span data-stu-id="8988b-130">Start an Interactive Session</span></span>
<span data-ttu-id="8988b-131">1 台のリモート コンピューターとの対話型セッションを開始するには、[Enter-PSSession](https://technet.microsoft.com/en-us/library/dd315384.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8988b-131">To start an interactive session with a single remote computer, use the [Enter-PSSession](https://technet.microsoft.com/en-us/library/dd315384.aspx) cmdlet.</span></span> <span data-ttu-id="8988b-132">たとえば、Server01 リモート コンピューターと対話型セッションを開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8988b-132">For example, to start an interactive session with the Server01 remote computer, type:</span></span>

```
Enter-PSSession Server01
```

<span data-ttu-id="8988b-133">コマンド プロンプトが、接続しているコンピューターの名前を表示するよう変更されます。</span><span class="sxs-lookup"><span data-stu-id="8988b-133">The command prompt changes to display the name of the computer to which you are connected.</span></span> <span data-ttu-id="8988b-134">これ以降、プロンプトで入力したコマンドはリモート コンピューターで実行され、結果はローカル コンピューターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8988b-134">From then on, any commands that you type at the prompt run on the remote computer and the results are displayed on the local computer.</span></span>

<span data-ttu-id="8988b-135">対話型セッションを終了するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8988b-135">To end the interactive session, type:</span></span>

```
Exit-PSSession
```

<span data-ttu-id="8988b-136">Enter-PSSession コマンドレットと Exit-PSSession コマンドレットの詳細については、「[Enter-PSSession](https://technet.microsoft.com/en-us/library/dd315384.aspx)」と「[Exit-PSSession](https://technet.microsoft.com/en-us/library/dd315322.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8988b-136">For more information about the Enter-PSSession and Exit-PSSession cmdlets, see [Enter-PSSession](https://technet.microsoft.com/en-us/library/dd315384.aspx) and [Exit-PSSession](https://technet.microsoft.com/en-us/library/dd315322.aspx).</span></span>

### <a name="run-a-remote-command"></a><span data-ttu-id="8988b-137">リモート コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="8988b-137">Run a Remote Command</span></span>
<span data-ttu-id="8988b-138">1 台以上のリモート コンピューターでいずれかのコマンドを実行するには、[Invoke-Command](https://technet.microsoft.com/en-us/library/dd347578.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8988b-138">To run any command on one or many remote computers, use the [Invoke-Command](https://technet.microsoft.com/en-us/library/dd347578.aspx) cmdlet.</span></span>
<span data-ttu-id="8988b-139">たとえば、[Get-UICulture](https://technet.microsoft.com/en-us/library/dd347742.aspx) コマンドをリモート コンピューター Server01 と Server02 で実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8988b-139">For example, to run a [Get-UICulture](https://technet.microsoft.com/en-us/library/dd347742.aspx) command on the Server01 and Server02 remote computers, type:</span></span>

```
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-UICulture}
```

<span data-ttu-id="8988b-140">コンピューターに出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="8988b-140">The output is returned to your computer.</span></span>

```
LCID    Name     DisplayName               PSComputerName
----    ----     -----------               --------------
1033    en-US    English (United States)   server01.corp.fabrikam.com
1033    en-US    English (United States)   server02.corp.fabrikam.com
```
<span data-ttu-id="8988b-141">Invoke-Command コマンドレットの詳細については、「[Invoke-Command](https://technet.microsoft.com/en-us/library/22fd98ba-1874-492e-95a5-c069467b8462)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8988b-141">For more information about the Invoke-Command cmdlet, see [Invoke-Command](https://technet.microsoft.com/en-us/library/22fd98ba-1874-492e-95a5-c069467b8462).</span></span>

### <a name="run-a-script"></a><span data-ttu-id="8988b-142">スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="8988b-142">Run a Script</span></span>
<span data-ttu-id="8988b-143">1 台以上のリモート コンピューターでスクリプトを実行するには、Invoke-Command コマンドレットの FilePath パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8988b-143">To run a script on one or many remote computers, use the FilePath parameter of the Invoke-Command cmdlet.</span></span> <span data-ttu-id="8988b-144">スクリプトがローカル コンピューターでアクセス可能でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8988b-144">The script must be on or accessible to your local computer.</span></span> <span data-ttu-id="8988b-145">結果はローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="8988b-145">The results are returned to your local computer.</span></span>

<span data-ttu-id="8988b-146">たとえば、次のコマンドは、リモート コンピューター Server01 と Server02 で DiskCollect.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8988b-146">For example, the following command runs the DiskCollect.ps1 script on the Server01 and Server02 remote computers.</span></span>

```
Invoke-Command -ComputerName Server01, Server02 -FilePath c:\Scripts\DiskCollect.ps1
```

<span data-ttu-id="8988b-147">Invoke-Command コマンドレットの詳細については、「[Invoke-Command](https://technet.microsoft.com/en-us/library/dd347578.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8988b-147">For more information about the Invoke-Command cmdlet, see [Invoke-Command](https://technet.microsoft.com/en-us/library/dd347578.aspx).</span></span>

### <a name="establish-a-persistent-connection"></a><span data-ttu-id="8988b-148">永続的な接続の確立</span><span class="sxs-lookup"><span data-stu-id="8988b-148">Establish a Persistent Connection</span></span>
<span data-ttu-id="8988b-149">データを共有する一連の関連コマンドを実行するには、リモート コンピューターでセッションを作成し、Invoke-Command コマンドレットを使用して作成したセッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8988b-149">To run a series of related commands that share data, create a session on the remote computer and then use the Invoke-Command cmdlet to run commands in the session that you create.</span></span> <span data-ttu-id="8988b-150">リモート セッションを作成するには、New-PSSession コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8988b-150">To create a remote session, use the New-PSSession cmdlet.</span></span>

<span data-ttu-id="8988b-151">たとえば、次のコマンドは、コンピューター Server01 でリモート セッションを作成し、コンピューター Server02 で別のリモート セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8988b-151">For example, the following command creates a remote session on the Server01 computer and another remote session on the Server02 computer.</span></span> <span data-ttu-id="8988b-152">セッション オブジェクトは $s 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="8988b-152">It saves the session objects in the $s variable.</span></span>

```
$s = New-PSSession -ComputerName Server01, Server02
```

<span data-ttu-id="8988b-153">セッションが確立されたので、それらで任意のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8988b-153">Now that the sessions are established, you can run any command in them.</span></span> <span data-ttu-id="8988b-154">また、セッションは永続的であるため、1 つのコマンドでデータを収集し、後続のコマンドで利用することができます。</span><span class="sxs-lookup"><span data-stu-id="8988b-154">And because the sessions are persistent, you can collect data in one command and use it in a subsequent command.</span></span>

<span data-ttu-id="8988b-155">たとえば、次のコマンドは $s 変数のセッションで Get-HotFix コマンドを実行し、結果を $h 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="8988b-155">For example, the following command runs a Get-HotFix command in the sessions in the $s variable and it saves the results in the $h variable.</span></span> <span data-ttu-id="8988b-156">$h 変数は $s のそれぞれのセッションで作成されますが、ローカル セッションには存在しません。</span><span class="sxs-lookup"><span data-stu-id="8988b-156">The $h variable is created in each of the sessions in $s, but it does not exist in the local session.</span></span>

```
Invoke-Command -Session $s {$h = Get-HotFix}
```

<span data-ttu-id="8988b-157">これで、次のように、後続のコマンドで $h 変数のデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8988b-157">Now you can use the data in the $h variable in subsequent commands, such as the following one.</span></span> <span data-ttu-id="8988b-158">結果はローカル コンピューターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8988b-158">The results are displayed on the local computer.</span></span>

```
Invoke-Command -Session $s {$h | where {$_.InstalledBy -ne "NTAUTHORITY\SYSTEM"}}
```

### <a name="advanced-remoting"></a><span data-ttu-id="8988b-159">高度なリモート処理</span><span class="sxs-lookup"><span data-stu-id="8988b-159">Advanced Remoting</span></span>
<span data-ttu-id="8988b-160">Windows PowerShell のリモート管理はこれだけではありません。</span><span class="sxs-lookup"><span data-stu-id="8988b-160">Windows PowerShell remote management just begins here.</span></span> <span data-ttu-id="8988b-161">Windows PowerShell と共にインストールされるコマンドレットを使用して、ローカルとリモートの両側からのリモート セッションの確立と構成、カスタマイズおよび制限されたセッションの作成、リモート セッションで実際に暗黙的に実行されるコマンドのリモート セッションからのユーザーによるインポート、リモート セッションのセキュリティの構成など、さまざまな処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8988b-161">By using the cmdlets installed with Windows PowerShell, you can establish and configure remote sessions both from the local and remote ends, create customized and restricted sessions, allow users to import commands from a remote session that actually run implicitly on the remote session, configure the security of a remote session, and much more.</span></span>

<span data-ttu-id="8988b-162">リモートの構成を容易にするために、Windows PowerShell には WSMan プロバイダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8988b-162">To facilitate remote configuration, Windows PowerShell includes a WSMan provider.</span></span> <span data-ttu-id="8988b-163">プロバイダーが作成する WSMAN: ドライブでは、ローカル コンピューターとリモート コンピューターの構成設定の階層内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="8988b-163">The WSMAN: drive that the provider creates lets you navigate through a hierarchy of configuration settings on the local computer and remote computers.</span></span>
<span data-ttu-id="8988b-164">WSMan プロバイダーの詳細については、「[WSMan Provider (WSMan プロバイダー)](https://technet.microsoft.com/en-us/library/dd819476.aspx)」および [WS-Management コマンドレットに関するページ](https://technet.microsoft.com/en-us/library/dd819481.aspx)を参照するか、Windows PowerShell コンソールで「get-help wsman」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="8988b-164">For more information about the WSMan provider, see  [WSMan Provider](https://technet.microsoft.com/en-us/library/dd819476.aspx) and [About WS-Management Cmdlets](https://technet.microsoft.com/en-us/library/dd819481.aspx), or in the Windows PowerShell console, type "Get-Help wsman".</span></span>

<span data-ttu-id="8988b-165">詳細については、次のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8988b-165">For more information, see:</span></span>
- [<span data-ttu-id="8988b-166">about_Remote のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="8988b-166">About Remote FAQ</span></span>](https://technet.microsoft.com/en-us/library/dd315359.aspx)
- [<span data-ttu-id="8988b-167">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8988b-167">Register-PSSessionConfiguration</span></span>](https://technet.microsoft.com/en-us/library/dd819496.aspx)
- <span data-ttu-id="8988b-168">[Import-PSSession](https://technet.microsoft.com/en-us/library/dd347575.aspx)</span><span class="sxs-lookup"><span data-stu-id="8988b-168">[Import-PSSession](https://technet.microsoft.com/en-us/library/dd347575.aspx).</span></span> 

<span data-ttu-id="8988b-169">リモート処理のエラーに関するヘルプは、「[about_Remote_Troubleshooting](https://technet.microsoft.com/en-us/library/dd347642.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8988b-169">For help with remoting errors, see [about_Remote_Troubleshooting](https://technet.microsoft.com/en-us/library/dd347642.aspx).</span></span>

## <a name="see-also"></a><span data-ttu-id="8988b-170">参照</span><span class="sxs-lookup"><span data-stu-id="8988b-170">See Also</span></span>
- [<span data-ttu-id="8988b-171">about_Remote</span><span class="sxs-lookup"><span data-stu-id="8988b-171">about_Remote</span></span>](https://technet.microsoft.com/en-us/library/9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)
- [<span data-ttu-id="8988b-172">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="8988b-172">about_Remote_FAQ</span></span>](https://technet.microsoft.com/en-us/library/e23702fd-9415-4a98-9975-390a4d3adc42)
- [<span data-ttu-id="8988b-173">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="8988b-173">about_Remote_Requirements</span></span>](https://technet.microsoft.com/en-us/library/da213949-134c-4741-b307-81f4492ba1bd)
- [<span data-ttu-id="8988b-174">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="8988b-174">about_Remote_Troubleshooting</span></span>](https://technet.microsoft.com/en-us/library/2f890148-8578-49ed-85ea-79a489dd6317)
- [<span data-ttu-id="8988b-175">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="8988b-175">about_PSSessions</span></span>](https://technet.microsoft.com/en-us/library/7a9b4e0e-fa1b-47b0-92f6-6e2995d70acb)
- [<span data-ttu-id="8988b-176">about_WS-Management_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8988b-176">about_WS-Management_Cmdlets</span></span>](https://technet.microsoft.com/en-us/library/6ed3370a-ea10-45a5-9493-696aeace27ed)
- [<span data-ttu-id="8988b-177">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="8988b-177">Invoke-Command</span></span>](https://technet.microsoft.com/en-us/library/22fd98ba-1874-492e-95a5-c069467b8462)
- [<span data-ttu-id="8988b-178">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="8988b-178">Import-PSSession</span></span>](https://technet.microsoft.com/en-us/library/048c115e-a6fb-4e0d-8cea-c5ca24630c9d)
- [<span data-ttu-id="8988b-179">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="8988b-179">New-PSSession</span></span>](https://technet.microsoft.com/en-us/library/59452f12-a11d-4558-99ea-e6ca6ad5ffd3)
- [<span data-ttu-id="8988b-180">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8988b-180">Register-PSSessionConfiguration</span></span>](https://technet.microsoft.com/en-us/library/af68867a-d201-4b19-a1de-594015ed8a25)
- [<span data-ttu-id="8988b-181">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="8988b-181">WSMan Provider</span></span>](https://technet.microsoft.com/en-us/library/66fe1241-e08f-49ca-832f-a84c33ca8735)

