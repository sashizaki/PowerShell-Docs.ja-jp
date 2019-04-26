---
title: ExpressionBinding の構成 (形式) のコントロールの要素を CustomControlName |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5242935-2782-4d23-84f5-2446b2b7ba83
caps.latest.revision: 8
ms.openlocfilehash: c9abd9f22907b87323c16d603a9f75bb3d375a03
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066636"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="846c4-102">Configuration の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="846c4-102">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="846c4-103">一般的なコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="846c4-103">Specifies the name of a common control.</span></span> <span data-ttu-id="846c4-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="846c4-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="846c4-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) CustomControlName のコントロールの CustomItem 構成 ExpressionBinding 要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素ExpressionBinding の構成 (形式) のコントロールの要素</span><span class="sxs-lookup"><span data-stu-id="846c4-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="846c4-106">構文</span><span class="sxs-lookup"><span data-stu-id="846c4-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="846c4-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="846c4-107">Attributes and Elements</span></span>

<span data-ttu-id="846c4-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControlName`要素。</span><span class="sxs-lookup"><span data-stu-id="846c4-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="846c4-109">属性</span><span class="sxs-lookup"><span data-stu-id="846c4-109">Attributes</span></span>

<span data-ttu-id="846c4-110">なし。</span><span class="sxs-lookup"><span data-stu-id="846c4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="846c4-111">子要素</span><span class="sxs-lookup"><span data-stu-id="846c4-111">Child Elements</span></span>

<span data-ttu-id="846c4-112">なし。</span><span class="sxs-lookup"><span data-stu-id="846c4-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="846c4-113">親要素</span><span class="sxs-lookup"><span data-stu-id="846c4-113">Parent Elements</span></span>

|<span data-ttu-id="846c4-114">要素</span><span class="sxs-lookup"><span data-stu-id="846c4-114">Element</span></span>|<span data-ttu-id="846c4-115">説明</span><span class="sxs-lookup"><span data-stu-id="846c4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="846c4-116">構成 (形式) のコントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="846c4-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="846c4-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="846c4-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="846c4-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="846c4-118">Text Value</span></span>

<span data-ttu-id="846c4-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="846c4-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="846c4-120">コメント</span><span class="sxs-lookup"><span data-stu-id="846c4-120">Remarks</span></span>

<span data-ttu-id="846c4-121">書式設定ファイルでは、すべてのビューで使用できる一般的なコントロールを作成して、特定のビューで使用できるビュー コントロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="846c4-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="846c4-122">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="846c4-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="846c4-123">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="846c4-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="846c4-124">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="846c4-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="846c4-125">参照</span><span class="sxs-lookup"><span data-stu-id="846c4-125">See Also</span></span>

[<span data-ttu-id="846c4-126">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="846c4-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="846c4-127">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="846c4-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="846c4-128">構成 (形式) のコントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="846c4-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="846c4-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="846c4-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
