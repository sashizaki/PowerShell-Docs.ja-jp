---
title: WideControl (形式) の要素を WideItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862628"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="05f80-102">WideControl の WideItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="05f80-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="05f80-103">プロパティまたは値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="05f80-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="05f80-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) WideItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="05f80-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="05f80-105">構文</span><span class="sxs-lookup"><span data-stu-id="05f80-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="05f80-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="05f80-106">Attributes and Elements</span></span>

<span data-ttu-id="05f80-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`WideItem`要素。</span><span class="sxs-lookup"><span data-stu-id="05f80-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="05f80-108">`FormatString` 要素は省略できます。</span><span class="sxs-lookup"><span data-stu-id="05f80-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="05f80-109">ただし、指定する必要があります、`PropertyName`または`ScriptBlock`が、要素は両方で指定できません。</span><span class="sxs-lookup"><span data-stu-id="05f80-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="05f80-110">属性</span><span class="sxs-lookup"><span data-stu-id="05f80-110">Attributes</span></span>

<span data-ttu-id="05f80-111">なし。</span><span class="sxs-lookup"><span data-stu-id="05f80-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="05f80-112">子要素</span><span class="sxs-lookup"><span data-stu-id="05f80-112">Child Elements</span></span>

|<span data-ttu-id="05f80-113">要素</span><span class="sxs-lookup"><span data-stu-id="05f80-113">Element</span></span>|<span data-ttu-id="05f80-114">説明</span><span class="sxs-lookup"><span data-stu-id="05f80-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="05f80-115">WideItem WideControl (形式) 用の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="05f80-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="05f80-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="05f80-116">Optional element.</span></span><br /><br /> <span data-ttu-id="05f80-117">ビューで、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="05f80-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="05f80-118">WideItem (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="05f80-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="05f80-119">表示幅値が表示されるオブジェクトのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="05f80-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="05f80-120">WideItem (形式) の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="05f80-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="05f80-121">値をワイド ビューで表示するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="05f80-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="05f80-122">親要素</span><span class="sxs-lookup"><span data-stu-id="05f80-122">Parent Elements</span></span>

|<span data-ttu-id="05f80-123">要素</span><span class="sxs-lookup"><span data-stu-id="05f80-123">Element</span></span>|<span data-ttu-id="05f80-124">説明</span><span class="sxs-lookup"><span data-stu-id="05f80-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="05f80-125">WideEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="05f80-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="05f80-126">ワイド ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="05f80-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="05f80-127">コメント</span><span class="sxs-lookup"><span data-stu-id="05f80-127">Remarks</span></span>

<span data-ttu-id="05f80-128">ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[表示幅が広い](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="05f80-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="05f80-129">例</span><span class="sxs-lookup"><span data-stu-id="05f80-129">Example</span></span>

<span data-ttu-id="05f80-130">次の例は、 `WideEntry` 、1 つを定義する要素`WideItem`要素。</span><span class="sxs-lookup"><span data-stu-id="05f80-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="05f80-131">`WideItem`プロパティまたは値を持つが、ビューで表示されているスクリプト要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="05f80-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="05f80-132">ワイド ビューの完全な例を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="05f80-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="05f80-133">参照</span><span class="sxs-lookup"><span data-stu-id="05f80-133">See Also</span></span>

[<span data-ttu-id="05f80-134">WideItem WideControl (形式) 用の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="05f80-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="05f80-135">WideItem (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="05f80-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="05f80-136">WideItem (形式) の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="05f80-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="05f80-137">WideEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="05f80-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="05f80-138">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="05f80-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
