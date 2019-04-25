---
title: ScriptBlock 要素のビュー (形式) のカスタム コントロールの ItemSelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 946cd2b5-ac37-4a13-bb49-29fbc70ec8d7
caps.latest.revision: 6
ms.openlocfilehash: 0c07ab0e5d04c4056a7e7215bfa55773bfccb41d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064477"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="ad621-102">View の CustomControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ad621-102">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="ad621-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad621-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="ad621-104">このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad621-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="ad621-105">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad621-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="ad621-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem の ItemSelectionCondition のビュー (形式) スクリプト ブロックの要素のカスタム コントロールの式バインディングのビュー (形式) ItemSelectionCondition 要素のカスタム コントロール用のビュー (形式) ExpressionBinding 要素カスタム コントロールのビュー (形式)</span><span class="sxs-lookup"><span data-stu-id="ad621-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ad621-107">構文</span><span class="sxs-lookup"><span data-stu-id="ad621-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ad621-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ad621-108">Attributes and Elements</span></span>

<span data-ttu-id="ad621-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="ad621-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ad621-110">属性</span><span class="sxs-lookup"><span data-stu-id="ad621-110">Attributes</span></span>

<span data-ttu-id="ad621-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ad621-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ad621-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ad621-112">Child Elements</span></span>

<span data-ttu-id="ad621-113">なし。</span><span class="sxs-lookup"><span data-stu-id="ad621-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ad621-114">親要素</span><span class="sxs-lookup"><span data-stu-id="ad621-114">Parent Elements</span></span>

|<span data-ttu-id="ad621-115">要素</span><span class="sxs-lookup"><span data-stu-id="ad621-115">Element</span></span>|<span data-ttu-id="ad621-116">説明</span><span class="sxs-lookup"><span data-stu-id="ad621-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad621-117">カスタム コントロールの表示 (形式) の式バインディングの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ad621-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="ad621-118">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad621-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ad621-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ad621-119">Text Value</span></span>

<span data-ttu-id="ad621-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad621-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad621-121">コメント</span><span class="sxs-lookup"><span data-stu-id="ad621-121">Remarks</span></span>

<span data-ttu-id="ad621-122">指定できないかどうかは、この要素が使用される、 [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素の選択条件を定義するときにします。</span><span class="sxs-lookup"><span data-stu-id="ad621-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad621-123">参照</span><span class="sxs-lookup"><span data-stu-id="ad621-123">See Also</span></span>

[<span data-ttu-id="ad621-124">ビュー (形式) のカスタム コントロールの ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="ad621-124">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ad621-125">カスタム コントロールの表示 (形式) の式バインディングの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ad621-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="ad621-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="ad621-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
