---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSSessionConfiguration
ms.openlocfilehash: 86650f33f376ccb7d1428836c9d0070e749cf0ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604954"
---
# <span data-ttu-id="f16ef-102">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f16ef-102">Enable-PSSessionConfiguration</span></span>

## <span data-ttu-id="f16ef-103">概要</span><span class="sxs-lookup"><span data-stu-id="f16ef-103">SYNOPSIS</span></span>
<span data-ttu-id="f16ef-104">ローカル コンピューター上のセッション構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f16ef-104">Enables the session configurations on the local computer.</span></span>

## <span data-ttu-id="f16ef-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f16ef-105">SYNTAX</span></span>

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f16ef-106">Description</span><span class="sxs-lookup"><span data-stu-id="f16ef-106">DESCRIPTION</span></span>

<span data-ttu-id="f16ef-107">`Enable-PSSessionConfiguration`コマンドレットで `Disable-PSSessionConfiguration` は、または `Disable-PSRemoting` コマンドレットやの **accessmode** パラメーターを使用して、無効になっている登録済みのセッション構成を有効にし `Register-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="f16ef-107">The `Enable-PSSessionConfiguration` cmdlet enables registered session configurations that have been disabled, such as by using the `Disable-PSSessionConfiguration` or `Disable-PSRemoting` cmdlets, or the **AccessMode** parameter of `Register-PSSessionConfiguration`.</span></span> <span data-ttu-id="f16ef-108">これは、ユーザーに応じてカスタマイズされたセッション構成を管理するために、システム管理者向けに設計された高度なコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="f16ef-108">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="f16ef-109">パラメーターを指定しない場合、では、 `Enable-PSSessionConfiguration` セッションに使用される既定の構成である、Microsoft の PowerShell 構成が有効になり **ます。**</span><span class="sxs-lookup"><span data-stu-id="f16ef-109">Without parameters, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** configuration, which is the default configuration that is used for sessions.</span></span>

<span data-ttu-id="f16ef-110">`Enable-PSSessionConfiguration` 影響を受けるセッション構成のセキュリティ記述子から **Deny_All** 設定を削除し、任意の IP アドレスで要求を受け入れるリスナーをオンにして、WinRM サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-110">`Enable-PSSessionConfiguration` removes the **Deny_All** setting from the security descriptor of the affected session configurations, turns on the listener that accepts requests on any IP address, and restarts the WinRM service.</span></span> <span data-ttu-id="f16ef-111">PowerShell 3.0 以降では、 `Enable-PSSessionConfiguration` セッション構成 () の **Enabled** プロパティの値も True に設定され `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ます。</span><span class="sxs-lookup"><span data-stu-id="f16ef-111">Beginning in PowerShell 3.0, `Enable-PSSessionConfiguration` also sets the value of the **Enabled** property of the session configuration (`WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled`) to True.</span></span> <span data-ttu-id="f16ef-112">ただし、では、 `Enable-PSSessionConfiguration`  `AccessMode=Local` ローカルコンピューターのユーザーのみがセッション構成を使用できるようにする Network_Deny_All () セキュリティ記述子の設定が削除または変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f16ef-112">However, `Enable-PSSessionConfiguration` does not remove or change the **Network_Deny_All** (`AccessMode=Local`) security descriptor setting that allows only users of the local computer to use to the session configuration.</span></span>

## <span data-ttu-id="f16ef-113">例</span><span class="sxs-lookup"><span data-stu-id="f16ef-113">EXAMPLES</span></span>

### <span data-ttu-id="f16ef-114">例 1: 既定のセッションを再度有効にする</span><span class="sxs-lookup"><span data-stu-id="f16ef-114">Example 1: Re-enable the default session</span></span>

