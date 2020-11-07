---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: 2904a614baa81f3baafef6394c82b682a8c4f032
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346736"
---
# <span data-ttu-id="393ed-103">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="393ed-103">Connect-PSSession</span></span>

## <span data-ttu-id="393ed-104">概要</span><span class="sxs-lookup"><span data-stu-id="393ed-104">SYNOPSIS</span></span>
<span data-ttu-id="393ed-105">切断されたセッションに再接続します。</span><span class="sxs-lookup"><span data-stu-id="393ed-105">Reconnects to disconnected sessions.</span></span>

## <span data-ttu-id="393ed-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="393ed-106">SYNTAX</span></span>

### <span data-ttu-id="393ed-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="393ed-107">Name (Default)</span></span>

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="393ed-108">Session</span><span class="sxs-lookup"><span data-stu-id="393ed-108">Session</span></span>

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="393ed-109">コンピューター名 Guid</span><span class="sxs-lookup"><span data-stu-id="393ed-109">ComputerNameGuid</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="393ed-110">[ComputerName]</span><span class="sxs-lookup"><span data-stu-id="393ed-110">ComputerName</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="393ed-111">ConnectionUriGuid</span><span class="sxs-lookup"><span data-stu-id="393ed-111">ConnectionUriGuid</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="393ed-112">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="393ed-112">ConnectionUri</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="393ed-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="393ed-113">InstanceId</span></span>

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="393ed-114">Id</span><span class="sxs-lookup"><span data-stu-id="393ed-114">Id</span></span>

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="393ed-115">Description</span><span class="sxs-lookup"><span data-stu-id="393ed-115">DESCRIPTION</span></span>

<span data-ttu-id="393ed-116">`Connect-PSSession`コマンドレットは、切断されたユーザー管理 **PSSessions** の PowerShell セッション (pssession) に再接続します。</span><span class="sxs-lookup"><span data-stu-id="393ed-116">The `Connect-PSSession` cmdlet reconnects to user-managed PowerShell sessions ( **PSSessions** ) that were disconnected.</span></span> <span data-ttu-id="393ed-117">意図的に切断されたセッションで動作します。たとえば、コマンド `Disconnect-PSSession` レットやコマンドレットの **Indisconnectedsession** パラメーターを使用することや、一時的なネットワークの停止などによって誤って切断されたセッションを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-117">It works on sessions that are disconnected intentionally, such as by using the `Disconnect-PSSession` cmdlet or the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet, and those that were disconnected unintentionally, such as by a temporary network outage.</span></span>

<span data-ttu-id="393ed-118">`Connect-PSSession` は、同じユーザーによって開始された切断されたセッションに接続できます。</span><span class="sxs-lookup"><span data-stu-id="393ed-118">`Connect-PSSession` can connect to any disconnected session that was started by the same user.</span></span> <span data-ttu-id="393ed-119">これには、他のコンピューター上の他のセッションによって開始または切断されたものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="393ed-119">These include those that were started by or disconnected from other sessions on other computers.</span></span>

