---
title: 構成用のコントロールの式のバインドの CustomControlName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5242935-2782-4d23-84f5-2446b2b7ba83
caps.latest.revision: 8
ms.openlocfilehash: c9abd9f22907b87323c16d603a9f75bb3d375a03
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364121"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="a5012-102">Configuration の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a5012-102">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="a5012-103">コモンコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5012-103">Specifies the name of a common control.</span></span> <span data-ttu-id="a5012-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5012-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="a5012-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素を構成するためのコントロールの CustomItem 要素の構成 (形式) のためのコントロールに対する customitem のバインド要素の構成 (Format) CustomControlName構成用のコントロールの式のバインドの要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a5012-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a5012-106">構文</span><span class="sxs-lookup"><span data-stu-id="a5012-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a5012-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a5012-107">Attributes and Elements</span></span>

<span data-ttu-id="a5012-108">次のセクションでは、属性、子要素、`CustomControlName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5012-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a5012-109">属性</span><span class="sxs-lookup"><span data-stu-id="a5012-109">Attributes</span></span>

<span data-ttu-id="a5012-110">なし。</span><span class="sxs-lookup"><span data-stu-id="a5012-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a5012-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a5012-111">Child Elements</span></span>

<span data-ttu-id="a5012-112">なし。</span><span class="sxs-lookup"><span data-stu-id="a5012-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a5012-113">親要素</span><span class="sxs-lookup"><span data-stu-id="a5012-113">Parent Elements</span></span>

|<span data-ttu-id="a5012-114">要素</span><span class="sxs-lookup"><span data-stu-id="a5012-114">Element</span></span>|<span data-ttu-id="a5012-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="a5012-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a5012-116">構成用のコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a5012-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="a5012-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="a5012-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a5012-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a5012-118">Text Value</span></span>

<span data-ttu-id="a5012-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5012-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="a5012-120">コメント</span><span class="sxs-lookup"><span data-stu-id="a5012-120">Remarks</span></span>

<span data-ttu-id="a5012-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5012-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="a5012-122">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5012-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="a5012-123">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a5012-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="a5012-124">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a5012-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="a5012-125">参照</span><span class="sxs-lookup"><span data-stu-id="a5012-125">See Also</span></span>

[<span data-ttu-id="a5012-126">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a5012-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="a5012-127">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a5012-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="a5012-128">構成用のコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a5012-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="a5012-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="a5012-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
