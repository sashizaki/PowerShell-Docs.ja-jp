---
description: Windows PowerShell セッションと、それらがリモートコマンドで果たす役割の詳細について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssession_details?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSession_Details
ms.openlocfilehash: bc07c1de294a05cd93dd9338d798fcaf24fb0ae4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223400"
---
# <a name="about-pssession-details"></a><span data-ttu-id="61cd6-104">PSSession の詳細について</span><span class="sxs-lookup"><span data-stu-id="61cd6-104">About PSSession Details</span></span>

## <a name="short-description"></a><span data-ttu-id="61cd6-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="61cd6-105">Short Description</span></span>

<span data-ttu-id="61cd6-106">Windows PowerShell セッションと、それらがリモートコマンドで果たす役割の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-106">Provides detailed information about Windows PowerShell sessions and the role they play in remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="61cd6-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="61cd6-107">Long Description</span></span>

<span data-ttu-id="61cd6-108">セッションとは、Windows PowerShell が実行される環境です。</span><span class="sxs-lookup"><span data-stu-id="61cd6-108">A session is an environment in which Windows PowerShell runs.</span></span> <span data-ttu-id="61cd6-109">Windows PowerShell を起動するたびに、セッションが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-109">A session is created for you whenever you start Windows PowerShell.</span></span> <span data-ttu-id="61cd6-110">コンピューターまたは別のコンピューターで、"Windows PowerShell セッション" または "PSSessions" と呼ばれる追加のセッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-110">You can create additional sessions, called "Windows PowerShell sessions" or "PSSessions" on your computer or another computer.</span></span>

<span data-ttu-id="61cd6-111">Windows PowerShell によって作成されるセッションとは異なり、作成する pssession を制御および管理します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-111">Unlike the sessions that Windows PowerShell creates for you, you control and manage the PSSessions that you create.</span></span>

<span data-ttu-id="61cd6-112">PSSessions は、リモートコンピューティングにおいて重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="61cd6-112">PSSessions play an important role in remote computing.</span></span> <span data-ttu-id="61cd6-113">リモートコンピューターに接続されている PSSession を作成すると、Windows PowerShell は PSSession をサポートするために、リモートコンピューターへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-113">When you create a PSSession that is connected to a remote computer, Windows PowerShell establishes a persistent connection to the remote computer to support the PSSession.</span></span> <span data-ttu-id="61cd6-114">PSSession を使用すると、データを共有する一連のコマンド、関数、およびスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-114">You can use the PSSession to run a series of commands, functions, and scripts that share data.</span></span>

<span data-ttu-id="61cd6-115">このトピックでは、Windows PowerShell のセッションと pssession の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-115">This topic provides detailed information about sessions and PSSessions in Windows PowerShell.</span></span> <span data-ttu-id="61cd6-116">セッションで実行できるタスクに関する基本的な情報については、「 [about_PSSessions](about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61cd6-116">For basic information about the tasks that you can perform with sessions, see [about_PSSessions](about_PSSessions.md).</span></span>

## <a name="about-sessions"></a><span data-ttu-id="61cd6-117">セッションについて</span><span class="sxs-lookup"><span data-stu-id="61cd6-117">About Sessions</span></span>

<span data-ttu-id="61cd6-118">技術的には、セッションとは、Windows PowerShell が実行される実行環境のことです。</span><span class="sxs-lookup"><span data-stu-id="61cd6-118">Technically, a session is an execution environment in which Windows PowerShell runs.</span></span> <span data-ttu-id="61cd6-119">各セッションには、Windows PowerShell を実行するための、システム管理エンジンとホストプログラムのインスタンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="61cd6-119">Each session includes an instance of the System.Management.Automation engine and a host program in which Windows PowerShell runs.</span></span> <span data-ttu-id="61cd6-120">ホストには、使い慣れた Windows PowerShell コンソール、または Cmd.exe などのコマンドを実行する別のプログラム、または windows powershell Integrated Scripting Environment (ISE) などの Windows PowerShell をホストするために構築されたプログラムなどがあります。</span><span class="sxs-lookup"><span data-stu-id="61cd6-120">The host can be the familiar Windows PowerShell console or another program that runs commands, such as Cmd.exe, or a program built to host Windows PowerShell, such as Windows PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="61cd6-121">Windows の観点から見ると、セッションはターゲットコンピューター上の Windows プロセスです。</span><span class="sxs-lookup"><span data-stu-id="61cd6-121">From a Windows perspective, a session is a Windows process on the target computer.</span></span>

