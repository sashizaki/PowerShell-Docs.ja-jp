---
description: PowerShell セッション (PSSession) を切断して再接続する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_disconnected_sessions?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Disconnected_Sessions
ms.openlocfilehash: f4dbcd4d9255e4285687692902a41a3f3f40e093
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223800"
---
# <a name="about-remote-disconnected-sessions"></a><span data-ttu-id="92d1f-104">切断されたリモートセッションについて</span><span class="sxs-lookup"><span data-stu-id="92d1f-104">About Remote Disconnected Sessions</span></span>

## <a name="short-description"></a><span data-ttu-id="92d1f-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="92d1f-105">Short description</span></span>

<span data-ttu-id="92d1f-106">PowerShell セッション (PSSession) を切断して再接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-106">Explains how to disconnect and reconnect to a PowerShell Session (PSSession).</span></span>

## <a name="long-description"></a><span data-ttu-id="92d1f-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="92d1f-107">Long description</span></span>

<span data-ttu-id="92d1f-108">PowerShell 3.0 以降では、PSSession から切断し、同じコンピューターまたは別のコンピューター上の PSSession に再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-108">Beginning in PowerShell 3.0, you can disconnect from a PSSession and reconnect to the PSSession on the same computer or a different computer.</span></span> <span data-ttu-id="92d1f-109">セッション状態が維持され、PSSession 内のコマンドはセッションが切断されている間も引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-109">The session state is maintained and commands in the PSSession continue to run while the session is disconnected.</span></span>

<span data-ttu-id="92d1f-110">切断されたセッション機能は、リモートコンピューターで PowerShell 3.0 以降のバージョンが実行されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-110">The Disconnected Sessions feature is only available when the remote computer is running PowerShell 3.0 or a later version.</span></span>

<span data-ttu-id="92d1f-111">切断されたセッション機能を使用すると、pssession で実行されているコマンドを中断することなく、PSSession が作成されたセッションを終了し、PowerShell を閉じてコンピューターをシャットダウンすることができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-111">The Disconnected Sessions feature allows you to close the session in which a PSSession was created, and even close PowerShell, and shut down the computer, without disrupting commands running in the PSSession.</span></span> <span data-ttu-id="92d1f-112">切断されたセッションは、完了までに時間がかかるコマンドを実行する場合に便利です。また、IT プロフェッショナルに必要な時間とデバイスの柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-112">Disconnected sessions are useful for running commands that take an extended time to complete, and provides the time and device flexibility that IT professionals require.</span></span>

