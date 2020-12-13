---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の Control 要素 (書式)
description: View の Controls の Control 要素 (書式)
ms.openlocfilehash: c48b8b7ecaebfde5e6ed2123b837d92561551766
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668084"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="fa48f-103">View の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-103">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="fa48f-104">ビューで使用できるコントロールと、コントロールを参照するために使用される名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="fa48f-104">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="fa48f-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fa48f-106">構文</span><span class="sxs-lookup"><span data-stu-id="fa48f-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fa48f-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fa48f-107">Attributes and Elements</span></span>

<span data-ttu-id="fa48f-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Control` ます。</span><span class="sxs-lookup"><span data-stu-id="fa48f-108">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fa48f-109">属性</span><span class="sxs-lookup"><span data-stu-id="fa48f-109">Attributes</span></span>

<span data-ttu-id="fa48f-110">なし。</span><span class="sxs-lookup"><span data-stu-id="fa48f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fa48f-111">子要素</span><span class="sxs-lookup"><span data-stu-id="fa48f-111">Child Elements</span></span>

|<span data-ttu-id="fa48f-112">要素</span><span class="sxs-lookup"><span data-stu-id="fa48f-112">Element</span></span>|<span data-ttu-id="fa48f-113">説明</span><span class="sxs-lookup"><span data-stu-id="fa48f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fa48f-114">ビューのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="fa48f-114">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="fa48f-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="fa48f-115">Required element.</span></span><br /><br /> <span data-ttu-id="fa48f-116">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa48f-116">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="fa48f-117">View の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-117">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="fa48f-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="fa48f-118">Required element.</span></span><br /><br /> <span data-ttu-id="fa48f-119">このビューによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="fa48f-119">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fa48f-120">親要素</span><span class="sxs-lookup"><span data-stu-id="fa48f-120">Parent Elements</span></span>

|<span data-ttu-id="fa48f-121">要素</span><span class="sxs-lookup"><span data-stu-id="fa48f-121">Element</span></span>|<span data-ttu-id="fa48f-122">説明</span><span class="sxs-lookup"><span data-stu-id="fa48f-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fa48f-123">Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="fa48f-123">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="fa48f-124">特定のビューで使用できるビューコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="fa48f-124">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fa48f-125">解説</span><span class="sxs-lookup"><span data-stu-id="fa48f-125">Remarks</span></span>

<span data-ttu-id="fa48f-126">このコントロールは、次の要素によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="fa48f-126">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="fa48f-127">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-127">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="fa48f-128">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-128">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="fa48f-129">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-129">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="fa48f-130">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-130">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="fa48f-131">参照</span><span class="sxs-lookup"><span data-stu-id="fa48f-131">See Also</span></span>

[<span data-ttu-id="fa48f-132">View の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-132">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="fa48f-133">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-133">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="fa48f-134">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-134">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="fa48f-135">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="fa48f-136">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-136">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="fa48f-137">Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="fa48f-137">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="fa48f-138">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fa48f-138">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="fa48f-139">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="fa48f-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
