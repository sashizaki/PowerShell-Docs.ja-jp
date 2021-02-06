---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
schema: 2.0.0
ms.openlocfilehash: 775b11db79b9ca8290864b757e5cd1a0615f89e4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599514"
---
# <span data-ttu-id="83f7e-101">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="83f7e-101">Get-MarkdownOption</span></span>

## <span data-ttu-id="83f7e-102">概要</span><span class="sxs-lookup"><span data-stu-id="83f7e-102">SYNOPSIS</span></span>
<span data-ttu-id="83f7e-103">コンソールで Markdown コンテンツをレンダリングするために使用される、現在の色とスタイルを返します。</span><span class="sxs-lookup"><span data-stu-id="83f7e-103">Returns the current colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="83f7e-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="83f7e-104">SYNTAX</span></span>

```
Get-MarkdownOption [<CommonParameters>]
```

## <span data-ttu-id="83f7e-105">Description</span><span class="sxs-lookup"><span data-stu-id="83f7e-105">DESCRIPTION</span></span>

<span data-ttu-id="83f7e-106">コンソールで Markdown コンテンツをレンダリングするために使用される、現在の色とスタイルを返します。</span><span class="sxs-lookup"><span data-stu-id="83f7e-106">Returns the current colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="83f7e-107">このコマンドレットの出力に表示される文字列には、表示される Markdown テキストの色とスタイルを変更するために使用する ANSI エスケープコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="83f7e-107">The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="83f7e-108">Markdown の詳細については、「 [Commonmark](https://commonmark.org/) 」 web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="83f7e-108">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

## <span data-ttu-id="83f7e-109">例</span><span class="sxs-lookup"><span data-stu-id="83f7e-109">EXAMPLES</span></span>

### <span data-ttu-id="83f7e-110">例 1-現在の色とスタイルを取得する</span><span class="sxs-lookup"><span data-stu-id="83f7e-110">Example 1 - Get the current colors and style</span></span>

```powershell
Get-MarkdownOption
```

```Output
Header1         : [7m
Header2         : [4;93m
Header3         : [4;94m
Header4         : [4;95m
Header5         : [4;96m
Header6         : [4;97m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

> [!NOTE]
> <span data-ttu-id="83f7e-111">出力に表示される文字列値は、  `[char]0x1B` ANSI エスケープシーケンスのエスケープ文字 () に続く文字です。</span><span class="sxs-lookup"><span data-stu-id="83f7e-111">The string values shown in the output are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="83f7e-112">ANSI エスケープコードの詳細については、「 [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83f7e-112">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="83f7e-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="83f7e-113">PARAMETERS</span></span>

### <span data-ttu-id="83f7e-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="83f7e-114">CommonParameters</span></span>

<span data-ttu-id="83f7e-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="83f7e-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="83f7e-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83f7e-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="83f7e-117">入力</span><span class="sxs-lookup"><span data-stu-id="83f7e-117">INPUTS</span></span>

### <span data-ttu-id="83f7e-118">なし</span><span class="sxs-lookup"><span data-stu-id="83f7e-118">None</span></span>

## <span data-ttu-id="83f7e-119">出力</span><span class="sxs-lookup"><span data-stu-id="83f7e-119">OUTPUTS</span></span>

### <span data-ttu-id="83f7e-120">PSMarkdownOptionInfo を表示します。</span><span class="sxs-lookup"><span data-stu-id="83f7e-120">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="83f7e-121">注</span><span class="sxs-lookup"><span data-stu-id="83f7e-121">NOTES</span></span>

## <span data-ttu-id="83f7e-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="83f7e-122">RELATED LINKS</span></span>

[<span data-ttu-id="83f7e-123">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="83f7e-123">Set-MarkdownOption</span></span>](Set-MarkdownOption.md)

[<span data-ttu-id="83f7e-124">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="83f7e-124">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="83f7e-125">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="83f7e-125">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="83f7e-126">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="83f7e-126">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="83f7e-127">CommonMark</span><span class="sxs-lookup"><span data-stu-id="83f7e-127">CommonMark</span></span>](https://commonmark.org/)

