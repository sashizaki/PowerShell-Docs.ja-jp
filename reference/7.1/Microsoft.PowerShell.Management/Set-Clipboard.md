---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/09/2019
online version: https://go.microsoft.com/fwlink/?linkid=526220
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: 6fbe7b1e5534b1227bcfd73fd58f3602186ef8c5
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239673"
---
# <span data-ttu-id="d38d0-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="d38d0-103">Set-Clipboard</span></span>

## <span data-ttu-id="d38d0-104">概要</span><span class="sxs-lookup"><span data-stu-id="d38d0-104">SYNOPSIS</span></span>
<span data-ttu-id="d38d0-105">クリップボードの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="d38d0-105">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="d38d0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d38d0-106">SYNTAX</span></span>

```
Set-Clipboard -Value <String[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d38d0-107">Description</span><span class="sxs-lookup"><span data-stu-id="d38d0-107">DESCRIPTION</span></span>

<span data-ttu-id="d38d0-108">コマンドレットでは、 `Set-Clipboard` クリップボードの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="d38d0-108">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="d38d0-109">Linux では、このコマンドレットでは `xclip` ユーティリティをパスに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d38d0-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="d38d0-110">例</span><span class="sxs-lookup"><span data-stu-id="d38d0-110">EXAMPLES</span></span>

### <span data-ttu-id="d38d0-111">例 1: テキストをクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="d38d0-111">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

## <span data-ttu-id="d38d0-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d38d0-112">PARAMETERS</span></span>

### <span data-ttu-id="d38d0-113">-追加</span><span class="sxs-lookup"><span data-stu-id="d38d0-113">-Append</span></span>

<span data-ttu-id="d38d0-114">コマンドレットがクリップボードをクリアせずにコンテンツを追加しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="d38d0-114">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="d38d0-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d38d0-115">-Confirm</span></span>

<span data-ttu-id="d38d0-116">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d38d0-116">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d38d0-117">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d38d0-117">-WhatIf</span></span>

<span data-ttu-id="d38d0-118">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="d38d0-118">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d38d0-119">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d38d0-119">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d38d0-120">-Value</span><span class="sxs-lookup"><span data-stu-id="d38d0-120">-Value</span></span>

<span data-ttu-id="d38d0-121">クリップボードに追加する文字列値。</span><span class="sxs-lookup"><span data-stu-id="d38d0-121">The string values to be added to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d38d0-122">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d38d0-122">CommonParameters</span></span>

<span data-ttu-id="d38d0-123">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d38d0-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d38d0-124">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d38d0-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d38d0-125">入力</span><span class="sxs-lookup"><span data-stu-id="d38d0-125">INPUTS</span></span>

### <span data-ttu-id="d38d0-126">System.String[]</span><span class="sxs-lookup"><span data-stu-id="d38d0-126">System.String[]</span></span>

## <span data-ttu-id="d38d0-127">出力</span><span class="sxs-lookup"><span data-stu-id="d38d0-127">OUTPUTS</span></span>

## <span data-ttu-id="d38d0-128">注</span><span class="sxs-lookup"><span data-stu-id="d38d0-128">NOTES</span></span>

<span data-ttu-id="d38d0-129">ループのように、頻繁に多数の値を指定してを使用する場合、 `Set-Clipboard` クリップボードから空白の値が返されることがまれにあります。</span><span class="sxs-lookup"><span data-stu-id="d38d0-129">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="d38d0-130">これは、ループ内でを使用して修正でき `Start-Sleep -Milliseconds 1` ます。</span><span class="sxs-lookup"><span data-stu-id="d38d0-130">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="d38d0-131">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d38d0-131">RELATED LINKS</span></span>

[<span data-ttu-id="d38d0-132">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="d38d0-132">Get-Clipboard</span></span>](Get-Clipboard.md)
