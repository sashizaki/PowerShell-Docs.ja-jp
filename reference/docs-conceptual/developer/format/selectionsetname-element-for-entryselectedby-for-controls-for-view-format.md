---
title: ビュー (Format) のコントロールに対する EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b594a064-746f-4900-99e4-7be7bf5aa5a2
caps.latest.revision: 7
ms.openlocfilehash: d540c99707f4e0796b2d408f2161a9208257ab32
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368351"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="53d5c-102">View の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="53d5c-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="53d5c-103">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="53d5c-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="53d5c-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="53d5c-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="53d5c-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビュー用のコントロール用の CustomControl (format) CustomEntry 要素のコントロール用の CustomEntries のコントロールのためのコントロールのためのコントロールのためのコントロールのためのコントロールのためのコントロールのためのコントロールのための Entryselectedby の SelectionSetName 要素を表示するためのコントロール (形式</span><span class="sxs-lookup"><span data-stu-id="53d5c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="53d5c-106">構文</span><span class="sxs-lookup"><span data-stu-id="53d5c-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="53d5c-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="53d5c-107">Attributes and Elements</span></span>

<span data-ttu-id="53d5c-108">次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="53d5c-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="53d5c-109">属性</span><span class="sxs-lookup"><span data-stu-id="53d5c-109">Attributes</span></span>

<span data-ttu-id="53d5c-110">None</span><span class="sxs-lookup"><span data-stu-id="53d5c-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="53d5c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="53d5c-111">Child Elements</span></span>

<span data-ttu-id="53d5c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="53d5c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="53d5c-113">親要素</span><span class="sxs-lookup"><span data-stu-id="53d5c-113">Parent Elements</span></span>

|<span data-ttu-id="53d5c-114">要素</span><span class="sxs-lookup"><span data-stu-id="53d5c-114">Element</span></span>|<span data-ttu-id="53d5c-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="53d5c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="53d5c-116">ビューのコントロールに対する CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="53d5c-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="53d5c-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="53d5c-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="53d5c-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="53d5c-118">Text Value</span></span>

<span data-ttu-id="53d5c-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="53d5c-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="53d5c-120">コメント</span><span class="sxs-lookup"><span data-stu-id="53d5c-120">Remarks</span></span>

<span data-ttu-id="53d5c-121">各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="53d5c-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="53d5c-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="53d5c-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="53d5c-123">選択セットの定義の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d5c-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="53d5c-124">参照</span><span class="sxs-lookup"><span data-stu-id="53d5c-124">See Also</span></span>

[<span data-ttu-id="53d5c-125">ビューのコントロールに対する CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="53d5c-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="53d5c-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="53d5c-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
