---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: c3c3c0bbb0436ef2e6857adc35f83e627d03f4b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599712"
---
# <span data-ttu-id="8f952-102">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f952-102">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="8f952-103">概要</span><span class="sxs-lookup"><span data-stu-id="8f952-103">SYNOPSIS</span></span>
<span data-ttu-id="8f952-104">登録済みのセッション構成のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="8f952-104">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="8f952-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f952-105">SYNTAX</span></span>

### <span data-ttu-id="8f952-106">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="8f952-106">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8f952-107">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="8f952-107">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8f952-108">セッションのすべてのもの</span><span class="sxs-lookup"><span data-stu-id="8f952-108">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="8f952-109">Description</span><span class="sxs-lookup"><span data-stu-id="8f952-109">DESCRIPTION</span></span>

<span data-ttu-id="8f952-110">`Set-PSSessionConfiguration`コマンドレットは、ローカルコンピューター上のセッション構成のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="8f952-110">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="8f952-111">**Name** パラメーターを使用して、変更するセッション構成を識別します。</span><span class="sxs-lookup"><span data-stu-id="8f952-111">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="8f952-112">その他のパラメーターは、セッション構成のプロパティに新しい値を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="8f952-112">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="8f952-113">構成からプロパティ値を削除し、既定値を使用するには、対応するパラメーターに空の文字列 ("") または値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="8f952-113">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="8f952-114">PowerShell 3.0 以降では、セッション構成ファイルを使用してセッション構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="8f952-114">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="8f952-115">この機能を使用すれば、セッション構成を使用するセッションのプロパティの設定や変更を迷わず簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="8f952-115">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="8f952-116">セッション構成ファイルを指定するには、の **Path** パラメーターを使用し `Set-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="8f952-116">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="8f952-117">セッション構成ファイルの詳細については、「 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f952-117">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="8f952-118">セッション構成ファイルを作成および変更する方法の詳細については、コマンドレットを参照してください `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="8f952-118">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="8f952-119">セッション構成は、ローカルコンピューターに接続するリモート **セッション (pssession**) の環境を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f952-119">Session configurations define the environment of remote sessions (**PSSessions**) that connect to the local computer.</span></span> <span data-ttu-id="8f952-120">すべての **PSSession** は、セッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f952-120">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="8f952-121">セッション構成は、セッションで使用できるモジュール、実行を許可されているコマンドレット、言語モード、クォータ、タイムアウトなどの **PSSession** の機能を決定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-121">The session configuration determines the features of the **PSSession**, such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="8f952-122">セッション構成のセキュリティ記述子は、セッション構成を使用してローカルコンピューターに接続できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-122">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="8f952-123">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f952-123">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="8f952-124">セッション構成のプロパティを表示するに `Get-PSSessionConfiguration` は、コマンドレットまたは WSMan プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f952-124">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="8f952-125">WSMan プロバイダーの詳細については、「」と入力 `Get-Help WSMan` してください。</span><span class="sxs-lookup"><span data-stu-id="8f952-125">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="8f952-126">例</span><span class="sxs-lookup"><span data-stu-id="8f952-126">EXAMPLES</span></span>

### <span data-ttu-id="8f952-127">例 1: セッション構成を作成して変更する</span><span class="sxs-lookup"><span data-stu-id="8f952-127">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="8f952-128">この例では、構成からスタートアップスクリプトを追加および削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8f952-128">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="8f952-129">最初のコマンドは、 **Adminshell** 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="8f952-129">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="8f952-130">2番目のコマンドは、 `AdminConfig.ps1` 構成にスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f952-130">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="8f952-131">変更は、 **WinRM** を再起動すると有効になります。</span><span class="sxs-lookup"><span data-stu-id="8f952-131">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="8f952-132">3番目のコマンドは、 `AdminConfig.ps1` 構成からスクリプトを削除します。</span><span class="sxs-lookup"><span data-stu-id="8f952-132">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="8f952-133">例 2: 結果を表示する</span><span class="sxs-lookup"><span data-stu-id="8f952-133">Example 2: Display results</span></span>

