---
title: 属性の種類 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b1026ad-f072-4fca-8052-a2d8eb491c2a
caps.latest.revision: 6
ms.openlocfilehash: 52c75b3ca73706da39029d5b3ead52ff7197a5f1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364581"
---
# <a name="attribute-types"></a><span data-ttu-id="218da-102">属性の種類</span><span class="sxs-lookup"><span data-stu-id="218da-102">Attribute Types</span></span>

<span data-ttu-id="218da-103">コマンドレットの属性は、機能によってグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="218da-103">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="218da-104">次のセクションでは、使用可能な属性について説明し、属性が呼び出されたときのランタイムの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="218da-104">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="218da-105">コマンドレットの属性</span><span class="sxs-lookup"><span data-stu-id="218da-105">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="218da-106">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="218da-106">Cmdlet</span></span>

<span data-ttu-id="218da-107">.NET Framework クラスをコマンドレットとして識別します。</span><span class="sxs-lookup"><span data-stu-id="218da-107">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="218da-108">これは必須の基本属性です。</span><span class="sxs-lookup"><span data-stu-id="218da-108">This is the required base attribute.</span></span>
<span data-ttu-id="218da-109">詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="218da-109">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="218da-110">パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="218da-110">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="218da-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="218da-111">Parameter</span></span>

<span data-ttu-id="218da-112">コマンドレットパラメーターとしてコマンドレットクラスのパブリックプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="218da-112">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="218da-113">詳細については、「[パラメーター属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="218da-113">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="218da-114">エイリアス</span><span class="sxs-lookup"><span data-stu-id="218da-114">Alias</span></span>

<span data-ttu-id="218da-115">パラメーターの1つ以上のエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="218da-115">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="218da-116">詳細については、「[エイリアス属性の宣言](./alias-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="218da-116">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="218da-117">引数の検証属性</span><span class="sxs-lookup"><span data-stu-id="218da-117">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="218da-118">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="218da-118">ValidateCount</span></span>

<span data-ttu-id="218da-119">コマンドレットパラメーターに使用できる引数の最小数と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="218da-119">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="218da-120">詳細については、「 [Validatecount 属性の宣言](./validatecount-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="218da-120">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="218da-121">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="218da-121">ValidateLength</span></span>

<span data-ttu-id="218da-122">コマンドレットパラメーター引数の文字数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="218da-122">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="218da-123">詳細については、「 [ValidateLength Attribute 宣言](./validatelength-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="218da-123">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="218da-124">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="218da-124">ValidatePattern</span></span>

<span data-ttu-id="218da-125">コマンドレットパラメーターの引数が一致する必要がある正規表現パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="218da-125">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="218da-126">詳細については、「 [Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="218da-126">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="218da-127">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="218da-127">ValidateRange</span></span>

<span data-ttu-id="218da-128">コマンドレットパラメーター引数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="218da-128">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="218da-129">詳細については、「 [ValidateRange Attribute 宣言](./validaterange-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="218da-129">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="218da-130">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="218da-130">ValidateSet</span></span>

<span data-ttu-id="218da-131">コマンドレットパラメーター引数に有効な値のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="218da-131">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="218da-132">詳細については、「 [Validateset 属性の宣言](./validateset-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="218da-132">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="218da-133">参照</span><span class="sxs-lookup"><span data-stu-id="218da-133">See Also</span></span>

[<span data-ttu-id="218da-134">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="218da-134">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
