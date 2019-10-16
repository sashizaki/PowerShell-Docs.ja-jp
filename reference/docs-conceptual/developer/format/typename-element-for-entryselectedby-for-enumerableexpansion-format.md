---
title: 列挙型拡張に対する EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0506928-db92-4ec4-855f-6f3592a383ae
caps.latest.revision: 6
ms.openlocfilehash: 5ead806d956ebbef95eeffc42bb39ef784208017
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361751"
---
# <a name="typename-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="ed771-102">EnumerableExpansion の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ed771-102">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="ed771-103">この定義によって展開される .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed771-103">Specifies a .NET type that is expanded by this definition.</span></span> <span data-ttu-id="ed771-104">この要素は、既定の設定を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed771-104">This element is used when defining a default settings.</span></span>

<span data-ttu-id="ed771-105">Configuration 要素 (Format) DefaultSettings 要素 (format) 列挙型拡張要素 (format) 列挙型拡張要素 (format) の EntrySelectedBy に対する Entryselectedby の TypeName 要素の EntrySelectedBy 要素列挙 Able展開 (形式)</span><span class="sxs-lookup"><span data-stu-id="ed771-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ed771-106">構文</span><span class="sxs-lookup"><span data-stu-id="ed771-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="ed771-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ed771-107">Attributes and Elements</span></span>

<span data-ttu-id="ed771-108">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed771-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ed771-109">属性</span><span class="sxs-lookup"><span data-stu-id="ed771-109">Attributes</span></span>

<span data-ttu-id="ed771-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ed771-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ed771-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ed771-111">Child Elements</span></span>

<span data-ttu-id="ed771-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ed771-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ed771-113">親要素</span><span class="sxs-lookup"><span data-stu-id="ed771-113">Parent Elements</span></span>

|<span data-ttu-id="ed771-114">要素</span><span class="sxs-lookup"><span data-stu-id="ed771-114">Element</span></span>|<span data-ttu-id="ed771-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="ed771-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ed771-116">列挙 Able展開 (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="ed771-116">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="ed771-117">この定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ed771-117">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ed771-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ed771-118">Text Value</span></span>

<span data-ttu-id="ed771-119">.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed771-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed771-120">コメント</span><span class="sxs-lookup"><span data-stu-id="ed771-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="ed771-121">参照</span><span class="sxs-lookup"><span data-stu-id="ed771-121">See Also</span></span>

[<span data-ttu-id="ed771-122">列挙 Able展開 (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="ed771-122">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="ed771-123">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ed771-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
