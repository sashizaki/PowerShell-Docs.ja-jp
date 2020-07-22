---
title: スクリプトにコメント ベースのヘルプを配置する
ms.date: 09/12/2016
ms.openlocfilehash: a3ade6c3138826b924939056b9d1ffb233006d44
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893188"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="2c494-102">スクリプトにコメント ベースのヘルプを配置する</span><span class="sxs-lookup"><span data-stu-id="2c494-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="2c494-103">このトピックでは、スクリプトにコメントベースのヘルプトピックを配置する方法について説明し `Get-Help` ます。このコマンドレットは、スクリプトに含まれる関数ではなく、スクリプトにコメントベースのヘルプトピックを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="2c494-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="2c494-104">スクリプトのコメントベースのヘルプを配置する場所</span><span class="sxs-lookup"><span data-stu-id="2c494-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="2c494-105">スクリプトファイルの先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="2c494-105">At the beginning of the script file.</span></span>

  <span data-ttu-id="2c494-106">スクリプトのヘルプは、コメントと空白行によってのみスクリプトの先頭に配置できます。</span><span class="sxs-lookup"><span data-stu-id="2c494-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="2c494-107">スクリプトファイルの末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="2c494-107">At the end of the script file.</span></span>

  <span data-ttu-id="2c494-108">スクリプト本体の最初の項目 (ヘルプの後) が関数宣言の場合、スクリプトヘルプの末尾と関数宣言の間には、少なくとも2つの空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="2c494-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="2c494-109">それ以外の場合、ヘルプは、スクリプトのヘルプではなく、関数のヘルプとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="2c494-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="2c494-110">スクリプト内のヘルプの配置例</span><span class="sxs-lookup"><span data-stu-id="2c494-110">Examples of Help Placement in a Script</span></span>

<span data-ttu-id="2c494-111">次の例は、スクリプトのコメントベースのヘルプの各配置オプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="2c494-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="2c494-112">スクリプトの先頭のヘルプ</span><span class="sxs-lookup"><span data-stu-id="2c494-112">Help at the Beginning of a Script</span></span>

<span data-ttu-id="2c494-113">次の例では、スクリプトの先頭にあるコメントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="2c494-113">The following example shows comment-based at the beginning of a script.</span></span>

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="2c494-114">スクリプトの最後のヘルプ</span><span class="sxs-lookup"><span data-stu-id="2c494-114">Help at the End of a Script</span></span>

 <span data-ttu-id="2c494-115">次の例では、スクリプトの最後にコメントを使用してコメントを示します。</span><span class="sxs-lookup"><span data-stu-id="2c494-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