<span data-ttu-id="393ed-120">ただし、は、 `Connect-PSSession` 切断されたセッションまたは閉じたセッション、またはコマンドレットを使用して開始された対話型セッションには接続できません `Enter-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="393ed-120">However, `Connect-PSSession` cannot connect to broken or closed sessions, or interactive sessions started by using the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="393ed-121">このほか、別のユーザーが開始したセッションには接続できません。ただし、そのセッションを作成したユーザーの資格情報がある場合には、このコマンドレットを使用した再接続が可能です。</span><span class="sxs-lookup"><span data-stu-id="393ed-121">Also you cannot connect sessions to sessions started by other users, unless you can provide the credentials of the user who created the session.</span></span>

<span data-ttu-id="393ed-122">切断されたセッションの機能の詳細については、「[about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="393ed-122">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="393ed-123">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="393ed-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="393ed-124">例</span><span class="sxs-lookup"><span data-stu-id="393ed-124">EXAMPLES</span></span>

### <span data-ttu-id="393ed-125">例 1: セッションに再接続する</span><span class="sxs-lookup"><span data-stu-id="393ed-125">Example 1: Reconnect to a session</span></span>

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

<span data-ttu-id="393ed-126">このコマンドは、Server01 コンピューターの ITTask セッションに再接続するものです。</span><span class="sxs-lookup"><span data-stu-id="393ed-126">This command reconnects to the ITTask session on the Server01 computer.</span></span>

<span data-ttu-id="393ed-127">出力は、コマンドが成功したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="393ed-127">The output shows that the command was successful.</span></span> <span data-ttu-id="393ed-128">セッションの **状態** が開かれ、 **可用性** が利用可能になっています。これは、セッションでコマンドを実行できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="393ed-128">The **State** of the session is Opened and the **Availability** is Available, which indicates that you can run commands in the session.</span></span>

### <span data-ttu-id="393ed-129">例 2: 切断と再接続の影響</span><span class="sxs-lookup"><span data-stu-id="393ed-129">Example 2: Effect of disconnecting and reconnecting</span></span>

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

<span data-ttu-id="393ed-130">この例では、セッションを切断した後で、改めて同じセッションに接続する効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="393ed-130">This example shows the effect of disconnecting and then reconnecting to a session.</span></span>

<span data-ttu-id="393ed-131">最初のコマンドは、コマンドレットを使用し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-131">The first command uses the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="393ed-132">**ComputerName** パラメーターを指定しなかった場合には、コマンドは現在のセッションで作成されたセッションのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="393ed-132">Without the **ComputerName** parameter, the command gets only sessions that were created in the current session.</span></span>

<span data-ttu-id="393ed-133">出力は、ローカル コンピューターの Backups セッションを取得したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="393ed-133">The output shows that the command gets the Backups session on the local computer.</span></span> <span data-ttu-id="393ed-134">セッションの **状態** が開かれ、 **可用性** が使用可能になっています。</span><span class="sxs-lookup"><span data-stu-id="393ed-134">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="393ed-135">2番目のコマンドは、コマンドレットを使用して、 `Get-PSSession` 現在のセッションで作成された **PSSession** オブジェクトを取得し、コマンドレットを使用して `Disconnect-PSSession` セッションを切断します。</span><span class="sxs-lookup"><span data-stu-id="393ed-135">The second command uses the `Get-PSSession` cmdlet to get the **PSSession** objects that were created in the current session and the `Disconnect-PSSession` cmdlet to disconnect the sessions.</span></span> <span data-ttu-id="393ed-136">出力は、Backups セッションが切断されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="393ed-136">The output shows that the Backups session was disconnected.</span></span> <span data-ttu-id="393ed-137">セッションの **状態** は Disconnected であり、 **Availability** は None です。</span><span class="sxs-lookup"><span data-stu-id="393ed-137">The **State** of the session is Disconnected and the **Availability** is None.</span></span>

<span data-ttu-id="393ed-138">3番目のコマンドは、コマンドレットを使用して、 `Get-PSSession` 現在のセッションで作成された **PSSession** オブジェクトを取得し、コマンドレットを使用して `Connect-PSSession` セッションを再接続します。</span><span class="sxs-lookup"><span data-stu-id="393ed-138">The third command uses the `Get-PSSession` cmdlet to get the **PSSession** objects that were created in the current session and the `Connect-PSSession` cmdlet to reconnect the sessions.</span></span> <span data-ttu-id="393ed-139">出力は、Backups セッションに再接続したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="393ed-139">The output shows that the Backups session was reconnected.</span></span> <span data-ttu-id="393ed-140">セッションの **状態** が開かれ、 **可用性** が使用可能になっています。</span><span class="sxs-lookup"><span data-stu-id="393ed-140">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="393ed-141">切断されて `Connect-PSSession` いないセッションでコマンドレットを使用すると、このコマンドはセッションに影響を与えず、エラーも生成されません。</span><span class="sxs-lookup"><span data-stu-id="393ed-141">If you use the `Connect-PSSession` cmdlet on a session that is not disconnected, the command does not affect the session and it does not generate any errors.</span></span>

### <span data-ttu-id="393ed-142">例 3: エンタープライズシナリオにおける一連のコマンド</span><span class="sxs-lookup"><span data-stu-id="393ed-142">Example 3: Series of commands in an enterprise scenario</span></span>

<span data-ttu-id="393ed-143">この一連のコマンドは、 `Connect-PSSession` エンタープライズシナリオでコマンドレットがどのように使用されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="393ed-143">This series of commands shows how the `Connect-PSSession` cmdlet might be used in an enterprise scenario.</span></span> <span data-ttu-id="393ed-144">この例では、システム管理者がリモート コンピューター上のセッションで、実行時間の長いジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="393ed-144">In this case, a system administrator starts a long-running job in a session on a remote computer.</span></span> <span data-ttu-id="393ed-145">管理者はジョブを開始した後、セッションを切断し、帰宅します。</span><span class="sxs-lookup"><span data-stu-id="393ed-145">After starting the job, the administrator disconnects from the session and goes home.</span></span>
<span data-ttu-id="393ed-146">その後、管理者が自宅のコンピューターにログオンし、ジョブが完了するまで実行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="393ed-146">Later that evening, the administrator logs on to her home computer and verifies that the job ran until it is completed.</span></span>

<span data-ttu-id="393ed-147">管理者は、リモートコンピューター上にセッションを作成し、セッションでスクリプトを実行することから始めます。最初のコマンドは、コマンドレットを使用して、 `New-PSSession` Server01 リモートコンピューター上に ITTask セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="393ed-147">The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the `New-PSSession` cmdlet to create the ITTask session on the Server01 remote computer.</span></span> <span data-ttu-id="393ed-148">このコマンドでは、 **ConfigurationName** パラメーターを使用して ITTasks セッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-148">The command uses the **ConfigurationName** parameter to specify the ITTasks session configuration.</span></span> <span data-ttu-id="393ed-149">このコマンドは、セッションを変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-149">The command saves the sessions in the `$s` variable.</span></span>

<span data-ttu-id="393ed-150">2番目のコマンド `Invoke-Command` レットを実行して、変数内のセッションでバックグラウンドジョブを開始し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-150">The second command `Invoke-Command` cmdlet to start a background job in the session in the `$s` variable.</span></span> <span data-ttu-id="393ed-151">このコマンドでは、 **FilePath** パラメーターを使用してバックグラウンド ジョブのスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="393ed-151">It uses the **FilePath** parameter to run the script in the background job.</span></span>

<span data-ttu-id="393ed-152">3番目のコマンドは、コマンドレットを使用して、 `Disconnect-PSSession` 変数内のセッションから切断し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-152">The third command uses the `Disconnect-PSSession` cmdlet to disconnect from the session in the `$s` variable.</span></span> <span data-ttu-id="393ed-153">このコマンドでは **OutputBufferingMode** パラメーターに Drop という値を使用して、セッションに出力を配信する処理に伴ってスクリプトがブロックされる事態を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="393ed-153">The command uses the **OutputBufferingMode** parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session.</span></span> <span data-ttu-id="393ed-154">この例では、 **IdleTimeoutSec** パラメーターを使用して、セッションタイムアウトを15時間に拡張しています。</span><span class="sxs-lookup"><span data-stu-id="393ed-154">It uses the **IdleTimeoutSec** parameter to extend the session time-out to 15 hours.</span></span> <span data-ttu-id="393ed-155">コマンドが完了すると、管理者は自分のコンピューターをロックし、夜間に自宅に移動します。</span><span class="sxs-lookup"><span data-stu-id="393ed-155">When the command is completed, the administrator locks her computer and goes home for the evening.</span></span>

<span data-ttu-id="393ed-156">その後、管理者は自宅のコンピューターを起動し、企業ネットワークにログオンして、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="393ed-156">Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts PowerShell.</span></span> <span data-ttu-id="393ed-157">4番目のコマンドは、コマンドレットを使用して、 `Get-PSSession` Server01 コンピューター上のセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="393ed-157">The fourth command uses the `Get-PSSession` cmdlet to get the sessions on the Server01 computer.</span></span> <span data-ttu-id="393ed-158">このコマンドは、ITTask セッションを検索します。5番目のコマンドは、コマンドレットを使用して `Connect-PSSession` ITTask セッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="393ed-158">The command finds the ITTask session.The fifth command uses the `Connect-PSSession` cmdlet to connect to the ITTask session.</span></span> <span data-ttu-id="393ed-159">このコマンドでは、セッションが `$s` 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-159">The command saves the session in the `$s` variable.</span></span>

<span data-ttu-id="393ed-160">6番目のコマンドは、コマンドレットを使用して、 `Invoke-Command` `Get-Job` 変数内のセッションでコマンドを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-160">The sixth command uses the `Invoke-Command` cmdlet to run a `Get-Job` command in the session in the `$s` variable.</span></span> <span data-ttu-id="393ed-161">出力は、ジョブが正常に完了したことを示しています。7番目のコマンドは、コマンドレットを使用して、セッション内の `Invoke-Command` `Receive-Job` 変数内のセッションでコマンドを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-161">The output shows that the job finished successfully.The seventh command uses the `Invoke-Command` cmdlet to run a `Receive-Job` command in the session in the `$s` variable in the session.</span></span> <span data-ttu-id="393ed-162">このコマンドは、変数に結果を保存し `$BackupSpecs` ます。8番目のコマンドは、コマンドレットを使用して、 `Invoke-Command` セッションで別のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="393ed-162">The command saves the results in the `$BackupSpecs` variable.The eighth command uses the `Invoke-Command` cmdlet to runs another script in the session.</span></span> <span data-ttu-id="393ed-163">このコマンドは、 `$BackupSpecs` スクリプトへの入力として、セッションの変数の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="393ed-163">The command uses the value of the `$BackupSpecs` variable in the session as input to the script.</span></span>

```
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

