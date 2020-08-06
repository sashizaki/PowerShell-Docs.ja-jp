---
title: CustomControl の CustomEntries 要素のビュー (形式) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c89eb25f6922a92e2c18298d0128c4c2ca93df3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785967"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="ecc9f-102">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ecc9f-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="ecc9f-103">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="ecc9f-104">カスタムコントロールビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="ecc9f-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl Element (Format) CustomControl for View (Format) の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="ecc9f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ecc9f-106">構文</span><span class="sxs-lookup"><span data-stu-id="ecc9f-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ecc9f-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ecc9f-107">Attributes and Elements</span></span>

<span data-ttu-id="ecc9f-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="ecc9f-109">1つまたは複数の子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ecc9f-110">属性</span><span class="sxs-lookup"><span data-stu-id="ecc9f-110">Attributes</span></span>

<span data-ttu-id="ecc9f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ecc9f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ecc9f-112">Child Elements</span></span>

|<span data-ttu-id="ecc9f-113">要素</span><span class="sxs-lookup"><span data-stu-id="ecc9f-113">Element</span></span>|<span data-ttu-id="ecc9f-114">説明</span><span class="sxs-lookup"><span data-stu-id="ecc9f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ecc9f-115">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="ecc9f-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="ecc9f-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-116">Required element.</span></span><br /><br /> <span data-ttu-id="ecc9f-117">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ecc9f-118">親要素</span><span class="sxs-lookup"><span data-stu-id="ecc9f-118">Parent Elements</span></span>

|<span data-ttu-id="ecc9f-119">要素</span><span class="sxs-lookup"><span data-stu-id="ecc9f-119">Element</span></span>|<span data-ttu-id="ecc9f-120">説明</span><span class="sxs-lookup"><span data-stu-id="ecc9f-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ecc9f-121">View の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ecc9f-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="ecc9f-122">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-122">Required element.</span></span><br /><br /> <span data-ttu-id="ecc9f-123">ビューのカスタムコントロール形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ecc9f-124">解説</span><span class="sxs-lookup"><span data-stu-id="ecc9f-124">Remarks</span></span>

<span data-ttu-id="ecc9f-125">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの要素で定義されてい `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="ecc9f-126">ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="ecc9f-127">そのような場合は、 `CustomEntry` オブジェクトまたはオブジェクトのセットごとに要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="ecc9f-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecc9f-128">参照</span><span class="sxs-lookup"><span data-stu-id="ecc9f-128">See Also</span></span>

[<span data-ttu-id="ecc9f-129">View の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ecc9f-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="ecc9f-130">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="ecc9f-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ecc9f-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ecc9f-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
