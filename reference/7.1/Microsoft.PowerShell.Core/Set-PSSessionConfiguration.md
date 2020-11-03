---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: d01de5a438ef0a3692ad9452fd4c16ac7e0bdce9
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218656"
---
# <span data-ttu-id="2cbac-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2cbac-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="2cbac-104">概要</span><span class="sxs-lookup"><span data-stu-id="2cbac-104">SYNOPSIS</span></span>
<span data-ttu-id="2cbac-105">登録済みのセッション構成のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="2cbac-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2cbac-106">SYNTAX</span></span>

### <span data-ttu-id="2cbac-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="2cbac-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2cbac-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="2cbac-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2cbac-109">セッションのすべてのもの</span><span class="sxs-lookup"><span data-stu-id="2cbac-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2cbac-110">Description</span><span class="sxs-lookup"><span data-stu-id="2cbac-110">DESCRIPTION</span></span>

<span data-ttu-id="2cbac-111">`Set-PSSessionConfiguration`コマンドレットは、ローカルコンピューター上のセッション構成のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="2cbac-112">**Name** パラメーターを使用して、変更するセッション構成を識別します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="2cbac-113">その他のパラメーターは、セッション構成のプロパティに新しい値を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="2cbac-114">構成からプロパティ値を削除し、既定値を使用するには、対応するパラメーターに空の文字列 ("") または値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="2cbac-115">PowerShell 3.0 以降では、セッション構成ファイルを使用してセッション構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="2cbac-116">この機能を使用すれば、セッション構成を使用するセッションのプロパティの設定や変更を迷わず簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="2cbac-117">セッション構成ファイルを指定するには、の **Path** パラメーターを使用し `Set-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="2cbac-118">セッション構成ファイルの詳細については、「 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cbac-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="2cbac-119">セッション構成ファイルを作成および変更する方法の詳細については、コマンドレットを参照してください `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="2cbac-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="2cbac-120">セッション構成は、ローカルコンピューターに接続するリモート **セッション (pssession** ) の環境を定義します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="2cbac-121">すべての **PSSession** は、セッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="2cbac-122">セッション構成は、セッションで使用できるモジュール、実行を許可されているコマンドレット、言語モード、クォータ、タイムアウトなどの **PSSession** の機能を決定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="2cbac-123">セッション構成のセキュリティ記述子は、セッション構成を使用してローカルコンピューターに接続できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="2cbac-124">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cbac-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="2cbac-125">セッション構成のプロパティを表示するに `Get-PSSessionConfiguration` は、コマンドレットまたは WSMan プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="2cbac-126">WSMan プロバイダーの詳細については、「」と入力 `Get-Help WSMan` してください。</span><span class="sxs-lookup"><span data-stu-id="2cbac-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="2cbac-127">例</span><span class="sxs-lookup"><span data-stu-id="2cbac-127">EXAMPLES</span></span>

### <span data-ttu-id="2cbac-128">例 1: セッション構成を作成して変更する</span><span class="sxs-lookup"><span data-stu-id="2cbac-128">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="2cbac-129">この例では、構成からスタートアップスクリプトを追加および削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-129">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="2cbac-130">最初のコマンドは、 **Adminshell** 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-130">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="2cbac-131">2番目のコマンドは、 `AdminConfig.ps1` 構成にスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-131">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="2cbac-132">変更は、 **WinRM** を再起動すると有効になります。</span><span class="sxs-lookup"><span data-stu-id="2cbac-132">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="2cbac-133">3番目のコマンドは、 `AdminConfig.ps1` 構成からスクリプトを削除します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-133">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="2cbac-134">例 2: 結果を表示する</span><span class="sxs-lookup"><span data-stu-id="2cbac-134">Example 2: Display results</span></span>

<span data-ttu-id="2cbac-135">この例では、 **MaximumReceivedObjectSizeMB** プロパティの値を20に増やしています。</span><span class="sxs-lookup"><span data-stu-id="2cbac-135">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="2cbac-136">このコマンドでは、 **WinRM** サービスの再起動を求めるメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-136">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="2cbac-137">変更は、 **WinRM** サービスが再起動されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-137">The change is not effective until the **WinRM** service is restarted.</span></span>

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

