---
title: GroupBy (Format) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8b6739b-770c-432a-95ab-551c7507c51f
caps.latest.revision: 6
ms.openlocfilehash: 3b5ce60d3a0d76988af48f49445a5478a415d498
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361671"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="9528b-102">GroupBy の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9528b-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="9528b-103">カスタムコントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="9528b-103">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="9528b-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9528b-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="9528b-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl の Entryselectedby 要素のエントリ名を指定します。 groupby (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="9528b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9528b-106">構文</span><span class="sxs-lookup"><span data-stu-id="9528b-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9528b-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="9528b-107">Attributes and Elements</span></span>

<span data-ttu-id="9528b-108">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9528b-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9528b-109">属性</span><span class="sxs-lookup"><span data-stu-id="9528b-109">Attributes</span></span>

<span data-ttu-id="9528b-110">なし。</span><span class="sxs-lookup"><span data-stu-id="9528b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9528b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="9528b-111">Child Elements</span></span>

<span data-ttu-id="9528b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="9528b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9528b-113">親要素</span><span class="sxs-lookup"><span data-stu-id="9528b-113">Parent Elements</span></span>

|<span data-ttu-id="9528b-114">要素</span><span class="sxs-lookup"><span data-stu-id="9528b-114">Element</span></span>|<span data-ttu-id="9528b-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="9528b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9528b-116">GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9528b-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="9528b-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="9528b-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9528b-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="9528b-118">Text Value</span></span>

<span data-ttu-id="9528b-119">.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9528b-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9528b-120">コメント</span><span class="sxs-lookup"><span data-stu-id="9528b-120">Remarks</span></span>

<span data-ttu-id="9528b-121">各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9528b-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="9528b-122">カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9528b-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9528b-123">参照</span><span class="sxs-lookup"><span data-stu-id="9528b-123">See Also</span></span>

[<span data-ttu-id="9528b-124">カスタムコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="9528b-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="9528b-125">GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9528b-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="9528b-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="9528b-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
