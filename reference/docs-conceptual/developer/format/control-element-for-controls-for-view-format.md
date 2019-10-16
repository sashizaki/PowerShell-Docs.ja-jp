---
title: ビューのコントロールの Control 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fd53f55-698d-4df5-bb9a-fe28dc3193e1
caps.latest.revision: 11
ms.openlocfilehash: df568ccb36a2646b983622cdf95718dd5cac62c3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363471"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="80674-102">View の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="80674-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="80674-103">ビューで使用できるコントロールと、コントロールを参照するために使用される名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="80674-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="80674-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="80674-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="80674-105">構文</span><span class="sxs-lookup"><span data-stu-id="80674-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="80674-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="80674-106">Attributes and Elements</span></span>

<span data-ttu-id="80674-107">次のセクションでは、`Control` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="80674-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="80674-108">属性</span><span class="sxs-lookup"><span data-stu-id="80674-108">Attributes</span></span>

<span data-ttu-id="80674-109">なし。</span><span class="sxs-lookup"><span data-stu-id="80674-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="80674-110">子要素</span><span class="sxs-lookup"><span data-stu-id="80674-110">Child Elements</span></span>

|<span data-ttu-id="80674-111">要素</span><span class="sxs-lookup"><span data-stu-id="80674-111">Element</span></span>|<span data-ttu-id="80674-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="80674-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="80674-113">ビューのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="80674-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="80674-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="80674-114">Required element.</span></span><br /><br /> <span data-ttu-id="80674-115">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="80674-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="80674-116">View (Format) コントロールのコントロールの CustomControl 要素</span><span class="sxs-lookup"><span data-stu-id="80674-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="80674-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="80674-117">Required element.</span></span><br /><br /> <span data-ttu-id="80674-118">このビューによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="80674-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="80674-119">親要素</span><span class="sxs-lookup"><span data-stu-id="80674-119">Parent Elements</span></span>

|<span data-ttu-id="80674-120">要素</span><span class="sxs-lookup"><span data-stu-id="80674-120">Element</span></span>|<span data-ttu-id="80674-121">[説明]</span><span class="sxs-lookup"><span data-stu-id="80674-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="80674-122">Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="80674-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="80674-123">特定のビューで使用できるビューコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="80674-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="80674-124">コメント</span><span class="sxs-lookup"><span data-stu-id="80674-124">Remarks</span></span>

<span data-ttu-id="80674-125">このコントロールは、次の要素によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="80674-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="80674-126">ビューのコントロール (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="80674-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="80674-127">CustomControl for View (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="80674-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="80674-128">GroupBy (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="80674-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="80674-129">GroupBy (Format) の CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="80674-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="80674-130">参照</span><span class="sxs-lookup"><span data-stu-id="80674-130">See Also</span></span>

[<span data-ttu-id="80674-131">View (Format) コントロールのコントロールの CustomControl 要素</span><span class="sxs-lookup"><span data-stu-id="80674-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="80674-132">ビューのコントロール (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="80674-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="80674-133">CustomControl for View (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="80674-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="80674-134">GroupBy (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="80674-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="80674-135">GroupBy (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="80674-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="80674-136">Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="80674-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="80674-137">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="80674-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="80674-138">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="80674-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
