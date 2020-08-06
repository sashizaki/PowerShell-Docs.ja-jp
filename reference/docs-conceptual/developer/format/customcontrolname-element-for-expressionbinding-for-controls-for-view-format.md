---
title: ビューのコントロールの式のバインドの CustomControlName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 871c6afd89db9360ea5012191b08863a9441f899
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786018"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="15846-102">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15846-102">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="15846-103">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="15846-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="15846-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="15846-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="15846-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロール要素 (形式) コントロールのコントロールの要素 (形式) コントロールの要素 (書式) を制御するためのコントロールの CustomControl 要素 (format) CustomControl for ビュー (形式) の CustomEntries 要素ビュー (format) のコントロールに対する CustomEntries の customentries 要素のビュー (形式) のカスタムバインド要素を表示するために、ビュー (format) の CustomControlName 要素に対して、ビューのコントロール (format) のコントロールに対して、ビュー (format) のバインド要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="15846-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) CustomControlName Element for ExpressionBindine for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15846-106">構文</span><span class="sxs-lookup"><span data-stu-id="15846-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="15846-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="15846-107">Attributes and Elements</span></span>

<span data-ttu-id="15846-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="15846-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="15846-109">属性</span><span class="sxs-lookup"><span data-stu-id="15846-109">Attributes</span></span>

<span data-ttu-id="15846-110">なし。</span><span class="sxs-lookup"><span data-stu-id="15846-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15846-111">子要素</span><span class="sxs-lookup"><span data-stu-id="15846-111">Child Elements</span></span>

<span data-ttu-id="15846-112">なし。</span><span class="sxs-lookup"><span data-stu-id="15846-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="15846-113">親要素</span><span class="sxs-lookup"><span data-stu-id="15846-113">Parent Elements</span></span>

|<span data-ttu-id="15846-114">要素</span><span class="sxs-lookup"><span data-stu-id="15846-114">Element</span></span>|<span data-ttu-id="15846-115">説明</span><span class="sxs-lookup"><span data-stu-id="15846-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15846-116">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15846-116">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="15846-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="15846-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="15846-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="15846-118">Text Value</span></span>

<span data-ttu-id="15846-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="15846-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="15846-120">解説</span><span class="sxs-lookup"><span data-stu-id="15846-120">Remarks</span></span>

<span data-ttu-id="15846-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="15846-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="15846-122">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="15846-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="15846-123">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15846-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="15846-124">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15846-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="15846-125">参照</span><span class="sxs-lookup"><span data-stu-id="15846-125">See Also</span></span>

[<span data-ttu-id="15846-126">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15846-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="15846-127">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15846-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="15846-128">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15846-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="15846-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="15846-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
