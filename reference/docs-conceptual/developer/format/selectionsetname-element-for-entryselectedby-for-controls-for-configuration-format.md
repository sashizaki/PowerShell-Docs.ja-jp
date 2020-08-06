---
title: 構成用のコントロール (Format) の EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 72072d8d13e6ca22afdb9bca2e0237d29ba0594f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787565"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="4b56a-102">Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4b56a-102">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4b56a-103">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b56a-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="4b56a-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b56a-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4b56a-105">Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの要素の構成 (形式) CustomControl の構成 (形式) の CustomEntries 要素の構成 (形式) CustoCustomControl 用の Mentry 要素は、構成 (format) のコントロールに対して EntrySelectedBy の Configuration (format) SelectionSetName 要素を構成するためのコントロール用の構成 (format) 要素を構成 (format) します。</span><span class="sxs-lookup"><span data-stu-id="4b56a-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4b56a-106">構文</span><span class="sxs-lookup"><span data-stu-id="4b56a-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="4b56a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4b56a-107">Attributes and Elements</span></span>

<span data-ttu-id="4b56a-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="4b56a-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4b56a-109">属性</span><span class="sxs-lookup"><span data-stu-id="4b56a-109">Attributes</span></span>

<span data-ttu-id="4b56a-110">なし</span><span class="sxs-lookup"><span data-stu-id="4b56a-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="4b56a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="4b56a-111">Child Elements</span></span>

<span data-ttu-id="4b56a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="4b56a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4b56a-113">親要素</span><span class="sxs-lookup"><span data-stu-id="4b56a-113">Parent Elements</span></span>

|<span data-ttu-id="4b56a-114">要素</span><span class="sxs-lookup"><span data-stu-id="4b56a-114">Element</span></span>|<span data-ttu-id="4b56a-115">説明</span><span class="sxs-lookup"><span data-stu-id="4b56a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b56a-116">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4b56a-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="4b56a-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4b56a-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4b56a-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="4b56a-118">Text Value</span></span>

<span data-ttu-id="4b56a-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b56a-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b56a-120">解説</span><span class="sxs-lookup"><span data-stu-id="4b56a-120">Remarks</span></span>

<span data-ttu-id="4b56a-121">各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b56a-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="4b56a-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="4b56a-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="4b56a-123">選択セットの定義の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b56a-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b56a-124">参照</span><span class="sxs-lookup"><span data-stu-id="4b56a-124">See Also</span></span>

[<span data-ttu-id="4b56a-125">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4b56a-125">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="4b56a-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4b56a-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
