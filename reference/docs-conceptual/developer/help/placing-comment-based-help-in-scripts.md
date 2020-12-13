---
ms.date: 09/12/2016
ms.topic: reference
title: スクリプトにコメント ベースのヘルプを配置する
description: スクリプトにコメント ベースのヘルプを配置する
ms.openlocfilehash: b0d32b7ab063269085899a643b0c3a17da2073fc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645444"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="81592-103">スクリプトにコメント ベースのヘルプを配置する</span><span class="sxs-lookup"><span data-stu-id="81592-103">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="81592-104">このトピックでは、スクリプトにコメントベースのヘルプトピックを配置する方法について説明し `Get-Help` ます。このコマンドレットは、スクリプトに含まれる関数ではなく、スクリプトにコメントベースのヘルプトピックを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="81592-104">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="81592-105">スクリプトの Comment-Based ヘルプの配置場所</span><span class="sxs-lookup"><span data-stu-id="81592-105">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="81592-106">スクリプトファイルの先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="81592-106">At the beginning of the script file.</span></span>

  <span data-ttu-id="81592-107">スクリプトのヘルプは、コメントと空白行によってのみスクリプトの先頭に配置できます。</span><span class="sxs-lookup"><span data-stu-id="81592-107">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="81592-108">スクリプトファイルの末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="81592-108">At the end of the script file.</span></span>

  <span data-ttu-id="81592-109">スクリプト本体の最初の項目 (ヘルプの後) が関数宣言の場合、スクリプトヘルプの末尾と関数宣言の間には、少なくとも2つの空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="81592-109">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="81592-110">それ以外の場合、ヘルプは、スクリプトのヘルプではなく、関数のヘルプとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="81592-110">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="81592-111">スクリプト内のヘルプの配置例</span><span class="sxs-lookup"><span data-stu-id="81592-111">Examples of Help Placement in a Script</span></span>

<span data-ttu-id="81592-112">次の例は、スクリプトのコメントベースのヘルプの各配置オプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="81592-112">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="81592-113">スクリプトの先頭のヘルプ</span><span class="sxs-lookup"><span data-stu-id="81592-113">Help at the Beginning of a Script</span></span>

<span data-ttu-id="81592-114">次の例では、スクリプトの先頭にあるコメントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="81592-114">The following example shows comment-based at the beginning of a script.</span></span>

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="81592-115">スクリプトの最後のヘルプ</span><span class="sxs-lookup"><span data-stu-id="81592-115">Help at the End of a Script</span></span>

 <span data-ttu-id="81592-116">次の例では、スクリプトの最後にコメントを使用してコメントを示します。</span><span class="sxs-lookup"><span data-stu-id="81592-116">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