<span data-ttu-id="92d1f-113">コマンドレットを使用して起動された対話型セッションから切断することはできません `Enter-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="92d1f-113">You can't disconnect from an interactive session that is started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="92d1f-114">切断されたセッションを使用すると、コンピューターやネットワークの停止の結果として意図せず切断された pssession を管理できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-114">You can use disconnected sessions to manage PSSessions that were disconnected unintentionally as the result of a computer or network outage.</span></span>

<span data-ttu-id="92d1f-115">実際の使用では、切断されたセッション機能を使用して、問題の解決を開始し、優先度の高い問題に対処してから、別の場所にある別のコンピューターでも、ソリューションで作業を再開することができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-115">In real-world use, the Disconnected Sessions feature allows you to begin solving a problem, turn your attention to a higher priority issue, and then resume work on the solution, even on a different computer in a different location.</span></span>

## <a name="disconnected-session-cmdlets"></a><span data-ttu-id="92d1f-116">切断されたセッションのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="92d1f-116">Disconnected session cmdlets</span></span>

<span data-ttu-id="92d1f-117">次のコマンドレットは、切断されたセッション機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="92d1f-117">The following cmdlets support the Disconnected Sessions feature:</span></span>

- <span data-ttu-id="92d1f-118">`Connect-PSSession`: 切断された PSSession に接続します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-118">`Connect-PSSession`: Connects to a disconnected PSSession.</span></span>
- <span data-ttu-id="92d1f-119">`Disconnect-PSSession`: PSSession を切断します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-119">`Disconnect-PSSession`: Disconnects a PSSession.</span></span>
- <span data-ttu-id="92d1f-120">`Get-PSSession`: ローカルコンピューターまたはリモートコンピューター上の pssession を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-120">`Get-PSSession`: Gets PSSessions on the local computer or on remote computers.</span></span>
- <span data-ttu-id="92d1f-121">`Receive-PSSession`: 切断されたセッションで実行されたコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-121">`Receive-PSSession`: Gets the results of commands that ran in disconnected sessions.</span></span>
- <span data-ttu-id="92d1f-122">`Invoke-Command`: **Indisconnectedsession** パラメーターは PSSession を作成し、直ちに切断します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-122">`Invoke-Command`: **InDisconnectedSession** parameter creates a PSSession and disconnects immediately.</span></span>

## <a name="how-the-disconnected-sessions-feature-works"></a><span data-ttu-id="92d1f-123">切断されたセッション機能の動作</span><span class="sxs-lookup"><span data-stu-id="92d1f-123">How the Disconnected Sessions feature works</span></span>

<span data-ttu-id="92d1f-124">PowerShell 3.0 以降では、PSSessions は、そのセッションが作成されたセッションから独立しています。</span><span class="sxs-lookup"><span data-stu-id="92d1f-124">Beginning in PowerShell 3.0, PSSessions are independent of the sessions in which they're created.</span></span> <span data-ttu-id="92d1f-125">PSSession が作成されたセッションが閉じられ、元のコンピューターがネットワークから切断されている場合でも、アクティブな PSSessions は接続のリモートコンピューターまたは **サーバー側** で保持されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-125">Active PSSessions are maintained on the remote computer or **server-side** of the connection, even if the session in which the PSSession was created is closed and the originating computer is shut down or disconnected from the network.</span></span>

<span data-ttu-id="92d1f-126">PowerShell 2.0 では、元のセッションまたは作成されたセッションから切断されたときに、リモートコンピューターから PSSession が削除されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-126">In PowerShell 2.0, the PSSession is deleted from the remote computer when it's disconnected from the originating session or the session in which it was created ends.</span></span>

<span data-ttu-id="92d1f-127">PSSession を切断すると、PSSession はアクティブのままになり、リモートコンピューター上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-127">When you disconnect a PSSession, the PSSession remains active and is maintained on the remote computer.</span></span> <span data-ttu-id="92d1f-128">セッションの状態が " **実行中** " から " **切断** " に変わります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-128">The session state changes from **Running** to **Disconnected**.</span></span> <span data-ttu-id="92d1f-129">切断された PSSession には、現在のセッションから、または同じコンピューター上の別のセッションから、または別のコンピューターから再接続できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-129">You can reconnect to a disconnected PSSession from the current session or from a different session on the same computer, or from a different computer.</span></span> <span data-ttu-id="92d1f-130">セッションを管理するリモートコンピューターは、を実行していて、ネットワークに接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-130">The remote computer that maintains the session must be running and be connected to the network.</span></span>

<span data-ttu-id="92d1f-131">切断された PSSession 内のコマンドは、コマンドが完了するか出力バッファーがいっぱいになるまで、リモートコンピューター上でも継続して実行されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-131">Commands in a disconnected PSSession continue to run uninterrupted on the remote computer until the command completes or the output buffer fills.</span></span> <span data-ttu-id="92d1f-132">完全な出力バッファーによってコマンドが中断されない **OutputBufferingMode** ようにするには、 `Disconnect-PSSession` 、 `New-PSSessionOption` 、またはコマンドレットの OutputBufferingMode パラメーターを使用し `New-PSTransportOption` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-132">To prevent a full output buffer from suspending a command, use the **OutputBufferingMode** parameter of the `Disconnect-PSSession`, `New-PSSessionOption`, or `New-PSTransportOption` cmdlets.</span></span>

<span data-ttu-id="92d1f-133">切断されたセッションは、リモートコンピューターの切断状態で保持されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-133">Disconnected sessions are maintained in the disconnected state on the remote computer.</span></span> <span data-ttu-id="92d1f-134">コマンドレットを使用する `Remove-PSSession` か、pssession のアイドルタイムアウトが期限切れになるまで、pssession を削除するまで、再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-134">They're available for you to reconnect, until you delete the PSSession, such as by using the `Remove-PSSession` cmdlet, or until the idle timeout of the PSSession expires.</span></span> <span data-ttu-id="92d1f-135">、、 **IdleTimeoutSec** **IdleTimeout** `Disconnect-PSSession` `New-PSSessionOption` またはコマンドレットの IdleTimeoutSec パラメーターまたは IdleTimeout パラメーターを使用して、PSSession のアイドルタイムアウトを調整でき `New-PSTransportOption` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-135">You can adjust the idle timeout of a PSSession by using the **IdleTimeoutSec** or **IdleTimeout** parameters of the `Disconnect-PSSession`, `New-PSSessionOption`, or `New-PSTransportOption` cmdlets.</span></span>

<span data-ttu-id="92d1f-136">別のユーザーが作成した pssession に接続できるのは、セッションの作成に使用された資格情報を提供できる場合、または `RunAs` セッション構成の資格情報を使用する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="92d1f-136">Another user can connect to PSSessions that you created, but only if they can provide the credentials that were used to create the session, or use the `RunAs` credentials of the session configuration.</span></span>

## <a name="how-to-get-pssessions"></a><span data-ttu-id="92d1f-137">PSSessions を取得する方法</span><span class="sxs-lookup"><span data-stu-id="92d1f-137">How to get PSSessions</span></span>

<span data-ttu-id="92d1f-138">PowerShell 3.0 以降では、 `Get-PSSession` コマンドレットは、ローカルコンピューターとリモートコンピューター上の PSSessions を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-138">Beginning in PowerShell 3.0, the `Get-PSSession` cmdlet gets PSSessions on the local computer and remote computers.</span></span> <span data-ttu-id="92d1f-139">また、現在のセッションで作成された pssession を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-139">It can also get PSSessions that were created in the current session.</span></span>

<span data-ttu-id="92d1f-140">ローカルコンピューターまたはリモートコンピューターで PSSessions を取得するには、 **ComputerName** パラメーターまたは **connectionuri** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-140">To get PSSessions on the local computer or remote computers, use the **ComputerName** or **ConnectionUri** parameters.</span></span> <span data-ttu-id="92d1f-141">パラメーターを指定しない場合、は、 `Get-PSSession` 終了位置に関係なく、ローカルセッションで作成された PSSession を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-141">Without parameters, `Get-PSSession` gets PSSession that were created in the local session, regardless of where they terminate.</span></span>

<span data-ttu-id="92d1f-142">PSSessions を取得するときは、それらが保持されているコンピューター (つまり、リモートコンピューターまたは **サーバー側** のコンピューター) でそれらを検索してください。</span><span class="sxs-lookup"><span data-stu-id="92d1f-142">When getting PSSessions, remember to look for them on the computer on which they're maintained, that is, the remote or **server-side** computer.</span></span>

<span data-ttu-id="92d1f-143">たとえば、Server01 コンピューターへの PSSession を作成する場合は、Server01 コンピューターからセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-143">For example, if you create a PSSession to the Server01 computer, get the session from the Server01 computer.</span></span> <span data-ttu-id="92d1f-144">別のコンピューターからローカルコンピューターに PSSession を作成する場合は、ローカルコンピューターからセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-144">If you create a PSSession from another computer to the local computer, get the session from the local computer.</span></span>

<span data-ttu-id="92d1f-145">次のコマンドシーケンスは、がどのように動作するかを示して `Get-PSSession` います。</span><span class="sxs-lookup"><span data-stu-id="92d1f-145">The following command sequence shows how `Get-PSSession` works.</span></span>

<span data-ttu-id="92d1f-146">最初のコマンドは、Server01 コンピューターへのセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-146">The first command creates a session to the Server01 computer.</span></span> <span data-ttu-id="92d1f-147">セッションは Server01 コンピューター上に存在します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-147">The session resides on the Server01 computer.</span></span>

```powershell
New-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

<span data-ttu-id="92d1f-148">セッションを取得するには、の **ComputerName** パラメーターに `Get-PSSession` 値 Server01 を指定します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-148">To get the session, use the **ComputerName** parameter of `Get-PSSession` with a value of Server01.</span></span>

