---
external help file: Disable-DscDebug.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/disable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-DscDebug
ms.openlocfilehash: fdaba8358772f559a33117c796a923d774b009cb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215352"
---
# <span data-ttu-id="24fc1-103">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="24fc1-103">Disable-DscDebug</span></span>

## <span data-ttu-id="24fc1-104">概要</span><span class="sxs-lookup"><span data-stu-id="24fc1-104">SYNOPSIS</span></span>
<span data-ttu-id="24fc1-105">DSC リソースのデバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-105">Stops debugging of DSC resources.</span></span>

## <span data-ttu-id="24fc1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="24fc1-106">SYNTAX</span></span>

```
Disable-DscDebug [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="24fc1-107">Description</span><span class="sxs-lookup"><span data-stu-id="24fc1-107">DESCRIPTION</span></span>
<span data-ttu-id="24fc1-108">**Dscdebug DscDebug** コマンドレットは、Windows PowerShell Desired State CONFIGURATION (dsc) エンジンが dsc リソースのデバッグを停止することを要求します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-108">The **Disable-DscDebug** cmdlet requests that the Windows PowerShell Desired State Configuration (DSC) engine stop debugging of DSC resources.</span></span>
<span data-ttu-id="24fc1-109">このコマンドレットは、DSC エンジンが現在デバッグモードではない場合には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="24fc1-109">This cmdlet has no effect if the DSC engine is not currently in debugging mode.</span></span>

## <span data-ttu-id="24fc1-110">例</span><span class="sxs-lookup"><span data-stu-id="24fc1-110">EXAMPLES</span></span>

### <span data-ttu-id="24fc1-111">例 1: リソースのデバッグを停止する</span><span class="sxs-lookup"><span data-stu-id="24fc1-111">Example 1: Stop resource debugging</span></span>

```
PS C:\> Disable-DscDebug
```

<span data-ttu-id="24fc1-112">このコマンドは、ローカル Configuration Manager (LCM) の DSC エンジンに対して、リソースのデバッグを停止することを示します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-112">This command indicates to the DSC engine on the Local Configuration Manager (LCM) to stop resource debugging.</span></span>

### <span data-ttu-id="24fc1-113">例 2: エンジンの状態を確認し、デバッグを停止する</span><span class="sxs-lookup"><span data-stu-id="24fc1-113">Example 2: Check the engine state and stop debugging</span></span>

```
PS C:\> if((Get-DscLocalConfigurationManager).DebugMode -like '*Break*'){Disable-DscDebug}
```

<span data-ttu-id="24fc1-114">このコマンドは、DSC エンジンの状態を確認し、既にデバッグモードになっている場合にのみリソースのデバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-114">This command checks the DSC engine state, and stops resource debugging only if it is already in debugging mode</span></span>

## <span data-ttu-id="24fc1-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="24fc1-115">PARAMETERS</span></span>

### <span data-ttu-id="24fc1-116">-AsJob</span><span class="sxs-lookup"><span data-stu-id="24fc1-116">-AsJob</span></span>
<span data-ttu-id="24fc1-117">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-117">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="24fc1-118">-CimSession</span><span class="sxs-lookup"><span data-stu-id="24fc1-118">-CimSession</span></span>
<span data-ttu-id="24fc1-119">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-119">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="24fc1-120">コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-120">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="24fc1-121">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="24fc1-121">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="24fc1-122">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="24fc1-122">-ThrottleLimit</span></span>
<span data-ttu-id="24fc1-123">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-123">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="24fc1-124">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-124">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="24fc1-125">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="24fc1-125">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="24fc1-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="24fc1-126">-Confirm</span></span>
<span data-ttu-id="24fc1-127">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24fc1-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="24fc1-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="24fc1-128">-WhatIf</span></span>
<span data-ttu-id="24fc1-129">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="24fc1-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="24fc1-130">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="24fc1-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="24fc1-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="24fc1-131">CommonParameters</span></span>
<span data-ttu-id="24fc1-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="24fc1-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="24fc1-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24fc1-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="24fc1-134">入力</span><span class="sxs-lookup"><span data-stu-id="24fc1-134">INPUTS</span></span>

## <span data-ttu-id="24fc1-135">出力</span><span class="sxs-lookup"><span data-stu-id="24fc1-135">OUTPUTS</span></span>

## <span data-ttu-id="24fc1-136">注</span><span class="sxs-lookup"><span data-stu-id="24fc1-136">NOTES</span></span>

## <span data-ttu-id="24fc1-137">関連リンク</span><span class="sxs-lookup"><span data-stu-id="24fc1-137">RELATED LINKS</span></span>

[<span data-ttu-id="24fc1-138">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="24fc1-138">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="24fc1-139">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="24fc1-139">Enable-DscDebug</span></span>](Enable-DscDebug.md)

[<span data-ttu-id="24fc1-140">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="24fc1-140">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="24fc1-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="24fc1-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="24fc1-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="24fc1-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="24fc1-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="24fc1-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="24fc1-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="24fc1-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
