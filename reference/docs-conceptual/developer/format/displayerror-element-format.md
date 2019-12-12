---
title: DisplayError 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c45800-a87d-456e-b07c-12d4d8c27c67
caps.latest.revision: 8
ms.openlocfilehash: 2c6a3d678ca68dc0d189f6ab981fdea5fef894cb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363991"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="6f0f3-102">DisplayError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6f0f3-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="6f0f3-103">データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="6f0f3-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="6f0f3-104">Configuration 要素 (Format) DefaultSettings Element (format) DisplayError 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6f0f3-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6f0f3-105">構文</span><span class="sxs-lookup"><span data-stu-id="6f0f3-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6f0f3-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="6f0f3-106">Attributes and Elements</span></span>

<span data-ttu-id="6f0f3-107">次のセクションでは、`DisplayError` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f0f3-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6f0f3-108">属性</span><span class="sxs-lookup"><span data-stu-id="6f0f3-108">Attributes</span></span>

<span data-ttu-id="6f0f3-109">なし。</span><span class="sxs-lookup"><span data-stu-id="6f0f3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6f0f3-110">子要素</span><span class="sxs-lookup"><span data-stu-id="6f0f3-110">Child Elements</span></span>

<span data-ttu-id="6f0f3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="6f0f3-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6f0f3-112">親要素</span><span class="sxs-lookup"><span data-stu-id="6f0f3-112">Parent Elements</span></span>

|<span data-ttu-id="6f0f3-113">要素</span><span class="sxs-lookup"><span data-stu-id="6f0f3-113">Element</span></span>|<span data-ttu-id="6f0f3-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="6f0f3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6f0f3-115">DefaultSettings 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6f0f3-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="6f0f3-116">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6f0f3-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6f0f3-117">コメント</span><span class="sxs-lookup"><span data-stu-id="6f0f3-117">Remarks</span></span>

<span data-ttu-id="6f0f3-118">既定では、データの一部を表示しようとしてエラーが発生すると、データの場所は空白のままになります。</span><span class="sxs-lookup"><span data-stu-id="6f0f3-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="6f0f3-119">この要素が true に設定されている場合、#ERR 文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f0f3-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f0f3-120">参照</span><span class="sxs-lookup"><span data-stu-id="6f0f3-120">See Also</span></span>

[<span data-ttu-id="6f0f3-121">DefaultSettings 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6f0f3-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="6f0f3-122">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="6f0f3-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
