---
title: 構成用のコントロールの SelectionCondition の PropertyName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec048408-e1c6-41ef-b39b-72f4c2dcf2ac
caps.latest.revision: 6
ms.openlocfilehash: b4b2440fdb7171d09fdc16ac7cc4f25ed1a4bb78
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362401"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="b32b3-102">Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b32b3-102">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b32b3-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="b32b3-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="b32b3-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、エントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b32b3-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="b32b3-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b32b3-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b32b3-106">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素Format) CustomControl 用の CustomEntry 要素を構成するためのコントロールのためのコントロール用の構成 (形式) の構成 (形式) のために、customentry の configuration (書式) の Selectionselectedby 構成用の EntrySelectedBy の SelectionCondition 要素 (Format) ListEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b32b3-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b32b3-107">構文</span><span class="sxs-lookup"><span data-stu-id="b32b3-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b32b3-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b32b3-108">Attributes and Elements</span></span>

<span data-ttu-id="b32b3-109">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b32b3-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b32b3-110">属性</span><span class="sxs-lookup"><span data-stu-id="b32b3-110">Attributes</span></span>

<span data-ttu-id="b32b3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b32b3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b32b3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b32b3-112">Child Elements</span></span>

<span data-ttu-id="b32b3-113">なし。</span><span class="sxs-lookup"><span data-stu-id="b32b3-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b32b3-114">親要素</span><span class="sxs-lookup"><span data-stu-id="b32b3-114">Parent Elements</span></span>

|<span data-ttu-id="b32b3-115">要素</span><span class="sxs-lookup"><span data-stu-id="b32b3-115">Element</span></span>|<span data-ttu-id="b32b3-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="b32b3-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b32b3-117">構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b32b3-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="b32b3-118">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="b32b3-118">Defines a condition that must exist for a common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b32b3-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b32b3-119">Text Value</span></span>

<span data-ttu-id="b32b3-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b32b3-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="b32b3-121">コメント</span><span class="sxs-lookup"><span data-stu-id="b32b3-121">Remarks</span></span>

<span data-ttu-id="b32b3-122">選択条件には、少なくとも1つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b32b3-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="b32b3-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b32b3-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b32b3-124">参照</span><span class="sxs-lookup"><span data-stu-id="b32b3-124">See Also</span></span>

[<span data-ttu-id="b32b3-125">構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b32b3-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="b32b3-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="b32b3-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
