---
title: ViewSelectedBy (Format) の SelectionSetName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f6410b463bcb00d2758849c2f7e13cd839277e50
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772605"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="06993-102">ViewSelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06993-102">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="06993-103">ビューに表示される一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="06993-103">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="06993-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) ViewSelectedBy Element (Format) SelectionSetName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="06993-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="06993-105">構文</span><span class="sxs-lookup"><span data-stu-id="06993-105">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="06993-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="06993-106">Attributes and Elements</span></span>

<span data-ttu-id="06993-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="06993-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="06993-108">属性</span><span class="sxs-lookup"><span data-stu-id="06993-108">Attributes</span></span>

<span data-ttu-id="06993-109">なし。</span><span class="sxs-lookup"><span data-stu-id="06993-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="06993-110">子要素</span><span class="sxs-lookup"><span data-stu-id="06993-110">Child Elements</span></span>

<span data-ttu-id="06993-111">なし。</span><span class="sxs-lookup"><span data-stu-id="06993-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="06993-112">親要素</span><span class="sxs-lookup"><span data-stu-id="06993-112">Parent Elements</span></span>

|<span data-ttu-id="06993-113">要素</span><span class="sxs-lookup"><span data-stu-id="06993-113">Element</span></span>|<span data-ttu-id="06993-114">説明</span><span class="sxs-lookup"><span data-stu-id="06993-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="06993-115">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06993-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="06993-116">ビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="06993-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="06993-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="06993-117">Text Value</span></span>

<span data-ttu-id="06993-118">選択セットの要素によって定義される選択セットの名前を指定し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="06993-118">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="06993-119">解説</span><span class="sxs-lookup"><span data-stu-id="06993-119">Remarks</span></span>

<span data-ttu-id="06993-120">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="06993-120">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="06993-121">選択セットの定義と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06993-121">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="06993-122">例</span><span class="sxs-lookup"><span data-stu-id="06993-122">Example</span></span>

<span data-ttu-id="06993-123">次の例では、リストビューの選択セットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="06993-123">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="06993-124">テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="06993-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="06993-125">参照</span><span class="sxs-lookup"><span data-stu-id="06993-125">See Also</span></span>

[<span data-ttu-id="06993-126">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="06993-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="06993-127">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06993-127">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="06993-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="06993-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
