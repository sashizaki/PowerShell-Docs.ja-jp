---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: da1df360d7c471d925bd2f57f5258ecb2d60e631
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239983"
---
# <span data-ttu-id="9b896-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="9b896-103">Get-Clipboard</span></span>

## <span data-ttu-id="9b896-104">概要</span><span class="sxs-lookup"><span data-stu-id="9b896-104">SYNOPSIS</span></span>
<span data-ttu-id="9b896-105">クリップボードの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b896-105">Gets the contents of the clipboard.</span></span>

## <span data-ttu-id="9b896-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9b896-106">SYNTAX</span></span>

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="9b896-107">Description</span><span class="sxs-lookup"><span data-stu-id="9b896-107">DESCRIPTION</span></span>

<span data-ttu-id="9b896-108">`Get-Clipboard`コマンドレットは、クリップボードの内容をテキストとして取得します。</span><span class="sxs-lookup"><span data-stu-id="9b896-108">The `Get-Clipboard` cmdlet gets the contents of the clipboard as text.</span></span> <span data-ttu-id="9b896-109">に類似した文字列の配列として、複数行のテキストが返され `Get-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="9b896-109">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="9b896-110">Linux では、このコマンドレットでは `xclip` ユーティリティをパスに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b896-110">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="9b896-111">例</span><span class="sxs-lookup"><span data-stu-id="9b896-111">EXAMPLES</span></span>

### <span data-ttu-id="9b896-112">例 1: クリップボードの内容を取得し、それをコマンドラインに表示する</span><span class="sxs-lookup"><span data-stu-id="9b896-112">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="9b896-113">この例では、テキスト "hello" をクリップボードにコピーしました。</span><span class="sxs-lookup"><span data-stu-id="9b896-113">In this example we have copied the text "hello" into the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
hello
```

## <span data-ttu-id="9b896-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9b896-114">PARAMETERS</span></span>

### <span data-ttu-id="9b896-115">-Raw</span><span class="sxs-lookup"><span data-stu-id="9b896-115">-Raw</span></span>

<span data-ttu-id="9b896-116">クリップボードの内容全体を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b896-116">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="9b896-117">複数行テキストは、文字列の配列ではなく、単一の複数行文字列として返されます。</span><span class="sxs-lookup"><span data-stu-id="9b896-117">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="9b896-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b896-118">CommonParameters</span></span>

<span data-ttu-id="9b896-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9b896-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9b896-120">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b896-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9b896-121">入力</span><span class="sxs-lookup"><span data-stu-id="9b896-121">INPUTS</span></span>

## <span data-ttu-id="9b896-122">出力</span><span class="sxs-lookup"><span data-stu-id="9b896-122">OUTPUTS</span></span>

### <span data-ttu-id="9b896-123">System.String</span><span class="sxs-lookup"><span data-stu-id="9b896-123">System.String</span></span>

## <span data-ttu-id="9b896-124">注</span><span class="sxs-lookup"><span data-stu-id="9b896-124">NOTES</span></span>

## <span data-ttu-id="9b896-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9b896-125">RELATED LINKS</span></span>

[<span data-ttu-id="9b896-126">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="9b896-126">Set-Clipboard</span></span>](Set-Clipboard.md)

