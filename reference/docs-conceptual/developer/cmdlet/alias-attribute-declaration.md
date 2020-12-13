---
ms.date: 09/13/2016
ms.topic: reference
title: エイリアス属性の宣言
description: エイリアス属性の宣言
ms.openlocfilehash: f2fe49578da2c795643b1f80fa44deefe1dbff09
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668305"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="97e36-103">エイリアス属性の宣言</span><span class="sxs-lookup"><span data-stu-id="97e36-103">Alias Attribute Declaration</span></span>

<span data-ttu-id="97e36-104">Alias 属性を使用すると、ユーザーはコマンドレットパラメーターに別の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="97e36-104">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="97e36-105">エイリアスを使用してパラメーター名のショートカットを指定することも、さまざまなシナリオに適した異なる名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="97e36-105">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="97e36-106">構文</span><span class="sxs-lookup"><span data-stu-id="97e36-106">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="97e36-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="97e36-107">Parameters</span></span>

<span data-ttu-id="97e36-108">`aliasName` (文字列 [])必須。</span><span class="sxs-lookup"><span data-stu-id="97e36-108">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="97e36-109">コマンドレットパラメーターのコンマ区切りのエイリアス名のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="97e36-109">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="97e36-110">解説</span><span class="sxs-lookup"><span data-stu-id="97e36-110">Remarks</span></span>

- <span data-ttu-id="97e36-111">Alias 属性は、コマンドレットパラメーターを指定するときに、Parameter 属性と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="97e36-111">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="97e36-112">これらの属性を宣言する方法の詳細については、「 [コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e36-112">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="97e36-113">各エイリアス名は、コマンドレット内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="97e36-113">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="97e36-114">Windows PowerShell では、重複するエイリアス名は確認されません。</span><span class="sxs-lookup"><span data-stu-id="97e36-114">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="97e36-115">Alias 属性は、コマンドレットのパラメーターごとに1回使用されます。</span><span class="sxs-lookup"><span data-stu-id="97e36-115">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="97e36-116">Alias 属性は、system.servicemodel [属性](/dotnet/api/System.Management.Automation.AliasAttribute) クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="97e36-116">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="97e36-117">参照</span><span class="sxs-lookup"><span data-stu-id="97e36-117">See Also</span></span>

[<span data-ttu-id="97e36-118">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="97e36-118">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="97e36-119">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="97e36-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
