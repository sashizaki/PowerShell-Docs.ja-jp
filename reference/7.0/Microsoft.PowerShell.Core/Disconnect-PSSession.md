---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disconnect-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-PSSession
ms.openlocfilehash: b3ee9ce8f699e66a091a017eb8c1b0c49f1b7636
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218512"
---
# <span data-ttu-id="664a6-103">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="664a6-103">Disconnect-PSSession</span></span>

## <span data-ttu-id="664a6-104">概要</span><span class="sxs-lookup"><span data-stu-id="664a6-104">SYNOPSIS</span></span>
<span data-ttu-id="664a6-105">セッションから切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-105">Disconnects from a session.</span></span>

## <span data-ttu-id="664a6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="664a6-106">SYNTAX</span></span>

### <span data-ttu-id="664a6-107">セッション (既定)</span><span class="sxs-lookup"><span data-stu-id="664a6-107">Session (Default)</span></span>

```
Disconnect-PSSession [-Session] <PSSession[]> [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="664a6-108">名前</span><span class="sxs-lookup"><span data-stu-id="664a6-108">Name</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="664a6-109">InstanceId</span><span class="sxs-lookup"><span data-stu-id="664a6-109">InstanceId</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="664a6-110">Id</span><span class="sxs-lookup"><span data-stu-id="664a6-110">Id</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="664a6-111">Description</span><span class="sxs-lookup"><span data-stu-id="664a6-111">DESCRIPTION</span></span>

<span data-ttu-id="664a6-112">コマンドレットは、 `Disconnect-PSSession` コマンドレットを使用して開始された PowerShell セッション ("PSSession") を `New-PSSession` 現在のセッションから切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-112">The `Disconnect-PSSession` cmdlet disconnects a PowerShell session ("PSSession"), such as one started by using the `New-PSSession` cmdlet, from the current session.</span></span> <span data-ttu-id="664a6-113">その結果、PSSession は切断状態になります。</span><span class="sxs-lookup"><span data-stu-id="664a6-113">As a result, the PSSession is in a disconnected state.</span></span> <span data-ttu-id="664a6-114">切断された PSSession には、現在のセッションから、またはローカル コンピューターや別のコンピューターの別のセッションから接続できます。</span><span class="sxs-lookup"><span data-stu-id="664a6-114">You can connect to the disconnected PSSession from the current session or from another session on the local computer or a different computer.</span></span>

<span data-ttu-id="664a6-115">`Disconnect-PSSession`コマンドレットは、現在のセッションに接続されている開いている pssession のみを切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-115">The `Disconnect-PSSession` cmdlet disconnects only open PSSessions that are connected to the current session.</span></span> <span data-ttu-id="664a6-116">`Disconnect-PSSession` 壊れた、または閉じた PSSessions、またはコマンドレットを使用して開始された対話型 PSSessions を切断することはできません。また、 `Enter-PSSession` 他のセッションに接続している pssession を切断することもできません。</span><span class="sxs-lookup"><span data-stu-id="664a6-116">`Disconnect-PSSession` cannot disconnect broken or closed PSSessions, or interactive PSSessions started by using the `Enter-PSSession` cmdlet, and it cannot disconnect PSSessions that are connected to other sessions.</span></span>

<span data-ttu-id="664a6-117">切断された PSSession に再接続するに `Connect-PSSession` は、またはコマンドレットを使用し `Receive-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-117">To reconnect to a disconnected PSSession, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span>

<span data-ttu-id="664a6-118">PSSession がタイムアウトになるか、出力バッファーがいっぱいになって PSSession 内のコマンドがブロックされた場合を除き、PSSession が切断された場合でも、PSSession 内のコマンドは完了するまで継続して実行されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-118">When a PSSession is disconnected, the commands in the PSSession continue to run until they complete, unless the PSSession times out or the commands in the PSSession are blocked by a full output buffer.</span></span> <span data-ttu-id="664a6-119">アイドル タイムアウトを変更するには、 **IdleTimeoutSec** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="664a6-119">To change the idle timeout, use the **IdleTimeoutSec** parameter.</span></span> <span data-ttu-id="664a6-120">出力バッファーモードを変更するには、 **OutputBufferingMode** パラメーターを使用して、コマンドレットの **indisconnectedsession** パラメーターを使用して、 `Invoke-Command` 切断されたセッションでコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="664a6-120">To change the output buffering mode, use the **OutputBufferingMode** parameter You can also use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet to run a command in a disconnected session.</span></span>