### <span data-ttu-id="2cbac-138">例 3: さまざまな方法で結果を表示する</span><span class="sxs-lookup"><span data-stu-id="2cbac-138">Example 3: Display results in different ways</span></span>

<span data-ttu-id="2cbac-139">この例では、によって、 `Set-PSSessionConfiguration` **MaintenanceShell** セッション構成のスタートアップスクリプトがに変更され `Maintenance.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-139">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="2cbac-140">出力には変更が示され、 **WinRM** サービスの再起動を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-140">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="2cbac-141">これに対する応答は "y" (はい) です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-141">The response is "y" (yes).</span></span>

<span data-ttu-id="2cbac-142">`Get-PSSessionConfiguration`**MaintenanceShell** セッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-142">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="2cbac-143">パイプライン演算子 (|) は、コマンドの結果をに送信し `Format-List` ます。これにより、構成オブジェクトのすべてのプロパティがリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-143">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="2cbac-144">次に、WSMan プロバイダーを使用して、 **MaintenanceShell** 構成の初期化パラメーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-144">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="2cbac-145">`Get-ChildItem`(エイリアス `dir` ) **MaintenanceShell** プラグインの **InitializationParameters** ノード内の子項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-145">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="2cbac-146">WSMan プロバイダーの詳細については、「」と入力 `Get-Help wsman` してください。</span><span class="sxs-lookup"><span data-stu-id="2cbac-146">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

## <span data-ttu-id="2cbac-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2cbac-147">PARAMETERS</span></span>

### <span data-ttu-id="2cbac-148">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="2cbac-148">-AccessMode</span></span>

<span data-ttu-id="2cbac-149">セッション構成を有効化および無効化し、コンピューター上のリモート セッションまたはローカル セッションにセッション構成を使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-149">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="2cbac-150">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2cbac-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2cbac-151">無効にします。</span><span class="sxs-lookup"><span data-stu-id="2cbac-151">Disabled.</span></span> <span data-ttu-id="2cbac-152">セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2cbac-152">Disables the session configuration.</span></span> <span data-ttu-id="2cbac-153">コンピューターへのリモート アクセスまたはローカル アクセスに使用できません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-153">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="2cbac-154">この値は、セッション構成の **Enabled** プロパティ ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) を **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-154">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="2cbac-155">Local。</span><span class="sxs-lookup"><span data-stu-id="2cbac-155">Local.</span></span> <span data-ttu-id="2cbac-156">**Network_Deny_All** エントリをセッション構成のセキュリティ記述子に追加します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-156">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="2cbac-157">ローカルコンピューターのユーザーは、セッション構成を使用して同じコンピューター上にローカルループバックセッションを作成できますが、リモートユーザーはアクセスを拒否されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-157">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="2cbac-158">[Remote]\(リモート\)。</span><span class="sxs-lookup"><span data-stu-id="2cbac-158">Remote.</span></span> <span data-ttu-id="2cbac-159">**Deny_All** エントリと **Network_Deny_All** エントリをセッション構成のセキュリティ記述子から削除します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-159">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="2cbac-160">ローカル コンピューターおよびリモート コンピューターのユーザーは、セッション構成を使用して、このコンピューターでセッションを作成し、コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-160">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="2cbac-161">既定値は **Remote** です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-161">The default value is **Remote**.</span></span>

<span data-ttu-id="2cbac-162">他のコマンドレットでは、後でこのパラメーターの値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-162">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="2cbac-163">たとえば、 `Enable-PSRemoting` コマンドレットは、コンピューター上のすべてのセッション構成を有効にし、それらへのリモートアクセスを許可し `Disable-PSRemoting` ます。また、コマンドレットは、コンピューター上のすべてのセッション構成へのローカルアクセスのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-163">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="2cbac-164">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2cbac-164">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2cbac-165">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="2cbac-165">-ApplicationBase</span></span>

<span data-ttu-id="2cbac-166">\* **AssemblyName** パラメーターの値に指定されているアセンブリファイル (.dll) のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-166">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="2cbac-167">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="2cbac-167">-AssemblyName</span></span>

<span data-ttu-id="2cbac-168">アセンブリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-168">Specifies the assembly name.</span></span> <span data-ttu-id="2cbac-169">このコマンドレットは、アセンブリで定義されているクラスに基づいてセッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-169">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="2cbac-170">セッション構成を定義するアセンブリ .dll ファイルのファイル名または完全パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-170">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="2cbac-171">ファイル名だけを入力した場合は、 **ApplicationBase** パラメーターの値でパスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-171">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

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

### <span data-ttu-id="2cbac-172">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="2cbac-172">-ConfigurationTypeName</span></span>

<span data-ttu-id="2cbac-173">**AssemblyName** パラメーターのアセンブリで定義されているセッションの構成の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-173">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="2cbac-174">指定する型は、 **System.Management.Automation.Remoting.PSSessionConfiguration** クラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cbac-174">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="2cbac-175">アセンブリ名を指定する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-175">This parameter is required when you specify an assembly name.</span></span>

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

### <span data-ttu-id="2cbac-176">-Force</span><span class="sxs-lookup"><span data-stu-id="2cbac-176">-Force</span></span>

<span data-ttu-id="2cbac-177">すべてのユーザープロンプトを非表示にし、プロンプトを表示せずに **WinRM** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-177">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="2cbac-178">サービスを再起動すると、構成の変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="2cbac-178">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="2cbac-179">再起動を回避し、再起動メッセージを表示しないようにするには、 **NoServiceRestart** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-179">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="2cbac-180">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="2cbac-180">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="2cbac-181">このコンピューターに1つのリモートコマンドで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-181">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="2cbac-182">データ サイズはメガバイト (MB) 単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-182">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="2cbac-183">既定値は 50 MB です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-183">The default is 50 MB.</span></span>

<span data-ttu-id="2cbac-184">**Configurationtypename** パラメーターで指定された構成の種類でデータサイズの制限が定義されている場合、構成の種類の制限が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-184">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="2cbac-185">このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-185">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="2cbac-186">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="2cbac-186">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="2cbac-187">このコンピューターに1つのオブジェクトで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-187">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="2cbac-188">データサイズをメガバイト単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-188">Enter the data size in megabytes.</span></span> <span data-ttu-id="2cbac-189">既定値は 10 MB です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-189">The default is 10 MB.</span></span>

<span data-ttu-id="2cbac-190">**Configurationtypename** パラメーターで指定された構成の種類でオブジェクトサイズの制限が定義されている場合、構成の種類の制限が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-190">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="2cbac-191">このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-191">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="2cbac-192">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="2cbac-192">-ModulesToImport</span></span>

<span data-ttu-id="2cbac-193">セッション構成を使用するセッションに自動的にインポートされたモジュールおよびスナップインを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-193">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="2cbac-194">モジュール名およびスナップイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-194">Enter the module and snap-in names.</span></span>

<span data-ttu-id="2cbac-195">既定では、 **PowerShell** のみがセッションにインポートされますが、コマンドレットが除外されていない限り、 `Import-Module` および Add-PSSnapin コマンドレットを使用して、モジュールとスナップインをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-195">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="2cbac-196">このパラメーター値に指定されたモジュールは、セッション構成ファイル () で指定されたモジュールに追加され `New-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-196">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="2cbac-197">ただし、セッション構成ファイル内の設定によって、モジュールでエクスポートされたコマンドが非表示になったり、ユーザーが使用できなくなったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="2cbac-197">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="2cbac-198">このパラメーター値に指定されたモジュールは、コマンドレットの **ModulesToImport** パラメーターを使用して指定されたモジュールの一覧に置き換わるもの `Register-PSSessionConfiguration` です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-198">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="2cbac-199">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2cbac-199">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2cbac-200">-Name</span><span class="sxs-lookup"><span data-stu-id="2cbac-200">-Name</span></span>

