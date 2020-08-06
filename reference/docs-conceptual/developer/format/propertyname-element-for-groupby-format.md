---
title: GroupBy (Format) の PropertyName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e83ebd49e4f3087c817b3cc8772889dbe85113aa
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785610"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="9497f-102">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9497f-102">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="9497f-103">値が変更されるたびに新しいグループを開始する .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="9497f-103">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="9497f-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (書式) GroupBy 要素 (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="9497f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9497f-105">構文</span><span class="sxs-lookup"><span data-stu-id="9497f-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9497f-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9497f-106">Attributes and Elements</span></span>

<span data-ttu-id="9497f-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="9497f-107">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9497f-108">属性</span><span class="sxs-lookup"><span data-stu-id="9497f-108">Attributes</span></span>

<span data-ttu-id="9497f-109">なし。</span><span class="sxs-lookup"><span data-stu-id="9497f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9497f-110">子要素</span><span class="sxs-lookup"><span data-stu-id="9497f-110">Child Elements</span></span>

<span data-ttu-id="9497f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="9497f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9497f-112">親要素</span><span class="sxs-lookup"><span data-stu-id="9497f-112">Parent Elements</span></span>

|<span data-ttu-id="9497f-113">要素</span><span class="sxs-lookup"><span data-stu-id="9497f-113">Element</span></span>|<span data-ttu-id="9497f-114">説明</span><span class="sxs-lookup"><span data-stu-id="9497f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9497f-115">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9497f-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="9497f-116">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="9497f-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9497f-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="9497f-117">Text Value</span></span>

<span data-ttu-id="9497f-118">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9497f-118">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="9497f-119">解説</span><span class="sxs-lookup"><span data-stu-id="9497f-119">Remarks</span></span>

<span data-ttu-id="9497f-120">このプロパティの値が変更されるたびに、Windows PowerShell によって新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="9497f-120">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="9497f-121">この要素が指定されている場合、 [ScriptBlock](./scriptblock-element-for-groupby-format.md)要素を指定して新しいグループを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="9497f-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="9497f-122">例</span><span class="sxs-lookup"><span data-stu-id="9497f-122">Example</span></span>

<span data-ttu-id="9497f-123">次の例は、プロパティの値が変更されたときに新しいグループを開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9497f-123">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="9497f-124">この要素を含む完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9497f-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9497f-125">参照</span><span class="sxs-lookup"><span data-stu-id="9497f-125">See Also</span></span>

[<span data-ttu-id="9497f-126">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9497f-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="9497f-127">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9497f-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="9497f-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="9497f-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
