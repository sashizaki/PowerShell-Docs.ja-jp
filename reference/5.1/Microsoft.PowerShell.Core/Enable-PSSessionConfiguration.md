---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSSessionConfiguration
ms.openlocfilehash: f44da41a08746ddb5b4396dbd263a671edb470bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212075"
---
# <span data-ttu-id="2a904-103">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a904-103">Enable-PSSessionConfiguration</span></span>

## <span data-ttu-id="2a904-104">概要</span><span class="sxs-lookup"><span data-stu-id="2a904-104">SYNOPSIS</span></span>
<span data-ttu-id="2a904-105">ローカル コンピューター上のセッション構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a904-105">Enables the session configurations on the local computer.</span></span>

## <span data-ttu-id="2a904-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2a904-106">SYNTAX</span></span>

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2a904-107">Description</span><span class="sxs-lookup"><span data-stu-id="2a904-107">DESCRIPTION</span></span>

<span data-ttu-id="2a904-108">`Enable-PSSessionConfiguration`コマンドレットで `Disable-PSSessionConfiguration` は、または `Disable-PSRemoting` コマンドレットやの **accessmode** パラメーターを使用して、無効になっている登録済みのセッション構成を有効にし `Register-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="2a904-108">The `Enable-PSSessionConfiguration` cmdlet enables registered session configurations that have been disabled, such as by using the `Disable-PSSessionConfiguration` or `Disable-PSRemoting` cmdlets, or the **AccessMode** parameter of `Register-PSSessionConfiguration`.</span></span> <span data-ttu-id="2a904-109">これは、ユーザーに応じてカスタマイズされたセッション構成を管理するために、システム管理者向けに設計された高度なコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="2a904-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="2a904-110">パラメーターを指定しない場合、では、 `Enable-PSSessionConfiguration` セッションに使用される既定の構成である、Microsoft の PowerShell 構成が有効になり **ます。**</span><span class="sxs-lookup"><span data-stu-id="2a904-110">Without parameters, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** configuration, which is the default configuration that is used for sessions.</span></span>

<span data-ttu-id="2a904-111">`Enable-PSSessionConfiguration` 影響を受けるセッション構成のセキュリティ記述子から **Deny_All** 設定を削除し、任意の IP アドレスで要求を受け入れるリスナーをオンにして、WinRM サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2a904-111">`Enable-PSSessionConfiguration` removes the **Deny_All** setting from the security descriptor of the affected session configurations, turns on the listener that accepts requests on any IP address, and restarts the WinRM service.</span></span> <span data-ttu-id="2a904-112">PowerShell 3.0 以降では、 `Enable-PSSessionConfiguration` セッション構成 () の **Enabled** プロパティの値も True に設定され `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ます。</span><span class="sxs-lookup"><span data-stu-id="2a904-112">Beginning in PowerShell 3.0, `Enable-PSSessionConfiguration` also sets the value of the **Enabled** property of the session configuration (`WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled`) to True.</span></span> <span data-ttu-id="2a904-113">ただし、では、 `Enable-PSSessionConfiguration` **Network_Deny_All** `AccessMode=Local` ローカルコンピューターのユーザーのみがセッション構成を使用できるようにする Network_Deny_All () セキュリティ記述子の設定が削除または変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2a904-113">However, `Enable-PSSessionConfiguration` does not remove or change the **Network_Deny_All** (`AccessMode=Local`) security descriptor setting that allows only users of the local computer to use to the session configuration.</span></span>

## <span data-ttu-id="2a904-114">例</span><span class="sxs-lookup"><span data-stu-id="2a904-114">EXAMPLES</span></span>

### <span data-ttu-id="2a904-115">例 1: 既定のセッションを再度有効にする</span><span class="sxs-lookup"><span data-stu-id="2a904-115">Example 1: Re-enable the default session</span></span>

