---
title: TypeName 要素のビュー (形式) のカスタム コントロールの SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2c65171-4d4c-46a9-a545-591df058acd1
caps.latest.revision: 7
ms.openlocfilehash: 00e9ae0916dd6d22602b99b201c9c4b7e549dc48
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863208"
---
# <a name="typename-element-for-selectioncondition-for-customcontrol-for-view--format"></a><span data-ttu-id="03cbb-102">View の CustomControl の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="03cbb-102">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>

<span data-ttu-id="03cbb-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="03cbb-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="03cbb-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="03cbb-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="03cbb-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素の表示 (カスタム コントロールの CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールのビュー (形式) CustomEntries 要素CustomEntry EntrySelectedBy SelectionCondition ビュー (形式) のカスタム コントロール用のビュー (形式) の TypeName 要素のカスタム コントロール用のビュー (形式) SelectionCondition 要素のカスタム コントロール用の形式) CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="03cbb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="03cbb-106">構文</span><span class="sxs-lookup"><span data-stu-id="03cbb-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="03cbb-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="03cbb-107">Attributes and Elements</span></span>

<span data-ttu-id="03cbb-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="03cbb-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="03cbb-109">属性</span><span class="sxs-lookup"><span data-stu-id="03cbb-109">Attributes</span></span>

<span data-ttu-id="03cbb-110">なし。</span><span class="sxs-lookup"><span data-stu-id="03cbb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="03cbb-111">子要素</span><span class="sxs-lookup"><span data-stu-id="03cbb-111">Child Elements</span></span>

<span data-ttu-id="03cbb-112">なし。</span><span class="sxs-lookup"><span data-stu-id="03cbb-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="03cbb-113">親要素</span><span class="sxs-lookup"><span data-stu-id="03cbb-113">Parent Elements</span></span>

|<span data-ttu-id="03cbb-114">要素</span><span class="sxs-lookup"><span data-stu-id="03cbb-114">Element</span></span>|<span data-ttu-id="03cbb-115">説明</span><span class="sxs-lookup"><span data-stu-id="03cbb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="03cbb-116">ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="03cbb-116">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="03cbb-117">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="03cbb-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="03cbb-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="03cbb-118">Text Value</span></span>

<span data-ttu-id="03cbb-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="03cbb-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="03cbb-120">コメント</span><span class="sxs-lookup"><span data-stu-id="03cbb-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="03cbb-121">参照</span><span class="sxs-lookup"><span data-stu-id="03cbb-121">See Also</span></span>

[<span data-ttu-id="03cbb-122">ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="03cbb-122">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="03cbb-123">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="03cbb-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
