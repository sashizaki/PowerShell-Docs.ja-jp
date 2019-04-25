---
title: EntrySelectedBy WideEntry (形式) 用の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81a91c74-6229-4b64-aa2b-9123e8b7e9e5
caps.latest.revision: 11
ms.openlocfilehash: be35f6e9e2ad0b2d9a21a91c053aa0f70cafaf9c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083928"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="f0eed-102">WideEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f0eed-102">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="f0eed-103">定義の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0eed-103">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="f0eed-104">このオブジェクトが表示されるたびに、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0eed-104">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="f0eed-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素 WideEntry (の TypeName 要素を WideEntry (形式)形式)</span><span class="sxs-lookup"><span data-stu-id="f0eed-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f0eed-106">構文</span><span class="sxs-lookup"><span data-stu-id="f0eed-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f0eed-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f0eed-107">Attributes and Elements</span></span>

<span data-ttu-id="f0eed-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="f0eed-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f0eed-109">属性</span><span class="sxs-lookup"><span data-stu-id="f0eed-109">Attributes</span></span>

<span data-ttu-id="f0eed-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f0eed-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f0eed-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f0eed-111">Child Elements</span></span>

<span data-ttu-id="f0eed-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f0eed-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f0eed-113">親要素</span><span class="sxs-lookup"><span data-stu-id="f0eed-113">Parent Elements</span></span>

|<span data-ttu-id="f0eed-114">要素</span><span class="sxs-lookup"><span data-stu-id="f0eed-114">Element</span></span>|<span data-ttu-id="f0eed-115">説明</span><span class="sxs-lookup"><span data-stu-id="f0eed-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f0eed-116">WideEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="f0eed-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="f0eed-117">このワイド エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="f0eed-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f0eed-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f0eed-118">Text Value</span></span>

<span data-ttu-id="f0eed-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="f0eed-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0eed-120">コメント</span><span class="sxs-lookup"><span data-stu-id="f0eed-120">Remarks</span></span>

<span data-ttu-id="f0eed-121">各ワイド エントリには、1 つまたは複数の .NET 型を選択し、セットまたは選択条件を使用する定義が存在する必要がありますを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0eed-121">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="f0eed-122">ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0eed-122">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0eed-123">参照</span><span class="sxs-lookup"><span data-stu-id="f0eed-123">See Also</span></span>

[<span data-ttu-id="f0eed-124">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0eed-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f0eed-125">WideEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="f0eed-125">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="f0eed-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="f0eed-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