```powershell
Get-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

<span data-ttu-id="92d1f-149">の **ComputerName** パラメーターの値 `Get-PSSession` が localhost の場合、は、 `Get-PSSession` で終了し、ローカルコンピューター上で保持されている pssession を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-149">If the value of the **ComputerName** parameter of `Get-PSSession` is localhost, `Get-PSSession` gets PSSessions that terminate at and are maintained on the local computer.</span></span> <span data-ttu-id="92d1f-150">Server01 コンピューターでは、ローカルコンピューターで開始された場合でも、PSSessions は取得されません。</span><span class="sxs-lookup"><span data-stu-id="92d1f-150">It doesn't get PSSessions on the Server01 computer, even if they were started on the local computer.</span></span>

```powershell
Get-PSSession -ComputerName localhost
```

<span data-ttu-id="92d1f-151">現在のセッションで作成されたセッションを取得するには、 `Get-PSSession` パラメーターを指定せずにコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-151">To get sessions that were created in the current session, use the `Get-PSSession` cmdlet without parameters.</span></span> <span data-ttu-id="92d1f-152">この例では、は、 `Get-PSSession` 現在のセッションで作成された PSSession を取得し、Server01 コンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-152">In this example, `Get-PSSession` gets the PSSession that was created in the current session and connects to the Server01 computer.</span></span>

```powershell
Get-PSSession
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-disconnect-sessions"></a><span data-ttu-id="92d1f-153">セッションを切断する方法</span><span class="sxs-lookup"><span data-stu-id="92d1f-153">How to disconnect sessions</span></span>

<span data-ttu-id="92d1f-154">PSSession を切断するには、 `Disconnect-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-154">To disconnect a PSSession, use the `Disconnect-PSSession` cmdlet.</span></span> <span data-ttu-id="92d1f-155">PSSession を特定するには、 **セッション** パラメーターを使用するか、 `New-PSSession` またはコマンドレットの pssession をにパイプラインで指定し `Get-PSSession` `Disconnect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-155">To identify the PSSession, use the **Session** parameter, or pipeline a PSSession from the `New-PSSession` or `Get-PSSession` cmdlets to `Disconnect-PSSession`.</span></span>

<span data-ttu-id="92d1f-156">次のコマンドは、PSSession を Server01 コンピューターに切断します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-156">The following command disconnects the PSSession to the Server01 computer.</span></span>
<span data-ttu-id="92d1f-157">**State** プロパティの値が **Disconnected** であり、 **Availability** が **None** であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="92d1f-157">Notice that the value of the **State** property is **Disconnected** and the **Availability** is **None**.</span></span>

```powershell
Get-PSSession -ComputerName Server01 | Disconnect-PSSession
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 2 Session2  Server01      Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="92d1f-158">切断されたセッションを作成するには、コマンドレットの **Indisconnectedsession** パラメーターを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-158">To create a disconnected session, use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="92d1f-159">コマンドが出力を返す前に、セッションを作成し、コマンドを起動して、直ちに切断します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-159">It creates a session, starts the command, and disconnects immediately, before the command can return any output.</span></span>

<span data-ttu-id="92d1f-160">次のコマンドは、 `Get-WinEvent` Server02 リモートコンピューター上の切断されたセッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-160">The following command runs a `Get-WinEvent` command in a disconnected session on the Server02 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server02 -InDisconnectedSession -ScriptBlock {
   Get-WinEvent -LogName "*PowerShell*" }
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 4 Session3  Server02      Disconnected  Microsoft.PowerShell          None
```

## <a name="how-to-connect-to-disconnected-sessions"></a><span data-ttu-id="92d1f-161">切断されたセッションに接続する方法</span><span class="sxs-lookup"><span data-stu-id="92d1f-161">How to connect to disconnected sessions</span></span>

<span data-ttu-id="92d1f-162">PSSession を作成したセッション、またはローカルコンピューターまたは他のコンピューター上の他のセッションから、使用可能な切断された PSSession に接続できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-162">You can connect to any available disconnected PSSession from the session in which you created the PSSession or from other sessions on the local computer or other computers.</span></span>

<span data-ttu-id="92d1f-163">PSSession の作成、pssession でのコマンドの実行、PSSession からの切断、PowerShell の終了、コンピューターのシャットダウンを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-163">You can create a PSSession, run commands in the PSSession, disconnect from the PSSession, close PowerShell, and shut down the computer.</span></span> <span data-ttu-id="92d1f-164">後で、別のコンピューターを開いて、PSSession を取得し、接続して、切断中に PSSession で実行されたコマンドの結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-164">Hours later, you can open a different computer, get the PSSession, connect to it, and get the results of commands that ran in the PSSession while it was disconnected.</span></span> <span data-ttu-id="92d1f-165">その後、セッションで他のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-165">Then you can run more commands in the session.</span></span>

<span data-ttu-id="92d1f-166">切断された PSSession を接続するには、コマンドレットを使用し `Connect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-166">To connect a disconnected PSSession, use the `Connect-PSSession` cmdlet.</span></span> <span data-ttu-id="92d1f-167">**ComputerName** または **connectionuri** パラメーターを使用して pssession を識別します。または、からに pssession を渡すことも `Get-PSSession` `Connect-PSSession` できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-167">Use the **ComputerName** or **ConnectionUri** parameters to identify the PSSession, or pipeline a PSSession from `Get-PSSession` to `Connect-PSSession`.</span></span>

<span data-ttu-id="92d1f-168">次のコマンドは、Server02 コンピューター上のセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-168">The following command gets the sessions on the Server02 computer.</span></span> <span data-ttu-id="92d1f-169">出力には、2つの切断されたセッションが含まれています。どちらも使用できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-169">The output includes two disconnected sessions, both of which are available.</span></span>

```powershell
Get-PSSession -ComputerName Server02
```

```Output
Id Name      ComputerName   State         ConfigurationName     Availability
-- ----      ------------   -----         -----------------     ------------
 2 Session2  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
 4 Session3  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="92d1f-170">次のコマンドは、Session2 に接続します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-170">The following command connects to Session2.</span></span> <span data-ttu-id="92d1f-171">これで PSSession が開き、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="92d1f-171">The PSSession is now open and available.</span></span>

```powershell
Connect-PSSession -ComputerName Server02 -Name Session2
```

```Output
Id Name      ComputerName    State    ConfigurationName     Availability
-- ----      ------------    -----    -----------------     ------------
 2 Session2  juneb-srv8320   Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-get-the-results"></a><span data-ttu-id="92d1f-172">結果を取得する方法</span><span class="sxs-lookup"><span data-stu-id="92d1f-172">How to get the results</span></span>

<span data-ttu-id="92d1f-173">切断された PSSession で実行されたコマンドの結果を取得するには、コマンドレットを使用し `Receive-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-173">To get the results of commands that ran in a disconnected PSSession, use the `Receive-PSSession` cmdlet.</span></span>

