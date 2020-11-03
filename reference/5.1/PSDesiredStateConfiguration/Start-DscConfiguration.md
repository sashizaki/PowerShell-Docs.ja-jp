---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215288"
---
# <span data-ttu-id="01a38-103">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="01a38-103">Start-DscConfiguration</span></span>

## <span data-ttu-id="01a38-104">概要</span><span class="sxs-lookup"><span data-stu-id="01a38-104">SYNOPSIS</span></span>
<span data-ttu-id="01a38-105">ノードに構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-105">Applies configuration to nodes.</span></span>

## <span data-ttu-id="01a38-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="01a38-106">SYNTAX</span></span>

### <span data-ttu-id="01a38-107">ComputerNameAndPathSet (既定)</span><span class="sxs-lookup"><span data-stu-id="01a38-107">ComputerNameAndPathSet (Default)</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="01a38-108">CimSessionAndPathSet</span><span class="sxs-lookup"><span data-stu-id="01a38-108">CimSessionAndPathSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="01a38-109">ComputerNameAndUseExistingSet</span><span class="sxs-lookup"><span data-stu-id="01a38-109">ComputerNameAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="01a38-110">CimSessionAndUseExistingSet</span><span class="sxs-lookup"><span data-stu-id="01a38-110">CimSessionAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="01a38-111">Description</span><span class="sxs-lookup"><span data-stu-id="01a38-111">DESCRIPTION</span></span>
<span data-ttu-id="01a38-112">**Start-DscConfiguration** コマンドレットはノードに構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-112">The **Start-DscConfiguration** cmdlet applies configuration to nodes.</span></span>
<span data-ttu-id="01a38-113">*Useexisting* パラメーターと共に使用すると、ターゲットコンピューター上の既存の構成が適用されます。</span><span class="sxs-lookup"><span data-stu-id="01a38-113">When used with the *UseExisting* parameter, the existing configuration on the target computer is applied.</span></span>
<span data-ttu-id="01a38-114">コンピューター名を指定するか Common Information Model (CIM) セッションを使用して、構成を適用するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="01a38-114">Specify which computers that you want to apply configuration to by specifying computer names or by using Common Information Model (CIM) sessions.</span></span>

<span data-ttu-id="01a38-115">既定では、このコマンドレットは、ジョブを作成し、 **Job** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="01a38-115">By default, this cmdlet creates a job and returns a **Job** object.</span></span>
<span data-ttu-id="01a38-116">バックグラウンドジョブの詳細については、「」と入力 `Get-Help about_Jobs` してください。</span><span class="sxs-lookup"><span data-stu-id="01a38-116">For more information about background jobs, type `Get-Help about_Jobs`.</span></span>
<span data-ttu-id="01a38-117">このコマンドレットを対話的に使用するには、 *Wait* パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="01a38-117">To use this cmdlet interactively, specify the *Wait* parameter.</span></span>

<span data-ttu-id="01a38-118">コマンドレットが構成設定を適用するときの動作内容の詳細を確認するには、 *Verbose* パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="01a38-118">Specify the *Verbose* parameter to see details of what the cmdlet does when it applies configuration settings.</span></span>

## <span data-ttu-id="01a38-119">例</span><span class="sxs-lookup"><span data-stu-id="01a38-119">EXAMPLES</span></span>

### <span data-ttu-id="01a38-120">例 1: 構成設定を適用する</span><span class="sxs-lookup"><span data-stu-id="01a38-120">Example 1: Apply configuration settings</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="01a38-121">以下のコマンドは、C:\DSC\Configurations\ からの構成設定を、このフォルダーに設定を持つすべてのコンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-121">This command applies the configuration settings from C:\DSC\Configurations\ to the every computer that has settings in that folder.</span></span>
<span data-ttu-id="01a38-122">コマンドは、配置されている対象ノードごとに **Job** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="01a38-122">The command returns **Job** objects for each target node deployed to.</span></span>

### <span data-ttu-id="01a38-123">例 2: 構成設定を適用し、構成が完了するまで待機する</span><span class="sxs-lookup"><span data-stu-id="01a38-123">Example 2: Apply configuration settings and wait for configuration to complete</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

