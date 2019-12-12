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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364931"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="28e32-102">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="28e32-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="28e32-103">値が変更されるたびに新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="28e32-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="28e32-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (形式) GroupBy 要素のビュー (形式) の groupby 要素</span><span class="sxs-lookup"><span data-stu-id="28e32-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="28e32-105">構文</span><span class="sxs-lookup"><span data-stu-id="28e32-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28e32-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="28e32-106">Attributes and Elements</span></span>

<span data-ttu-id="28e32-107">次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="28e32-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="28e32-108">属性</span><span class="sxs-lookup"><span data-stu-id="28e32-108">Attributes</span></span>

<span data-ttu-id="28e32-109">なし。</span><span class="sxs-lookup"><span data-stu-id="28e32-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="28e32-110">子要素</span><span class="sxs-lookup"><span data-stu-id="28e32-110">Child Elements</span></span>

<span data-ttu-id="28e32-111">なし。</span><span class="sxs-lookup"><span data-stu-id="28e32-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="28e32-112">親要素</span><span class="sxs-lookup"><span data-stu-id="28e32-112">Parent Elements</span></span>

|<span data-ttu-id="28e32-113">要素</span><span class="sxs-lookup"><span data-stu-id="28e32-113">Element</span></span>|<span data-ttu-id="28e32-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="28e32-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28e32-115">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="28e32-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="28e32-116">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="28e32-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="28e32-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="28e32-117">Text Value</span></span>

<span data-ttu-id="28e32-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="28e32-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="28e32-119">コメント</span><span class="sxs-lookup"><span data-stu-id="28e32-119">Remarks</span></span>

<span data-ttu-id="28e32-120">このスクリプトの値が変更されるたびに、PowerShell によって新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="28e32-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="28e32-121">この要素が指定されている場合、 [PropertyName](propertyname-element-for-groupby-format.md)要素を指定して新しいグループを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="28e32-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="28e32-122">参照</span><span class="sxs-lookup"><span data-stu-id="28e32-122">See Also</span></span>

[<span data-ttu-id="28e32-123">GroupBy (Format) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="28e32-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="28e32-124">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="28e32-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="28e32-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="28e32-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
