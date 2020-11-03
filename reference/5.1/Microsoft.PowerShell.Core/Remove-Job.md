---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 589c43c814d5d68e57fd20226c675bf0f9587b69
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212792"
---
# <span data-ttu-id="44cc1-103">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="44cc1-103">Remove-Job</span></span>

## <span data-ttu-id="44cc1-104">概要</span><span class="sxs-lookup"><span data-stu-id="44cc1-104">SYNOPSIS</span></span>
<span data-ttu-id="44cc1-105">PowerShell バックグラウンドジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-105">Deletes a PowerShell background job.</span></span>

## <span data-ttu-id="44cc1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="44cc1-106">SYNTAX</span></span>

### <span data-ttu-id="44cc1-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="44cc1-107">SessionIdParameterSet (Default)</span></span>

```
Remove-Job [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="44cc1-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="44cc1-108">JobParameterSet</span></span>

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="44cc1-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="44cc1-109">NameParameterSet</span></span>

```
Remove-Job [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="44cc1-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="44cc1-110">InstanceIdParameterSet</span></span>

```
Remove-Job [-InstanceId] <Guid[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="44cc1-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="44cc1-111">FilterParameterSet</span></span>

```
Remove-Job [-Filter] <Hashtable> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="44cc1-112">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="44cc1-112">StateParameterSet</span></span>

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="44cc1-113">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="44cc1-113">CommandParameterSet</span></span>

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="44cc1-114">Description</span><span class="sxs-lookup"><span data-stu-id="44cc1-114">DESCRIPTION</span></span>

<span data-ttu-id="44cc1-115">コマンドレットは、 `Remove-Job` コマンドレットによって開始された PowerShell バックグラウンドジョブ、 `Start-Job` または `Invoke-Command` **AsJob** パラメーターをサポートするなどのコマンドレットによって開始された PowerShell バックグラウンドジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-115">The `Remove-Job` cmdlet deletes PowerShell background jobs that were started by the `Start-Job` cmdlet or by cmdlets such as `Invoke-Command` that support the **AsJob** parameter.</span></span>

<span data-ttu-id="44cc1-116">を使用すると、 `Remove-Job` すべてのジョブを削除したり、選択したジョブを削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-116">You can use `Remove-Job` to delete all jobs or delete selected jobs.</span></span> <span data-ttu-id="44cc1-117">ジョブは、 **名前** 、 **ID** 、 **インスタンス id** 、 **コマンド** 、または **状態** によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-117">The jobs are identified by their **Name** , **ID** , **Instance ID** , **Command** , or **State** .</span></span> <span data-ttu-id="44cc1-118">または、ジョブオブジェクトをパイプラインの下に送信することもでき `Remove-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-118">Or, a job object can be sent down the pipeline to `Remove-Job`.</span></span> <span data-ttu-id="44cc1-119">パラメーターまたはパラメーター値が指定されていない場合、に `Remove-Job` よる影響はありません。</span><span class="sxs-lookup"><span data-stu-id="44cc1-119">Without parameters or parameter values, `Remove-Job` has no effect.</span></span>

<span data-ttu-id="44cc1-120">PowerShell 3.0 以降、では、 `Remove-Job` スケジュールされたジョブやワークフロージョブなどのカスタムジョブの種類を削除できます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-120">Since PowerShell 3.0, `Remove-Job` can delete custom job types, such as scheduled jobs and workflow jobs.</span></span> <span data-ttu-id="44cc1-121">たとえば、は、 `Remove-Job` スケジュールされたジョブ、ディスク上のスケジュールされたジョブのすべてのインスタンス、およびトリガーされたすべてのジョブインスタンスの結果を削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-121">For example, `Remove-Job` deletes the scheduled job, all instances of the scheduled job on disk, and the results of all triggered job instances.</span></span>

<span data-ttu-id="44cc1-122">実行中のジョブを削除しようとすると、は `Remove-Job` 失敗します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-122">If you try to delete a running job, `Remove-Job` fails.</span></span> <span data-ttu-id="44cc1-123">`Stop-Job`コマンドレットを使用して、実行中のジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-123">Use the `Stop-Job` cmdlet to stop a running job.</span></span> <span data-ttu-id="44cc1-124">または、 `Remove-Job` **Force** パラメーターと共にを使用して、実行中のジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-124">Or, use `Remove-Job` with the **Force** parameter to delete a running job.</span></span>

<span data-ttu-id="44cc1-125">バックグラウンドジョブを削除するか、PowerShell セッションを閉じるまで、ジョブはグローバルジョブキャッシュに残ります。</span><span class="sxs-lookup"><span data-stu-id="44cc1-125">Jobs remain in the global job cache until you delete the background job or close the PowerShell session.</span></span>

## <span data-ttu-id="44cc1-126">例</span><span class="sxs-lookup"><span data-stu-id="44cc1-126">EXAMPLES</span></span>

### <span data-ttu-id="44cc1-127">例 1: 名前を使用してジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="44cc1-127">Example 1: Delete a job by using its name</span></span>

<span data-ttu-id="44cc1-128">この例では、変数とパイプラインを使用して、名前を指定してジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-128">This example uses a variable and the pipeline to delete a job by name.</span></span>

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

<span data-ttu-id="44cc1-129">`Get-Job`**Name** パラメーターを使用して、ジョブ **batchjob** を指定します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-129">`Get-Job` uses the **Name** parameter to specify the job, **BatchJob** .</span></span> <span data-ttu-id="44cc1-130">ジョブオブジェクトは変数に格納され `$batch` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-130">The job object is stored in the `$batch` variable.</span></span> <span data-ttu-id="44cc1-131">のオブジェクト `$batch` は、パイプラインの下にに送信され `Remove-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-131">The object in `$batch` is sent down the pipeline to `Remove-Job`.</span></span>

<span data-ttu-id="44cc1-132">別の方法として、などの **ジョブ** パラメーターを使用することも `Remove-Job -Job $batch` できます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-132">An alternative is to use the **Job** parameter, such as `Remove-Job -Job $batch`.</span></span>

### <span data-ttu-id="44cc1-133">例 2: セッション内のすべてのジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="44cc1-133">Example 2: Delete all jobs in a session</span></span>

<span data-ttu-id="44cc1-134">この例では、現在の PowerShell セッションのすべてのジョブが削除されます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-134">In this example, all the jobs in the current PowerShell session are deleted.</span></span>

```powershell
Get-job | Remove-Job
```

<span data-ttu-id="44cc1-135">`Get-Job` 現在の PowerShell セッションのすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-135">`Get-Job` gets all the jobs in the current PowerShell session.</span></span> <span data-ttu-id="44cc1-136">ジョブオブジェクトは、パイプラインからに送信され `Remove-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-136">The job objects are sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="44cc1-137">例 3: NotStarted ジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="44cc1-137">Example 3: Delete NotStarted jobs</span></span>

<span data-ttu-id="44cc1-138">この例では、開始されていない現在の PowerShell セッションからすべてのジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-138">This example deletes all jobs from the current PowerShell session that haven't started.</span></span>

```powershell
Remove-Job -State NotStarted
```

<span data-ttu-id="44cc1-139">`Remove-Job`**State** パラメーターを使用して、ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-139">`Remove-Job` uses the **State** parameter to specify the job status.</span></span>

### <span data-ttu-id="44cc1-140">例 4: フレンドリ名を使用してジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="44cc1-140">Example 4: Delete jobs by using a friendly name</span></span>

<span data-ttu-id="44cc1-141">この例では、現在のセッションから、実行中のジョブを含め、\* batch \* \* で終わるすべてのジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-141">This example deletes all jobs from the current session with friendly names that end with \*batch\*\*, including jobs that are running.</span></span>

```powershell
Remove-Job -Name *batch -Force
```

<span data-ttu-id="44cc1-142">`Remove-Job`**name** パラメーターを使用してジョブ名のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-142">`Remove-Job` uses the **Name** parameter to specify a job name pattern.</span></span> <span data-ttu-id="44cc1-143">このパターンには、 `*` **batch** で終了するすべてのジョブ名を検索するためのアスタリスク () ワイルドカードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44cc1-143">The pattern includes the asterisk (`*`) wildcard to find all job names that end with **batch** .</span></span> <span data-ttu-id="44cc1-144">**Force** パラメーターは、を実行しているジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-144">The **Force** parameter deletes jobs that running.</span></span>

### <span data-ttu-id="44cc1-145">例 5: Invoke-Command によって作成されたジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="44cc1-145">Example 5: Delete a job that was created by Invoke-Command</span></span>

<span data-ttu-id="44cc1-146">次の例では、を使用してリモートコンピューターで開始されたジョブを `Invoke-Command` **AsJob** パラメーターと共に削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-146">This example removes a job that was started on a remote computer using `Invoke-Command` with the **AsJob** parameter.</span></span>

<span data-ttu-id="44cc1-147">この例では **AsJob** パラメーターを使用しているため、ジョブオブジェクトはローカルコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-147">Because the example uses the **AsJob** parameter, the job object is created on the local computer.</span></span>
<span data-ttu-id="44cc1-148">ただし、ジョブはリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-148">But, the job runs on a remote computer.</span></span> <span data-ttu-id="44cc1-149">その結果、ジョブを管理するには、ローカルのコマンドを使用することになります。</span><span class="sxs-lookup"><span data-stu-id="44cc1-149">As a result, you use local commands to manage the job.</span></span>

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

<span data-ttu-id="44cc1-150">`Invoke-Command`**Server01** コンピューターでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-150">`Invoke-Command` runs a job on the **Server01** computer.</span></span> <span data-ttu-id="44cc1-151">**AsJob** パラメーターは、 **ScriptBlock** をバックグラウンドジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-151">The **AsJob** parameter runs the **ScriptBlock** as a background job.</span></span> <span data-ttu-id="44cc1-152">ジョブオブジェクトは変数に格納され `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-152">The job object is stored in the `$job` variable.</span></span> <span data-ttu-id="44cc1-153">`$job`変数オブジェクトは、パイプラインの下にに送信され `Remove-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-153">The `$job` variable object is sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="44cc1-154">例 6: Invoke-Command と Start-Job によって作成されたジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="44cc1-154">Example 6: Delete a job that was created by Invoke-Command and Start-Job</span></span>

<span data-ttu-id="44cc1-155">この例では、を使用して起動されたリモートコンピューター上のジョブを実行する方法を示し `Invoke-Command` `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-155">This example shows how to remove a job on a remote computer that was started by using `Invoke-Command` to run `Start-Job`.</span></span> <span data-ttu-id="44cc1-156">ジョブオブジェクトはリモートコンピューター上に作成され、リモートコマンドを使用してジョブを管理します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-156">The job object is created on the remote computer and remote commands are used to manage the job.</span></span> <span data-ttu-id="44cc1-157">リモートコマンドを実行する場合は、永続的な接続が必要です `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="44cc1-157">A persistent connection is required when running a remote `Start-Job` command.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

<span data-ttu-id="44cc1-158">`New-PSSession`**Server01** コンピューターへの永続的な接続である **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-158">`New-PSSession` creates a **PSSession** , a persistent connection, to the **Server01** computer.</span></span> <span data-ttu-id="44cc1-159">接続は変数に保存され `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-159">The connection is saved in the `$S` variable.</span></span>

<span data-ttu-id="44cc1-160">`Invoke-Command` に保存されているセッションに接続 `$S` します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-160">`Invoke-Command` connects to the session saved in `$S`.</span></span> <span data-ttu-id="44cc1-161">**ScriptBlock** は、を使用して `Start-Job` リモートジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-161">The **ScriptBlock** uses `Start-Job` to start a remote job.</span></span> <span data-ttu-id="44cc1-162">ジョブはコマンドを実行 `Get-Process` し、 **Name** パラメーターを使用して、わかりやすいジョブ名 **myjob** を指定します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-162">The job runs a `Get-Process` command and uses the **Name** parameter to specify a friendly job name, **MyJob** .</span></span>

<span data-ttu-id="44cc1-163">`Invoke-Command` は、 `$S` セッションを使用してを実行 `Remove-Job` します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-163">`Invoke-Command` uses the `$S` session and runs `Remove-Job`.</span></span> <span data-ttu-id="44cc1-164">**Name** パラメーターは、 **myjob** という名前のジョブが削除されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-164">The **Name** parameter specifies that the job named **MyJob** is deleted.</span></span>

### <span data-ttu-id="44cc1-165">例 7: InstanceId を使用してジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="44cc1-165">Example 7: Delete a job by using its InstanceId</span></span>

<span data-ttu-id="44cc1-166">この例では、 **InstanceId** に基づいてジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-166">This example removes a job based on its **InstanceId** .</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process PowerShell}
$job | Format-List -Property *
Remove-Job -InstanceId ad02b942-8007-4407-87f3-d23e71955872
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-Process PowerShell
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : ad02b942-8007-4407-87f3-d23e71955872
Id            : 3
Name          : Job3
ChildJobs     : {Job4}
PSBeginTime   : 7/26/2019 11:36:56
PSEndTime     : 7/26/2019 11:36:57
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="44cc1-167">`Start-Job` バックグラウンドジョブを開始し、ジョブオブジェクトを変数に保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-167">`Start-Job` starts a background job and the job object is saved in the `$job` variable.</span></span>

<span data-ttu-id="44cc1-168">のオブジェクト `$job` は、パイプラインの下にに送信され `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-168">The object in `$job` is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="44cc1-169">**Property** パラメーターはアスタリスク () を使用して `*` 、すべてのオブジェクトのプロパティがリストに表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-169">The **Property** parameter uses an asterisk (`*`) to specify that all the object's properties are displayed in a list.</span></span>

<span data-ttu-id="44cc1-170">`Remove-Job` では、 **InstanceId** パラメーターを使用して、削除するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-170">`Remove-Job` uses the **InstanceId** parameter to specify the job to delete.</span></span>

## <span data-ttu-id="44cc1-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="44cc1-171">PARAMETERS</span></span>

### <span data-ttu-id="44cc1-172">-Command</span><span class="sxs-lookup"><span data-stu-id="44cc1-172">-Command</span></span>

<span data-ttu-id="44cc1-173">指定された単語をコマンドに含んでいるジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-173">Deletes jobs that include the specified words in the command.</span></span> <span data-ttu-id="44cc1-174">コンマ区切りの配列を入力できます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-174">You can enter a comma-separated array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="44cc1-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="44cc1-175">-Confirm</span></span>

<span data-ttu-id="44cc1-176">を実行する前に確認メッセージを表示 `Remove-Job` します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-176">Prompts you for confirmation before `Remove-Job` is run.</span></span>

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

### <span data-ttu-id="44cc1-177">-Filter</span><span class="sxs-lookup"><span data-stu-id="44cc1-177">-Filter</span></span>

<span data-ttu-id="44cc1-178">関連付けられたハッシュテーブルに設定されているすべての条件を満たすジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-178">Deletes jobs that satisfy all the conditions established in the associated hash table.</span></span> <span data-ttu-id="44cc1-179">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-179">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="44cc1-180">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-180">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="44cc1-181">これは、を使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="44cc1-181">It doesn't work on standard background jobs, such as those created by using the `Start-Job`.</span></span>

<span data-ttu-id="44cc1-182">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="44cc1-182">This parameter is introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="44cc1-183">-Force</span><span class="sxs-lookup"><span data-stu-id="44cc1-183">-Force</span></span>

<span data-ttu-id="44cc1-184">ジョブの状態が **Running** の場合でも、ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-184">Deletes a job even if the job's state is **Running** .</span></span> <span data-ttu-id="44cc1-185">**Force** パラメーターが指定されていない場合、は `Remove-Job` 実行中のジョブを削除しません。</span><span class="sxs-lookup"><span data-stu-id="44cc1-185">If the **Force** parameter isn't specified, `Remove-Job` doesn't delete running jobs.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, NameParameterSet, InstanceIdParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44cc1-186">-Id</span><span class="sxs-lookup"><span data-stu-id="44cc1-186">-Id</span></span>

<span data-ttu-id="44cc1-187">指定された **Id** を持つバックグラウンドジョブを削除します。コンマ区切りの配列を入力できます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-187">Deletes background jobs with the specified **Id** . You can enter a comma-separated array.</span></span> <span data-ttu-id="44cc1-188">ジョブの **Id** は、現在のセッション内のジョブを識別する一意の整数です。</span><span class="sxs-lookup"><span data-stu-id="44cc1-188">The job's **Id** is a unique integer that identifies a job within the current session.</span></span>

<span data-ttu-id="44cc1-189">ジョブの **Id** を検索するには、パラメーターを指定せずにを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-189">To find a job's **Id** , use `Get-Job` without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="44cc1-190">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="44cc1-190">-InstanceId</span></span>

<span data-ttu-id="44cc1-191">指定した **InstanceId** のジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-191">Deletes jobs with the specified **InstanceId** .</span></span> <span data-ttu-id="44cc1-192">コンマ区切りの配列を入力できます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-192">You can enter a comma-separated array.</span></span> <span data-ttu-id="44cc1-193">**InstanceId** は、ジョブを識別する一意の GUID です。</span><span class="sxs-lookup"><span data-stu-id="44cc1-193">An **InstanceId** is a unique GUID that identifies a job.</span></span>

<span data-ttu-id="44cc1-194">ジョブの **InstanceId** を検索するには、を使用 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-194">To find a job's **InstanceId** , use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="44cc1-195">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="44cc1-195">-Job</span></span>

<span data-ttu-id="44cc1-196">削除するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-196">Specifies the jobs to be deleted.</span></span> <span data-ttu-id="44cc1-197">ジョブが格納されている変数、またはジョブを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-197">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="44cc1-198">コンマ区切りの配列を入力できます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-198">You can enter a comma-separated array.</span></span>

<span data-ttu-id="44cc1-199">パイプラインの下にジョブオブジェクトを送信することができ `Remove-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-199">You can send job objects down the pipeline to `Remove-Job`.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="44cc1-200">-Name</span><span class="sxs-lookup"><span data-stu-id="44cc1-200">-Name</span></span>

<span data-ttu-id="44cc1-201">指定されたフレンドリ名を持つジョブのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-201">Only deletes jobs with the specified friendly name.</span></span> <span data-ttu-id="44cc1-202">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-202">Wildcards are permitted.</span></span> <span data-ttu-id="44cc1-203">コンマ区切りの配列を入力できます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-203">You can enter a comma-separated array.</span></span>

<span data-ttu-id="44cc1-204">ジョブのフレンドリ名は、PowerShell セッション内でも一意であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="44cc1-204">Friendly names for jobs aren't guaranteed to be unique, even within a PowerShell session.</span></span> <span data-ttu-id="44cc1-205">名前でファイルを削除する場合は、 **WhatIf** パラメーターと **Confirm** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-205">Use the **WhatIf** and **Confirm** parameters when you delete files by name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="44cc1-206">-状態</span><span class="sxs-lookup"><span data-stu-id="44cc1-206">-State</span></span>

<span data-ttu-id="44cc1-207">は、指定された状態のジョブのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-207">Only deletes jobs with the specified state.</span></span> <span data-ttu-id="44cc1-208">状態が **Running** のジョブを削除するには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-208">To delete jobs with a state of **Running** , use the **Force** parameter.</span></span>

<span data-ttu-id="44cc1-209">許容される値:</span><span class="sxs-lookup"><span data-stu-id="44cc1-209">Accepted values:</span></span>

- <span data-ttu-id="44cc1-210">AtBreakpoint</span><span class="sxs-lookup"><span data-stu-id="44cc1-210">AtBreakpoint</span></span>
- <span data-ttu-id="44cc1-211">Blocked</span><span class="sxs-lookup"><span data-stu-id="44cc1-211">Blocked</span></span>
- <span data-ttu-id="44cc1-212">完了</span><span class="sxs-lookup"><span data-stu-id="44cc1-212">Completed</span></span>
- <span data-ttu-id="44cc1-213">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="44cc1-213">Disconnected</span></span>
- <span data-ttu-id="44cc1-214">失敗</span><span class="sxs-lookup"><span data-stu-id="44cc1-214">Failed</span></span>
- <span data-ttu-id="44cc1-215">NotStarted</span><span class="sxs-lookup"><span data-stu-id="44cc1-215">NotStarted</span></span>
- <span data-ttu-id="44cc1-216">実行中</span><span class="sxs-lookup"><span data-stu-id="44cc1-216">Running</span></span>
- <span data-ttu-id="44cc1-217">停止済み</span><span class="sxs-lookup"><span data-stu-id="44cc1-217">Stopped</span></span>
- <span data-ttu-id="44cc1-218">停止中</span><span class="sxs-lookup"><span data-stu-id="44cc1-218">Stopping</span></span>
- <span data-ttu-id="44cc1-219">Suspended</span><span class="sxs-lookup"><span data-stu-id="44cc1-219">Suspended</span></span>
- <span data-ttu-id="44cc1-220">中断中</span><span class="sxs-lookup"><span data-stu-id="44cc1-220">Suspending</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: AtBreakpoint, Blocked, Completed, Disconnected, Failed, NotStarted, Running, Stopped, Stopping, Suspended, Suspending

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="44cc1-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="44cc1-221">-WhatIf</span></span>

<span data-ttu-id="44cc1-222">が実行された場合に何が起こるか `Remove-Job` を示します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-222">Shows what would happen if `Remove-Job` runs.</span></span> <span data-ttu-id="44cc1-223">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="44cc1-223">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="44cc1-224">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="44cc1-224">CommonParameters</span></span>

<span data-ttu-id="44cc1-225">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="44cc1-225">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="44cc1-226">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44cc1-226">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="44cc1-227">入力</span><span class="sxs-lookup"><span data-stu-id="44cc1-227">INPUTS</span></span>

### <span data-ttu-id="44cc1-228">システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="44cc1-228">System.Management.Automation.Job</span></span>

<span data-ttu-id="44cc1-229">パイプラインの下にジョブオブジェクトを送信することができ `Remove-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-229">You can send a job object down the pipeline to `Remove-Job`.</span></span>

## <span data-ttu-id="44cc1-230">出力</span><span class="sxs-lookup"><span data-stu-id="44cc1-230">OUTPUTS</span></span>

### <span data-ttu-id="44cc1-231">なし</span><span class="sxs-lookup"><span data-stu-id="44cc1-231">None</span></span>

<span data-ttu-id="44cc1-232">`Remove-Job` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="44cc1-232">`Remove-Job` doesn't generate any output.</span></span>

## <span data-ttu-id="44cc1-233">注</span><span class="sxs-lookup"><span data-stu-id="44cc1-233">NOTES</span></span>

<span data-ttu-id="44cc1-234">PowerShell ジョブによって新しいプロセスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-234">A PowerShell job creates a new process.</span></span> <span data-ttu-id="44cc1-235">ジョブが完了すると、プロセスは終了します。</span><span class="sxs-lookup"><span data-stu-id="44cc1-235">When the job completes, the process exits.</span></span> <span data-ttu-id="44cc1-236">`Remove-Job`を実行すると、ジョブの状態が削除されます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-236">When `Remove-Job` is run, the job's state is removed.</span></span>

<span data-ttu-id="44cc1-237">ジョブが完了前に停止し、そのプロセスが終了していない場合、プロセスは強制的に終了されます。</span><span class="sxs-lookup"><span data-stu-id="44cc1-237">If a job stops before completion and its process hasn't exited, the process is forcibly terminated.</span></span>

## <span data-ttu-id="44cc1-238">関連リンク</span><span class="sxs-lookup"><span data-stu-id="44cc1-238">RELATED LINKS</span></span>

[<span data-ttu-id="44cc1-239">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="44cc1-239">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="44cc1-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="44cc1-240">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="44cc1-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="44cc1-241">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="44cc1-242">Get-Job</span><span class="sxs-lookup"><span data-stu-id="44cc1-242">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="44cc1-243">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="44cc1-243">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="44cc1-244">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="44cc1-244">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="44cc1-245">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="44cc1-245">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="44cc1-246">Start-Job</span><span class="sxs-lookup"><span data-stu-id="44cc1-246">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="44cc1-247">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="44cc1-247">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="44cc1-248">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="44cc1-248">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="44cc1-249">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="44cc1-249">Wait-Job</span></span>](Wait-Job.md)