<span data-ttu-id="2cbac-201">変更するセッション構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-201">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="2cbac-202">このパラメーターを使用してセッション構成の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-202">You cannot use this parameter to change the name of the session configuration.</span></span>

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

### <span data-ttu-id="2cbac-203">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="2cbac-203">-NoServiceRestart</span></span>

<span data-ttu-id="2cbac-204">は、 **WinRM** サービスを再起動せず、サービスの再起動を求めるメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-204">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="2cbac-205">既定では、を実行すると `Set-PSSessionConfiguration` 、新しいセッション構成を有効にするために **WinRM** サービスを再起動するように求められます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-205">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="2cbac-206">**WinRM** サービスが再起動されるまで、新しいセッション構成は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-206">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="2cbac-207">プロンプトを表示せずに **WinRM** サービスを再起動するには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-207">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="2cbac-208">**WinRM** サービスを手動で再起動するには、コマンドレットを使用し `Restart-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-208">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="2cbac-209">-Path</span><span class="sxs-lookup"><span data-stu-id="2cbac-209">-Path</span></span>

<span data-ttu-id="2cbac-210">セッション構成ファイル (.pssc) のパス (コマンドレットによって作成されたものなど) を指定します `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="2cbac-210">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="2cbac-211">パスを省略した場合、既定値は現在のディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="2cbac-211">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="2cbac-212">セッション構成ファイルを変更する方法の詳細については、コマンドレットのヘルプトピックを参照してください `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="2cbac-212">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="2cbac-213">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2cbac-213">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2cbac-214">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="2cbac-214">-PSVersion</span></span>

<span data-ttu-id="2cbac-215">このセッション構成を使用するセッションの PowerShell のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-215">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="2cbac-216">このパラメーターの値は、セッション構成ファイルの **PowerShellVersion** キーの値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-216">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="2cbac-217">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2cbac-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2cbac-218">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="2cbac-218">-RunAsCredential</span></span>

<span data-ttu-id="2cbac-219">セッションのコマンドの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-219">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="2cbac-220">既定では、コマンドは現在のユーザーのアクセス許可で実行されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-220">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="2cbac-221">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2cbac-221">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2cbac-222">-Security記述子 Sddl</span><span class="sxs-lookup"><span data-stu-id="2cbac-222">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="2cbac-223">構成に対して別のセキュリティ記述子定義言語 (SDDL) 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-223">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="2cbac-224">この文字列によって、新しいセッション構成を使用するために必要なアクセス許可が決定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-224">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="2cbac-225">セッションでセッション構成を使用するには、その構成に対して少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-225">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="2cbac-226">構成に既定のセキュリティ記述子を使用するには、空の文字列 ("") またはの値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-226">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="2cbac-227">既定値は、WSMan: ドライブのルート SDDL です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-227">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="2cbac-228">セキュリティ記述子が複雑な場合は、このパラメーターの代わりに **Showsecuritydescriptor ui** パラメーターを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2cbac-228">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="2cbac-229">両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-229">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="2cbac-230">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="2cbac-230">-SessionTypeOption</span></span>

<span data-ttu-id="2cbac-231">セッション構成の種類固有のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-231">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="2cbac-232">コマンドレットが返す **Psworkflowexecutionoption** オブジェクトなど、セッションの種類のオプションオブジェクトを入力し `New-PSWorkflowExecutionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-232">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="2cbac-233">セッション構成を使用するセッションのオプションは、セッション オプションの値とセッション構成オプションによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-233">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="2cbac-234">指定しない限り、セッションで設定されているオプション (コマンドレットを使用するなど) は、 `New-PSSessionOption` セッション構成で設定されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-234">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="2cbac-235">ただし、セッション オプションの値は、セッション構成に設定されている最大値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-235">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="2cbac-236">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2cbac-236">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2cbac-237">-Showsecurity記述子 Ui</span><span class="sxs-lookup"><span data-stu-id="2cbac-237">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="2cbac-238">このコマンドレットが、セッション構成の新しい SDDL の作成に役立つプロパティシートであることを示します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-238">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="2cbac-239">コマンドを実行し `Set-PSSessionConfiguration` てから **WinRM** サービスを再起動すると、プロパティシートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-239">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="2cbac-240">構成にアクセス許可を設定する場合は、セッションでセッション構成を使用するには、少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-240">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="2cbac-241">**SecurityDescriptorSDDL** パラメーターとこのパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-241">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="2cbac-242">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="2cbac-242">-StartupScript</span></span>

