---
title: 関数にコメント ベースのヘルプを配置する
ms.date: 09/12/2016
ms.openlocfilehash: c7a8f8db6c71fa2ef12aaa4df0f78815626ec8d6
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893205"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="40fb4-102">関数にコメント ベースのヘルプを配置する</span><span class="sxs-lookup"><span data-stu-id="40fb4-102">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="40fb4-103">このトピックでは、コマンドレットによって `Get-Help` コメントベースのヘルプトピックが適切な関数に関連付けられるように、関数のコメントベースのヘルプを配置する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="40fb4-103">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="40fb4-104">関数のコメントベースのヘルプを配置する場所</span><span class="sxs-lookup"><span data-stu-id="40fb4-104">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="40fb4-105">関数本体の先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="40fb4-105">At the beginning of the function body.</span></span>

- <span data-ttu-id="40fb4-106">関数本体の末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="40fb4-106">At the end of the function body.</span></span>

- <span data-ttu-id="40fb4-107">キーワードの前 `Function` 。</span><span class="sxs-lookup"><span data-stu-id="40fb4-107">Before the `Function` keyword.</span></span> <span data-ttu-id="40fb4-108">関数がスクリプトまたはスクリプトモジュール内にある場合は、コメントベースのヘルプとキーワードの最後の行の間に複数の空白行を入れることはできません `Function` 。</span><span class="sxs-lookup"><span data-stu-id="40fb4-108">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="40fb4-109">それ以外の場合は、 `Get-Help` 関数ではなく、スクリプトにヘルプを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="40fb4-109">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="40fb4-110">関数内のヘルプの配置例</span><span class="sxs-lookup"><span data-stu-id="40fb4-110">Examples of Help Placement in a Function</span></span>

<span data-ttu-id="40fb4-111">次の例では、関数のコメントベースのヘルプの3つの配置オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="40fb4-111">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="40fb4-112">関数本体の先頭のヘルプ</span><span class="sxs-lookup"><span data-stu-id="40fb4-112">Help at the Beginning of a Function Body</span></span>

<span data-ttu-id="40fb4-113">次の例では、関数本体の先頭にあるコメントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="40fb4-113">The following example shows comment-based at the beginning of a function body.</span></span>

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

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="40fb4-114">関数本体の最後のヘルプ</span><span class="sxs-lookup"><span data-stu-id="40fb4-114">Help at the End of a Function Body</span></span>

 <span data-ttu-id="40fb4-115">次の例では、関数本体の最後にコメントを使用してコメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="40fb4-115">The following example shows comment-based at the end of a function body.</span></span>

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

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="40fb4-116">Function キーワードの前のヘルプ</span><span class="sxs-lookup"><span data-stu-id="40fb4-116">Help Before the Function Keyword</span></span>

 <span data-ttu-id="40fb4-117">次の例では、関数キーワードの前の行に基づいてコメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="40fb4-117">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
