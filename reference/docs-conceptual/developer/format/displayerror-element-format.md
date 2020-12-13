---
ms.date: 09/13/2016
ms.topic: reference
title: DisplayError 要素 (書式)
description: DisplayError 要素 (書式)
ms.openlocfilehash: fb54df86a3558263687a8c417870495b7066f563
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649934"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="5eaec-103">DisplayError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5eaec-103">DisplayError Element (Format)</span></span>

<span data-ttu-id="5eaec-104">データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5eaec-104">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="5eaec-105">Configuration 要素 (Format) DefaultSettings Element (format) DisplayError 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5eaec-105">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5eaec-106">構文</span><span class="sxs-lookup"><span data-stu-id="5eaec-106">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5eaec-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5eaec-107">Attributes and Elements</span></span>

<span data-ttu-id="5eaec-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `DisplayError` ます。</span><span class="sxs-lookup"><span data-stu-id="5eaec-108">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5eaec-109">属性</span><span class="sxs-lookup"><span data-stu-id="5eaec-109">Attributes</span></span>

<span data-ttu-id="5eaec-110">なし。</span><span class="sxs-lookup"><span data-stu-id="5eaec-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5eaec-111">子要素</span><span class="sxs-lookup"><span data-stu-id="5eaec-111">Child Elements</span></span>

<span data-ttu-id="5eaec-112">なし。</span><span class="sxs-lookup"><span data-stu-id="5eaec-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5eaec-113">親要素</span><span class="sxs-lookup"><span data-stu-id="5eaec-113">Parent Elements</span></span>

|<span data-ttu-id="5eaec-114">要素</span><span class="sxs-lookup"><span data-stu-id="5eaec-114">Element</span></span>|<span data-ttu-id="5eaec-115">説明</span><span class="sxs-lookup"><span data-stu-id="5eaec-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5eaec-116">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5eaec-116">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="5eaec-117">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="5eaec-117">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5eaec-118">解説</span><span class="sxs-lookup"><span data-stu-id="5eaec-118">Remarks</span></span>

<span data-ttu-id="5eaec-119">既定では、データの一部を表示しようとしてエラーが発生すると、データの場所は空白のままになります。</span><span class="sxs-lookup"><span data-stu-id="5eaec-119">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="5eaec-120">この要素が true に設定されている場合、#ERR 文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5eaec-120">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="5eaec-121">参照</span><span class="sxs-lookup"><span data-stu-id="5eaec-121">See Also</span></span>

[<span data-ttu-id="5eaec-122">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5eaec-122">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="5eaec-123">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="5eaec-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
