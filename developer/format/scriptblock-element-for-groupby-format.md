---
title: GroupBy (形式) の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: 37a297228eb33ff75daf94a12635d42b52c6cc9f
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229328"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="7d41c-102">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7d41c-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="7d41c-103">その値が変更されるたびに、新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d41c-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="7d41c-104">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) の GroupBy (形式) のビュー (形式) スクリプト ブロックの要素の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="7d41c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7d41c-105">構文</span><span class="sxs-lookup"><span data-stu-id="7d41c-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7d41c-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7d41c-106">Attributes and Elements</span></span>

<span data-ttu-id="7d41c-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="7d41c-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d41c-108">属性</span><span class="sxs-lookup"><span data-stu-id="7d41c-108">Attributes</span></span>

<span data-ttu-id="7d41c-109">なし。</span><span class="sxs-lookup"><span data-stu-id="7d41c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7d41c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="7d41c-110">Child Elements</span></span>

<span data-ttu-id="7d41c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7d41c-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7d41c-112">親要素</span><span class="sxs-lookup"><span data-stu-id="7d41c-112">Parent Elements</span></span>

|<span data-ttu-id="7d41c-113">要素</span><span class="sxs-lookup"><span data-stu-id="7d41c-113">Element</span></span>|<span data-ttu-id="7d41c-114">説明</span><span class="sxs-lookup"><span data-stu-id="7d41c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7d41c-115">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="7d41c-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="7d41c-116">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7d41c-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7d41c-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7d41c-117">Text Value</span></span>

<span data-ttu-id="7d41c-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d41c-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d41c-119">コメント</span><span class="sxs-lookup"><span data-stu-id="7d41c-119">Remarks</span></span>

<span data-ttu-id="7d41c-120">PowerShell は、このスクリプトの値が変更されるたびに、新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="7d41c-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="7d41c-121">この要素が指定されている場合は指定できません、 [PropertyName](propertyname-element-for-groupby-format.md)要素を新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="7d41c-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d41c-122">参照</span><span class="sxs-lookup"><span data-stu-id="7d41c-122">See Also</span></span>

[<span data-ttu-id="7d41c-123">GroupBy (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="7d41c-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="7d41c-124">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="7d41c-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="7d41c-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="7d41c-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
