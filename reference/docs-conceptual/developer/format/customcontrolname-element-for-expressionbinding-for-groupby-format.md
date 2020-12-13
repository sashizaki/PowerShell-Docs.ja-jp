---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の ExpressionBinding の CustomControlName 要素 (書式)
description: GroupBy の ExpressionBinding の CustomControlName 要素 (書式)
ms.openlocfilehash: bb7dbd449137628da1794628c5a7d7e10158dd46
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655433"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="0d99a-103">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d99a-103">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="0d99a-104">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d99a-104">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="0d99a-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d99a-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="0d99a-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素を groupby (形式) CustomEntry の CustomControl の CustomEntries 要素 CustomControl for groupby (format) Customentries 要素の CustomEntry for groupby (format) 式のバインド要素 groupby (形式) の式のバインドのための、groupby (format) CustomControlName 要素のバインド要素</span><span class="sxs-lookup"><span data-stu-id="0d99a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0d99a-107">構文</span><span class="sxs-lookup"><span data-stu-id="0d99a-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0d99a-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0d99a-108">Attributes and Elements</span></span>

<span data-ttu-id="0d99a-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="0d99a-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0d99a-110">属性</span><span class="sxs-lookup"><span data-stu-id="0d99a-110">Attributes</span></span>

<span data-ttu-id="0d99a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="0d99a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0d99a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="0d99a-112">Child Elements</span></span>

<span data-ttu-id="0d99a-113">なし。</span><span class="sxs-lookup"><span data-stu-id="0d99a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0d99a-114">親要素</span><span class="sxs-lookup"><span data-stu-id="0d99a-114">Parent Elements</span></span>

|<span data-ttu-id="0d99a-115">要素</span><span class="sxs-lookup"><span data-stu-id="0d99a-115">Element</span></span>|<span data-ttu-id="0d99a-116">説明</span><span class="sxs-lookup"><span data-stu-id="0d99a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0d99a-117">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d99a-117">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="0d99a-118">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="0d99a-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0d99a-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="0d99a-119">Text Value</span></span>

<span data-ttu-id="0d99a-120">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d99a-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d99a-121">解説</span><span class="sxs-lookup"><span data-stu-id="0d99a-121">Remarks</span></span>

<span data-ttu-id="0d99a-122">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d99a-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="0d99a-123">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d99a-123">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="0d99a-124">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d99a-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="0d99a-125">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d99a-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="0d99a-126">参照</span><span class="sxs-lookup"><span data-stu-id="0d99a-126">See Also</span></span>

[<span data-ttu-id="0d99a-127">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d99a-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="0d99a-128">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d99a-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="0d99a-129">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d99a-129">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="0d99a-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="0d99a-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
