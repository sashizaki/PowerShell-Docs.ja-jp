---
title: コントロールが表示されます (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b594a064-746f-4900-99e4-7be7bf5aa5a2
caps.latest.revision: 7
ms.openlocfilehash: d540c99707f4e0796b2d408f2161a9208257ab32
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860998"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="9de66-102">View の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9de66-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="9de66-103">このコントロールの定義を使用して .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="9de66-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="9de66-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9de66-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="9de66-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry EntrySelectedBy のビュー (コントロールのビュー (形式) SelectionSetName 要素のコントロールのビュー (形式) EntrySelectedBy 要素のコントロールのビュー (形式) CustomEntry 要素のコントロールのカスタム コントロール形式)</span><span class="sxs-lookup"><span data-stu-id="9de66-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9de66-106">構文</span><span class="sxs-lookup"><span data-stu-id="9de66-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="9de66-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="9de66-107">Attributes and Elements</span></span>

<span data-ttu-id="9de66-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="9de66-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9de66-109">属性</span><span class="sxs-lookup"><span data-stu-id="9de66-109">Attributes</span></span>

<span data-ttu-id="9de66-110">None</span><span class="sxs-lookup"><span data-stu-id="9de66-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="9de66-111">子要素</span><span class="sxs-lookup"><span data-stu-id="9de66-111">Child Elements</span></span>

<span data-ttu-id="9de66-112">なし。</span><span class="sxs-lookup"><span data-stu-id="9de66-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9de66-113">親要素</span><span class="sxs-lookup"><span data-stu-id="9de66-113">Parent Elements</span></span>

|<span data-ttu-id="9de66-114">要素</span><span class="sxs-lookup"><span data-stu-id="9de66-114">Element</span></span>|<span data-ttu-id="9de66-115">説明</span><span class="sxs-lookup"><span data-stu-id="9de66-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9de66-116">コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="9de66-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="9de66-117">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="9de66-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9de66-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="9de66-118">Text Value</span></span>

<span data-ttu-id="9de66-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9de66-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="9de66-120">コメント</span><span class="sxs-lookup"><span data-stu-id="9de66-120">Remarks</span></span>

<span data-ttu-id="9de66-121">少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている各コントロールの定義が必要です。</span><span class="sxs-lookup"><span data-stu-id="9de66-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="9de66-122">複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="9de66-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="9de66-123">選択範囲のセットを定義する詳細については、次を参照してください。[選択範囲の設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="9de66-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9de66-124">参照</span><span class="sxs-lookup"><span data-stu-id="9de66-124">See Also</span></span>

[<span data-ttu-id="9de66-125">コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="9de66-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="9de66-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="9de66-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
