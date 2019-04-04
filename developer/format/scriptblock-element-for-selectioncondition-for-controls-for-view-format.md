---
title: コントロールが表示されます (形式) の SelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08512496-5682-4539-ab56-0c5394ce1f01
caps.latest.revision: 6
ms.openlocfilehash: 0137886437f01518f396613c564517e7910e657a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861838"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="48b11-102">View の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="48b11-102">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="48b11-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="48b11-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="48b11-104">このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="48b11-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="48b11-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="48b11-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="48b11-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry EntrySelectedBy のビュー (コントロールのビュー (形式) SelectionCondition 要素のコントロールのビュー (形式) EntrySelectedBy 要素のコントロールのビュー (形式) CustomEntry 要素のコントロールのカスタム コントロールビュー (形式) のコントロールの SelectionCondition の ScriptBlock 要素の形式)</span><span class="sxs-lookup"><span data-stu-id="48b11-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="48b11-107">構文</span><span class="sxs-lookup"><span data-stu-id="48b11-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="48b11-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="48b11-108">Attributes and Elements</span></span>

<span data-ttu-id="48b11-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="48b11-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="48b11-110">属性</span><span class="sxs-lookup"><span data-stu-id="48b11-110">Attributes</span></span>

<span data-ttu-id="48b11-111">なし。</span><span class="sxs-lookup"><span data-stu-id="48b11-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="48b11-112">子要素</span><span class="sxs-lookup"><span data-stu-id="48b11-112">Child Elements</span></span>

<span data-ttu-id="48b11-113">なし。</span><span class="sxs-lookup"><span data-stu-id="48b11-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="48b11-114">親要素</span><span class="sxs-lookup"><span data-stu-id="48b11-114">Parent Elements</span></span>

|<span data-ttu-id="48b11-115">要素</span><span class="sxs-lookup"><span data-stu-id="48b11-115">Element</span></span>|<span data-ttu-id="48b11-116">説明</span><span class="sxs-lookup"><span data-stu-id="48b11-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48b11-117">コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="48b11-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="48b11-118">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="48b11-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="48b11-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="48b11-119">Text Value</span></span>

<span data-ttu-id="48b11-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="48b11-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="48b11-121">コメント</span><span class="sxs-lookup"><span data-stu-id="48b11-121">Remarks</span></span>

<span data-ttu-id="48b11-122">選択条件が少なくとも 1 つスクリプトまたはプロパティの名前を評価するために指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="48b11-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="48b11-123">選択条件を使用する方法の詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48b11-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="48b11-124">参照</span><span class="sxs-lookup"><span data-stu-id="48b11-124">See Also</span></span>

[<span data-ttu-id="48b11-125">コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="48b11-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="48b11-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="48b11-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
