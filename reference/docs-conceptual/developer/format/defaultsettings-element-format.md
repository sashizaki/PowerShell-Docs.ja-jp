---
title: DefaultSettings 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363871"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="4ff10-102">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4ff10-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="4ff10-103">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4ff10-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="4ff10-104">一般的な設定には、エラーの表示、テーブル内のテキストの折り返し、コレクションの展開方法の定義などがあります。</span><span class="sxs-lookup"><span data-stu-id="4ff10-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="4ff10-105">Configuration 要素 (Format) DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4ff10-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4ff10-106">構文</span><span class="sxs-lookup"><span data-stu-id="4ff10-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4ff10-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="4ff10-107">Attributes and Elements</span></span>

<span data-ttu-id="4ff10-108">次のセクションでは、属性、子要素、`DefaultSettings` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ff10-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4ff10-109">属性</span><span class="sxs-lookup"><span data-stu-id="4ff10-109">Attributes</span></span>

<span data-ttu-id="4ff10-110">なし。</span><span class="sxs-lookup"><span data-stu-id="4ff10-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4ff10-111">子要素</span><span class="sxs-lookup"><span data-stu-id="4ff10-111">Child Elements</span></span>

|<span data-ttu-id="4ff10-112">要素</span><span class="sxs-lookup"><span data-stu-id="4ff10-112">Element</span></span>|<span data-ttu-id="4ff10-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="4ff10-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4ff10-114">DisplayError 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="4ff10-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="4ff10-115">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="4ff10-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4ff10-116">データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ff10-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="4ff10-117">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4ff10-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="4ff10-118">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="4ff10-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4ff10-119">.NET オブジェクトをビューに表示するときに展開するさまざまな方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="4ff10-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="4ff10-120">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="4ff10-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="4ff10-121">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="4ff10-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4ff10-122">オブジェクトをテーブルビューに表示するために必要なプロパティの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ff10-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="4ff10-123">ShowError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4ff10-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="4ff10-124">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="4ff10-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4ff10-125">データの一部を表示しているときにエラーが発生した場合に、完全なエラーレコードが表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ff10-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="4ff10-126">WrapTables 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="4ff10-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="4ff10-127">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="4ff10-127">Optional element.</span></span><br /><br /> <span data-ttu-id="4ff10-128">列の幅に合わない場合に、テーブル内のデータを次の行に移動するように指定します。</span><span class="sxs-lookup"><span data-stu-id="4ff10-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4ff10-129">親要素</span><span class="sxs-lookup"><span data-stu-id="4ff10-129">Parent Elements</span></span>

|<span data-ttu-id="4ff10-130">要素</span><span class="sxs-lookup"><span data-stu-id="4ff10-130">Element</span></span>|<span data-ttu-id="4ff10-131">[説明]</span><span class="sxs-lookup"><span data-stu-id="4ff10-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4ff10-132">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="4ff10-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="4ff10-133">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="4ff10-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4ff10-134">コメント</span><span class="sxs-lookup"><span data-stu-id="4ff10-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="4ff10-135">参照</span><span class="sxs-lookup"><span data-stu-id="4ff10-135">See Also</span></span>

[<span data-ttu-id="4ff10-136">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="4ff10-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="4ff10-137">DisplayError 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="4ff10-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="4ff10-138">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4ff10-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="4ff10-139">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="4ff10-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="4ff10-140">ShowError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4ff10-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="4ff10-141">WrapTables 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="4ff10-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="4ff10-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="4ff10-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
