---
title: ビュー (形式) のカスタム コントロールの SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52b05a9-762e-4f1c-ad57-9d1710149722
caps.latest.revision: 10
ms.openlocfilehash: 25d46665ca5df3ddf49af5718d513b84c77988c8
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862768"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="0d4db-102">View の CustomControl の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d4db-102">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="0d4db-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d4db-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="0d4db-104">このセット内の型のいずれかが存在するときに、条件が満たされ、このコントロールを使用して、オブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d4db-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="0d4db-105">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d4db-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="0d4db-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) EntrySelectedBy CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロール表示 (形式) CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="0d4db-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0d4db-107">構文</span><span class="sxs-lookup"><span data-stu-id="0d4db-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0d4db-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="0d4db-108">Attributes and Elements</span></span>

<span data-ttu-id="0d4db-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="0d4db-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0d4db-110">属性</span><span class="sxs-lookup"><span data-stu-id="0d4db-110">Attributes</span></span>

<span data-ttu-id="0d4db-111">なし。</span><span class="sxs-lookup"><span data-stu-id="0d4db-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0d4db-112">子要素</span><span class="sxs-lookup"><span data-stu-id="0d4db-112">Child Elements</span></span>

<span data-ttu-id="0d4db-113">なし。</span><span class="sxs-lookup"><span data-stu-id="0d4db-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0d4db-114">親要素</span><span class="sxs-lookup"><span data-stu-id="0d4db-114">Parent Elements</span></span>

|<span data-ttu-id="0d4db-115">要素</span><span class="sxs-lookup"><span data-stu-id="0d4db-115">Element</span></span>|<span data-ttu-id="0d4db-116">説明</span><span class="sxs-lookup"><span data-stu-id="0d4db-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0d4db-117">ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="0d4db-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="0d4db-118">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="0d4db-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0d4db-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="0d4db-119">Text Value</span></span>

<span data-ttu-id="0d4db-120">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d4db-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d4db-121">コメント</span><span class="sxs-lookup"><span data-stu-id="0d4db-121">Remarks</span></span>

<span data-ttu-id="0d4db-122">選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="0d4db-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="0d4db-123">作成と選択範囲のセットの参照の詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="0d4db-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="0d4db-124">選択条件では、選択範囲のセットまたは .NET の型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d4db-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="0d4db-125">選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="0d4db-125">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0d4db-126">参照</span><span class="sxs-lookup"><span data-stu-id="0d4db-126">See Also</span></span>

[<span data-ttu-id="0d4db-127">ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="0d4db-127">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="0d4db-128">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="0d4db-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0d4db-129">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="0d4db-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0d4db-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="0d4db-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