<span data-ttu-id="393ed-164">9番目のコマンドは、変数内のセッションから切断し `$s` ます。管理者が PowerShell を終了し、コンピューターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="393ed-164">The ninth command disconnects from the session in the `$s` variable.The administrator closes PowerShell and closes the computer.</span></span> <span data-ttu-id="393ed-165">次の日、セッションに再接続すると、会社用コンピューターからスクリプトの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="393ed-165">She can reconnect to the session on the next day and check the script status from her work computer.</span></span>

## <span data-ttu-id="393ed-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="393ed-166">PARAMETERS</span></span>

### <span data-ttu-id="393ed-167">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="393ed-167">-AllowRedirection</span></span>

<span data-ttu-id="393ed-168">このコマンドレットがこの接続を代替 URI にリダイレクトできることを示します。</span><span class="sxs-lookup"><span data-stu-id="393ed-168">Indicates that this cmdlet allows redirection of this connection to an alternate URI.</span></span>

<span data-ttu-id="393ed-169">**ConnectionURI** パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトするように指示を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="393ed-169">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="393ed-170">既定では、PowerShell は接続をリダイレクトしませんが、このパラメーターを使用して接続をリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="393ed-170">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="393ed-171">また、 **MaximumConnectionRedirectionCount** セッション オプション値を変更することで、接続をリダイレクトする回数を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="393ed-171">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="393ed-172">コマンドレットの **Maximumredirection** パラメーターを使用する `New-PSSessionOption` か、 **$PSSessionOption** preference 変数の **MaximumConnectionRedirectionCount** プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-172">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="393ed-173">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="393ed-173">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-174">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="393ed-174">-ApplicationName</span></span>

