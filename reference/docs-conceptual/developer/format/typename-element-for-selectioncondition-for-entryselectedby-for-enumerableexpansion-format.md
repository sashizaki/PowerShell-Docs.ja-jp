---
title: 列挙型拡張に対する EntrySelectedBy の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9100ab7-fbdc-4c0d-bb56-57669ef42b95
caps.latest.revision: 9
ms.openlocfilehash: 316e54d11647aedc1552a0bb74b943de7e4e3588
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361581"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="065f7-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="065f7-102">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="065f7-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="065f7-103">Specifies a .NET type that triggers the condition.</span></span>

<span data-ttu-id="065f7-104">Configuration 要素 DefaultSettings Element (Format) 列挙 Able膨張要素 (format) 列挙 able展開要素 (format) Entryselectedby 要素 (format) の EntrySelectedBy (Format) の SelectionCondition 要素を指定します。列挙型拡張 (Format) の EntrySelectedBy の SelectionCondition に対する列挙型拡張 (Format) TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="065f7-104">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="065f7-105">構文</span><span class="sxs-lookup"><span data-stu-id="065f7-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="065f7-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="065f7-106">Attributes and Elements</span></span>

<span data-ttu-id="065f7-107">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="065f7-107">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="065f7-108">属性</span><span class="sxs-lookup"><span data-stu-id="065f7-108">Attributes</span></span>

<span data-ttu-id="065f7-109">なし。</span><span class="sxs-lookup"><span data-stu-id="065f7-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="065f7-110">子要素</span><span class="sxs-lookup"><span data-stu-id="065f7-110">Child Elements</span></span>

<span data-ttu-id="065f7-111">なし。</span><span class="sxs-lookup"><span data-stu-id="065f7-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="065f7-112">親要素</span><span class="sxs-lookup"><span data-stu-id="065f7-112">Parent Elements</span></span>

|<span data-ttu-id="065f7-113">要素</span><span class="sxs-lookup"><span data-stu-id="065f7-113">Element</span></span>|<span data-ttu-id="065f7-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="065f7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="065f7-115">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="065f7-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="065f7-116">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="065f7-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="065f7-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="065f7-117">Text Value</span></span>

<span data-ttu-id="065f7-118">.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="065f7-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="065f7-119">コメント</span><span class="sxs-lookup"><span data-stu-id="065f7-119">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="065f7-120">参照</span><span class="sxs-lookup"><span data-stu-id="065f7-120">See Also</span></span>

[<span data-ttu-id="065f7-121">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="065f7-121">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="065f7-122">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="065f7-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
