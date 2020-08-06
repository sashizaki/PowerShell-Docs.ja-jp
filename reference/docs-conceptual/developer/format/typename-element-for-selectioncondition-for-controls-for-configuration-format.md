---
title: 構成用のコントロールの SelectionCondition の TypeName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2db856d1b84dded315204d8c8574ae86acb63515
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780068"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="26c25-102">Configuration の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="26c25-102">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="26c25-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="26c25-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="26c25-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="26c25-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="26c25-105">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (format) CustomControl 要素の構成のためのコントロールの CustomControl の構成 (形式) の CustomEntries 要素については、CustomControl for Controls の CustomEntry 要素を構成します。構成 (形式) のために、CustomEntry 用の configuration (形式) の SelectionCondition 要素を構成するための entryselectedby for configuration (format) の SelectionCondition 要素を構成するためのコントロールの SelectionCondition (形式)</span><span class="sxs-lookup"><span data-stu-id="26c25-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="26c25-106">構文</span><span class="sxs-lookup"><span data-stu-id="26c25-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="26c25-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="26c25-107">Attributes and Elements</span></span>

<span data-ttu-id="26c25-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="26c25-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="26c25-109">属性</span><span class="sxs-lookup"><span data-stu-id="26c25-109">Attributes</span></span>

<span data-ttu-id="26c25-110">なし。</span><span class="sxs-lookup"><span data-stu-id="26c25-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="26c25-111">子要素</span><span class="sxs-lookup"><span data-stu-id="26c25-111">Child Elements</span></span>

<span data-ttu-id="26c25-112">なし。</span><span class="sxs-lookup"><span data-stu-id="26c25-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="26c25-113">親要素</span><span class="sxs-lookup"><span data-stu-id="26c25-113">Parent Elements</span></span>

|<span data-ttu-id="26c25-114">要素</span><span class="sxs-lookup"><span data-stu-id="26c25-114">Element</span></span>|<span data-ttu-id="26c25-115">説明</span><span class="sxs-lookup"><span data-stu-id="26c25-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26c25-116">CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="26c25-116">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="26c25-117">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="26c25-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="26c25-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="26c25-118">Text Value</span></span>

<span data-ttu-id="26c25-119">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="26c25-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="26c25-120">解説</span><span class="sxs-lookup"><span data-stu-id="26c25-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="26c25-121">参照</span><span class="sxs-lookup"><span data-stu-id="26c25-121">See Also</span></span>

[<span data-ttu-id="26c25-122">CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="26c25-122">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="26c25-123">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="26c25-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
