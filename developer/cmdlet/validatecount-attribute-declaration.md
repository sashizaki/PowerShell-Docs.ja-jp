---
title: ValidateCount 属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: 1a7b5ea340fe5212d003c97a9017278d6c631355
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859158"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="9259b-102">ValidateCount 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="9259b-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="9259b-103">ValidateCount 属性には、コマンドレット パラメーターの許可されている引数の最小値と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9259b-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="9259b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9259b-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="9259b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9259b-105">Parameters</span></span>

<span data-ttu-id="9259b-106">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="9259b-106">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="9259b-107">引数の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9259b-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="9259b-108">`MaxLength`([System.Int32](/dotnet/api/System.Int32)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="9259b-108">`MaxLength`([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="9259b-109">引数の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9259b-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="9259b-110">コメント</span><span class="sxs-lookup"><span data-stu-id="9259b-110">Remarks</span></span>

- <span data-ttu-id="9259b-111">この属性を宣言する方法の詳細については、次を参照してください。[入力検証規則の宣言方法](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b)します。</span><span class="sxs-lookup"><span data-stu-id="9259b-111">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).</span></span>

- <span data-ttu-id="9259b-112">この属性がない呼び出されると、コマンドレットの対応するパラメーターに任意の数の引数のことができます。</span><span class="sxs-lookup"><span data-stu-id="9259b-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="9259b-113">Windows PowerShell ランタイムには、次の条件下でエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="9259b-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="9259b-114">`MinLength`と`MaxLength`型の属性のパラメーターがない[System.Int32](/dotnet/api/System.Int32)します。</span><span class="sxs-lookup"><span data-stu-id="9259b-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32](/dotnet/api/System.Int32).</span></span>

    - <span data-ttu-id="9259b-115">値、`MaxLength`属性パラメーターは、の値より小さい、`MinLength`属性パラメーター。</span><span class="sxs-lookup"><span data-stu-id="9259b-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="9259b-116">ValidateCount 属性を定義した、 [System.Management.Automation.Validatecount](/dotnet/api/System.Management.Automation.ValidateCount)クラス。</span><span class="sxs-lookup"><span data-stu-id="9259b-116">The ValidateCount attribute is defined by the [System.Management.Automation.Validatecount](/dotnet/api/System.Management.Automation.ValidateCount) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="9259b-117">参照</span><span class="sxs-lookup"><span data-stu-id="9259b-117">See Also</span></span>

[<span data-ttu-id="9259b-118">System.Management.Automation.Validatecount</span><span class="sxs-lookup"><span data-stu-id="9259b-118">System.Management.Automation.Validatecount</span></span>](/dotnet/api/System.Management.Automation.ValidateCount)

[<span data-ttu-id="9259b-119">入力の検証規則を宣言する方法</span><span class="sxs-lookup"><span data-stu-id="9259b-119">How to Declare Input Validation Rules</span></span>](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b)

[<span data-ttu-id="9259b-120">入力の検証規則を宣言する方法</span><span class="sxs-lookup"><span data-stu-id="9259b-120">How to Declare Input Validation Rules</span></span>](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b)

[<span data-ttu-id="9259b-121">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="9259b-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
