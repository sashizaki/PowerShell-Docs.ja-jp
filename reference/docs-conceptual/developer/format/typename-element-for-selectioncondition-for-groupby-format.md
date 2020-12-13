---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の SelectionCondition の TypeName 要素 (書式)
description: GroupBy の SelectionCondition の TypeName 要素 (書式)
ms.openlocfilehash: 096d2355e113a7e44cc6ae31ea23efc3f01080a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664630"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="4cfec-103">GroupBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4cfec-103">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="4cfec-104">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cfec-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="4cfec-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4cfec-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="4cfec-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 groupby (format) の CustomControl の Entryselectedby for groupby (format) Selectionselectedby 要素の EntrySelectedBy 要素の Selectionselectedby groupby (形式) の selectioncondition に対する groupby (format) TypeName 要素の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4cfec-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4cfec-107">構文</span><span class="sxs-lookup"><span data-stu-id="4cfec-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="4cfec-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4cfec-108">Attributes and Elements</span></span>

<span data-ttu-id="4cfec-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="4cfec-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4cfec-110">属性</span><span class="sxs-lookup"><span data-stu-id="4cfec-110">Attributes</span></span>

<span data-ttu-id="4cfec-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4cfec-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4cfec-112">子要素</span><span class="sxs-lookup"><span data-stu-id="4cfec-112">Child Elements</span></span>

<span data-ttu-id="4cfec-113">なし。</span><span class="sxs-lookup"><span data-stu-id="4cfec-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4cfec-114">親要素</span><span class="sxs-lookup"><span data-stu-id="4cfec-114">Parent Elements</span></span>

|<span data-ttu-id="4cfec-115">要素</span><span class="sxs-lookup"><span data-stu-id="4cfec-115">Element</span></span>|<span data-ttu-id="4cfec-116">説明</span><span class="sxs-lookup"><span data-stu-id="4cfec-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4cfec-117">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4cfec-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="4cfec-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4cfec-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4cfec-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="4cfec-119">Text Value</span></span>

<span data-ttu-id="4cfec-120">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="4cfec-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cfec-121">解説</span><span class="sxs-lookup"><span data-stu-id="4cfec-121">Remarks</span></span>

<span data-ttu-id="4cfec-122">この要素が指定されている場合、要素を指定することはできません `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="4cfec-122">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="4cfec-123">選択条件の定義の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cfec-123">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cfec-124">参照</span><span class="sxs-lookup"><span data-stu-id="4cfec-124">See Also</span></span>

[<span data-ttu-id="4cfec-125">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4cfec-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="4cfec-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4cfec-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
