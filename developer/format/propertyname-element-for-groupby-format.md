---
title: GroupBy (形式) の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863268"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="54513-102">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="54513-102">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="54513-103">その値が変更されるたびに、新しいグループを開始する .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="54513-103">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="54513-104">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) の GroupBy (形式) のビュー (形式) PropertyName 要素の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="54513-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="54513-105">構文</span><span class="sxs-lookup"><span data-stu-id="54513-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="54513-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="54513-106">Attributes and Elements</span></span>

<span data-ttu-id="54513-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="54513-107">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="54513-108">属性</span><span class="sxs-lookup"><span data-stu-id="54513-108">Attributes</span></span>

<span data-ttu-id="54513-109">なし。</span><span class="sxs-lookup"><span data-stu-id="54513-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="54513-110">子要素</span><span class="sxs-lookup"><span data-stu-id="54513-110">Child Elements</span></span>

<span data-ttu-id="54513-111">なし。</span><span class="sxs-lookup"><span data-stu-id="54513-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="54513-112">親要素</span><span class="sxs-lookup"><span data-stu-id="54513-112">Parent Elements</span></span>

|<span data-ttu-id="54513-113">要素</span><span class="sxs-lookup"><span data-stu-id="54513-113">Element</span></span>|<span data-ttu-id="54513-114">説明</span><span class="sxs-lookup"><span data-stu-id="54513-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="54513-115">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="54513-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="54513-116">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="54513-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="54513-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="54513-117">Text Value</span></span>

<span data-ttu-id="54513-118">.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="54513-118">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="54513-119">コメント</span><span class="sxs-lookup"><span data-stu-id="54513-119">Remarks</span></span>

<span data-ttu-id="54513-120">Windows PowerShell は、このプロパティの値が変更されるたびに、新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="54513-120">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="54513-121">この要素が指定されている場合は指定できません、 [ScriptBlock](./scriptblock-element-for-groupby-format.md)要素を新しいグループを開始します。</span><span class="sxs-lookup"><span data-stu-id="54513-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="54513-122">例</span><span class="sxs-lookup"><span data-stu-id="54513-122">Example</span></span>

<span data-ttu-id="54513-123">次の例では、プロパティの値が変更されたときに、新しいグループを開始する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="54513-123">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="54513-124">この要素を含む完全な書式設定ファイルの例は、[表示幅が広い (GroupBy)](./wide-view-groupby.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54513-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54513-125">参照</span><span class="sxs-lookup"><span data-stu-id="54513-125">See Also</span></span>

[<span data-ttu-id="54513-126">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="54513-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="54513-127">GroupBy (形式) の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="54513-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="54513-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="54513-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
