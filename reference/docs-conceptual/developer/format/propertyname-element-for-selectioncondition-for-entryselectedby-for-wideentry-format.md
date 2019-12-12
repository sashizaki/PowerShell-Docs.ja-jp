---
title: WideEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340abb12-6df1-42f4-bdae-b0509c90952c
caps.latest.revision: 11
ms.openlocfilehash: 196877b97db9ed0592e357486c1318dc1e7efd31
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362241"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="592b0-102">WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="592b0-102">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="592b0-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="592b0-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="592b0-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="592b0-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="592b0-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) SelectionCondition 要素の (Format) 項目の EntrySelectedBy 要素Entryselectedby for WideEntry (Format) PropertyName Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="592b0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="592b0-106">構文</span><span class="sxs-lookup"><span data-stu-id="592b0-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="592b0-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="592b0-107">Attributes and Elements</span></span>

<span data-ttu-id="592b0-108">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="592b0-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="592b0-109">属性</span><span class="sxs-lookup"><span data-stu-id="592b0-109">Attributes</span></span>

<span data-ttu-id="592b0-110">なし。</span><span class="sxs-lookup"><span data-stu-id="592b0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="592b0-111">子要素</span><span class="sxs-lookup"><span data-stu-id="592b0-111">Child Elements</span></span>

<span data-ttu-id="592b0-112">なし。</span><span class="sxs-lookup"><span data-stu-id="592b0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="592b0-113">親要素</span><span class="sxs-lookup"><span data-stu-id="592b0-113">Parent Elements</span></span>

|<span data-ttu-id="592b0-114">要素</span><span class="sxs-lookup"><span data-stu-id="592b0-114">Element</span></span>|<span data-ttu-id="592b0-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="592b0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="592b0-116">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="592b0-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="592b0-117">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="592b0-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="592b0-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="592b0-118">Text Value</span></span>

<span data-ttu-id="592b0-119">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="592b0-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="592b0-120">コメント</span><span class="sxs-lookup"><span data-stu-id="592b0-120">Remarks</span></span>

<span data-ttu-id="592b0-121">選択条件では、少なくとも1つのプロパティ名または評価対象のスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="592b0-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="592b0-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="592b0-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="592b0-123">ワイドビューのその他のコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="592b0-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="592b0-124">参照</span><span class="sxs-lookup"><span data-stu-id="592b0-124">See Also</span></span>

[<span data-ttu-id="592b0-125">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="592b0-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="592b0-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="592b0-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="592b0-127">WideEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="592b0-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="592b0-128">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="592b0-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="592b0-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="592b0-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
