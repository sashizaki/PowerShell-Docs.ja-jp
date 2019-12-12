---
title: GroupBy (Format) の Label 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3351d237-e8c2-4ec5-9500-4eceadb407c2
caps.latest.revision: 11
ms.openlocfilehash: e7158711c60d13c745bbdfab9b1b9fc7d98b34e2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365201"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="72f6a-102">GroupBy の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="72f6a-102">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="72f6a-103">新しいグループが検出されたときに表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="72f6a-103">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="72f6a-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) groupby のビュー (format) Label 要素の groupby (形式)</span><span class="sxs-lookup"><span data-stu-id="72f6a-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="72f6a-105">構文</span><span class="sxs-lookup"><span data-stu-id="72f6a-105">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="72f6a-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="72f6a-106">Attributes and Elements</span></span>

<span data-ttu-id="72f6a-107">次のセクションでは、`Label` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="72f6a-107">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="72f6a-108">属性</span><span class="sxs-lookup"><span data-stu-id="72f6a-108">Attributes</span></span>

<span data-ttu-id="72f6a-109">なし。</span><span class="sxs-lookup"><span data-stu-id="72f6a-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="72f6a-110">子要素</span><span class="sxs-lookup"><span data-stu-id="72f6a-110">Child Elements</span></span>

<span data-ttu-id="72f6a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="72f6a-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="72f6a-112">親要素</span><span class="sxs-lookup"><span data-stu-id="72f6a-112">Parent Elements</span></span>

|<span data-ttu-id="72f6a-113">要素</span><span class="sxs-lookup"><span data-stu-id="72f6a-113">Element</span></span>|<span data-ttu-id="72f6a-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="72f6a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="72f6a-115">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="72f6a-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="72f6a-116">オブジェクトの新しいグループをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="72f6a-116">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="72f6a-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="72f6a-117">Text Value</span></span>

<span data-ttu-id="72f6a-118">Windows PowerShell で新しいプロパティまたはスクリプト値が検出されたときに表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="72f6a-118">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="72f6a-119">コメント</span><span class="sxs-lookup"><span data-stu-id="72f6a-119">Remarks</span></span>

<span data-ttu-id="72f6a-120">Windows PowerShell では、この要素で指定されたテキストに加えて、グループを開始する新しい値が表示され、グループの前後に空白行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="72f6a-120">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="72f6a-121">例</span><span class="sxs-lookup"><span data-stu-id="72f6a-121">Example</span></span>

<span data-ttu-id="72f6a-122">次の例は、新しいグループのラベルを示しています。</span><span class="sxs-lookup"><span data-stu-id="72f6a-122">The following example shows the label for a new group.</span></span> <span data-ttu-id="72f6a-123">表示されるラベルは次のようになります: `Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="72f6a-123">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="72f6a-124">この要素を含む完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72f6a-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72f6a-125">参照</span><span class="sxs-lookup"><span data-stu-id="72f6a-125">See Also</span></span>

[<span data-ttu-id="72f6a-126">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="72f6a-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="72f6a-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="72f6a-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
