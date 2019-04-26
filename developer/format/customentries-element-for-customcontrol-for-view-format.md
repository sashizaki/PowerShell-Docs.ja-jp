---
title: ビュー (形式) のカスタム コントロールの要素を CustomEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb412831-94f7-4054-b19e-32c1b14c66dd
caps.latest.revision: 11
ms.openlocfilehash: 827baacd22ef258dd9b0c8a383a23fce7d975f7f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066517"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="91540-102">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="91540-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="91540-103">カスタム コントロールのビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="91540-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="91540-104">カスタム コントロールのビューには、1 つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91540-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="91540-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries 要素をビュー (形式) のカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="91540-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91540-106">構文</span><span class="sxs-lookup"><span data-stu-id="91540-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91540-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="91540-107">Attributes and Elements</span></span>

<span data-ttu-id="91540-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControlEntries`要素。</span><span class="sxs-lookup"><span data-stu-id="91540-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="91540-109">1 つまたは複数の子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91540-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="91540-110">属性</span><span class="sxs-lookup"><span data-stu-id="91540-110">Attributes</span></span>

<span data-ttu-id="91540-111">なし。</span><span class="sxs-lookup"><span data-stu-id="91540-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91540-112">子要素</span><span class="sxs-lookup"><span data-stu-id="91540-112">Child Elements</span></span>

|<span data-ttu-id="91540-113">要素</span><span class="sxs-lookup"><span data-stu-id="91540-113">Element</span></span>|<span data-ttu-id="91540-114">説明</span><span class="sxs-lookup"><span data-stu-id="91540-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91540-115">表示 (形式) CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="91540-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="91540-116">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="91540-116">Required element.</span></span><br /><br /> <span data-ttu-id="91540-117">カスタム コントロールのビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="91540-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="91540-118">親要素</span><span class="sxs-lookup"><span data-stu-id="91540-118">Parent Elements</span></span>

|<span data-ttu-id="91540-119">要素</span><span class="sxs-lookup"><span data-stu-id="91540-119">Element</span></span>|<span data-ttu-id="91540-120">説明</span><span class="sxs-lookup"><span data-stu-id="91540-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91540-121">カスタム コントロールの要素のビュー (形式)</span><span class="sxs-lookup"><span data-stu-id="91540-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="91540-122">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="91540-122">Required element.</span></span><br /><br /> <span data-ttu-id="91540-123">ビューのカスタム コントロールの書式を定義します。</span><span class="sxs-lookup"><span data-stu-id="91540-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="91540-124">コメント</span><span class="sxs-lookup"><span data-stu-id="91540-124">Remarks</span></span>

<span data-ttu-id="91540-125">ほとんどの場合、コントロールが、1 つで定義されている、1 つだけ定義`CustomEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="91540-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="91540-126">ただし別の .NET オブジェクトを表示する同じコントロールを使用する場合は、複数の定義を含めることは可能です。</span><span class="sxs-lookup"><span data-stu-id="91540-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="91540-127">その場合で定義できますを`CustomEntry`要素の各オブジェクトまたはオブジェクトのセット。</span><span class="sxs-lookup"><span data-stu-id="91540-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="91540-128">参照</span><span class="sxs-lookup"><span data-stu-id="91540-128">See Also</span></span>

[<span data-ttu-id="91540-129">カスタム コントロールの要素のビュー (形式)</span><span class="sxs-lookup"><span data-stu-id="91540-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="91540-130">表示 (形式) CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="91540-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="91540-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="91540-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
