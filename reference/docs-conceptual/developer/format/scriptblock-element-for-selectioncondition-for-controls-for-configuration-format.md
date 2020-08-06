---
title: 構成用のコントロールの SelectionCondition の ScriptBlock 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 24584aacd7869abd3dcfc6ff546e6dea4c2c04fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785440"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="e4613-102">Configuration の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4613-102">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e4613-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4613-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="e4613-104">このスクリプトがに評価されると、 `true` 条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4613-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="e4613-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4613-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e4613-106">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) の CustomControl 要素の構成のためのコントロールの要素の構成 (書式) の CustomControl の構成 (形式) の CustomEntries 要素 CustomControl for Controls の CustomEntry 要素構成 (形式) のために、CustomEntry for コントロールの構成 (形式) の SelectionCondition 要素を構成するためのコントロール用の EntrySelectedBy の構成 (形式) のコントロールの SelectionCondition の要素</span><span class="sxs-lookup"><span data-stu-id="e4613-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e4613-107">構文</span><span class="sxs-lookup"><span data-stu-id="e4613-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e4613-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e4613-108">Attributes and Elements</span></span>

<span data-ttu-id="e4613-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="e4613-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e4613-110">属性</span><span class="sxs-lookup"><span data-stu-id="e4613-110">Attributes</span></span>

<span data-ttu-id="e4613-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e4613-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e4613-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e4613-112">Child Elements</span></span>

<span data-ttu-id="e4613-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e4613-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e4613-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e4613-114">Parent Elements</span></span>

|<span data-ttu-id="e4613-115">要素</span><span class="sxs-lookup"><span data-stu-id="e4613-115">Element</span></span>|<span data-ttu-id="e4613-116">説明</span><span class="sxs-lookup"><span data-stu-id="e4613-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e4613-117">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4613-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="e4613-118">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e4613-118">Defines a condition that must exist for the common control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e4613-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e4613-119">Text Value</span></span>

<span data-ttu-id="e4613-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4613-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4613-121">解説</span><span class="sxs-lookup"><span data-stu-id="e4613-121">Remarks</span></span>

<span data-ttu-id="e4613-122">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4613-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="e4613-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4613-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4613-124">参照</span><span class="sxs-lookup"><span data-stu-id="e4613-124">See Also</span></span>

[<span data-ttu-id="e4613-125">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4613-125">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="e4613-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e4613-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
