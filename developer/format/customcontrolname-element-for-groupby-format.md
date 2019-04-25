---
title: GroupBy (形式) の要素を CustomControlName |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066544"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="93a1e-102">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="93a1e-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="93a1e-103">新しいグループを表示するために使用するカスタム コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="93a1e-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="93a1e-104">この要素は、テーブル、リスト、ワイドまたはカスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="93a1e-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="93a1e-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) の GroupBy (形式) のビュー (形式) CustomControlName 要素の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="93a1e-106">構文</span><span class="sxs-lookup"><span data-stu-id="93a1e-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93a1e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-107">Attributes and Elements</span></span>

<span data-ttu-id="93a1e-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControlName`要素。</span><span class="sxs-lookup"><span data-stu-id="93a1e-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="93a1e-109">属性</span><span class="sxs-lookup"><span data-stu-id="93a1e-109">Attributes</span></span>

<span data-ttu-id="93a1e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="93a1e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93a1e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-111">Child Elements</span></span>

<span data-ttu-id="93a1e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="93a1e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="93a1e-113">親要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-113">Parent Elements</span></span>

|<span data-ttu-id="93a1e-114">要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-114">Element</span></span>|<span data-ttu-id="93a1e-115">説明</span><span class="sxs-lookup"><span data-stu-id="93a1e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93a1e-116">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="93a1e-117">Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="93a1e-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="93a1e-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="93a1e-118">Text Value</span></span>

<span data-ttu-id="93a1e-119">新しいグループを表示するために使用するカスタム コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="93a1e-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="93a1e-120">コメント</span><span class="sxs-lookup"><span data-stu-id="93a1e-120">Remarks</span></span>

<span data-ttu-id="93a1e-121">書式設定ファイルでは、すべてのビューで使用できる一般的なコントロールを作成して、特定のビューで使用できるビュー コントロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="93a1e-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="93a1e-122">次の要素は、これらのカスタム コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="93a1e-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="93a1e-123">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="93a1e-124">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="93a1e-125">参照</span><span class="sxs-lookup"><span data-stu-id="93a1e-125">See Also</span></span>

[<span data-ttu-id="93a1e-126">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="93a1e-127">構成 (形式) のコントロールのコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="93a1e-128">コントロールが表示されます (形式) のコントロールの name 要素</span><span class="sxs-lookup"><span data-stu-id="93a1e-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="93a1e-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="93a1e-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
