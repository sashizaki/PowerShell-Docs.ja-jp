---
title: ビューのコントロールの SelectionCondition の PropertyName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92c4237d-c2b2-4908-82ac-f36070f89d26
caps.latest.revision: 6
ms.openlocfilehash: 79859bed3d762948182e03babf71d4270278bae7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362361"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="d0d45-102">View の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d0d45-102">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="d0d45-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0d45-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="d0d45-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、エントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0d45-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="d0d45-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0d45-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d0d45-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビュー用のコントロールの CustomControl (書式) の CustomEntry 要素のコントロール用のカスタムエントリのためのコントロールのためのコントロールのためのコントロールのためのコントロールのための、ビューのコントロールの EntrySelectedBy の SelectionCondition 要素を表示するためのコントロール (Format) ビューのコントロール (Format) の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="d0d45-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d0d45-107">構文</span><span class="sxs-lookup"><span data-stu-id="d0d45-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d0d45-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d0d45-108">Attributes and Elements</span></span>

<span data-ttu-id="d0d45-109">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0d45-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d0d45-110">属性</span><span class="sxs-lookup"><span data-stu-id="d0d45-110">Attributes</span></span>

<span data-ttu-id="d0d45-111">なし。</span><span class="sxs-lookup"><span data-stu-id="d0d45-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d0d45-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d0d45-112">Child Elements</span></span>

<span data-ttu-id="d0d45-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d0d45-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d0d45-114">親要素</span><span class="sxs-lookup"><span data-stu-id="d0d45-114">Parent Elements</span></span>

|<span data-ttu-id="d0d45-115">要素</span><span class="sxs-lookup"><span data-stu-id="d0d45-115">Element</span></span>|<span data-ttu-id="d0d45-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="d0d45-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d0d45-117">ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d0d45-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="d0d45-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d0d45-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d0d45-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d0d45-119">Text Value</span></span>

<span data-ttu-id="d0d45-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d0d45-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0d45-121">コメント</span><span class="sxs-lookup"><span data-stu-id="d0d45-121">Remarks</span></span>

<span data-ttu-id="d0d45-122">選択条件には、少なくとも1つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0d45-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="d0d45-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0d45-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0d45-124">参照</span><span class="sxs-lookup"><span data-stu-id="d0d45-124">See Also</span></span>

[<span data-ttu-id="d0d45-125">ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d0d45-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="d0d45-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="d0d45-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
