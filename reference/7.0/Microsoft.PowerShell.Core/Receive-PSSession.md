---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-PSSession
ms.openlocfilehash: 43f9823f19df9ceec44f1e27d5183cca418647ba
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218488"
---
# <span data-ttu-id="85a9f-103">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="85a9f-103">Receive-PSSession</span></span>

## <span data-ttu-id="85a9f-104">概要</span><span class="sxs-lookup"><span data-stu-id="85a9f-104">SYNOPSIS</span></span>

<span data-ttu-id="85a9f-105">切断されたセッションのコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-105">Gets results of commands in disconnected sessions</span></span>

## <span data-ttu-id="85a9f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85a9f-106">SYNTAX</span></span>

### <span data-ttu-id="85a9f-107">セッション (既定)</span><span class="sxs-lookup"><span data-stu-id="85a9f-107">Session (Default)</span></span>

```
Receive-PSSession [-Session] <PSSession> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85a9f-108">Id</span><span class="sxs-lookup"><span data-stu-id="85a9f-108">Id</span></span>

```
Receive-PSSession [-Id] <Int32> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="85a9f-109">コンピューターのセッション名</span><span class="sxs-lookup"><span data-stu-id="85a9f-109">ComputerSessionName</span></span>

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85a9f-110">ComputerInstanceId</span><span class="sxs-lookup"><span data-stu-id="85a9f-110">ComputerInstanceId</span></span>

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85a9f-111">ConnectionUriSessionName セッション名</span><span class="sxs-lookup"><span data-stu-id="85a9f-111">ConnectionUriSessionName</span></span>

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85a9f-112">ConnectionUriInstanceId</span><span class="sxs-lookup"><span data-stu-id="85a9f-112">ConnectionUriInstanceId</span></span>

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85a9f-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="85a9f-113">InstanceId</span></span>

```
Receive-PSSession -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="85a9f-114">セッション</span><span class="sxs-lookup"><span data-stu-id="85a9f-114">SessionName</span></span>

```
Receive-PSSession -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="85a9f-115">Description</span><span class="sxs-lookup"><span data-stu-id="85a9f-115">DESCRIPTION</span></span>

<span data-ttu-id="85a9f-116">`Receive-PSSession`コマンドレットは、切断された PowerShell セッション ( **PSSession** ) で実行されているコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-116">The `Receive-PSSession` cmdlet gets the results of commands running in PowerShell sessions ( **PSSession** ) that were disconnected.</span></span> <span data-ttu-id="85a9f-117">セッションが現在接続されている場合、は、 `Receive-PSSession` セッションが切断されたときに実行されていたコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-117">If the session is currently connected, `Receive-PSSession` gets the results of commands that were running when the session was disconnected.</span></span> <span data-ttu-id="85a9f-118">セッションがまだ切断されている場合、は `Receive-PSSession` セッションに接続し、中断されたすべてのコマンドを再開して、セッションで実行されているコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-118">If the session is still disconnected, `Receive-PSSession` connects to the session, resumes any commands that were suspended, and gets the results of commands running in the session.</span></span>

<span data-ttu-id="85a9f-119">このコマンドレットは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="85a9f-119">This cmdlet was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="85a9f-120">`Receive-PSSession`コマンドの代わりに、またはを使用でき `Connect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-120">You can use a `Receive-PSSession` in addition to or instead of a `Connect-PSSession` command.</span></span>
<span data-ttu-id="85a9f-121">`Receive-PSSession` は、他のセッションまたは他のコンピューターで開始された切断または再接続されたセッションに接続できます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-121">`Receive-PSSession` can connect to any disconnected or reconnected session that was started in other sessions or on other computers.</span></span>

<span data-ttu-id="85a9f-122">`Receive-PSSession`**PSSessions** `Disconnect-PSSession` コマンドレットまたは `Invoke-Command` **indisconnectedsession** パラメーターを使用して意図的に切断された pssession で動作します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-122">`Receive-PSSession` works on **PSSessions** that were disconnected intentionally using the `Disconnect-PSSession` cmdlet or the `Invoke-Command` **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="85a9f-123">または、ネットワークの中断によって意図せず切断されました。</span><span class="sxs-lookup"><span data-stu-id="85a9f-123">Or disconnected unintentionally by a network interruption.</span></span>

<span data-ttu-id="85a9f-124">コマンドレットを使用し `Receive-PSSession` て、コマンドが実行または中断されていないセッションに接続する場合、は `Receive-PSSession` セッションに接続しますが、出力またはエラーは返しません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-124">If you use the `Receive-PSSession` cmdlet to connect to a session in which no commands are running or suspended, `Receive-PSSession` connects to the session, but returns no output or errors.</span></span>

<span data-ttu-id="85a9f-125">切断されたセッションの機能の詳細については、「[about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-125">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="85a9f-126">いくつかの例では、スプラッティングを使用して、行の長さを減らし、読みやすさを向上させます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-126">Some examples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="85a9f-127">詳細については、「 [about_Splatting](./About/about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-127">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="85a9f-128">例</span><span class="sxs-lookup"><span data-stu-id="85a9f-128">EXAMPLES</span></span>

### <span data-ttu-id="85a9f-129">例 1: PSSession に接続する</span><span class="sxs-lookup"><span data-stu-id="85a9f-129">Example 1: Connect to a PSSession</span></span>

<span data-ttu-id="85a9f-130">この例では、リモートコンピューター上のセッションに接続し、セッションで実行されているコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-130">This example connects to a session on a remote computer and gets the results of commands that are running in a session.</span></span>

```powershell
Receive-PSSession -ComputerName Server01 -Name ITTask
```

<span data-ttu-id="85a9f-131">は、 `Receive-PSSession` **ComputerName** パラメーターを使用してリモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-131">The `Receive-PSSession` specifies the remote computer with the **ComputerName** parameter.</span></span> <span data-ttu-id="85a9f-132">**Name** パラメーターは、Server01 コンピューター上の ittask セッションを識別します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-132">The **Name** parameter identifies the ITTask session on the Server01 computer.</span></span> <span data-ttu-id="85a9f-133">この例では、ITTask セッションで実行されていたコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-133">The example gets the results of commands that were running in the ITTask session.</span></span>

<span data-ttu-id="85a9f-134">コマンドは **Outtarget** パラメーターを使用しないため、結果はコマンドラインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-134">Because the command doesn't use the **OutTarget** parameter, the results appear on the command line.</span></span>

### <span data-ttu-id="85a9f-135">例 2: 切断されたセッションのすべてのコマンドの結果を取得する</span><span class="sxs-lookup"><span data-stu-id="85a9f-135">Example 2: Get results of all commands on disconnected sessions</span></span>

<span data-ttu-id="85a9f-136">この例では、2台のリモートコンピューター上の切断されたすべてのセッションで実行されているすべてのコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-136">This example gets the results of all commands running in all disconnected sessions on two remote computers.</span></span>

<span data-ttu-id="85a9f-137">セッションが切断されていない場合、またはコマンドを実行していない場合、は `Receive-PSSession` セッションに接続せず、出力もエラーも返しません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-137">If any session wasn't disconnected or isn't running commands, `Receive-PSSession` doesn't connect to the session and doesn't return any output or errors.</span></span>

```powershell
Get-PSSession -ComputerName Server01, Server02 | Receive-PSSession
```

<span data-ttu-id="85a9f-138">`Get-PSSession`**ComputerName** パラメーターを使用して、リモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-138">`Get-PSSession` uses the **ComputerName** parameter to specify the remote computers.</span></span> <span data-ttu-id="85a9f-139">オブジェクトは、パイプラインの下位に送信され `Receive-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-139">The objects are sent down the pipeline to `Receive-PSSession`.</span></span>

