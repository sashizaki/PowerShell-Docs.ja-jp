---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/update-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DscConfiguration
ms.openlocfilehash: 13365902ab317a3daa41b9a951d5e2fa6e4f1b37
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213571"
---
# <span data-ttu-id="7c5c7-103">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c5c7-103">Update-DscConfiguration</span></span>

## <span data-ttu-id="7c5c7-104">概要</span><span class="sxs-lookup"><span data-stu-id="7c5c7-104">SYNOPSIS</span></span>
<span data-ttu-id="7c5c7-105">プルサーバーで更新された構成を確認し、適用します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-105">Checks the pull server for an updated configuration and applies it.</span></span>

## <span data-ttu-id="7c5c7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7c5c7-106">SYNTAX</span></span>

### <span data-ttu-id="7c5c7-107">ComputerNameSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="7c5c7-107">ComputerNameSet (Default)</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7c5c7-108">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="7c5c7-108">CimSessionSet</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7c5c7-109">Description</span><span class="sxs-lookup"><span data-stu-id="7c5c7-109">DESCRIPTION</span></span>
<span data-ttu-id="7c5c7-110">`Update-DscConfiguration`コマンドレットは、プルサーバーに接続し、ノードの現在の構成と異なる場合は構成をダウンロードしてから、構成をコンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-110">The `Update-DscConfiguration` cmdlet connects to a pull server, downloads the configuration if it differs from what is current on the node, and then applies the configuration to the computer.</span></span>

<span data-ttu-id="7c5c7-111">このコマンドレットは、Microsoft サポートライブラリの [WINDOWS RT 8.1、Windows 8.1、および Windows Server 2012 R2 の11月2014更新プログラムのロールアップ](https://support.microsoft.com/kb/3000850) の一部としてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="7c5c7-112">例</span><span class="sxs-lookup"><span data-stu-id="7c5c7-112">EXAMPLES</span></span>

### <span data-ttu-id="7c5c7-113">例 1: 構成を更新する</span><span class="sxs-lookup"><span data-stu-id="7c5c7-113">Example 1: Update a configuration</span></span>

```
PS C:\> Update-DscConfiguration -Wait -Verbose
```

<span data-ttu-id="7c5c7-114">このコマンドを実行すると、サーバーは登録されたプルサービスに接続し、割り当てられている最新の構成をダウンロードして適用します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-114">After running this command, the server will connect to the registered pull service, download the latest assigned configuration, and then apply it.</span></span>
<span data-ttu-id="7c5c7-115">-Wait および-Verbose パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-115">The -Wait and -Verbose parameters are optional.</span></span>
<span data-ttu-id="7c5c7-116">対話形式で作業すると、これらのパラメーターを組み合わせることにより、構成を適用する際の進行状況と成功または失敗に関するリアルタイムのフィードバックが可能になります。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-116">When working interactively, these parameters combined enable real-time feedback about progress and success or failure when applying the configuration.</span></span>

### <span data-ttu-id="7c5c7-117">例 2: CIM セッション経由で接続して構成を更新する</span><span class="sxs-lookup"><span data-stu-id="7c5c7-117">Example 2: Update a configuration by connecting over a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Update-DscConfiguration -CimSession $Session -Wait
```

<span data-ttu-id="7c5c7-118">最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="7c5c7-119">コマンドはパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-119">The command prompts you for a password.</span></span>
<span data-ttu-id="7c5c7-120">詳細を表示するには「`Get-Help New-CimSession`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="7c5c7-121">2番目のコマンドは $Session に格納されている **CimSession** で指定されたコンピューターを更新します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-121">The second command updates the computer specified in the **CimSession** stored in $Session.</span></span>
<span data-ttu-id="7c5c7-122">このコマンドは、 *Wait* パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-122">The command specifies the *Wait* parameter.</span></span>
<span data-ttu-id="7c5c7-123">コンソールでは、現在のコマンドが終了するまで追加のコマンドは受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-123">The console does not accept additional commands until the current command finishes.</span></span>

## <span data-ttu-id="7c5c7-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7c5c7-124">PARAMETERS</span></span>

### <span data-ttu-id="7c5c7-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="7c5c7-125">-CimSession</span></span>
<span data-ttu-id="7c5c7-126">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="7c5c7-127">コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="7c5c7-128">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-128">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="7c5c7-129">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7c5c7-129">-ComputerName</span></span>
<span data-ttu-id="7c5c7-130">コンピューター名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-130">Specifies an array of computer names.</span></span>
<span data-ttu-id="7c5c7-131">コマンドレットでは、このパラメーターで指定したコンピューターに構成設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-131">The cmdlet applies the configuration settings to the computers that this parameter specifies.</span></span>

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

### <span data-ttu-id="7c5c7-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="7c5c7-132">-Credential</span></span>
<span data-ttu-id="7c5c7-133">ターゲット コンピューターに対して、ユーザー名とパスワードを、 **PSCredential** オブジェクトとして指定します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-133">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="7c5c7-134">**PSCredential** オブジェクトを取得するには、Get-Credential コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-134">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="7c5c7-135">詳細を表示するには「`Get-Help Get-Credential`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-135">For more information, type `Get-Help Get-Credential`.</span></span>

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

### <span data-ttu-id="7c5c7-136">-JobName</span><span class="sxs-lookup"><span data-stu-id="7c5c7-136">-JobName</span></span>
<span data-ttu-id="7c5c7-137">ジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-137">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="7c5c7-138">このパラメーターを指定すると、コマンドレットがジョブとして実行され、 **Job** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-138">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="7c5c7-139">既定では、Windows PowerShell は JobN という名前を割り当てます。ここで、N は整数です。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-139">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="7c5c7-140">*Wait* パラメーターを指定した場合は、このパラメーターを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-140">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7c5c7-141">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="7c5c7-141">-ThrottleLimit</span></span>
<span data-ttu-id="7c5c7-142">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-142">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="7c5c7-143">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-143">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="7c5c7-144">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-144">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="7c5c7-145">-Wait</span><span class="sxs-lookup"><span data-stu-id="7c5c7-145">-Wait</span></span>
<span data-ttu-id="7c5c7-146">コマンドレットによって、すべての構成タスクが完了するまでコンソールがブロックされることを示します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-146">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="7c5c7-147">このパラメーターを指定した場合は、 *JobName* パラメーターを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-147">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="7c5c7-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7c5c7-148">-Confirm</span></span>
<span data-ttu-id="7c5c7-149">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7c5c7-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7c5c7-150">-WhatIf</span></span>
<span data-ttu-id="7c5c7-151">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7c5c7-152">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7c5c7-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c5c7-153">CommonParameters</span></span>
<span data-ttu-id="7c5c7-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7c5c7-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c5c7-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7c5c7-156">入力</span><span class="sxs-lookup"><span data-stu-id="7c5c7-156">INPUTS</span></span>

## <span data-ttu-id="7c5c7-157">出力</span><span class="sxs-lookup"><span data-stu-id="7c5c7-157">OUTPUTS</span></span>

## <span data-ttu-id="7c5c7-158">注</span><span class="sxs-lookup"><span data-stu-id="7c5c7-158">NOTES</span></span>

## <span data-ttu-id="7c5c7-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7c5c7-159">RELATED LINKS</span></span>

[<span data-ttu-id="7c5c7-160">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="7c5c7-160">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="7c5c7-161">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c5c7-161">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="7c5c7-162">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="7c5c7-162">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="7c5c7-163">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c5c7-163">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="7c5c7-164">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c5c7-164">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="7c5c7-165">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c5c7-165">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="7c5c7-166">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c5c7-166">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
