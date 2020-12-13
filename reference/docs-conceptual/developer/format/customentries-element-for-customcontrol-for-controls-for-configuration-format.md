---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の CustomControl の CustomEntries 要素 (書式)
description: Configuration の Controls の CustomControl の CustomEntries 要素 (書式)
ms.openlocfilehash: 86c2b517d0d7075a355a3190a14e25d9dd4fe374
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655395"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="f802b-103">Configuration の Controls の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f802b-103">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f802b-104">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="f802b-104">Provides the definitions of a common control.</span></span> <span data-ttu-id="f802b-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f802b-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f802b-106">Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの構成 (形式) のコントロール要素を構成するための CustomControl の構成 (format) の CustomEntries 要素の構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="f802b-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f802b-107">構文</span><span class="sxs-lookup"><span data-stu-id="f802b-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f802b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f802b-108">Attributes and Elements</span></span>

<span data-ttu-id="f802b-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="f802b-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="f802b-110">1つまたは複数の子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f802b-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f802b-111">属性</span><span class="sxs-lookup"><span data-stu-id="f802b-111">Attributes</span></span>

<span data-ttu-id="f802b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f802b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f802b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="f802b-113">Child Elements</span></span>

|<span data-ttu-id="f802b-114">要素</span><span class="sxs-lookup"><span data-stu-id="f802b-114">Element</span></span>|<span data-ttu-id="f802b-115">説明</span><span class="sxs-lookup"><span data-stu-id="f802b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f802b-116">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f802b-116">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="f802b-117">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="f802b-117">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f802b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="f802b-118">Parent Elements</span></span>

|<span data-ttu-id="f802b-119">要素</span><span class="sxs-lookup"><span data-stu-id="f802b-119">Element</span></span>|<span data-ttu-id="f802b-120">説明</span><span class="sxs-lookup"><span data-stu-id="f802b-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f802b-121">構成用のコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f802b-121">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="f802b-122">共通コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="f802b-122">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f802b-123">解説</span><span class="sxs-lookup"><span data-stu-id="f802b-123">Remarks</span></span>

<span data-ttu-id="f802b-124">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの要素で定義されてい `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="f802b-124">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="f802b-125">ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f802b-125">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="f802b-126">そのような場合は、 `CustomEntry` オブジェクトまたはオブジェクトのセットごとに要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f802b-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="f802b-127">参照</span><span class="sxs-lookup"><span data-stu-id="f802b-127">See Also</span></span>

[<span data-ttu-id="f802b-128">構成用のコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f802b-128">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="f802b-129">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f802b-129">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="f802b-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f802b-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
