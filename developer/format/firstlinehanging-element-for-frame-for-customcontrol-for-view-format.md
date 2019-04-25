---
title: ビュー (形式) のカスタム コントロールのフレームの FirstLineHanging 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6ac3d86-0529-4b93-9bc7-ee94fcef9618
caps.latest.revision: 8
ms.openlocfilehash: ea43e025f5f653ff000e1d7591b535e73da5c9e5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065973"
---
# <a name="firstlinehanging-element-for-frame-for-customcontrol-for-view-format"></a><span data-ttu-id="225c9-102">View の CustomControl の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="225c9-102">FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>

<span data-ttu-id="225c9-103">データの最初の行が左にシフト文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="225c9-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="225c9-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="225c9-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="225c9-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem ビュー (形式) のカスタム コントロールのフレームのビュー (形式) FirstLineHanging 要素のカスタム コントロール用のフレーム要素を CustomControlView (形式)</span><span class="sxs-lookup"><span data-stu-id="225c9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format) FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="225c9-106">構文</span><span class="sxs-lookup"><span data-stu-id="225c9-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="225c9-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="225c9-107">Attributes and Elements</span></span>

<span data-ttu-id="225c9-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineHanging`要素。</span><span class="sxs-lookup"><span data-stu-id="225c9-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="225c9-109">属性</span><span class="sxs-lookup"><span data-stu-id="225c9-109">Attributes</span></span>

<span data-ttu-id="225c9-110">なし。</span><span class="sxs-lookup"><span data-stu-id="225c9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="225c9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="225c9-111">Child Elements</span></span>

<span data-ttu-id="225c9-112">なし。</span><span class="sxs-lookup"><span data-stu-id="225c9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="225c9-113">親要素</span><span class="sxs-lookup"><span data-stu-id="225c9-113">Parent Elements</span></span>

|<span data-ttu-id="225c9-114">要素</span><span class="sxs-lookup"><span data-stu-id="225c9-114">Element</span></span>|<span data-ttu-id="225c9-115">説明</span><span class="sxs-lookup"><span data-stu-id="225c9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="225c9-116">ビュー (形式) のカスタム コントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="225c9-116">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="225c9-117">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="225c9-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="225c9-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="225c9-118">Text Value</span></span>

<span data-ttu-id="225c9-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="225c9-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="225c9-120">コメント</span><span class="sxs-lookup"><span data-stu-id="225c9-120">Remarks</span></span>

<span data-ttu-id="225c9-121">この要素が指定されているかどうかは指定できません、 [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="225c9-121">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="225c9-122">参照</span><span class="sxs-lookup"><span data-stu-id="225c9-122">See Also</span></span>

[<span data-ttu-id="225c9-123">ビュー (形式) のカスタム コントロールのフレームの FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="225c9-123">FirstLineIndent Element for Frame for CustomControl for View (Format)</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="225c9-124">ビュー (形式) のカスタム コントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="225c9-124">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="225c9-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="225c9-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
