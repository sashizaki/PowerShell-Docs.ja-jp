---
title: 構成用のコントロールの SelectionCondition の ScriptBlock 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb032dfc-9ef6-403c-b557-5858617e3483
caps.latest.revision: 6
ms.openlocfilehash: 102987970152420896a0c986f0973280ae209623
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368621"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="7988f-102">Configuration の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7988f-102">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="7988f-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7988f-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="7988f-104">このスクリプトが `true`に評価されると、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7988f-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="7988f-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7988f-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="7988f-106">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素Format) CustomControl 用の CustomEntry 要素を構成用のコントロール用に構成 (形式) します。構成用のコントロール (format) の構成 (format) の SelectionCondition 要素を構成するためのコントロール (形式)構成用のコントロールの SelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7988f-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7988f-107">構文</span><span class="sxs-lookup"><span data-stu-id="7988f-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7988f-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7988f-108">Attributes and Elements</span></span>

<span data-ttu-id="7988f-109">次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7988f-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7988f-110">属性</span><span class="sxs-lookup"><span data-stu-id="7988f-110">Attributes</span></span>

<span data-ttu-id="7988f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7988f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7988f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="7988f-112">Child Elements</span></span>

<span data-ttu-id="7988f-113">なし。</span><span class="sxs-lookup"><span data-stu-id="7988f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7988f-114">親要素</span><span class="sxs-lookup"><span data-stu-id="7988f-114">Parent Elements</span></span>

|<span data-ttu-id="7988f-115">要素</span><span class="sxs-lookup"><span data-stu-id="7988f-115">Element</span></span>|<span data-ttu-id="7988f-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="7988f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7988f-117">構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7988f-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="7988f-118">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7988f-118">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7988f-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7988f-119">Text Value</span></span>

<span data-ttu-id="7988f-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7988f-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="7988f-121">コメント</span><span class="sxs-lookup"><span data-stu-id="7988f-121">Remarks</span></span>

<span data-ttu-id="7988f-122">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7988f-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="7988f-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7988f-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7988f-124">参照</span><span class="sxs-lookup"><span data-stu-id="7988f-124">See Also</span></span>

[<span data-ttu-id="7988f-125">構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7988f-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="7988f-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="7988f-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
