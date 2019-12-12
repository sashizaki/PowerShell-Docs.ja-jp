---
title: CustomEntry for ビュー (Format) の EntrySelectedBy の TypeName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76548af7-05bd-4d12-bf71-6fb69c434ef2
caps.latest.revision: 10
ms.openlocfilehash: c3dd761cd9b6c468d4833ea35b897ba5d425f598
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368071"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="f94f9-102">View の CustomEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f94f9-102">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="f94f9-103">カスタムコントロールビューのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f94f9-103">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="f94f9-104">定義に指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="f94f9-104">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="f94f9-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素の CustomControl for view (format) EntrySelectedBy 要素 for view (Format) EntrySelectedByCustomentry for ビューの EntrySelectedBy ビュー (形式) のための CustomEntry for ビュー (形式) の TypeName 要素の要素</span><span class="sxs-lookup"><span data-stu-id="f94f9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f94f9-106">構文</span><span class="sxs-lookup"><span data-stu-id="f94f9-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f94f9-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f94f9-107">Attributes and Elements</span></span>

<span data-ttu-id="f94f9-108">次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f94f9-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f94f9-109">属性</span><span class="sxs-lookup"><span data-stu-id="f94f9-109">Attributes</span></span>

<span data-ttu-id="f94f9-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f94f9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f94f9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f94f9-111">Child Elements</span></span>

<span data-ttu-id="f94f9-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f94f9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f94f9-113">親要素</span><span class="sxs-lookup"><span data-stu-id="f94f9-113">Parent Elements</span></span>

|<span data-ttu-id="f94f9-114">要素</span><span class="sxs-lookup"><span data-stu-id="f94f9-114">Element</span></span>|<span data-ttu-id="f94f9-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="f94f9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f94f9-116">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="f94f9-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="f94f9-117">このカスタムコントロールビュー定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f94f9-117">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f94f9-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f94f9-118">Text Value</span></span>

<span data-ttu-id="f94f9-119">`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f94f9-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f94f9-120">コメント</span><span class="sxs-lookup"><span data-stu-id="f94f9-120">Remarks</span></span>

<span data-ttu-id="f94f9-121">各カスタムコントロールビュー定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f94f9-121">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f94f9-122">カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f94f9-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f94f9-123">参照</span><span class="sxs-lookup"><span data-stu-id="f94f9-123">See Also</span></span>

[<span data-ttu-id="f94f9-124">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="f94f9-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="f94f9-125">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="f94f9-125">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f94f9-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="f94f9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
