---
ms.date: 09/13/2016
ms.topic: reference
title: バックグラウンド ジョブ
description: バックグラウンド ジョブ
ms.openlocfilehash: 5478789a2ee1f2eabc71a46673e3a707643cdba8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648625"
---
# <a name="background-jobs"></a><span data-ttu-id="5c3b5-103">バックグラウンド ジョブ</span><span class="sxs-lookup"><span data-stu-id="5c3b5-103">Background Jobs</span></span>

<span data-ttu-id="5c3b5-104">コマンドレットは、内部で、または Windows PowerShell の *バックグラウンドジョブ* としてアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-104">Cmdlets can perform their action internally or as a Windows PowerShell *background job*.</span></span> <span data-ttu-id="5c3b5-105">コマンドレットをバックグラウンドジョブとして実行すると、その作業は、コマンドレットが使用しているパイプラインスレッドとは別に、独自のスレッドで非同期に実行されます。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-105">When a cmdlet runs as a background job, the work is done asynchronously in its own thread separate from the pipeline thread that the cmdlet is using.</span></span> <span data-ttu-id="5c3b5-106">ユーザーの観点からは、コマンドレットをバックグラウンドジョブとして実行すると、ジョブの完了に時間がかかり、ジョブの実行中にユーザーが中断せずに続行できる場合でも、コマンドプロンプトが直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-106">From the user perspective, when a cmdlet runs as a background job, the command prompt returns immediately even if the job takes an extended amount of time to complete, and the user can continue without interruption while the job runs.</span></span>

## <a name="background-jobs-child-jobs-and-the-job-repository"></a><span data-ttu-id="5c3b5-107">バックグラウンドジョブ、子ジョブ、およびジョブリポジトリ</span><span class="sxs-lookup"><span data-stu-id="5c3b5-107">Background Jobs, Child Jobs, and the Job Repository</span></span>

