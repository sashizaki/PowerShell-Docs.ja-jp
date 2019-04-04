---
title: TypeName 要素の表示 (形式) CustomEntry EntrySelectedBy |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76548af7-05bd-4d12-bf71-6fb69c434ef2
caps.latest.revision: 10
ms.openlocfilehash: c3dd761cd9b6c468d4833ea35b897ba5d425f598
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858838"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="a0a03-102">View の CustomEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0a03-102">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="a0a03-103">このカスタム コントロールのビューの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0a03-103">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="a0a03-104">定義に指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="a0a03-104">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="a0a03-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) EntrySelectedBy CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry EntrySelectedBy CustomEntry ビュー (形式) のためのビュー (形式) TypeName 要素の要素</span><span class="sxs-lookup"><span data-stu-id="a0a03-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a0a03-106">構文</span><span class="sxs-lookup"><span data-stu-id="a0a03-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0a03-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a0a03-107">Attributes and Elements</span></span>

<span data-ttu-id="a0a03-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="a0a03-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0a03-109">属性</span><span class="sxs-lookup"><span data-stu-id="a0a03-109">Attributes</span></span>

<span data-ttu-id="a0a03-110">なし。</span><span class="sxs-lookup"><span data-stu-id="a0a03-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a0a03-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a0a03-111">Child Elements</span></span>

<span data-ttu-id="a0a03-112">なし。</span><span class="sxs-lookup"><span data-stu-id="a0a03-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a0a03-113">親要素</span><span class="sxs-lookup"><span data-stu-id="a0a03-113">Parent Elements</span></span>

|<span data-ttu-id="a0a03-114">要素</span><span class="sxs-lookup"><span data-stu-id="a0a03-114">Element</span></span>|<span data-ttu-id="a0a03-115">説明</span><span class="sxs-lookup"><span data-stu-id="a0a03-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0a03-116">表示 (形式) CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="a0a03-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="a0a03-117">このカスタム コントロールのビュー定義を使用する .NET 型または条件を使用するには、この定義が存在する必要がありますを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0a03-117">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a0a03-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a0a03-118">Text Value</span></span>

<span data-ttu-id="a0a03-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="a0a03-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0a03-120">コメント</span><span class="sxs-lookup"><span data-stu-id="a0a03-120">Remarks</span></span>

<span data-ttu-id="a0a03-121">各カスタム コントロールのビュー定義に少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0a03-121">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="a0a03-122">カスタム コントロールのビューのコンポーネントに関する詳細については、[カスタム コントロールを作成する](./creating-custom-controls.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0a03-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0a03-123">参照</span><span class="sxs-lookup"><span data-stu-id="a0a03-123">See Also</span></span>

[<span data-ttu-id="a0a03-124">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="a0a03-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="a0a03-125">表示 (形式) CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="a0a03-125">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a0a03-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="a0a03-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
