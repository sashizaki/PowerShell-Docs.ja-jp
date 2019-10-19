---
title: GroupBy (Format) の CustomControlName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368881"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="ebb25-102">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ebb25-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="ebb25-103">新しいグループを表示するために使用されるカスタムコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebb25-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="ebb25-104">この要素は、テーブル、リスト、ワイド、またはカスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebb25-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="ebb25-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) GroupBy 要素 (format) の CustomControlName 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebb25-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ebb25-106">構文</span><span class="sxs-lookup"><span data-stu-id="ebb25-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ebb25-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ebb25-107">Attributes and Elements</span></span>

<span data-ttu-id="ebb25-108">次のセクションでは、`CustomControlName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ebb25-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ebb25-109">属性</span><span class="sxs-lookup"><span data-stu-id="ebb25-109">Attributes</span></span>

<span data-ttu-id="ebb25-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ebb25-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ebb25-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ebb25-111">Child Elements</span></span>

<span data-ttu-id="ebb25-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ebb25-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ebb25-113">親要素</span><span class="sxs-lookup"><span data-stu-id="ebb25-113">Parent Elements</span></span>

|<span data-ttu-id="ebb25-114">要素</span><span class="sxs-lookup"><span data-stu-id="ebb25-114">Element</span></span>|<span data-ttu-id="ebb25-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="ebb25-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ebb25-116">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ebb25-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="ebb25-117">Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="ebb25-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ebb25-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ebb25-118">Text Value</span></span>

<span data-ttu-id="ebb25-119">新しいグループの表示に使用されるカスタムコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebb25-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="ebb25-120">コメント</span><span class="sxs-lookup"><span data-stu-id="ebb25-120">Remarks</span></span>

<span data-ttu-id="ebb25-121">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebb25-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="ebb25-122">次の要素は、これらのカスタムコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebb25-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="ebb25-123">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ebb25-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="ebb25-124">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ebb25-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="ebb25-125">参照</span><span class="sxs-lookup"><span data-stu-id="ebb25-125">See Also</span></span>

[<span data-ttu-id="ebb25-126">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ebb25-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="ebb25-127">構成用コントロールのコントロールの Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ebb25-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="ebb25-128">ビューのコントロールに対する Control の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ebb25-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="ebb25-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ebb25-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)