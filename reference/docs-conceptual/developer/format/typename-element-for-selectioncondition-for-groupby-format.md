---
title: GroupBy (Format) の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 290d38e3-b9bd-4382-9671-2e28b32b7260
caps.latest.revision: 6
ms.openlocfilehash: a4036b1e9de85da7e0029e02cca9e0eaed462f70
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361481"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="84db2-102">GroupBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="84db2-102">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="84db2-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="84db2-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="84db2-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="84db2-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="84db2-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl の Entryselectedby for groupby (format) Selectionselectedby 要素の Selectionselectedby を使用して、groupby (形式) の SelectionCondition に対して groupby (format) TypeName 要素の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="84db2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="84db2-106">構文</span><span class="sxs-lookup"><span data-stu-id="84db2-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="84db2-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="84db2-107">Attributes and Elements</span></span>

<span data-ttu-id="84db2-108">次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="84db2-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="84db2-109">属性</span><span class="sxs-lookup"><span data-stu-id="84db2-109">Attributes</span></span>

<span data-ttu-id="84db2-110">なし。</span><span class="sxs-lookup"><span data-stu-id="84db2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="84db2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="84db2-111">Child Elements</span></span>

<span data-ttu-id="84db2-112">なし。</span><span class="sxs-lookup"><span data-stu-id="84db2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="84db2-113">親要素</span><span class="sxs-lookup"><span data-stu-id="84db2-113">Parent Elements</span></span>

|<span data-ttu-id="84db2-114">要素</span><span class="sxs-lookup"><span data-stu-id="84db2-114">Element</span></span>|<span data-ttu-id="84db2-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="84db2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="84db2-116">GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="84db2-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="84db2-117">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="84db2-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="84db2-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="84db2-118">Text Value</span></span>

<span data-ttu-id="84db2-119">`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="84db2-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="84db2-120">コメント</span><span class="sxs-lookup"><span data-stu-id="84db2-120">Remarks</span></span>

<span data-ttu-id="84db2-121">この要素が指定されている場合、`SelectionSetName` 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="84db2-121">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="84db2-122">選択条件の定義の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84db2-122">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84db2-123">参照</span><span class="sxs-lookup"><span data-stu-id="84db2-123">See Also</span></span>

[<span data-ttu-id="84db2-124">GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="84db2-124">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="84db2-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="84db2-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
