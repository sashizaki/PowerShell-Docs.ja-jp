---
title: ビューのコントロールの SelectionCondition の TypeName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4795c3af40cf60fb8e71185feced18c192b3a0aa
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780051"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="27c8c-102">View の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="27c8c-102">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="27c8c-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="27c8c-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="27c8c-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="27c8c-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="27c8c-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (形式) コントロールのコントロール要素 (format) のコントロールの要素 (書式) を制御するためのコントロールの要素 (書式) の CustomControl 要素 (format) のコントロールの CustomControl のカスタム CustomEntries view (format) のコントロールの CustomEntries のためのコントロールのために、ビュー (format) のコントロールの SelectionCondition 要素を表示するためのコントロール (format) の SelectionCondition 要素をコントロールに対して使用します。</span><span class="sxs-lookup"><span data-stu-id="27c8c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) TypeName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="27c8c-106">構文</span><span class="sxs-lookup"><span data-stu-id="27c8c-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="27c8c-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="27c8c-107">Attributes and Elements</span></span>

<span data-ttu-id="27c8c-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="27c8c-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="27c8c-109">属性</span><span class="sxs-lookup"><span data-stu-id="27c8c-109">Attributes</span></span>

<span data-ttu-id="27c8c-110">なし。</span><span class="sxs-lookup"><span data-stu-id="27c8c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="27c8c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="27c8c-111">Child Elements</span></span>

<span data-ttu-id="27c8c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="27c8c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="27c8c-113">親要素</span><span class="sxs-lookup"><span data-stu-id="27c8c-113">Parent Elements</span></span>

|<span data-ttu-id="27c8c-114">要素</span><span class="sxs-lookup"><span data-stu-id="27c8c-114">Element</span></span>|<span data-ttu-id="27c8c-115">説明</span><span class="sxs-lookup"><span data-stu-id="27c8c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="27c8c-116">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="27c8c-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="27c8c-117">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="27c8c-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="27c8c-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="27c8c-118">Text Value</span></span>

<span data-ttu-id="27c8c-119">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="27c8c-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="27c8c-120">解説</span><span class="sxs-lookup"><span data-stu-id="27c8c-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="27c8c-121">参照</span><span class="sxs-lookup"><span data-stu-id="27c8c-121">See Also</span></span>

[<span data-ttu-id="27c8c-122">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="27c8c-122">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="27c8c-123">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="27c8c-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