### <span data-ttu-id="85a9f-140">例 3: セッションで実行されているスクリプトの結果を取得する</span><span class="sxs-lookup"><span data-stu-id="85a9f-140">Example 3: Get the results of a script running in a session</span></span>

<span data-ttu-id="85a9f-141">この例では、コマンドレットを使用して、 `Receive-PSSession` リモートコンピューターのセッションで実行されていたスクリプトの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-141">This example uses the `Receive-PSSession` cmdlet to get the results of a script that was running in a remote computer's session.</span></span>

```powershell
$parms = @{
  ComputerName = "Server01"
  Name = "ITTask"
  OutTarget = "Job"
  JobName = "ITTaskJob01"
  Credential = "Domain01\Admin01"
}
Receive-PSSession @parms
```

```Output
Id     Name            State         HasMoreData     Location
--     ----            -----         -----------     --------
16     ITTaskJob01     Running       True            Server01
```

<span data-ttu-id="85a9f-142">このコマンドでは、 **ComputerName** および **Name** の 2　つのパラメーターを使用して、切断されたセッションを特定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-142">The command uses the **ComputerName** and **Name** parameters to identify the disconnected session.</span></span>
<span data-ttu-id="85a9f-143">この例では、 **Outtarget** パラメーターに job という値を指定して、 `Receive-PSSession` 結果をジョブとして返すように指示しています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-143">It uses the **OutTarget** parameter with a value of Job to direct `Receive-PSSession` to return the results as a job.</span></span> <span data-ttu-id="85a9f-144">**JobName** パラメーターは、再接続されたセッションのジョブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-144">The **JobName** parameter specifies a name for the job in the reconnected session.</span></span>
<span data-ttu-id="85a9f-145">**Credential** パラメーターは、 `Receive-PSSession` ドメイン管理者のアクセス許可を使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-145">The **Credential** parameter runs the `Receive-PSSession` command using the permissions of a domain administrator.</span></span>

<span data-ttu-id="85a9f-146">出力は、が `Receive-PSSession` 現在のセッションのジョブとして結果を返したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-146">The output shows that `Receive-PSSession` returned the results as a job in the current session.</span></span> <span data-ttu-id="85a9f-147">ジョブの結果を取得するには、コマンドを使用します。 `Receive-Job`</span><span class="sxs-lookup"><span data-stu-id="85a9f-147">To get the job results, use a `Receive-Job` command</span></span>

### <span data-ttu-id="85a9f-148">例 4: ネットワークが停止した後に結果を取得する</span><span class="sxs-lookup"><span data-stu-id="85a9f-148">Example 4: Get results after a network outage</span></span>

<span data-ttu-id="85a9f-149">この例では、コマンドレットを使用して、ネットワークの停止によっ `Receive-PSSession` てセッション接続が中断された後にジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-149">This example uses the `Receive-PSSession` cmdlet to get the results of a job after a network outage disrupts a session connection.</span></span> <span data-ttu-id="85a9f-150">PowerShell は、次の4分間にセッションの再接続を自動的に1回試行します。これにより、4分間のすべての試行が失敗した場合にのみ、作業が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-150">PowerShell automatically attempts to reconnect the session once per second for the next four minutes and abandons the effort only if all attempts in the four-minute interval fail.</span></span>

```
PS> $s = New-PSSession -ComputerName Server01 -Name AD -ConfigurationName ADEndpoint
PS> $s

Id  Name   ComputerName    State        ConfigurationName     Availability
--  ----   ------------    -----        -----------------     ------------
8   AD      Server01       Opened       ADEndpoint               Available


PS> Invoke-Command -Session $s -FilePath \\Server12\Scripts\SharedScripts\New-ADResolve.ps1

Running "New-ADResolve.ps1"

# Network outage
# Restart local computer
# Network access is not re-established within 4 minutes


PS> Get-PSSession -ComputerName Server01

Id  Name   ComputerName    State          ConfigurationName      Availability
--  ----   ------------    -----          -----------------      ------------
1  Backup  Server01        Disconnected   Microsoft.PowerShell           None
8  AD      Server01        Disconnected   ADEndpoint                     None


PS> Receive-PSSession -ComputerName Server01 -Name AD -OutTarget Job -JobName AD

Job Id   Name      State         HasMoreData     Location
--       ----      -----         -----------     --------
16       ADJob     Running       True            Server01


PS> Get-PSSession -ComputerName Server01

Id  Name    ComputerName    State         ConfigurationName     Availability
--  ----    ------------    -----         -----------------     ------------
1  Backup   Server01        Disconnected  Microsoft.PowerShell          Busy
8  AD       Server01        Opened        ADEndpoint               Available
```

<span data-ttu-id="85a9f-151">コマンドレットでは、 `New-PSSession` Server01 コンピューター上にセッションを作成し、そのセッションを変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-151">The `New-PSSession` cmdlet creates a session on the Server01 computer and saves the session in the `$s` variable.</span></span> <span data-ttu-id="85a9f-152">変数は、 `$s` **状態** が開かれていて、 **可用性** が使用可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-152">The `$s` variable displays that the **State** is Opened and the **Availability** is Available.</span></span> <span data-ttu-id="85a9f-153">これらの値は、セッションに接続していて、セッションでコマンドを実行できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-153">These values indicate that you're connected to the session and can run commands in the session.</span></span>

<span data-ttu-id="85a9f-154">`Invoke-Command`コマンドレットは、変数内のセッションでスクリプトを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-154">The `Invoke-Command` cmdlet runs a script in the session in the `$s` variable.</span></span> <span data-ttu-id="85a9f-155">スクリプトが開始され、データを返し始めたところで、ネットワークが停止し、セッションが中断しました。</span><span class="sxs-lookup"><span data-stu-id="85a9f-155">The script begins to run and return data, but a network outage occurs that interrupts the session.</span></span> <span data-ttu-id="85a9f-156">ユーザーは、セッションを終了し、ローカル コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-156">The user has to exit the session and restart the local computer.</span></span>

