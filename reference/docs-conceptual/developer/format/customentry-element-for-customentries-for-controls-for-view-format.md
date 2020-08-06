---
title: View (Format) コントロールの CustomEntries の CustomEntry 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4fc960ab803580f684ce0f224b1db4d7d4af1720
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785899"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="4f1a3-102">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4f1a3-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="4f1a3-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="4f1a3-103">Provides a definition of the control.</span></span> <span data-ttu-id="4f1a3-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f1a3-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="4f1a3-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (形式) コントロールのコントロール要素を表示するコントロールのコントロールの要素 (書式) の CustomControl 要素 (format) ビューのコントロールの CustomEntries の CustomControl for ビュー (形式) のカスタムエントリ要素</span><span class="sxs-lookup"><span data-stu-id="4f1a3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4f1a3-106">構文</span><span class="sxs-lookup"><span data-stu-id="4f1a3-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4f1a3-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4f1a3-107">Attributes and Elements</span></span>

<span data-ttu-id="4f1a3-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="4f1a3-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4f1a3-109">属性</span><span class="sxs-lookup"><span data-stu-id="4f1a3-109">Attributes</span></span>

<span data-ttu-id="4f1a3-110">なし。</span><span class="sxs-lookup"><span data-stu-id="4f1a3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4f1a3-111">子要素</span><span class="sxs-lookup"><span data-stu-id="4f1a3-111">Child Elements</span></span>

|<span data-ttu-id="4f1a3-112">要素</span><span class="sxs-lookup"><span data-stu-id="4f1a3-112">Element</span></span>|<span data-ttu-id="4f1a3-113">説明</span><span class="sxs-lookup"><span data-stu-id="4f1a3-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f1a3-114">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4f1a3-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="4f1a3-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4f1a3-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4f1a3-116">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4f1a3-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="4f1a3-117">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4f1a3-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="4f1a3-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="4f1a3-118">Required element.</span></span><br /><br /> <span data-ttu-id="4f1a3-119">コントロールがデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="4f1a3-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4f1a3-120">親要素</span><span class="sxs-lookup"><span data-stu-id="4f1a3-120">Parent Elements</span></span>

|<span data-ttu-id="4f1a3-121">要素</span><span class="sxs-lookup"><span data-stu-id="4f1a3-121">Element</span></span>|<span data-ttu-id="4f1a3-122">説明</span><span class="sxs-lookup"><span data-stu-id="4f1a3-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f1a3-123">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4f1a3-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="4f1a3-124">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="4f1a3-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4f1a3-125">解説</span><span class="sxs-lookup"><span data-stu-id="4f1a3-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="4f1a3-126">参照</span><span class="sxs-lookup"><span data-stu-id="4f1a3-126">See Also</span></span>

[<span data-ttu-id="4f1a3-127">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4f1a3-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="4f1a3-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4f1a3-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
