---
title: ValidateSet 属性宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateSet
- ValidateSet attribute, described
- ValidateSet attribute
ms.assetid: 4a6f97ab-45b2-4f3d-84d4-30acf8e074d0
caps.latest.revision: 12
ms.openlocfilehash: b036f39cd01ffe4b4ce7db9627cb6da0d5327190
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364281"
---
# <a name="validateset-attribute-declaration"></a><span data-ttu-id="2cd66-102">ValidateSet 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="2cd66-102">ValidateSet Attribute Declaration</span></span>

<span data-ttu-id="2cd66-103">ValidateSetAttribute 属性は、コマンドレットパラメーターの引数として使用可能な値のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cd66-103">The ValidateSetAttribute attribute specifies a set of possible values for a cmdlet parameter argument.</span></span> <span data-ttu-id="2cd66-104">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cd66-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="2cd66-105">この属性を指定すると、Windows PowerShell ランタイムは、コマンドレットパラメーターの指定された引数が、指定された要素セット内の要素と一致するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2cd66-105">When this attribute is specified, the Windows PowerShell runtime determines whether the supplied argument for the cmdlet parameter matches an element in the supplied element set.</span></span> <span data-ttu-id="2cd66-106">コマンドレットは、パラメーター引数が set 内の要素と一致する場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="2cd66-106">The cmdlet is run only if the parameter argument matches an element in the set.</span></span> <span data-ttu-id="2cd66-107">一致するものが見つからない場合は、Windows PowerShell ランタイムによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="2cd66-107">If no match is found, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="2cd66-108">構文</span><span class="sxs-lookup"><span data-stu-id="2cd66-108">Syntax</span></span>

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="2cd66-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cd66-109">Parameters</span></span>

<span data-ttu-id="2cd66-110">`ValidValues` ([system.string](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="2cd66-110">`ValidValues` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="2cd66-111">有効なパラメーター要素の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cd66-111">Specifies the valid parameter element values.</span></span> <span data-ttu-id="2cd66-112">次のサンプルは、1つまたは複数の要素を指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2cd66-112">The following sample shows how to specify one element or multiple elements.</span></span>

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

<span data-ttu-id="2cd66-113">@no__t-[0 (system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="2cd66-113">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="2cd66-114">@No__t-0 の既定値は、大文字小文字が無視されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2cd66-114">The default value of `true` indicates that case is ignored.</span></span> <span data-ttu-id="2cd66-115">値を `false` にすると、コマンドレットで大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2cd66-115">A value of `false` makes the cmdlet case-sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="2cd66-116">コメント</span><span class="sxs-lookup"><span data-stu-id="2cd66-116">Remarks</span></span>

- <span data-ttu-id="2cd66-117">この属性は、パラメーターごとに1回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cd66-117">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="2cd66-118">パラメーター値が配列の場合は、配列のすべての要素が属性セットの要素と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cd66-118">If the parameter value is an array, every element of the array must match an element of the attribute set.</span></span>

- <span data-ttu-id="2cd66-119">ValidateSetAttribute 属性は、 [ValidateSetAttribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2cd66-119">The ValidateSetAttribute attribute is defined by the [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="2cd66-120">参照</span><span class="sxs-lookup"><span data-stu-id="2cd66-120">See Also</span></span>

[<span data-ttu-id="2cd66-121">Validatesetattribute (システム管理)</span><span class="sxs-lookup"><span data-stu-id="2cd66-121">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="2cd66-122">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="2cd66-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
