---
title: Alias 属性宣言 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.openlocfilehash: 4c1ff34a244611173ca919a44d6598189b19dc98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782414"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="0a5a1-102">エイリアス属性の宣言</span><span class="sxs-lookup"><span data-stu-id="0a5a1-102">Alias Attribute Declaration</span></span>

<span data-ttu-id="0a5a1-103">Alias 属性を使用すると、ユーザーはコマンドレットパラメーターに別の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-103">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="0a5a1-104">エイリアスを使用してパラメーター名のショートカットを指定することも、さまざまなシナリオに適した異なる名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-104">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="0a5a1-105">構文</span><span class="sxs-lookup"><span data-stu-id="0a5a1-105">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="0a5a1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a5a1-106">Parameters</span></span>

<span data-ttu-id="0a5a1-107">`aliasName`(文字列 [])必須。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-107">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="0a5a1-108">コマンドレットパラメーターのコンマ区切りのエイリアス名のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-108">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a5a1-109">解説</span><span class="sxs-lookup"><span data-stu-id="0a5a1-109">Remarks</span></span>

- <span data-ttu-id="0a5a1-110">Alias 属性は、コマンドレットパラメーターを指定するときに、Parameter 属性と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-110">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="0a5a1-111">これらの属性を宣言する方法の詳細については、「[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-111">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="0a5a1-112">各エイリアス名は、コマンドレット内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-112">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="0a5a1-113">Windows PowerShell では、重複するエイリアス名は確認されません。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-113">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="0a5a1-114">Alias 属性は、コマンドレットのパラメーターごとに1回使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-114">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="0a5a1-115">Alias 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.AliasAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0a5a1-115">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a5a1-116">参照</span><span class="sxs-lookup"><span data-stu-id="0a5a1-116">See Also</span></span>

[<span data-ttu-id="0a5a1-117">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="0a5a1-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="0a5a1-118">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="0a5a1-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
