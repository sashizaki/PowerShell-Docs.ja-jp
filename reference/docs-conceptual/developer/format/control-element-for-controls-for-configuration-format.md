---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の Control 要素 (書式)
description: Configuration の Controls の Control 要素 (書式)
ms.openlocfilehash: 43424de025cb89d81533e973abd7c39c09533747
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655654"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="318b7-103">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="318b7-103">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="318b7-104">書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="318b7-104">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="318b7-105">Configuration 要素 (Format) コントロールの構成 (書式) のコントロール要素の Configuration (書式) コントロール要素</span><span class="sxs-lookup"><span data-stu-id="318b7-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="318b7-106">構文</span><span class="sxs-lookup"><span data-stu-id="318b7-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="318b7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="318b7-107">Attributes and Elements</span></span>

<span data-ttu-id="318b7-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Control` ます。</span><span class="sxs-lookup"><span data-stu-id="318b7-108">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="318b7-109">各子要素のうち1つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="318b7-109">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="318b7-110">属性</span><span class="sxs-lookup"><span data-stu-id="318b7-110">Attributes</span></span>

<span data-ttu-id="318b7-111">なし。</span><span class="sxs-lookup"><span data-stu-id="318b7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="318b7-112">子要素</span><span class="sxs-lookup"><span data-stu-id="318b7-112">Child Elements</span></span>

|<span data-ttu-id="318b7-113">要素</span><span class="sxs-lookup"><span data-stu-id="318b7-113">Element</span></span>|<span data-ttu-id="318b7-114">説明</span><span class="sxs-lookup"><span data-stu-id="318b7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="318b7-115">Configuration の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="318b7-115">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="318b7-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="318b7-116">Required element.</span></span><br /><br /> <span data-ttu-id="318b7-117">コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="318b7-117">Defines the control.</span></span>|
|[<span data-ttu-id="318b7-118">Configuration のコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="318b7-118">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="318b7-119">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="318b7-119">Required element.</span></span><br /><br /> <span data-ttu-id="318b7-120">コントロールを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="318b7-120">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="318b7-121">親要素</span><span class="sxs-lookup"><span data-stu-id="318b7-121">Parent Elements</span></span>

|<span data-ttu-id="318b7-122">要素</span><span class="sxs-lookup"><span data-stu-id="318b7-122">Element</span></span>|<span data-ttu-id="318b7-123">説明</span><span class="sxs-lookup"><span data-stu-id="318b7-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="318b7-124">Configuration の Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="318b7-124">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="318b7-125">書式設定ファイルのすべてのビューまたはその他のコントロールで使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="318b7-125">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="318b7-126">解説</span><span class="sxs-lookup"><span data-stu-id="318b7-126">Remarks</span></span>

<span data-ttu-id="318b7-127">このコントロールに指定される名前は、次の要素で参照できます。</span><span class="sxs-lookup"><span data-stu-id="318b7-127">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="318b7-128">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="318b7-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="318b7-129">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="318b7-129">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="318b7-130">参照</span><span class="sxs-lookup"><span data-stu-id="318b7-130">See Also</span></span>

[<span data-ttu-id="318b7-131">Configuration の Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="318b7-131">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="318b7-132">構成用のコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="318b7-132">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="318b7-133">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="318b7-133">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="318b7-134">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="318b7-134">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="318b7-135">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="318b7-135">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="318b7-136">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="318b7-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
