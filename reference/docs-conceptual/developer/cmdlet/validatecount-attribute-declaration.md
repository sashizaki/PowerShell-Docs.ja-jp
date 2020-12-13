---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateCount 属性の宣言
description: ValidateCount 属性の宣言
ms.openlocfilehash: 6acdd02a10ecc1bc2be0e6be88cf2f42a3673eb8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646264"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="58d18-103">ValidateCount 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="58d18-103">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="58d18-104">ValidateCount 属性では、コマンドレットパラメーターに許可される引数の最小数と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="58d18-104">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="58d18-105">構文</span><span class="sxs-lookup"><span data-stu-id="58d18-105">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="58d18-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58d18-106">Parameters</span></span>

<span data-ttu-id="58d18-107">`MinLength` ([System.string][]) が必要です。</span><span class="sxs-lookup"><span data-stu-id="58d18-107">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="58d18-108">引数の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="58d18-108">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="58d18-109">`MaxLength`([System.string][]) が必要です。</span><span class="sxs-lookup"><span data-stu-id="58d18-109">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="58d18-110">引数の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="58d18-110">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="58d18-111">解説</span><span class="sxs-lookup"><span data-stu-id="58d18-111">Remarks</span></span>

- <span data-ttu-id="58d18-112">この属性を宣言する方法の詳細については、「 [引数カウントを検証する方法][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58d18-112">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="58d18-113">この属性が呼び出されない場合、対応するコマンドレットパラメーターには任意の数の引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="58d18-113">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="58d18-114">Windows PowerShell ランタイムは、次の状況でエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="58d18-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="58d18-115">`MinLength`属性と `MaxLength` 属性のパラメーターが、system.string [][]型ではありません。</span><span class="sxs-lookup"><span data-stu-id="58d18-115">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="58d18-116">属性パラメーターの値 `MaxLength` が、属性パラメーターの値未満です `MinLength` 。</span><span class="sxs-lookup"><span data-stu-id="58d18-116">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="58d18-117">ValidateCount 属性は、 [system.string クラスに][] よって定義されています。</span><span class="sxs-lookup"><span data-stu-id="58d18-117">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="58d18-118">参照</span><span class="sxs-lookup"><span data-stu-id="58d18-118">See Also</span></span>

<span data-ttu-id="58d18-119">[System. Automation. ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="58d18-119">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="58d18-120">[引数カウントを検証する方法][]</span><span class="sxs-lookup"><span data-stu-id="58d18-120">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="58d18-121">[Windows PowerShell コマンドレットの記述][]</span><span class="sxs-lookup"><span data-stu-id="58d18-121">[Writing a Windows PowerShell Cmdlet][]</span></span>

[引数カウントを検証する方法]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Windows PowerShell コマンドレットの記述]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
