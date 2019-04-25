---
title: コントロールが表示されます (形式) の SelectionCondition PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92c4237d-c2b2-4908-82ac-f36070f89d26
caps.latest.revision: 6
ms.openlocfilehash: 79859bed3d762948182e03babf71d4270278bae7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065021"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="a1190-102">View の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a1190-102">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="a1190-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1190-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="a1190-104">このプロパティが存在するかを評価すると`true`条件が満たされ、エントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a1190-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="a1190-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a1190-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a1190-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry EntrySelectedBy のビュー (コントロールのビュー (形式) SelectionCondition 要素のコントロールのビュー (形式) EntrySelectedBy 要素のコントロールのビュー (形式) CustomEntry 要素のコントロールのカスタム コントロールコントロールが表示されます (形式) の SelectionCondition の形式) PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="a1190-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a1190-107">構文</span><span class="sxs-lookup"><span data-stu-id="a1190-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a1190-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a1190-108">Attributes and Elements</span></span>

<span data-ttu-id="a1190-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="a1190-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a1190-110">属性</span><span class="sxs-lookup"><span data-stu-id="a1190-110">Attributes</span></span>

<span data-ttu-id="a1190-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a1190-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a1190-112">子要素</span><span class="sxs-lookup"><span data-stu-id="a1190-112">Child Elements</span></span>

<span data-ttu-id="a1190-113">なし。</span><span class="sxs-lookup"><span data-stu-id="a1190-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a1190-114">親要素</span><span class="sxs-lookup"><span data-stu-id="a1190-114">Parent Elements</span></span>

|<span data-ttu-id="a1190-115">要素</span><span class="sxs-lookup"><span data-stu-id="a1190-115">Element</span></span>|<span data-ttu-id="a1190-116">説明</span><span class="sxs-lookup"><span data-stu-id="a1190-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a1190-117">コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a1190-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a1190-118">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a1190-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a1190-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a1190-119">Text Value</span></span>

<span data-ttu-id="a1190-120">.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1190-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1190-121">コメント</span><span class="sxs-lookup"><span data-stu-id="a1190-121">Remarks</span></span>

<span data-ttu-id="a1190-122">選択条件では、少なくとも 1 つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a1190-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="a1190-123">選択条件を使用する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1190-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1190-124">参照</span><span class="sxs-lookup"><span data-stu-id="a1190-124">See Also</span></span>

[<span data-ttu-id="a1190-125">コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a1190-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="a1190-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="a1190-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
