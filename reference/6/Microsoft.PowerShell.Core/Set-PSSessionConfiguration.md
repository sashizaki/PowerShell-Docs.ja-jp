---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 8a769959295de0eed7776cc972b007514cfe8734
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218651"
---
# <span data-ttu-id="f95f0-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f95f0-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="f95f0-104">概要</span><span class="sxs-lookup"><span data-stu-id="f95f0-104">SYNOPSIS</span></span>
<span data-ttu-id="f95f0-105">登録済みのセッション構成のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="f95f0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f95f0-106">SYNTAX</span></span>

### <span data-ttu-id="f95f0-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="f95f0-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f95f0-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="f95f0-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f95f0-109">セッションのすべてのもの</span><span class="sxs-lookup"><span data-stu-id="f95f0-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="f95f0-110">Description</span><span class="sxs-lookup"><span data-stu-id="f95f0-110">DESCRIPTION</span></span>

<span data-ttu-id="f95f0-111">`Set-PSSessionConfiguration`コマンドレットは、ローカルコンピューター上のセッション構成のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="f95f0-112">**Name** パラメーターを使用して、変更するセッション構成を識別します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="f95f0-113">その他のパラメーターは、セッション構成のプロパティに新しい値を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="f95f0-114">構成からプロパティ値を削除し、既定値を使用するには、対応するパラメーターに空の文字列 ("") または値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="f95f0-115">PowerShell 3.0 以降では、セッション構成ファイルを使用してセッション構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="f95f0-116">この機能を使用すれば、セッション構成を使用するセッションのプロパティの設定や変更を迷わず簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="f95f0-117">セッション構成ファイルを指定するには、の **Path** パラメーターを使用し `Set-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="f95f0-118">セッション構成ファイルの詳細については、「 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f95f0-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="f95f0-119">セッション構成ファイルを作成および変更する方法の詳細については、コマンドレットを参照してください `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="f95f0-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="f95f0-120">セッション構成は、ローカルコンピューターに接続するリモート **セッション (pssession** ) の環境を定義します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="f95f0-121">すべての **PSSession** は、セッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="f95f0-122">セッション構成は、セッションで使用できるモジュール、実行を許可されているコマンドレット、言語モード、クォータ、タイムアウトなどの **PSSession** の機能を決定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="f95f0-123">セッション構成のセキュリティ記述子は、セッション構成を使用してローカルコンピューターに接続できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="f95f0-124">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f95f0-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="f95f0-125">セッション構成のプロパティを表示するに `Get-PSSessionConfiguration` は、コマンドレットまたは WSMan プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="f95f0-126">WSMan プロバイダーの詳細については、「」と入力 `Get-Help WSMan` してください。</span><span class="sxs-lookup"><span data-stu-id="f95f0-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="f95f0-127">例</span><span class="sxs-lookup"><span data-stu-id="f95f0-127">EXAMPLES</span></span>

### <span data-ttu-id="f95f0-128">例 1: セッション構成を作成して変更する</span><span class="sxs-lookup"><span data-stu-id="f95f0-128">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="f95f0-129">この例では、構成からスタートアップスクリプトを追加および削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-129">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="f95f0-130">最初のコマンドは、 **Adminshell** 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-130">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="f95f0-131">2番目のコマンドは、 `AdminConfig.ps1` 構成にスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-131">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="f95f0-132">変更は、 **WinRM** を再起動すると有効になります。</span><span class="sxs-lookup"><span data-stu-id="f95f0-132">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="f95f0-133">3番目のコマンドは、 `AdminConfig.ps1` 構成からスクリプトを削除します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-133">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="f95f0-134">例 2: 結果を表示する</span><span class="sxs-lookup"><span data-stu-id="f95f0-134">Example 2: Display results</span></span>

<span data-ttu-id="f95f0-135">この例では、 **MaximumReceivedObjectSizeMB** プロパティの値を20に増やしています。</span><span class="sxs-lookup"><span data-stu-id="f95f0-135">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="f95f0-136">このコマンドでは、 **WinRM** サービスの再起動を求めるメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-136">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="f95f0-137">変更は、 **WinRM** サービスが再起動されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-137">The change is not effective until the **WinRM** service is restarted.</span></span>

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

### <span data-ttu-id="f95f0-138">例 3: さまざまな方法で結果を表示する</span><span class="sxs-lookup"><span data-stu-id="f95f0-138">Example 3: Display results in different ways</span></span>

