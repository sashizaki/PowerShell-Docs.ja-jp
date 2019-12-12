---
title: GroupBy (Format) の式のバインドの CustomControlName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e11da8f-1e75-4d3d-b4c8-b500dec3028e
caps.latest.revision: 6
ms.openlocfilehash: 32f8a71e9818c8c1a052f3b96f442f169c1bda4a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368911"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="17e41-102">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="17e41-102">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="17e41-103">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="17e41-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="17e41-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="17e41-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="17e41-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素CustomControl for groupby (format) CustomItem 要素の CustomEntry for groupby (format) 式のバインド要素 groupby (形式) の式のバインドのための、GroupBy (format) CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="17e41-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="17e41-106">構文</span><span class="sxs-lookup"><span data-stu-id="17e41-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="17e41-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="17e41-107">Attributes and Elements</span></span>

<span data-ttu-id="17e41-108">次のセクションでは、`CustomControlName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="17e41-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="17e41-109">属性</span><span class="sxs-lookup"><span data-stu-id="17e41-109">Attributes</span></span>

<span data-ttu-id="17e41-110">なし。</span><span class="sxs-lookup"><span data-stu-id="17e41-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="17e41-111">子要素</span><span class="sxs-lookup"><span data-stu-id="17e41-111">Child Elements</span></span>

<span data-ttu-id="17e41-112">なし。</span><span class="sxs-lookup"><span data-stu-id="17e41-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="17e41-113">親要素</span><span class="sxs-lookup"><span data-stu-id="17e41-113">Parent Elements</span></span>

|<span data-ttu-id="17e41-114">要素</span><span class="sxs-lookup"><span data-stu-id="17e41-114">Element</span></span>|<span data-ttu-id="17e41-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="17e41-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="17e41-116">GroupBy (Format) の CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="17e41-116">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="17e41-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="17e41-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="17e41-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="17e41-118">Text Value</span></span>

<span data-ttu-id="17e41-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="17e41-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="17e41-120">コメント</span><span class="sxs-lookup"><span data-stu-id="17e41-120">Remarks</span></span>

<span data-ttu-id="17e41-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="17e41-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="17e41-122">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="17e41-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="17e41-123">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="17e41-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="17e41-124">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="17e41-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="17e41-125">参照</span><span class="sxs-lookup"><span data-stu-id="17e41-125">See Also</span></span>

[<span data-ttu-id="17e41-126">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="17e41-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="17e41-127">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="17e41-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="17e41-128">GroupBy (Format) の CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="17e41-128">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="17e41-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="17e41-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
