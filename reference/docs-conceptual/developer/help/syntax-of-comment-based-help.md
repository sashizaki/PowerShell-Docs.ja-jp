---
ms.date: 09/12/2016
ms.topic: reference
title: コメント ベースのヘルプの構文
description: コメント ベースのヘルプの構文
ms.openlocfilehash: 3866f25b40fc970e8d219af6f423b7a25f5b875c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659515"
---
# <a name="syntax-of-comment-based-help"></a><span data-ttu-id="962c9-103">コメント ベースのヘルプの構文</span><span class="sxs-lookup"><span data-stu-id="962c9-103">Syntax of Comment-Based Help</span></span>

<span data-ttu-id="962c9-104">ここでは、コメントベースのヘルプの構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="962c9-104">This section describes the syntax of comment-based help.</span></span>

## <a name="syntax-diagram"></a><span data-ttu-id="962c9-105">構文ダイアグラム</span><span class="sxs-lookup"><span data-stu-id="962c9-105">Syntax Diagram</span></span>

 <span data-ttu-id="962c9-106">コメントベースのヘルプの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="962c9-106">The syntax for comment-based Help is as follows:</span></span>

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a><span data-ttu-id="962c9-107">構文の説明</span><span class="sxs-lookup"><span data-stu-id="962c9-107">Syntax Description</span></span>

 <span data-ttu-id="962c9-108">コメントベースのヘルプは、一連のコメントとして書かれています。</span><span class="sxs-lookup"><span data-stu-id="962c9-108">Comment-based Help is written as a series of comments.</span></span> <span data-ttu-id="962c9-109">コメントの各行の前にコメント記号 () を入力する `#` か、および記号を使用し `<#` てコメントブロックを作成することができ `#>` ます。</span><span class="sxs-lookup"><span data-stu-id="962c9-109">You can type a comment symbol (`#`) before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="962c9-110">コメントブロック内のすべての行は、コメントとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="962c9-110">All the lines within the comment block are interpreted as comments.</span></span>

 <span data-ttu-id="962c9-111">コメントベースのヘルプの各セクションは、キーワードによって定義され、各キーワードの前にドット () が付き `.` ます。</span><span class="sxs-lookup"><span data-stu-id="962c9-111">Each section of comment-based Help is defined by a keyword and each keyword is preceded by a dot (`.`).</span></span> <span data-ttu-id="962c9-112">キーワードは任意の順序で表示できます。</span><span class="sxs-lookup"><span data-stu-id="962c9-112">The keywords can appear in any order.</span></span> <span data-ttu-id="962c9-113">キーワード名の大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="962c9-113">The keyword names are not case-sensitive.</span></span>

 <span data-ttu-id="962c9-114">コメントブロックには、少なくとも1つのヘルプキーワードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="962c9-114">A comment block must contain at least one help keyword.</span></span> <span data-ttu-id="962c9-115">**たとえば**、いくつかのキーワードは、同じコメントブロック内で何度も出現する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="962c9-115">Some of the keywords, such as **EXAMPLE**, can appear many times in the same comment block.</span></span> <span data-ttu-id="962c9-116">各キーワードのヘルプコンテンツは、キーワードの後の行から開始され、複数の行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="962c9-116">The Help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

 <span data-ttu-id="962c9-117">コメントベースのヘルプトピック内のすべての行は、連続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="962c9-117">All of the lines in a comment-based Help topic must be contiguous.</span></span> <span data-ttu-id="962c9-118">コメントベースのヘルプトピックがヘルプトピックに含まれていないコメントの後に続く場合は、ヘルプ以外の最後のコメント行とコメントベースのヘルプの先頭の間に、少なくとも1つの空白行がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="962c9-118">If a comment-based Help topic follows a comment that is not part of the Help topic, there must be at least one blank line between the last non-Help comment line and the beginning of the comment-based Help.</span></span>

 <span data-ttu-id="962c9-119">たとえば、次のコメントベースのヘルプトピックにはが含まれています。Description キーワードとその値 (関数またはスクリプトの説明)。</span><span class="sxs-lookup"><span data-stu-id="962c9-119">For example, the following comment-based help topic contains the .Description keyword and its value, which is a description of a function or script.</span></span>

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```
