---
title: GroupBy (形式) のフレームの FirstLineIndent 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33be3b9e-53c8-433f-8c11-c65b0d46744c
caps.latest.revision: 6
ms.openlocfilehash: 9ba6fc1b9924a4b0d5b56ee15290a2293217403c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858558"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a><span data-ttu-id="1373e-102">GroupBy の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1373e-102">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="1373e-103">データの最初の行が右側にシフトした文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1373e-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="1373e-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1373e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1373e-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) のフレームの GroupBy (形式) FirstLineIndent 要素 CustomItem の GroupBy (形式) フレーム要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="1373e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1373e-106">構文</span><span class="sxs-lookup"><span data-stu-id="1373e-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1373e-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="1373e-107">Attributes and Elements</span></span>

<span data-ttu-id="1373e-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineIndent`要素。</span><span class="sxs-lookup"><span data-stu-id="1373e-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1373e-109">属性</span><span class="sxs-lookup"><span data-stu-id="1373e-109">Attributes</span></span>

<span data-ttu-id="1373e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1373e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1373e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="1373e-111">Child Elements</span></span>

<span data-ttu-id="1373e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="1373e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1373e-113">親要素</span><span class="sxs-lookup"><span data-stu-id="1373e-113">Parent Elements</span></span>

|<span data-ttu-id="1373e-114">要素</span><span class="sxs-lookup"><span data-stu-id="1373e-114">Element</span></span>|<span data-ttu-id="1373e-115">説明</span><span class="sxs-lookup"><span data-stu-id="1373e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1373e-116">GroupBy (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="1373e-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="1373e-117">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="1373e-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1373e-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="1373e-118">Text Value</span></span>

<span data-ttu-id="1373e-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1373e-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="1373e-120">コメント</span><span class="sxs-lookup"><span data-stu-id="1373e-120">Remarks</span></span>

<span data-ttu-id="1373e-121">この要素が指定されているかどうかは指定できません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="1373e-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="1373e-122">参照</span><span class="sxs-lookup"><span data-stu-id="1373e-122">See Also</span></span>

[<span data-ttu-id="1373e-123">GroupBy (形式) のフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="1373e-123">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1373e-124">GroupBy (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="1373e-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="1373e-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="1373e-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
