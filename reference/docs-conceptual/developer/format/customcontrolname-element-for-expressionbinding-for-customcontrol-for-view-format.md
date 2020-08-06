---
title: View (Format) の CustomControl の式のバインドの CustomControlName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6f1ffca045b7efcecb4dce4e788a8c508fa6ef08
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783757"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a><span data-ttu-id="85ef1-102">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="85ef1-102">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>

<span data-ttu-id="85ef1-103">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="85ef1-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="85ef1-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="85ef1-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="85ef1-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) の CustomControl 要素のビュー (format) CustomEntries 要素の CustomControl for view (format) customentries 要素に対して、CustomEntries for view (format) CustomControlName 要素の customentries (format) 式バインドのバインド要素 (形式) を指定します。</span><span class="sxs-lookup"><span data-stu-id="85ef1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem (Format) CustomControlName Element for Expression Binding for CustomItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="85ef1-106">構文</span><span class="sxs-lookup"><span data-stu-id="85ef1-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="85ef1-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="85ef1-107">Attributes and Elements</span></span>

<span data-ttu-id="85ef1-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="85ef1-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="85ef1-109">属性</span><span class="sxs-lookup"><span data-stu-id="85ef1-109">Attributes</span></span>

<span data-ttu-id="85ef1-110">なし。</span><span class="sxs-lookup"><span data-stu-id="85ef1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="85ef1-111">子要素</span><span class="sxs-lookup"><span data-stu-id="85ef1-111">Child Elements</span></span>

<span data-ttu-id="85ef1-112">なし。</span><span class="sxs-lookup"><span data-stu-id="85ef1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="85ef1-113">親要素</span><span class="sxs-lookup"><span data-stu-id="85ef1-113">Parent Elements</span></span>

|<span data-ttu-id="85ef1-114">要素</span><span class="sxs-lookup"><span data-stu-id="85ef1-114">Element</span></span>|<span data-ttu-id="85ef1-115">説明</span><span class="sxs-lookup"><span data-stu-id="85ef1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="85ef1-116">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="85ef1-116">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="85ef1-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="85ef1-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="85ef1-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="85ef1-118">Text Value</span></span>

<span data-ttu-id="85ef1-119">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="85ef1-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="85ef1-120">解説</span><span class="sxs-lookup"><span data-stu-id="85ef1-120">Remarks</span></span>

<span data-ttu-id="85ef1-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成したり、特定のビューで使用できるビューコントロールを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="85ef1-121">You can create common controls that can be used by all the views of a formatting file and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="85ef1-122">これらのコントロールの名前は、次の要素によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="85ef1-122">The names of these controls are specified by the following elements.</span></span>

- [<span data-ttu-id="85ef1-123">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="85ef1-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="85ef1-124">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="85ef1-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="85ef1-125">参照</span><span class="sxs-lookup"><span data-stu-id="85ef1-125">See Also</span></span>

[<span data-ttu-id="85ef1-126">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="85ef1-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="85ef1-127">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="85ef1-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="85ef1-128">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="85ef1-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="85ef1-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="85ef1-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
