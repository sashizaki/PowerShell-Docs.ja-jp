---
ms.date: 09/13/2016
ms.topic: reference
title: ViewSelectedBy の SelectionSetName 要素 (書式)
description: ViewSelectedBy の SelectionSetName 要素 (書式)
ms.openlocfilehash: a1a1816761715a138bcb3c2bd4cb9dbbb2f9cb92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654900"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="05fd0-103">ViewSelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="05fd0-103">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="05fd0-104">ビューに表示される一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="05fd0-104">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="05fd0-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) ViewSelectedBy Element (Format) SelectionSetName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="05fd0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="05fd0-106">構文</span><span class="sxs-lookup"><span data-stu-id="05fd0-106">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="05fd0-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="05fd0-107">Attributes and Elements</span></span>

<span data-ttu-id="05fd0-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="05fd0-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="05fd0-109">属性</span><span class="sxs-lookup"><span data-stu-id="05fd0-109">Attributes</span></span>

<span data-ttu-id="05fd0-110">なし。</span><span class="sxs-lookup"><span data-stu-id="05fd0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="05fd0-111">子要素</span><span class="sxs-lookup"><span data-stu-id="05fd0-111">Child Elements</span></span>

<span data-ttu-id="05fd0-112">なし。</span><span class="sxs-lookup"><span data-stu-id="05fd0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="05fd0-113">親要素</span><span class="sxs-lookup"><span data-stu-id="05fd0-113">Parent Elements</span></span>

|<span data-ttu-id="05fd0-114">要素</span><span class="sxs-lookup"><span data-stu-id="05fd0-114">Element</span></span>|<span data-ttu-id="05fd0-115">説明</span><span class="sxs-lookup"><span data-stu-id="05fd0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="05fd0-116">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="05fd0-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="05fd0-117">ビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="05fd0-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="05fd0-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="05fd0-118">Text Value</span></span>

<span data-ttu-id="05fd0-119">選択セットの要素によって定義される選択セットの名前を指定し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="05fd0-119">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="05fd0-120">解説</span><span class="sxs-lookup"><span data-stu-id="05fd0-120">Remarks</span></span>

<span data-ttu-id="05fd0-121">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="05fd0-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="05fd0-122">選択セットの定義と参照の詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05fd0-122">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="05fd0-123">例</span><span class="sxs-lookup"><span data-stu-id="05fd0-123">Example</span></span>

<span data-ttu-id="05fd0-124">次の例では、リストビューの選択セットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="05fd0-124">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="05fd0-125">テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="05fd0-125">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="05fd0-126">参照</span><span class="sxs-lookup"><span data-stu-id="05fd0-126">See Also</span></span>

[<span data-ttu-id="05fd0-127">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="05fd0-127">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="05fd0-128">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="05fd0-128">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="05fd0-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="05fd0-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
