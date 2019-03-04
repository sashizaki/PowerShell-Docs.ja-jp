---
title: 構成 (形式) のコントロールの EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42143d1e-7cda-4c4a-b568-fa1951bb9417
caps.latest.revision: 6
ms.openlocfilehash: 9060ee54d6f88c7f910b16cf5c9b87f37844b736
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860908"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="00c79-102">Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="00c79-102">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="00c79-103">このコントロールの定義を使用して .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="00c79-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="00c79-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="00c79-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="00c79-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素CustomEntry EntrySelectedBy の構成 (形式) のコントロールの構成 (形式) SelectionSetName 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="00c79-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="00c79-106">構文</span><span class="sxs-lookup"><span data-stu-id="00c79-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="00c79-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="00c79-107">Attributes and Elements</span></span>

<span data-ttu-id="00c79-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="00c79-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="00c79-109">属性</span><span class="sxs-lookup"><span data-stu-id="00c79-109">Attributes</span></span>

<span data-ttu-id="00c79-110">None</span><span class="sxs-lookup"><span data-stu-id="00c79-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="00c79-111">子要素</span><span class="sxs-lookup"><span data-stu-id="00c79-111">Child Elements</span></span>

<span data-ttu-id="00c79-112">なし。</span><span class="sxs-lookup"><span data-stu-id="00c79-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="00c79-113">親要素</span><span class="sxs-lookup"><span data-stu-id="00c79-113">Parent Elements</span></span>

|<span data-ttu-id="00c79-114">要素</span><span class="sxs-lookup"><span data-stu-id="00c79-114">Element</span></span>|<span data-ttu-id="00c79-115">説明</span><span class="sxs-lookup"><span data-stu-id="00c79-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="00c79-116">構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="00c79-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="00c79-117">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="00c79-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="00c79-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="00c79-118">Text Value</span></span>

<span data-ttu-id="00c79-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="00c79-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="00c79-120">コメント</span><span class="sxs-lookup"><span data-stu-id="00c79-120">Remarks</span></span>

<span data-ttu-id="00c79-121">少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている各コントロールの定義が必要です。</span><span class="sxs-lookup"><span data-stu-id="00c79-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="00c79-122">複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="00c79-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="00c79-123">選択範囲のセットを定義する詳細については、次を参照してください。[選択範囲の設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="00c79-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="00c79-124">参照</span><span class="sxs-lookup"><span data-stu-id="00c79-124">See Also</span></span>

[<span data-ttu-id="00c79-125">構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="00c79-125">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="00c79-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="00c79-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
