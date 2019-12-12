---
title: View (Format) の CustomControl の SelectionCondition の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48a417-2083-46d4-ac38-16c12e65b6b9
caps.latest.revision: 7
ms.openlocfilehash: e08037d5d051d3be51e90193c7e87cc2e738f78a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362351"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="88bf8-102">View の CustomControl の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="88bf8-102">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="88bf8-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="88bf8-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="88bf8-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="88bf8-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="88bf8-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="88bf8-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="88bf8-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素を表示するための CustomControl for ビュー (形式) の Custommentry 要素の CustomControl for View (Format) CustomEntry for CustomControl 用の CustomItem 要素を使用して、CustomEntry for CustomControl for view (format) Selectionselectedby for CustomControl for View (Format) PropertyName の EntrySelectedBy 要素を指定します。CustomControl for ビュー (Format) の SelectionCondition の要素</span><span class="sxs-lookup"><span data-stu-id="88bf8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="88bf8-107">構文</span><span class="sxs-lookup"><span data-stu-id="88bf8-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="88bf8-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="88bf8-108">Attributes and Elements</span></span>

<span data-ttu-id="88bf8-109">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="88bf8-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="88bf8-110">属性</span><span class="sxs-lookup"><span data-stu-id="88bf8-110">Attributes</span></span>

<span data-ttu-id="88bf8-111">なし。</span><span class="sxs-lookup"><span data-stu-id="88bf8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="88bf8-112">子要素</span><span class="sxs-lookup"><span data-stu-id="88bf8-112">Child Elements</span></span>

<span data-ttu-id="88bf8-113">なし。</span><span class="sxs-lookup"><span data-stu-id="88bf8-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="88bf8-114">親要素</span><span class="sxs-lookup"><span data-stu-id="88bf8-114">Parent Elements</span></span>

|<span data-ttu-id="88bf8-115">要素</span><span class="sxs-lookup"><span data-stu-id="88bf8-115">Element</span></span>|<span data-ttu-id="88bf8-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="88bf8-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88bf8-117">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="88bf8-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="88bf8-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="88bf8-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="88bf8-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="88bf8-119">Text Value</span></span>

<span data-ttu-id="88bf8-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="88bf8-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="88bf8-121">コメント</span><span class="sxs-lookup"><span data-stu-id="88bf8-121">Remarks</span></span>

<span data-ttu-id="88bf8-122">選択条件には、少なくとも1つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="88bf8-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="88bf8-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88bf8-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="88bf8-124">参照</span><span class="sxs-lookup"><span data-stu-id="88bf8-124">See Also</span></span>

[<span data-ttu-id="88bf8-125">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="88bf8-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="88bf8-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="88bf8-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
