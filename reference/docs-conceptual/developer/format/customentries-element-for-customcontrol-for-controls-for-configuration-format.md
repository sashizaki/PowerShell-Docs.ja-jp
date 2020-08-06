---
title: Configuration 用のコントロールの CustomControl の CustomEntries 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b1f494cf1a254d71362830ba9eb0f4905a2a484d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785984"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="1aaff-102">Configuration の Controls の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1aaff-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="1aaff-103">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="1aaff-103">Provides the definitions of a common control.</span></span> <span data-ttu-id="1aaff-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="1aaff-105">Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの構成 (形式) のコントロール要素を構成するための CustomControl の構成 (format) の CustomEntries 要素の構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="1aaff-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1aaff-106">構文</span><span class="sxs-lookup"><span data-stu-id="1aaff-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="1aaff-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1aaff-107">Attributes and Elements</span></span>

<span data-ttu-id="1aaff-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="1aaff-109">1つまたは複数の子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aaff-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1aaff-110">属性</span><span class="sxs-lookup"><span data-stu-id="1aaff-110">Attributes</span></span>

<span data-ttu-id="1aaff-111">なし。</span><span class="sxs-lookup"><span data-stu-id="1aaff-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1aaff-112">子要素</span><span class="sxs-lookup"><span data-stu-id="1aaff-112">Child Elements</span></span>

|<span data-ttu-id="1aaff-113">要素</span><span class="sxs-lookup"><span data-stu-id="1aaff-113">Element</span></span>|<span data-ttu-id="1aaff-114">説明</span><span class="sxs-lookup"><span data-stu-id="1aaff-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1aaff-115">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1aaff-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="1aaff-116">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="1aaff-116">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1aaff-117">親要素</span><span class="sxs-lookup"><span data-stu-id="1aaff-117">Parent Elements</span></span>

|<span data-ttu-id="1aaff-118">要素</span><span class="sxs-lookup"><span data-stu-id="1aaff-118">Element</span></span>|<span data-ttu-id="1aaff-119">説明</span><span class="sxs-lookup"><span data-stu-id="1aaff-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1aaff-120">構成用のコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1aaff-120">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="1aaff-121">共通コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="1aaff-121">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1aaff-122">解説</span><span class="sxs-lookup"><span data-stu-id="1aaff-122">Remarks</span></span>

<span data-ttu-id="1aaff-123">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの要素で定義されてい `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-123">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="1aaff-124">ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-124">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="1aaff-125">そのような場合は、 `CustomEntry` オブジェクトまたはオブジェクトのセットごとに要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="1aaff-125">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="1aaff-126">参照</span><span class="sxs-lookup"><span data-stu-id="1aaff-126">See Also</span></span>

[<span data-ttu-id="1aaff-127">構成用のコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1aaff-127">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="1aaff-128">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1aaff-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="1aaff-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="1aaff-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
