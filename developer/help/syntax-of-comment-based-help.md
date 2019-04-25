---
title: 構文のコメント ベースのヘルプ |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8adc997-1a71-48e9-9383-513ef13da7cf
caps.latest.revision: 4
ms.openlocfilehash: 584e5923008e8369a83c699478844f0e0c295adc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083214"
---
# <a name="syntax-of-comment-based-help"></a><span data-ttu-id="e8642-102">コメント ベースのヘルプの構文</span><span class="sxs-lookup"><span data-stu-id="e8642-102">Syntax of Comment-Based Help</span></span>

<span data-ttu-id="e8642-103">このセクションでは、コメント ベースのヘルプの構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8642-103">This section describes the syntax of comment-based help.</span></span>

## <a name="syntax-diagram"></a><span data-ttu-id="e8642-104">構文ダイアグラム</span><span class="sxs-lookup"><span data-stu-id="e8642-104">Syntax Diagram</span></span>

 <span data-ttu-id="e8642-105">コメント ベースのヘルプの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8642-105">The syntax for comment-based Help is as follows:</span></span>

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a><span data-ttu-id="e8642-106">構文の説明</span><span class="sxs-lookup"><span data-stu-id="e8642-106">Syntax Description</span></span>

 <span data-ttu-id="e8642-107">コメント ベースのヘルプは、一連のコメントとして書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e8642-107">Comment-based Help is written as a series of comments.</span></span> <span data-ttu-id="e8642-108">各の行、コメントの前にコメント記号 (#) を入力するか、使用することができます、"\<#"と"#>"記号がコメント ブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8642-108">You can type a comment symbol (#) before each line of comments, or you can use the "\<#" and "#>" symbols to create a comment block.</span></span> <span data-ttu-id="e8642-109">コメント ブロック内のすべての行はコメントとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="e8642-109">All the lines within the comment block are interpreted as comments.</span></span>

 <span data-ttu-id="e8642-110">コメント ベースのヘルプの各セクションではキーワードで定義され、各キーワードの前にドット (.)。</span><span class="sxs-lookup"><span data-stu-id="e8642-110">Each section of comment-based Help is defined by a keyword and each keyword is preceded by a dot (.).</span></span> <span data-ttu-id="e8642-111">キーワードは、任意の順序で表示できます。</span><span class="sxs-lookup"><span data-stu-id="e8642-111">The keywords can appear in any order.</span></span> <span data-ttu-id="e8642-112">キーワード名は区別されません。</span><span class="sxs-lookup"><span data-stu-id="e8642-112">The keyword names are not case-sensitive.</span></span>

 <span data-ttu-id="e8642-113">コメント ブロックは、少なくとも 1 つのヘルプ キーワードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8642-113">A comment block must contain at least one help keyword.</span></span> <span data-ttu-id="e8642-114">何度もは、コメント ブロックは同じで、キーワード、例などのいくつか表示できます。</span><span class="sxs-lookup"><span data-stu-id="e8642-114">Some of the keywords, such as EXAMPLE, can appear many times in the same comment block.</span></span> <span data-ttu-id="e8642-115">各キーワードのヘルプ コンテンツのキーワードの後に始まり、行を複数の行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="e8642-115">The Help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

 <span data-ttu-id="e8642-116">すべてのコメント ベースのヘルプ トピック内の行が連続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8642-116">All of the lines in a comment-based Help topic must be contiguous.</span></span> <span data-ttu-id="e8642-117">コメント ベースのヘルプ トピックには、ヘルプ トピックの一部でないコメントが後ろに、ある場合は、ヘルプではないコメントの最後の行とコメント ベースのヘルプの先頭の間に少なくとも 1 つの空白行が必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8642-117">If a comment-based Help topic follows a comment that is not part of the Help topic, there must be at least one blank line between the last non-Help comment line and the beginning of the comment-based Help.</span></span>

 <span data-ttu-id="e8642-118">たとえば、次のコメント ベースのヘルプ トピックが含まれています、します。キーワードの説明とその値は、関数またはスクリプトの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="e8642-118">For example, the following comment-based help topic contains the .Description keyword and its value, which is a description of a function or script.</span></span>

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```