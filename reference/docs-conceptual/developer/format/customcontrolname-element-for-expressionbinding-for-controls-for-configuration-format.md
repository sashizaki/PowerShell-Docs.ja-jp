---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の ExpressionBinding の CustomControlName 要素 (書式)
description: Configuration の Controls の ExpressionBinding の CustomControlName 要素 (書式)
ms.openlocfilehash: 3815956f59f19c0215aaf26b94dede656b9453cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648314"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="6b330-103">Configuration の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6b330-103">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="6b330-104">コモンコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b330-104">Specifies the name of a common control.</span></span> <span data-ttu-id="6b330-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b330-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="6b330-106">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) の CustomControl 要素の構成 (形式) の CustomControl の構成 (書式) の CustomEntries 要素のコントロール要素 CustomControl for Controls の構成 (書式) 用の Customentries 要素のコントロールの構成式のバインド要素の構成のためのコントロールの構成 (format) CustomControlName 要素の構成用コントロールの構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="6b330-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6b330-107">構文</span><span class="sxs-lookup"><span data-stu-id="6b330-107">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6b330-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6b330-108">Attributes and Elements</span></span>

<span data-ttu-id="6b330-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="6b330-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6b330-110">属性</span><span class="sxs-lookup"><span data-stu-id="6b330-110">Attributes</span></span>

<span data-ttu-id="6b330-111">なし。</span><span class="sxs-lookup"><span data-stu-id="6b330-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6b330-112">子要素</span><span class="sxs-lookup"><span data-stu-id="6b330-112">Child Elements</span></span>

<span data-ttu-id="6b330-113">なし。</span><span class="sxs-lookup"><span data-stu-id="6b330-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6b330-114">親要素</span><span class="sxs-lookup"><span data-stu-id="6b330-114">Parent Elements</span></span>

|<span data-ttu-id="6b330-115">要素</span><span class="sxs-lookup"><span data-stu-id="6b330-115">Element</span></span>|<span data-ttu-id="6b330-116">説明</span><span class="sxs-lookup"><span data-stu-id="6b330-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6b330-117">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6b330-117">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="6b330-118">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b330-118">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6b330-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="6b330-119">Text Value</span></span>

<span data-ttu-id="6b330-120">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b330-120">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b330-121">解説</span><span class="sxs-lookup"><span data-stu-id="6b330-121">Remarks</span></span>

<span data-ttu-id="6b330-122">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b330-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="6b330-123">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b330-123">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="6b330-124">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6b330-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="6b330-125">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6b330-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="6b330-126">参照</span><span class="sxs-lookup"><span data-stu-id="6b330-126">See Also</span></span>

[<span data-ttu-id="6b330-127">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6b330-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="6b330-128">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6b330-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="6b330-129">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6b330-129">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="6b330-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="6b330-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
