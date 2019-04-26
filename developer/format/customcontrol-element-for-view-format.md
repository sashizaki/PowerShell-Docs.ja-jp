---
title: ビュー (形式) の要素をカスタム コントロール |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2edac16c-0b30-4985-ac84-0821aa9a9f6d
caps.latest.revision: 12
ms.openlocfilehash: bd0f7ca4de8dede97d1553cd62884ea45876e0c7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066670"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="872a1-102">View の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="872a1-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="872a1-103">ビューのカスタム コントロールの書式を定義します。</span><span class="sxs-lookup"><span data-stu-id="872a1-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="872a1-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="872a1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="872a1-105">構文</span><span class="sxs-lookup"><span data-stu-id="872a1-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="872a1-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="872a1-106">Attributes and Elements</span></span>

<span data-ttu-id="872a1-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControl`要素。</span><span class="sxs-lookup"><span data-stu-id="872a1-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="872a1-108">1 つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="872a1-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="872a1-109">属性</span><span class="sxs-lookup"><span data-stu-id="872a1-109">Attributes</span></span>

<span data-ttu-id="872a1-110">なし。</span><span class="sxs-lookup"><span data-stu-id="872a1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="872a1-111">子要素</span><span class="sxs-lookup"><span data-stu-id="872a1-111">Child Elements</span></span>

|<span data-ttu-id="872a1-112">要素</span><span class="sxs-lookup"><span data-stu-id="872a1-112">Element</span></span>|<span data-ttu-id="872a1-113">説明</span><span class="sxs-lookup"><span data-stu-id="872a1-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="872a1-114">ビュー (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="872a1-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="872a1-115">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="872a1-115">Required element.</span></span><br /><br /> <span data-ttu-id="872a1-116">カスタム コントロールのビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="872a1-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="872a1-117">親要素</span><span class="sxs-lookup"><span data-stu-id="872a1-117">Parent Elements</span></span>

|<span data-ttu-id="872a1-118">要素</span><span class="sxs-lookup"><span data-stu-id="872a1-118">Element</span></span>|<span data-ttu-id="872a1-119">説明</span><span class="sxs-lookup"><span data-stu-id="872a1-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="872a1-120">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="872a1-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="872a1-121">1 つまたは複数の .NET オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="872a1-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="872a1-122">コメント</span><span class="sxs-lookup"><span data-stu-id="872a1-122">Remarks</span></span>

<span data-ttu-id="872a1-123">ほとんどの場合、1 つだけ定義がそれぞれのコントロール ビューに必要なが同じビューを使用して、さまざまな .NET オブジェクトを表示する場合は、複数の定義を提供することは。</span><span class="sxs-lookup"><span data-stu-id="872a1-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="872a1-124">その場合の各オブジェクトまたはオブジェクトのセットを別の定義を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="872a1-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="872a1-125">参照</span><span class="sxs-lookup"><span data-stu-id="872a1-125">See Also</span></span>

[<span data-ttu-id="872a1-126">ビュー (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="872a1-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="872a1-127">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="872a1-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="872a1-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="872a1-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