<span data-ttu-id="5c3b5-108">バックグラウンドジョブをサポートするコマンドレットによって返されるジョブオブジェクトは、ジョブを定義します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-108">The job object that is returned by the cmdlets that support background jobs defines the job.</span></span> <span data-ttu-id="5c3b5-109">( [Start ジョブ](/powershell/module/Microsoft.PowerShell.Core/Start-Job) コマンドレットは、ジョブオブジェクトも返します)。ジョブの名前、ジョブを指定するために使用される識別子、状態情報、および子ジョブがこの定義に含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-109">(The [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet also returns a job object.) The name of the job, an identifier that is used to specify the job, the state information, and the child jobs are included in this definition.</span></span> <span data-ttu-id="5c3b5-110">このジョブでは、作業は実行されません。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-110">The job does not perform any of the work.</span></span> <span data-ttu-id="5c3b5-111">子ジョブによって実際の作業が実行されるため、各バックグラウンドジョブには少なくとも1つの子ジョブがあります。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-111">Each background job has at least one child job because the child job performs the actual work.</span></span> <span data-ttu-id="5c3b5-112">作業がバックグラウンドジョブとして実行されるようにコマンドレットを実行する場合、このコマンドレットはジョブと子ジョブを、 *ジョブリポジトリ* と呼ばれる共通リポジトリに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-112">When you run a cmdlet so that the work is performed as a background job, the cmdlet must add the job and the child jobs to a common repository, referred to as the *job repository*.</span></span>

<span data-ttu-id="5c3b5-113">コマンドラインでのバックグラウンドジョブの処理方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-113">For more information about how background jobs are handled at the command line, see the following:</span></span>

- [<span data-ttu-id="5c3b5-114">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="5c3b5-114">about_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [<span data-ttu-id="5c3b5-115">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="5c3b5-115">about_Job_Details</span></span>](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [<span data-ttu-id="5c3b5-116">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="5c3b5-116">about_Remote_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a><span data-ttu-id="5c3b5-117">バックグラウンドジョブとして実行されるコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="5c3b5-117">Writing a Cmdlet That Runs as a Background Job</span></span>

<span data-ttu-id="5c3b5-118">バックグラウンドジョブとして実行できるコマンドレットを作成するには、次のタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-118">To write a cmdlet that can be run as a background job, you must complete the following tasks:</span></span>

- <span data-ttu-id="5c3b5-119">`asJob`コマンドレットをバックグラウンドジョブとして実行するかどうかをユーザーが決定できるように、スイッチパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-119">Define an `asJob` switch parameter so that the user can decide whether to run the cmdlet as a background job.</span></span>

- <span data-ttu-id="5c3b5-120">System.object [クラスから派生した](/dotnet/api/System.Management.Automation.Job) オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-120">Create an object that derives from the [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) class.</span></span> <span data-ttu-id="5c3b5-121">このオブジェクトには、カスタムジョブオブジェクト、または Windows PowerShell によって提供されるジョブオブジェクト ( [Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) オブジェクトなど) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-121">This object can be a custom job object or a job object provided by Windows PowerShell, such as a [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) object.</span></span>

- <span data-ttu-id="5c3b5-122">レコード処理メソッドで、 `if` コマンドレットをバックグラウンドジョブとして実行する必要があるかどうかを検出するステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-122">In a record processing method, add an `if` statement that detects whether the cmdlet should run as a background job.</span></span>

- <span data-ttu-id="5c3b5-123">カスタムジョブオブジェクトの場合は、job クラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-123">For custom job objects, implement the job class.</span></span>

- <span data-ttu-id="5c3b5-124">コマンドレットがバックグラウンドジョブとして実行されているかどうかに応じて、適切なオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-124">Return the appropriate objects, depending on whether the cmdlet is run as a background job.</span></span>

<span data-ttu-id="5c3b5-125">コード例については、「 [ジョブをサポートする方法](./how-to-support-jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-125">For a code example, see [How to Support Jobs](./how-to-support-jobs.md).</span></span>

## <a name="background-job-related-apis"></a><span data-ttu-id="5c3b5-126">バックグラウンド Job-Related Api</span><span class="sxs-lookup"><span data-stu-id="5c3b5-126">Background Job-Related APIs</span></span>

<span data-ttu-id="5c3b5-127">Windows PowerShell では、バックグラウンドジョブを管理するために次の Api が提供されています。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-127">The following APIs are provided by Windows PowerShell to manage background jobs.</span></span>

<span data-ttu-id="5c3b5-128">System.string はカスタムジョブオブジェクト[を派生さ](/dotnet/api/System.Management.Automation.Job)せるものです。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-128">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) Derives custom job objects.</span></span> <span data-ttu-id="5c3b5-129">これは抽象クラスです。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-129">This is an abstract class.</span></span>

<span data-ttu-id="5c3b5-130">現在アクティブなバックグラウンドジョブに関する情報[を管理および](/dotnet/api/System.Management.Automation.JobRepository)提供します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-130">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) Manages and provides information about the current active background jobs.</span></span>

<span data-ttu-id="5c3b5-131">[システムの管理. Jobstate](/dotnet/api/System.Management.Automation.JobState) は、バックグラウンドジョブの状態を定義します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-131">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) Defines the state of the background job.</span></span> <span data-ttu-id="5c3b5-132">状態には、開始、実行中、停止が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-132">States include Started, Running, and Stopped.</span></span>

<span data-ttu-id="5c3b5-133">[システムの管理. Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) は、バックグラウンドジョブの状態に関する情報を提供します。最後の状態変更がエラーによって発生した場合は、ジョブが現在の状態になった理由を示します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-133">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) Provides information about the state of a background job and, if the last state change was caused by an error, the reason the job entered its current state.</span></span>

<span data-ttu-id="5c3b5-134">" [System. Automation. Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) " は、バックグラウンドジョブが状態を変更したときに発生するイベントの引数を提供します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-134">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) Provides the arguments for an event that is raised when a background job changes state.</span></span>

## <a name="windows-powershell-job-cmdlets"></a><span data-ttu-id="5c3b5-135">Windows PowerShell ジョブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5c3b5-135">Windows PowerShell Job Cmdlets</span></span>

<span data-ttu-id="5c3b5-136">次のコマンドレットは、Windows PowerShell によってバックグラウンドジョブを管理するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-136">The following cmdlets are provided by Windows PowerShell to manage background jobs.</span></span>

[<span data-ttu-id="5c3b5-137">Get-Job</span><span class="sxs-lookup"><span data-stu-id="5c3b5-137">Get-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

<span data-ttu-id="5c3b5-138">現在のセッションで実行されている Windows PowerShell のバックグラウンド ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-138">Gets Windows PowerShell background jobs that are running in the current session.</span></span>

[<span data-ttu-id="5c3b5-139">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="5c3b5-139">Receive-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

<span data-ttu-id="5c3b5-140">現在のセッションの Windows PowerShell バックグラウンド ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-140">Gets the results of the Windows PowerShell background jobs in the current session.</span></span>

[<span data-ttu-id="5c3b5-141">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="5c3b5-141">Remove-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

<span data-ttu-id="5c3b5-142">Windows PowerShell バックグラウンド ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-142">Deletes a Windows PowerShell background job.</span></span>

[<span data-ttu-id="5c3b5-143">Start-Job</span><span class="sxs-lookup"><span data-stu-id="5c3b5-143">Start-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

<span data-ttu-id="5c3b5-144">Windows PowerShell バックグラウンド ジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-144">Starts a Windows PowerShell background job.</span></span>

[<span data-ttu-id="5c3b5-145">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="5c3b5-145">Stop-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

<span data-ttu-id="5c3b5-146">Windows PowerShell バックグラウンド ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-146">Stops a Windows PowerShell background job.</span></span>

[<span data-ttu-id="5c3b5-147">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="5c3b5-147">Wait-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

<span data-ttu-id="5c3b5-148">セッションで実行されている 1 つまたはすべての Windows PowerShell のバックグラウンド ジョブが完了するまでは、コマンド プロンプトが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="5c3b5-148">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are complete.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c3b5-149">参照</span><span class="sxs-lookup"><span data-stu-id="5c3b5-149">See Also</span></span>

[<span data-ttu-id="5c3b5-150">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="5c3b5-150">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
