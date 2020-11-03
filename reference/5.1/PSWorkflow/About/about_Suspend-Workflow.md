---
description: アクティビティについて説明し `Suspend-Workflow` ます。このアクティビティは、アクティビティが表示されるワークフローを中断します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_suspend-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Suspend ワークフロー
ms.openlocfilehash: cbe5386ae5aa4bd863079fde240ddf2ce5384727
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221864"
---
# <a name="about-suspend-workflow"></a><span data-ttu-id="c8dda-104">Suspend-Workflow について</span><span class="sxs-lookup"><span data-stu-id="c8dda-104">About Suspend-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="c8dda-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="c8dda-105">Short description</span></span>

<span data-ttu-id="c8dda-106">アクティビティについて説明し `Suspend-Workflow` ます。このアクティビティは、アクティビティが表示されるワークフローを中断します。</span><span class="sxs-lookup"><span data-stu-id="c8dda-106">Describes the `Suspend-Workflow` activity, which suspends the workflow in which the activity appears.</span></span>

## <a name="long-description"></a><span data-ttu-id="c8dda-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="c8dda-107">Long description</span></span>

<span data-ttu-id="c8dda-108">アクティビティは、ワークフロー `Suspend-Workflow` 内からワークフロー処理を一時的に停止します。</span><span class="sxs-lookup"><span data-stu-id="c8dda-108">The `Suspend-Workflow` activity temporarily stops workflow processing from within the workflow.</span></span> <span data-ttu-id="c8dda-109">中断する前に、Windows PowerShell ワークフローはチェックポイントを取得して、ワークフローの状態とデータが保持され、ワークフローが中断ポイントから再開できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c8dda-109">Before suspending, Windows PowerShell Workflow takes a checkpoint so the workflow's state and data are preserved and the workflow can resume from the suspension point.</span></span>

<span data-ttu-id="c8dda-110">ワークフローを再開するには、ワークフローを実行するユーザーがコマンドレットを使用し `Resume-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="c8dda-110">To resume the workflow, the user running the workflow uses the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="c8dda-111">ワークフロー内からワークフローを再開することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8dda-111">You can't resume a workflow from within the workflow.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8dda-112">構文</span><span class="sxs-lookup"><span data-stu-id="c8dda-112">Syntax</span></span>

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a><span data-ttu-id="c8dda-113">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="c8dda-113">Detailed description</span></span>

<span data-ttu-id="c8dda-114">は、 `Suspend-Workflow` ワークフローを一時的に停止し、ワークフロージョブを表すジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c8dda-114">The `Suspend-Workflow` temporarily stops the workflow and returns a job object that represents the workflow job.</span></span> <span data-ttu-id="c8dda-115">ジョブとしてワークフローを実行していない場合でも、ジョブオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="c8dda-115">A job object is returned even if you didn't run the workflow as a job.</span></span> <span data-ttu-id="c8dda-116">たとえば、 **AsJob** workflow 共通パラメーターを使用するなどです。</span><span class="sxs-lookup"><span data-stu-id="c8dda-116">For example, such as by using the **AsJob** workflow common parameter.</span></span> <span data-ttu-id="c8dda-117">ジョブの状態は **中断** されています。</span><span class="sxs-lookup"><span data-stu-id="c8dda-117">The job state is **Suspended**.</span></span>

<span data-ttu-id="c8dda-118">Job コマンドレットを使用して、中断されたワークフロージョブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c8dda-118">You can use the job cmdlets to manage the suspended workflow job.</span></span> <span data-ttu-id="c8dda-119">ワークフロージョブを再開するには、 `Resume-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dda-119">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span>

<span data-ttu-id="c8dda-120">ワークフロージョブを再開すると、アクティビティの後のコマンドでワークフローが再開され `Suspend-Workflow` ます。</span><span class="sxs-lookup"><span data-stu-id="c8dda-120">When you resume the workflow job, the workflow resumes at the command that follows the `Suspend-Workflow` activity.</span></span>

