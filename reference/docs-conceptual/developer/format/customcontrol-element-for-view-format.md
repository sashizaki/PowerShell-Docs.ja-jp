---
title: View (Format) の CustomControl 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2edac16c-0b30-4985-ac84-0821aa9a9f6d
caps.latest.revision: 12
ms.openlocfilehash: bd0f7ca4de8dede97d1553cd62884ea45876e0c7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363361"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="91d16-102">View の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="91d16-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="91d16-103">ビューのカスタムコントロール形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="91d16-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="91d16-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="91d16-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91d16-105">構文</span><span class="sxs-lookup"><span data-stu-id="91d16-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91d16-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="91d16-106">Attributes and Elements</span></span>

<span data-ttu-id="91d16-107">次のセクションでは、`CustomControl` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="91d16-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="91d16-108">1つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91d16-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="91d16-109">属性</span><span class="sxs-lookup"><span data-stu-id="91d16-109">Attributes</span></span>

<span data-ttu-id="91d16-110">なし。</span><span class="sxs-lookup"><span data-stu-id="91d16-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91d16-111">子要素</span><span class="sxs-lookup"><span data-stu-id="91d16-111">Child Elements</span></span>

|<span data-ttu-id="91d16-112">要素</span><span class="sxs-lookup"><span data-stu-id="91d16-112">Element</span></span>|<span data-ttu-id="91d16-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="91d16-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91d16-114">CustomControl for View (Format) の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="91d16-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="91d16-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="91d16-115">Required element.</span></span><br /><br /> <span data-ttu-id="91d16-116">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="91d16-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="91d16-117">親要素</span><span class="sxs-lookup"><span data-stu-id="91d16-117">Parent Elements</span></span>

|<span data-ttu-id="91d16-118">要素</span><span class="sxs-lookup"><span data-stu-id="91d16-118">Element</span></span>|<span data-ttu-id="91d16-119">[説明]</span><span class="sxs-lookup"><span data-stu-id="91d16-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91d16-120">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91d16-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="91d16-121">1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="91d16-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="91d16-122">コメント</span><span class="sxs-lookup"><span data-stu-id="91d16-122">Remarks</span></span>

<span data-ttu-id="91d16-123">ほとんどの場合、各コントロールビューに必要な定義は1つだけですが、同じビューを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="91d16-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="91d16-124">このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="91d16-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="91d16-125">参照</span><span class="sxs-lookup"><span data-stu-id="91d16-125">See Also</span></span>

[<span data-ttu-id="91d16-126">CustomControl for View (Format) の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="91d16-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="91d16-127">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91d16-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="91d16-128">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="91d16-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
