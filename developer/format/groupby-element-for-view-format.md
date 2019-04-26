---
title: GroupBy 要素 (形式) の表示 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a2b061-2a4a-4ad1-84f9-cdbefb64aaab
caps.latest.revision: 8
ms.openlocfilehash: abb8b91626128b3deaa2db24a9fd8b34a6563410
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065545"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="1ab58-102">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1ab58-102">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="1ab58-103">オブジェクトの新しいグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="1ab58-103">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="1ab58-104">この要素は、テーブル、リスト、幅、またはカスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ab58-104">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="1ab58-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) のビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1ab58-106">構文</span><span class="sxs-lookup"><span data-stu-id="1ab58-106">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ab58-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-107">Attributes and Elements</span></span>

<span data-ttu-id="1ab58-108">次のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ab58-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1ab58-109">属性</span><span class="sxs-lookup"><span data-stu-id="1ab58-109">Attributes</span></span>

<span data-ttu-id="1ab58-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1ab58-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1ab58-111">子要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-111">Child Elements</span></span>

|<span data-ttu-id="1ab58-112">要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-112">Element</span></span>|<span data-ttu-id="1ab58-113">説明</span><span class="sxs-lookup"><span data-stu-id="1ab58-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ab58-114">GroupBy (形式) のカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-114">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="1ab58-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1ab58-115">Optional element.</span></span><br /><br /> <span data-ttu-id="1ab58-116">新しいグループを表示するカスタム コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ab58-116">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="1ab58-117">GroupBy (形式) の CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-117">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="1ab58-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1ab58-118">Optional element.</span></span><br /><br /> <span data-ttu-id="1ab58-119">新しいグループを表示するために使用するコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ab58-119">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="1ab58-120">GroupBy (形式) のラベル要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-120">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="1ab58-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1ab58-121">Optional element.</span></span><br /><br /> <span data-ttu-id="1ab58-122">新しいグループが発生したときに表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ab58-122">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="1ab58-123">GroupBy (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="1ab58-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1ab58-124">Optional element.</span></span><br /><br /> <span data-ttu-id="1ab58-125">.NET プロパティを開始を示す値が変更されるたびに、新しいグループ。</span><span class="sxs-lookup"><span data-stu-id="1ab58-125">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="1ab58-126">GroupBy (形式) の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-126">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="1ab58-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1ab58-127">Optional element.</span></span><br /><br /> <span data-ttu-id="1ab58-128">その値が変更されるたびに、新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ab58-128">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1ab58-129">親要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-129">Parent Elements</span></span>

|<span data-ttu-id="1ab58-130">要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-130">Element</span></span>|<span data-ttu-id="1ab58-131">説明</span><span class="sxs-lookup"><span data-stu-id="1ab58-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ab58-132">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1ab58-132">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="1ab58-133">1 つまたは複数の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ab58-133">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1ab58-134">コメント</span><span class="sxs-lookup"><span data-stu-id="1ab58-134">Remarks</span></span>

<span data-ttu-id="1ab58-135">オブジェクトの新しいグループを表示する方法を定義するときは、プロパティまたは新しいグループを開始するスクリプトを指定する必要があります。ただし、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1ab58-135">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ab58-136">参照</span><span class="sxs-lookup"><span data-stu-id="1ab58-136">See Also</span></span>

[<span data-ttu-id="1ab58-137">GroupBy (形式) の CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-137">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="1ab58-138">GroupBy (形式) のラベル要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-138">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="1ab58-139">GroupBy (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-139">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="1ab58-140">GroupBy (形式) の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="1ab58-140">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="1ab58-141">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1ab58-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="1ab58-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="1ab58-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
