---
title: Configuration の Controls 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 44b9db0d3523e5e9086da9911882b258a2a54ca6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783791"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="0dc21-102">Configuration の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0dc21-102">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="0dc21-103">書式設定ファイルのすべてのビューで使用できる共通コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="0dc21-103">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="0dc21-104">Configuration 要素 (Format) コントロールの構成要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0dc21-104">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0dc21-105">構文</span><span class="sxs-lookup"><span data-stu-id="0dc21-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0dc21-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0dc21-106">Attributes and Elements</span></span>

<span data-ttu-id="0dc21-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `Controls` ます。</span><span class="sxs-lookup"><span data-stu-id="0dc21-107">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0dc21-108">属性</span><span class="sxs-lookup"><span data-stu-id="0dc21-108">Attributes</span></span>

<span data-ttu-id="0dc21-109">なし。</span><span class="sxs-lookup"><span data-stu-id="0dc21-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0dc21-110">子要素</span><span class="sxs-lookup"><span data-stu-id="0dc21-110">Child Elements</span></span>

|<span data-ttu-id="0dc21-111">要素</span><span class="sxs-lookup"><span data-stu-id="0dc21-111">Element</span></span>|<span data-ttu-id="0dc21-112">説明</span><span class="sxs-lookup"><span data-stu-id="0dc21-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0dc21-113">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0dc21-113">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="0dc21-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="0dc21-114">Required element.</span></span><br /><br /> <span data-ttu-id="0dc21-115">書式設定ファイルのすべてのビューで使用できるコモンコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="0dc21-115">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0dc21-116">親要素</span><span class="sxs-lookup"><span data-stu-id="0dc21-116">Parent Elements</span></span>

|<span data-ttu-id="0dc21-117">要素</span><span class="sxs-lookup"><span data-stu-id="0dc21-117">Element</span></span>|<span data-ttu-id="0dc21-118">説明</span><span class="sxs-lookup"><span data-stu-id="0dc21-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0dc21-119">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0dc21-119">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="0dc21-120">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="0dc21-120">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0dc21-121">解説</span><span class="sxs-lookup"><span data-stu-id="0dc21-121">Remarks</span></span>

<span data-ttu-id="0dc21-122">任意の数のコモンコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0dc21-122">You can create any number of common controls.</span></span> <span data-ttu-id="0dc21-123">コントロールごとに、コントロールとそのコンポーネントを参照するために使用する名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc21-123">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dc21-124">参照</span><span class="sxs-lookup"><span data-stu-id="0dc21-124">See Also</span></span>

[<span data-ttu-id="0dc21-125">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0dc21-125">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="0dc21-126">Configuration の Controls の Control 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0dc21-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="0dc21-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="0dc21-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
