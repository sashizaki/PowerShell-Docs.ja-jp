---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213600"
---
# <span data-ttu-id="3f192-103">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f192-103">Stop-DscConfiguration</span></span>

## <span data-ttu-id="3f192-104">概要</span><span class="sxs-lookup"><span data-stu-id="3f192-104">SYNOPSIS</span></span>
<span data-ttu-id="3f192-105">実行中の構成ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="3f192-105">Stops a configuration job that is running.</span></span>

## <span data-ttu-id="3f192-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3f192-106">SYNTAX</span></span>

### <span data-ttu-id="3f192-107">All</span><span class="sxs-lookup"><span data-stu-id="3f192-107">All</span></span>

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3f192-108">Description</span><span class="sxs-lookup"><span data-stu-id="3f192-108">DESCRIPTION</span></span>

<span data-ttu-id="3f192-109">`Stop-DscConfiguration`コマンドレットでは、実行中の構成ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="3f192-109">The `Stop-DscConfiguration` cmdlet stops a configuration job that is running.</span></span> <span data-ttu-id="3f192-110">Common Information Model (CIM) セッションを使用して、このコマンドレットが適用されるコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f192-110">Specify which computers this cmdlet applies to by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="3f192-111">構成ジョブが実行されていない場合、このコマンドレットは警告メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="3f192-111">If there's no configuration job running, this cmdlet returns a warning message.</span></span>

<span data-ttu-id="3f192-112">`Stop-DscConfiguration` は、Microsoft サポートライブラリの [WINDOWS RT 8.1、Windows 8.1、および Windows Server 2012 R2 の2014年11月の更新プログラムのロールアップ](https://support.microsoft.com/kb/3000850) の一部としてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f192-112">`Stop-DscConfiguration` is only available as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span> <span data-ttu-id="3f192-113">このコマンドレットを使用する前に、「 [Windows PowerShell 5.0 の新機能](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)」の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3f192-113">Before you use this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)</span></span>

## <span data-ttu-id="3f192-114">例</span><span class="sxs-lookup"><span data-stu-id="3f192-114">EXAMPLES</span></span>

### <span data-ttu-id="3f192-115">例 1: 構成ジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="3f192-115">Example 1: Stop a configuration job</span></span>

<span data-ttu-id="3f192-116">この例では、コマンドレットを使用して CIM セッションを作成し `New-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="3f192-116">In this example, a CIM session is created using the `New-CimSession` cmdlet.</span></span> <span data-ttu-id="3f192-117">**CimSession** オブジェクトは、実行中の構成ジョブを停止するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f192-117">The **CimSession** object is used to stop a running configuration job.</span></span>

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

<span data-ttu-id="3f192-118">`New-CimSession`**ComputerName** パラメーターを使用して、Server01 コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f192-118">`New-CimSession` uses the **ComputerName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="3f192-119">**Credential** パラメーターでは、ユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f192-119">The **Credential** parameter specifies the user account.</span></span> <span data-ttu-id="3f192-120">**CimSession** オブジェクトは変数に格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="3f192-120">The **CimSession** object is stored in the `$Session` variable.</span></span> <span data-ttu-id="3f192-121">コマンドを実行すると、ユーザーアカウントのパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="3f192-121">When the command is run, you're prompted for the user account's password.</span></span>

<span data-ttu-id="3f192-122">`Stop-DscConfiguration` では、 **CimSession** パラメーターと、に格納されているオブジェクトを使用して、 `$Session` 構成ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="3f192-122">`Stop-DscConfiguration` uses the **CimSession** parameter and the object stored in `$Session` to stop the configuration job.</span></span>

## <span data-ttu-id="3f192-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3f192-123">PARAMETERS</span></span>

### <span data-ttu-id="3f192-124">-AsJob</span><span class="sxs-lookup"><span data-stu-id="3f192-124">-AsJob</span></span>

<span data-ttu-id="3f192-125">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3f192-125">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="3f192-126">PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f192-126">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="3f192-127">**AsJob** パラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f192-127">To use the **AsJob** parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="3f192-128">Windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[ **管理者として実行** ] オプションを使用して PowerShell を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f192-128">On Windows Vista and later versions of the Windows operating system, you must open PowerShell with the **Run as administrator** option.</span></span> <span data-ttu-id="3f192-129">詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f192-129">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3f192-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="3f192-130">-CimSession</span></span>

<span data-ttu-id="3f192-131">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3f192-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="3f192-132">コンピューター名またはセッションオブジェクト (またはからの出力など) を入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="3f192-132">Enter a computer name or a session object, such as the output from `New-CimSession` or `Get-CimSession`.</span></span>

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

### <span data-ttu-id="3f192-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3f192-133">-Confirm</span></span>

<span data-ttu-id="3f192-134">`Stop-DscConfiguration`**Confirm** パラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3f192-134">`Stop-DscConfiguration` doesn't support the **Confirm** parameter.</span></span> <span data-ttu-id="3f192-135">**Confirm** パラメーターが使用されている場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f192-135">If the **Confirm** parameter is used, an error is displayed.</span></span>

<span data-ttu-id="3f192-136">**確認** をサポートしている PowerShell コマンドレットの場合、パラメーターを使用すると、コマンドを実行する前に確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f192-136">For PowerShell cmdlets that support **Confirm** , using the parameter prompts you for verification before a command is run.</span></span>

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

### <span data-ttu-id="3f192-137">-Force</span><span class="sxs-lookup"><span data-stu-id="3f192-137">-Force</span></span>

<span data-ttu-id="3f192-138">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3f192-138">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3f192-139">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="3f192-139">-ThrottleLimit</span></span>

<span data-ttu-id="3f192-140">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f192-140">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

<span data-ttu-id="3f192-141">このパラメーターを省略した場合、または値を入力した場合 `0` 、PowerShell では、コンピューターで実行されている CIM コマンドレットの数に基づいて、最適なスロットル制限が計算されます。</span><span class="sxs-lookup"><span data-stu-id="3f192-141">If this parameter is omitted or a value of `0` is entered, PowerShell calculates an optimum throttle limit based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="3f192-142">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="3f192-142">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="3f192-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3f192-143">-WhatIf</span></span>

<span data-ttu-id="3f192-144">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="3f192-144">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="3f192-145">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="3f192-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="3f192-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f192-146">CommonParameters</span></span>

<span data-ttu-id="3f192-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3f192-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3f192-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f192-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3f192-149">入力</span><span class="sxs-lookup"><span data-stu-id="3f192-149">INPUTS</span></span>

### <span data-ttu-id="3f192-150">なし</span><span class="sxs-lookup"><span data-stu-id="3f192-150">None</span></span>

## <span data-ttu-id="3f192-151">出力</span><span class="sxs-lookup"><span data-stu-id="3f192-151">OUTPUTS</span></span>

### <span data-ttu-id="3f192-152">なし</span><span class="sxs-lookup"><span data-stu-id="3f192-152">None</span></span>

## <span data-ttu-id="3f192-153">注</span><span class="sxs-lookup"><span data-stu-id="3f192-153">NOTES</span></span>

## <span data-ttu-id="3f192-154">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3f192-154">RELATED LINKS</span></span>

[<span data-ttu-id="3f192-155">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="3f192-155">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="3f192-156">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f192-156">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="3f192-157">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="3f192-157">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="3f192-158">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="3f192-158">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="3f192-159">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f192-159">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="3f192-160">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f192-160">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="3f192-161">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f192-161">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="3f192-162">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f192-162">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)

[<span data-ttu-id="3f192-163">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="3f192-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)
