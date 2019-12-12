---
title: 構成用コントロールのコントロールの CustomControl 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9d92a9e-c680-46ca-962e-e82452726953
caps.latest.revision: 10
ms.openlocfilehash: 1d72ce5b18e89bd81c7f81b27f4b8c60bed99764
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368971"
---
# <a name="customcontrol-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="5d44d-102">Configuration の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5d44d-102">CustomControl Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="5d44d-103">コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d44d-103">Defines a control.</span></span> <span data-ttu-id="5d44d-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d44d-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="5d44d-105">Configuration 要素 (Format) コントロールの構成 (format) CustomControl 要素のコントロール要素の構成 (形式) のコントロールの要素</span><span class="sxs-lookup"><span data-stu-id="5d44d-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5d44d-106">構文</span><span class="sxs-lookup"><span data-stu-id="5d44d-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5d44d-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5d44d-107">Attributes and Elements</span></span>

<span data-ttu-id="5d44d-108">次のセクションでは、`CustomControl` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d44d-108">The following sections describe the attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="5d44d-109">この要素には、少なくとも1つの子要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="5d44d-109">This element must have at least one child element.</span></span> <span data-ttu-id="5d44d-110">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="5d44d-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="5d44d-111">属性</span><span class="sxs-lookup"><span data-stu-id="5d44d-111">Attributes</span></span>

<span data-ttu-id="5d44d-112">なし。</span><span class="sxs-lookup"><span data-stu-id="5d44d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5d44d-113">子要素</span><span class="sxs-lookup"><span data-stu-id="5d44d-113">Child Elements</span></span>

|<span data-ttu-id="5d44d-114">要素</span><span class="sxs-lookup"><span data-stu-id="5d44d-114">Element</span></span>|<span data-ttu-id="5d44d-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="5d44d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d44d-116">Configuration の CustomControl の CustomEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5d44d-116">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="5d44d-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="5d44d-117">Required element.</span></span><br /><br /> <span data-ttu-id="5d44d-118">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="5d44d-118">Provides the definitions of a control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5d44d-119">親要素</span><span class="sxs-lookup"><span data-stu-id="5d44d-119">Parent Elements</span></span>

|<span data-ttu-id="5d44d-120">要素</span><span class="sxs-lookup"><span data-stu-id="5d44d-120">Element</span></span>|<span data-ttu-id="5d44d-121">[説明]</span><span class="sxs-lookup"><span data-stu-id="5d44d-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d44d-122">Configuration のコントロールの Control 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5d44d-122">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="5d44d-123">書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d44d-123">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5d44d-124">コメント</span><span class="sxs-lookup"><span data-stu-id="5d44d-124">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="5d44d-125">参照</span><span class="sxs-lookup"><span data-stu-id="5d44d-125">See Also</span></span>

[<span data-ttu-id="5d44d-126">Configuration のコントロールの Control 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5d44d-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="5d44d-127">Configuration の CustomControl の CustomEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5d44d-127">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="5d44d-128">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="5d44d-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
