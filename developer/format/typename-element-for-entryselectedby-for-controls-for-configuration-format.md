---
title: TypeName 要素の構成 (形式) のコントロールの EntrySelectedBy |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30bb1382-8c6b-4371-82e6-baf427fa0781
caps.latest.revision: 6
ms.openlocfilehash: cec8c5d76bded321ec1d6a1cd0409d7c88863c03
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860298"
---
# <a name="typename-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="1c0e1-102">Configuration の Controls の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1c0e1-102">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="1c0e1-103">このコントロールの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c0e1-103">Specifies a .NET type that uses this definition of the control.</span></span> <span data-ttu-id="1c0e1-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c0e1-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="1c0e1-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素CustomEntry EntrySelectedBy の構成 (形式) のコントロールの構成 (形式) の TypeName 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="1c0e1-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1c0e1-106">構文</span><span class="sxs-lookup"><span data-stu-id="1c0e1-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="1c0e1-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="1c0e1-107">Attributes and Elements</span></span>

<span data-ttu-id="1c0e1-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="1c0e1-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1c0e1-109">属性</span><span class="sxs-lookup"><span data-stu-id="1c0e1-109">Attributes</span></span>

<span data-ttu-id="1c0e1-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1c0e1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1c0e1-111">子要素</span><span class="sxs-lookup"><span data-stu-id="1c0e1-111">Child Elements</span></span>

<span data-ttu-id="1c0e1-112">なし。</span><span class="sxs-lookup"><span data-stu-id="1c0e1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1c0e1-113">親要素</span><span class="sxs-lookup"><span data-stu-id="1c0e1-113">Parent Elements</span></span>

|<span data-ttu-id="1c0e1-114">要素</span><span class="sxs-lookup"><span data-stu-id="1c0e1-114">Element</span></span>|<span data-ttu-id="1c0e1-115">説明</span><span class="sxs-lookup"><span data-stu-id="1c0e1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1c0e1-116">構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="1c0e1-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="1c0e1-117">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="1c0e1-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1c0e1-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="1c0e1-118">Text Value</span></span>

<span data-ttu-id="1c0e1-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="1c0e1-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c0e1-120">コメント</span><span class="sxs-lookup"><span data-stu-id="1c0e1-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="1c0e1-121">参照</span><span class="sxs-lookup"><span data-stu-id="1c0e1-121">See Also</span></span>

[<span data-ttu-id="1c0e1-122">構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="1c0e1-122">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="1c0e1-123">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="1c0e1-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
