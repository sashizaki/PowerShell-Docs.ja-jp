---
description: PowerShell でのリモートコマンドの実行に関する質問と回答が含まれています。
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_faq?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_FAQ
ms.openlocfilehash: da3516697c58e3273538ed2ed93a7a54fcd9bb49
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600386"
---
# <a name="about-remote-faq"></a><span data-ttu-id="f1234-103">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="f1234-103">About Remote FAQ</span></span>

## <a name="short-description"></a><span data-ttu-id="f1234-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="f1234-104">Short description</span></span>
<span data-ttu-id="f1234-105">PowerShell でのリモートコマンドの実行に関する質問と回答が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1234-105">Contains questions and answers about running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="f1234-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="f1234-106">Long description</span></span>

<span data-ttu-id="f1234-107">リモートで作業する場合は、1台のコンピューター ("ローカルコンピューター" と呼ばれます) に PowerShell でコマンドを入力しますが、コマンドは別のコンピューター ("リモートコンピューター" と呼ばれます) で実行します。</span><span class="sxs-lookup"><span data-stu-id="f1234-107">When you work remotely, you type commands in PowerShell on one computer (known as the "local computer"), but the commands run on another computer (known as the "remote computer").</span></span> <span data-ttu-id="f1234-108">リモート操作のエクスペリエンスは、リモートコンピューターで可能な限り直接作業するのと同じです。</span><span class="sxs-lookup"><span data-stu-id="f1234-108">The experience of working remotely should be as much like working directly at the remote computer as possible.</span></span>

<span data-ttu-id="f1234-109">注: PowerShell リモート処理を使用するには、リモートコンピューターがリモート処理用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1234-109">Note: To use PowerShell remoting, the remote computer must be configured for remoting.</span></span> <span data-ttu-id="f1234-110">詳細については、「[about_Remote_Requirements](about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-110">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="must-both-computers-have-powershell-installed"></a><span data-ttu-id="f1234-111">両方のコンピューターに PowerShell がインストールされている必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-111">Must both computers have PowerShell installed?</span></span>

<span data-ttu-id="f1234-112">はい。</span><span class="sxs-lookup"><span data-stu-id="f1234-112">Yes.</span></span> <span data-ttu-id="f1234-113">リモートで作業するには、ローカルコンピューターとリモートコンピューターに、PowerShell、Microsoft .NET Framework、および Web Services for Management (WS-MANAGEMENT) プロトコルが必要です。</span><span class="sxs-lookup"><span data-stu-id="f1234-113">To work remotely, the local and remote computers must have PowerShell, the Microsoft .NET Framework, and the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="f1234-114">特定のコマンドを実行するために必要なすべてのファイルとその他のリソースは、リモートコンピューター上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1234-114">Any files and other resources that are needed to execute a particular command must be on the remote computer.</span></span>

<span data-ttu-id="f1234-115">Windows PowerShell 3.0 を実行しているコンピューターと Windows PowerShell 2.0 を実行しているコンピューターは、リモート接続してリモートコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-115">Computers running Windows PowerShell 3.0 and computers running Windows PowerShell 2.0 can connect to each other remotely and run remote commands.</span></span>
<span data-ttu-id="f1234-116">ただし、セッションから切断して再接続する機能など、一部の機能は両方のコンピューターが Windows PowerShell 3.0 を実行している場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f1234-116">However, some features, such as the ability to disconnect from a session and reconnect to it, work only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="f1234-117">リモートコンピューターに接続するためのアクセス許可、PowerShell を実行するためのアクセス許可、およびデータストア (ファイルやフォルダーなど) にアクセスするためのアクセス許可、およびリモートコンピューター上のレジストリが必要です。</span><span class="sxs-lookup"><span data-stu-id="f1234-117">You must have permission to connect to the remote computer, permission to run PowerShell, and permission to access data stores (such as files and folders), and the registry on the remote computer.</span></span>

