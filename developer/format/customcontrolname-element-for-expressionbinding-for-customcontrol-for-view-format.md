---
title: ExpressionBinding のビュー (形式) のカスタム コントロールの要素を CustomControlName |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea821e8b-4d65-4263-b7e4-6aeca9f534c2
caps.latest.revision: 9
ms.openlocfilehash: b44ced75bbaac7c0744f347bdc97f87365b8fe39
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860438"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a><span data-ttu-id="60f45-102">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="60f45-102">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>

<span data-ttu-id="60f45-103">一般的なコントロールまたはビューのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="60f45-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="60f45-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="60f45-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="60f45-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素のビュー (形式) CustomItem CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールのビュー (形式) CustomEntries 要素CustomEntry CustomItem (形式) の式バインディングの CustomItem (形式) CustomControlName 要素のビュー (形式) ExpressionBinding 要素の要素</span><span class="sxs-lookup"><span data-stu-id="60f45-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem (Format) CustomControlName Element for Expression Binding for CustomItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="60f45-106">構文</span><span class="sxs-lookup"><span data-stu-id="60f45-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="60f45-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="60f45-107">Attributes and Elements</span></span>

<span data-ttu-id="60f45-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControlName`要素。</span><span class="sxs-lookup"><span data-stu-id="60f45-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="60f45-109">属性</span><span class="sxs-lookup"><span data-stu-id="60f45-109">Attributes</span></span>

<span data-ttu-id="60f45-110">なし。</span><span class="sxs-lookup"><span data-stu-id="60f45-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="60f45-111">子要素</span><span class="sxs-lookup"><span data-stu-id="60f45-111">Child Elements</span></span>

<span data-ttu-id="60f45-112">なし。</span><span class="sxs-lookup"><span data-stu-id="60f45-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="60f45-113">親要素</span><span class="sxs-lookup"><span data-stu-id="60f45-113">Parent Elements</span></span>

|<span data-ttu-id="60f45-114">要素</span><span class="sxs-lookup"><span data-stu-id="60f45-114">Element</span></span>|<span data-ttu-id="60f45-115">説明</span><span class="sxs-lookup"><span data-stu-id="60f45-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60f45-116">ExpressionBinding 要素 CustomItem (形式)</span><span class="sxs-lookup"><span data-stu-id="60f45-116">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="60f45-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="60f45-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="60f45-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="60f45-118">Text Value</span></span>

<span data-ttu-id="60f45-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="60f45-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="60f45-120">コメント</span><span class="sxs-lookup"><span data-stu-id="60f45-120">Remarks</span></span>

<span data-ttu-id="60f45-121">書式設定ファイルのすべてのビューで使用できる一般的なコントロールを作成して、特定のビューで使用できるビュー コントロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="60f45-121">You can create common controls that can be used by all the views of a formatting file and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="60f45-122">これらのコントロールの名前は、次の要素によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="60f45-122">The names of these controls are specified by the following elements.</span></span>

- [<span data-ttu-id="60f45-123">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="60f45-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="60f45-124">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="60f45-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="60f45-125">参照</span><span class="sxs-lookup"><span data-stu-id="60f45-125">See Also</span></span>

[<span data-ttu-id="60f45-126">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="60f45-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="60f45-127">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="60f45-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="60f45-128">ExpressionBinding 要素 CustomItem (形式)</span><span class="sxs-lookup"><span data-stu-id="60f45-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="60f45-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="60f45-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
