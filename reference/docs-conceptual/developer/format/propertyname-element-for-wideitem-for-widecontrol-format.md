---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の WideItem の PropertyName 要素 (書式)
description: WideControl の WideItem の PropertyName 要素 (書式)
ms.openlocfilehash: 1d4d5eaf7708dfbd7997122fac156a36487538ea
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665619"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="e8919-103">WideControl の WideItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e8919-103">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="e8919-104">ワイドビューに表示される値を持つオブジェクトのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8919-104">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="e8919-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideItem Element (format) PropertyName Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="e8919-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8919-106">構文</span><span class="sxs-lookup"><span data-stu-id="e8919-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8919-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e8919-107">Attributes and Elements</span></span>

<span data-ttu-id="e8919-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="e8919-108">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8919-109">属性</span><span class="sxs-lookup"><span data-stu-id="e8919-109">Attributes</span></span>

<span data-ttu-id="e8919-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e8919-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8919-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e8919-111">Child Elements</span></span>

<span data-ttu-id="e8919-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e8919-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8919-113">親要素</span><span class="sxs-lookup"><span data-stu-id="e8919-113">Parent Elements</span></span>

|<span data-ttu-id="e8919-114">要素</span><span class="sxs-lookup"><span data-stu-id="e8919-114">Element</span></span>|<span data-ttu-id="e8919-115">説明</span><span class="sxs-lookup"><span data-stu-id="e8919-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8919-116">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="e8919-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="e8919-117">ワイドビューに表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e8919-117">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e8919-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e8919-118">Text Value</span></span>

<span data-ttu-id="e8919-119">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8919-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8919-120">解説</span><span class="sxs-lookup"><span data-stu-id="e8919-120">Remarks</span></span>

<span data-ttu-id="e8919-121">ワイドビューのコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8919-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e8919-122">例</span><span class="sxs-lookup"><span data-stu-id="e8919-122">Example</span></span>

<span data-ttu-id="e8919-123">この例 [は、ProcessName オブジェクトの](/dotnet/api/System.Diagnostics.Process) プロパティの値を表示するワイドビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="e8919-123">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="e8919-124">参照</span><span class="sxs-lookup"><span data-stu-id="e8919-124">See Also</span></span>

[<span data-ttu-id="e8919-125">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="e8919-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="e8919-126">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="e8919-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="e8919-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e8919-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
