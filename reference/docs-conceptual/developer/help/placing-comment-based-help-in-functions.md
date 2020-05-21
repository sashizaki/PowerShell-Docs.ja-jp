---
title: 関数にコメントベースのヘルプを配置する |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec7159e-e4e9-4b21-95df-94244432f679
caps.latest.revision: 5
ms.openlocfilehash: 898225a582c7ed25f746dec7f84012db1ae60b98
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557068"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="e6088-102">関数にコメント ベースのヘルプを配置する</span><span class="sxs-lookup"><span data-stu-id="e6088-102">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="e6088-103">このトピックでは、コマンドレットによって `Get-Help` コメントベースのヘルプトピックが適切な関数に関連付けられるように、関数のコメントベースのヘルプを配置する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6088-103">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="e6088-104">関数のコメントベースのヘルプを配置する場所</span><span class="sxs-lookup"><span data-stu-id="e6088-104">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="e6088-105">関数本体の先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="e6088-105">At the beginning of the function body.</span></span>

- <span data-ttu-id="e6088-106">関数本体の末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="e6088-106">At the end of the function body.</span></span>

- <span data-ttu-id="e6088-107">キーワードの前 `Function` 。</span><span class="sxs-lookup"><span data-stu-id="e6088-107">Before the `Function` keyword.</span></span> <span data-ttu-id="e6088-108">関数がスクリプトまたはスクリプトモジュール内にある場合は、コメントベースのヘルプとキーワードの最後の行の間に複数の空白行を入れることはできません `Function` 。</span><span class="sxs-lookup"><span data-stu-id="e6088-108">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="e6088-109">それ以外の場合は、 `Get-Help` 関数ではなく、スクリプトにヘルプを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e6088-109">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="e6088-110">関数内のヘルプの配置例</span><span class="sxs-lookup"><span data-stu-id="e6088-110">Examples of Help Placement in a Function</span></span>

 <span data-ttu-id="e6088-111">次の例では、関数のコメントベースのヘルプの3つの配置オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e6088-111">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="e6088-112">関数本体の先頭のヘルプ</span><span class="sxs-lookup"><span data-stu-id="e6088-112">Help at the Beginning of a Function Body</span></span>

 <span data-ttu-id="e6088-113">次の例では、関数本体の先頭にあるコメントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="e6088-113">The following example shows comment-based at the beginning of a function body.</span></span>

```powershell

function MyProcess
{
    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>

    Get-Process powershell
}

```

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="e6088-114">関数本体の最後のヘルプ</span><span class="sxs-lookup"><span data-stu-id="e6088-114">Help at the End of a Function Body</span></span>

 <span data-ttu-id="e6088-115">次の例では、関数本体の最後にコメントを使用してコメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="e6088-115">The following example shows comment-based at the end of a function body.</span></span>

```powershell

function MyFunction
{
    Get-Process powershell

    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>
}

```

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="e6088-116">Function キーワードの前のヘルプ</span><span class="sxs-lookup"><span data-stu-id="e6088-116">Help Before the Function Keyword</span></span>

 <span data-ttu-id="e6088-117">次の例では、関数キーワードの前の行に基づいてコメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="e6088-117">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell

<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}

```
