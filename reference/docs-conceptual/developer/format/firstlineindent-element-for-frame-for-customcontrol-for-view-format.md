---
title: CustomControl for View (Format) のフレームの FirstLineIndent 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0d51be5b5fc04bc0ea8442ca96767b1d9d8473a4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785814"
---
# <a name="firstlineindent-element-for-frame-for-customcontrol-for-view-format"></a><span data-ttu-id="41726-102">View の CustomControl の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41726-102">FirstLineIndent Element for Frame for CustomControl for View (Format)</span></span>

<span data-ttu-id="41726-103">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="41726-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="41726-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="41726-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="41726-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の customentries for CustomControl for view (format) Customentries 要素の CustomEntries for CustomControl for View (format) の Customentries 要素を使用して、for View (Format) FirstLineIndent 要素を設定します。</span><span class="sxs-lookup"><span data-stu-id="41726-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format) FirstLineIndent Element</span></span>

## <a name="syntax"></a><span data-ttu-id="41726-106">構文</span><span class="sxs-lookup"><span data-stu-id="41726-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41726-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="41726-107">Attributes and Elements</span></span>

<span data-ttu-id="41726-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineIndent` ます。</span><span class="sxs-lookup"><span data-stu-id="41726-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="41726-109">属性</span><span class="sxs-lookup"><span data-stu-id="41726-109">Attributes</span></span>

<span data-ttu-id="41726-110">なし。</span><span class="sxs-lookup"><span data-stu-id="41726-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="41726-111">子要素</span><span class="sxs-lookup"><span data-stu-id="41726-111">Child Elements</span></span>

<span data-ttu-id="41726-112">なし。</span><span class="sxs-lookup"><span data-stu-id="41726-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="41726-113">親要素</span><span class="sxs-lookup"><span data-stu-id="41726-113">Parent Elements</span></span>

|<span data-ttu-id="41726-114">要素</span><span class="sxs-lookup"><span data-stu-id="41726-114">Element</span></span>|<span data-ttu-id="41726-115">説明</span><span class="sxs-lookup"><span data-stu-id="41726-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41726-116">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41726-116">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="41726-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="41726-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="41726-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="41726-118">Text Value</span></span>

<span data-ttu-id="41726-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="41726-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="41726-120">解説</span><span class="sxs-lookup"><span data-stu-id="41726-120">Remarks</span></span>

<span data-ttu-id="41726-121">この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="41726-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="41726-122">参照</span><span class="sxs-lookup"><span data-stu-id="41726-122">See Also</span></span>

[<span data-ttu-id="41726-123">View の CustomControl の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41726-123">FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="41726-124">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41726-124">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="41726-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="41726-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
