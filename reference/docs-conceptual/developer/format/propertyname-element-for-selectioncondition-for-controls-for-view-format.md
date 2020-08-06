---
title: ビューのコントロールの SelectionCondition の PropertyName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 251fc129896cfa4a6255330e23854b014675ac5f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780816"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="e8657-102">View の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e8657-102">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="e8657-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8657-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="e8657-104">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、エントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8657-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="e8657-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8657-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e8657-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (形式) コントロールのコントロール要素 (format) のコントロールの要素 (書式) を制御するためのコントロールの要素 (書式) の CustomControl 要素 (format) のコントロールの CustomControl のカスタム CustomEntries ビュー (format) のためのコントロールの CustomEntries の参照 (書式) の参照 (形式) の SelectionCondition 要素を表示するためのコントロールのための項目を指定します。ビュー (形式) のコントロールのビュー (Format) の PropertyName 要素を表示するには、コントロールを対象にします。</span><span class="sxs-lookup"><span data-stu-id="e8657-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8657-107">構文</span><span class="sxs-lookup"><span data-stu-id="e8657-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8657-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e8657-108">Attributes and Elements</span></span>

<span data-ttu-id="e8657-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="e8657-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8657-110">属性</span><span class="sxs-lookup"><span data-stu-id="e8657-110">Attributes</span></span>

<span data-ttu-id="e8657-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e8657-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8657-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e8657-112">Child Elements</span></span>

<span data-ttu-id="e8657-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e8657-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8657-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e8657-114">Parent Elements</span></span>

|<span data-ttu-id="e8657-115">要素</span><span class="sxs-lookup"><span data-stu-id="e8657-115">Element</span></span>|<span data-ttu-id="e8657-116">説明</span><span class="sxs-lookup"><span data-stu-id="e8657-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8657-117">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e8657-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="e8657-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e8657-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e8657-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e8657-119">Text Value</span></span>

<span data-ttu-id="e8657-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8657-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8657-121">解説</span><span class="sxs-lookup"><span data-stu-id="e8657-121">Remarks</span></span>

<span data-ttu-id="e8657-122">選択条件には、少なくとも1つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8657-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="e8657-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8657-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8657-124">参照</span><span class="sxs-lookup"><span data-stu-id="e8657-124">See Also</span></span>

[<span data-ttu-id="e8657-125">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e8657-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="e8657-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e8657-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
