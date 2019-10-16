---
title: Configuration の Controls 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369001"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="20dbb-102">Configuration の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="20dbb-102">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="20dbb-103">書式設定ファイルのすべてのビューで使用できる共通コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="20dbb-103">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="20dbb-104">Configuration 要素 (Format) コントロールの構成要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="20dbb-104">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="20dbb-105">構文</span><span class="sxs-lookup"><span data-stu-id="20dbb-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="20dbb-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="20dbb-106">Attributes and Elements</span></span>

<span data-ttu-id="20dbb-107">次のセクションでは、`Controls` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="20dbb-107">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="20dbb-108">属性</span><span class="sxs-lookup"><span data-stu-id="20dbb-108">Attributes</span></span>

<span data-ttu-id="20dbb-109">なし。</span><span class="sxs-lookup"><span data-stu-id="20dbb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="20dbb-110">子要素</span><span class="sxs-lookup"><span data-stu-id="20dbb-110">Child Elements</span></span>

|<span data-ttu-id="20dbb-111">要素</span><span class="sxs-lookup"><span data-stu-id="20dbb-111">Element</span></span>|<span data-ttu-id="20dbb-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="20dbb-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="20dbb-113">Configuration のコントロールの Control 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="20dbb-113">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="20dbb-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="20dbb-114">Required element.</span></span><br /><br /> <span data-ttu-id="20dbb-115">書式設定ファイルのすべてのビューで使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="20dbb-115">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="20dbb-116">親要素</span><span class="sxs-lookup"><span data-stu-id="20dbb-116">Parent Elements</span></span>

|<span data-ttu-id="20dbb-117">要素</span><span class="sxs-lookup"><span data-stu-id="20dbb-117">Element</span></span>|<span data-ttu-id="20dbb-118">[説明]</span><span class="sxs-lookup"><span data-stu-id="20dbb-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="20dbb-119">Configuration 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="20dbb-119">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="20dbb-120">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="20dbb-120">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="20dbb-121">コメント</span><span class="sxs-lookup"><span data-stu-id="20dbb-121">Remarks</span></span>

<span data-ttu-id="20dbb-122">任意の数のコモンコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="20dbb-122">You can create any number of common controls.</span></span> <span data-ttu-id="20dbb-123">コントロールごとに、コントロールとそのコンポーネントを参照するために使用する名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20dbb-123">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="20dbb-124">参照</span><span class="sxs-lookup"><span data-stu-id="20dbb-124">See Also</span></span>

[<span data-ttu-id="20dbb-125">Configuration 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="20dbb-125">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="20dbb-126">Configuration のコントロールの Control 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="20dbb-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="20dbb-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="20dbb-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
