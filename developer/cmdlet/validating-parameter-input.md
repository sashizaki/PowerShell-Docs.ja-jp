---
title: パラメーターの入力の検証 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameters, validation rules
- validation, examples
- validation
ms.assetid: 3f15bf20-a068-4a7d-a170-bc43f755d1fe
caps.latest.revision: 14
ms.openlocfilehash: 171e3e974619e197a0bcc9dfc759297005e34568
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429841"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="4d27a-102">パラメーター入力を検証する</span><span class="sxs-lookup"><span data-stu-id="4d27a-102">Validating Parameter Input</span></span>

<span data-ttu-id="4d27a-103">PowerShell では、いくつかの方法でコマンドレットのパラメーターに渡される引数を検証できます。</span><span class="sxs-lookup"><span data-stu-id="4d27a-103">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="4d27a-104">PowerShell には、長さ、範囲、および引数の文字のパターンを検証できます。</span><span class="sxs-lookup"><span data-stu-id="4d27a-104">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="4d27a-105">使用可能な引数 (数) の数を検証できます。</span><span class="sxs-lookup"><span data-stu-id="4d27a-105">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="4d27a-106">これらの検証規則は、コマンドレット クラスのパブリック プロパティのパラメーターの属性で宣言されている検証属性によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4d27a-106">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="4d27a-107">パラメーターの引数を検証するには、PowerShell のランタイムは、コマンドレットの実行前に、パラメーターの値を確認するのに検証属性によって提供される情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-107">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="4d27a-108">パラメーターの入力が有効でない場合、ユーザーは、エラー メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-108">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="4d27a-109">各検証パラメーターは、PowerShell によって適用される検証規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-109">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="4d27a-110">PowerShell では、次の属性に基づいて規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-110">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="4d27a-111">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="4d27a-111">ValidateCount</span></span>

<span data-ttu-id="4d27a-112">パラメーターを受け入れることができる引数の最小値と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-112">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="4d27a-113">詳細については、次を参照してください。 [ValidateCount 属性宣言](./validatecount-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-113">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="4d27a-114">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="4d27a-114">ValidateLength</span></span>

<span data-ttu-id="4d27a-115">パラメーターの引数では、最小値と最大文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-115">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="4d27a-116">詳細については、次を参照してください。 [ValidateLength 属性宣言](./validatelength-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-116">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="4d27a-117">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="4d27a-117">ValidatePattern</span></span>

<span data-ttu-id="4d27a-118">パラメーターの引数を検証する正規表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-118">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="4d27a-119">詳細については、次を参照してください。 [ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-119">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="4d27a-120">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="4d27a-120">ValidateRange</span></span>

<span data-ttu-id="4d27a-121">パラメーターの引数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-121">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="4d27a-122">詳細については、次を参照してください。 [ValidateRange 属性宣言](./validaterange-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-122">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="4d27a-123">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="4d27a-123">ValidateSet</span></span>

<span data-ttu-id="4d27a-124">パラメーターの引数の有効な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-124">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="4d27a-125">詳細については、次を参照してください。 [ValidateSet 属性宣言](./validateset-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d27a-125">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d27a-126">参照</span><span class="sxs-lookup"><span data-stu-id="4d27a-126">See Also</span></span>

[<span data-ttu-id="4d27a-127">パラメーターの入力を検証する方法</span><span class="sxs-lookup"><span data-stu-id="4d27a-127">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="4d27a-128">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="4d27a-128">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