<span data-ttu-id="393ed-175">アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-175">Specifies the name of an application.</span></span> <span data-ttu-id="393ed-176">このコマンドレットは、指定されたアプリケーションを使用するセッションにのみ接続します。</span><span class="sxs-lookup"><span data-stu-id="393ed-176">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="393ed-177">接続 URI のアプリケーション名セグメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="393ed-177">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="393ed-178">たとえば、次の接続 URI では、アプリケーション名は WSMan: `http://localhost:5985/WSMAN` です。</span><span class="sxs-lookup"><span data-stu-id="393ed-178">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span> <span data-ttu-id="393ed-179">セッションのアプリケーション名は、セッションの **Runspace.ConnectionInfo.AppName** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="393ed-179">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="393ed-180">このパラメーター値は、セッションを選択してフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-180">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="393ed-181">セッションが使用するアプリケーションが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="393ed-181">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-182">-認証</span><span class="sxs-lookup"><span data-stu-id="393ed-182">-Authentication</span></span>

<span data-ttu-id="393ed-183">切断されたセッションに再接続するためにコマンドでユーザー資格情報を認証するために使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-183">Specifies the mechanism that is used to authenticate user credentials in the command to reconnect to the disconnected session.</span></span> <span data-ttu-id="393ed-184">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="393ed-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="393ed-185">Default</span><span class="sxs-lookup"><span data-stu-id="393ed-185">Default</span></span>
- <span data-ttu-id="393ed-186">基本</span><span class="sxs-lookup"><span data-stu-id="393ed-186">Basic</span></span>
- <span data-ttu-id="393ed-187">Credssp</span><span class="sxs-lookup"><span data-stu-id="393ed-187">Credssp</span></span>
- <span data-ttu-id="393ed-188">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="393ed-188">Digest</span></span>
- <span data-ttu-id="393ed-189">Kerberos</span><span class="sxs-lookup"><span data-stu-id="393ed-189">Kerberos</span></span>
- <span data-ttu-id="393ed-190">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="393ed-190">Negotiate</span></span>
- <span data-ttu-id="393ed-191">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="393ed-191">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="393ed-192">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="393ed-192">The default value is Default.</span></span>

