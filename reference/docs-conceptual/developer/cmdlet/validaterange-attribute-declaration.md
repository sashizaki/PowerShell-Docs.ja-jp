---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateRange 属性の宣言
description: ValidateRange 属性の宣言
ms.openlocfilehash: 1fec9d1bd36cd21b7f0f23bf6d72338d276dce91
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660603"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="70730-103">ValidateRange 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="70730-103">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="70730-104">ValidateRange 属性は、コマンドレットパラメーター引数の最小値と最大値 (範囲) を指定します。</span><span class="sxs-lookup"><span data-stu-id="70730-104">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="70730-105">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="70730-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="70730-106">構文</span><span class="sxs-lookup"><span data-stu-id="70730-106">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="70730-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70730-107">Parameters</span></span>

<span data-ttu-id="70730-108">`MinRange` ([System.object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="70730-108">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="70730-109">許容される最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="70730-109">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="70730-110">`MaxRange` ([System.object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="70730-110">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="70730-111">許容される最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="70730-111">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="70730-112">解説</span><span class="sxs-lookup"><span data-stu-id="70730-112">Remarks</span></span>

- <span data-ttu-id="70730-113">パラメーターの値 `MinRange` がパラメーターの値よりも大きい場合、Windows PowerShell ランタイムは構築エラーをスローし `MaxRange` ます。</span><span class="sxs-lookup"><span data-stu-id="70730-113">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="70730-114">Windows PowerShell ランタイムは、次の条件下で検証エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="70730-114">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="70730-115">引数の値が制限よりも小さいか、または制限を超えている場合 `MinRange` `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="70730-115">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="70730-116">引数がおよびパラメーターと同じ型ではない場合 `MinRange` `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="70730-116">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="70730-117">ValidateRange 属性は、system.servicemodel [属性](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="70730-117">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="70730-118">参照</span><span class="sxs-lookup"><span data-stu-id="70730-118">See Also</span></span>

[<span data-ttu-id="70730-119">System. Automation. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="70730-119">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="70730-120">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="70730-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
