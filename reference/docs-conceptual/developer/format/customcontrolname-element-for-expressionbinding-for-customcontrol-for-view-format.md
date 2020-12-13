---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)
description: View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)
ms.openlocfilehash: 24b27428c07d7178f0069f6d0e5b7ffc555efe34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666809"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a><span data-ttu-id="b069f-103">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b069f-103">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>

<span data-ttu-id="b069f-104">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b069f-104">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="b069f-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b069f-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="b069f-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) の CustomControl 要素のビュー (format) CustomEntries 要素の CustomControl for view (format) customentries 要素に対して、CustomEntries for view (format) CustomControlName 要素の customentries (format) 式バインドのバインド要素 (形式) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b069f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem (Format) CustomControlName Element for Expression Binding for CustomItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b069f-107">構文</span><span class="sxs-lookup"><span data-stu-id="b069f-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b069f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b069f-108">Attributes and Elements</span></span>

<span data-ttu-id="b069f-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="b069f-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b069f-110">属性</span><span class="sxs-lookup"><span data-stu-id="b069f-110">Attributes</span></span>

<span data-ttu-id="b069f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b069f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b069f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b069f-112">Child Elements</span></span>

<span data-ttu-id="b069f-113">なし。</span><span class="sxs-lookup"><span data-stu-id="b069f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b069f-114">親要素</span><span class="sxs-lookup"><span data-stu-id="b069f-114">Parent Elements</span></span>

|<span data-ttu-id="b069f-115">要素</span><span class="sxs-lookup"><span data-stu-id="b069f-115">Element</span></span>|<span data-ttu-id="b069f-116">説明</span><span class="sxs-lookup"><span data-stu-id="b069f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b069f-117">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b069f-117">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="b069f-118">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="b069f-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b069f-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b069f-119">Text Value</span></span>

<span data-ttu-id="b069f-120">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b069f-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="b069f-121">解説</span><span class="sxs-lookup"><span data-stu-id="b069f-121">Remarks</span></span>

<span data-ttu-id="b069f-122">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成したり、特定のビューで使用できるビューコントロールを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="b069f-122">You can create common controls that can be used by all the views of a formatting file and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="b069f-123">これらのコントロールの名前は、次の要素によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="b069f-123">The names of these controls are specified by the following elements.</span></span>

- [<span data-ttu-id="b069f-124">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b069f-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="b069f-125">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b069f-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="b069f-126">参照</span><span class="sxs-lookup"><span data-stu-id="b069f-126">See Also</span></span>

[<span data-ttu-id="b069f-127">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b069f-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="b069f-128">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b069f-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="b069f-129">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b069f-129">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="b069f-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="b069f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
