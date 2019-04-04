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
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="07036-102">GroupBy の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="07036-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="07036-103">この定義のカスタム コントロールを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="07036-103">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="07036-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="07036-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="07036-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の EntrySelectedBy の GroupBy (形式) の TypeName 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="07036-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="07036-106">構文</span><span class="sxs-lookup"><span data-stu-id="07036-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="07036-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="07036-107">Attributes and Elements</span></span>

<span data-ttu-id="07036-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="07036-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="07036-109">属性</span><span class="sxs-lookup"><span data-stu-id="07036-109">Attributes</span></span>

<span data-ttu-id="07036-110">なし。</span><span class="sxs-lookup"><span data-stu-id="07036-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="07036-111">子要素</span><span class="sxs-lookup"><span data-stu-id="07036-111">Child Elements</span></span>

<span data-ttu-id="07036-112">なし。</span><span class="sxs-lookup"><span data-stu-id="07036-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="07036-113">親要素</span><span class="sxs-lookup"><span data-stu-id="07036-113">Parent Elements</span></span>

|<span data-ttu-id="07036-114">要素</span><span class="sxs-lookup"><span data-stu-id="07036-114">Element</span></span>|<span data-ttu-id="07036-115">説明</span><span class="sxs-lookup"><span data-stu-id="07036-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="07036-116">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="07036-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="07036-117">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="07036-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="07036-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="07036-118">Text Value</span></span>

<span data-ttu-id="07036-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="07036-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="07036-120">コメント</span><span class="sxs-lookup"><span data-stu-id="07036-120">Remarks</span></span>

<span data-ttu-id="07036-121">少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている各コントロールの定義が必要です。</span><span class="sxs-lookup"><span data-stu-id="07036-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="07036-122">カスタム コントロールのビューのコンポーネントに関する詳細については、[カスタム コントロールを作成する](./creating-custom-controls.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07036-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="07036-123">参照</span><span class="sxs-lookup"><span data-stu-id="07036-123">See Also</span></span>

[<span data-ttu-id="07036-124">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="07036-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="07036-125">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="07036-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="07036-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="07036-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
