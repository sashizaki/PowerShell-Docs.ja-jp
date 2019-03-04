---
title: 構成 (形式) の要素をコントロールのコントロールの名前 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4371d45-49a4-4303-8384-5b54105bd0d6
caps.latest.revision: 8
ms.openlocfilehash: 2704a530e0ae269efb772ac10e531bcbb12f6eff
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860088"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="18513-102">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="18513-102">Name Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="18513-103">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="18513-103">Specifies the name of the control.</span></span> <span data-ttu-id="18513-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="18513-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="18513-105">構成 (形式) のコントロールのコントロールの構成 (形式) の Name 要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="18513-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) Name Element for Control for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="18513-106">構文</span><span class="sxs-lookup"><span data-stu-id="18513-106">Syntax</span></span>

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="18513-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="18513-107">Attributes and Elements</span></span>

<span data-ttu-id="18513-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`Name`要素。</span><span class="sxs-lookup"><span data-stu-id="18513-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="18513-109">属性</span><span class="sxs-lookup"><span data-stu-id="18513-109">Attributes</span></span>

<span data-ttu-id="18513-110">なし。</span><span class="sxs-lookup"><span data-stu-id="18513-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="18513-111">子要素</span><span class="sxs-lookup"><span data-stu-id="18513-111">Child Elements</span></span>

<span data-ttu-id="18513-112">なし。</span><span class="sxs-lookup"><span data-stu-id="18513-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="18513-113">親要素</span><span class="sxs-lookup"><span data-stu-id="18513-113">Parent Elements</span></span>

|<span data-ttu-id="18513-114">要素</span><span class="sxs-lookup"><span data-stu-id="18513-114">Element</span></span>|<span data-ttu-id="18513-115">説明</span><span class="sxs-lookup"><span data-stu-id="18513-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="18513-116">構成 (形式) のコントロールのコントロール要素</span><span class="sxs-lookup"><span data-stu-id="18513-116">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="18513-117">書式設定ファイルと、コントロールを参照するために使用される名前のすべてのビューで使用できる一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="18513-117">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="18513-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="18513-118">Text Value</span></span>

<span data-ttu-id="18513-119">このコントロールを参照するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="18513-119">Specify the name that is used to reference this control.</span></span>

## <a name="remarks"></a><span data-ttu-id="18513-120">コメント</span><span class="sxs-lookup"><span data-stu-id="18513-120">Remarks</span></span>

<span data-ttu-id="18513-121">ここで指定した名前は、このコントロールを参照する、次の要素で使用できます。</span><span class="sxs-lookup"><span data-stu-id="18513-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="18513-122">テーブル、リスト、ワイドまたはカスタム コントロールのビューを作成する場合は、次の要素によって、コントロールを指定できます。[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="18513-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="18513-123">別の一般的なコントロールを作成するときにこのコントロールは、次の要素によって指定できます。[構成 (形式) のコントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span><span class="sxs-lookup"><span data-stu-id="18513-123">When creating another common control, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for Configuration (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)</span></span>

- <span data-ttu-id="18513-124">コントロールの作成は、ビューで使用できますが、ときにこのコントロールは、次の要素によって指定できます。[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="18513-124">When creating a control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="18513-125">参照</span><span class="sxs-lookup"><span data-stu-id="18513-125">See Also</span></span>

[<span data-ttu-id="18513-126">構成 (形式) のコントロールのコントロール要素</span><span class="sxs-lookup"><span data-stu-id="18513-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="18513-127">構成 (形式) のコントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="18513-127">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="18513-128">コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="18513-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="18513-129">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="18513-129">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="18513-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="18513-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
