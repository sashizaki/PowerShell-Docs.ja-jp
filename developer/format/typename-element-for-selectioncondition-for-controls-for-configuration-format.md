---
title: TypeName 要素の構成 (形式) のコントロールの SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477c8711-fffc-4f92-af45-6d4f80990474
caps.latest.revision: 7
ms.openlocfilehash: 60f02f3240c5574e1b1f9027b060bd9af89a11d2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083945"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="52822-102">Configuration の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="52822-102">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="52822-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="52822-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="52822-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="52822-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="52822-105">コントロールのコントロールのカスタム コントロールの構成 (形式) CustomEntries 要素の構成 (形式) のカスタム コントロール要素のコントロールの構成 (形式) のコントロール要素の構成要素 (形式) のコントロール要素CustomEntry EntrySelectedBy CustomEntry のための構成 (形式) SelectionCondition 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの構成 (形式) CustomEntry 要素構成 (形式) のコントロールの SelectionCondition の構成 (形式) TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="52822-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="52822-106">構文</span><span class="sxs-lookup"><span data-stu-id="52822-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="52822-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="52822-107">Attributes and Elements</span></span>

<span data-ttu-id="52822-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="52822-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="52822-109">属性</span><span class="sxs-lookup"><span data-stu-id="52822-109">Attributes</span></span>

<span data-ttu-id="52822-110">なし。</span><span class="sxs-lookup"><span data-stu-id="52822-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="52822-111">子要素</span><span class="sxs-lookup"><span data-stu-id="52822-111">Child Elements</span></span>

<span data-ttu-id="52822-112">なし。</span><span class="sxs-lookup"><span data-stu-id="52822-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="52822-113">親要素</span><span class="sxs-lookup"><span data-stu-id="52822-113">Parent Elements</span></span>

|<span data-ttu-id="52822-114">要素</span><span class="sxs-lookup"><span data-stu-id="52822-114">Element</span></span>|<span data-ttu-id="52822-115">説明</span><span class="sxs-lookup"><span data-stu-id="52822-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52822-116">構成 (形式) の CustomEntry EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="52822-116">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="52822-117">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="52822-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="52822-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="52822-118">Text Value</span></span>

<span data-ttu-id="52822-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="52822-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="52822-120">コメント</span><span class="sxs-lookup"><span data-stu-id="52822-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="52822-121">参照</span><span class="sxs-lookup"><span data-stu-id="52822-121">See Also</span></span>

[<span data-ttu-id="52822-122">構成 (形式) の CustomEntry EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="52822-122">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="52822-123">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="52822-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