<span data-ttu-id="f95f0-139">この例では、によって、 `Set-PSSessionConfiguration` **MaintenanceShell** セッション構成のスタートアップスクリプトがに変更され `Maintenance.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-139">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="f95f0-140">出力には変更が示され、 **WinRM** サービスの再起動を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-140">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="f95f0-141">これに対する応答は "y" (はい) です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-141">The response is "y" (yes).</span></span>

<span data-ttu-id="f95f0-142">`Get-PSSessionConfiguration`**MaintenanceShell** セッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-142">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="f95f0-143">パイプライン演算子 (|) は、コマンドの結果をに送信し `Format-List` ます。これにより、構成オブジェクトのすべてのプロパティがリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-143">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="f95f0-144">次に、WSMan プロバイダーを使用して、 **MaintenanceShell** 構成の初期化パラメーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-144">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="f95f0-145">`Get-ChildItem`(エイリアス `dir` ) **MaintenanceShell** プラグインの **InitializationParameters** ノード内の子項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-145">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="f95f0-146">WSMan プロバイダーの詳細については、「」と入力 `Get-Help wsman` してください。</span><span class="sxs-lookup"><span data-stu-id="f95f0-146">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

## <span data-ttu-id="f95f0-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f95f0-147">PARAMETERS</span></span>

### <span data-ttu-id="f95f0-148">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="f95f0-148">-AccessMode</span></span>

<span data-ttu-id="f95f0-149">セッション構成を有効化および無効化し、コンピューター上のリモート セッションまたはローカル セッションにセッション構成を使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-149">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="f95f0-150">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f95f0-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f95f0-151">無効にします。</span><span class="sxs-lookup"><span data-stu-id="f95f0-151">Disabled.</span></span> <span data-ttu-id="f95f0-152">セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f95f0-152">Disables the session configuration.</span></span> <span data-ttu-id="f95f0-153">コンピューターへのリモート アクセスまたはローカル アクセスに使用できません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-153">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="f95f0-154">この値は、セッション構成の **Enabled** プロパティ ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) を **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-154">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="f95f0-155">Local。</span><span class="sxs-lookup"><span data-stu-id="f95f0-155">Local.</span></span> <span data-ttu-id="f95f0-156">**Network_Deny_All** エントリをセッション構成のセキュリティ記述子に追加します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-156">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="f95f0-157">ローカルコンピューターのユーザーは、セッション構成を使用して同じコンピューター上にローカルループバックセッションを作成できますが、リモートユーザーはアクセスを拒否されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-157">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="f95f0-158">[Remote]\(リモート\)。</span><span class="sxs-lookup"><span data-stu-id="f95f0-158">Remote.</span></span> <span data-ttu-id="f95f0-159">**Deny_All** エントリと **Network_Deny_All** エントリをセッション構成のセキュリティ記述子から削除します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-159">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="f95f0-160">ローカル コンピューターおよびリモート コンピューターのユーザーは、セッション構成を使用して、このコンピューターでセッションを作成し、コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-160">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="f95f0-161">既定値は **Remote** です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-161">The default value is **Remote**.</span></span>

<span data-ttu-id="f95f0-162">他のコマンドレットでは、後でこのパラメーターの値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-162">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="f95f0-163">たとえば、 `Enable-PSRemoting` コマンドレットは、コンピューター上のすべてのセッション構成を有効にし、それらへのリモートアクセスを許可し `Disable-PSRemoting` ます。また、コマンドレットは、コンピューター上のすべてのセッション構成へのローカルアクセスのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-163">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="f95f0-164">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f95f0-164">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f95f0-165">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="f95f0-165">-ApplicationBase</span></span>

<span data-ttu-id="f95f0-166">\* **AssemblyName** パラメーターの値に指定されているアセンブリファイル (.dll) のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-166">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="f95f0-167">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="f95f0-167">-AssemblyName</span></span>

<span data-ttu-id="f95f0-168">アセンブリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-168">Specifies the assembly name.</span></span> <span data-ttu-id="f95f0-169">このコマンドレットは、アセンブリで定義されているクラスに基づいてセッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-169">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="f95f0-170">セッション構成を定義するアセンブリ .dll ファイルのファイル名または完全パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-170">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="f95f0-171">ファイル名だけを入力した場合は、 **ApplicationBase** パラメーターの値でパスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-171">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

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

### <span data-ttu-id="f95f0-172">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="f95f0-172">-ConfigurationTypeName</span></span>

<span data-ttu-id="f95f0-173">**AssemblyName** パラメーターのアセンブリで定義されているセッションの構成の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-173">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="f95f0-174">指定する型は、 **System.Management.Automation.Remoting.PSSessionConfiguration** クラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f95f0-174">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="f95f0-175">アセンブリ名を指定する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-175">This parameter is required when you specify an assembly name.</span></span>

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

### <span data-ttu-id="f95f0-176">-Force</span><span class="sxs-lookup"><span data-stu-id="f95f0-176">-Force</span></span>

<span data-ttu-id="f95f0-177">すべてのユーザープロンプトを非表示にし、プロンプトを表示せずに **WinRM** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-177">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="f95f0-178">サービスを再起動すると、構成の変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="f95f0-178">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="f95f0-179">再起動を回避し、再起動メッセージを表示しないようにするには、 **NoServiceRestart** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-179">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="f95f0-180">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="f95f0-180">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="f95f0-181">このコンピューターに1つのリモートコマンドで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-181">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="f95f0-182">データ サイズはメガバイト (MB) 単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-182">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="f95f0-183">既定値は 50 MB です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-183">The default is 50 MB.</span></span>

<span data-ttu-id="f95f0-184">**Configurationtypename** パラメーターで指定された構成の種類でデータサイズの制限が定義されている場合、構成の種類の制限が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-184">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="f95f0-185">このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-185">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="f95f0-186">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="f95f0-186">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="f95f0-187">このコンピューターに1つのオブジェクトで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-187">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="f95f0-188">データサイズをメガバイト単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-188">Enter the data size in megabytes.</span></span> <span data-ttu-id="f95f0-189">既定値は 10 MB です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-189">The default is 10 MB.</span></span>

<span data-ttu-id="f95f0-190">**Configurationtypename** パラメーターで指定された構成の種類でオブジェクトサイズの制限が定義されている場合、構成の種類の制限が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-190">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="f95f0-191">このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-191">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="f95f0-192">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="f95f0-192">-ModulesToImport</span></span>

<span data-ttu-id="f95f0-193">セッション構成を使用するセッションに自動的にインポートされたモジュールおよびスナップインを指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-193">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="f95f0-194">モジュール名およびスナップイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-194">Enter the module and snap-in names.</span></span>

<span data-ttu-id="f95f0-195">既定では、 **PowerShell** のみがセッションにインポートされますが、コマンドレットが除外されていない限り、 `Import-Module` および Add-PSSnapin コマンドレットを使用して、モジュールとスナップインをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-195">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="f95f0-196">このパラメーター値に指定されたモジュールは、セッション構成ファイル () で指定されたモジュールに追加され `New-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-196">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="f95f0-197">ただし、セッション構成ファイル内の設定によって、モジュールでエクスポートされたコマンドが非表示になったり、ユーザーが使用できなくなったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="f95f0-197">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="f95f0-198">このパラメーター値に指定されたモジュールは、コマンドレットの **ModulesToImport** パラメーターを使用して指定されたモジュールの一覧に置き換わるもの `Register-PSSessionConfiguration` です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-198">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="f95f0-199">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f95f0-199">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f95f0-200">-Name</span><span class="sxs-lookup"><span data-stu-id="f95f0-200">-Name</span></span>

