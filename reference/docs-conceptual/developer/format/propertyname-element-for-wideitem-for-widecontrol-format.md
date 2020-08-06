---
title: WideControl の WideItem の PropertyName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7728f960a67faa99eaafb4a4934674e119b8af27
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780476"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="5b833-102">WideControl の WideItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5b833-102">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="5b833-103">ワイドビューに表示される値を持つオブジェクトのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b833-103">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="5b833-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideItem Element (format) PropertyName Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="5b833-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5b833-105">構文</span><span class="sxs-lookup"><span data-stu-id="5b833-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5b833-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5b833-106">Attributes and Elements</span></span>

<span data-ttu-id="5b833-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="5b833-107">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5b833-108">属性</span><span class="sxs-lookup"><span data-stu-id="5b833-108">Attributes</span></span>

<span data-ttu-id="5b833-109">なし。</span><span class="sxs-lookup"><span data-stu-id="5b833-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5b833-110">子要素</span><span class="sxs-lookup"><span data-stu-id="5b833-110">Child Elements</span></span>

<span data-ttu-id="5b833-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5b833-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5b833-112">親要素</span><span class="sxs-lookup"><span data-stu-id="5b833-112">Parent Elements</span></span>

|<span data-ttu-id="5b833-113">要素</span><span class="sxs-lookup"><span data-stu-id="5b833-113">Element</span></span>|<span data-ttu-id="5b833-114">説明</span><span class="sxs-lookup"><span data-stu-id="5b833-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5b833-115">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5b833-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="5b833-116">ワイドビューに表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="5b833-116">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5b833-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5b833-117">Text Value</span></span>

<span data-ttu-id="5b833-118">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5b833-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b833-119">解説</span><span class="sxs-lookup"><span data-stu-id="5b833-119">Remarks</span></span>

<span data-ttu-id="5b833-120">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b833-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5b833-121">例</span><span class="sxs-lookup"><span data-stu-id="5b833-121">Example</span></span>

<span data-ttu-id="5b833-122">この例[は、ProcessName オブジェクトの](/dotnet/api/System.Diagnostics.Process)プロパティの値を表示するワイドビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="5b833-122">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5b833-123">参照</span><span class="sxs-lookup"><span data-stu-id="5b833-123">See Also</span></span>

[<span data-ttu-id="5b833-124">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5b833-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="5b833-125">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="5b833-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="5b833-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="5b833-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