<span data-ttu-id="85a9f-157">コンピューターが再起動すると、ユーザーは PowerShell を起動し、コマンドを実行して `Get-PSSession` Server01 コンピューター上のセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-157">When the computer restarts, the user starts PowerShell and runs a `Get-PSSession` command to get sessions on the Server01 computer.</span></span> <span data-ttu-id="85a9f-158">出力には、Server01 コンピューターに **AD** セッションがまだ存在していることが示されています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-158">The output shows that the **AD** session still exists on the Server01 computer.</span></span> <span data-ttu-id="85a9f-159">この **状態** は、 **AD** セッションが切断されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-159">The **State** indicates that the **AD** session is disconnected.</span></span> <span data-ttu-id="85a9f-160">**Availability** 値が None の場合は、セッションがどのクライアントセッションにも接続されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-160">The **Availability** value of None, indicates that the session isn't connected to any client sessions.</span></span>

<span data-ttu-id="85a9f-161">`Receive-PSSession`コマンドレットは、 **AD** セッションに再接続し、セッションで実行されたスクリプトの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-161">The `Receive-PSSession` cmdlet reconnects to the **AD** session and gets the results of the script that ran in the session.</span></span> <span data-ttu-id="85a9f-162">このコマンドは、 **Outtarget** パラメーターを使用して、 **adjob** という名前のジョブに結果を要求します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-162">The command uses the **OutTarget** parameter to request the results in a job named **ADJob**.</span></span> <span data-ttu-id="85a9f-163">このコマンドはジョブオブジェクトを返し、出力はスクリプトがまだ実行されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-163">The command returns a job object and the output indicates that the script is still running.</span></span>

<span data-ttu-id="85a9f-164">`Get-PSSession`コマンドレットは、ジョブの状態を確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-164">The `Get-PSSession` cmdlet is used to check the job state.</span></span> <span data-ttu-id="85a9f-165">出力は、 `Receive-PSSession` コマンドレットが **AD** セッションに再接続されたことを確認します。このセッションは、現在開いていて、コマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-165">The output confirms that the `Receive-PSSession` cmdlet reconnected to the **AD** session, which is now open and available for commands.</span></span> <span data-ttu-id="85a9f-166">また、スクリプトは実行を再開し、スクリプトの結果を取得しています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-166">And, the script resumed execution and is getting the script results.</span></span>

### <span data-ttu-id="85a9f-167">例 5: 切断されたセッションに再接続する</span><span class="sxs-lookup"><span data-stu-id="85a9f-167">Example 5: Reconnect to disconnected sessions</span></span>

<span data-ttu-id="85a9f-168">この例では、コマンドレットを使用して、 `Receive-PSSession` 意図的に切断されたセッションに再接続し、セッションで実行されていたジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-168">This example uses the `Receive-PSSession` cmdlet to reconnect to sessions that were intentionally disconnected and get the results of jobs that were running in the sessions.</span></span>

```
PS> $parms = @{
      InDisconnectedSession = $True
      ComputerName = "Server01", "Server02", "Server30"
      FilePath = "\\Server12\Scripts\SharedScripts\Get-BugStatus.ps1"
      Name = "BugStatus"
      SessionOption = @{IdleTimeout = 86400000}
      ConfigurationName = "ITTasks"
    }
PS> Invoke-Command @parms
PS> Exit


PS> $s = Get-PSSession -ComputerName Server01, Server02, Server30 -Name BugStatus
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Disconnected  ITTasks                       None
8  ITTask  Server02        Disconnected  ITTasks                       None
2  ITTask  Server30        Disconnected  ITTasks                       None


PS> $Results = Receive-PSSession -Session $s
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Opened        ITTasks                  Available
8  ITTask  Server02        Opened        ITTasks                  Available
2  ITTask  Server30        Opened        ITTasks                  Available


PS> $Results

Bug Report - Domain 01
----------------------
ComputerName          BugCount          LastUpdated
--------------        ---------         ------------
Server01              121               Friday, December 30, 2011 5:03:34 PM
```

<span data-ttu-id="85a9f-169">`Invoke-Command`コマンドレットは、3台のリモートコンピューター上でスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-169">The `Invoke-Command` cmdlet runs a script on three remote computers.</span></span> <span data-ttu-id="85a9f-170">このスクリプトでは、複数のデータベースからデータを収集して集計するため、スクリプトが完了するまでに長い時間がかかることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-170">Because the script gathers and summarizes data from multiple databases, it often takes the script an extended time to finish.</span></span> <span data-ttu-id="85a9f-171">このコマンドは、スクリプトを開始する **Indisconnectedsession** パラメーターを使用して、セッションを直ちに切断します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-171">The command uses the **InDisconnectedSession** parameter that starts the scripts and then immediately disconnects the sessions.</span></span> <span data-ttu-id="85a9f-172">**Sessionoption** パラメーターは、切断されたセッションの **IdleTimeout** 値を拡張します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-172">The **SessionOption** parameter extends the **IdleTimeout** value of the disconnected session.</span></span> <span data-ttu-id="85a9f-173">切断されたセッションは、切断された時点からアイドル状態と見なされます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-173">Disconnected sessions are considered idle from the moment they're disconnected.</span></span> <span data-ttu-id="85a9f-174">コマンドが完了し、セッションに再接続できるように、十分な長さのアイドルタイムアウトを設定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-174">It's important to set the idle time-out for long enough so that the commands can complete and you can reconnect to the session.</span></span> <span data-ttu-id="85a9f-175">IdleTimeout を設定できるのは、 **PSSession** を作成したときだけです。また、その接続を切断した場合にのみ、 **IdleTimeout** を変更できます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-175">You can set the **IdleTimeout** only when you create the **PSSession** and change it only when you disconnect from it.</span></span> <span data-ttu-id="85a9f-176">**PSSession** に接続するとき、またはその結果を受信するときに、 **IdleTimeout** 値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-176">You can't change the **IdleTimeout** value when you connect to a **PSSession** or receiving its results.</span></span> <span data-ttu-id="85a9f-177">コマンドを実行すると、ユーザーは PowerShell を終了し、コンピューターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-177">After running the command, the user exits PowerShell and closes the computer.</span></span>

<span data-ttu-id="85a9f-178">次に、ユーザーが Windows を再開し、PowerShell を起動して、を使用して `Get-PSSession` スクリプトが実行されていたセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-178">The next day, the user resumes Windows, starts PowerShell, and uses `Get-PSSession` to get the sessions in which the scripts were running.</span></span> <span data-ttu-id="85a9f-179">コマンドは、コンピューター名、セッション名、セッション構成の名前を指定してセッションを識別し、そのセッションを変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-179">The command identifies the sessions by the computer name, session name, and the name of the session configuration and saves the sessions in the `$s` variable.</span></span> <span data-ttu-id="85a9f-180">変数の値 `$s` が表示され、セッションが切断されているがビジー状態ではないことが示されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-180">The value of the `$s` variable is displayed and shows that the sessions are disconnected, but aren't busy.</span></span>

<span data-ttu-id="85a9f-181">`Receive-PSSession`コマンドレットは、変数内のセッションに接続 `$s` し、その結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-181">The `Receive-PSSession` cmdlet connects to the sessions in the `$s` variable and gets their results.</span></span>
<span data-ttu-id="85a9f-182">このコマンドは、変数に結果を保存し `$Results` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-182">The command saves the results in the `$Results` variable.</span></span> <span data-ttu-id="85a9f-183">`$s`変数が表示され、セッションが接続されていて、コマンドで使用できることが示されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-183">The `$s` variable is displayed and shows that the sessions are connected and available for commands.</span></span>

