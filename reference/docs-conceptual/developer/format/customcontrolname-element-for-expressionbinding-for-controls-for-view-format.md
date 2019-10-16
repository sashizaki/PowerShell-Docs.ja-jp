---
title: ビューのコントロールの式のバインドの CustomControlName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b6ee11e-9086-41d2-afd3-42fb9f24da69
caps.latest.revision: 7
ms.openlocfilehash: bf1d57447f9018f1535af14466427aaeabc048f3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369151"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="00236-102">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="00236-102">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="00236-103">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="00236-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="00236-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="00236-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="00236-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (形式) のコントロールの Customentries の CustomControlName (format) 式のバインド要素のビュー (format) の customentries 要素のためのコントロール用の CustomEntries 要素です。ビューのコントロール (Format) の式が Bindine の要素</span><span class="sxs-lookup"><span data-stu-id="00236-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) CustomControlName Element for ExpressionBindine for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="00236-106">構文</span><span class="sxs-lookup"><span data-stu-id="00236-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="00236-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="00236-107">Attributes and Elements</span></span>

<span data-ttu-id="00236-108">次のセクションでは、属性、子要素、`CustomControlName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="00236-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="00236-109">属性</span><span class="sxs-lookup"><span data-stu-id="00236-109">Attributes</span></span>

<span data-ttu-id="00236-110">なし。</span><span class="sxs-lookup"><span data-stu-id="00236-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="00236-111">子要素</span><span class="sxs-lookup"><span data-stu-id="00236-111">Child Elements</span></span>

<span data-ttu-id="00236-112">なし。</span><span class="sxs-lookup"><span data-stu-id="00236-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="00236-113">親要素</span><span class="sxs-lookup"><span data-stu-id="00236-113">Parent Elements</span></span>

|<span data-ttu-id="00236-114">要素</span><span class="sxs-lookup"><span data-stu-id="00236-114">Element</span></span>|<span data-ttu-id="00236-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="00236-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="00236-116">ビューのコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="00236-116">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="00236-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="00236-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="00236-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="00236-118">Text Value</span></span>

<span data-ttu-id="00236-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="00236-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="00236-120">コメント</span><span class="sxs-lookup"><span data-stu-id="00236-120">Remarks</span></span>

<span data-ttu-id="00236-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="00236-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="00236-122">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="00236-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="00236-123">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="00236-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="00236-124">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="00236-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="00236-125">参照</span><span class="sxs-lookup"><span data-stu-id="00236-125">See Also</span></span>

[<span data-ttu-id="00236-126">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="00236-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="00236-127">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="00236-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="00236-128">ビューのコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="00236-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="00236-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="00236-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
