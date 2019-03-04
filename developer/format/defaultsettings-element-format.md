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
ms.openlocfilehash: 59cc0514087cc52438e0d1271b8b77a7799eb32c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855668"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="e28a6-102">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="e28a6-103">書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e28a6-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="e28a6-104">一般的な設定に含めるコレクションを展開する方法を定義するテーブル内のテキストの折り返し、エラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="e28a6-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="e28a6-105">構成要素 (形式) DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e28a6-106">構文</span><span class="sxs-lookup"><span data-stu-id="e28a6-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e28a6-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e28a6-107">Attributes and Elements</span></span>

<span data-ttu-id="e28a6-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`DefaultSettings`要素。</span><span class="sxs-lookup"><span data-stu-id="e28a6-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e28a6-109">属性</span><span class="sxs-lookup"><span data-stu-id="e28a6-109">Attributes</span></span>

<span data-ttu-id="e28a6-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e28a6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e28a6-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e28a6-111">Child Elements</span></span>

|<span data-ttu-id="e28a6-112">要素</span><span class="sxs-lookup"><span data-stu-id="e28a6-112">Element</span></span>|<span data-ttu-id="e28a6-113">説明</span><span class="sxs-lookup"><span data-stu-id="e28a6-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e28a6-114">DisplayError 要素 (Frmat)</span><span class="sxs-lookup"><span data-stu-id="e28a6-114">DisplayError Element (Frmat)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="e28a6-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e28a6-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e28a6-116">データの一部を表示中にエラーが発生したときに、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="e28a6-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="e28a6-117">EnumerableExpansions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="e28a6-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e28a6-118">Optional element.</span></span><br /><br /> <span data-ttu-id="e28a6-119">.NET オブジェクトをビューに表示されているときに展開するさまざまな方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e28a6-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="e28a6-120">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="e28a6-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e28a6-121">Optional element.</span></span><br /><br /> <span data-ttu-id="e28a6-122">テーブル ビューでオブジェクトを表示するオブジェクトが必要なプロパティの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e28a6-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="e28a6-123">ShowError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="e28a6-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e28a6-124">Optional element.</span></span><br /><br /> <span data-ttu-id="e28a6-125">データの一部を表示中にエラーが発生したときに、完全なエラー レコードが表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="e28a6-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="e28a6-126">WrapTables 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="e28a6-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e28a6-127">Optional element.</span></span><br /><br /> <span data-ttu-id="e28a6-128">列の幅に収まらない場合、次の行にテーブル内のデータを移動することを指定します。</span><span class="sxs-lookup"><span data-stu-id="e28a6-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e28a6-129">親要素</span><span class="sxs-lookup"><span data-stu-id="e28a6-129">Parent Elements</span></span>

|<span data-ttu-id="e28a6-130">要素</span><span class="sxs-lookup"><span data-stu-id="e28a6-130">Element</span></span>|<span data-ttu-id="e28a6-131">説明</span><span class="sxs-lookup"><span data-stu-id="e28a6-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e28a6-132">構成要素</span><span class="sxs-lookup"><span data-stu-id="e28a6-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="e28a6-133">書式設定ファイルの最上位の要素を表します。</span><span class="sxs-lookup"><span data-stu-id="e28a6-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e28a6-134">コメント</span><span class="sxs-lookup"><span data-stu-id="e28a6-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="e28a6-135">参照</span><span class="sxs-lookup"><span data-stu-id="e28a6-135">See Also</span></span>

[<span data-ttu-id="e28a6-136">構成要素</span><span class="sxs-lookup"><span data-stu-id="e28a6-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="e28a6-137">DisplayError 要素 (Frmat)</span><span class="sxs-lookup"><span data-stu-id="e28a6-137">DisplayError Element (Frmat)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="e28a6-138">EnumerableExpansions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="e28a6-139">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="e28a6-140">ShowError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="e28a6-141">WrapTables 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e28a6-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="e28a6-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="e28a6-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
