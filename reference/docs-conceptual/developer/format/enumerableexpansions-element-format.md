---
title: 列挙 Able展開要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50c33892-2ade-44c2-906c-81e5f5ca21f2
caps.latest.revision: 9
ms.openlocfilehash: 1ecbda8a3b623757517019105e3b1ee46ccbb55c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363301"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="c8fee-102">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c8fee-102">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="c8fee-103">.NET コレクションオブジェクトがビューに表示されるときの展開方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8fee-103">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="c8fee-104">Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c8fee-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c8fee-105">構文</span><span class="sxs-lookup"><span data-stu-id="c8fee-105">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c8fee-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c8fee-106">Attributes and Elements</span></span>

<span data-ttu-id="c8fee-107">次のセクションでは、`EnumerableExpansions` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8fee-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="c8fee-108">使用できる子要素の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="c8fee-108">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="c8fee-109">属性</span><span class="sxs-lookup"><span data-stu-id="c8fee-109">Attributes</span></span>

<span data-ttu-id="c8fee-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c8fee-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c8fee-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c8fee-111">Child Elements</span></span>

|<span data-ttu-id="c8fee-112">要素</span><span class="sxs-lookup"><span data-stu-id="c8fee-112">Element</span></span>|<span data-ttu-id="c8fee-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="c8fee-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c8fee-114">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c8fee-114">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="c8fee-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c8fee-115">Optional element.</span></span><br /><br /> <span data-ttu-id="c8fee-116">ビューに表示されるときに展開される特定の .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c8fee-116">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c8fee-117">親要素</span><span class="sxs-lookup"><span data-stu-id="c8fee-117">Parent Elements</span></span>

|<span data-ttu-id="c8fee-118">要素</span><span class="sxs-lookup"><span data-stu-id="c8fee-118">Element</span></span>|<span data-ttu-id="c8fee-119">[説明]</span><span class="sxs-lookup"><span data-stu-id="c8fee-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c8fee-120">DefaultSettings 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c8fee-120">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="c8fee-121">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8fee-121">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c8fee-122">コメント</span><span class="sxs-lookup"><span data-stu-id="c8fee-122">Remarks</span></span>

<span data-ttu-id="c8fee-123">この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8fee-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="c8fee-124">この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="c8fee-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8fee-125">参照</span><span class="sxs-lookup"><span data-stu-id="c8fee-125">See Also</span></span>

[<span data-ttu-id="c8fee-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="c8fee-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
