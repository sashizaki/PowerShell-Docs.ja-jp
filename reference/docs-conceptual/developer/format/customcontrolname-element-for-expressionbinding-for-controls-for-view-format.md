---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の ExpressionBinding の CustomControlName 要素 (書式)
description: View の Controls の ExpressionBinding の CustomControlName 要素 (書式)
ms.openlocfilehash: 35e1554a9eed491f37499a7455e9c5cae3cd9e1e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655446"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="161b2-103">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="161b2-103">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="161b2-104">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="161b2-104">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="161b2-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="161b2-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="161b2-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロール要素 (形式) コントロールのコントロールの要素 (形式) コントロールの要素 (書式) を制御するためのコントロールの CustomControl 要素 (format) CustomControl for ビュー (形式) の CustomEntries 要素ビュー (format) のコントロールに対する CustomEntries の customentries 要素のビュー (形式) のカスタムバインド要素を表示するために、ビュー (format) の CustomControlName 要素に対して、ビューのコントロール (format) のコントロールに対して、ビュー (format) のバインド要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="161b2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) CustomControlName Element for ExpressionBindine for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="161b2-107">構文</span><span class="sxs-lookup"><span data-stu-id="161b2-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="161b2-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="161b2-108">Attributes and Elements</span></span>

<span data-ttu-id="161b2-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="161b2-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="161b2-110">属性</span><span class="sxs-lookup"><span data-stu-id="161b2-110">Attributes</span></span>

<span data-ttu-id="161b2-111">なし。</span><span class="sxs-lookup"><span data-stu-id="161b2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="161b2-112">子要素</span><span class="sxs-lookup"><span data-stu-id="161b2-112">Child Elements</span></span>

<span data-ttu-id="161b2-113">なし。</span><span class="sxs-lookup"><span data-stu-id="161b2-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="161b2-114">親要素</span><span class="sxs-lookup"><span data-stu-id="161b2-114">Parent Elements</span></span>

|<span data-ttu-id="161b2-115">要素</span><span class="sxs-lookup"><span data-stu-id="161b2-115">Element</span></span>|<span data-ttu-id="161b2-116">説明</span><span class="sxs-lookup"><span data-stu-id="161b2-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="161b2-117">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="161b2-117">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="161b2-118">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="161b2-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="161b2-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="161b2-119">Text Value</span></span>

<span data-ttu-id="161b2-120">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="161b2-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="161b2-121">解説</span><span class="sxs-lookup"><span data-stu-id="161b2-121">Remarks</span></span>

<span data-ttu-id="161b2-122">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="161b2-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="161b2-123">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="161b2-123">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="161b2-124">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="161b2-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="161b2-125">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="161b2-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="161b2-126">参照</span><span class="sxs-lookup"><span data-stu-id="161b2-126">See Also</span></span>

[<span data-ttu-id="161b2-127">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="161b2-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="161b2-128">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="161b2-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="161b2-129">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="161b2-129">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="161b2-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="161b2-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
