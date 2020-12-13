---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)
description: Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: 5e4368a9546307c5ff223ae42ecaa1d2872bc587
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665959"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="f5320-103">Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f5320-103">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f5320-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5320-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="f5320-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、エントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5320-105">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="f5320-106">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5320-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f5320-107">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (形式) CustomControl 要素の構成のためのコントロールの構成 (形式) の CustomEntries 要素の構成のためのコントロールの CustomControl の CustomControl の CustomEntry 要素の構成 (Format) CustomEntry 用の構成 (format) の SelectionCondition 要素の Configuration (format) の SelectionCondition 要素を指定します。 entryselectedby for ListEntry の SelectionCondition に対して、Configuration (format) PropertyName 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5320-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f5320-108">構文</span><span class="sxs-lookup"><span data-stu-id="f5320-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f5320-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f5320-109">Attributes and Elements</span></span>

<span data-ttu-id="f5320-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="f5320-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f5320-111">属性</span><span class="sxs-lookup"><span data-stu-id="f5320-111">Attributes</span></span>

<span data-ttu-id="f5320-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f5320-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f5320-113">子要素</span><span class="sxs-lookup"><span data-stu-id="f5320-113">Child Elements</span></span>

<span data-ttu-id="f5320-114">なし。</span><span class="sxs-lookup"><span data-stu-id="f5320-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f5320-115">親要素</span><span class="sxs-lookup"><span data-stu-id="f5320-115">Parent Elements</span></span>

|<span data-ttu-id="f5320-116">要素</span><span class="sxs-lookup"><span data-stu-id="f5320-116">Element</span></span>|<span data-ttu-id="f5320-117">説明</span><span class="sxs-lookup"><span data-stu-id="f5320-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f5320-118">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f5320-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="f5320-119">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f5320-119">Defines a condition that must exist for a common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f5320-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f5320-120">Text Value</span></span>

<span data-ttu-id="f5320-121">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5320-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5320-122">解説</span><span class="sxs-lookup"><span data-stu-id="f5320-122">Remarks</span></span>

<span data-ttu-id="f5320-123">選択条件には、少なくとも1つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5320-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="f5320-124">選択条件の使用方法の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5320-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f5320-125">参照</span><span class="sxs-lookup"><span data-stu-id="f5320-125">See Also</span></span>

[<span data-ttu-id="f5320-126">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f5320-126">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="f5320-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f5320-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
