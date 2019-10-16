---
title: View (Format) の CustomControl の ItemSelectionCondition の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 946cd2b5-ac37-4a13-bb49-29fbc70ec8d7
caps.latest.revision: 6
ms.openlocfilehash: 0c07ab0e5d04c4056a7e7215bfa55773bfccb41d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362071"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="ed9ac-102">View の CustomControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ed9ac-102">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="ed9ac-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed9ac-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="ed9ac-104">このスクリプトが `true` に評価されると、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed9ac-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="ed9ac-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed9ac-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="ed9ac-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomControl for view (format) の式のバインド要素に対して、CustomControl for View (format) 要素のバインドのバインド要素を指定します。 ItemSelectionCondition の場合、この要素は、ビューの CustomControl (形式)</span><span class="sxs-lookup"><span data-stu-id="ed9ac-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ed9ac-107">構文</span><span class="sxs-lookup"><span data-stu-id="ed9ac-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ed9ac-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ed9ac-108">Attributes and Elements</span></span>

<span data-ttu-id="ed9ac-109">次のセクションでは、属性、子要素、`ScriptBlock` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed9ac-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ed9ac-110">属性</span><span class="sxs-lookup"><span data-stu-id="ed9ac-110">Attributes</span></span>

<span data-ttu-id="ed9ac-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ed9ac-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ed9ac-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ed9ac-112">Child Elements</span></span>

<span data-ttu-id="ed9ac-113">なし。</span><span class="sxs-lookup"><span data-stu-id="ed9ac-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ed9ac-114">親要素</span><span class="sxs-lookup"><span data-stu-id="ed9ac-114">Parent Elements</span></span>

|<span data-ttu-id="ed9ac-115">要素</span><span class="sxs-lookup"><span data-stu-id="ed9ac-115">Element</span></span>|<span data-ttu-id="ed9ac-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="ed9ac-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ed9ac-117">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ed9ac-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="ed9ac-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ed9ac-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ed9ac-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ed9ac-119">Text Value</span></span>

<span data-ttu-id="ed9ac-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed9ac-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed9ac-121">コメント</span><span class="sxs-lookup"><span data-stu-id="ed9ac-121">Remarks</span></span>

<span data-ttu-id="ed9ac-122">この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed9ac-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed9ac-123">参照</span><span class="sxs-lookup"><span data-stu-id="ed9ac-123">See Also</span></span>

[<span data-ttu-id="ed9ac-124">CustomControl for ビュー (Format) の ItemSelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="ed9ac-124">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ed9ac-125">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ed9ac-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="ed9ac-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ed9ac-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
