---
title: ビューのコントロールのコントロールの Name 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365101"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="ff19a-102">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ff19a-102">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="ff19a-103">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff19a-103">Specifies the name of the control.</span></span>

<span data-ttu-id="ff19a-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素 (format) を表示するコントロールの要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ff19a-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ff19a-105">構文</span><span class="sxs-lookup"><span data-stu-id="ff19a-105">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ff19a-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ff19a-106">Attributes and Elements</span></span>

<span data-ttu-id="ff19a-107">次のセクションでは、属性、子要素、`Name` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff19a-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ff19a-108">属性</span><span class="sxs-lookup"><span data-stu-id="ff19a-108">Attributes</span></span>

<span data-ttu-id="ff19a-109">なし。</span><span class="sxs-lookup"><span data-stu-id="ff19a-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ff19a-110">子要素</span><span class="sxs-lookup"><span data-stu-id="ff19a-110">Child Elements</span></span>

<span data-ttu-id="ff19a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ff19a-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ff19a-112">親要素</span><span class="sxs-lookup"><span data-stu-id="ff19a-112">Parent Elements</span></span>

|<span data-ttu-id="ff19a-113">要素</span><span class="sxs-lookup"><span data-stu-id="ff19a-113">Element</span></span>|<span data-ttu-id="ff19a-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="ff19a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff19a-115">ビューのコントロールの Control 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ff19a-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="ff19a-116">ビューで使用できるコントロールと、コントロールを参照するために使用される名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="ff19a-116">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ff19a-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ff19a-117">Text Value</span></span>

<span data-ttu-id="ff19a-118">コントロールを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff19a-118">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff19a-119">コメント</span><span class="sxs-lookup"><span data-stu-id="ff19a-119">Remarks</span></span>

<span data-ttu-id="ff19a-120">ここで指定した名前は、このコントロールを参照するために次の要素で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff19a-120">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="ff19a-121">テーブル、リスト、ワイドコントロール、またはカスタムコントロールビューを作成するときに、コントロールを指定するには、次の要素を使用します。 [GroupBy 要素 (Format)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="ff19a-121">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="ff19a-122">ビューで使用できる別のコントロールを作成する場合、このコントロールは、[ビュー (Format) のコントロールの CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="ff19a-122">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="ff19a-123">参照</span><span class="sxs-lookup"><span data-stu-id="ff19a-123">See Also</span></span>

[<span data-ttu-id="ff19a-124">ビューの GroupBy 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ff19a-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="ff19a-125">ビューのコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ff19a-125">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="ff19a-126">ビューのコントロールの Control 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ff19a-126">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="ff19a-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ff19a-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
