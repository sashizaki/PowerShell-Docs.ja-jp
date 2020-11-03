---
description: '`ForEach -Parallel`Windows PowerShell ワークフローの言語構成要素について説明します。'
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_foreach-parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach 並列
ms.openlocfilehash: 1012b45396b65d424dacac067c2af8d3b6823f92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221907"
---
# <a name="about-foreach-parallel"></a><span data-ttu-id="ea877-104">Foreach-Parallel について</span><span class="sxs-lookup"><span data-stu-id="ea877-104">About Foreach-Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="ea877-105">概要</span><span class="sxs-lookup"><span data-stu-id="ea877-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ea877-106">`ForEach -Parallel`Windows PowerShell ワークフローの言語構成要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea877-106">Describes the `ForEach -Parallel` language construct in Windows PowerShell Workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="ea877-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="ea877-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ea877-108">キーワードの **Parallel** パラメーターは、 `ForEach` `ForEach` 指定されたコレクション内の各項目に対して、スクリプトブロック内のコマンドを1回実行します。</span><span class="sxs-lookup"><span data-stu-id="ea877-108">The **Parallel** parameter of the `ForEach` keyword runs the commands in a `ForEach` script block once for each item in a specified collection.</span></span>

<span data-ttu-id="ea877-109">ディスクのコレクション内のディスクなど、コレクション内の項目は並行して処理されます。</span><span class="sxs-lookup"><span data-stu-id="ea877-109">The items in the collection, such as a disk in a collection of disks, are processed in parallel.</span></span> <span data-ttu-id="ea877-110">スクリプトブロック内のコマンドは、コレクション内の各項目に対して順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="ea877-110">The commands in the script block run sequentially on each item in the collection.</span></span>

<span data-ttu-id="ea877-111">`ForEach -Parallel` は、Windows PowerShell ワークフローでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ea877-111">`ForEach -Parallel` is valid only in a Windows PowerShell Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="ea877-112">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea877-112">SYNTAX</span></span>

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a><span data-ttu-id="ea877-113">詳細説明</span><span class="sxs-lookup"><span data-stu-id="ea877-113">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="ea877-114">Windows PowerShell の ForEach ステートメントと同様に、コレクションを含む変数は、 `$<collection>` ステートメントの前に定義する必要があり `ForEach -Parallel` ますが、現在のアイテムを表す変数は、ステートメントで定義されてい `$<item>` `ForEach -Parallel` ます。</span><span class="sxs-lookup"><span data-stu-id="ea877-114">Like the ForEach statement in Windows PowerShell, the variable that contains collection `$<collection>` must be defined before the `ForEach -Parallel` statement, but the variable that represents the current item `$<item>` is defined in the `ForEach -Parallel` statement.</span></span>

<span data-ttu-id="ea877-115">`ForEach -Parallel`コンストラクトは、 `ForEach` キーワードと **Parallel** パラメーターとは異なります。</span><span class="sxs-lookup"><span data-stu-id="ea877-115">The `ForEach -Parallel` construct is different from the `ForEach` keyword and the **Parallel** parameter.</span></span> <span data-ttu-id="ea877-116">キーワードは、 `ForEach` コレクション内の項目を順番に処理します。</span><span class="sxs-lookup"><span data-stu-id="ea877-116">The `ForEach` keyword processes the items in the collection in sequence.</span></span> <span data-ttu-id="ea877-117">**Parallel** パラメーターは、スクリプトブロック内のコマンドを並列で実行します。</span><span class="sxs-lookup"><span data-stu-id="ea877-117">The **Parallel** parameter runs commands in a script block in parallel.</span></span> <span data-ttu-id="ea877-118">並列スクリプトブロックは、スクリプトブロックで囲むことができ `ForEach -Parallel` ます。</span><span class="sxs-lookup"><span data-stu-id="ea877-118">You can enclose a Parallel script block in a `ForEach -Parallel` script block.</span></span>

<span data-ttu-id="ea877-119">ワークフロー内の対象コンピューター ( **PSComputerName** workflow 共通パラメーターによって指定されたものなど) は、常に並列で処理されます。</span><span class="sxs-lookup"><span data-stu-id="ea877-119">The target computers in a workflow, such as those specified by the **PSComputerName** workflow common parameter, are always processed in parallel.</span></span>
<span data-ttu-id="ea877-120">この目的のためにキーワードを指定する必要はありません `ForEach -Parallel` 。</span><span class="sxs-lookup"><span data-stu-id="ea877-120">You do not need to specify the `ForEach -Parallel` keyword for this purpose.</span></span>

### <a name="examples"></a><span data-ttu-id="ea877-121">例</span><span class="sxs-lookup"><span data-stu-id="ea877-121">EXAMPLES</span></span>

<span data-ttu-id="ea877-122">次のワークフローには、 `ForEach -Parallel` アクティビティが取得するディスクを処理するステートメントが含まれてい `Get-Disk` ます。</span><span class="sxs-lookup"><span data-stu-id="ea877-122">The following workflow contains a `ForEach -Parallel` statement that processes the disks that the `Get-Disk` activity gets.</span></span> <span data-ttu-id="ea877-123">スクリプトブロック内のコマンドは順番に実行され `ForEach -Parallel` ますが、ディスク上で並列実行されます。</span><span class="sxs-lookup"><span data-stu-id="ea877-123">The commands in the `ForEach -Parallel` script block run sequentially, but they run on the disks in parallel.</span></span> <span data-ttu-id="ea877-124">ディスクは、同時に、任意の順序で処理される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea877-124">The disks might be processed concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    $Disks = Get-Disk

    # The disks are processed in parallel.
    ForEach -Parallel ($Disk in $Disks)
    {
        # The commands run sequentially on each disk.
        $DiskPath = $Disk.Path
        $Disk | Initialize-Disk
        Set-Disk -Path $DiskPath
    }
}

workflow Test-Workflow
{
    #Run commands in parallel.
    Parallel
    {
        Get-Process
        Get-Service
    }

   $Disks = Get-Disk

   # The disks are processed in parallel.
   ForEach -Parallel ($Disk in $Disks)
   {
       # The commands run in parallel on each disk.
       Parallel
       {
           Initialize-Disk
           InlineScript {.\Get-DiskInventory}
       }
   }
}
```

## <a name="see-also"></a><span data-ttu-id="ea877-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea877-125">SEE ALSO</span></span>

[<span data-ttu-id="ea877-126">Writing a Script Workflow</span><span class="sxs-lookup"><span data-stu-id="ea877-126">Writing a Script Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[<span data-ttu-id="ea877-127">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="ea877-127">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[<span data-ttu-id="ea877-128">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="ea877-128">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="ea877-129">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="ea877-129">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="ea877-130">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="ea877-130">about_Workflows</span></span>](about_Workflows.md)
