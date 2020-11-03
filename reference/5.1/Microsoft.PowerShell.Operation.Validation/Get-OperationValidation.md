---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/get-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OperationValidation
ms.openlocfilehash: 22ff12848fb7aefaa7f684ee5d8723cc723a5879
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214288"
---
# <span data-ttu-id="289d5-103">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="289d5-103">Get-OperationValidation</span></span>

## <span data-ttu-id="289d5-104">概要</span><span class="sxs-lookup"><span data-stu-id="289d5-104">SYNOPSIS</span></span>
<span data-ttu-id="289d5-105">操作検証フレームワークテストを取得します。</span><span class="sxs-lookup"><span data-stu-id="289d5-105">Gets Operation Validation Framework tests.</span></span>

## <span data-ttu-id="289d5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="289d5-106">SYNTAX</span></span>

```
Get-OperationValidation [[-ModuleName] <String[]>] [-TestType <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="289d5-107">Description</span><span class="sxs-lookup"><span data-stu-id="289d5-107">DESCRIPTION</span></span>
<span data-ttu-id="289d5-108">**Get operationvalidation** コマンドレットは、インストールされているモジュールの操作検証フレームワークテストを取得します。</span><span class="sxs-lookup"><span data-stu-id="289d5-108">The **Get-OperationValidation** cmdlet gets Operation Validation Framework tests for installed modules.</span></span>

<span data-ttu-id="289d5-109">診断フォルダーを含むモジュールは、Simple または包括的なサブフォルダー、またはその両方で、Pester テストが検査されます。</span><span class="sxs-lookup"><span data-stu-id="289d5-109">Modules that include a Diagnostics folder are inspected for Pester tests in the Simple or Comprehensive subfolder, or both.</span></span>

## <span data-ttu-id="289d5-110">例</span><span class="sxs-lookup"><span data-stu-id="289d5-110">EXAMPLES</span></span>

### <span data-ttu-id="289d5-111">例 1: 操作検証テストを取得する</span><span class="sxs-lookup"><span data-stu-id="289d5-111">Example 1: Get Operation Validation tests</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "C:\temp\modules\AddNumbers"
    Type:     Simple
    File:     addnum.tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Simple\addnum.tests.ps1
    Name:
        Add-Em
        Subtract em
        Add-Numbers
    Type:     Comprehensive
    File:     Comp.Adding.Tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Comprehensive\Comp.Adding.Tests.ps1
    Name:
        Comprehensive Adding Tests
        Comprehensive Subtracting Tests
        Comprehensive Examples
```

<span data-ttu-id="289d5-112">このコマンドは、C:\temp\modules フォルダー内の AddNumbers という名前のモジュールから検証テストを取得します。</span><span class="sxs-lookup"><span data-stu-id="289d5-112">This command gets validation tests from the module named AddNumbers in the C:\temp\modules folder.</span></span>

## <span data-ttu-id="289d5-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="289d5-113">PARAMETERS</span></span>

### <span data-ttu-id="289d5-114">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="289d5-114">-ModuleName</span></span>
<span data-ttu-id="289d5-115">モジュールの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="289d5-115">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="289d5-116">-TestType</span><span class="sxs-lookup"><span data-stu-id="289d5-116">-TestType</span></span>
<span data-ttu-id="289d5-117">テストの種類の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="289d5-117">Specifies an array of test types.</span></span>
<span data-ttu-id="289d5-118">有効な値は、Simple、包括的、または both です。</span><span class="sxs-lookup"><span data-stu-id="289d5-118">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="289d5-119">既定値は "Simple, 包括的" です。</span><span class="sxs-lookup"><span data-stu-id="289d5-119">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="289d5-120">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="289d5-120">CommonParameters</span></span>
<span data-ttu-id="289d5-121">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="289d5-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="289d5-122">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="289d5-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="289d5-123">入力</span><span class="sxs-lookup"><span data-stu-id="289d5-123">INPUTS</span></span>

### <span data-ttu-id="289d5-124">なし</span><span class="sxs-lookup"><span data-stu-id="289d5-124">None</span></span>
<span data-ttu-id="289d5-125">このコマンドレットに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="289d5-125">You cannot pipe any input to this cmdlet.</span></span>

## <span data-ttu-id="289d5-126">出力</span><span class="sxs-lookup"><span data-stu-id="289d5-126">OUTPUTS</span></span>

### <span data-ttu-id="289d5-127">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="289d5-127">PSCustomObject</span></span>
<span data-ttu-id="289d5-128">**Pscustomobject** 検証について説明します。</span><span class="sxs-lookup"><span data-stu-id="289d5-128">The **PSCustomObject** describes the validation.</span></span>

## <span data-ttu-id="289d5-129">注</span><span class="sxs-lookup"><span data-stu-id="289d5-129">NOTES</span></span>

## <span data-ttu-id="289d5-130">関連リンク</span><span class="sxs-lookup"><span data-stu-id="289d5-130">RELATED LINKS</span></span>

[<span data-ttu-id="289d5-131">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="289d5-131">Invoke-OperationValidation</span></span>](Invoke-OperationValidation.md)
