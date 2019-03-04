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
ms.openlocfilehash: f7e5d4fb2f89bd6bc7036fdcff8f38e017d5d0e4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858848"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="90ba2-102">パラメーター入力を検証する</span><span class="sxs-lookup"><span data-stu-id="90ba2-102">Validating Parameter Input</span></span>

<span data-ttu-id="90ba2-103">Windows PowerShell には、いくつかの方法でコマンドレットのパラメーターに渡される引数を検証できます。</span><span class="sxs-lookup"><span data-stu-id="90ba2-103">Windows PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span> <span data-ttu-id="90ba2-104">Windows PowerShell には、長さ、範囲、および引数の文字のパターンを検証できます。</span><span class="sxs-lookup"><span data-stu-id="90ba2-104">Windows PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span> <span data-ttu-id="90ba2-105">使用可能な引数 (数) の数を検証できます。</span><span class="sxs-lookup"><span data-stu-id="90ba2-105">It can validate the number of arguments available (the count).</span></span> <span data-ttu-id="90ba2-106">これらの検証規則は、コマンドレット クラスのパブリック プロパティのパラメーターの属性で宣言されている検証属性によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="90ba2-106">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="90ba2-107">パラメーターの引数を検証するには、Windows PowerShell ランタイムは、コマンドレットの実行前に、パラメーターの値を確認するのに検証属性によって提供される情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-107">To validate a parameter argument, the Windows PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span> <span data-ttu-id="90ba2-108">パラメーターの入力が有効でない場合、ユーザーは、エラー メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-108">If the parameter input is not valid, the user receives an error message.</span></span> <span data-ttu-id="90ba2-109">各検証パラメーターは、Windows PowerShell によって適用される検証規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-109">Each validation parameter defines a validation rule that is enforced by Windows PowerShell.</span></span>

<span data-ttu-id="90ba2-110">Windows PowerShell では、次の属性に基づいて規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-110">Windows PowerShell enforces the validation rules based on the following attributes.</span></span>

<span data-ttu-id="90ba2-111">ValidateCount では、パラメーターを受け入れることができる引数の最小値と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-111">ValidateCount Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span> <span data-ttu-id="90ba2-112">この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidateCount 属性宣言](./validatecount-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-112">For more information about the syntax used to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

<span data-ttu-id="90ba2-113">ValidateLength では、パラメーターの引数の最小値と最大文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-113">ValidateLength Specifies the minimum and maximum number of characters in the parameter argument.</span></span> <span data-ttu-id="90ba2-114">この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidateLength 属性宣言](./validatelength-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-114">For more information about the syntax used to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

<span data-ttu-id="90ba2-115">ValidatePattern は、パラメーターの引数を検証する正規表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-115">ValidatePattern Specifies a regular expression that validates the parameter argument.</span></span> <span data-ttu-id="90ba2-116">この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-116">For more information about the syntax used to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

<span data-ttu-id="90ba2-117">ValidateRange では、パラメーターの引数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-117">ValidateRange Specifies the minimum and maximum values of the parameter argument.</span></span> <span data-ttu-id="90ba2-118">この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidateRange 属性宣言](./validaterange-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-118">For more information about the syntax used to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

<span data-ttu-id="90ba2-119">ValidateSet は、パラメーターの引数の有効な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-119">ValidateSet Specifies the valid values for the parameter argument.</span></span> <span data-ttu-id="90ba2-120">この属性を宣言するために使用する構文の詳細については、次を参照してください。 [ValidateSet 属性宣言](./validateset-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="90ba2-120">For more information about the syntax used to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90ba2-121">参照</span><span class="sxs-lookup"><span data-stu-id="90ba2-121">See Also</span></span>

[<span data-ttu-id="90ba2-122">パラメーターの入力を検証する方法</span><span class="sxs-lookup"><span data-stu-id="90ba2-122">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="90ba2-123">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="90ba2-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
