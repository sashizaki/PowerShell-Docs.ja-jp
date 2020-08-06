---
title: 構成用のコントロール (Format) の ItemSeclectionCondition の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f44b1a7f059fa5f41c19eed93762b61eda5110e8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772894"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="ccd88-102">Configuration の Controls の ItemSeclectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ccd88-102">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="ccd88-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccd88-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="ccd88-104">このスクリプトがに評価されると、 `true` 条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccd88-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="ccd88-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccd88-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="ccd88-106">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (形式) の CustomControl 要素の構成のためのコントロールの要素の構成 (書式) の CustomControl の構成 (形式) の CustomEntries 要素の構成のためのコントロールの CustomControl のための構成 (形式) CustomEntry コントロールのための構成式のバインド要素の構成式のバインド要素の構成のためのコントロールの構成 (形式) ItemSelectionCondition 要素のコントロールに対するコントロールの構成 (format) ScriptBlock 要素の構成用のコントロールの ItemSelectionCondition の要素のバインドの構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="ccd88-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ccd88-107">構文</span><span class="sxs-lookup"><span data-stu-id="ccd88-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ccd88-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ccd88-108">Attributes and Elements</span></span>

<span data-ttu-id="ccd88-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="ccd88-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ccd88-110">属性</span><span class="sxs-lookup"><span data-stu-id="ccd88-110">Attributes</span></span>

<span data-ttu-id="ccd88-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ccd88-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ccd88-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ccd88-112">Child Elements</span></span>

<span data-ttu-id="ccd88-113">なし。</span><span class="sxs-lookup"><span data-stu-id="ccd88-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ccd88-114">親要素</span><span class="sxs-lookup"><span data-stu-id="ccd88-114">Parent Elements</span></span>

|<span data-ttu-id="ccd88-115">要素</span><span class="sxs-lookup"><span data-stu-id="ccd88-115">Element</span></span>|<span data-ttu-id="ccd88-116">説明</span><span class="sxs-lookup"><span data-stu-id="ccd88-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ccd88-117">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ccd88-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ccd88-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ccd88-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ccd88-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ccd88-119">Text Value</span></span>

<span data-ttu-id="ccd88-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccd88-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="ccd88-121">解説</span><span class="sxs-lookup"><span data-stu-id="ccd88-121">Remarks</span></span>

<span data-ttu-id="ccd88-122">この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ccd88-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccd88-123">参照</span><span class="sxs-lookup"><span data-stu-id="ccd88-123">See Also</span></span>

[<span data-ttu-id="ccd88-124">Configuration の Controls の ItemSeclectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ccd88-124">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="ccd88-125">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ccd88-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="ccd88-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ccd88-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