<span data-ttu-id="8f952-134">この例では、 **MaximumReceivedObjectSizeMB** プロパティの値を20に増やしています。</span><span class="sxs-lookup"><span data-stu-id="8f952-134">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="8f952-135">このコマンドでは、 **WinRM** サービスの再起動を求めるメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-135">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="8f952-136">変更は、 **WinRM** サービスが再起動されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="8f952-136">The change is not effective until the **WinRM** service is restarted.</span></span>

```powershell
Set-PSSessionConfiguration -Name "IncObj" -MaximumReceivedObjectSizeMB 20
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\IncObj\InitializationParameters

ParamName                       ParamValue
---------                       ----------
psmaximumreceivedobjectsizemb   20

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

### <span data-ttu-id="8f952-137">例 3: さまざまな方法で結果を表示する</span><span class="sxs-lookup"><span data-stu-id="8f952-137">Example 3: Display results in different ways</span></span>

<span data-ttu-id="8f952-138">この例では、によって、 `Set-PSSessionConfiguration` **MaintenanceShell** セッション構成のスタートアップスクリプトがに変更され `Maintenance.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="8f952-138">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="8f952-139">出力には変更が示され、 **WinRM** サービスの再起動を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-139">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="8f952-140">これに対する応答は "y" (はい) です。</span><span class="sxs-lookup"><span data-stu-id="8f952-140">The response is "y" (yes).</span></span>

<span data-ttu-id="8f952-141">`Get-PSSessionConfiguration`**MaintenanceShell** セッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f952-141">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="8f952-142">パイプライン演算子 (|) は、コマンドの結果をに送信し `Format-List` ます。これにより、構成オブジェクトのすべてのプロパティがリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-142">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="8f952-143">次に、WSMan プロバイダーを使用して、 **MaintenanceShell** 構成の初期化パラメーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="8f952-143">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="8f952-144">`Get-ChildItem`(エイリアス `dir` )**MaintenanceShell** プラグインの **InitializationParameters** ノード内の子項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f952-144">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="8f952-145">WSMan プロバイダーの詳細については、「」と入力 `Get-Help wsman` してください。</span><span class="sxs-lookup"><span data-stu-id="8f952-145">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

```powershell
Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

```

```powershell
Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *
```

```Output
xmlns            : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
Name             : MaintenanceShell
Filename         : %windir%\system32\pwrshplugin.dll
SDKVersion       : 1
XmlRenderingType : text
lang             : en-US
PSVersion        : 2.0
startupscript    : c:\ps-test\Maintenance.ps1
ResourceUri      : http://schemas.microsoft.com/powershell/MaintenanceShell
SupportsOptions  : true
ExactMatch       : true
Capability       : {Shell}
Permission       :
```

```powershell
dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters
```

