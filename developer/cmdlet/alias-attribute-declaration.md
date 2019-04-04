---
title: エイリアス属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.assetid: d0df3a46-b1cc-42b9-beb1-e16bce254007
caps.latest.revision: 10
ms.openlocfilehash: 4d20672c5181c994c1b53624f6c42a301db11f26
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855048"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="c5c26-102">エイリアス属性の宣言</span><span class="sxs-lookup"><span data-stu-id="c5c26-102">Alias Attribute Declaration</span></span>

<span data-ttu-id="c5c26-103">Alias 属性は、コマンドレット パラメーターに異なる名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c5c26-103">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="c5c26-104">エイリアスは、パラメーター名のショートカットを提供するために使用できますか、さまざまなシナリオに適した別の名を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c5c26-104">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="c5c26-105">構文</span><span class="sxs-lookup"><span data-stu-id="c5c26-105">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="c5c26-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5c26-106">Parameters</span></span>

<span data-ttu-id="c5c26-107">`aliasName` (String[] など必須。</span><span class="sxs-lookup"><span data-stu-id="c5c26-107">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="c5c26-108">一連のコマンドレット パラメーターのコンマ区切りのエイリアス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5c26-108">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5c26-109">コメント</span><span class="sxs-lookup"><span data-stu-id="c5c26-109">Remarks</span></span>

- <span data-ttu-id="c5c26-110">Alias 属性は、コマンドレット パラメーターを指定すると、パラメーターの属性で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5c26-110">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="c5c26-111">これらの属性を宣言する方法の詳細については、[コマンドレット パラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5c26-111">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="c5c26-112">各エイリアス名をコマンドレット内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5c26-112">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="c5c26-113">Windows PowerShell は、重複するエイリアス名にはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="c5c26-113">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="c5c26-114">Alias 属性は、コマンドレットの各パラメーターの 1 回使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5c26-114">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="c5c26-115">Alias 属性は、 [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="c5c26-115">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5c26-116">参照</span><span class="sxs-lookup"><span data-stu-id="c5c26-116">See Also</span></span>

[<span data-ttu-id="c5c26-117">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="c5c26-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="c5c26-118">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c5c26-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
