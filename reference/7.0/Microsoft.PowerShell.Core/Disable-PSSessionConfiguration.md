---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 37925cb1dfa7d588c38df46ec00ad2bfdc7cf9a2
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210992"
---
# <span data-ttu-id="5962b-103">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5962b-103">Disable-PSSessionConfiguration</span></span>

## <span data-ttu-id="5962b-104">概要</span><span class="sxs-lookup"><span data-stu-id="5962b-104">SYNOPSIS</span></span>
<span data-ttu-id="5962b-105">ローカル コンピューター上のセッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5962b-105">Disables session configurations on the local computer.</span></span>

## <span data-ttu-id="5962b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5962b-106">SYNTAX</span></span>

```
Disable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="5962b-107">Description</span><span class="sxs-lookup"><span data-stu-id="5962b-107">DESCRIPTION</span></span>

<span data-ttu-id="5962b-108">`Disable-PSSessionConfiguration`コマンドレットは、ローカルコンピューター上のセッション構成を無効にします。これにより、すべてのユーザーがセッション構成を **PSSessions** 使用してローカルコンピューター上にユーザー管理セッション (pssession) を作成できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5962b-108">The `Disable-PSSessionConfiguration` cmdlet disables session configurations on the local computer, which prevents all users from using the session configurations to create a user-managed sessions ( **PSSessions** ) on the local computer.</span></span> <span data-ttu-id="5962b-109">これは、ユーザーに応じてカスタマイズされたセッション構成を管理するために、システム管理者向けに設計された高度なコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="5962b-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="5962b-110">PowerShell 3.0 以降では、 `Disable-PSSessionConfiguration` コマンドレットにより、セッション構成 () の **Enabled** 設定が False に設定され `WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled` ます。</span><span class="sxs-lookup"><span data-stu-id="5962b-110">Starting in PowerShell 3.0, the `Disable-PSSessionConfiguration` cmdlet sets the **Enabled** setting of the session configuration (`WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled`) to False.</span></span>

<span data-ttu-id="5962b-111">PowerShell 2.0 では、 `Disable-PSSessionConfiguration` コマンドレットは、登録されている1つ以上のセッション構成のセキュリティ記述子に **Deny_All** エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="5962b-111">In PowerShell 2.0, the `Disable-PSSessionConfiguration` cmdlet adds a **Deny_All** entry to the security descriptor of one or more registered session configurations.</span></span>

<span data-ttu-id="5962b-112">パラメーターを指定しない場合は、 `Disable-PSSessionConfiguration` セッションに使用される既定の構成である、 **Microsoft PowerShell** 構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5962b-112">Without parameters, `Disable-PSSessionConfiguration` disables the **Microsoft.PowerShell** configuration, the default configuration used for sessions.</span></span> <span data-ttu-id="5962b-113">ユーザーが別の構成を指定していない限り、ローカル ユーザーとリモート ユーザーの両方がコンピューターに接続するセッションをできないように、効果的に防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="5962b-113">Unless the user specifies a different configuration, both local and remote users are effectively prevented from creating any sessions that connect to the computer.</span></span>

<span data-ttu-id="5962b-114">コンピューター上のすべてのセッション構成を無効にするには、を使用 `Disable-PSRemoting` します。</span><span class="sxs-lookup"><span data-stu-id="5962b-114">To disable all session configurations on the computer, use `Disable-PSRemoting`.</span></span>

## <span data-ttu-id="5962b-115">例</span><span class="sxs-lookup"><span data-stu-id="5962b-115">EXAMPLES</span></span>

### <span data-ttu-id="5962b-116">例 1: 既定の構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="5962b-116">Example 1: Disable the default configuration</span></span>

<span data-ttu-id="5962b-117">この例では、Microsoft PowerShell セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5962b-117">This example disables the Microsoft.PowerShell session configuration.</span></span>

```powershell
Disable-PSSessionConfiguration
```

### <span data-ttu-id="5962b-118">例 2: 登録されているすべてのセッション構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="5962b-118">Example 2: Disable all registered session configurations</span></span>

<span data-ttu-id="5962b-119">この例では、コンピューター上で登録されているすべてのセッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5962b-119">This example disables all registered session configurations on the computer.</span></span>

```powershell
Disable-PSSessionConfiguration -Name *
```

### <span data-ttu-id="5962b-120">例 3: 名前でセッション構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="5962b-120">Example 3: Disable session configurations by name</span></span>

<span data-ttu-id="5962b-121">この例では、Microsoft で始まる名前を持つすべてのセッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5962b-121">This example disables all session configurations that have names that begin with Microsoft.</span></span> <span data-ttu-id="5962b-122">**Force** パラメーターを指定すると、コマンドレットからのすべてのユーザープロンプトが抑制されます。</span><span class="sxs-lookup"><span data-stu-id="5962b-122">The **Force** parameter suppresses all user prompts from the cmdlet.</span></span>

```powershell
Disable-PSSessionConfiguration -Name Microsoft* -Force
```

### <span data-ttu-id="5962b-123">例 4: パイプラインを使用してセッション構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="5962b-123">Example 4: Disable session configurations by using the pipeline</span></span>

<span data-ttu-id="5962b-124">この例では、 **MaintenanceShell** および **adminshell** セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5962b-124">This example disables the **MaintenanceShell** and **AdminShell** session configurations.</span></span> <span data-ttu-id="5962b-125">パイプライン演算子 (|) は、の結果をに送信し `Get-PSSessionConfiguration` `Disable-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="5962b-125">The pipeline operator (|) sends the results of a `Get-PSSessionConfiguration` to `Disable-PSSessionConfiguration`.</span></span>

