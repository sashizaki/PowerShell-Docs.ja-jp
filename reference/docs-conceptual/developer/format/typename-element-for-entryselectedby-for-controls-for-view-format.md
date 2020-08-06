---
title: ビュー (Format) のコントロールに対する EntrySelectedBy の TypeName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6eaa4f80a18c91ca351657fd40a8cac6f688c22f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783332"
---
# <a name="typename-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="ad10e-102">View の Controls の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ad10e-102">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="ad10e-103">コントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad10e-103">Specifies a .NET type that uses this definition of the control.</span></span> <span data-ttu-id="ad10e-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad10e-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="ad10e-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素 (format) を表示するコントロールのコントロール要素 (書式) のコントロール要素 CustomControl の CustomEntries 要素ビューのコントロール (format) のコントロールのために、ビュー (format) の CustomEntry 要素を使用して、ビュー (形式) のコントロールに対して EntrySelectedBy のビュー (format) の TypeName 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad10e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ad10e-106">構文</span><span class="sxs-lookup"><span data-stu-id="ad10e-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="ad10e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ad10e-107">Attributes and Elements</span></span>

<span data-ttu-id="ad10e-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="ad10e-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ad10e-109">属性</span><span class="sxs-lookup"><span data-stu-id="ad10e-109">Attributes</span></span>

<span data-ttu-id="ad10e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ad10e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ad10e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ad10e-111">Child Elements</span></span>

<span data-ttu-id="ad10e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ad10e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ad10e-113">親要素</span><span class="sxs-lookup"><span data-stu-id="ad10e-113">Parent Elements</span></span>

|<span data-ttu-id="ad10e-114">要素</span><span class="sxs-lookup"><span data-stu-id="ad10e-114">Element</span></span>|<span data-ttu-id="ad10e-115">説明</span><span class="sxs-lookup"><span data-stu-id="ad10e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad10e-116">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ad10e-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="ad10e-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad10e-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ad10e-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ad10e-118">Text Value</span></span>

<span data-ttu-id="ad10e-119">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="ad10e-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad10e-120">解説</span><span class="sxs-lookup"><span data-stu-id="ad10e-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="ad10e-121">参照</span><span class="sxs-lookup"><span data-stu-id="ad10e-121">See Also</span></span>

[<span data-ttu-id="ad10e-122">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ad10e-122">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="ad10e-123">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ad10e-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
