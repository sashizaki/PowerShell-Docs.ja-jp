---
title: ビューのコントロールの SelectionCondition の TypeName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7141aefc-6656-4c52-8a9c-c2bfc9c87be9
caps.latest.revision: 6
ms.openlocfilehash: 7a697c286ec9efe750930739cdfa2580003365dd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361601"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="656ab-102">View の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="656ab-102">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="656ab-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="656ab-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="656ab-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="656ab-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="656ab-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビュー用のコントロールの CustomControl (書式) の CustomEntry 要素のコントロール用のカスタムエントリのためのコントロールのためのコントロールのためのコントロールのためのコントロールのための、ビューのコントロールの EntrySelectedBy の SelectionCondition 要素を表示するためのコントロール (Format) ビューのコントロールの SelectionCondition の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="656ab-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) TypeName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="656ab-106">構文</span><span class="sxs-lookup"><span data-stu-id="656ab-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="656ab-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="656ab-107">Attributes and Elements</span></span>

<span data-ttu-id="656ab-108">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="656ab-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="656ab-109">属性</span><span class="sxs-lookup"><span data-stu-id="656ab-109">Attributes</span></span>

<span data-ttu-id="656ab-110">なし。</span><span class="sxs-lookup"><span data-stu-id="656ab-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="656ab-111">子要素</span><span class="sxs-lookup"><span data-stu-id="656ab-111">Child Elements</span></span>

<span data-ttu-id="656ab-112">なし。</span><span class="sxs-lookup"><span data-stu-id="656ab-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="656ab-113">親要素</span><span class="sxs-lookup"><span data-stu-id="656ab-113">Parent Elements</span></span>

|<span data-ttu-id="656ab-114">要素</span><span class="sxs-lookup"><span data-stu-id="656ab-114">Element</span></span>|<span data-ttu-id="656ab-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="656ab-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="656ab-116">ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="656ab-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="656ab-117">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="656ab-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="656ab-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="656ab-118">Text Value</span></span>

<span data-ttu-id="656ab-119">.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="656ab-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="656ab-120">コメント</span><span class="sxs-lookup"><span data-stu-id="656ab-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="656ab-121">参照</span><span class="sxs-lookup"><span data-stu-id="656ab-121">See Also</span></span>

[<span data-ttu-id="656ab-122">ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="656ab-122">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="656ab-123">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="656ab-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
