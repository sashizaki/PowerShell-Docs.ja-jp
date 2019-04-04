---
title: 構成 (形式) のコントロールの SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7dcaeadb-4e79-47a0-96e2-8952af26abbe
caps.latest.revision: 7
ms.openlocfilehash: 5db35a8094ea2bb966c8d6a96802c72f64c05c17
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858138"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="97d67-102">Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="97d67-102">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="97d67-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="97d67-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="97d67-104">このセット内の型のいずれかが存在して、条件が満たされると、このコントロールを使用して、オブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97d67-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="97d67-105">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="97d67-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="97d67-106">コントロールのコントロールのカスタム コントロールの構成 (形式) CustomEntries 要素の構成 (形式) のカスタム コントロール要素のコントロールの構成 (形式) のコントロール要素の構成要素 (形式) のコントロール要素CustomEntry controls for EntrySelectedBy の構成 (形式) SelectionCondition 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの構成 (形式) CustomEntry 要素構成 (形式) のコントロールの SelectionCondition の構成 (形式) SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="97d67-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="97d67-107">構文</span><span class="sxs-lookup"><span data-stu-id="97d67-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="97d67-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="97d67-108">Attributes and Elements</span></span>

<span data-ttu-id="97d67-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="97d67-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="97d67-110">属性</span><span class="sxs-lookup"><span data-stu-id="97d67-110">Attributes</span></span>

<span data-ttu-id="97d67-111">なし。</span><span class="sxs-lookup"><span data-stu-id="97d67-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="97d67-112">子要素</span><span class="sxs-lookup"><span data-stu-id="97d67-112">Child Elements</span></span>

<span data-ttu-id="97d67-113">なし。</span><span class="sxs-lookup"><span data-stu-id="97d67-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="97d67-114">親要素</span><span class="sxs-lookup"><span data-stu-id="97d67-114">Parent Elements</span></span>

|<span data-ttu-id="97d67-115">要素</span><span class="sxs-lookup"><span data-stu-id="97d67-115">Element</span></span>|<span data-ttu-id="97d67-116">説明</span><span class="sxs-lookup"><span data-stu-id="97d67-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97d67-117">構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="97d67-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="97d67-118">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="97d67-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="97d67-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="97d67-119">Text Value</span></span>

<span data-ttu-id="97d67-120">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="97d67-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="97d67-121">コメント</span><span class="sxs-lookup"><span data-stu-id="97d67-121">Remarks</span></span>

<span data-ttu-id="97d67-122">選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="97d67-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="97d67-123">作成と選択範囲のセットの参照の詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97d67-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="97d67-124">選択条件では、選択範囲のセットまたは .NET の型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="97d67-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="97d67-125">選択条件を使用する方法の詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97d67-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97d67-126">参照</span><span class="sxs-lookup"><span data-stu-id="97d67-126">See Also</span></span>

[<span data-ttu-id="97d67-127">構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="97d67-127">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="97d67-128">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="97d67-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="97d67-129">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="97d67-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="97d67-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="97d67-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
