---
title: WideControl の WideItem の PropertyName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d91d0e6-bf18-4587-b651-db66849e5df5
caps.latest.revision: 6
ms.openlocfilehash: 326880834cd82ab826aadc409cd7a8f21cd36824
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364941"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="b82a3-102">WideControl の WideItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b82a3-102">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="b82a3-103">ワイドビューに表示される値を持つオブジェクトのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="b82a3-103">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="b82a3-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideItem Element (format) PropertyName Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="b82a3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b82a3-105">構文</span><span class="sxs-lookup"><span data-stu-id="b82a3-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b82a3-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b82a3-106">Attributes and Elements</span></span>

<span data-ttu-id="b82a3-107">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b82a3-107">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b82a3-108">属性</span><span class="sxs-lookup"><span data-stu-id="b82a3-108">Attributes</span></span>

<span data-ttu-id="b82a3-109">なし。</span><span class="sxs-lookup"><span data-stu-id="b82a3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b82a3-110">子要素</span><span class="sxs-lookup"><span data-stu-id="b82a3-110">Child Elements</span></span>

<span data-ttu-id="b82a3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b82a3-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b82a3-112">親要素</span><span class="sxs-lookup"><span data-stu-id="b82a3-112">Parent Elements</span></span>

|<span data-ttu-id="b82a3-113">要素</span><span class="sxs-lookup"><span data-stu-id="b82a3-113">Element</span></span>|<span data-ttu-id="b82a3-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="b82a3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b82a3-115">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b82a3-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="b82a3-116">ワイドビューに表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="b82a3-116">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b82a3-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b82a3-117">Text Value</span></span>

<span data-ttu-id="b82a3-118">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b82a3-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="b82a3-119">コメント</span><span class="sxs-lookup"><span data-stu-id="b82a3-119">Remarks</span></span>

<span data-ttu-id="b82a3-120">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b82a3-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b82a3-121">例</span><span class="sxs-lookup"><span data-stu-id="b82a3-121">Example</span></span>

<span data-ttu-id="b82a3-122">この例[は、ProcessName オブジェクトの](/dotnet/api/System.Diagnostics.Process)プロパティの値を表示するワイドビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="b82a3-122">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b82a3-123">参照</span><span class="sxs-lookup"><span data-stu-id="b82a3-123">See Also</span></span>

[<span data-ttu-id="b82a3-124">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b82a3-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="b82a3-125">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="b82a3-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b82a3-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="b82a3-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
