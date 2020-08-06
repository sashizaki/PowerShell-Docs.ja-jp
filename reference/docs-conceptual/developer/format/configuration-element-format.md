---
title: Configuration 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 90be02f8e27c0bd391e01da1a08ecd8eeb29b84c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783842"
---
# <a name="configuration-element-format"></a><span data-ttu-id="2e651-102">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2e651-102">Configuration Element (Format)</span></span>

<span data-ttu-id="2e651-103">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="2e651-103">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="2e651-104">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="2e651-104">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="2e651-105">構文</span><span class="sxs-lookup"><span data-stu-id="2e651-105">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2e651-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2e651-106">Attributes and Elements</span></span>

<span data-ttu-id="2e651-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="2e651-107">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="2e651-108">この要素は、各書式設定ファイルのルート要素である必要があり、この要素には少なくとも1つの子要素が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e651-108">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2e651-109">属性</span><span class="sxs-lookup"><span data-stu-id="2e651-109">Attributes</span></span>

<span data-ttu-id="2e651-110">なし。</span><span class="sxs-lookup"><span data-stu-id="2e651-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2e651-111">子要素</span><span class="sxs-lookup"><span data-stu-id="2e651-111">Child Elements</span></span>

|<span data-ttu-id="2e651-112">要素</span><span class="sxs-lookup"><span data-stu-id="2e651-112">Element</span></span>|<span data-ttu-id="2e651-113">説明</span><span class="sxs-lookup"><span data-stu-id="2e651-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2e651-114">Configuration の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2e651-114">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="2e651-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e651-115">Optional element.</span></span><br /><br /> <span data-ttu-id="2e651-116">書式設定ファイルのすべてのビューで使用できる共通コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="2e651-116">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="2e651-117">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2e651-117">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="2e651-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e651-118">Optional element.</span></span><br /><br /> <span data-ttu-id="2e651-119">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="2e651-119">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="2e651-120">SelectionSets 要素の形式</span><span class="sxs-lookup"><span data-stu-id="2e651-120">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="2e651-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e651-121">Optional element.</span></span><br /><br /> <span data-ttu-id="2e651-122">書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="2e651-122">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="2e651-123">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2e651-123">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="2e651-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e651-124">Optional element.</span></span><br /><br /> <span data-ttu-id="2e651-125">オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="2e651-125">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2e651-126">親要素</span><span class="sxs-lookup"><span data-stu-id="2e651-126">Parent Elements</span></span>

<span data-ttu-id="2e651-127">[なし] :</span><span class="sxs-lookup"><span data-stu-id="2e651-127">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e651-128">解説</span><span class="sxs-lookup"><span data-stu-id="2e651-128">Remarks</span></span>

<span data-ttu-id="2e651-129">書式設定ファイルは、オブジェクトの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="2e651-129">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="2e651-130">ほとんどの場合、このルート要素には、書式設定ファイルのテーブル、リスト、およびワイドビューを定義する[Viewdefinitions](./viewdefinitions-element-format.md)要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e651-130">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="2e651-131">ビュー定義に加えて、書式設定ファイルでは、これらのビューで使用できる共通の選択セット、設定、およびコントロールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="2e651-131">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e651-132">参照</span><span class="sxs-lookup"><span data-stu-id="2e651-132">See Also</span></span>

[<span data-ttu-id="2e651-133">Configuration の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2e651-133">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="2e651-134">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2e651-134">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="2e651-135">SelectionSets 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2e651-135">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="2e651-136">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2e651-136">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="2e651-137">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2e651-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
