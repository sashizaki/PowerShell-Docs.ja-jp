---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration 要素 (書式)
description: Configuration 要素 (書式)
ms.openlocfilehash: 0524736d40dd7a7acb0b6fb61d1438b75672c240
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655689"
---
# <a name="configuration-element-format"></a><span data-ttu-id="15444-103">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15444-103">Configuration Element (Format)</span></span>

<span data-ttu-id="15444-104">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="15444-104">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="15444-105">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="15444-105">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="15444-106">構文</span><span class="sxs-lookup"><span data-stu-id="15444-106">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="15444-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="15444-107">Attributes and Elements</span></span>

<span data-ttu-id="15444-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="15444-108">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="15444-109">この要素は、各書式設定ファイルのルート要素である必要があり、この要素には少なくとも1つの子要素が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="15444-109">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="15444-110">属性</span><span class="sxs-lookup"><span data-stu-id="15444-110">Attributes</span></span>

<span data-ttu-id="15444-111">なし。</span><span class="sxs-lookup"><span data-stu-id="15444-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15444-112">子要素</span><span class="sxs-lookup"><span data-stu-id="15444-112">Child Elements</span></span>

|<span data-ttu-id="15444-113">要素</span><span class="sxs-lookup"><span data-stu-id="15444-113">Element</span></span>|<span data-ttu-id="15444-114">説明</span><span class="sxs-lookup"><span data-stu-id="15444-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15444-115">Configuration の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15444-115">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="15444-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="15444-116">Optional element.</span></span><br /><br /> <span data-ttu-id="15444-117">書式設定ファイルのすべてのビューで使用できる共通コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="15444-117">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="15444-118">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15444-118">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="15444-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="15444-119">Optional element.</span></span><br /><br /> <span data-ttu-id="15444-120">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="15444-120">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="15444-121">SelectionSets 要素の形式</span><span class="sxs-lookup"><span data-stu-id="15444-121">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="15444-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="15444-122">Optional element.</span></span><br /><br /> <span data-ttu-id="15444-123">書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="15444-123">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="15444-124">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15444-124">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="15444-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="15444-125">Optional element.</span></span><br /><br /> <span data-ttu-id="15444-126">オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="15444-126">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="15444-127">親要素</span><span class="sxs-lookup"><span data-stu-id="15444-127">Parent Elements</span></span>

<span data-ttu-id="15444-128">[なし] :</span><span class="sxs-lookup"><span data-stu-id="15444-128">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="15444-129">解説</span><span class="sxs-lookup"><span data-stu-id="15444-129">Remarks</span></span>

<span data-ttu-id="15444-130">書式設定ファイルは、オブジェクトの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="15444-130">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="15444-131">ほとんどの場合、このルート要素には、書式設定ファイルのテーブル、リスト、およびワイドビューを定義する [Viewdefinitions](./viewdefinitions-element-format.md) 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="15444-131">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="15444-132">ビュー定義に加えて、書式設定ファイルでは、これらのビューで使用できる共通の選択セット、設定、およびコントロールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="15444-132">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="15444-133">参照</span><span class="sxs-lookup"><span data-stu-id="15444-133">See Also</span></span>

[<span data-ttu-id="15444-134">Configuration の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15444-134">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="15444-135">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15444-135">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="15444-136">SelectionSets 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15444-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="15444-137">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15444-137">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="15444-138">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="15444-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