<span data-ttu-id="393ed-193">このパラメーターの値の詳細については、MSDN ライブラリの「 [Authenticationmechanism 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="393ed-193">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

> [!CAUTION]
> <span data-ttu-id="393ed-194">ユーザーの資格情報が認証対象のリモート コンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモート ネットワーク共有にアクセスする場合など、複数のリソースの認証を必要とするコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="393ed-194">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="393ed-195">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="393ed-195">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="393ed-196">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="393ed-196">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-197">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="393ed-197">-CertificateThumbprint</span></span>

<span data-ttu-id="393ed-198">切断されたセッションに接続するためのアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-198">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="393ed-199">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="393ed-199">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="393ed-200">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-200">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="393ed-201">ローカルユーザーアカウントにのみマップできます。</span><span class="sxs-lookup"><span data-stu-id="393ed-201">They can be mapped only to local user accounts.</span></span> <span data-ttu-id="393ed-202">ドメインアカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="393ed-202">They do not work with domain accounts.</span></span>

<span data-ttu-id="393ed-203">証明書の拇印を取得するに `Get-Item` は、 `Get-ChildItem` PowerShell Cert: ドライブでまたはコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="393ed-203">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-204">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="393ed-204">-ComputerName</span></span>

<span data-ttu-id="393ed-205">切断されたセッションが格納されているコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-205">Specifies the computers on which the disconnected sessions are stored.</span></span> <span data-ttu-id="393ed-206">セッションは、接続のサーバー側または受信側のコンピューターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-206">Sessions are stored on the computer that is at the server-side or receiving end of a connection.</span></span> <span data-ttu-id="393ed-207">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="393ed-207">The default is the local computer.</span></span>

<span data-ttu-id="393ed-208">コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="393ed-208">Type the NetBIOS name, an IP address, or a fully qualified domain name of one computer.</span></span> <span data-ttu-id="393ed-209">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="393ed-209">Wildcard characters are not permitted.</span></span> <span data-ttu-id="393ed-210">ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="393ed-210">To specify the local computer, type the computer name, localhost, or a dot (.)</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameGuid, ComputerName
Aliases: Cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-211">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="393ed-211">-ConfigurationName</span></span>

<span data-ttu-id="393ed-212">指定したセッション構成を使用するセッションにのみ接続します。</span><span class="sxs-lookup"><span data-stu-id="393ed-212">Connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="393ed-213">セッション構成の構成名または完全修飾リソース URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="393ed-213">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="393ed-214">構成名だけを指定した場合は、次のスキーマ URI が付加され `http://schemas.microsoft.com/powershell` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-214">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span> <span data-ttu-id="393ed-215">セッションの構成名は、セッションの **ConfigurationName** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="393ed-215">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="393ed-216">このパラメーター値は、セッションを選択してフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-216">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="393ed-217">セッションが使用するセッション構成が変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="393ed-217">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="393ed-218">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="393ed-218">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-219">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="393ed-219">-ConnectionUri</span></span>

<span data-ttu-id="393ed-220">切断されたセッションの接続エンドポイントの Uri を指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-220">Specifies the URIs of the connection endpoints for the disconnected sessions.</span></span>

<span data-ttu-id="393ed-221">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="393ed-221">The URI must be fully qualified.</span></span> <span data-ttu-id="393ed-222">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="393ed-222">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="393ed-223">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="393ed-223">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="393ed-224">接続 URI を指定しない場合は、 **UseSSL** パラメーターと **Port** パラメーターを使用して接続 uri の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="393ed-224">If you do not specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="393ed-225">URI の **Transport** セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="393ed-225">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="393ed-226">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準ポート80で HTTP 用および 443 (HTTPS 用) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-226">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="393ed-227">PowerShell リモート処理に既定のポートを使用するには、HTTP の場合はポート5985、HTTPS の場合は5986を指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-227">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="393ed-228">対象のコンピューターが接続を別の URI にリダイレクトする場合、コマンドで **Allowredirection** パラメーターを使用しない限り、PowerShell によってリダイレクトが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-228">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUriGuid, ConnectionUri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-229">-Credential</span><span class="sxs-lookup"><span data-stu-id="393ed-229">-Credential</span></span>

<span data-ttu-id="393ed-230">切断されたセッションに接続するためのアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-230">Specifies a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="393ed-231">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="393ed-231">The default is the current user.</span></span>

<span data-ttu-id="393ed-232">またはなどのユーザー名を入力する `User01` `Domain01\User01` か、 `PSCredential` コマンドレットによって生成されるオブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-232">Type a user name, such as `User01` or `Domain01\User01`, or enter a `PSCredential` object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="393ed-233">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="393ed-233">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="393ed-234">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-234">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="393ed-235">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="393ed-235">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-236">-Id</span><span class="sxs-lookup"><span data-stu-id="393ed-236">-Id</span></span>

<span data-ttu-id="393ed-237">切断されたセッションの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-237">Specifies the IDs of the disconnected sessions.</span></span> <span data-ttu-id="393ed-238">**Id** パラメーターは、切断されたセッションが現在のセッションに既に接続されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="393ed-238">The **Id** parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="393ed-239">このパラメーターは、セッションがローカル コンピューター上に保存されているものの、現在のセッションに接続されていなかった場合には、有効でありながら効力を発揮しません。</span><span class="sxs-lookup"><span data-stu-id="393ed-239">This parameter is valid, but not effective, when the session is stored on the local computer, but was not connected to the current session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-240">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="393ed-240">-InstanceId</span></span>

<span data-ttu-id="393ed-241">切断されたセッションのインスタンス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-241">Specifies the instance IDs of the disconnected sessions.</span></span>

<span data-ttu-id="393ed-242">インスタンス ID は、ローカルコンピューターまたはリモートコンピューター上の **PSSession** を一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="393ed-242">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span>

<span data-ttu-id="393ed-243">インスタンス ID は、 **PSSession** の **InstanceID** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-243">The instance ID is stored in the **InstanceID** property of the **PSSession**.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-244">-Name</span><span class="sxs-lookup"><span data-stu-id="393ed-244">-Name</span></span>

<span data-ttu-id="393ed-245">切断されたセッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-245">Specifies the friendly names of the disconnected sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-246">-Port</span><span class="sxs-lookup"><span data-stu-id="393ed-246">-Port</span></span>

<span data-ttu-id="393ed-247">セッションに再接続するときに使用するリモート コンピューターのネットワーク ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-247">Specifies the network port on the remote computer that is used to reconnect to the session.</span></span> <span data-ttu-id="393ed-248">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="393ed-248">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="393ed-249">既定のポートは5985で、これは HTTP 用の WinRM ポート、および HTTPS 用の WinRM ポートである5986です。</span><span class="sxs-lookup"><span data-stu-id="393ed-249">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="393ed-250">代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="393ed-250">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="393ed-251">リスナーを構成するには、PowerShell プロンプトで次の2つのコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="393ed-251">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="393ed-252">必要な場合を除き、 **Port** パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="393ed-252">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="393ed-253">コマンドに設定されているポートは、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-253">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="393ed-254">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="393ed-254">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-255">-セッション</span><span class="sxs-lookup"><span data-stu-id="393ed-255">-Session</span></span>

<span data-ttu-id="393ed-256">切断されたセッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-256">Specifies the disconnected sessions.</span></span> <span data-ttu-id="393ed-257">**Pssession** オブジェクトを含む変数、またはコマンドなどの **pssession** オブジェクトを作成または取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-257">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-258">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="393ed-258">-SessionOption</span></span>

<span data-ttu-id="393ed-259">セッションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-259">Specifies advanced options for the session.</span></span> <span data-ttu-id="393ed-260">コマンドレットを使用して作成する **sessionoption** オブジェクト、 `New-PSSessionOption` またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="393ed-260">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="393ed-261">オプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-261">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="393ed-262">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="393ed-262">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="393ed-263">セッションオプションの値は、ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="393ed-263">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="393ed-264">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="393ed-264">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="393ed-265">既定値を含むセッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="393ed-265">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="393ed-266">**$PSSessionOption** ユーザー設定変数の詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="393ed-266">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="393ed-267">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="393ed-267">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-268">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="393ed-268">-ThrottleLimit</span></span>

<span data-ttu-id="393ed-269">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="393ed-269">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="393ed-270">このパラメーターを省略した場合、または値 0 を入力した場合は、既定値の 32 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-270">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="393ed-271">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="393ed-271">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-272">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="393ed-272">-UseSSL</span></span>

<span data-ttu-id="393ed-273">このコマンドレットが、切断されたセッションに接続するために Secure Sockets Layer (SSL) プロトコルを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="393ed-273">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="393ed-274">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="393ed-274">By default, SSL is not used.</span></span>

<span data-ttu-id="393ed-275">WS-Management は、ネットワーク経由で送信されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="393ed-275">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="393ed-276">**UseSSL** パラメーターは、HTTP 接続ではなく HTTPS 接続を介してデータを送信する追加の保護です。</span><span class="sxs-lookup"><span data-stu-id="393ed-276">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="393ed-277">このパラメーターを使用しても、コマンドに使用されているポートで SSL を使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="393ed-277">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-278">-Confirm</span><span class="sxs-lookup"><span data-stu-id="393ed-278">-Confirm</span></span>

<span data-ttu-id="393ed-279">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="393ed-279">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-280">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="393ed-280">-WhatIf</span></span>

<span data-ttu-id="393ed-281">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="393ed-281">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="393ed-282">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="393ed-282">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="393ed-283">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="393ed-283">CommonParameters</span></span>

<span data-ttu-id="393ed-284">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="393ed-284">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="393ed-285">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="393ed-285">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="393ed-286">入力</span><span class="sxs-lookup"><span data-stu-id="393ed-286">INPUTS</span></span>

### <span data-ttu-id="393ed-287">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="393ed-287">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="393ed-288">パイプを使用してセッション ( **PSSession** ) をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="393ed-288">You can pipe a session ( **PSSession** ) to this cmdlet.</span></span>

## <span data-ttu-id="393ed-289">出力</span><span class="sxs-lookup"><span data-stu-id="393ed-289">OUTPUTS</span></span>

### <span data-ttu-id="393ed-290">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="393ed-290">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="393ed-291">このコマンドレットは、再接続先のセッションを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="393ed-291">This cmdlet returns an object that represents the session to which it reconnected.</span></span>

## <span data-ttu-id="393ed-292">注</span><span class="sxs-lookup"><span data-stu-id="393ed-292">NOTES</span></span>

- <span data-ttu-id="393ed-293">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="393ed-293">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="393ed-294">`Connect-PSSession` 切断されているセッション、つまり **State** プロパティの値が disconnected のセッションにのみ再接続します。</span><span class="sxs-lookup"><span data-stu-id="393ed-294">`Connect-PSSession` reconnects only to sessions that are disconnected, that is, sessions that have a value of Disconnected for the **State** property.</span></span> <span data-ttu-id="393ed-295">Windows PowerShell 3.0 以降のバージョンを実行しているコンピューターに接続されている、または終了したセッションのみを切断し、再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="393ed-295">Only sessions that are connected to, or end at, computers that run Windows PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>

- <span data-ttu-id="393ed-296">切断されていないセッションでを使用する場合、このコマンドはセッションに影響を与えず、エラーを生成しません `Connect-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="393ed-296">If you use `Connect-PSSession` on a session that is not disconnected, the command does not affect the session and it does not generate errors.</span></span>

- <span data-ttu-id="393ed-297">**EnableNetworkAccess** パラメーターを使用して作成された対話型トークンを使用して切断されたループバックセッションは、セッションが作成されたコンピューターからのみ再接続できます。</span><span class="sxs-lookup"><span data-stu-id="393ed-297">Disconnected loopback sessions with interactive tokens, which are created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="393ed-298">この制約は、悪意のあるアクセスからコンピューターを保護するためのものです。</span><span class="sxs-lookup"><span data-stu-id="393ed-298">This restriction protects the computer from malicious access.</span></span>

- <span data-ttu-id="393ed-299">**PSSession** の **State** プロパティの値は、現在のセッションを基準としています。</span><span class="sxs-lookup"><span data-stu-id="393ed-299">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
  <span data-ttu-id="393ed-300">したがって、値が **Disconnected** の場合は、 **PSSession** が現在のセッションに接続されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="393ed-300">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="393ed-301">ただし、 **PSSession** がすべてのセッションから切断されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="393ed-301">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="393ed-302">別のセッションに接続されている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="393ed-302">It might be connected to a different session.</span></span> <span data-ttu-id="393ed-303">セッションに接続または再接続できるかどうかを確認するには、 **Availability** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="393ed-303">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="393ed-304">**Availability** の値が None の場合は、セッションに接続できることを示します。</span><span class="sxs-lookup"><span data-stu-id="393ed-304">An **Availability** value of None indicates that you can connect to the session.</span></span> <span data-ttu-id="393ed-305">値が Busy の場合は、PSSession が別のセッションに接続されているため、 **PSSession** に接続できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="393ed-305">A value of Busy indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

  <span data-ttu-id="393ed-306">セッションの **State** プロパティの値の詳細については、MSDN ライブラリの「 [RunspaceState 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="393ed-306">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) in the MSDN library.</span></span>

  <span data-ttu-id="393ed-307">セッションの **Availability** プロパティの値の詳細については、MSDN ライブラリの「 [RunspaceAvailability 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="393ed-307">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) in the MSDN library.</span></span>

- <span data-ttu-id="393ed-308">Pssession に接続するときに、 **pssession** のアイドルタイムアウト値を変更することはできませ **ん。**</span><span class="sxs-lookup"><span data-stu-id="393ed-308">You cannot change the idle time-out value of a **PSSession** when you connect to the **PSSession**.</span></span> <span data-ttu-id="393ed-309">の **sessionoption** パラメーターは、 `Connect-PSSession` **IdleTimeout** 値を持つ **sessionoption** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="393ed-309">The **SessionOption** parameter of `Connect-PSSession` takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="393ed-310">ただし、PSSession に接続するときは、 **Sessionoption** オブジェクトの **idletimeout** 値と変数の **idletimeout** 値 `$PSSessionOption` は無視さ **PSSession** れます。</span><span class="sxs-lookup"><span data-stu-id="393ed-310">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the `$PSSessionOption` variable are ignored when connecting to a **PSSession**.</span></span>

  <span data-ttu-id="393ed-311">**Pssession の作成時、** またはコマンドレットを使用して pssession のアイドルタイムアウト **を設定** および変更したり、 `New-PSSession` `Invoke-Command` **pssession** から切断したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="393ed-311">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the `New-PSSession` or `Invoke-Command` cmdlets, and when you disconnect from the **PSSession**.</span></span>

  <span data-ttu-id="393ed-312">**PSSession** の **IdleTimeout** プロパティは、切断されたセッションをリモートコンピューターで保持する期間を決定するため、切断されたセッションにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="393ed-312">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions, because it determines how long a disconnected session is maintained on the remote computer.</span></span> <span data-ttu-id="393ed-313">セッションが切断されると、その時点からアイドル状態であると判断されます。これは、そのセッションでコマンドを実行している場合であっても同じです。</span><span class="sxs-lookup"><span data-stu-id="393ed-313">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

## <span data-ttu-id="393ed-314">関連リンク</span><span class="sxs-lookup"><span data-stu-id="393ed-314">RELATED LINKS</span></span>

[<span data-ttu-id="393ed-315">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="393ed-315">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="393ed-316">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="393ed-316">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="393ed-317">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="393ed-317">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="393ed-318">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="393ed-318">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="393ed-319">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="393ed-319">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="393ed-320">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="393ed-320">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="393ed-321">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="393ed-321">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="393ed-322">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="393ed-322">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="393ed-323">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="393ed-323">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="393ed-324">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="393ed-324">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="393ed-325">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="393ed-325">Remove-PSSession</span></span>](Remove-PSSession.md)
