---
title: 構成用のコントロール (Format) の EntrySelectedBy の TypeName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30bb1382-8c6b-4371-82e6-baf427fa0781
caps.latest.revision: 6
ms.openlocfilehash: cec8c5d76bded321ec1d6a1cd0409d7c88863c03
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368081"
---
# <a name="typename-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="2b3d0-102">Configuration の Controls の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2b3d0-102">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="2b3d0-103">コントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b3d0-103">Specifies a .NET type that uses this definition of the control.</span></span> <span data-ttu-id="2b3d0-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b3d0-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="2b3d0-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素Format) CustomControl 用の CustomEntry 要素を構成するためのコントロール用の customentry 要素 (形式) を構成するために、EntrySelectedBy の configuration (format) TypeName 要素を構成するためのコントロール (形式)</span><span class="sxs-lookup"><span data-stu-id="2b3d0-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2b3d0-106">構文</span><span class="sxs-lookup"><span data-stu-id="2b3d0-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b3d0-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2b3d0-107">Attributes and Elements</span></span>

<span data-ttu-id="2b3d0-108">次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b3d0-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2b3d0-109">属性</span><span class="sxs-lookup"><span data-stu-id="2b3d0-109">Attributes</span></span>

<span data-ttu-id="2b3d0-110">なし。</span><span class="sxs-lookup"><span data-stu-id="2b3d0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2b3d0-111">子要素</span><span class="sxs-lookup"><span data-stu-id="2b3d0-111">Child Elements</span></span>

<span data-ttu-id="2b3d0-112">なし。</span><span class="sxs-lookup"><span data-stu-id="2b3d0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2b3d0-113">親要素</span><span class="sxs-lookup"><span data-stu-id="2b3d0-113">Parent Elements</span></span>

|<span data-ttu-id="2b3d0-114">要素</span><span class="sxs-lookup"><span data-stu-id="2b3d0-114">Element</span></span>|<span data-ttu-id="2b3d0-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="2b3d0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2b3d0-116">Configuration 用のコントロール用の CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2b3d0-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="2b3d0-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b3d0-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2b3d0-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2b3d0-118">Text Value</span></span>

<span data-ttu-id="2b3d0-119">`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b3d0-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b3d0-120">コメント</span><span class="sxs-lookup"><span data-stu-id="2b3d0-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="2b3d0-121">参照</span><span class="sxs-lookup"><span data-stu-id="2b3d0-121">See Also</span></span>

[<span data-ttu-id="2b3d0-122">Configuration 用のコントロール用の CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2b3d0-122">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="2b3d0-123">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2b3d0-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
