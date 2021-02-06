---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: c694e73e69c1e51ecf88f445684923ef5f19113f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601811"
---
# <span data-ttu-id="d78c5-102">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="d78c5-102">ConvertFrom-Markdown</span></span>

## <span data-ttu-id="d78c5-103">概要</span><span class="sxs-lookup"><span data-stu-id="d78c5-103">SYNOPSIS</span></span>
<span data-ttu-id="d78c5-104">文字列またはファイルの内容を **Markdowninfo** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="d78c5-104">Convert the contents of a string or a file to a **MarkdownInfo** object.</span></span>

## <span data-ttu-id="d78c5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d78c5-105">SYNTAX</span></span>

### <span data-ttu-id="d78c5-106">PathParamSet (既定)</span><span class="sxs-lookup"><span data-stu-id="d78c5-106">PathParamSet (Default)</span></span>

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="d78c5-107">LiteralParamSet</span><span class="sxs-lookup"><span data-stu-id="d78c5-107">LiteralParamSet</span></span>

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="d78c5-108">InputObjParamSet</span><span class="sxs-lookup"><span data-stu-id="d78c5-108">InputObjParamSet</span></span>

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## <span data-ttu-id="d78c5-109">Description</span><span class="sxs-lookup"><span data-stu-id="d78c5-109">DESCRIPTION</span></span>

<span data-ttu-id="d78c5-110">このコマンドレットは、指定されたコンテンツを **Markdowninfo** に変換します。</span><span class="sxs-lookup"><span data-stu-id="d78c5-110">This cmdlet converts the specified content into a **MarkdownInfo**.</span></span> <span data-ttu-id="d78c5-111">**Path** パラメーターにファイルパスを指定すると、ファイルの内容が変換されます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-111">When a file path is specified for the **Path** parameter, the contents on the file are converted.</span></span> <span data-ttu-id="d78c5-112">出力オブジェクトには、次の3つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d78c5-112">The output object has three properties:</span></span>

- <span data-ttu-id="d78c5-113">**Token** プロパティには、変換されたオブジェクトの抽象構文ツリー (AST) があります。</span><span class="sxs-lookup"><span data-stu-id="d78c5-113">The **Token** property has the abstract syntax tree (AST) of the the converted object</span></span>
- <span data-ttu-id="d78c5-114">**Html** プロパティには、指定した入力の html 変換が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-114">The **Html** property has the HTML conversion of the specified input</span></span>
- <span data-ttu-id="d78c5-115">**AsVT100EncodedString** パラメーターが指定されている場合、 **VT100EncodedString** プロパティには、ANSI (VT100) エスケープシーケンスで変換された文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-115">The **VT100EncodedString** property has the converted string with ANSI (VT100) escape sequences if the **AsVT100EncodedString** parameter was specified</span></span>

<span data-ttu-id="d78c5-116">このコマンドレットは、PowerShell 6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d78c5-116">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="d78c5-117">例</span><span class="sxs-lookup"><span data-stu-id="d78c5-117">EXAMPLES</span></span>

