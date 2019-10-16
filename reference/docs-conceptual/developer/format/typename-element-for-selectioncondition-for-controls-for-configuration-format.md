---
title: 構成用のコントロールの SelectionCondition の TypeName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477c8711-fffc-4f92-af45-6d4f80990474
caps.latest.revision: 7
ms.openlocfilehash: 60f02f3240c5574e1b1f9027b060bd9af89a11d2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361611"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="d9679-102">Configuration の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d9679-102">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="d9679-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9679-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="d9679-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9679-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="d9679-105">Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの構成 (形式) のコントロール要素の構成 (書式設定) 要素構成 (Format) CustomEntry 要素の CustomControl のためのコントロール用の構成 (形式) の構成 (形式) のために、customentry に対して EntrySelectedBy の Configuration (Format) SelectionCondition 要素を指定します。構成 (形式) のコントロールの SelectionCondition の構成 (形式) TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="d9679-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d9679-106">構文</span><span class="sxs-lookup"><span data-stu-id="d9679-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d9679-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d9679-107">Attributes and Elements</span></span>

<span data-ttu-id="d9679-108">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9679-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d9679-109">属性</span><span class="sxs-lookup"><span data-stu-id="d9679-109">Attributes</span></span>

<span data-ttu-id="d9679-110">なし。</span><span class="sxs-lookup"><span data-stu-id="d9679-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d9679-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d9679-111">Child Elements</span></span>

<span data-ttu-id="d9679-112">なし。</span><span class="sxs-lookup"><span data-stu-id="d9679-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d9679-113">親要素</span><span class="sxs-lookup"><span data-stu-id="d9679-113">Parent Elements</span></span>

|<span data-ttu-id="d9679-114">要素</span><span class="sxs-lookup"><span data-stu-id="d9679-114">Element</span></span>|<span data-ttu-id="d9679-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="d9679-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9679-116">CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d9679-116">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="d9679-117">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d9679-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d9679-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d9679-118">Text Value</span></span>

<span data-ttu-id="d9679-119">.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9679-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9679-120">コメント</span><span class="sxs-lookup"><span data-stu-id="d9679-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="d9679-121">参照</span><span class="sxs-lookup"><span data-stu-id="d9679-121">See Also</span></span>

[<span data-ttu-id="d9679-122">CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d9679-122">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="d9679-123">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="d9679-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
