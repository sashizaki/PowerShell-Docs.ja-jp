---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/invoke-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-OperationValidation
ms.openlocfilehash: 6c9d4001392de48032a0fe1ba3667db90ea614fc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214283"
---
# <span data-ttu-id="be04f-103">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="be04f-103">Invoke-OperationValidation</span></span>

## <span data-ttu-id="be04f-104">概要</span><span class="sxs-lookup"><span data-stu-id="be04f-104">SYNOPSIS</span></span>

<span data-ttu-id="be04f-105">操作検証フレームワークテストを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be04f-105">Invokes Operation Validation Framework tests.</span></span>

## <span data-ttu-id="be04f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="be04f-106">SYNTAX</span></span>

### <span data-ttu-id="be04f-107">FileAndTest (既定値)</span><span class="sxs-lookup"><span data-stu-id="be04f-107">FileAndTest (Default)</span></span>

```
Invoke-OperationValidation [-TestInfo <PSObject[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="be04f-108">Path</span><span class="sxs-lookup"><span data-stu-id="be04f-108">Path</span></span>

```
Invoke-OperationValidation [-testFilePath <String[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="be04f-109">UseGetOperationTest</span><span class="sxs-lookup"><span data-stu-id="be04f-109">UseGetOperationTest</span></span>

```
Invoke-OperationValidation [-ModuleName <String[]>] [-TestType <String[]>] [-IncludePesterOutput] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="be04f-110">Description</span><span class="sxs-lookup"><span data-stu-id="be04f-110">DESCRIPTION</span></span>

<span data-ttu-id="be04f-111">**呼び出し operationvalidation** コマンドレットは、指定されたモジュールの操作検証フレームワークテストを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be04f-111">The **Invoke-OperationValidation** cmdlet invokes Operation Validation Framework tests for a specified module.</span></span>

## <span data-ttu-id="be04f-112">例</span><span class="sxs-lookup"><span data-stu-id="be04f-112">EXAMPLES</span></span>

### <span data-ttu-id="be04f-113">例 1: 操作検証テストを呼び出す</span><span class="sxs-lookup"><span data-stu-id="be04f-113">Example 1: Invoke an Operation Validation test</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "OperationValidation" | Invoke-OperationValidation -IncludePesterOutput
Describing Simple Test Suite
 [+] first Operational test 20ms
 [+] second Operational test 19ms
 [+] third Operational test 9ms
Tests completed in 48ms
Passed: 3 Failed: 0 Skipped: 0 Pending: 0
Describing Scenario targeted tests
   Context The RemoteAccess service
    [+] The service is running 37ms
   Context The Firewall Rules
    [+] A rule for TCP port 3389 is enabled 1.19s
    [+] A rule for UDP port 3389 is enabled 11ms
Tests completed in 1.24s
Passed: 3 Failed: 0 Skipped: 0 Pending: 0




   Module: OperationValidation




Result  Name
------- --------
Passed  Simple Test Suite::first Operational test
Passed  Simple Test Suite::second Operational test
Passed  Simple Test Suite::third Operational test
Passed  Scenario targeted tests:The RemoteAccess service:The service is running
Passed  Scenario targeted tests:The Firewall Rules:A rule for TCP port 3389 is enabled
Passed  Scenario targeted tests:The Firewall Rules:A rule for UDP port 3389 is enabled
```

<span data-ttu-id="be04f-114">このコマンドは、OperationValidation という名前のモジュールを取得し、パイプライン演算子を使用して、テストを実行する **呼び出し operationvalidation** コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="be04f-114">This command gets the module named OperationValidation, and uses the pipeline operator to pass it to the **Invoke-OperationValidation** cmdlet, which runs the test.</span></span>

## <span data-ttu-id="be04f-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="be04f-115">PARAMETERS</span></span>

### <span data-ttu-id="be04f-116">-IncludePesterOutput</span><span class="sxs-lookup"><span data-stu-id="be04f-116">-IncludePesterOutput</span></span>

<span data-ttu-id="be04f-117">Pester テスト出力を含みます。</span><span class="sxs-lookup"><span data-stu-id="be04f-117">Includes Pester test output.</span></span>
<span data-ttu-id="be04f-118">既定値は $False です。</span><span class="sxs-lookup"><span data-stu-id="be04f-118">The default is $False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be04f-119">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="be04f-119">-ModuleName</span></span>

<span data-ttu-id="be04f-120">モジュールの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="be04f-120">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be04f-121">-testFilePath</span><span class="sxs-lookup"><span data-stu-id="be04f-121">-testFilePath</span></span>

<span data-ttu-id="be04f-122">操作検証フレームワークのテストファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="be04f-122">Specifies the path of an Operation Validation Framework test file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="be04f-123">-TestInfo</span><span class="sxs-lookup"><span data-stu-id="be04f-123">-TestInfo</span></span>

<span data-ttu-id="be04f-124">ファイルへのパスと実行するテストの名前を指定するカスタムオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="be04f-124">Specifies a custom object that specifies the path to the file and the name of the test to run.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: FileAndTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="be04f-125">-TestType</span><span class="sxs-lookup"><span data-stu-id="be04f-125">-TestType</span></span>

<span data-ttu-id="be04f-126">テストの種類の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="be04f-126">Specifies an array of test types.</span></span>
<span data-ttu-id="be04f-127">有効な値は、Simple、包括的、または both です。</span><span class="sxs-lookup"><span data-stu-id="be04f-127">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="be04f-128">既定値は "Simple, 包括的" です。</span><span class="sxs-lookup"><span data-stu-id="be04f-128">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be04f-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="be04f-129">-Confirm</span></span>

<span data-ttu-id="be04f-130">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be04f-130">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be04f-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="be04f-131">-WhatIf</span></span>

<span data-ttu-id="be04f-132">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="be04f-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="be04f-133">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="be04f-133">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="be04f-134">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="be04f-134">CommonParameters</span></span>
<span data-ttu-id="be04f-135">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="be04f-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="be04f-136">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be04f-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="be04f-137">入力</span><span class="sxs-lookup"><span data-stu-id="be04f-137">INPUTS</span></span>

### <span data-ttu-id="be04f-138">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="be04f-138">PSCustomObject</span></span>

<span data-ttu-id="be04f-139">パイプを使用して、 **Get OperationValidation** の出力をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="be04f-139">You can pipe the output of **Get-OperationValidation** to this cmdlet.</span></span>

## <span data-ttu-id="be04f-140">出力</span><span class="sxs-lookup"><span data-stu-id="be04f-140">OUTPUTS</span></span>

### <span data-ttu-id="be04f-141">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="be04f-141">PSCustomObject</span></span>

<span data-ttu-id="be04f-142">**Pscustomobject** 、検証が成功したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="be04f-142">The **PSCustomObject** describes whether the validation was successful.</span></span>

## <span data-ttu-id="be04f-143">注</span><span class="sxs-lookup"><span data-stu-id="be04f-143">NOTES</span></span>

## <span data-ttu-id="be04f-144">関連リンク</span><span class="sxs-lookup"><span data-stu-id="be04f-144">RELATED LINKS</span></span>

[<span data-ttu-id="be04f-145">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="be04f-145">Get-OperationValidation</span></span>](Get-OperationValidation.md)
