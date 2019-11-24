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
ms.openlocfilehash: a663bd69be7825b1685f64ff8d3068bdd8ca3265
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367781"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="0a6cc-102">関数にコメント ベースのヘルプを配置する</span><span class="sxs-lookup"><span data-stu-id="0a6cc-102">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="0a6cc-103">このトピックでは、`Get-Help` コマンドレットによってコメントベースのヘルプトピックが適切な関数に関連付けられるように、関数のコメントベースのヘルプを配置する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-103">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="0a6cc-104">関数のコメントベースのヘルプを配置する場所</span><span class="sxs-lookup"><span data-stu-id="0a6cc-104">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="0a6cc-105">関数本体の先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-105">At the beginning of the function body.</span></span>

- <span data-ttu-id="0a6cc-106">関数本体の末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-106">At the end of the function body.</span></span>

- <span data-ttu-id="0a6cc-107">`Function` キーワードの前。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-107">Before the `Function` keyword.</span></span> <span data-ttu-id="0a6cc-108">関数がスクリプトモジュールまたはスクリプトモジュール内にある場合は、コメントベースのヘルプの最後の行と `Function` キーワードの間に複数の空白行を入れることはできません。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-108">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="0a6cc-109">それ以外の場合、`Get-Help` は、関数ではなく、スクリプトにヘルプを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-109">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="0a6cc-110">関数内のヘルプの配置例</span><span class="sxs-lookup"><span data-stu-id="0a6cc-110">Examples of Help Placement in a Function</span></span>

 <span data-ttu-id="0a6cc-111">次の例では、関数のコメントベースのヘルプの3つの配置オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-111">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="0a6cc-112">関数本体の先頭のヘルプ</span><span class="sxs-lookup"><span data-stu-id="0a6cc-112">Help at the Beginning of a Function Body</span></span>

 <span data-ttu-id="0a6cc-113">次の例では、関数本体の先頭にあるコメントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-113">The following example shows comment-based at the beginning of a function body.</span></span>

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

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="0a6cc-114">関数本体の最後のヘルプ</span><span class="sxs-lookup"><span data-stu-id="0a6cc-114">Help at the End of a Function Body</span></span>

 <span data-ttu-id="0a6cc-115">次の例では、関数本体の最後にコメントを使用してコメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-115">The following example shows comment-based at the end of a function body.</span></span>

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

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="0a6cc-116">Function キーワードの前のヘルプ</span><span class="sxs-lookup"><span data-stu-id="0a6cc-116">Help Before the Function Keyword</span></span>

 <span data-ttu-id="0a6cc-117">次の例では、関数キーワードの前の行に基づいてコメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="0a6cc-117">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell

<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}

```