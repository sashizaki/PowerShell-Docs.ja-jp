---
title: GroupBy (形式) のフレームの FirstLineHanging 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cdcf66e-96a5-47b5-9269-b4330bde29f2
caps.latest.revision: 6
ms.openlocfilehash: 08db1f2d89c3fe6c1e9a5a522de3071425042c3f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065835"
---
# <a name="firstlinehanging-element-for-frame-for-groupby-format"></a><span data-ttu-id="c3529-102">GroupBy の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c3529-102">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="c3529-103">データの最初の行が左にシフト文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3529-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="c3529-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3529-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="c3529-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) のフレームの GroupBy (形式) FirstLineHanging 要素 CustomItem の GroupBy (形式) フレーム要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="c3529-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineHanging Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c3529-106">構文</span><span class="sxs-lookup"><span data-stu-id="c3529-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c3529-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c3529-107">Attributes and Elements</span></span>

<span data-ttu-id="c3529-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineHanging`要素。</span><span class="sxs-lookup"><span data-stu-id="c3529-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c3529-109">属性</span><span class="sxs-lookup"><span data-stu-id="c3529-109">Attributes</span></span>

<span data-ttu-id="c3529-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c3529-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c3529-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c3529-111">Child Elements</span></span>

<span data-ttu-id="c3529-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c3529-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c3529-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c3529-113">Parent Elements</span></span>

|<span data-ttu-id="c3529-114">要素</span><span class="sxs-lookup"><span data-stu-id="c3529-114">Element</span></span>|<span data-ttu-id="c3529-115">説明</span><span class="sxs-lookup"><span data-stu-id="c3529-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c3529-116">GroupBy (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="c3529-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="c3529-117">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="c3529-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c3529-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c3529-118">Text Value</span></span>

<span data-ttu-id="c3529-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3529-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3529-120">コメント</span><span class="sxs-lookup"><span data-stu-id="c3529-120">Remarks</span></span>

<span data-ttu-id="c3529-121">この要素が指定されているかどうかは指定できません、 [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="c3529-121">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3529-122">参照</span><span class="sxs-lookup"><span data-stu-id="c3529-122">See Also</span></span>

[<span data-ttu-id="c3529-123">GroupBy (形式) のフレームの FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="c3529-123">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="c3529-124">GroupBy (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="c3529-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="c3529-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="c3529-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
