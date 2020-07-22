---
title: コメント ベースのヘルプの構文
ms.date: 09/12/2016
ms.openlocfilehash: 950afecc39f9d27207f77547679faab700481458
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893222"
---
# <a name="syntax-of-comment-based-help"></a><span data-ttu-id="de540-102">コメント ベースのヘルプの構文</span><span class="sxs-lookup"><span data-stu-id="de540-102">Syntax of Comment-Based Help</span></span>

<span data-ttu-id="de540-103">ここでは、コメントベースのヘルプの構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="de540-103">This section describes the syntax of comment-based help.</span></span>

## <a name="syntax-diagram"></a><span data-ttu-id="de540-104">構文ダイアグラム</span><span class="sxs-lookup"><span data-stu-id="de540-104">Syntax Diagram</span></span>

 <span data-ttu-id="de540-105">コメントベースのヘルプの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="de540-105">The syntax for comment-based Help is as follows:</span></span>

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a><span data-ttu-id="de540-106">構文の説明</span><span class="sxs-lookup"><span data-stu-id="de540-106">Syntax Description</span></span>

 <span data-ttu-id="de540-107">コメントベースのヘルプは、一連のコメントとして書かれています。</span><span class="sxs-lookup"><span data-stu-id="de540-107">Comment-based Help is written as a series of comments.</span></span> <span data-ttu-id="de540-108">コメントの各行の前にコメント記号 () を入力する `#` か、および記号を使用し `<#` てコメントブロックを作成することができ `#>` ます。</span><span class="sxs-lookup"><span data-stu-id="de540-108">You can type a comment symbol (`#`) before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="de540-109">コメントブロック内のすべての行は、コメントとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="de540-109">All the lines within the comment block are interpreted as comments.</span></span>

 <span data-ttu-id="de540-110">コメントベースのヘルプの各セクションは、キーワードによって定義され、各キーワードの前にドット () が付き `.` ます。</span><span class="sxs-lookup"><span data-stu-id="de540-110">Each section of comment-based Help is defined by a keyword and each keyword is preceded by a dot (`.`).</span></span> <span data-ttu-id="de540-111">キーワードは任意の順序で表示できます。</span><span class="sxs-lookup"><span data-stu-id="de540-111">The keywords can appear in any order.</span></span> <span data-ttu-id="de540-112">キーワード名の大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="de540-112">The keyword names are not case-sensitive.</span></span>

 <span data-ttu-id="de540-113">コメントブロックには、少なくとも1つのヘルプキーワードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="de540-113">A comment block must contain at least one help keyword.</span></span> <span data-ttu-id="de540-114">**たとえば**、いくつかのキーワードは、同じコメントブロック内で何度も出現する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de540-114">Some of the keywords, such as **EXAMPLE**, can appear many times in the same comment block.</span></span> <span data-ttu-id="de540-115">各キーワードのヘルプコンテンツは、キーワードの後の行から開始され、複数の行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="de540-115">The Help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

 <span data-ttu-id="de540-116">コメントベースのヘルプトピック内のすべての行は、連続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="de540-116">All of the lines in a comment-based Help topic must be contiguous.</span></span> <span data-ttu-id="de540-117">コメントベースのヘルプトピックがヘルプトピックに含まれていないコメントの後に続く場合は、ヘルプ以外の最後のコメント行とコメントベースのヘルプの先頭の間に、少なくとも1つの空白行がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="de540-117">If a comment-based Help topic follows a comment that is not part of the Help topic, there must be at least one blank line between the last non-Help comment line and the beginning of the comment-based Help.</span></span>

 <span data-ttu-id="de540-118">たとえば、次のコメントベースのヘルプトピックにはが含まれています。Description キーワードとその値 (関数またはスクリプトの説明)。</span><span class="sxs-lookup"><span data-stu-id="de540-118">For example, the following comment-based help topic contains the .Description keyword and its value, which is a description of a function or script.</span></span>

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```
