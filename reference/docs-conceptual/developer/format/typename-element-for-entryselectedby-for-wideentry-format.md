---
ms.date: 09/13/2016
ms.topic: reference
title: WideEntry の EntrySelectedBy の TypeName 要素 (書式)
description: WideEntry の EntrySelectedBy の TypeName 要素 (書式)
ms.openlocfilehash: 2e0facd6ff7c6fec96dabf488449a8502429bcff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654795"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="dd34e-103">WideEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="dd34e-103">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="dd34e-104">定義の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd34e-104">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="dd34e-105">このオブジェクトが表示されるたびに、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd34e-105">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="dd34e-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry の WideEntry (Format) TypeName 要素の EntrySelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="dd34e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dd34e-107">構文</span><span class="sxs-lookup"><span data-stu-id="dd34e-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dd34e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dd34e-108">Attributes and Elements</span></span>

<span data-ttu-id="dd34e-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="dd34e-109">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dd34e-110">属性</span><span class="sxs-lookup"><span data-stu-id="dd34e-110">Attributes</span></span>

<span data-ttu-id="dd34e-111">なし。</span><span class="sxs-lookup"><span data-stu-id="dd34e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dd34e-112">子要素</span><span class="sxs-lookup"><span data-stu-id="dd34e-112">Child Elements</span></span>

<span data-ttu-id="dd34e-113">なし。</span><span class="sxs-lookup"><span data-stu-id="dd34e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dd34e-114">親要素</span><span class="sxs-lookup"><span data-stu-id="dd34e-114">Parent Elements</span></span>

|<span data-ttu-id="dd34e-115">要素</span><span class="sxs-lookup"><span data-stu-id="dd34e-115">Element</span></span>|<span data-ttu-id="dd34e-116">説明</span><span class="sxs-lookup"><span data-stu-id="dd34e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dd34e-117">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="dd34e-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="dd34e-118">このワイドエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="dd34e-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dd34e-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="dd34e-119">Text Value</span></span>

<span data-ttu-id="dd34e-120">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="dd34e-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd34e-121">解説</span><span class="sxs-lookup"><span data-stu-id="dd34e-121">Remarks</span></span>

<span data-ttu-id="dd34e-122">各ワイドエントリでは、1つまたは複数の .NET 型、選択セット、または定義を使用するために存在する必要がある選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd34e-122">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="dd34e-123">ワイドビューのその他のコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd34e-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd34e-124">参照</span><span class="sxs-lookup"><span data-stu-id="dd34e-124">See Also</span></span>

[<span data-ttu-id="dd34e-125">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="dd34e-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="dd34e-126">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="dd34e-126">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="dd34e-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="dd34e-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