<span data-ttu-id="92d1f-174">`Receive-PSSession`コマンドレットを使用するのではなく、を使用でき `Connect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-174">You can use `Receive-PSSession` rather than using the `Connect-PSSession` cmdlet.</span></span> <span data-ttu-id="92d1f-175">セッションが既に再接続されている場合、は、 `Receive-PSSession` セッションが切断されたときに実行されたコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-175">If the session is already reconnected, `Receive-PSSession` gets the results of commands that ran when the session was disconnected.</span></span> <span data-ttu-id="92d1f-176">PSSession がまだ切断されている場合、は `Receive-PSSession` それに接続し、切断されたときに実行されたコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-176">If the PSSession is still disconnected, `Receive-PSSession` connects to it and then gets the results of commands that ran while it was disconnected.</span></span>

<span data-ttu-id="92d1f-177">`Receive-PSSession` は、ジョブ (非同期) またはホストプログラムに (同期的に) 結果を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-177">`Receive-PSSession` can return the results in a job (asynchronously) or to the host program (synchronously).</span></span> <span data-ttu-id="92d1f-178">**ジョブ** または **ホスト** を選択するには、 **outtarget** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-178">Use the **OutTarget** parameter to select **Job** or **Host**.</span></span> <span data-ttu-id="92d1f-179">既定値は **Host** です。</span><span class="sxs-lookup"><span data-stu-id="92d1f-179">The default value is **Host**.</span></span> <span data-ttu-id="92d1f-180">ただし、受信しているコマンドが現在のセッションで **ジョブ** として開始されている場合、既定では **ジョブ** として返されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-180">However, if the command that's being received was started in the current session as a **Job** , it's returned as a **Job** by default.</span></span>

<span data-ttu-id="92d1f-181">次のコマンドは、コマンドレットを使用して、 `Receive-PSSession` Server02 コンピューター上の PSSession に接続し、 `Get-WinEvent` Session3 セッションで実行されたコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-181">The following command uses the `Receive-PSSession` cmdlet to connect to the PSSession on the Server02 computer and get the results of the `Get-WinEvent` command that ran in the Session3 session.</span></span> <span data-ttu-id="92d1f-182">このコマンドは、 **Outtarget** パラメーターを使用して、 **ジョブ** の結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-182">The command uses the **OutTarget** parameter to get the results in a **Job**.</span></span>

```powershell
Receive-PSSession -ComputerName Server02 -Name Session3 -OutTarget Job
```

```Output
Id   Name   PSJobTypeName   State         HasMoreData     Location
--   ----   -------------   -----         -----------     --------
 3   Job3   RemoteJob       Running       True            Server02
```

<span data-ttu-id="92d1f-183">ジョブの結果を取得するには、 `Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-183">To get the job's results, use the `Receive-Job` cmdlet.</span></span>

```powershell
Get-Job | Receive-Job -Keep
```

```Output
ProviderName: PowerShell

TimeCreated             Id LevelDisplayName Message     PSComputerName
-----------             -- ---------------- -------     --------------
5/14/2012 7:26:04 PM   400 Information      Engine stat Server02
5/14/2012 7:26:03 PM   600 Information      Provider "W Server02
5/14/2012 7:26:03 PM   600 Information      Provider "C Server02
5/14/2012 7:26:03 PM   600 Information      Provider "V Server02
```

## <a name="state-and-availability-properties"></a><span data-ttu-id="92d1f-184">状態と可用性のプロパティ</span><span class="sxs-lookup"><span data-stu-id="92d1f-184">State and Availability properties</span></span>

<span data-ttu-id="92d1f-185">切断された PSSession の **状態** と **可用性** のプロパティは、セッションを再接続できるかどうかを通知します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-185">The **State** and **Availability** properties of a disconnected PSSession tell you whether the session is available for you to reconnect to it.</span></span>

<span data-ttu-id="92d1f-186">PSSession が現在のセッションに接続されると、その状態が **開か** れ、その可用性が **利用可能** になります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-186">When a PSSession is connected to the current session, its state is **Opened** and its availability is **Available**.</span></span> <span data-ttu-id="92d1f-187">PSSession から切断すると、PSSession の状態は **Disconnected** になり、その可用性は **None** になります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-187">When you disconnect from the PSSession, the PSSession state is **Disconnected** and its availability is **None**.</span></span>

<span data-ttu-id="92d1f-188">**State** プロパティの値は、現在のセッションに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="92d1f-188">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="92d1f-189">値が **Disconnected** の場合は、PSSession が現在のセッションに接続されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-189">A value of **Disconnected** means that the PSSession isn't connected to the current session.</span></span> <span data-ttu-id="92d1f-190">ただし、PSSession がすべてのセッションから切断されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="92d1f-190">But, it doesn't mean that the PSSession is disconnected from all sessions.</span></span> <span data-ttu-id="92d1f-191">別のセッションに接続されている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="92d1f-191">It might be connected to a different session.</span></span>

<span data-ttu-id="92d1f-192">PSSession に接続または再接続できるかどうかを判断するには、 **Availability** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-192">To determine whether you can connect or reconnect to the PSSession, use the **Availability** property.</span></span> <span data-ttu-id="92d1f-193">値 **None** は、セッションに接続できることを示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-193">A value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="92d1f-194">値が **Busy** の場合は、PSSession が別のセッションに接続されているため、PSSession に接続できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-194">A value of **Busy** indicates that you can't connect to the PSSession because it's connected to another session.</span></span>

<span data-ttu-id="92d1f-195">次の例は、同じコンピューター上の2つの PowerShell セッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-195">The following example is run in two PowerShell sessions on the same computer.</span></span>
<span data-ttu-id="92d1f-196">PSSession が切断されて再接続されると、各セッションの **状態** と **可用性** のプロパティの値を変更することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="92d1f-196">Note the changing values of the **State** and **Availability** properties in each session as the PSSession is disconnected and reconnected.</span></span>

