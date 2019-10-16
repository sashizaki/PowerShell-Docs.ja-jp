---
title: ビューのコントロール (Format) の ItemSelectionCondition の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4191157-bf01-4831-b221-6f8cc581cd53
caps.latest.revision: 6
ms.openlocfilehash: 0cbefbb48427b56d4ae2a5ae27c7726dcfad7b84
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364921"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="95cb2-102">View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="95cb2-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="95cb2-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="95cb2-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="95cb2-104">このスクリプトが `true` に評価されると、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="95cb2-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="95cb2-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="95cb2-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="95cb2-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (形式) のコントロールに対する Customentries のビュー (形式) 式のバインド要素のビュー (形式) の Customentries 要素のコントロールの CustomEntries に対して、ビュー (形式) 用に設定します。ビューのコントロール (Format) の ItemSelectionCondition のビュー (Format) ScriptBlock 要素の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="95cb2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="95cb2-107">構文</span><span class="sxs-lookup"><span data-stu-id="95cb2-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="95cb2-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="95cb2-108">Attributes and Elements</span></span>

<span data-ttu-id="95cb2-109">次のセクションでは、属性、子要素、`ScriptBlock` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="95cb2-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="95cb2-110">属性</span><span class="sxs-lookup"><span data-stu-id="95cb2-110">Attributes</span></span>

<span data-ttu-id="95cb2-111">なし。</span><span class="sxs-lookup"><span data-stu-id="95cb2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="95cb2-112">子要素</span><span class="sxs-lookup"><span data-stu-id="95cb2-112">Child Elements</span></span>

<span data-ttu-id="95cb2-113">なし。</span><span class="sxs-lookup"><span data-stu-id="95cb2-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="95cb2-114">親要素</span><span class="sxs-lookup"><span data-stu-id="95cb2-114">Parent Elements</span></span>

|<span data-ttu-id="95cb2-115">要素</span><span class="sxs-lookup"><span data-stu-id="95cb2-115">Element</span></span>|<span data-ttu-id="95cb2-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="95cb2-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="95cb2-117">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="95cb2-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="95cb2-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="95cb2-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="95cb2-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="95cb2-119">Text Value</span></span>

<span data-ttu-id="95cb2-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="95cb2-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="95cb2-121">コメント</span><span class="sxs-lookup"><span data-stu-id="95cb2-121">Remarks</span></span>

<span data-ttu-id="95cb2-122">この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="95cb2-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="95cb2-123">参照</span><span class="sxs-lookup"><span data-stu-id="95cb2-123">See Also</span></span>

[<span data-ttu-id="95cb2-124">ビューのコントロール (Format) の ItemSelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="95cb2-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="95cb2-125">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="95cb2-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="95cb2-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="95cb2-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
