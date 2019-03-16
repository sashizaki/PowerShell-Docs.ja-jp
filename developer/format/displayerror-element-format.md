---
title: DisplayError 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c45800-a87d-456e-b07c-12d4d8c27c67
caps.latest.revision: 8
ms.openlocfilehash: 2c6a3d678ca68dc0d189f6ab981fdea5fef894cb
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056483"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="4b7c7-102">DisplayError 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4b7c7-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="4b7c7-103">データの一部を表示するエラーが発生したときに、文字列 #ERR が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b7c7-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="4b7c7-104">構成要素 (形式) DefaultSettings 要素 (形式) DisplayError 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4b7c7-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4b7c7-105">構文</span><span class="sxs-lookup"><span data-stu-id="4b7c7-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4b7c7-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="4b7c7-106">Attributes and Elements</span></span>

<span data-ttu-id="4b7c7-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`DisplayError`要素。</span><span class="sxs-lookup"><span data-stu-id="4b7c7-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4b7c7-108">属性</span><span class="sxs-lookup"><span data-stu-id="4b7c7-108">Attributes</span></span>

<span data-ttu-id="4b7c7-109">なし。</span><span class="sxs-lookup"><span data-stu-id="4b7c7-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4b7c7-110">子要素</span><span class="sxs-lookup"><span data-stu-id="4b7c7-110">Child Elements</span></span>

<span data-ttu-id="4b7c7-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4b7c7-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4b7c7-112">親要素</span><span class="sxs-lookup"><span data-stu-id="4b7c7-112">Parent Elements</span></span>

|<span data-ttu-id="4b7c7-113">要素</span><span class="sxs-lookup"><span data-stu-id="4b7c7-113">Element</span></span>|<span data-ttu-id="4b7c7-114">説明</span><span class="sxs-lookup"><span data-stu-id="4b7c7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b7c7-115">DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4b7c7-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="4b7c7-116">書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4b7c7-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4b7c7-117">コメント</span><span class="sxs-lookup"><span data-stu-id="4b7c7-117">Remarks</span></span>

<span data-ttu-id="4b7c7-118">既定では、データの一部を表示するときにエラーが発生したときに、データの場所が空白のままです。</span><span class="sxs-lookup"><span data-stu-id="4b7c7-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="4b7c7-119">この要素が true の場合、#ERR 文字列に設定するときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b7c7-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b7c7-120">参照</span><span class="sxs-lookup"><span data-stu-id="4b7c7-120">See Also</span></span>

[<span data-ttu-id="4b7c7-121">DefaultSettings 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4b7c7-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="4b7c7-122">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="4b7c7-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
