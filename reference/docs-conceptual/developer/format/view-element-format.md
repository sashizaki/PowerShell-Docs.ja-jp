---
ms.date: 09/13/2016
ms.topic: reference
title: View 要素 (書式)
description: View 要素 (書式)
ms.openlocfilehash: 6fed1304d94339cc90b6ae53e06483c08d937c12
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649743"
---
# <a name="view-element-format"></a><span data-ttu-id="62d9a-103">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-103">View Element (Format)</span></span>

<span data-ttu-id="62d9a-104">1つ以上の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-104">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="62d9a-105">書式設定ファイルで定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="62d9a-105">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="62d9a-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="62d9a-107">構文</span><span class="sxs-lookup"><span data-stu-id="62d9a-107">Syntax</span></span>

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="62d9a-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="62d9a-108">Attributes and Elements</span></span>

<span data-ttu-id="62d9a-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `View` ます。</span><span class="sxs-lookup"><span data-stu-id="62d9a-109">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="62d9a-110">コントロールの子要素を1つだけ指定し、ビューの名前とビューを使用するオブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62d9a-110">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="62d9a-111">カスタムコントロールの定義、オブジェクトのグループ化、およびビューが帯域外であるかどうかの指定はオプションです。</span><span class="sxs-lookup"><span data-stu-id="62d9a-111">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="62d9a-112">属性</span><span class="sxs-lookup"><span data-stu-id="62d9a-112">Attributes</span></span>

<span data-ttu-id="62d9a-113">なし。</span><span class="sxs-lookup"><span data-stu-id="62d9a-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="62d9a-114">子要素</span><span class="sxs-lookup"><span data-stu-id="62d9a-114">Child Elements</span></span>

|<span data-ttu-id="62d9a-115">要素</span><span class="sxs-lookup"><span data-stu-id="62d9a-115">Element</span></span>|<span data-ttu-id="62d9a-116">説明</span><span class="sxs-lookup"><span data-stu-id="62d9a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="62d9a-117">View の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-117">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="62d9a-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="62d9a-118">Optional element.</span></span><br /><br /> <span data-ttu-id="62d9a-119">ビュー内から名前で参照できるコントロールのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-119">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="62d9a-120">CustomControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="62d9a-120">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="62d9a-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="62d9a-121">Optional element.</span></span><br /><br /> <span data-ttu-id="62d9a-122">ビューのカスタムコントロール形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-122">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="62d9a-123">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-123">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="62d9a-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="62d9a-124">Optional element.</span></span><br /><br /> <span data-ttu-id="62d9a-125">.NET オブジェクトのメンバーをグループ化する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-125">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="62d9a-126">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-126">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="62d9a-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="62d9a-127">Optional element.</span></span><br /><br /> <span data-ttu-id="62d9a-128">ビューのリスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-128">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="62d9a-129">View の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-129">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="62d9a-130">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="62d9a-130">Required element.</span></span><br /><br /> <span data-ttu-id="62d9a-131">ビューを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-131">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="62d9a-132">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-132">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="62d9a-133">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="62d9a-133">Optional element.</span></span><br /><br /> <span data-ttu-id="62d9a-134">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-134">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="62d9a-135">View (Format) の ViewSelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="62d9a-135">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="62d9a-136">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="62d9a-136">Required element.</span></span><br /><br /> <span data-ttu-id="62d9a-137">このビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-137">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="62d9a-138">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-138">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="62d9a-139">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="62d9a-139">Optional element.</span></span><br /><br /> <span data-ttu-id="62d9a-140">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-140">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="62d9a-141">親要素</span><span class="sxs-lookup"><span data-stu-id="62d9a-141">Parent Elements</span></span>

|<span data-ttu-id="62d9a-142">要素</span><span class="sxs-lookup"><span data-stu-id="62d9a-142">Element</span></span>|<span data-ttu-id="62d9a-143">説明</span><span class="sxs-lookup"><span data-stu-id="62d9a-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="62d9a-144">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-144">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="62d9a-145">オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="62d9a-145">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="62d9a-146">解説</span><span class="sxs-lookup"><span data-stu-id="62d9a-146">Remarks</span></span>

<span data-ttu-id="62d9a-147">さまざまなビューとカスタムコントロールのコンポーネントの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62d9a-147">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="62d9a-148">テーブルビューのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="62d9a-148">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="62d9a-149">リストビューのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="62d9a-149">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="62d9a-150">ワイドビューコンポーネント</span><span class="sxs-lookup"><span data-stu-id="62d9a-150">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="62d9a-151">カスタムコントロール</span><span class="sxs-lookup"><span data-stu-id="62d9a-151">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="62d9a-152">例</span><span class="sxs-lookup"><span data-stu-id="62d9a-152">Example</span></span>

<span data-ttu-id="62d9a-153">次の例は、 `View` [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトのテーブルビューを定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="62d9a-153">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="62d9a-154">参照</span><span class="sxs-lookup"><span data-stu-id="62d9a-154">See Also</span></span>

[<span data-ttu-id="62d9a-155">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-155">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="62d9a-156">View の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-156">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="62d9a-157">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-157">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="62d9a-158">View の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-158">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="62d9a-159">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-159">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="62d9a-160">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-160">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="62d9a-161">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-161">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="62d9a-162">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62d9a-162">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="62d9a-163">CustomControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="62d9a-163">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="62d9a-164">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="62d9a-164">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
