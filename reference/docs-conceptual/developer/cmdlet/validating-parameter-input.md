---
ms.date: 09/13/2016
ms.topic: reference
title: パラメーター入力を検証する
description: パラメーター入力を検証する
ms.openlocfilehash: a97b5c670e8c36463a85bbef1506f6311bdd5ec3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660393"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="1c975-103">パラメーター入力を検証する</span><span class="sxs-lookup"><span data-stu-id="1c975-103">Validating Parameter Input</span></span>

<span data-ttu-id="1c975-104">PowerShell では、コマンドレットパラメーターに渡す引数をいくつかの方法で検証できます。</span><span class="sxs-lookup"><span data-stu-id="1c975-104">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="1c975-105">PowerShell では、引数の長さ、範囲、および文字のパターンを検証できます。</span><span class="sxs-lookup"><span data-stu-id="1c975-105">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="1c975-106">使用可能な引数の数 (カウント) を検証できます。</span><span class="sxs-lookup"><span data-stu-id="1c975-106">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="1c975-107">これらの検証規則は、コマンドレットクラスのパブリックプロパティでパラメーター属性を使用して宣言された検証属性によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="1c975-107">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="1c975-108">パラメーター引数を検証するために、PowerShell ランタイムは検証属性によって提供される情報を使用して、コマンドレットの実行前にパラメーターの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="1c975-108">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="1c975-109">パラメーターの入力が有効でない場合、ユーザーはエラーメッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1c975-109">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="1c975-110">各検証パラメーターでは、PowerShell によって適用される検証規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="1c975-110">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="1c975-111">PowerShell では、次の属性に基づいて検証規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="1c975-111">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="1c975-112">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="1c975-112">ValidateCount</span></span>

<span data-ttu-id="1c975-113">パラメーターが受け入れることができる引数の最小数と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c975-113">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="1c975-114">詳細については、「 [Validatecount 属性の宣言](./validatecount-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c975-114">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="1c975-115">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="1c975-115">ValidateLength</span></span>

<span data-ttu-id="1c975-116">パラメーター引数の文字数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c975-116">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="1c975-117">詳細については、「 [ValidateLength Attribute 宣言](./validatelength-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c975-117">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="1c975-118">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="1c975-118">ValidatePattern</span></span>

<span data-ttu-id="1c975-119">パラメーター引数を検証する正規表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c975-119">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="1c975-120">詳細については、「 [Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c975-120">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="1c975-121">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="1c975-121">ValidateRange</span></span>

<span data-ttu-id="1c975-122">パラメーター引数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c975-122">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="1c975-123">詳細については、「 [ValidateRange Attribute 宣言](./validaterange-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c975-123">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="1c975-124">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="1c975-124">ValidateSet</span></span>

<span data-ttu-id="1c975-125">パラメーター引数の有効な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c975-125">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="1c975-126">詳細については、「 [Validateset 属性の宣言](./validateset-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c975-126">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c975-127">参照</span><span class="sxs-lookup"><span data-stu-id="1c975-127">See Also</span></span>

[<span data-ttu-id="1c975-128">パラメーター入力を検証する方法</span><span class="sxs-lookup"><span data-stu-id="1c975-128">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="1c975-129">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="1c975-129">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
