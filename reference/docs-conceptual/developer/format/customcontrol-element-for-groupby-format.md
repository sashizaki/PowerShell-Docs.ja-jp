---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の CustomControl 要素 (書式)
description: GroupBy の CustomControl 要素 (書式)
ms.openlocfilehash: 633cfcbd10206dc8d7fb4bc1d0092f19aa5bde7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646102"
---
# <a name="customcontrol-element-for-groupby-format"></a><span data-ttu-id="06af4-103">GroupBy の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06af4-103">CustomControl Element for GroupBy (Format)</span></span>

<span data-ttu-id="06af4-104">新しいグループを表示するカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="06af4-104">Defines the custom control that displays the new group.</span></span>

<span data-ttu-id="06af4-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) groupby 要素 (format) の CustomControl 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="06af4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="06af4-106">構文</span><span class="sxs-lookup"><span data-stu-id="06af4-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
<CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="06af4-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="06af4-107">Attributes and Elements</span></span>

<span data-ttu-id="06af4-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControl` ます。</span><span class="sxs-lookup"><span data-stu-id="06af4-108">The following sections describe the attributes, child elements, and parent element of the `CustomControl` element.</span></span> <span data-ttu-id="06af4-109">任意の数の子要素を指定し、任意の順序で一覧表示することができます。</span><span class="sxs-lookup"><span data-stu-id="06af4-109">You can specify any number of child elements and list them in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="06af4-110">属性</span><span class="sxs-lookup"><span data-stu-id="06af4-110">Attributes</span></span>

<span data-ttu-id="06af4-111">なし。</span><span class="sxs-lookup"><span data-stu-id="06af4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="06af4-112">子要素</span><span class="sxs-lookup"><span data-stu-id="06af4-112">Child Elements</span></span>

|<span data-ttu-id="06af4-113">要素</span><span class="sxs-lookup"><span data-stu-id="06af4-113">Element</span></span>|<span data-ttu-id="06af4-114">説明</span><span class="sxs-lookup"><span data-stu-id="06af4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="06af4-115">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06af4-115">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="06af4-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="06af4-116">Required element.</span></span><br /><br /> <span data-ttu-id="06af4-117">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="06af4-117">Provides the definitions for the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="06af4-118">親要素</span><span class="sxs-lookup"><span data-stu-id="06af4-118">Parent Elements</span></span>

|<span data-ttu-id="06af4-119">要素</span><span class="sxs-lookup"><span data-stu-id="06af4-119">Element</span></span>|<span data-ttu-id="06af4-120">説明</span><span class="sxs-lookup"><span data-stu-id="06af4-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="06af4-121">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06af4-121">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="06af4-122">Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="06af4-122">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="06af4-123">解説</span><span class="sxs-lookup"><span data-stu-id="06af4-123">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="06af4-124">参照</span><span class="sxs-lookup"><span data-stu-id="06af4-124">See Also</span></span>

[<span data-ttu-id="06af4-125">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06af4-125">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="06af4-126">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06af4-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="06af4-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="06af4-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
