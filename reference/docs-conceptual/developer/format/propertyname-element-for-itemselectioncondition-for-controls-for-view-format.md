---
title: ビューのコントロール (Format) の ItemSelectionCondition の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba3955bc-f3a1-4ef6-86ac-80ffc133ad1b
caps.latest.revision: 6
ms.openlocfilehash: 28ad31be4be7be20f1f43ea1b69ad5d294de86f6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362481"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="23fcd-102">View の Controls の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="23fcd-102">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="23fcd-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="23fcd-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="23fcd-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="23fcd-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="23fcd-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="23fcd-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="23fcd-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (形式) のコントロールに対する Customentries のビュー (形式) 式のバインド要素のビュー (形式) の Customentries 要素のコントロールの CustomEntries に対して、ビュー (形式) 用に設定します。ビューのコントロール (Format) の ItemSelectionCondition のビュー (Format) PropertyName 要素の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="23fcd-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="23fcd-107">構文</span><span class="sxs-lookup"><span data-stu-id="23fcd-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="23fcd-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="23fcd-108">Attributes and Elements</span></span>

<span data-ttu-id="23fcd-109">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="23fcd-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="23fcd-110">属性</span><span class="sxs-lookup"><span data-stu-id="23fcd-110">Attributes</span></span>

<span data-ttu-id="23fcd-111">なし。</span><span class="sxs-lookup"><span data-stu-id="23fcd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="23fcd-112">子要素</span><span class="sxs-lookup"><span data-stu-id="23fcd-112">Child Elements</span></span>

<span data-ttu-id="23fcd-113">なし。</span><span class="sxs-lookup"><span data-stu-id="23fcd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="23fcd-114">親要素</span><span class="sxs-lookup"><span data-stu-id="23fcd-114">Parent Elements</span></span>

|<span data-ttu-id="23fcd-115">要素</span><span class="sxs-lookup"><span data-stu-id="23fcd-115">Element</span></span>|<span data-ttu-id="23fcd-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="23fcd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="23fcd-117">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="23fcd-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="23fcd-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="23fcd-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="23fcd-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="23fcd-119">Text Value</span></span>

<span data-ttu-id="23fcd-120">条件をトリガーする .NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="23fcd-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="23fcd-121">コメント</span><span class="sxs-lookup"><span data-stu-id="23fcd-121">Remarks</span></span>

<span data-ttu-id="23fcd-122">この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="23fcd-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="23fcd-123">参照</span><span class="sxs-lookup"><span data-stu-id="23fcd-123">See Also</span></span>

[<span data-ttu-id="23fcd-124">ビューのコントロール (Format) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="23fcd-124">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="23fcd-125">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="23fcd-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="23fcd-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="23fcd-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
