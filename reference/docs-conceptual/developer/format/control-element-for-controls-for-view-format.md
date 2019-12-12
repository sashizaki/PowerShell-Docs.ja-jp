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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363471"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="24ced-102">View の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24ced-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="24ced-103">ビューで使用できるコントロールと、コントロールを参照するために使用される名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="24ced-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="24ced-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="24ced-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="24ced-105">構文</span><span class="sxs-lookup"><span data-stu-id="24ced-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="24ced-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="24ced-106">Attributes and Elements</span></span>

<span data-ttu-id="24ced-107">次のセクションでは、`Control` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="24ced-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="24ced-108">属性</span><span class="sxs-lookup"><span data-stu-id="24ced-108">Attributes</span></span>

<span data-ttu-id="24ced-109">なし。</span><span class="sxs-lookup"><span data-stu-id="24ced-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="24ced-110">子要素</span><span class="sxs-lookup"><span data-stu-id="24ced-110">Child Elements</span></span>

|<span data-ttu-id="24ced-111">要素</span><span class="sxs-lookup"><span data-stu-id="24ced-111">Element</span></span>|<span data-ttu-id="24ced-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="24ced-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24ced-113">ビューのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="24ced-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="24ced-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="24ced-114">Required element.</span></span><br /><br /> <span data-ttu-id="24ced-115">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="24ced-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="24ced-116">View (Format) コントロールのコントロールの CustomControl 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="24ced-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="24ced-117">Required element.</span></span><br /><br /> <span data-ttu-id="24ced-118">このビューによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="24ced-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="24ced-119">親要素</span><span class="sxs-lookup"><span data-stu-id="24ced-119">Parent Elements</span></span>

|<span data-ttu-id="24ced-120">要素</span><span class="sxs-lookup"><span data-stu-id="24ced-120">Element</span></span>|<span data-ttu-id="24ced-121">[説明]</span><span class="sxs-lookup"><span data-stu-id="24ced-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24ced-122">Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="24ced-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="24ced-123">特定のビューで使用できるビューコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="24ced-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="24ced-124">コメント</span><span class="sxs-lookup"><span data-stu-id="24ced-124">Remarks</span></span>

<span data-ttu-id="24ced-125">このコントロールは、次の要素によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="24ced-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="24ced-126">ビューのコントロール (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="24ced-127">CustomControl for View (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="24ced-128">GroupBy (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="24ced-129">GroupBy (Format) の CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="24ced-130">参照</span><span class="sxs-lookup"><span data-stu-id="24ced-130">See Also</span></span>

[<span data-ttu-id="24ced-131">View (Format) コントロールのコントロールの CustomControl 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="24ced-132">ビューのコントロール (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="24ced-133">CustomControl for View (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="24ced-134">GroupBy (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="24ced-135">GroupBy (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="24ced-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="24ced-136">Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="24ced-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="24ced-137">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="24ced-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="24ced-138">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="24ced-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
