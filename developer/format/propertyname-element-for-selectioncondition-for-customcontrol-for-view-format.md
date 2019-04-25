---
title: PropertyName 要素のビュー (形式) のカスタム コントロールの SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48a417-2083-46d4-ac38-16c12e65b6b9
caps.latest.revision: 7
ms.openlocfilehash: e08037d5d051d3be51e90193c7e87cc2e738f78a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064698"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="d6ba0-102">View の CustomControl の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d6ba0-102">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="d6ba0-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="d6ba0-104">このプロパティが存在するかを評価すると`true`条件が満たされ、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="d6ba0-105">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="d6ba0-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素の表示 (カスタム コントロールの CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールのビュー (形式) CustomEntries 要素CustomEntry CustomEntry EntrySelectedBy ビュー (形式) の PropertyName のカスタム コントロール用のビュー (形式) SelectionCondition 要素のカスタム コントロール用のビュー (形式) EntrySelectedBy 要素のカスタム コントロール用の形式) CustomItem 要素ビュー (形式) のカスタム コントロールの SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d6ba0-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d6ba0-107">構文</span><span class="sxs-lookup"><span data-stu-id="d6ba0-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d6ba0-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d6ba0-108">Attributes and Elements</span></span>

<span data-ttu-id="d6ba0-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d6ba0-110">属性</span><span class="sxs-lookup"><span data-stu-id="d6ba0-110">Attributes</span></span>

<span data-ttu-id="d6ba0-111">なし。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d6ba0-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d6ba0-112">Child Elements</span></span>

<span data-ttu-id="d6ba0-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d6ba0-114">親要素</span><span class="sxs-lookup"><span data-stu-id="d6ba0-114">Parent Elements</span></span>

|<span data-ttu-id="d6ba0-115">要素</span><span class="sxs-lookup"><span data-stu-id="d6ba0-115">Element</span></span>|<span data-ttu-id="d6ba0-116">説明</span><span class="sxs-lookup"><span data-stu-id="d6ba0-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d6ba0-117">ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d6ba0-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="d6ba0-118">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d6ba0-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d6ba0-119">Text Value</span></span>

<span data-ttu-id="d6ba0-120">.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6ba0-121">コメント</span><span class="sxs-lookup"><span data-stu-id="d6ba0-121">Remarks</span></span>

<span data-ttu-id="d6ba0-122">選択条件では、少なくとも 1 つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="d6ba0-123">選択条件を使用する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d6ba0-124">参照</span><span class="sxs-lookup"><span data-stu-id="d6ba0-124">See Also</span></span>

[<span data-ttu-id="d6ba0-125">ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d6ba0-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="d6ba0-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="d6ba0-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
