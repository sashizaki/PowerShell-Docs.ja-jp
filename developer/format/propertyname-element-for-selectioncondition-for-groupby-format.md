---
title: GroupBy (形式) の SelectionCondition PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1707317-6c26-4866-bcc1-8924103c9014
caps.latest.revision: 6
ms.openlocfilehash: 7241ea0ea364befa7ad4ab0af4c4209be72214a7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064817"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="65a90-102">GroupBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65a90-102">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="65a90-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="65a90-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="65a90-104">このプロパティが存在するかを評価すると`true`条件が満たされ、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="65a90-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="65a90-105">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="65a90-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="65a90-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の SelectionCondition の GroupBy (形式) PropertyName 要素 EntrySelectedBy の GroupBy (形式) SelectionCondition 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="65a90-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="65a90-107">構文</span><span class="sxs-lookup"><span data-stu-id="65a90-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="65a90-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="65a90-108">Attributes and Elements</span></span>

<span data-ttu-id="65a90-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="65a90-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="65a90-110">属性</span><span class="sxs-lookup"><span data-stu-id="65a90-110">Attributes</span></span>

<span data-ttu-id="65a90-111">なし。</span><span class="sxs-lookup"><span data-stu-id="65a90-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="65a90-112">子要素</span><span class="sxs-lookup"><span data-stu-id="65a90-112">Child Elements</span></span>

<span data-ttu-id="65a90-113">なし。</span><span class="sxs-lookup"><span data-stu-id="65a90-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="65a90-114">親要素</span><span class="sxs-lookup"><span data-stu-id="65a90-114">Parent Elements</span></span>

|<span data-ttu-id="65a90-115">要素</span><span class="sxs-lookup"><span data-stu-id="65a90-115">Element</span></span>|<span data-ttu-id="65a90-116">説明</span><span class="sxs-lookup"><span data-stu-id="65a90-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65a90-117">GroupBy (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="65a90-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="65a90-118">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="65a90-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="65a90-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="65a90-119">Text Value</span></span>

<span data-ttu-id="65a90-120">.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="65a90-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="65a90-121">コメント</span><span class="sxs-lookup"><span data-stu-id="65a90-121">Remarks</span></span>

<span data-ttu-id="65a90-122">選択条件では、少なくとも 1 つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="65a90-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="65a90-123">選択条件を使用する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="65a90-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="65a90-124">参照</span><span class="sxs-lookup"><span data-stu-id="65a90-124">See Also</span></span>

[<span data-ttu-id="65a90-125">GroupBy (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="65a90-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="65a90-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="65a90-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
