---
title: コントロールの構成 (形式) のフレームの FirstLineIndent 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f489720-11f6-4019-940e-07f423d4278d
caps.latest.revision: 6
ms.openlocfilehash: c5b2d971fe1590116f96b024ae8769334768acf2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856348"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="2a34a-102">Configuration の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2a34a-102">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="2a34a-103">データの最初の行が右側にシフトした文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a34a-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="2a34a-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a34a-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="2a34a-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素CustomEntry CustomItem のフレームの構成 (形式) FirstLineIndent 要素のコントロールの構成のフレーム要素のコントロール用の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素コントロールの構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="2a34a-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2a34a-106">構文</span><span class="sxs-lookup"><span data-stu-id="2a34a-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2a34a-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2a34a-107">Attributes and Elements</span></span>

<span data-ttu-id="2a34a-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`FirstLineIndent`要素。</span><span class="sxs-lookup"><span data-stu-id="2a34a-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2a34a-109">属性</span><span class="sxs-lookup"><span data-stu-id="2a34a-109">Attributes</span></span>

<span data-ttu-id="2a34a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="2a34a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2a34a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="2a34a-111">Child Elements</span></span>

<span data-ttu-id="2a34a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="2a34a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2a34a-113">親要素</span><span class="sxs-lookup"><span data-stu-id="2a34a-113">Parent Elements</span></span>

|<span data-ttu-id="2a34a-114">要素</span><span class="sxs-lookup"><span data-stu-id="2a34a-114">Element</span></span>|<span data-ttu-id="2a34a-115">説明</span><span class="sxs-lookup"><span data-stu-id="2a34a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2a34a-116">構成 (形式) のコントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="2a34a-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="2a34a-117">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="2a34a-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2a34a-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2a34a-118">Text Value</span></span>

<span data-ttu-id="2a34a-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a34a-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a34a-120">コメント</span><span class="sxs-lookup"><span data-stu-id="2a34a-120">Remarks</span></span>

<span data-ttu-id="2a34a-121">この要素が指定されているかどうかは指定できません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="2a34a-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a34a-122">参照</span><span class="sxs-lookup"><span data-stu-id="2a34a-122">See Also</span></span>

[<span data-ttu-id="2a34a-123">コントロールの構成 (形式) のフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="2a34a-123">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="2a34a-124">構成 (形式) のコントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="2a34a-124">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="2a34a-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="2a34a-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