<span data-ttu-id="2cbac-243">構成のスタートアップスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-243">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="2cbac-244">PowerShell スクリプトの完全修飾パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-244">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="2cbac-245">指定されたスクリプトが、セッション構成を使用する新しいセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-245">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="2cbac-246">セッション構成からスタートアップスクリプトを削除するには、空の文字列 ("") または値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-246">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="2cbac-247">スタートアップスクリプトを使用して、ユーザーセッションをさらに構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-247">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="2cbac-248">スクリプトでエラーが発生しても、終了しないエラーが発生しても、セッションは作成されず、 `New-PSSession` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-248">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="2cbac-249">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="2cbac-249">-ThreadOptions</span></span>

<span data-ttu-id="2cbac-250">構成のスレッドオプション設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-250">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="2cbac-251">この設定は、セッションでコマンドが実行されたときのスレッドの作成方法および使用方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-251">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="2cbac-252">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2cbac-252">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2cbac-253">Default</span><span class="sxs-lookup"><span data-stu-id="2cbac-253">Default</span></span>
- <span data-ttu-id="2cbac-254">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="2cbac-254">ReuseThread</span></span>
- <span data-ttu-id="2cbac-255">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="2cbac-255">UseCurrentThread</span></span>
- <span data-ttu-id="2cbac-256">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="2cbac-256">UseNewThread</span></span>

