---
title: GroupBy (Format) の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddcecc46-ac75-43fa-b03a-802a68524ec3
caps.latest.revision: 10
ms.openlocfilehash: da6ac5abe7acbbee8f57b3e81529664f81800b86
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362521"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="6f416-102">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6f416-102">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="6f416-103">値が変更されるたびに新しいグループを開始する .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6f416-103">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="6f416-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (書式) GroupBy 要素 (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="6f416-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6f416-105">構文</span><span class="sxs-lookup"><span data-stu-id="6f416-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6f416-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="6f416-106">Attributes and Elements</span></span>

<span data-ttu-id="6f416-107">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f416-107">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6f416-108">属性</span><span class="sxs-lookup"><span data-stu-id="6f416-108">Attributes</span></span>

<span data-ttu-id="6f416-109">なし。</span><span class="sxs-lookup"><span data-stu-id="6f416-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6f416-110">子要素</span><span class="sxs-lookup"><span data-stu-id="6f416-110">Child Elements</span></span>

<span data-ttu-id="6f416-111">なし。</span><span class="sxs-lookup"><span data-stu-id="6f416-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6f416-112">親要素</span><span class="sxs-lookup"><span data-stu-id="6f416-112">Parent Elements</span></span>

|<span data-ttu-id="6f416-113">要素</span><span class="sxs-lookup"><span data-stu-id="6f416-113">Element</span></span>|<span data-ttu-id="6f416-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="6f416-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6f416-115">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6f416-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="6f416-116">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="6f416-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6f416-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="6f416-117">Text Value</span></span>

<span data-ttu-id="6f416-118">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f416-118">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f416-119">コメント</span><span class="sxs-lookup"><span data-stu-id="6f416-119">Remarks</span></span>

<span data-ttu-id="6f416-120">このプロパティの値が変更されるたびに、Windows PowerShell によって新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="6f416-120">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="6f416-121">この要素が指定されている場合、 [ScriptBlock](./scriptblock-element-for-groupby-format.md)要素を指定して新しいグループを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="6f416-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="6f416-122">例</span><span class="sxs-lookup"><span data-stu-id="6f416-122">Example</span></span>

<span data-ttu-id="6f416-123">次の例は、プロパティの値が変更されたときに新しいグループを開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f416-123">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="6f416-124">この要素を含む完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f416-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f416-125">参照</span><span class="sxs-lookup"><span data-stu-id="6f416-125">See Also</span></span>

[<span data-ttu-id="6f416-126">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6f416-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="6f416-127">GroupBy (Format) の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="6f416-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="6f416-128">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="6f416-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
