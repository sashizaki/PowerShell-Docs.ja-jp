---
title: 構成要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066823"
---
# <a name="configuration-element-format"></a><span data-ttu-id="17dd9-102">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="17dd9-102">Configuration Element (Format)</span></span>

<span data-ttu-id="17dd9-103">書式設定ファイルの最上位の要素を表します。</span><span class="sxs-lookup"><span data-stu-id="17dd9-103">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="17dd9-104">構成要素</span><span class="sxs-lookup"><span data-stu-id="17dd9-104">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="17dd9-105">構文</span><span class="sxs-lookup"><span data-stu-id="17dd9-105">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="17dd9-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="17dd9-106">Attributes and Elements</span></span>

<span data-ttu-id="17dd9-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Configuration`要素。</span><span class="sxs-lookup"><span data-stu-id="17dd9-107">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="17dd9-108">この要素は、書式設定ファイルごとにルート要素である必要があり、この要素は、少なくとも 1 つの子要素を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="17dd9-108">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="17dd9-109">属性</span><span class="sxs-lookup"><span data-stu-id="17dd9-109">Attributes</span></span>

<span data-ttu-id="17dd9-110">なし。</span><span class="sxs-lookup"><span data-stu-id="17dd9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="17dd9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="17dd9-111">Child Elements</span></span>

|<span data-ttu-id="17dd9-112">要素</span><span class="sxs-lookup"><span data-stu-id="17dd9-112">Element</span></span>|<span data-ttu-id="17dd9-113">説明</span><span class="sxs-lookup"><span data-stu-id="17dd9-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="17dd9-114">構成 (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="17dd9-114">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="17dd9-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="17dd9-115">Optional element.</span></span><br /><br /> <span data-ttu-id="17dd9-116">書式設定ファイルのすべてのビューで使用できる一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="17dd9-116">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="17dd9-117">DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="17dd9-117">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="17dd9-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="17dd9-118">Optional element.</span></span><br /><br /> <span data-ttu-id="17dd9-119">書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="17dd9-119">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="17dd9-120">SelectionSets 要素の形式</span><span class="sxs-lookup"><span data-stu-id="17dd9-120">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="17dd9-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="17dd9-121">Optional element.</span></span><br /><br /> <span data-ttu-id="17dd9-122">書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="17dd9-122">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="17dd9-123">ViewDefinitions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="17dd9-123">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="17dd9-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="17dd9-124">Optional element.</span></span><br /><br /> <span data-ttu-id="17dd9-125">オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="17dd9-125">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="17dd9-126">親要素</span><span class="sxs-lookup"><span data-stu-id="17dd9-126">Parent Elements</span></span>

<span data-ttu-id="17dd9-127">なし。</span><span class="sxs-lookup"><span data-stu-id="17dd9-127">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="17dd9-128">コメント</span><span class="sxs-lookup"><span data-stu-id="17dd9-128">Remarks</span></span>

<span data-ttu-id="17dd9-129">書式設定ファイルでは、オブジェクトの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="17dd9-129">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="17dd9-130">このルート要素を含むほとんどの場合、 [ViewDefinitions](./viewdefinitions-element-format.md)テーブル、リスト、および書式設定ファイルの全体のビューを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="17dd9-130">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="17dd9-131">書式設定ファイルには、ビューの定義に加えて、一般的な選択範囲を設定、設定、およびそれらのビューが使用できるコントロールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="17dd9-131">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="17dd9-132">参照</span><span class="sxs-lookup"><span data-stu-id="17dd9-132">See Also</span></span>

[<span data-ttu-id="17dd9-133">構成 (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="17dd9-133">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="17dd9-134">DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="17dd9-134">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="17dd9-135">SelectionSets 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="17dd9-135">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="17dd9-136">ViewDefinitions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="17dd9-136">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="17dd9-137">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="17dd9-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
