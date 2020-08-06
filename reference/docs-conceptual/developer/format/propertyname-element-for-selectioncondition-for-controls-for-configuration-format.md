---
title: 構成用のコントロールの SelectionCondition の PropertyName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7730951a840fcfcd8bf819fff5182049bd6b6c23
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773132"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="3658e-102">Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3658e-102">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="3658e-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="3658e-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="3658e-104">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、エントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3658e-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="3658e-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3658e-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="3658e-106">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (形式) CustomControl 要素の構成のためのコントロールの構成 (形式) の CustomEntries 要素の構成のためのコントロールの CustomControl の CustomControl の CustomEntry 要素の構成 (Format) CustomEntry 用の構成 (format) の SelectionCondition 要素の Configuration (format) の SelectionCondition 要素を指定します。 entryselectedby for ListEntry の SelectionCondition に対して、Configuration (format) PropertyName 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="3658e-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3658e-107">構文</span><span class="sxs-lookup"><span data-stu-id="3658e-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3658e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3658e-108">Attributes and Elements</span></span>

<span data-ttu-id="3658e-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="3658e-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3658e-110">属性</span><span class="sxs-lookup"><span data-stu-id="3658e-110">Attributes</span></span>

<span data-ttu-id="3658e-111">なし。</span><span class="sxs-lookup"><span data-stu-id="3658e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3658e-112">子要素</span><span class="sxs-lookup"><span data-stu-id="3658e-112">Child Elements</span></span>

<span data-ttu-id="3658e-113">なし。</span><span class="sxs-lookup"><span data-stu-id="3658e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3658e-114">親要素</span><span class="sxs-lookup"><span data-stu-id="3658e-114">Parent Elements</span></span>

|<span data-ttu-id="3658e-115">要素</span><span class="sxs-lookup"><span data-stu-id="3658e-115">Element</span></span>|<span data-ttu-id="3658e-116">説明</span><span class="sxs-lookup"><span data-stu-id="3658e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3658e-117">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3658e-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="3658e-118">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="3658e-118">Defines a condition that must exist for a common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3658e-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="3658e-119">Text Value</span></span>

<span data-ttu-id="3658e-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3658e-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="3658e-121">解説</span><span class="sxs-lookup"><span data-stu-id="3658e-121">Remarks</span></span>

<span data-ttu-id="3658e-122">選択条件には、少なくとも1つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3658e-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="3658e-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3658e-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3658e-124">参照</span><span class="sxs-lookup"><span data-stu-id="3658e-124">See Also</span></span>

[<span data-ttu-id="3658e-125">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3658e-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="3658e-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="3658e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
