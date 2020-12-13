---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)
description: Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)
ms.openlocfilehash: b775aa8a3184aa3ebcbda17a8e3191c69d67a700
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645730"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="f8e64-103">Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8e64-103">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f8e64-104">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8e64-104">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="f8e64-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8e64-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f8e64-106">Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの要素の構成 (形式) CustomControl の構成 (形式) の CustomEntries 要素の構成 (形式) CustoCustomControl 用の Mentry 要素は、構成 (format) のコントロールに対して EntrySelectedBy の Configuration (format) SelectionSetName 要素を構成するためのコントロール用の構成 (format) 要素を構成 (format) します。</span><span class="sxs-lookup"><span data-stu-id="f8e64-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f8e64-107">構文</span><span class="sxs-lookup"><span data-stu-id="f8e64-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f8e64-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f8e64-108">Attributes and Elements</span></span>

<span data-ttu-id="f8e64-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="f8e64-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f8e64-110">属性</span><span class="sxs-lookup"><span data-stu-id="f8e64-110">Attributes</span></span>

<span data-ttu-id="f8e64-111">なし</span><span class="sxs-lookup"><span data-stu-id="f8e64-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="f8e64-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f8e64-112">Child Elements</span></span>

<span data-ttu-id="f8e64-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f8e64-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f8e64-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f8e64-114">Parent Elements</span></span>

|<span data-ttu-id="f8e64-115">要素</span><span class="sxs-lookup"><span data-stu-id="f8e64-115">Element</span></span>|<span data-ttu-id="f8e64-116">説明</span><span class="sxs-lookup"><span data-stu-id="f8e64-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8e64-117">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8e64-117">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="f8e64-118">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f8e64-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f8e64-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f8e64-119">Text Value</span></span>

<span data-ttu-id="f8e64-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8e64-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8e64-121">解説</span><span class="sxs-lookup"><span data-stu-id="f8e64-121">Remarks</span></span>

<span data-ttu-id="f8e64-122">各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8e64-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f8e64-123">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f8e64-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="f8e64-124">選択セットの定義の詳細については、「 [選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8e64-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8e64-125">参照</span><span class="sxs-lookup"><span data-stu-id="f8e64-125">See Also</span></span>

[<span data-ttu-id="f8e64-126">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8e64-126">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="f8e64-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f8e64-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
