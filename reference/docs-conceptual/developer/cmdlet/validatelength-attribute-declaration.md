---
title: ValidateLength Attribute 宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.assetid: 82fe3a35-a94b-4bc1-ad9e-dfc5f1e788b3
caps.latest.revision: 13
ms.openlocfilehash: a25fa2410fcc6803563573596af1bc99052c3ffa
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369181"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="b9d7a-102">ValidateLength 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="b9d7a-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="b9d7a-103">ValidateLength 属性は、コマンドレットパラメーター引数の文字数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="b9d7a-104">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9d7a-105">構文</span><span class="sxs-lookup"><span data-stu-id="b9d7a-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="b9d7a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9d7a-106">Parameters</span></span>

<span data-ttu-id="b9d7a-107">`MinLength` ([Int32](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="b9d7a-108">許容される最小文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="b9d7a-109">`MaxLength` ([Int32](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="b9d7a-110">許容される最大文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9d7a-111">コメント</span><span class="sxs-lookup"><span data-stu-id="b9d7a-111">Remarks</span></span>

- <span data-ttu-id="b9d7a-112">この属性を宣言する方法の詳細については、「[入力検証規則を宣言する方法](./how-to-validate-parameter-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="b9d7a-113">この属性が使用されていない場合、対応するパラメーター引数は任意の長さにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-113">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="b9d7a-114">Windows PowerShell ランタイムは、次の状況でエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="b9d7a-115">@No__t-0 属性パラメーターの値が、`MinLength` 属性パラメーターの値より小さい場合。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-115">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

    - <span data-ttu-id="b9d7a-116">@No__t-0 属性パラメーターが0に設定されている場合。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-116">When the `MaxLength` attribute parameter is set to 0.</span></span>

    - <span data-ttu-id="b9d7a-117">引数が文字列でない場合。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-117">When the argument is not a string.</span></span>

- <span data-ttu-id="b9d7a-118">ValidateLength 属性は、 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="b9d7a-118">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9d7a-119">参照</span><span class="sxs-lookup"><span data-stu-id="b9d7a-119">See Also</span></span>

[<span data-ttu-id="b9d7a-120">Validatelengthattribute (システム管理)</span><span class="sxs-lookup"><span data-stu-id="b9d7a-120">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="b9d7a-121">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="b9d7a-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
