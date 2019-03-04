---
title: ExpressionBinding のビュー (形式) のコントロールの要素を CustomControlName |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b6ee11e-9086-41d2-afd3-42fb9f24da69
caps.latest.revision: 7
ms.openlocfilehash: bf1d57447f9018f1535af14466427aaeabc048f3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855598"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="a72c7-102">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a72c7-102">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="a72c7-103">一般的なコントロールまたはビューのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a72c7-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="a72c7-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a72c7-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a72c7-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) CustomControlName のコントロールのビュー (形式) ExpressionBinding 要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールコントロールが表示されます (形式) の ExpressionBindine 要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) CustomControlName Element for ExpressionBindine for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a72c7-106">構文</span><span class="sxs-lookup"><span data-stu-id="a72c7-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a72c7-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-107">Attributes and Elements</span></span>

<span data-ttu-id="a72c7-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControlName`要素。</span><span class="sxs-lookup"><span data-stu-id="a72c7-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a72c7-109">属性</span><span class="sxs-lookup"><span data-stu-id="a72c7-109">Attributes</span></span>

<span data-ttu-id="a72c7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="a72c7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a72c7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-111">Child Elements</span></span>

<span data-ttu-id="a72c7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="a72c7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a72c7-113">親要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-113">Parent Elements</span></span>

|<span data-ttu-id="a72c7-114">要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-114">Element</span></span>|<span data-ttu-id="a72c7-115">説明</span><span class="sxs-lookup"><span data-stu-id="a72c7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a72c7-116">コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-116">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="a72c7-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="a72c7-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a72c7-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a72c7-118">Text Value</span></span>

<span data-ttu-id="a72c7-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a72c7-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="a72c7-120">コメント</span><span class="sxs-lookup"><span data-stu-id="a72c7-120">Remarks</span></span>

<span data-ttu-id="a72c7-121">書式設定ファイルでは、すべてのビューで使用できる一般的なコントロールを作成して、特定のビューで使用できるビュー コントロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a72c7-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="a72c7-122">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a72c7-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="a72c7-123">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="a72c7-124">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="a72c7-125">参照</span><span class="sxs-lookup"><span data-stu-id="a72c7-125">See Also</span></span>

[<span data-ttu-id="a72c7-126">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="a72c7-127">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="a72c7-128">コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="a72c7-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="a72c7-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="a72c7-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