<span data-ttu-id="85a9f-184">スクリプトの結果 `$Results` 変数が PowerShell コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-184">The script results in the `$Results` variable are displayed in the PowerShell console.</span></span> <span data-ttu-id="85a9f-185">結果のいずれかが予期しないものである場合、ユーザーはセッションでコマンドを実行して根本原因を調査できます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-185">If any of the results are unexpected, the user can run commands in the sessions to investigate the root cause.</span></span>

### <span data-ttu-id="85a9f-186">例 6: 切断されたセッションでジョブを実行する</span><span class="sxs-lookup"><span data-stu-id="85a9f-186">Example 6: Running a job in a disconnected session</span></span>

<span data-ttu-id="85a9f-187">この例では、切断されたセッションで実行されているジョブに対して何が起こるかを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-187">This example shows what happens to a job that's running in a disconnected session.</span></span>

```
PS> $s = New-PSSession -ComputerName Server01 -Name Test
PS> $j = Invoke-Command -Session $s { 1..1500 | Foreach-Object {"Return $_"; sleep 30}} -AsJob
PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Running       True            Server01


PS> $s | Disconnect-PSSession

Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server01        Disconnected  Microsoft.PowerShell          None


PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Disconnected  True            Server01


PS> Receive-Job $j -Keep

Return 1
Return 2


PS> $s2 = Connect-PSSession -ComputerName Server01 -Name Test
PS> $j2 = Receive-PSSession -ComputerName Server01 -Name Test
PS> Receive-Job $j

Return 3
Return 4
```

<span data-ttu-id="85a9f-188">コマンドレットにより、 `New-PSSession` Server01 コンピューター上にテストセッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-188">The `New-PSSession` cmdlet creates the Test session on the Server01 computer.</span></span> <span data-ttu-id="85a9f-189">このコマンドでは、セッションが `$s` 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-189">The command saves the session in the `$s` variable.</span></span>

<span data-ttu-id="85a9f-190">`Invoke-Command`コマンドレットは、変数内のセッションでコマンドを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-190">The `Invoke-Command` cmdlet runs a command in the session in the `$s` variable.</span></span> <span data-ttu-id="85a9f-191">このコマンドは、 **AsJob** パラメーターを使用して、ジョブとしてコマンドを実行し、現在のセッションにジョブオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-191">The command uses the **AsJob** parameter to run the command as a job and creates the job object in the current session.</span></span>
<span data-ttu-id="85a9f-192">このコマンドは、変数に保存されているジョブオブジェクトを返し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-192">The command returns a job object that's saved in the `$j` variable.</span></span> <span data-ttu-id="85a9f-193">変数は、 `$j` ジョブオブジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-193">The `$j` variable displays the job object.</span></span>

<span data-ttu-id="85a9f-194">変数内のセッションオブジェクト `$s` がに送信され、 `Disconnect-PSSession` セッションが切断されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-194">The session object in the `$s` variable is sent down the pipeline to `Disconnect-PSSession` and the session is disconnected.</span></span>

<span data-ttu-id="85a9f-195">`$j`変数が表示され、変数内のジョブオブジェクトを切断した場合の影響が示され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-195">The `$j` variable is displayed and shows the effect of disconnecting the job object in the `$j` variable.</span></span> <span data-ttu-id="85a9f-196">ジョブの状態が、Disconnected になっています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-196">The job state is now Disconnected.</span></span>

<span data-ttu-id="85a9f-197">は、 `Receive-Job` 変数のジョブで実行され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-197">The `Receive-Job` is run on the job in the `$j` variable.</span></span> <span data-ttu-id="85a9f-198">出力には、ジョブがセッションの前に出力を返し、ジョブが切断されたことが示されています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-198">The output shows that the job began to return output before the session and the job were disconnected.</span></span>

<span data-ttu-id="85a9f-199">`Connect-PSSession`コマンドレットは、同じクライアントセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-199">The `Connect-PSSession` cmdlet is run in the same client session.</span></span> <span data-ttu-id="85a9f-200">コマンドは、Server01 コンピューター上のテストセッションに再接続し、セッションを変数に保存し `$s2` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-200">The command reconnects to the Test session on the Server01 computer and saves the session in the `$s2` variable.</span></span>

<span data-ttu-id="85a9f-201">`Receive-PSSession`コマンドレットは、セッションで実行されていたジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-201">The `Receive-PSSession` cmdlet gets the results of the job that was running in the session.</span></span> <span data-ttu-id="85a9f-202">コマンドは同じセッションで実行されるので、 `Receive-PSSession` 既定では結果をジョブとして返し、同じジョブオブジェクトを再利用します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-202">Because the command is run in the same session, `Receive-PSSession` returns the results as a job by default and reuses the same job object.</span></span> <span data-ttu-id="85a9f-203">このコマンドは、ジョブを変数に保存し `$j2` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-203">The command saves the job in the `$j2` variable.</span></span> <span data-ttu-id="85a9f-204">`Receive-Job`コマンドレットは、変数内のジョブの結果を取得し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-204">The `Receive-Job` cmdlet gets the results of the job in the `$j` variable.</span></span>

## <span data-ttu-id="85a9f-205">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85a9f-205">PARAMETERS</span></span>

### <span data-ttu-id="85a9f-206">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="85a9f-206">-AllowRedirection</span></span>

<span data-ttu-id="85a9f-207">このコマンドレットがこの接続を代替 Uniform Resource Identifier (URI) にリダイレクトできることを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-207">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="85a9f-208">**ConnectionURI** パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトするように指示を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-208">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="85a9f-209">既定では、PowerShell は接続をリダイレクトしませんが、このパラメーターを使用して接続をリダイレクトできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-209">By default, PowerShell doesn't redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="85a9f-210">また、 **MaximumConnectionRedirectionCount** セッション オプション値を変更することで、接続をリダイレクトする回数を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-210">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="85a9f-211">コマンドレットの **Maximumredirection** パラメーターを使用する `New-PSSessionOption` か、Preference 変数の **MaximumConnectionRedirectionCount** プロパティを設定し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-211">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="85a9f-212">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-212">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-213">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="85a9f-213">-ApplicationName</span></span>

<span data-ttu-id="85a9f-214">アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-214">Specifies an application.</span></span> <span data-ttu-id="85a9f-215">このコマンドレットは、指定されたアプリケーションを使用するセッションにのみ接続します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-215">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="85a9f-216">接続 URI のアプリケーション名セグメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-216">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="85a9f-217">たとえば、次の接続 URI では、WSMan はアプリケーション名 `http://localhost:5985/WSMAN` です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-217">For example, in the following connection URI, WSMan is the application name: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="85a9f-218">セッションのアプリケーション名は、セッションの **Runspace.ConnectionInfo.AppName** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-218">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="85a9f-219">パラメーターの値は、セッションを選択してフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-219">The parameter's value is used to select and filter sessions.</span></span> <span data-ttu-id="85a9f-220">セッションで使用されるアプリケーションは変更されません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-220">It doesn't change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-221">-認証</span><span class="sxs-lookup"><span data-stu-id="85a9f-221">-Authentication</span></span>

