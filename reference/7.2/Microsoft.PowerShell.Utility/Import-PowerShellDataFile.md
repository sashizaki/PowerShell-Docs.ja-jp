---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: d7942abff2974064c52a8a9ac086a280959b3a63
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "99602601"
---
# <span data-ttu-id="89523-102">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="89523-102">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="89523-103">概要</span><span class="sxs-lookup"><span data-stu-id="89523-103">SYNOPSIS</span></span>
<span data-ttu-id="89523-104">内容を呼び出さずに、ファイルから値をインポート `.PSD1` します。</span><span class="sxs-lookup"><span data-stu-id="89523-104">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="89523-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89523-105">SYNTAX</span></span>

### <span data-ttu-id="89523-106">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="89523-106">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [-Path] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

### <span data-ttu-id="89523-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="89523-107">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

## <span data-ttu-id="89523-108">Description</span><span class="sxs-lookup"><span data-stu-id="89523-108">DESCRIPTION</span></span>

<span data-ttu-id="89523-109">`Import-PowerShellDataFile`コマンドレットは、ファイルで定義されているハッシュテーブルからキーと値のペアを安全にインポートし `.PSD1` ます。</span><span class="sxs-lookup"><span data-stu-id="89523-109">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="89523-110">値は、 `Invoke-Expression` ファイルの内容に対してを使用してインポートできます。</span><span class="sxs-lookup"><span data-stu-id="89523-110">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="89523-111">ただし、は、 `Invoke-Expression` ファイルに格納されているすべてのコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="89523-111">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="89523-112">これは、望ましくない結果を生成したり、アンセーフコードを実行したりする可能性があります</span><span class="sxs-lookup"><span data-stu-id="89523-112">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="89523-113">`Import-PowerShellDataFile` コードを呼び出さずにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="89523-113">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span> <span data-ttu-id="89523-114">既定では、500キーの制限がありますが、 **SkipLimitCheck** スイッチでバイパスすることができます。</span><span class="sxs-lookup"><span data-stu-id="89523-114">By default there is a 500 key limit but can be bypassed with the **SkipLimitCheck** switch.</span></span>

## <span data-ttu-id="89523-115">例</span><span class="sxs-lookup"><span data-stu-id="89523-115">EXAMPLES</span></span>

### <span data-ttu-id="89523-116">例 1: .PSD1 から値を取得する</span><span class="sxs-lookup"><span data-stu-id="89523-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="89523-117">この例では、ハッシュテーブルに格納されているキーと値のペアを取得、ファイル内に保持し `Configuration.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="89523-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="89523-118">`Get-Content` は、ファイルの内容を表示するために使用され `Configuration.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="89523-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

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

## <span data-ttu-id="89523-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89523-119">PARAMETERS</span></span>

### <span data-ttu-id="89523-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="89523-120">-LiteralPath</span></span>

<span data-ttu-id="89523-121">インポートされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="89523-121">The path to the file being imported.</span></span> <span data-ttu-id="89523-122">パス内のすべての文字は、リテラル値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="89523-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="89523-123">ワイルドカード文字は処理されません。</span><span class="sxs-lookup"><span data-stu-id="89523-123">Wildcard characters are not processed.</span></span>

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

### <span data-ttu-id="89523-124">-Path</span><span class="sxs-lookup"><span data-stu-id="89523-124">-Path</span></span>

<span data-ttu-id="89523-125">インポートされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="89523-125">The path to the file being imported.</span></span> <span data-ttu-id="89523-126">ワイルドカードは使用できますが、最初に一致するファイルのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="89523-126">Wildcards are allowed but only the first matching file is imported.</span></span>

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

### <span data-ttu-id="89523-127">-SkipLimitCheck</span><span class="sxs-lookup"><span data-stu-id="89523-127">-SkipLimitCheck</span></span>

<span data-ttu-id="89523-128">既定で `Import-PowerShellDataFile` は、ファイルから500キーのみがインポートさ `.psd1` れます。</span><span class="sxs-lookup"><span data-stu-id="89523-128">By default `Import-PowerShellDataFile` imports only 500 keys from a `.psd1` file.</span></span> <span data-ttu-id="89523-129">500を超えるキーをインポートするには、 **SkipLimitCheck** を使用します。</span><span class="sxs-lookup"><span data-stu-id="89523-129">Use **SkipLimitCheck** to import more than 500 keys.</span></span>

```yaml
Type: Switch
Parameter Sets: All
Aliases:

Required: False
Position: 0
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89523-130">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="89523-130">CommonParameters</span></span>

<span data-ttu-id="89523-131">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="89523-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89523-132">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89523-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="89523-133">入力</span><span class="sxs-lookup"><span data-stu-id="89523-133">INPUTS</span></span>

## <span data-ttu-id="89523-134">出力</span><span class="sxs-lookup"><span data-stu-id="89523-134">OUTPUTS</span></span>

### <span data-ttu-id="89523-135">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="89523-135">System.Collections.Hashtable</span></span>

## <span data-ttu-id="89523-136">注</span><span class="sxs-lookup"><span data-stu-id="89523-136">NOTES</span></span>

## <span data-ttu-id="89523-137">関連リンク</span><span class="sxs-lookup"><span data-stu-id="89523-137">RELATED LINKS</span></span>

[<span data-ttu-id="89523-138">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="89523-138">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="89523-139">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="89523-139">Import-LocalizedData</span></span>](Import-LocalizedData.md)
