---
external help file: Remove-DscConfigurationDocument.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DscConfigurationDocument
ms.openlocfilehash: d3e9b15dfeea94921503247adc08b291eed9d7d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215299"
---
# <span data-ttu-id="c6124-103">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="c6124-103">Remove-DscConfigurationDocument</span></span>

## <span data-ttu-id="c6124-104">概要</span><span class="sxs-lookup"><span data-stu-id="c6124-104">SYNOPSIS</span></span>
<span data-ttu-id="c6124-105">構成ドキュメントを DSC 構成ストアから削除します。</span><span class="sxs-lookup"><span data-stu-id="c6124-105">Removes a configuration document from the DSC configuration store.</span></span>

## <span data-ttu-id="c6124-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c6124-106">SYNTAX</span></span>

```
Remove-DscConfigurationDocument -Stage <Stage> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c6124-107">Description</span><span class="sxs-lookup"><span data-stu-id="c6124-107">DESCRIPTION</span></span>
<span data-ttu-id="c6124-108">`Remove-DscConfigurationDocument`コマンドレットは、Windows PowerShell Desired State configuration (DSC) 構成ストアから構成ドキュメント (.mof ファイル) を削除します。</span><span class="sxs-lookup"><span data-stu-id="c6124-108">The `Remove-DscConfigurationDocument` cmdlet removes a configuration document (.mof file) from the Windows PowerShell Desired State Configuration (DSC) configuration store.</span></span>
<span data-ttu-id="c6124-109">このコマンドレットは、構成時に、 `Start-DscConfiguration` 対象のコンピューター上のフォルダーに .mof ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c6124-109">During configuration, the `Start-DscConfiguration` cmdlet copies a .mof file to a folder on the target computer.</span></span>
<span data-ttu-id="c6124-110">このコマンドレットは、その構成ドキュメントを削除し、追加のクリーンアップを行います。</span><span class="sxs-lookup"><span data-stu-id="c6124-110">This cmdlet removes that configuration document and does additional cleanup.</span></span>

<span data-ttu-id="c6124-111">このコマンドレットは、Microsoft サポートライブラリの [WINDOWS RT 8.1、Windows 8.1、および Windows Server 2012 R2 の11月2014更新プログラムのロールアップ](https://support.microsoft.com/kb/3000850) の一部としてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6124-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="c6124-112">例</span><span class="sxs-lookup"><span data-stu-id="c6124-112">EXAMPLES</span></span>

### <span data-ttu-id="c6124-113">例 1: 現在の構成ドキュメントを削除する</span><span class="sxs-lookup"><span data-stu-id="c6124-113">Example 1: Remove the current configuration document</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Remove-DscConfigurationDocument -Stage Current -CimSession $Session
```

<span data-ttu-id="c6124-114">最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="c6124-114">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="c6124-115">コマンドはパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="c6124-115">The command prompts you for a password.</span></span>
<span data-ttu-id="c6124-116">詳細を表示するには「`Get-Help New-CimSession`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6124-116">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="c6124-117">2番目のコマンドは、$Session に格納されている **CimSession** で指定されたコンピューターの現在の構成ドキュメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6124-117">The second command removes the current configuration document for the computer specified in the **CimSession** stored in $Session.</span></span>

## <span data-ttu-id="c6124-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c6124-118">PARAMETERS</span></span>

### <span data-ttu-id="c6124-119">-AsJob</span><span class="sxs-lookup"><span data-stu-id="c6124-119">-AsJob</span></span>
<span data-ttu-id="c6124-120">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="c6124-120">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="c6124-121">*AsJob* パラメーターを指定すると、このコマンドはジョブを表すオブジェクトを返し、コマンドプロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="c6124-121">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="c6124-122">ジョブが完了するまで、引き続きセッションで作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c6124-122">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="c6124-123">ジョブは、ローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="c6124-123">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="c6124-124">ジョブを管理するには、Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6124-124">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="c6124-125">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6124-125">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="c6124-126">このパラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。また、windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[管理者として実行] オプションを使用して Windows PowerShell を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6124-126">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="c6124-127">詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6124-127">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="c6124-128">Windows PowerShell のバックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6124-128">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="c6124-129">-CimSession</span><span class="sxs-lookup"><span data-stu-id="c6124-129">-CimSession</span></span>
<span data-ttu-id="c6124-130">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6124-130">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="c6124-131">コンピューター名またはセッションオブジェクト ( **CimSession** または **CimSession** コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6124-131">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

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

