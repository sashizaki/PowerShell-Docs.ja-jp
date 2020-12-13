---
ms.date: 09/13/2016
ms.topic: reference
title: View の GroupBy 要素 (書式)
description: View の GroupBy 要素 (書式)
ms.openlocfilehash: d8ca93a3b2c1490928885579919c07f5eb274cd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652097"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="074c8-103">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-103">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="074c8-104">オブジェクトの新しいグループをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="074c8-104">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="074c8-105">この要素は、テーブル、リスト、ワイド、またはカスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="074c8-105">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="074c8-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (形式) GroupBy 要素ビュー (形式)</span><span class="sxs-lookup"><span data-stu-id="074c8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="074c8-107">構文</span><span class="sxs-lookup"><span data-stu-id="074c8-107">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="074c8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="074c8-108">Attributes and Elements</span></span>

<span data-ttu-id="074c8-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="074c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="074c8-110">属性</span><span class="sxs-lookup"><span data-stu-id="074c8-110">Attributes</span></span>

<span data-ttu-id="074c8-111">なし。</span><span class="sxs-lookup"><span data-stu-id="074c8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="074c8-112">子要素</span><span class="sxs-lookup"><span data-stu-id="074c8-112">Child Elements</span></span>

|<span data-ttu-id="074c8-113">要素</span><span class="sxs-lookup"><span data-stu-id="074c8-113">Element</span></span>|<span data-ttu-id="074c8-114">説明</span><span class="sxs-lookup"><span data-stu-id="074c8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="074c8-115">GroupBy の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-115">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="074c8-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="074c8-116">Optional element.</span></span><br /><br /> <span data-ttu-id="074c8-117">新しいグループを表示するカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="074c8-117">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="074c8-118">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-118">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="074c8-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="074c8-119">Optional element.</span></span><br /><br /> <span data-ttu-id="074c8-120">新しいグループを表示するために使用するコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="074c8-120">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="074c8-121">GroupBy の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-121">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="074c8-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="074c8-122">Optional element.</span></span><br /><br /> <span data-ttu-id="074c8-123">新しいグループが検出されたときに表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="074c8-123">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="074c8-124">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-124">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="074c8-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="074c8-125">Optional element.</span></span><br /><br /> <span data-ttu-id="074c8-126">.NET プロパティの値が変更されるたびに、によって新しいグループが開始されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="074c8-126">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="074c8-127">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="074c8-128">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="074c8-128">Optional element.</span></span><br /><br /> <span data-ttu-id="074c8-129">値が変更されるたびに新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="074c8-129">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="074c8-130">親要素</span><span class="sxs-lookup"><span data-stu-id="074c8-130">Parent Elements</span></span>

|<span data-ttu-id="074c8-131">要素</span><span class="sxs-lookup"><span data-stu-id="074c8-131">Element</span></span>|<span data-ttu-id="074c8-132">説明</span><span class="sxs-lookup"><span data-stu-id="074c8-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="074c8-133">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-133">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="074c8-134">1つ以上の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="074c8-134">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="074c8-135">解説</span><span class="sxs-lookup"><span data-stu-id="074c8-135">Remarks</span></span>

<span data-ttu-id="074c8-136">新しいオブジェクトのグループをどのように表示するかを定義するときには、新しいグループを開始するプロパティまたはスクリプトを指定する必要があります。ただし、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="074c8-136">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="074c8-137">参照</span><span class="sxs-lookup"><span data-stu-id="074c8-137">See Also</span></span>

[<span data-ttu-id="074c8-138">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-138">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="074c8-139">GroupBy の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-139">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="074c8-140">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-140">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="074c8-141">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-141">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="074c8-142">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="074c8-142">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="074c8-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="074c8-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
