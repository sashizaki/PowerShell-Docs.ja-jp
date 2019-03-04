---
title: GroupBy (形式) の ExpressionBinding CustomControlName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e11da8f-1e75-4d3d-b4c8-b500dec3028e
caps.latest.revision: 6
ms.openlocfilehash: 32f8a71e9818c8c1a052f3b96f442f169c1bda4a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854298"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="afe6a-102">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="afe6a-102">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="afe6a-103">一般的なコントロールまたはビューのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="afe6a-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="afe6a-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="afe6a-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="afe6a-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)ExpressionBinding の GroupBy (形式) の GroupBy (形式) CustomControlName 要素 CustomItem の GroupBy (形式) ExpressionBinding 要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="afe6a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="afe6a-106">構文</span><span class="sxs-lookup"><span data-stu-id="afe6a-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="afe6a-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-107">Attributes and Elements</span></span>

<span data-ttu-id="afe6a-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControlName`要素。</span><span class="sxs-lookup"><span data-stu-id="afe6a-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="afe6a-109">属性</span><span class="sxs-lookup"><span data-stu-id="afe6a-109">Attributes</span></span>

<span data-ttu-id="afe6a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="afe6a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="afe6a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-111">Child Elements</span></span>

<span data-ttu-id="afe6a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="afe6a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="afe6a-113">親要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-113">Parent Elements</span></span>

|<span data-ttu-id="afe6a-114">要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-114">Element</span></span>|<span data-ttu-id="afe6a-115">説明</span><span class="sxs-lookup"><span data-stu-id="afe6a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="afe6a-116">GroupBy (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-116">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="afe6a-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="afe6a-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="afe6a-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="afe6a-118">Text Value</span></span>

<span data-ttu-id="afe6a-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="afe6a-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="afe6a-120">コメント</span><span class="sxs-lookup"><span data-stu-id="afe6a-120">Remarks</span></span>

<span data-ttu-id="afe6a-121">書式設定ファイルでは、すべてのビューで使用できる一般的なコントロールを作成して、特定のビューで使用できるビュー コントロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="afe6a-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="afe6a-122">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="afe6a-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="afe6a-123">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="afe6a-124">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="afe6a-125">参照</span><span class="sxs-lookup"><span data-stu-id="afe6a-125">See Also</span></span>

[<span data-ttu-id="afe6a-126">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="afe6a-127">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="afe6a-128">GroupBy (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="afe6a-128">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="afe6a-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="afe6a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