```powershell
# Session 1
New-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30 -Name Test | Disconnect-PSSession
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Connect-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
3 Test    Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```Output
# Idle Timeout
```

<span data-ttu-id="92d1f-197">切断されたセッションは、コマンドレットなどを使用して削除するか、タイムアウトにするまで、リモートコンピューター上で保持され `Remove-PSSession` ます。PSSession の **IdleTimeout** プロパティは、切断されたセッションが削除されるまでの期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-197">Disconnected sessions are maintained on the remote computer until you delete them, such as by using the `Remove-PSSession` cmdlet, or they time out. The **IdleTimeout** property of a PSSession determines how long a disconnected session is maintained before it's deleted.</span></span>

<span data-ttu-id="92d1f-198">PSSessions は、 **ハートビートスレッド** が応答を受信しなかったときにアイドル状態になります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-198">PSSessions are idle when the **heartbeat thread** receives no response.</span></span>
<span data-ttu-id="92d1f-199">セッションを切断すると、切断されたセッションでコマンドがまだ実行されている場合でも、アイドル状態になり、 **IdleTimeout** クロックが開始されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-199">Disconnecting a session makes it idle and starts the **IdleTimeout** clock, even if commands are still running in the disconnected session.</span></span> <span data-ttu-id="92d1f-200">PowerShell は、切断されたセッションをアクティブにし、アイドル状態と見なします。</span><span class="sxs-lookup"><span data-stu-id="92d1f-200">PowerShell considers disconnected sessions to be active, but idle.</span></span>

<span data-ttu-id="92d1f-201">セッションを作成または切断するときに、PSSession のアイドルタイムアウトが、必要なセッションを維持するのに十分な長さであることを確認します。ただし、リモートコンピューター上の不要なリソースを消費することはありません。</span><span class="sxs-lookup"><span data-stu-id="92d1f-201">When creating and disconnecting sessions, verify that the idle timeout in the PSSession is long enough to maintain the session for your needs, but not so long that it consumes unnecessary resources on the remote computer.</span></span>

<span data-ttu-id="92d1f-202">セッション構成の **IdleTimeoutMs** プロパティによって、セッション構成を使用するセッションの既定のアイドルタイムアウトが決まります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-202">The **IdleTimeoutMs** property of the session configuration determines the default idle timeout of sessions that use the session configuration.</span></span> <span data-ttu-id="92d1f-203">既定値を上書きすることはできますが、使用する値はセッション構成の **MaxIdleTimeoutMs** プロパティを超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="92d1f-203">You can override the default value, but the value that you use can't exceed the **MaxIdleTimeoutMs** property of the session configuration.</span></span>

<span data-ttu-id="92d1f-204">セッション構成の **IdleTimeoutMs** 値と **MaxIdleTimeoutMs** 値の値を調べるには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-204">To find the value of the **IdleTimeoutMs** and **MaxIdleTimeoutMs** values of a session configuration, use the following command format.</span></span>

```powershell
Get-PSSessionConfiguration |
  Format-Table Name, IdleTimeoutMs, MaxIdleTimeoutMs
```

<span data-ttu-id="92d1f-205">セッション構成の既定値を上書きし、PSSession の作成時や切断時に PSSession のアイドルタイムアウトを設定できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-205">You can override the default value in the session configuration and set the idle timeout of a PSSession when you create a PSSession and when you disconnect.</span></span>

<span data-ttu-id="92d1f-206">リモートコンピューターの Administrators グループのメンバーである場合は、セッション構成の **IdleTimeoutMs** プロパティと **MaxIdleTimeoutMs** プロパティを作成および変更できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-206">If you're a member of the Administrators group on the remote computer, you can create and change the **IdleTimeoutMs** and **MaxIdleTimeoutMs** properties of session configurations.</span></span>

## <a name="idle-timeout-values"></a><span data-ttu-id="92d1f-207">アイドルタイムアウト値</span><span class="sxs-lookup"><span data-stu-id="92d1f-207">Idle timeout values</span></span>

<span data-ttu-id="92d1f-208">セッション構成とセッションオプションのアイドルタイムアウト値は、ミリ秒単位です。</span><span class="sxs-lookup"><span data-stu-id="92d1f-208">The idle timeout value of session configurations and session options is in milliseconds.</span></span> <span data-ttu-id="92d1f-209">セッションのアイドルタイムアウト値とセッション構成オプションは、秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-209">The idle timeout value of sessions and session configuration options is in seconds.</span></span>

<span data-ttu-id="92d1f-210">Pssession (、) を作成したとき `New-PSSession` と、その接続を切断したとき () に、pssession のアイドルタイムアウトを設定でき `Invoke-Command` `Disconnect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-210">You can set the idle timeout of a PSSession when you create the PSSession (`New-PSSession`, `Invoke-Command`) and when you disconnect from it (`Disconnect-PSSession`).</span></span> <span data-ttu-id="92d1f-211">ただし、PSSession () に接続するときや、結果を取得するとき ()、 **IdleTimeout** 値を変更することはできません `Connect-PSSession` `Receive-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="92d1f-211">However, you can't change the **IdleTimeout** value when you connect to the PSSession (`Connect-PSSession`) or get results (`Receive-PSSession`).</span></span>

<span data-ttu-id="92d1f-212">コマンドレットとコマンドレットには、 `Connect-PSSession` `Receive-PSSession` コマンドレットによって返されるような **sessionoption** オブジェクトを受け取る **sessionoption** パラメーターがあり `New-PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-212">The `Connect-PSSession` and `Receive-PSSession` cmdlets have a **SessionOption** parameter that takes a **SessionOption** object, such as one returned by the `New-PSSessionOption` cmdlet.</span></span> <span data-ttu-id="92d1f-213">**Sessionoption** オブジェクトの **idletimeout** 値と、ユーザー設定変数の **idletimeout** 値は、 `$PSSessionOption` またはコマンドで PSSession の **idletimeout** の値を変更しません `Connect-PSSession` `Receive-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="92d1f-213">The **IdleTimeout** value in **SessionOption** object and the **IdleTimeout** value in the `$PSSessionOption` preference variable don't change the value of the **IdleTimeout** of the PSSession in a `Connect-PSSession` or `Receive-PSSession` command.</span></span>

<span data-ttu-id="92d1f-214">特定のアイドルタイムアウト値を使用して PSSession を作成するには、ユーザー設定変数を作成し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-214">To create a PSSession with a particular idle timeout value, create a `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="92d1f-215">**IdleTimeout** プロパティの値を目的の値 (ミリ秒単位) に設定します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-215">Set the value of the **IdleTimeout** property to the desired value (in milliseconds).</span></span>

<span data-ttu-id="92d1f-216">PSSessions を作成すると、変数の値は、 `$PSSessionOption` セッション構成の値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-216">When you create PSSessions, the values in `$PSSessionOption` variable take precedence over the values in the session configuration.</span></span>

