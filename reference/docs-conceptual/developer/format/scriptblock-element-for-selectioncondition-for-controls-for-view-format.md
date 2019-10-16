---
title: ビューのコントロールの SelectionCondition の ScriptBlock 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08512496-5682-4539-ab56-0c5394ce1f01
caps.latest.revision: 6
ms.openlocfilehash: 0137886437f01518f396613c564517e7910e657a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364801"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="23aab-102">View の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="23aab-102">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="23aab-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="23aab-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="23aab-104">このスクリプトが `true` に評価されると、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="23aab-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="23aab-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="23aab-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="23aab-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビュー用のコントロールの CustomControl (書式) の CustomEntry 要素のコントロール用のカスタムエントリのためのコントロールのためのコントロールのためのコントロールのためのコントロールのための、ビューのコントロールの EntrySelectedBy の SelectionCondition 要素を表示するためのコントロール (Format) ビューのコントロール (Format) の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="23aab-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="23aab-107">構文</span><span class="sxs-lookup"><span data-stu-id="23aab-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="23aab-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="23aab-108">Attributes and Elements</span></span>

<span data-ttu-id="23aab-109">次のセクションでは、属性、子要素、`ScriptBlock` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="23aab-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="23aab-110">属性</span><span class="sxs-lookup"><span data-stu-id="23aab-110">Attributes</span></span>

<span data-ttu-id="23aab-111">なし。</span><span class="sxs-lookup"><span data-stu-id="23aab-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="23aab-112">子要素</span><span class="sxs-lookup"><span data-stu-id="23aab-112">Child Elements</span></span>

<span data-ttu-id="23aab-113">なし。</span><span class="sxs-lookup"><span data-stu-id="23aab-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="23aab-114">親要素</span><span class="sxs-lookup"><span data-stu-id="23aab-114">Parent Elements</span></span>

|<span data-ttu-id="23aab-115">要素</span><span class="sxs-lookup"><span data-stu-id="23aab-115">Element</span></span>|<span data-ttu-id="23aab-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="23aab-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="23aab-117">ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="23aab-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="23aab-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="23aab-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="23aab-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="23aab-119">Text Value</span></span>

<span data-ttu-id="23aab-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="23aab-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="23aab-121">コメント</span><span class="sxs-lookup"><span data-stu-id="23aab-121">Remarks</span></span>

<span data-ttu-id="23aab-122">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="23aab-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="23aab-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23aab-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="23aab-124">参照</span><span class="sxs-lookup"><span data-stu-id="23aab-124">See Also</span></span>

[<span data-ttu-id="23aab-125">ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="23aab-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="23aab-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="23aab-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
