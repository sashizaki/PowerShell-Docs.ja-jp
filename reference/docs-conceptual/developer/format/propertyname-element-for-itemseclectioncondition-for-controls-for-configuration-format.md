---
title: 構成用のコントロール (Format) の ItemSeclectionCondition の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8ab181-c559-492e-a0cf-299e381fdcc3
caps.latest.revision: 6
ms.openlocfilehash: ce25789bdfc2679372ca9e42f99dcc6a30ae2def
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362531"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="ac018-102">Configuration の Controls の ItemSeclectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac018-102">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="ac018-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac018-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="ac018-104">このプロパティが存在する場合、または `true` と評価された場合、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac018-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="ac018-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac018-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="ac018-106">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素を構成するためのコントロール用 CustomItem 要素の構成式のバインド要素 CustomItem の構成 (形式)構成用のコントロール (形式) の ItemSeclectionCondition の構成 (Format) PropertyName 要素の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ac018-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ac018-107">構文</span><span class="sxs-lookup"><span data-stu-id="ac018-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ac018-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ac018-108">Attributes and Elements</span></span>

<span data-ttu-id="ac018-109">次のセクションでは、属性、子要素、`PropertyName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac018-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ac018-110">属性</span><span class="sxs-lookup"><span data-stu-id="ac018-110">Attributes</span></span>

<span data-ttu-id="ac018-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ac018-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ac018-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ac018-112">Child Elements</span></span>

<span data-ttu-id="ac018-113">なし。</span><span class="sxs-lookup"><span data-stu-id="ac018-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ac018-114">親要素</span><span class="sxs-lookup"><span data-stu-id="ac018-114">Parent Elements</span></span>

|<span data-ttu-id="ac018-115">要素</span><span class="sxs-lookup"><span data-stu-id="ac018-115">Element</span></span>|<span data-ttu-id="ac018-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="ac018-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ac018-117">構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ac018-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ac018-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac018-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ac018-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ac018-119">Text Value</span></span>

<span data-ttu-id="ac018-120">条件をトリガーする .NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac018-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac018-121">コメント</span><span class="sxs-lookup"><span data-stu-id="ac018-121">Remarks</span></span>

<span data-ttu-id="ac018-122">この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac018-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac018-123">参照</span><span class="sxs-lookup"><span data-stu-id="ac018-123">See Also</span></span>

[<span data-ttu-id="ac018-124">ItemSeclectionCondition の ScriptBlock 要素 (構成用コントロール用) (形式)</span><span class="sxs-lookup"><span data-stu-id="ac018-124">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="ac018-125">構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ac018-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="ac018-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ac018-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
