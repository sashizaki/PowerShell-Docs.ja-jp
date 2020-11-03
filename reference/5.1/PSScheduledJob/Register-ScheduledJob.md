---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213416"
---
# <span data-ttu-id="066d0-103">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="066d0-103">Register-ScheduledJob</span></span>

## <span data-ttu-id="066d0-104">概要</span><span class="sxs-lookup"><span data-stu-id="066d0-104">SYNOPSIS</span></span>
<span data-ttu-id="066d0-105">スケジュールされたジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-105">Creates a scheduled job.</span></span>

## <span data-ttu-id="066d0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="066d0-106">SYNTAX</span></span>

### <span data-ttu-id="066d0-107">ScriptBlock (既定値)</span><span class="sxs-lookup"><span data-stu-id="066d0-107">ScriptBlock (Default)</span></span>

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="066d0-108">FilePath</span><span class="sxs-lookup"><span data-stu-id="066d0-108">FilePath</span></span>

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="066d0-109">Description</span><span class="sxs-lookup"><span data-stu-id="066d0-109">DESCRIPTION</span></span>

<span data-ttu-id="066d0-110">コマンドレットでは、 `Register-ScheduledJob` スケジュールされたジョブをローカルコンピューター上に作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-110">The `Register-ScheduledJob` cmdlet creates scheduled jobs on the local computer.</span></span>

<span data-ttu-id="066d0-111">スケジュールされたジョブは、Windows PowerShell のバックグラウンドジョブであり、一度だけまたは定期的なスケジュールで自動的に開始できます。</span><span class="sxs-lookup"><span data-stu-id="066d0-111">A scheduled job is a Windows PowerShell background job that can be started automatically on a one-time or recurring schedule.</span></span> <span data-ttu-id="066d0-112">スケジュールされたジョブはディスクに保存され、タスクスケジューラに登録されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-112">Scheduled jobs are stored on disk and registered in Task Scheduler.</span></span>
<span data-ttu-id="066d0-113">ジョブは、タスクスケジューラまたは Windows PowerShell のスケジュールされたジョブコマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="066d0-113">The jobs can be managed in Task Scheduler or by using the Scheduled Job cmdlets in Windows PowerShell.</span></span>

<span data-ttu-id="066d0-114">スケジュールされたジョブが開始されると、スケジュールされたジョブのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-114">When a scheduled job starts, it creates an instance of the scheduled job.</span></span> <span data-ttu-id="066d0-115">スケジュールされたジョブのインスタンスは、結果がディスクに保存される点を除き、Windows PowerShell のバックグラウンド ジョブと同じです。</span><span class="sxs-lookup"><span data-stu-id="066d0-115">Scheduled job instances are identical to Windows PowerShell background jobs, except that the results are saved on disk.</span></span> <span data-ttu-id="066d0-116">、、などのジョブコマンドレットを使用して、 `Start-Job` `Get-Job` `Receive-Job` ジョブインスタンスの開始、表示、および結果の取得を行います。</span><span class="sxs-lookup"><span data-stu-id="066d0-116">Use the Job cmdlets, such as `Start-Job`, `Get-Job`, and `Receive-Job` to start, view, and get the results of the job instances.</span></span>

<span data-ttu-id="066d0-117">を使用して `Register-ScheduledJob` 、スケジュールされた新しいジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-117">Use `Register-ScheduledJob` to create a new scheduled job.</span></span> <span data-ttu-id="066d0-118">スケジュールされたジョブで実行するコマンドを指定するには、 **ScriptBlock** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-118">To specify the commands that the scheduled job runs, use the **ScriptBlock** parameter.</span></span> <span data-ttu-id="066d0-119">ジョブによって実行されるスクリプトを指定するには、 **FilePath** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-119">To specify a script that the job runs, use the **FilePath** parameter.</span></span>

<span data-ttu-id="066d0-120">Windows PowerShell-スケジュールされたジョブでは、スケジュールされたタスクに使用タスクスケジューラ同じジョブトリガーとジョブオプションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-120">Windows PowerShell-scheduled jobs use the same job triggers and job options that Task Scheduler uses for scheduled tasks.</span></span>

