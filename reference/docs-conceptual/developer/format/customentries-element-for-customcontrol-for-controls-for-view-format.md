---
title: View (Format) 用のコントロールの CustomControl の CustomEntries 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a52bd2368044c34a0b73da331785d55597e30260
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783706"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a><span data-ttu-id="cf80b-102">View の Controls の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cf80b-102">CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

<span data-ttu-id="cf80b-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cf80b-103">Provides the definitions for the control.</span></span> <span data-ttu-id="cf80b-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf80b-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="cf80b-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (形式) コントロールのコントロールの要素 (書式) のコントロール要素 (format) のコントロールの CustomControl 要素 (format) のコントロールのコントロール要素 (形式) のコントロールの CustomControl</span><span class="sxs-lookup"><span data-stu-id="cf80b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cf80b-106">構文</span><span class="sxs-lookup"><span data-stu-id="cf80b-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cf80b-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cf80b-107">Attributes and Elements</span></span>

<span data-ttu-id="cf80b-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="cf80b-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="cf80b-109">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="cf80b-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="cf80b-110">属性</span><span class="sxs-lookup"><span data-stu-id="cf80b-110">Attributes</span></span>

<span data-ttu-id="cf80b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="cf80b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cf80b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="cf80b-112">Child Elements</span></span>

|<span data-ttu-id="cf80b-113">要素</span><span class="sxs-lookup"><span data-stu-id="cf80b-113">Element</span></span>|<span data-ttu-id="cf80b-114">説明</span><span class="sxs-lookup"><span data-stu-id="cf80b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cf80b-115">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cf80b-115">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="cf80b-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="cf80b-116">Required element.</span></span><br /><br /> <span data-ttu-id="cf80b-117">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cf80b-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cf80b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="cf80b-118">Parent Elements</span></span>

|<span data-ttu-id="cf80b-119">要素</span><span class="sxs-lookup"><span data-stu-id="cf80b-119">Element</span></span>|<span data-ttu-id="cf80b-120">説明</span><span class="sxs-lookup"><span data-stu-id="cf80b-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cf80b-121">View の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cf80b-121">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="cf80b-122">ビューによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf80b-122">Defines the control used by the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cf80b-123">解説</span><span class="sxs-lookup"><span data-stu-id="cf80b-123">Remarks</span></span>

<span data-ttu-id="cf80b-124">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの要素で指定され `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="cf80b-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="cf80b-125">ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf80b-125">However, it is possible to provide multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="cf80b-126">そのような場合は、 `CustomEntry` オブジェクトまたはオブジェクトのセットごとに要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cf80b-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf80b-127">参照</span><span class="sxs-lookup"><span data-stu-id="cf80b-127">See Also</span></span>

[<span data-ttu-id="cf80b-128">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cf80b-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="cf80b-129">View の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cf80b-129">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="cf80b-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="cf80b-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
