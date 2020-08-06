---
title: OutputType 属性の宣言 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a4cc874031bba092cfef6041bef0e19e6af3f09c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786545"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="bf9d0-102">OutputType 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="bf9d0-102">OutputType Attribute Declaration</span></span>

<span data-ttu-id="bf9d0-103">属性は、 `OutputType` コマンドレット、関数、またはスクリプトによって返される .NET Framework 型を識別します。</span><span class="sxs-lookup"><span data-stu-id="bf9d0-103">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf9d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="bf9d0-104">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="bf9d0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf9d0-105">Parameters</span></span>

<span data-ttu-id="bf9d0-106">型 ( `string[]` または `Type[]` ) が必要です。</span><span class="sxs-lookup"><span data-stu-id="bf9d0-106">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="bf9d0-107">コマンドレット関数またはスクリプトによって返される型を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf9d0-107">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="bf9d0-108">ParameterSetName (string []) 省略可能。</span><span class="sxs-lookup"><span data-stu-id="bf9d0-108">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="bf9d0-109">パラメーターで指定した型を返すパラメーターセットを指定し `type` ます。</span><span class="sxs-lookup"><span data-stu-id="bf9d0-109">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="bf9d0-110">providerCmdlet オプション。</span><span class="sxs-lookup"><span data-stu-id="bf9d0-110">providerCmdlet Optional.</span></span> <span data-ttu-id="bf9d0-111">パラメーターで指定した型を返すプロバイダーコマンドレットを指定し `type` ます。</span><span class="sxs-lookup"><span data-stu-id="bf9d0-111">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf9d0-112">参照</span><span class="sxs-lookup"><span data-stu-id="bf9d0-112">See Also</span></span>

[<span data-ttu-id="bf9d0-113">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="bf9d0-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
