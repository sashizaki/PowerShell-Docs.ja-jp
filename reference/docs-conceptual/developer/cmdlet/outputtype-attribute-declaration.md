---
title: OutputType 属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97a98ee-ffc0-42f0-a9a6-b0717b39c798
caps.latest.revision: 5
ms.openlocfilehash: 7aa6fa407e509a31c4066c4f73ae01b02b2f338c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365341"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="3e4a1-102">OutputType 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="3e4a1-102">OutputType Attribute Declaration</span></span>

<span data-ttu-id="3e4a1-103">@No__t-0 属性は、コマンドレット、関数、またはスクリプトによって返される .NET Framework 型を識別します。</span><span class="sxs-lookup"><span data-stu-id="3e4a1-103">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e4a1-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e4a1-104">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="3e4a1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e4a1-105">Parameters</span></span>

<span data-ttu-id="3e4a1-106">型 (`string[]` または `Type[]`) が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e4a1-106">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="3e4a1-107">コマンドレット関数またはスクリプトによって返される型を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e4a1-107">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="3e4a1-108">ParameterSetName (string []) 省略可能。</span><span class="sxs-lookup"><span data-stu-id="3e4a1-108">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="3e4a1-109">@No__t-0 パラメーターで指定された型を返すパラメーターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e4a1-109">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="3e4a1-110">providerCmdlet オプション。</span><span class="sxs-lookup"><span data-stu-id="3e4a1-110">providerCmdlet Optional.</span></span> <span data-ttu-id="3e4a1-111">@No__t-0 パラメーターに指定された型を返すプロバイダーコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e4a1-111">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e4a1-112">参照</span><span class="sxs-lookup"><span data-stu-id="3e4a1-112">See Also</span></span>

[<span data-ttu-id="3e4a1-113">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="3e4a1-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)