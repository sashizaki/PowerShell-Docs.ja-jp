---
title: GroupBy (形式) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e01344bd-ad69-4789-8e9f-2e79880c3a33
caps.latest.revision: 6
ms.openlocfilehash: cb79fb942111cee89c6b2abba75de4c494082b7e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853078"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="f52fe-102">GroupBy の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f52fe-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="f52fe-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f52fe-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="f52fe-104">このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="f52fe-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="f52fe-105">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f52fe-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f52fe-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の SelectionCondition の GroupBy (形式) ScriptBlock 要素 EntrySelectedBy の GroupBy (形式) SelectionCondition 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="f52fe-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f52fe-107">構文</span><span class="sxs-lookup"><span data-stu-id="f52fe-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f52fe-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f52fe-108">Attributes and Elements</span></span>

<span data-ttu-id="f52fe-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="f52fe-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f52fe-110">属性</span><span class="sxs-lookup"><span data-stu-id="f52fe-110">Attributes</span></span>

<span data-ttu-id="f52fe-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f52fe-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f52fe-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f52fe-112">Child Elements</span></span>

<span data-ttu-id="f52fe-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f52fe-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f52fe-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f52fe-114">Parent Elements</span></span>

|<span data-ttu-id="f52fe-115">要素</span><span class="sxs-lookup"><span data-stu-id="f52fe-115">Element</span></span>|<span data-ttu-id="f52fe-116">説明</span><span class="sxs-lookup"><span data-stu-id="f52fe-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f52fe-117">GroupBy (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f52fe-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="f52fe-118">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f52fe-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f52fe-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f52fe-119">Text Value</span></span>

<span data-ttu-id="f52fe-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f52fe-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f52fe-121">コメント</span><span class="sxs-lookup"><span data-stu-id="f52fe-121">Remarks</span></span>

<span data-ttu-id="f52fe-122">選択条件が少なくとも 1 つスクリプトまたはプロパティの名前を評価するために指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f52fe-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="f52fe-123">選択条件を使用する方法の詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f52fe-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f52fe-124">参照</span><span class="sxs-lookup"><span data-stu-id="f52fe-124">See Also</span></span>

[<span data-ttu-id="f52fe-125">GroupBy (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f52fe-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="f52fe-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="f52fe-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
