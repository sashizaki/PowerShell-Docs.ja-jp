---
title: DefaultSettings 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7da7948fc0814e38a8f3910596e223470ec27d75
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787735"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="08428-102">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08428-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="08428-103">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="08428-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="08428-104">一般的な設定には、エラーの表示、テーブル内のテキストの折り返し、コレクションの展開方法の定義などがあります。</span><span class="sxs-lookup"><span data-stu-id="08428-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="08428-105">Configuration 要素 (Format) DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="08428-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="08428-106">構文</span><span class="sxs-lookup"><span data-stu-id="08428-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="08428-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="08428-107">Attributes and Elements</span></span>

<span data-ttu-id="08428-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `DefaultSettings` ます。</span><span class="sxs-lookup"><span data-stu-id="08428-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="08428-109">属性</span><span class="sxs-lookup"><span data-stu-id="08428-109">Attributes</span></span>

<span data-ttu-id="08428-110">なし。</span><span class="sxs-lookup"><span data-stu-id="08428-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="08428-111">子要素</span><span class="sxs-lookup"><span data-stu-id="08428-111">Child Elements</span></span>

|<span data-ttu-id="08428-112">要素</span><span class="sxs-lookup"><span data-stu-id="08428-112">Element</span></span>|<span data-ttu-id="08428-113">説明</span><span class="sxs-lookup"><span data-stu-id="08428-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="08428-114">DisplayError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08428-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="08428-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="08428-115">Optional element.</span></span><br /><br /> <span data-ttu-id="08428-116">データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="08428-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="08428-117">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08428-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="08428-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="08428-118">Optional element.</span></span><br /><br /> <span data-ttu-id="08428-119">.NET オブジェクトをビューに表示するときに展開するさまざまな方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="08428-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="08428-120">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="08428-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="08428-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="08428-121">Optional element.</span></span><br /><br /> <span data-ttu-id="08428-122">オブジェクトをテーブルビューに表示するために必要なプロパティの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="08428-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="08428-123">ShowError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08428-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="08428-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="08428-124">Optional element.</span></span><br /><br /> <span data-ttu-id="08428-125">データの一部を表示しているときにエラーが発生した場合に、完全なエラーレコードが表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="08428-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="08428-126">WrapTables 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08428-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="08428-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="08428-127">Optional element.</span></span><br /><br /> <span data-ttu-id="08428-128">列の幅に合わない場合に、テーブル内のデータを次の行に移動するように指定します。</span><span class="sxs-lookup"><span data-stu-id="08428-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="08428-129">親要素</span><span class="sxs-lookup"><span data-stu-id="08428-129">Parent Elements</span></span>

|<span data-ttu-id="08428-130">要素</span><span class="sxs-lookup"><span data-stu-id="08428-130">Element</span></span>|<span data-ttu-id="08428-131">説明</span><span class="sxs-lookup"><span data-stu-id="08428-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="08428-132">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="08428-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="08428-133">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="08428-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="08428-134">解説</span><span class="sxs-lookup"><span data-stu-id="08428-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="08428-135">参照</span><span class="sxs-lookup"><span data-stu-id="08428-135">See Also</span></span>

[<span data-ttu-id="08428-136">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="08428-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="08428-137">DisplayError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08428-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="08428-138">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08428-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="08428-139">PropertyCountForTable (形式)</span><span class="sxs-lookup"><span data-stu-id="08428-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="08428-140">ShowError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08428-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="08428-141">WrapTables 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08428-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="08428-142">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="08428-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
