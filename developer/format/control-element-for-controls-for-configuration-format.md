---
title: コントロールの構成 (形式) の control 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858888"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="18e89-102">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="18e89-102">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="18e89-103">書式設定ファイルと、コントロールを参照するために使用される名前のすべてのビューで使用できる一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="18e89-103">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="18e89-104">構成 (形式) のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="18e89-104">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="18e89-105">構文</span><span class="sxs-lookup"><span data-stu-id="18e89-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="18e89-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="18e89-106">Attributes and Elements</span></span>

<span data-ttu-id="18e89-107">次のセクションでは、属性、子要素、および親要素について説明します、`Control`要素。</span><span class="sxs-lookup"><span data-stu-id="18e89-107">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="18e89-108">各子要素の 1 つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18e89-108">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="18e89-109">属性</span><span class="sxs-lookup"><span data-stu-id="18e89-109">Attributes</span></span>

<span data-ttu-id="18e89-110">なし。</span><span class="sxs-lookup"><span data-stu-id="18e89-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="18e89-111">子要素</span><span class="sxs-lookup"><span data-stu-id="18e89-111">Child Elements</span></span>

|<span data-ttu-id="18e89-112">要素</span><span class="sxs-lookup"><span data-stu-id="18e89-112">Element</span></span>|<span data-ttu-id="18e89-113">説明</span><span class="sxs-lookup"><span data-stu-id="18e89-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="18e89-114">構成 (形式) のコントロールのコントロールのカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="18e89-114">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="18e89-115">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="18e89-115">Required element.</span></span><br /><br /> <span data-ttu-id="18e89-116">コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="18e89-116">Defines the control.</span></span>|
|[<span data-ttu-id="18e89-117">構成 (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="18e89-117">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="18e89-118">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="18e89-118">Required element.</span></span><br /><br /> <span data-ttu-id="18e89-119">コントロールを参照するための名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="18e89-119">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="18e89-120">親要素</span><span class="sxs-lookup"><span data-stu-id="18e89-120">Parent Elements</span></span>

|<span data-ttu-id="18e89-121">要素</span><span class="sxs-lookup"><span data-stu-id="18e89-121">Element</span></span>|<span data-ttu-id="18e89-122">説明</span><span class="sxs-lookup"><span data-stu-id="18e89-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="18e89-123">構成 (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="18e89-123">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="18e89-124">書式設定ファイルのすべてのビューで、またはその他のコントロールで使用できる一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="18e89-124">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="18e89-125">コメント</span><span class="sxs-lookup"><span data-stu-id="18e89-125">Remarks</span></span>

<span data-ttu-id="18e89-126">このコントロールに指定された名前は、次の要素で参照できます。</span><span class="sxs-lookup"><span data-stu-id="18e89-126">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="18e89-127">ExpressionBinding 要素 CustomItem (形式)</span><span class="sxs-lookup"><span data-stu-id="18e89-127">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="18e89-128">View(Format) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="18e89-128">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="18e89-129">参照</span><span class="sxs-lookup"><span data-stu-id="18e89-129">See Also</span></span>

[<span data-ttu-id="18e89-130">構成 (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="18e89-130">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="18e89-131">構成 (形式) のコントロールのカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="18e89-131">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="18e89-132">ExpressionBinding 要素 CustomItem (形式)</span><span class="sxs-lookup"><span data-stu-id="18e89-132">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="18e89-133">View(Format) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="18e89-133">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="18e89-134">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="18e89-134">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="18e89-135">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="18e89-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
