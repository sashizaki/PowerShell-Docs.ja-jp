---
title: View 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361461"
---
# <a name="view-element-format"></a><span data-ttu-id="48943-102">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="48943-102">View Element (Format)</span></span>

<span data-ttu-id="48943-103">1つ以上の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="48943-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="48943-104">書式設定ファイルで定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="48943-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="48943-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="48943-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="48943-106">構文</span><span class="sxs-lookup"><span data-stu-id="48943-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="48943-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="48943-107">Attributes and Elements</span></span>

<span data-ttu-id="48943-108">次のセクションでは、`View` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="48943-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="48943-109">コントロールの子要素を1つだけ指定し、ビューの名前とビューを使用するオブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48943-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="48943-110">カスタムコントロールの定義、オブジェクトのグループ化、およびビューが帯域外であるかどうかの指定はオプションです。</span><span class="sxs-lookup"><span data-stu-id="48943-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="48943-111">属性</span><span class="sxs-lookup"><span data-stu-id="48943-111">Attributes</span></span>

<span data-ttu-id="48943-112">なし。</span><span class="sxs-lookup"><span data-stu-id="48943-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="48943-113">子要素</span><span class="sxs-lookup"><span data-stu-id="48943-113">Child Elements</span></span>

|<span data-ttu-id="48943-114">要素</span><span class="sxs-lookup"><span data-stu-id="48943-114">Element</span></span>|<span data-ttu-id="48943-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="48943-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48943-116">View (Format) の Controls 要素</span><span class="sxs-lookup"><span data-stu-id="48943-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="48943-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="48943-117">Optional element.</span></span><br /><br /> <span data-ttu-id="48943-118">ビュー内から名前で参照できるコントロールのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="48943-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="48943-119">CustomControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="48943-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="48943-120">Optional element.</span></span><br /><br /> <span data-ttu-id="48943-121">ビューのカスタムコントロール形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="48943-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="48943-122">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="48943-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="48943-123">Optional element.</span></span><br /><br /> <span data-ttu-id="48943-124">.NET オブジェクトのメンバーをグループ化する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="48943-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="48943-125">ListControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="48943-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="48943-126">Optional element.</span></span><br /><br /> <span data-ttu-id="48943-127">ビューのリスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="48943-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="48943-128">ビューの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="48943-129">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="48943-129">Required element.</span></span><br /><br /> <span data-ttu-id="48943-130">ビューを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="48943-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="48943-131">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="48943-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="48943-132">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="48943-132">Optional element.</span></span><br /><br /> <span data-ttu-id="48943-133">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="48943-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="48943-134">View (Format) の ViewSelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="48943-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="48943-135">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="48943-135">Required element.</span></span><br /><br /> <span data-ttu-id="48943-136">このビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="48943-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="48943-137">WideControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="48943-138">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="48943-138">Optional element.</span></span><br /><br /> <span data-ttu-id="48943-139">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="48943-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="48943-140">親要素</span><span class="sxs-lookup"><span data-stu-id="48943-140">Parent Elements</span></span>

|<span data-ttu-id="48943-141">要素</span><span class="sxs-lookup"><span data-stu-id="48943-141">Element</span></span>|<span data-ttu-id="48943-142">[説明]</span><span class="sxs-lookup"><span data-stu-id="48943-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48943-143">ViewDefinitions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="48943-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="48943-144">オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="48943-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="48943-145">コメント</span><span class="sxs-lookup"><span data-stu-id="48943-145">Remarks</span></span>

<span data-ttu-id="48943-146">さまざまなビューとカスタムコントロールのコンポーネントの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48943-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="48943-147">テーブルビューのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="48943-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="48943-148">リストビューのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="48943-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="48943-149">ワイドビューコンポーネント</span><span class="sxs-lookup"><span data-stu-id="48943-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="48943-150">カスタムコントロール</span><span class="sxs-lookup"><span data-stu-id="48943-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="48943-151">例</span><span class="sxs-lookup"><span data-stu-id="48943-151">Example</span></span>

<span data-ttu-id="48943-152">この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのテーブルビューを定義する `View` 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="48943-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="48943-153">参照</span><span class="sxs-lookup"><span data-stu-id="48943-153">See Also</span></span>

[<span data-ttu-id="48943-154">ViewDefinitions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="48943-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="48943-155">ビューの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="48943-156">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="48943-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="48943-157">View (Format) の Controls 要素</span><span class="sxs-lookup"><span data-stu-id="48943-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="48943-158">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="48943-159">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="48943-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="48943-160">ListControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="48943-161">WideControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="48943-162">CustomControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="48943-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="48943-163">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="48943-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
