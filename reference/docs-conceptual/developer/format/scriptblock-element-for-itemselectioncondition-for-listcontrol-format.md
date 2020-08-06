---
title: ListControl の ItemSelectionCondition の ScriptBlock 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 38dc952bfadd6aed24bae8cbef05adcd22e61dd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787633"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="44b48-102">ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44b48-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="44b48-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="44b48-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="44b48-104">このスクリプトがに評価されると、 `true` 条件が満たされ、リスト項目が使用されます。</span><span class="sxs-lookup"><span data-stu-id="44b48-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="44b48-105">この要素は、リストビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="44b48-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="44b48-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListControl (format) ListEntry 要素の listentries for ListControl (Format) ListItems 要素の ListEntries 要素 ListEntry for ListControl (Format) の ListItem 要素 for ListItems for List コントロール (format) ItemSelectionCondition の ItemSelectionCondition for ListControl (Format) ScriptBlock 要素 for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="44b48-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="44b48-107">構文</span><span class="sxs-lookup"><span data-stu-id="44b48-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="44b48-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="44b48-108">Attributes and Elements</span></span>

<span data-ttu-id="44b48-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="44b48-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="44b48-110">属性</span><span class="sxs-lookup"><span data-stu-id="44b48-110">Attributes</span></span>

<span data-ttu-id="44b48-111">なし。</span><span class="sxs-lookup"><span data-stu-id="44b48-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="44b48-112">子要素</span><span class="sxs-lookup"><span data-stu-id="44b48-112">Child Elements</span></span>

<span data-ttu-id="44b48-113">なし。</span><span class="sxs-lookup"><span data-stu-id="44b48-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="44b48-114">親要素</span><span class="sxs-lookup"><span data-stu-id="44b48-114">Parent Elements</span></span>

|<span data-ttu-id="44b48-115">要素</span><span class="sxs-lookup"><span data-stu-id="44b48-115">Element</span></span>|<span data-ttu-id="44b48-116">説明</span><span class="sxs-lookup"><span data-stu-id="44b48-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44b48-117">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44b48-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="44b48-118">このリスト項目を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="44b48-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="44b48-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="44b48-119">Text Value</span></span>

<span data-ttu-id="44b48-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="44b48-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="44b48-121">解説</span><span class="sxs-lookup"><span data-stu-id="44b48-121">Remarks</span></span>

<span data-ttu-id="44b48-122">この要素が使用されている場合、 `PropertyName` 選択条件を定義するときに要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="44b48-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="44b48-123">参照</span><span class="sxs-lookup"><span data-stu-id="44b48-123">See Also</span></span>

[<span data-ttu-id="44b48-124">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="44b48-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
