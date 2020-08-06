---
title: Configuration のコントロールの Control 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9447efac84cff3cc33468aeebc97a8bdd6137518
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783825"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="9b770-102">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9b770-102">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9b770-103">書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="9b770-103">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="9b770-104">Configuration 要素 (Format) コントロールの構成 (書式) のコントロール要素の Configuration (書式) コントロール要素</span><span class="sxs-lookup"><span data-stu-id="9b770-104">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9b770-105">構文</span><span class="sxs-lookup"><span data-stu-id="9b770-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b770-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9b770-106">Attributes and Elements</span></span>

<span data-ttu-id="9b770-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `Control` ます。</span><span class="sxs-lookup"><span data-stu-id="9b770-107">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="9b770-108">各子要素のうち1つだけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b770-108">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b770-109">属性</span><span class="sxs-lookup"><span data-stu-id="9b770-109">Attributes</span></span>

<span data-ttu-id="9b770-110">なし。</span><span class="sxs-lookup"><span data-stu-id="9b770-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9b770-111">子要素</span><span class="sxs-lookup"><span data-stu-id="9b770-111">Child Elements</span></span>

|<span data-ttu-id="9b770-112">要素</span><span class="sxs-lookup"><span data-stu-id="9b770-112">Element</span></span>|<span data-ttu-id="9b770-113">説明</span><span class="sxs-lookup"><span data-stu-id="9b770-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b770-114">Configuration の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9b770-114">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="9b770-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="9b770-115">Required element.</span></span><br /><br /> <span data-ttu-id="9b770-116">コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="9b770-116">Defines the control.</span></span>|
|[<span data-ttu-id="9b770-117">Configuration のコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="9b770-117">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="9b770-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="9b770-118">Required element.</span></span><br /><br /> <span data-ttu-id="9b770-119">コントロールを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b770-119">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9b770-120">親要素</span><span class="sxs-lookup"><span data-stu-id="9b770-120">Parent Elements</span></span>

|<span data-ttu-id="9b770-121">要素</span><span class="sxs-lookup"><span data-stu-id="9b770-121">Element</span></span>|<span data-ttu-id="9b770-122">説明</span><span class="sxs-lookup"><span data-stu-id="9b770-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b770-123">Configuration の Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="9b770-123">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="9b770-124">書式設定ファイルのすべてのビューまたはその他のコントロールで使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="9b770-124">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9b770-125">解説</span><span class="sxs-lookup"><span data-stu-id="9b770-125">Remarks</span></span>

<span data-ttu-id="9b770-126">このコントロールに指定される名前は、次の要素で参照できます。</span><span class="sxs-lookup"><span data-stu-id="9b770-126">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="9b770-127">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="9b770-127">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="9b770-128">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="9b770-128">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="9b770-129">参照</span><span class="sxs-lookup"><span data-stu-id="9b770-129">See Also</span></span>

[<span data-ttu-id="9b770-130">Configuration の Controls 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="9b770-130">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="9b770-131">構成用のコントロールの CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9b770-131">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="9b770-132">CustomItem の式のバインド要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="9b770-132">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="9b770-133">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="9b770-133">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="9b770-134">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9b770-134">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="9b770-135">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="9b770-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
