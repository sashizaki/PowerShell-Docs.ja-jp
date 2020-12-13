---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の CustomEntries の CustomEntry 要素 (書式)
description: View の Controls の CustomEntries の CustomEntry 要素 (書式)
ms.openlocfilehash: a525b198c8f595e04dc0804d36b5533b94f43c6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646085"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="7584b-103">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7584b-103">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="7584b-104">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="7584b-104">Provides a definition of the control.</span></span> <span data-ttu-id="7584b-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7584b-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="7584b-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (形式) コントロールのコントロール要素を表示するコントロールのコントロールの要素 (書式) の CustomControl 要素 (format) ビューのコントロールの CustomEntries の CustomControl for ビュー (形式) のカスタムエントリ要素</span><span class="sxs-lookup"><span data-stu-id="7584b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7584b-107">構文</span><span class="sxs-lookup"><span data-stu-id="7584b-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7584b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7584b-108">Attributes and Elements</span></span>

<span data-ttu-id="7584b-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="7584b-109">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7584b-110">属性</span><span class="sxs-lookup"><span data-stu-id="7584b-110">Attributes</span></span>

<span data-ttu-id="7584b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7584b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7584b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="7584b-112">Child Elements</span></span>

|<span data-ttu-id="7584b-113">要素</span><span class="sxs-lookup"><span data-stu-id="7584b-113">Element</span></span>|<span data-ttu-id="7584b-114">説明</span><span class="sxs-lookup"><span data-stu-id="7584b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7584b-115">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7584b-115">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="7584b-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7584b-116">Optional element.</span></span><br /><br /> <span data-ttu-id="7584b-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7584b-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="7584b-118">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7584b-118">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="7584b-119">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="7584b-119">Required element.</span></span><br /><br /> <span data-ttu-id="7584b-120">コントロールがデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7584b-120">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7584b-121">親要素</span><span class="sxs-lookup"><span data-stu-id="7584b-121">Parent Elements</span></span>

|<span data-ttu-id="7584b-122">要素</span><span class="sxs-lookup"><span data-stu-id="7584b-122">Element</span></span>|<span data-ttu-id="7584b-123">説明</span><span class="sxs-lookup"><span data-stu-id="7584b-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7584b-124">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7584b-124">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="7584b-125">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="7584b-125">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7584b-126">解説</span><span class="sxs-lookup"><span data-stu-id="7584b-126">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="7584b-127">参照</span><span class="sxs-lookup"><span data-stu-id="7584b-127">See Also</span></span>

[<span data-ttu-id="7584b-128">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7584b-128">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7584b-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="7584b-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
