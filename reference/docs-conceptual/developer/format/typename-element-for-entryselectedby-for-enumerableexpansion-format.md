---
title: 列挙型拡張に対する EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 670aeb0986b07c8b7834a9f4f9510f1757a62186
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785083"
---
# <a name="typename-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="0d829-102">EnumerableExpansion の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d829-102">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="0d829-103">この定義によって展開される .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d829-103">Specifies a .NET type that is expanded by this definition.</span></span> <span data-ttu-id="0d829-104">この要素は、既定の設定を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d829-104">This element is used when defining a default settings.</span></span>

<span data-ttu-id="0d829-105">Configuration 要素 (Format) DefaultSettings Element (Format) 列挙型拡張要素 (format) 列挙型拡張要素 (format) の entryselectedby 要素 (format) を指定します。 EntrySelectedBy の EntrySelectedBy の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="0d829-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0d829-106">構文</span><span class="sxs-lookup"><span data-stu-id="0d829-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="0d829-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0d829-107">Attributes and Elements</span></span>

<span data-ttu-id="0d829-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="0d829-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0d829-109">属性</span><span class="sxs-lookup"><span data-stu-id="0d829-109">Attributes</span></span>

<span data-ttu-id="0d829-110">なし。</span><span class="sxs-lookup"><span data-stu-id="0d829-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0d829-111">子要素</span><span class="sxs-lookup"><span data-stu-id="0d829-111">Child Elements</span></span>

<span data-ttu-id="0d829-112">なし。</span><span class="sxs-lookup"><span data-stu-id="0d829-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0d829-113">親要素</span><span class="sxs-lookup"><span data-stu-id="0d829-113">Parent Elements</span></span>

|<span data-ttu-id="0d829-114">要素</span><span class="sxs-lookup"><span data-stu-id="0d829-114">Element</span></span>|<span data-ttu-id="0d829-115">説明</span><span class="sxs-lookup"><span data-stu-id="0d829-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0d829-116">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d829-116">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="0d829-117">この定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="0d829-117">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0d829-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="0d829-118">Text Value</span></span>

<span data-ttu-id="0d829-119">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="0d829-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d829-120">解説</span><span class="sxs-lookup"><span data-stu-id="0d829-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="0d829-121">参照</span><span class="sxs-lookup"><span data-stu-id="0d829-121">See Also</span></span>

[<span data-ttu-id="0d829-122">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d829-122">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="0d829-123">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="0d829-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
