---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の WideItem の ScriptBlock 要素 (書式)
description: WideControl の WideItem の ScriptBlock 要素 (書式)
ms.openlocfilehash: 68e47926e5e6b846c8a0a3dbc16d1f0d59f11dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659877"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="cdd0c-103">WideControl の WideItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cdd0c-103">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="cdd0c-104">ワイドビューに値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdd0c-104">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="cdd0c-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideItem Element (format) Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="cdd0c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cdd0c-106">構文</span><span class="sxs-lookup"><span data-stu-id="cdd0c-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cdd0c-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cdd0c-107">Attributes and Elements</span></span>

<span data-ttu-id="cdd0c-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="cdd0c-108">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cdd0c-109">属性</span><span class="sxs-lookup"><span data-stu-id="cdd0c-109">Attributes</span></span>

<span data-ttu-id="cdd0c-110">なし。</span><span class="sxs-lookup"><span data-stu-id="cdd0c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cdd0c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="cdd0c-111">Child Elements</span></span>

<span data-ttu-id="cdd0c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cdd0c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cdd0c-113">親要素</span><span class="sxs-lookup"><span data-stu-id="cdd0c-113">Parent Elements</span></span>

|<span data-ttu-id="cdd0c-114">要素</span><span class="sxs-lookup"><span data-stu-id="cdd0c-114">Element</span></span>|<span data-ttu-id="cdd0c-115">説明</span><span class="sxs-lookup"><span data-stu-id="cdd0c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cdd0c-116">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cdd0c-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="cdd0c-117">ワイドビューに表示される値を持つプロパティまたはスクリプトブロックを定義します。</span><span class="sxs-lookup"><span data-stu-id="cdd0c-117">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cdd0c-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="cdd0c-118">Text Value</span></span>

<span data-ttu-id="cdd0c-119">値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdd0c-119">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdd0c-120">解説</span><span class="sxs-lookup"><span data-stu-id="cdd0c-120">Remarks</span></span>

<span data-ttu-id="cdd0c-121">ワイドビューのコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd0c-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="cdd0c-122">例</span><span class="sxs-lookup"><span data-stu-id="cdd0c-122">Example</span></span>

<span data-ttu-id="cdd0c-123">この例では、 `WideItem` ビューに値が表示されるスクリプトを定義する要素を示します。</span><span class="sxs-lookup"><span data-stu-id="cdd0c-123">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="cdd0c-124">参照</span><span class="sxs-lookup"><span data-stu-id="cdd0c-124">See Also</span></span>

[<span data-ttu-id="cdd0c-125">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cdd0c-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="cdd0c-126">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="cdd0c-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="cdd0c-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="cdd0c-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
