---
title: バック グラウンド ジョブ |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0ef5ac9-8254-4832-ace8-84b356c10f08
caps.latest.revision: 13
ms.openlocfilehash: ff4fe159eedc47fc69f4d783cd90d2b0e888c0d5
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794707"
---
# <a name="background-jobs"></a><span data-ttu-id="41259-102">バックグラウンド ジョブ</span><span class="sxs-lookup"><span data-stu-id="41259-102">Background Jobs</span></span>

<span data-ttu-id="41259-103">内部的には、Windows PowerShell コマンドレットでそれらのアクションを実行できます*バック グラウンド ジョブ*します。</span><span class="sxs-lookup"><span data-stu-id="41259-103">Cmdlets can perform their action internally or as a Windows PowerShell*background job*.</span></span> <span data-ttu-id="41259-104">コマンドレットをバック グラウンド ジョブとして実行すると、作業は、コマンドレットを使用しているパイプラインのスレッドから別の独自のスレッドで非同期に実行します。</span><span class="sxs-lookup"><span data-stu-id="41259-104">When a cmdlet runs as a background job, the work is done asynchronously in its own thread separate from the pipeline thread that the cmdlet is using.</span></span> <span data-ttu-id="41259-105">ユーザーの観点からコマンドレットをバック グラウンド ジョブとして実行すると、コマンド プロンプトに戻りますすぐに場合でも、ジョブを完了するに非常に長い時間を受け取り、ユーザーがジョブの実行中に中断なく続行します。</span><span class="sxs-lookup"><span data-stu-id="41259-105">From the user perspective, when a cmdlet runs as a background job, the command prompt returns immediately even if the job takes an extended amount of time to complete, and the user can continue without interruption while the job runs.</span></span>

## <a name="background-jobs-child-jobs-and-the-job-repository"></a><span data-ttu-id="41259-106">バック グラウンド ジョブの子ジョブおよびジョブ リポジトリ</span><span class="sxs-lookup"><span data-stu-id="41259-106">Background Jobs, Child Jobs, and the Job Repository</span></span>

<span data-ttu-id="41259-107">バック グラウンド ジョブをサポートするコマンドレットによって返されるジョブ オブジェクトは、ジョブを定義します。</span><span class="sxs-lookup"><span data-stu-id="41259-107">The job object that is returned by the cmdlets that support background jobs defines the job.</span></span> <span data-ttu-id="41259-108">(、 [Start-job](/powershell/module/Microsoft.PowerShell.Core/Start-Job)コマンドレットはジョブ オブジェクトも返します)。この定義では、ジョブ、ジョブ、状態情報、および子ジョブを指定するために使用する識別子の名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="41259-108">(The [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet also returns a job object.) The name of the job, an identifier that is used to specify the job, the state information, and the child jobs are included in this definition.</span></span> <span data-ttu-id="41259-109">ジョブは、作業のいずれかを実行しません。</span><span class="sxs-lookup"><span data-stu-id="41259-109">The job does not perform any of the work.</span></span> <span data-ttu-id="41259-110">各バック グラウンド ジョブでは、子ジョブは、実際の作業を実行するために少なくとも 1 つの子ジョブがあります。</span><span class="sxs-lookup"><span data-stu-id="41259-110">Each background job has at least one child job because the child job performs the actual work.</span></span> <span data-ttu-id="41259-111">作業がバック グラウンド ジョブとして実行されるようにコマンドレットを実行するときにコマンドレットは、する必要があります、ジョブと子ジョブに追加と呼ばれる共通のリポジトリ、*のジョブ リポジトリ*します。</span><span class="sxs-lookup"><span data-stu-id="41259-111">When you run a cmdlet so that the work is performed as a background job, the cmdlet must add the job and the child jobs to a common repository, referred to as the *job repository*.</span></span>

<span data-ttu-id="41259-112">コマンドラインでバック グラウンド ジョブを処理する方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41259-112">For more information about how background jobs are handled at the command line, see the following:</span></span>

- [<span data-ttu-id="41259-113">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="41259-113">about_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [<span data-ttu-id="41259-114">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="41259-114">about_Job_Details</span></span>](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [<span data-ttu-id="41259-115">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="41259-115">about_Remote_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a><span data-ttu-id="41259-116">バック グラウンド ジョブとして実行されるコマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="41259-116">Writing a Cmdlet That Runs as a Background Job</span></span>

<span data-ttu-id="41259-117">バック グラウンド ジョブとして実行できるコマンドレットを作成するには、次のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="41259-117">To write a cmdlet that can be run as a background job, you must complete the following tasks:</span></span>

- <span data-ttu-id="41259-118">定義、`asJob`スイッチ パラメーターで、ユーザーが、コマンドレットをバック グラウンド ジョブとして実行するかどうかを決定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="41259-118">Define an `asJob` switch parameter so that the user can decide whether to run the cmdlet as a background job.</span></span>

- <span data-ttu-id="41259-119">派生したオブジェクトを作成、 [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job)クラス。</span><span class="sxs-lookup"><span data-stu-id="41259-119">Create an object that derives from the [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) class.</span></span> <span data-ttu-id="41259-120">このオブジェクトは、カスタムのジョブ オブジェクトまたはジョブ オブジェクトなど、Windows PowerShell によって提供される、 [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="41259-120">This object can be a custom job object or a job object provided by Windows PowerShell, such as a [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) object.</span></span>

- <span data-ttu-id="41259-121">レコードの処理メソッドには、追加、`if`コマンドレットがバック グラウンド ジョブとして実行する必要があるかどうかを検出するステートメント。</span><span class="sxs-lookup"><span data-stu-id="41259-121">In a record processing method, add an `if` statement that detects whether the cmdlet should run as a background job.</span></span>

- <span data-ttu-id="41259-122">カスタムのジョブ オブジェクトの場合は、job クラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="41259-122">For custom job objects, implement the job class.</span></span>

- <span data-ttu-id="41259-123">コマンドレットをバック グラウンド ジョブとして実行するかどうかに応じて、適切なオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="41259-123">Return the appropriate objects, depending on whether the cmdlet is run as a background job.</span></span>

<span data-ttu-id="41259-124">コード例では、次を参照してください。[サポート ジョブ方法](./how-to-support-jobs.md)します。</span><span class="sxs-lookup"><span data-stu-id="41259-124">For a code example, see [How to Support Jobs](./how-to-support-jobs.md).</span></span>

## <a name="background-job-related-apis"></a><span data-ttu-id="41259-125">バック グラウンド ジョブに関連する Api</span><span class="sxs-lookup"><span data-stu-id="41259-125">Background Job-Related APIs</span></span>

<span data-ttu-id="41259-126">次の Api は、バック グラウンド ジョブを管理する Windows PowerShell によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="41259-126">The following APIs are provided by Windows PowerShell to manage background jobs.</span></span>

<span data-ttu-id="41259-127">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job)カスタムのジョブ オブジェクトを派生します。</span><span class="sxs-lookup"><span data-stu-id="41259-127">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) Derives custom job objects.</span></span> <span data-ttu-id="41259-128">これは、抽象クラスです。</span><span class="sxs-lookup"><span data-stu-id="41259-128">This is an abstract class.</span></span>

<span data-ttu-id="41259-129">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository)を管理し、現在のアクティブなバック グラウンド ジョブに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="41259-129">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) Manages and provides information about the current active background jobs.</span></span>

<span data-ttu-id="41259-130">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState)バック グラウンド ジョブの状態を定義します。</span><span class="sxs-lookup"><span data-stu-id="41259-130">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) Defines the state of the background job.</span></span> <span data-ttu-id="41259-131">開始、実行、および停止の状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="41259-131">States include Started, Running, and Stopped.</span></span>

