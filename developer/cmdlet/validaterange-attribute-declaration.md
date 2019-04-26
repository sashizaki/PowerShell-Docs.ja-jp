---
title: ValidateRange 属性の宣言 |Microsoft Docs
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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067112"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="2a0c8-102">ValidateRange 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="2a0c8-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="2a0c8-103">ValidateRange 属性には、コマンドレット パラメーターの引数の最小値と最大値 (範囲) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="2a0c8-104">この属性は、Windows PowerShell 関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a0c8-105">構文</span><span class="sxs-lookup"><span data-stu-id="2a0c8-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="2a0c8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a0c8-106">Parameters</span></span>

<span data-ttu-id="2a0c8-107">`MinRange` ([System.Object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="2a0c8-108">許容される最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="2a0c8-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="2a0c8-110">許容される最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a0c8-111">コメント</span><span class="sxs-lookup"><span data-stu-id="2a0c8-111">Remarks</span></span>

- <span data-ttu-id="2a0c8-112">Windows PowerShell ランタイム構築エラーをスローするときの値、`MinRange`パラメーターがの値より大きい、`MaxRange`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="2a0c8-113">Windows PowerShell ランタイムには、次の条件で検証エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

    - <span data-ttu-id="2a0c8-114">引数の値がより小さい`MinRange`制限より大きいか、`MaxRange`制限します。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

    - <span data-ttu-id="2a0c8-115">同じ型の引数がありませんが、`MinRange`と`MaxRange`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="2a0c8-116">ValidateRange 属性を定義した、 [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="2a0c8-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a0c8-117">参照</span><span class="sxs-lookup"><span data-stu-id="2a0c8-117">See Also</span></span>

[<span data-ttu-id="2a0c8-118">System.Management.Automation.Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="2a0c8-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="2a0c8-119">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="2a0c8-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
