---
title: GroupBy (Format) の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e761e02a7910cd598449d564e827889162da9f25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787684"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="15a32-102">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15a32-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="15a32-103">値が変更されるたびに新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="15a32-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="15a32-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (形式) GroupBy 要素のビュー (形式) の groupby 要素</span><span class="sxs-lookup"><span data-stu-id="15a32-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15a32-105">構文</span><span class="sxs-lookup"><span data-stu-id="15a32-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="15a32-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="15a32-106">Attributes and Elements</span></span>

<span data-ttu-id="15a32-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="15a32-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="15a32-108">属性</span><span class="sxs-lookup"><span data-stu-id="15a32-108">Attributes</span></span>

<span data-ttu-id="15a32-109">なし。</span><span class="sxs-lookup"><span data-stu-id="15a32-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15a32-110">子要素</span><span class="sxs-lookup"><span data-stu-id="15a32-110">Child Elements</span></span>

<span data-ttu-id="15a32-111">なし。</span><span class="sxs-lookup"><span data-stu-id="15a32-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="15a32-112">親要素</span><span class="sxs-lookup"><span data-stu-id="15a32-112">Parent Elements</span></span>

|<span data-ttu-id="15a32-113">要素</span><span class="sxs-lookup"><span data-stu-id="15a32-113">Element</span></span>|<span data-ttu-id="15a32-114">説明</span><span class="sxs-lookup"><span data-stu-id="15a32-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15a32-115">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15a32-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="15a32-116">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="15a32-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="15a32-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="15a32-117">Text Value</span></span>

<span data-ttu-id="15a32-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="15a32-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="15a32-119">解説</span><span class="sxs-lookup"><span data-stu-id="15a32-119">Remarks</span></span>

<span data-ttu-id="15a32-120">このスクリプトの値が変更されるたびに、PowerShell によって新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="15a32-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="15a32-121">この要素が指定されている場合、 [PropertyName](propertyname-element-for-groupby-format.md)要素を指定して新しいグループを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="15a32-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="15a32-122">参照</span><span class="sxs-lookup"><span data-stu-id="15a32-122">See Also</span></span>

[<span data-ttu-id="15a32-123">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15a32-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="15a32-124">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15a32-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="15a32-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="15a32-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
