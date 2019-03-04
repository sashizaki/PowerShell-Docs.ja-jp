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
ms.openlocfilehash: 41a6aaa24e5850bd390c8e3b6505cc88fc80b7b5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856208"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="60474-102">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="60474-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="60474-103">その値が変更されるたびに、新しいグループを開始するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="60474-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="60474-104">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) の GroupBy (形式) のビュー (形式) スクリプト ブロックの要素の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="60474-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="60474-105">構文</span><span class="sxs-lookup"><span data-stu-id="60474-105">Syntax</span></span>

```xml
<ScriptBolck>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="60474-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="60474-106">Attributes and Elements</span></span>

<span data-ttu-id="60474-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="60474-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="60474-108">属性</span><span class="sxs-lookup"><span data-stu-id="60474-108">Attributes</span></span>

<span data-ttu-id="60474-109">なし。</span><span class="sxs-lookup"><span data-stu-id="60474-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="60474-110">子要素</span><span class="sxs-lookup"><span data-stu-id="60474-110">Child Elements</span></span>

<span data-ttu-id="60474-111">なし。</span><span class="sxs-lookup"><span data-stu-id="60474-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="60474-112">親要素</span><span class="sxs-lookup"><span data-stu-id="60474-112">Parent Elements</span></span>

|<span data-ttu-id="60474-113">要素</span><span class="sxs-lookup"><span data-stu-id="60474-113">Element</span></span>|<span data-ttu-id="60474-114">説明</span><span class="sxs-lookup"><span data-stu-id="60474-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60474-115">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="60474-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="60474-116">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="60474-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="60474-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="60474-117">Text Value</span></span>

<span data-ttu-id="60474-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="60474-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="60474-119">コメント</span><span class="sxs-lookup"><span data-stu-id="60474-119">Remarks</span></span>

<span data-ttu-id="60474-120">Windows PowerShell は、このスクリプトの値が変更されるたびに、新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="60474-120">Windows PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="60474-121">この要素が指定されている場合は指定できません、 [PropertyName](http://msdn.microsoft.com/en-us/396dede0-039a-4a87-a5ef-3ecabb729676)要素を新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="60474-121">When this element is specified, you cannot specify the [PropertyName](http://msdn.microsoft.com/en-us/396dede0-039a-4a87-a5ef-3ecabb729676) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="60474-122">参照</span><span class="sxs-lookup"><span data-stu-id="60474-122">See Also</span></span>

[<span data-ttu-id="60474-123">GroupBy (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="60474-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="60474-124">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="60474-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="60474-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="60474-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