<span data-ttu-id="c8dda-121">たとえば、次のワークフローにはアクティビティが含まれてい `Suspend-Workflow` ます。</span><span class="sxs-lookup"><span data-stu-id="c8dda-121">For example, the following workflow includes the `Suspend-Workflow` activity.</span></span>
<span data-ttu-id="c8dda-122">ワークフローを実行すると、アクティビティが実行され、その出力が変数に保存された後、ワークフローが中断され、中断された `Get-Date` `$a` ワークフローを表すジョブオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="c8dda-122">When you run the workflow, it runs the `Get-Date` activity, saves its output in the `$a` variable, and then suspends the workflow, and returns a job object that represents the suspended workflow.</span></span> <span data-ttu-id="c8dda-123">ジョブの種類は **Psworkflowjob** です。</span><span class="sxs-lookup"><span data-stu-id="c8dda-123">The job type is **PSWorkflowJob**.</span></span>

<span data-ttu-id="c8dda-124">などのジョブコマンドレットを使用して、 `Get-Job` ワークフロージョブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c8dda-124">You can use the job cmdlets, such as `Get-Job`, to manage the workflow job.</span></span>

```powershell
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

Test-Suspend
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Suspended  True         localhost Test-Suspend
```

## <a name="resuming-a-workflow-job"></a><span data-ttu-id="c8dda-125">ワークフロージョブの再開</span><span class="sxs-lookup"><span data-stu-id="c8dda-125">Resuming a workflow job</span></span>

<span data-ttu-id="c8dda-126">ワークフロージョブを再開するには、 `Resume-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8dda-126">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="c8dda-127">`Resume-Job` コマンドレットは、ワークフロー ジョブ オブジェクトを即座に返します (まだ再開されていない場合でも)。</span><span class="sxs-lookup"><span data-stu-id="c8dda-127">The `Resume-Job` cmdlet returns the workflow job object immediately, even though it might not yet be resumed.</span></span> <span data-ttu-id="c8dda-128">ジョブが再開されるまで待機するには、 **wait** パラメーターを使用するか、コマンドレットを使用して `Get-Job` 現在のジョブオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="c8dda-128">To wait for the job to be resumed, use the **Wait** parameter, or use the `Get-Job` cmdlet to get the current job object.</span></span>

```powershell
Resume-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State    HasMoreData  Location  Command
--  ----  -------------  -----    -----------  --------  -------
8   Job8  PSWorkflowJob  Running  True         localhost Test-Suspend
```

```powershell
Get-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Completed  True         localhost Test-Suspend
```

## <a name="getting-the-output-of-a-workflow-job"></a><span data-ttu-id="c8dda-129">ワークフロージョブの出力の取得</span><span class="sxs-lookup"><span data-stu-id="c8dda-129">Getting the output of a workflow job</span></span>

<span data-ttu-id="c8dda-130">ワークフロージョブの出力を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="c8dda-130">To get the output of a workflow job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="c8dda-131">出力は、コマンドレットの後に続くコマンドでワークフローが再開されたことを示して `Suspend-Workflow` います。</span><span class="sxs-lookup"><span data-stu-id="c8dda-131">The output shows that the workflow resumed at the command that followed the `Suspend-Workflow` cmdlet.</span></span> <span data-ttu-id="c8dda-132">`$a`中断前に作成された変数の値は、再開時にワークフローで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8dda-132">The value of the `$a` variable, which was populated before the suspension, is available to the workflow when it resumes.</span></span>

```powershell
Get-Job -Name Job8 | Receive-Job
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 19
Milliseconds      : 823
Ticks             : 198230041
TotalDays         : 0.000229432917824074
TotalHours        : 0.00550639002777778
TotalMinutes      : 0.330383401666667
TotalSeconds      : 19.8230041
TotalMilliseconds : 19823.0041
PSComputerName    : localhost
```

## <a name="see-also"></a><span data-ttu-id="c8dda-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8dda-133">See also</span></span>

[<span data-ttu-id="c8dda-134">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="c8dda-134">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="c8dda-135">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="c8dda-135">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="c8dda-136">[Psworkflow](xref:PSWorkflow) コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c8dda-136">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="c8dda-137">ワークフロー ガイド</span><span class="sxs-lookup"><span data-stu-id="c8dda-137">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="c8dda-138">Windows PowerShell ワークフローを記述する</span><span class="sxs-lookup"><span data-stu-id="c8dda-138">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
