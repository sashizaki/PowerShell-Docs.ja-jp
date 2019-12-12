---
title: WideEntry (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13a429c-a31b-4e29-828c-c0c0917b5415
caps.latest.revision: 11
ms.openlocfilehash: baea89e4b259611dfa45b6bcf94fa0bf2df6b9de
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368411"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="f6473-102">WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f6473-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="f6473-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="f6473-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="f6473-104">このセット内のいずれかの型が存在する場合、条件が満たされ、このワイドビューの定義を使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6473-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="f6473-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) SelectionCondition 要素の (Format) 項目の EntrySelectedBy 要素WideEntry (format) の EntrySelectedBy for WideEntry (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="f6473-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f6473-106">構文</span><span class="sxs-lookup"><span data-stu-id="f6473-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f6473-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f6473-107">Attributes and Elements</span></span>

<span data-ttu-id="f6473-108">次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6473-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f6473-109">属性</span><span class="sxs-lookup"><span data-stu-id="f6473-109">Attributes</span></span>

<span data-ttu-id="f6473-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f6473-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f6473-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f6473-111">Child Elements</span></span>

<span data-ttu-id="f6473-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f6473-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f6473-113">親要素</span><span class="sxs-lookup"><span data-stu-id="f6473-113">Parent Elements</span></span>

|<span data-ttu-id="f6473-114">要素</span><span class="sxs-lookup"><span data-stu-id="f6473-114">Element</span></span>|<span data-ttu-id="f6473-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="f6473-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f6473-116">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f6473-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="f6473-117">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f6473-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f6473-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f6473-118">Text Value</span></span>

<span data-ttu-id="f6473-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6473-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6473-120">コメント</span><span class="sxs-lookup"><span data-stu-id="f6473-120">Remarks</span></span>

<span data-ttu-id="f6473-121">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6473-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="f6473-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6473-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f6473-123">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="f6473-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="f6473-124">選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6473-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="f6473-125">ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6473-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6473-126">参照</span><span class="sxs-lookup"><span data-stu-id="f6473-126">See Also</span></span>

[<span data-ttu-id="f6473-127">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="f6473-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f6473-128">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="f6473-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f6473-129">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="f6473-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f6473-130">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f6473-130">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f6473-131">WideEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="f6473-131">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f6473-132">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="f6473-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
