---
title: GroupBy (Format) の CustomControlName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4e3102f12cd37fa72a2de1bf1db5d1f82db31222
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783740"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="07bd2-102">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="07bd2-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="07bd2-103">新しいグループを表示するために使用されるカスタムコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="07bd2-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="07bd2-104">この要素は、テーブル、リスト、ワイド、またはカスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="07bd2-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="07bd2-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) GroupBy 要素 (format) の CustomControlName 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="07bd2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="07bd2-106">構文</span><span class="sxs-lookup"><span data-stu-id="07bd2-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="07bd2-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="07bd2-107">Attributes and Elements</span></span>

<span data-ttu-id="07bd2-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="07bd2-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="07bd2-109">属性</span><span class="sxs-lookup"><span data-stu-id="07bd2-109">Attributes</span></span>

<span data-ttu-id="07bd2-110">なし。</span><span class="sxs-lookup"><span data-stu-id="07bd2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="07bd2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="07bd2-111">Child Elements</span></span>

<span data-ttu-id="07bd2-112">なし。</span><span class="sxs-lookup"><span data-stu-id="07bd2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="07bd2-113">親要素</span><span class="sxs-lookup"><span data-stu-id="07bd2-113">Parent Elements</span></span>

|<span data-ttu-id="07bd2-114">要素</span><span class="sxs-lookup"><span data-stu-id="07bd2-114">Element</span></span>|<span data-ttu-id="07bd2-115">説明</span><span class="sxs-lookup"><span data-stu-id="07bd2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="07bd2-116">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="07bd2-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="07bd2-117">Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="07bd2-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="07bd2-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="07bd2-118">Text Value</span></span>

<span data-ttu-id="07bd2-119">新しいグループの表示に使用されるカスタムコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="07bd2-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="07bd2-120">解説</span><span class="sxs-lookup"><span data-stu-id="07bd2-120">Remarks</span></span>

<span data-ttu-id="07bd2-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="07bd2-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="07bd2-122">次の要素は、これらのカスタムコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="07bd2-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="07bd2-123">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="07bd2-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="07bd2-124">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="07bd2-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="07bd2-125">参照</span><span class="sxs-lookup"><span data-stu-id="07bd2-125">See Also</span></span>

[<span data-ttu-id="07bd2-126">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="07bd2-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="07bd2-127">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="07bd2-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="07bd2-128">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="07bd2-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="07bd2-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="07bd2-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
