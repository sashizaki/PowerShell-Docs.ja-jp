---
title: 構成 (形式) のコントロールのカスタム コントロールの要素を CustomEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fc4de2-208f-4506-9a6a-c2675bb83be4
caps.latest.revision: 11
ms.openlocfilehash: abef6c91500f665c2366f221496d4cfd6444f5c9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856308"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="a6093-102">Configuration の Controls の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a6093-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="a6093-103">コモン コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="a6093-103">Provides the definitions of a common control.</span></span> <span data-ttu-id="a6093-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6093-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="a6093-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素形式)</span><span class="sxs-lookup"><span data-stu-id="a6093-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a6093-106">構文</span><span class="sxs-lookup"><span data-stu-id="a6093-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="a6093-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a6093-107">Attributes and Elements</span></span>

<span data-ttu-id="a6093-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntries`要素。</span><span class="sxs-lookup"><span data-stu-id="a6093-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="a6093-109">1 つまたは複数の子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6093-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a6093-110">属性</span><span class="sxs-lookup"><span data-stu-id="a6093-110">Attributes</span></span>

<span data-ttu-id="a6093-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a6093-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a6093-112">子要素</span><span class="sxs-lookup"><span data-stu-id="a6093-112">Child Elements</span></span>

|<span data-ttu-id="a6093-113">要素</span><span class="sxs-lookup"><span data-stu-id="a6093-113">Element</span></span>|<span data-ttu-id="a6093-114">説明</span><span class="sxs-lookup"><span data-stu-id="a6093-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a6093-115">構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a6093-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="a6093-116">コモン コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="a6093-116">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a6093-117">親要素</span><span class="sxs-lookup"><span data-stu-id="a6093-117">Parent Elements</span></span>

|<span data-ttu-id="a6093-118">要素</span><span class="sxs-lookup"><span data-stu-id="a6093-118">Element</span></span>|<span data-ttu-id="a6093-119">説明</span><span class="sxs-lookup"><span data-stu-id="a6093-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a6093-120">構成 (形式) のコントロールのカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="a6093-120">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="a6093-121">一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6093-121">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a6093-122">コメント</span><span class="sxs-lookup"><span data-stu-id="a6093-122">Remarks</span></span>

<span data-ttu-id="a6093-123">ほとんどの場合、コントロールが、1 つで定義されている、1 つだけ定義`CustomEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="a6093-123">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="a6093-124">ただし別の .NET オブジェクトを表示する同じコントロールを使用する場合は、複数の定義を含めることは可能です。</span><span class="sxs-lookup"><span data-stu-id="a6093-124">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="a6093-125">その場合で定義できますを`CustomEntry`要素の各オブジェクトまたはオブジェクトのセット。</span><span class="sxs-lookup"><span data-stu-id="a6093-125">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6093-126">参照</span><span class="sxs-lookup"><span data-stu-id="a6093-126">See Also</span></span>

[<span data-ttu-id="a6093-127">構成 (形式) のコントロールのカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="a6093-127">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="a6093-128">構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a6093-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="a6093-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="a6093-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
