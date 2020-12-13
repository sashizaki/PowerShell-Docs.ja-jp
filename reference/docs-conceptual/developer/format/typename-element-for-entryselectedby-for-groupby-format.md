---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の EntrySelectedBy の TypeName 要素 (書式)
description: GroupBy の EntrySelectedBy の TypeName 要素 (書式)
ms.openlocfilehash: 07cc92e9c501aa0eb2d219e416851be0fcd80f47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645703"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="6ec43-103">GroupBy の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ec43-103">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="6ec43-104">カスタムコントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ec43-104">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="6ec43-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ec43-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="6ec43-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素に対して、groupby (形式) の CustomEntries 要素の CustomControl の CustomControl の CustomEntry 要素を指定します。 groupby (format) の EntrySelectedBy を指定します。 groupby (形式)</span><span class="sxs-lookup"><span data-stu-id="6ec43-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6ec43-107">構文</span><span class="sxs-lookup"><span data-stu-id="6ec43-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ec43-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6ec43-108">Attributes and Elements</span></span>

<span data-ttu-id="6ec43-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="6ec43-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ec43-110">属性</span><span class="sxs-lookup"><span data-stu-id="6ec43-110">Attributes</span></span>

<span data-ttu-id="6ec43-111">なし。</span><span class="sxs-lookup"><span data-stu-id="6ec43-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6ec43-112">子要素</span><span class="sxs-lookup"><span data-stu-id="6ec43-112">Child Elements</span></span>

<span data-ttu-id="6ec43-113">なし。</span><span class="sxs-lookup"><span data-stu-id="6ec43-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6ec43-114">親要素</span><span class="sxs-lookup"><span data-stu-id="6ec43-114">Parent Elements</span></span>

|<span data-ttu-id="6ec43-115">要素</span><span class="sxs-lookup"><span data-stu-id="6ec43-115">Element</span></span>|<span data-ttu-id="6ec43-116">説明</span><span class="sxs-lookup"><span data-stu-id="6ec43-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ec43-117">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ec43-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="6ec43-118">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="6ec43-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6ec43-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="6ec43-119">Text Value</span></span>

<span data-ttu-id="6ec43-120">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="6ec43-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ec43-121">解説</span><span class="sxs-lookup"><span data-stu-id="6ec43-121">Remarks</span></span>

<span data-ttu-id="6ec43-122">各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ec43-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="6ec43-123">カスタムコントロールビューのコンポーネントの詳細については、「 [カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ec43-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ec43-124">参照</span><span class="sxs-lookup"><span data-stu-id="6ec43-124">See Also</span></span>

[<span data-ttu-id="6ec43-125">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="6ec43-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="6ec43-126">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ec43-126">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="6ec43-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="6ec43-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
