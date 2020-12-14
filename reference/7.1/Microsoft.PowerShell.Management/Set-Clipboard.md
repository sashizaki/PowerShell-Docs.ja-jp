---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: 1ee55dfaf4ecd3e46bedd8f356b1f677180c9c62
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564556"
---
# <span data-ttu-id="42e0e-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="42e0e-103">Set-Clipboard</span></span>

## <span data-ttu-id="42e0e-104">概要</span><span class="sxs-lookup"><span data-stu-id="42e0e-104">SYNOPSIS</span></span>
<span data-ttu-id="42e0e-105">クリップボードの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="42e0e-105">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="42e0e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="42e0e-106">SYNTAX</span></span>

```
Set-Clipboard -Value <String[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="42e0e-107">Description</span><span class="sxs-lookup"><span data-stu-id="42e0e-107">DESCRIPTION</span></span>

<span data-ttu-id="42e0e-108">コマンドレットでは、 `Set-Clipboard` クリップボードの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="42e0e-108">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="42e0e-109">Linux では、このコマンドレットでは `xclip` ユーティリティをパスに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42e0e-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="42e0e-110">例</span><span class="sxs-lookup"><span data-stu-id="42e0e-110">EXAMPLES</span></span>

### <span data-ttu-id="42e0e-111">例 1: テキストをクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="42e0e-111">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="42e0e-112">例 2: ファイルの内容をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="42e0e-112">Example 2: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="42e0e-113">この例では、ファイルの内容をクリップボードにパイプします。</span><span class="sxs-lookup"><span data-stu-id="42e0e-113">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="42e0e-114">この例では、GitHub などの別のアプリケーションに貼り付けることができるように、ssh の公開キーを取得しています。</span><span class="sxs-lookup"><span data-stu-id="42e0e-114">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="42e0e-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="42e0e-115">PARAMETERS</span></span>

### <span data-ttu-id="42e0e-116">-追加</span><span class="sxs-lookup"><span data-stu-id="42e0e-116">-Append</span></span>

<span data-ttu-id="42e0e-117">コマンドレットがクリップボードをクリアせずにコンテンツを追加しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="42e0e-117">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="42e0e-118">-Confirm</span><span class="sxs-lookup"><span data-stu-id="42e0e-118">-Confirm</span></span>

<span data-ttu-id="42e0e-119">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="42e0e-119">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="42e0e-120">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="42e0e-120">-WhatIf</span></span>

<span data-ttu-id="42e0e-121">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="42e0e-121">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="42e0e-122">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="42e0e-122">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="42e0e-123">-Value</span><span class="sxs-lookup"><span data-stu-id="42e0e-123">-Value</span></span>

<span data-ttu-id="42e0e-124">クリップボードに追加する文字列値。</span><span class="sxs-lookup"><span data-stu-id="42e0e-124">The string values to be added to the clipboard.</span></span>

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

### <span data-ttu-id="42e0e-125">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="42e0e-125">CommonParameters</span></span>

<span data-ttu-id="42e0e-126">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="42e0e-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="42e0e-127">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e0e-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="42e0e-128">入力</span><span class="sxs-lookup"><span data-stu-id="42e0e-128">INPUTS</span></span>

### <span data-ttu-id="42e0e-129">System.String[]</span><span class="sxs-lookup"><span data-stu-id="42e0e-129">System.String[]</span></span>

## <span data-ttu-id="42e0e-130">出力</span><span class="sxs-lookup"><span data-stu-id="42e0e-130">OUTPUTS</span></span>

## <span data-ttu-id="42e0e-131">注</span><span class="sxs-lookup"><span data-stu-id="42e0e-131">NOTES</span></span>

<span data-ttu-id="42e0e-132">ループのように、頻繁に多数の値を指定してを使用する場合、 `Set-Clipboard` クリップボードから空白の値が返されることがまれにあります。</span><span class="sxs-lookup"><span data-stu-id="42e0e-132">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="42e0e-133">これは、ループ内でを使用して修正でき `Start-Sleep -Milliseconds 1` ます。</span><span class="sxs-lookup"><span data-stu-id="42e0e-133">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="42e0e-134">関連リンク</span><span class="sxs-lookup"><span data-stu-id="42e0e-134">RELATED LINKS</span></span>

[<span data-ttu-id="42e0e-135">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="42e0e-135">Get-Clipboard</span></span>](Get-Clipboard.md)
