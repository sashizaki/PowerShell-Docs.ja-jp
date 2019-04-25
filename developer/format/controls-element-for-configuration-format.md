---
title: 構成 (形式) の controls 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066874"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="bfe00-102">Configuration の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfe00-102">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="bfe00-103">書式設定ファイルのすべてのビューで使用できる一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="bfe00-103">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="bfe00-104">構成 (形式) の構成要素 (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="bfe00-104">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bfe00-105">構文</span><span class="sxs-lookup"><span data-stu-id="bfe00-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bfe00-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bfe00-106">Attributes and Elements</span></span>

<span data-ttu-id="bfe00-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Controls`要素。</span><span class="sxs-lookup"><span data-stu-id="bfe00-107">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bfe00-108">属性</span><span class="sxs-lookup"><span data-stu-id="bfe00-108">Attributes</span></span>

<span data-ttu-id="bfe00-109">なし。</span><span class="sxs-lookup"><span data-stu-id="bfe00-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bfe00-110">子要素</span><span class="sxs-lookup"><span data-stu-id="bfe00-110">Child Elements</span></span>

|<span data-ttu-id="bfe00-111">要素</span><span class="sxs-lookup"><span data-stu-id="bfe00-111">Element</span></span>|<span data-ttu-id="bfe00-112">説明</span><span class="sxs-lookup"><span data-stu-id="bfe00-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bfe00-113">構成 (形式) のコントロールのコントロール要素</span><span class="sxs-lookup"><span data-stu-id="bfe00-113">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="bfe00-114">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="bfe00-114">Required element.</span></span><br /><br /> <span data-ttu-id="bfe00-115">書式設定ファイルのすべてのビューで使用できる一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="bfe00-115">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bfe00-116">親要素</span><span class="sxs-lookup"><span data-stu-id="bfe00-116">Parent Elements</span></span>

|<span data-ttu-id="bfe00-117">要素</span><span class="sxs-lookup"><span data-stu-id="bfe00-117">Element</span></span>|<span data-ttu-id="bfe00-118">説明</span><span class="sxs-lookup"><span data-stu-id="bfe00-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bfe00-119">構成要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bfe00-119">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="bfe00-120">書式設定ファイルの最上位の要素を表します。</span><span class="sxs-lookup"><span data-stu-id="bfe00-120">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bfe00-121">コメント</span><span class="sxs-lookup"><span data-stu-id="bfe00-121">Remarks</span></span>

<span data-ttu-id="bfe00-122">任意の数のコモン コントロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bfe00-122">You can create any number of common controls.</span></span> <span data-ttu-id="bfe00-123">コントロールごとに、コントロールとコントロールのコンポーネントを参照するために使用される名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfe00-123">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfe00-124">参照</span><span class="sxs-lookup"><span data-stu-id="bfe00-124">See Also</span></span>

[<span data-ttu-id="bfe00-125">構成要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bfe00-125">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="bfe00-126">構成 (形式) のコントロールのコントロール要素</span><span class="sxs-lookup"><span data-stu-id="bfe00-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="bfe00-127">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="bfe00-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
