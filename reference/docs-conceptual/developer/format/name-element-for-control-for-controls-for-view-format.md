---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の Control の Name 要素 (書式)
description: View の Controls の Control の Name 要素 (書式)
ms.openlocfilehash: 52b7170777a35596767c34f2d58106dfa6479567
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666486"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a><span data-ttu-id="6ef9b-103">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ef9b-103">Name Element for Control for Controls for View (Format)</span></span>

<span data-ttu-id="6ef9b-104">コントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-104">Specifies the name of the control.</span></span>

<span data-ttu-id="6ef9b-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素 (format) を表示するコントロールの要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ef9b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) Name Element for Control for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6ef9b-106">構文</span><span class="sxs-lookup"><span data-stu-id="6ef9b-106">Syntax</span></span>

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ef9b-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6ef9b-107">Attributes and Elements</span></span>

<span data-ttu-id="6ef9b-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ef9b-109">属性</span><span class="sxs-lookup"><span data-stu-id="6ef9b-109">Attributes</span></span>

<span data-ttu-id="6ef9b-110">なし。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6ef9b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6ef9b-111">Child Elements</span></span>

<span data-ttu-id="6ef9b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6ef9b-113">親要素</span><span class="sxs-lookup"><span data-stu-id="6ef9b-113">Parent Elements</span></span>

|<span data-ttu-id="6ef9b-114">要素</span><span class="sxs-lookup"><span data-stu-id="6ef9b-114">Element</span></span>|<span data-ttu-id="6ef9b-115">説明</span><span class="sxs-lookup"><span data-stu-id="6ef9b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ef9b-116">ビューのコントロールの Control 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6ef9b-116">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="6ef9b-117">ビューで使用できるコントロールと、コントロールを参照するために使用される名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-117">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6ef9b-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="6ef9b-118">Text Value</span></span>

<span data-ttu-id="6ef9b-119">コントロールを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-119">Specify the name that is used to reference the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ef9b-120">解説</span><span class="sxs-lookup"><span data-stu-id="6ef9b-120">Remarks</span></span>

<span data-ttu-id="6ef9b-121">ここで指定した名前は、このコントロールを参照するために次の要素で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-121">The name specified here can be used in the following elements to reference this control.</span></span>

- <span data-ttu-id="6ef9b-122">テーブル、リスト、ワイドコントロール、またはカスタムコントロールビューを作成するときに、コントロールを指定するには、次の要素を使用します。 [GroupBy 要素 (Format)](./groupby-element-for-view-format.md)</span><span class="sxs-lookup"><span data-stu-id="6ef9b-122">When creating a table, list, wide or custom control view, the control can be specified by the following element: [GroupBy Element for View (Format)](./groupby-element-for-view-format.md)</span></span>

- <span data-ttu-id="6ef9b-123">ビューで使用できる別のコントロールを作成する場合、このコントロールは、[ビュー (Format) のコントロールの CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ef9b-123">When creating another control that can be used by a view, this control can be specified by the following element: [ExpressionBinding Element for CustomItem for Controls for View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="6ef9b-124">参照</span><span class="sxs-lookup"><span data-stu-id="6ef9b-124">See Also</span></span>

[<span data-ttu-id="6ef9b-125">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ef9b-125">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="6ef9b-126">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ef9b-126">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="6ef9b-127">ビューのコントロールの Control 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6ef9b-127">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="6ef9b-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="6ef9b-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
