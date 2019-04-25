---
title: PropertyName WideItem WideControl (形式) の要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d91d0e6-bf18-4587-b651-db66849e5df5
caps.latest.revision: 6
ms.openlocfilehash: 326880834cd82ab826aadc409cd7a8f21cd36824
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064647"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="8c39f-102">WideControl の WideItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8c39f-102">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="8c39f-103">表示幅値が表示されるオブジェクトのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c39f-103">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="8c39f-104">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) WideItem 要素 (形式) PropertyName の構成要素 WideItem (形式)</span><span class="sxs-lookup"><span data-stu-id="8c39f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8c39f-105">構文</span><span class="sxs-lookup"><span data-stu-id="8c39f-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8c39f-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8c39f-106">Attributes and Elements</span></span>

<span data-ttu-id="8c39f-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="8c39f-107">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c39f-108">属性</span><span class="sxs-lookup"><span data-stu-id="8c39f-108">Attributes</span></span>

<span data-ttu-id="8c39f-109">なし。</span><span class="sxs-lookup"><span data-stu-id="8c39f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c39f-110">子要素</span><span class="sxs-lookup"><span data-stu-id="8c39f-110">Child Elements</span></span>

<span data-ttu-id="8c39f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="8c39f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8c39f-112">親要素</span><span class="sxs-lookup"><span data-stu-id="8c39f-112">Parent Elements</span></span>

|<span data-ttu-id="8c39f-113">要素</span><span class="sxs-lookup"><span data-stu-id="8c39f-113">Element</span></span>|<span data-ttu-id="8c39f-114">説明</span><span class="sxs-lookup"><span data-stu-id="8c39f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c39f-115">WideItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="8c39f-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="8c39f-116">プロパティまたは値を持つがワイド ビューで表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c39f-116">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8c39f-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8c39f-117">Text Value</span></span>

<span data-ttu-id="8c39f-118">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c39f-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c39f-119">コメント</span><span class="sxs-lookup"><span data-stu-id="8c39f-119">Remarks</span></span>

<span data-ttu-id="8c39f-120">ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c39f-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8c39f-121">例</span><span class="sxs-lookup"><span data-stu-id="8c39f-121">Example</span></span>

<span data-ttu-id="8c39f-122">この例の ProcessName プロパティの値を表示するワイド ビューを示して、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8c39f-122">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8c39f-123">参照</span><span class="sxs-lookup"><span data-stu-id="8c39f-123">See Also</span></span>

[<span data-ttu-id="8c39f-124">WideItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="8c39f-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="8c39f-125">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="8c39f-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="8c39f-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="8c39f-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
