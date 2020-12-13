---
ms.date: 09/13/2016
ms.topic: reference
title: 属性の種類
description: 属性の種類
ms.openlocfilehash: 65640f2f8449887dedb9fae137eb16b6252f1d57
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667115"
---
# <a name="attribute-types"></a><span data-ttu-id="4ee63-103">属性の種類</span><span class="sxs-lookup"><span data-stu-id="4ee63-103">Attribute Types</span></span>

<span data-ttu-id="4ee63-104">コマンドレットの属性は、機能によってグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="4ee63-104">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="4ee63-105">次のセクションでは、使用可能な属性について説明し、属性が呼び出されたときのランタイムの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ee63-105">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="4ee63-106">コマンドレットの属性</span><span class="sxs-lookup"><span data-stu-id="4ee63-106">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="4ee63-107">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="4ee63-107">Cmdlet</span></span>

<span data-ttu-id="4ee63-108">.NET Framework クラスをコマンドレットとして識別します。</span><span class="sxs-lookup"><span data-stu-id="4ee63-108">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="4ee63-109">これは必須の基本属性です。</span><span class="sxs-lookup"><span data-stu-id="4ee63-109">This is the required base attribute.</span></span>
<span data-ttu-id="4ee63-110">詳細については、「 [コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee63-110">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="4ee63-111">パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="4ee63-111">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="4ee63-112">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ee63-112">Parameter</span></span>

<span data-ttu-id="4ee63-113">コマンドレットパラメーターとしてコマンドレットクラスのパブリックプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="4ee63-113">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="4ee63-114">詳細については、「 [パラメーター属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee63-114">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="4ee63-115">エイリアス</span><span class="sxs-lookup"><span data-stu-id="4ee63-115">Alias</span></span>

<span data-ttu-id="4ee63-116">パラメーターの1つ以上のエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ee63-116">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="4ee63-117">詳細については、「 [エイリアス属性の宣言](./alias-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee63-117">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="4ee63-118">引数の検証属性</span><span class="sxs-lookup"><span data-stu-id="4ee63-118">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="4ee63-119">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="4ee63-119">ValidateCount</span></span>

<span data-ttu-id="4ee63-120">コマンドレットパラメーターに使用できる引数の最小数と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ee63-120">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="4ee63-121">詳細については、「 [Validatecount 属性の宣言](./validatecount-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee63-121">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="4ee63-122">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="4ee63-122">ValidateLength</span></span>

<span data-ttu-id="4ee63-123">コマンドレットパラメーター引数の文字数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ee63-123">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="4ee63-124">詳細については、「 [ValidateLength Attribute 宣言](./validatelength-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee63-124">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="4ee63-125">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="4ee63-125">ValidatePattern</span></span>

<span data-ttu-id="4ee63-126">コマンドレットパラメーターの引数が一致する必要がある正規表現パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ee63-126">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="4ee63-127">詳細については、「 [Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee63-127">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="4ee63-128">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="4ee63-128">ValidateRange</span></span>

<span data-ttu-id="4ee63-129">コマンドレットパラメーター引数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ee63-129">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="4ee63-130">詳細については、「 [ValidateRange Attribute 宣言](./validaterange-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee63-130">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="4ee63-131">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="4ee63-131">ValidateSet</span></span>

<span data-ttu-id="4ee63-132">コマンドレットパラメーター引数に有効な値のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ee63-132">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="4ee63-133">詳細については、「 [Validateset 属性の宣言](./validateset-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee63-133">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4ee63-134">参照</span><span class="sxs-lookup"><span data-stu-id="4ee63-134">See Also</span></span>

[<span data-ttu-id="4ee63-135">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="4ee63-135">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
