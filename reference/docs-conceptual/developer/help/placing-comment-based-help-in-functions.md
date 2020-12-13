---
ms.date: 09/12/2016
ms.topic: reference
title: 関数にコメント ベースのヘルプを配置する
description: 関数にコメント ベースのヘルプを配置する
ms.openlocfilehash: 3bd72f0c71d8f6ad54c43c99f044423c072fdeeb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658207"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="788fb-103">関数にコメント ベースのヘルプを配置する</span><span class="sxs-lookup"><span data-stu-id="788fb-103">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="788fb-104">このトピックでは、コマンドレットによって `Get-Help` コメントベースのヘルプトピックが適切な関数に関連付けられるように、関数のコメントベースのヘルプを配置する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="788fb-104">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="788fb-105">関数の Comment-Based ヘルプを配置する場所</span><span class="sxs-lookup"><span data-stu-id="788fb-105">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="788fb-106">関数本体の先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="788fb-106">At the beginning of the function body.</span></span>

- <span data-ttu-id="788fb-107">関数本体の末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="788fb-107">At the end of the function body.</span></span>

- <span data-ttu-id="788fb-108">キーワードの前 `Function` 。</span><span class="sxs-lookup"><span data-stu-id="788fb-108">Before the `Function` keyword.</span></span> <span data-ttu-id="788fb-109">関数がスクリプトまたはスクリプトモジュール内にある場合は、コメントベースのヘルプとキーワードの最後の行の間に複数の空白行を入れることはできません `Function` 。</span><span class="sxs-lookup"><span data-stu-id="788fb-109">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="788fb-110">それ以外の場合は、 `Get-Help` 関数ではなく、スクリプトにヘルプを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="788fb-110">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="788fb-111">関数内のヘルプの配置例</span><span class="sxs-lookup"><span data-stu-id="788fb-111">Examples of Help Placement in a Function</span></span>

<span data-ttu-id="788fb-112">次の例では、関数のコメントベースのヘルプの3つの配置オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="788fb-112">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="788fb-113">関数本体の先頭のヘルプ</span><span class="sxs-lookup"><span data-stu-id="788fb-113">Help at the Beginning of a Function Body</span></span>

<span data-ttu-id="788fb-114">次の例では、関数本体の先頭にあるコメントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="788fb-114">The following example shows comment-based at the beginning of a function body.</span></span>

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

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="788fb-115">関数本体の最後のヘルプ</span><span class="sxs-lookup"><span data-stu-id="788fb-115">Help at the End of a Function Body</span></span>

 <span data-ttu-id="788fb-116">次の例では、関数本体の最後にコメントを使用してコメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="788fb-116">The following example shows comment-based at the end of a function body.</span></span>

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

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="788fb-117">Function キーワードの前のヘルプ</span><span class="sxs-lookup"><span data-stu-id="788fb-117">Help Before the Function Keyword</span></span>

 <span data-ttu-id="788fb-118">次の例では、関数キーワードの前の行に基づいてコメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="788fb-118">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
