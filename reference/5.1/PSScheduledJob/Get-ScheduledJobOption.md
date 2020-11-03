---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213427"
---
# <span data-ttu-id="14ee7-103">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="14ee7-103">Get-ScheduledJobOption</span></span>

## <span data-ttu-id="14ee7-104">概要</span><span class="sxs-lookup"><span data-stu-id="14ee7-104">SYNOPSIS</span></span>
<span data-ttu-id="14ee7-105">スケジュールされたジョブのジョブ オプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-105">Gets the job options of scheduled jobs.</span></span>

## <span data-ttu-id="14ee7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14ee7-106">SYNTAX</span></span>

### <span data-ttu-id="14ee7-107">JobDefinition (既定値)</span><span class="sxs-lookup"><span data-stu-id="14ee7-107">JobDefinition (Default)</span></span>

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="14ee7-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="14ee7-108">JobDefinitionId</span></span>

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="14ee7-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="14ee7-109">JobDefinitionName</span></span>

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="14ee7-110">Description</span><span class="sxs-lookup"><span data-stu-id="14ee7-110">DESCRIPTION</span></span>
<span data-ttu-id="14ee7-111">**Get-scheduledjoboption** コマンドレットは、スケジュールされたジョブのジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-111">The **Get-ScheduledJobOption** cmdlet gets the job options of scheduled jobs.</span></span>
<span data-ttu-id="14ee7-112">このコマンドを使用すると、ジョブ オプションを確認することや、パイプを使用してジョブ オプションを他のコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="14ee7-112">You can use this command to examine the job options or to pipe the job options to other cmdlets.</span></span>

<span data-ttu-id="14ee7-113">ジョブ オプションは、スケジュールされたジョブの一部であり、ディスクに単独で保存されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="14ee7-113">Job options are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="14ee7-114">スケジュールされたジョブのジョブ オプションを取得するには、スケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-114">To get the job options of a scheduled job, specify the scheduled job.</span></span>

<span data-ttu-id="14ee7-115">**Get-ScheduledJobOption** コマンドレットのパラメーターを使用して、スケジュールされたジョブを特定します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-115">Use the parameters of the **Get-ScheduledJobOption** cmdlet to identify the scheduled job.</span></span>
<span data-ttu-id="14ee7-116">スケジュールされたジョブは、名前または識別番号で識別できます。または、Get-ScheduledJob コマンドレットによって返されたものなどの **Scheduledjob** オブジェクトを **get-scheduledjoboption** に入力するか、パイプを使用して識別することができます。</span><span class="sxs-lookup"><span data-stu-id="14ee7-116">You can identify scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-ScheduledJobOption** .</span></span>

<span data-ttu-id="14ee7-117">**Get-scheduledjoboption** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="14ee7-117">**Get-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="14ee7-118">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ee7-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="14ee7-119">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ee7-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="14ee7-120">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="14ee7-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="14ee7-121">例</span><span class="sxs-lookup"><span data-stu-id="14ee7-121">EXAMPLES</span></span>

### <span data-ttu-id="14ee7-122">例 1: ジョブオプションを取得する</span><span class="sxs-lookup"><span data-stu-id="14ee7-122">Example 1: Get job options</span></span>

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : False

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="14ee7-123">このコマンドは、名前にバックアップが含まれるスケジュールされたジョブのジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-123">This command gets the job options of scheduled jobs that have BackUp in their names.</span></span>
<span data-ttu-id="14ee7-124">結果には、 **Get-ScheduledJobOption** から返されたジョブ オプション オブジェクトが示されています。</span><span class="sxs-lookup"><span data-stu-id="14ee7-124">The results show the job options object that **Get-ScheduledJobOption** returned.</span></span>

### <span data-ttu-id="14ee7-125">例 2: すべてのジョブオプションを取得する</span><span class="sxs-lookup"><span data-stu-id="14ee7-125">Example 2: Get all job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

<span data-ttu-id="14ee7-126">このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブのジョブ オプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-126">This command gets the job options of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="14ee7-127">Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-127">It uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="14ee7-128">パイプライン演算子 (|) によって、スケジュールされたジョブが **get-scheduledjoboption** コマンドレットに送信されます。このコマンドレットは、スケジュールされた各ジョブのジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-128">A pipeline operator (|) sends the scheduled jobs to the **Get-ScheduledJobOption** cmdlet, which gets the job options of each scheduled job.</span></span>

### <span data-ttu-id="14ee7-129">例 3: 選択したジョブオプションを取得する</span><span class="sxs-lookup"><span data-stu-id="14ee7-129">Example 3: Get selected job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

<span data-ttu-id="14ee7-130">この例では、特定の値でジョブ オプション オブジェクトを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-130">This example shows how to find job options object with particular values.</span></span>

<span data-ttu-id="14ee7-131">最初のコマンドは、RunElevated されたプロパティの値が $True で、Runelevated Network プロパティの値が $False であるジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-131">The first command gets job options in which the RunElevated property has a value of $True and the RunWithoutNetwork property has a value of $False.</span></span>
<span data-ttu-id="14ee7-132">出力には、選択された **JobOptions** オブジェクトが示されます。</span><span class="sxs-lookup"><span data-stu-id="14ee7-132">The output shows the **JobOptions** object that was selected.</span></span>

### <span data-ttu-id="14ee7-133">例 4: ジョブオプションを使用して新しいジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="14ee7-133">Example 4: Use job options to create a new job</span></span>

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