<span data-ttu-id="f95f0-201">変更するセッション構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-201">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="f95f0-202">このパラメーターを使用してセッション構成の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-202">You cannot use this parameter to change the name of the session configuration.</span></span>

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

### <span data-ttu-id="f95f0-203">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="f95f0-203">-NoServiceRestart</span></span>

<span data-ttu-id="f95f0-204">は、 **WinRM** サービスを再起動せず、サービスの再起動を求めるメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-204">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="f95f0-205">既定では、を実行すると `Set-PSSessionConfiguration` 、新しいセッション構成を有効にするために **WinRM** サービスを再起動するように求められます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-205">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="f95f0-206">**WinRM** サービスが再起動されるまで、新しいセッション構成は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-206">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="f95f0-207">プロンプトを表示せずに **WinRM** サービスを再起動するには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-207">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="f95f0-208">**WinRM** サービスを手動で再起動するには、コマンドレットを使用し `Restart-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-208">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="f95f0-209">-Path</span><span class="sxs-lookup"><span data-stu-id="f95f0-209">-Path</span></span>

<span data-ttu-id="f95f0-210">セッション構成ファイル (.pssc) のパス (コマンドレットによって作成されたものなど) を指定します `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="f95f0-210">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="f95f0-211">パスを省略した場合、既定値は現在のディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="f95f0-211">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="f95f0-212">セッション構成ファイルを変更する方法の詳細については、コマンドレットのヘルプトピックを参照してください `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="f95f0-212">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="f95f0-213">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f95f0-213">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f95f0-214">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="f95f0-214">-PSVersion</span></span>

<span data-ttu-id="f95f0-215">このセッション構成を使用するセッションの PowerShell のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-215">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="f95f0-216">このパラメーターの値は、セッション構成ファイルの **PowerShellVersion** キーの値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-216">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="f95f0-217">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f95f0-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f95f0-218">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="f95f0-218">-RunAsCredential</span></span>

<span data-ttu-id="f95f0-219">セッションのコマンドの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-219">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="f95f0-220">既定では、コマンドは現在のユーザーのアクセス許可で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-220">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="f95f0-221">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f95f0-221">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f95f0-222">-Security記述子 Sddl</span><span class="sxs-lookup"><span data-stu-id="f95f0-222">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="f95f0-223">構成に対して別のセキュリティ記述子定義言語 (SDDL) 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-223">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="f95f0-224">この文字列によって、新しいセッション構成を使用するために必要なアクセス許可が決定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-224">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="f95f0-225">セッションでセッション構成を使用するには、その構成に対して少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-225">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="f95f0-226">構成に既定のセキュリティ記述子を使用するには、空の文字列 ("") またはの値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-226">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="f95f0-227">既定値は、WSMan: ドライブのルート SDDL です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-227">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="f95f0-228">セキュリティ記述子が複雑な場合は、このパラメーターの代わりに **Showsecuritydescriptor ui** パラメーターを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f95f0-228">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="f95f0-229">両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-229">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="f95f0-230">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="f95f0-230">-SessionTypeOption</span></span>

<span data-ttu-id="f95f0-231">セッション構成の種類固有のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-231">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="f95f0-232">コマンドレットが返す **Psworkflowexecutionoption** オブジェクトなど、セッションの種類のオプションオブジェクトを入力し `New-PSWorkflowExecutionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-232">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="f95f0-233">セッション構成を使用するセッションのオプションは、セッション オプションの値とセッション構成オプションによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-233">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="f95f0-234">指定しない限り、セッションで設定されているオプション (コマンドレットを使用するなど) は、 `New-PSSessionOption` セッション構成で設定されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-234">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="f95f0-235">ただし、セッション オプションの値は、セッション構成に設定されている最大値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-235">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="f95f0-236">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f95f0-236">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f95f0-237">-Showsecurity記述子 Ui</span><span class="sxs-lookup"><span data-stu-id="f95f0-237">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="f95f0-238">このコマンドレットが、セッション構成の新しい SDDL の作成に役立つプロパティシートであることを示します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-238">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="f95f0-239">コマンドを実行し `Set-PSSessionConfiguration` てから **WinRM** サービスを再起動すると、プロパティシートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-239">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="f95f0-240">構成にアクセス許可を設定する場合は、セッションでセッション構成を使用するには、少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-240">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="f95f0-241">**SecurityDescriptorSDDL** パラメーターとこのパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-241">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="f95f0-242">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="f95f0-242">-StartupScript</span></span>

