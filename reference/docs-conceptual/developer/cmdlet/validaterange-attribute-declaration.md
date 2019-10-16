---
title: ValidateRange Attribute 宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.assetid: 1f8066e6-e5d3-4f4e-8948-a90af5dace82
caps.latest.revision: 11
ms.openlocfilehash: 155a406b9855c435041fe175ac7d983a4b4eb8b7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369131"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="868cf-102">ValidateRange 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="868cf-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="868cf-103">ValidateRange 属性は、コマンドレットパラメーター引数の最小値と最大値 (範囲) を指定します。</span><span class="sxs-lookup"><span data-stu-id="868cf-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="868cf-104">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="868cf-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="868cf-105">構文</span><span class="sxs-lookup"><span data-stu-id="868cf-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="868cf-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="868cf-106">Parameters</span></span>

<span data-ttu-id="868cf-107">`MinRange` ([system.object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="868cf-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="868cf-108">許容される最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="868cf-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="868cf-109">`MaxRange` ([system.object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="868cf-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="868cf-110">許容される最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="868cf-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="868cf-111">コメント</span><span class="sxs-lookup"><span data-stu-id="868cf-111">Remarks</span></span>

- <span data-ttu-id="868cf-112">@No__t-0 パラメーターの値が `MaxRange` パラメーターの値よりも大きい場合、Windows PowerShell ランタイムは構築エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="868cf-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="868cf-113">Windows PowerShell ランタイムは、次の条件下で検証エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="868cf-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

    - <span data-ttu-id="868cf-114">引数の値が @no__t 0 より小さいか、@no__t の上限を超えている場合。</span><span class="sxs-lookup"><span data-stu-id="868cf-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

    - <span data-ttu-id="868cf-115">引数が `MinRange` および `MaxRange` パラメーターと同じ型ではない場合。</span><span class="sxs-lookup"><span data-stu-id="868cf-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="868cf-116">ValidateRange 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="868cf-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="868cf-117">参照</span><span class="sxs-lookup"><span data-stu-id="868cf-117">See Also</span></span>

[<span data-ttu-id="868cf-118">System. Automation. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="868cf-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="868cf-119">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="868cf-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
