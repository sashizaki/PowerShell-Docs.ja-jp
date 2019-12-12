---
title: 列挙 Able展開要素 (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93d27173-9ae4-46e5-bb78-90525915cd70
caps.latest.revision: 9
ms.openlocfilehash: bc1e58c00ca8419f9204076f0a46050281e704db
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368751"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="cd48b-102">EnumerableExpansion 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cd48b-102">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="cd48b-103">特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="cd48b-103">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="cd48b-104">Configuration 要素 (Format) DefaultSettings 要素 (Format) Enumerableexpansions 要素 (format) の列挙 Ablesize 拡張要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cd48b-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cd48b-105">構文</span><span class="sxs-lookup"><span data-stu-id="cd48b-105">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cd48b-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="cd48b-106">Attributes and Elements</span></span>

<span data-ttu-id="cd48b-107">次のセクションでは、`EnumerableExpansion` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd48b-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cd48b-108">属性</span><span class="sxs-lookup"><span data-stu-id="cd48b-108">Attributes</span></span>

<span data-ttu-id="cd48b-109">なし。</span><span class="sxs-lookup"><span data-stu-id="cd48b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cd48b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="cd48b-110">Child Elements</span></span>

|<span data-ttu-id="cd48b-111">要素</span><span class="sxs-lookup"><span data-stu-id="cd48b-111">Element</span></span>|<span data-ttu-id="cd48b-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="cd48b-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cd48b-113">列挙 Able展開 (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="cd48b-113">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="cd48b-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cd48b-114">Optional element.</span></span><br /><br /> <span data-ttu-id="cd48b-115">この定義によって展開される .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd48b-115">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="cd48b-116">要素の展開 (形式)</span><span class="sxs-lookup"><span data-stu-id="cd48b-116">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="cd48b-117">この定義に対してコレクションオブジェクトを展開する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd48b-117">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cd48b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="cd48b-118">Parent Elements</span></span>

|<span data-ttu-id="cd48b-119">要素</span><span class="sxs-lookup"><span data-stu-id="cd48b-119">Element</span></span>|<span data-ttu-id="cd48b-120">[説明]</span><span class="sxs-lookup"><span data-stu-id="cd48b-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cd48b-121">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cd48b-121">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="cd48b-122">ビューに表示される .NET コレクションオブジェクトを拡張するさまざまな方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="cd48b-122">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cd48b-123">コメント</span><span class="sxs-lookup"><span data-stu-id="cd48b-123">Remarks</span></span>

<span data-ttu-id="cd48b-124">この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cd48b-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="cd48b-125">この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="cd48b-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="cd48b-126">既定の動作では、コレクション内のオブジェクトのプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd48b-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd48b-127">参照</span><span class="sxs-lookup"><span data-stu-id="cd48b-127">See Also</span></span>

[<span data-ttu-id="cd48b-128">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="cd48b-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