<span data-ttu-id="61cd6-122">各セッションは個別に構成されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-122">Each session is configured independently.</span></span> <span data-ttu-id="61cd6-123">これには、独自のプロパティ、独自の実行ポリシー、および独自のプロファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-123">It includes its own properties, its own execution policy, and its own profiles.</span></span> <span data-ttu-id="61cd6-124">セッションの作成時に存在する環境は、コンピューター上の環境を変更しても、その有効期間にわたって保持されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-124">The environment that exists when the session is created persists for its lifetime even if you change the environment on the computer.</span></span> <span data-ttu-id="61cd6-125">すべてのセッションは、スクリプトで作成したセッションでも、グローバルスコープで作成されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-125">All sessions are created in a global scope, even sessions that you create in a script.</span></span>

<span data-ttu-id="61cd6-126">セッションでは、一度に1つのコマンド (またはコマンドパイプライン) のみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-126">You can run only one command (or command pipeline) in a session at one time.</span></span> <span data-ttu-id="61cd6-127">2番目のコマンドは同期的に (一度に1つずつ) 実行され、最初のコマンドが完了するまで最大4分間待機します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-127">A second command run synchronously (one at a time) waits up to four minutes for the first command to be completed.</span></span> <span data-ttu-id="61cd6-128">非同期的に (同時に) 実行する2番目のコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-128">A second command run asynchronously (concurrently) fails.</span></span>

## <a name="about-pssessions"></a><span data-ttu-id="61cd6-129">PSSessions について</span><span class="sxs-lookup"><span data-stu-id="61cd6-129">About PSSessions</span></span>

<span data-ttu-id="61cd6-130">セッションは、Windows PowerShell を起動するたびに作成されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-130">A session is created each time that you start Windows PowerShell.</span></span> <span data-ttu-id="61cd6-131">また、Windows PowerShell は、個々のコマンドを実行するための一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-131">And, Windows PowerShell creates temporary sessions to run individual commands.</span></span>
<span data-ttu-id="61cd6-132">ただし、制御および管理するセッション ("Windows PowerShell セッション" または "PSSessions" と呼ばれます) を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-132">However, you can also create sessions (called "Windows PowerShell sessions" or "PSSessions") that you control and manage.</span></span>

<span data-ttu-id="61cd6-133">PSSessions は、リモートコマンドにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="61cd6-133">PSSessions are critical to remote commands.</span></span> <span data-ttu-id="61cd6-134">またはコマンドレットの **ComputerName** パラメーターを使用する `Invoke-Command` と、Windows PowerShell は、コマンドを `Enter-PSSession` 実行するための一時的なセッションを確立してから、コマンドまたは対話型セッションが完了すると直ちにセッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-134">If you use the **ComputerName** parameter of the `Invoke-Command` or `Enter-PSSession` cmdlets, Windows PowerShell establishes a temporary session to run the command and then closes the session as soon as the command or the interactive session is complete.</span></span>

<span data-ttu-id="61cd6-135">ただし、コマンドレットを使用して PSSession を作成した場合、 `New-PSSession` Windows PowerShell は、複数のコマンドや対話型セッションを実行できる、リモートコンピューター上の永続的なセッションを確立します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-135">However, if you use the `New-PSSession` cmdlet to create a PSSession, Windows PowerShell establishes a persistent session on the remote computer in which you can run multiple commands or interactive sessions.</span></span> <span data-ttu-id="61cd6-136">作成した pssession は開いたままで、削除するか、作成されたセッションを閉じるまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-136">The PSSessions that you create remain open and available for use until you delete them or until you close the session in which they were created.</span></span>

<span data-ttu-id="61cd6-137">リモートコンピューター上に PSSession を作成すると、システムによってリモートコンピューター上に PowerShell プロセスが作成され、ローカルコンピューターからリモートコンピューター上のプロセスへの接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-137">When you create a PSSession on a remote computer, the system creates a PowerShell process on the remote computer and establishes a connection from the local computer to the process on the remote computer.</span></span> <span data-ttu-id="61cd6-138">ローカルコンピューター上に PSSession を作成すると、新しいプロセスと接続の両方がローカルコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-138">When you create a PSSession on the local computer, both the new process and the connections are created on the local computer.</span></span>

