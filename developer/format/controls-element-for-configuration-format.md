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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861178"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="11deb-102">Configuration の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="11deb-102">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="11deb-103">書式設定ファイルのすべてのビューで使用できる一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="11deb-103">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="11deb-104">構成 (形式) の構成要素 (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="11deb-104">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="11deb-105">構文</span><span class="sxs-lookup"><span data-stu-id="11deb-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="11deb-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="11deb-106">Attributes and Elements</span></span>

<span data-ttu-id="11deb-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Controls`要素。</span><span class="sxs-lookup"><span data-stu-id="11deb-107">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="11deb-108">属性</span><span class="sxs-lookup"><span data-stu-id="11deb-108">Attributes</span></span>

<span data-ttu-id="11deb-109">なし。</span><span class="sxs-lookup"><span data-stu-id="11deb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="11deb-110">子要素</span><span class="sxs-lookup"><span data-stu-id="11deb-110">Child Elements</span></span>

|<span data-ttu-id="11deb-111">要素</span><span class="sxs-lookup"><span data-stu-id="11deb-111">Element</span></span>|<span data-ttu-id="11deb-112">説明</span><span class="sxs-lookup"><span data-stu-id="11deb-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="11deb-113">構成 (形式) のコントロールのコントロール要素</span><span class="sxs-lookup"><span data-stu-id="11deb-113">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="11deb-114">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="11deb-114">Required element.</span></span><br /><br /> <span data-ttu-id="11deb-115">書式設定ファイルのすべてのビューで使用できる一般的なコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="11deb-115">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="11deb-116">親要素</span><span class="sxs-lookup"><span data-stu-id="11deb-116">Parent Elements</span></span>

|<span data-ttu-id="11deb-117">要素</span><span class="sxs-lookup"><span data-stu-id="11deb-117">Element</span></span>|<span data-ttu-id="11deb-118">説明</span><span class="sxs-lookup"><span data-stu-id="11deb-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="11deb-119">構成要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="11deb-119">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="11deb-120">書式設定ファイルの最上位の要素を表します。</span><span class="sxs-lookup"><span data-stu-id="11deb-120">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="11deb-121">コメント</span><span class="sxs-lookup"><span data-stu-id="11deb-121">Remarks</span></span>

<span data-ttu-id="11deb-122">任意の数のコモン コントロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="11deb-122">You can create any number of common controls.</span></span> <span data-ttu-id="11deb-123">コントロールごとに、コントロールとコントロールのコンポーネントを参照するために使用される名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11deb-123">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="11deb-124">参照</span><span class="sxs-lookup"><span data-stu-id="11deb-124">See Also</span></span>

[<span data-ttu-id="11deb-125">構成要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="11deb-125">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="11deb-126">構成 (形式) のコントロールのコントロール要素</span><span class="sxs-lookup"><span data-stu-id="11deb-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="11deb-127">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="11deb-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
