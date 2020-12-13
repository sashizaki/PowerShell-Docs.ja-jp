---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateLength 属性の宣言
description: ValidateLength 属性の宣言
ms.openlocfilehash: b35fe24c6fc44aaca6a39d819d6e3fc2d8a2cade
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646183"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="05531-103">ValidateLength 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="05531-103">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="05531-104">ValidateLength 属性は、コマンドレットパラメーター引数の文字数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="05531-104">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="05531-105">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="05531-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="05531-106">構文</span><span class="sxs-lookup"><span data-stu-id="05531-106">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="05531-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="05531-107">Parameters</span></span>

<span data-ttu-id="05531-108">`MinLength` ([System.string](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="05531-108">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="05531-109">許容される最小文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="05531-109">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="05531-110">`MaxLength` ([System.string](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="05531-110">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="05531-111">許容される最大文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="05531-111">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="05531-112">解説</span><span class="sxs-lookup"><span data-stu-id="05531-112">Remarks</span></span>

- <span data-ttu-id="05531-113">この属性を宣言する方法の詳細については、「 [入力検証規則を宣言する方法](./how-to-validate-parameter-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05531-113">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="05531-114">この属性が使用されていない場合、対応するパラメーター引数は任意の長さにすることができます。</span><span class="sxs-lookup"><span data-stu-id="05531-114">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="05531-115">Windows PowerShell ランタイムは、次の状況でエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="05531-115">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="05531-116">`MaxLength`属性パラメーターの値が属性パラメーターの値より小さい場合 `MinLength` 。</span><span class="sxs-lookup"><span data-stu-id="05531-116">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

  - <span data-ttu-id="05531-117">`MaxLength`属性パラメーターが0に設定されている場合。</span><span class="sxs-lookup"><span data-stu-id="05531-117">When the `MaxLength` attribute parameter is set to 0.</span></span>

  - <span data-ttu-id="05531-118">引数が文字列でない場合。</span><span class="sxs-lookup"><span data-stu-id="05531-118">When the argument is not a string.</span></span>

- <span data-ttu-id="05531-119">ValidateLength 属性は、 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="05531-119">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="05531-120">参照</span><span class="sxs-lookup"><span data-stu-id="05531-120">See Also</span></span>

[<span data-ttu-id="05531-121">Validatelengthattribute (システム管理)</span><span class="sxs-lookup"><span data-stu-id="05531-121">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="05531-122">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="05531-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
