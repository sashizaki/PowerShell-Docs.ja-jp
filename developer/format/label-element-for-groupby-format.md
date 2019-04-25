---
title: GroupBy (形式) の要素にラベルを付ける |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3351d237-e8c2-4ec5-9500-4eceadb407c2
caps.latest.revision: 11
ms.openlocfilehash: e7158711c60d13c745bbdfab9b1b9fc7d98b34e2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065412"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="e16f6-102">GroupBy の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e16f6-102">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="e16f6-103">新しいグループが発生したときに表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="e16f6-103">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="e16f6-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) の GroupBy (形式) のビュー (形式) ラベル要素の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="e16f6-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e16f6-105">構文</span><span class="sxs-lookup"><span data-stu-id="e16f6-105">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e16f6-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e16f6-106">Attributes and Elements</span></span>

<span data-ttu-id="e16f6-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Label`要素。</span><span class="sxs-lookup"><span data-stu-id="e16f6-107">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e16f6-108">属性</span><span class="sxs-lookup"><span data-stu-id="e16f6-108">Attributes</span></span>

<span data-ttu-id="e16f6-109">なし。</span><span class="sxs-lookup"><span data-stu-id="e16f6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e16f6-110">子要素</span><span class="sxs-lookup"><span data-stu-id="e16f6-110">Child Elements</span></span>

<span data-ttu-id="e16f6-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e16f6-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e16f6-112">親要素</span><span class="sxs-lookup"><span data-stu-id="e16f6-112">Parent Elements</span></span>

|<span data-ttu-id="e16f6-113">要素</span><span class="sxs-lookup"><span data-stu-id="e16f6-113">Element</span></span>|<span data-ttu-id="e16f6-114">説明</span><span class="sxs-lookup"><span data-stu-id="e16f6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e16f6-115">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="e16f6-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="e16f6-116">オブジェクトの新しいグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e16f6-116">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e16f6-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e16f6-117">Text Value</span></span>

<span data-ttu-id="e16f6-118">Windows PowerShell が新しいプロパティまたはスクリプトの値を検出するたびに表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="e16f6-118">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="e16f6-119">コメント</span><span class="sxs-lookup"><span data-stu-id="e16f6-119">Remarks</span></span>

<span data-ttu-id="e16f6-120">この要素で指定されたテキスト、だけでなく Windows PowerShell には、グループを開始し、グループの前後に空白行を追加した新しい値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e16f6-120">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="e16f6-121">例</span><span class="sxs-lookup"><span data-stu-id="e16f6-121">Example</span></span>

<span data-ttu-id="e16f6-122">次の例では、新しいグループのラベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e16f6-122">The following example shows the label for a new group.</span></span> <span data-ttu-id="e16f6-123">表示されるラベルは、次のようになります。 `Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="e16f6-123">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="e16f6-124">この要素を含む完全な書式設定ファイルの例は、次を参照してください。[表示幅が広い (GroupBy)](./wide-view-groupby.md)します。</span><span class="sxs-lookup"><span data-stu-id="e16f6-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e16f6-125">参照</span><span class="sxs-lookup"><span data-stu-id="e16f6-125">See Also</span></span>

[<span data-ttu-id="e16f6-126">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="e16f6-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="e16f6-127">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="e16f6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
