---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-markdown?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Markdown
ms.openlocfilehash: bb73853c8432bcd4fcc900ee1d6fc620ed883ebb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210160"
---
# <span data-ttu-id="9092d-103">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="9092d-103">Show-Markdown</span></span>

## <span data-ttu-id="9092d-104">概要</span><span class="sxs-lookup"><span data-stu-id="9092d-104">SYNOPSIS</span></span>
<span data-ttu-id="9092d-105">VT100 エスケープシーケンスを使用するか、HTML を使用してブラウザーで、Markdown ファイルまたは文字列をコンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="9092d-105">Shows a Markdown file or string in the console in a friendly way using VT100 escape sequences or in a browser using HTML.</span></span>

## <span data-ttu-id="9092d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9092d-106">SYNTAX</span></span>

### <span data-ttu-id="9092d-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="9092d-107">Path (Default)</span></span>

```
Show-Markdown [-Path] <String[]> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="9092d-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="9092d-108">InputObject</span></span>

```
Show-Markdown -InputObject <PSObject> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="9092d-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9092d-109">LiteralPath</span></span>

```
Show-Markdown -LiteralPath <String[]> [-UseBrowser] [<CommonParameters>]
```

## <span data-ttu-id="9092d-110">Description</span><span class="sxs-lookup"><span data-stu-id="9092d-110">DESCRIPTION</span></span>

<span data-ttu-id="9092d-111">`Show-Markdown`コマンドレットは、ターミナルまたはブラウザーで人間が判読できる形式で Markdown を表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9092d-111">The `Show-Markdown` cmdlet is used to render Markdown in a human readable format either in a terminal or in a browser.</span></span>

<span data-ttu-id="9092d-112">`Show-Markdown` 端末がレンダリングする VT100 エスケープシーケンスを含む文字列を返すことができます (VT100 エスケープシーケンスがサポートされている場合)。</span><span class="sxs-lookup"><span data-stu-id="9092d-112">`Show-Markdown` can return a string that includes the VT100 escape sequences which the terminal renders (if it supports VT100 escape sequences).</span></span> <span data-ttu-id="9092d-113">これは主に、ターミナルで Markdown ファイルを表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9092d-113">This is primarily used for viewing Markdown files in a terminal.</span></span> <span data-ttu-id="9092d-114">また、AsVT100EncodedString パラメーターを指定することで、を使用してこの文字列を取得することもでき `ConvertFrom-Markdown` ます。 **AsVT100EncodedString**</span><span class="sxs-lookup"><span data-stu-id="9092d-114">You can also get this string via the `ConvertFrom-Markdown` by specifying the **AsVT100EncodedString** parameter.</span></span>

<span data-ttu-id="9092d-115">`Show-Markdown` では、ブラウザーを開いて、Markdown の表示バージョンを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="9092d-115">`Show-Markdown` also has the ability to open a browser and show you a rendered version of the Markdown.</span></span> <span data-ttu-id="9092d-116">HTML に変換し、HTML ファイルを既定のブラウザーで開くことで、Markdown を表示します。</span><span class="sxs-lookup"><span data-stu-id="9092d-116">It renders the Markdown by turning it into HTML and opening the HTML file in your default browser.</span></span>

<span data-ttu-id="9092d-117">`Show-Markdown`を使用してターミナルで Markdown を表示する方法を変更でき `Set-MarkdownOption` ます。</span><span class="sxs-lookup"><span data-stu-id="9092d-117">You can change how `Show-Markdown` renders Markdown in a terminal by using `Set-MarkdownOption`.</span></span>

<span data-ttu-id="9092d-118">このコマンドレットは、PowerShell 6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9092d-118">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="9092d-119">例</span><span class="sxs-lookup"><span data-stu-id="9092d-119">EXAMPLES</span></span>

### <span data-ttu-id="9092d-120">例 1: パスを指定する単純な例</span><span class="sxs-lookup"><span data-stu-id="9092d-120">Example 1: Simple example specifying a path</span></span>

```powershell
Show-Markdown -Path ./README.md
```

### <span data-ttu-id="9092d-121">例 2: 文字列を指定する単純な例</span><span class="sxs-lookup"><span data-stu-id="9092d-121">Example 2: Simple example specifying a string</span></span>

```powershell
@"
# Show-Markdown

## Markdown

You can now interact with Markdown via PowerShell!

*stars*
__underlines__
"@ | Show-Markdown
```

### <span data-ttu-id="9092d-122">例 2: ブラウザーで Markdown を開く</span><span class="sxs-lookup"><span data-stu-id="9092d-122">Example 2: Opening Markdown in a browser</span></span>

```powershell
Show-Markdown -Path ./README.md -UseBrowser
```

## <span data-ttu-id="9092d-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9092d-123">PARAMETERS</span></span>

### <span data-ttu-id="9092d-124">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9092d-124">-InputObject</span></span>

<span data-ttu-id="9092d-125">ターミナルに表示される Markdown 文字列。</span><span class="sxs-lookup"><span data-stu-id="9092d-125">A Markdown string that will be shown in the terminal.</span></span> <span data-ttu-id="9092d-126">サポートされている形式で渡さない場合 `Show-Markdown` は、によってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9092d-126">If you do not pass in a supported format, `Show-Markdown` will emit an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9092d-127">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9092d-127">-LiteralPath</span></span>

<span data-ttu-id="9092d-128">Markdown ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9092d-128">Specifies the path to a Markdown file.</span></span> <span data-ttu-id="9092d-129">Path パラメーターと異なり、LiteralPath の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9092d-129">Unlike the Path parameter, the value of LiteralPath is used exactly as it is typed.</span></span> <span data-ttu-id="9092d-130">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="9092d-130">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9092d-131">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9092d-131">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9092d-132">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="9092d-132">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9092d-133">-Path</span><span class="sxs-lookup"><span data-stu-id="9092d-133">-Path</span></span>

<span data-ttu-id="9092d-134">表示する Markdown ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9092d-134">Specifies the path to a Markdown file to be rendered.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="9092d-135">-UseBrowser</span><span class="sxs-lookup"><span data-stu-id="9092d-135">-UseBrowser</span></span>

<span data-ttu-id="9092d-136">Markdown 入力を HTML としてコンパイルし、既定のブラウザーで開きます。</span><span class="sxs-lookup"><span data-stu-id="9092d-136">Compiles the Markdown input as HTML and opens it in your default browser.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9092d-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9092d-137">CommonParameters</span></span>

<span data-ttu-id="9092d-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9092d-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9092d-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9092d-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9092d-140">入力</span><span class="sxs-lookup"><span data-stu-id="9092d-140">INPUTS</span></span>

### <span data-ttu-id="9092d-141">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="9092d-141">System.Management.Automation.PSObject</span></span>

### <span data-ttu-id="9092d-142">System.String[]</span><span class="sxs-lookup"><span data-stu-id="9092d-142">System.String[]</span></span>

## <span data-ttu-id="9092d-143">出力</span><span class="sxs-lookup"><span data-stu-id="9092d-143">OUTPUTS</span></span>

### <span data-ttu-id="9092d-144">System.String</span><span class="sxs-lookup"><span data-stu-id="9092d-144">System.String</span></span>

## <span data-ttu-id="9092d-145">注</span><span class="sxs-lookup"><span data-stu-id="9092d-145">NOTES</span></span>

## <span data-ttu-id="9092d-146">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9092d-146">RELATED LINKS</span></span>

[<span data-ttu-id="9092d-147">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="9092d-147">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)
