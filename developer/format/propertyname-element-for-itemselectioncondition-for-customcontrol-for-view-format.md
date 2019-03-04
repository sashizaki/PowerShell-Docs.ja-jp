---
title: PropertyName 要素のビュー (形式) のカスタム コントロールの ItemSelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b12006-8d52-486b-91a3-e6224ca80e56
caps.latest.revision: 6
ms.openlocfilehash: 52d0b0816eaef6752220e0c3b1249e5a0e44a3ee
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854788"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="5f22b-102">View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5f22b-102">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="5f22b-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f22b-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="5f22b-104">このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f22b-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="5f22b-105">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f22b-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="5f22b-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem の ItemSelectionCondition のビュー (形式) PropertyName 要素のカスタム コントロールの式バインディングのビュー (形式) ItemSelectionCondition 要素のカスタム コントロール用のビュー (形式) ExpressionBinding 要素ビュー (形式のカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="5f22b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>

## <a name="syntax"></a><span data-ttu-id="5f22b-107">構文</span><span class="sxs-lookup"><span data-stu-id="5f22b-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5f22b-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5f22b-108">Attributes and Elements</span></span>

<span data-ttu-id="5f22b-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="5f22b-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5f22b-110">属性</span><span class="sxs-lookup"><span data-stu-id="5f22b-110">Attributes</span></span>

<span data-ttu-id="5f22b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5f22b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5f22b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5f22b-112">Child Elements</span></span>

<span data-ttu-id="5f22b-113">なし。</span><span class="sxs-lookup"><span data-stu-id="5f22b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5f22b-114">親要素</span><span class="sxs-lookup"><span data-stu-id="5f22b-114">Parent Elements</span></span>

|<span data-ttu-id="5f22b-115">要素</span><span class="sxs-lookup"><span data-stu-id="5f22b-115">Element</span></span>|<span data-ttu-id="5f22b-116">説明</span><span class="sxs-lookup"><span data-stu-id="5f22b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5f22b-117">カスタム コントロールの表示 (形式) の式バインディングの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5f22b-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="5f22b-118">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="5f22b-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5f22b-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5f22b-119">Text Value</span></span>

<span data-ttu-id="5f22b-120">条件をトリガーする、.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f22b-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f22b-121">コメント</span><span class="sxs-lookup"><span data-stu-id="5f22b-121">Remarks</span></span>

<span data-ttu-id="5f22b-122">指定できないかどうかは、この要素が使用される、 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素の選択条件を定義するときにします。</span><span class="sxs-lookup"><span data-stu-id="5f22b-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f22b-123">参照</span><span class="sxs-lookup"><span data-stu-id="5f22b-123">See Also</span></span>

[<span data-ttu-id="5f22b-124">ビュー (形式) のカスタム コントロールの ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="5f22b-124">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5f22b-125">カスタム コントロールの表示 (形式) の式バインディングの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5f22b-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="5f22b-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="5f22b-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
