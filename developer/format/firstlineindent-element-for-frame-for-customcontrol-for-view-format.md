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
ms.openlocfilehash: 9ec6caedcb7cf20d4aab2216cd8a9707269d9452
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854958"
---
# <a name="firstlineindent-element-for-frame-for-customcontrol-for-view-format"></a><span data-ttu-id="bd14c-102">View の CustomControl の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bd14c-102">FirstLineIndent Element for Frame for CustomControl for View (Format)</span></span>

<span data-ttu-id="bd14c-103">データの最初の行が右側にシフトした文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd14c-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="bd14c-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd14c-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="bd14c-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem ビュー (形式) FirstLineIndent 要素のカスタム コントロール用のフレーム要素を CutomControlView (形式)</span><span class="sxs-lookup"><span data-stu-id="bd14c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CutomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format) FirstLineIndent Element</span></span>

## <a name="syntax"></a><span data-ttu-id="bd14c-106">構文</span><span class="sxs-lookup"><span data-stu-id="bd14c-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bd14c-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="bd14c-107">Attributes and Elements</span></span>

<span data-ttu-id="bd14c-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineIndent`要素。</span><span class="sxs-lookup"><span data-stu-id="bd14c-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bd14c-109">属性</span><span class="sxs-lookup"><span data-stu-id="bd14c-109">Attributes</span></span>

<span data-ttu-id="bd14c-110">なし。</span><span class="sxs-lookup"><span data-stu-id="bd14c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bd14c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="bd14c-111">Child Elements</span></span>

<span data-ttu-id="bd14c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="bd14c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bd14c-113">親要素</span><span class="sxs-lookup"><span data-stu-id="bd14c-113">Parent Elements</span></span>

|<span data-ttu-id="bd14c-114">要素</span><span class="sxs-lookup"><span data-stu-id="bd14c-114">Element</span></span>|<span data-ttu-id="bd14c-115">説明</span><span class="sxs-lookup"><span data-stu-id="bd14c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bd14c-116">ビュー (形式) のカスタム コントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="bd14c-116">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="bd14c-117">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="bd14c-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bd14c-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="bd14c-118">Text Value</span></span>

<span data-ttu-id="bd14c-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd14c-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd14c-120">コメント</span><span class="sxs-lookup"><span data-stu-id="bd14c-120">Remarks</span></span>

<span data-ttu-id="bd14c-121">この要素が指定されているかどうかは指定できません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="bd14c-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd14c-122">参照</span><span class="sxs-lookup"><span data-stu-id="bd14c-122">See Also</span></span>

[<span data-ttu-id="bd14c-123">ビュー (形式) のカスタム コントロールのフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="bd14c-123">FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bd14c-124">ビュー (形式) のカスタム コントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="bd14c-124">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bd14c-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="bd14c-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
