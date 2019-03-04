---
title: 構成 (形式) のコントロールのコントロールの要素をカスタム コントロール |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9d92a9e-c680-46ca-962e-e82452726953
caps.latest.revision: 10
ms.openlocfilehash: 1d72ce5b18e89bd81c7f81b27f4b8c60bed99764
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857668"
---
# <a name="customcontrol-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="b1bf8-102">Configuration の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b1bf8-102">CustomControl Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b1bf8-103">コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1bf8-103">Defines a control.</span></span> <span data-ttu-id="b1bf8-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1bf8-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b1bf8-105">構成 (形式) のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b1bf8-106">構文</span><span class="sxs-lookup"><span data-stu-id="b1bf8-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1bf8-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-107">Attributes and Elements</span></span>

<span data-ttu-id="b1bf8-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControl`要素。</span><span class="sxs-lookup"><span data-stu-id="b1bf8-108">The following sections describe the attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="b1bf8-109">この要素は、少なくとも 1 つの子要素をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1bf8-109">This element must have at least one child element.</span></span> <span data-ttu-id="b1bf8-110">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="b1bf8-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="b1bf8-111">属性</span><span class="sxs-lookup"><span data-stu-id="b1bf8-111">Attributes</span></span>

<span data-ttu-id="b1bf8-112">なし。</span><span class="sxs-lookup"><span data-stu-id="b1bf8-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b1bf8-113">子要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-113">Child Elements</span></span>

|<span data-ttu-id="b1bf8-114">要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-114">Element</span></span>|<span data-ttu-id="b1bf8-115">説明</span><span class="sxs-lookup"><span data-stu-id="b1bf8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1bf8-116">構成 (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-116">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="b1bf8-117">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="b1bf8-117">Required element.</span></span><br /><br /> <span data-ttu-id="b1bf8-118">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="b1bf8-118">Provides the definitions of a control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b1bf8-119">親要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-119">Parent Elements</span></span>

|<span data-ttu-id="b1bf8-120">要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-120">Element</span></span>|<span data-ttu-id="b1bf8-121">説明</span><span class="sxs-lookup"><span data-stu-id="b1bf8-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1bf8-122">構成 (形式) のコントロールのコントロール要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-122">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="b1bf8-123">書式設定ファイルと、コントロールを参照するために使用される名前のすべてのビューで使用できる一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1bf8-123">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b1bf8-124">コメント</span><span class="sxs-lookup"><span data-stu-id="b1bf8-124">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b1bf8-125">参照</span><span class="sxs-lookup"><span data-stu-id="b1bf8-125">See Also</span></span>

[<span data-ttu-id="b1bf8-126">構成 (形式) のコントロールのコントロール要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="b1bf8-127">構成 (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="b1bf8-127">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="b1bf8-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="b1bf8-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
