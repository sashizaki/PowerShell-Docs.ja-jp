---
title: TableControl (形式) の TableRowEntroes TableRowEntry 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18d86af7-7ff9-4968-81be-2caa61937d49
caps.latest.revision: 10
ms.openlocfilehash: 001d46debde61f928c338b2f68112fb201f96216
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853588"
---
# <a name="tablerowentry-element-for-tablerowentroes-for-tablecontrol-format"></a><span data-ttu-id="aa7c3-102">TableControl の TableRowEntries の TableRowEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa7c3-102">TableRowEntry Element for TableRowEntroes for TableControl (Format)</span></span>

<span data-ttu-id="aa7c3-103">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-103">Defines the data that is displayed in a row of the table.</span></span>

<span data-ttu-id="aa7c3-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素の要素に TableControl (形式) TableRowEntry TableRowEntries TableControl (形式) 用の</span><span class="sxs-lookup"><span data-stu-id="aa7c3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aa7c3-105">構文</span><span class="sxs-lookup"><span data-stu-id="aa7c3-105">Syntax</span></span>

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aa7c3-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-106">Attributes and Elements</span></span>

<span data-ttu-id="aa7c3-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TableRowEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-107">The following sections describe attributes, child elements, and parent element of the `TableRowEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa7c3-108">属性</span><span class="sxs-lookup"><span data-stu-id="aa7c3-108">Attributes</span></span>

<span data-ttu-id="aa7c3-109">なし。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aa7c3-110">子要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-110">Child Elements</span></span>

|<span data-ttu-id="aa7c3-111">要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-111">Element</span></span>|<span data-ttu-id="aa7c3-112">説明</span><span class="sxs-lookup"><span data-stu-id="aa7c3-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa7c3-113">TableControl (形式) の TableRowEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-113">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="aa7c3-114">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-114">Required element.</span></span><br /><br /> <span data-ttu-id="aa7c3-115">プロパティ値が行に表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-115">Defines the objects whose property values are displayed in the row.</span></span>|
|[<span data-ttu-id="aa7c3-116">TableControl (形式) の TableRowEntry TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-116">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="aa7c3-117">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-117">Required element.</span></span><br /><br /> <span data-ttu-id="aa7c3-118">プロパティまたは表示値を持つスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-118">Defines the properties or scripts whose values are displayed.</span></span>|
|[<span data-ttu-id="aa7c3-119">TableRowEntry の TableCntrol (形式) の要素にラップします。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-119">Wrap Element for TableRowEntry for TableCntrol (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrl-format.md)|<span data-ttu-id="aa7c3-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-120">Optional element.</span></span><br /><br /> <span data-ttu-id="aa7c3-121">次の行を列の幅を超えるテキストが表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-121">Specifies that text that exceeds the column width is displayed on the next line.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aa7c3-122">親要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-122">Parent Elements</span></span>

|<span data-ttu-id="aa7c3-123">要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-123">Element</span></span>|<span data-ttu-id="aa7c3-124">説明</span><span class="sxs-lookup"><span data-stu-id="aa7c3-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa7c3-125">TableControl (形式) の TableRowEntries 要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="aa7c3-126">テーブルの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-126">Defines the rows of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa7c3-127">コメント</span><span class="sxs-lookup"><span data-stu-id="aa7c3-127">Remarks</span></span>

<span data-ttu-id="aa7c3-128">1 つ`TableColumnItems`要素と 1 つ`EntrySelectedBy`要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-128">One `TableColumnItems` element and one `EntrySelectedBy` element must be specified.</span></span>

<span data-ttu-id="aa7c3-129">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-129">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="aa7c3-130">例</span><span class="sxs-lookup"><span data-stu-id="aa7c3-130">Example</span></span>

<span data-ttu-id="aa7c3-131">次の例は、`TableRowEntry`の 2 つのプロパティの値を表示する行を定義する要素、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-131">The following example shows a `TableRowEntry` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName> Property for first column</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName> Property for second column</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="aa7c3-132">参照</span><span class="sxs-lookup"><span data-stu-id="aa7c3-132">See Also</span></span>

[<span data-ttu-id="aa7c3-133">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="aa7c3-134">TableControl (形式) の TableRowEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-134">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="aa7c3-135">TableControl (形式) の TableRowEntry TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-135">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="aa7c3-136">TableControl (形式) の TableRowEntries 要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-136">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="aa7c3-137">TableControl (形式) の TableRowEntries TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="aa7c3-137">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)

[<span data-ttu-id="aa7c3-138">TableRowEntry の TableCntrol (形式) の要素にラップします。</span><span class="sxs-lookup"><span data-stu-id="aa7c3-138">Wrap Element for TableRowEntry for TableCntrol (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrl-format.md)

[<span data-ttu-id="aa7c3-139">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="aa7c3-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
