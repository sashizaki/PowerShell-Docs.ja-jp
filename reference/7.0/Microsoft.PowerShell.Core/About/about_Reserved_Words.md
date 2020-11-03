---
description: PowerShell で特別な意味を持つため、識別子として使用できない予約語の一覧を示します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_reserved_words?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Reserved_Words
ms.openlocfilehash: c4b67a523a40319635d159791b80ab302b9aa3b4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223731"
---
# <a name="about-reserved-words"></a><span data-ttu-id="95e26-104">予約語について</span><span class="sxs-lookup"><span data-stu-id="95e26-104">About Reserved Words</span></span>

## <a name="short-description"></a><span data-ttu-id="95e26-105">概要</span><span class="sxs-lookup"><span data-stu-id="95e26-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="95e26-106">PowerShell で特別な意味を持つため、識別子として使用できない予約語の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="95e26-106">Lists the reserved words that cannot be used as identifiers because they have a special meaning in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="95e26-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="95e26-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="95e26-108">PowerShell では、特別な意味を持つ特定の単語があります。</span><span class="sxs-lookup"><span data-stu-id="95e26-108">There are certain words that have special meaning in PowerShell.</span></span> <span data-ttu-id="95e26-109">これらの単語が引用符で囲まれていない場合、PowerShell は文字列として扱うのではなく、特別な意味を適用しようとします。</span><span class="sxs-lookup"><span data-stu-id="95e26-109">When these words appear without quotation marks, PowerShell attempts to apply their special meaning rather than treating them as character strings.</span></span> <span data-ttu-id="95e26-110">これらの単語をコマンドまたはスクリプトで特別な意味を呼び出さずにパラメーター引数として使用するには、予約語を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="95e26-110">To use these words as parameter arguments in a command or script without invoking their special meaning, enclose the reserved words in quotation marks.</span></span>

<span data-ttu-id="95e26-111">PowerShell の予約語は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="95e26-111">The following are the reserved words in PowerShell:</span></span>

```
assembly         exit            process
base             filter          public
begin            finally         return
break            for             sequence
catch            foreach         static
class            from (*)        switch
command          function        throw
configuration    hidden          trap
continue         if              try
data             in              type
define (*)       inlinescript    until
do               interface       using
dynamicparam     module          var (*)
else             namespace       while
elseif           parallel        workflow
end              param
enum             private

(*) These keywords are reserved for future use.
```

<span data-ttu-id="95e26-112">、、、およびなどのいくつかの言語キーワードに `Foreach` `If` は、独自の `For` `While` ヘルプ記事があります。</span><span class="sxs-lookup"><span data-stu-id="95e26-112">Several language keywords, including `Foreach`, `If`, `For`, and `While`, have their own help articles.</span></span> <span data-ttu-id="95e26-113">これを表示するには、「」 `Get-Help about_` と入力し、キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="95e26-113">To view them, type `Get-Help about_` and add the keyword.</span></span> <span data-ttu-id="95e26-114">たとえば、ステートメントに関する情報を取得するには、次のように `Foreach` 入力します。</span><span class="sxs-lookup"><span data-stu-id="95e26-114">For example, to get information about the `Foreach` statement, type:</span></span>

```powershell
Get-Help about_ForEach
```

<span data-ttu-id="95e26-115">ステートメントまたはステートメントの構文の詳細について `Filter` は `Return` 、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="95e26-115">For information about the `Filter` statement or the `Return` statement syntax, type:</span></span>

```powershell
Get-Help about_Functions
```

<span data-ttu-id="95e26-116">他の予約語の詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="95e26-116">For information about other reserved words, type:</span></span>

```powershell
Get-Help <Reserved_Word>
```

> [!NOTE]
> <span data-ttu-id="95e26-117">すべての予約語に独自のヘルプ記事があるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="95e26-117">Not every reserved word has its own help article.</span></span> <span data-ttu-id="95e26-118">に `Get-Help` よって記事が返されない場合は、次のコマンドを使用して、予約語について説明する記事を検索できます。</span><span class="sxs-lookup"><span data-stu-id="95e26-118">If `Get-Help` does not return an article, you can search for articles that talk about the reserved word using the following command:</span></span>
>
> ```powershell
> Get-Help <Reserved_Word> -Category:HelpFile
> ```

## <a name="see-also"></a><span data-ttu-id="95e26-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="95e26-119">SEE ALSO</span></span>

- [<span data-ttu-id="95e26-120">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="95e26-120">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="95e26-121">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="95e26-121">about_Language_Keywords</span></span>](about_Language_Keywords.md)
- [<span data-ttu-id="95e26-122">about_Parsing</span><span class="sxs-lookup"><span data-stu-id="95e26-122">about_Parsing</span></span>](about_Parsing.md)
- [<span data-ttu-id="95e26-123">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="95e26-123">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
- [<span data-ttu-id="95e26-124">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="95e26-124">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="95e26-125">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="95e26-125">about_Special_Characters</span></span>](about_Special_Characters.md)