<span data-ttu-id="85a9f-222">切断されたセッションに再接続するためにコマンドでユーザー資格情報を認証するために使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-222">Specifies the mechanism that's used to authenticate the user credentials in the command to reconnect to a disconnected session.</span></span> <span data-ttu-id="85a9f-223">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-223">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85a9f-224">Default</span><span class="sxs-lookup"><span data-stu-id="85a9f-224">Default</span></span>
- <span data-ttu-id="85a9f-225">Basic</span><span class="sxs-lookup"><span data-stu-id="85a9f-225">Basic</span></span>
- <span data-ttu-id="85a9f-226">Credssp</span><span class="sxs-lookup"><span data-stu-id="85a9f-226">Credssp</span></span>
- <span data-ttu-id="85a9f-227">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="85a9f-227">Digest</span></span>
- <span data-ttu-id="85a9f-228">Kerberos</span><span class="sxs-lookup"><span data-stu-id="85a9f-228">Kerberos</span></span>
- <span data-ttu-id="85a9f-229">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="85a9f-229">Negotiate</span></span>
- <span data-ttu-id="85a9f-230">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="85a9f-230">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="85a9f-231">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-231">The default value is Default.</span></span>

<span data-ttu-id="85a9f-232">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-232">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="85a9f-233">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-233">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="85a9f-234">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-234">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="85a9f-235">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-235">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-236">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="85a9f-236">-CertificateThumbprint</span></span>

<span data-ttu-id="85a9f-237">切断されたセッションに接続するためのアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-237">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="85a9f-238">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-238">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="85a9f-239">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-239">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="85a9f-240">証明書は、ローカルユーザーアカウントにしかマップできず、ドメインアカウントでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-240">Certificates can be mapped only to local user accounts, and don't work with domain accounts.</span></span>

<span data-ttu-id="85a9f-241">証明書の拇印を取得するに `Get-Item` は、PowerShell ドライブでまたはコマンドを使用し `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-241">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-242">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="85a9f-242">-ComputerName</span></span>

<span data-ttu-id="85a9f-243">切断されたセッションが格納されているコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-243">Specifies the computer on which the disconnected session is stored.</span></span> <span data-ttu-id="85a9f-244">セッションは、サーバー側または接続の受信側にあるコンピューターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-244">Sessions are stored on the computer that's at the server-side, or receiving end of a connection.</span></span> <span data-ttu-id="85a9f-245">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-245">The default is the local computer.</span></span>

<span data-ttu-id="85a9f-246">1台のコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-246">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of one computer.</span></span>
<span data-ttu-id="85a9f-247">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-247">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="85a9f-248">ローカルコンピューターを指定するには、コンピューター名、ドット ( `.` )、 `$env:COMPUTERNAME` 、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-248">To specify the local computer, type the computer name, a dot (`.`), `$env:COMPUTERNAME`, or localhost.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-249">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="85a9f-249">-ConfigurationName</span></span>

<span data-ttu-id="85a9f-250">セッション構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-250">Specifies the name of a session configuration.</span></span> <span data-ttu-id="85a9f-251">このコマンドレットは、指定されたセッション構成を使用するセッションにのみ接続します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-251">This cmdlet connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="85a9f-252">セッション構成の構成名または完全修飾リソース URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-252">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="85a9f-253">構成名のみを指定する場合は、次のスキーマ URI が先頭に付加されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-253">If you specify only the configuration name, the following schema URI is prepended:</span></span>

<span data-ttu-id="85a9f-254">`http://schemas.microsoft.com/powershell`.</span><span class="sxs-lookup"><span data-stu-id="85a9f-254">`http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="85a9f-255">セッションの構成名は、セッションの **ConfigurationName** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-255">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="85a9f-256">パラメーターの値は、セッションを選択してフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-256">The parameter's value is used to select and filter sessions.</span></span> <span data-ttu-id="85a9f-257">セッションが使用するセッション構成が変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-257">It doesn't change the session configuration that the session uses.</span></span>

