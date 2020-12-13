---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の SelectionCondition の TypeName 要素 (書式)
description: Configuration の Controls の SelectionCondition の TypeName 要素 (書式)
ms.openlocfilehash: fddb8ddbac7c9292a05cadfa31f98db6439a557d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659673"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="b09df-103">Configuration の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b09df-103">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b09df-104">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="b09df-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="b09df-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b09df-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b09df-106">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (format) CustomControl 要素の構成のためのコントロールの CustomControl の構成 (形式) の CustomEntries 要素については、CustomControl for Controls の CustomEntry 要素を構成します。構成 (形式) のために、CustomEntry 用の configuration (形式) の SelectionCondition 要素を構成するための entryselectedby for configuration (format) の SelectionCondition 要素を構成するためのコントロールの SelectionCondition (形式)</span><span class="sxs-lookup"><span data-stu-id="b09df-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b09df-107">構文</span><span class="sxs-lookup"><span data-stu-id="b09df-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b09df-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b09df-108">Attributes and Elements</span></span>

<span data-ttu-id="b09df-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="b09df-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b09df-110">属性</span><span class="sxs-lookup"><span data-stu-id="b09df-110">Attributes</span></span>

<span data-ttu-id="b09df-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b09df-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b09df-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b09df-112">Child Elements</span></span>

<span data-ttu-id="b09df-113">なし。</span><span class="sxs-lookup"><span data-stu-id="b09df-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b09df-114">親要素</span><span class="sxs-lookup"><span data-stu-id="b09df-114">Parent Elements</span></span>

|<span data-ttu-id="b09df-115">要素</span><span class="sxs-lookup"><span data-stu-id="b09df-115">Element</span></span>|<span data-ttu-id="b09df-116">説明</span><span class="sxs-lookup"><span data-stu-id="b09df-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b09df-117">CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b09df-117">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="b09df-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="b09df-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b09df-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b09df-119">Text Value</span></span>

<span data-ttu-id="b09df-120">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="b09df-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b09df-121">解説</span><span class="sxs-lookup"><span data-stu-id="b09df-121">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b09df-122">参照</span><span class="sxs-lookup"><span data-stu-id="b09df-122">See Also</span></span>

[<span data-ttu-id="b09df-123">CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b09df-123">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="b09df-124">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="b09df-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
