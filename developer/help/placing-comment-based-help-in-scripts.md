---
title: スクリプトにコメント ベースのヘルプを配置する |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860768"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="aa50a-102">スクリプトにコメント ベースのヘルプを配置する</span><span class="sxs-lookup"><span data-stu-id="aa50a-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="aa50a-103">このトピックでは、スクリプトのコメント ベースのヘルプを配置する場所を説明しますように、`Get-Help`スクリプトとスクリプトで可能性のあるすべての関数ではなく、コマンドレットは、コメント ベースのヘルプ トピックを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="aa50a-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="aa50a-104">スクリプトのコメント ベースのヘルプを配置する場所</span><span class="sxs-lookup"><span data-stu-id="aa50a-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="aa50a-105">スクリプト ファイルの先頭にします。</span><span class="sxs-lookup"><span data-stu-id="aa50a-105">At the beginning of the script file.</span></span> <span data-ttu-id="aa50a-106">スクリプトでスクリプトのヘルプの前に、コメントや空白行のみです。</span><span class="sxs-lookup"><span data-stu-id="aa50a-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="aa50a-107">スクリプト ファイルの末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="aa50a-107">At the end of the script file.</span></span>

  <span data-ttu-id="aa50a-108">(ヘルプ) の後のスクリプトの本文の最初の項目が関数宣言の場合は、ヘルプ、スクリプトの末尾と関数の宣言の間に少なくとも 2 つの空白行が必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa50a-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="aa50a-109">それ以外の場合、ヘルプは、関数、スクリプトのヘルプではないのヘルプとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="aa50a-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="aa50a-110">スクリプトでヘルプの例</span><span class="sxs-lookup"><span data-stu-id="aa50a-110">Examples of Help Placement in a Script</span></span>

 <span data-ttu-id="aa50a-111">次の例は、各スクリプトのコメント ベースのヘルプの配置オプションを示します。</span><span class="sxs-lookup"><span data-stu-id="aa50a-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="aa50a-112">スクリプトの先頭にあるヘルプします。</span><span class="sxs-lookup"><span data-stu-id="aa50a-112">Help at the Beginning of a Script</span></span>

 <span data-ttu-id="aa50a-113">次の例を示しますスクリプトの先頭にコメント ベースします。</span><span class="sxs-lookup"><span data-stu-id="aa50a-113">The following example shows comment-based at the beginning of a script.</span></span>

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="aa50a-114">スクリプトの末尾にあるヘルプします。</span><span class="sxs-lookup"><span data-stu-id="aa50a-114">Help at the End of a Script</span></span>

 <span data-ttu-id="aa50a-115">次の例では、コメント ベースのスクリプトの末尾を示します。</span><span class="sxs-lookup"><span data-stu-id="aa50a-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```