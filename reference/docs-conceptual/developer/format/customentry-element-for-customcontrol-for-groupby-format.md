---
title: GroupBy (Format) の CustomControl の CustomEntry 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4df8e5b96868b3814c6d84fa329950bb5345ef6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785916"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="e453d-102">GroupBy の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e453d-102">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="e453d-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e453d-103">Provides a definition of the control.</span></span> <span data-ttu-id="e453d-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e453d-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="e453d-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を表示 (format) の CustomControl 要素を groupby (形式) の CustomControl の CustomControl の CustomEntry 要素の groupby (形式)</span><span class="sxs-lookup"><span data-stu-id="e453d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e453d-106">構文</span><span class="sxs-lookup"><span data-stu-id="e453d-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e453d-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e453d-107">Attributes and Elements</span></span>

<span data-ttu-id="e453d-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="e453d-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e453d-109">属性</span><span class="sxs-lookup"><span data-stu-id="e453d-109">Attributes</span></span>

<span data-ttu-id="e453d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e453d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e453d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e453d-111">Child Elements</span></span>

|<span data-ttu-id="e453d-112">要素</span><span class="sxs-lookup"><span data-stu-id="e453d-112">Element</span></span>|<span data-ttu-id="e453d-113">説明</span><span class="sxs-lookup"><span data-stu-id="e453d-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e453d-114">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e453d-114">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="e453d-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e453d-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e453d-116">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e453d-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="e453d-117">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e453d-117">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="e453d-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="e453d-118">Required element.</span></span><br /><br /> <span data-ttu-id="e453d-119">コントロールがデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e453d-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e453d-120">親要素</span><span class="sxs-lookup"><span data-stu-id="e453d-120">Parent Elements</span></span>

|<span data-ttu-id="e453d-121">要素</span><span class="sxs-lookup"><span data-stu-id="e453d-121">Element</span></span>|<span data-ttu-id="e453d-122">説明</span><span class="sxs-lookup"><span data-stu-id="e453d-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e453d-123">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e453d-123">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="e453d-124">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e453d-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e453d-125">解説</span><span class="sxs-lookup"><span data-stu-id="e453d-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="e453d-126">参照</span><span class="sxs-lookup"><span data-stu-id="e453d-126">See Also</span></span>

[<span data-ttu-id="e453d-127">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e453d-127">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="e453d-128">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e453d-128">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="e453d-129">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e453d-129">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="e453d-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e453d-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
