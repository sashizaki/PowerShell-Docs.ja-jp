---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 2885b2624f8334e8699e0baea5fc41b3f025fe2a
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "93220032"
---
# <span data-ttu-id="aff22-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="aff22-103">Get-Clipboard</span></span>

## <span data-ttu-id="aff22-104">概要</span><span class="sxs-lookup"><span data-stu-id="aff22-104">SYNOPSIS</span></span>
<span data-ttu-id="aff22-105">現在の Windows クリップボードエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="aff22-105">Gets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="aff22-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aff22-106">SYNTAX</span></span>

```
Get-Clipboard [-Format <ClipboardFormat>] [-TextFormatType <TextDataFormat>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="aff22-107">Description</span><span class="sxs-lookup"><span data-stu-id="aff22-107">DESCRIPTION</span></span>

<span data-ttu-id="aff22-108">`Get-Clipboard`コマンドレットは、現在の Windows クリップボードエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="aff22-108">The `Get-Clipboard` cmdlet gets the current Windows clipboard entry.</span></span> <span data-ttu-id="aff22-109">に類似した文字列の配列として、複数行のテキストが返され `Get-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="aff22-109">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

## <span data-ttu-id="aff22-110">例</span><span class="sxs-lookup"><span data-stu-id="aff22-110">EXAMPLES</span></span>

### <span data-ttu-id="aff22-111">例 1: クリップボードの内容を取得し、それをコマンドラインに表示する</span><span class="sxs-lookup"><span data-stu-id="aff22-111">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="aff22-112">この例では、ブラウザーで画像を右クリックし、[ **コピー** ] アクションを選択しました。</span><span class="sxs-lookup"><span data-stu-id="aff22-112">In this example we have right-clicked on an image in a browser and chose the **Copy** action.</span></span> <span data-ttu-id="aff22-113">次のコマンドは、クリップボードに格納されているイメージの URL としてのリンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="aff22-113">The following command displays the link, as a URL, of the image that is stored in the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
https://en.wikipedia.org/wiki/PowerShell
```

### <span data-ttu-id="aff22-114">例 2: 特定の形式でクリップボードの内容を取得する</span><span class="sxs-lookup"><span data-stu-id="aff22-114">Example 2: Get the content of the clipboard in a specific format</span></span>

<span data-ttu-id="aff22-115">この例では、Windows Explorerby でファイルを選択し、 <kbd>Ctrl + C</kbd>キーを押して、ファイルをクリップボードにコピーしました。</span><span class="sxs-lookup"><span data-stu-id="aff22-115">In this example we copied files to the clipboard in Windows Explorerby selecting them and pressing <kbd>Ctrl-C</kbd>.</span></span> <span data-ttu-id="aff22-116">次のコマンドを使用して、ファイルの一覧としてクリップボードの内容にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="aff22-116">Using the following command, you can access the contents of the clipboard as a list of files:</span></span>

```powershell
Get-Clipboard -Format FileDropList
```

```Output
    Directory: C:\Git\PS-Docs\PowerShell-Docs\wmf

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/7/2019   1:11 PM          10010 TOC.yml
-a----       11/18/2016  10:10 AM             53 md.style
-a----         5/6/2019   9:32 AM           4177 overview.md
-a----        6/28/2018   2:28 PM            345 README.md
```

## <span data-ttu-id="aff22-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aff22-117">PARAMETERS</span></span>

### <span data-ttu-id="aff22-118">-形式</span><span class="sxs-lookup"><span data-stu-id="aff22-118">-Format</span></span>

<span data-ttu-id="aff22-119">クリップボードの種類 (形式) を指定します。</span><span class="sxs-lookup"><span data-stu-id="aff22-119">Specifies the type, or format, of the clipboard.</span></span> <span data-ttu-id="aff22-120">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aff22-120">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="aff22-121">Text</span><span class="sxs-lookup"><span data-stu-id="aff22-121">Text</span></span>
- <span data-ttu-id="aff22-122">FileDropList</span><span class="sxs-lookup"><span data-stu-id="aff22-122">FileDropList</span></span>
- <span data-ttu-id="aff22-123">Image</span><span class="sxs-lookup"><span data-stu-id="aff22-123">Image</span></span>
- <span data-ttu-id="aff22-124">オーディオ</span><span class="sxs-lookup"><span data-stu-id="aff22-124">Audio</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ClipboardFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, FileDropList, Image, Audio

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aff22-125">-Raw</span><span class="sxs-lookup"><span data-stu-id="aff22-125">-Raw</span></span>

<span data-ttu-id="aff22-126">クリップボードの内容全体を取得します。</span><span class="sxs-lookup"><span data-stu-id="aff22-126">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="aff22-127">複数行テキストは、文字列の配列ではなく、単一の複数行文字列として返されます。</span><span class="sxs-lookup"><span data-stu-id="aff22-127">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="aff22-128">-TextFormatType</span><span class="sxs-lookup"><span data-stu-id="aff22-128">-TextFormatType</span></span>

<span data-ttu-id="aff22-129">クリップボードのテキストデータ形式の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="aff22-129">Specifies the text data format type of the clipboard.</span></span> <span data-ttu-id="aff22-130">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aff22-130">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="aff22-131">Text</span><span class="sxs-lookup"><span data-stu-id="aff22-131">Text</span></span>
- <span data-ttu-id="aff22-132">UnicodeText</span><span class="sxs-lookup"><span data-stu-id="aff22-132">UnicodeText</span></span>
- <span data-ttu-id="aff22-133">Rtf</span><span class="sxs-lookup"><span data-stu-id="aff22-133">Rtf</span></span>
- <span data-ttu-id="aff22-134">Html</span><span class="sxs-lookup"><span data-stu-id="aff22-134">Html</span></span>
- <span data-ttu-id="aff22-135">CommaSeparatedValue</span><span class="sxs-lookup"><span data-stu-id="aff22-135">CommaSeparatedValue</span></span>

```yaml
Type: System.Windows.Forms.TextDataFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, UnicodeText, Rtf, Html, CommaSeparatedValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aff22-136">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="aff22-136">CommonParameters</span></span>

<span data-ttu-id="aff22-137">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="aff22-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aff22-138">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aff22-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aff22-139">入力</span><span class="sxs-lookup"><span data-stu-id="aff22-139">INPUTS</span></span>

## <span data-ttu-id="aff22-140">出力</span><span class="sxs-lookup"><span data-stu-id="aff22-140">OUTPUTS</span></span>

### <span data-ttu-id="aff22-141">System.string, system.object, system.object, system.object, システムのイメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="aff22-141">System.String, System.IO.FileInfo, System.IO.Stream, System.Drawing.Image</span></span>

## <span data-ttu-id="aff22-142">注</span><span class="sxs-lookup"><span data-stu-id="aff22-142">NOTES</span></span>

## <span data-ttu-id="aff22-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="aff22-143">RELATED LINKS</span></span>

[<span data-ttu-id="aff22-144">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="aff22-144">Set-Clipboard</span></span>](Set-Clipboard.md)