## <a name="when-do-i-need-a-pssession"></a><span data-ttu-id="61cd6-139">PSSession はどのような場合に必要ですか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-139">When Do I Need a PSSession?</span></span>

<span data-ttu-id="61cd6-140">`Invoke-Command`およびコマンドレットには、 `Enter-PSSession` **ComputerName** パラメーターと **Session** パラメーターの両方があります。</span><span class="sxs-lookup"><span data-stu-id="61cd6-140">The `Invoke-Command` and `Enter-PSSession` cmdlets have both **ComputerName** and **Session** parameters.</span></span> <span data-ttu-id="61cd6-141">リモートコマンドを実行するには、いずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-141">You can use either to run a remote command.</span></span>

<span data-ttu-id="61cd6-142">1つまたは複数のコンピューターで1つのコマンドまたは一連の関連のないコマンドを実行するには、 **ComputerName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-142">Use the **ComputerName** parameter to run a single command or a series of unrelated commands on one or many computers.</span></span>

<span data-ttu-id="61cd6-143">データを共有するコマンドを実行するには、リモートコンピューターへの永続的な接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="61cd6-143">To run commands that share data, you need a persistent connection to the remote computer.</span></span> <span data-ttu-id="61cd6-144">その場合は、PSSession を作成し、 **セッション** パラメーターを使用して pssession でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-144">In that case, create a PSSession, and then use the **Session** parameter to run commands in the PSSession.</span></span>

<span data-ttu-id="61cd6-145">、、、などのリモートコンピューターからデータを取得する他の多くのコマンドレットには、 `Get-Process` `Get-Service` `Get-EventLog` `Get-WmiObject` **ComputerName** パラメーターしかありません。</span><span class="sxs-lookup"><span data-stu-id="61cd6-145">Many other cmdlets that get data from remote computers, such as `Get-Process`, `Get-Service`, `Get-EventLog`, and `Get-WmiObject` have only a **ComputerName** parameter.</span></span> <span data-ttu-id="61cd6-146">Windows PowerShell リモート処理以外のテクノロジを使用してデータをリモートで収集します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-146">They use technologies other than Windows PowerShell remoting to gather data remotely.</span></span> <span data-ttu-id="61cd6-147">これらのコマンドレットには **Session** パラメーターはありませんが、コマンドレットを使用して、 `Invoke-Command` PSSession でこれらのコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-147">These cmdlets do not have a **Session** parameter, but you can use the `Invoke-Command` cmdlet to run these commands in a PSSession.</span></span>

## <a name="how-do-i-create-a-pssession"></a><span data-ttu-id="61cd6-148">PSSession を作成するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-148">How Do I Create a PSSession?</span></span>