<span data-ttu-id="92d1f-217">たとえば、次のコマンドでは、アイドルタイムアウトが48時間に設定されています。</span><span class="sxs-lookup"><span data-stu-id="92d1f-217">For example, the following command sets an idle timeout of 48 hours:</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -IdleTimeoutMSec 172800000
```

<span data-ttu-id="92d1f-218">特定のアイドルタイムアウト値を使用して PSSession を作成するには、コマンドレットの **IdleTimeoutMSec** パラメーターを使用し `New-PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-218">To create a PSSession with a particular idle timeout value, use the **IdleTimeoutMSec** parameter of the `New-PSSessionOption` cmdlet.</span></span> <span data-ttu-id="92d1f-219">次に、またはコマンドレットの **sessionoption** パラメーターの値で session オプションを使用し `New-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-219">Then, use the session option in the value of the **SessionOption** parameter of the `New-PSSession` or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="92d1f-220">セッションの作成時に設定される値は、ユーザー設定変数およびセッション構成で設定された値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-220">The values set when creating the session take precedence over the values set in the `$PSSessionOption` preference variable and the session configuration.</span></span>

<span data-ttu-id="92d1f-221">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-221">For example:</span></span>

```powershell
$o = New-PSSessionOption -IdleTimeoutMSec 172800000
New-PSSession -SessionOption $o
```

<span data-ttu-id="92d1f-222">切断時の PSSession のアイドルタイムアウトを変更するには、コマンドレットの **IdleTimeoutSec** パラメーターを使用し `Disconnect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-222">To change the idle timeout of a PSSession when disconnecting, use the **IdleTimeoutSec** parameter of the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="92d1f-223">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-223">For example:</span></span>

```powershell
Disconnect-PSSession -IdleTimeoutSec 172800
```

<span data-ttu-id="92d1f-224">特定のアイドルタイムアウトと最大アイドルタイムアウトを使用してセッション構成を作成するには、コマンドレットの **IdleTimeoutSec** パラメーターと **MaxIdleTimeoutSec** パラメーターを使用し `New-PSTransportOption` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-224">To create a session configuration with a particular idle timeout and maximum idle timeout, use the **IdleTimeoutSec** and **MaxIdleTimeoutSec** parameters of the `New-PSTransportOption` cmdlet.</span></span> <span data-ttu-id="92d1f-225">次に、の **TransportOption** パラメーターの値で transport オプションを使用し `Register-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-225">Then, use the transport option in the value of the **TransportOption** parameter of `Register-PSSessionConfiguration`.</span></span>

<span data-ttu-id="92d1f-226">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-226">For example:</span></span>

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

<span data-ttu-id="92d1f-227">セッション構成の既定のアイドルタイムアウトと最大アイドルタイムアウトを変更するには、コマンドレットの **IdleTimeoutSec** パラメーターと **MaxIdleTimeoutSec** パラメーターを使用し `New-PSTransportOption` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-227">To change the default idle timeout and maximum idle timeout of a session configuration, use the **IdleTimeoutSec** and **MaxIdleTimeoutSec** parameters of the `New-PSTransportOption` cmdlet.</span></span> <span data-ttu-id="92d1f-228">次に、の **TransportOption** パラメーターの値で transport オプションを使用し `Set-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-228">Then, use the transport option in the value of the **TransportOption** parameter of `Set-PSSessionConfiguration`.</span></span>

<span data-ttu-id="92d1f-229">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-229">For example:</span></span>

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="output-buffering-mode"></a><span data-ttu-id="92d1f-230">出力バッファーモード</span><span class="sxs-lookup"><span data-stu-id="92d1f-230">Output buffering mode</span></span>

<span data-ttu-id="92d1f-231">Pssession の出力バッファーモードによって、PSSession の出力バッファーがいっぱいになったときのコマンド出力の管理方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-231">The output buffering mode of a PSSession determines how command output is managed when the output buffer of the PSSession is full.</span></span>

<span data-ttu-id="92d1f-232">切断されたセッションでは、出力バッファーモードは、セッションが切断されている間もコマンドを実行し続けるかどうかを効果的に判断します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-232">In a disconnected session, the output buffering mode effectively determines whether the command continues to run while the session is disconnected.</span></span>

<span data-ttu-id="92d1f-233">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="92d1f-233">The valid values as follows:</span></span>

- <span data-ttu-id="92d1f-234">**[ブロック]** 。</span><span class="sxs-lookup"><span data-stu-id="92d1f-234">**Block**.</span></span> <span data-ttu-id="92d1f-235">出力バッファーがいっぱいのとき、バッファーが空くまで実行が中断されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-235">When the output buffer is full, execution is suspended until the buffer is clear.</span></span> <span data-ttu-id="92d1f-236">既定値。</span><span class="sxs-lookup"><span data-stu-id="92d1f-236">The default value.</span></span>
- <span data-ttu-id="92d1f-237">**[削除]** 。</span><span class="sxs-lookup"><span data-stu-id="92d1f-237">**Drop**.</span></span> <span data-ttu-id="92d1f-238">出力バッファーがいっぱいのとき、実行は続行されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-238">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="92d1f-239">新しい出力が生成されると、最も古い出力が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-239">As new output is generated, the oldest output is discarded.</span></span>

<span data-ttu-id="92d1f-240">**ブロック** はデータを保持しますが、コマンドを中断する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-240">**Block** preserves data, but might interrupt the command.</span></span> <span data-ttu-id="92d1f-241">値が **Drop** の場合は、データが失われる可能性はありますが、コマンドを完了できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-241">A value of **Drop** allows the command to complete, although data might be lost.</span></span> <span data-ttu-id="92d1f-242">**Drop** 値を使用すると、コマンド出力がディスク上のファイルにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-242">When using the **Drop** value, redirect the command output to a file on disk.</span></span> <span data-ttu-id="92d1f-243">この値は、切断されたセッションにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92d1f-243">This value is recommended for disconnected sessions.</span></span>

<span data-ttu-id="92d1f-244">セッション構成の **OutputBufferingMode** プロパティによって、セッション構成を使用するセッションの既定の出力バッファーモードが決まります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-244">The **OutputBufferingMode** property of the session configuration determines the default output buffering mode of sessions that use the session configuration.</span></span>

<span data-ttu-id="92d1f-245">**OutputBufferingMode** のセッション構成の値を検索するには、次のいずれかのコマンド形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-245">To find a session configuration's value of the **OutputBufferingMode** , you can use either of the following command formats:</span></span>

```powershell
(Get-PSSessionConfiguration <ConfigurationName>).OutputBufferingMode
```

