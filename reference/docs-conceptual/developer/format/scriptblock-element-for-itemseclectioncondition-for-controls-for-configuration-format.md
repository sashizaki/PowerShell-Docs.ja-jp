---
title: 構成用のコントロール (Format) の ItemSeclectionCondition の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f7aec9-7b01-4370-84f4-1e58508a851f
caps.latest.revision: 6
ms.openlocfilehash: e92b2dfff07358132c480c47c34279e5365fe400
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362121"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="9ef98-102">Configuration の Controls の ItemSeclectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9ef98-102">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9ef98-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ef98-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="9ef98-104">このスクリプトが `true` に評価されると、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9ef98-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="9ef98-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9ef98-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="9ef98-106">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素を構成するためのコントロール用 CustomItem 要素の構成式のバインド要素 CustomItem の構成 (形式)構成のコントロール (Format) の ItemSelectionCondition の構成 (Format) ScriptBlock 要素の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="9ef98-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9ef98-107">構文</span><span class="sxs-lookup"><span data-stu-id="9ef98-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9ef98-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="9ef98-108">Attributes and Elements</span></span>

<span data-ttu-id="9ef98-109">次のセクションでは、属性、子要素、`ScriptBlock` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ef98-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9ef98-110">属性</span><span class="sxs-lookup"><span data-stu-id="9ef98-110">Attributes</span></span>

<span data-ttu-id="9ef98-111">なし。</span><span class="sxs-lookup"><span data-stu-id="9ef98-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9ef98-112">子要素</span><span class="sxs-lookup"><span data-stu-id="9ef98-112">Child Elements</span></span>

<span data-ttu-id="9ef98-113">なし。</span><span class="sxs-lookup"><span data-stu-id="9ef98-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9ef98-114">親要素</span><span class="sxs-lookup"><span data-stu-id="9ef98-114">Parent Elements</span></span>

|<span data-ttu-id="9ef98-115">要素</span><span class="sxs-lookup"><span data-stu-id="9ef98-115">Element</span></span>|<span data-ttu-id="9ef98-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="9ef98-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ef98-117">構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9ef98-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="9ef98-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="9ef98-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9ef98-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="9ef98-119">Text Value</span></span>

<span data-ttu-id="9ef98-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ef98-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ef98-121">コメント</span><span class="sxs-lookup"><span data-stu-id="9ef98-121">Remarks</span></span>

<span data-ttu-id="9ef98-122">この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ef98-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ef98-123">参照</span><span class="sxs-lookup"><span data-stu-id="9ef98-123">See Also</span></span>

[<span data-ttu-id="9ef98-124">ItemSeclectionCondition の PropertyName 要素 (構成用コントロール用) (形式)</span><span class="sxs-lookup"><span data-stu-id="9ef98-124">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="9ef98-125">構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9ef98-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="9ef98-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="9ef98-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