<span data-ttu-id="f95f0-243">構成のスタートアップスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-243">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="f95f0-244">PowerShell スクリプトの完全修飾パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-244">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="f95f0-245">指定されたスクリプトが、セッション構成を使用する新しいセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-245">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="f95f0-246">セッション構成からスタートアップスクリプトを削除するには、空の文字列 ("") または値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-246">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="f95f0-247">スタートアップスクリプトを使用して、ユーザーセッションをさらに構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-247">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="f95f0-248">スクリプトでエラーが発生しても、終了しないエラーが発生しても、セッションは作成されず、 `New-PSSession` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-248">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="f95f0-249">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="f95f0-249">-ThreadOptions</span></span>

<span data-ttu-id="f95f0-250">構成のスレッドオプション設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-250">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="f95f0-251">この設定は、セッションでコマンドが実行されたときのスレッドの作成方法および使用方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-251">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="f95f0-252">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f95f0-252">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f95f0-253">Default</span><span class="sxs-lookup"><span data-stu-id="f95f0-253">Default</span></span>
- <span data-ttu-id="f95f0-254">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="f95f0-254">ReuseThread</span></span>
- <span data-ttu-id="f95f0-255">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="f95f0-255">UseCurrentThread</span></span>
- <span data-ttu-id="f95f0-256">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="f95f0-256">UseNewThread</span></span>

<span data-ttu-id="f95f0-257">既定値は **UseCurrentThread** です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-257">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="f95f0-258">詳細については、「 [Psthreadoptions 列挙型](/dotnet/api/system.management.automation.runspaces.psthreadoptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f95f0-258">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

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

### <span data-ttu-id="f95f0-259">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="f95f0-259">-TransportOption</span></span>