```powershell
Get-PSSessionConfiguration | Format-Table Name, OutputBufferingMode
```

<span data-ttu-id="92d1f-246">セッション構成の既定値を上書きし、PSSession の作成時、切断時、再接続時に PSSession の出力バッファーモードを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-246">You can override the default value in the session configuration and set the output buffering mode of a PSSession when you create a PSSession, when you disconnect, and when you reconnect.</span></span>

<span data-ttu-id="92d1f-247">リモートコンピューターの Administrators グループのメンバーである場合は、セッション構成の出力バッファーモードを作成および変更できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-247">If you're a member of the Administrators group on the remote computer, you can create and change the output buffering mode of session configurations.</span></span>

<span data-ttu-id="92d1f-248">出力バッファリングモードが **drop** の PSSession を作成するに `$PSSessionOption` は、 **OutputBufferingMode** プロパティの値が **drop** に設定されているユーザー設定変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-248">To create a PSSession with an output buffering mode of **Drop** , create a `$PSSessionOption` preference variable in which the value of the **OutputBufferingMode** property is **Drop**.</span></span>

<span data-ttu-id="92d1f-249">PSSessions を作成すると、変数の値は、 `$PSSessionOption` セッション構成の値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-249">When you create PSSessions, the values in `$PSSessionOption` variable take precedence over the values in the session configuration.</span></span>

<span data-ttu-id="92d1f-250">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-250">For example:</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OutputBufferingMode Drop
```

<span data-ttu-id="92d1f-251">出力バッファリングモード **drop** を使用して PSSession を作成するには、コマンドレットの **OutputBufferingMode** パラメーターを使用して、 `New-PSSessionOption` 値 **drop** を指定したセッションオプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-251">To create a PSSession with an output buffering mode of **Drop** , use the **OutputBufferingMode** parameter of the `New-PSSessionOption` cmdlet to create a session option with a value of **Drop**.</span></span> <span data-ttu-id="92d1f-252">次に、またはコマンドレットの **sessionoption** パラメーターの値で session オプションを使用し `New-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-252">Then, use the session option in the value of the **SessionOption** parameter of the `New-PSSession` or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="92d1f-253">セッションの作成時に設定される値は、ユーザー設定変数およびセッション構成で設定された値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-253">The values set when creating the session take precedence over the values set in the `$PSSessionOption` preference variable and the session configuration.</span></span>

<span data-ttu-id="92d1f-254">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-254">For example:</span></span>

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
New-PSSession -SessionOption $o
```

<span data-ttu-id="92d1f-255">切断時に PSSession の出力バッファーモードを変更するには、コマンドレットの **OutputBufferingMode** パラメーターを使用し `Disconnect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-255">To change the output buffering mode of a PSSession when disconnecting, use the **OutputBufferingMode** parameter of the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="92d1f-256">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-256">For example:</span></span>

```powershell
Disconnect-PSSession -OutputBufferingMode Drop
```

<span data-ttu-id="92d1f-257">再接続時に PSSession の出力バッファーモードを変更するには、コマンドレットの **OutputBufferingMode** パラメーターを使用し `New-PSSessionOption` て、値 **Drop** を指定したセッションオプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-257">To change the output buffering mode of a PSSession when reconnecting, use the **OutputBufferingMode** parameter of the `New-PSSessionOption` cmdlet to create a session option with a value of **Drop**.</span></span> <span data-ttu-id="92d1f-258">次に、またはの **sessionoption** パラメーターの値で session オプションを使用し `Connect-PSSession` `Receive-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-258">Then, use the session option in the value of the **SessionOption** parameter of `Connect-PSSession` or `Receive-PSSession`.</span></span>

<span data-ttu-id="92d1f-259">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-259">For example:</span></span>

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
Connect-PSSession -ComputerName Server01 -Name Test -SessionOption $o
```

<span data-ttu-id="92d1f-260">既定の出力バッファーモード **drop** を使用してセッション構成を作成するには、コマンドレットの **OutputBufferingMode** パラメーターを使用して、 `New-PSTransportOption` 値 **drop** を指定してトランスポートオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-260">To create a session configuration with a default output buffering mode of **Drop** , use the **OutputBufferingMode** parameter of the `New-PSTransportOption` cmdlet to create a transport option object with a value of **Drop**.</span></span> <span data-ttu-id="92d1f-261">次に、の **TransportOption** パラメーターの値で transport オプションを使用し `Register-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-261">Then, use the transport option in the value of the **TransportOption** parameter of `Register-PSSessionConfiguration`.</span></span>

<span data-ttu-id="92d1f-262">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-262">For example:</span></span>

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

<span data-ttu-id="92d1f-263">セッション構成の既定の出力バッファーモードを変更するには、コマンドレットの **OutputBufferingMode** パラメーターを使用し `New-PSTransportOption` て、値 **Drop** を指定したトランスポートオプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-263">To change the default output buffering mode of a session configuration, use the **OutputBufferingMode** parameter of the `New-PSTransportOption` cmdlet to create a transport option with a value of **Drop**.</span></span> <span data-ttu-id="92d1f-264">次に、の **sessionoption** パラメーターの値で Transport オプションを使用し `Set-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-264">Then, use the Transport option in the value of the **SessionOption** parameter of `Set-PSSessionConfiguration`.</span></span>

<span data-ttu-id="92d1f-265">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-265">For example:</span></span>

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="disconnecting-loopback-sessions"></a><span data-ttu-id="92d1f-266">ループバックセッションの切断</span><span class="sxs-lookup"><span data-stu-id="92d1f-266">Disconnecting loopback sessions</span></span>

<span data-ttu-id="92d1f-267">ループバックセッション (ローカルセッション) は、同じコンピューター上で開始および終了する pssession です。</span><span class="sxs-lookup"><span data-stu-id="92d1f-267">Loopback sessions, or local sessions, are PSSessions that originate and terminate on the same computer.</span></span> <span data-ttu-id="92d1f-268">他の PSSessions と同様に、アクティブなループバックセッションは接続のリモートエンド (ローカルコンピューター) 上のコンピューターで保持されるため、ループバックセッションに接続して再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-268">Like other PSSessions, active loopback sessions are maintained on the computer on the remote end of the connection (the local computer), so you can disconnect from and reconnect to loopback sessions.</span></span>

