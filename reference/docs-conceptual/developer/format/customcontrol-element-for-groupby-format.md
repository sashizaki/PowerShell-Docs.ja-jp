---
title: GroupBy (Format) の CustomControl 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2472e256-8f4f-4288-8b67-a3300649dafa
caps.latest.revision: 9
ms.openlocfilehash: 2e84e770a345e272d4c5917b00afe7520840e1db
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368961"
---
# <a name="customcontrol-element-for-groupby-format"></a><span data-ttu-id="2ce6c-102">GroupBy の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2ce6c-102">CustomControl Element for GroupBy (Format)</span></span>

<span data-ttu-id="2ce6c-103">新しいグループを表示するカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="2ce6c-103">Defines the custom control that displays the new group.</span></span>

<span data-ttu-id="2ce6c-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) groupby 要素 (format) の CustomControl 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ce6c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2ce6c-105">構文</span><span class="sxs-lookup"><span data-stu-id="2ce6c-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
<CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2ce6c-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2ce6c-106">Attributes and Elements</span></span>

<span data-ttu-id="2ce6c-107">次のセクションでは、`CustomControl` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ce6c-107">The following sections describe the attributes, child elements, and parent element of the `CustomControl` element.</span></span> <span data-ttu-id="2ce6c-108">任意の数の子要素を指定し、任意の順序で一覧表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2ce6c-108">You can specify any number of child elements and list them in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="2ce6c-109">属性</span><span class="sxs-lookup"><span data-stu-id="2ce6c-109">Attributes</span></span>

<span data-ttu-id="2ce6c-110">なし。</span><span class="sxs-lookup"><span data-stu-id="2ce6c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2ce6c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="2ce6c-111">Child Elements</span></span>

|<span data-ttu-id="2ce6c-112">要素</span><span class="sxs-lookup"><span data-stu-id="2ce6c-112">Element</span></span>|<span data-ttu-id="2ce6c-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="2ce6c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2ce6c-114">GroupBy (Format) の CustomControl の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="2ce6c-114">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="2ce6c-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="2ce6c-115">Required element.</span></span><br /><br /> <span data-ttu-id="2ce6c-116">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="2ce6c-116">Provides the definitions for the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2ce6c-117">親要素</span><span class="sxs-lookup"><span data-stu-id="2ce6c-117">Parent Elements</span></span>

|<span data-ttu-id="2ce6c-118">要素</span><span class="sxs-lookup"><span data-stu-id="2ce6c-118">Element</span></span>|<span data-ttu-id="2ce6c-119">[説明]</span><span class="sxs-lookup"><span data-stu-id="2ce6c-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2ce6c-120">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2ce6c-120">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="2ce6c-121">Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="2ce6c-121">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2ce6c-122">コメント</span><span class="sxs-lookup"><span data-stu-id="2ce6c-122">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="2ce6c-123">参照</span><span class="sxs-lookup"><span data-stu-id="2ce6c-123">See Also</span></span>

[<span data-ttu-id="2ce6c-124">GroupBy (Format) の CustomControl の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="2ce6c-124">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="2ce6c-125">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2ce6c-125">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="2ce6c-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2ce6c-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
