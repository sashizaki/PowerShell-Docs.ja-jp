---
title: View 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c0c6fa373cfca3a55a62f201e1eabc6a1e308ef7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785032"
---
# <a name="view-element-format"></a><span data-ttu-id="2bb1b-102">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-102">View Element (Format)</span></span>

<span data-ttu-id="2bb1b-103">1つ以上の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="2bb1b-104">書式設定ファイルで定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="2bb1b-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2bb1b-106">構文</span><span class="sxs-lookup"><span data-stu-id="2bb1b-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="2bb1b-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2bb1b-107">Attributes and Elements</span></span>

<span data-ttu-id="2bb1b-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `View` ます。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="2bb1b-109">コントロールの子要素を1つだけ指定し、ビューの名前とビューを使用するオブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="2bb1b-110">カスタムコントロールの定義、オブジェクトのグループ化、およびビューが帯域外であるかどうかの指定はオプションです。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="2bb1b-111">属性</span><span class="sxs-lookup"><span data-stu-id="2bb1b-111">Attributes</span></span>

<span data-ttu-id="2bb1b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2bb1b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="2bb1b-113">Child Elements</span></span>

|<span data-ttu-id="2bb1b-114">要素</span><span class="sxs-lookup"><span data-stu-id="2bb1b-114">Element</span></span>|<span data-ttu-id="2bb1b-115">説明</span><span class="sxs-lookup"><span data-stu-id="2bb1b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2bb1b-116">View の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="2bb1b-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-117">Optional element.</span></span><br /><br /> <span data-ttu-id="2bb1b-118">ビュー内から名前で参照できるコントロールのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="2bb1b-119">CustomControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="2bb1b-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-120">Optional element.</span></span><br /><br /> <span data-ttu-id="2bb1b-121">ビューのカスタムコントロール形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="2bb1b-122">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="2bb1b-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-123">Optional element.</span></span><br /><br /> <span data-ttu-id="2bb1b-124">.NET オブジェクトのメンバーをグループ化する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="2bb1b-125">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="2bb1b-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-126">Optional element.</span></span><br /><br /> <span data-ttu-id="2bb1b-127">ビューのリスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="2bb1b-128">View の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="2bb1b-129">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-129">Required element.</span></span><br /><br /> <span data-ttu-id="2bb1b-130">ビューを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="2bb1b-131">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="2bb1b-132">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-132">Optional element.</span></span><br /><br /> <span data-ttu-id="2bb1b-133">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="2bb1b-134">View (Format) の ViewSelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="2bb1b-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="2bb1b-135">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-135">Required element.</span></span><br /><br /> <span data-ttu-id="2bb1b-136">このビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="2bb1b-137">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="2bb1b-138">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-138">Optional element.</span></span><br /><br /> <span data-ttu-id="2bb1b-139">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2bb1b-140">親要素</span><span class="sxs-lookup"><span data-stu-id="2bb1b-140">Parent Elements</span></span>

|<span data-ttu-id="2bb1b-141">要素</span><span class="sxs-lookup"><span data-stu-id="2bb1b-141">Element</span></span>|<span data-ttu-id="2bb1b-142">説明</span><span class="sxs-lookup"><span data-stu-id="2bb1b-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2bb1b-143">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="2bb1b-144">オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2bb1b-145">解説</span><span class="sxs-lookup"><span data-stu-id="2bb1b-145">Remarks</span></span>

<span data-ttu-id="2bb1b-146">さまざまなビューとカスタムコントロールのコンポーネントの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="2bb1b-147">テーブルビューのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="2bb1b-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="2bb1b-148">リストビューのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="2bb1b-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="2bb1b-149">ワイドビューコンポーネント</span><span class="sxs-lookup"><span data-stu-id="2bb1b-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="2bb1b-150">カスタムコントロール</span><span class="sxs-lookup"><span data-stu-id="2bb1b-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="2bb1b-151">例</span><span class="sxs-lookup"><span data-stu-id="2bb1b-151">Example</span></span>

<span data-ttu-id="2bb1b-152">次の例は、 `View` [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのテーブルビューを定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="2bb1b-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2bb1b-153">参照</span><span class="sxs-lookup"><span data-stu-id="2bb1b-153">See Also</span></span>

[<span data-ttu-id="2bb1b-154">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="2bb1b-155">View の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="2bb1b-156">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="2bb1b-157">View の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="2bb1b-158">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="2bb1b-159">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="2bb1b-160">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="2bb1b-161">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="2bb1b-162">CustomControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2bb1b-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="2bb1b-163">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2bb1b-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
