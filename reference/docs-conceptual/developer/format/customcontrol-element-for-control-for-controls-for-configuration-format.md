---
title: 構成用コントロールのコントロールの CustomControl 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5aacf824421dfce19f1f495fc0a95e766cdbaf8b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786086"
---
# <a name="customcontrol-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="33af7-102">Configuration の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="33af7-102">CustomControl Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="33af7-103">コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="33af7-103">Defines a control.</span></span> <span data-ttu-id="33af7-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="33af7-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="33af7-105">Configuration 要素 (Format) コントロールの構成 (format) CustomControl 要素のコントロール要素の構成 (形式) のコントロールの要素</span><span class="sxs-lookup"><span data-stu-id="33af7-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="33af7-106">構文</span><span class="sxs-lookup"><span data-stu-id="33af7-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="33af7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="33af7-107">Attributes and Elements</span></span>

<span data-ttu-id="33af7-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControl` ます。</span><span class="sxs-lookup"><span data-stu-id="33af7-108">The following sections describe the attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="33af7-109">この要素には、少なくとも1つの子要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="33af7-109">This element must have at least one child element.</span></span> <span data-ttu-id="33af7-110">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="33af7-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="33af7-111">属性</span><span class="sxs-lookup"><span data-stu-id="33af7-111">Attributes</span></span>

<span data-ttu-id="33af7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="33af7-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="33af7-113">子要素</span><span class="sxs-lookup"><span data-stu-id="33af7-113">Child Elements</span></span>

|<span data-ttu-id="33af7-114">要素</span><span class="sxs-lookup"><span data-stu-id="33af7-114">Element</span></span>|<span data-ttu-id="33af7-115">説明</span><span class="sxs-lookup"><span data-stu-id="33af7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33af7-116">Configuration の CustomControl の CustomEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="33af7-116">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="33af7-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="33af7-117">Required element.</span></span><br /><br /> <span data-ttu-id="33af7-118">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="33af7-118">Provides the definitions of a control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="33af7-119">親要素</span><span class="sxs-lookup"><span data-stu-id="33af7-119">Parent Elements</span></span>

|<span data-ttu-id="33af7-120">要素</span><span class="sxs-lookup"><span data-stu-id="33af7-120">Element</span></span>|<span data-ttu-id="33af7-121">説明</span><span class="sxs-lookup"><span data-stu-id="33af7-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33af7-122">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="33af7-122">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="33af7-123">書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="33af7-123">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="33af7-124">解説</span><span class="sxs-lookup"><span data-stu-id="33af7-124">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="33af7-125">参照</span><span class="sxs-lookup"><span data-stu-id="33af7-125">See Also</span></span>

[<span data-ttu-id="33af7-126">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="33af7-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="33af7-127">Configuration の CustomControl の CustomEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="33af7-127">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="33af7-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="33af7-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
