---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: c2f88431c0a09a2d4093c6523467a812812c10bc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603037"
---
# <span data-ttu-id="2fc96-102">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2fc96-102">Disable-PSSessionConfiguration</span></span>

## <span data-ttu-id="2fc96-103">概要</span><span class="sxs-lookup"><span data-stu-id="2fc96-103">SYNOPSIS</span></span>
<span data-ttu-id="2fc96-104">ローカル コンピューター上のセッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc96-104">Disables session configurations on the local computer.</span></span>

## <span data-ttu-id="2fc96-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2fc96-105">SYNTAX</span></span>

```
Disable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2fc96-106">Description</span><span class="sxs-lookup"><span data-stu-id="2fc96-106">DESCRIPTION</span></span>

<span data-ttu-id="2fc96-107">`Disable-PSSessionConfiguration`コマンドレットは、ローカルコンピューター上のセッション構成を無効にします。これにより、すべてのユーザーがセッション構成を使用してローカルコンピューター上にユーザー管理セッション (pssession) を作成できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2fc96-107">The `Disable-PSSessionConfiguration` cmdlet disables session configurations on the local computer, which prevents all users from using the session configurations to create a user-managed sessions (**PSSessions**) on the local computer.</span></span> <span data-ttu-id="2fc96-108">これは、ユーザーに応じてカスタマイズされたセッション構成を管理するために、システム管理者向けに設計された高度なコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="2fc96-108">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="2fc96-109">PowerShell 3.0 以降では、 `Disable-PSSessionConfiguration` コマンドレットにより、セッション構成 () の **Enabled** 設定が False に設定され `WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled` ます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-109">Starting in PowerShell 3.0, the `Disable-PSSessionConfiguration` cmdlet sets the **Enabled** setting of the session configuration (`WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled`) to False.</span></span>

<span data-ttu-id="2fc96-110">PowerShell 2.0 では、 `Disable-PSSessionConfiguration` コマンドレットは、登録されている1つ以上のセッション構成のセキュリティ記述子に **Deny_All** エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fc96-110">In PowerShell 2.0, the `Disable-PSSessionConfiguration` cmdlet adds a **Deny_All** entry to the security descriptor of one or more registered session configurations.</span></span>

<span data-ttu-id="2fc96-111">パラメーターを指定しない場合は、 `Disable-PSSessionConfiguration` セッションに使用される既定の構成である、 **Microsoft PowerShell** 構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc96-111">Without parameters, `Disable-PSSessionConfiguration` disables the **Microsoft.PowerShell** configuration, the default configuration used for sessions.</span></span> <span data-ttu-id="2fc96-112">ユーザーが別の構成を指定していない限り、ローカル ユーザーとリモート ユーザーの両方がコンピューターに接続するセッションをできないように、効果的に防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-112">Unless the user specifies a different configuration, both local and remote users are effectively prevented from creating any sessions that connect to the computer.</span></span>

<span data-ttu-id="2fc96-113">コンピューター上のすべてのセッション構成を無効にするには、を使用 `Disable-PSRemoting` します。</span><span class="sxs-lookup"><span data-stu-id="2fc96-113">To disable all session configurations on the computer, use `Disable-PSRemoting`.</span></span>

## <span data-ttu-id="2fc96-114">例</span><span class="sxs-lookup"><span data-stu-id="2fc96-114">EXAMPLES</span></span>

### <span data-ttu-id="2fc96-115">例 1: 既定の構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="2fc96-115">Example 1: Disable the default configuration</span></span>

<span data-ttu-id="2fc96-116">この例では、Microsoft PowerShell セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc96-116">This example disables the Microsoft.PowerShell session configuration.</span></span>

```powershell
Disable-PSSessionConfiguration
```

### <span data-ttu-id="2fc96-117">例 2: 登録されているすべてのセッション構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="2fc96-117">Example 2: Disable all registered session configurations</span></span>

<span data-ttu-id="2fc96-118">この例では、コンピューター上で登録されているすべてのセッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc96-118">This example disables all registered session configurations on the computer.</span></span>

```powershell
Disable-PSSessionConfiguration -Name *
```

### <span data-ttu-id="2fc96-119">例 3: 名前でセッション構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="2fc96-119">Example 3: Disable session configurations by name</span></span>

<span data-ttu-id="2fc96-120">この例では、Microsoft で始まる名前を持つすべてのセッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc96-120">This example disables all session configurations that have names that begin with Microsoft.</span></span> <span data-ttu-id="2fc96-121">**Force** パラメーターを指定すると、コマンドレットからのすべてのユーザープロンプトが抑制されます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-121">The **Force** parameter suppresses all user prompts from the cmdlet.</span></span>

```powershell
Disable-PSSessionConfiguration -Name Microsoft* -Force
```

### <span data-ttu-id="2fc96-122">例 4: パイプラインを使用してセッション構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="2fc96-122">Example 4: Disable session configurations by using the pipeline</span></span>

<span data-ttu-id="2fc96-123">この例では、 **MaintenanceShell** および **adminshell** セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc96-123">This example disables the **MaintenanceShell** and **AdminShell** session configurations.</span></span> <span data-ttu-id="2fc96-124">パイプライン演算子 (|) は、の結果をに送信し `Get-PSSessionConfiguration` `Disable-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-124">The pipeline operator (|) sends the results of a `Get-PSSessionConfiguration` to `Disable-PSSessionConfiguration`.</span></span>

