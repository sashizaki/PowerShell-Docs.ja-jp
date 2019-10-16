---
title: View (Format) の CustomControl の ItemSelectionCondition の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b12006-8d52-486b-91a3-e6224ca80e56
caps.latest.revision: 6
ms.openlocfilehash: 52d0b0816eaef6752220e0c3b1249e5a0e44a3ee
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362441"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="3077d-102">View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3077d-102">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="3077d-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="3077d-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="3077d-104">このプロパティが存在する場合、または `true` と評価された場合、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3077d-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="3077d-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3077d-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="3077d-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomControl for view (format) 式のバインド要素の CustomControl for view (format) の PropertyName Selectioncondition 要素に対する、ItemSelectionCondition の参照 (format) 項目バインドのバインド要素ビューの CustomControl (形式)</span><span class="sxs-lookup"><span data-stu-id="3077d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>

## <a name="syntax"></a><span data-ttu-id="3077d-107">構文</span><span class="sxs-lookup"><span data-stu-id="3077d-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3077d-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3077d-108">Attributes and Elements</span></span>

<span data-ttu-id="3077d-109">次のセクションでは、属性、子要素、`PropertyName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3077d-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3077d-110">属性</span><span class="sxs-lookup"><span data-stu-id="3077d-110">Attributes</span></span>

<span data-ttu-id="3077d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="3077d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3077d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="3077d-112">Child Elements</span></span>

<span data-ttu-id="3077d-113">なし。</span><span class="sxs-lookup"><span data-stu-id="3077d-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3077d-114">親要素</span><span class="sxs-lookup"><span data-stu-id="3077d-114">Parent Elements</span></span>

|<span data-ttu-id="3077d-115">要素</span><span class="sxs-lookup"><span data-stu-id="3077d-115">Element</span></span>|<span data-ttu-id="3077d-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="3077d-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3077d-117">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="3077d-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="3077d-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="3077d-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3077d-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="3077d-119">Text Value</span></span>

<span data-ttu-id="3077d-120">条件をトリガーする .NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3077d-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="3077d-121">コメント</span><span class="sxs-lookup"><span data-stu-id="3077d-121">Remarks</span></span>

<span data-ttu-id="3077d-122">この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3077d-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="3077d-123">参照</span><span class="sxs-lookup"><span data-stu-id="3077d-123">See Also</span></span>

[<span data-ttu-id="3077d-124">CustomControl for ビュー (Format) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="3077d-124">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3077d-125">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="3077d-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="3077d-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="3077d-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
