---
title: 列挙型拡張に対する EntrySelectedBy の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f47384be10705b913d52b5cc8cb4ecf9ba83f17c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787344"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="4e5fb-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4e5fb-102">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="4e5fb-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e5fb-103">Specifies a .NET type that triggers the condition.</span></span>

<span data-ttu-id="4e5fb-104">Configuration 要素 DefaultSettings (Format) 列挙型の拡張要素 (format) 列挙型の展開要素 (形式) entryselectedby 要素 (format) entryselectedby の要素 (format) を指定します。 entryselectedby の selectionselectedby は、entryselectedby の Selectionselectedby に対する SelectionCondition の selectioncondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e5fb-104">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4e5fb-105">構文</span><span class="sxs-lookup"><span data-stu-id="4e5fb-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4e5fb-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4e5fb-106">Attributes and Elements</span></span>

<span data-ttu-id="4e5fb-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="4e5fb-107">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4e5fb-108">属性</span><span class="sxs-lookup"><span data-stu-id="4e5fb-108">Attributes</span></span>

<span data-ttu-id="4e5fb-109">なし。</span><span class="sxs-lookup"><span data-stu-id="4e5fb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4e5fb-110">子要素</span><span class="sxs-lookup"><span data-stu-id="4e5fb-110">Child Elements</span></span>

<span data-ttu-id="4e5fb-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4e5fb-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4e5fb-112">親要素</span><span class="sxs-lookup"><span data-stu-id="4e5fb-112">Parent Elements</span></span>

|<span data-ttu-id="4e5fb-113">要素</span><span class="sxs-lookup"><span data-stu-id="4e5fb-113">Element</span></span>|<span data-ttu-id="4e5fb-114">説明</span><span class="sxs-lookup"><span data-stu-id="4e5fb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e5fb-115">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4e5fb-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="4e5fb-116">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4e5fb-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4e5fb-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="4e5fb-117">Text Value</span></span>

<span data-ttu-id="4e5fb-118">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="4e5fb-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e5fb-119">解説</span><span class="sxs-lookup"><span data-stu-id="4e5fb-119">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="4e5fb-120">参照</span><span class="sxs-lookup"><span data-stu-id="4e5fb-120">See Also</span></span>

[<span data-ttu-id="4e5fb-121">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4e5fb-121">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="4e5fb-122">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4e5fb-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
