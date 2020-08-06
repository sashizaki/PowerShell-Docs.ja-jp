---
title: WideItem for WideControl (Format) の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: be649d6de0d2dfa6bad14f2d7476cced9cd6cb6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787599"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="a28a9-102">WideControl の WideItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a28a9-102">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="a28a9-103">ワイドビューに値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a28a9-103">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="a28a9-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideItem Element (format) Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a28a9-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a28a9-105">構文</span><span class="sxs-lookup"><span data-stu-id="a28a9-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a28a9-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a28a9-106">Attributes and Elements</span></span>

<span data-ttu-id="a28a9-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="a28a9-107">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a28a9-108">属性</span><span class="sxs-lookup"><span data-stu-id="a28a9-108">Attributes</span></span>

<span data-ttu-id="a28a9-109">なし。</span><span class="sxs-lookup"><span data-stu-id="a28a9-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a28a9-110">子要素</span><span class="sxs-lookup"><span data-stu-id="a28a9-110">Child Elements</span></span>

<span data-ttu-id="a28a9-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a28a9-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a28a9-112">親要素</span><span class="sxs-lookup"><span data-stu-id="a28a9-112">Parent Elements</span></span>

|<span data-ttu-id="a28a9-113">要素</span><span class="sxs-lookup"><span data-stu-id="a28a9-113">Element</span></span>|<span data-ttu-id="a28a9-114">説明</span><span class="sxs-lookup"><span data-stu-id="a28a9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a28a9-115">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a28a9-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="a28a9-116">ワイドビューに表示される値を持つプロパティまたはスクリプトブロックを定義します。</span><span class="sxs-lookup"><span data-stu-id="a28a9-116">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a28a9-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a28a9-117">Text Value</span></span>

<span data-ttu-id="a28a9-118">値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a28a9-118">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="a28a9-119">解説</span><span class="sxs-lookup"><span data-stu-id="a28a9-119">Remarks</span></span>

<span data-ttu-id="a28a9-120">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a28a9-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a28a9-121">例</span><span class="sxs-lookup"><span data-stu-id="a28a9-121">Example</span></span>

<span data-ttu-id="a28a9-122">この例では、 `WideItem` ビューに値が表示されるスクリプトを定義する要素を示します。</span><span class="sxs-lookup"><span data-stu-id="a28a9-122">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="a28a9-123">参照</span><span class="sxs-lookup"><span data-stu-id="a28a9-123">See Also</span></span>

[<span data-ttu-id="a28a9-124">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a28a9-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="a28a9-125">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="a28a9-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a28a9-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a28a9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
