---
title: GroupBy (Format) の SelectionCondition の PropertyName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8ada9a8ca7fbfdba5b2fea1881b2670c56a71d4f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773081"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="15df1-102">GroupBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15df1-102">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="15df1-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="15df1-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="15df1-104">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15df1-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="15df1-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="15df1-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="15df1-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 groupby (format) の CustomControl の Entryselectedby for groupby (format) Selectionselectedby 要素について、groupby (format) の selectioncondition 要素に対して groupby (形式) の SelectionCondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="15df1-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15df1-107">構文</span><span class="sxs-lookup"><span data-stu-id="15df1-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="15df1-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="15df1-108">Attributes and Elements</span></span>

<span data-ttu-id="15df1-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="15df1-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="15df1-110">属性</span><span class="sxs-lookup"><span data-stu-id="15df1-110">Attributes</span></span>

<span data-ttu-id="15df1-111">なし。</span><span class="sxs-lookup"><span data-stu-id="15df1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15df1-112">子要素</span><span class="sxs-lookup"><span data-stu-id="15df1-112">Child Elements</span></span>

<span data-ttu-id="15df1-113">なし。</span><span class="sxs-lookup"><span data-stu-id="15df1-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="15df1-114">親要素</span><span class="sxs-lookup"><span data-stu-id="15df1-114">Parent Elements</span></span>

|<span data-ttu-id="15df1-115">要素</span><span class="sxs-lookup"><span data-stu-id="15df1-115">Element</span></span>|<span data-ttu-id="15df1-116">説明</span><span class="sxs-lookup"><span data-stu-id="15df1-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15df1-117">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15df1-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="15df1-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="15df1-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="15df1-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="15df1-119">Text Value</span></span>

<span data-ttu-id="15df1-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="15df1-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="15df1-121">解説</span><span class="sxs-lookup"><span data-stu-id="15df1-121">Remarks</span></span>

<span data-ttu-id="15df1-122">選択条件には、少なくとも1つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="15df1-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="15df1-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15df1-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15df1-124">参照</span><span class="sxs-lookup"><span data-stu-id="15df1-124">See Also</span></span>

[<span data-ttu-id="15df1-125">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15df1-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="15df1-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="15df1-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