<span data-ttu-id="14ee7-134">この例では、スケジュールされた新しいジョブで Get-ScheduledJobOption ジョブオプションを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-134">This example shows how to use the job options that Get-ScheduledJobOption gets in a new scheduled job.</span></span>

<span data-ttu-id="14ee7-135">最初のコマンドは、 **get-scheduledjoboption** を使用して、スケジュールされたジョブ BackupTestLogs のジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-135">The first command uses **Get-ScheduledJobOption** to get the jobs options of the BackupTestLogs scheduled job.</span></span>
<span data-ttu-id="14ee7-136">このコマンドは、オプションを $Opts 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-136">The command saves the options in the $Opts variable.</span></span>

<span data-ttu-id="14ee7-137">2番目のコマンドは、Register-ScheduledJob コマンドレットを使用して、スケジュールされた新しいジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-137">The second command uses Register-ScheduledJob cmdlet to create a new scheduled job.</span></span>
<span data-ttu-id="14ee7-138">*ScheduledJobOption* パラメーターの値は、$Opts 変数内のオプション オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="14ee7-138">The value of the *ScheduledJobOption* parameter is the options object in the $Opts variable.</span></span>

### <span data-ttu-id="14ee7-139">例 5: リモートコンピューターからジョブオプションを取得する</span><span class="sxs-lookup"><span data-stu-id="14ee7-139">Example 5: Get job options from a remote computer</span></span>

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

<span data-ttu-id="14ee7-140">このコマンドは、Invoke-Command コマンドレットを使用して、Srv01 コンピューター上の DataDemon ジョブのスケジュールされたジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-140">This command uses the Invoke-Command cmdlet to get the scheduled job options of the DataDemon job on the Srv01 computer.</span></span>
<span data-ttu-id="14ee7-141">このコマンドは、オプションを $O 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-141">The command saves the options in the $O variable.</span></span>

## <span data-ttu-id="14ee7-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14ee7-142">PARAMETERS</span></span>

### <span data-ttu-id="14ee7-143">-Id</span><span class="sxs-lookup"><span data-stu-id="14ee7-143">-Id</span></span>
<span data-ttu-id="14ee7-144">スケジュールされたジョブの識別番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-144">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="14ee7-145">**Get-ScheduledJobOption** は、指定されたスケジュールされたジョブのジョブ オプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-145">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>

<span data-ttu-id="14ee7-146">ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの識別番号を取得するには、Get-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-146">To get the identification numbers of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14ee7-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="14ee7-147">-InputObject</span></span>
<span data-ttu-id="14ee7-148">スケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-148">Specifies a scheduled job.</span></span>
<span data-ttu-id="14ee7-149">**Scheduledjob** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **scheduledjob** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-149">Enter a variable that contains a **ScheduledJob** object or type a command or expression that gets a **ScheduledJob** object, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="14ee7-150">パイプを使用して **ScheduledJob** オブジェクトを **Get-ScheduledJobOption** に渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="14ee7-150">You can also pipe a **ScheduledJob** object to **Get-ScheduledJobOption** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="14ee7-151">-Name</span><span class="sxs-lookup"><span data-stu-id="14ee7-151">-Name</span></span>
<span data-ttu-id="14ee7-152">スケジュールされたジョブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-152">Specifies the names of scheduled jobs.</span></span>
<span data-ttu-id="14ee7-153">**Get-ScheduledJobOption** は、指定されたスケジュールされたジョブのジョブ オプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-153">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>
<span data-ttu-id="14ee7-154">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="14ee7-154">Wildcards are supported.</span></span>

<span data-ttu-id="14ee7-155">ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの名前を取得するには、Get-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="14ee7-155">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="14ee7-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="14ee7-156">CommonParameters</span></span>
<span data-ttu-id="14ee7-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="14ee7-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14ee7-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ee7-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="14ee7-159">入力</span><span class="sxs-lookup"><span data-stu-id="14ee7-159">INPUTS</span></span>

### <span data-ttu-id="14ee7-160">ScheduledJobDefinition (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="14ee7-160">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="14ee7-161">スケジュールされたジョブを Get-ScheduledJob から **get-scheduledjoboption** にパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="14ee7-161">You can pipe a scheduled job from Get-ScheduledJob to **Get-ScheduledJobOption** .</span></span>

## <span data-ttu-id="14ee7-162">出力</span><span class="sxs-lookup"><span data-stu-id="14ee7-162">OUTPUTS</span></span>

### <span data-ttu-id="14ee7-163">ScheduledJobOptions (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="14ee7-163">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="14ee7-164">注</span><span class="sxs-lookup"><span data-stu-id="14ee7-164">NOTES</span></span>

## <span data-ttu-id="14ee7-165">関連リンク</span><span class="sxs-lookup"><span data-stu-id="14ee7-165">RELATED LINKS</span></span>

[<span data-ttu-id="14ee7-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="14ee7-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="14ee7-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="14ee7-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="14ee7-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="14ee7-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="14ee7-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="14ee7-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="14ee7-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="14ee7-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="14ee7-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="14ee7-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="14ee7-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="14ee7-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="14ee7-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="14ee7-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="14ee7-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="14ee7-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="14ee7-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="14ee7-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="14ee7-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="14ee7-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="14ee7-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="14ee7-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="14ee7-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="14ee7-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="14ee7-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="14ee7-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="14ee7-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="14ee7-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="14ee7-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="14ee7-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
