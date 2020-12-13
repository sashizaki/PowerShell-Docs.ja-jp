---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomEntry の EntrySelectedBy の TypeName 要素 (書式)
description: View の CustomEntry の EntrySelectedBy の TypeName 要素 (書式)
ms.openlocfilehash: 72bb88bccc2bbd62f7ed160b820cf9169cb69341
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645750"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="e4b70-103">View の CustomEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4b70-103">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="e4b70-104">カスタムコントロールビューのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4b70-104">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="e4b70-105">定義に指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="e4b70-105">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="e4b70-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) CustomControl 要素 (形式) の CustomEntries for view (format) CustomControl for view (format) を使用して、customentry for ビューの entryselectedby 要素を指定します。この要素は、customentry for View 用の EntrySelectedBy の TypeName 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4b70-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e4b70-107">構文</span><span class="sxs-lookup"><span data-stu-id="e4b70-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e4b70-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e4b70-108">Attributes and Elements</span></span>

<span data-ttu-id="e4b70-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="e4b70-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e4b70-110">属性</span><span class="sxs-lookup"><span data-stu-id="e4b70-110">Attributes</span></span>

<span data-ttu-id="e4b70-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e4b70-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e4b70-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e4b70-112">Child Elements</span></span>

<span data-ttu-id="e4b70-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e4b70-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e4b70-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e4b70-114">Parent Elements</span></span>

|<span data-ttu-id="e4b70-115">要素</span><span class="sxs-lookup"><span data-stu-id="e4b70-115">Element</span></span>|<span data-ttu-id="e4b70-116">説明</span><span class="sxs-lookup"><span data-stu-id="e4b70-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e4b70-117">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e4b70-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="e4b70-118">このカスタムコントロールビュー定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e4b70-118">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e4b70-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e4b70-119">Text Value</span></span>

<span data-ttu-id="e4b70-120">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="e4b70-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4b70-121">解説</span><span class="sxs-lookup"><span data-stu-id="e4b70-121">Remarks</span></span>

<span data-ttu-id="e4b70-122">各カスタムコントロールビュー定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b70-122">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e4b70-123">カスタムコントロールビューのコンポーネントの詳細については、「 [カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b70-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4b70-124">参照</span><span class="sxs-lookup"><span data-stu-id="e4b70-124">See Also</span></span>

[<span data-ttu-id="e4b70-125">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="e4b70-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="e4b70-126">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e4b70-126">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e4b70-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e4b70-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
