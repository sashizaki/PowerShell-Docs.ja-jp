---
description: '`Sequence`選択されたアクティビティを順番に実行するキーワードについて説明します。'
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_sequence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Sequence
ms.openlocfilehash: a9dd4fb24274fe4e1478ca69c734b43a2f196792
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221883"
---
# <a name="about-sequence"></a><span data-ttu-id="c560b-104">シーケンスについて</span><span class="sxs-lookup"><span data-stu-id="c560b-104">About Sequence</span></span>

## <a name="short-description"></a><span data-ttu-id="c560b-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="c560b-105">Short description</span></span>

<span data-ttu-id="c560b-106">`Sequence`選択されたアクティビティを順番に実行するキーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c560b-106">Describes the `Sequence` keyword that runs selected activities sequentially.</span></span>

## <a name="long-description"></a><span data-ttu-id="c560b-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="c560b-107">Long description</span></span>

<span data-ttu-id="c560b-108">キーワードは、 `Sequence` 選択したワークフローアクティビティを順番に実行します。</span><span class="sxs-lookup"><span data-stu-id="c560b-108">The `Sequence` keyword runs selected workflow activities sequentially.</span></span> <span data-ttu-id="c560b-109">ワークフローアクティビティは、表示される順序で実行され、同時に実行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c560b-109">Workflow activities run in the order that they appear and do not run concurrently.</span></span> <span data-ttu-id="c560b-110">`Sequence`キーワードは、PowerShell ワークフローでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c560b-110">The `Sequence` keyword is only valid in a PowerShell Workflow.</span></span>

<span data-ttu-id="c560b-111">キーワードは、 `Sequence` `Parallel` 選択したコマンドを順番に実行するために、スクリプトブロックで使用されます。</span><span class="sxs-lookup"><span data-stu-id="c560b-111">The `Sequence` keyword is used in a `Parallel` script block to run selected commands sequentially.</span></span>

<span data-ttu-id="c560b-112">ワークフローアクティビティは既定では順番に実行されるため、 `Sequence` キーワードはスクリプトブロックでのみ有効です `Parallel` 。</span><span class="sxs-lookup"><span data-stu-id="c560b-112">Because workflow activities run sequentially by default, the `Sequence` keyword is only effective in a `Parallel` script block.</span></span> <span data-ttu-id="c560b-113">キーワードが `Sequence` スクリプトブロックに含まれていない場合は `Parallel` 有効ですが、無効になります。</span><span class="sxs-lookup"><span data-stu-id="c560b-113">If the `Sequence` keyword isn't included in a `Parallel` script block, it's valid but ineffective.</span></span>

<span data-ttu-id="c560b-114">スクリプトブロックを使用すると、 `Sequence` 依存するコマンドを順番に実行できるため、より多くのコマンドを並列で実行できます。</span><span class="sxs-lookup"><span data-stu-id="c560b-114">The `Sequence` script block lets you run more commands in parallel by allowing you to run dependent commands sequentially.</span></span>

## <a name="syntax"></a><span data-ttu-id="c560b-115">構文</span><span class="sxs-lookup"><span data-stu-id="c560b-115">Syntax</span></span>

### <a name="workflow-using-sequence"></a><span data-ttu-id="c560b-116">Sequence を使用したワークフロー</span><span class="sxs-lookup"><span data-stu-id="c560b-116">Workflow using Sequence</span></span>

```
workflow <Verb-Noun>
{
    Sequence
    {
        [<Activity>]
        [<Activity>]
        # ...
    }
}
```

### <a name="workflow-using-parallel-and-sequence"></a><span data-ttu-id="c560b-117">Parallel と Sequence を使用したワークフロー</span><span class="sxs-lookup"><span data-stu-id="c560b-117">Workflow using Parallel and Sequence</span></span>

```
workflow <Verb-Noun>
{
    Parallel
    {
        [<Activity>]
        Sequence
        {
            [<Activity>]
            [<Activity>]
            # ...
        }
    }
}
```

## <a name="detailed-description"></a><span data-ttu-id="c560b-118">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="c560b-118">Detailed description</span></span>

