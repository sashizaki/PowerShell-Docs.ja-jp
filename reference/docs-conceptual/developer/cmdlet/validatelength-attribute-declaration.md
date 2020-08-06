---
title: ValidateLength Attribute 宣言 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.openlocfilehash: 7145dde55e79eeea6e3ceb91dfc1c93043a8857c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786307"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="d5e94-102">ValidateLength 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="d5e94-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="d5e94-103">ValidateLength 属性は、コマンドレットパラメーター引数の文字数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5e94-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="d5e94-104">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5e94-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5e94-105">構文</span><span class="sxs-lookup"><span data-stu-id="d5e94-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="d5e94-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5e94-106">Parameters</span></span>

<span data-ttu-id="d5e94-107">`MinLength`([System.string](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="d5e94-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="d5e94-108">許容される最小文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5e94-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="d5e94-109">`MaxLength`([System.string](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="d5e94-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="d5e94-110">許容される最大文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5e94-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5e94-111">解説</span><span class="sxs-lookup"><span data-stu-id="d5e94-111">Remarks</span></span>

- <span data-ttu-id="d5e94-112">この属性を宣言する方法の詳細については、「[入力検証規則を宣言する方法](./how-to-validate-parameter-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5e94-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="d5e94-113">この属性が使用されていない場合、対応するパラメーター引数は任意の長さにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5e94-113">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="d5e94-114">Windows PowerShell ランタイムは、次の状況でエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="d5e94-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="d5e94-115">`MaxLength`属性パラメーターの値が属性パラメーターの値より小さい場合 `MinLength` 。</span><span class="sxs-lookup"><span data-stu-id="d5e94-115">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

  - <span data-ttu-id="d5e94-116">`MaxLength`属性パラメーターが0に設定されている場合。</span><span class="sxs-lookup"><span data-stu-id="d5e94-116">When the `MaxLength` attribute parameter is set to 0.</span></span>

  - <span data-ttu-id="d5e94-117">引数が文字列でない場合。</span><span class="sxs-lookup"><span data-stu-id="d5e94-117">When the argument is not a string.</span></span>

- <span data-ttu-id="d5e94-118">ValidateLength 属性は、 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="d5e94-118">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5e94-119">参照</span><span class="sxs-lookup"><span data-stu-id="d5e94-119">See Also</span></span>

[<span data-ttu-id="d5e94-120">Validatelengthattribute (システム管理)</span><span class="sxs-lookup"><span data-stu-id="d5e94-120">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="d5e94-121">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="d5e94-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
