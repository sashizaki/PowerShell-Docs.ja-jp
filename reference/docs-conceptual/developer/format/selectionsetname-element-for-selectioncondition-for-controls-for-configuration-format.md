---
title: 構成用のコントロールの SelectionCondition の SelectionSetName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7dcaeadb-4e79-47a0-96e2-8952af26abbe
caps.latest.revision: 7
ms.openlocfilehash: 5db35a8094ea2bb966c8d6a96802c72f64c05c17
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368281"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="92a08-102">Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92a08-102">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="92a08-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a08-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="92a08-104">このセット内のいずれかの型が存在する場合、条件が満たされ、このコントロールを使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92a08-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="92a08-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="92a08-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="92a08-106">Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの構成 (形式) のコントロール要素の構成 (書式設定) 要素Configuration (Format) CustomEntry 要素の CustomControl のためのコントロールのための構成 (形式) のためのコントロールのための Entryselectedby の configuration (format) SelectionCondition 要素に対するコントロール用の EntrySelectedBy 要素構成 (形式) のコントロールの SelectionCondition の構成 (形式) SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="92a08-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92a08-107">構文</span><span class="sxs-lookup"><span data-stu-id="92a08-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92a08-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="92a08-108">Attributes and Elements</span></span>

<span data-ttu-id="92a08-109">次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="92a08-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92a08-110">属性</span><span class="sxs-lookup"><span data-stu-id="92a08-110">Attributes</span></span>

<span data-ttu-id="92a08-111">なし。</span><span class="sxs-lookup"><span data-stu-id="92a08-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92a08-112">子要素</span><span class="sxs-lookup"><span data-stu-id="92a08-112">Child Elements</span></span>

<span data-ttu-id="92a08-113">なし。</span><span class="sxs-lookup"><span data-stu-id="92a08-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92a08-114">親要素</span><span class="sxs-lookup"><span data-stu-id="92a08-114">Parent Elements</span></span>

|<span data-ttu-id="92a08-115">要素</span><span class="sxs-lookup"><span data-stu-id="92a08-115">Element</span></span>|<span data-ttu-id="92a08-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="92a08-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92a08-117">構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="92a08-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="92a08-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="92a08-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92a08-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="92a08-119">Text Value</span></span>

<span data-ttu-id="92a08-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a08-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="92a08-121">コメント</span><span class="sxs-lookup"><span data-stu-id="92a08-121">Remarks</span></span>

<span data-ttu-id="92a08-122">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="92a08-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="92a08-123">選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a08-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="92a08-124">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="92a08-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="92a08-125">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a08-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92a08-126">参照</span><span class="sxs-lookup"><span data-stu-id="92a08-126">See Also</span></span>

[<span data-ttu-id="92a08-127">構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="92a08-127">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="92a08-128">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="92a08-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="92a08-129">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="92a08-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="92a08-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="92a08-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
