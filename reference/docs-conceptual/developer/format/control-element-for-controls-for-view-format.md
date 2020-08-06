---
title: ビューのコントロールの Control 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13ea2f09aec7fea8e5460197f133b5f5219cd369
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783808"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="ab596-102">View の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="ab596-103">ビューで使用できるコントロールと、コントロールを参照するために使用される名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="ab596-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="ab596-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ab596-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ab596-105">構文</span><span class="sxs-lookup"><span data-stu-id="ab596-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ab596-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ab596-106">Attributes and Elements</span></span>

<span data-ttu-id="ab596-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `Control` ます。</span><span class="sxs-lookup"><span data-stu-id="ab596-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ab596-108">属性</span><span class="sxs-lookup"><span data-stu-id="ab596-108">Attributes</span></span>

<span data-ttu-id="ab596-109">なし。</span><span class="sxs-lookup"><span data-stu-id="ab596-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ab596-110">子要素</span><span class="sxs-lookup"><span data-stu-id="ab596-110">Child Elements</span></span>

|<span data-ttu-id="ab596-111">要素</span><span class="sxs-lookup"><span data-stu-id="ab596-111">Element</span></span>|<span data-ttu-id="ab596-112">説明</span><span class="sxs-lookup"><span data-stu-id="ab596-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab596-113">ビューのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ab596-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="ab596-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="ab596-114">Required element.</span></span><br /><br /> <span data-ttu-id="ab596-115">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab596-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="ab596-116">View の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="ab596-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="ab596-117">Required element.</span></span><br /><br /> <span data-ttu-id="ab596-118">このビューによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="ab596-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ab596-119">親要素</span><span class="sxs-lookup"><span data-stu-id="ab596-119">Parent Elements</span></span>

|<span data-ttu-id="ab596-120">要素</span><span class="sxs-lookup"><span data-stu-id="ab596-120">Element</span></span>|<span data-ttu-id="ab596-121">説明</span><span class="sxs-lookup"><span data-stu-id="ab596-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab596-122">Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ab596-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="ab596-123">特定のビューで使用できるビューコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="ab596-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ab596-124">解説</span><span class="sxs-lookup"><span data-stu-id="ab596-124">Remarks</span></span>

<span data-ttu-id="ab596-125">このコントロールは、次の要素によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="ab596-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="ab596-126">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="ab596-127">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="ab596-128">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="ab596-129">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="ab596-130">参照</span><span class="sxs-lookup"><span data-stu-id="ab596-130">See Also</span></span>

[<span data-ttu-id="ab596-131">View の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="ab596-132">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="ab596-133">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ab596-134">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ab596-135">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ab596-136">Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ab596-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="ab596-137">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab596-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="ab596-138">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ab596-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
