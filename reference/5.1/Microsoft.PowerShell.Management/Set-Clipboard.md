---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: c1cf126e41a5e918afffbc41d30f957e650efdf5
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564504"
---
# <span data-ttu-id="50c70-102">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="50c70-102">Set-Clipboard</span></span>

## <span data-ttu-id="50c70-103">概要</span><span class="sxs-lookup"><span data-stu-id="50c70-103">SYNOPSIS</span></span>
<span data-ttu-id="50c70-104">現在の Windows クリップボードエントリを設定します。</span><span class="sxs-lookup"><span data-stu-id="50c70-104">Sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="50c70-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="50c70-105">SYNTAX</span></span>

### <span data-ttu-id="50c70-106">String (既定値)</span><span class="sxs-lookup"><span data-stu-id="50c70-106">String (Default)</span></span>

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50c70-107">値</span><span class="sxs-lookup"><span data-stu-id="50c70-107">Value</span></span>

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50c70-108">パス</span><span class="sxs-lookup"><span data-stu-id="50c70-108">Path</span></span>

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50c70-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="50c70-109">LiteralPath</span></span>

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="50c70-110">Description</span><span class="sxs-lookup"><span data-stu-id="50c70-110">DESCRIPTION</span></span>

<span data-ttu-id="50c70-111">`Set-Clipboard`コマンドレットは、現在の Windows クリップボードエントリを設定します。</span><span class="sxs-lookup"><span data-stu-id="50c70-111">The `Set-Clipboard` cmdlet sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="50c70-112">例</span><span class="sxs-lookup"><span data-stu-id="50c70-112">EXAMPLES</span></span>

### <span data-ttu-id="50c70-113">例 1: テキストをクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="50c70-113">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="50c70-114">例 2: ディレクトリの内容をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="50c70-114">Example 2: Copy the contents of a directory to the clipboard</span></span>

<span data-ttu-id="50c70-115">この例では、指定したフォルダーの内容をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="50c70-115">This example copies the content of the specified folder to the clipboard.</span></span>

```powershell
Set-Clipboard -Path "C:\Staging\"
```

### <span data-ttu-id="50c70-116">例 3: ファイルの内容をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="50c70-116">Example 3: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="50c70-117">この例では、ファイルの内容をクリップボードにパイプします。</span><span class="sxs-lookup"><span data-stu-id="50c70-117">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="50c70-118">この例では、GitHub などの別のアプリケーションに貼り付けることができるように、ssh の公開キーを取得しています。</span><span class="sxs-lookup"><span data-stu-id="50c70-118">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="50c70-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="50c70-119">PARAMETERS</span></span>

### <span data-ttu-id="50c70-120">-追加</span><span class="sxs-lookup"><span data-stu-id="50c70-120">-Append</span></span>

<span data-ttu-id="50c70-121">コマンドレットがクリップボードをクリアせずにコンテンツを追加しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="50c70-121">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="50c70-122">-AsHtml</span><span class="sxs-lookup"><span data-stu-id="50c70-122">-AsHtml</span></span>

<span data-ttu-id="50c70-123">コマンドレットによってコンテンツが HTML としてクリップボードに表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="50c70-123">Indicates that the cmdlet renders the content as HTML to the clipboard.</span></span>

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

### <span data-ttu-id="50c70-124">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="50c70-124">-LiteralPath</span></span>

<span data-ttu-id="50c70-125">クリップボードにコピーされる項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="50c70-125">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="50c70-126">**Path** とは異なり、**LiteralPath** の値は入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="50c70-126">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="50c70-127">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="50c70-127">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="50c70-128">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="50c70-128">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="50c70-129">単一引用符で囲んだ文字はエスケープ シーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="50c70-129">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="50c70-130">-Path</span><span class="sxs-lookup"><span data-stu-id="50c70-130">-Path</span></span>

<span data-ttu-id="50c70-131">クリップボードにコピーされる項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="50c70-131">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="50c70-132">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="50c70-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="50c70-133">-Value</span><span class="sxs-lookup"><span data-stu-id="50c70-133">-Value</span></span>

<span data-ttu-id="50c70-134">クリップボードにコピーするコンテンツを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="50c70-134">Specifies, as a string array, the content to copy to the clipboard.</span></span>

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

### <span data-ttu-id="50c70-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="50c70-135">-Confirm</span></span>

<span data-ttu-id="50c70-136">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50c70-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="50c70-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="50c70-137">-WhatIf</span></span>

<span data-ttu-id="50c70-138">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="50c70-138">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="50c70-139">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="50c70-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="50c70-140">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="50c70-140">CommonParameters</span></span>

<span data-ttu-id="50c70-141">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="50c70-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="50c70-142">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50c70-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="50c70-143">入力</span><span class="sxs-lookup"><span data-stu-id="50c70-143">INPUTS</span></span>

### <span data-ttu-id="50c70-144">System.String[]</span><span class="sxs-lookup"><span data-stu-id="50c70-144">System.String[]</span></span>

## <span data-ttu-id="50c70-145">出力</span><span class="sxs-lookup"><span data-stu-id="50c70-145">OUTPUTS</span></span>

## <span data-ttu-id="50c70-146">注</span><span class="sxs-lookup"><span data-stu-id="50c70-146">NOTES</span></span>

<span data-ttu-id="50c70-147">ループのように、頻繁に多数の値を指定してを使用する場合、 `Set-Clipboard` クリップボードから空白の値が返されることがまれにあります。</span><span class="sxs-lookup"><span data-stu-id="50c70-147">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="50c70-148">これは、ループ内でを使用して修正でき `Start-Sleep -Milliseconds 1` ます。</span><span class="sxs-lookup"><span data-stu-id="50c70-148">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="50c70-149">関連リンク</span><span class="sxs-lookup"><span data-stu-id="50c70-149">RELATED LINKS</span></span>

[<span data-ttu-id="50c70-150">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="50c70-150">Get-Clipboard</span></span>](Get-Clipboard.md)
