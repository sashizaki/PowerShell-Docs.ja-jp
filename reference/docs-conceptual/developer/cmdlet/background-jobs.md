---
title: バックグラウンドジョブ |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0ef5ac9-8254-4832-ace8-84b356c10f08
caps.latest.revision: 13
ms.openlocfilehash: ff4fe159eedc47fc69f4d783cd90d2b0e888c0d5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363561"
---
# <a name="background-jobs"></a><span data-ttu-id="0b38c-102">バックグラウンド ジョブ</span><span class="sxs-lookup"><span data-stu-id="0b38c-102">Background Jobs</span></span>

<span data-ttu-id="0b38c-103">コマンドレットは、内部で、または Windows PowerShell の*バックグラウンドジョブ*としてアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0b38c-103">Cmdlets can perform their action internally or as a Windows PowerShell*background job*.</span></span> <span data-ttu-id="0b38c-104">コマンドレットをバックグラウンドジョブとして実行すると、その作業は、コマンドレットが使用しているパイプラインスレッドとは別に、独自のスレッドで非同期に実行されます。</span><span class="sxs-lookup"><span data-stu-id="0b38c-104">When a cmdlet runs as a background job, the work is done asynchronously in its own thread separate from the pipeline thread that the cmdlet is using.</span></span> <span data-ttu-id="0b38c-105">ユーザーの観点からは、コマンドレットをバックグラウンドジョブとして実行すると、ジョブの完了に時間がかかり、ジョブの実行中にユーザーが中断せずに続行できる場合でも、コマンドプロンプトが直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="0b38c-105">From the user perspective, when a cmdlet runs as a background job, the command prompt returns immediately even if the job takes an extended amount of time to complete, and the user can continue without interruption while the job runs.</span></span>

## <a name="background-jobs-child-jobs-and-the-job-repository"></a><span data-ttu-id="0b38c-106">バックグラウンドジョブ、子ジョブ、およびジョブリポジトリ</span><span class="sxs-lookup"><span data-stu-id="0b38c-106">Background Jobs, Child Jobs, and the Job Repository</span></span>

