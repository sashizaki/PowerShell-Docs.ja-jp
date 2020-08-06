---
title: 構成用コントロールのコントロールの Name 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3d45ba98b909ebee18e01d2b6985a48906ce39d9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783536"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="7c785-102">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c785-102">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="7c785-103">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c785-103">Specifies the name of the control.</span></span> <span data-ttu-id="7c785-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7c785-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="7c785-105">Configuration 要素 (Format) コントロールの構成 (書式) のコントロール要素の構成 (format) コントロールの要素の構成 (形式) コントロールの要素</span><span class="sxs-lookup"><span data-stu-id="7c785-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7c785-106">構文</span><span class="sxs-lookup"><span data-stu-id="7c785-106">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="7c785-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7c785-107">Attributes and Elements</span></span>

<span data-ttu-id="7c785-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="7c785-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7c785-109">属性</span><span class="sxs-lookup"><span data-stu-id="7c785-109">Attributes</span></span>

<span data-ttu-id="7c785-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7c785-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7c785-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7c785-111">Child Elements</span></span>

<span data-ttu-id="7c785-112">なし。</span><span class="sxs-lookup"><span data-stu-id="7c785-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7c785-113">親要素</span><span class="sxs-lookup"><span data-stu-id="7c785-113">Parent Elements</span></span>

|<span data-ttu-id="7c785-114">要素</span><span class="sxs-lookup"><span data-stu-id="7c785-114">Element</span></span>|<span data-ttu-id="7c785-115">説明</span><span class="sxs-lookup"><span data-stu-id="7c785-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7c785-116">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c785-116">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="7c785-117">書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="7c785-117">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7c785-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7c785-118">Text Value</span></span>

<span data-ttu-id="7c785-119">このコントロールを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c785-119">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c785-120">解説</span><span class="sxs-lookup"><span data-stu-id="7c785-120">Remarks</span></span>

<span data-ttu-id="7c785-121">ここで指定した名前は、このコントロールを参照するために次の要素で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c785-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="7c785-122">テーブル、リスト、ワイドコントロール、またはカスタムコントロールビューを作成するときに、コントロールを指定するには、次の要素を使用します。 [GroupBy 要素 (Format)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="7c785-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="7c785-123">別のコモンコントロールを作成するときに、このコントロールを指定するには、次の要素を使用します。[構成するコントロールの CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)です。</span><span class="sxs-lookup"><span data-stu-id="7c785-123">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="7c785-124">ビューで使用できるコントロールを作成する場合、このコントロールは、[ビュー (Format) のコントロールの CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="7c785-124">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="7c785-125">参照</span><span class="sxs-lookup"><span data-stu-id="7c785-125">See Also</span></span>

[<span data-ttu-id="7c785-126">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c785-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="7c785-127">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c785-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="7c785-128">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c785-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="7c785-129">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c785-129">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="7c785-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="7c785-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