### <span data-ttu-id="c6124-132">-Force</span><span class="sxs-lookup"><span data-stu-id="c6124-132">-Force</span></span>
<span data-ttu-id="c6124-133">このコマンドレットが構成ドキュメントを削除する前に、実行中の構成ジョブを停止することを示します。</span><span class="sxs-lookup"><span data-stu-id="c6124-133">Indicates that this cmdlet stops the running configuration job before it removes the configuration document.</span></span>
<span data-ttu-id="c6124-134">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6124-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c6124-135">-ステージ</span><span class="sxs-lookup"><span data-stu-id="c6124-135">-Stage</span></span>
<span data-ttu-id="c6124-136">削除する構成ドキュメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6124-136">Specifies which configuration document to remove.</span></span>
<span data-ttu-id="c6124-137">複数のドキュメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6124-137">You can specify multiple documents.</span></span>
<span data-ttu-id="c6124-138">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c6124-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c6124-139">現在。</span><span class="sxs-lookup"><span data-stu-id="c6124-139">Current.</span></span>
<span data-ttu-id="c6124-140">システムの現在の状態を説明する構成ドキュメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6124-140">Remove the configuration document that describes the current state of the system.</span></span>
- <span data-ttu-id="c6124-141">保留中 </span><span class="sxs-lookup"><span data-stu-id="c6124-141">Pending.</span></span>
<span data-ttu-id="c6124-142">システムの保留中の状態を説明する構成ドキュメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6124-142">Remove the configuration document that describes the pending state of the system.</span></span>
- <span data-ttu-id="c6124-143">前へ。</span><span class="sxs-lookup"><span data-stu-id="c6124-143">Previous.</span></span>
<span data-ttu-id="c6124-144">システムの以前の状態を説明する構成ドキュメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6124-144">Remove the configuration document that describes the previous state of the system.</span></span>

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoveDscConfigurationDocument.Stage
Parameter Sets: (All)
Aliases:
Accepted values: Current, Pending, Previous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c6124-145">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="c6124-145">-ThrottleLimit</span></span>
<span data-ttu-id="c6124-146">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6124-146">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="c6124-147">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="c6124-147">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="c6124-148">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="c6124-148">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="c6124-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c6124-149">-Confirm</span></span>
<span data-ttu-id="c6124-150">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6124-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c6124-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c6124-151">-WhatIf</span></span>
<span data-ttu-id="c6124-152">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c6124-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c6124-153">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c6124-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c6124-154">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6124-154">CommonParameters</span></span>
<span data-ttu-id="c6124-155">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c6124-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c6124-156">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6124-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c6124-157">入力</span><span class="sxs-lookup"><span data-stu-id="c6124-157">INPUTS</span></span>

### <span data-ttu-id="c6124-158">なし</span><span class="sxs-lookup"><span data-stu-id="c6124-158">None</span></span>

## <span data-ttu-id="c6124-159">出力</span><span class="sxs-lookup"><span data-stu-id="c6124-159">OUTPUTS</span></span>

### <span data-ttu-id="c6124-160">なし</span><span class="sxs-lookup"><span data-stu-id="c6124-160">None</span></span>

## <span data-ttu-id="c6124-161">注</span><span class="sxs-lookup"><span data-stu-id="c6124-161">NOTES</span></span>

## <span data-ttu-id="c6124-162">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c6124-162">RELATED LINKS</span></span>

[<span data-ttu-id="c6124-163">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="c6124-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="c6124-164">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c6124-164">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="c6124-165">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="c6124-165">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)
