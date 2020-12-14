---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: efb24b14122ad37043636d999afaa4199eb3097b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564375"
---
# <span data-ttu-id="91e9c-102">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="91e9c-102">Set-Clipboard</span></span>

## <span data-ttu-id="91e9c-103">概要</span><span class="sxs-lookup"><span data-stu-id="91e9c-103">SYNOPSIS</span></span>
<span data-ttu-id="91e9c-104">クリップボードの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="91e9c-104">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="91e9c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91e9c-105">SYNTAX</span></span>

```
Set-Clipboard [-Value] <string[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="91e9c-106">Description</span><span class="sxs-lookup"><span data-stu-id="91e9c-106">DESCRIPTION</span></span>

<span data-ttu-id="91e9c-107">コマンドレットでは、 `Set-Clipboard` クリップボードの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="91e9c-107">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="91e9c-108">Linux では、このコマンドレットでは `xclip` ユーティリティをパスに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91e9c-108">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="91e9c-109">例</span><span class="sxs-lookup"><span data-stu-id="91e9c-109">EXAMPLES</span></span>

### <span data-ttu-id="91e9c-110">例 1: テキストをクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="91e9c-110">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="91e9c-111">例 2: ファイルの内容をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="91e9c-111">Example 2: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="91e9c-112">この例では、ファイルの内容をクリップボードにパイプします。</span><span class="sxs-lookup"><span data-stu-id="91e9c-112">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="91e9c-113">この例では、GitHub などの別のアプリケーションに貼り付けることができるように、ssh の公開キーを取得しています。</span><span class="sxs-lookup"><span data-stu-id="91e9c-113">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="91e9c-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91e9c-114">PARAMETERS</span></span>

### <span data-ttu-id="91e9c-115">-追加</span><span class="sxs-lookup"><span data-stu-id="91e9c-115">-Append</span></span>

<span data-ttu-id="91e9c-116">コマンドレットがクリップボードをクリアせずにコンテンツを追加しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="91e9c-116">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="91e9c-117">-Confirm</span><span class="sxs-lookup"><span data-stu-id="91e9c-117">-Confirm</span></span>

<span data-ttu-id="91e9c-118">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e9c-118">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="91e9c-119">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="91e9c-119">-WhatIf</span></span>

<span data-ttu-id="91e9c-120">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="91e9c-120">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="91e9c-121">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="91e9c-121">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="91e9c-122">-Value</span><span class="sxs-lookup"><span data-stu-id="91e9c-122">-Value</span></span>

<span data-ttu-id="91e9c-123">クリップボードに追加する文字列値。</span><span class="sxs-lookup"><span data-stu-id="91e9c-123">The string values to be added to the clipboard.</span></span>

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

### <span data-ttu-id="91e9c-124">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="91e9c-124">CommonParameters</span></span>

<span data-ttu-id="91e9c-125">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="91e9c-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91e9c-126">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91e9c-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91e9c-127">入力</span><span class="sxs-lookup"><span data-stu-id="91e9c-127">INPUTS</span></span>

### <span data-ttu-id="91e9c-128">System.String[]</span><span class="sxs-lookup"><span data-stu-id="91e9c-128">System.String[]</span></span>

## <span data-ttu-id="91e9c-129">出力</span><span class="sxs-lookup"><span data-stu-id="91e9c-129">OUTPUTS</span></span>

## <span data-ttu-id="91e9c-130">注</span><span class="sxs-lookup"><span data-stu-id="91e9c-130">NOTES</span></span>

<span data-ttu-id="91e9c-131">ループのように、頻繁に多数の値を指定してを使用する場合、 `Set-Clipboard` クリップボードから空白の値が返されることがまれにあります。</span><span class="sxs-lookup"><span data-stu-id="91e9c-131">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="91e9c-132">これは、ループ内でを使用して修正でき `Start-Sleep -Milliseconds 1` ます。</span><span class="sxs-lookup"><span data-stu-id="91e9c-132">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="91e9c-133">関連リンク</span><span class="sxs-lookup"><span data-stu-id="91e9c-133">RELATED LINKS</span></span>

[<span data-ttu-id="91e9c-134">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="91e9c-134">Get-Clipboard</span></span>](Get-Clipboard.md)
