---
title: スクリプトにコメントベースのヘルプを配置する |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361181"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="c37fc-102">スクリプトにコメント ベースのヘルプを配置する</span><span class="sxs-lookup"><span data-stu-id="c37fc-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="c37fc-103">このトピックでは、`Get-Help` コマンドレットがコメントベースのヘルプトピックをスクリプトに関連付け、スクリプト内に存在する可能性のある関数を使用しないように、スクリプトのコメントベースのヘルプを配置する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="c37fc-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="c37fc-104">スクリプトのコメントベースのヘルプを配置する場所</span><span class="sxs-lookup"><span data-stu-id="c37fc-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="c37fc-105">スクリプトファイルの先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="c37fc-105">At the beginning of the script file.</span></span> <span data-ttu-id="c37fc-106">スクリプトのヘルプは、コメントと空白行によってのみスクリプトの先頭に配置できます。</span><span class="sxs-lookup"><span data-stu-id="c37fc-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="c37fc-107">スクリプトファイルの末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="c37fc-107">At the end of the script file.</span></span>

  <span data-ttu-id="c37fc-108">スクリプト本体の最初の項目 (ヘルプの後) が関数宣言の場合、スクリプトヘルプの末尾と関数宣言の間には、少なくとも2つの空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="c37fc-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="c37fc-109">それ以外の場合、ヘルプは、スクリプトのヘルプではなく、関数のヘルプとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="c37fc-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="c37fc-110">スクリプト内のヘルプの配置例</span><span class="sxs-lookup"><span data-stu-id="c37fc-110">Examples of Help Placement in a Script</span></span>

 <span data-ttu-id="c37fc-111">次の例は、スクリプトのコメントベースのヘルプの各配置オプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="c37fc-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="c37fc-112">スクリプトの先頭のヘルプ</span><span class="sxs-lookup"><span data-stu-id="c37fc-112">Help at the Beginning of a Script</span></span>

 <span data-ttu-id="c37fc-113">次の例では、スクリプトの先頭にあるコメントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c37fc-113">The following example shows comment-based at the beginning of a script.</span></span>

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="c37fc-114">スクリプトの最後のヘルプ</span><span class="sxs-lookup"><span data-stu-id="c37fc-114">Help at the End of a Script</span></span>

 <span data-ttu-id="c37fc-115">次の例では、スクリプトの最後にコメントを使用してコメントを示します。</span><span class="sxs-lookup"><span data-stu-id="c37fc-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```