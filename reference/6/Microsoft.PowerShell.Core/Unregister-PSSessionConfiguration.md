---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: c622642a572509e9069fceff2492baf0cc8ea911
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218640"
---
# <span data-ttu-id="35650-103">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="35650-103">Unregister-PSSessionConfiguration</span></span>

## <span data-ttu-id="35650-104">概要</span><span class="sxs-lookup"><span data-stu-id="35650-104">SYNOPSIS</span></span>
<span data-ttu-id="35650-105">登録されたセッション構成をコンピューターから削除します。</span><span class="sxs-lookup"><span data-stu-id="35650-105">Deletes registered session configurations from the computer.</span></span>

## <span data-ttu-id="35650-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="35650-106">SYNTAX</span></span>

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="35650-107">Description</span><span class="sxs-lookup"><span data-stu-id="35650-107">DESCRIPTION</span></span>

<span data-ttu-id="35650-108">コマンドレットでは、 `Unregister-PSSessionConfiguration` 登録されているセッション構成をコンピューターから削除します。</span><span class="sxs-lookup"><span data-stu-id="35650-108">The `Unregister-PSSessionConfiguration` cmdlet deletes registered session configurations from the computer.</span></span> <span data-ttu-id="35650-109">このコマンドレットは、システム管理者がユーザー用にカスタマイズされたセッション構成を管理するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="35650-109">This cmdlet is designed for system administrators to manage customized session configurations for users.</span></span>

<span data-ttu-id="35650-110">変更を有効にするために、は `Unregister-PSSessionConfiguration` **WinRM** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="35650-110">To make the change effective, `Unregister-PSSessionConfiguration` restarts the **WinRM** service.</span></span> <span data-ttu-id="35650-111">再起動が行われないようにするには、 **NoServiceRestart** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="35650-111">To prevent the restart, specify the **NoServiceRestart** parameter.</span></span>

<span data-ttu-id="35650-112">既定の **Microsoft PowerShell** または **microsoft.powershell32** セッション構成を誤って削除した場合は、コマンドレットを使用して `Enable-PSRemoting` 復元します。</span><span class="sxs-lookup"><span data-stu-id="35650-112">If you accidentally delete the default **Microsoft.PowerShell** or **Microsoft.PowerShell32** session configurations, use the `Enable-PSRemoting` cmdlet to restore them.</span></span> <span data-ttu-id="35650-113">詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35650-113">For more information, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="35650-114">例</span><span class="sxs-lookup"><span data-stu-id="35650-114">EXAMPLES</span></span>

### <span data-ttu-id="35650-115">例 1: セッション構成を削除する</span><span class="sxs-lookup"><span data-stu-id="35650-115">Example 1: Delete a session configuration</span></span>

<span data-ttu-id="35650-116">この例では、 **MaintenanceShell** セッション構成をコンピューターから削除します。</span><span class="sxs-lookup"><span data-stu-id="35650-116">This example deletes the **MaintenanceShell** session configuration from the computer.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### <span data-ttu-id="35650-117">例 2: セッション構成を削除し、WinRM サービスを再起動する</span><span class="sxs-lookup"><span data-stu-id="35650-117">Example 2: Delete a session configuration and restart the WinRM service</span></span>

<span data-ttu-id="35650-118">この例では、 **MaintenanceShell** 構成を削除し、WinRM サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="35650-118">In this example, we delete the **MaintenanceShell** configuration and restart the WinRM service.</span></span> <span data-ttu-id="35650-119">**Force** パラメーターを指定すると、プロンプトを表示せずに、 **WinRM** サービスを再起動するためのすべてのユーザーメッセージが抑制されます。</span><span class="sxs-lookup"><span data-stu-id="35650-119">The **Force** parameter suppresses all user messages to restart the **WinRM** service without prompting.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### <span data-ttu-id="35650-120">例 3: すべてのセッション構成を削除する</span><span class="sxs-lookup"><span data-stu-id="35650-120">Example 3: Delete all session configurations</span></span>

