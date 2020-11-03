---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/publish-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-DscConfiguration
ms.openlocfilehash: 139de2bfdb88c443e7bc48d36e37e95644556bf5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215304"
---
# <span data-ttu-id="418fc-103">Publish-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="418fc-103">Publish-DscConfiguration</span></span>

## <span data-ttu-id="418fc-104">概要</span><span class="sxs-lookup"><span data-stu-id="418fc-104">SYNOPSIS</span></span>
<span data-ttu-id="418fc-105">一連のコンピューターに DSC 構成を発行します。</span><span class="sxs-lookup"><span data-stu-id="418fc-105">Publishes a DSC configuration to a set of computers.</span></span>

## <span data-ttu-id="418fc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="418fc-106">SYNTAX</span></span>

### <span data-ttu-id="418fc-107">ComputerNameSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="418fc-107">ComputerNameSet (Default)</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="418fc-108">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="418fc-108">CimSessionSet</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="418fc-109">Description</span><span class="sxs-lookup"><span data-stu-id="418fc-109">DESCRIPTION</span></span>
<span data-ttu-id="418fc-110">**Start-dscconfiguration** コマンドレットは、Windows PowerShell Desired State CONFIGURATION (DSC) 構成ドキュメントを一連のコンピューターで発行します。</span><span class="sxs-lookup"><span data-stu-id="418fc-110">The **Publish-DscConfiguration** cmdlet publishes a Windows PowerShell Desired State Configuration (DSC) configuration document on set of computers.</span></span>
<span data-ttu-id="418fc-111">このコマンドレットでは、構成は適用されません。</span><span class="sxs-lookup"><span data-stu-id="418fc-111">This cmdlet does not apply the configuration.</span></span>
<span data-ttu-id="418fc-112">構成は、 *Useexisting* パラメーターと共に使用される場合、または DSC エンジンが整合性サイクルを実行する場合に、Start-DscConfiguration コマンドレットによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="418fc-112">Configurations are applied by either the Start-DscConfiguration cmdlet when it is used with the *UseExisting* parameter or when the DSC engine runs its consistency cycle.</span></span>
<span data-ttu-id="418fc-113">DSC エンジンは、ローカル Configuration Manager (LCM) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="418fc-113">The DSC engine is also known as the Local Configuration Manager (LCM).</span></span>

<span data-ttu-id="418fc-114">このコマンドレットは、複数の構成ドキュメントのフラグメントが配信される場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="418fc-114">This cmdlet is especially useful when fragments of multiple configuration documents are delivered.</span></span>
<span data-ttu-id="418fc-115">複数の構成ドキュメントフラグメントが配信されると、古い構成ドキュメントフラグメントが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="418fc-115">When multiple configuration documents fragments are delivered, they overwrite the older configuration document fragments.</span></span>

## <span data-ttu-id="418fc-116">例</span><span class="sxs-lookup"><span data-stu-id="418fc-116">EXAMPLES</span></span>

### <span data-ttu-id="418fc-117">例 1: リモートコンピューターに構成を発行する</span><span class="sxs-lookup"><span data-stu-id="418fc-117">Example 1: Publish a configuration to a remote computer</span></span>

```
PS C:\> Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

<span data-ttu-id="418fc-118">このコマンドは、構成をリモートコンピューターに発行します。</span><span class="sxs-lookup"><span data-stu-id="418fc-118">This command publishes a configuration to a remote computer.</span></span>
<span data-ttu-id="418fc-119">コマンドレットを実行するユーザーは、リモートコンピューターの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="418fc-119">The user who runs the cmdlet should be administrator on the remote computer.</span></span>

## <span data-ttu-id="418fc-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="418fc-120">PARAMETERS</span></span>

### <span data-ttu-id="418fc-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="418fc-121">-CimSession</span></span>
<span data-ttu-id="418fc-122">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="418fc-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="418fc-123">コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="418fc-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="418fc-124">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="418fc-124">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="418fc-125">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="418fc-125">-ComputerName</span></span>
<span data-ttu-id="418fc-126">このコマンドレットが構成を発行する1つまたは複数のコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="418fc-126">Specifies one or more computers on which this cmdlet publishes the configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="418fc-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="418fc-127">-Credential</span></span>
<span data-ttu-id="418fc-128">ターゲットデバイスへのアクセスに使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="418fc-128">Specifies credentials that are used to access the target device.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="418fc-129">-Force</span><span class="sxs-lookup"><span data-stu-id="418fc-129">-Force</span></span>
<span data-ttu-id="418fc-130">コマンドレットを強制的に終了します。</span><span class="sxs-lookup"><span data-stu-id="418fc-130">Forces the cmdlet to finish.</span></span>
<span data-ttu-id="418fc-131">ローカルの Configuration Manager 更新モードが PULL に設定されている場合、このパラメーターを使用すると、このパラメーターをプッシュして、DSC 構成の発行を有効にするように変更されます。</span><span class="sxs-lookup"><span data-stu-id="418fc-131">If the Local Configuration Manager refresh mode is set to PULL, usage of this parameter changes it to PUSH and enables publication of the DSC configuration.</span></span>
<span data-ttu-id="418fc-132">また、保留中の DSC 構成が存在する場合、このパラメーターを使用すると、保留中の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="418fc-132">Also, if a pending DSC configuration exists, usage of this parameter overwrites that pending configuration.</span></span>

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

### <span data-ttu-id="418fc-133">-Path</span><span class="sxs-lookup"><span data-stu-id="418fc-133">-Path</span></span>
<span data-ttu-id="418fc-134">対象のコンピューターに発行する構成を含むパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="418fc-134">Specifies a path that contains configurations to publish to target computers.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="418fc-135">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="418fc-135">-ThrottleLimit</span></span>
<span data-ttu-id="418fc-136">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="418fc-136">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="418fc-137">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="418fc-137">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="418fc-138">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="418fc-138">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="418fc-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="418fc-139">-Confirm</span></span>
<span data-ttu-id="418fc-140">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="418fc-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="418fc-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="418fc-141">-WhatIf</span></span>
<span data-ttu-id="418fc-142">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="418fc-142">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="418fc-143">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="418fc-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="418fc-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="418fc-144">CommonParameters</span></span>
<span data-ttu-id="418fc-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="418fc-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="418fc-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="418fc-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="418fc-147">入力</span><span class="sxs-lookup"><span data-stu-id="418fc-147">INPUTS</span></span>

## <span data-ttu-id="418fc-148">出力</span><span class="sxs-lookup"><span data-stu-id="418fc-148">OUTPUTS</span></span>

## <span data-ttu-id="418fc-149">注</span><span class="sxs-lookup"><span data-stu-id="418fc-149">NOTES</span></span>

## <span data-ttu-id="418fc-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="418fc-150">RELATED LINKS</span></span>

[<span data-ttu-id="418fc-151">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="418fc-151">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="418fc-152">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="418fc-152">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="418fc-153">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="418fc-153">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="418fc-154">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="418fc-154">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="418fc-155">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="418fc-155">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="418fc-156">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="418fc-156">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
