---
title: View (Format) コントロールの CustomEntries の CustomEntry 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6739205-2bc9-4507-b2af-d19d548c2057
caps.latest.revision: 6
ms.openlocfilehash: b92b99d88992cf13dbf7bfbe88aad603615f3138
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364051"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="bc359-102">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bc359-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="bc359-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="bc359-103">Provides a definition of the control.</span></span> <span data-ttu-id="bc359-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc359-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="bc359-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for View (Format) CustomEntry 要素 (ビューのコントロールの CustomEntries の場合)</span><span class="sxs-lookup"><span data-stu-id="bc359-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bc359-106">構文</span><span class="sxs-lookup"><span data-stu-id="bc359-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bc359-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="bc359-107">Attributes and Elements</span></span>

<span data-ttu-id="bc359-108">次のセクションでは、`CustomEntry` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc359-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bc359-109">属性</span><span class="sxs-lookup"><span data-stu-id="bc359-109">Attributes</span></span>

<span data-ttu-id="bc359-110">なし。</span><span class="sxs-lookup"><span data-stu-id="bc359-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bc359-111">子要素</span><span class="sxs-lookup"><span data-stu-id="bc359-111">Child Elements</span></span>

|<span data-ttu-id="bc359-112">要素</span><span class="sxs-lookup"><span data-stu-id="bc359-112">Element</span></span>|<span data-ttu-id="bc359-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="bc359-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bc359-114">ビューのコントロールに対する CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bc359-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="bc359-115">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="bc359-115">Optional element.</span></span><br /><br /> <span data-ttu-id="bc359-116">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="bc359-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="bc359-117">ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bc359-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="bc359-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="bc359-118">Required element.</span></span><br /><br /> <span data-ttu-id="bc359-119">コントロールがデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="bc359-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bc359-120">親要素</span><span class="sxs-lookup"><span data-stu-id="bc359-120">Parent Elements</span></span>

|<span data-ttu-id="bc359-121">要素</span><span class="sxs-lookup"><span data-stu-id="bc359-121">Element</span></span>|<span data-ttu-id="bc359-122">[説明]</span><span class="sxs-lookup"><span data-stu-id="bc359-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bc359-123">CustomControl for View (Format) の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="bc359-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="bc359-124">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="bc359-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bc359-125">コメント</span><span class="sxs-lookup"><span data-stu-id="bc359-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="bc359-126">参照</span><span class="sxs-lookup"><span data-stu-id="bc359-126">See Also</span></span>

[<span data-ttu-id="bc359-127">CustomControl for View (Format) の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="bc359-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bc359-128">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="bc359-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