```powershell
Get-PSSessionConfiguration -Name MaintenanceShell, AdminShell | Disable-PSSessionConfiguration
```

### <span data-ttu-id="5962b-126">例 5: セッション構成を無効にした場合の影響</span><span class="sxs-lookup"><span data-stu-id="5962b-126">Example 5: Effects of disabling a session configuration</span></span>

<span data-ttu-id="5962b-127">この例では、実行前と実行後のアクセス許可、 `Disable-PSSessionConfiguration` およびセッション構成を無効にした場合の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="5962b-127">This example shows the permissions before and after running `Disable-PSSessionConfiguration` and the effect of disabling a session configuration.</span></span>

```
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> Disable-PSSessionConfiguration -Name MaintenanceShell -Force
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       Everyone AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> New-PSSession -ComputerName localhost -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message : Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

> [!NOTE]
> <span data-ttu-id="5962b-128">構成を無効にしても、コマンドレットを使用して構成を変更することはできません `Set-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="5962b-128">Disabling the configuration does not prevent you from changing the configuration using the `Set-PSSessionConfiguration` cmdlet.</span></span> <span data-ttu-id="5962b-129">構成の使用は禁止されています。</span><span class="sxs-lookup"><span data-stu-id="5962b-129">It only prevents use of the configuration.</span></span>

## <span data-ttu-id="5962b-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5962b-130">PARAMETERS</span></span>

### <span data-ttu-id="5962b-131">-Force</span><span class="sxs-lookup"><span data-stu-id="5962b-131">-Force</span></span>

<span data-ttu-id="5962b-132">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5962b-132">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="5962b-133">-Name</span><span class="sxs-lookup"><span data-stu-id="5962b-133">-Name</span></span>

<span data-ttu-id="5962b-134">無効にするセッション構成の名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5962b-134">Specifies an array of names of session configurations to disable.</span></span> <span data-ttu-id="5962b-135">1 つまたは複数の構成名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5962b-135">Enter one or more configuration names.</span></span> <span data-ttu-id="5962b-136">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5962b-136">Wildcard characters are permitted.</span></span> <span data-ttu-id="5962b-137">パイプを使用して、構成名またはセッション構成オブジェクトを含む文字列をにパイプすることもでき `Disable-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="5962b-137">You can also pipe a string that contains a configuration name or a session configuration object to `Disable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="5962b-138">このパラメーターを省略すると、は、 `Disable-PSSessionConfiguration` Microsoft PowerShell セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5962b-138">If you omit this parameter, `Disable-PSSessionConfiguration` disables the Microsoft.PowerShell session configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="5962b-139">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="5962b-139">-NoServiceRestart</span></span>

<span data-ttu-id="5962b-140">WSMan サービスの再起動を防止するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5962b-140">Used to prevent the restart of the WSMan service.</span></span> <span data-ttu-id="5962b-141">構成を無効にするために、サービスを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5962b-141">It is not necessary to restart the service to disable the configuration.</span></span>

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

### <span data-ttu-id="5962b-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5962b-142">-Confirm</span></span>

<span data-ttu-id="5962b-143">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5962b-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5962b-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5962b-144">-WhatIf</span></span>

<span data-ttu-id="5962b-145">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="5962b-145">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5962b-146">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5962b-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5962b-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5962b-147">CommonParameters</span></span>

<span data-ttu-id="5962b-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5962b-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5962b-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5962b-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5962b-150">入力</span><span class="sxs-lookup"><span data-stu-id="5962b-150">INPUTS</span></span>

### <span data-ttu-id="5962b-151">Register-pssessionconfiguration、System.string のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="5962b-151">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="5962b-152">このコマンドレットには、セッション構成オブジェクトまたはセッション構成の名前を含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="5962b-152">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="5962b-153">出力</span><span class="sxs-lookup"><span data-stu-id="5962b-153">OUTPUTS</span></span>

### <span data-ttu-id="5962b-154">なし</span><span class="sxs-lookup"><span data-stu-id="5962b-154">None</span></span>

<span data-ttu-id="5962b-155">このコマンドレットはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="5962b-155">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="5962b-156">注</span><span class="sxs-lookup"><span data-stu-id="5962b-156">NOTES</span></span>

<span data-ttu-id="5962b-157">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5962b-157">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="5962b-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5962b-158">RELATED LINKS</span></span>

[<span data-ttu-id="5962b-159">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5962b-159">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="5962b-160">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5962b-160">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="5962b-161">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="5962b-161">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="5962b-162">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5962b-162">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="5962b-163">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5962b-163">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="5962b-164">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="5962b-164">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="5962b-165">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5962b-165">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="5962b-166">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="5962b-166">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="5962b-167">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="5962b-167">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="5962b-168">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="5962b-168">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
