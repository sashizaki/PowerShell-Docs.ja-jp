---
title: View (Format) の CustomControl の式のバインドの CustomControlName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea821e8b-4d65-4263-b7e4-6aeca9f534c2
caps.latest.revision: 9
ms.openlocfilehash: b44ced75bbaac7c0744f347bdc97f87365b8fe39
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364111"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a><span data-ttu-id="c5810-102">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c5810-102">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>

<span data-ttu-id="c5810-103">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5810-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="c5810-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5810-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="c5810-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素のビュー (形式) の CustomEntries 要素のビュー (形式) の Custommentry 要素 for view (format) Customentries の CustomControlCustomItem (format) の式のバインドのために、CustomEntry for ビュー (形式) の式のバインド要素の CustomControlName 要素の要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="c5810-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem (Format) CustomControlName Element for Expression Binding for CustomItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c5810-106">構文</span><span class="sxs-lookup"><span data-stu-id="c5810-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c5810-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c5810-107">Attributes and Elements</span></span>

<span data-ttu-id="c5810-108">次のセクションでは、属性、子要素、`CustomControlName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5810-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c5810-109">属性</span><span class="sxs-lookup"><span data-stu-id="c5810-109">Attributes</span></span>

<span data-ttu-id="c5810-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c5810-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c5810-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c5810-111">Child Elements</span></span>

<span data-ttu-id="c5810-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c5810-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c5810-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c5810-113">Parent Elements</span></span>

|<span data-ttu-id="c5810-114">要素</span><span class="sxs-lookup"><span data-stu-id="c5810-114">Element</span></span>|<span data-ttu-id="c5810-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="c5810-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c5810-116">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c5810-116">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="c5810-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="c5810-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c5810-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c5810-118">Text Value</span></span>

<span data-ttu-id="c5810-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5810-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5810-120">コメント</span><span class="sxs-lookup"><span data-stu-id="c5810-120">Remarks</span></span>

<span data-ttu-id="c5810-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成したり、特定のビューで使用できるビューコントロールを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="c5810-121">You can create common controls that can be used by all the views of a formatting file and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="c5810-122">これらのコントロールの名前は、次の要素によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="c5810-122">The names of these controls are specified by the following elements.</span></span>

- [<span data-ttu-id="c5810-123">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c5810-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="c5810-124">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c5810-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="c5810-125">参照</span><span class="sxs-lookup"><span data-stu-id="c5810-125">See Also</span></span>

[<span data-ttu-id="c5810-126">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c5810-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="c5810-127">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c5810-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="c5810-128">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c5810-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="c5810-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="c5810-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
