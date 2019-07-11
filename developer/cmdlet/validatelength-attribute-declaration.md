---
title: ValidateLength 属性の宣言 |Microsoft Docs
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
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735098"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="f6d79-102">ValidateLength 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="f6d79-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="f6d79-103">ValidateLength 属性には、コマンドレット パラメーターの引数の文字の最小値と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6d79-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="f6d79-104">この属性は、Windows PowerShell 関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6d79-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6d79-105">構文</span><span class="sxs-lookup"><span data-stu-id="f6d79-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="f6d79-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6d79-106">Parameters</span></span>

<span data-ttu-id="f6d79-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="f6d79-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="f6d79-108">許可される文字の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6d79-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="f6d79-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="f6d79-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="f6d79-110">許可される文字の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6d79-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6d79-111">コメント</span><span class="sxs-lookup"><span data-stu-id="f6d79-111">Remarks</span></span>

- <span data-ttu-id="f6d79-112">この属性を宣言する方法の詳細については、次を参照してください。[入力検証規則の宣言方法](./how-to-validate-parameter-input.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6d79-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="f6d79-113">この属性を使用しない場合、任意の長さの対応するパラメーターの引数を引き起こすことができます。</span><span class="sxs-lookup"><span data-stu-id="f6d79-113">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="f6d79-114">Windows PowerShell ランタイムには、次の条件下でエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="f6d79-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="f6d79-115">ときの値、`MaxLength`属性パラメーターは、の値より小さい、`MinLength`属性パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f6d79-115">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

    - <span data-ttu-id="f6d79-116">ときに、`MaxLength`属性のパラメーターが 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="f6d79-116">When the `MaxLength` attribute parameter is set to 0.</span></span>

    - <span data-ttu-id="f6d79-117">ときに、引数は文字列ではありません。</span><span class="sxs-lookup"><span data-stu-id="f6d79-117">When the argument is not a string.</span></span>

- <span data-ttu-id="f6d79-118">ValidateLength 属性を定義した、 [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="f6d79-118">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6d79-119">参照</span><span class="sxs-lookup"><span data-stu-id="f6d79-119">See Also</span></span>

[<span data-ttu-id="f6d79-120">System.Management.Automation.Validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="f6d79-120">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="f6d79-121">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="f6d79-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
