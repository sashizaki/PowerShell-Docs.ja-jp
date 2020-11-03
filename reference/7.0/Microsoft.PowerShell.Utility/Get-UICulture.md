---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: cd5bbcae124b1c24438d2821c4da9d71a22d38a2
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209215"
---
# <span data-ttu-id="14330-103">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="14330-103">Get-UICulture</span></span>

## <span data-ttu-id="14330-104">概要</span><span class="sxs-lookup"><span data-stu-id="14330-104">SYNOPSIS</span></span>
<span data-ttu-id="14330-105">オペレーティングシステムの現在の UI カルチャ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="14330-105">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="14330-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14330-106">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="14330-107">Description</span><span class="sxs-lookup"><span data-stu-id="14330-107">DESCRIPTION</span></span>

<span data-ttu-id="14330-108">`Get-UICulture`コマンドレットは、Windows の現在のユーザーインターフェイス (UI) カルチャ設定に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="14330-108">The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="14330-109">UI カルチャは、どのテキスト文字列がメニューやメッセージなどのユーザー インターフェイス要素に使用されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="14330-109">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="14330-110">また、コマンドレットを使用して、 `Get-Culture` システム上の現在のカルチャを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="14330-110">You can also use the `Get-Culture` cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="14330-111">カルチャは、数値、通貨、日付などの項目の表示形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="14330-111">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="14330-112">例</span><span class="sxs-lookup"><span data-stu-id="14330-112">EXAMPLES</span></span>

### <span data-ttu-id="14330-113">例 1: UI カルチャを取得する</span><span class="sxs-lookup"><span data-stu-id="14330-113">Example 1: Get the UI culture</span></span>

```powershell
Get-UICulture
```

<span data-ttu-id="14330-114">このコマンドは、現在の UI カルチャの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="14330-114">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="14330-115">例 2: UI カルチャを取得し、結果の書式を設定する</span><span class="sxs-lookup"><span data-stu-id="14330-115">Example 2: Get the UI culture and format the results</span></span>

```powershell
Get-UICulture | Format-List *
```

<span data-ttu-id="14330-116">このコマンドは、現在の UI カルチャのプロパティのすべての値を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="14330-116">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="14330-117">例 3: Calendar プロパティの値を取得する</span><span class="sxs-lookup"><span data-stu-id="14330-117">Example 3: Get the value of the Calendar property</span></span>

```powershell
(Get-UICulture).Calendar
```

<span data-ttu-id="14330-118">このコマンドは、現在の UI カルチャの **Calendar** プロパティの現在の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="14330-118">This command displays the current values for the **Calendar** property of the current UI culture.</span></span>
<span data-ttu-id="14330-119">カレンダーは、UI カルチャのプロパティの 1 つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="14330-119">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="14330-120">すべてのプロパティを表示するには、「」と入力 `Get-UICulture | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="14330-120">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="14330-121">例 4: 短い日付パターンを取得する</span><span class="sxs-lookup"><span data-stu-id="14330-121">Example 4: Get the short date pattern</span></span>

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="14330-122">このコマンドは、現在の UI カルチャの短い形式の日付パターンを表示します。</span><span class="sxs-lookup"><span data-stu-id="14330-122">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="14330-123">UI カルチャの **DateTimeFormat** プロパティのすべてのサブプロパティを表示するには、「」と入力 `(Get-UICulture).DateTimeFormat | gm` します。</span><span class="sxs-lookup"><span data-stu-id="14330-123">To see all of the subproperties of the **DateTimeFormat** property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="14330-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14330-124">PARAMETERS</span></span>

### <span data-ttu-id="14330-125">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="14330-125">CommonParameters</span></span>

<span data-ttu-id="14330-126">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="14330-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14330-127">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14330-127">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="14330-128">入力</span><span class="sxs-lookup"><span data-stu-id="14330-128">INPUTS</span></span>

### <span data-ttu-id="14330-129">なし</span><span class="sxs-lookup"><span data-stu-id="14330-129">None</span></span>

<span data-ttu-id="14330-130">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="14330-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="14330-131">出力</span><span class="sxs-lookup"><span data-stu-id="14330-131">OUTPUTS</span></span>

### <span data-ttu-id="14330-132">VistaCultureInfo, Microsoft. PowerShell...</span><span class="sxs-lookup"><span data-stu-id="14330-132">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>

<span data-ttu-id="14330-133">`Get-UICulture` 現在の UI カルチャを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="14330-133">`Get-UICulture` returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="14330-134">Windows PowerShell 3.0 では、 **CultureInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="14330-134">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="14330-135">Windows PowerShell 2.0 では、 **VistaCultureInfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="14330-135">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="14330-136">注</span><span class="sxs-lookup"><span data-stu-id="14330-136">NOTES</span></span>

- <span data-ttu-id="14330-137">変数および変数を使用することもでき `$PsCulture` `$PsUICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="14330-137">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="14330-138">変数には `$PsCulture` 現在のカルチャの名前が格納され、変数には `$PsUICulture` 現在の UI カルチャの名前が格納されます。</span><span class="sxs-lookup"><span data-stu-id="14330-138">The `$PsCulture` variable stores the name of the current culture, and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="14330-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="14330-139">RELATED LINKS</span></span>