<span data-ttu-id="01a38-124">以下のコマンドは、C:\DSC\Configurations\ からの構成をローカル コンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-124">This command applies the configuration from C:\DSC\Configurations\ to the local computer.</span></span>
<span data-ttu-id="01a38-125">コマンドは、配置されている対象ノードごとに **Job** オブジェクトを返します (この場合はローカル コンピューターのみ)。</span><span class="sxs-lookup"><span data-stu-id="01a38-125">The command returns **Job** objects for each target node deployed to, in this case, just the local computer.</span></span>
<span data-ttu-id="01a38-126">この例では、 *Verbose* パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="01a38-126">This example specifies the *Verbose* parameter.</span></span>
<span data-ttu-id="01a38-127">そのため、コマンドを実行すると、コンソールにメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="01a38-127">Therefore, the command sends messages to the console as it proceeds.</span></span>
<span data-ttu-id="01a38-128">このコマンドには、 *Wait* パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="01a38-128">The command includes the *Wait* parameter.</span></span>
<span data-ttu-id="01a38-129">そのため、コマンドがすべての構成タスクを完了するまで、コンソールを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="01a38-129">Therefore, you cannot use the console until the command finishes all configuration tasks.</span></span>

### <span data-ttu-id="01a38-130">例 3: CIM セッションを使用して構成設定を適用する</span><span class="sxs-lookup"><span data-stu-id="01a38-130">Example 3: Apply configuration settings by using a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="01a38-131">この例では、指定したコンピューターに構成設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-131">This example applies configuration settings to a specified computer.</span></span>
<span data-ttu-id="01a38-132">例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="01a38-132">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="01a38-133">または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-133">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="01a38-134">最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="01a38-134">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="01a38-135">コマンドはパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="01a38-135">The command prompts you for a password.</span></span>
<span data-ttu-id="01a38-136">詳細を表示するには「`Get-Help NewCimSession`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="01a38-136">For more information, type `Get-Help NewCimSession`.</span></span>

<span data-ttu-id="01a38-137">2番目のコマンドは、C:\DSC\Configurations\ の構成設定を、$Session 変数に格納されている **CimSession** オブジェクトによって識別されるコンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-137">The second command applies the configuration settings from C:\DSC\Configurations\ to the computers identified by the **CimSession** objects stored in the $Session variable.</span></span>
<span data-ttu-id="01a38-138">この例で、$Session 変数には、Server01 という名前のコンピューターに対してのみ CIM セッションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="01a38-138">In this example, the $Session variable contains a CIM session only for the computer named Server01.</span></span>
<span data-ttu-id="01a38-139">コマンドは設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-139">The command applies the configuration.</span></span>
<span data-ttu-id="01a38-140">コマンドは、構成されているコンピューターごとに **Job** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="01a38-140">The command creates **Job** objects for each configured computer.</span></span>

## <span data-ttu-id="01a38-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="01a38-141">PARAMETERS</span></span>

### <span data-ttu-id="01a38-142">-CimSession</span><span class="sxs-lookup"><span data-stu-id="01a38-142">-CimSession</span></span>
<span data-ttu-id="01a38-143">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="01a38-143">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="01a38-144">コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="01a38-144">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="01a38-145">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="01a38-145">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="01a38-146">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="01a38-146">-ComputerName</span></span>
<span data-ttu-id="01a38-147">コンピューター名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="01a38-147">Specifies an array of computer names.</span></span>
<span data-ttu-id="01a38-148">このパラメーターは、 *Path* パラメーターに構成ドキュメントがあるコンピューターを、配列で指定されているものに制限します。</span><span class="sxs-lookup"><span data-stu-id="01a38-148">This parameter restricts the computers that have configuration documents in the *Path* parameter to those specified in the array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="01a38-149">-Credential</span><span class="sxs-lookup"><span data-stu-id="01a38-149">-Credential</span></span>
<span data-ttu-id="01a38-150">ターゲット コンピューターに対して、ユーザー名とパスワードを、 **PSCredential** オブジェクトとして指定します。</span><span class="sxs-lookup"><span data-stu-id="01a38-150">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="01a38-151">**PSCredential** オブジェクトを取得するには、Get-Credential コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-151">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="01a38-152">詳細を表示するには「`Get-Help Get-Credential`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="01a38-152">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01a38-153">-Force</span><span class="sxs-lookup"><span data-stu-id="01a38-153">-Force</span></span>
<span data-ttu-id="01a38-154">対象のコンピューターで現在実行されている構成操作を停止し、新しい Start-Configuration 操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="01a38-154">Stops the configuration operation currently running on the target computer and begins the new Start-Configuration operation.</span></span>
<span data-ttu-id="01a38-155">ローカル Configuration Manager の **Refreshmode** プロパティが **Pull** に設定されている場合、このパラメーターを指定すると **Push** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="01a38-155">If the **RefreshMode** property of the Local Configuration Manager is set to **Pull** , specifying this parameter changes it to **Push** .</span></span>

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

