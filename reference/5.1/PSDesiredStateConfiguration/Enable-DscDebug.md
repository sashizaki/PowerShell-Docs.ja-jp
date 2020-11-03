---
external help file: Enable-DscDebug.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/enable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-DscDebug
ms.openlocfilehash: 136481c5a1945c3d5cbd1ca7fc8ce5f580c39b0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215360"
---
# <span data-ttu-id="884ec-103">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="884ec-103">Enable-DscDebug</span></span>

## <span data-ttu-id="884ec-104">概要</span><span class="sxs-lookup"><span data-stu-id="884ec-104">SYNOPSIS</span></span>
<span data-ttu-id="884ec-105">すべての DSC リソースのデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="884ec-105">Starts debugging of all DSC resources.</span></span>

## <span data-ttu-id="884ec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="884ec-106">SYNTAX</span></span>

```
Enable-DscDebug [-BreakAll] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="884ec-107">Description</span><span class="sxs-lookup"><span data-stu-id="884ec-107">DESCRIPTION</span></span>
<span data-ttu-id="884ec-108">**DscDebug** コマンドレットは、dsc エンジンによる Windows PowerShell Desired State CONFIGURATION (dsc) リソースのデバッグを有効にします。これは、ローカル CONFIGURATION MANAGER (LCM) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="884ec-108">The **Enable-DscDebug** cmdlet enables Windows PowerShell Desired State Configuration (DSC) resource debugging by the DSC engine, which is also known as the Local Configuration Manager (LCM).</span></span>
<span data-ttu-id="884ec-109">既定では、すべてのリソースインスタンスがデバッガーに分割されます。</span><span class="sxs-lookup"><span data-stu-id="884ec-109">By default, all resource instances break into the debugger.</span></span>

## <span data-ttu-id="884ec-110">例</span><span class="sxs-lookup"><span data-stu-id="884ec-110">EXAMPLES</span></span>

### <span data-ttu-id="884ec-111">例 1: デバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="884ec-111">Example 1: Start debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll
```

<span data-ttu-id="884ec-112">このコマンドは、リソースのデバッグを開始するよう DSC エンジンまたは LCM に指示します。</span><span class="sxs-lookup"><span data-stu-id="884ec-112">This command indicates to the DSC engine or LCM to start resource debugging.</span></span>
<span data-ttu-id="884ec-113">次に構成を実行すると、プロセスがデバッガーに入ります。</span><span class="sxs-lookup"><span data-stu-id="884ec-113">The next time the configuration is run, the process enters the debugger.</span></span>

### <span data-ttu-id="884ec-114">例 2: リモートデバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="884ec-114">Example 2: Start remote debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll -CimSession DeploymentServer
```

<span data-ttu-id="884ec-115">このコマンドは、リモートコンピューターの DSC エンジンに対し、リソースのデバッグを開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="884ec-115">This command indicates to the DSC engine of the remote computer to start resource debugging.</span></span>

## <span data-ttu-id="884ec-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="884ec-116">PARAMETERS</span></span>

### <span data-ttu-id="884ec-117">-AsJob</span><span class="sxs-lookup"><span data-stu-id="884ec-117">-AsJob</span></span>
<span data-ttu-id="884ec-118">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="884ec-118">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="884ec-119">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="884ec-119">-BreakAll</span></span>
<span data-ttu-id="884ec-120">構成の実行時にすべてのリソースがデバッガーに入ることを示します。</span><span class="sxs-lookup"><span data-stu-id="884ec-120">Indicates that all resources enter the debugger when a configuration runs.</span></span>

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

### <span data-ttu-id="884ec-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="884ec-121">-CimSession</span></span>
<span data-ttu-id="884ec-122">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="884ec-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="884ec-123">コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="884ec-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="884ec-124">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="884ec-124">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="884ec-125">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="884ec-125">-ThrottleLimit</span></span>
<span data-ttu-id="884ec-126">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="884ec-126">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="884ec-127">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="884ec-127">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="884ec-128">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="884ec-128">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="884ec-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="884ec-129">-Confirm</span></span>
<span data-ttu-id="884ec-130">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="884ec-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="884ec-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="884ec-131">-WhatIf</span></span>
<span data-ttu-id="884ec-132">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="884ec-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="884ec-133">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="884ec-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="884ec-134">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="884ec-134">CommonParameters</span></span>
<span data-ttu-id="884ec-135">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="884ec-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="884ec-136">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="884ec-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="884ec-137">入力</span><span class="sxs-lookup"><span data-stu-id="884ec-137">INPUTS</span></span>

## <span data-ttu-id="884ec-138">出力</span><span class="sxs-lookup"><span data-stu-id="884ec-138">OUTPUTS</span></span>

## <span data-ttu-id="884ec-139">注</span><span class="sxs-lookup"><span data-stu-id="884ec-139">NOTES</span></span>

## <span data-ttu-id="884ec-140">関連リンク</span><span class="sxs-lookup"><span data-stu-id="884ec-140">RELATED LINKS</span></span>

[<span data-ttu-id="884ec-141">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="884ec-141">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="884ec-142">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="884ec-142">Disable-DscDebug</span></span>](Disable-DscDebug.md)

[<span data-ttu-id="884ec-143">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="884ec-143">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="884ec-144">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="884ec-144">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="884ec-145">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="884ec-145">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="884ec-146">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="884ec-146">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="884ec-147">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="884ec-147">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
