---
title: GroupBy (Format) の式のバインドの CustomControlName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 06e612b25accf81467108ca48500943153efd575
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786001"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="bcf0a-102">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcf0a-102">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="bcf0a-103">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bcf0a-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="bcf0a-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcf0a-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="bcf0a-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素を groupby (形式) CustomEntry の CustomControl の CustomEntries 要素 CustomControl for groupby (format) Customentries 要素の CustomEntry for groupby (format) 式のバインド要素 groupby (形式) の式のバインドのための、groupby (format) CustomControlName 要素のバインド要素</span><span class="sxs-lookup"><span data-stu-id="bcf0a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bcf0a-106">構文</span><span class="sxs-lookup"><span data-stu-id="bcf0a-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bcf0a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bcf0a-107">Attributes and Elements</span></span>

<span data-ttu-id="bcf0a-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="bcf0a-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bcf0a-109">属性</span><span class="sxs-lookup"><span data-stu-id="bcf0a-109">Attributes</span></span>

<span data-ttu-id="bcf0a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="bcf0a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bcf0a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="bcf0a-111">Child Elements</span></span>

<span data-ttu-id="bcf0a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="bcf0a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bcf0a-113">親要素</span><span class="sxs-lookup"><span data-stu-id="bcf0a-113">Parent Elements</span></span>

|<span data-ttu-id="bcf0a-114">要素</span><span class="sxs-lookup"><span data-stu-id="bcf0a-114">Element</span></span>|<span data-ttu-id="bcf0a-115">説明</span><span class="sxs-lookup"><span data-stu-id="bcf0a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bcf0a-116">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcf0a-116">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="bcf0a-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="bcf0a-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bcf0a-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="bcf0a-118">Text Value</span></span>

<span data-ttu-id="bcf0a-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bcf0a-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="bcf0a-120">解説</span><span class="sxs-lookup"><span data-stu-id="bcf0a-120">Remarks</span></span>

<span data-ttu-id="bcf0a-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcf0a-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="bcf0a-122">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bcf0a-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="bcf0a-123">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcf0a-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="bcf0a-124">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcf0a-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="bcf0a-125">参照</span><span class="sxs-lookup"><span data-stu-id="bcf0a-125">See Also</span></span>

[<span data-ttu-id="bcf0a-126">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcf0a-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="bcf0a-127">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcf0a-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="bcf0a-128">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcf0a-128">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="bcf0a-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="bcf0a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
