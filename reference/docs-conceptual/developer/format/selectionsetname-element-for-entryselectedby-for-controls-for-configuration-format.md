---
title: 構成用のコントロール (Format) の EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42143d1e-7cda-4c4a-b568-fa1951bb9417
caps.latest.revision: 6
ms.openlocfilehash: 9060ee54d6f88c7f910b16cf5c9b87f37844b736
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364791"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="d9fb8-102">Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d9fb8-102">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="d9fb8-103">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d9fb8-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="d9fb8-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9fb8-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="d9fb8-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素Format) CustomControl 用の CustomEntry 要素を構成するためのコントロール用の customentry 要素の構成 (形式) を構成するために、EntrySelectedBy の configuration (format) SelectionSetName 要素を構成するためのコントロール (形式)</span><span class="sxs-lookup"><span data-stu-id="d9fb8-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d9fb8-106">構文</span><span class="sxs-lookup"><span data-stu-id="d9fb8-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d9fb8-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d9fb8-107">Attributes and Elements</span></span>

<span data-ttu-id="d9fb8-108">次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9fb8-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d9fb8-109">属性</span><span class="sxs-lookup"><span data-stu-id="d9fb8-109">Attributes</span></span>

<span data-ttu-id="d9fb8-110">None</span><span class="sxs-lookup"><span data-stu-id="d9fb8-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="d9fb8-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d9fb8-111">Child Elements</span></span>

<span data-ttu-id="d9fb8-112">なし。</span><span class="sxs-lookup"><span data-stu-id="d9fb8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d9fb8-113">親要素</span><span class="sxs-lookup"><span data-stu-id="d9fb8-113">Parent Elements</span></span>

|<span data-ttu-id="d9fb8-114">要素</span><span class="sxs-lookup"><span data-stu-id="d9fb8-114">Element</span></span>|<span data-ttu-id="d9fb8-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="d9fb8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9fb8-116">Configuration 用のコントロール用の CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d9fb8-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="d9fb8-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d9fb8-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d9fb8-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d9fb8-118">Text Value</span></span>

<span data-ttu-id="d9fb8-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9fb8-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9fb8-120">コメント</span><span class="sxs-lookup"><span data-stu-id="d9fb8-120">Remarks</span></span>

<span data-ttu-id="d9fb8-121">各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9fb8-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="d9fb8-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d9fb8-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="d9fb8-123">選択セットの定義の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9fb8-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9fb8-124">参照</span><span class="sxs-lookup"><span data-stu-id="d9fb8-124">See Also</span></span>

[<span data-ttu-id="d9fb8-125">Configuration 用のコントロール用の CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d9fb8-125">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="d9fb8-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="d9fb8-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
