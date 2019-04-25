---
title: FormatString 要素 ListControl (形式) を ListItem の |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd2cac66-88bb-449f-9d47-bd2cd4fe1801
caps.latest.revision: 13
ms.openlocfilehash: e6024ec4f7fc490c92408047c8c15c775e45bf9d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065622"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="3f056-102">ListControl の ListItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3f056-102">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="3f056-103">プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f056-103">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="3f056-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListControl (形式) のリスト項目要素を ListControl (形式)ListItem 要素 ListControl (形式) を ListItem の ListControl (形式) FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="3f056-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3f056-105">構文</span><span class="sxs-lookup"><span data-stu-id="3f056-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3f056-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3f056-106">Attributes and Elements</span></span>

<span data-ttu-id="3f056-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`FormatString`要素。</span><span class="sxs-lookup"><span data-stu-id="3f056-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3f056-108">属性</span><span class="sxs-lookup"><span data-stu-id="3f056-108">Attributes</span></span>

<span data-ttu-id="3f056-109">なし。</span><span class="sxs-lookup"><span data-stu-id="3f056-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3f056-110">子要素</span><span class="sxs-lookup"><span data-stu-id="3f056-110">Child Elements</span></span>

<span data-ttu-id="3f056-111">なし。</span><span class="sxs-lookup"><span data-stu-id="3f056-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3f056-112">親要素</span><span class="sxs-lookup"><span data-stu-id="3f056-112">Parent Elements</span></span>

|<span data-ttu-id="3f056-113">要素</span><span class="sxs-lookup"><span data-stu-id="3f056-113">Element</span></span>|<span data-ttu-id="3f056-114">説明</span><span class="sxs-lookup"><span data-stu-id="3f056-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3f056-115">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="3f056-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="3f056-116">プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3f056-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3f056-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="3f056-117">Text Value</span></span>

<span data-ttu-id="3f056-118">データの書式設定に使用されるパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f056-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="3f056-119">たとえば、このパターンを使用型の任意のプロパティの値の書式[System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0:mm}。</span><span class="sxs-lookup"><span data-stu-id="3f056-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f056-120">コメント</span><span class="sxs-lookup"><span data-stu-id="3f056-120">Remarks</span></span>

<span data-ttu-id="3f056-121">テーブルのビューやリスト ビュー、ワイド ビューは、カスタム ビューを作成するときに、書式指定文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f056-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="3f056-122">ビューに表示される値の書式設定に関する詳細については、次を参照してください。[表示されるデータの書式設定](./formatting-displayed-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="3f056-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="3f056-123">リスト ビューで書式指定文字列の使用に関する詳細については、次を参照してください。[リスト ビューの作成](./creating-a-list-view.md)です。</span><span class="sxs-lookup"><span data-stu-id="3f056-123">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="3f056-124">例</span><span class="sxs-lookup"><span data-stu-id="3f056-124">Example</span></span>

<span data-ttu-id="3f056-125">次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3f056-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="3f056-126">参照</span><span class="sxs-lookup"><span data-stu-id="3f056-126">See Also</span></span>

[<span data-ttu-id="3f056-127">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="3f056-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="3f056-128">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="3f056-128">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="3f056-129">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="3f056-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