<span data-ttu-id="41259-132">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo)バック グラウンド ジョブの状態に関する情報を提供し、最新の状態を変更する場合は、エラー、ジョブの現在の状態になった理由によって発生しました。</span><span class="sxs-lookup"><span data-stu-id="41259-132">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) Provides information about the state of a background job and, if the last state change was caused by an error, the reason the job entered its current state.</span></span>

<span data-ttu-id="41259-133">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs)バック グラウンド ジョブの状態が変更されたときに発生するイベントの引数を提供します。</span><span class="sxs-lookup"><span data-stu-id="41259-133">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) Provides the arguments for an event that is raised when a background job changes state.</span></span>

## <a name="windows-powershell-job-cmdlets"></a><span data-ttu-id="41259-134">Windows PowerShell ジョブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="41259-134">Windows PowerShell Job Cmdlets</span></span>

<span data-ttu-id="41259-135">次のコマンドレットは、バック グラウンド ジョブを管理する Windows PowerShell によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="41259-135">The following cmdlets are provided by Windows PowerShell to manage background jobs.</span></span>

[<span data-ttu-id="41259-136">Get-Job</span><span class="sxs-lookup"><span data-stu-id="41259-136">Get-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

<span data-ttu-id="41259-137">現在のセッションで実行されている Windows PowerShell のバックグラウンド ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="41259-137">Gets Windows PowerShell background jobs that are running in the current session.</span></span>

[<span data-ttu-id="41259-138">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="41259-138">Receive-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

<span data-ttu-id="41259-139">現在のセッションの Windows PowerShell バックグラウンド ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="41259-139">Gets the results of the Windows PowerShell background jobs in the current session.</span></span>

[<span data-ttu-id="41259-140">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="41259-140">Remove-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

<span data-ttu-id="41259-141">Windows PowerShell バックグラウンド ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="41259-141">Deletes a Windows PowerShell background job.</span></span>

[<span data-ttu-id="41259-142">Start-Job</span><span class="sxs-lookup"><span data-stu-id="41259-142">Start-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

<span data-ttu-id="41259-143">Windows PowerShell バックグラウンド ジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="41259-143">Starts a Windows PowerShell background job.</span></span>

[<span data-ttu-id="41259-144">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="41259-144">Stop-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

<span data-ttu-id="41259-145">Windows PowerShell バックグラウンド ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="41259-145">Stops a Windows PowerShell background job.</span></span>

[<span data-ttu-id="41259-146">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="41259-146">Wait-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

<span data-ttu-id="41259-147">セッションで実行されている 1 つまたはすべての Windows PowerShell のバックグラウンド ジョブが完了するまでは、コマンド プロンプトが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="41259-147">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are complete.</span></span>

## <a name="see-also"></a><span data-ttu-id="41259-148">参照</span><span class="sxs-lookup"><span data-stu-id="41259-148">See Also</span></span>

[<span data-ttu-id="41259-149">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="41259-149">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