<span data-ttu-id="0b38c-107">バックグラウンドジョブをサポートするコマンドレットによって返されるジョブオブジェクトは、ジョブを定義します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-107">The job object that is returned by the cmdlets that support background jobs defines the job.</span></span> <span data-ttu-id="0b38c-108">( [Start ジョブ](/powershell/module/Microsoft.PowerShell.Core/Start-Job)コマンドレットは、ジョブオブジェクトも返します)。ジョブの名前、ジョブを指定するために使用される識別子、状態情報、および子ジョブがこの定義に含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b38c-108">(The [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet also returns a job object.) The name of the job, an identifier that is used to specify the job, the state information, and the child jobs are included in this definition.</span></span> <span data-ttu-id="0b38c-109">このジョブでは、作業は実行されません。</span><span class="sxs-lookup"><span data-stu-id="0b38c-109">The job does not perform any of the work.</span></span> <span data-ttu-id="0b38c-110">子ジョブによって実際の作業が実行されるため、各バックグラウンドジョブには少なくとも1つの子ジョブがあります。</span><span class="sxs-lookup"><span data-stu-id="0b38c-110">Each background job has at least one child job because the child job performs the actual work.</span></span> <span data-ttu-id="0b38c-111">作業がバックグラウンドジョブとして実行されるようにコマンドレットを実行する場合、このコマンドレットはジョブと子ジョブを、*ジョブリポジトリ*と呼ばれる共通リポジトリに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b38c-111">When you run a cmdlet so that the work is performed as a background job, the cmdlet must add the job and the child jobs to a common repository, referred to as the *job repository*.</span></span>

<span data-ttu-id="0b38c-112">コマンドラインでのバックグラウンドジョブの処理方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b38c-112">For more information about how background jobs are handled at the command line, see the following:</span></span>

- [<span data-ttu-id="0b38c-113">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="0b38c-113">about_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [<span data-ttu-id="0b38c-114">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="0b38c-114">about_Job_Details</span></span>](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [<span data-ttu-id="0b38c-115">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="0b38c-115">about_Remote_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a><span data-ttu-id="0b38c-116">バックグラウンドジョブとして実行されるコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="0b38c-116">Writing a Cmdlet That Runs as a Background Job</span></span>

<span data-ttu-id="0b38c-117">バックグラウンドジョブとして実行できるコマンドレットを作成するには、次のタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b38c-117">To write a cmdlet that can be run as a background job, you must complete the following tasks:</span></span>

- <span data-ttu-id="0b38c-118">コマンドレットをバックグラウンドジョブとして実行するかどうかをユーザーが決定できるように、`asJob` スイッチパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-118">Define an `asJob` switch parameter so that the user can decide whether to run the cmdlet as a background job.</span></span>

- <span data-ttu-id="0b38c-119">System.object[クラスから派生した](/dotnet/api/System.Management.Automation.Job)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-119">Create an object that derives from the [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) class.</span></span> <span data-ttu-id="0b38c-120">このオブジェクトには、カスタムジョブオブジェクト、または Windows PowerShell によって提供されるジョブオブジェクト ( [Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob)オブジェクトなど) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0b38c-120">This object can be a custom job object or a job object provided by Windows PowerShell, such as a [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) object.</span></span>

- <span data-ttu-id="0b38c-121">レコード処理メソッドで、コマンドレットをバックグラウンドジョブとして実行する必要があるかどうかを検出する `if` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-121">In a record processing method, add an `if` statement that detects whether the cmdlet should run as a background job.</span></span>

- <span data-ttu-id="0b38c-122">カスタムジョブオブジェクトの場合は、job クラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-122">For custom job objects, implement the job class.</span></span>

- <span data-ttu-id="0b38c-123">コマンドレットがバックグラウンドジョブとして実行されているかどうかに応じて、適切なオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-123">Return the appropriate objects, depending on whether the cmdlet is run as a background job.</span></span>

<span data-ttu-id="0b38c-124">コード例については、「[ジョブをサポートする方法](./how-to-support-jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b38c-124">For a code example, see [How to Support Jobs](./how-to-support-jobs.md).</span></span>

## <a name="background-job-related-apis"></a><span data-ttu-id="0b38c-125">バックグラウンドジョブに関連する Api</span><span class="sxs-lookup"><span data-stu-id="0b38c-125">Background Job-Related APIs</span></span>

<span data-ttu-id="0b38c-126">Windows PowerShell では、バックグラウンドジョブを管理するために次の Api が提供されています。</span><span class="sxs-lookup"><span data-stu-id="0b38c-126">The following APIs are provided by Windows PowerShell to manage background jobs.</span></span>

<span data-ttu-id="0b38c-127">System.string はカスタムジョブオブジェクト[を派生さ](/dotnet/api/System.Management.Automation.Job)せるものです。</span><span class="sxs-lookup"><span data-stu-id="0b38c-127">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) Derives custom job objects.</span></span> <span data-ttu-id="0b38c-128">これは抽象クラスです。</span><span class="sxs-lookup"><span data-stu-id="0b38c-128">This is an abstract class.</span></span>

<span data-ttu-id="0b38c-129">現在アクティブなバックグラウンドジョブに関する情報[を管理および](/dotnet/api/System.Management.Automation.JobRepository)提供します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-129">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) Manages and provides information about the current active background jobs.</span></span>

<span data-ttu-id="0b38c-130">[システムの管理. Jobstate](/dotnet/api/System.Management.Automation.JobState)は、バックグラウンドジョブの状態を定義します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-130">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) Defines the state of the background job.</span></span> <span data-ttu-id="0b38c-131">状態には、開始、実行中、停止が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b38c-131">States include Started, Running, and Stopped.</span></span>

<span data-ttu-id="0b38c-132">[システムの管理. Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo)は、バックグラウンドジョブの状態に関する情報を提供します。最後の状態変更がエラーによって発生した場合は、ジョブが現在の状態になった理由を示します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-132">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) Provides information about the state of a background job and, if the last state change was caused by an error, the reason the job entered its current state.</span></span>

<span data-ttu-id="0b38c-133">" [System. Automation. Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) " は、バックグラウンドジョブが状態を変更したときに発生するイベントの引数を提供します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-133">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) Provides the arguments for an event that is raised when a background job changes state.</span></span>

## <a name="windows-powershell-job-cmdlets"></a><span data-ttu-id="0b38c-134">Windows PowerShell ジョブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0b38c-134">Windows PowerShell Job Cmdlets</span></span>

<span data-ttu-id="0b38c-135">次のコマンドレットは、Windows PowerShell によってバックグラウンドジョブを管理するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="0b38c-135">The following cmdlets are provided by Windows PowerShell to manage background jobs.</span></span>

[<span data-ttu-id="0b38c-136">Get-Job</span><span class="sxs-lookup"><span data-stu-id="0b38c-136">Get-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

<span data-ttu-id="0b38c-137">現在のセッションで実行されている Windows PowerShell のバックグラウンド ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-137">Gets Windows PowerShell background jobs that are running in the current session.</span></span>

[<span data-ttu-id="0b38c-138">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="0b38c-138">Receive-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

<span data-ttu-id="0b38c-139">現在のセッションの Windows PowerShell バックグラウンド ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-139">Gets the results of the Windows PowerShell background jobs in the current session.</span></span>

[<span data-ttu-id="0b38c-140">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="0b38c-140">Remove-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

<span data-ttu-id="0b38c-141">Windows PowerShell バックグラウンド ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-141">Deletes a Windows PowerShell background job.</span></span>

[<span data-ttu-id="0b38c-142">Start-Job</span><span class="sxs-lookup"><span data-stu-id="0b38c-142">Start-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

<span data-ttu-id="0b38c-143">Windows PowerShell バックグラウンド ジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-143">Starts a Windows PowerShell background job.</span></span>

[<span data-ttu-id="0b38c-144">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="0b38c-144">Stop-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

<span data-ttu-id="0b38c-145">Windows PowerShell バックグラウンド ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="0b38c-145">Stops a Windows PowerShell background job.</span></span>

[<span data-ttu-id="0b38c-146">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="0b38c-146">Wait-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

<span data-ttu-id="0b38c-147">セッションで実行されている 1 つまたはすべての Windows PowerShell のバックグラウンド ジョブが完了するまでは、コマンド プロンプトが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="0b38c-147">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are complete.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b38c-148">参照</span><span class="sxs-lookup"><span data-stu-id="0b38c-148">See Also</span></span>

[<span data-ttu-id="0b38c-149">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="0b38c-149">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
