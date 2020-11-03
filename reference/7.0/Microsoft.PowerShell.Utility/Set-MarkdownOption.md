---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-7&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: e18cc8e0f5e547c4418f59b6f55109052b69c220
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "93217955"
---
# <span data-ttu-id="68132-101">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="68132-101">Set-MarkdownOption</span></span>

## <span data-ttu-id="68132-102">概要</span><span class="sxs-lookup"><span data-stu-id="68132-102">SYNOPSIS</span></span>
<span data-ttu-id="68132-103">コンソールで Markdown コンテンツをレンダリングするために使用する色とスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-103">Sets the colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="68132-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="68132-104">SYNTAX</span></span>

### <span data-ttu-id="68132-105">個別設定 (既定)</span><span class="sxs-lookup"><span data-stu-id="68132-105">IndividualSetting (Default)</span></span>

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### <span data-ttu-id="68132-106">テーマ</span><span class="sxs-lookup"><span data-stu-id="68132-106">Theme</span></span>

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### <span data-ttu-id="68132-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="68132-107">InputObject</span></span>

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## <span data-ttu-id="68132-108">Description</span><span class="sxs-lookup"><span data-stu-id="68132-108">DESCRIPTION</span></span>

<span data-ttu-id="68132-109">コンソールで Markdown コンテンツをレンダリングするために使用する色とスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-109">Sets the colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="68132-110">これらのスタイルは、表示される Markdown テキストの色とスタイルを変更する ANSI エスケープコードを使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="68132-110">These styles are defined using ANSI escape codes that change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="68132-111">Markdown の詳細については、「 [Commonmark](https://commonmark.org/) 」 web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68132-111">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

