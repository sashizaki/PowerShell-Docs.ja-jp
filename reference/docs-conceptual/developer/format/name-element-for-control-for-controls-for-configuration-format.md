---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の Control の Name 要素 (書式)
description: Configuration の Controls の Control の Name 要素 (書式)
ms.openlocfilehash: 0c1c83f827482886ca742f2c0174e8383f87fb52
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666503"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="e7ebd-103">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e7ebd-103">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e7ebd-104">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-104">Specifies the name of the control.</span></span> <span data-ttu-id="e7ebd-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e7ebd-106">Configuration 要素 (Format) コントロールの構成 (書式) のコントロール要素の構成 (format) コントロールの要素の構成 (形式) コントロールの要素</span><span class="sxs-lookup"><span data-stu-id="e7ebd-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e7ebd-107">構文</span><span class="sxs-lookup"><span data-stu-id="e7ebd-107">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e7ebd-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e7ebd-108">Attributes and Elements</span></span>

<span data-ttu-id="e7ebd-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-109">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e7ebd-110">属性</span><span class="sxs-lookup"><span data-stu-id="e7ebd-110">Attributes</span></span>

<span data-ttu-id="e7ebd-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e7ebd-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e7ebd-112">Child Elements</span></span>

<span data-ttu-id="e7ebd-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e7ebd-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e7ebd-114">Parent Elements</span></span>

|<span data-ttu-id="e7ebd-115">要素</span><span class="sxs-lookup"><span data-stu-id="e7ebd-115">Element</span></span>|<span data-ttu-id="e7ebd-116">説明</span><span class="sxs-lookup"><span data-stu-id="e7ebd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7ebd-117">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e7ebd-117">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="e7ebd-118">書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-118">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e7ebd-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e7ebd-119">Text Value</span></span>

<span data-ttu-id="e7ebd-120">このコントロールを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-120">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7ebd-121">解説</span><span class="sxs-lookup"><span data-stu-id="e7ebd-121">Remarks</span></span>

<span data-ttu-id="e7ebd-122">ここで指定した名前は、このコントロールを参照するために次の要素で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-122">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="e7ebd-123">テーブル、リスト、ワイドコントロール、またはカスタムコントロールビューを作成するときに、コントロールを指定するには、次の要素を使用します。 [GroupBy 要素 (Format)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="e7ebd-123">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="e7ebd-124">別のコモンコントロールを作成するときに、このコントロールを指定するには、次の要素を使用します。[構成するコントロールの CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-124">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="e7ebd-125">ビューで使用できるコントロールを作成する場合、このコントロールは、[ビュー (Format) のコントロールの CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="e7ebd-125">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="e7ebd-126">参照</span><span class="sxs-lookup"><span data-stu-id="e7ebd-126">See Also</span></span>

[<span data-ttu-id="e7ebd-127">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e7ebd-127">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="e7ebd-128">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e7ebd-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e7ebd-129">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e7ebd-129">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="e7ebd-130">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e7ebd-130">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="e7ebd-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e7ebd-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
