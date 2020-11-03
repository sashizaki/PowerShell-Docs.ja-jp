---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: f3230c247296d5fd907d580e719cbbbc560183a9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214467"
---
# <span data-ttu-id="f469b-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="f469b-103">Set-Clipboard</span></span>

## <span data-ttu-id="f469b-104">概要</span><span class="sxs-lookup"><span data-stu-id="f469b-104">SYNOPSIS</span></span>
<span data-ttu-id="f469b-105">現在の Windows クリップボードエントリを設定します。</span><span class="sxs-lookup"><span data-stu-id="f469b-105">Sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="f469b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f469b-106">SYNTAX</span></span>

### <span data-ttu-id="f469b-107">String (既定値)</span><span class="sxs-lookup"><span data-stu-id="f469b-107">String (Default)</span></span>

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f469b-108">値</span><span class="sxs-lookup"><span data-stu-id="f469b-108">Value</span></span>

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f469b-109">Path</span><span class="sxs-lookup"><span data-stu-id="f469b-109">Path</span></span>

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f469b-110">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f469b-110">LiteralPath</span></span>

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f469b-111">Description</span><span class="sxs-lookup"><span data-stu-id="f469b-111">DESCRIPTION</span></span>

<span data-ttu-id="f469b-112">`Set-Clipboard`コマンドレットは、現在の Windows クリップボードエントリを設定します。</span><span class="sxs-lookup"><span data-stu-id="f469b-112">The `Set-Clipboard` cmdlet sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="f469b-113">例</span><span class="sxs-lookup"><span data-stu-id="f469b-113">EXAMPLES</span></span>

### <span data-ttu-id="f469b-114">例 1: テキストをクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="f469b-114">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="f469b-115">例 2: ディレクトリの内容をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="f469b-115">Example 2: Copy the contents of a directory to the clipboard</span></span>

<span data-ttu-id="f469b-116">このコマンドは、指定されたフォルダーの内容をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f469b-116">This command copies the content of the specified folder to the clipboard.</span></span>

```powershell
Set-Clipboard -Path "C:\Staging\"
```

## <span data-ttu-id="f469b-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f469b-117">PARAMETERS</span></span>

### <span data-ttu-id="f469b-118">-追加</span><span class="sxs-lookup"><span data-stu-id="f469b-118">-Append</span></span>

<span data-ttu-id="f469b-119">コマンドレットがクリップボードをクリアせずにコンテンツを追加しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f469b-119">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="f469b-120">-AsHtml</span><span class="sxs-lookup"><span data-stu-id="f469b-120">-AsHtml</span></span>

<span data-ttu-id="f469b-121">コマンドレットによってコンテンツが HTML としてクリップボードに表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f469b-121">Indicates that the cmdlet renders the content as HTML to the clipboard.</span></span>

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

### <span data-ttu-id="f469b-122">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f469b-122">-LiteralPath</span></span>

<span data-ttu-id="f469b-123">クリップボードにコピーされる項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f469b-123">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="f469b-124">**Path** とは異なり、 **LiteralPath** の値は入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="f469b-124">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="f469b-125">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="f469b-125">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f469b-126">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="f469b-126">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f469b-127">単一引用符で囲んだ文字はエスケープ シーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="f469b-127">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f469b-128">-Path</span><span class="sxs-lookup"><span data-stu-id="f469b-128">-Path</span></span>

<span data-ttu-id="f469b-129">クリップボードにコピーされる項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f469b-129">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="f469b-130">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f469b-130">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="f469b-131">-Value</span><span class="sxs-lookup"><span data-stu-id="f469b-131">-Value</span></span>

<span data-ttu-id="f469b-132">クリップボードにコピーするコンテンツを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="f469b-132">Specifies, as a string array, the content to copy to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Value
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f469b-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f469b-133">-Confirm</span></span>

<span data-ttu-id="f469b-134">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f469b-134">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f469b-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f469b-135">-WhatIf</span></span>

<span data-ttu-id="f469b-136">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="f469b-136">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f469b-137">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f469b-137">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f469b-138">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f469b-138">CommonParameters</span></span>

<span data-ttu-id="f469b-139">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f469b-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f469b-140">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f469b-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f469b-141">入力</span><span class="sxs-lookup"><span data-stu-id="f469b-141">INPUTS</span></span>

### <span data-ttu-id="f469b-142">System.String[]</span><span class="sxs-lookup"><span data-stu-id="f469b-142">System.String[]</span></span>

## <span data-ttu-id="f469b-143">出力</span><span class="sxs-lookup"><span data-stu-id="f469b-143">OUTPUTS</span></span>

## <span data-ttu-id="f469b-144">注</span><span class="sxs-lookup"><span data-stu-id="f469b-144">NOTES</span></span>

<span data-ttu-id="f469b-145">ループのように、頻繁に多数の値を指定してを使用する場合、 `Set-Clipboard` クリップボードから空白の値が返されることがまれにあります。</span><span class="sxs-lookup"><span data-stu-id="f469b-145">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="f469b-146">これは、ループ内でを使用して修正でき `Start-Sleep -Milliseconds 1` ます。</span><span class="sxs-lookup"><span data-stu-id="f469b-146">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="f469b-147">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f469b-147">RELATED LINKS</span></span>

[<span data-ttu-id="f469b-148">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="f469b-148">Get-Clipboard</span></span>](Get-Clipboard.md)
