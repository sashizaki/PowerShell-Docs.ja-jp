---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateSet 属性の宣言
description: ValidateSet 属性の宣言
ms.openlocfilehash: 7894d00561366ada492911e8147acbd8d3454a55
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660473"
---
# <a name="validateset-attribute-declaration"></a><span data-ttu-id="6c987-103">ValidateSet 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="6c987-103">ValidateSet Attribute Declaration</span></span>

<span data-ttu-id="6c987-104">ValidateSetAttribute 属性は、コマンドレットパラメーターの引数として使用可能な値のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c987-104">The ValidateSetAttribute attribute specifies a set of possible values for a cmdlet parameter argument.</span></span> <span data-ttu-id="6c987-105">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c987-105">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="6c987-106">この属性を指定すると、Windows PowerShell ランタイムは、コマンドレットパラメーターの指定された引数が、指定された要素セット内の要素と一致するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="6c987-106">When this attribute is specified, the Windows PowerShell runtime determines whether the supplied argument for the cmdlet parameter matches an element in the supplied element set.</span></span> <span data-ttu-id="6c987-107">コマンドレットは、パラメーター引数が set 内の要素と一致する場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="6c987-107">The cmdlet is run only if the parameter argument matches an element in the set.</span></span> <span data-ttu-id="6c987-108">一致するものが見つからない場合は、Windows PowerShell ランタイムによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="6c987-108">If no match is found, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c987-109">構文</span><span class="sxs-lookup"><span data-stu-id="6c987-109">Syntax</span></span>

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="6c987-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c987-110">Parameters</span></span>

<span data-ttu-id="6c987-111">`ValidValues` ([System.string](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="6c987-111">`ValidValues` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="6c987-112">有効なパラメーター要素の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c987-112">Specifies the valid parameter element values.</span></span> <span data-ttu-id="6c987-113">次のサンプルは、1つまたは複数の要素を指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c987-113">The following sample shows how to specify one element or multiple elements.</span></span>

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

<span data-ttu-id="6c987-114">`IgnoreCase` ([System.string) 省略](/dotnet/api/System.Boolean)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="6c987-114">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="6c987-115">の既定値は、 `true` 大文字小文字を区別しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6c987-115">The default value of `true` indicates that case is ignored.</span></span> <span data-ttu-id="6c987-116">値をにすると `false` 、コマンドレットでは大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="6c987-116">A value of `false` makes the cmdlet case-sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c987-117">解説</span><span class="sxs-lookup"><span data-stu-id="6c987-117">Remarks</span></span>

- <span data-ttu-id="6c987-118">この属性は、パラメーターごとに1回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c987-118">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="6c987-119">パラメーター値が配列の場合は、配列のすべての要素が属性セットの要素と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c987-119">If the parameter value is an array, every element of the array must match an element of the attribute set.</span></span>

- <span data-ttu-id="6c987-120">ValidateSetAttribute 属性は、 [ValidateSetAttribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c987-120">The ValidateSetAttribute attribute is defined by the [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c987-121">参照</span><span class="sxs-lookup"><span data-stu-id="6c987-121">See Also</span></span>

[<span data-ttu-id="6c987-122">Validatesetattribute (システム管理)</span><span class="sxs-lookup"><span data-stu-id="6c987-122">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="6c987-123">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="6c987-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
