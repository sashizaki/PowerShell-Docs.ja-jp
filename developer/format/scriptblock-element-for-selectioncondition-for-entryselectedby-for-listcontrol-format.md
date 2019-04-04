---
title: SelectionCondition EntrySelectedBy ListControl (形式) のためのスクリプト ブロックの要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: b65d953169f6daf15fb617ce4d0303cf4cb584ee
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057775"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="c0d47-102">ListControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0d47-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="c0d47-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0d47-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="c0d47-104">このスクリプトを評価するときに`true`条件が満たされ、一覧のエントリを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0d47-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="c0d47-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) EntrySelectedBy 要素の ListEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EntrySelectedBy ListEntry (形式) のためのスクリプト ブロック要素を ListEntry (形式)</span><span class="sxs-lookup"><span data-stu-id="c0d47-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c0d47-106">構文</span><span class="sxs-lookup"><span data-stu-id="c0d47-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c0d47-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c0d47-107">Attributes and Elements</span></span>

<span data-ttu-id="c0d47-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="c0d47-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c0d47-109">属性</span><span class="sxs-lookup"><span data-stu-id="c0d47-109">Attributes</span></span>

<span data-ttu-id="c0d47-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c0d47-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c0d47-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c0d47-111">Child Elements</span></span>

<span data-ttu-id="c0d47-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c0d47-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c0d47-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c0d47-113">Parent Elements</span></span>

|<span data-ttu-id="c0d47-114">要素</span><span class="sxs-lookup"><span data-stu-id="c0d47-114">Element</span></span>|<span data-ttu-id="c0d47-115">説明</span><span class="sxs-lookup"><span data-stu-id="c0d47-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c0d47-116">ListEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="c0d47-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="c0d47-117">このリストのエントリを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c0d47-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c0d47-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c0d47-118">Text Value</span></span>

<span data-ttu-id="c0d47-119">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0d47-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0d47-120">コメント</span><span class="sxs-lookup"><span data-stu-id="c0d47-120">Remarks</span></span>

<span data-ttu-id="c0d47-121">選択条件が少なくとも 1 つスクリプトまたはプロパティの名前を評価するために指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0d47-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="c0d47-122">(選択条件を使用する方法の詳細については、次を参照してください[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)。)。</span><span class="sxs-lookup"><span data-stu-id="c0d47-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="c0d47-123">リスト ビューの他のコンポーネントの詳細については、[リスト ビュー](./creating-a-list-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d47-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0d47-124">参照</span><span class="sxs-lookup"><span data-stu-id="c0d47-124">See Also</span></span>

[<span data-ttu-id="c0d47-125">ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c0d47-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="c0d47-126">SelectionCondition EntrySelectedBy ListEntry (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="c0d47-126">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="c0d47-127">ListEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="c0d47-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="c0d47-128">リスト ビュー</span><span class="sxs-lookup"><span data-stu-id="c0d47-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c0d47-129">ビューのエントリまたは項目を使用する場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="c0d47-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c0d47-130">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="c0d47-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
