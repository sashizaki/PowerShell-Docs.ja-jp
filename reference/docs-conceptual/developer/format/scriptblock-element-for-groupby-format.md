---
title: GroupBy (Format) の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: 37a297228eb33ff75daf94a12635d42b52c6cc9f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364931"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="54902-102">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="54902-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="54902-103">値が変更されるたびに新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="54902-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="54902-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (形式) GroupBy 要素のビュー (形式) の groupby 要素</span><span class="sxs-lookup"><span data-stu-id="54902-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="54902-105">構文</span><span class="sxs-lookup"><span data-stu-id="54902-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="54902-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="54902-106">Attributes and Elements</span></span>

<span data-ttu-id="54902-107">次のセクションでは、属性、子要素、`ScriptBlock` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="54902-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="54902-108">属性</span><span class="sxs-lookup"><span data-stu-id="54902-108">Attributes</span></span>

<span data-ttu-id="54902-109">なし。</span><span class="sxs-lookup"><span data-stu-id="54902-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="54902-110">子要素</span><span class="sxs-lookup"><span data-stu-id="54902-110">Child Elements</span></span>

<span data-ttu-id="54902-111">なし。</span><span class="sxs-lookup"><span data-stu-id="54902-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="54902-112">親要素</span><span class="sxs-lookup"><span data-stu-id="54902-112">Parent Elements</span></span>

|<span data-ttu-id="54902-113">要素</span><span class="sxs-lookup"><span data-stu-id="54902-113">Element</span></span>|<span data-ttu-id="54902-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="54902-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="54902-115">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="54902-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="54902-116">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="54902-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="54902-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="54902-117">Text Value</span></span>

<span data-ttu-id="54902-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="54902-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="54902-119">コメント</span><span class="sxs-lookup"><span data-stu-id="54902-119">Remarks</span></span>

<span data-ttu-id="54902-120">このスクリプトの値が変更されるたびに、PowerShell によって新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="54902-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="54902-121">この要素が指定されている場合、 [PropertyName](propertyname-element-for-groupby-format.md)要素を指定して新しいグループを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="54902-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="54902-122">参照</span><span class="sxs-lookup"><span data-stu-id="54902-122">See Also</span></span>

[<span data-ttu-id="54902-123">GroupBy (Format) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="54902-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="54902-124">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="54902-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="54902-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="54902-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
