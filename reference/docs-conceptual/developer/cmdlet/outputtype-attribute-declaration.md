---
ms.date: 09/13/2016
ms.topic: reference
title: OutputType 属性の宣言
description: OutputType 属性の宣言
ms.openlocfilehash: b5e33346e9ac29c13323781d62daffab892573a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646460"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="c0dc9-103">OutputType 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="c0dc9-103">OutputType Attribute Declaration</span></span>

<span data-ttu-id="c0dc9-104">属性は、 `OutputType` コマンドレット、関数、またはスクリプトによって返される .NET Framework 型を識別します。</span><span class="sxs-lookup"><span data-stu-id="c0dc9-104">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0dc9-105">構文</span><span class="sxs-lookup"><span data-stu-id="c0dc9-105">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="c0dc9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0dc9-106">Parameters</span></span>

<span data-ttu-id="c0dc9-107">型 ( `string[]` または `Type[]` ) が必要です。</span><span class="sxs-lookup"><span data-stu-id="c0dc9-107">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="c0dc9-108">コマンドレット関数またはスクリプトによって返される型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0dc9-108">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="c0dc9-109">ParameterSetName (string []) 省略可能。</span><span class="sxs-lookup"><span data-stu-id="c0dc9-109">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="c0dc9-110">パラメーターで指定した型を返すパラメーターセットを指定し `type` ます。</span><span class="sxs-lookup"><span data-stu-id="c0dc9-110">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="c0dc9-111">providerCmdlet オプション。</span><span class="sxs-lookup"><span data-stu-id="c0dc9-111">providerCmdlet Optional.</span></span> <span data-ttu-id="c0dc9-112">パラメーターで指定した型を返すプロバイダーコマンドレットを指定し `type` ます。</span><span class="sxs-lookup"><span data-stu-id="c0dc9-112">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0dc9-113">参照</span><span class="sxs-lookup"><span data-stu-id="c0dc9-113">See Also</span></span>

[<span data-ttu-id="c0dc9-114">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="c0dc9-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