<span data-ttu-id="2cbac-257">既定値は **UseCurrentThread** です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-257">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="2cbac-258">詳細については、「 [Psthreadoptions 列挙型](/dotnet/api/system.management.automation.runspaces.psthreadoptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cbac-258">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

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

### <span data-ttu-id="2cbac-259">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="2cbac-259">-TransportOption</span></span>

<span data-ttu-id="2cbac-260">セッション構成のトランスポートオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-260">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="2cbac-261">トランスポートオプションオブジェクト (コマンドレットが返す **Wsmanconfigurationoption** オブジェクトなど) を入力し `New-PSTransportOption` ます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-261">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="2cbac-262">セッション構成を使用するセッションのオプションは、セッション オプションの値とセッション構成オプションによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-262">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="2cbac-263">指定しない限り、セッションで設定されているオプション (コマンドレットを使用するなど) は、 `New-PSSessionOption` セッション構成で設定されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-263">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="2cbac-264">ただし、セッション オプションの値は、セッション構成に設定されている最大値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-264">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="2cbac-265">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2cbac-265">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2cbac-266">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="2cbac-266">-UseSharedProcess</span></span>

<span data-ttu-id="2cbac-267">同じユーザーによって開始され、同じセッション構成を使用するすべてのセッションをホストするには、1つのプロセスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-267">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="2cbac-268">既定では、各セッションは、個別のプロセスでホストされます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-268">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="2cbac-269">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2cbac-269">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2cbac-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2cbac-270">-Confirm</span></span>

<span data-ttu-id="2cbac-271">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2cbac-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2cbac-272">-WhatIf</span></span>

<span data-ttu-id="2cbac-273">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-273">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2cbac-274">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-274">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2cbac-275">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="2cbac-275">-ThreadApartmentState</span></span>

