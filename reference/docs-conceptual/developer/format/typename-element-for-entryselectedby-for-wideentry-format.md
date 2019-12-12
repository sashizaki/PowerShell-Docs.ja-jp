---
title: WideEntry (Format) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81a91c74-6229-4b64-aa2b-9123e8b7e9e5
caps.latest.revision: 11
ms.openlocfilehash: be35f6e9e2ad0b2d9a21a91c053aa0f70cafaf9c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361621"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="c37e7-102">WideEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c37e7-102">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="c37e7-103">定義の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c37e7-103">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="c37e7-104">このオブジェクトが表示されるたびに、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c37e7-104">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="c37e7-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry の WideEntry (Format) TypeName 要素の要素 (形式)。形式</span><span class="sxs-lookup"><span data-stu-id="c37e7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c37e7-106">構文</span><span class="sxs-lookup"><span data-stu-id="c37e7-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c37e7-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c37e7-107">Attributes and Elements</span></span>

<span data-ttu-id="c37e7-108">次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c37e7-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c37e7-109">属性</span><span class="sxs-lookup"><span data-stu-id="c37e7-109">Attributes</span></span>

<span data-ttu-id="c37e7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c37e7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c37e7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c37e7-111">Child Elements</span></span>

<span data-ttu-id="c37e7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c37e7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c37e7-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c37e7-113">Parent Elements</span></span>

|<span data-ttu-id="c37e7-114">要素</span><span class="sxs-lookup"><span data-stu-id="c37e7-114">Element</span></span>|<span data-ttu-id="c37e7-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="c37e7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c37e7-116">WideEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c37e7-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="c37e7-117">このワイドエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c37e7-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c37e7-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c37e7-118">Text Value</span></span>

<span data-ttu-id="c37e7-119">`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c37e7-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c37e7-120">コメント</span><span class="sxs-lookup"><span data-stu-id="c37e7-120">Remarks</span></span>

<span data-ttu-id="c37e7-121">各ワイドエントリでは、1つまたは複数の .NET 型、選択セット、または定義を使用するために存在する必要がある選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c37e7-121">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="c37e7-122">ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c37e7-122">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c37e7-123">参照</span><span class="sxs-lookup"><span data-stu-id="c37e7-123">See Also</span></span>

[<span data-ttu-id="c37e7-124">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="c37e7-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="c37e7-125">WideEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c37e7-125">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="c37e7-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="c37e7-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
