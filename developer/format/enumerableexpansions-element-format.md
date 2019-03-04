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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860258"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="9680e-102">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9680e-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="9680e-103">ビューに表示されているときに .NET コレクション オブジェクトを展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="9680e-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="9680e-104">構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9680e-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9680e-105">構文</span><span class="sxs-lookup"><span data-stu-id="9680e-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9680e-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="9680e-106">Attributes and Elements</span></span>

<span data-ttu-id="9680e-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`EnumerableExpansions`要素。</span><span class="sxs-lookup"><span data-stu-id="9680e-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="9680e-108">使用できる子要素の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="9680e-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="9680e-109">属性</span><span class="sxs-lookup"><span data-stu-id="9680e-109">Attributes</span></span>

<span data-ttu-id="9680e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="9680e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9680e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="9680e-111">Child Elements</span></span>

|<span data-ttu-id="9680e-112">要素</span><span class="sxs-lookup"><span data-stu-id="9680e-112">Element</span></span>|<span data-ttu-id="9680e-113">説明</span><span class="sxs-lookup"><span data-stu-id="9680e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9680e-114">EnumerableExpansion 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9680e-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="9680e-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9680e-115">Optional element.</span></span><br /><br /> <span data-ttu-id="9680e-116">ビューに表示されているときに展開される特定の .NET コレクション オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="9680e-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9680e-117">親要素</span><span class="sxs-lookup"><span data-stu-id="9680e-117">Parent Elements</span></span>

|<span data-ttu-id="9680e-118">要素</span><span class="sxs-lookup"><span data-stu-id="9680e-118">Element</span></span>|<span data-ttu-id="9680e-119">説明</span><span class="sxs-lookup"><span data-stu-id="9680e-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9680e-120">DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9680e-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="9680e-121">書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9680e-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9680e-122">コメント</span><span class="sxs-lookup"><span data-stu-id="9680e-122">Remarks</span></span>

<span data-ttu-id="9680e-123">この要素を使用して、コレクション オブジェクトと、コレクション内のオブジェクトを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="9680e-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="9680e-124">コレクション オブジェクトをサポートする任意のオブジェクトを指すここで、 **System.Collections.ICollection**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9680e-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="9680e-125">参照</span><span class="sxs-lookup"><span data-stu-id="9680e-125">See Also</span></span>

[<span data-ttu-id="9680e-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="9680e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
