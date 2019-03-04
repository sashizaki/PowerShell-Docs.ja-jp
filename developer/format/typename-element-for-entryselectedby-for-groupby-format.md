---
title: GroupBy (形式) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8b6739b-770c-432a-95ab-551c7507c51f
caps.latest.revision: 6
ms.openlocfilehash: 3b5ce60d3a0d76988af48f49445a5478a415d498
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861668"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="c8d0c-102">GroupBy の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c8d0c-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="c8d0c-103">この定義のカスタム コントロールを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8d0c-103">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="c8d0c-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8d0c-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="c8d0c-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の EntrySelectedBy の GroupBy (形式) の TypeName 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="c8d0c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c8d0c-106">構文</span><span class="sxs-lookup"><span data-stu-id="c8d0c-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c8d0c-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c8d0c-107">Attributes and Elements</span></span>

<span data-ttu-id="c8d0c-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="c8d0c-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c8d0c-109">属性</span><span class="sxs-lookup"><span data-stu-id="c8d0c-109">Attributes</span></span>

<span data-ttu-id="c8d0c-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c8d0c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c8d0c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c8d0c-111">Child Elements</span></span>

<span data-ttu-id="c8d0c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c8d0c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c8d0c-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c8d0c-113">Parent Elements</span></span>

|<span data-ttu-id="c8d0c-114">要素</span><span class="sxs-lookup"><span data-stu-id="c8d0c-114">Element</span></span>|<span data-ttu-id="c8d0c-115">説明</span><span class="sxs-lookup"><span data-stu-id="c8d0c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c8d0c-116">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="c8d0c-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="c8d0c-117">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8d0c-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c8d0c-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c8d0c-118">Text Value</span></span>

<span data-ttu-id="c8d0c-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="c8d0c-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8d0c-120">コメント</span><span class="sxs-lookup"><span data-stu-id="c8d0c-120">Remarks</span></span>

<span data-ttu-id="c8d0c-121">少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている各コントロールの定義が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8d0c-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="c8d0c-122">カスタム コントロールのビューのコンポーネントに関する詳細については、次を参照してください。[カスタム コントロールを作成する](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="c8d0c-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8d0c-123">参照</span><span class="sxs-lookup"><span data-stu-id="c8d0c-123">See Also</span></span>

[<span data-ttu-id="c8d0c-124">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="c8d0c-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="c8d0c-125">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="c8d0c-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="c8d0c-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="c8d0c-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