<span data-ttu-id="35650-121">この例では、コンピューター上のすべてのセッション構成を削除する2つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="35650-121">This examples show two ways to delete all the session configurations on the computer.</span></span> <span data-ttu-id="35650-122">どちらのコマンドも同じ効果を持ち、同義に使用できます。</span><span class="sxs-lookup"><span data-stu-id="35650-122">Both commands have the same effect and can be used interchangeably.</span></span>

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### <span data-ttu-id="35650-123">例 4: 再起動せずに登録を解除する</span><span class="sxs-lookup"><span data-stu-id="35650-123">Example 4: Unregister without a restart</span></span>

<span data-ttu-id="35650-124">この例では、 **NoServiceRestart** パラメーターを使用して、コンピューター上のセッションを中断するサービスの再起動を防止する効果を示します。</span><span class="sxs-lookup"><span data-stu-id="35650-124">This example shows the effect of using the **NoServiceRestart** parameter to prevent a service restart that would disrupt any sessions on the computer.</span></span>

```
PS> Unregister-PSSessionConfiguration -Name "MaintenanceShell" -NoServiceRestart
PS> Get-PSSessionConfiguration -Name "MaintenanceShell"

Get-PSSessionConfiguration -Name MaintenanceShell : No Session Configuration matches criteria "MaintenanceShell".
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

PS> New-PSSession -ConfigurationName "MaintenanceShell"

Id Name      ComputerName    State    Configuration         Availability
-- ----      ------------    -----    -------------         ------------
1 Session1  localhost       Opened   MaintenanceShell      Available

PS> Restart-Service winrm
PS> New-PSSession -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message :
 The WS-Management service cannot process the request.
 The resource URI (http://schemas.microsoft.com/powershell/MaintenanceShell) was not found in the WS-Management catalog.
 The catalog contains the metadata that describes resources, or logical endpoints.
 For more information, see the about_Remote_Troubleshooting Help topic.
 + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
 + FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="35650-125">によって、 `Unregister-PSSessionConfiguration` **MaintenanceShell** セッション構成が削除されます。</span><span class="sxs-lookup"><span data-stu-id="35650-125">The `Unregister-PSSessionConfiguration` deletes the **MaintenanceShell** session configuration.</span></span>
<span data-ttu-id="35650-126">ただし、このコマンドでは **NoServiceRestart** パラメーターが使用されるため、 **WinRM** サービスは再起動されず、変更はまだ完全に有効になりません。</span><span class="sxs-lookup"><span data-stu-id="35650-126">However, because the command uses the **NoServiceRestart** parameter, the **WinRM** service is not restarted and the change is not yet completely effective.</span></span>

<span data-ttu-id="35650-127">次に、は `Get-PSSessionConfiguration` **MaintenanceShell** セッションを取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="35650-127">Next, the `Get-PSSessionConfiguration` tries to get the **MaintenanceShell** session.</span></span> <span data-ttu-id="35650-128">セッションは WS-Management リソーステーブルから削除されているため、で `Get-PSSessionConfiguration` 返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="35650-128">Because the session has been removed from the WS-Management resource table, `Get-PSSessionConfiguration` cannot return it.</span></span>

<span data-ttu-id="35650-129">コマンドレットでは、 `New-PSSession` **MaintenanceShell** 構成を使用してセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="35650-129">The `New-PSSession` cmdlet creates a session using the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="35650-130">このコマンドは成功します。</span><span class="sxs-lookup"><span data-stu-id="35650-130">The command succeeds.</span></span> <span data-ttu-id="35650-131">次に、 **WinRM** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="35650-131">Next, we restart the **WinRM** service.</span></span>

<span data-ttu-id="35650-132">最後に、 `New-PSSession` コマンドレットは、 **MaintenanceShell** 構成を使用するセッションを作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="35650-132">Finally, the `New-PSSession` cmdlet tries to create a session that uses the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="35650-133">今回は、WinRM サービスの再起動時に **MaintenanceShell** 構成が削除されたため、セッションが失敗します。</span><span class="sxs-lookup"><span data-stu-id="35650-133">This time, the session fails because the **MaintenanceShell** configuration was deleted when the WinRM service restarted.</span></span>

## <span data-ttu-id="35650-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="35650-134">PARAMETERS</span></span>

### <span data-ttu-id="35650-135">-Force</span><span class="sxs-lookup"><span data-stu-id="35650-135">-Force</span></span>

<span data-ttu-id="35650-136">コマンドレットによって確認メッセージが表示されないことを示し、プロンプトを表示せずに **WinRM** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="35650-136">Indicates that the cmdlet does not prompt you for confirmation, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="35650-137">サービスを再起動すると、構成の変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="35650-137">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="35650-138">再起動を回避し、再起動メッセージを表示しないようにするには、 **NoServiceRestart** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="35650-138">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="35650-139">-Name</span><span class="sxs-lookup"><span data-stu-id="35650-139">-Name</span></span>

<span data-ttu-id="35650-140">削除するセッション構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="35650-140">Specifies the names of the session configurations to delete.</span></span> <span data-ttu-id="35650-141">1 つのセッション構成名または構成名パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="35650-141">Enter one session configuration name or a configuration name pattern.</span></span> <span data-ttu-id="35650-142">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35650-142">Wildcard characters are permitted.</span></span> <span data-ttu-id="35650-143">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="35650-143">This parameter is required.</span></span>

<span data-ttu-id="35650-144">パイプを使用してセッション構成をにパイプすることもでき `Unregister-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="35650-144">You can also pipe a session configurations to `Unregister-PSSessionConfiguration`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="35650-145">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="35650-145">-NoServiceRestart</span></span>

