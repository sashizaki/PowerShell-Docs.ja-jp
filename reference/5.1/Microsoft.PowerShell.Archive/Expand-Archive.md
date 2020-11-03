---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: 41d571747a9b81cafff8c0ca20d5121163ece452
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "93218075"
---
# <span data-ttu-id="2f43f-103">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="2f43f-103">Expand-Archive</span></span>

## <span data-ttu-id="2f43f-104">概要</span><span class="sxs-lookup"><span data-stu-id="2f43f-104">SYNOPSIS</span></span>
<span data-ttu-id="2f43f-105">指定したアーカイブ (zip 形式) ファイルからファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-105">Extracts files from a specified archive (zipped) file.</span></span>

## <span data-ttu-id="2f43f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2f43f-106">SYNTAX</span></span>

### <span data-ttu-id="2f43f-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="2f43f-107">Path (Default)</span></span>

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="2f43f-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2f43f-108">LiteralPath</span></span>

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2f43f-109">Description</span><span class="sxs-lookup"><span data-stu-id="2f43f-109">DESCRIPTION</span></span>

<span data-ttu-id="2f43f-110">コマンドレットは、指定した `Expand-Archive` zip 形式のアーカイブファイルから、指定した保存先フォルダーにファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-110">The `Expand-Archive` cmdlet extracts files from a specified zipped archive file to a specified destination folder.</span></span> <span data-ttu-id="2f43f-111">アーカイブファイルを使用すると、配布と保存を容易にするために、複数のファイルを1つの zip ファイルにパッケージ化し、必要に応じて圧縮することができます。</span><span class="sxs-lookup"><span data-stu-id="2f43f-111">An archive file allows multiple files to be packaged, and optionally compressed, into a single zipped file for easier distribution and storage.</span></span>

## <span data-ttu-id="2f43f-112">例</span><span class="sxs-lookup"><span data-stu-id="2f43f-112">EXAMPLES</span></span>

### <span data-ttu-id="2f43f-113">例 1: アーカイブの内容を抽出する</span><span class="sxs-lookup"><span data-stu-id="2f43f-113">Example 1: Extract the contents of an archive</span></span>

<span data-ttu-id="2f43f-114">この例では、 **DestinationPath** パラメーターで指定したフォルダーに既存のアーカイブファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-114">This example extracts the contents of an existing archive file into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

<span data-ttu-id="2f43f-115">この例では、 **LiteralPath** パラメーターが使用されています。これは、ファイル名にワイルドカードとして解釈される可能性のある文字が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="2f43f-115">In this example, the **LiteralPath** parameter is used because the filename contains characters that could be interpreted as wildcards.</span></span>

### <span data-ttu-id="2f43f-116">例 2: 現在のフォルダー内のアーカイブの内容を抽出する</span><span class="sxs-lookup"><span data-stu-id="2f43f-116">Example 2: Extract the contents of an archive in the current folder</span></span>

<span data-ttu-id="2f43f-117">この例では、現在のフォルダーにある既存のアーカイブファイルの内容を、 **DestinationPath** パラメーターで指定したフォルダーに抽出します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-117">This example extracts the contents of an existing archive file in the current folder into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## <span data-ttu-id="2f43f-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2f43f-118">PARAMETERS</span></span>

### <span data-ttu-id="2f43f-119">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="2f43f-119">-DestinationPath</span></span>

<span data-ttu-id="2f43f-120">既定では、は、 `Expand-Archive` ZIP ファイルと同じ名前のフォルダーを現在の場所に作成します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-120">By default, `Expand-Archive` creates a folder in the current location that is the same name as the ZIP file.</span></span> <span data-ttu-id="2f43f-121">パラメーターを使用すると、別のフォルダーへのパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2f43f-121">The parameter allows you to specify the path to a different folder.</span></span> <span data-ttu-id="2f43f-122">ターゲットフォルダーが存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="2f43f-122">The target folder is created if it does not exist.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: A folder in the current location
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2f43f-123">-Force</span><span class="sxs-lookup"><span data-stu-id="2f43f-123">-Force</span></span>

<span data-ttu-id="2f43f-124">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-124">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="2f43f-125">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2f43f-125">-LiteralPath</span></span>

<span data-ttu-id="2f43f-126">アーカイブファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-126">Specifies the path to an archive file.</span></span> <span data-ttu-id="2f43f-127">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f43f-127">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="2f43f-128">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2f43f-128">Wildcard characters are not supported.</span></span> <span data-ttu-id="2f43f-129">パスにエスケープ文字が含まれている場合は、各エスケープ文字を単一引用符で囲み、すべての文字をエスケープシーケンスとして解釈しないように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-129">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2f43f-130">-Path</span><span class="sxs-lookup"><span data-stu-id="2f43f-130">-Path</span></span>

<span data-ttu-id="2f43f-131">アーカイブファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-131">Specifies the path to the archive file.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2f43f-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2f43f-132">-Confirm</span></span>

<span data-ttu-id="2f43f-133">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f43f-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2f43f-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2f43f-134">-WhatIf</span></span>

<span data-ttu-id="2f43f-135">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-135">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2f43f-136">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2f43f-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2f43f-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f43f-137">CommonParameters</span></span>
<span data-ttu-id="2f43f-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2f43f-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2f43f-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f43f-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2f43f-140">入力</span><span class="sxs-lookup"><span data-stu-id="2f43f-140">INPUTS</span></span>

### <span data-ttu-id="2f43f-141">System.String</span><span class="sxs-lookup"><span data-stu-id="2f43f-141">System.String</span></span>

<span data-ttu-id="2f43f-142">パイプを使用して、既存のアーカイブファイルへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f43f-142">You can pipe a string that contains a path to an existing archive file.</span></span>

## <span data-ttu-id="2f43f-143">出力</span><span class="sxs-lookup"><span data-stu-id="2f43f-143">OUTPUTS</span></span>

### <span data-ttu-id="2f43f-144">なし</span><span class="sxs-lookup"><span data-stu-id="2f43f-144">None</span></span>

## <span data-ttu-id="2f43f-145">注</span><span class="sxs-lookup"><span data-stu-id="2f43f-145">NOTES</span></span>

<span data-ttu-id="2f43f-146">[ZIP ファイルの仕様](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)では、ASCII 以外の文字を含むファイル名をエンコードするための標準的な方法は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="2f43f-146">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="2f43f-147">コマンドレットでは、 `Compress-Archive` utf-8 エンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-147">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="2f43f-148">他の ZIP アーカイブツールでは、別のエンコード方式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f43f-148">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="2f43f-149">UTF-8 エンコードを使用して格納されていないファイル名を使用してファイルを抽出すると、は `Expand-Archive` アーカイブで見つかった生の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f43f-149">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="2f43f-150">これにより、アーカイブに格納されているソースファイル名とは異なるファイル名が生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f43f-150">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="2f43f-151">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2f43f-151">RELATED LINKS</span></span>

[<span data-ttu-id="2f43f-152">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="2f43f-152">Compress-Archive</span></span>](compress-archive.md)