<span data-ttu-id="f1234-118">詳細については、「[about_Remote_Requirements](about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-118">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="how-does-remoting-work"></a><span data-ttu-id="f1234-119">リモート処理のしくみ</span><span class="sxs-lookup"><span data-stu-id="f1234-119">How does remoting work?</span></span>

<span data-ttu-id="f1234-120">リモートコマンドを送信すると、コマンドはネットワーク経由でリモートコンピューター上の PowerShell エンジンに送信され、リモートコンピューターの PowerShell クライアントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-120">When you submit a remote command, the command is transmitted across the network to the PowerShell engine on the remote computer, and it runs in the PowerShell client on the remote computer.</span></span> <span data-ttu-id="f1234-121">コマンドの結果はローカルコンピューターに送り返され、ローカルコンピューターの PowerShell セッションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-121">The command results are sent back to the local computer and appear in the PowerShell session on the local computer.</span></span>

<span data-ttu-id="f1234-122">コマンドを送信し、出力を受信するために、PowerShell は WS-Management プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1234-122">To transmit the commands and receive the output, PowerShell uses the WS-Management protocol.</span></span> <span data-ttu-id="f1234-123">WS-Management プロトコルの詳細については、Windows ドキュメントの「 [WS-Management プロトコル](/windows/win32/winrm/ws-management-protocol) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-123">For information about the WS-Management protocol, see [WS-Management Protocol](/windows/win32/winrm/ws-management-protocol) in the Windows documentation.</span></span>

<span data-ttu-id="f1234-124">Windows PowerShell 3.0 以降では、リモートセッションはリモートコンピューターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-124">Beginning in Windows PowerShell 3.0, remote sessions are stored on the remote computer.</span></span> <span data-ttu-id="f1234-125">これにより、セッションを切断し、別のセッションまたは別のコンピューターから再接続できます。その際、コマンドを中断したり、状態を失うことはありません。</span><span class="sxs-lookup"><span data-stu-id="f1234-125">This enables you to disconnect from the session and reconnect from a different session or a different computer without interrupting the commands or losing state.</span></span>

### <a name="is-powershell-remoting-secure"></a><span data-ttu-id="f1234-126">PowerShell リモート処理はセキュリティで保護されていますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-126">Is PowerShell remoting secure?</span></span>

<span data-ttu-id="f1234-127">リモートコンピューターに接続すると、システムはローカルコンピューターのユーザー名とパスワードの資格情報、またはコマンドで指定した資格情報を使用してリモートコンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="f1234-127">When you connect to a remote computer, the system uses the username and password credentials on the local computer or the credentials that you supply in the command to log you in to the remote computer.</span></span> <span data-ttu-id="f1234-128">資格情報と転送の残りの部分は暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-128">The credentials and the rest of the transmission are encrypted.</span></span>

<span data-ttu-id="f1234-129">さらに保護を追加するには、HTTP ではなく Secure Sockets Layer (SSL) を使用して Windows リモート管理 (WinRM) 要求をリッスンするようにリモートコンピューターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-129">To add additional protection, you can configure the remote computer to use Secure Sockets Layer (SSL) instead of HTTP to listen for Windows Remote Management (WinRM) requests.</span></span> <span data-ttu-id="f1234-130">次に、  `Invoke-Command` `New-PSSession` `Enter-PSSession` 接続を確立するときに、、、およびコマンドレットの UseSSL パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-130">Then, users can use the **UseSSL** parameter of the `Invoke-Command`, `New-PSSession`, and `Enter-PSSession` cmdlets when establishing a connection.</span></span> <span data-ttu-id="f1234-131">このオプションは、HTTP ではなく、より安全な HTTPS チャネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1234-131">This option uses the more secure HTTPS channel instead of HTTP.</span></span>

### <a name="do-all-remote-commands-require-powershell-remoting"></a><span data-ttu-id="f1234-132">すべてのリモートコマンドに PowerShell リモート処理が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="f1234-132">Do all remote commands require PowerShell remoting?</span></span>

<span data-ttu-id="f1234-133">いいえ。</span><span class="sxs-lookup"><span data-stu-id="f1234-133">No.</span></span> <span data-ttu-id="f1234-134">いくつかのコマンドレットには、リモートコンピューターからオブジェクトを取得できる **ComputerName** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="f1234-134">Several cmdlets have a **ComputerName** parameter that lets you get objects from the remote computer.</span></span>

<span data-ttu-id="f1234-135">これらのコマンドレットは、PowerShell リモート処理を使用しません。</span><span class="sxs-lookup"><span data-stu-id="f1234-135">These cmdlets do not use PowerShell remoting.</span></span> <span data-ttu-id="f1234-136">そのため、powershell リモート処理用にコンピューターが構成されていない場合や、コンピューターが PowerShell リモート処理の要件を満たしていない場合でも、PowerShell を実行している任意のコンピューターで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-136">So, you can use them on any computer that is running PowerShell, even if the computer is not configured for PowerShell remoting or if the computer does not meet the requirements for PowerShell remoting.</span></span>

<span data-ttu-id="f1234-137">これらのコマンドレットには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f1234-137">These cmdlets include the following:</span></span>

- `Get-Process`
- `Get-Service`
- `Get-WinEvent`
- `Get-EventLog`
- `Test-Connection`

<span data-ttu-id="f1234-138">**ComputerName** パラメーターを使用してすべてのコマンドレットを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f1234-138">To find all the cmdlets with a **ComputerName** parameter, type:</span></span>

```powershell
Get-Help * -Parameter ComputerName
# or
Get-Command -ParameterName ComputerName
```

<span data-ttu-id="f1234-139">特定のコマンドレットの **ComputerName** パラメーターに PowerShell リモート処理が必要かどうかを確認するには、パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-139">To determine whether the **ComputerName** parameter of a particular cmdlet requires PowerShell remoting, see the parameter description.</span></span> <span data-ttu-id="f1234-140">パラメーターの説明を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f1234-140">To display the parameter description, type:</span></span>

```powershell
Get-Help <cmdlet-name> -Parameter ComputerName
```

<span data-ttu-id="f1234-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f1234-141">For example:</span></span>

```powershell
Get-Help Get-Process -Parameter ComputerName
```

<span data-ttu-id="f1234-142">他のすべてのコマンドについては、コマンドレットを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="f1234-142">For all other commands, use the `Invoke-Command` cmdlet.</span></span>

### <a name="how-do-i-run-a-command-on-a-remote-computer"></a><span data-ttu-id="f1234-143">リモートコンピューターでコマンドを実行操作方法には</span><span class="sxs-lookup"><span data-stu-id="f1234-143">How do I run a command on a remote computer?</span></span>

<span data-ttu-id="f1234-144">リモートコンピューターでコマンドを実行するには、コマンドレットを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="f1234-144">To run a command on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="f1234-145">コマンドを中かっこ () で囲み、 `{}` スクリプトブロックにします。</span><span class="sxs-lookup"><span data-stu-id="f1234-145">Enclose your command in braces (`{}`) to make it a script block.</span></span> <span data-ttu-id="f1234-146">の **ScriptBlock** パラメーターを使用し `Invoke-Command` て、コマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1234-146">Use the **ScriptBlock** parameter of `Invoke-Command` to specify the command.</span></span>

<span data-ttu-id="f1234-147">の **ComputerName** パラメーターを使用して `Invoke-Command` 、リモートコンピューターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-147">You can use the **ComputerName** parameter of `Invoke-Command` to specify a remote computer.</span></span> <span data-ttu-id="f1234-148">または、リモートコンピューターへの永続的な接続 (セッション) を作成し、の **session** パラメーターを使用して、その `Invoke-Command` セッションでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-148">Or, you can create a persistent connection to a remote computer (a session) and then use the **Session** parameter of `Invoke-Command` to run the command in the session.</span></span>

<span data-ttu-id="f1234-149">たとえば、次のコマンドは、 `Get-Process` コマンドをリモートで実行します。</span><span class="sxs-lookup"><span data-stu-id="f1234-149">For example, the following commands run a `Get-Process` command remotely.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-Process}

#  - OR -

