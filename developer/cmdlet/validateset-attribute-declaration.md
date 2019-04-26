---
title: ValidateSet 属性の宣言 |Microsoft Docs
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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067071"
---
# <a name="validateset-attribute-declaration"></a><span data-ttu-id="25440-102">ValidateSet 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="25440-102">ValidateSet Attribute Declaration</span></span>

<span data-ttu-id="25440-103">ValidateSetAttribute 属性には、一連のコマンドレット パラメーターの引数に指定できる値を指定します。</span><span class="sxs-lookup"><span data-stu-id="25440-103">The ValidateSetAttribute attribute specifies a set of possible values for a cmdlet parameter argument.</span></span> <span data-ttu-id="25440-104">この属性は、Windows PowerShell 関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="25440-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="25440-105">この属性を指定すると、Windows PowerShell ランタイムがコマンドレット パラメーターに指定された引数が指定された要素セット内の要素と一致するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="25440-105">When this attribute is specified, the Windows PowerShell runtime determines whether the supplied argument for the cmdlet parameter matches an element in the supplied element set.</span></span> <span data-ttu-id="25440-106">コマンドレットは、パラメーターの引数には、set 内の要素が一致する場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="25440-106">The cmdlet is run only if the parameter argument matches an element in the set.</span></span> <span data-ttu-id="25440-107">一致が検出されない場合は、Windows PowerShell ランタイムによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="25440-107">If no match is found, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="25440-108">構文</span><span class="sxs-lookup"><span data-stu-id="25440-108">Syntax</span></span>

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="25440-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25440-109">Parameters</span></span>

<span data-ttu-id="25440-110">`ValidValues` ([System.String](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="25440-110">`ValidValues` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="25440-111">有効なパラメーターの要素の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="25440-111">Specifies the valid parameter element values.</span></span> <span data-ttu-id="25440-112">次の例では、要素を 1 つまたは複数の要素を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="25440-112">The following sample shows how to specify one element or multiple elements.</span></span>

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

<span data-ttu-id="25440-113">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="25440-113">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="25440-114">既定値`true`ケースが無視されることを示します。</span><span class="sxs-lookup"><span data-stu-id="25440-114">The default value of `true` indicates that case is ignored.</span></span> <span data-ttu-id="25440-115">値`false`コマンドレットは、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="25440-115">A value of `false` makes the cmdlet case-sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="25440-116">コメント</span><span class="sxs-lookup"><span data-stu-id="25440-116">Remarks</span></span>

- <span data-ttu-id="25440-117">この属性は、パラメーターごと 1 回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="25440-117">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="25440-118">パラメーターの値が配列の場合、配列の各要素は属性のセットの要素と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25440-118">If the parameter value is an array, every element of the array must match an element of the attribute set.</span></span>

- <span data-ttu-id="25440-119">ValidateSetAttribute 属性を定義した、 [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="25440-119">The ValidateSetAttribute attribute is defined by the [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="25440-120">参照</span><span class="sxs-lookup"><span data-stu-id="25440-120">See Also</span></span>

[<span data-ttu-id="25440-121">System.Management.Automation.Validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="25440-121">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="25440-122">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="25440-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
