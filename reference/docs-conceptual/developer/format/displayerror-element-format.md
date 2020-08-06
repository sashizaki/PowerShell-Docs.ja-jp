---
title: DisplayError 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774288"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="55caa-102">DisplayError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55caa-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="55caa-103">データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="55caa-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="55caa-104">Configuration 要素 (Format) DefaultSettings Element (format) DisplayError 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="55caa-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="55caa-105">構文</span><span class="sxs-lookup"><span data-stu-id="55caa-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="55caa-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="55caa-106">Attributes and Elements</span></span>

<span data-ttu-id="55caa-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `DisplayError` ます。</span><span class="sxs-lookup"><span data-stu-id="55caa-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="55caa-108">属性</span><span class="sxs-lookup"><span data-stu-id="55caa-108">Attributes</span></span>

<span data-ttu-id="55caa-109">なし。</span><span class="sxs-lookup"><span data-stu-id="55caa-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="55caa-110">子要素</span><span class="sxs-lookup"><span data-stu-id="55caa-110">Child Elements</span></span>

<span data-ttu-id="55caa-111">なし。</span><span class="sxs-lookup"><span data-stu-id="55caa-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="55caa-112">親要素</span><span class="sxs-lookup"><span data-stu-id="55caa-112">Parent Elements</span></span>

|<span data-ttu-id="55caa-113">要素</span><span class="sxs-lookup"><span data-stu-id="55caa-113">Element</span></span>|<span data-ttu-id="55caa-114">説明</span><span class="sxs-lookup"><span data-stu-id="55caa-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="55caa-115">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55caa-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="55caa-116">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="55caa-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="55caa-117">解説</span><span class="sxs-lookup"><span data-stu-id="55caa-117">Remarks</span></span>

<span data-ttu-id="55caa-118">既定では、データの一部を表示しようとしてエラーが発生すると、データの場所は空白のままになります。</span><span class="sxs-lookup"><span data-stu-id="55caa-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="55caa-119">この要素が true に設定されている場合、#ERR 文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55caa-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="55caa-120">参照</span><span class="sxs-lookup"><span data-stu-id="55caa-120">See Also</span></span>

[<span data-ttu-id="55caa-121">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55caa-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="55caa-122">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="55caa-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
