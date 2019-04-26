---
title: GroupBy (形式) の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 290d38e3-b9bd-4382-9671-2e28b32b7260
caps.latest.revision: 6
ms.openlocfilehash: a4036b1e9de85da7e0029e02cca9e0eaed462f70
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083775"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="8556e-102">GroupBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8556e-102">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="8556e-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="8556e-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="8556e-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8556e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="8556e-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の SelectionCondition の GroupBy (形式) の TypeName 要素 EntrySelectedBy の GroupBy (形式) SelectionCondition 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="8556e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8556e-106">構文</span><span class="sxs-lookup"><span data-stu-id="8556e-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="8556e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8556e-107">Attributes and Elements</span></span>

<span data-ttu-id="8556e-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="8556e-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8556e-109">属性</span><span class="sxs-lookup"><span data-stu-id="8556e-109">Attributes</span></span>

<span data-ttu-id="8556e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8556e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8556e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8556e-111">Child Elements</span></span>

<span data-ttu-id="8556e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="8556e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8556e-113">親要素</span><span class="sxs-lookup"><span data-stu-id="8556e-113">Parent Elements</span></span>

|<span data-ttu-id="8556e-114">要素</span><span class="sxs-lookup"><span data-stu-id="8556e-114">Element</span></span>|<span data-ttu-id="8556e-115">説明</span><span class="sxs-lookup"><span data-stu-id="8556e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8556e-116">GroupBy (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="8556e-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="8556e-117">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="8556e-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8556e-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8556e-118">Text Value</span></span>

<span data-ttu-id="8556e-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="8556e-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8556e-120">コメント</span><span class="sxs-lookup"><span data-stu-id="8556e-120">Remarks</span></span>

<span data-ttu-id="8556e-121">この要素が指定されている場合は指定できません、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="8556e-121">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="8556e-122">選択条件を定義する詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="8556e-122">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8556e-123">参照</span><span class="sxs-lookup"><span data-stu-id="8556e-123">See Also</span></span>

[<span data-ttu-id="8556e-124">GroupBy (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="8556e-124">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="8556e-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="8556e-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
