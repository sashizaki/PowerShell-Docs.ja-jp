---
title: View (Format) の CustomControl の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2c65171-4d4c-46a9-a545-591df058acd1
caps.latest.revision: 7
ms.openlocfilehash: 00e9ae0916dd6d22602b99b201c9c4b7e549dc48
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361591"
---
# <a name="typename-element-for-selectioncondition-for-customcontrol-for-view--format"></a><span data-ttu-id="037c6-102">View の CustomControl の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="037c6-102">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>

<span data-ttu-id="037c6-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="037c6-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="037c6-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="037c6-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="037c6-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素を表示するための CustomControl for ビュー (形式) の Custommentry 要素の CustomControl for View (Format) CustomControl for view (Format) の SelectionCondition の CustomControl for ビュー (format) の TypeName 要素に対して、CustomEntry for CustomControl for ビュー (形式) の SelectionCondition 要素を指定するための CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="037c6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="037c6-106">構文</span><span class="sxs-lookup"><span data-stu-id="037c6-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="037c6-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="037c6-107">Attributes and Elements</span></span>

<span data-ttu-id="037c6-108">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="037c6-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="037c6-109">属性</span><span class="sxs-lookup"><span data-stu-id="037c6-109">Attributes</span></span>

<span data-ttu-id="037c6-110">なし。</span><span class="sxs-lookup"><span data-stu-id="037c6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="037c6-111">子要素</span><span class="sxs-lookup"><span data-stu-id="037c6-111">Child Elements</span></span>

<span data-ttu-id="037c6-112">なし。</span><span class="sxs-lookup"><span data-stu-id="037c6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="037c6-113">親要素</span><span class="sxs-lookup"><span data-stu-id="037c6-113">Parent Elements</span></span>

|<span data-ttu-id="037c6-114">要素</span><span class="sxs-lookup"><span data-stu-id="037c6-114">Element</span></span>|<span data-ttu-id="037c6-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="037c6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="037c6-116">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="037c6-116">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="037c6-117">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="037c6-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="037c6-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="037c6-118">Text Value</span></span>

<span data-ttu-id="037c6-119">.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="037c6-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="037c6-120">コメント</span><span class="sxs-lookup"><span data-stu-id="037c6-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="037c6-121">参照</span><span class="sxs-lookup"><span data-stu-id="037c6-121">See Also</span></span>

[<span data-ttu-id="037c6-122">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="037c6-122">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="037c6-123">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="037c6-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
