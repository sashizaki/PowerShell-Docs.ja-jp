---
title: ListControl の ListItem の FormatString 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9ec73aa1c2e8180258722627e30344de4e67bda5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781581"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="025f2-102">ListControl の ListItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="025f2-102">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="025f2-103">プロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="025f2-103">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="025f2-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries 要素 for ListItems (format) ListEntry Element for ListControl (format) Element for ListControl (format) ListControl for ListControl (format) を使用します。</span><span class="sxs-lookup"><span data-stu-id="025f2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="025f2-105">構文</span><span class="sxs-lookup"><span data-stu-id="025f2-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="025f2-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="025f2-106">Attributes and Elements</span></span>

<span data-ttu-id="025f2-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `FormatString` ます。</span><span class="sxs-lookup"><span data-stu-id="025f2-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="025f2-108">属性</span><span class="sxs-lookup"><span data-stu-id="025f2-108">Attributes</span></span>

<span data-ttu-id="025f2-109">なし。</span><span class="sxs-lookup"><span data-stu-id="025f2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="025f2-110">子要素</span><span class="sxs-lookup"><span data-stu-id="025f2-110">Child Elements</span></span>

<span data-ttu-id="025f2-111">なし。</span><span class="sxs-lookup"><span data-stu-id="025f2-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="025f2-112">親要素</span><span class="sxs-lookup"><span data-stu-id="025f2-112">Parent Elements</span></span>

|<span data-ttu-id="025f2-113">要素</span><span class="sxs-lookup"><span data-stu-id="025f2-113">Element</span></span>|<span data-ttu-id="025f2-114">説明</span><span class="sxs-lookup"><span data-stu-id="025f2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="025f2-115">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="025f2-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="025f2-116">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="025f2-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="025f2-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="025f2-117">Text Value</span></span>

<span data-ttu-id="025f2-118">データの書式設定に使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="025f2-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="025f2-119">たとえば、このパターンを使用すると、型 system.string: {0: MMM} {0: dd} {0: HH}: {0: mm} のプロパティの値を書式設定[できます。](/dotnet/api/System.TimeSpan)</span><span class="sxs-lookup"><span data-stu-id="025f2-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="025f2-120">解説</span><span class="sxs-lookup"><span data-stu-id="025f2-120">Remarks</span></span>

<span data-ttu-id="025f2-121">書式指定文字列は、テーブルビュー、リストビュー、ワイドビュー、またはカスタムビューを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="025f2-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="025f2-122">ビューに表示される値の書式設定の詳細については、「[表示されるデータの書式設定](./formatting-displayed-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="025f2-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="025f2-123">リストビューでの書式指定文字列の使用の詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="025f2-123">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="025f2-124">例</span><span class="sxs-lookup"><span data-stu-id="025f2-124">Example</span></span>

<span data-ttu-id="025f2-125">次の例は、プロパティの値の書式設定文字列を定義する方法を示して `StartTime` います。</span><span class="sxs-lookup"><span data-stu-id="025f2-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="025f2-126">参照</span><span class="sxs-lookup"><span data-stu-id="025f2-126">See Also</span></span>

[<span data-ttu-id="025f2-127">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="025f2-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="025f2-128">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="025f2-128">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="025f2-129">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="025f2-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