```Output
ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## <span data-ttu-id="8f952-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f952-146">PARAMETERS</span></span>

### <span data-ttu-id="8f952-147">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="8f952-147">-AccessMode</span></span>

<span data-ttu-id="8f952-148">セッション構成を有効化および無効化し、コンピューター上のリモート セッションまたはローカル セッションにセッション構成を使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-148">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="8f952-149">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f952-149">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8f952-150">無効にします。</span><span class="sxs-lookup"><span data-stu-id="8f952-150">Disabled.</span></span> <span data-ttu-id="8f952-151">セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8f952-151">Disables the session configuration.</span></span> <span data-ttu-id="8f952-152">コンピューターへのリモート アクセスまたはローカル アクセスに使用できません。</span><span class="sxs-lookup"><span data-stu-id="8f952-152">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="8f952-153">この値は、セッション構成の **Enabled** プロパティ ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) を **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-153">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="8f952-154">Local。</span><span class="sxs-lookup"><span data-stu-id="8f952-154">Local.</span></span> <span data-ttu-id="8f952-155">**Network_Deny_All** エントリをセッション構成のセキュリティ記述子に追加します。</span><span class="sxs-lookup"><span data-stu-id="8f952-155">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="8f952-156">ローカルコンピューターのユーザーは、セッション構成を使用して同じコンピューター上にローカルループバックセッションを作成できますが、リモートユーザーはアクセスを拒否されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-156">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="8f952-157">[Remote]\(リモート\)。</span><span class="sxs-lookup"><span data-stu-id="8f952-157">Remote.</span></span> <span data-ttu-id="8f952-158">**Deny_All** エントリと **Network_Deny_All** エントリをセッション構成のセキュリティ記述子から削除します。</span><span class="sxs-lookup"><span data-stu-id="8f952-158">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="8f952-159">ローカル コンピューターおよびリモート コンピューターのユーザーは、セッション構成を使用して、このコンピューターでセッションを作成し、コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8f952-159">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="8f952-160">既定値は **Remote** です。</span><span class="sxs-lookup"><span data-stu-id="8f952-160">The default value is **Remote**.</span></span>

<span data-ttu-id="8f952-161">他のコマンドレットでは、後でこのパラメーターの値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="8f952-161">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="8f952-162">たとえば、 `Enable-PSRemoting` コマンドレットは、コンピューター上のすべてのセッション構成を有効にし、それらへのリモートアクセスを許可し `Disable-PSRemoting` ます。また、コマンドレットは、コンピューター上のすべてのセッション構成へのローカルアクセスのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="8f952-162">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="8f952-163">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8f952-163">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSessionConfigurationAccessMode
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Local, Remote

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-164">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="8f952-164">-ApplicationBase</span></span>

<span data-ttu-id="8f952-165">\* **AssemblyName** パラメーターの値に指定されているアセンブリファイル (.dll) のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-165">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-166">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="8f952-166">-AssemblyName</span></span>

<span data-ttu-id="8f952-167">アセンブリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-167">Specifies the assembly name.</span></span> <span data-ttu-id="8f952-168">このコマンドレットは、アセンブリで定義されているクラスに基づいてセッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="8f952-168">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="8f952-169">セッション構成を定義するアセンブリ .dll ファイルのファイル名または完全パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="8f952-169">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="8f952-170">ファイル名だけを入力した場合は、 **ApplicationBase** パラメーターの値でパスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="8f952-170">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-171">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="8f952-171">-ConfigurationTypeName</span></span>

<span data-ttu-id="8f952-172">**AssemblyName** パラメーターのアセンブリで定義されているセッションの構成の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-172">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="8f952-173">指定する型は、**System.Management.Automation.Remoting.PSSessionConfiguration** クラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f952-173">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="8f952-174">アセンブリ名を指定する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="8f952-174">This parameter is required when you specify an assembly name.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-175">-Force</span><span class="sxs-lookup"><span data-stu-id="8f952-175">-Force</span></span>

<span data-ttu-id="8f952-176">すべてのユーザープロンプトを非表示にし、プロンプトを表示せずに **WinRM** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="8f952-176">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="8f952-177">サービスを再起動すると、構成の変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="8f952-177">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="8f952-178">再起動を回避し、再起動メッセージを表示しないようにするには、**NoServiceRestart** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f952-178">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="8f952-179">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="8f952-179">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="8f952-180">このコンピューターに1つのリモートコマンドで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-180">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="8f952-181">データ サイズはメガバイト (MB) 単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="8f952-181">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="8f952-182">既定値は 50 MB です。</span><span class="sxs-lookup"><span data-stu-id="8f952-182">The default is 50 MB.</span></span>

<span data-ttu-id="8f952-183">**Configurationtypename** パラメーターで指定された構成の種類でデータサイズの制限が定義されている場合、構成の種類の制限が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-183">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="8f952-184">このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-184">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-185">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="8f952-185">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="8f952-186">このコンピューターに1つのオブジェクトで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-186">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="8f952-187">データサイズをメガバイト単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="8f952-187">Enter the data size in megabytes.</span></span> <span data-ttu-id="8f952-188">既定値は 10 MB です。</span><span class="sxs-lookup"><span data-stu-id="8f952-188">The default is 10 MB.</span></span>

<span data-ttu-id="8f952-189">**Configurationtypename** パラメーターで指定された構成の種類でオブジェクトサイズの制限が定義されている場合、構成の種類の制限が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-189">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="8f952-190">このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-190">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-191">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="8f952-191">-ModulesToImport</span></span>

<span data-ttu-id="8f952-192">セッション構成を使用するセッションに自動的にインポートされたモジュールおよびスナップインを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-192">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="8f952-193">モジュール名およびスナップイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8f952-193">Enter the module and snap-in names.</span></span>

<span data-ttu-id="8f952-194">既定では、 **PowerShell** のみがセッションにインポートされますが、コマンドレットが除外されていない限り、 `Import-Module` および Add-PSSnapin コマンドレットを使用して、モジュールとスナップインをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8f952-194">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="8f952-195">このパラメーター値に指定されたモジュールは、セッション構成ファイル () で指定されたモジュールに追加され `New-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="8f952-195">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="8f952-196">ただし、セッション構成ファイル内の設定によって、モジュールでエクスポートされたコマンドが非表示になったり、ユーザーが使用できなくなったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="8f952-196">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="8f952-197">このパラメーター値に指定されたモジュールは、コマンドレットの **ModulesToImport** パラメーターを使用して指定されたモジュールの一覧に置き換わるもの `Register-PSSessionConfiguration` です。</span><span class="sxs-lookup"><span data-stu-id="8f952-197">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="8f952-198">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8f952-198">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-199">-Name</span><span class="sxs-lookup"><span data-stu-id="8f952-199">-Name</span></span>

