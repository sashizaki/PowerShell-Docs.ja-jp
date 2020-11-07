---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 5fce0c872871006dd760ee8df2fb692faaa1aab9
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342367"
---
# <span data-ttu-id="269bd-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="269bd-103">Get-Clipboard</span></span>

## <span data-ttu-id="269bd-104">概要</span><span class="sxs-lookup"><span data-stu-id="269bd-104">SYNOPSIS</span></span>
<span data-ttu-id="269bd-105">クリップボードの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="269bd-105">Gets the contents of the clipboard.</span></span>

## <span data-ttu-id="269bd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="269bd-106">SYNTAX</span></span>

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="269bd-107">Description</span><span class="sxs-lookup"><span data-stu-id="269bd-107">DESCRIPTION</span></span>

<span data-ttu-id="269bd-108">`Get-Clipboard`コマンドレットは、クリップボードの内容をテキストとして取得します。</span><span class="sxs-lookup"><span data-stu-id="269bd-108">The `Get-Clipboard` cmdlet gets the contents of the clipboard as text.</span></span> <span data-ttu-id="269bd-109">に類似した文字列の配列として、複数行のテキストが返され `Get-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="269bd-109">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="269bd-110">Linux では、このコマンドレットでは `xclip` ユーティリティをパスに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="269bd-110">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span> <span data-ttu-id="269bd-111">このコマンドレットは macOS ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="269bd-111">This cmdlet is not supported on macOS.</span></span>

## <span data-ttu-id="269bd-112">例</span><span class="sxs-lookup"><span data-stu-id="269bd-112">EXAMPLES</span></span>

### <span data-ttu-id="269bd-113">例 1: クリップボードの内容を取得し、それをコマンドラインに表示する</span><span class="sxs-lookup"><span data-stu-id="269bd-113">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="269bd-114">この例では、テキスト "hello" をクリップボードにコピーしました。</span><span class="sxs-lookup"><span data-stu-id="269bd-114">In this example we have copied the text "hello" into the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
hello
```

## <span data-ttu-id="269bd-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="269bd-115">PARAMETERS</span></span>

### <span data-ttu-id="269bd-116">-Raw</span><span class="sxs-lookup"><span data-stu-id="269bd-116">-Raw</span></span>

<span data-ttu-id="269bd-117">クリップボードの内容全体を取得します。</span><span class="sxs-lookup"><span data-stu-id="269bd-117">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="269bd-118">複数行テキストは、文字列の配列ではなく、単一の複数行文字列として返されます。</span><span class="sxs-lookup"><span data-stu-id="269bd-118">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="269bd-119">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="269bd-119">CommonParameters</span></span>

<span data-ttu-id="269bd-120">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="269bd-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="269bd-121">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="269bd-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="269bd-122">入力</span><span class="sxs-lookup"><span data-stu-id="269bd-122">INPUTS</span></span>

## <span data-ttu-id="269bd-123">出力</span><span class="sxs-lookup"><span data-stu-id="269bd-123">OUTPUTS</span></span>

### <span data-ttu-id="269bd-124">System.String</span><span class="sxs-lookup"><span data-stu-id="269bd-124">System.String</span></span>

## <span data-ttu-id="269bd-125">注</span><span class="sxs-lookup"><span data-stu-id="269bd-125">NOTES</span></span>

## <span data-ttu-id="269bd-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="269bd-126">RELATED LINKS</span></span>

[<span data-ttu-id="269bd-127">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="269bd-127">Set-Clipboard</span></span>](Set-Clipboard.md)
