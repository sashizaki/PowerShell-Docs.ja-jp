---
description: 結合演算子 (-join) が複数の文字列を1つの文字列に結合する方法について説明します。
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_join?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Join
ms.openlocfilehash: d76e95aaeca1b5b94bb1a2216576a985ffb209c0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601196"
---
# <a name="about-join"></a><span data-ttu-id="2d19f-103">結合について</span><span class="sxs-lookup"><span data-stu-id="2d19f-103">About join</span></span>

## <a name="short-description"></a><span data-ttu-id="2d19f-104">概要</span><span class="sxs-lookup"><span data-stu-id="2d19f-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2d19f-105">結合演算子 (-join) が複数の文字列を1つの文字列に結合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d19f-105">Describes how the join operator (-join) combines multiple strings into a single string.</span></span>

## <a name="long-description"></a><span data-ttu-id="2d19f-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="2d19f-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="2d19f-107">Join 操作は、一連の文字列を連結して1つの文字列にします。</span><span class="sxs-lookup"><span data-stu-id="2d19f-107">The join operator concatenates a set of strings into a single string.</span></span> <span data-ttu-id="2d19f-108">文字列は、コマンドに出現する順序で、結果の文字列に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2d19f-108">The strings are appended to the resulting string in the order that they appear in the command.</span></span>

### <a name="syntax"></a><span data-ttu-id="2d19f-109">構文</span><span class="sxs-lookup"><span data-stu-id="2d19f-109">Syntax</span></span>

<span data-ttu-id="2d19f-110">次の図は、結合演算子の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="2d19f-110">The following diagram shows the syntax for the join operator.</span></span>

```powershell
-Join <String[]>
<String[]> -Join <Delimiter>
```

#### <a name="parameters"></a><span data-ttu-id="2d19f-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d19f-111">Parameters</span></span>

<span data-ttu-id="2d19f-112">String []-結合する1つ以上の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d19f-112">String[] - Specifies one or more strings to be joined.</span></span>

<span data-ttu-id="2d19f-113">Delimiter-連結された文字列の間に配置される1つ以上の文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d19f-113">Delimiter - Specifies one or more characters placed between the concatenated strings.</span></span> <span data-ttu-id="2d19f-114">既定値は区切り記号 ("") ではありません。</span><span class="sxs-lookup"><span data-stu-id="2d19f-114">The default is no delimiter ("").</span></span>

<span data-ttu-id="2d19f-115">解説</span><span class="sxs-lookup"><span data-stu-id="2d19f-115">Remarks</span></span>

<span data-ttu-id="2d19f-116">単項結合演算子 (-join <string [] >) は、コンマよりも優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="2d19f-116">The unary join operator (-join <string[]>) has higher precedence than a comma.</span></span> <span data-ttu-id="2d19f-117">その結果、コンマ区切りの文字列リストを単項結合演算子に送信した場合、最初の文字列 (最初のコンマの前) だけが結合演算子に送信されます。</span><span class="sxs-lookup"><span data-stu-id="2d19f-117">As a result, if you submit a comma-separated list of strings to the unary join operator, only the first string (before the first comma) is submitted to the join operator.</span></span>

<span data-ttu-id="2d19f-118">単項結合演算子を使用するには、文字列をかっこで囲みます。または、変数に文字列を格納し、結合する変数を送信します。</span><span class="sxs-lookup"><span data-stu-id="2d19f-118">To use the unary join operator, enclose the strings in parentheses, or store the strings in a variable, and then submit the variable to join.</span></span>

<span data-ttu-id="2d19f-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2d19f-119">For example:</span></span>

```powershell
-join "a", "b", "c"
a
b
c

-join ("a", "b", "c")
abc

$z = "a", "b", "c"
-join $z
abc
```

### <a name="examples"></a><span data-ttu-id="2d19f-120">例</span><span class="sxs-lookup"><span data-stu-id="2d19f-120">Examples</span></span>

<span data-ttu-id="2d19f-121">次のステートメントは、3つの文字列を結合します。</span><span class="sxs-lookup"><span data-stu-id="2d19f-121">The following statement joins three strings:</span></span>

```powershell
-join ("Windows", "PowerShell", "2.0")
WindowsPowerShell2.0
```

<span data-ttu-id="2d19f-122">次のステートメントは、スペースで区切られた3つの文字列を結合します。</span><span class="sxs-lookup"><span data-stu-id="2d19f-122">The following statement joins three strings delimited by a space:</span></span>

```powershell
"Windows", "PowerShell", "2.0" -join " "
Windows PowerShell 2.0
```

<span data-ttu-id="2d19f-123">次のステートメントでは、3つの文字列を結合するために複数の文字の区切り記号を使用しています。</span><span class="sxs-lookup"><span data-stu-id="2d19f-123">The following statements use a multiple-character delimiter to join three strings:</span></span>

```powershell
$a = "WIND", "S P", "ERSHELL"
$a -join "OW"
WINDOWS POWERSHELL
```

<span data-ttu-id="2d19f-124">次のステートメントは、ここで指定した文字列内の行を1つの文字列に結合します。</span><span class="sxs-lookup"><span data-stu-id="2d19f-124">The following statement joins the lines in a here-string into a single string.</span></span> <span data-ttu-id="2d19f-125">ここでは文字列が1つの文字列であるため、この文字列内の行は、結合する前に分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d19f-125">Because a here-string is one string, the lines in the here-string must be split before they can be joined.</span></span> <span data-ttu-id="2d19f-126">このメソッドを使用すると、次の文字列に保存されている XML ファイル内の文字列を再度参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="2d19f-126">You can use this method to rejoin the strings in an XML file that has been saved in a here-string:</span></span>

```powershell
$a = @'
a
b
c
'@

(-split $a) -join " "
a b c
```

## <a name="see-also"></a><span data-ttu-id="2d19f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d19f-127">SEE ALSO</span></span>

[<span data-ttu-id="2d19f-128">about_Operators</span><span class="sxs-lookup"><span data-stu-id="2d19f-128">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="2d19f-129">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="2d19f-129">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="2d19f-130">about_Split</span><span class="sxs-lookup"><span data-stu-id="2d19f-130">about_Split</span></span>](about_Split.md)

