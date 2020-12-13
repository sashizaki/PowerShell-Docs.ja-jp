---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の SelectionCondition の TypeName 要素 (書式)
description: View の CustomControl の SelectionCondition の TypeName 要素 (書式)
ms.openlocfilehash: ab02c6921985dbe86e5adcbc6565c76f6617399a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651285"
---
# <a name="typename-element-for-selectioncondition-for-customcontrol-for-view--format"></a><span data-ttu-id="48e95-103">View の CustomControl の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="48e95-103">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>

<span data-ttu-id="48e95-104">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e95-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="48e95-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="48e95-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="48e95-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (format) CustomControl のビュー (形式) の CustomEntries 要素の CustomControl for view (format) の CustomEntries の要素の CustomControl for ビューの CustomEntries に使用します。 (フォーマット) CustomControl for View (Format) の SelectionCondition の CustomControl for View (format) TypeName 要素の EntrySelectedBy for CustomControl for view (format) の SelectionCondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e95-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="48e95-107">構文</span><span class="sxs-lookup"><span data-stu-id="48e95-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="48e95-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="48e95-108">Attributes and Elements</span></span>

<span data-ttu-id="48e95-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="48e95-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="48e95-110">属性</span><span class="sxs-lookup"><span data-stu-id="48e95-110">Attributes</span></span>

<span data-ttu-id="48e95-111">なし。</span><span class="sxs-lookup"><span data-stu-id="48e95-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="48e95-112">子要素</span><span class="sxs-lookup"><span data-stu-id="48e95-112">Child Elements</span></span>

<span data-ttu-id="48e95-113">なし。</span><span class="sxs-lookup"><span data-stu-id="48e95-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="48e95-114">親要素</span><span class="sxs-lookup"><span data-stu-id="48e95-114">Parent Elements</span></span>

|<span data-ttu-id="48e95-115">要素</span><span class="sxs-lookup"><span data-stu-id="48e95-115">Element</span></span>|<span data-ttu-id="48e95-116">説明</span><span class="sxs-lookup"><span data-stu-id="48e95-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48e95-117">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="48e95-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="48e95-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="48e95-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="48e95-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="48e95-119">Text Value</span></span>

<span data-ttu-id="48e95-120">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="48e95-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="48e95-121">解説</span><span class="sxs-lookup"><span data-stu-id="48e95-121">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="48e95-122">参照</span><span class="sxs-lookup"><span data-stu-id="48e95-122">See Also</span></span>

[<span data-ttu-id="48e95-123">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="48e95-123">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="48e95-124">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="48e95-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