<span data-ttu-id="61cd6-149">PSSession を作成するには、 `New-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-149">To create a PSSession, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="61cd6-150">を使用し `New-PSSession` て、ローカルコンピューターまたはリモートコンピューター上に PSSession を作成できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-150">You can use `New-PSSession` to create a PSSession on a local or remote computer.</span></span>

## <a name="can-i-create-a-pssession-on-any-computer"></a><span data-ttu-id="61cd6-151">任意のコンピューターで PSSession を作成できますか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-151">Can I Create a PSSession on Any Computer?</span></span>

<span data-ttu-id="61cd6-152">リモートコンピューターに接続されている PSSession を作成するには、Windows PowerShell のリモート処理用にコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61cd6-152">To create a PSSession that is connected to a remote computer, the computer must be configured for remoting in Windows PowerShell.</span></span> <span data-ttu-id="61cd6-153">現在のユーザーは、リモートコンピューターの Administrators グループのメンバーであるか、または現在のユーザーが Administrators グループのメンバーの資格情報を提供できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="61cd6-153">The current user must be a member of the Administrators group on the remote computer, or the current user must be able to supply the credentials of a member of the Administrators group.</span></span> <span data-ttu-id="61cd6-154">詳細については、「[about_Remote_Requirements](about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61cd6-154">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

## <a name="can-i-see-my-pssessions-in-other-sessions"></a><span data-ttu-id="61cd6-155">他のセッションでは、PSSessions を表示できますか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-155">Can I See My PSSessions in Other Sessions?</span></span>

<span data-ttu-id="61cd6-156">Windows PowerShell 3.0 以降では、コマンドレットの **ComputerName** パラメーターは、 `Get-PSSession` 指定されたリモートコンピューターで作成した pssessions を取得します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-156">Beginning in Windows PowerShell 3.0, the **ComputerName** parameter of the `Get-PSSession` cmdlet gets PSSessions that you created on the specified remote computers.</span></span>

<span data-ttu-id="61cd6-157">アクティブな PSSessions は、リモートコンピューター (接続の "サーバー側") で保持され、任意のコンピューター上の任意のセッションから取得できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-157">Active PSSessions are maintained on the remote computer (the "server-side" of a connection) and you can get them from any session on any computer.</span></span>

<span data-ttu-id="61cd6-158">たとえば、Server01 コンピューターから Server02 コンピューターに PSSession を作成し、Server03 コンピューターに切り替える場合は、次のようなコマンドを使用してセッションを取得できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-158">For example, if you create a PSSession from the Server01 computer to the Server02 computer, and then switch to the Server03 computer, you can use a command like the following one to get the session.</span></span>

```powershell
Get-PSSession -ComputerName Server02
```

<span data-ttu-id="61cd6-159">セッションから切断した場合でも、セッションは、削除するか、タイムアウトになるまで、リモートコンピューター上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-159">Even if you disconnect from the session, the session is maintained on the remote computer until you delete it or it times out.</span></span>

<span data-ttu-id="61cd6-160">Windows PowerShell 2.0 では、現在のセッションで作成した pssession のみを取得できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-160">In Windows PowerShell 2.0, you can get only the PSSessions that you have created in the current session.</span></span> <span data-ttu-id="61cd6-161">他のセッションで作成した pssession を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="61cd6-161">You cannot get PSSessions that you created in other sessions.</span></span>

<span data-ttu-id="61cd6-162">詳細については、「 [Get PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61cd6-162">For more information, see [Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession).</span></span>

## <a name="can-i-see-the-pssessions-that-others-have-created-on-my-computer"></a><span data-ttu-id="61cd6-163">他のユーザーがマイコンピューターで作成した PSSessions を確認できますか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-163">Can I See the PSSessions That Others Have Created on My Computer?</span></span>

<span data-ttu-id="61cd6-164">PSSession を作成したユーザーの資格情報、または PSSession が使用するセッション構成に RunAs 資格情報が含まれている場合にのみ、他のユーザーが作成した PSSession のみを取得して管理できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-164">You can get and manage only the PSSessions that others have created only if you can supply the credentials of the user who created the PSSession or the session configuration that the PSSession uses includes RunAs credentials.</span></span> <span data-ttu-id="61cd6-165">そうしないと、作成した pssession だけを取得、接続、使用、管理できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-165">Otherwise, you can get, connect to, use, and manage only the PSSessions that you created.</span></span>

## <a name="can-i-connect-to-a-pssession-from-a-different-computer"></a><span data-ttu-id="61cd6-166">別のコンピューターから PSSession に接続することはできますか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-166">Can I Connect to a PSSession From a Different Computer?</span></span>

<span data-ttu-id="61cd6-167">Windows PowerShell 3.0 以降では、PSSessions は、それらが作成されたセッションから独立しています。</span><span class="sxs-lookup"><span data-stu-id="61cd6-167">Beginning in Windows PowerShell 3.0, PSSessions are independent of the sessions in which they were created.</span></span> <span data-ttu-id="61cd6-168">アクティブな PSSessions は、接続のリモートまたは "サーバー側" でコンピューター上に保持されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-168">Active PSSessions are maintained on the computer at the remote or "server-side" of a connection.</span></span>

<span data-ttu-id="61cd6-169">コマンドレットを使用して、 `Disconnect-PSSession` PSSession から切断することができます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-169">You can use the `Disconnect-PSSession` cmdlet to disconnect from a PSSession.</span></span> <span data-ttu-id="61cd6-170">PSSession はローカルセッションから切断されますが、リモートコンピューター上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-170">The PSSession is disconnected from the local session, but is maintained on the remote computer.</span></span>
<span data-ttu-id="61cd6-171">コマンドは、切断された PSSession で引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-171">Commands continue to run in the disconnected PSSession.</span></span> <span data-ttu-id="61cd6-172">PSSession を中断せずに、Windows PowerShell を閉じて、元のコンピューターをシャットダウンすることができます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-172">You can close Windows PowerShell and shut down the originating computer without interrupting the PSSession.</span></span>

<span data-ttu-id="61cd6-173">その後、数時間後に、コマンドレットを使用して PSSession を取得し、コマンドレットを使用して `Get-PSSession` `Connect-PSSession` 別のコンピューター上の新しいセッションから pssession に接続できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-173">Then, even hours later, you can use the `Get-PSSession` cmdlet to get the PSSession and the `Connect-PSSession` cmdlet to connect to the PSSession from a new session on a different computer.</span></span>

<span data-ttu-id="61cd6-174">詳細については、「 [about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61cd6-174">For more information, see [about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md).</span></span>

## <a name="what-happens-to-my-pssession-if-my-computer-stops"></a><span data-ttu-id="61cd6-175">マイコンピューターが停止した場合、PSSession はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-175">What Happens to My PSSession if My Computer Stops?</span></span>

<span data-ttu-id="61cd6-176">切断された pssession は、そのセッションが作成されたセッションから独立しています。</span><span class="sxs-lookup"><span data-stu-id="61cd6-176">Disconnected PSSessions are independent of the sessions in which they were created.</span></span> <span data-ttu-id="61cd6-177">PSSession を切断してから、元のコンピューターを閉じると、PSSession がリモートコンピューター上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-177">If you disconnect a PSSession and then close the originating computer, the PSSession is maintained on the remote computer.</span></span>

<span data-ttu-id="61cd6-178">さらに、Windows PowerShell は、コンピューターの再起動、一時的な停電、ネットワークの中断など、意図せずに切断されたアクティブな PSSessions を回復しようとします。</span><span class="sxs-lookup"><span data-stu-id="61cd6-178">In addition, Windows PowerShell attempts to recover active PSSessions that are disconnected unintentionally, such as by a computer reboot, a temporary power outage or network disruption.</span></span> <span data-ttu-id="61cd6-179">Windows PowerShell は、開始された状態への PSSession の保持または復旧を試みます。ただし、発信元セッションがまだ使用可能な場合、または接続されていない場合は切断状態になります。</span><span class="sxs-lookup"><span data-stu-id="61cd6-179">Windows PowerShell attempts to maintain or recover the PSSession to an Opened state, if the originating session is still available, or to a disconnected state if it is not.</span></span>

<span data-ttu-id="61cd6-180">"アクティブ" PSSession は、コマンドを実行しているものです。</span><span class="sxs-lookup"><span data-stu-id="61cd6-180">An "active" PSSession is one that is running commands.</span></span> <span data-ttu-id="61cd6-181">PSSession が接続されており (切断されていない)、接続されたセッションが終了したときに PSSession でコマンドが実行されている場合、Windows PowerShell は、リモートコンピューター上の PSSession を維持しようとします。</span><span class="sxs-lookup"><span data-stu-id="61cd6-181">If a PSSession is connected (not disconnected) and commands are running in the PSSession when the connected session closes, Windows PowerShell attempts to maintain the PSSession on the remote computer.</span></span> <span data-ttu-id="61cd6-182">ただし、PSSession で実行されているコマンドがない場合、接続されているセッションが閉じられると、Windows PowerShell は PSSession を閉じます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-182">However, if no commands are running in the PSSession, Windows PowerShell closes the PSSession when the connected session closes.</span></span>

<span data-ttu-id="61cd6-183">詳細については、「 [about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61cd6-183">For more information, see [about_Remote_Disconnected_Sessions](about_Remote_Disconnected_Sessions.md).</span></span>

## <a name="can-i-run-a-background-job-in-a-pssession"></a><span data-ttu-id="61cd6-184">バックグラウンドジョブを PSSession で実行できますか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-184">Can I Run a Background Job in a PSSession?</span></span>

<span data-ttu-id="61cd6-185">はい。</span><span class="sxs-lookup"><span data-stu-id="61cd6-185">Yes.</span></span> <span data-ttu-id="61cd6-186">バックグラウンドジョブは、現在のセッションと対話することなくバックグラウンドで非同期に実行されるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="61cd6-186">A background job is a command that runs asynchronously in the background without interacting with the current session.</span></span> <span data-ttu-id="61cd6-187">ジョブを開始するコマンドを送信すると、このコマンドはジョブオブジェクトを返しますが、ジョブは完了するまでバックグラウンドで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-187">When you submit a command to start a job, the command returns a job object, but the job continues to run in the background until it is complete.</span></span>

<span data-ttu-id="61cd6-188">ローカルコンピューターでバックグラウンドジョブを開始するには、コマンドを使用し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-188">To start a background job on a local computer, use the `Start-Job` command.</span></span>
<span data-ttu-id="61cd6-189">バックグラウンドジョブは、( **ComputerName** パラメーターを使用して) 一時的な接続で実行するか、または ( **Session** パラメーターを使用して) PSSession で実行できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-189">You can run the background job in a temporary connection (by using the **ComputerName** parameter) or in a PSSession (by using the **Session** parameter).</span></span>

<span data-ttu-id="61cd6-190">リモートコンピューターでバックグラウンドジョブを開始するに `Invoke-Command` は、コマンドレットを **AsJob** パラメーターと共に使用するか、コマンドレットを使用して `Invoke-Command` `Start-Job` リモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-190">To start a background job on a remote computer, use the `Invoke-Command` cmdlet with its **AsJob** parameter, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span> <span data-ttu-id="61cd6-191">**AsJob** パラメーターを使用する場合は、 **ComputerName** パラメーターまたは **Session** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-191">When using the **AsJob** parameter, you can use the **ComputerName** or **Session** parameters.</span></span>

<span data-ttu-id="61cd6-192">を使用してコマンドを実行する場合は、 `Invoke-Command` `Start-Job` PSSession でコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61cd6-192">When using `Invoke-Command` to run a `Start-Job` command, you must run the command in a PSSession.</span></span> <span data-ttu-id="61cd6-193">**ComputerName** パラメーターを使用すると、Windows PowerShell は、ジョブオブジェクトから制御が戻ったときに接続を終了し、ジョブが中断されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-193">If you use the **ComputerName** parameter, Windows PowerShell ends the connection when the job object returns, and the job is interrupted.</span></span>

<span data-ttu-id="61cd6-194">詳細については、「[about_Jobs](about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61cd6-194">For more information, see [about_Jobs](about_Jobs.md).</span></span>

## <a name="can-i-run-an-interactive-session"></a><span data-ttu-id="61cd6-195">対話型セッションを実行できますか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-195">Can I Run an Interactive Session?</span></span>

<span data-ttu-id="61cd6-196">はい。</span><span class="sxs-lookup"><span data-stu-id="61cd6-196">Yes.</span></span> <span data-ttu-id="61cd6-197">リモートコンピューターとの対話型セッションを開始するには、 `Enter-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-197">To start an interactive session with a remote computer, use the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="61cd6-198">対話型セッションでは、入力したコマンドはリモートコンピューター上で直接入力した場合と同じように、リモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-198">In an interactive session, the commands that you type run on the remote computer, just as if you typed them directly on the remote computer.</span></span>