<span data-ttu-id="066d0-121">の **Trigger** パラメーターでは `Register-ScheduledJob` 、ジョブを開始するジョブトリガーを1つ以上追加します。</span><span class="sxs-lookup"><span data-stu-id="066d0-121">The **Trigger** parameter of `Register-ScheduledJob` adds one or more job triggers that start the job.</span></span> <span data-ttu-id="066d0-122">**Trigger** パラメーターは省略可能であるため、スケジュールされたジョブを作成するときにトリガーを追加し、後でジョブトリガーを追加して、 **runnow** パラメーターを追加してジョブをすぐに開始します。また、コマンドレットを使用して、スケジュールされていない `Start-Job` ジョブを他のジョブのテンプレートとして保存します。</span><span class="sxs-lookup"><span data-stu-id="066d0-122">The **Trigger** parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the **RunNow** parameter to start the job immediately, use the `Start-Job` cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="066d0-123">**Options** パラメーターを使用すると、スケジュールされたジョブのオプション設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="066d0-123">The **Options** parameter lets you customize the options settings for the scheduled job.</span></span> <span data-ttu-id="066d0-124">**Options** パラメーターはオプションであるため、スケジュールされたジョブを作成するときにジョブオプションを設定することも、いつでも変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="066d0-124">The **Options** parameter is optional, so you can set job options when you create the scheduled job or change them at any time.</span></span> <span data-ttu-id="066d0-125">ジョブ オプションの設定によっては、スケジュールされたジョブが実行されない場合があるため、ジョブ オプションを確認し、慎重に設定してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-125">Because job option settings can prevent the scheduled job from running, review the job options and set them carefully.</span></span>