<span data-ttu-id="664a6-121">切断されたセッションの機能の詳細については、「[about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="664a6-121">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="664a6-122">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="664a6-122">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="664a6-123">例</span><span class="sxs-lookup"><span data-stu-id="664a6-123">EXAMPLES</span></span>

### <span data-ttu-id="664a6-124">例 1-名前を指定してセッションを切断する</span><span class="sxs-lookup"><span data-stu-id="664a6-124">Example 1 - Disconnect a session by name</span></span>

<span data-ttu-id="664a6-125">このコマンドは、Server01 コンピューター上の UpdateSession PSSession を現在のセッションから切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-125">This command disconnects the UpdateSession PSSession on the Server01 computer from the current session.</span></span> <span data-ttu-id="664a6-126">このコマンドは、 **Name** パラメーターを使用して PSSession を識別します。</span><span class="sxs-lookup"><span data-stu-id="664a6-126">The command uses the **Name** parameter to identify the PSSession.</span></span>

```
PS> Disconnect-PSSession -Name UpdateSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  UpdateSession   Server01        Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="664a6-127">出力には、切断の試行が成功したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-127">The output shows that the attempt to disconnect was successful.</span></span> <span data-ttu-id="664a6-128">セッションの状態は Disconnected であり、Availability は None です。つまり、セッションがビジー状態ではなく、再接続できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="664a6-128">The session state is Disconnected and the Availability is None, which indicates that the session is not busy and can be reconnected.</span></span>

### <span data-ttu-id="664a6-129">例 2-特定のコンピューターからセッションを切断する</span><span class="sxs-lookup"><span data-stu-id="664a6-129">Example 2 - Disconnect a session from a specific computer</span></span>

<span data-ttu-id="664a6-130">このコマンドは、Server12 コンピューター上の ITTask PSSession を現在のセッションから切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-130">This command disconnects the ITTask PSSession on the Server12 computer from the current session.</span></span>
<span data-ttu-id="664a6-131">ITTask セッションは、現在のセッションで作成され、Server12 コンピューターに接続されています。</span><span class="sxs-lookup"><span data-stu-id="664a6-131">The ITTask session was created in the current session and connects to the Server12 computer.</span></span> <span data-ttu-id="664a6-132">このコマンドは、コマンドレットを使用してセッションを取得し、コマンドレットを使用し `Get-PSSession` てセッションを `Disconnect-PSSession` 切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-132">The command uses the `Get-PSSession` cmdlet to get the session and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span>

```
PS> Get-PSSession -ComputerName Server12 -Name ITTask |
  Disconnect-PSSession -OutputBufferingMode Drop -IdleTimeoutSec 86400
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  ITTask          Server12        Disconnected  ITTasks               None
```

<span data-ttu-id="664a6-133">この `Disconnect-PSSession` コマンドは、 **OutputBufferingMode** パラメーターを使用して出力モードを **Drop** に設定します。</span><span class="sxs-lookup"><span data-stu-id="664a6-133">The `Disconnect-PSSession` command uses the **OutputBufferingMode** parameter to set the output mode to **Drop**.</span></span> <span data-ttu-id="664a6-134">この設定により、セッション出力バッファーがいっぱいになった場合でも、セッションで実行されているスクリプトの実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-134">This setting ensures that the script that is running in the session can continue to run even if the session output buffer is full.</span></span> <span data-ttu-id="664a6-135">スクリプトの出力はファイル共有のレポートに書き込まれるため、他の出力は失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="664a6-135">Because the script writes its output to a report on a file share, other output can be lost without consequence.</span></span>

<span data-ttu-id="664a6-136">また、このコマンドでは、 **IdleTimeoutSec** パラメーターを使用して、セッションのアイドル タイムアウトを 24 時間に延長します。</span><span class="sxs-lookup"><span data-stu-id="664a6-136">The command also uses the **IdleTimeoutSec** parameter to extend the idle timeout of the session to 24 hours.</span></span> <span data-ttu-id="664a6-137">この設定により、この管理者または他の管理者はセッションに再接続し、実行されたスクリプトを検証して、必要に応じてトラブルシューティングを行うための時間を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="664a6-137">This setting allows time for this administrator or other administrators to reconnect to the session to verify that the script ran and troubleshoot if needed.</span></span>

### <span data-ttu-id="664a6-138">例 3-複数のコンピューターでの複数の pssession の使用</span><span class="sxs-lookup"><span data-stu-id="664a6-138">Example 3 - Using multiple PSSessions on multiple computers</span></span>

<span data-ttu-id="664a6-139">この一連のコマンドは、 `Disconnect-PSSession` エンタープライズシナリオでコマンドレットがどのように使用されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="664a6-139">This series of commands shows how the `Disconnect-PSSession` cmdlet might be used in an enterprise scenario.</span></span> <span data-ttu-id="664a6-140">このケースでは、新しい技術者がリモート コンピューター上のセッションのスクリプトを開始したときに問題が発生したため、</span><span class="sxs-lookup"><span data-stu-id="664a6-140">In this case, a new technician starts a script in a session on a remote computer and runs into a problem.</span></span> <span data-ttu-id="664a6-141">経験豊富なマネージャーによるセッションへの接続および問題解決を依頼できるように、セッションを切断しました。</span><span class="sxs-lookup"><span data-stu-id="664a6-141">The technician disconnects from the session so that a more experienced manager can connect to the session and resolve the problem.</span></span>

```
PS> $s = New-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
PS> Invoke-Command $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Get-PSSession -Name ITTask -ComputerName Srv1 | Disconnect-PSSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1 ITTask           Srv1            Disconnected  Microsoft.PowerShell          None

PS> Get-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None
 2 ITTask          Srv2            Opened        Microsoft.PowerShell     Available
 3 ITTask          Srv30           Opened        Microsoft.PowerShell     Available

PS> Get-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None

PS> $s = Connect-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
PS> Invoke-Command -Session $s {dir $home\Scripts\PatchStatusOutput.ps1}
PS> Invoke-Command -Session $s {mkdir $home\Scripts\PatchStatusOutput}
PS> Invoke-Command -Session $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Disconnect-PSSession -Session $s
```

<span data-ttu-id="664a6-142">この技術者は、最初に複数のリモート コンピューターでセッションを作成し、各セッションでスクリプトを実行しました。</span><span class="sxs-lookup"><span data-stu-id="664a6-142">The technician begins by creating sessions on several remote computers and running a script in each session.</span></span> <span data-ttu-id="664a6-143">最初のコマンドは、 `New-PSSession` コマンドレットを使用して、3台のリモートコンピューター上に ITTask セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="664a6-143">The first command uses the `New-PSSession` cmdlet to create the ITTask session on three remote computers.</span></span> <span data-ttu-id="664a6-144">このコマンドは、セッションを $s 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="664a6-144">The command saves the sessions in the $s variable.</span></span> <span data-ttu-id="664a6-145">2番目のコマンドは、コマンドレットの **FilePath** パラメーターを使用して、 `Invoke-Command` $s 変数内のセッションでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="664a6-145">The second command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run a script in the sessions in the $s variable.</span></span>

<span data-ttu-id="664a6-146">Srv1 コンピューターで実行中のスクリプトで、予期しないエラーが生成されました。</span><span class="sxs-lookup"><span data-stu-id="664a6-146">The script running on the Srv1 computer generates unexpected errors.</span></span> <span data-ttu-id="664a6-147">技術者はマネージャーに連絡し、サポートを依頼しました。</span><span class="sxs-lookup"><span data-stu-id="664a6-147">The technician contacts his manager and asks for assistance.</span></span> <span data-ttu-id="664a6-148">マネージャーは、調査できるように、セッションから切断するように技術者に指示します。2番目のコマンドは、コマンドレットを使用して、 `Get-PSSession` Srv1 コンピューター上の ITTask セッションを取得し、コマンドレットを使用し `Disconnect-PSSession` て切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-148">The manager directs the technician to disconnect from the session so he can investigate.The second command uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span> <span data-ttu-id="664a6-149">このコマンドは、他のコンピューター上の ITTask セッションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="664a6-149">This command does not affect the ITTask sessions on the other computers.</span></span>

<span data-ttu-id="664a6-150">3番目のコマンドは、 `Get-PSSession` コマンドレットを使用して ITTask セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="664a6-150">The third command uses the `Get-PSSession` cmdlet to get the ITTask sessions.</span></span> <span data-ttu-id="664a6-151">出力には、切断のコマンドが Srv2 および Srv30 コンピューターの ITTask セッションに影響を与えなかったことが示されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-151">The output shows that the ITTask sessions on the Srv2 and Srv30 computers were not affected by the command to disconnect.</span></span>

<span data-ttu-id="664a6-152">マネージャーはホームコンピューターにログオンし、会社のネットワークに接続して PowerShell を起動し、コマンドレットを使用して `Get-PSSession` Srv1 コンピューター上の ITTask セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="664a6-152">The manager logs on to his home computer, connects to his corporate network, starts PowerShell, and uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="664a6-153">マネージャーは、技術者の資格情報を使用してセッションにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="664a6-153">He uses the credentials of the technician to access the session.</span></span>

<span data-ttu-id="664a6-154">次に、コマンドレットを使用して、 `Connect-PSSession` Srv1 コンピューター上の ITTask セッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="664a6-154">Next, the manager uses the `Connect-PSSession` cmdlet to connect to the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="664a6-155">このコマンドは、セッションを $s 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="664a6-155">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="664a6-156">マネージャーは、コマンドレットを使用して、 `Invoke-Command` 変数内のセッションでいくつかの診断コマンドを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-156">The manager uses the `Invoke-Command` cmdlet to run some diagnostic commands in the session in the `$s` variable.</span></span> <span data-ttu-id="664a6-157">これにより、必要なディレクトリが見つからなかったためにスクリプトが失敗したことが判明しました。</span><span class="sxs-lookup"><span data-stu-id="664a6-157">He recognizes that the script failed because it did not find a required directory.</span></span>
<span data-ttu-id="664a6-158">マネージャーは、関数を使用して `MkDir` ディレクトリを作成し、スクリプトを再起動して `Get-PatchStatus.ps1` セッションから切断します。マネージャーは、その結果を技術者に報告し、タスクを完了するためにセッションに再接続し、必要なディレクトリが存在しない場合に作成するコマンドをスクリプトに追加するように指示し `Get-PatchStatus.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-158">The manager uses the `MkDir` function to create the directory, and then he restarts the `Get-PatchStatus.ps1` script and disconnects from the session.The manager reports his findings to the technician, suggests that he reconnect to the session to complete the tasks, and asks him to add a command to the `Get-PatchStatus.ps1` script that creates the required directory if it does not exist.</span></span>

### <span data-ttu-id="664a6-159">例 4-PSSession のタイムアウト値を変更する</span><span class="sxs-lookup"><span data-stu-id="664a6-159">Example 4 - Change the timeout value for a PSSession</span></span>

<span data-ttu-id="664a6-160">この例では、セッションを切断できるように **IdleTimeout** プロパティの値を修正する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="664a6-160">This example shows how to correct the value of the **IdleTimeout** property of a session so that it can be disconnected.</span></span>

<span data-ttu-id="664a6-161">切断されたセッションが削除されるまでの期間は、セッションのアイドル タイムアウト プロパティで決定されるため、このプロパティは切断するセッションにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="664a6-161">The idle timeout property of a session is critical to disconnected sessions, because it determines how long a disconnected session is maintained before it is deleted.</span></span> <span data-ttu-id="664a6-162">アイドル タイムアウト オプションは、セッションの作成時およびセッションの切断時に設定できます。</span><span class="sxs-lookup"><span data-stu-id="664a6-162">You can set the idle timeout option when you create a session and when you disconnect it.</span></span> <span data-ttu-id="664a6-163">セッションのアイドルタイムアウトの既定値は、ローカルコンピューターのユーザー設定 `$PSSessionOption` 変数と、リモートコンピューター上のセッション構成で設定されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-163">The default values for the idle timeout of a session are set in the `$PSSessionOption` preference variable on the local computer and in the session configuration on the remote computer.</span></span> <span data-ttu-id="664a6-164">セッションに設定された値は、セッション構成に設定された値よりも優先されますが、セッション値はセッション構成で設定されたクォータ ( **MaxIdleTimeoutMs** 値など) を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="664a6-164">Values set for the session take precedence over values set in the session configuration, but session values cannot exceed quotas set in the session configuration, such as the **MaxIdleTimeoutMs** value.</span></span>

```
PS> $Timeout = New-PSSessionOption -IdleTimeout 172800000
PS> $s = New-PSSession -Computer Server01 -Name ITTask -SessionOption $Timeout
PS> Disconnect-PSSession -Session $s
Disconnect-PSSession : The session ITTask cannot be disconnected because the specified
idle timeout value 172800(seconds) is either greater than the server maximum allowed
43200 (seconds) or less that the minimum allowed60(seconds).  Choose an idle time out
value that is within the allowed range and try again.

PS> Invoke-Command -ComputerName Server01 {Get-PSSessionConfiguration Microsoft.PowerShell} |
 Format-List -Property *

Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/microsoft.powershell
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
SecurityDescriptorSddl        : O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GXGW;;;WD)
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 2147483647
Uri                           : http://schemas.microsoft.com/powershell/microsoft.powershell
SDKVersion                    : 2
Name                          : microsoft.powershell
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
ParentResourceUri             : http://schemas.microsoft.com/powershell/microsoft.powershell
Enabled                       : true
MaxShells                     : 25
MaxShellsPerUser              : 25
Permission                    : BUILTIN\Administrators AccessAllowed
PSComputerName                : localhost
RunspaceId                    : aea84310-6dbf-4c21-90ac-13980039925a
PSShowComputerName            : True


PS> $s.Runspace.ConnectionInfo
ConnectionUri                     : http://Server01/wsman
ComputerName                      : Server01
Scheme                            : http
Port                              : 80
AppName                           : /wsman
Credential                        :
ShellUri                          : http://schemas.microsoft.com/powershell/Microsoft.PowerShell
AuthenticationMechanism           : Default
CertificateThumbprint             :
MaximumConnectionRedirectionCount : 5
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
UseCompression                    : True
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
NoEncryption                      : False
UseUTF16                          : False
OutputBufferingMode               : Drop
IncludePortInSPN                  : False
Culture                           : en-US
UICulture                         : en-US
OpenTimeout                       : 180000
CancelTimeout                     : 60000
OperationTimeout                  : 180000
IdleTimeout                       : 172800000

PS> Disconnect-PSSession $s -IdleTimeoutSec 43200
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Disconnected  Microsoft.PowerShell          None

PS> $s.Runspace.ConnectionInfo.IdleTimeout
43200000
```

<span data-ttu-id="664a6-165">最初のコマンドは、コマンドレットを使用して `New-PSSessionOption` セッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="664a6-165">The first command uses the `New-PSSessionOption` cmdlet to create a session option object.</span></span> <span data-ttu-id="664a6-166">**IdleTimeout** パラメーターを使用して、アイドル タイムアウトを 48 時間 (172,800,000 ミリ秒) に設定します。</span><span class="sxs-lookup"><span data-stu-id="664a6-166">It uses the **IdleTimeout** parameter to set an idle timeout of 48 hours (172800000 milliseconds).</span></span> <span data-ttu-id="664a6-167">セッション オプション オブジェクトは $Timeout 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-167">The command saves the session option object in the $Timeout variable.</span></span>

<span data-ttu-id="664a6-168">2番目のコマンドは、コマンドレットを使用して、 `New-PSSession` Server01 コンピューター上の ITTask セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="664a6-168">The second command uses the `New-PSSession` cmdlet to create the ITTask session on the Server01 computer.</span></span> <span data-ttu-id="664a6-169">セッションは $Timeout 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-169">The command save the session in the $s variable.</span></span> <span data-ttu-id="664a6-170">**SessionOption** パラメーターの値は、$Timeout 変数内の 48 時間のアイドル タイムアウトです。</span><span class="sxs-lookup"><span data-stu-id="664a6-170">The value of the **SessionOption** parameter is the 48-hour idle timeout in the $Timeout variable.</span></span>

<span data-ttu-id="664a6-171">3 番目のコマンドは、$s 変数内の ITTask セッションを切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-171">The third command disconnects the ITTask session in the $s variable.</span></span> <span data-ttu-id="664a6-172">セッションのアイドル タイムアウト値がセッション構成の **MaxIdleTimeoutMs** クォータを超えているため、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="664a6-172">The command fails because the idle timeout value of the session exceeds the **MaxIdleTimeoutMs** quota in the session configuration.</span></span> <span data-ttu-id="664a6-173">アイドル タイムアウトはセッションが切断されるまで使用されないため、セッションの使用中にはこの違反が検出されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="664a6-173">Because the idle timeout is not used until the session is disconnected, this violation can go undetected while the session is in use.</span></span>

<span data-ttu-id="664a6-174">4番目のコマンドは、コマンドレットを使用して、 `Invoke-Command` `Get-PSSessionConfiguration` Server01 コンピューター上の Microsoft PowerShell セッション構成のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="664a6-174">The fourth command uses the `Invoke-Command` cmdlet to run a `Get-PSSessionConfiguration` command for the Microsoft.PowerShell session configuration on the Server01 computer.</span></span> <span data-ttu-id="664a6-175">このコマンドは、コマンドレットを使用して、 `Format-List` セッション構成のすべてのプロパティを一覧に表示します。出力には、セッション構成を使用するセッションで許可される **IdleTimeout** の最大値を確立する **MaxIdleTimeoutMS** プロパティが4320万ミリ秒 (12 時間) であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="664a6-175">The command uses the `Format-List` cmdlet to display all properties of the session configuration in a list.The output shows that the **MaxIdleTimeoutMS** property, which establishes the maximum permitted **IdleTimeout** value for sessions that use the session configuration, is 43200000 milliseconds (12 hours).</span></span>

<span data-ttu-id="664a6-176">5 番目のコマンドは、$s 変数内のセッションのセッション オプション値を取得します。</span><span class="sxs-lookup"><span data-stu-id="664a6-176">The fifth command gets the session option values of the session in the $s variable.</span></span> <span data-ttu-id="664a6-177">多くのセッションオプションの値は、セッションの実行 **空間** プロパティの **ConnectionInfo** プロパティのプロパティです。出力は、セッションの **IdleTimeout** プロパティの値が1億7280万ミリ秒 (48 時間) であることを示しています。これは、セッション構成の12時間の **MaxIdleTimeoutMs** クォータに違反します。この競合を解決するには、 **ConfigurationName** パラメーターを使用して別のセッション構成を選択するか、 **IdleTimeout** パラメーターを使用してセッションのアイドルタイムアウトを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="664a6-177">The values of many session options are properties of the **ConnectionInfo** property of the **Runspace** property of the session.The output shows that the value of the **IdleTimeout** property of the session is 172800000 milliseconds (48 hours), which violates the **MaxIdleTimeoutMs** quota of 12 hours in the session configuration.To resolve this conflict, you can use the **ConfigurationName** parameter to select a different session configuration or use the **IdleTimeout** parameter to reduce the idle timeout of the session.</span></span>

<span data-ttu-id="664a6-178">6 番目のコマンドは、セッションを切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-178">The sixth command disconnects the session.</span></span> <span data-ttu-id="664a6-179">これは **IdleTimeoutSec** パラメーターを使用して、アイドル タイムアウトを 12 時間に設定します。</span><span class="sxs-lookup"><span data-stu-id="664a6-179">It uses the **IdleTimeoutSec** parameter to set the idle timeout to the 12-hour maximum.</span></span>

<span data-ttu-id="664a6-180">7 番目のコマンドは、切断されたセッションのミリ秒で測定された **IdleTimeout** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="664a6-180">The seventh command gets the value of the **IdleTimeout** property of the disconnected session, which is measured in milliseconds.</span></span> <span data-ttu-id="664a6-181">コマンドが成功したことを出力で確認します。</span><span class="sxs-lookup"><span data-stu-id="664a6-181">The output confirms that the command was successful.</span></span>

## <span data-ttu-id="664a6-182">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="664a6-182">PARAMETERS</span></span>

### <span data-ttu-id="664a6-183">-Id</span><span class="sxs-lookup"><span data-stu-id="664a6-183">-Id</span></span>

<span data-ttu-id="664a6-184">指定されたセッション ID を持つセッションから切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-184">Disconnects from sessions with the specified session ID.</span></span> <span data-ttu-id="664a6-185">1 つ以上の ID をコンマで区切って入力するか、範囲演算子 (..) を使用して ID の範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="664a6-185">Type one or more IDs (separated by commas), or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="664a6-186">セッションの ID を取得するには、コマンドレットを使用し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-186">To get the ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="664a6-187">インスタンス ID は、セッションの **ID** プロパティに格納されています。</span><span class="sxs-lookup"><span data-stu-id="664a6-187">The instance ID is stored in the **ID** property of the session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="664a6-188">-IdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="664a6-188">-IdleTimeoutSec</span></span>

<span data-ttu-id="664a6-189">切断された PSSession のアイドル タイムアウトを変更します。</span><span class="sxs-lookup"><span data-stu-id="664a6-189">Changes the idle timeout value of the disconnected PSSession.</span></span> <span data-ttu-id="664a6-190">値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="664a6-190">Enter a value in seconds.</span></span> <span data-ttu-id="664a6-191">最小値は 60 (1 分) です。</span><span class="sxs-lookup"><span data-stu-id="664a6-191">The minimum value is 60 (1 minute).</span></span>

<span data-ttu-id="664a6-192">アイドル タイムアウトにより、切断された PSSession がリモート コンピューターで維持される期間が決まります。</span><span class="sxs-lookup"><span data-stu-id="664a6-192">The idle timeout determines how long the disconnected PSSession is maintained on the remote computer.</span></span> <span data-ttu-id="664a6-193">タイムアウトになると、PSSession が削除されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-193">When the timeout expires, the PSSession is deleted.</span></span>

<span data-ttu-id="664a6-194">PSSession が切断されると、その時点からアイドル状態であると判断されます。これは、そのセッションでコマンドを実行している場合であっても同じです。</span><span class="sxs-lookup"><span data-stu-id="664a6-194">Disconnected PSSessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

<span data-ttu-id="664a6-195">セッションのアイドル タイムアウトの既定値は、セッション構成の **IdleTimeoutMs** プロパティにより設定されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-195">The default value for the idle timeout of a session is set by the value of the **IdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="664a6-196">既定値は 7,200,000 ミリ秒 (2 時間) です。</span><span class="sxs-lookup"><span data-stu-id="664a6-196">The default value is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="664a6-197">このパラメーターの値は、$PSSessionOption 設定変数の **IdleTimeout** プロパティの値およびセッション構成の既定のアイドル タイムアウト値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-197">The value of this parameter takes precedence over the value of the **IdleTimeout** property of the $PSSessionOption preference variable and the default idle timeout value in the session configuration.</span></span> <span data-ttu-id="664a6-198">ただし、この値はセッション構成の **MaxIdleTimeoutMs** プロパティの値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="664a6-198">However, this value cannot exceed the value of the **MaxIdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="664a6-199">**MaxIdleTimeoutMs** の既定値は 12 時間 (43,200,000 ミリ秒) です。</span><span class="sxs-lookup"><span data-stu-id="664a6-199">The default value of **MaxIdleTimeoutMs** is 12 hours (43200000 milliseconds).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="664a6-200">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="664a6-200">-InstanceId</span></span>

<span data-ttu-id="664a6-201">指定されたインスタンス ID を持つセッションから切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-201">Disconnects from sessions with the specified instance IDs.</span></span>

<span data-ttu-id="664a6-202">インスタンス ID は、ローカル コンピューターまたはリモート コンピューターのセッションを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="664a6-202">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="664a6-203">複数のコンピューター上の複数のセッションであっても、インスタンス ID は一意です。</span><span class="sxs-lookup"><span data-stu-id="664a6-203">The instance ID is unique, even across multiple sessions on multiple computers.</span></span>

<span data-ttu-id="664a6-204">セッションのインスタンス ID を取得するには、コマンドレットを使用し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-204">To get the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="664a6-205">インスタンス ID は、セッションの **InstanceID** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-205">The instance ID is stored in the **InstanceID** property of the session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="664a6-206">-Name</span><span class="sxs-lookup"><span data-stu-id="664a6-206">-Name</span></span>

<span data-ttu-id="664a6-207">指定されたフレンドリ名を持つセッションから切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-207">Disconnects from sessions with the specified friendly names.</span></span> <span data-ttu-id="664a6-208">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="664a6-208">Wildcards are permitted.</span></span>

<span data-ttu-id="664a6-209">セッションのフレンドリ名を取得するには、コマンドレットを使用し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-209">To get the friendly name of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="664a6-210">フレンドリ名は、セッションの **Name** プロパティに格納されています。</span><span class="sxs-lookup"><span data-stu-id="664a6-210">The friendly name is stored in the **Name** property of the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="664a6-211">-セッション</span><span class="sxs-lookup"><span data-stu-id="664a6-211">-Session</span></span>

<span data-ttu-id="664a6-212">指定された PSSession から切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-212">Disconnects from the specified PSSessions.</span></span> <span data-ttu-id="664a6-213">コマンドレットから返されるような PSSession オブジェクトを入力し `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-213">Enter PSSession objects, such as those that the `New-PSSession` cmdlet returns.</span></span> <span data-ttu-id="664a6-214">パイプを使用して PSSession オブジェクトをにパイプすることもでき `Disconnect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-214">You can also pipe a PSSession object to `Disconnect-PSSession`.</span></span>

<span data-ttu-id="664a6-215">`Get-PSSession`コマンドレットは、リモートコンピューターで終了するすべての pssession を取得できます。これには、切断された pssession と、他のコンピューター上の他のセッションに接続されている pssession も含まれます。</span><span class="sxs-lookup"><span data-stu-id="664a6-215">The `Get-PSSession` cmdlet can get all PSSessions that terminate at a remote computer, including PSSessions that are disconnected and PSSessions that are connected to other sessions on other computers.</span></span> <span data-ttu-id="664a6-216">`Disconnect-PSSession` 現在のセッションに接続されている PSSession のみを切断します。</span><span class="sxs-lookup"><span data-stu-id="664a6-216">`Disconnect-PSSession` disconnects only PSSession that are connected to the current session.</span></span> <span data-ttu-id="664a6-217">他の PSSessions をにパイプすると `Disconnect-PSSession` 、 `Disconnect-PSSession` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="664a6-217">If you pipe other PSSessions to `Disconnect-PSSession`, the `Disconnect-PSSession` command fails.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="664a6-218">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="664a6-218">-ThrottleLimit</span></span>

<span data-ttu-id="664a6-219">コマンドのスロットル制限を設定し `Disconnect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-219">Sets the throttle limit for the `Disconnect-PSSession` command.</span></span>

<span data-ttu-id="664a6-220">スロットルの制限は、このコマンドを実行するために確立できるコンカレント接続の最大値です。</span><span class="sxs-lookup"><span data-stu-id="664a6-220">The throttle limit is the maximum number of concurrent connections that can be established to run this command.</span></span> <span data-ttu-id="664a6-221">このパラメーターを省略した場合、または値 0 を入力した場合は、既定値の 32 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-221">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="664a6-222">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="664a6-222">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="664a6-223">-OutputBufferingMode</span><span class="sxs-lookup"><span data-stu-id="664a6-223">-OutputBufferingMode</span></span>

<span data-ttu-id="664a6-224">出力バッファーがいっぱいになったときに切断されたセッションでコマンド出力を管理する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="664a6-224">Determines how command output is managed in the disconnected session when the output buffer is full.</span></span> <span data-ttu-id="664a6-225">既定値は **Block** です。</span><span class="sxs-lookup"><span data-stu-id="664a6-225">The default value is **Block**.</span></span>

<span data-ttu-id="664a6-226">切断されたセッションのコマンドで出力が返されたが、出力バッファーがいっぱいになっている場合に、コマンドをセッションの切断中に継続して実行するかどうかは、実質的にこのパラメーターの値によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-226">If the command in the disconnected session is returning output and the output buffer fills, the value of this parameter effectively determines whether the command continues to run while the session is disconnected.</span></span> <span data-ttu-id="664a6-227">値が **Block** の場合は、セッションが再接続されるまでコマンドが中断されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-227">A value of **Block** suspends the command until the session is reconnected.</span></span> <span data-ttu-id="664a6-228">値が **Drop** の場合は、データが失われる可能性はありますが、コマンドを完了できます。</span><span class="sxs-lookup"><span data-stu-id="664a6-228">A value of **Drop** allows the command to complete, although data might be lost.</span></span> <span data-ttu-id="664a6-229">**Drop** 値を使用すると、コマンド出力がディスク上のファイルにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="664a6-229">When using the **Drop** value, redirect the command output to a file on disk.</span></span>

<span data-ttu-id="664a6-230">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="664a6-230">Valid values are:</span></span>

- <span data-ttu-id="664a6-231">**Block** : 出力バッファーがいっぱいになると、バッファーがクリアされるまで実行が中断されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-231">**Block** : When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="664a6-232">**Drop** : 出力バッファーがいっぱいになると、実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-232">**Drop** : When the output buffer is full, execution continues.</span></span> <span data-ttu-id="664a6-233">新しい出力が保存されると、最も古い出力が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-233">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="664a6-234">**None** : 出力バッファリングモードが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="664a6-234">**None** : No output buffering mode is specified.</span></span> <span data-ttu-id="664a6-235">セッション構成の **OutputBufferingMode** プロパティの値は、切断されたセッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-235">The value of the **OutputBufferingMode** property of the session configuration is used for the disconnected session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Block
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="664a6-236">-Confirm</span><span class="sxs-lookup"><span data-stu-id="664a6-236">-Confirm</span></span>

<span data-ttu-id="664a6-237">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-237">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="664a6-238">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="664a6-238">-WhatIf</span></span>

<span data-ttu-id="664a6-239">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="664a6-239">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="664a6-240">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="664a6-240">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="664a6-241">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="664a6-241">CommonParameters</span></span>

<span data-ttu-id="664a6-242">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="664a6-242">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="664a6-243">詳細については、「[about_CommonParameters](./About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="664a6-243">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="664a6-244">入力</span><span class="sxs-lookup"><span data-stu-id="664a6-244">INPUTS</span></span>

### <span data-ttu-id="664a6-245">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="664a6-245">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="664a6-246">パイプを使用してセッションをにパイプすることができ `Disconnect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="664a6-246">You can pipe a session to `Disconnect-PSSession`.</span></span>

## <span data-ttu-id="664a6-247">出力</span><span class="sxs-lookup"><span data-stu-id="664a6-247">OUTPUTS</span></span>

### <span data-ttu-id="664a6-248">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="664a6-248">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="664a6-249">`Disconnect-PSSession` 切断されたセッションを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="664a6-249">`Disconnect-PSSession` returns an object that represents the session that it disconnected.</span></span>

## <span data-ttu-id="664a6-250">注</span><span class="sxs-lookup"><span data-stu-id="664a6-250">NOTES</span></span>

- <span data-ttu-id="664a6-251">`Disconnect-PSSession`コマンドレットは、ローカルコンピューターとリモートコンピューターで PowerShell 3.0 以降が実行されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="664a6-251">The `Disconnect-PSSession` cmdlet works only when the local and remote computers are running PowerShell 3.0 or later.</span></span>
- <span data-ttu-id="664a6-252">切断された `Disconnect-PSSession` セッションでコマンドレットを使用した場合、このコマンドはセッションに影響を与えず、エラーを生成しません。</span><span class="sxs-lookup"><span data-stu-id="664a6-252">If you use the `Disconnect-PSSession` cmdlet on a disconnected session, the command has no effect on the session and it does not generate errors.</span></span>
- <span data-ttu-id="664a6-253">対話型セキュリティ トークン ( **EnableNetworkAccess** パラメーターにより作成される) を使用しているループバック セッションが切断された場合には、そのセッションを作成したコンピューターからのみ再接続できます。</span><span class="sxs-lookup"><span data-stu-id="664a6-253">Disconnected loopback sessions with interactive security tokens (those created with the **EnableNetworkAccess** parameter) can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="664a6-254">この制約は、悪意のあるアクセスからコンピューターを保護するためのものです。</span><span class="sxs-lookup"><span data-stu-id="664a6-254">This restriction protects the computer from malicious access.</span></span>
- <span data-ttu-id="664a6-255">PSSession を切断した場合には、セッションの状態が **Disconnected** 、可用性が **None** に、それぞれ変更されます。</span><span class="sxs-lookup"><span data-stu-id="664a6-255">When you disconnect a PSSession, the session state is **Disconnected** and the availability is **None**.</span></span>

  <span data-ttu-id="664a6-256">**State** プロパティの値は、現在のセッションに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="664a6-256">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="664a6-257">そのため、 **Disconnected** という値は、PSSession が現在のセッションに接続されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="664a6-257">Therefore, a value of **Disconnected** means that the PSSession is not connected to the current session.</span></span> <span data-ttu-id="664a6-258">ただし、PSSession がすべてのセッションから切断されていることを意味するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="664a6-258">However, it does not mean that the PSSession is disconnected from all sessions.</span></span> <span data-ttu-id="664a6-259">別のセッションに接続されている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="664a6-259">It might be connected to a different session.</span></span> <span data-ttu-id="664a6-260">セッションに接続または再接続できるかどうかを確認するには、 **Availability** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="664a6-260">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="664a6-261">**Availability** の値が **None** の場合は、セッションに接続できることを示します。</span><span class="sxs-lookup"><span data-stu-id="664a6-261">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="664a6-262">**Busy** は、PSSession が別のセッションに接続されているため、PSSession に接続できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="664a6-262">A value of **Busy** indicates that you cannot connect to the PSSession because it is connected to another session.</span></span>

  <span data-ttu-id="664a6-263">セッションの **State** プロパティの値の詳細については、「 [RunspaceState Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="664a6-263">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span>

  <span data-ttu-id="664a6-264">セッションの **Availability** プロパティの値の詳細については、「 [RunspaceAvailability Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="664a6-264">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="664a6-265">関連リンク</span><span class="sxs-lookup"><span data-stu-id="664a6-265">RELATED LINKS</span></span>

[<span data-ttu-id="664a6-266">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="664a6-266">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="664a6-267">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="664a6-267">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="664a6-268">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="664a6-268">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="664a6-269">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="664a6-269">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="664a6-270">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="664a6-270">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="664a6-271">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="664a6-271">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="664a6-272">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="664a6-272">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="664a6-273">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="664a6-273">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="664a6-274">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="664a6-274">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="664a6-275">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="664a6-275">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="664a6-276">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="664a6-276">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="664a6-277">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="664a6-277">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="664a6-278">about_Remote</span><span class="sxs-lookup"><span data-stu-id="664a6-278">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="664a6-279">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="664a6-279">about_Remote_Disconnected_Sessions</span></span>](About/about_Remote_Disconnected_Sessions.md)