<span data-ttu-id="61cd6-199">( **ComputerName** パラメーターを使用して) 一時的なセッションで、または ( **セッション** パラメーターを使用して) PSSession で対話型セッションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-199">You can run an interactive session in a temporary session (by using the **ComputerName** parameter) or in a PSSession (by using the **Session** parameter).</span></span>
<span data-ttu-id="61cd6-200">PSSession を使用する場合、PSSession は前のコマンドのデータを保持し、PSSession は、後のコマンドで使用するために対話型セッション中に生成されたすべてのデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-200">If you use a PSSession, the PSSession retains the data from previous commands, and the PSSession retains any data generated during the interactive session for use in later commands.</span></span>

<span data-ttu-id="61cd6-201">対話型セッションを終了すると、PSSession は開いたままになり、使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="61cd6-201">When you end the interactive session, the PSSession remains open and available for use.</span></span>

<span data-ttu-id="61cd6-202">詳細については、「PSSession と[出口](xref:Microsoft.PowerShell.Core.Exit-PSSession)の[入力](xref:Microsoft.PowerShell.Core.Enter-PSSession)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61cd6-202">For more information, see [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) and [Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession).</span></span>

## <a name="must-i-delete-the-pssessions"></a><span data-ttu-id="61cd6-203">PSSessions を削除する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-203">Must I Delete the PSSessions?</span></span>

