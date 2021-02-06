---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: 4bd912db3f86ffa8b495faf3e62259f207340938
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601809"
---
# <span data-ttu-id="88142-102">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="88142-102">Get-UICulture</span></span>

## <span data-ttu-id="88142-103">概要</span><span class="sxs-lookup"><span data-stu-id="88142-103">SYNOPSIS</span></span>
<span data-ttu-id="88142-104">オペレーティングシステムの現在の UI カルチャ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="88142-104">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="88142-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="88142-105">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="88142-106">Description</span><span class="sxs-lookup"><span data-stu-id="88142-106">DESCRIPTION</span></span>

<span data-ttu-id="88142-107">`Get-UICulture`コマンドレットは、Windows の現在のユーザーインターフェイス (UI) カルチャ設定に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="88142-107">The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="88142-108">UI カルチャは、どのテキスト文字列がメニューやメッセージなどのユーザー インターフェイス要素に使用されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="88142-108">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="88142-109">また、コマンドレットを使用して、 `Get-Culture` システム上の現在のカルチャを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="88142-109">You can also use the `Get-Culture` cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="88142-110">カルチャは、数値、通貨、日付などの項目の表示形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="88142-110">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="88142-111">例</span><span class="sxs-lookup"><span data-stu-id="88142-111">EXAMPLES</span></span>

### <span data-ttu-id="88142-112">例 1: UI カルチャを取得する</span><span class="sxs-lookup"><span data-stu-id="88142-112">Example 1: Get the UI culture</span></span>

```powershell
Get-UICulture
```

<span data-ttu-id="88142-113">このコマンドは、現在の UI カルチャの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="88142-113">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="88142-114">例 2: UI カルチャを取得し、結果の書式を設定する</span><span class="sxs-lookup"><span data-stu-id="88142-114">Example 2: Get the UI culture and format the results</span></span>

```powershell
Get-UICulture | Format-List *
```

<span data-ttu-id="88142-115">このコマンドは、現在の UI カルチャのプロパティのすべての値を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="88142-115">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="88142-116">例 3: Calendar プロパティの値を取得する</span><span class="sxs-lookup"><span data-stu-id="88142-116">Example 3: Get the value of the Calendar property</span></span>

```powershell
(Get-UICulture).Calendar
```

<span data-ttu-id="88142-117">このコマンドは、現在の UI カルチャの **Calendar** プロパティの現在の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="88142-117">This command displays the current values for the **Calendar** property of the current UI culture.</span></span>
<span data-ttu-id="88142-118">カレンダーは、UI カルチャのプロパティの 1 つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="88142-118">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="88142-119">すべてのプロパティを表示するには、「」と入力 `Get-UICulture | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="88142-119">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="88142-120">例 4: 短い日付パターンを取得する</span><span class="sxs-lookup"><span data-stu-id="88142-120">Example 4: Get the short date pattern</span></span>

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="88142-121">このコマンドは、現在の UI カルチャの短い形式の日付パターンを表示します。</span><span class="sxs-lookup"><span data-stu-id="88142-121">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="88142-122">UI カルチャの **DateTimeFormat** プロパティのすべてのサブプロパティを表示するには、「」と入力 `(Get-UICulture).DateTimeFormat | gm` します。</span><span class="sxs-lookup"><span data-stu-id="88142-122">To see all of the subproperties of the **DateTimeFormat** property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="88142-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="88142-123">PARAMETERS</span></span>

### <span data-ttu-id="88142-124">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="88142-124">CommonParameters</span></span>

<span data-ttu-id="88142-125">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="88142-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="88142-126">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88142-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="88142-127">入力</span><span class="sxs-lookup"><span data-stu-id="88142-127">INPUTS</span></span>

### <span data-ttu-id="88142-128">なし</span><span class="sxs-lookup"><span data-stu-id="88142-128">None</span></span>

<span data-ttu-id="88142-129">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="88142-129">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="88142-130">出力</span><span class="sxs-lookup"><span data-stu-id="88142-130">OUTPUTS</span></span>

### <span data-ttu-id="88142-131">VistaCultureInfo, Microsoft. PowerShell...</span><span class="sxs-lookup"><span data-stu-id="88142-131">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>

<span data-ttu-id="88142-132">`Get-UICulture` 現在の UI カルチャを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="88142-132">`Get-UICulture` returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="88142-133">Windows PowerShell 3.0 では、 **CultureInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="88142-133">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="88142-134">Windows PowerShell 2.0 では、 **VistaCultureInfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="88142-134">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="88142-135">注</span><span class="sxs-lookup"><span data-stu-id="88142-135">NOTES</span></span>

- <span data-ttu-id="88142-136">変数および変数を使用することもでき `$PsCulture` `$PsUICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="88142-136">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="88142-137">変数には `$PsCulture` 現在のカルチャの名前が格納され、変数には `$PsUICulture` 現在の UI カルチャの名前が格納されます。</span><span class="sxs-lookup"><span data-stu-id="88142-137">The `$PsCulture` variable stores the name of the current culture, and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="88142-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="88142-138">RELATED LINKS</span></span>

