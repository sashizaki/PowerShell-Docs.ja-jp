---
title: GroupBy (Format) の Label 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 07b4d037472a9dd2329e94576ec10f5b82f46b34
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785780"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="b62da-102">GroupBy の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b62da-102">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="b62da-103">新しいグループが検出されたときに表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b62da-103">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="b62da-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) groupby のビュー (format) Label 要素の groupby (形式)</span><span class="sxs-lookup"><span data-stu-id="b62da-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b62da-105">構文</span><span class="sxs-lookup"><span data-stu-id="b62da-105">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b62da-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b62da-106">Attributes and Elements</span></span>

<span data-ttu-id="b62da-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `Label` ます。</span><span class="sxs-lookup"><span data-stu-id="b62da-107">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b62da-108">属性</span><span class="sxs-lookup"><span data-stu-id="b62da-108">Attributes</span></span>

<span data-ttu-id="b62da-109">なし。</span><span class="sxs-lookup"><span data-stu-id="b62da-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b62da-110">子要素</span><span class="sxs-lookup"><span data-stu-id="b62da-110">Child Elements</span></span>

<span data-ttu-id="b62da-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b62da-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b62da-112">親要素</span><span class="sxs-lookup"><span data-stu-id="b62da-112">Parent Elements</span></span>

|<span data-ttu-id="b62da-113">要素</span><span class="sxs-lookup"><span data-stu-id="b62da-113">Element</span></span>|<span data-ttu-id="b62da-114">説明</span><span class="sxs-lookup"><span data-stu-id="b62da-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b62da-115">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b62da-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="b62da-116">オブジェクトの新しいグループをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="b62da-116">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b62da-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b62da-117">Text Value</span></span>

<span data-ttu-id="b62da-118">Windows PowerShell で新しいプロパティまたはスクリプト値が検出されたときに表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="b62da-118">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="b62da-119">解説</span><span class="sxs-lookup"><span data-stu-id="b62da-119">Remarks</span></span>

<span data-ttu-id="b62da-120">Windows PowerShell では、この要素で指定されたテキストに加えて、グループを開始する新しい値が表示され、グループの前後に空白行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="b62da-120">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="b62da-121">例</span><span class="sxs-lookup"><span data-stu-id="b62da-121">Example</span></span>

<span data-ttu-id="b62da-122">次の例は、新しいグループのラベルを示しています。</span><span class="sxs-lookup"><span data-stu-id="b62da-122">The following example shows the label for a new group.</span></span> <span data-ttu-id="b62da-123">表示されるラベルは次のようになります。`Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="b62da-123">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="b62da-124">この要素を含む完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b62da-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b62da-125">参照</span><span class="sxs-lookup"><span data-stu-id="b62da-125">See Also</span></span>

[<span data-ttu-id="b62da-126">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b62da-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="b62da-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="b62da-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
