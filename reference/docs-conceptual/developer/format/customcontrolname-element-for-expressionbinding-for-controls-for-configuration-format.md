---
title: 構成用のコントロールの式のバインドの CustomControlName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 690b6ae01b8116b72fbd00aef574feda1fd737b0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786035"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="09c1a-102">Configuration の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="09c1a-102">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="09c1a-103">コモンコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="09c1a-103">Specifies the name of a common control.</span></span> <span data-ttu-id="09c1a-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="09c1a-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="09c1a-105">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) の CustomControl 要素の構成 (形式) の CustomControl の構成 (書式) の CustomEntries 要素のコントロール要素 CustomControl for Controls の構成 (書式) 用の Customentries 要素のコントロールの構成式のバインド要素の構成のためのコントロールの構成 (format) CustomControlName 要素の構成用コントロールの構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="09c1a-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="09c1a-106">構文</span><span class="sxs-lookup"><span data-stu-id="09c1a-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="09c1a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="09c1a-107">Attributes and Elements</span></span>

<span data-ttu-id="09c1a-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="09c1a-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="09c1a-109">属性</span><span class="sxs-lookup"><span data-stu-id="09c1a-109">Attributes</span></span>

<span data-ttu-id="09c1a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="09c1a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="09c1a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="09c1a-111">Child Elements</span></span>

<span data-ttu-id="09c1a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="09c1a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="09c1a-113">親要素</span><span class="sxs-lookup"><span data-stu-id="09c1a-113">Parent Elements</span></span>

|<span data-ttu-id="09c1a-114">要素</span><span class="sxs-lookup"><span data-stu-id="09c1a-114">Element</span></span>|<span data-ttu-id="09c1a-115">説明</span><span class="sxs-lookup"><span data-stu-id="09c1a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="09c1a-116">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="09c1a-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="09c1a-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="09c1a-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="09c1a-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="09c1a-118">Text Value</span></span>

<span data-ttu-id="09c1a-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="09c1a-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="09c1a-120">解説</span><span class="sxs-lookup"><span data-stu-id="09c1a-120">Remarks</span></span>

<span data-ttu-id="09c1a-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="09c1a-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="09c1a-122">次の要素は、これらのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="09c1a-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="09c1a-123">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="09c1a-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="09c1a-124">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="09c1a-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="09c1a-125">参照</span><span class="sxs-lookup"><span data-stu-id="09c1a-125">See Also</span></span>

[<span data-ttu-id="09c1a-126">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="09c1a-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="09c1a-127">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="09c1a-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="09c1a-128">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="09c1a-128">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="09c1a-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="09c1a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
