---
title: コントロールのコントロールのビュー (形式) の要素を名前 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862388"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="9333b-102">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9333b-102">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="9333b-103">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9333b-103">Specifies the name of the control.</span></span>

<span data-ttu-id="9333b-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) 要素 (形式) コントロールの Controls 要素のコントロールのビュー (形式) の名前の要素のコントロールのビュー (形式)</span><span class="sxs-lookup"><span data-stu-id="9333b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9333b-105">構文</span><span class="sxs-lookup"><span data-stu-id="9333b-105">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9333b-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="9333b-106">Attributes and Elements</span></span>

<span data-ttu-id="9333b-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Name`要素。</span><span class="sxs-lookup"><span data-stu-id="9333b-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9333b-108">属性</span><span class="sxs-lookup"><span data-stu-id="9333b-108">Attributes</span></span>

<span data-ttu-id="9333b-109">なし。</span><span class="sxs-lookup"><span data-stu-id="9333b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9333b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="9333b-110">Child Elements</span></span>

<span data-ttu-id="9333b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="9333b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9333b-112">親要素</span><span class="sxs-lookup"><span data-stu-id="9333b-112">Parent Elements</span></span>

|<span data-ttu-id="9333b-113">要素</span><span class="sxs-lookup"><span data-stu-id="9333b-113">Element</span></span>|<span data-ttu-id="9333b-114">説明</span><span class="sxs-lookup"><span data-stu-id="9333b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9333b-115">コントロールが表示されます (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="9333b-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="9333b-116">ビューとコントロールを参照するために使用される名前で使用できるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="9333b-116">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9333b-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="9333b-117">Text Value</span></span>

<span data-ttu-id="9333b-118">コントロールを参照するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9333b-118">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="9333b-119">コメント</span><span class="sxs-lookup"><span data-stu-id="9333b-119">Remarks</span></span>

<span data-ttu-id="9333b-120">ここで指定した名前は、このコントロールを参照する、次の要素で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9333b-120">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="9333b-121">テーブル、リスト、ワイドまたはカスタム コントロールのビューを作成する場合は、次の要素によって、コントロールを指定できます。[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="9333b-121">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="9333b-122">別のコントロールの作成は、ビューで使用できますが、ときにこのコントロールは、次の要素によって指定できます。[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="9333b-122">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="9333b-123">参照</span><span class="sxs-lookup"><span data-stu-id="9333b-123">See Also</span></span>

[<span data-ttu-id="9333b-124">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="9333b-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="9333b-125">コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="9333b-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="9333b-126">コントロールが表示されます (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="9333b-126">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="9333b-127">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="9333b-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
