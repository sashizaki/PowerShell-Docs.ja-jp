---
description: ワークフローでチェックポイントを取得する Checkpoint-Workflow アクティビティについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_checkpoint-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Checkpoint ワークフロー
ms.openlocfilehash: 223deb07ff6ed387cf04736116ea0ce3f998bb59
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221912"
---
# <a name="about-checkpoint-workflow"></a><span data-ttu-id="ad0d1-104">Checkpoint-Workflow について</span><span class="sxs-lookup"><span data-stu-id="ad0d1-104">About Checkpoint-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="ad0d1-105">概要</span><span class="sxs-lookup"><span data-stu-id="ad0d1-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ad0d1-106">ワークフローでチェックポイントを取得する Checkpoint-Workflow アクティビティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-106">Describes the Checkpoint-Workflow activity, which takes a checkpoint in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="ad0d1-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="ad0d1-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ad0d1-108">Checkpoint-Workflow アクティビティはチェックポイントを取得します。これにより、状態とデータがワークフローに保存されます。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-108">The Checkpoint-Workflow activity takes a checkpoint, which saves state and data in the workflow.</span></span> <span data-ttu-id="ad0d1-109">ワークフローが中断または中断された場合は、再起動するのではなく、最新のチェックポイントから再開できます。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-109">If the workflow is suspended or interrupted, it can be resumed from the most recent checkpoint, rather than having to be restarted.</span></span>

<span data-ttu-id="ad0d1-110">Checkpoint-Workflow アクティビティは、ワークフローでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-110">The Checkpoint-Workflow activity is valid only in a workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="ad0d1-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ad0d1-111">SYNTAX</span></span>

```
Workflow <Verb-Noun>
{
    Checkpoint-Workflow
}
```

<span data-ttu-id="ad0d1-112">Checkpoint-Workflow アクティビティは、共通パラメーターやワークフロー共通パラメーターを含むパラメーターを一切受け入れません。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-112">The Checkpoint-Workflow activity does not accept any parameters, including common parameters and workflow common parameters.</span></span>

<span data-ttu-id="ad0d1-113">Checkpoint-Activity チェックポイントは、表示可能なバインドまたは Param ステートメントの後に、ワークフローの任意の場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-113">You can place the Checkpoint-Activity checkpoint anywhere in a workflow after the CmdletBinding or Param statement.</span></span> <span data-ttu-id="ad0d1-114">ただし、チェックポイントを配置する場合は、データを収集し、ワークフローを実行しているコンピューターのディスクに書き込むというパフォーマンスコストを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-114">However, when placing checkpoints, consider the performance cost of collecting the data and writing it to disk on the computer that is running the workflow.</span></span>

<span data-ttu-id="ad0d1-115">中断されたワークフローのセクションを再実行する時間が、チェックポイントの状態とデータをディスクに書き込む時間を超えることを必ず確認します。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-115">Be sure that the time it takes to rerun a section of the workflow if it is interrupted is greater than the time it takes to write the checkpoint state and data to disk.</span></span>

<span data-ttu-id="ad0d1-116">重要な手順の後にチェックポイントを作成することを検討してください。再起動するのではなく、ワークフローを再開できます。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-116">Consider taking checkpoints after critical steps so the workflow can be resumed rather than restarted.</span></span> <span data-ttu-id="ad0d1-117">たとえば、べき等ではないコマンドの後にチェックポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-117">For example, take a checkpoint after commands that are not idempotent.</span></span>

### <a name="about-checkpoints"></a><span data-ttu-id="ad0d1-118">チェックポイントについて</span><span class="sxs-lookup"><span data-stu-id="ad0d1-118">ABOUT CHECKPOINTS</span></span>

<span data-ttu-id="ad0d1-119">"チェックポイント" とは、変数の現在の値などのワークフローの状態と、そのポイントまでに生成された出力のことで、ディスクに保存されます。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-119">A checkpoint is a snapshot of the current state of the workflow, including the current values of variables, and any output generated up to that point, and it saves it to disk.</span></span>

<span data-ttu-id="ad0d1-120">意図的または意図せずにワークフローが中断された場合、Windows PowerShell ワークフローは、最新のチェックポイントのデータを自動的に使用して、ワークフローの復旧と再開を行います。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-120">If a workflow is interrupted, intentionally or unintentionally, Windows PowerShell Workflow automatically uses the data in newest checkpoint to recover and resume the workflow.</span></span>

<span data-ttu-id="ad0d1-121">AsJob ワークフロー共通パラメーターなどを使用してワークフローをジョブとして実行する場合、ワークフローチェックポイントは、Remove-Job コマンドレットを使用してなど、ジョブを削除するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-121">When you run the workflow as a job, such as by using the AsJob workflow common parameter, the workflow checkpoints are retained until you delete the job, such as by using the Remove-Job cmdlet.</span></span>
<span data-ttu-id="ad0d1-122">それ以外の場合、ワークフローのチェックポイントは、ワークフローが完了すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-122">Otherwise, workflow checkpoints are deleted when the workflow completes.</span></span>

### <a name="other-checkpointing-techniques"></a><span data-ttu-id="ad0d1-123">その他のチェックポイント方法</span><span class="sxs-lookup"><span data-stu-id="ad0d1-123">OTHER CHECKPOINTING TECHNIQUES</span></span>

<span data-ttu-id="ad0d1-124">Windows PowerShell ワークフローでは、Checkpoint-Workflow アクティビティに加えて、次のようなチェックポイント処理手法もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-124">In addition to the Checkpoint-Workflow activity, Windows PowerShell Workflow supports other checkpointing techniques, including the following:</span></span>

- <span data-ttu-id="ad0d1-125">PSPersist ワークフロー共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad0d1-125">PSPersist workflow common parameter</span></span>
- <span data-ttu-id="ad0d1-126">PSPersist アクティビティ共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad0d1-126">PSPersist activity common parameter</span></span>
- <span data-ttu-id="ad0d1-127">PSPersistPreference 変数 (ワークフロー内)</span><span class="sxs-lookup"><span data-stu-id="ad0d1-127">PSPersistPreference variable (in a workflow)</span></span>

<span data-ttu-id="ad0d1-128">ワークフローにチェックポイントを追加する方法の詳細については、「ワークフローにチェックポイントを追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-128">For more information about adding a checkpoint to a workflow, see "How to Add Checkpoints to a Workflow."</span></span>

## <a name="examples"></a><span data-ttu-id="ad0d1-129">例</span><span class="sxs-lookup"><span data-stu-id="ad0d1-129">EXAMPLES</span></span>

<span data-ttu-id="ad0d1-130">次のワークフローには、実行時間の長い関数を完了した後の Checkpoint-Workflow アクティビティの呼び出しと、データを共有するスクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad0d1-130">The following workflow includes a call to the Checkpoint-Workflow activity after completing a long-running function and a script that share data.</span></span>

```powershell
Workflow Test-Workflow
{
    $a = Invoke-LongRunningFunction
    InlineScript { \\Server\Share\Get-DataPacks.ps1 $Using:a}
    Checkpoint-Workflow

    Invoke-LongRunningFunction
    {
        ...
    }
}
```

## <a name="see-also"></a><span data-ttu-id="ad0d1-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad0d1-131">SEE ALSO</span></span>

[<span data-ttu-id="ad0d1-132">Windows PowerShell ワークフローを記述する</span><span class="sxs-lookup"><span data-stu-id="ad0d1-132">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
