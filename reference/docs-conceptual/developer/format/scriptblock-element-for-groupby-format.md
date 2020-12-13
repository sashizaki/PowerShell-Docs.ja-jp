---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の ScriptBlock 要素 (書式)
description: GroupBy の ScriptBlock 要素 (書式)
ms.openlocfilehash: 117cbef93889046626741449886a1caaa39815cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665245"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="e1197-103">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e1197-103">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="e1197-104">値が変更されるたびに新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1197-104">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="e1197-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (形式) GroupBy 要素のビュー (形式) の groupby 要素</span><span class="sxs-lookup"><span data-stu-id="e1197-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e1197-106">構文</span><span class="sxs-lookup"><span data-stu-id="e1197-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e1197-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e1197-107">Attributes and Elements</span></span>

<span data-ttu-id="e1197-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="e1197-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e1197-109">属性</span><span class="sxs-lookup"><span data-stu-id="e1197-109">Attributes</span></span>

<span data-ttu-id="e1197-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e1197-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e1197-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e1197-111">Child Elements</span></span>

<span data-ttu-id="e1197-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e1197-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e1197-113">親要素</span><span class="sxs-lookup"><span data-stu-id="e1197-113">Parent Elements</span></span>

|<span data-ttu-id="e1197-114">要素</span><span class="sxs-lookup"><span data-stu-id="e1197-114">Element</span></span>|<span data-ttu-id="e1197-115">説明</span><span class="sxs-lookup"><span data-stu-id="e1197-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e1197-116">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e1197-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="e1197-117">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e1197-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e1197-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e1197-118">Text Value</span></span>

<span data-ttu-id="e1197-119">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1197-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1197-120">解説</span><span class="sxs-lookup"><span data-stu-id="e1197-120">Remarks</span></span>

<span data-ttu-id="e1197-121">このスクリプトの値が変更されるたびに、PowerShell によって新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="e1197-121">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="e1197-122">この要素が指定されている場合、 [PropertyName](propertyname-element-for-groupby-format.md) 要素を指定して新しいグループを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="e1197-122">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1197-123">参照</span><span class="sxs-lookup"><span data-stu-id="e1197-123">See Also</span></span>

[<span data-ttu-id="e1197-124">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e1197-124">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="e1197-125">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e1197-125">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="e1197-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e1197-126">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
