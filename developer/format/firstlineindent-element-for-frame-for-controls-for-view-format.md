---
title: コントロールが表示されます (形式) のフレームの FirstLineIndent 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec63f4f9-8858-4529-8646-ffbbc278f83e
caps.latest.revision: 7
ms.openlocfilehash: 694c5baaa5e90a772257276ba139d90acf7ec0e3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066024"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="3671c-102">View の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3671c-102">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="3671c-103">データの最初の行が右側にシフトした文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3671c-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="3671c-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3671c-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="3671c-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem のフレームのビュー (形式) FirstLineIndent 要素のコントロールのビュー (形式) フレーム要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールビュー (形式) のコントロールの</span><span class="sxs-lookup"><span data-stu-id="3671c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineIndent Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3671c-106">構文</span><span class="sxs-lookup"><span data-stu-id="3671c-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3671c-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3671c-107">Attributes and Elements</span></span>

<span data-ttu-id="3671c-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineIndent`要素。</span><span class="sxs-lookup"><span data-stu-id="3671c-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3671c-109">属性</span><span class="sxs-lookup"><span data-stu-id="3671c-109">Attributes</span></span>

<span data-ttu-id="3671c-110">なし。</span><span class="sxs-lookup"><span data-stu-id="3671c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3671c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="3671c-111">Child Elements</span></span>

<span data-ttu-id="3671c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="3671c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3671c-113">親要素</span><span class="sxs-lookup"><span data-stu-id="3671c-113">Parent Elements</span></span>

|<span data-ttu-id="3671c-114">要素</span><span class="sxs-lookup"><span data-stu-id="3671c-114">Element</span></span>|<span data-ttu-id="3671c-115">説明</span><span class="sxs-lookup"><span data-stu-id="3671c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3671c-116">コントロールが表示されます (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="3671c-116">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="3671c-117">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="3671c-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3671c-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="3671c-118">Text Value</span></span>

<span data-ttu-id="3671c-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3671c-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="3671c-120">コメント</span><span class="sxs-lookup"><span data-stu-id="3671c-120">Remarks</span></span>

<span data-ttu-id="3671c-121">この要素が指定されているかどうかは指定できません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="3671c-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="3671c-122">参照</span><span class="sxs-lookup"><span data-stu-id="3671c-122">See Also</span></span>

[<span data-ttu-id="3671c-123">コントロールが表示されます (形式) のフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="3671c-123">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="3671c-124">コントロールが表示されます (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="3671c-124">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="3671c-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="3671c-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
