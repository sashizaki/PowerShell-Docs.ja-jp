---
title: コントロールが表示されます (形式) の CustomEntries CustomEntry 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6739205-2bc9-4507-b2af-d19d548c2057
caps.latest.revision: 6
ms.openlocfilehash: b92b99d88992cf13dbf7bfbe88aad603615f3138
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858778"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="41dce-102">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41dce-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="41dce-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="41dce-103">Provides a definition of the control.</span></span> <span data-ttu-id="41dce-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="41dce-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="41dce-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールコントロールが表示されます (形式) の CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="41dce-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="41dce-106">構文</span><span class="sxs-lookup"><span data-stu-id="41dce-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41dce-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="41dce-107">Attributes and Elements</span></span>

<span data-ttu-id="41dce-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="41dce-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="41dce-109">属性</span><span class="sxs-lookup"><span data-stu-id="41dce-109">Attributes</span></span>

<span data-ttu-id="41dce-110">なし。</span><span class="sxs-lookup"><span data-stu-id="41dce-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="41dce-111">子要素</span><span class="sxs-lookup"><span data-stu-id="41dce-111">Child Elements</span></span>

|<span data-ttu-id="41dce-112">要素</span><span class="sxs-lookup"><span data-stu-id="41dce-112">Element</span></span>|<span data-ttu-id="41dce-113">説明</span><span class="sxs-lookup"><span data-stu-id="41dce-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41dce-114">コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="41dce-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="41dce-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="41dce-115">Optional element.</span></span><br /><br /> <span data-ttu-id="41dce-116">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="41dce-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="41dce-117">コントロールが表示されます (形式) の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="41dce-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="41dce-118">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="41dce-118">Required element.</span></span><br /><br /> <span data-ttu-id="41dce-119">コントロールがデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="41dce-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="41dce-120">親要素</span><span class="sxs-lookup"><span data-stu-id="41dce-120">Parent Elements</span></span>

|<span data-ttu-id="41dce-121">要素</span><span class="sxs-lookup"><span data-stu-id="41dce-121">Element</span></span>|<span data-ttu-id="41dce-122">説明</span><span class="sxs-lookup"><span data-stu-id="41dce-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41dce-123">ビュー (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="41dce-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="41dce-124">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="41dce-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="41dce-125">コメント</span><span class="sxs-lookup"><span data-stu-id="41dce-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="41dce-126">参照</span><span class="sxs-lookup"><span data-stu-id="41dce-126">See Also</span></span>

[<span data-ttu-id="41dce-127">ビュー (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="41dce-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="41dce-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="41dce-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
