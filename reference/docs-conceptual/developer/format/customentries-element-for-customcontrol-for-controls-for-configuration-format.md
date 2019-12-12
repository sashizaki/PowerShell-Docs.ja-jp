---
title: Configuration 用のコントロールの CustomControl の CustomEntries 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fc4de2-208f-4506-9a6a-c2675bb83be4
caps.latest.revision: 11
ms.openlocfilehash: abef6c91500f665c2366f221496d4cfd6444f5c9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368821"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="ab9f7-102">Configuration の Controls の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab9f7-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="ab9f7-103">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-103">Provides the definitions of a common control.</span></span> <span data-ttu-id="ab9f7-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="ab9f7-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式</span><span class="sxs-lookup"><span data-stu-id="ab9f7-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ab9f7-106">構文</span><span class="sxs-lookup"><span data-stu-id="ab9f7-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="ab9f7-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ab9f7-107">Attributes and Elements</span></span>

<span data-ttu-id="ab9f7-108">次のセクションでは、`CustomEntries` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="ab9f7-109">1つまたは複数の子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ab9f7-110">属性</span><span class="sxs-lookup"><span data-stu-id="ab9f7-110">Attributes</span></span>

<span data-ttu-id="ab9f7-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ab9f7-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ab9f7-112">Child Elements</span></span>

|<span data-ttu-id="ab9f7-113">要素</span><span class="sxs-lookup"><span data-stu-id="ab9f7-113">Element</span></span>|<span data-ttu-id="ab9f7-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="ab9f7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab9f7-115">CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)</span><span class="sxs-lookup"><span data-stu-id="ab9f7-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="ab9f7-116">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-116">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ab9f7-117">親要素</span><span class="sxs-lookup"><span data-stu-id="ab9f7-117">Parent Elements</span></span>

|<span data-ttu-id="ab9f7-118">要素</span><span class="sxs-lookup"><span data-stu-id="ab9f7-118">Element</span></span>|<span data-ttu-id="ab9f7-119">[説明]</span><span class="sxs-lookup"><span data-stu-id="ab9f7-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab9f7-120">構成用のコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ab9f7-120">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="ab9f7-121">共通コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-121">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ab9f7-122">コメント</span><span class="sxs-lookup"><span data-stu-id="ab9f7-122">Remarks</span></span>

<span data-ttu-id="ab9f7-123">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの `CustomEntry` 要素で定義されます。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-123">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="ab9f7-124">ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-124">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="ab9f7-125">このような場合は、オブジェクトまたはオブジェクトのセットごとに `CustomEntry` 要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="ab9f7-125">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab9f7-126">参照</span><span class="sxs-lookup"><span data-stu-id="ab9f7-126">See Also</span></span>

[<span data-ttu-id="ab9f7-127">構成用のコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ab9f7-127">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="ab9f7-128">CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)</span><span class="sxs-lookup"><span data-stu-id="ab9f7-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="ab9f7-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ab9f7-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