<span data-ttu-id="61cd6-204">はい。</span><span class="sxs-lookup"><span data-stu-id="61cd6-204">Yes.</span></span> <span data-ttu-id="61cd6-205">PSSession は、メモリやその他のリソースを使用していない場合でも、それを使用する自己完結型の環境であるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="61cd6-205">A PSSession is a process, which is a self-contained environment that uses memory and other resources even when you are not using it.</span></span> <span data-ttu-id="61cd6-206">PSSession が終了したら、それを削除します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-206">When you are finished with a PSSession, delete it.</span></span> <span data-ttu-id="61cd6-207">複数の pssession を作成する場合は、使用していない PSSessions を閉じ、現在使用されているものだけを維持します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-207">If you create multiple PSSessions, close the ones that you are not using, and maintain only the ones currently in use.</span></span>

<span data-ttu-id="61cd6-208">PSSessions を削除するには、コマンドレットを使用し `Remove-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-208">To delete PSSessions, use the `Remove-PSSession` cmdlet.</span></span> <span data-ttu-id="61cd6-209">PSSessions を削除し、使用していたすべてのリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="61cd6-209">It deletes the PSSessions and releases all of the resources that they were using.</span></span>

<span data-ttu-id="61cd6-210">また、の **IdleTimeOut** パラメーターを使用して、 `New-PSSessionOption` 指定した間隔の後にアイドル状態の PSSession を閉じることもできます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-210">You can also use the **IdleTimeOut** parameter of `New-PSSessionOption` to close an idle PSSession after an interval that you specify.</span></span> <span data-ttu-id="61cd6-211">詳細については、「 [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61cd6-211">For more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="61cd6-212">PSSession オブジェクトを変数に保存し、PSSession を削除するか、タイムアウトにすると、変数には PSSession オブジェクトが残りますが、PSSession はアクティブではなく、使用または修復もできません。</span><span class="sxs-lookup"><span data-stu-id="61cd6-212">If you save a PSSession object in a variable and then delete the PSSession or let it time out, the variable still contains the PSSession object, but the PSSession is not active and cannot be used or repaired.</span></span>

## <a name="are-all-sessions-and-pssessions-alike"></a><span data-ttu-id="61cd6-213">すべてのセッションと PSSessions は似ていますか。</span><span class="sxs-lookup"><span data-stu-id="61cd6-213">Are All Sessions and PSSessions Alike?</span></span>

<span data-ttu-id="61cd6-214">いいえ。</span><span class="sxs-lookup"><span data-stu-id="61cd6-214">No.</span></span> <span data-ttu-id="61cd6-215">開発者は、選択したプロバイダーとコマンドレットのみを含むカスタムセッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="61cd6-215">Developers can create custom sessions that include only selected providers and cmdlets.</span></span> <span data-ttu-id="61cd6-216">あるセッションではコマンドが動作し、別のセッションでは動作しない場合は、セッションが制限されていることが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="61cd6-216">If a command works in one session but not in another, it might be because the session is restricted.</span></span>

## <a name="see-also"></a><span data-ttu-id="61cd6-217">参照</span><span class="sxs-lookup"><span data-stu-id="61cd6-217">See Also</span></span>

[<span data-ttu-id="61cd6-218">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="61cd6-218">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="61cd6-219">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="61cd6-219">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="61cd6-220">about_Remote</span><span class="sxs-lookup"><span data-stu-id="61cd6-220">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="61cd6-221">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="61cd6-221">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="61cd6-222">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="61cd6-222">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="61cd6-223">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="61cd6-223">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="61cd6-224">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="61cd6-224">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="61cd6-225">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="61cd6-225">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[<span data-ttu-id="61cd6-226">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="61cd6-226">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="61cd6-227">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="61cd6-227">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="61cd6-228">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="61cd6-228">Remove-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSession)
