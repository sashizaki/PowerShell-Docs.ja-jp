---
title: Configuration のコントロールの Control 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369011"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="91c1a-102">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="91c1a-102">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="91c1a-103">書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="91c1a-103">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="91c1a-104">Configuration 要素 (Format) コントロールの構成 (書式) のコントロール要素の Configuration (書式) コントロール要素</span><span class="sxs-lookup"><span data-stu-id="91c1a-104">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91c1a-105">構文</span><span class="sxs-lookup"><span data-stu-id="91c1a-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91c1a-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="91c1a-106">Attributes and Elements</span></span>

<span data-ttu-id="91c1a-107">次のセクションでは、`Control` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="91c1a-107">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="91c1a-108">各子要素のうち1つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91c1a-108">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="91c1a-109">属性</span><span class="sxs-lookup"><span data-stu-id="91c1a-109">Attributes</span></span>

<span data-ttu-id="91c1a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="91c1a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91c1a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="91c1a-111">Child Elements</span></span>

|<span data-ttu-id="91c1a-112">要素</span><span class="sxs-lookup"><span data-stu-id="91c1a-112">Element</span></span>|<span data-ttu-id="91c1a-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="91c1a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91c1a-114">構成用コントロールのコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="91c1a-114">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="91c1a-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="91c1a-115">Required element.</span></span><br /><br /> <span data-ttu-id="91c1a-116">コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="91c1a-116">Defines the control.</span></span>|
|[<span data-ttu-id="91c1a-117">Configuration のコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91c1a-117">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="91c1a-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="91c1a-118">Required element.</span></span><br /><br /> <span data-ttu-id="91c1a-119">コントロールを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="91c1a-119">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="91c1a-120">親要素</span><span class="sxs-lookup"><span data-stu-id="91c1a-120">Parent Elements</span></span>

|<span data-ttu-id="91c1a-121">要素</span><span class="sxs-lookup"><span data-stu-id="91c1a-121">Element</span></span>|<span data-ttu-id="91c1a-122">[説明]</span><span class="sxs-lookup"><span data-stu-id="91c1a-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91c1a-123">Configuration の Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91c1a-123">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="91c1a-124">書式設定ファイルのすべてのビューまたはその他のコントロールで使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="91c1a-124">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="91c1a-125">コメント</span><span class="sxs-lookup"><span data-stu-id="91c1a-125">Remarks</span></span>

<span data-ttu-id="91c1a-126">このコントロールに指定される名前は、次の要素で参照できます。</span><span class="sxs-lookup"><span data-stu-id="91c1a-126">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="91c1a-127">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91c1a-127">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="91c1a-128">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91c1a-128">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="91c1a-129">参照</span><span class="sxs-lookup"><span data-stu-id="91c1a-129">See Also</span></span>

[<span data-ttu-id="91c1a-130">Configuration の Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91c1a-130">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="91c1a-131">構成用のコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="91c1a-131">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="91c1a-132">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91c1a-132">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="91c1a-133">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91c1a-133">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="91c1a-134">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91c1a-134">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="91c1a-135">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="91c1a-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
