---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls 要素 (書式)
description: Configuration の Controls 要素 (書式)
ms.openlocfilehash: 53f874ddccf3b4f1f0a23aad608e786524bde830
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668101"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="c2f15-103">Configuration の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c2f15-103">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="c2f15-104">書式設定ファイルのすべてのビューで使用できる共通コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="c2f15-104">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="c2f15-105">Configuration 要素 (Format) コントロールの構成要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c2f15-105">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c2f15-106">構文</span><span class="sxs-lookup"><span data-stu-id="c2f15-106">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c2f15-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c2f15-107">Attributes and Elements</span></span>

<span data-ttu-id="c2f15-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Controls` ます。</span><span class="sxs-lookup"><span data-stu-id="c2f15-108">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c2f15-109">属性</span><span class="sxs-lookup"><span data-stu-id="c2f15-109">Attributes</span></span>

<span data-ttu-id="c2f15-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c2f15-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c2f15-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c2f15-111">Child Elements</span></span>

|<span data-ttu-id="c2f15-112">要素</span><span class="sxs-lookup"><span data-stu-id="c2f15-112">Element</span></span>|<span data-ttu-id="c2f15-113">説明</span><span class="sxs-lookup"><span data-stu-id="c2f15-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c2f15-114">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c2f15-114">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="c2f15-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="c2f15-115">Required element.</span></span><br /><br /> <span data-ttu-id="c2f15-116">書式設定ファイルのすべてのビューで使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="c2f15-116">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c2f15-117">親要素</span><span class="sxs-lookup"><span data-stu-id="c2f15-117">Parent Elements</span></span>

|<span data-ttu-id="c2f15-118">要素</span><span class="sxs-lookup"><span data-stu-id="c2f15-118">Element</span></span>|<span data-ttu-id="c2f15-119">説明</span><span class="sxs-lookup"><span data-stu-id="c2f15-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c2f15-120">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c2f15-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="c2f15-121">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="c2f15-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c2f15-122">解説</span><span class="sxs-lookup"><span data-stu-id="c2f15-122">Remarks</span></span>

<span data-ttu-id="c2f15-123">任意の数のコモンコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c2f15-123">You can create any number of common controls.</span></span> <span data-ttu-id="c2f15-124">コントロールごとに、コントロールとそのコンポーネントを参照するために使用する名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f15-124">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2f15-125">参照</span><span class="sxs-lookup"><span data-stu-id="c2f15-125">See Also</span></span>

[<span data-ttu-id="c2f15-126">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c2f15-126">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="c2f15-127">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c2f15-127">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="c2f15-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="c2f15-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
