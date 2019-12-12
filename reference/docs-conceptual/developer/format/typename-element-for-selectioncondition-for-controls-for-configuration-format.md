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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361611"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="19dd5-102">Configuration の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="19dd5-102">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="19dd5-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="19dd5-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="19dd5-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="19dd5-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="19dd5-105">Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの構成 (形式) のコントロール要素の構成 (書式設定) 要素構成 (Format) CustomEntry 要素の CustomControl のためのコントロール用の構成 (形式) の構成 (形式) のために、customentry に対して EntrySelectedBy の Configuration (Format) SelectionCondition 要素を指定します。構成 (形式) のコントロールの SelectionCondition の構成 (形式) TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="19dd5-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="19dd5-106">構文</span><span class="sxs-lookup"><span data-stu-id="19dd5-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="19dd5-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="19dd5-107">Attributes and Elements</span></span>

<span data-ttu-id="19dd5-108">次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="19dd5-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="19dd5-109">属性</span><span class="sxs-lookup"><span data-stu-id="19dd5-109">Attributes</span></span>

<span data-ttu-id="19dd5-110">なし。</span><span class="sxs-lookup"><span data-stu-id="19dd5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="19dd5-111">子要素</span><span class="sxs-lookup"><span data-stu-id="19dd5-111">Child Elements</span></span>

<span data-ttu-id="19dd5-112">なし。</span><span class="sxs-lookup"><span data-stu-id="19dd5-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="19dd5-113">親要素</span><span class="sxs-lookup"><span data-stu-id="19dd5-113">Parent Elements</span></span>

|<span data-ttu-id="19dd5-114">要素</span><span class="sxs-lookup"><span data-stu-id="19dd5-114">Element</span></span>|<span data-ttu-id="19dd5-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="19dd5-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="19dd5-116">CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="19dd5-116">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="19dd5-117">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="19dd5-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="19dd5-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="19dd5-118">Text Value</span></span>

<span data-ttu-id="19dd5-119">`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="19dd5-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="19dd5-120">コメント</span><span class="sxs-lookup"><span data-stu-id="19dd5-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="19dd5-121">参照</span><span class="sxs-lookup"><span data-stu-id="19dd5-121">See Also</span></span>

[<span data-ttu-id="19dd5-122">CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="19dd5-122">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="19dd5-123">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="19dd5-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
