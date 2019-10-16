---
title: View (Format) の CustomControl の SelectionCondition の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52b05a9-762e-4f1c-ad57-9d1710149722
caps.latest.revision: 10
ms.openlocfilehash: 25d46665ca5df3ddf49af5718d513b84c77988c8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368271"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="8f344-102">View の CustomControl の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f344-102">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="8f344-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f344-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="8f344-104">このセット内のいずれかの型が存在する場合、条件が満たされ、このコントロールを使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f344-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="8f344-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f344-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="8f344-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素の CustomControl for view (format) EntrySelectedBy 要素 for view (Format) EntrySelectedByCustomEntry for ビューの要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="8f344-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8f344-107">構文</span><span class="sxs-lookup"><span data-stu-id="8f344-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8f344-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="8f344-108">Attributes and Elements</span></span>

<span data-ttu-id="8f344-109">次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f344-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8f344-110">属性</span><span class="sxs-lookup"><span data-stu-id="8f344-110">Attributes</span></span>

<span data-ttu-id="8f344-111">なし。</span><span class="sxs-lookup"><span data-stu-id="8f344-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8f344-112">子要素</span><span class="sxs-lookup"><span data-stu-id="8f344-112">Child Elements</span></span>

<span data-ttu-id="8f344-113">なし。</span><span class="sxs-lookup"><span data-stu-id="8f344-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8f344-114">親要素</span><span class="sxs-lookup"><span data-stu-id="8f344-114">Parent Elements</span></span>

|<span data-ttu-id="8f344-115">要素</span><span class="sxs-lookup"><span data-stu-id="8f344-115">Element</span></span>|<span data-ttu-id="8f344-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="8f344-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f344-117">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="8f344-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="8f344-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f344-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8f344-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8f344-119">Text Value</span></span>

<span data-ttu-id="8f344-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f344-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f344-121">コメント</span><span class="sxs-lookup"><span data-stu-id="8f344-121">Remarks</span></span>

<span data-ttu-id="8f344-122">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="8f344-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="8f344-123">選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f344-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="8f344-124">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f344-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="8f344-125">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f344-125">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f344-126">参照</span><span class="sxs-lookup"><span data-stu-id="8f344-126">See Also</span></span>

[<span data-ttu-id="8f344-127">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="8f344-127">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="8f344-128">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="8f344-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8f344-129">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="8f344-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="8f344-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="8f344-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
