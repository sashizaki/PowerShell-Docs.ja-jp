---
title: 構成用のコントロールの式のバインドの PropertyName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f4343eeb157a1e3fc94a43c610ca5bdc94a5f667
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780911"
---
# <a name="propertyname-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="58b40-102">Configuration の Controls の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="58b40-102">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="58b40-103">コモンコントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="58b40-103">Specifies the .NET property whose value is displayed by the common control.</span></span> <span data-ttu-id="58b40-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="58b40-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="58b40-105">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) の CustomControl 要素の構成 (形式) の CustomControl の構成 (書式) の CustomEntries 要素のコントロール要素 CustomControl for Controls の構成 (書式) Customentries 要素のコントロールの構成式のバインド要素の構成のためのコントロールの構成 (format) PropertyName 要素の構成のためのコントロールの構成 (形式) のバインド要素</span><span class="sxs-lookup"><span data-stu-id="58b40-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="58b40-106">構文</span><span class="sxs-lookup"><span data-stu-id="58b40-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58b40-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="58b40-107">Attributes and Elements</span></span>

<span data-ttu-id="58b40-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="58b40-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="58b40-109">属性</span><span class="sxs-lookup"><span data-stu-id="58b40-109">Attributes</span></span>

<span data-ttu-id="58b40-110">なし。</span><span class="sxs-lookup"><span data-stu-id="58b40-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="58b40-111">子要素</span><span class="sxs-lookup"><span data-stu-id="58b40-111">Child Elements</span></span>

<span data-ttu-id="58b40-112">なし。</span><span class="sxs-lookup"><span data-stu-id="58b40-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="58b40-113">親要素</span><span class="sxs-lookup"><span data-stu-id="58b40-113">Parent Elements</span></span>

|<span data-ttu-id="58b40-114">要素</span><span class="sxs-lookup"><span data-stu-id="58b40-114">Element</span></span>|<span data-ttu-id="58b40-115">説明</span><span class="sxs-lookup"><span data-stu-id="58b40-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="58b40-116">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="58b40-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="58b40-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="58b40-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="58b40-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="58b40-118">Text Value</span></span>

<span data-ttu-id="58b40-119">コントロールによって表示される値を持つ .NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="58b40-119">Specify the name of the .NET property whose value is displayed by the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="58b40-120">解説</span><span class="sxs-lookup"><span data-stu-id="58b40-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="58b40-121">参照</span><span class="sxs-lookup"><span data-stu-id="58b40-121">See Also</span></span>

[<span data-ttu-id="58b40-122">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="58b40-122">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="58b40-123">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="58b40-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
