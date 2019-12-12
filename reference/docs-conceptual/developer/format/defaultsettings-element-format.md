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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363871"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="12c2b-102">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="12c2b-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="12c2b-103">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="12c2b-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="12c2b-104">一般的な設定には、エラーの表示、テーブル内のテキストの折り返し、コレクションの展開方法の定義などがあります。</span><span class="sxs-lookup"><span data-stu-id="12c2b-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="12c2b-105">Configuration 要素 (Format) DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="12c2b-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="12c2b-106">構文</span><span class="sxs-lookup"><span data-stu-id="12c2b-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12c2b-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="12c2b-107">Attributes and Elements</span></span>

<span data-ttu-id="12c2b-108">次のセクションでは、`DefaultSettings` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="12c2b-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="12c2b-109">属性</span><span class="sxs-lookup"><span data-stu-id="12c2b-109">Attributes</span></span>

<span data-ttu-id="12c2b-110">なし。</span><span class="sxs-lookup"><span data-stu-id="12c2b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="12c2b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="12c2b-111">Child Elements</span></span>

|<span data-ttu-id="12c2b-112">要素</span><span class="sxs-lookup"><span data-stu-id="12c2b-112">Element</span></span>|<span data-ttu-id="12c2b-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="12c2b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12c2b-114">DisplayError 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="12c2b-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="12c2b-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="12c2b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="12c2b-116">データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="12c2b-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="12c2b-117">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="12c2b-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="12c2b-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="12c2b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="12c2b-119">.NET オブジェクトをビューに表示するときに展開するさまざまな方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="12c2b-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="12c2b-120">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="12c2b-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="12c2b-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="12c2b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="12c2b-122">オブジェクトをテーブルビューに表示するために必要なプロパティの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="12c2b-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="12c2b-123">ShowError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="12c2b-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="12c2b-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="12c2b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="12c2b-125">データの一部を表示しているときにエラーが発生した場合に、完全なエラーレコードが表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="12c2b-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="12c2b-126">WrapTables 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="12c2b-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="12c2b-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="12c2b-127">Optional element.</span></span><br /><br /> <span data-ttu-id="12c2b-128">列の幅に合わない場合に、テーブル内のデータを次の行に移動するように指定します。</span><span class="sxs-lookup"><span data-stu-id="12c2b-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="12c2b-129">親要素</span><span class="sxs-lookup"><span data-stu-id="12c2b-129">Parent Elements</span></span>

|<span data-ttu-id="12c2b-130">要素</span><span class="sxs-lookup"><span data-stu-id="12c2b-130">Element</span></span>|<span data-ttu-id="12c2b-131">[説明]</span><span class="sxs-lookup"><span data-stu-id="12c2b-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12c2b-132">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="12c2b-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="12c2b-133">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="12c2b-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="12c2b-134">コメント</span><span class="sxs-lookup"><span data-stu-id="12c2b-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="12c2b-135">参照</span><span class="sxs-lookup"><span data-stu-id="12c2b-135">See Also</span></span>

[<span data-ttu-id="12c2b-136">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="12c2b-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="12c2b-137">DisplayError 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="12c2b-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="12c2b-138">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="12c2b-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="12c2b-139">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="12c2b-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="12c2b-140">ShowError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="12c2b-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="12c2b-141">WrapTables 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="12c2b-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="12c2b-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="12c2b-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
