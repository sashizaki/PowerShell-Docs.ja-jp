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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068661"
---
# <a name="attribute-types"></a><span data-ttu-id="2daa0-102">属性の種類</span><span class="sxs-lookup"><span data-stu-id="2daa0-102">Attribute Types</span></span>

<span data-ttu-id="2daa0-103">コマンドレットの属性は、機能のグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="2daa0-103">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="2daa0-104">次のセクションでは、使用可能な属性を記述し、ランタイムが、属性が呼び出されたときにを説明します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-104">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="2daa0-105">コマンドレットの属性</span><span class="sxs-lookup"><span data-stu-id="2daa0-105">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="2daa0-106">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="2daa0-106">Cmdlet</span></span>

<span data-ttu-id="2daa0-107">コマンドレットとしては、.NET Framework クラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-107">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="2daa0-108">これは、必要な基本属性です。</span><span class="sxs-lookup"><span data-stu-id="2daa0-108">This is the required base attribute.</span></span>
<span data-ttu-id="2daa0-109">詳細については、次を参照してください。[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-109">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="2daa0-110">パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="2daa0-110">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="2daa0-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2daa0-111">Parameter</span></span>

<span data-ttu-id="2daa0-112">コマンドレット パラメーターとしてコマンドレット クラスのパブリック プロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-112">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="2daa0-113">詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-113">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="2daa0-114">エイリアス</span><span class="sxs-lookup"><span data-stu-id="2daa0-114">Alias</span></span>

<span data-ttu-id="2daa0-115">パラメーターの 1 つまたは複数のエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-115">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="2daa0-116">詳細については、次を参照してください。[エイリアス属性宣言](./alias-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-116">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="2daa0-117">引数の検証属性</span><span class="sxs-lookup"><span data-stu-id="2daa0-117">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="2daa0-118">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="2daa0-118">ValidateCount</span></span>

<span data-ttu-id="2daa0-119">コマンドレット パラメーターに使用できる引数の最小値と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-119">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="2daa0-120">詳細については、次を参照してください。 [ValidateCount 属性宣言](./validatecount-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-120">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="2daa0-121">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="2daa0-121">ValidateLength</span></span>

<span data-ttu-id="2daa0-122">コマンドレット パラメーターの引数の文字の最小値と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-122">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="2daa0-123">詳細については、次を参照してください。 [ValidateLength 属性宣言](./validatelength-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-123">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="2daa0-124">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="2daa0-124">ValidatePattern</span></span>

<span data-ttu-id="2daa0-125">コマンドレットのパラメーターの引数と一致する正規表現パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-125">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="2daa0-126">詳細については、次を参照してください。 [ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-126">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="2daa0-127">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="2daa0-127">ValidateRange</span></span>

<span data-ttu-id="2daa0-128">コマンドレット パラメーターの引数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-128">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="2daa0-129">詳細については、次を参照してください。 [ValidateRange 属性宣言](./validaterange-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-129">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="2daa0-130">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="2daa0-130">ValidateSet</span></span>

<span data-ttu-id="2daa0-131">一連のコマンドレット パラメーターの引数の有効な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-131">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="2daa0-132">詳細については、次を参照してください。 [ValidateSet 属性宣言](./validateset-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="2daa0-132">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2daa0-133">参照</span><span class="sxs-lookup"><span data-stu-id="2daa0-133">See Also</span></span>

[<span data-ttu-id="2daa0-134">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="2daa0-134">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
