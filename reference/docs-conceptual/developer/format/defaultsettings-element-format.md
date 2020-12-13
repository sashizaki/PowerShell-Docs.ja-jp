---
ms.date: 09/13/2016
ms.topic: reference
title: DefaultSettings 要素 (書式)
description: DefaultSettings 要素 (書式)
ms.openlocfilehash: 1c2055b38a416fe2d75fa20c6c87e92d9eed4285
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666724"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="f56c5-103">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-103">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="f56c5-104">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="f56c5-104">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="f56c5-105">一般的な設定には、エラーの表示、テーブル内のテキストの折り返し、コレクションの展開方法の定義などがあります。</span><span class="sxs-lookup"><span data-stu-id="f56c5-105">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="f56c5-106">Configuration 要素 (Format) DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-106">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f56c5-107">構文</span><span class="sxs-lookup"><span data-stu-id="f56c5-107">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f56c5-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f56c5-108">Attributes and Elements</span></span>

<span data-ttu-id="f56c5-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `DefaultSettings` ます。</span><span class="sxs-lookup"><span data-stu-id="f56c5-109">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f56c5-110">属性</span><span class="sxs-lookup"><span data-stu-id="f56c5-110">Attributes</span></span>

<span data-ttu-id="f56c5-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f56c5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f56c5-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f56c5-112">Child Elements</span></span>

|<span data-ttu-id="f56c5-113">要素</span><span class="sxs-lookup"><span data-stu-id="f56c5-113">Element</span></span>|<span data-ttu-id="f56c5-114">説明</span><span class="sxs-lookup"><span data-stu-id="f56c5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f56c5-115">DisplayError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-115">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="f56c5-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f56c5-116">Optional element.</span></span><br /><br /> <span data-ttu-id="f56c5-117">データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f56c5-117">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="f56c5-118">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-118">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="f56c5-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f56c5-119">Optional element.</span></span><br /><br /> <span data-ttu-id="f56c5-120">.NET オブジェクトをビューに表示するときに展開するさまざまな方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f56c5-120">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="f56c5-121">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-121">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="f56c5-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f56c5-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f56c5-123">オブジェクトをテーブルビューに表示するために必要なプロパティの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f56c5-123">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="f56c5-124">ShowError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-124">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="f56c5-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f56c5-125">Optional element.</span></span><br /><br /> <span data-ttu-id="f56c5-126">データの一部を表示しているときにエラーが発生した場合に、完全なエラーレコードが表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f56c5-126">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="f56c5-127">WrapTables 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-127">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="f56c5-128">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f56c5-128">Optional element.</span></span><br /><br /> <span data-ttu-id="f56c5-129">列の幅に合わない場合に、テーブル内のデータを次の行に移動するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f56c5-129">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f56c5-130">親要素</span><span class="sxs-lookup"><span data-stu-id="f56c5-130">Parent Elements</span></span>

|<span data-ttu-id="f56c5-131">要素</span><span class="sxs-lookup"><span data-stu-id="f56c5-131">Element</span></span>|<span data-ttu-id="f56c5-132">説明</span><span class="sxs-lookup"><span data-stu-id="f56c5-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f56c5-133">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="f56c5-133">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="f56c5-134">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="f56c5-134">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f56c5-135">解説</span><span class="sxs-lookup"><span data-stu-id="f56c5-135">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="f56c5-136">参照</span><span class="sxs-lookup"><span data-stu-id="f56c5-136">See Also</span></span>

[<span data-ttu-id="f56c5-137">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="f56c5-137">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="f56c5-138">DisplayError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-138">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="f56c5-139">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-139">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="f56c5-140">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-140">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="f56c5-141">ShowError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-141">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="f56c5-142">WrapTables 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f56c5-142">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="f56c5-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f56c5-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
