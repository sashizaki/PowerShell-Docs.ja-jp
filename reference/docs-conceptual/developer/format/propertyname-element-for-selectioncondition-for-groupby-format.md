---
title: GroupBy (Format) の SelectionCondition の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1707317-6c26-4866-bcc1-8924103c9014
caps.latest.revision: 6
ms.openlocfilehash: 7241ea0ea364befa7ad4ab0af4c4209be72214a7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364951"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="2ea51-102">GroupBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2ea51-102">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="2ea51-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ea51-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="2ea51-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ea51-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="2ea51-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ea51-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2ea51-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl の Entryselectedby for groupby (format) Selectionselectedby 要素の Selectionselectedby を使用して、groupby (format) の selectioncondition に対して groupby (形式) の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2ea51-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2ea51-107">構文</span><span class="sxs-lookup"><span data-stu-id="2ea51-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2ea51-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2ea51-108">Attributes and Elements</span></span>

<span data-ttu-id="2ea51-109">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ea51-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2ea51-110">属性</span><span class="sxs-lookup"><span data-stu-id="2ea51-110">Attributes</span></span>

<span data-ttu-id="2ea51-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2ea51-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2ea51-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2ea51-112">Child Elements</span></span>

<span data-ttu-id="2ea51-113">なし。</span><span class="sxs-lookup"><span data-stu-id="2ea51-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2ea51-114">親要素</span><span class="sxs-lookup"><span data-stu-id="2ea51-114">Parent Elements</span></span>

|<span data-ttu-id="2ea51-115">要素</span><span class="sxs-lookup"><span data-stu-id="2ea51-115">Element</span></span>|<span data-ttu-id="2ea51-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="2ea51-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2ea51-117">GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2ea51-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="2ea51-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2ea51-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2ea51-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2ea51-119">Text Value</span></span>

<span data-ttu-id="2ea51-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ea51-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="2ea51-121">コメント</span><span class="sxs-lookup"><span data-stu-id="2ea51-121">Remarks</span></span>

<span data-ttu-id="2ea51-122">選択条件には、少なくとも1つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ea51-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="2ea51-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea51-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ea51-124">参照</span><span class="sxs-lookup"><span data-stu-id="2ea51-124">See Also</span></span>

[<span data-ttu-id="2ea51-125">GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2ea51-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="2ea51-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2ea51-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
