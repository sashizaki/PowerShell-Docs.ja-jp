---
title: DefaultSettings 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066347"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="99717-102">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="99717-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="99717-103">書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="99717-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="99717-104">一般的な設定に含めるコレクションを展開する方法を定義するテーブル内のテキストの折り返し、エラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="99717-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="99717-105">構成要素 (形式) DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="99717-106">構文</span><span class="sxs-lookup"><span data-stu-id="99717-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="99717-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99717-107">Attributes and Elements</span></span>

<span data-ttu-id="99717-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`DefaultSettings`要素。</span><span class="sxs-lookup"><span data-stu-id="99717-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="99717-109">属性</span><span class="sxs-lookup"><span data-stu-id="99717-109">Attributes</span></span>

<span data-ttu-id="99717-110">なし。</span><span class="sxs-lookup"><span data-stu-id="99717-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="99717-111">子要素</span><span class="sxs-lookup"><span data-stu-id="99717-111">Child Elements</span></span>

|<span data-ttu-id="99717-112">要素</span><span class="sxs-lookup"><span data-stu-id="99717-112">Element</span></span>|<span data-ttu-id="99717-113">説明</span><span class="sxs-lookup"><span data-stu-id="99717-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="99717-114">DisplayError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="99717-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="99717-115">Optional element.</span></span><br /><br /> <span data-ttu-id="99717-116">データの一部を表示中にエラーが発生したときに、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="99717-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="99717-117">EnumerableExpansions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="99717-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="99717-118">Optional element.</span></span><br /><br /> <span data-ttu-id="99717-119">.NET オブジェクトをビューに表示されているときに展開するさまざまな方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="99717-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="99717-120">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="99717-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="99717-121">Optional element.</span></span><br /><br /> <span data-ttu-id="99717-122">テーブル ビューでオブジェクトを表示するオブジェクトが必要なプロパティの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="99717-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="99717-123">ShowError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="99717-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="99717-124">Optional element.</span></span><br /><br /> <span data-ttu-id="99717-125">データの一部を表示中にエラーが発生したときに、完全なエラー レコードが表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="99717-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="99717-126">WrapTables 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="99717-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="99717-127">Optional element.</span></span><br /><br /> <span data-ttu-id="99717-128">列の幅に収まらない場合、次の行にテーブル内のデータを移動することを指定します。</span><span class="sxs-lookup"><span data-stu-id="99717-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="99717-129">親要素</span><span class="sxs-lookup"><span data-stu-id="99717-129">Parent Elements</span></span>

|<span data-ttu-id="99717-130">要素</span><span class="sxs-lookup"><span data-stu-id="99717-130">Element</span></span>|<span data-ttu-id="99717-131">説明</span><span class="sxs-lookup"><span data-stu-id="99717-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="99717-132">構成要素</span><span class="sxs-lookup"><span data-stu-id="99717-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="99717-133">書式設定ファイルの最上位の要素を表します。</span><span class="sxs-lookup"><span data-stu-id="99717-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="99717-134">コメント</span><span class="sxs-lookup"><span data-stu-id="99717-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="99717-135">参照</span><span class="sxs-lookup"><span data-stu-id="99717-135">See Also</span></span>

[<span data-ttu-id="99717-136">構成要素</span><span class="sxs-lookup"><span data-stu-id="99717-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="99717-137">DisplayError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="99717-138">EnumerableExpansions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="99717-139">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="99717-140">ShowError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="99717-141">WrapTables 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="99717-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="99717-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="99717-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