Invoke-Command -Session $s -ScriptBlock {Get-Process}
```

<span data-ttu-id="f1234-150">リモートコマンドを中断するには、「 <kbd>CTRL</kbd>C」と入力し + <kbd></kbd>ます。</span><span class="sxs-lookup"><span data-stu-id="f1234-150">To interrupt a remote command, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="f1234-151">中断要求はリモートコンピューターに渡され、そこでリモートコマンドが終了します。</span><span class="sxs-lookup"><span data-stu-id="f1234-151">The interruption request is passed to the remote computer, where it terminates the remote command.</span></span>

<span data-ttu-id="f1234-152">リモートコマンドの詳細については、「about_Remote」と、リモート処理をサポートするコマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-152">For more information about remote commands, see about_Remote and the Help topics for the cmdlets that support remoting.</span></span>

### <a name="can-i-just-telnet-into-a-remote-computer"></a><span data-ttu-id="f1234-153">リモートコンピューターに telnet でサインインすることはできますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-153">Can I just telnet into a remote computer?</span></span>

<span data-ttu-id="f1234-154">コマンドレットを使用し `Enter-PSSession` て、リモートコンピューターとの対話型セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-154">You can use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="f1234-155">PowerShell プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f1234-155">At the PowerShell prompt, type:</span></span>

```powershell
Enter-PSSession <ComputerName>
```

<span data-ttu-id="f1234-156">リモートコンピューターに接続していることを示すために、コマンドプロンプトが変更されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-156">The command prompt changes to show that you are connected to the remote computer.</span></span>

```
<ComputerName>\C:>
```

<span data-ttu-id="f1234-157">入力したコマンドは、リモートコンピューターで直接入力した場合と同じように、リモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-157">Now, the commands that you type run on the remote computer just as though you typed them directly on the remote computer.</span></span>

<span data-ttu-id="f1234-158">対話型セッションを終了するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f1234-158">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="f1234-159">対話型セッションは、WS-Management プロトコルを使用する永続的なセッションです。</span><span class="sxs-lookup"><span data-stu-id="f1234-159">An interactive session is a persistent session that uses the WS-Management protocol.</span></span> <span data-ttu-id="f1234-160">これは Telnet の使用と同じではありませんが、同様のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f1234-160">It is not the same as using Telnet, but it provides a similar experience.</span></span>

<span data-ttu-id="f1234-161">詳細については、「`Enter-PSSession`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-161">For more information, see `Enter-PSSession`.</span></span>

### <a name="can-i-create-a-persistent-connection"></a><span data-ttu-id="f1234-162">永続的な接続を作成できますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-162">Can I create a persistent connection?</span></span>

<span data-ttu-id="f1234-163">はい。</span><span class="sxs-lookup"><span data-stu-id="f1234-163">Yes.</span></span> <span data-ttu-id="f1234-164">リモートコマンドを実行するには、リモートコンピューターの名前、NetBIOS 名、またはその IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1234-164">You can run remote commands by specifying the name of the remote computer, its NetBIOS name, or its IP address.</span></span> <span data-ttu-id="f1234-165">または、リモートコンピューターに接続されている PowerShell セッション (PSSession) を指定することによって、リモートコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-165">Or, you can run remote commands by specifying a PowerShell session (PSSession) that is connected to the remote computer.</span></span>

<span data-ttu-id="f1234-166">またはの **ComputerName** パラメーターを使用すると `Invoke-Command` `Enter-PSSession` 、PowerShell によって一時的な接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-166">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, PowerShell establishes a temporary connection.</span></span> <span data-ttu-id="f1234-167">PowerShell は接続を使用して現在のコマンドのみを実行し、接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="f1234-167">PowerShell uses the connection to run only the current command, and then it closes the connection.</span></span> <span data-ttu-id="f1234-168">これは、多くのリモートコンピューターであっても、1つのコマンドまたは複数の関連のないコマンドを実行するための非常に効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="f1234-168">This is a very efficient method for running a single command or several unrelated commands, even on many remote computers.</span></span>

<span data-ttu-id="f1234-169">コマンドレットを使用して PSSession を作成すると `New-PSSession` 、PowerShell は pssession の永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="f1234-169">When you use the `New-PSSession` cmdlet to create a PSSession, PowerShell establishes a persistent connection for the PSSession.</span></span> <span data-ttu-id="f1234-170">その後、データを共有するコマンドを含め、複数のコマンドを PSSession で実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-170">Then, you can run multiple commands in the PSSession, including commands that share data.</span></span>

<span data-ttu-id="f1234-171">通常は、PSSession を作成して、データを共有する一連の関連コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1234-171">Typically, you create a PSSession to run a series of related commands that share data.</span></span> <span data-ttu-id="f1234-172">それ以外の場合、 **ComputerName** パラメーターによって作成される一時的な接続では、ほとんどのコマンドに対して十分です。</span><span class="sxs-lookup"><span data-stu-id="f1234-172">Otherwise, the temporary connection created by the **ComputerName** parameter is sufficient for most commands.</span></span>

<span data-ttu-id="f1234-173">セッションの詳細については、「about_PSSessions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-173">For more information about sessions, see about_PSSessions.</span></span>

### <a name="can-i-run-commands-on-more-than-one-computer-at-a-time"></a><span data-ttu-id="f1234-174">一度に複数のコンピューターでコマンドを実行できますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-174">Can I run commands on more than one computer at a time?</span></span>

<span data-ttu-id="f1234-175">はい。</span><span class="sxs-lookup"><span data-stu-id="f1234-175">Yes.</span></span> <span data-ttu-id="f1234-176">コマンドレットの **ComputerName** パラメーターには `Invoke-Command` 複数のコンピューター名を指定し、 **Session** パラメーターは複数の pssession を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f1234-176">The **ComputerName** parameter of the `Invoke-Command` cmdlet accepts multiple computer names, and the **Session** parameter accepts multiple PSSessions.</span></span>

<span data-ttu-id="f1234-177">コマンドを実行すると、PowerShell は、指定された `Invoke-Command` すべてのコンピューターまたは指定された pssession のすべてでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1234-177">When you run an `Invoke-Command` command, PowerShell runs the commands on all of the specified computers or in all of the specified PSSessions.</span></span>

<span data-ttu-id="f1234-178">PowerShell では、数百の同時リモート接続を管理できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-178">PowerShell can manage hundreds of concurrent remote connections.</span></span> <span data-ttu-id="f1234-179">ただし、送信できるリモートコマンドの数は、コンピューターのリソースとその容量によって制限され、複数のネットワーク接続を確立して維持することができます。</span><span class="sxs-lookup"><span data-stu-id="f1234-179">However, the number of remote commands that you can send might be limited by the resources of your computer and its capacity to establish and maintain multiple network connections.</span></span>

<span data-ttu-id="f1234-180">詳細については、ヘルプトピックの「」の例を参照してください `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="f1234-180">For more information, see the example in the `Invoke-Command` Help topic.</span></span>

