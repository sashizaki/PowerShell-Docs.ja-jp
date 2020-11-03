---
description: ワークフロー内のアクティビティを並列実行する Parallel キーワードについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parallel
ms.openlocfilehash: 402e93672bbea4ec9b6bfda8d608f266f6c40a21
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221891"
---
# <a name="about-parallel"></a><span data-ttu-id="ad3ee-104">並列について</span><span class="sxs-lookup"><span data-stu-id="ad3ee-104">About Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="ad3ee-105">概要</span><span class="sxs-lookup"><span data-stu-id="ad3ee-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ad3ee-106">ワークフロー内のアクティビティを並列実行する Parallel キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-106">Describes the Parallel keyword, which runs the activities in a workflow in parallel.</span></span>

## <a name="long-description"></a><span data-ttu-id="ad3ee-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="ad3ee-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ad3ee-108">Parallel キーワードは、ワークフローアクティビティを並行して実行します。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-108">The Parallel keyword runs workflow activities in parallel.</span></span> <span data-ttu-id="ad3ee-109">このキーワードは、Windows PowerShell ワークフローでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-109">This keyword is valid only in  Windows PowerShell  Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="ad3ee-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ad3ee-110">SYNTAX</span></span>

```
workflow <Verb-Noun>
{
     Parallel
     {
          [<Activity>]
          [<Activity>]
        ...
     }
 }
```

## <a name="detailed-description"></a><span data-ttu-id="ad3ee-111">詳細説明</span><span class="sxs-lookup"><span data-stu-id="ad3ee-111">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="ad3ee-112">Parallel スクリプト ブロックのコマンドは、同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-112">The commands in a Parallel script block can run concurrently.</span></span> <span data-ttu-id="ad3ee-113">実行される順序は決まっていません。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-113">The order in which they run is not determined.</span></span>

<span data-ttu-id="ad3ee-114">たとえば、次のワークフローには、コンピューターでプロセスやサービスを取得するアクティビティを実行する Parallel スクリプト ブロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-114">For example, the following workflow includes a Parallel script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="ad3ee-115">Get-Process と Get-Service のコマンドは互いに独立しているため、同時に、任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-115">Because the Get-Process and Get-Service commands are independent of each other, they can run concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
         Get-Process
         Get-Service
    }
}
```

<span data-ttu-id="ad3ee-116">コマンドを並列実行すると、非常に効率的で、ワークフローを完了するためにかかる時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-116">Running commands in parallel is very efficient and reduces the time it takes to complete a workflow significantly.</span></span>

<span data-ttu-id="ad3ee-117">並列スクリプトブロックで選択したコマンドを順番に実行するには、Sequence キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-117">To run selected commands in a Parallel script block in sequential order, use the Sequence keyword.</span></span> <span data-ttu-id="ad3ee-118">詳細については、「about_Sequence」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-118">For more information, see about_Sequence.</span></span>

<span data-ttu-id="ad3ee-119">コレクション内の項目に対して並列スクリプトブロックを実行するには、ForEach または ForEach-Parallel キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad3ee-119">To run a Parallel script block on items in a collection, use the ForEach or ForEach -Parallel keywords.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad3ee-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad3ee-120">SEE ALSO</span></span>

<span data-ttu-id="ad3ee-121">["スクリプトワークフローの作成"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="ad3ee-121">["Writing a Script Workflow"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span></span>

[<span data-ttu-id="ad3ee-122">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="ad3ee-122">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="ad3ee-123">about_ForEach-並列</span><span class="sxs-lookup"><span data-stu-id="ad3ee-123">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="ad3ee-124">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="ad3ee-124">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="ad3ee-125">about_Sequence</span><span class="sxs-lookup"><span data-stu-id="ad3ee-125">about_Sequence</span></span>](about_Sequence.md)

[<span data-ttu-id="ad3ee-126">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="ad3ee-126">about_Workflows</span></span>](about_workflows.md)
