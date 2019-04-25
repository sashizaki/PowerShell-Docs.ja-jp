---
title: ListItem の ListControl (形式) の要素にラベルを付ける |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c693ff46-d1ad-4dc7-93ac-41ff2fc6c103
caps.latest.revision: 9
ms.openlocfilehash: c1293d5a1f942704ac01388c66bd9009fd340e82
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065429"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="ad9e1-102">ListControl の ListItem の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ad9e1-102">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="ad9e1-103">行のプロパティまたはスクリプトの値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9e1-103">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="ad9e1-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListControl 要素 (の ListEntry の ListControl (形式) のリスト項目のListControl (形式) を ListItem ListControl (形式) Label 要素の ListItems の ListItem 要素の形式)</span><span class="sxs-lookup"><span data-stu-id="ad9e1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ad9e1-105">構文</span><span class="sxs-lookup"><span data-stu-id="ad9e1-105">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ad9e1-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ad9e1-106">Attributes and Elements</span></span>

<span data-ttu-id="ad9e1-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Label`要素。</span><span class="sxs-lookup"><span data-stu-id="ad9e1-107">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ad9e1-108">属性</span><span class="sxs-lookup"><span data-stu-id="ad9e1-108">Attributes</span></span>

<span data-ttu-id="ad9e1-109">なし。</span><span class="sxs-lookup"><span data-stu-id="ad9e1-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ad9e1-110">子要素</span><span class="sxs-lookup"><span data-stu-id="ad9e1-110">Child Elements</span></span>

<span data-ttu-id="ad9e1-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ad9e1-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ad9e1-112">親要素</span><span class="sxs-lookup"><span data-stu-id="ad9e1-112">Parent Elements</span></span>

|<span data-ttu-id="ad9e1-113">要素</span><span class="sxs-lookup"><span data-stu-id="ad9e1-113">Element</span></span>|<span data-ttu-id="ad9e1-114">説明</span><span class="sxs-lookup"><span data-stu-id="ad9e1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad9e1-115">ListControl (形式) のリスト項目の ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="ad9e1-115">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="ad9e1-116">プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ad9e1-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ad9e1-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ad9e1-117">Text Value</span></span>

<span data-ttu-id="ad9e1-118">プロパティまたはスクリプトの値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9e1-118">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad9e1-119">コメント</span><span class="sxs-lookup"><span data-stu-id="ad9e1-119">Remarks</span></span>

<span data-ttu-id="ad9e1-120">ラベルが指定されていない場合、プロパティまたはスクリプトの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad9e1-120">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="ad9e1-121">リスト ビューでのラベルの使用に関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="ad9e1-121">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ad9e1-122">例</span><span class="sxs-lookup"><span data-stu-id="ad9e1-122">Example</span></span>

<span data-ttu-id="ad9e1-123">次の例では、行にラベルを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad9e1-123">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="ad9e1-124">参照</span><span class="sxs-lookup"><span data-stu-id="ad9e1-124">See Also</span></span>

[<span data-ttu-id="ad9e1-125">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="ad9e1-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ad9e1-126">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ad9e1-126">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="ad9e1-127">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="ad9e1-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
