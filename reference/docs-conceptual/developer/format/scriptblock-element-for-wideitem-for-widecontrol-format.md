---
title: WideItem for WideControl (Format) の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e00e8f36-76f2-49a0-9b02-3a2a7fceb2dd
caps.latest.revision: 8
ms.openlocfilehash: 6534e9dbfbe0dedf60dadd6467cff9ad9b447ba4
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362031"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="087a0-102">WideControl の WideItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="087a0-102">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="087a0-103">ワイドビューに値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="087a0-103">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="087a0-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideItem Element (format) Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="087a0-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="087a0-105">構文</span><span class="sxs-lookup"><span data-stu-id="087a0-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="087a0-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="087a0-106">Attributes and Elements</span></span>

<span data-ttu-id="087a0-107">次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="087a0-107">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="087a0-108">属性</span><span class="sxs-lookup"><span data-stu-id="087a0-108">Attributes</span></span>

<span data-ttu-id="087a0-109">なし。</span><span class="sxs-lookup"><span data-stu-id="087a0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="087a0-110">子要素</span><span class="sxs-lookup"><span data-stu-id="087a0-110">Child Elements</span></span>

<span data-ttu-id="087a0-111">なし。</span><span class="sxs-lookup"><span data-stu-id="087a0-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="087a0-112">親要素</span><span class="sxs-lookup"><span data-stu-id="087a0-112">Parent Elements</span></span>

|<span data-ttu-id="087a0-113">要素</span><span class="sxs-lookup"><span data-stu-id="087a0-113">Element</span></span>|<span data-ttu-id="087a0-114">説明</span><span class="sxs-lookup"><span data-stu-id="087a0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="087a0-115">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="087a0-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="087a0-116">ワイドビューに表示される値を持つプロパティまたはスクリプトブロックを定義します。</span><span class="sxs-lookup"><span data-stu-id="087a0-116">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="087a0-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="087a0-117">Text Value</span></span>

<span data-ttu-id="087a0-118">値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="087a0-118">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="087a0-119">コメント</span><span class="sxs-lookup"><span data-stu-id="087a0-119">Remarks</span></span>

<span data-ttu-id="087a0-120">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="087a0-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="087a0-121">例</span><span class="sxs-lookup"><span data-stu-id="087a0-121">Example</span></span>

<span data-ttu-id="087a0-122">この例は、ビューに値が表示されるスクリプトを定義する `WideItem` 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="087a0-122">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="087a0-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="087a0-123">See Also</span></span>

[<span data-ttu-id="087a0-124">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="087a0-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="087a0-125">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="087a0-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="087a0-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="087a0-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
