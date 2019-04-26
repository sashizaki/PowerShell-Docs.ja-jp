---
title: TableControl (形式) の TableColumnItem PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb26d72c-2f77-4801-badf-0537ccc55e31
caps.latest.revision: 10
ms.openlocfilehash: 6e86b6a0874b385703121802bc8108a0410442cd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064615"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="e1d95-102">TableControl の TableColumnItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e1d95-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="e1d95-103">行の列で値が表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1d95-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="e1d95-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) TableColumnItems 要素 (形式) TableColumnItem 要素 (形式)TableColumnItem (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="e1d95-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e1d95-105">構文</span><span class="sxs-lookup"><span data-stu-id="e1d95-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e1d95-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e1d95-106">Attributes and Elements</span></span>

<span data-ttu-id="e1d95-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="e1d95-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e1d95-108">属性</span><span class="sxs-lookup"><span data-stu-id="e1d95-108">Attributes</span></span>

<span data-ttu-id="e1d95-109">なし。</span><span class="sxs-lookup"><span data-stu-id="e1d95-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e1d95-110">子要素</span><span class="sxs-lookup"><span data-stu-id="e1d95-110">Child Elements</span></span>

<span data-ttu-id="e1d95-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e1d95-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e1d95-112">親要素</span><span class="sxs-lookup"><span data-stu-id="e1d95-112">Parent Elements</span></span>

|<span data-ttu-id="e1d95-113">要素</span><span class="sxs-lookup"><span data-stu-id="e1d95-113">Element</span></span>|<span data-ttu-id="e1d95-114">説明</span><span class="sxs-lookup"><span data-stu-id="e1d95-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e1d95-115">TableColumnItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e1d95-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="e1d95-116">プロパティまたは値を持つが、行の列に表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e1d95-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e1d95-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e1d95-117">Text Value</span></span>

<span data-ttu-id="e1d95-118">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1d95-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1d95-119">コメント</span><span class="sxs-lookup"><span data-stu-id="e1d95-119">Remarks</span></span>

<span data-ttu-id="e1d95-120">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1d95-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e1d95-121">例</span><span class="sxs-lookup"><span data-stu-id="e1d95-121">Example</span></span>

<span data-ttu-id="e1d95-122">この例では、`TableColumnItem`要素を指定する、`Status`のプロパティ、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e1d95-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="e1d95-123">参照</span><span class="sxs-lookup"><span data-stu-id="e1d95-123">See Also</span></span>

[<span data-ttu-id="e1d95-124">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1d95-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e1d95-125">TableColumnItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e1d95-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="e1d95-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="e1d95-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
