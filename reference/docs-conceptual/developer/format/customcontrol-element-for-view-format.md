---
title: View (Format) の CustomControl 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 660e8fd6531862790a2af7ab27a82e073c230693
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786052"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="bf44a-102">View の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf44a-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="bf44a-103">ビューのカスタムコントロール形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="bf44a-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="bf44a-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf44a-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bf44a-105">構文</span><span class="sxs-lookup"><span data-stu-id="bf44a-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bf44a-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bf44a-106">Attributes and Elements</span></span>

<span data-ttu-id="bf44a-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControl` ます。</span><span class="sxs-lookup"><span data-stu-id="bf44a-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="bf44a-108">1つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf44a-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bf44a-109">属性</span><span class="sxs-lookup"><span data-stu-id="bf44a-109">Attributes</span></span>

<span data-ttu-id="bf44a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="bf44a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bf44a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="bf44a-111">Child Elements</span></span>

|<span data-ttu-id="bf44a-112">要素</span><span class="sxs-lookup"><span data-stu-id="bf44a-112">Element</span></span>|<span data-ttu-id="bf44a-113">説明</span><span class="sxs-lookup"><span data-stu-id="bf44a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf44a-114">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf44a-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="bf44a-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="bf44a-115">Required element.</span></span><br /><br /> <span data-ttu-id="bf44a-116">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf44a-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bf44a-117">親要素</span><span class="sxs-lookup"><span data-stu-id="bf44a-117">Parent Elements</span></span>

|<span data-ttu-id="bf44a-118">要素</span><span class="sxs-lookup"><span data-stu-id="bf44a-118">Element</span></span>|<span data-ttu-id="bf44a-119">説明</span><span class="sxs-lookup"><span data-stu-id="bf44a-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf44a-120">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf44a-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="bf44a-121">1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="bf44a-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bf44a-122">解説</span><span class="sxs-lookup"><span data-stu-id="bf44a-122">Remarks</span></span>

<span data-ttu-id="bf44a-123">ほとんどの場合、各コントロールビューに必要な定義は1つだけですが、同じビューを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bf44a-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="bf44a-124">このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bf44a-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf44a-125">参照</span><span class="sxs-lookup"><span data-stu-id="bf44a-125">See Also</span></span>

[<span data-ttu-id="bf44a-126">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf44a-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bf44a-127">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf44a-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="bf44a-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="bf44a-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