### <a name="where-are-my-profiles"></a><span data-ttu-id="f1234-181">プロファイルはどこにありますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-181">Where are my profiles?</span></span>

<span data-ttu-id="f1234-182">PowerShell プロファイルはリモートセッションで自動的に実行されないため、プロファイルによって追加されたコマンドはセッションに存在しません。</span><span class="sxs-lookup"><span data-stu-id="f1234-182">PowerShell profiles are not run automatically in remote sessions, so the commands that the profile adds are not present in the session.</span></span> <span data-ttu-id="f1234-183">また、 `$profile` 自動変数は、リモートセッションでは設定されません。</span><span class="sxs-lookup"><span data-stu-id="f1234-183">In addition, the `$profile` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="f1234-184">セッションでプロファイルを実行するには、コマンドレットを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="f1234-184">To run a profile in a session, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="f1234-185">たとえば、次のコマンドは、のセッションでローカルコンピューターからたとえばプロファイルを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="f1234-185">For example, the following command runs the CurrentUserCurrentHost profile from the local computer in the session in `$s`.</span></span>

```
Invoke-Command -Session $s -FilePath $profile
```

<span data-ttu-id="f1234-186">次のコマンドは、のセッションでリモートコンピューターからたとえばプロファイルを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="f1234-186">The following command runs the CurrentUserCurrentHost profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="f1234-187">変数が設定されていないため、この `$profile` コマンドはプロファイルへの明示的なパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1234-187">Because the `$profile` variable is not populated, the command uses the explicit path to the profile.</span></span>

```powershell
Invoke-Command -Session $s {
  . "$home\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="f1234-188">このコマンドを実行すると、プロファイルによってセッションに追加されたコマンドがで使用できるように `$s` なります。</span><span class="sxs-lookup"><span data-stu-id="f1234-188">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

<span data-ttu-id="f1234-189">セッション構成のスタートアップスクリプトを使用して、セッション構成を使用するすべてのリモートセッションでプロファイルを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1234-189">You can also use a startup script in a session configuration to run a profile in every remote session that uses the session configuration.</span></span>

<span data-ttu-id="f1234-190">PowerShell プロファイルの詳細については、「about_Profiles」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-190">For more information about PowerShell profiles, see about_Profiles.</span></span>
<span data-ttu-id="f1234-191">セッション構成の詳細については、「」を参照してください `Register-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="f1234-191">For more information about session configurations, see `Register-PSSessionConfiguration`.</span></span>

### <a name="how-does-throttling-work-on-remote-commands"></a><span data-ttu-id="f1234-192">リモートコマンドでのスロットルの動作</span><span class="sxs-lookup"><span data-stu-id="f1234-192">How does throttling work on remote commands?</span></span>

<span data-ttu-id="f1234-193">PowerShell には、ローカルコンピューター上のリソースを管理するために、コマンドごとの調整機能が用意されています。この機能を使用すると、各コマンドに対して確立される同時リモート接続の数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-193">To help you manage the resources on your local computer, PowerShell includes a per-command throttling feature that lets you limit the number of concurrent remote connections that are established for each command.</span></span>

<span data-ttu-id="f1234-194">既定値は32同時接続ですが、コマンドレットの **ThrottleLimit** パラメーターを使用して、特定のコマンドに対してカスタムスロットル制限を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="f1234-194">The default is 32 concurrent connections, but you can use the **ThrottleLimit** parameter of the cmdlets to set a custom throttle limit for particular commands.</span></span>

<span data-ttu-id="f1234-195">調整機能を使用する場合は、セッション全体またはコンピューターに対してではなく、各コマンドに適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-195">When you use the throttling feature, remember that it is applied to each command, not to the entire session or to the computer.</span></span> <span data-ttu-id="f1234-196">複数のセッションまたは PSSessions で同時にコマンドを実行している場合、同時接続の数は、すべてのセッションの同時接続の合計になります。</span><span class="sxs-lookup"><span data-stu-id="f1234-196">If you are running commands concurrently in several sessions or PSSessions, the number of concurrent connections is the sum of the concurrent connections in all the sessions.</span></span>

<span data-ttu-id="f1234-197">**ThrottleLimit** パラメーターを使用してコマンドレットを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f1234-197">To find cmdlets with a **ThrottleLimit** parameter, type:</span></span>

```
Get-Help * -Parameter ThrottleLimit
-or-
Get-Command -ParameterName ThrottleLimit
```

### <a name="is-the-output-of-remote-commands-different-from-local-output"></a><span data-ttu-id="f1234-198">リモートコマンドの出力は、ローカル出力とは異なりますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-198">Is the output of remote commands different from local output?</span></span>

<span data-ttu-id="f1234-199">PowerShell をローカルで使用する場合は、"live" .NET Framework オブジェクトを送受信します。"live" オブジェクトは、実際のプログラムまたはシステムコンポーネントに関連付けられているオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f1234-199">When you use PowerShell locally, you send and receive "live" .NET Framework objects; "live" objects are objects that are associated with actual programs or system components.</span></span> <span data-ttu-id="f1234-200">メソッドを呼び出すか、またはライブオブジェクトのプロパティを変更すると、変更は実際のプログラムまたはコンポーネントに影響します。</span><span class="sxs-lookup"><span data-stu-id="f1234-200">When you invoke the methods or change the properties of live objects, the changes affect the actual program or component.</span></span> <span data-ttu-id="f1234-201">また、プログラムまたはコンポーネントのプロパティが変更されると、それらを表すオブジェクトのプロパティも変更されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-201">And, when the properties of a program or component change, the properties of the object that represent them also change.</span></span>

<span data-ttu-id="f1234-202">ただし、ほとんどのライブオブジェクトをネットワーク経由で転送することはできないため、PowerShell はリモートコマンドで送信されるオブジェクトのほとんどを "シリアル化" します。つまり、各オブジェクトは、送信用の一連の XML (XML [Export-clixml] の制約言語) データ要素に変換されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-202">However, because most live objects cannot be transmitted over the network, PowerShell "serializes" most of the objects sent in remote commands, that is, it converts each object into a series of XML (Constraint Language in XML [CLiXML]) data elements for transmission.</span></span>

