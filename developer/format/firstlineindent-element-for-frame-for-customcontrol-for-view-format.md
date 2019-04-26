---
title: ビュー (形式) のカスタム コントロールのフレームの FirstLineIndent 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb4e1564-3fd3-4be3-b93e-ac90480e05c0
caps.latest.revision: 6
ms.openlocfilehash: 3130ecc69f7d1568bcbd392dd24e8cdcc3382905
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065871"
---
# <a name="firstlineindent-element-for-frame-for-customcontrol-for-view-format"></a><span data-ttu-id="42591-102">View の CustomControl の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42591-102">FirstLineIndent Element for Frame for CustomControl for View (Format)</span></span>

<span data-ttu-id="42591-103">データの最初の行が右側にシフトした文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="42591-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="42591-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="42591-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="42591-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem ビュー (形式) FirstLineIndent 要素のカスタム コントロール用のフレーム要素を CustomControlView (形式)</span><span class="sxs-lookup"><span data-stu-id="42591-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format) FirstLineIndent Element</span></span>

## <a name="syntax"></a><span data-ttu-id="42591-106">構文</span><span class="sxs-lookup"><span data-stu-id="42591-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="42591-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="42591-107">Attributes and Elements</span></span>

<span data-ttu-id="42591-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineIndent`要素。</span><span class="sxs-lookup"><span data-stu-id="42591-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="42591-109">属性</span><span class="sxs-lookup"><span data-stu-id="42591-109">Attributes</span></span>

<span data-ttu-id="42591-110">なし。</span><span class="sxs-lookup"><span data-stu-id="42591-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="42591-111">子要素</span><span class="sxs-lookup"><span data-stu-id="42591-111">Child Elements</span></span>

<span data-ttu-id="42591-112">なし。</span><span class="sxs-lookup"><span data-stu-id="42591-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="42591-113">親要素</span><span class="sxs-lookup"><span data-stu-id="42591-113">Parent Elements</span></span>

|<span data-ttu-id="42591-114">要素</span><span class="sxs-lookup"><span data-stu-id="42591-114">Element</span></span>|<span data-ttu-id="42591-115">説明</span><span class="sxs-lookup"><span data-stu-id="42591-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="42591-116">ビュー (形式) のカスタム コントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="42591-116">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="42591-117">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="42591-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="42591-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="42591-118">Text Value</span></span>

<span data-ttu-id="42591-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="42591-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="42591-120">コメント</span><span class="sxs-lookup"><span data-stu-id="42591-120">Remarks</span></span>

<span data-ttu-id="42591-121">この要素が指定されているかどうかは指定できません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="42591-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="42591-122">参照</span><span class="sxs-lookup"><span data-stu-id="42591-122">See Also</span></span>

[<span data-ttu-id="42591-123">ビュー (形式) のカスタム コントロールのフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="42591-123">FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="42591-124">ビュー (形式) のカスタム コントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="42591-124">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="42591-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="42591-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
