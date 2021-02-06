---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: 7772c3e7a5f7492713e0be9a94e92b8c41cd3dd4
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "99603040"
---
# <span data-ttu-id="ada83-102">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="ada83-102">Set-Clipboard</span></span>

## <span data-ttu-id="ada83-103">概要</span><span class="sxs-lookup"><span data-stu-id="ada83-103">SYNOPSIS</span></span>
<span data-ttu-id="ada83-104">クリップボードの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="ada83-104">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="ada83-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ada83-105">SYNTAX</span></span>

```
Set-Clipboard -Value <String[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ada83-106">Description</span><span class="sxs-lookup"><span data-stu-id="ada83-106">DESCRIPTION</span></span>

<span data-ttu-id="ada83-107">コマンドレットでは、 `Set-Clipboard` クリップボードの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="ada83-107">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="ada83-108">Linux では、このコマンドレットでは `xclip` ユーティリティをパスに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ada83-108">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="ada83-109">例</span><span class="sxs-lookup"><span data-stu-id="ada83-109">EXAMPLES</span></span>

### <span data-ttu-id="ada83-110">例 1: テキストをクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="ada83-110">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="ada83-111">例 2: ファイルの内容をクリップボードにコピーする</span><span class="sxs-lookup"><span data-stu-id="ada83-111">Example 2: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="ada83-112">この例では、ファイルの内容をクリップボードにパイプします。</span><span class="sxs-lookup"><span data-stu-id="ada83-112">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="ada83-113">この例では、GitHub などの別のアプリケーションに貼り付けることができるように、ssh の公開キーを取得しています。</span><span class="sxs-lookup"><span data-stu-id="ada83-113">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="ada83-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ada83-114">PARAMETERS</span></span>

### <span data-ttu-id="ada83-115">-追加</span><span class="sxs-lookup"><span data-stu-id="ada83-115">-Append</span></span>

<span data-ttu-id="ada83-116">コマンドレットがクリップボードをクリアせずにコンテンツを追加しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="ada83-116">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="ada83-117">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ada83-117">-Confirm</span></span>

<span data-ttu-id="ada83-118">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ada83-118">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ada83-119">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ada83-119">-WhatIf</span></span>

<span data-ttu-id="ada83-120">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="ada83-120">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ada83-121">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="ada83-121">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ada83-122">-Value</span><span class="sxs-lookup"><span data-stu-id="ada83-122">-Value</span></span>

<span data-ttu-id="ada83-123">クリップボードに追加する文字列値。</span><span class="sxs-lookup"><span data-stu-id="ada83-123">The string values to be added to the clipboard.</span></span>

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

### <span data-ttu-id="ada83-124">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ada83-124">CommonParameters</span></span>

<span data-ttu-id="ada83-125">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ada83-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ada83-126">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ada83-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ada83-127">入力</span><span class="sxs-lookup"><span data-stu-id="ada83-127">INPUTS</span></span>

### <span data-ttu-id="ada83-128">System.String[]</span><span class="sxs-lookup"><span data-stu-id="ada83-128">System.String[]</span></span>

## <span data-ttu-id="ada83-129">出力</span><span class="sxs-lookup"><span data-stu-id="ada83-129">OUTPUTS</span></span>

## <span data-ttu-id="ada83-130">注</span><span class="sxs-lookup"><span data-stu-id="ada83-130">NOTES</span></span>

<span data-ttu-id="ada83-131">ループのように、頻繁に多数の値を指定してを使用する場合、 `Set-Clipboard` クリップボードから空白の値が返されることがまれにあります。</span><span class="sxs-lookup"><span data-stu-id="ada83-131">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="ada83-132">これは、ループ内でを使用して修正でき `Start-Sleep -Milliseconds 1` ます。</span><span class="sxs-lookup"><span data-stu-id="ada83-132">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="ada83-133">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ada83-133">RELATED LINKS</span></span>

[<span data-ttu-id="ada83-134">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="ada83-134">Get-Clipboard</span></span>](Get-Clipboard.md)
