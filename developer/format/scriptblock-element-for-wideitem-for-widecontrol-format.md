---
title: WideItem WideControl (形式) 用のスクリプト ブロックの要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e00e8f36-76f2-49a0-9b02-3a2a7fceb2dd
caps.latest.revision: 8
ms.openlocfilehash: 6534e9dbfbe0dedf60dadd6467cff9ad9b447ba4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064205"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="fae27-102">WideControl の WideItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fae27-102">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="fae27-103">値をワイド ビューで表示するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fae27-103">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="fae27-104">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) WideItem 要素 (形式) スクリプト ブロックの構成要素 WideItem (形式)</span><span class="sxs-lookup"><span data-stu-id="fae27-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fae27-105">構文</span><span class="sxs-lookup"><span data-stu-id="fae27-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fae27-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fae27-106">Attributes and Elements</span></span>

<span data-ttu-id="fae27-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="fae27-107">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fae27-108">属性</span><span class="sxs-lookup"><span data-stu-id="fae27-108">Attributes</span></span>

<span data-ttu-id="fae27-109">なし。</span><span class="sxs-lookup"><span data-stu-id="fae27-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fae27-110">子要素</span><span class="sxs-lookup"><span data-stu-id="fae27-110">Child Elements</span></span>

<span data-ttu-id="fae27-111">なし。</span><span class="sxs-lookup"><span data-stu-id="fae27-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fae27-112">親要素</span><span class="sxs-lookup"><span data-stu-id="fae27-112">Parent Elements</span></span>

|<span data-ttu-id="fae27-113">要素</span><span class="sxs-lookup"><span data-stu-id="fae27-113">Element</span></span>|<span data-ttu-id="fae27-114">説明</span><span class="sxs-lookup"><span data-stu-id="fae27-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fae27-115">WideItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="fae27-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="fae27-116">表示幅値が表示されるプロパティまたはスクリプト ブロックを定義します。</span><span class="sxs-lookup"><span data-stu-id="fae27-116">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fae27-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="fae27-117">Text Value</span></span>

<span data-ttu-id="fae27-118">値が表示されているスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fae27-118">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="fae27-119">コメント</span><span class="sxs-lookup"><span data-stu-id="fae27-119">Remarks</span></span>

<span data-ttu-id="fae27-120">ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="fae27-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="fae27-121">例</span><span class="sxs-lookup"><span data-stu-id="fae27-121">Example</span></span>

<span data-ttu-id="fae27-122">この例では、`WideItem`値を持つが、ビューに表示するスクリプトを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="fae27-122">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="fae27-123">参照</span><span class="sxs-lookup"><span data-stu-id="fae27-123">See Also</span></span>

[<span data-ttu-id="fae27-124">WideItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="fae27-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="fae27-125">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="fae27-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="fae27-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="fae27-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