<span data-ttu-id="f95f0-260">セッション構成のトランスポートオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-260">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="f95f0-261">トランスポートオプションオブジェクト (コマンドレットが返す **Wsmanconfigurationoption** オブジェクトなど) を入力し `New-PSTransportOption` ます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-261">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="f95f0-262">セッション構成を使用するセッションのオプションは、セッション オプションの値とセッション構成オプションによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-262">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="f95f0-263">指定しない限り、セッションで設定されているオプション (コマンドレットを使用するなど) は、 `New-PSSessionOption` セッション構成で設定されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-263">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="f95f0-264">ただし、セッション オプションの値は、セッション構成に設定されている最大値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-264">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="f95f0-265">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f95f0-265">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f95f0-266">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="f95f0-266">-UseSharedProcess</span></span>

<span data-ttu-id="f95f0-267">同じユーザーによって開始され、同じセッション構成を使用するすべてのセッションをホストするには、1つのプロセスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-267">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="f95f0-268">既定では、各セッションは、個別のプロセスでホストされます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-268">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="f95f0-269">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f95f0-269">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f95f0-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f95f0-270">-Confirm</span></span>

<span data-ttu-id="f95f0-271">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f95f0-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f95f0-272">-WhatIf</span></span>

<span data-ttu-id="f95f0-273">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-273">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f95f0-274">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-274">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f95f0-275">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f95f0-275">CommonParameters</span></span>

<span data-ttu-id="f95f0-276">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f95f0-276">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f95f0-277">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f95f0-277">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f95f0-278">入力</span><span class="sxs-lookup"><span data-stu-id="f95f0-278">INPUTS</span></span>

### <span data-ttu-id="f95f0-279">なし</span><span class="sxs-lookup"><span data-stu-id="f95f0-279">None</span></span>

<span data-ttu-id="f95f0-280">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-280">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f95f0-281">出力</span><span class="sxs-lookup"><span data-stu-id="f95f0-281">OUTPUTS</span></span>

### <span data-ttu-id="f95f0-282">WSManConfigLeafElement のようになります。</span><span class="sxs-lookup"><span data-stu-id="f95f0-282">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="f95f0-283">注</span><span class="sxs-lookup"><span data-stu-id="f95f0-283">NOTES</span></span>

<span data-ttu-id="f95f0-284">このコマンドレットを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-284">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="f95f0-285">`Set-PSSessionConfiguration`コマンドレットは構成名を変更せず、 **WSMan** プロバイダーはコマンドレットをサポートしていません `Rename-Item` 。</span><span class="sxs-lookup"><span data-stu-id="f95f0-285">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="f95f0-286">セッション構成の名前を変更するには、コマンドレットを使用して構成を削除した後、コマンドレットを使用して、 `Unregister-PSSessionConfiguration` `Register-PSSessionConfiguration` 新しいセッション構成を作成して登録します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-286">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="f95f0-287">コマンドレットを使用して、 `Set-PSSessionConfiguration` 既定の microsoft.powershell32 セッション構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-287">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="f95f0-288">これらの構成は保護されません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-288">They are not protected.</span></span> <span data-ttu-id="f95f0-289">既定のセッション構成の元のバージョンに戻すには、コマンドレットを使用して `Unregister-PSSessionConfiguration` 既定のセッション構成を削除してから、コマンドレットを使用し `Enable-PSRemoting` て復元します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-289">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="f95f0-290">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f95f0-290">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="f95f0-291">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f95f0-291">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="f95f0-292">WSMan: ドライブでコマンドを使用して、セッション構成のプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f95f0-292">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="f95f0-293">ただし、powershell 2.0 で WSMan: ドライブを使用して、 **OutputBufferingMode** などの powershell 3.0 で導入されたセッション構成プロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-293">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="f95f0-294">Windows PowerShell 2.0 のコマンドではエラーは生成されませんが、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="f95f0-294">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="f95f0-295">PowerShell 3.0 で導入されたプロパティを変更するには、PowerShell 3.0 で WSMan: ドライブを使用します。</span><span class="sxs-lookup"><span data-stu-id="f95f0-295">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="f95f0-296">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f95f0-296">RELATED LINKS</span></span>

[<span data-ttu-id="f95f0-297">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f95f0-297">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="f95f0-298">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f95f0-298">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="f95f0-299">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f95f0-299">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="f95f0-300">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f95f0-300">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="f95f0-301">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="f95f0-301">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="f95f0-302">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="f95f0-302">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="f95f0-303">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f95f0-303">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="f95f0-304">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f95f0-304">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="f95f0-305">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f95f0-305">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="f95f0-306">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f95f0-306">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="f95f0-307">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="f95f0-307">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="f95f0-308">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="f95f0-308">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