<span data-ttu-id="c560b-119">`Parallel` スクリプト ブロックのコマンドは、同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="c560b-119">The commands in a `Parallel` script block can run concurrently.</span></span> <span data-ttu-id="c560b-120">実行される順序は決まっていません。</span><span class="sxs-lookup"><span data-stu-id="c560b-120">The order in which they run is not determined.</span></span> <span data-ttu-id="c560b-121">この機能により、スクリプトワークフローのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="c560b-121">This feature improves the performance of a script workflow.</span></span>

<span data-ttu-id="c560b-122">スクリプトブロックを使用すると `Sequence` 、アクティビティがスクリプトブロックに含まれていても、選択したアクティビティを順番に実行でき `Parallel` ます。</span><span class="sxs-lookup"><span data-stu-id="c560b-122">You can use a `Sequence` script block to run selected activities sequentially, even though the activities appear in a `Parallel` script block.</span></span>

<span data-ttu-id="c560b-123">スクリプトブロック内のアクティビティは、 `Sequence` 一覧表示されている順序で連続して実行されます。</span><span class="sxs-lookup"><span data-stu-id="c560b-123">The activities in a `Sequence` script block run consecutively in the order that they are listed.</span></span> <span data-ttu-id="c560b-124">スクリプトブロック内のアクティビティは `Sequence` 、前のアクティビティが完了した後にのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="c560b-124">An activity in a `Sequence` script block starts only after the previous activity completes.</span></span>

<span data-ttu-id="c560b-125">ただし、スクリプトブロックにスクリプトブロックが含まれている場合は、スクリプトブロックの `Sequence` `Parallel` 実行順序が決定され `Sequence` ません。</span><span class="sxs-lookup"><span data-stu-id="c560b-125">However, when the `Sequence` script block appears in a `Parallel` script block, the order in which the `Sequence` script block runs isn't determined.</span></span> <span data-ttu-id="c560b-126">スクリプトブロック内の他のアクティビティの前、後、または同時実行が実行される可能性があり `Parallel` ます。</span><span class="sxs-lookup"><span data-stu-id="c560b-126">It might run before, after, or concurrent with other activities in the `Parallel` script block.</span></span>

<span data-ttu-id="c560b-127">たとえば、次のワークフローには、 `Parallel` コンピューター上のプロセスとサービスを取得するアクティビティを実行するスクリプトブロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c560b-127">For example, the following workflow includes a `Parallel` script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="c560b-128">`Parallel`スクリプトブロックには、 `Sequence` ファイルから情報を取得し、その情報をスクリプトへの入力として使用するスクリプトブロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c560b-128">The `Parallel` script block contains a `Sequence` script block that gets information from a file and uses the information as input to a script.</span></span>

<span data-ttu-id="c560b-129">`Get-Process`、 `Get-Service` 、および修正プログラムに関連するコマンドは、互いに独立しています。</span><span class="sxs-lookup"><span data-stu-id="c560b-129">The `Get-Process`, `Get-Service`, and hotfix-related commands are independent of each other.</span></span> <span data-ttu-id="c560b-130">これらのコマンドは、同時に、または任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="c560b-130">The commands can run concurrently or in any order.</span></span> <span data-ttu-id="c560b-131">ただし、修正プログラムの情報を取得するコマンドは、その情報を使用するコマンドの前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c560b-131">But, the command that gets the hotfix information must run before the command that uses it.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
    Get-Process
    Get-Service

    Sequence
    {
        $Hotfix = Get-Content 'D:\HotFixes\Required.txt'
        Foreach ($h in $Hotfix) {'D:\Scripts\Verify-Hotfix' -Hotfix $h}
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="c560b-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="c560b-132">See also</span></span>

[<span data-ttu-id="c560b-133">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="c560b-133">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="c560b-134">about_ForEach-並列</span><span class="sxs-lookup"><span data-stu-id="c560b-134">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="c560b-135">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="c560b-135">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="c560b-136">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="c560b-136">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="c560b-137">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="c560b-137">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="c560b-138">Windows PowerShell スクリプトを利用してワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="c560b-138">Creating a Workflow by Using a Windows PowerShell Script</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