<span data-ttu-id="f1234-203">PowerShell は、シリアル化されたオブジェクトを受け取ると、その XML を逆シリアル化されたオブジェクト型に変換します。</span><span class="sxs-lookup"><span data-stu-id="f1234-203">When PowerShell receives a serialized object, it converts the XML into a deserialized object type.</span></span> <span data-ttu-id="f1234-204">逆シリアル化されたオブジェクトは、以前のプログラムまたはコンポーネントのプロパティの正確な記録ですが、"ライブ" ではなくなりました。つまり、コンポーネントに直接関連付けられなくなります。</span><span class="sxs-lookup"><span data-stu-id="f1234-204">The deserialized object is an accurate record of the properties of the program or component at a previous time, but it is no longer "live", that is, it is no longer directly associated with the component.</span></span> <span data-ttu-id="f1234-205">また、これらのメソッドは、有効ではなくなったため、削除されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-205">And, the methods are removed because they are no longer effective.</span></span>

<span data-ttu-id="f1234-206">通常は、ライブオブジェクトを使用する場合と同様に、逆シリアル化されたオブジェクトを使用できますが、制限に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1234-206">Typically, you can use deserialized objects just as you would use live objects, but you must be aware of their limitations.</span></span> <span data-ttu-id="f1234-207">また、コマンドレットによって返されるオブジェクトには、 `Invoke-Command` コマンドの配信元を特定するのに役立つ追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f1234-207">Also, the objects that are returned by the `Invoke-Command` cmdlet have additional properties that help you to determine the origin of the command.</span></span>

<span data-ttu-id="f1234-208">DirectoryInfo オブジェクトや Guid など、オブジェクトの種類によっては、受信時にライブオブジェクトに変換されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-208">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="f1234-209">これらのオブジェクトは、特別な処理や書式設定を必要としません。</span><span class="sxs-lookup"><span data-stu-id="f1234-209">These objects do not need any special handling or formatting.</span></span>