<span data-ttu-id="85a9f-258">セッション構成の詳細については、「 [about_Session_Configurations](./About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-258">For more information about session configurations, see [about_Session_Configurations](./About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-259">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="85a9f-259">-ConnectionUri</span></span>

<span data-ttu-id="85a9f-260">切断されたセッションに再接続するために使用する接続エンドポイントを定義する URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-260">Specifies a URI that defines the connection endpoint that is used to reconnect to the disconnected session.</span></span>

<span data-ttu-id="85a9f-261">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-261">The URI must be fully qualified.</span></span> <span data-ttu-id="85a9f-262">文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-262">The string's format is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="85a9f-263">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-263">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="85a9f-264">接続 URI を指定しない場合は、 **UseSSL** 、 **ComputerName** 、 **Port** 、および **APPLICATIONNAME** パラメーターを使用して接続 uri の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-264">If you don't specify a connection URI, you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="85a9f-265">URI の **Transport** セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-265">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="85a9f-266">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準のポート80を使用して HTTP と443が HTTPS 用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-266">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with standard ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="85a9f-267">PowerShell リモート処理に既定のポートを使用するには、HTTP の場合はポート5985、HTTPS の場合は5986を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-267">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="85a9f-268">対象のコンピューターが接続を別の URI にリダイレクトする場合、コマンドで **Allowredirection** パラメーターを使用しない限り、PowerShell によってリダイレクトが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-268">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases: URI, CU

Required: True
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-269">-Credential</span><span class="sxs-lookup"><span data-stu-id="85a9f-269">-Credential</span></span>

<span data-ttu-id="85a9f-270">切断されたセッションに接続するためのアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-270">Specifies a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="85a9f-271">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-271">The default is the current user.</span></span>

<span data-ttu-id="85a9f-272">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-272">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="85a9f-273">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-273">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="85a9f-274">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-274">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="85a9f-275">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-275">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-276">-Id</span><span class="sxs-lookup"><span data-stu-id="85a9f-276">-Id</span></span>

<span data-ttu-id="85a9f-277">切断されたセッションの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-277">Specifies the ID of a disconnected session.</span></span> <span data-ttu-id="85a9f-278">**Id** パラメーターは、切断されたセッションが現在のセッションに既に接続されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-278">The **Id** parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="85a9f-279">セッションがローカルコンピューターに格納されているが、現在のセッションに接続されていない場合、このパラメーターは有効ですが、有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-279">This parameter is valid, but not effective, when the session is stored on the local computer, but wasn't connected to the current session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-280">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="85a9f-280">-InstanceId</span></span>

<span data-ttu-id="85a9f-281">切断されたセッションのインスタンス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-281">Specifies the instance ID of the disconnected session.</span></span> <span data-ttu-id="85a9f-282">インスタンス ID は、ローカルコンピューターまたはリモートコンピューター上の **PSSession** を一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-282">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span> <span data-ttu-id="85a9f-283">インスタンス ID は、 **PSSession** の **InstanceID** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-283">The instance ID is stored in the **InstanceID** property of the **PSSession**.</span></span>

```yaml
Type: System.Guid
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-284">-JobName</span><span class="sxs-lookup"><span data-stu-id="85a9f-284">-JobName</span></span>

<span data-ttu-id="85a9f-285">が返すジョブのフレンドリ名を指定し `Receive-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-285">Specifies a friendly name for the job that `Receive-PSSession` returns.</span></span>

<span data-ttu-id="85a9f-286">`Receive-PSSession`**Outtarget** パラメーターの値が job の場合、または切断されたセッションで実行されているジョブが現在のセッションで開始された場合に、ジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-286">`Receive-PSSession` returns a job when the value of the **OutTarget** parameter is Job or the job that's running in the disconnected session was started in the current session.</span></span>

<span data-ttu-id="85a9f-287">切断されたセッションで実行されているジョブが現在のセッションで開始された場合、PowerShell は、セッションの元のジョブオブジェクトを再利用し、 **JobName** パラメーターの値を無視します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-287">If the job that's running in the disconnected session was started in the current session, PowerShell reuses the original job object in the session and ignores the value of the **JobName** parameter.</span></span>

<span data-ttu-id="85a9f-288">切断されたセッションで実行されているジョブが別のセッションで開始された場合は、PowerShell によって新しいジョブオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-288">If the job that's running in the disconnected session was started in a different session, PowerShell creates a new job object.</span></span> <span data-ttu-id="85a9f-289">通常は既定の名前を使用ますが、このパラメータを使用して名前を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-289">It uses a default name, but you can use this parameter to change the name.</span></span>

<span data-ttu-id="85a9f-290">**Outtarget** パラメーターの既定値または明示的な値が Job でない場合、コマンドは成功しますが、 **JobName** パラメーターを指定しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-290">If the default value or explicit value of the **OutTarget** parameter isn't Job, the command succeeds, but the **JobName** parameter has no effect.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-291">-Name</span><span class="sxs-lookup"><span data-stu-id="85a9f-291">-Name</span></span>

<span data-ttu-id="85a9f-292">切断されたセッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-292">Specifies the friendly name of the disconnected session.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ConnectionUriSessionName, SessionName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-293">-OutTarget</span><span class="sxs-lookup"><span data-stu-id="85a9f-293">-OutTarget</span></span>

<span data-ttu-id="85a9f-294">セッションの結果を返す方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-294">Determines how the session results are returned.</span></span> <span data-ttu-id="85a9f-295">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-295">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85a9f-296">**ジョブ** 。</span><span class="sxs-lookup"><span data-stu-id="85a9f-296">**Job**.</span></span> <span data-ttu-id="85a9f-297">ジョブ オブジェクトで結果を非同期的に返します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-297">Returns the results asynchronously in a job object.</span></span> <span data-ttu-id="85a9f-298">ジョブに名前を付けたり、名前を変更したりするには、 **JobName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-298">You can use the **JobName** parameter to specify a name or new name for the job.</span></span>
- <span data-ttu-id="85a9f-299">**ホスト** 。</span><span class="sxs-lookup"><span data-stu-id="85a9f-299">**Host**.</span></span> <span data-ttu-id="85a9f-300">コマンドラインに (同期的に) 結果を返します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-300">Returns the results to the command line (synchronously).</span></span> <span data-ttu-id="85a9f-301">コマンドを再開しようとしている場合、または結果が多数のオブジェクトで構成される場合には、応答が遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-301">If the command is being resumed or the results consist of a large number of objects, the response might be delayed.</span></span>

<span data-ttu-id="85a9f-302">**Outtarget** パラメーターの既定値は Host です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-302">The default value of the **OutTarget** parameter is Host.</span></span> <span data-ttu-id="85a9f-303">切断されたセッションで受信しているコマンドが現在のセッションで開始された場合、 **Outtarget** パラメーターの既定値は、コマンドが開始されたフォームです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-303">If the command that's being received in a disconnected session was started in the current session, the default value of the **OutTarget** parameter is the form in which the command was started.</span></span> <span data-ttu-id="85a9f-304">コマンドがジョブとして開始された場合、既定ではジョブとして返されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-304">If the command was started as a job, by default, it's returned as a job.</span></span> <span data-ttu-id="85a9f-305">それ以外の場合は、既定でホストプログラムに返されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-305">Otherwise, it's returned to the host program by default.</span></span>

<span data-ttu-id="85a9f-306">ホスト プログラムは通常、返されたオブジェクトを直ちにコマンド ラインに返します。ただし、この動作は変更することができます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-306">Typically, the host program displays returned objects at the command line without delay, but this behavior can vary.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutTarget
Parameter Sets: (All)
Aliases:
Accepted values: Default, Host, Job

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-307">-Port</span><span class="sxs-lookup"><span data-stu-id="85a9f-307">-Port</span></span>

<span data-ttu-id="85a9f-308">セッションへの再接続に使用するリモートコンピューターのネットワークポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-308">Specifies the remote computer's network port that's used to reconnect to the session.</span></span> <span data-ttu-id="85a9f-309">リモートコンピューターに接続するには、接続が使用するポートでリッスンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-309">To connect to a remote computer, it must be listening on the port that the connection uses.</span></span> <span data-ttu-id="85a9f-310">既定のポートは5985で、これは HTTP 用の WinRM ポート、および HTTPS 用の WinRM ポートである5986です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-310">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="85a9f-311">代替ポートを使用する前に、そのポートでリッスンするようにリモートコンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-311">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen on that port.</span></span> <span data-ttu-id="85a9f-312">リスナーを構成するには、PowerShell プロンプトで次の2つのコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-312">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="85a9f-313">必要な場合を除き、 **Port** パラメーターは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-313">Don't use the **Port** parameter unless it's necessary.</span></span> <span data-ttu-id="85a9f-314">コマンドで設定されたポートは、コマンドを実行するすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-314">The port that's set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="85a9f-315">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-315">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-316">-セッション</span><span class="sxs-lookup"><span data-stu-id="85a9f-316">-Session</span></span>

<span data-ttu-id="85a9f-317">切断されたセッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-317">Specifies the disconnected session.</span></span> <span data-ttu-id="85a9f-318">**Pssession** を含む変数、またはコマンドなどの **pssession** を作成または取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-318">Enter a variable that contains the **PSSession** or a command that creates or gets the **PSSession** , such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-319">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="85a9f-319">-SessionOption</span></span>

<span data-ttu-id="85a9f-320">セッションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-320">Specifies advanced options for the session.</span></span> <span data-ttu-id="85a9f-321">コマンドレットを使用して作成する **sessionoption** オブジェクト、 `New-PSSessionOption` またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-321">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="85a9f-322">オプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-322">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="85a9f-323">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-323">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="85a9f-324">セッションオプションの値は、ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-324">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="85a9f-325">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-325">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="85a9f-326">既定値を含むセッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="85a9f-326">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="85a9f-327">**$PSSessionOption** ユーザー設定変数の詳細については、「 [about_Preference_Variables](./About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-327">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span> <span data-ttu-id="85a9f-328">セッション構成の詳細については、「 [about_Session_Configurations](./About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-328">For more information about session configurations, see [about_Session_Configurations](./About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-329">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="85a9f-329">-UseSSL</span></span>

<span data-ttu-id="85a9f-330">このコマンドレットが、切断されたセッションに接続するために Secure Sockets Layer (SSL) プロトコルを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-330">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="85a9f-331">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-331">By default, SSL isn't used.</span></span>

<span data-ttu-id="85a9f-332">WS-Management は、ネットワーク経由で送信されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-332">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="85a9f-333">**UseSSL** は、HTTP 接続ではなく HTTPS 接続を使用してデータを送信することによって、セキュリティをさらに高める役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="85a9f-333">**UseSSL** is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="85a9f-334">このパラメーターを使用していて、コマンドに使用されているポートで SSL が使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-334">If you use this parameter and SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85a9f-335">-Confirm</span><span class="sxs-lookup"><span data-stu-id="85a9f-335">-Confirm</span></span>

<span data-ttu-id="85a9f-336">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-336">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="85a9f-337">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="85a9f-337">-WhatIf</span></span>

<span data-ttu-id="85a9f-338">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-338">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="85a9f-339">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-339">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="85a9f-340">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="85a9f-340">CommonParameters</span></span>

<span data-ttu-id="85a9f-341">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-341">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85a9f-342">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-342">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85a9f-343">入力</span><span class="sxs-lookup"><span data-stu-id="85a9f-343">INPUTS</span></span>

### <span data-ttu-id="85a9f-344">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="85a9f-344">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="85a9f-345">コマンドレットによって返されるオブジェクトなど、セッションオブジェクトをこのコマンドレットにパイプすることができ `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-345">You can pipe session objects to this cmdlet, such as objects returned by the `Get-PSSession` cmdlet.</span></span>

### <span data-ttu-id="85a9f-346">System.Int32</span><span class="sxs-lookup"><span data-stu-id="85a9f-346">System.Int32</span></span>

<span data-ttu-id="85a9f-347">このコマンドレットには、セッション Id をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-347">You can pipe session Ids to this cmdlet.</span></span>

### <span data-ttu-id="85a9f-348">System.Guid</span><span class="sxs-lookup"><span data-stu-id="85a9f-348">System.Guid</span></span>

<span data-ttu-id="85a9f-349">パイプを使用して、このコマンドレットのセッションのインスタンス Id をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-349">You can pipe the instance Ids of sessions this cmdlet.</span></span>

### <span data-ttu-id="85a9f-350">System.String</span><span class="sxs-lookup"><span data-stu-id="85a9f-350">System.String</span></span>

<span data-ttu-id="85a9f-351">このコマンドレットには、セッション名をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-351">You can pipe session names to this cmdlet.</span></span>

## <span data-ttu-id="85a9f-352">出力</span><span class="sxs-lookup"><span data-stu-id="85a9f-352">OUTPUTS</span></span>

### <span data-ttu-id="85a9f-353">システム管理. ジョブまたは PSObject</span><span class="sxs-lookup"><span data-stu-id="85a9f-353">System.Management.Automation.Job or PSObject</span></span>

<span data-ttu-id="85a9f-354">このコマンドレットは、切断されたセッションで実行されたコマンドの結果を返します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="85a9f-354">This cmdlet returns the results of commands that ran in the disconnected session, if any.</span></span> <span data-ttu-id="85a9f-355">**Outtarget** パラメーターの値または既定値が job の場合、は `Receive-PSSession` ジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-355">If the value or default value of the **OutTarget** parameter is Job, `Receive-PSSession` returns a job object.</span></span> <span data-ttu-id="85a9f-356">それ以外の場合には、コマンドの結果を示すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-356">Otherwise, it returns objects that represent that command results.</span></span>

## <span data-ttu-id="85a9f-357">注</span><span class="sxs-lookup"><span data-stu-id="85a9f-357">NOTES</span></span>

<span data-ttu-id="85a9f-358">`Receive-PSSession` 切断されたセッションからのみ結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-358">`Receive-PSSession` gets results only from sessions that were disconnected.</span></span> <span data-ttu-id="85a9f-359">PowerShell 3.0 以降のバージョンを実行しているコンピューターは、接続されている、または終了したセッションのみを切断し、再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-359">Only sessions that are connected to, or terminate at, computers that run PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>

<span data-ttu-id="85a9f-360">切断されたセッションで実行されていたコマンドが結果を生成しなかった場合、または結果が既に別のセッションに戻されている場合、は `Receive-PSSession` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-360">If the commands that were running in the disconnected session didn't generate results or if the results were already returned to another session, `Receive-PSSession` doesn't generate any output.</span></span>

<span data-ttu-id="85a9f-361">セッションの出力バッファーモードは、セッションが切断されたときにセッション内のコマンドが出力を管理する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-361">A session's output buffering mode determines how commands in the session manage output when the session is disconnected.</span></span> <span data-ttu-id="85a9f-362">セッションの **OutputBufferingMode** オプションの値が Drop で、出力バッファーがいっぱいの場合、コマンドは出力の削除を開始します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-362">When the value of the **OutputBufferingMode** option of the session is Drop and the output buffer is full, the command starts to delete output.</span></span> <span data-ttu-id="85a9f-363">`Receive-PSSession` この出力を回復できません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-363">`Receive-PSSession` can't recover this output.</span></span> <span data-ttu-id="85a9f-364">出力バッファーモードオプションの詳細については、 [新しい-PSSessionOption](New-PSSessionOption.md) と [new-pstransportoption](New-PSTransportOption.md) コマンドレットのヘルプ記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-364">For more information about the output buffering mode option, see the help articles for the [New-PSSessionOption](New-PSSessionOption.md) and [New-PSTransportOption](New-PSTransportOption.md) cmdlets.</span></span>

<span data-ttu-id="85a9f-365">Pssession に接続するとき **、または** 結果を受信するときに、 **pssession** のアイドルタイムアウト値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-365">You can't change the idle time-out value of a **PSSession** when you connect to the **PSSession** or receive results.</span></span> <span data-ttu-id="85a9f-366">の **sessionoption** パラメーターは、 `Receive-PSSession` **IdleTimeout** 値を持つ **sessionoption** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-366">The **SessionOption** parameter of `Receive-PSSession` takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="85a9f-367">ただし、 **Sessionoption** オブジェクトの **idletimeout** 値と変数の **idletimeout** 値 `$PSSessionOption` は、 **PSSession** に接続するとき、または結果を受信するときに無視されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-367">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the `$PSSessionOption` variable are ignored when it connects to a **PSSession** or receiving results.</span></span>

- <span data-ttu-id="85a9f-368">**Pssession の作成時、** またはコマンドレットを使用して pssession のアイドルタイムアウト **を設定** および変更したり、 `New-PSSession` `Invoke-Command` **pssession** から切断したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-368">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the `New-PSSession` or `Invoke-Command` cmdlets, and when you disconnect from the **PSSession**.</span></span>
- <span data-ttu-id="85a9f-369">**PSSession** の **IdleTimeout** プロパティは、切断されたセッションをリモートコンピューターで保持する期間を決定するため、切断されたセッションにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="85a9f-369">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions because it determines how long a disconnected session is maintained on the remote computer.</span></span> <span data-ttu-id="85a9f-370">セッションが切断されると、その時点からアイドル状態であると判断されます。これは、そのセッションでコマンドを実行している場合であっても同じです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-370">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

<span data-ttu-id="85a9f-371">コマンドレットの **AsJob** パラメーターを使用してリモートセッションでジョブの開始ジョブを開始すると、ジョブがリモートセッションで実行されている場合で `Invoke-Command` も、現在のセッションでジョブオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-371">If you start a start a job in a remote session by using the **AsJob** parameter of the `Invoke-Command` cmdlet, the job object is created in the current session, even though the job runs in the remote session.</span></span> <span data-ttu-id="85a9f-372">リモートセッションを切断すると、現在のセッションのジョブオブジェクトがジョブから切断されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-372">If you disconnect the remote session, the job object in the current session is disconnected from the job.</span></span> <span data-ttu-id="85a9f-373">ジョブオブジェクトには、返された結果が含まれていますが、切断されたセッションのジョブから新しい結果を受け取ることはありません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-373">The job object contains any results that were returned to it, but doesn't receive new results from the job in the disconnected session.</span></span>

<span data-ttu-id="85a9f-374">実行中のジョブを含むセッションに別のクライアントが接続した場合、元のセッションの元のジョブオブジェクトに配信された結果は、新しく接続されたセッションでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-374">If a different client connects to the session that contains the running job, the results that were delivered to the original job object in the original session aren't available in the newly connected session.</span></span> <span data-ttu-id="85a9f-375">再接続したセッションでは、元のジョブ オブジェクトに配信されなかった結果のみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-375">Only results that were not delivered to the original job object are available in the reconnected session.</span></span>

<span data-ttu-id="85a9f-376">同様に、セッションでスクリプトを開始し、セッションから切断した場合、セッションに接続している別のクライアントが切断する前にスクリプトがセッションに配信された結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-376">Similarly, if you start a script in a session and then disconnect from the session, any results that the script delivers to the session before disconnecting aren't available to another client that connects to the session.</span></span>

<span data-ttu-id="85a9f-377">切断するセッションでデータが失われないようにするには、コマンドレットの **Indisconnectedsession** パラメーターを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-377">To prevent data loss in sessions that you intend to disconnect, use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="85a9f-378">このパラメーターは現在のセッションに結果が返されないようにするものであるため、セッションに再接続した時点で結果がすべて利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-378">Because this parameter prevents results from being returned to the current session, all results are available when the session is reconnected.</span></span>

<span data-ttu-id="85a9f-379">コマンドレットを使用して `Invoke-Command` リモートセッションでコマンドを実行することで、データの損失を防ぐこともでき `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-379">You can also prevent data loss by using the `Invoke-Command` cmdlet to run a `Start-Job` command in the remote session.</span></span> <span data-ttu-id="85a9f-380">この場合には、リモート セッションでジョブ オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-380">In this case, the job object is created in the remote session.</span></span> <span data-ttu-id="85a9f-381">コマンドレットを使用し `Receive-PSSession` てジョブの結果を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-381">You can't use the `Receive-PSSession` cmdlet to get the job results.</span></span> <span data-ttu-id="85a9f-382">代わりに、コマンドレットを使用して `Connect-PSSession` セッションに接続し、コマンドレットを使用して `Invoke-Command` `Receive-Job` セッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-382">Instead, use the `Connect-PSSession` cmdlet to connect to the session and then use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the session.</span></span>

<span data-ttu-id="85a9f-383">実行中のジョブを含むセッションを切断して再接続すると、元のジョブオブジェクトが再利用されるのは、ジョブが切断されて同じセッションに再接続され、再接続するコマンドで新しいジョブ名が指定されていない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-383">When a session that contains a running job is disconnected and then reconnected, the original job object is reused only if the job is disconnected and reconnected to the same session, and the command to reconnect doesn't specify a new job name.</span></span> <span data-ttu-id="85a9f-384">セッションが別のクライアントセッションに再接続された場合、または新しいジョブ名を指定した場合は、PowerShell によって新しいセッションの新しいジョブオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="85a9f-384">If the session is reconnected to a different client session or a new job name is specified, PowerShell creates a new job object for the new session.</span></span>

<span data-ttu-id="85a9f-385">**PSSession** を切断すると、セッション状態は Disconnected になり、可用性は None になります。</span><span class="sxs-lookup"><span data-stu-id="85a9f-385">When you disconnect a **PSSession** , the session state is Disconnected and the availability is None.</span></span>

- <span data-ttu-id="85a9f-386">**State** プロパティの値は、現在のセッションに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="85a9f-386">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="85a9f-387">値が Disconnected の場合は、 **PSSession** が現在のセッションに接続されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-387">A value of Disconnected means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="85a9f-388">ただし、 **PSSession** がすべてのセッションから切断されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="85a9f-388">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="85a9f-389">別のセッションに接続されている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="85a9f-389">It might be connected to a different session.</span></span>
  <span data-ttu-id="85a9f-390">セッションに接続または再接続できるかどうかを確認するには、 **Availability** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-390">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>
- <span data-ttu-id="85a9f-391">**Availability** の値が None の場合は、セッションに接続できることを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-391">An **Availability** value of None indicates that you can connect to the session.</span></span> <span data-ttu-id="85a9f-392">値が Busy の場合は、PSSession が別のセッションに接続されているため、 **PSSession** に接続できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="85a9f-392">A value of Busy indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span>
- <span data-ttu-id="85a9f-393">セッションの **State** プロパティの値の詳細については、MSDN ライブラリの「 [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-393">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate) in the MSDN library.</span></span>
- <span data-ttu-id="85a9f-394">セッションの **Availability** プロパティの値の詳細については、「 [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a9f-394">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="85a9f-395">関連リンク</span><span class="sxs-lookup"><span data-stu-id="85a9f-395">RELATED LINKS</span></span>

[<span data-ttu-id="85a9f-396">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="85a9f-396">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="85a9f-397">about_Remote</span><span class="sxs-lookup"><span data-stu-id="85a9f-397">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="85a9f-398">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="85a9f-398">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="85a9f-399">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="85a9f-399">about_Session_Configurations</span></span>](./About/about_Session_Configurations.md)

[<span data-ttu-id="85a9f-400">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="85a9f-400">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="85a9f-401">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="85a9f-401">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="85a9f-402">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="85a9f-402">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="85a9f-403">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="85a9f-403">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="85a9f-404">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="85a9f-404">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="85a9f-405">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="85a9f-405">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="85a9f-406">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="85a9f-406">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="85a9f-407">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="85a9f-407">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="85a9f-408">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="85a9f-408">Remove-PSSession</span></span>](Remove-PSSession.md)