### <span data-ttu-id="01a38-156">-JobName</span><span class="sxs-lookup"><span data-stu-id="01a38-156">-JobName</span></span>
<span data-ttu-id="01a38-157">ジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="01a38-157">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="01a38-158">このパラメーターを指定すると、コマンドレットがジョブとして実行され、 **Job** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="01a38-158">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="01a38-159">既定では、Windows PowerShell は JobN という名前を割り当てます。ここで、N は整数です。</span><span class="sxs-lookup"><span data-stu-id="01a38-159">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="01a38-160">*Wait* パラメーターを指定した場合は、このパラメーターを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="01a38-160">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

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

### <span data-ttu-id="01a38-161">-Path</span><span class="sxs-lookup"><span data-stu-id="01a38-161">-Path</span></span>
<span data-ttu-id="01a38-162">構成設定ファイルを含むフォルダーのファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="01a38-162">Specifies a file path of a folder that contains configuration settings files.</span></span>
<span data-ttu-id="01a38-163">このコマンドレットは、指定したパスに設定ファイルがあるコンピューターに、これらの構成設定を発行して適用します。</span><span class="sxs-lookup"><span data-stu-id="01a38-163">This cmdlet publishes and applies these configuration settings to computers that have settings files in the specified path.</span></span>
<span data-ttu-id="01a38-164">各ターゲットノードには、次の形式の設定ファイルが必要です: NetBIOS 名 .mof。</span><span class="sxs-lookup"><span data-stu-id="01a38-164">Each target node must have a settings file of the following format: NetBIOS Name.mof.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01a38-165">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="01a38-165">-ThrottleLimit</span></span>
<span data-ttu-id="01a38-166">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="01a38-166">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="01a38-167">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="01a38-167">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="01a38-168">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="01a38-168">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="01a38-169">-UseExisting</span><span class="sxs-lookup"><span data-stu-id="01a38-169">-UseExisting</span></span>
<span data-ttu-id="01a38-170">このコマンドレットが既存の構成を適用することを示します。</span><span class="sxs-lookup"><span data-stu-id="01a38-170">Indicates that this cmdlet applies the existing configuration.</span></span>
<span data-ttu-id="01a38-171">構成は、 **start-dscconfiguration** を使用するか、または Publish-DscConfiguration コマンドレットを使用して発行することにより、ターゲットコンピューターに存在することができます。</span><span class="sxs-lookup"><span data-stu-id="01a38-171">The configuration can exist on the target computer by enactment using **Start-DscConfiguration** or by publication using the Publish-DscConfiguration cmdlet.</span></span>

<span data-ttu-id="01a38-172">このコマンドレットにこのパラメーターを指定する前に、「 [Windows PowerShell 5.0 の新機能](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)」の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="01a38-172">Before you specify this parameter for this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01a38-173">-Wait</span><span class="sxs-lookup"><span data-stu-id="01a38-173">-Wait</span></span>
<span data-ttu-id="01a38-174">コマンドレットによって、すべての構成タスクが完了するまでコンソールがブロックされることを示します。</span><span class="sxs-lookup"><span data-stu-id="01a38-174">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="01a38-175">このパラメーターを指定した場合は、 *JobName* パラメーターを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="01a38-175">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="01a38-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="01a38-176">-Confirm</span></span>
<span data-ttu-id="01a38-177">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01a38-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="01a38-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="01a38-178">-WhatIf</span></span>
<span data-ttu-id="01a38-179">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="01a38-179">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="01a38-180">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="01a38-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="01a38-181">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="01a38-181">CommonParameters</span></span>
<span data-ttu-id="01a38-182">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="01a38-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="01a38-183">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01a38-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="01a38-184">入力</span><span class="sxs-lookup"><span data-stu-id="01a38-184">INPUTS</span></span>

## <span data-ttu-id="01a38-185">出力</span><span class="sxs-lookup"><span data-stu-id="01a38-185">OUTPUTS</span></span>

## <span data-ttu-id="01a38-186">注</span><span class="sxs-lookup"><span data-stu-id="01a38-186">NOTES</span></span>

## <span data-ttu-id="01a38-187">関連リンク</span><span class="sxs-lookup"><span data-stu-id="01a38-187">RELATED LINKS</span></span>

[<span data-ttu-id="01a38-188">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="01a38-188">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="01a38-189">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="01a38-189">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="01a38-190">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="01a38-190">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="01a38-191">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="01a38-191">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="01a38-192">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="01a38-192">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="01a38-193">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="01a38-193">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="01a38-194">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="01a38-194">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)
