---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: 098e98dec6733af036795e4decb633f59d40c633
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209047"
---
# <span data-ttu-id="729ad-103">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="729ad-103">Get-UICulture</span></span>

## <span data-ttu-id="729ad-104">概要</span><span class="sxs-lookup"><span data-stu-id="729ad-104">SYNOPSIS</span></span>
<span data-ttu-id="729ad-105">オペレーティングシステムの現在の UI カルチャ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="729ad-105">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="729ad-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="729ad-106">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="729ad-107">Description</span><span class="sxs-lookup"><span data-stu-id="729ad-107">DESCRIPTION</span></span>
<span data-ttu-id="729ad-108">**UICulture** コマンドレットは、Windows の現在のユーザーインターフェイス (UI) カルチャ設定に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="729ad-108">The **Get-UICulture** cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="729ad-109">UI カルチャは、どのテキスト文字列がメニューやメッセージなどのユーザー インターフェイス要素に使用されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="729ad-109">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="729ad-110">また、Get-Culture コマンドレットを使用して、システム上の現在のカルチャを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="729ad-110">You can also use the Get-Culture cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="729ad-111">カルチャは、数値、通貨、日付などの項目の表示形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="729ad-111">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="729ad-112">例</span><span class="sxs-lookup"><span data-stu-id="729ad-112">EXAMPLES</span></span>

### <span data-ttu-id="729ad-113">例 1: UI カルチャを取得する</span><span class="sxs-lookup"><span data-stu-id="729ad-113">Example 1: Get the UI culture</span></span>

```
PS C:\> Get-UICulture
```

<span data-ttu-id="729ad-114">このコマンドは、現在の UI カルチャの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="729ad-114">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="729ad-115">例 2: UI カルチャを取得し、結果の書式を設定する</span><span class="sxs-lookup"><span data-stu-id="729ad-115">Example 2: Get the UI culture and format the results</span></span>

```
PS C:\> Get-UICulture | Format-List *
```

<span data-ttu-id="729ad-116">このコマンドは、現在の UI カルチャのプロパティのすべての値を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="729ad-116">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="729ad-117">例 3: Calendar プロパティの値を取得する</span><span class="sxs-lookup"><span data-stu-id="729ad-117">Example 3: Get the value of the Calendar property</span></span>

```
PS C:\> (Get-UICulture).Calendar
```

<span data-ttu-id="729ad-118">このコマンドは、現在の UI カルチャのカレンダーのプロパティの現在の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="729ad-118">This command displays the current values for the Calendar property of the current UI culture.</span></span>
<span data-ttu-id="729ad-119">カレンダーは、UI カルチャのプロパティの 1 つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="729ad-119">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="729ad-120">すべてのプロパティを表示するには、「」と入力 `Get-UICulture | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="729ad-120">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="729ad-121">例 4: 短い日付パターンを取得する</span><span class="sxs-lookup"><span data-stu-id="729ad-121">Example 4: Get the short date pattern</span></span>

```
PS C:\> (Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="729ad-122">このコマンドは、現在の UI カルチャの短い形式の日付パターンを表示します。</span><span class="sxs-lookup"><span data-stu-id="729ad-122">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="729ad-123">UI カルチャの DateTimeFormat プロパティのすべてのサブプロパティを表示するには、「」と入力 `(Get-UICulture).DateTimeFormat | gm` します。</span><span class="sxs-lookup"><span data-stu-id="729ad-123">To see all of the subproperties of the DateTimeFormat property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="729ad-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="729ad-124">PARAMETERS</span></span>

### <span data-ttu-id="729ad-125">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="729ad-125">CommonParameters</span></span>
<span data-ttu-id="729ad-126">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="729ad-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="729ad-127">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="729ad-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="729ad-128">入力</span><span class="sxs-lookup"><span data-stu-id="729ad-128">INPUTS</span></span>

### <span data-ttu-id="729ad-129">なし</span><span class="sxs-lookup"><span data-stu-id="729ad-129">None</span></span>
<span data-ttu-id="729ad-130">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="729ad-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="729ad-131">出力</span><span class="sxs-lookup"><span data-stu-id="729ad-131">OUTPUTS</span></span>

### <span data-ttu-id="729ad-132">VistaCultureInfo, Microsoft. PowerShell...</span><span class="sxs-lookup"><span data-stu-id="729ad-132">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>
<span data-ttu-id="729ad-133">**UICulture** は、現在の UI カルチャを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="729ad-133">**Get-UICulture** returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="729ad-134">Windows PowerShell 3.0 では、 **CultureInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="729ad-134">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="729ad-135">Windows PowerShell 2.0 では、 **VistaCultureInfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="729ad-135">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="729ad-136">注</span><span class="sxs-lookup"><span data-stu-id="729ad-136">NOTES</span></span>

* <span data-ttu-id="729ad-137">また、$PsCulture 変数と $PsUICulture 変数も使用することができます。</span><span class="sxs-lookup"><span data-stu-id="729ad-137">You can also use the $PsCulture and $PsUICulture variables.</span></span> <span data-ttu-id="729ad-138">$PsCulture 変数は、現在のカルチャの名前を格納し、$PsUICulture 変数は、現在の UI カルチャの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="729ad-138">The $PsCulture variable stores the name of the current culture, and the $PsUICulture variable stores the name of the current UI culture.</span></span>

*

## <span data-ttu-id="729ad-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="729ad-139">RELATED LINKS</span></span>

## <span data-ttu-id="729ad-140">関連リンク</span><span class="sxs-lookup"><span data-stu-id="729ad-140">RELATED LINKS</span></span>
