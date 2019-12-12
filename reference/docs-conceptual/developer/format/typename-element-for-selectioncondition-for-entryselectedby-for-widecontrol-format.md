---
title: WideControl (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d6d43fa-c900-4e2f-952d-deccd584236f
caps.latest.revision: 11
ms.openlocfilehash: 6142350e3843a5feddcb5cee8901bbfa607d8d4c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368061"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="3a542-102">WideControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3a542-102">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="3a542-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a542-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="3a542-104">この型が存在する場合は、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3a542-104">When this type is present, the definition is used.</span></span>

<span data-ttu-id="3a542-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) SelectionCondition 要素の (Format) 項目の EntrySelectedBy 要素Entryselectedby for WideEntry (Format) の SelectionCondition に対する EntrySelectedBy for WideEntry (Format) TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="3a542-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3a542-106">構文</span><span class="sxs-lookup"><span data-stu-id="3a542-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3a542-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3a542-107">Attributes and Elements</span></span>

<span data-ttu-id="3a542-108">次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a542-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3a542-109">属性</span><span class="sxs-lookup"><span data-stu-id="3a542-109">Attributes</span></span>

<span data-ttu-id="3a542-110">なし。</span><span class="sxs-lookup"><span data-stu-id="3a542-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3a542-111">子要素</span><span class="sxs-lookup"><span data-stu-id="3a542-111">Child Elements</span></span>

<span data-ttu-id="3a542-112">なし。</span><span class="sxs-lookup"><span data-stu-id="3a542-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3a542-113">親要素</span><span class="sxs-lookup"><span data-stu-id="3a542-113">Parent Elements</span></span>

|<span data-ttu-id="3a542-114">要素</span><span class="sxs-lookup"><span data-stu-id="3a542-114">Element</span></span>|<span data-ttu-id="3a542-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="3a542-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3a542-116">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="3a542-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="3a542-117">このワイドエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="3a542-117">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3a542-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="3a542-118">Text Value</span></span>

<span data-ttu-id="3a542-119">`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a542-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3a542-120">コメント</span><span class="sxs-lookup"><span data-stu-id="3a542-120">Remarks</span></span>

<span data-ttu-id="3a542-121">選択条件では、.NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a542-121">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="3a542-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a542-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="3a542-123">ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a542-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a542-124">参照</span><span class="sxs-lookup"><span data-stu-id="3a542-124">See Also</span></span>

[<span data-ttu-id="3a542-125">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="3a542-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="3a542-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="3a542-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="3a542-127">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="3a542-127">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="3a542-128">EntrySelectedBy for WideEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3a542-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="3a542-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="3a542-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
