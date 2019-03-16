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
ms.openlocfilehash: f2f6b9af7740b1231881294c2f32bf97b5a1568b
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054427"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="69d78-102">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="69d78-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="69d78-103">その値が変更されるたびに、新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="69d78-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="69d78-104">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) の GroupBy (形式) のビュー (形式) スクリプト ブロックの要素の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="69d78-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="69d78-105">構文</span><span class="sxs-lookup"><span data-stu-id="69d78-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="69d78-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="69d78-106">Attributes and Elements</span></span>

<span data-ttu-id="69d78-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="69d78-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="69d78-108">属性</span><span class="sxs-lookup"><span data-stu-id="69d78-108">Attributes</span></span>

<span data-ttu-id="69d78-109">なし。</span><span class="sxs-lookup"><span data-stu-id="69d78-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="69d78-110">子要素</span><span class="sxs-lookup"><span data-stu-id="69d78-110">Child Elements</span></span>

<span data-ttu-id="69d78-111">なし。</span><span class="sxs-lookup"><span data-stu-id="69d78-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="69d78-112">親要素</span><span class="sxs-lookup"><span data-stu-id="69d78-112">Parent Elements</span></span>

|<span data-ttu-id="69d78-113">要素</span><span class="sxs-lookup"><span data-stu-id="69d78-113">Element</span></span>|<span data-ttu-id="69d78-114">説明</span><span class="sxs-lookup"><span data-stu-id="69d78-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="69d78-115">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="69d78-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="69d78-116">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="69d78-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="69d78-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="69d78-117">Text Value</span></span>

<span data-ttu-id="69d78-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="69d78-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="69d78-119">コメント</span><span class="sxs-lookup"><span data-stu-id="69d78-119">Remarks</span></span>

<span data-ttu-id="69d78-120">Windows PowerShell は、このスクリプトの値が変更されるたびに、新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="69d78-120">Windows PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="69d78-121">この要素が指定されている場合は指定できません、 [PropertyName](http://msdn.microsoft.com/en-us/396dede0-039a-4a87-a5ef-3ecabb729676)要素を新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="69d78-121">When this element is specified, you cannot specify the [PropertyName](http://msdn.microsoft.com/en-us/396dede0-039a-4a87-a5ef-3ecabb729676) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="69d78-122">参照</span><span class="sxs-lookup"><span data-stu-id="69d78-122">See Also</span></span>

[<span data-ttu-id="69d78-123">GroupBy (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="69d78-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="69d78-124">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="69d78-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="69d78-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="69d78-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
