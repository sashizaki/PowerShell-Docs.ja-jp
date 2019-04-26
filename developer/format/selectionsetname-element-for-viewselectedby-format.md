---
title: ViewSelectedBy (形式) の要素を SelectionSetName |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ab0f033-df09-4435-a8bd-76ec2d01f13b
caps.latest.revision: 13
ms.openlocfilehash: d1de2b30860bac80bf17508f40eec33c2794c4b2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076227"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="b1267-102">ViewSelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b1267-102">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="b1267-103">ビューが表示されている .NET オブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1267-103">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="b1267-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ViewSelectedBy 要素 (形式) SelectionSetName 要素を ViewSelectedBy (形式)</span><span class="sxs-lookup"><span data-stu-id="b1267-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b1267-105">構文</span><span class="sxs-lookup"><span data-stu-id="b1267-105">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1267-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b1267-106">Attributes and Elements</span></span>

<span data-ttu-id="b1267-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="b1267-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b1267-108">属性</span><span class="sxs-lookup"><span data-stu-id="b1267-108">Attributes</span></span>

<span data-ttu-id="b1267-109">なし。</span><span class="sxs-lookup"><span data-stu-id="b1267-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b1267-110">子要素</span><span class="sxs-lookup"><span data-stu-id="b1267-110">Child Elements</span></span>

<span data-ttu-id="b1267-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b1267-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b1267-112">親要素</span><span class="sxs-lookup"><span data-stu-id="b1267-112">Parent Elements</span></span>

|<span data-ttu-id="b1267-113">要素</span><span class="sxs-lookup"><span data-stu-id="b1267-113">Element</span></span>|<span data-ttu-id="b1267-114">説明</span><span class="sxs-lookup"><span data-stu-id="b1267-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1267-115">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b1267-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="b1267-116">ビューが表示されている .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1267-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b1267-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b1267-117">Text Value</span></span>

<span data-ttu-id="b1267-118">定義されている選択セットの名前を指定、`Name`選択セットの要素。</span><span class="sxs-lookup"><span data-stu-id="b1267-118">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1267-119">コメント</span><span class="sxs-lookup"><span data-stu-id="b1267-119">Remarks</span></span>

<span data-ttu-id="b1267-120">継承によって関連付けられているオブジェクトのセットなどの 1 つの名前を使用して参照する関連のオブジェクトのセットがある場合は、選択範囲のセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1267-120">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="b1267-121">定義と参照セットの選択の詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1267-121">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="b1267-122">例</span><span class="sxs-lookup"><span data-stu-id="b1267-122">Example</span></span>

<span data-ttu-id="b1267-123">次の例では、選択のリスト ビューのセットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b1267-123">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="b1267-124">テーブルの幅をカスタム ビューに同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1267-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="b1267-125">参照</span><span class="sxs-lookup"><span data-stu-id="b1267-125">See Also</span></span>

[<span data-ttu-id="b1267-126">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1267-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b1267-127">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b1267-127">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="b1267-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="b1267-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
