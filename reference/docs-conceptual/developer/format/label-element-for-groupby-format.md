---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の Label 要素 (書式)
description: GroupBy の Label 要素 (書式)
ms.openlocfilehash: ff4b0dec01bb5b472b1813540661791b91568eed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649784"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="479f7-103">GroupBy の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="479f7-103">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="479f7-104">新しいグループが検出されたときに表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="479f7-104">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="479f7-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) groupby のビュー (format) Label 要素の groupby (形式)</span><span class="sxs-lookup"><span data-stu-id="479f7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="479f7-106">構文</span><span class="sxs-lookup"><span data-stu-id="479f7-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="479f7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="479f7-107">Attributes and Elements</span></span>

<span data-ttu-id="479f7-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Label` ます。</span><span class="sxs-lookup"><span data-stu-id="479f7-108">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="479f7-109">属性</span><span class="sxs-lookup"><span data-stu-id="479f7-109">Attributes</span></span>

<span data-ttu-id="479f7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="479f7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="479f7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="479f7-111">Child Elements</span></span>

<span data-ttu-id="479f7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="479f7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="479f7-113">親要素</span><span class="sxs-lookup"><span data-stu-id="479f7-113">Parent Elements</span></span>

|<span data-ttu-id="479f7-114">要素</span><span class="sxs-lookup"><span data-stu-id="479f7-114">Element</span></span>|<span data-ttu-id="479f7-115">説明</span><span class="sxs-lookup"><span data-stu-id="479f7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="479f7-116">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="479f7-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="479f7-117">オブジェクトの新しいグループをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="479f7-117">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="479f7-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="479f7-118">Text Value</span></span>

<span data-ttu-id="479f7-119">Windows PowerShell で新しいプロパティまたはスクリプト値が検出されたときに表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="479f7-119">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="479f7-120">解説</span><span class="sxs-lookup"><span data-stu-id="479f7-120">Remarks</span></span>

<span data-ttu-id="479f7-121">Windows PowerShell では、この要素で指定されたテキストに加えて、グループを開始する新しい値が表示され、グループの前後に空白行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="479f7-121">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="479f7-122">例</span><span class="sxs-lookup"><span data-stu-id="479f7-122">Example</span></span>

<span data-ttu-id="479f7-123">次の例は、新しいグループのラベルを示しています。</span><span class="sxs-lookup"><span data-stu-id="479f7-123">The following example shows the label for a new group.</span></span> <span data-ttu-id="479f7-124">表示されるラベルは次のようになります。 `Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="479f7-124">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="479f7-125">この要素を含む完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="479f7-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="479f7-126">参照</span><span class="sxs-lookup"><span data-stu-id="479f7-126">See Also</span></span>

[<span data-ttu-id="479f7-127">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="479f7-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="479f7-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="479f7-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
