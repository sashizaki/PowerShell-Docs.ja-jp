---
title: PropertyName 要素の構成 (形式) のコントロールの SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec048408-e1c6-41ef-b39b-72f4c2dcf2ac
caps.latest.revision: 6
ms.openlocfilehash: b4b2440fdb7171d09fdc16ac7cc4f25ed1a4bb78
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861028"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="52665-102">Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="52665-102">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="52665-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="52665-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="52665-104">このプロパティが存在するかを評価すると`true`条件が満たされ、エントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="52665-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="52665-105">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="52665-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="52665-106">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (CustomEntry の EntrySelectedBy の構成 (形式) SelectionCondition 要素のコントロールの CustomEntry の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素SelectionCondition EntrySelectedBy ListEntry (形式) のための format) PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="52665-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="52665-107">構文</span><span class="sxs-lookup"><span data-stu-id="52665-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="52665-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="52665-108">Attributes and Elements</span></span>

<span data-ttu-id="52665-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="52665-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="52665-110">属性</span><span class="sxs-lookup"><span data-stu-id="52665-110">Attributes</span></span>

<span data-ttu-id="52665-111">なし。</span><span class="sxs-lookup"><span data-stu-id="52665-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="52665-112">子要素</span><span class="sxs-lookup"><span data-stu-id="52665-112">Child Elements</span></span>

<span data-ttu-id="52665-113">なし。</span><span class="sxs-lookup"><span data-stu-id="52665-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="52665-114">親要素</span><span class="sxs-lookup"><span data-stu-id="52665-114">Parent Elements</span></span>

|<span data-ttu-id="52665-115">要素</span><span class="sxs-lookup"><span data-stu-id="52665-115">Element</span></span>|<span data-ttu-id="52665-116">説明</span><span class="sxs-lookup"><span data-stu-id="52665-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52665-117">構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="52665-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="52665-118">使用する一般的なコントロールの定義を満たす必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="52665-118">Defines a condition that must exist for a common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="52665-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="52665-119">Text Value</span></span>

<span data-ttu-id="52665-120">.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="52665-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="52665-121">コメント</span><span class="sxs-lookup"><span data-stu-id="52665-121">Remarks</span></span>

<span data-ttu-id="52665-122">選択条件では、少なくとも 1 つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="52665-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="52665-123">選択条件を使用する方法の詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52665-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52665-124">参照</span><span class="sxs-lookup"><span data-stu-id="52665-124">See Also</span></span>

[<span data-ttu-id="52665-125">構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="52665-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="52665-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="52665-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