<span data-ttu-id="066d0-126">`Register-ScheduledJob` は、Windows PowerShell に含まれている **Psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="066d0-126">`Register-ScheduledJob` is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="066d0-127">スケジュールされたジョブの詳細については、 **Psscheduledjob** モジュールの概要に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-127">For more information about Scheduled Jobs, see the About articles in the **PSScheduledJob** module.</span></span>
<span data-ttu-id="066d0-128">**Psscheduledjob** モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または [about_Scheduled_Jobs](./about/about_scheduled_jobs.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-128">Import the **PSScheduledJob** module and then type: `Get-Help about_Scheduled*` or see [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).</span></span>

<span data-ttu-id="066d0-129">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="066d0-129">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="066d0-130">例</span><span class="sxs-lookup"><span data-stu-id="066d0-130">EXAMPLES</span></span>

### <span data-ttu-id="066d0-131">例 1: スケジュールされたジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="066d0-131">Example 1: Create a scheduled job</span></span>

<span data-ttu-id="066d0-132">この例では、ローカルコンピューター上にスケジュールされたジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-132">This example creates a scheduled job on the local computer.</span></span>

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

<span data-ttu-id="066d0-133">`Register-ScheduledJob`**Name** パラメーターを使用して、スケジュールされたジョブの **アーカイブスクリプト** を作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-133">`Register-ScheduledJob` uses the **Name** parameter to create the **Archive-Scripts** scheduled job.</span></span>
<span data-ttu-id="066d0-134">**ScriptBlock** `Get-ChildItem` ファイルのディレクトリを再帰的に検索する ScriptBlock パラメーターが実行され `$home` `.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-134">The **ScriptBlock** parameter runs `Get-ChildItem` that searches the `$home` directory recursively for `.ps1` files.</span></span> <span data-ttu-id="066d0-135">`Copy-Item`コマンドレットは、 **Destination** パラメーターで指定されたディレクトリにファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="066d0-135">The `Copy-Item` cmdlet copies the files to a directory specified by the **Destination** parameter.</span></span>

<span data-ttu-id="066d0-136">スケジュールされたジョブにはトリガーが含まれていないため、自動的に開始されません。</span><span class="sxs-lookup"><span data-stu-id="066d0-136">Because the scheduled job doesn't contain a trigger, it's not started automatically.</span></span> <span data-ttu-id="066d0-137">ジョブトリガーをに追加するには `Add-JobTrigger` 、コマンドレットを使用して、 `Start-Job` 必要に応じてジョブを開始するか、スケジュールされたジョブを他のスケジュールされたジョブのテンプレートとして使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-137">You can add job triggers with `Add-JobTrigger`, use the `Start-Job` cmdlet to start the job on demand, or use the scheduled job as a template for other scheduled jobs.</span></span>

### <span data-ttu-id="066d0-138">例 2: トリガーとカスタムオプションを使用してスケジュールされたジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="066d0-138">Example 2: Create a scheduled job with triggers and custom options</span></span>

<span data-ttu-id="066d0-139">この例では、ジョブ トリガーとカスタムのジョブ オプションを指定して、スケジュールされたジョブを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="066d0-139">This example shows how to create a scheduled job that has a job trigger and custom job options.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

<span data-ttu-id="066d0-140">変数には、 `$O` コマンドレットによって作成されたジョブオプションオブジェクトが格納 `New-ScheduledJobOption` されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-140">The `$O` variable stores the job option object that the `New-ScheduledJobOption` cmdlet created.</span></span> <span data-ttu-id="066d0-141">オプションは、コンピューターがアイドル状態でない場合でもスケジュールされたジョブを開始し、必要に応じて、ジョブの複数のインスタンスを連続して実行できるようにコンピューターをスリープ解除します。</span><span class="sxs-lookup"><span data-stu-id="066d0-141">The options start the scheduled job even if the computer isn't idle, wakes the computer to run the job, if necessary, and allows multiple instances of the job to run in a series.</span></span>

<span data-ttu-id="066d0-142">変数は、コマンドレットの結果を格納して、 `$T` `New-JobTrigger` 月曜日の午後9:00 にジョブを開始するジョブトリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-142">The `$T` variable stores the result from the `New-JobTrigger` cmdlet to create job trigger that starts a job every other Monday at 9:00 PM.</span></span>

<span data-ttu-id="066d0-143">変数には、 `$path` スクリプトファイルへのパスが格納され `UpdateVersion.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-143">The `$path` variable stores the path to the `UpdateVersion.ps1` script file.</span></span>

<span data-ttu-id="066d0-144">`Register-ScheduledJob` では、 **名前** パラメーターを使用して、スケジュールされたジョブ **updateversion** を作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-144">`Register-ScheduledJob` uses the **Name** paramter to create the **UpdateVersion** scheduled job.</span></span>
<span data-ttu-id="066d0-145">**FilePath** パラメーターでは、を使用して、 `$path` ジョブを実行するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-145">The **FilePath** parameter uses `$path` to specify the script that the job runs.</span></span> <span data-ttu-id="066d0-146">**Get-scheduledjoboption** パラメーターは、に格納されているジョブオプションを使用し `$O` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-146">The **ScheduledJobOption** parameter uses the job options stored in `$O`.</span></span> <span data-ttu-id="066d0-147">**トリガー** パラメーターは、に格納されているジョブトリガーを使用し `$T` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-147">The **Trigger** parameter uses the job triggers stored in `$T`.</span></span>

### <span data-ttu-id="066d0-148">例 3: ハッシュテーブルを使用してトリガーとスケジュールされたジョブのオプションを指定する</span><span class="sxs-lookup"><span data-stu-id="066d0-148">Example 3: Use hash tables to specify a trigger and scheduled job options</span></span>

<span data-ttu-id="066d0-149">この例は、例2のコマンドと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="066d0-149">This example has the same effect as the command in Example 2.</span></span> <span data-ttu-id="066d0-150">この例では、ハッシュテーブルを使用して **トリガー** および **get-scheduledjoboption** パラメーターの値を指定する、スケジュールされたジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-150">It creates a scheduled job, using hash tables to specify the values of the **Trigger** and **ScheduledJobOption** parameters.</span></span> <span data-ttu-id="066d0-151">`$O` `$T` 例2で定義されているとの変数は、ハッシュテーブルに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="066d0-151">The `$O` and `$T`variables defined in Example 2 are replaced with hash tables.</span></span>

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### <span data-ttu-id="066d0-152">例 4: リモートコンピューターにスケジュールされたジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="066d0-152">Example 4: Create scheduled jobs on remote computers</span></span>

<span data-ttu-id="066d0-153">この例では、スケジュールされたジョブ **energydata.ps1** を複数のリモートコンピューター上に作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-153">In this example, the **EnergyData** scheduled job is created on multiple remote computers.</span></span> <span data-ttu-id="066d0-154">スケジュールされたジョブは、生データを収集し、リモートコンピューター上の実行中のログに保存するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="066d0-154">The scheduled job runs a script that gathers raw data and saves it in a running log on the remote computer.</span></span>

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

<span data-ttu-id="066d0-155">変数は、 `$Cred` スケジュールされたジョブを作成するアクセス許可を持つユーザーのために、 **PSCredential** オブジェクトに資格情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="066d0-155">The `$Cred` variable stores credentials in a **PSCredential** object for a user with permissions to create scheduled jobs.</span></span> <span data-ttu-id="066d0-156">変数には、 `$O` で作成されたジョブオプションが格納され `New-ScheduledJobOption` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-156">The `$O` variable stores the job options created with `New-ScheduledJobOption`.</span></span> <span data-ttu-id="066d0-157">変数は、 `$T` で作成されたジョブトリガーを格納し `New-JobTrigger` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-157">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="066d0-158">コマンドレットでは、 `Invoke-Command` **ComputerName** パラメーターを使用して、ファイルからサーバー名の一覧を取得し `Servers.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-158">The `Invoke-Command` cmdlet uses the **ComputerName** parameter to get a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="066d0-159">**Credential** パラメーターは、に格納されている資格情報オブジェクトを取得し `$Cred` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-159">The **Credential** parameter gets the credential object stored in `$Cred`.</span></span>
<span data-ttu-id="066d0-160">**ScriptBlock** パラメーターは、 `Register-ScheduledJob` ファイル内のコンピューターでコマンドを実行し `Servers.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-160">The **ScriptBlock** parameter runs a `Register-ScheduledJob` command on the computers in the `Servers.txt` file.</span></span>

<span data-ttu-id="066d0-161">のパラメーターは、で定義されてい `Register-ScheduledJob` `$params` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-161">The parameters for `Register-ScheduledJob` are defined by `$params`.</span></span> <span data-ttu-id="066d0-162">**Name** パラメーターは、各リモートコンピューターでジョブの名前を **energydata.ps1** に指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-162">The **Name** parameters specifies the job is named **Get-EnergyData** on each remote computer.</span></span> <span data-ttu-id="066d0-163">**FilePath** は、スクリプトの場所を指定し `EnergyData.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-163">**FilePath** provides the location of the `EnergyData.ps1` script.</span></span> <span data-ttu-id="066d0-164">このスクリプトは、参加しているすべてのコンピューターで使用できるファイルサーバーにあります。ジョブは、のジョブトリガーによって指定されたスケジュールと、のジョブオプションで実行され `$T` `$O` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-164">The script is located on a file server that is available to all participating computers.The job runs on the schedule specified by the job triggers in `$T` and the job options in `$O`.</span></span>

<span data-ttu-id="066d0-165">この `Register-ScheduledJob @params` コマンドは、スクリプトブロックのパラメーターを使用して、スケジュールされたジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-165">The `Register-ScheduledJob @params` command creates the scheduled job with the parameters from the script block.</span></span>

### <span data-ttu-id="066d0-166">例 5: リモートコンピューターでスクリプトを実行するスケジュールされたジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="066d0-166">Example 5: Create a scheduled job that runs a script on remote computers</span></span>

<span data-ttu-id="066d0-167">この例では、ローカルコンピューター上にスケジュールされたジョブ **CollectEnergyData** を作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-167">This example creates the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="066d0-168">このジョブは、複数のリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-168">The job runs on multiple remote computers.</span></span>

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

<span data-ttu-id="066d0-169">変数には、 `$Admin` **PSCredential** オブジェクトでコマンドを実行するアクセス許可を持つユーザーの資格情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-169">The `$Admin` variable stores credentials for a user with permissions to run the commands in a **PSCredential** object.</span></span> <span data-ttu-id="066d0-170">変数は、 `$T` で作成されたジョブトリガーを格納し `New-JobTrigger` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-170">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="066d0-171">この `Register-ScheduledJob` コマンドレットでは、 **Name** パラメーターを使用して、ローカルコンピューター上のスケジュールされたジョブ **CollectEnergyData** を作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-171">The `Register-ScheduledJob` cmdlet uses the **Name** parameter to create the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="066d0-172">**Trigger** パラメーターはのジョブトリガーを指定し、 `$T` **maxresultcount** パラメーターは保存される結果の数を99に増やします。</span><span class="sxs-lookup"><span data-stu-id="066d0-172">The **Trigger** parameter specifies the job triggers in `$T` and the **MaxResultCount** parameter increases the number of saved results to 99.</span></span>

<span data-ttu-id="066d0-173">**ScriptBlock** パラメーターは、でパラメーターを定義し `Invoke-Command` `$params` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-173">The **ScriptBlock** parameter defines the `Invoke-Command` parameters with `$params`.</span></span> <span data-ttu-id="066d0-174">**AsJob** パラメーターは、 `Energydata.ps1` スクリプトがリモートコンピューター上で実行されている場合でも、ローカルコンピューター上にバックグラウンドジョブオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-174">The **AsJob** parameter creates the background job object on the local computer, even though the `Energydata.ps1` script runs on the remote computers.</span></span> <span data-ttu-id="066d0-175">**ComputerName** パラメーターは、ファイルからサーバー名の一覧を取得し `Servers.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-175">The **ComputerName** parameter gets a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="066d0-176">**Credential** パラメーターは、リモートコンピューターでスクリプトを実行する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-176">The **Credential** parameter specifies a user account that has permission to run scripts on the remote computers.</span></span> <span data-ttu-id="066d0-177">また、 **認証** パラメーターでは、委任された資格情報を許可する **CredSSP** の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-177">And, the **Authentication** parameter specifies a value of **CredSSP** to allow delegated credentials.</span></span>

<span data-ttu-id="066d0-178">は、 `Invoke-Command @params` スクリプトブロックのパラメーターを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="066d0-178">The `Invoke-Command @params` runs the command with the parameters from the script block.</span></span>

## <span data-ttu-id="066d0-179">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="066d0-179">PARAMETERS</span></span>

### <span data-ttu-id="066d0-180">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="066d0-180">-ArgumentList</span></span>

<span data-ttu-id="066d0-181">**FilePath** パラメーターで指定されたスクリプトのパラメーター、または **ScriptBlock** パラメーターで指定されたコマンドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-181">Specifies values for the parameters of the script that is specified by the **FilePath** parameter or for the command that is specified by the **ScriptBlock** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-182">-認証</span><span class="sxs-lookup"><span data-stu-id="066d0-182">-Authentication</span></span>

<span data-ttu-id="066d0-183">ユーザーの資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-183">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="066d0-184">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="066d0-184">The default value is Default.</span></span>

<span data-ttu-id="066d0-185">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="066d0-185">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="066d0-186">Default</span><span class="sxs-lookup"><span data-stu-id="066d0-186">Default</span></span>
- <span data-ttu-id="066d0-187">Basic</span><span class="sxs-lookup"><span data-stu-id="066d0-187">Basic</span></span>
- <span data-ttu-id="066d0-188">Credssp</span><span class="sxs-lookup"><span data-stu-id="066d0-188">Credssp</span></span>
- <span data-ttu-id="066d0-189">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="066d0-189">Digest</span></span>
- <span data-ttu-id="066d0-190">Kerberos</span><span class="sxs-lookup"><span data-stu-id="066d0-190">Kerberos</span></span>
- <span data-ttu-id="066d0-191">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="066d0-191">Negotiate</span></span>
- <span data-ttu-id="066d0-192">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="066d0-192">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="066d0-193">このパラメーターの値の詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-193">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="066d0-194">ユーザーの資格情報が認証対象のリモート コンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモート ネットワーク共有にアクセスする場合など、複数のリソースの認証を必要とするコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="066d0-194">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="066d0-195">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="066d0-195">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="066d0-196">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="066d0-196">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="066d0-197">-Confirm</span></span>

<span data-ttu-id="066d0-198">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-198">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="066d0-199">-Credential</span><span class="sxs-lookup"><span data-stu-id="066d0-199">-Credential</span></span>

<span data-ttu-id="066d0-200">スケジュールされたジョブを実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-200">Specifies a user account that has permission to run the scheduled job.</span></span> <span data-ttu-id="066d0-201">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="066d0-201">The default is the current user.</span></span>

<span data-ttu-id="066d0-202">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットのような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-202">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="066d0-203">ユーザー名のみを入力した場合は、パスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="066d0-203">If you enter only a user name, you're prompted for a password.</span></span>

<span data-ttu-id="066d0-204">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-204">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="066d0-205">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-205">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-206">-FilePath</span><span class="sxs-lookup"><span data-stu-id="066d0-206">-FilePath</span></span>

<span data-ttu-id="066d0-207">スケジュールされたジョブで実行するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-207">Specifies a script that the scheduled job runs.</span></span> <span data-ttu-id="066d0-208">ローカルコンピューター上のファイルへのパスを入力し `.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-208">Enter the path to a `.ps1` file on the local computer.</span></span> <span data-ttu-id="066d0-209">スクリプト パラメーターの既定値を指定するには、 **ArgumentList** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-209">To specify default values for the script parameters, use the **ArgumentList** parameter.</span></span>
<span data-ttu-id="066d0-210">すべての `Register-ScheduledJob` コマンドで **ScriptBlock** パラメーターまたは **FilePath** パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="066d0-210">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-211">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="066d0-211">-InitializationScript</span></span>

<span data-ttu-id="066d0-212">Windows PowerShell スクリプト () への完全修飾パスを指定し `.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-212">Specifies the fully qualified path to a Windows PowerShell script (`.ps1`).</span></span> <span data-ttu-id="066d0-213">初期化スクリプトは、 **ScriptBlock** パラメーターで指定されたコマンドまたは **FilePath** パラメーターで指定されスクリプトの前に、バックグラウンド ジョブ用に作成されたセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-213">The initialization script runs in the session that is created for the background job before the commands that are specified by the **ScriptBlock** parameter or the script that is specified by the **FilePath** parameter.</span></span> <span data-ttu-id="066d0-214">初期化スクリプトを使用すると、ファイル、関数、またはエイリアスの追加、ディレクトリの作成、前提条件の確認など、セッションを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="066d0-214">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="066d0-215">プライマリ ジョブ コマンドを実行するスクリプトを指定するには、 **FilePath** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-215">To specify a script that runs the primary job commands, use the **FilePath** parameter.</span></span>

<span data-ttu-id="066d0-216">初期化スクリプトによってエラーが生成された場合、未終了エラーでも、スケジュールされたジョブの現在のインスタンスは実行されず、状態は **Failed** になります。</span><span class="sxs-lookup"><span data-stu-id="066d0-216">If the initialization script generates an error, even a non-terminating error, the current instance of the scheduled job doesn't run and its status is **Failed** .</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-217">-MaxResultCount</span><span class="sxs-lookup"><span data-stu-id="066d0-217">-MaxResultCount</span></span>

<span data-ttu-id="066d0-218">スケジュールされたジョブに対して保持されるジョブの結果のエントリ数を指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-218">Specifies how many job result entries are maintained for the scheduled job.</span></span> <span data-ttu-id="066d0-219">既定値は 32 です。</span><span class="sxs-lookup"><span data-stu-id="066d0-219">The default value is 32.</span></span>

<span data-ttu-id="066d0-220">Windows PowerShell では、スケジュールされたジョブのトリガーされた各インスタンスの実行履歴と結果をディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="066d0-220">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span> <span data-ttu-id="066d0-221">このパラメーターの値により、このスケジュールされたジョブに対して保存されるジョブ インスタンスの結果の数が決まります。</span><span class="sxs-lookup"><span data-stu-id="066d0-221">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span> <span data-ttu-id="066d0-222">ジョブ インスタンスの結果の数がこの値を超えた場合は、最新のジョブ インスタンスの結果を保存するために、最も古いジョブ インスタンスの結果が削除されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-222">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="066d0-223">ジョブの実行履歴とジョブの結果は、 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span><span class="sxs-lookup"><span data-stu-id="066d0-223">The job execution history and job results are saved in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span></span>
<span data-ttu-id="066d0-224">ジョブが作成されるコンピューター上のディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="066d0-224">directories on the computer on which the job is created.</span></span> <span data-ttu-id="066d0-225">実行履歴を表示するには、 `Get-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-225">To see the execution history, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="066d0-226">ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-226">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="066d0-227">**MaxResultCount** パラメーターは、スケジュールされたジョブの ExecutionHistoryLength プロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-227">The **MaxResultCount** parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="066d0-228">現在の実行履歴とジョブの結果を削除するには、コマンドレットの **ClearExecutionHistory** パラメーターを使用し `Set-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-228">To delete the current execution history and job results, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span>

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

### <span data-ttu-id="066d0-229">-Name</span><span class="sxs-lookup"><span data-stu-id="066d0-229">-Name</span></span>

<span data-ttu-id="066d0-230">スケジュールされたジョブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-230">Specifies a name for the scheduled job.</span></span> <span data-ttu-id="066d0-231">この名前は、スケジュールされたジョブの開始されたすべてのインスタンスにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-231">The name is also used for all started instances of the scheduled job.</span></span> <span data-ttu-id="066d0-232">名前は、コンピューター上で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="066d0-232">The name must be unique on the computer.</span></span> <span data-ttu-id="066d0-233">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="066d0-233">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-234">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="066d0-234">-RunAs32</span></span>

<span data-ttu-id="066d0-235">スケジュールされたジョブを 32 ビット プロセスで実行します。</span><span class="sxs-lookup"><span data-stu-id="066d0-235">Runs the scheduled job in a 32-bit process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-236">-RunEvery</span><span class="sxs-lookup"><span data-stu-id="066d0-236">-RunEvery</span></span>

<span data-ttu-id="066d0-237">ジョブを実行する頻度を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-237">Used to specify how often to run the job.</span></span> <span data-ttu-id="066d0-238">たとえば、15分ごとにジョブを実行するには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-238">For example, use this option to run a job every 15 minutes.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-239">-RunNow</span><span class="sxs-lookup"><span data-stu-id="066d0-239">-RunNow</span></span>

<span data-ttu-id="066d0-240">コマンドレットが実行されるとすぐに、ジョブを直ちに開始し `Register-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-240">Starts a job immediately, as soon as the `Register-ScheduledJob` cmdlet is run.</span></span> <span data-ttu-id="066d0-241">このパラメーターを指定すると、登録後すぐに Windows PowerShell スクリプトを実行するためにタスクスケジューラをトリガーする必要がなくなり、開始日時を指定するトリガーをユーザーが作成する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="066d0-241">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and doesn't require users to create a trigger that specifies a starting date and time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-242">-Get-scheduledjoboption</span><span class="sxs-lookup"><span data-stu-id="066d0-242">-ScheduledJobOption</span></span>

<span data-ttu-id="066d0-243">スケジュールされたジョブのオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-243">Sets options for the scheduled job.</span></span> <span data-ttu-id="066d0-244">コマンドレットを使用して作成したオブジェクトやハッシュテーブルの値など、 **ScheduledJobOptions** オブジェクトを入力し `New-ScheduledJobOption` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-244">Enter a **ScheduledJobOptions** object, such as one that you create by using the `New-ScheduledJobOption` cmdlet, or a hash table value.</span></span>

<span data-ttu-id="066d0-245">スケジュールジョブを登録するとき、 `Set-ScheduledJobOption` またはコマンドレットまたはコマンドレットを使用してオプションを変更するときに、スケジュールされたジョブのオプションを設定でき `Set-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-245">You can set options for a scheduled job when you register the schedule job or use the `Set-ScheduledJobOption` or `Set-ScheduledJob` cmdlets to change the options.</span></span>

<span data-ttu-id="066d0-246">さまざまなオプションとその既定値により、スケジュールされたジョブが実行されるかどうかとそのタイミングが決まります。</span><span class="sxs-lookup"><span data-stu-id="066d0-246">Many of the options and their default values determine whether and when a scheduled job runs.</span></span> <span data-ttu-id="066d0-247">ジョブをスケジュールする前に、必ずこれらのオプションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-247">Be sure to review these options before scheduling a job.</span></span> <span data-ttu-id="066d0-248">スケジュールされたジョブオプションの説明 (既定値を含む) については、「」を参照してください `New-ScheduledJobOption` 。</span><span class="sxs-lookup"><span data-stu-id="066d0-248">For a description of the scheduled job options, including the default values, see `New-ScheduledJobOption`.</span></span>

<span data-ttu-id="066d0-249">ハッシュ テーブルを渡すには、次のキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-249">To submit a hash table, use the following keys.</span></span> <span data-ttu-id="066d0-250">次のハッシュ テーブルには、キーとその既定値が示されています。</span><span class="sxs-lookup"><span data-stu-id="066d0-250">In the following hash table, the keys are shown with their default values.</span></span>

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-251">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="066d0-251">-ScriptBlock</span></span>

<span data-ttu-id="066d0-252">スケジュールされたジョブで実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-252">Specifies the commands that the scheduled job runs.</span></span> <span data-ttu-id="066d0-253">コマンドを中かっこ () で囲み、 `{}` スクリプトブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="066d0-253">Enclose the commands in curly braces (`{}`) to create a script block.</span></span> <span data-ttu-id="066d0-254">コマンド パラメーターの既定値を指定するには、 **ArgumentList** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-254">To specify default values for command parameters, use the **ArgumentList** parameter.</span></span>

<span data-ttu-id="066d0-255">すべての `Register-ScheduledJob` コマンドで **ScriptBlock** パラメーターまたは **FilePath** パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="066d0-255">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-256">-トリガー</span><span class="sxs-lookup"><span data-stu-id="066d0-256">-Trigger</span></span>

<span data-ttu-id="066d0-257">スケジュールされたジョブのトリガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="066d0-257">Specifies the triggers for the scheduled job.</span></span> <span data-ttu-id="066d0-258">コマンドレットが返すオブジェクトや、ジョブトリガーのキーと値のハッシュテーブルなど、1つまたは複数の **Scheduledjobtrigger** オブジェクトを入力し `New-JobTrigger` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-258">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the `New-JobTrigger` cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="066d0-259">ジョブトリガーによってスケジュールジョブが開始されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-259">A job trigger starts the schedule job.</span></span> <span data-ttu-id="066d0-260">トリガーでは、1 回だけ、定期的なスケジュール、またはイベント (ユーザーがログオンしたときや Windows が起動したときなど) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="066d0-260">The trigger can specify a one-time or recurring scheduled or an event, such as when a user logs on or Windows starts.</span></span>

<span data-ttu-id="066d0-261">**Trigger** パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="066d0-261">The **Trigger** parameter is optional.</span></span> <span data-ttu-id="066d0-262">スケジュールされたジョブを作成するときにトリガーを追加したり、、 `Add-JobTrigger` `Set-JobTrigger` 、またはコマンドレットを使用して `Set-ScheduledJob` ジョブトリガーを後で追加または変更したり、コマンドレットを使用してスケジュールされたジョブを直ちに開始することができ `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-262">You can add a trigger when you create the scheduled job, use the `Add-JobTrigger`, `Set-JobTrigger`, or `Set-ScheduledJob` cmdlets to add or change job triggers later, or use the `Start-Job` cmdlet to start the scheduled job immediately.</span></span> <span data-ttu-id="066d0-263">また、テンプレートとして使用するために、トリガーのないスケジュールされたジョブを作成し、管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="066d0-263">You can also create and maintain a scheduled job without a trigger that is used as a template.</span></span>

<span data-ttu-id="066d0-264">ハッシュテーブルを送信するには、次のキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="066d0-264">To submit a hash table, use the following keys:</span></span>

- <span data-ttu-id="066d0-265">**頻度** : 毎日、毎週、atstartup、atstartup</span><span class="sxs-lookup"><span data-stu-id="066d0-265">**Frequency** : Daily, Weekly, AtStartup, AtLogon</span></span>
- <span data-ttu-id="066d0-266">**At** : 任意の有効な時刻文字列</span><span class="sxs-lookup"><span data-stu-id="066d0-266">**At** : Any valid time string</span></span>
- <span data-ttu-id="066d0-267">**DaysOfWeek** -曜日名の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="066d0-267">**DaysOfWeek** - Any combination of day names</span></span>
- <span data-ttu-id="066d0-268">**Interval** -任意の有効な頻度の間隔</span><span class="sxs-lookup"><span data-stu-id="066d0-268">**Interval** - Any valid frequency interval</span></span>
- <span data-ttu-id="066d0-269">**RandomDelay** : 任意の有効な timespan 文字列</span><span class="sxs-lookup"><span data-stu-id="066d0-269">**RandomDelay** : Any valid timespan string</span></span>
- <span data-ttu-id="066d0-270">**User** : 任意の有効なユーザー。</span><span class="sxs-lookup"><span data-stu-id="066d0-270">**User** : Any valid user.</span></span> <span data-ttu-id="066d0-271">AtLogon frequency 値と共にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-271">Used only with the AtLogon frequency value</span></span>

<span data-ttu-id="066d0-272">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="066d0-272">For example:</span></span>

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066d0-273">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="066d0-273">-WhatIf</span></span>

<span data-ttu-id="066d0-274">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="066d0-274">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="066d0-275">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="066d0-275">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="066d0-276">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="066d0-276">CommonParameters</span></span>

<span data-ttu-id="066d0-277">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="066d0-277">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="066d0-278">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-278">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="066d0-279">入力</span><span class="sxs-lookup"><span data-stu-id="066d0-279">INPUTS</span></span>

### <span data-ttu-id="066d0-280">なし</span><span class="sxs-lookup"><span data-stu-id="066d0-280">None</span></span>

<span data-ttu-id="066d0-281">入力をパイプラインからこのコマンドレットに送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="066d0-281">You can't send input down the pipeline to this cmdlet.</span></span>

## <span data-ttu-id="066d0-282">出力</span><span class="sxs-lookup"><span data-stu-id="066d0-282">OUTPUTS</span></span>

### <span data-ttu-id="066d0-283">ScheduledJobDefinition (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="066d0-283">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="066d0-284">注</span><span class="sxs-lookup"><span data-stu-id="066d0-284">NOTES</span></span>

<span data-ttu-id="066d0-285">スケジュールされた各ジョブは、ローカルコンピューターのディレクトリのサブディレクトリに保存され `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-285">Each scheduled job is saved in a subdirectory of the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span>
<span data-ttu-id="066d0-286">サブディレクトリには、スケジュールされたジョブの名前が付けられ、スケジュールされたジョブの XML ファイルとその実行履歴のレコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="066d0-286">The subdirectory is named for the scheduled job and contains an XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="066d0-287">ディスク上のスケジュールされたジョブの詳細については、「 [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-287">For more information about scheduled jobs on disk, see [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).</span></span>

<span data-ttu-id="066d0-288">Windows PowerShell で作成したスケジュールされたジョブは、タスクスケジューラフォルダーのタスクスケジューラに表示され `Library\Microsoft\Windows\PowerShell\ScheduledJobs` ます。</span><span class="sxs-lookup"><span data-stu-id="066d0-288">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler `Library\Microsoft\Windows\PowerShell\ScheduledJobs` folder.</span></span> <span data-ttu-id="066d0-289">タスク スケジューラを使用して、スケジュールされたジョブを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="066d0-289">You can use Task Scheduler to view and edit the scheduled job.</span></span>

<span data-ttu-id="066d0-290">タスクスケジューラ、 **schtasks.exe** コマンドラインツール、およびタスクスケジューラコマンドレットを使用して、スケジュールされたジョブコマンドレットで作成したスケジュールされたジョブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="066d0-290">You can use Task Scheduler, the **schtasks.exe** command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="066d0-291">ただし、スケジュールされたジョブのコマンドレットを使用してタスクスケジューラで作成したタスクを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="066d0-291">However, you can't use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

<span data-ttu-id="066d0-292">スケジュールされたジョブ コマンドが失敗した場合は、エラー メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="066d0-292">If a scheduled job command fails, Windows PowerShell returns an error message.</span></span> <span data-ttu-id="066d0-293">ただし、タスクスケジューラによって実行が試行されたときにジョブが失敗した場合、Windows PowerShell でエラーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="066d0-293">However, if the job fails when Task Scheduler tries to run it, the error isn't available to Windows PowerShell.</span></span>

<span data-ttu-id="066d0-294">スケジュールされたジョブが実行されない場合は、次の方法で理由を確認してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-294">If a scheduled job doesn't run, use the following methods to find the reason:</span></span>

- <span data-ttu-id="066d0-295">ジョブトリガーが適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="066d0-295">Verify that the job trigger is set properly.</span></span>
  - <span data-ttu-id="066d0-296">ジョブオプションに設定されている条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="066d0-296">Verify that the conditions set in the job options are satisfied.</span></span>
- <span data-ttu-id="066d0-297">ジョブを実行するユーザーアカウントに、ジョブのコマンドまたはスクリプトを実行する権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="066d0-297">Verify that the user account under which the job runs has permission to run the commands or scripts in the job.</span></span>
- <span data-ttu-id="066d0-298">タスクスケジューラの履歴でエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="066d0-298">Check the Task Scheduler history for errors.</span></span>
- <span data-ttu-id="066d0-299">タスクスケジューライベントログでエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="066d0-299">Check the Task Scheduler event log for errors.</span></span>

<span data-ttu-id="066d0-300">詳細については、「 [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="066d0-300">For more information, see [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).</span></span>

## <span data-ttu-id="066d0-301">関連リンク</span><span class="sxs-lookup"><span data-stu-id="066d0-301">RELATED LINKS</span></span>

[<span data-ttu-id="066d0-302">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="066d0-302">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="066d0-303">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="066d0-303">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="066d0-304">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="066d0-304">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="066d0-305">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="066d0-305">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="066d0-306">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="066d0-306">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="066d0-307">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="066d0-307">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="066d0-308">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="066d0-308">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="066d0-309">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="066d0-309">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="066d0-310">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="066d0-310">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="066d0-311">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="066d0-311">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="066d0-312">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="066d0-312">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="066d0-313">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="066d0-313">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="066d0-314">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="066d0-314">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="066d0-315">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="066d0-315">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="066d0-316">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="066d0-316">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="066d0-317">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="066d0-317">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
