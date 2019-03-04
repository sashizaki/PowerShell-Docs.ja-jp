---
title: コントロールが表示されます (形式) の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7141aefc-6656-4c52-8a9c-c2bfc9c87be9
caps.latest.revision: 6
ms.openlocfilehash: 7a697c286ec9efe750930739cdfa2580003365dd
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862288"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="7e3a5-102">View の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7e3a5-102">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="7e3a5-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e3a5-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="7e3a5-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7e3a5-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="7e3a5-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry EntrySelectedBy のビュー (コントロールのビュー (形式) SelectionCondition 要素のコントロールのビュー (形式) EntrySelectedBy 要素のコントロールのビュー (形式) CustomEntry 要素のコントロールのカスタム コントロールビュー (形式) のコントロールの SelectionCondition の TypeName 要素の形式)</span><span class="sxs-lookup"><span data-stu-id="7e3a5-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) TypeName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7e3a5-106">構文</span><span class="sxs-lookup"><span data-stu-id="7e3a5-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="7e3a5-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7e3a5-107">Attributes and Elements</span></span>

<span data-ttu-id="7e3a5-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="7e3a5-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7e3a5-109">属性</span><span class="sxs-lookup"><span data-stu-id="7e3a5-109">Attributes</span></span>

<span data-ttu-id="7e3a5-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7e3a5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7e3a5-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7e3a5-111">Child Elements</span></span>

<span data-ttu-id="7e3a5-112">なし。</span><span class="sxs-lookup"><span data-stu-id="7e3a5-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7e3a5-113">親要素</span><span class="sxs-lookup"><span data-stu-id="7e3a5-113">Parent Elements</span></span>

|<span data-ttu-id="7e3a5-114">要素</span><span class="sxs-lookup"><span data-stu-id="7e3a5-114">Element</span></span>|<span data-ttu-id="7e3a5-115">説明</span><span class="sxs-lookup"><span data-stu-id="7e3a5-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7e3a5-116">コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7e3a5-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="7e3a5-117">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7e3a5-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7e3a5-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7e3a5-118">Text Value</span></span>

<span data-ttu-id="7e3a5-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="7e3a5-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e3a5-120">コメント</span><span class="sxs-lookup"><span data-stu-id="7e3a5-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="7e3a5-121">参照</span><span class="sxs-lookup"><span data-stu-id="7e3a5-121">See Also</span></span>

[<span data-ttu-id="7e3a5-122">コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7e3a5-122">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="7e3a5-123">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="7e3a5-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