<span data-ttu-id="8f952-200">変更するセッション構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-200">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="8f952-201">このパラメーターを使用してセッション構成の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f952-201">You cannot use this parameter to change the name of the session configuration.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-202">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="8f952-202">-NoServiceRestart</span></span>

<span data-ttu-id="8f952-203">は、 **WinRM** サービスを再起動せず、サービスの再起動を求めるメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="8f952-203">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="8f952-204">既定では、を実行すると `Set-PSSessionConfiguration` 、新しいセッション構成を有効にするために **WinRM** サービスを再起動するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8f952-204">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="8f952-205">**WinRM** サービスが再起動されるまで、新しいセッション構成は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="8f952-205">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="8f952-206">プロンプトを表示せずに **WinRM** サービスを再起動するには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f952-206">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="8f952-207">**WinRM** サービスを手動で再起動するには、コマンドレットを使用し `Restart-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="8f952-207">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="8f952-208">-Path</span><span class="sxs-lookup"><span data-stu-id="8f952-208">-Path</span></span>

<span data-ttu-id="8f952-209">セッション構成ファイル (.pssc) のパス (コマンドレットによって作成されたものなど) を指定します `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="8f952-209">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="8f952-210">パスを省略した場合、既定値は現在のディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="8f952-210">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="8f952-211">セッション構成ファイルを変更する方法の詳細については、コマンドレットのヘルプトピックを参照してください `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="8f952-211">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="8f952-212">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8f952-212">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SessionConfigurationFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-213">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="8f952-213">-PSVersion</span></span>

<span data-ttu-id="8f952-214">このセッション構成を使用するセッションの PowerShell のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-214">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="8f952-215">このパラメーターの値は、セッション構成ファイルの **PowerShellVersion** キーの値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-215">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="8f952-216">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8f952-216">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases: PowerShellVersion

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-217">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="8f952-217">-RunAsCredential</span></span>

<span data-ttu-id="8f952-218">セッションのコマンドの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-218">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="8f952-219">既定では、コマンドは現在のユーザーのアクセス許可で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-219">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="8f952-220">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8f952-220">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-221">-Security記述子 Sddl</span><span class="sxs-lookup"><span data-stu-id="8f952-221">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="8f952-222">構成に対して別のセキュリティ記述子定義言語 (SDDL) 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-222">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="8f952-223">この文字列によって、新しいセッション構成を使用するために必要なアクセス許可が決定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-223">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="8f952-224">セッションでセッション構成を使用するには、その構成に対して少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="8f952-224">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="8f952-225">構成に既定のセキュリティ記述子を使用するには、空の文字列 ("") またはの値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="8f952-225">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="8f952-226">既定値は、WSMan: ドライブのルート SDDL です。</span><span class="sxs-lookup"><span data-stu-id="8f952-226">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="8f952-227">セキュリティ記述子が複雑な場合は、このパラメーターの代わりに **Showsecuritydescriptor ui** パラメーターを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="8f952-227">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="8f952-228">両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f952-228">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="8f952-229">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="8f952-229">-SessionTypeOption</span></span>

<span data-ttu-id="8f952-230">セッション構成の種類固有のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-230">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="8f952-231">コマンドレットが返す **Psworkflowexecutionoption** オブジェクトなど、セッションの種類のオプションオブジェクトを入力し `New-PSWorkflowExecutionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="8f952-231">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="8f952-232">セッション構成を使用するセッションのオプションは、セッション オプションの値とセッション構成オプションによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-232">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="8f952-233">指定しない限り、セッションで設定されているオプション (コマンドレットを使用するなど) は、 `New-PSSessionOption` セッション構成で設定されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-233">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="8f952-234">ただし、セッション オプションの値は、セッション構成に設定されている最大値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="8f952-234">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="8f952-235">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8f952-235">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSSessionTypeOption
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-236">-Showsecurity記述子 Ui</span><span class="sxs-lookup"><span data-stu-id="8f952-236">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="8f952-237">このコマンドレットが、セッション構成の新しい SDDL の作成に役立つプロパティシートであることを示します。</span><span class="sxs-lookup"><span data-stu-id="8f952-237">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="8f952-238">コマンドを実行し `Set-PSSessionConfiguration` てから **WinRM** サービスを再起動すると、プロパティシートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-238">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="8f952-239">構成にアクセス許可を設定する場合は、セッションでセッション構成を使用するには、少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="8f952-239">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="8f952-240">**SecurityDescriptorSDDL** パラメーターとこのパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f952-240">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="8f952-241">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="8f952-241">-StartupScript</span></span>