### <span data-ttu-id="d78c5-118">例 1: Markdown コンテンツを含むファイルを HTML に変換する</span><span class="sxs-lookup"><span data-stu-id="d78c5-118">Example 1: Convert a file containing Markdown content to HTML</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md
```

<span data-ttu-id="d78c5-119">**Markdowninfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-119">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="d78c5-120">**Tokens** プロパティには、ファイルの変換された内容の AST が含まれてい `README.md` ます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-120">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="d78c5-121">**Html** プロパティには、html で変換されたファイルの内容があり `README.md` ます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-121">The **Html** property has the HTML converted content of the `README.md` file.</span></span>

### <span data-ttu-id="d78c5-122">例 2: Markdown コンテンツを含むファイルを VT100 でエンコードされた文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="d78c5-122">Example 2: Convert a file containing Markdown content to a VT100-encoded string</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

<span data-ttu-id="d78c5-123">**Markdowninfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-123">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="d78c5-124">**Tokens** プロパティには、ファイルの変換された内容の AST が含まれてい `README.md` ます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-124">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="d78c5-125">**VT100EncodedString** プロパティには、VT100 でエンコードされた、ファイルの内容が変換された文字列があり `README.md` ます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-125">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="d78c5-126">例 3: Markdown コンテンツを含む入力オブジェクトを VT100 でエンコードされた文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="d78c5-126">Example 3: Convert input object containing Markdown content to a VT100-encoded string</span></span>

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="d78c5-127">**Markdowninfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-127">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="d78c5-128">からの **FileInfo** オブジェクト `Get-Item` は、VT100 でエンコードされた文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-128">The **FileInfo** object from `Get-Item` is converted to a VT100-encoded string.</span></span> <span data-ttu-id="d78c5-129">**Tokens** プロパティには、ファイルの変換された内容の AST が含まれてい `README.md` ます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-129">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="d78c5-130">**VT100EncodedString** プロパティには、VT100 でエンコードされた、ファイルの内容が変換された文字列があり `README.md` ます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-130">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="d78c5-131">例 4: Markdown コンテンツを含む文字列を VT100 でエンコードされた文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="d78c5-131">Example 4: Convert a string containing Markdown content to a VT100-encoded string</span></span>

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="d78c5-132">**Markdowninfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-132">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="d78c5-133">指定された文字列は、VT100 でエンコードされた `**Bold text**` 文字列に変換され、 **VT100EncodedString** プロパティで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-133">The specified string `**Bold text**` is converted to a VT100-encoded string and available in **VT100EncodedString** property.</span></span>

## <span data-ttu-id="d78c5-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d78c5-134">PARAMETERS</span></span>

### <span data-ttu-id="d78c5-135">-AsVT100EncodedString</span><span class="sxs-lookup"><span data-stu-id="d78c5-135">-AsVT100EncodedString</span></span>

<span data-ttu-id="d78c5-136">出力を VT100 エスケープコードを使用して文字列としてエンコードするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d78c5-136">Specifies if the output should be encoded as a string with VT100 escape codes.</span></span>

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

### <span data-ttu-id="d78c5-137">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d78c5-137">-InputObject</span></span>

<span data-ttu-id="d78c5-138">変換するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d78c5-138">Specifies the object to be converted.</span></span> <span data-ttu-id="d78c5-139">**System.string 型の** オブジェクトを指定すると、文字列が変換されます。</span><span class="sxs-lookup"><span data-stu-id="d78c5-139">When an object of type **System.String** is specified, the string is converted.</span></span> <span data-ttu-id="d78c5-140">System.object 型のオブジェクトを指定すると、オブジェクトによって指定されたファイルの内容が変換され **ます。**</span><span class="sxs-lookup"><span data-stu-id="d78c5-140">When an object of type **System.IO.FileInfo** is specified, the contents of the file specified by the object are converted.</span></span> <span data-ttu-id="d78c5-141">他の種類のオブジェクトの場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d78c5-141">Objects of any other type result in an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObjParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d78c5-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d78c5-142">-LiteralPath</span></span>

<span data-ttu-id="d78c5-143">変換するファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d78c5-143">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralParamSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d78c5-144">-Path</span><span class="sxs-lookup"><span data-stu-id="d78c5-144">-Path</span></span>

<span data-ttu-id="d78c5-145">変換するファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d78c5-145">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PathParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d78c5-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d78c5-146">CommonParameters</span></span>

<span data-ttu-id="d78c5-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d78c5-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d78c5-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d78c5-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d78c5-149">入力</span><span class="sxs-lookup"><span data-stu-id="d78c5-149">INPUTS</span></span>

### <span data-ttu-id="d78c5-150">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="d78c5-150">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="d78c5-151">出力</span><span class="sxs-lookup"><span data-stu-id="d78c5-151">OUTPUTS</span></span>

### <span data-ttu-id="d78c5-152">Microsoft... Markdownrender</span><span class="sxs-lookup"><span data-stu-id="d78c5-152">Microsoft.PowerShell.MarkdownRender.MarkdownInfo</span></span>

## <span data-ttu-id="d78c5-153">注</span><span class="sxs-lookup"><span data-stu-id="d78c5-153">NOTES</span></span>

## <span data-ttu-id="d78c5-154">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d78c5-154">RELATED LINKS</span></span>

[<span data-ttu-id="d78c5-155">Markdown パーサー</span><span class="sxs-lookup"><span data-stu-id="d78c5-155">Markdown Parser</span></span>](https://github.com/lunet-io/markdig)

[<span data-ttu-id="d78c5-156">ANSI エスケープコード</span><span class="sxs-lookup"><span data-stu-id="d78c5-156">ANSI escape code</span></span>](https://wikipedia.org/wiki/ANSI_escape_code)

