---
title: ビューの GroupBy 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2f9071a3ebbc7cc2ccb7721dd518e82723e9cc4e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781428"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="ac97e-102">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-102">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="ac97e-103">オブジェクトの新しいグループをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac97e-103">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="ac97e-104">この要素は、テーブル、リスト、ワイド、またはカスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac97e-104">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="ac97e-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (形式) GroupBy 要素ビュー (形式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ac97e-106">構文</span><span class="sxs-lookup"><span data-stu-id="ac97e-106">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ac97e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ac97e-107">Attributes and Elements</span></span>

<span data-ttu-id="ac97e-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac97e-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ac97e-109">属性</span><span class="sxs-lookup"><span data-stu-id="ac97e-109">Attributes</span></span>

<span data-ttu-id="ac97e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ac97e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ac97e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ac97e-111">Child Elements</span></span>

|<span data-ttu-id="ac97e-112">要素</span><span class="sxs-lookup"><span data-stu-id="ac97e-112">Element</span></span>|<span data-ttu-id="ac97e-113">説明</span><span class="sxs-lookup"><span data-stu-id="ac97e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ac97e-114">GroupBy の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-114">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="ac97e-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ac97e-115">Optional element.</span></span><br /><br /> <span data-ttu-id="ac97e-116">新しいグループを表示するカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac97e-116">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="ac97e-117">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-117">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="ac97e-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ac97e-118">Optional element.</span></span><br /><br /> <span data-ttu-id="ac97e-119">新しいグループを表示するために使用するコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac97e-119">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="ac97e-120">GroupBy の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-120">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="ac97e-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ac97e-121">Optional element.</span></span><br /><br /> <span data-ttu-id="ac97e-122">新しいグループが検出されたときに表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac97e-122">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="ac97e-123">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="ac97e-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ac97e-124">Optional element.</span></span><br /><br /> <span data-ttu-id="ac97e-125">.NET プロパティの値が変更されるたびに、によって新しいグループが開始されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac97e-125">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="ac97e-126">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-126">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="ac97e-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ac97e-127">Optional element.</span></span><br /><br /> <span data-ttu-id="ac97e-128">値が変更されるたびに新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac97e-128">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ac97e-129">親要素</span><span class="sxs-lookup"><span data-stu-id="ac97e-129">Parent Elements</span></span>

|<span data-ttu-id="ac97e-130">要素</span><span class="sxs-lookup"><span data-stu-id="ac97e-130">Element</span></span>|<span data-ttu-id="ac97e-131">説明</span><span class="sxs-lookup"><span data-stu-id="ac97e-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ac97e-132">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-132">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="ac97e-133">1つ以上の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac97e-133">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ac97e-134">解説</span><span class="sxs-lookup"><span data-stu-id="ac97e-134">Remarks</span></span>

<span data-ttu-id="ac97e-135">新しいオブジェクトのグループをどのように表示するかを定義するときには、新しいグループを開始するプロパティまたはスクリプトを指定する必要があります。ただし、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac97e-135">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac97e-136">参照</span><span class="sxs-lookup"><span data-stu-id="ac97e-136">See Also</span></span>

[<span data-ttu-id="ac97e-137">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-137">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="ac97e-138">GroupBy の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-138">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="ac97e-139">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-139">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="ac97e-140">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-140">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="ac97e-141">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac97e-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="ac97e-142">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ac97e-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