<span data-ttu-id="8f952-242">構成のスタートアップスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-242">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="8f952-243">PowerShell スクリプトの完全修飾パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="8f952-243">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="8f952-244">指定されたスクリプトが、セッション構成を使用する新しいセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-244">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="8f952-245">セッション構成からスタートアップスクリプトを削除するには、空の文字列 ("") または値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="8f952-245">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="8f952-246">スタートアップスクリプトを使用して、ユーザーセッションをさらに構成することができます。</span><span class="sxs-lookup"><span data-stu-id="8f952-246">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="8f952-247">スクリプトでエラーが発生しても、終了しないエラーが発生しても、セッションは作成されず、 `New-PSSession` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="8f952-247">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="8f952-248">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="8f952-248">-ThreadOptions</span></span>

<span data-ttu-id="8f952-249">構成のスレッドオプション設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-249">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="8f952-250">この設定は、セッションでコマンドが実行されたときのスレッドの作成方法および使用方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f952-250">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="8f952-251">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f952-251">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8f952-252">Default</span><span class="sxs-lookup"><span data-stu-id="8f952-252">Default</span></span>
- <span data-ttu-id="8f952-253">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="8f952-253">ReuseThread</span></span>
- <span data-ttu-id="8f952-254">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="8f952-254">UseCurrentThread</span></span>
- <span data-ttu-id="8f952-255">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="8f952-255">UseNewThread</span></span>

