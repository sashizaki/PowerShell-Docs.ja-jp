---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: f25191d27013469023b9fcfb03650a8693c6ddb4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209731"
---
# <span data-ttu-id="f5ccc-103">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="f5ccc-103">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="f5ccc-104">概要</span><span class="sxs-lookup"><span data-stu-id="f5ccc-104">SYNOPSIS</span></span>
<span data-ttu-id="f5ccc-105">内容を呼び出さずに、ファイルから値をインポート `.PSD1` します。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-105">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="f5ccc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f5ccc-106">SYNTAX</span></span>

### <span data-ttu-id="f5ccc-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="f5ccc-107">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="f5ccc-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="f5ccc-108">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="f5ccc-109">Description</span><span class="sxs-lookup"><span data-stu-id="f5ccc-109">DESCRIPTION</span></span>

<span data-ttu-id="f5ccc-110">`Import-PowerShellDataFile`コマンドレットは、ファイルで定義されているハッシュテーブルからキーと値のペアを安全にインポートし `.PSD1` ます。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-110">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="f5ccc-111">値は、 `Invoke-Expression` ファイルの内容に対してを使用してインポートできます。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-111">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="f5ccc-112">ただし、は、 `Invoke-Expression` ファイルに格納されているすべてのコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-112">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="f5ccc-113">これは、望ましくない結果を生成したり、アンセーフコードを実行したりする可能性があります</span><span class="sxs-lookup"><span data-stu-id="f5ccc-113">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="f5ccc-114">`Import-PowerShellDataFile` コードを呼び出さずにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-114">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span>

## <span data-ttu-id="f5ccc-115">例</span><span class="sxs-lookup"><span data-stu-id="f5ccc-115">EXAMPLES</span></span>

### <span data-ttu-id="f5ccc-116">例 1: .PSD1 から値を取得する</span><span class="sxs-lookup"><span data-stu-id="f5ccc-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="f5ccc-117">この例では、ハッシュテーブルに格納されているキーと値のペアを取得、ファイル内に保持し `Configuration.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="f5ccc-118">`Get-Content` は、ファイルの内容を表示するために使用され `Configuration.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

```powershell
Get-Content .\Configuration.psd1
$config = Import-PowerShellDataFile .\Configuration.psd1
$config.AllNodes
```

```Output
@{
    AllNodes = @(
        @{
            NodeName = 'DSC-01'
        }
        @{
            NodeName = 'DSC-02'
        }
    )
}

Name                           Value
----                           -----
NodeName                       DSC-01
NodeName                       DSC-02
```

## <span data-ttu-id="f5ccc-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f5ccc-119">PARAMETERS</span></span>

### <span data-ttu-id="f5ccc-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f5ccc-120">-LiteralPath</span></span>

<span data-ttu-id="f5ccc-121">インポートされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-121">The path to the file being imported.</span></span> <span data-ttu-id="f5ccc-122">パス内のすべての文字は、リテラル値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="f5ccc-123">ワイルドカード文字は処理されません。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-123">Wildcard characters are not processed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f5ccc-124">-Path</span><span class="sxs-lookup"><span data-stu-id="f5ccc-124">-Path</span></span>

<span data-ttu-id="f5ccc-125">インポートされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-125">The path to the file being imported.</span></span> <span data-ttu-id="f5ccc-126">ワイルドカードは使用できますが、最初に一致するファイルのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-126">Wildcards are allowed but only the first matching file is imported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f5ccc-127">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5ccc-127">CommonParameters</span></span>

<span data-ttu-id="f5ccc-128">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f5ccc-129">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5ccc-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f5ccc-130">入力</span><span class="sxs-lookup"><span data-stu-id="f5ccc-130">INPUTS</span></span>

## <span data-ttu-id="f5ccc-131">出力</span><span class="sxs-lookup"><span data-stu-id="f5ccc-131">OUTPUTS</span></span>

### <span data-ttu-id="f5ccc-132">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="f5ccc-132">System.Collections.Hashtable</span></span>

## <span data-ttu-id="f5ccc-133">注</span><span class="sxs-lookup"><span data-stu-id="f5ccc-133">NOTES</span></span>

## <span data-ttu-id="f5ccc-134">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f5ccc-134">RELATED LINKS</span></span>

[<span data-ttu-id="f5ccc-135">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="f5ccc-135">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="f5ccc-136">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="f5ccc-136">Import-LocalizedData</span></span>](Import-LocalizedData.md)
