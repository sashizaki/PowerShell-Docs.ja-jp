---
title: ScriptBlock 要素の構成 (形式) のコントロールの SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb032dfc-9ef6-403c-b557-5858617e3483
caps.latest.revision: 6
ms.openlocfilehash: 102987970152420896a0c986f0973280ae209623
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064426"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="7f016-102">Configuration の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7f016-102">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="7f016-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f016-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="7f016-104">このスクリプトを評価するときに`true`条件が満たされ、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f016-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="7f016-105">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7f016-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="7f016-106">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素CustomEntry EntrySelectedBy の構成 (形式) のコントロールの構成 (形式) SelectionCondition 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素構成 (形式) のコントロールの SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="7f016-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7f016-107">構文</span><span class="sxs-lookup"><span data-stu-id="7f016-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7f016-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7f016-108">Attributes and Elements</span></span>

<span data-ttu-id="7f016-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="7f016-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7f016-110">属性</span><span class="sxs-lookup"><span data-stu-id="7f016-110">Attributes</span></span>

<span data-ttu-id="7f016-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7f016-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7f016-112">子要素</span><span class="sxs-lookup"><span data-stu-id="7f016-112">Child Elements</span></span>

<span data-ttu-id="7f016-113">なし。</span><span class="sxs-lookup"><span data-stu-id="7f016-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7f016-114">親要素</span><span class="sxs-lookup"><span data-stu-id="7f016-114">Parent Elements</span></span>

|<span data-ttu-id="7f016-115">要素</span><span class="sxs-lookup"><span data-stu-id="7f016-115">Element</span></span>|<span data-ttu-id="7f016-116">説明</span><span class="sxs-lookup"><span data-stu-id="7f016-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f016-117">構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7f016-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="7f016-118">使用する一般的なコントロールの定義を満たす必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7f016-118">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7f016-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7f016-119">Text Value</span></span>

<span data-ttu-id="7f016-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f016-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f016-121">コメント</span><span class="sxs-lookup"><span data-stu-id="7f016-121">Remarks</span></span>

<span data-ttu-id="7f016-122">選択条件が少なくとも 1 つスクリプトまたはプロパティの名前を評価するために指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7f016-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="7f016-123">選択条件を使用する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f016-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7f016-124">参照</span><span class="sxs-lookup"><span data-stu-id="7f016-124">See Also</span></span>

[<span data-ttu-id="7f016-125">構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7f016-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="7f016-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="7f016-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