<span data-ttu-id="2a904-116">この例では、コンピューター上の **Microsoft PowerShell** の既定のセッション構成を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a904-116">This example re-enables the **Microsoft.PowerShell** default session configuration on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration
```

### <span data-ttu-id="2a904-117">例 2: 指定されたセッションを再度有効にする</span><span class="sxs-lookup"><span data-stu-id="2a904-117">Example 2: Re-enable specified sessions</span></span>

<span data-ttu-id="2a904-118">この例では、コンピューター上の **MaintenanceShell** および **adminshell** セッション構成を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a904-118">This example re-enables the **MaintenanceShell** and **AdminShell** session configurations on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### <span data-ttu-id="2a904-119">例 3: すべてのセッションを再度有効にする</span><span class="sxs-lookup"><span data-stu-id="2a904-119">Example 3: Re-enable the all sessions</span></span>

<span data-ttu-id="2a904-120">この例では、コンピューター上のすべてのセッション構成を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a904-120">This example re-enables all session configurations on the computer.</span></span> <span data-ttu-id="2a904-121">これらのコマンドは同等です。</span><span class="sxs-lookup"><span data-stu-id="2a904-121">These commands are equivalent.</span></span>
<span data-ttu-id="2a904-122">そのため、いずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a904-122">Therefore, you can use either.</span></span>

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

<span data-ttu-id="2a904-123">`Enable-PSSessionConfiguration` 既に有効になっているセッション構成を有効にした場合、ではエラーは生成されません。</span><span class="sxs-lookup"><span data-stu-id="2a904-123">`Enable-PSSessionConfiguration` does not generate an error if you enable a session configuration that is already enabled.</span></span>

### <span data-ttu-id="2a904-124">例 4: セッションを再度有効にし、新しいセキュリティ記述子を指定する</span><span class="sxs-lookup"><span data-stu-id="2a904-124">Example 4: Re-enable a session and specify a new security descriptor</span></span>

<span data-ttu-id="2a904-125">この例では、 **MaintenanceShell** セッション構成を再度有効にし、構成の新しいセキュリティ記述子を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a904-125">This example re-enables the **MaintenanceShell** session configuration and specifies a new security descriptor for the configuration.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## <span data-ttu-id="2a904-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2a904-126">PARAMETERS</span></span>

### <span data-ttu-id="2a904-127">-Force</span><span class="sxs-lookup"><span data-stu-id="2a904-127">-Force</span></span>

<span data-ttu-id="2a904-128">コマンドレットによって確認メッセージが表示されないことを示し、プロンプトを表示せずに WinRM サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2a904-128">Indicates that the cmdlet does not prompt you for confirmation, and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="2a904-129">サービスを再起動すると、構成の変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="2a904-129">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="2a904-130">再起動を回避し、再起動メッセージを表示しないようにするには、 **NoServiceRestart** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a904-130">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="2a904-131">-Name</span><span class="sxs-lookup"><span data-stu-id="2a904-131">-Name</span></span>

<span data-ttu-id="2a904-132">有効にするセッション構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a904-132">Specifies the names of session configurations to enable.</span></span> <span data-ttu-id="2a904-133">1 つまたは複数の構成名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2a904-133">Enter one or more configuration names.</span></span>
<span data-ttu-id="2a904-134">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a904-134">Wildcard characters are permitted.</span></span>

<span data-ttu-id="2a904-135">パイプを使用して、構成名またはセッション構成オブジェクトを含む文字列をにパイプすることもでき `Enable-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="2a904-135">You can also pipe a string that contains a configuration name or a session configuration object to `Enable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="2a904-136">このパラメーターを省略すると、に `Enable-PSSessionConfiguration` よって、 **Microsoft PowerShell** セッション構成が有効になります。</span><span class="sxs-lookup"><span data-stu-id="2a904-136">If you omit this parameter, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** session configuration.</span></span>

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

### <span data-ttu-id="2a904-137">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="2a904-137">-NoServiceRestart</span></span>

<span data-ttu-id="2a904-138">コマンドレットがサービスを再起動しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="2a904-138">Indicates that the cmdlet does not restart the service.</span></span>

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

### <span data-ttu-id="2a904-139">-Security記述子 Sddl</span><span class="sxs-lookup"><span data-stu-id="2a904-139">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="2a904-140">このコマンドレットがセッション構成のセキュリティ記述子を置き換えるセキュリティ記述子を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a904-140">Specifies a security descriptor with which this cmdlet replaces the security descriptor on the session configuration.</span></span>

<span data-ttu-id="2a904-141">このパラメーターを省略した場合、は `Enable-PSSessionConfiguration` セキュリティ記述子からすべて拒否項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="2a904-141">If you omit this parameter, `Enable-PSSessionConfiguration` only deletes the deny all item from the security descriptor.</span></span>

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

### <span data-ttu-id="2a904-142">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="2a904-142">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="2a904-143">コンピューターがパブリックネットワーク上にある場合に、このコマンドレットによってセッション構成が有効になることを示します。</span><span class="sxs-lookup"><span data-stu-id="2a904-143">Indicates that this cmdlet enables the session configuration when the computer is on a public network.</span></span> <span data-ttu-id="2a904-144">このパラメーターは、同じローカル サブネット内のコンピューターに対してのみリモート アクセスを許可する、パブリック ネットワークのファイアウォール規則を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a904-144">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="2a904-145">既定では、は `Enable-PSSessionConfiguration` パブリックネットワークで失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a904-145">By default, `Enable-PSSessionConfiguration` fails on a public network.</span></span>

<span data-ttu-id="2a904-146">このパラメーターは、Windows オペレーティングシステムのクライアントバージョン向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="2a904-146">This parameter is designed for client versions of the Windows operating system.</span></span> <span data-ttu-id="2a904-147">Windows オペレーティングシステムのサーバーバージョンには、パブリックネットワーク用のローカルサブネットファイアウォール規則があります。</span><span class="sxs-lookup"><span data-stu-id="2a904-147">Server versions of the Windows operating system have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="2a904-148">ただし、ローカルサブネットファイアウォールルールがサーバーバージョンの Windows オペレーティングシステムで無効になっている場合は、このパラメーターによって再度有効になります。</span><span class="sxs-lookup"><span data-stu-id="2a904-148">However, if the local subnet firewall rule is disabled on a server version of the Windows operating system, this parameter re-enables it.</span></span>

<span data-ttu-id="2a904-149">ローカルサブネットの制限を削除し、パブリックネットワーク上のすべての場所からのリモートアクセスを有効にするには、 `Set-NetFirewallRule` NetSecurity モジュールのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a904-149">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="2a904-150">詳細については、「`Enable-PSRemoting`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a904-150">For more information, see `Enable-PSRemoting`.</span></span>

<span data-ttu-id="2a904-151">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2a904-151">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2a904-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2a904-152">-Confirm</span></span>

<span data-ttu-id="2a904-153">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a904-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2a904-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2a904-154">-WhatIf</span></span>

<span data-ttu-id="2a904-155">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2a904-155">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2a904-156">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2a904-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2a904-157">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a904-157">CommonParameters</span></span>

<span data-ttu-id="2a904-158">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2a904-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2a904-159">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a904-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2a904-160">入力</span><span class="sxs-lookup"><span data-stu-id="2a904-160">INPUTS</span></span>

### <span data-ttu-id="2a904-161">Register-pssessionconfiguration、System.string のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="2a904-161">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="2a904-162">このコマンドレットには、セッション構成オブジェクトまたはセッション構成の名前を含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="2a904-162">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="2a904-163">出力</span><span class="sxs-lookup"><span data-stu-id="2a904-163">OUTPUTS</span></span>

### <span data-ttu-id="2a904-164">なし</span><span class="sxs-lookup"><span data-stu-id="2a904-164">None</span></span>

<span data-ttu-id="2a904-165">このコマンドレットはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="2a904-165">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="2a904-166">注</span><span class="sxs-lookup"><span data-stu-id="2a904-166">NOTES</span></span>

<span data-ttu-id="2a904-167">このコマンドレットを使用するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a904-167">To use this cmdlet, you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="2a904-168">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2a904-168">RELATED LINKS</span></span>

[<span data-ttu-id="2a904-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a904-169">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="2a904-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a904-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="2a904-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2a904-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="2a904-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="2a904-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="2a904-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a904-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="2a904-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a904-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="2a904-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2a904-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="2a904-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a904-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="2a904-177">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="2a904-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="2a904-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="2a904-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="2a904-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="2a904-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