<span data-ttu-id="92d1f-269">既定では、ループバックセッションは、他のコンピューターにアクセスするためにセッションで実行されるコマンドを許可しないネットワークセキュリティトークンを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-269">By default, loopback sessions are created with a network security token that doesn't permit commands run in the session to access other computers.</span></span> <span data-ttu-id="92d1f-270">ローカルコンピューターまたはリモートコンピューター上の任意のセッションから、ネットワークセキュリティトークンを持つループバックセッションに再接続できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-270">You can reconnect to loopback sessions that have a network security token from any session on the local computer or a remote computer.</span></span>

<span data-ttu-id="92d1f-271">ただし、、、またはコマンドレットの **EnableNetworkAccess** パラメーターを使用すると、 `New-PSSession` `Enter-PSSession` `Invoke-Command` 対話的なセキュリティトークンを使用してループバックセッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-271">However, if you use the **EnableNetworkAccess** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlet, the loopback session is created with an interactive security token.</span></span> <span data-ttu-id="92d1f-272">対話型トークンを使用すると、ループバックセッションで実行されるコマンドで他のコンピューターからデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-272">The interactive token enables commands that run in the loopback session to get data from other computers.</span></span>

<span data-ttu-id="92d1f-273">対話型トークンを使用してループバックセッションを切断し、同じセッションまたは同じコンピューター上の別のセッションからそれらに再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-273">You can disconnect loopback sessions with interactive tokens and then reconnect to them from the same session or a different session on the same computer.</span></span>
<span data-ttu-id="92d1f-274">ただし、悪意のあるアクセスを防ぐために、対話的なトークンを使用して、作成されたコンピューターからのみループバックセッションに再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-274">However, to prevent malicious access, you can reconnect to loopback sessions with interactive tokens only from the computer on which they were created.</span></span>

## <a name="waiting-for-jobs-in-disconnected-sessions"></a><span data-ttu-id="92d1f-275">切断されたセッションのジョブを待機しています</span><span class="sxs-lookup"><span data-stu-id="92d1f-275">Waiting for jobs in disconnected sessions</span></span>

<span data-ttu-id="92d1f-276">コマンド `Wait-Job` レットは、ジョブが完了するまで待機してから、コマンドプロンプトまたは次のコマンドに戻ります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-276">The `Wait-Job` cmdlet waits until a job completes and then returns to the command prompt or the next command.</span></span> <span data-ttu-id="92d1f-277">既定では、ジョブが実行されている `Wait-Job` セッションが切断されている場合、はを返します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-277">By default, `Wait-Job` returns if the session in which a job is running is disconnected.</span></span> <span data-ttu-id="92d1f-278">`Wait-Job`セッションが再接続されるまで待機するようにコマンドレットに指示するには、 **Opened** 状態で **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-278">To direct the `Wait-Job` cmdlet to wait until the session is reconnected, in the **Opened** state, use the **Force** parameter.</span></span> <span data-ttu-id="92d1f-279">詳細については、「 [待機-ジョブ](xref:Microsoft.PowerShell.Core.Wait-Job)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d1f-279">For more information, see [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).</span></span>

## <a name="robust-sessions-and-unintentional-disconnection"></a><span data-ttu-id="92d1f-280">堅牢なセッションと意図しない切断</span><span class="sxs-lookup"><span data-stu-id="92d1f-280">Robust sessions and unintentional disconnection</span></span>

<span data-ttu-id="92d1f-281">PSSession は、コンピューターの障害やネットワークの停止が原因で、意図せず切断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-281">A PSSession might be unintentionally disconnected because of a computer failure or network outage.</span></span> <span data-ttu-id="92d1f-282">PowerShell は PSSession の復旧を試みますが、その成功は原因の重大度と期間によって異なります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-282">PowerShell attempts to recover the PSSession, but its success depends upon the severity and duration of the cause.</span></span>

<span data-ttu-id="92d1f-283">意図せず切断された PSSession の状態は、 **壊れ** ているか **閉じ** られている可能性がありますが、 **切断** されることもあります。</span><span class="sxs-lookup"><span data-stu-id="92d1f-283">The state of an unintentionally disconnected PSSession might be **Broken** or **Closed** , but it might also be **Disconnected**.</span></span> <span data-ttu-id="92d1f-284">**State** の値が **disconnected** の場合は、セッションが意図的に切断された場合と同じ手法を使用して PSSession を管理できます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-284">If the value of **State** is **Disconnected** , you can use the same techniques to manage the PSSession as you would if the session were disconnected intentionally.</span></span> <span data-ttu-id="92d1f-285">たとえば、コマンドレットを使用してセッションに再接続し、コマンドレットを使用して、 `Connect-PSSession` `Receive-PSSession` セッションの切断中に実行されたコマンドの結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="92d1f-285">For example, you can use the `Connect-PSSession` cmdlet to reconnect to the session and the `Receive-PSSession` cmdlet to get results of commands that ran while the session was disconnected.</span></span>

<span data-ttu-id="92d1f-286">コマンドが PSSession で実行されているときに PSSession が作成されたセッションを終了 (終了) した場合、PowerShell は、リモートコンピューター上の **Disconnected** 状態の pssession を保持します。</span><span class="sxs-lookup"><span data-stu-id="92d1f-286">If you close (exit) the session in which a PSSession was created while commands are running in the PSSession, PowerShell maintains the PSSession in the **Disconnected** state on the remote computer.</span></span> <span data-ttu-id="92d1f-287">PSSession が作成されたセッションを終了 (終了) したが、PSSession で実行されているコマンドが存在しない場合、PowerShell は PSSession を維持しません。</span><span class="sxs-lookup"><span data-stu-id="92d1f-287">If you close (exit) the session in which a PSSession was created, but no commands are running in the PSSession, PowerShell doesn't attempt to maintain the PSSession.</span></span>

## <a name="see-also"></a><span data-ttu-id="92d1f-288">関連項目</span><span class="sxs-lookup"><span data-stu-id="92d1f-288">See also</span></span>

[<span data-ttu-id="92d1f-289">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="92d1f-289">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="92d1f-290">about_Remote</span><span class="sxs-lookup"><span data-stu-id="92d1f-290">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="92d1f-291">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="92d1f-291">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="92d1f-292">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="92d1f-292">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="92d1f-293">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="92d1f-293">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="92d1f-294">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="92d1f-294">Connect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[<span data-ttu-id="92d1f-295">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="92d1f-295">Disconnect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[<span data-ttu-id="92d1f-296">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="92d1f-296">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="92d1f-297">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="92d1f-297">Receive-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Receive-PSSession)

[<span data-ttu-id="92d1f-298">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="92d1f-298">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
