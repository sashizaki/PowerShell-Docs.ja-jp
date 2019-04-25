---
title: コントロールの表示 (形式) の control 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fd53f55-698d-4df5-bb9a-fe28dc3193e1
caps.latest.revision: 11
ms.openlocfilehash: df568ccb36a2646b983622cdf95718dd5cac62c3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066772"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="1b643-102">View の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1b643-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="1b643-103">ビューとコントロールを参照するために使用される名前で使用できるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b643-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="1b643-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) では、コントロールの要素 (形式) のコントロール要素を制御表示されます (形式)</span><span class="sxs-lookup"><span data-stu-id="1b643-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1b643-105">構文</span><span class="sxs-lookup"><span data-stu-id="1b643-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1b643-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1b643-106">Attributes and Elements</span></span>

<span data-ttu-id="1b643-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Control`要素。</span><span class="sxs-lookup"><span data-stu-id="1b643-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1b643-108">属性</span><span class="sxs-lookup"><span data-stu-id="1b643-108">Attributes</span></span>

<span data-ttu-id="1b643-109">なし。</span><span class="sxs-lookup"><span data-stu-id="1b643-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1b643-110">子要素</span><span class="sxs-lookup"><span data-stu-id="1b643-110">Child Elements</span></span>

|<span data-ttu-id="1b643-111">要素</span><span class="sxs-lookup"><span data-stu-id="1b643-111">Element</span></span>|<span data-ttu-id="1b643-112">説明</span><span class="sxs-lookup"><span data-stu-id="1b643-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1b643-113">コントロールが表示されます (形式) の name 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="1b643-114">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="1b643-114">Required element.</span></span><br /><br /> <span data-ttu-id="1b643-115">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b643-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="1b643-116">コントロールが表示されます (形式) のコントロールのカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="1b643-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="1b643-117">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="1b643-117">Required element.</span></span><br /><br /> <span data-ttu-id="1b643-118">このビューで使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b643-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1b643-119">親要素</span><span class="sxs-lookup"><span data-stu-id="1b643-119">Parent Elements</span></span>

|<span data-ttu-id="1b643-120">要素</span><span class="sxs-lookup"><span data-stu-id="1b643-120">Element</span></span>|<span data-ttu-id="1b643-121">説明</span><span class="sxs-lookup"><span data-stu-id="1b643-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1b643-122">コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1b643-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="1b643-123">特定のビューで使用できるビュー コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b643-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1b643-124">コメント</span><span class="sxs-lookup"><span data-stu-id="1b643-124">Remarks</span></span>

<span data-ttu-id="1b643-125">このコントロールは、次の要素で指定できます。</span><span class="sxs-lookup"><span data-stu-id="1b643-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="1b643-126">コントロールが表示されます (形式) の ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="1b643-127">ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="1b643-128">GroupBy (形式) の ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="1b643-129">GroupBy (形式) の CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="1b643-130">参照</span><span class="sxs-lookup"><span data-stu-id="1b643-130">See Also</span></span>

[<span data-ttu-id="1b643-131">コントロールが表示されます (形式) のコントロールのカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="1b643-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="1b643-132">コントロールが表示されます (形式) の ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="1b643-133">ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="1b643-134">GroupBy (形式) の ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="1b643-135">GroupBy (形式) の ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="1b643-136">コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1b643-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="1b643-137">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="1b643-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="1b643-138">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="1b643-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