<span data-ttu-id="35650-146">このコマンドレットが **WinRM** サービスを再起動せず、サービスの再起動を求めるメッセージを表示しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="35650-146">Indicates that this cmdlet does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="35650-147">既定では、コマンドを実行すると、 `Unregister-PSSessionConfiguration` 変更を有効にするために **WinRM** サービスを再起動するように求められます。</span><span class="sxs-lookup"><span data-stu-id="35650-147">By default, when you run an `Unregister-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the change effective.</span></span> <span data-ttu-id="35650-148">**WinRM** サービスが再起動されるまで、が見つからない場合でも、ユーザーは登録されていないセッション構成を引き続き使用できます `Get-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="35650-148">Until the **WinRM** service is restarted, users can still use the unregistered session configuration, even though `Get-PSSessionConfiguration` does not find it.</span></span>

<span data-ttu-id="35650-149">プロンプトを表示せずに **WinRM** サービスを再起動するには、 **Force** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="35650-149">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="35650-150">**WinRM** サービスを手動で再起動するには、コマンドレットを使用し `Restart-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="35650-150">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="35650-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="35650-151">-Confirm</span></span>

<span data-ttu-id="35650-152">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35650-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="35650-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="35650-153">-WhatIf</span></span>

<span data-ttu-id="35650-154">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="35650-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="35650-155">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="35650-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="35650-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="35650-156">CommonParameters</span></span>

<span data-ttu-id="35650-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="35650-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="35650-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35650-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="35650-159">入力</span><span class="sxs-lookup"><span data-stu-id="35650-159">INPUTS</span></span>

### <span data-ttu-id="35650-160">Register-pssessionconfiguration # のコマンド # には、</span><span class="sxs-lookup"><span data-stu-id="35650-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

<span data-ttu-id="35650-161">セッション構成オブジェクトをからこのコマンドレットにパイプすることができ `Get-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="35650-161">You can pipe a session configuration object from `Get-PSSessionConfiguration` to this cmdlet.</span></span>

## <span data-ttu-id="35650-162">出力</span><span class="sxs-lookup"><span data-stu-id="35650-162">OUTPUTS</span></span>

### <span data-ttu-id="35650-163">なし</span><span class="sxs-lookup"><span data-stu-id="35650-163">None</span></span>

<span data-ttu-id="35650-164">このコマンドレットはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="35650-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="35650-165">注</span><span class="sxs-lookup"><span data-stu-id="35650-165">NOTES</span></span>

<span data-ttu-id="35650-166">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35650-166">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="35650-167">関連リンク</span><span class="sxs-lookup"><span data-stu-id="35650-167">RELATED LINKS</span></span>

[<span data-ttu-id="35650-168">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="35650-168">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="35650-169">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="35650-169">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="35650-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="35650-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="35650-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="35650-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="35650-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="35650-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="35650-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="35650-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="35650-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="35650-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="35650-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="35650-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="35650-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="35650-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="35650-177">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="35650-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="35650-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="35650-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="35650-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="35650-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