<span data-ttu-id="8f952-256">既定値は **UseCurrentThread** です。</span><span class="sxs-lookup"><span data-stu-id="8f952-256">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="8f952-257">詳細については、「 [Psthreadoptions 列挙型](/dotnet/api/system.management.automation.runspaces.psthreadoptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f952-257">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSThreadOptions
Parameter Sets: (All)
Aliases:
Accepted values: Default, UseNewThread, ReuseThread, UseCurrentThread

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-258">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="8f952-258">-TransportOption</span></span>

<span data-ttu-id="8f952-259">セッション構成のトランスポートオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-259">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="8f952-260">トランスポートオプションオブジェクト (コマンドレットが返す **Wsmanconfigurationoption** オブジェクトなど) を入力し `New-PSTransportOption` ます。</span><span class="sxs-lookup"><span data-stu-id="8f952-260">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="8f952-261">セッション構成を使用するセッションのオプションは、セッション オプションの値とセッション構成オプションによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-261">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="8f952-262">指定しない限り、セッションで設定されているオプション (コマンドレットを使用するなど) は、 `New-PSSessionOption` セッション構成で設定されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-262">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="8f952-263">ただし、セッション オプションの値は、セッション構成に設定されている最大値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="8f952-263">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="8f952-264">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8f952-264">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTransportOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-265">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="8f952-265">-UseSharedProcess</span></span>

<span data-ttu-id="8f952-266">同じユーザーによって開始され、同じセッション構成を使用するすべてのセッションをホストするには、1つのプロセスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f952-266">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="8f952-267">既定では、各セッションは、個別のプロセスでホストされます。</span><span class="sxs-lookup"><span data-stu-id="8f952-267">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="8f952-268">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8f952-268">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8f952-269">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8f952-269">-Confirm</span></span>

<span data-ttu-id="8f952-270">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f952-270">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8f952-271">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8f952-271">-WhatIf</span></span>

<span data-ttu-id="8f952-272">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="8f952-272">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8f952-273">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f952-273">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8f952-274">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="8f952-274">-ThreadApartmentState</span></span>

<span data-ttu-id="8f952-275">使用するスレッドモジュールのアパートメント状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f952-275">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="8f952-276">使用可能な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f952-276">Acceptable values are:</span></span>

- <span data-ttu-id="8f952-277">Unknown</span><span class="sxs-lookup"><span data-stu-id="8f952-277">Unknown</span></span>
- <span data-ttu-id="8f952-278">MTA</span><span class="sxs-lookup"><span data-stu-id="8f952-278">MTA</span></span>
- <span data-ttu-id="8f952-279">STA</span><span class="sxs-lookup"><span data-stu-id="8f952-279">STA</span></span>

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f952-280">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f952-280">CommonParameters</span></span>

<span data-ttu-id="8f952-281">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8f952-281">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8f952-282">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f952-282">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8f952-283">入力</span><span class="sxs-lookup"><span data-stu-id="8f952-283">INPUTS</span></span>

### <span data-ttu-id="8f952-284">なし</span><span class="sxs-lookup"><span data-stu-id="8f952-284">None</span></span>

<span data-ttu-id="8f952-285">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8f952-285">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8f952-286">出力</span><span class="sxs-lookup"><span data-stu-id="8f952-286">OUTPUTS</span></span>

### <span data-ttu-id="8f952-287">WSManConfigLeafElement のようになります。</span><span class="sxs-lookup"><span data-stu-id="8f952-287">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="8f952-288">注</span><span class="sxs-lookup"><span data-stu-id="8f952-288">NOTES</span></span>

<span data-ttu-id="8f952-289">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f952-289">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="8f952-290">このコマンドレットを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="8f952-290">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="8f952-291">`Set-PSSessionConfiguration`コマンドレットは構成名を変更せず、 **WSMan** プロバイダーはコマンドレットをサポートしていません `Rename-Item` 。</span><span class="sxs-lookup"><span data-stu-id="8f952-291">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="8f952-292">セッション構成の名前を変更するには、コマンドレットを使用して構成を削除した後、コマンドレットを使用して、 `Unregister-PSSessionConfiguration` `Register-PSSessionConfiguration` 新しいセッション構成を作成して登録します。</span><span class="sxs-lookup"><span data-stu-id="8f952-292">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="8f952-293">コマンドレットを使用して、 `Set-PSSessionConfiguration` 既定の microsoft.powershell32 セッション構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="8f952-293">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="8f952-294">これらの構成は保護されません。</span><span class="sxs-lookup"><span data-stu-id="8f952-294">They are not protected.</span></span> <span data-ttu-id="8f952-295">既定のセッション構成の元のバージョンに戻すには、コマンドレットを使用して `Unregister-PSSessionConfiguration` 既定のセッション構成を削除してから、コマンドレットを使用し `Enable-PSRemoting` て復元します。</span><span class="sxs-lookup"><span data-stu-id="8f952-295">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="8f952-296">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8f952-296">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="8f952-297">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="8f952-297">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="8f952-298">WSMan: ドライブでコマンドを使用して、セッション構成のプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8f952-298">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="8f952-299">ただし、powershell 2.0 で WSMan: ドライブを使用して、 **OutputBufferingMode** などの powershell 3.0 で導入されたセッション構成プロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f952-299">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="8f952-300">Windows PowerShell 2.0 のコマンドではエラーは生成されませんが、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="8f952-300">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="8f952-301">PowerShell 3.0 で導入されたプロパティを変更するには、PowerShell 3.0 で WSMan: ドライブを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f952-301">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="8f952-302">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8f952-302">RELATED LINKS</span></span>

[<span data-ttu-id="8f952-303">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f952-303">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="8f952-304">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f952-304">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="8f952-305">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f952-305">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="8f952-306">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8f952-306">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="8f952-307">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="8f952-307">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="8f952-308">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="8f952-308">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="8f952-309">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f952-309">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="8f952-310">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8f952-310">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="8f952-311">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f952-311">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="8f952-312">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="8f952-312">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="8f952-313">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="8f952-313">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="8f952-314">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="8f952-314">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