<span data-ttu-id="f1234-210">リモート出力の解釈と書式設定の詳細については、「 [about_Remote_Output](about_Remote_Output.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-210">For information about interpreting and formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

### <a name="can-i-run-background-jobs-remotely"></a><span data-ttu-id="f1234-211">バックグラウンドジョブをリモートで実行できますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-211">Can I run background jobs remotely?</span></span>

<span data-ttu-id="f1234-212">はい。</span><span class="sxs-lookup"><span data-stu-id="f1234-212">Yes.</span></span> <span data-ttu-id="f1234-213">PowerShell バックグラウンドジョブは、セッションと対話せずに非同期的に実行される PowerShell コマンドです。</span><span class="sxs-lookup"><span data-stu-id="f1234-213">A PowerShell background job is a PowerShell command that runs asynchronously without interacting with the session.</span></span> <span data-ttu-id="f1234-214">バックグラウンドジョブを開始すると、コマンドプロンプトがすぐに返されます。ジョブが長時間実行されている場合でも、ジョブの実行中にセッションで作業を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="f1234-214">When you start a background job, the command prompt returns immediately, and you can continue to work in the session while the job runs even if it runs for an extended period of time.</span></span>

<span data-ttu-id="f1234-215">バックグラウンドジョブは常に一時的なセッションで非同期に実行されるため、他のコマンドが実行されている間でもバックグラウンドジョブを開始できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-215">You can start a background job even while other commands are running because background jobs always run asynchronously in a temporary session.</span></span>

<span data-ttu-id="f1234-216">バックグラウンドジョブは、ローカルコンピューターまたはリモートコンピューターで実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-216">You can run background jobs on a local or remote computer.</span></span> <span data-ttu-id="f1234-217">既定では、バックグラウンドジョブはローカルコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-217">By default, a background job runs on the local computer.</span></span> <span data-ttu-id="f1234-218">ただし、コマンドレットの **AsJob** パラメーターを使用し `Invoke-Command` て、バックグラウンドジョブとして任意のリモートコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-218">However, you can use the **AsJob** parameter of the `Invoke-Command` cmdlet to run any remote command as a background job.</span></span> <span data-ttu-id="f1234-219">また、を使用して `Invoke-Command` コマンドをリモートで実行することもでき `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="f1234-219">And, you can use `Invoke-Command` to run a `Start-Job` command remotely.</span></span>

<span data-ttu-id="f1234-220">PowerShell のバックグラウンドジョブの詳細については、[about_Jobs (about_Jobs)] および [about_Remote_Jobs (about_Remote_Jobs)] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-220">For more information about background jobs in PowerShell , see [about_Jobs(about_Jobs.md)] and [about_Remote_Jobs(about_Remote_Jobs.md)].</span></span>

### <a name="can-i-run-windows-programs-on-a-remote-computer"></a><span data-ttu-id="f1234-221">リモートコンピューターで windows プログラムを実行できますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-221">Can I run windows programs on a remote computer?</span></span>

<span data-ttu-id="f1234-222">PowerShell リモートコマンドを使用して、リモートコンピューター上の Windows ベースのプログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-222">You can use PowerShell remote commands to run Windows-based programs on remote computers.</span></span> <span data-ttu-id="f1234-223">たとえば、 `Shutdown.exe` リモートコンピューターでまたはを実行でき `Ipconfig.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="f1234-223">For example, you can run `Shutdown.exe` or `Ipconfig.exe` on a remote computer.</span></span>

<span data-ttu-id="f1234-224">ただし、PowerShell コマンドを使用してリモートコンピューター上のプログラムのユーザーインターフェイスを開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="f1234-224">However, you cannot use PowerShell commands to open the user interface for any program on a remote computer.</span></span>

<span data-ttu-id="f1234-225">リモートコンピューターで Windows プログラムを起動しても、コマンドは完了せず、PowerShell コマンドプロンプトでは、プログラムが終了するまで、または<kbd>CTRL</kbd>C キーを押してコマンドを中断するまでは返されません + <kbd></kbd> 。</span><span class="sxs-lookup"><span data-stu-id="f1234-225">When you start a Windows program on a remote computer, the command is not completed, and the PowerShell command prompt does not return, until the program is finished or until you press <kbd>CTRL</kbd>+<kbd>C</kbd> to interrupt the command.</span></span> <span data-ttu-id="f1234-226">たとえば、リモートコンピューターでプログラムを実行した場合、 `Ipconfig.exe` が完了するまでコマンドプロンプトからは返されません `Ipconfig.exe` 。</span><span class="sxs-lookup"><span data-stu-id="f1234-226">For example, if you run the `Ipconfig.exe` program on a remote computer, the command prompt does not return until `Ipconfig.exe` is completed.</span></span>

<span data-ttu-id="f1234-227">リモートコマンドを使用してユーザーインターフェイスを持つプログラムを起動すると、プログラムのプロセスが開始されますが、ユーザーインターフェイスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f1234-227">If you use remote commands to start a program that has a user interface, the program process starts, but the user interface does not appear.</span></span> <span data-ttu-id="f1234-228">PowerShell コマンドが完了していません。コマンドプロンプトは、プログラムプロセスを停止するか、または<kbd>CTRL</kbd>C キーを押すまで戻りません + <kbd></kbd>。これにより、コマンドが中断され、プロセスが停止します。</span><span class="sxs-lookup"><span data-stu-id="f1234-228">The PowerShell command is not completed, and the command prompt does not return until you stop the program process or until you press <kbd>CTRL</kbd>+<kbd>C</kbd>, which interrupts the command and stops the process.</span></span>

<span data-ttu-id="f1234-229">たとえば、PowerShell コマンドを使用してリモートコンピューターで実行する場合、 `Notepad` メモ帳のプロセスはリモートコンピューターで開始されますが、メモ帳のユーザーインターフェイスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f1234-229">For example, if you use a PowerShell command to run `Notepad` on a remote computer, the Notepad process starts on the remote computer, but the Notepad user interface does not appear.</span></span> <span data-ttu-id="f1234-230">コマンドを中断してコマンドプロンプトを復元するには、 <kbd>CTRL</kbd> + <kbd>C</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f1234-230">To interrupt the command and restore the command prompt, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <a name="can-i-limit-the-commands-that-users-can-run-remotely-on-my-computer"></a><span data-ttu-id="f1234-231">ユーザーがコンピューター上でリモートで実行できるコマンドを制限できますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-231">Can I limit the commands that users can run remotely on my computer?</span></span>

<span data-ttu-id="f1234-232">はい。</span><span class="sxs-lookup"><span data-stu-id="f1234-232">Yes.</span></span> <span data-ttu-id="f1234-233">すべてのリモートセッションで、リモートコンピューター上のセッション構成のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1234-233">Every remote session must use one of the session configurations on the remote computer.</span></span> <span data-ttu-id="f1234-234">コンピューター上のセッション構成 (およびそれらのセッション構成に対するアクセス許可) を管理して、コンピューター上でコマンドをリモートで実行できるユーザーと実行可能なコマンドを決定できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-234">You can manage the session configurations on your computer (and the permissions to those session configurations) to determine who can run commands remotely on your computer and which commands they can run.</span></span>

<span data-ttu-id="f1234-235">セッション構成によって、セッションの環境が構成されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-235">A session configuration configures the environment for the session.</span></span> <span data-ttu-id="f1234-236">構成を定義するには、新しい構成クラスを実装するアセンブリを使用するか、セッションで実行されるスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1234-236">You can define the configuration by using an assembly that implements a new configuration class or by using a script that runs in the session.</span></span> <span data-ttu-id="f1234-237">構成では、セッションで使用できるコマンドを特定できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-237">The configuration can determine the commands that are available in the session.</span></span>
<span data-ttu-id="f1234-238">また、構成には、1つのオブジェクトまたはコマンドでセッションがリモートで受信できるデータの量を制限する設定など、コンピューターを保護する設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f1234-238">And, the configuration can include settings that protect the computer, such as settings that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="f1234-239">また、構成を使用するために必要なアクセス許可を決定するセキュリティ記述子を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1234-239">You can also specify a security descriptor that determines the permissions that are required to use the configuration.</span></span>

<span data-ttu-id="f1234-240">`Enable-PSRemoting`コマンドレットにより、コンピューターに既定のセッション構成が作成されます。これには、microsoft.powershell32、および (64 ビットオペレーティングシステムのみ) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-240">The `Enable-PSRemoting` cmdlet creates the default session configurations on your computer: Microsoft.PowerShell, Microsoft.PowerShell.Workflow, and Microsoft.PowerShell32 (64-bit operating systems only).</span></span> <span data-ttu-id="f1234-241">`Enable-PSRemoting` 構成のセキュリティ記述子を設定して、コンピューター上の Administrators グループのメンバーだけが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f1234-241">`Enable-PSRemoting` sets the security descriptor for the configuration to allow only members of the Administrators group on your computer to use them.</span></span>

<span data-ttu-id="f1234-242">セッション構成コマンドレットを使用して、既定のセッション構成を編集したり、新しいセッション構成を作成したり、すべてのセッション構成のセキュリティ記述子を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="f1234-242">You can use the session configuration cmdlets to edit the default session configurations, to create new session configurations, and to change the security descriptors of all the session configurations.</span></span>

<span data-ttu-id="f1234-243">Windows PowerShell 3.0 以降では、 `New-PSSessionConfigurationFile` コマンドレットを使用して、テキストファイルを使用してカスタムセッション構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-243">Beginning in Windows PowerShell 3.0, the `New-PSSessionConfigurationFile` cmdlet lets you create custom session configurations by using a text file.</span></span> <span data-ttu-id="f1234-244">このファイルには、言語モードを設定し、セッション構成を使用するセッションで使用できるコマンドレットとモジュールを指定するためのオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1234-244">The file includes options for setting the language mode and for specifying the cmdlets and modules that are available in sessions that use the session configuration.</span></span>

<span data-ttu-id="f1234-245">ユーザーは `Invoke-Command` 、、、またはコマンドレットを使用するときに、ConfigurationName パラメーターを使用して、 `New-PSSession` `Enter-PSSession` セッションに使用するセッション構成を示すことができます。 </span><span class="sxs-lookup"><span data-stu-id="f1234-245">When users use the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets, they can use the **ConfigurationName** parameter to indicate the session configuration that is used for the session.</span></span> <span data-ttu-id="f1234-246">また、セッションのユーザー設定変数の値を変更することによって、セッションで使用される既定の構成を変更することもでき `$PSSessionConfigurationName` ます。</span><span class="sxs-lookup"><span data-stu-id="f1234-246">And, they can change the default configuration that their sessions use by changing the value of the `$PSSessionConfigurationName` preference variable in the session.</span></span>

<span data-ttu-id="f1234-247">セッション構成の詳細については、セッション構成コマンドレットのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-247">For more information about session configurations, see the Help for the session configuration cmdlets.</span></span> <span data-ttu-id="f1234-248">セッション構成コマンドレットを見つけるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f1234-248">To find the session configuration cmdlets, type:</span></span>

```powershell
Get-Command *PSSessionConfiguration
```

### <a name="what-are-fan-in-and-fan-out-configurations"></a><span data-ttu-id="f1234-249">ファンとファンアウトの構成とは</span><span class="sxs-lookup"><span data-stu-id="f1234-249">What are fan in and fan out configurations?</span></span>

<span data-ttu-id="f1234-250">複数のコンピューターに関連する最も一般的な PowerShell リモート処理のシナリオは、1つのローカルコンピューター (管理者のコンピューター) が多数のリモートコンピューターで PowerShell コマンドを実行する、1対多の構成です。</span><span class="sxs-lookup"><span data-stu-id="f1234-250">The most common PowerShell remoting scenario involving multiple computers is the one-to-many configuration, in which one local computer (the administrator's computer) runs PowerShell commands on numerous remote computers.</span></span> <span data-ttu-id="f1234-251">これは "ファンアウト" シナリオと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f1234-251">This is known as the "fan-out" scenario.</span></span>

<span data-ttu-id="f1234-252">ただし、一部の企業では、多数のクライアントコンピューターが、ファイルサーバーやキオスクなど、PowerShell を実行している1台のリモートコンピューターに接続するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="f1234-252">However, in some enterprises, the configuration is many-to-one, where many client computers connect to a single remote computer that is running PowerShell, such as a file server or a kiosk.</span></span> <span data-ttu-id="f1234-253">これは、"ファンイン" 構成と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f1234-253">This is known as the "fan-in" configuration.</span></span>

<span data-ttu-id="f1234-254">PowerShell リモート処理では、ファンアウト構成とファンアウト構成の両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f1234-254">PowerShell remoting supports both fan-out and fan-in configurations.</span></span>

<span data-ttu-id="f1234-255">ファンアウト構成の場合、PowerShell では、Web Services for Management (WS-MANAGEMENT) プロトコルと、WS-MANAGEMENT の Microsoft 実装をサポートする WinRM サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1234-255">For the fan-out configuration, PowerShell uses the Web Services for Management (WS-Management) protocol and the WinRM service that supports the Microsoft implementation of WS-Management.</span></span> <span data-ttu-id="f1234-256">ローカルコンピューターがリモートコンピューターに接続すると、WS-Management によって接続が確立され、PowerShell のプラグインを使用してリモートコンピューターで PowerShell ホストプロセス (Wsmprovhost.exe) が開始されます。</span><span class="sxs-lookup"><span data-stu-id="f1234-256">When a local computer connects to a remote computer, WS-Management establishes a connection and uses a plug-in for PowerShell to start the PowerShell host process (Wsmprovhost.exe) on the remote computer.</span></span> <span data-ttu-id="f1234-257">ユーザーは、代替ポート、代替セッション構成、およびその他の機能を指定して、リモート接続をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f1234-257">The user can specify an alternate port, an alternate session configuration, and other features to customize the remote connection.</span></span>

<span data-ttu-id="f1234-258">"ファンイン" 構成をサポートするために、PowerShell はインターネットインフォメーションサービス (IIS) を使用して WS-MANAGEMENT をホストし、PowerShell プラグインを読み込んで、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="f1234-258">To support the "fan-in" configuration, PowerShell uses internet Information Services (IIS) to host WS-Management, to load the PowerShell plug-in, and to start PowerShell.</span></span> <span data-ttu-id="f1234-259">このシナリオでは、各 PowerShell セッションを個別のプロセスで開始するのではなく、すべての PowerShell セッションを同じホストプロセスで実行します。</span><span class="sxs-lookup"><span data-stu-id="f1234-259">In this scenario, instead of starting each PowerShell session in a separate process, all PowerShell sessions run in the same host process.</span></span>

<span data-ttu-id="f1234-260">IIS のホストとファンインリモート管理は、Windows XP または Windows Server 2003 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f1234-260">IIS hosting and fan-in remote management is not supported in Windows XP or in Windows Server 2003.</span></span>

<span data-ttu-id="f1234-261">ファンアウト構成では、ユーザーは接続 URI と HTTP エンドポイント (トランスポート、コンピューター名、ポート、アプリケーション名など) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-261">In a fan-in configuration, the user can specify a connection URI and an HTTP endpoint, including the transport, computer name, port, and application name.</span></span>
<span data-ttu-id="f1234-262">IIS は、指定されたアプリケーション名を持つすべての要求をアプリケーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="f1234-262">IIS forwards all the requests with a specified application name to the application.</span></span> <span data-ttu-id="f1234-263">既定値は、PowerShell をホストできる WS-MANAGEMENT です。</span><span class="sxs-lookup"><span data-stu-id="f1234-263">The default is WS-Management, which can host PowerShell.</span></span>

<span data-ttu-id="f1234-264">また、認証メカニズムを指定し、HTTP および HTTPS エンドポイントからのリダイレクトを禁止または許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1234-264">You can also specify an authentication mechanism and prohibit or allow redirection from HTTP and HTTPS endpoints.</span></span>

### <a name="can-i-test-remoting-on-a-single-computer-not-in-a-domain"></a><span data-ttu-id="f1234-265">ドメイン内にない1台のコンピューターでリモート処理をテストできますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-265">Can I test remoting on a single computer not in a domain?</span></span>

<span data-ttu-id="f1234-266">はい。</span><span class="sxs-lookup"><span data-stu-id="f1234-266">Yes.</span></span> <span data-ttu-id="f1234-267">PowerShell リモート処理は、ローカルコンピューターがドメイン内にない場合でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-267">PowerShell remoting is available even when the local computer is not in a domain.</span></span> <span data-ttu-id="f1234-268">リモート処理機能を使用して、セッションに接続し、同じコンピューター上にセッションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f1234-268">You can use the remoting features to connect to sessions and to create sessions on the same computer.</span></span> <span data-ttu-id="f1234-269">これらの機能は、リモートコンピューターに接続する場合と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="f1234-269">The features work the same as they do when you connect to a remote computer.</span></span>

<span data-ttu-id="f1234-270">ワークグループ内のコンピューターでリモートコマンドを実行するには、コンピューターの次の Windows 設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="f1234-270">To run remote commands on a computer in a workgroup, change the following Windows settings on the computer.</span></span>

<span data-ttu-id="f1234-271">注意: これらの設定は、システム上のすべてのユーザーに影響を与え、悪意のある攻撃に対してシステムの脆弱性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="f1234-271">Caution: These settings affect all users on the system and they can make the system more vulnerable to a malicious attack.</span></span> <span data-ttu-id="f1234-272">これらの変更を行うときは注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="f1234-272">Use caution when making these changes.</span></span>

- <span data-ttu-id="f1234-273">Windows Vista、Windows 7、Windows 8:</span><span class="sxs-lookup"><span data-stu-id="f1234-273">Windows Vista, Windows 7, Windows 8:</span></span>

  <span data-ttu-id="f1234-274">次のレジストリエントリを作成し、その値を 1: LocalAccountTokenFilterPolicy in に設定します。 ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span><span class="sxs-lookup"><span data-stu-id="f1234-274">Create the following registry entry, and then set its value to 1: LocalAccountTokenFilterPolicy in ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span></span>

  <span data-ttu-id="f1234-275">次の PowerShell コマンドを使用して、このエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f1234-275">You can use the following PowerShell command to add this entry:</span></span>

    ```powershell
    $parameters = @{
      Path='HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System'
      Name='LocalAccountTokenFilterPolicy'
      propertyType='DWord'
      Value=1
    }
    New-ItemProperty @parameters
    ```

- <span data-ttu-id="f1234-276">Windows Server 2003、Windows Server 2008、Windows Server 2012、Windows Server 2012 R2:</span><span class="sxs-lookup"><span data-stu-id="f1234-276">Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:</span></span>

  <span data-ttu-id="f1234-277">"ネットワークアクセス: ローカルアカウントの共有とセキュリティモデル" ポリシーの既定の設定は "Classic" であるため、変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f1234-277">No changes are needed because the default setting of the "Network Access: Sharing and security model for local accounts" policy is "Classic".</span></span> <span data-ttu-id="f1234-278">設定が変更された場合は、その設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="f1234-278">Verify the setting in case it has changed.</span></span>

### <a name="can-i-run-remote-commands-on-a-computer-in-another-domain"></a><span data-ttu-id="f1234-279">別のドメイン内のコンピューターでリモートコマンドを実行できますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-279">Can I run remote commands on a computer in another domain?</span></span>

<span data-ttu-id="f1234-280">はい。</span><span class="sxs-lookup"><span data-stu-id="f1234-280">Yes.</span></span> <span data-ttu-id="f1234-281">通常、コマンドはエラーなしで実行されますが、、、またはコマンドレットの **Credential** パラメーターを使用して、 `Invoke-Command` `New-PSSession` `Enter-PSSession` リモートコンピューターの Administrators グループのメンバーの資格情報を指定することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1234-281">Typically, the commands run without error, although you might need to use the **Credential** parameter of the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets to provide the credentials of a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="f1234-282">これは、現在のユーザーがローカルコンピューターとリモートコンピューターの Administrators グループのメンバーである場合にも必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f1234-282">This is sometimes required even when the current user is a member of the Administrators group on the local and remote computers.</span></span>

<span data-ttu-id="f1234-283">ただし、リモートコンピューターがローカルコンピューターによって信頼されているドメインにない場合は、リモートコンピューターがユーザーの資格情報を認証できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1234-283">However, if the remote computer is not in a domain that the local computer trusts, the remote computer might not be able to authenticate the user's credentials.</span></span>

<span data-ttu-id="f1234-284">認証を有効にするには、次のコマンドを使用して、WinRM のローカルコンピューターの信頼されたホストの一覧にリモートコンピューターを追加します。</span><span class="sxs-lookup"><span data-stu-id="f1234-284">To enable authentication, use the following command to add the remote computer to the list of trusted hosts for the local computer in WinRM.</span></span> <span data-ttu-id="f1234-285">PowerShell プロンプトでコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f1234-285">Type the command at the PowerShell prompt.</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value <Remote-computer-name>
```

<span data-ttu-id="f1234-286">たとえば、Server01 コンピューターをローカルコンピューター上の信頼されたホストの一覧に追加するには、PowerShell プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f1234-286">For example, to add the Server01 computer to the list of trusted hosts on the local computer, type the following command at the PowerShell prompt:</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value Server01
```

### <a name="does-powershell-support-remoting-over-ssh"></a><span data-ttu-id="f1234-287">PowerShell は SSH 経由のリモート処理をサポートしていますか。</span><span class="sxs-lookup"><span data-stu-id="f1234-287">Does PowerShell support remoting over SSH?</span></span>

<span data-ttu-id="f1234-288">はい。</span><span class="sxs-lookup"><span data-stu-id="f1234-288">Yes.</span></span> <span data-ttu-id="f1234-289">詳細については、「 [SSH 経由の PowerShell リモート処理](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1234-289">For more information, see [PowerShell remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <a name="see-also"></a><span data-ttu-id="f1234-290">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1234-290">See also</span></span>

[<span data-ttu-id="f1234-291">about_Remote</span><span class="sxs-lookup"><span data-stu-id="f1234-291">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="f1234-292">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="f1234-292">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="f1234-293">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="f1234-293">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="f1234-294">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="f1234-294">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)

[<span data-ttu-id="f1234-295">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="f1234-295">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="f1234-296">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f1234-296">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="f1234-297">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f1234-297">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
