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
ms.openlocfilehash: 560fa105ac3f93ae6334df0112f5290dfa20576c
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692009"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="e6b6f-102">ValidateRange 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="e6b6f-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="e6b6f-103">ValidateRange 属性は、コマンドレットパラメーター引数の最小値と最大値 (範囲) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="e6b6f-104">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6b6f-105">構文</span><span class="sxs-lookup"><span data-stu-id="e6b6f-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="e6b6f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6b6f-106">Parameters</span></span>

<span data-ttu-id="e6b6f-107">`MinRange`([System.object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="e6b6f-108">許容される最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="e6b6f-109">`MaxRange`([System.object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="e6b6f-110">許容される最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6b6f-111">解説</span><span class="sxs-lookup"><span data-stu-id="e6b6f-111">Remarks</span></span>

- <span data-ttu-id="e6b6f-112">パラメーターの値 `MinRange` がパラメーターの値よりも大きい場合、Windows PowerShell ランタイムは構築エラーをスローし `MaxRange` ます。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="e6b6f-113">Windows PowerShell ランタイムは、次の条件下で検証エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="e6b6f-114">引数の値が制限よりも小さいか、または制限を超えている場合 `MinRange` `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="e6b6f-115">引数がおよびパラメーターと同じ型ではない場合 `MinRange` `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="e6b6f-116">ValidateRange 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="e6b6f-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6b6f-117">参照</span><span class="sxs-lookup"><span data-stu-id="e6b6f-117">See Also</span></span>

[<span data-ttu-id="e6b6f-118">System. Automation. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="e6b6f-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="e6b6f-119">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="e6b6f-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