<span data-ttu-id="2cbac-276">使用するスレッドモジュールのアパートメント状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-276">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="2cbac-277">使用可能な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2cbac-277">Acceptable values are:</span></span>

- <span data-ttu-id="2cbac-278">Unknown</span><span class="sxs-lookup"><span data-stu-id="2cbac-278">Unknown</span></span>
- <span data-ttu-id="2cbac-279">MTA</span><span class="sxs-lookup"><span data-stu-id="2cbac-279">MTA</span></span>
- <span data-ttu-id="2cbac-280">STA</span><span class="sxs-lookup"><span data-stu-id="2cbac-280">STA</span></span>

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

### <span data-ttu-id="2cbac-281">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cbac-281">CommonParameters</span></span>

<span data-ttu-id="2cbac-282">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2cbac-282">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2cbac-283">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cbac-283">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2cbac-284">入力</span><span class="sxs-lookup"><span data-stu-id="2cbac-284">INPUTS</span></span>

### <span data-ttu-id="2cbac-285">なし</span><span class="sxs-lookup"><span data-stu-id="2cbac-285">None</span></span>

<span data-ttu-id="2cbac-286">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-286">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2cbac-287">出力</span><span class="sxs-lookup"><span data-stu-id="2cbac-287">OUTPUTS</span></span>

### <span data-ttu-id="2cbac-288">WSManConfigLeafElement のようになります。</span><span class="sxs-lookup"><span data-stu-id="2cbac-288">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="2cbac-289">注</span><span class="sxs-lookup"><span data-stu-id="2cbac-289">NOTES</span></span>

<span data-ttu-id="2cbac-290">このコマンドレットを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-290">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="2cbac-291">`Set-PSSessionConfiguration`コマンドレットは構成名を変更せず、 **WSMan** プロバイダーはコマンドレットをサポートしていません `Rename-Item` 。</span><span class="sxs-lookup"><span data-stu-id="2cbac-291">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="2cbac-292">セッション構成の名前を変更するには、コマンドレットを使用して構成を削除した後、コマンドレットを使用して、 `Unregister-PSSessionConfiguration` `Register-PSSessionConfiguration` 新しいセッション構成を作成して登録します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-292">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="2cbac-293">コマンドレットを使用して、 `Set-PSSessionConfiguration` 既定の microsoft.powershell32 セッション構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-293">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="2cbac-294">これらの構成は保護されません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-294">They are not protected.</span></span> <span data-ttu-id="2cbac-295">既定のセッション構成の元のバージョンに戻すには、コマンドレットを使用して `Unregister-PSSessionConfiguration` 既定のセッション構成を削除してから、コマンドレットを使用し `Enable-PSRemoting` て復元します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-295">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="2cbac-296">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2cbac-296">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="2cbac-297">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="2cbac-297">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="2cbac-298">WSMan: ドライブでコマンドを使用して、セッション構成のプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="2cbac-298">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="2cbac-299">ただし、powershell 2.0 で WSMan: ドライブを使用して、 **OutputBufferingMode** などの powershell 3.0 で導入されたセッション構成プロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-299">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="2cbac-300">Windows PowerShell 2.0 のコマンドではエラーは生成されませんが、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="2cbac-300">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="2cbac-301">PowerShell 3.0 で導入されたプロパティを変更するには、PowerShell 3.0 で WSMan: ドライブを使用します。</span><span class="sxs-lookup"><span data-stu-id="2cbac-301">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="2cbac-302">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2cbac-302">RELATED LINKS</span></span>

[<span data-ttu-id="2cbac-303">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2cbac-303">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="2cbac-304">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2cbac-304">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="2cbac-305">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2cbac-305">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="2cbac-306">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2cbac-306">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="2cbac-307">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="2cbac-307">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="2cbac-308">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="2cbac-308">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="2cbac-309">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2cbac-309">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="2cbac-310">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2cbac-310">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="2cbac-311">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2cbac-311">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="2cbac-312">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="2cbac-312">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="2cbac-313">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="2cbac-313">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="2cbac-314">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="2cbac-314">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)