> [!NOTE]
> <span data-ttu-id="68132-112">設定で使用される文字列値は、 **Escape** `[char]0x1B` ANSI エスケープシーケンスのエスケープ文字 () に続く文字です。</span><span class="sxs-lookup"><span data-stu-id="68132-112">The string values used in the settings are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="68132-113">文字列に **エスケープ** 文字を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="68132-113">Do not include the **Escape** character in the string.</span></span> <span data-ttu-id="68132-114">ANSI エスケープコードの詳細については、「 [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68132-114">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="68132-115">例</span><span class="sxs-lookup"><span data-stu-id="68132-115">EXAMPLES</span></span>

### <span data-ttu-id="68132-116">例 1-ライトテーマに切り替える</span><span class="sxs-lookup"><span data-stu-id="68132-116">Example 1 - Switch to the Light Theme</span></span>

<span data-ttu-id="68132-117">この例では、 **ライト** テーマを選択し、 **PassThru** パラメーターを使用して新しい構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="68132-117">This example selects the **Light** theme and displays the new configuration using the **PassThru** parameter.</span></span>

```powershell
Set-MarkdownOption -Theme Light -PassThru
```

```Output
Header1         : [7m
Header2         : [4;33m
Header3         : [4;34m
Header4         : [4;35m
Header5         : [4;36m
Header6         : [4;30m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

### <span data-ttu-id="68132-118">例 2-色とスタイルの設定をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="68132-118">Example 2 - Customize the color and style settings</span></span>

<span data-ttu-id="68132-119">この例では、Markdown ヘッダーのエスケープコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="68132-119">This example changes the escape code for the Markdown headers.</span></span> <span data-ttu-id="68132-120">ヘッダーの既定の構成では、さまざまな色の下線付きのテキストとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="68132-120">The default configuration for headers renders them as underlined text of various colors.</span></span> <span data-ttu-id="68132-121">この変更により、下線のスタイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="68132-121">This change removes the underline style.</span></span>

```powershell
$mdOptions = Get-MarkdownOption
$mdOptions.Header2 = '[93m'
$mdOptions.Header3 = '[94m'
$mdOptions.Header4 = '[95m'
$mdOptions.Header5 = '[96m'
$mdOptions.Header6 = '[97m'
Set-MarkdownOption -InputObject $mdOptions -PassThru
```

```Output
Header1         : [7m
Header2         : [93m
Header3         : [94m
Header4         : [95m
Header5         : [96m
Header6         : [97m
Code            : [48;2;155;155;155;38;2;30;30;31m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

## <span data-ttu-id="68132-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="68132-122">PARAMETERS</span></span>

### <span data-ttu-id="68132-123">-BoldForegroundColor</span><span class="sxs-lookup"><span data-stu-id="68132-123">-BoldForegroundColor</span></span>

<span data-ttu-id="68132-124">太字の Markdown テキストを表示する前景色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-124">Sets the foreground color for rendering bold Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-125">-コード</span><span class="sxs-lookup"><span data-stu-id="68132-125">-Code</span></span>

<span data-ttu-id="68132-126">Markdown テキストの表示コードブロックと範囲の色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-126">Sets the color for rendering code blocks and spans in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-127">-Header1Color</span><span class="sxs-lookup"><span data-stu-id="68132-127">-Header1Color</span></span>

<span data-ttu-id="68132-128">Markdown text の Header1 ブロックを表示するときの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-128">Sets the color for rendering Header1 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-129">-Header2Color</span><span class="sxs-lookup"><span data-stu-id="68132-129">-Header2Color</span></span>

<span data-ttu-id="68132-130">Markdown text の .Header2 ブロックを表示するときの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-130">Sets the color for rendering Header2 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-131">-Header3Color</span><span class="sxs-lookup"><span data-stu-id="68132-131">-Header3Color</span></span>

<span data-ttu-id="68132-132">Markdown text の Header3 ブロックを表示するときの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-132">Sets the color for rendering Header3 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-133">-Header4Color</span><span class="sxs-lookup"><span data-stu-id="68132-133">-Header4Color</span></span>

<span data-ttu-id="68132-134">Markdown text の Header4 ブロックを表示するときの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-134">Sets the color for rendering Header4 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-135">-Header5Color</span><span class="sxs-lookup"><span data-stu-id="68132-135">-Header5Color</span></span>

<span data-ttu-id="68132-136">Markdown text の Header5 ブロックを表示するときの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-136">Sets the color for rendering Header5 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-137">-Header6Color</span><span class="sxs-lookup"><span data-stu-id="68132-137">-Header6Color</span></span>

<span data-ttu-id="68132-138">Markdown text の Header6 ブロックを表示するときの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-138">Sets the color for rendering Header6 blocks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-139">-ImageAltTextForegroundColor</span><span class="sxs-lookup"><span data-stu-id="68132-139">-ImageAltTextForegroundColor</span></span>

<span data-ttu-id="68132-140">Markdown text 内の image 要素の代替テキストを表示する前景色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-140">Sets the foreground color for rendering the alternate text of an image element in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="68132-141">-InputObject</span></span>

<span data-ttu-id="68132-142">設定する構成を格納している **PSMarkdownOptionInfo** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="68132-142">A **PSMarkdownOptionInfo** object containing the configuration to be set.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="68132-143">-ItalicsForegroundColor</span><span class="sxs-lookup"><span data-stu-id="68132-143">-ItalicsForegroundColor</span></span>

<span data-ttu-id="68132-144">Markdown テキストで斜体を表示する前景色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-144">Sets the foreground color for rendering the italics in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-145">-LinkForegroundColor</span><span class="sxs-lookup"><span data-stu-id="68132-145">-LinkForegroundColor</span></span>

<span data-ttu-id="68132-146">Markdown text でのハイパーリンクの描画の前景色を設定します。</span><span class="sxs-lookup"><span data-stu-id="68132-146">Sets the foreground color for rendering hyperlinks in Markdown text.</span></span>

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-147">-PassThru</span><span class="sxs-lookup"><span data-stu-id="68132-147">-PassThru</span></span>

<span data-ttu-id="68132-148">コマンドレットによって、新しい構成を含む **PSMarkdownOptionInfo** オブジェクトが出力されます。</span><span class="sxs-lookup"><span data-stu-id="68132-148">Causes the cmdlet to output a **PSMarkdownOptionInfo** object containing the new configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-149">-テーマ</span><span class="sxs-lookup"><span data-stu-id="68132-149">-Theme</span></span>

<span data-ttu-id="68132-150">定義済みの色の設定を含むテーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="68132-150">Selects a theme containing predefined color settings.</span></span> <span data-ttu-id="68132-151">指定できる値は、 **ダーク** および **ライト** です。</span><span class="sxs-lookup"><span data-stu-id="68132-151">The possible values are **Dark** and **Light**.</span></span>

```yaml
Type: System.String
Parameter Sets: Theme
Aliases:
Accepted values: Dark, Light

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68132-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="68132-152">CommonParameters</span></span>

<span data-ttu-id="68132-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="68132-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="68132-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68132-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="68132-155">入力</span><span class="sxs-lookup"><span data-stu-id="68132-155">INPUTS</span></span>

### <span data-ttu-id="68132-156">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="68132-156">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="68132-157">出力</span><span class="sxs-lookup"><span data-stu-id="68132-157">OUTPUTS</span></span>

### <span data-ttu-id="68132-158">PSMarkdownOptionInfo を表示します。</span><span class="sxs-lookup"><span data-stu-id="68132-158">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="68132-159">注</span><span class="sxs-lookup"><span data-stu-id="68132-159">NOTES</span></span>

<span data-ttu-id="68132-160">色とスタイルを定義するために使用される文字列値は、正規表現と一致している必要があり `^\[*[0-9;]*?m{1}` ます。</span><span class="sxs-lookup"><span data-stu-id="68132-160">The string values used to define the color and style must match the regular expression `^\[*[0-9;]*?m{1}`.</span></span>

## <span data-ttu-id="68132-161">関連リンク</span><span class="sxs-lookup"><span data-stu-id="68132-161">RELATED LINKS</span></span>

[<span data-ttu-id="68132-162">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="68132-162">Get-MarkdownOption</span></span>](Get-MarkdownOption.md)

[<span data-ttu-id="68132-163">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="68132-163">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="68132-164">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="68132-164">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="68132-165">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="68132-165">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="68132-166">CommonMark</span><span class="sxs-lookup"><span data-stu-id="68132-166">CommonMark</span></span>](https://commonmark.org/)
