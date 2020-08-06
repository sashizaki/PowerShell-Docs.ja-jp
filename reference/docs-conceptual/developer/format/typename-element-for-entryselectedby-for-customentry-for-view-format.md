---
title: CustomEntry for ビュー (Format) の EntrySelectedBy の TypeName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f8dc2c808e6eb3d6a7873cdbddc936b95d94c541
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785100"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="1fdc6-102">View の CustomEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1fdc6-102">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="1fdc6-103">カスタムコントロールビューのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-103">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="1fdc6-104">定義に指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-104">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="1fdc6-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) CustomControl 要素 (形式) の CustomEntries for view (format) CustomControl for view (format) を使用して、customentry for ビューの entryselectedby 要素を指定します。この要素は、customentry for View 用の EntrySelectedBy の TypeName 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1fdc6-106">構文</span><span class="sxs-lookup"><span data-stu-id="1fdc6-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1fdc6-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1fdc6-107">Attributes and Elements</span></span>

<span data-ttu-id="1fdc6-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1fdc6-109">属性</span><span class="sxs-lookup"><span data-stu-id="1fdc6-109">Attributes</span></span>

<span data-ttu-id="1fdc6-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1fdc6-111">子要素</span><span class="sxs-lookup"><span data-stu-id="1fdc6-111">Child Elements</span></span>

<span data-ttu-id="1fdc6-112">なし。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1fdc6-113">親要素</span><span class="sxs-lookup"><span data-stu-id="1fdc6-113">Parent Elements</span></span>

|<span data-ttu-id="1fdc6-114">要素</span><span class="sxs-lookup"><span data-stu-id="1fdc6-114">Element</span></span>|<span data-ttu-id="1fdc6-115">説明</span><span class="sxs-lookup"><span data-stu-id="1fdc6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1fdc6-116">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="1fdc6-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="1fdc6-117">このカスタムコントロールビュー定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-117">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1fdc6-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="1fdc6-118">Text Value</span></span>

<span data-ttu-id="1fdc6-119">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fdc6-120">解説</span><span class="sxs-lookup"><span data-stu-id="1fdc6-120">Remarks</span></span>

<span data-ttu-id="1fdc6-121">各カスタムコントロールビュー定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-121">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="1fdc6-122">カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdc6-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1fdc6-123">参照</span><span class="sxs-lookup"><span data-stu-id="1fdc6-123">See Also</span></span>

[<span data-ttu-id="1fdc6-124">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="1fdc6-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="1fdc6-125">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="1fdc6-125">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="1fdc6-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="1fdc6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