<span data-ttu-id="f16ef-115">この例では、コンピューター上の **Microsoft PowerShell** の既定のセッション構成を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="f16ef-115">This example re-enables the **Microsoft.PowerShell** default session configuration on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration
```

### <span data-ttu-id="f16ef-116">例 2: 指定されたセッションを再度有効にする</span><span class="sxs-lookup"><span data-stu-id="f16ef-116">Example 2: Re-enable specified sessions</span></span>

<span data-ttu-id="f16ef-117">この例では、コンピューター上の **MaintenanceShell** および **adminshell** セッション構成を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="f16ef-117">This example re-enables the **MaintenanceShell** and **AdminShell** session configurations on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### <span data-ttu-id="f16ef-118">例 3: すべてのセッションを再度有効にする</span><span class="sxs-lookup"><span data-stu-id="f16ef-118">Example 3: Re-enable the all sessions</span></span>

<span data-ttu-id="f16ef-119">この例では、コンピューター上のすべてのセッション構成を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="f16ef-119">This example re-enables all session configurations on the computer.</span></span> <span data-ttu-id="f16ef-120">これらのコマンドは同等です。</span><span class="sxs-lookup"><span data-stu-id="f16ef-120">These commands are equivalent.</span></span>
<span data-ttu-id="f16ef-121">そのため、いずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f16ef-121">Therefore, you can use either.</span></span>

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

<span data-ttu-id="f16ef-122">`Enable-PSSessionConfiguration` 既に有効になっているセッション構成を有効にした場合、ではエラーは生成されません。</span><span class="sxs-lookup"><span data-stu-id="f16ef-122">`Enable-PSSessionConfiguration` does not generate an error if you enable a session configuration that is already enabled.</span></span>

### <span data-ttu-id="f16ef-123">例 4: セッションを再度有効にし、新しいセキュリティ記述子を指定する</span><span class="sxs-lookup"><span data-stu-id="f16ef-123">Example 4: Re-enable a session and specify a new security descriptor</span></span>

<span data-ttu-id="f16ef-124">この例では、 **MaintenanceShell** セッション構成を再度有効にし、構成の新しいセキュリティ記述子を指定します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-124">This example re-enables the **MaintenanceShell** session configuration and specifies a new security descriptor for the configuration.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## <span data-ttu-id="f16ef-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f16ef-125">PARAMETERS</span></span>

### <span data-ttu-id="f16ef-126">-Force</span><span class="sxs-lookup"><span data-stu-id="f16ef-126">-Force</span></span>

<span data-ttu-id="f16ef-127">コマンドレットによって確認メッセージが表示されないことを示し、プロンプトを表示せずに WinRM サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-127">Indicates that the cmdlet does not prompt you for confirmation, and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="f16ef-128">サービスを再起動すると、構成の変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="f16ef-128">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="f16ef-129">再起動を回避し、再起動メッセージを表示しないようにするには、**NoServiceRestart** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-129">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="f16ef-130">-Name</span><span class="sxs-lookup"><span data-stu-id="f16ef-130">-Name</span></span>

<span data-ttu-id="f16ef-131">有効にするセッション構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-131">Specifies the names of session configurations to enable.</span></span> <span data-ttu-id="f16ef-132">1 つまたは複数の構成名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-132">Enter one or more configuration names.</span></span>
<span data-ttu-id="f16ef-133">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f16ef-133">Wildcard characters are permitted.</span></span>

<span data-ttu-id="f16ef-134">パイプを使用して、構成名またはセッション構成オブジェクトを含む文字列をにパイプすることもでき `Enable-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="f16ef-134">You can also pipe a string that contains a configuration name or a session configuration object to `Enable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="f16ef-135">このパラメーターを省略すると、に `Enable-PSSessionConfiguration` よって、 **Microsoft PowerShell** セッション構成が有効になります。</span><span class="sxs-lookup"><span data-stu-id="f16ef-135">If you omit this parameter, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** session configuration.</span></span>

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

### <span data-ttu-id="f16ef-136">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="f16ef-136">-NoServiceRestart</span></span>

<span data-ttu-id="f16ef-137">コマンドレットがサービスを再起動しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-137">Indicates that the cmdlet does not restart the service.</span></span>

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

### <span data-ttu-id="f16ef-138">-Security記述子 Sddl</span><span class="sxs-lookup"><span data-stu-id="f16ef-138">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="f16ef-139">このコマンドレットがセッション構成のセキュリティ記述子を置き換えるセキュリティ記述子を指定します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-139">Specifies a security descriptor with which this cmdlet replaces the security descriptor on the session configuration.</span></span>

<span data-ttu-id="f16ef-140">このパラメーターを省略した場合、は `Enable-PSSessionConfiguration` セキュリティ記述子からすべて拒否項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-140">If you omit this parameter, `Enable-PSSessionConfiguration` only deletes the deny all item from the security descriptor.</span></span>

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

### <span data-ttu-id="f16ef-141">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="f16ef-141">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="f16ef-142">コンピューターがパブリックネットワーク上にある場合に、このコマンドレットによってセッション構成が有効になることを示します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-142">Indicates that this cmdlet enables the session configuration when the computer is on a public network.</span></span> <span data-ttu-id="f16ef-143">このパラメーターは、同じローカル サブネット内のコンピューターに対してのみリモート アクセスを許可する、パブリック ネットワークのファイアウォール規則を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f16ef-143">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="f16ef-144">既定では、は `Enable-PSSessionConfiguration` パブリックネットワークで失敗します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-144">By default, `Enable-PSSessionConfiguration` fails on a public network.</span></span>

<span data-ttu-id="f16ef-145">このパラメーターは、Windows オペレーティングシステムのクライアントバージョン向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="f16ef-145">This parameter is designed for client versions of the Windows operating system.</span></span> <span data-ttu-id="f16ef-146">Windows オペレーティングシステムのサーバーバージョンには、パブリックネットワーク用のローカルサブネットファイアウォール規則があります。</span><span class="sxs-lookup"><span data-stu-id="f16ef-146">Server versions of the Windows operating system have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="f16ef-147">ただし、ローカルサブネットファイアウォールルールがサーバーバージョンの Windows オペレーティングシステムで無効になっている場合は、このパラメーターによって再度有効になります。</span><span class="sxs-lookup"><span data-stu-id="f16ef-147">However, if the local subnet firewall rule is disabled on a server version of the Windows operating system, this parameter re-enables it.</span></span>

<span data-ttu-id="f16ef-148">ローカルサブネットの制限を削除し、パブリックネットワーク上のすべての場所からのリモートアクセスを有効にするには、 `Set-NetFirewallRule` NetSecurity モジュールのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-148">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="f16ef-149">詳細については、「`Enable-PSRemoting`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f16ef-149">For more information, see `Enable-PSRemoting`.</span></span>

<span data-ttu-id="f16ef-150">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f16ef-150">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f16ef-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f16ef-151">-Confirm</span></span>

<span data-ttu-id="f16ef-152">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f16ef-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f16ef-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f16ef-153">-WhatIf</span></span>

<span data-ttu-id="f16ef-154">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="f16ef-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f16ef-155">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f16ef-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f16ef-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f16ef-156">CommonParameters</span></span>

<span data-ttu-id="f16ef-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f16ef-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f16ef-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f16ef-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f16ef-159">入力</span><span class="sxs-lookup"><span data-stu-id="f16ef-159">INPUTS</span></span>

### <span data-ttu-id="f16ef-160">Register-pssessionconfiguration、System.string のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="f16ef-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="f16ef-161">このコマンドレットには、セッション構成オブジェクトまたはセッション構成の名前を含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="f16ef-161">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="f16ef-162">出力</span><span class="sxs-lookup"><span data-stu-id="f16ef-162">OUTPUTS</span></span>

### <span data-ttu-id="f16ef-163">なし</span><span class="sxs-lookup"><span data-stu-id="f16ef-163">None</span></span>

<span data-ttu-id="f16ef-164">このコマンドレットはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="f16ef-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="f16ef-165">注</span><span class="sxs-lookup"><span data-stu-id="f16ef-165">NOTES</span></span>

<span data-ttu-id="f16ef-166">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f16ef-166">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="f16ef-167">このコマンドレットを使用するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f16ef-167">To use this cmdlet, you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="f16ef-168">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f16ef-168">RELATED LINKS</span></span>

[<span data-ttu-id="f16ef-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f16ef-169">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="f16ef-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f16ef-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="f16ef-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f16ef-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="f16ef-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="f16ef-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="f16ef-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f16ef-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="f16ef-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f16ef-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="f16ef-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f16ef-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="f16ef-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f16ef-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="f16ef-177">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f16ef-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="f16ef-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="f16ef-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="f16ef-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="f16ef-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
