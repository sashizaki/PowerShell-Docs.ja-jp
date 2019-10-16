---
title: ViewSelectedBy (Format) の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ab0f033-df09-4435-a8bd-76ec2d01f13b
caps.latest.revision: 13
ms.openlocfilehash: d1de2b30860bac80bf17508f40eec33c2794c4b2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368261"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="f238b-102">ViewSelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f238b-102">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="f238b-103">ビューに表示される一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f238b-103">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="f238b-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) ViewSelectedBy Element (Format) SelectionSetName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f238b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f238b-105">構文</span><span class="sxs-lookup"><span data-stu-id="f238b-105">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f238b-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f238b-106">Attributes and Elements</span></span>

<span data-ttu-id="f238b-107">次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f238b-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f238b-108">属性</span><span class="sxs-lookup"><span data-stu-id="f238b-108">Attributes</span></span>

<span data-ttu-id="f238b-109">なし。</span><span class="sxs-lookup"><span data-stu-id="f238b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f238b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="f238b-110">Child Elements</span></span>

<span data-ttu-id="f238b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f238b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f238b-112">親要素</span><span class="sxs-lookup"><span data-stu-id="f238b-112">Parent Elements</span></span>

|<span data-ttu-id="f238b-113">要素</span><span class="sxs-lookup"><span data-stu-id="f238b-113">Element</span></span>|<span data-ttu-id="f238b-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="f238b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f238b-115">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f238b-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="f238b-116">ビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="f238b-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f238b-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f238b-117">Text Value</span></span>

<span data-ttu-id="f238b-118">選択セットの `Name` 要素によって定義される選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f238b-118">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f238b-119">コメント</span><span class="sxs-lookup"><span data-stu-id="f238b-119">Remarks</span></span>

<span data-ttu-id="f238b-120">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f238b-120">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="f238b-121">選択セットの定義と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f238b-121">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="f238b-122">例</span><span class="sxs-lookup"><span data-stu-id="f238b-122">Example</span></span>

<span data-ttu-id="f238b-123">次の例では、リストビューの選択セットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f238b-123">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="f238b-124">テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f238b-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="f238b-125">参照</span><span class="sxs-lookup"><span data-stu-id="f238b-125">See Also</span></span>

[<span data-ttu-id="f238b-126">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="f238b-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f238b-127">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f238b-127">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="f238b-128">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="f238b-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
