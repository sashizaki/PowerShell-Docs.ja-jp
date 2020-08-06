---
title: 列挙 Able展開要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2b536b1ab9b34b0089d0a38d3c5dc7a937176443
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774016"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="ad2e5-102">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ad2e5-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="ad2e5-103">.NET コレクションオブジェクトがビューに表示されるときの展開方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad2e5-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="ad2e5-104">Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ad2e5-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ad2e5-105">構文</span><span class="sxs-lookup"><span data-stu-id="ad2e5-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ad2e5-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ad2e5-106">Attributes and Elements</span></span>

<span data-ttu-id="ad2e5-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `EnumerableExpansions` ます。</span><span class="sxs-lookup"><span data-stu-id="ad2e5-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="ad2e5-108">使用できる子要素の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ad2e5-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="ad2e5-109">属性</span><span class="sxs-lookup"><span data-stu-id="ad2e5-109">Attributes</span></span>

<span data-ttu-id="ad2e5-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ad2e5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ad2e5-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ad2e5-111">Child Elements</span></span>

|<span data-ttu-id="ad2e5-112">要素</span><span class="sxs-lookup"><span data-stu-id="ad2e5-112">Element</span></span>|<span data-ttu-id="ad2e5-113">説明</span><span class="sxs-lookup"><span data-stu-id="ad2e5-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad2e5-114">EnumerableExpansion 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ad2e5-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="ad2e5-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ad2e5-115">Optional element.</span></span><br /><br /> <span data-ttu-id="ad2e5-116">ビューに表示されるときに展開される特定の .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ad2e5-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ad2e5-117">親要素</span><span class="sxs-lookup"><span data-stu-id="ad2e5-117">Parent Elements</span></span>

|<span data-ttu-id="ad2e5-118">要素</span><span class="sxs-lookup"><span data-stu-id="ad2e5-118">Element</span></span>|<span data-ttu-id="ad2e5-119">説明</span><span class="sxs-lookup"><span data-stu-id="ad2e5-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad2e5-120">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ad2e5-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="ad2e5-121">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad2e5-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ad2e5-122">解説</span><span class="sxs-lookup"><span data-stu-id="ad2e5-122">Remarks</span></span>

<span data-ttu-id="ad2e5-123">この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad2e5-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="ad2e5-124">この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="ad2e5-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad2e5-125">参照</span><span class="sxs-lookup"><span data-stu-id="ad2e5-125">See Also</span></span>

[<span data-ttu-id="ad2e5-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ad2e5-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
