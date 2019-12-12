---
title: CustomControl の CustomEntries 要素のビュー (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb412831-94f7-4054-b19e-32c1b14c66dd
caps.latest.revision: 11
ms.openlocfilehash: 827baacd22ef258dd9b0c8a383a23fce7d975f7f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364081"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="3831d-102">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3831d-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="3831d-103">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="3831d-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="3831d-104">カスタムコントロールビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3831d-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="3831d-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl Element (Format) CustomControl for View (Format) の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="3831d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3831d-106">構文</span><span class="sxs-lookup"><span data-stu-id="3831d-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3831d-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3831d-107">Attributes and Elements</span></span>

<span data-ttu-id="3831d-108">次のセクションでは、`CustomControlEntries` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3831d-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="3831d-109">1つまたは複数の子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3831d-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3831d-110">属性</span><span class="sxs-lookup"><span data-stu-id="3831d-110">Attributes</span></span>

<span data-ttu-id="3831d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="3831d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3831d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="3831d-112">Child Elements</span></span>

|<span data-ttu-id="3831d-113">要素</span><span class="sxs-lookup"><span data-stu-id="3831d-113">Element</span></span>|<span data-ttu-id="3831d-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="3831d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3831d-115">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="3831d-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="3831d-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="3831d-116">Required element.</span></span><br /><br /> <span data-ttu-id="3831d-117">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="3831d-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3831d-118">親要素</span><span class="sxs-lookup"><span data-stu-id="3831d-118">Parent Elements</span></span>

|<span data-ttu-id="3831d-119">要素</span><span class="sxs-lookup"><span data-stu-id="3831d-119">Element</span></span>|<span data-ttu-id="3831d-120">[説明]</span><span class="sxs-lookup"><span data-stu-id="3831d-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3831d-121">View (Format) の CustomControl 要素</span><span class="sxs-lookup"><span data-stu-id="3831d-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="3831d-122">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="3831d-122">Required element.</span></span><br /><br /> <span data-ttu-id="3831d-123">ビューのカスタムコントロール形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="3831d-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3831d-124">コメント</span><span class="sxs-lookup"><span data-stu-id="3831d-124">Remarks</span></span>

<span data-ttu-id="3831d-125">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの `CustomEntry` 要素で定義されます。</span><span class="sxs-lookup"><span data-stu-id="3831d-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="3831d-126">ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3831d-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="3831d-127">このような場合は、オブジェクトまたはオブジェクトのセットごとに `CustomEntry` 要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3831d-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="3831d-128">参照</span><span class="sxs-lookup"><span data-stu-id="3831d-128">See Also</span></span>

[<span data-ttu-id="3831d-129">View (Format) の CustomControl 要素</span><span class="sxs-lookup"><span data-stu-id="3831d-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="3831d-130">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="3831d-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3831d-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="3831d-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