```powershell
Get-PSSessionConfiguration -Name MaintenanceShell, AdminShell | Disable-PSSessionConfiguration
```

### <span data-ttu-id="2fc96-125">例 5: セッション構成を無効にした場合の影響</span><span class="sxs-lookup"><span data-stu-id="2fc96-125">Example 5: Effects of disabling a session configuration</span></span>

<span data-ttu-id="2fc96-126">この例では、実行前と実行後のアクセス許可、 `Disable-PSSessionConfiguration` およびセッション構成を無効にした場合の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="2fc96-126">This example shows the permissions before and after running `Disable-PSSessionConfiguration` and the effect of disabling a session configuration.</span></span>

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
> <span data-ttu-id="2fc96-127">構成を無効にしても、コマンドレットを使用して構成を変更することはできません `Set-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="2fc96-127">Disabling the configuration does not prevent you from changing the configuration using the `Set-PSSessionConfiguration` cmdlet.</span></span> <span data-ttu-id="2fc96-128">構成の使用は禁止されています。</span><span class="sxs-lookup"><span data-stu-id="2fc96-128">It only prevents use of the configuration.</span></span>

## <span data-ttu-id="2fc96-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2fc96-129">PARAMETERS</span></span>

### <span data-ttu-id="2fc96-130">-Force</span><span class="sxs-lookup"><span data-stu-id="2fc96-130">-Force</span></span>

<span data-ttu-id="2fc96-131">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fc96-131">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="2fc96-132">-Name</span><span class="sxs-lookup"><span data-stu-id="2fc96-132">-Name</span></span>

<span data-ttu-id="2fc96-133">無効にするセッション構成の名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2fc96-133">Specifies an array of names of session configurations to disable.</span></span> <span data-ttu-id="2fc96-134">1 つまたは複数の構成名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc96-134">Enter one or more configuration names.</span></span> <span data-ttu-id="2fc96-135">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-135">Wildcard characters are permitted.</span></span> <span data-ttu-id="2fc96-136">パイプを使用して、構成名またはセッション構成オブジェクトを含む文字列をにパイプすることもでき `Disable-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-136">You can also pipe a string that contains a configuration name or a session configuration object to `Disable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="2fc96-137">このパラメーターを省略すると、は、 `Disable-PSSessionConfiguration` Microsoft PowerShell セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc96-137">If you omit this parameter, `Disable-PSSessionConfiguration` disables the Microsoft.PowerShell session configuration.</span></span>

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

### <span data-ttu-id="2fc96-138">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="2fc96-138">-NoServiceRestart</span></span>

<span data-ttu-id="2fc96-139">WSMan サービスの再起動を防止するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-139">Used to prevent the restart of the WSMan service.</span></span> <span data-ttu-id="2fc96-140">構成を無効にするために、サービスを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2fc96-140">It is not necessary to restart the service to disable the configuration.</span></span>

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

### <span data-ttu-id="2fc96-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2fc96-141">-Confirm</span></span>

<span data-ttu-id="2fc96-142">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2fc96-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2fc96-143">-WhatIf</span></span>

<span data-ttu-id="2fc96-144">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2fc96-144">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2fc96-145">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2fc96-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2fc96-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fc96-146">CommonParameters</span></span>

<span data-ttu-id="2fc96-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2fc96-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2fc96-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc96-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2fc96-149">入力</span><span class="sxs-lookup"><span data-stu-id="2fc96-149">INPUTS</span></span>

### <span data-ttu-id="2fc96-150">Register-pssessionconfiguration、System.string のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="2fc96-150">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="2fc96-151">このコマンドレットには、セッション構成オブジェクトまたはセッション構成の名前を含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-151">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="2fc96-152">出力</span><span class="sxs-lookup"><span data-stu-id="2fc96-152">OUTPUTS</span></span>

### <span data-ttu-id="2fc96-153">なし</span><span class="sxs-lookup"><span data-stu-id="2fc96-153">None</span></span>

<span data-ttu-id="2fc96-154">このコマンドレットはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="2fc96-154">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="2fc96-155">注</span><span class="sxs-lookup"><span data-stu-id="2fc96-155">NOTES</span></span>

<span data-ttu-id="2fc96-156">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2fc96-156">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="2fc96-157">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc96-157">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="2fc96-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2fc96-158">RELATED LINKS</span></span>

[<span data-ttu-id="2fc96-159">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2fc96-159">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="2fc96-160">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2fc96-160">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="2fc96-161">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2fc96-161">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="2fc96-162">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2fc96-162">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="2fc96-163">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2fc96-163">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="2fc96-164">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2fc96-164">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="2fc96-165">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2fc96-165">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="2fc96-166">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="2fc96-166">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="2fc96-167">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="2fc96-167">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="2fc96-168">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="2fc96-168">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
