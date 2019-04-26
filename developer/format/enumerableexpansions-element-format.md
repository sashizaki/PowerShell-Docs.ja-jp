---
title: EnumerableExpansions 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50c33892-2ade-44c2-906c-81e5f5ca21f2
caps.latest.revision: 9
ms.openlocfilehash: 1ecbda8a3b623757517019105e3b1ee46ccbb55c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066092"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="7675c-102">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7675c-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="7675c-103">ビューに表示されているときに .NET コレクション オブジェクトを展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7675c-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="7675c-104">構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7675c-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7675c-105">構文</span><span class="sxs-lookup"><span data-stu-id="7675c-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7675c-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7675c-106">Attributes and Elements</span></span>

<span data-ttu-id="7675c-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`EnumerableExpansions`要素。</span><span class="sxs-lookup"><span data-stu-id="7675c-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="7675c-108">使用できる子要素の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="7675c-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="7675c-109">属性</span><span class="sxs-lookup"><span data-stu-id="7675c-109">Attributes</span></span>

<span data-ttu-id="7675c-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7675c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7675c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7675c-111">Child Elements</span></span>

|<span data-ttu-id="7675c-112">要素</span><span class="sxs-lookup"><span data-stu-id="7675c-112">Element</span></span>|<span data-ttu-id="7675c-113">説明</span><span class="sxs-lookup"><span data-stu-id="7675c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7675c-114">EnumerableExpansion 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7675c-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="7675c-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7675c-115">Optional element.</span></span><br /><br /> <span data-ttu-id="7675c-116">ビューに表示されているときに展開される特定の .NET コレクション オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="7675c-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7675c-117">親要素</span><span class="sxs-lookup"><span data-stu-id="7675c-117">Parent Elements</span></span>

|<span data-ttu-id="7675c-118">要素</span><span class="sxs-lookup"><span data-stu-id="7675c-118">Element</span></span>|<span data-ttu-id="7675c-119">説明</span><span class="sxs-lookup"><span data-stu-id="7675c-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7675c-120">DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7675c-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="7675c-121">書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="7675c-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7675c-122">コメント</span><span class="sxs-lookup"><span data-stu-id="7675c-122">Remarks</span></span>

<span data-ttu-id="7675c-123">この要素を使用して、コレクション オブジェクトと、コレクション内のオブジェクトを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7675c-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="7675c-124">コレクション オブジェクトをサポートする任意のオブジェクトを指すここで、 **System.Collections.ICollection**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7675c-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="7675c-125">参照</span><span class="sxs-lookup"><span data-stu-id="7675c-125">See Also</span></span>

[<span data-ttu-id="7675c-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="7675c-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
