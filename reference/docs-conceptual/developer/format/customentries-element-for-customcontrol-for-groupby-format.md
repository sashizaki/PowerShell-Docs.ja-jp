---
title: GroupBy (Format) の CustomControl の CustomEntries 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2221d1bb94159697ff10466e4606d6d54e117e30
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785950"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="aa19a-102">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa19a-102">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="aa19a-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa19a-103">Provides the definitions for the control.</span></span> <span data-ttu-id="aa19a-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa19a-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="aa19a-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー Element (format) GroupBy 要素の groupby (format) CustomControl 要素を groupby (形式) の CustomControl の CustomEntries 要素に設定します。</span><span class="sxs-lookup"><span data-stu-id="aa19a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aa19a-106">構文</span><span class="sxs-lookup"><span data-stu-id="aa19a-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aa19a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aa19a-107">Attributes and Elements</span></span>

<span data-ttu-id="aa19a-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="aa19a-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="aa19a-109">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="aa19a-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa19a-110">属性</span><span class="sxs-lookup"><span data-stu-id="aa19a-110">Attributes</span></span>

<span data-ttu-id="aa19a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="aa19a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aa19a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="aa19a-112">Child Elements</span></span>

|<span data-ttu-id="aa19a-113">要素</span><span class="sxs-lookup"><span data-stu-id="aa19a-113">Element</span></span>|<span data-ttu-id="aa19a-114">説明</span><span class="sxs-lookup"><span data-stu-id="aa19a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa19a-115">GroupBy の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa19a-115">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="aa19a-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="aa19a-116">Required element.</span></span><br /><br /> <span data-ttu-id="aa19a-117">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa19a-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aa19a-118">親要素</span><span class="sxs-lookup"><span data-stu-id="aa19a-118">Parent Elements</span></span>

|<span data-ttu-id="aa19a-119">要素</span><span class="sxs-lookup"><span data-stu-id="aa19a-119">Element</span></span>|<span data-ttu-id="aa19a-120">説明</span><span class="sxs-lookup"><span data-stu-id="aa19a-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa19a-121">GroupBy の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa19a-121">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="aa19a-122">新しいグループを表示するカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="aa19a-122">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa19a-123">解説</span><span class="sxs-lookup"><span data-stu-id="aa19a-123">Remarks</span></span>

<span data-ttu-id="aa19a-124">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの要素で指定され `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="aa19a-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="aa19a-125">ただし、同じコントロールを使用して異なるグループを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="aa19a-125">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="aa19a-126">そのような場合は、 `CustomEntry` グループの要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="aa19a-126">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa19a-127">参照</span><span class="sxs-lookup"><span data-stu-id="aa19a-127">See Also</span></span>

[<span data-ttu-id="aa19a-128">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa19a-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="aa19a-129">GroupBy の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa19a-129">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="aa19a-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="aa19a-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
