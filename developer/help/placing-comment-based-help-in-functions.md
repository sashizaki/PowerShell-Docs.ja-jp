---
title: 関数のコメント ベースのヘルプを配置する |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec7159e-e4e9-4b21-95df-94244432f679
caps.latest.revision: 5
ms.openlocfilehash: a663bd69be7825b1685f64ff8d3068bdd8ca3265
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083197"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="3e778-102">関数にコメント ベースのヘルプを配置する</span><span class="sxs-lookup"><span data-stu-id="3e778-102">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="3e778-103">このトピックでは、関数のコメント ベースのヘルプを配置する場所を説明しますように、`Get-Help`コマンドレットは、適切な関数をコメント ベースのヘルプ トピックを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3e778-103">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="3e778-104">関数のコメント ベースのヘルプを配置する場所</span><span class="sxs-lookup"><span data-stu-id="3e778-104">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="3e778-105">関数本体の先頭にします。</span><span class="sxs-lookup"><span data-stu-id="3e778-105">At the beginning of the function body.</span></span>

- <span data-ttu-id="3e778-106">関数本体の末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="3e778-106">At the end of the function body.</span></span>

- <span data-ttu-id="3e778-107">前に、`Function`キーワード。</span><span class="sxs-lookup"><span data-stu-id="3e778-107">Before the `Function` keyword.</span></span> <span data-ttu-id="3e778-108">コメント ベースのヘルプの最後の行の間で 1 つ以上の空白行が存在することはできません、関数は、スクリプトまたはスクリプト モジュールが、および`Function`キーワード。</span><span class="sxs-lookup"><span data-stu-id="3e778-108">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="3e778-109">それ以外の場合、`Get-Help`スクリプトを使用して、関数ではなく、ヘルプを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3e778-109">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="3e778-110">関数でヘルプの例</span><span class="sxs-lookup"><span data-stu-id="3e778-110">Examples of Help Placement in a Function</span></span>

 <span data-ttu-id="3e778-111">次の例は、各関数のコメント ベースのヘルプの次の 3 つの配置オプションを示します。</span><span class="sxs-lookup"><span data-stu-id="3e778-111">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="3e778-112">関数本体の先頭のヘルプします。</span><span class="sxs-lookup"><span data-stu-id="3e778-112">Help at the Beginning of a Function Body</span></span>

 <span data-ttu-id="3e778-113">次の例を示します関数本体の先頭にコメント ベースします。</span><span class="sxs-lookup"><span data-stu-id="3e778-113">The following example shows comment-based at the beginning of a function body.</span></span>

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

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="3e778-114">関数本体の末尾にあるヘルプします。</span><span class="sxs-lookup"><span data-stu-id="3e778-114">Help at the End of a Function Body</span></span>

 <span data-ttu-id="3e778-115">次の例では、コメント ベースの関数本体の末尾を示します。</span><span class="sxs-lookup"><span data-stu-id="3e778-115">The following example shows comment-based at the end of a function body.</span></span>

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

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="3e778-116">関数キーワードの前にヘルプします。</span><span class="sxs-lookup"><span data-stu-id="3e778-116">Help Before the Function Keyword</span></span>

 <span data-ttu-id="3e778-117">次の例を示します関数キーワードの前に行のコメント ベースします。</span><span class="sxs-lookup"><span data-stu-id="3e778-117">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell

<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}

```