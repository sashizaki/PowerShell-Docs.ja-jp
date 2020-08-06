---
title: GroupBy (Format) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e62762cf142bd2d20b21ad8f4249285bd3679280
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780269"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="2276e-102">GroupBy の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2276e-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="2276e-103">カスタムコントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="2276e-103">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="2276e-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2276e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2276e-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素に対して、groupby (形式) の CustomEntries 要素の CustomControl の CustomControl の CustomEntry 要素を指定します。 groupby (format) の EntrySelectedBy を指定します。 groupby (形式)</span><span class="sxs-lookup"><span data-stu-id="2276e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2276e-106">構文</span><span class="sxs-lookup"><span data-stu-id="2276e-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2276e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2276e-107">Attributes and Elements</span></span>

<span data-ttu-id="2276e-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="2276e-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2276e-109">属性</span><span class="sxs-lookup"><span data-stu-id="2276e-109">Attributes</span></span>

<span data-ttu-id="2276e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="2276e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2276e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="2276e-111">Child Elements</span></span>

<span data-ttu-id="2276e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="2276e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2276e-113">親要素</span><span class="sxs-lookup"><span data-stu-id="2276e-113">Parent Elements</span></span>

|<span data-ttu-id="2276e-114">要素</span><span class="sxs-lookup"><span data-stu-id="2276e-114">Element</span></span>|<span data-ttu-id="2276e-115">説明</span><span class="sxs-lookup"><span data-stu-id="2276e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2276e-116">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2276e-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="2276e-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2276e-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2276e-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2276e-118">Text Value</span></span>

<span data-ttu-id="2276e-119">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="2276e-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2276e-120">解説</span><span class="sxs-lookup"><span data-stu-id="2276e-120">Remarks</span></span>

<span data-ttu-id="2276e-121">各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2276e-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="2276e-122">カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2276e-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2276e-123">参照</span><span class="sxs-lookup"><span data-stu-id="2276e-123">See Also</span></span>

[<span data-ttu-id="2276e-124">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="2276e-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="2276e-125">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2276e-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="2276e-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2276e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
