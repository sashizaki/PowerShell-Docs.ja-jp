---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 33773769cd19373764cf4adbe86bb990589948ff
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218176"
---
# <span data-ttu-id="880af-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="880af-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="880af-104">概要</span><span class="sxs-lookup"><span data-stu-id="880af-104">SYNOPSIS</span></span>
<span data-ttu-id="880af-105">登録済みのセッション構成のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="880af-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="880af-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="880af-106">SYNTAX</span></span>

### <span data-ttu-id="880af-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="880af-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="880af-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="880af-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="880af-109">セッションのすべてのもの</span><span class="sxs-lookup"><span data-stu-id="880af-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="880af-110">Description</span><span class="sxs-lookup"><span data-stu-id="880af-110">DESCRIPTION</span></span>

<span data-ttu-id="880af-111">`Set-PSSessionConfiguration`コマンドレットは、ローカルコンピューター上のセッション構成のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="880af-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="880af-112">**Name** パラメーターを使用して、変更するセッション構成を識別します。</span><span class="sxs-lookup"><span data-stu-id="880af-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="880af-113">その他のパラメーターは、セッション構成のプロパティに新しい値を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="880af-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="880af-114">構成からプロパティ値を削除し、既定値を使用するには、対応するパラメーターに空の文字列 ("") または値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="880af-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="880af-115">PowerShell 3.0 以降では、セッション構成ファイルを使用してセッション構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="880af-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="880af-116">この機能を使用すれば、セッション構成を使用するセッションのプロパティの設定や変更を迷わず簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="880af-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="880af-117">セッション構成ファイルを指定するには、の **Path** パラメーターを使用し `Set-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="880af-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="880af-118">セッション構成ファイルの詳細については、「 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="880af-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="880af-119">セッション構成ファイルを作成および変更する方法の詳細については、コマンドレットを参照してください `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="880af-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="880af-120">セッション構成は、ローカルコンピューターに接続するリモート **セッション (pssession** ) の環境を定義します。</span><span class="sxs-lookup"><span data-stu-id="880af-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="880af-121">すべての **PSSession** は、セッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="880af-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="880af-122">セッション構成は、セッションで使用できるモジュール、実行を許可されているコマンドレット、言語モード、クォータ、タイムアウトなどの **PSSession** の機能を決定します。</span><span class="sxs-lookup"><span data-stu-id="880af-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="880af-123">セッション構成のセキュリティ記述子は、セッション構成を使用してローカルコンピューターに接続できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="880af-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="880af-124">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="880af-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="880af-125">セッション構成のプロパティを表示するに `Get-PSSessionConfiguration` は、コマンドレットまたは WSMan プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="880af-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="880af-126">WSMan プロバイダーの詳細については、「」と入力 `Get-Help WSMan` してください。</span><span class="sxs-lookup"><span data-stu-id="880af-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="880af-127">例</span><span class="sxs-lookup"><span data-stu-id="880af-127">EXAMPLES</span></span>

### <span data-ttu-id="880af-128">例 1: スレッドのアパートメント状態を変更する</span><span class="sxs-lookup"><span data-stu-id="880af-128">Example 1: Change the thread apartment state</span></span>

```
PS C:\> Set-PSSessionConfiguration -Name "MaintenanceShell" -ThreadApartmentState STA
```

<span data-ttu-id="880af-129">このコマンドは、MaintenanceShell 構成のスレッド アパートメント状態を STA に変更します。</span><span class="sxs-lookup"><span data-stu-id="880af-129">This command changes the thread apartment state in the MaintenanceShell configuration to STA.</span></span>
<span data-ttu-id="880af-130">変更は、 **WinRM** サービスを再起動すると有効になります。</span><span class="sxs-lookup"><span data-stu-id="880af-130">The change is effective when you restart the **WinRM** service.</span></span>

### <span data-ttu-id="880af-131">例 2: セッション構成を作成して変更する</span><span class="sxs-lookup"><span data-stu-id="880af-131">Example 2: Create and change a session configuration</span></span>

<span data-ttu-id="880af-132">この例では、構成からスタートアップスクリプトを追加および削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="880af-132">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="880af-133">最初のコマンドは、 **Adminshell** 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="880af-133">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="880af-134">2番目のコマンドは、 `AdminConfig.ps1` 構成にスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="880af-134">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="880af-135">変更は、 **WinRM** を再起動すると有効になります。</span><span class="sxs-lookup"><span data-stu-id="880af-135">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="880af-136">3番目のコマンドは、 `AdminConfig.ps1` 構成からスクリプトを削除します。</span><span class="sxs-lookup"><span data-stu-id="880af-136">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="880af-137">例 3: 結果を表示する</span><span class="sxs-lookup"><span data-stu-id="880af-137">Example 3: Display results</span></span>

<span data-ttu-id="880af-138">この例では、 **MaximumReceivedObjectSizeMB** プロパティの値を20に増やしています。</span><span class="sxs-lookup"><span data-stu-id="880af-138">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="880af-139">このコマンドでは、 **WinRM** サービスの再起動を求めるメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="880af-139">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="880af-140">変更は、 **WinRM** サービスが再起動されるまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="880af-140">The change is not effective until the **WinRM** service is restarted.</span></span>

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

### <span data-ttu-id="880af-141">例 4: さまざまな方法で結果を表示する</span><span class="sxs-lookup"><span data-stu-id="880af-141">Example 4: Display results in different ways</span></span>

<span data-ttu-id="880af-142">この例では、によって、 `Set-PSSessionConfiguration` **MaintenanceShell** セッション構成のスタートアップスクリプトがに変更され `Maintenance.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="880af-142">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="880af-143">出力には変更が示され、 **WinRM** サービスの再起動を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="880af-143">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="880af-144">これに対する応答は "y" (はい) です。</span><span class="sxs-lookup"><span data-stu-id="880af-144">The response is "y" (yes).</span></span>

<span data-ttu-id="880af-145">`Get-PSSessionConfiguration`**MaintenanceShell** セッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="880af-145">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="880af-146">パイプライン演算子 (|) は、コマンドの結果をに送信し `Format-List` ます。これにより、構成オブジェクトのすべてのプロパティがリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="880af-146">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="880af-147">次に、WSMan プロバイダーを使用して、 **MaintenanceShell** 構成の初期化パラメーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="880af-147">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="880af-148">`Get-ChildItem`(エイリアス `dir` ) **MaintenanceShell** プラグインの **InitializationParameters** ノード内の子項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="880af-148">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="880af-149">WSMan プロバイダーの詳細については、「」と入力 `Get-Help wsman` してください。</span><span class="sxs-lookup"><span data-stu-id="880af-149">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

```
PS> Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

PS> Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *

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

PS> dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## <span data-ttu-id="880af-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="880af-150">PARAMETERS</span></span>

### <span data-ttu-id="880af-151">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="880af-151">-AccessMode</span></span>

<span data-ttu-id="880af-152">セッション構成を有効化および無効化し、コンピューター上のリモート セッションまたはローカル セッションにセッション構成を使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="880af-152">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="880af-153">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="880af-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="880af-154">無効にします。</span><span class="sxs-lookup"><span data-stu-id="880af-154">Disabled.</span></span> <span data-ttu-id="880af-155">セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="880af-155">Disables the session configuration.</span></span> <span data-ttu-id="880af-156">コンピューターへのリモート アクセスまたはローカル アクセスに使用できません。</span><span class="sxs-lookup"><span data-stu-id="880af-156">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="880af-157">この値は、セッション構成の **Enabled** プロパティ ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) を **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="880af-157">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="880af-158">Local。</span><span class="sxs-lookup"><span data-stu-id="880af-158">Local.</span></span> <span data-ttu-id="880af-159">**Network_Deny_All** エントリをセッション構成のセキュリティ記述子に追加します。</span><span class="sxs-lookup"><span data-stu-id="880af-159">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="880af-160">ローカルコンピューターのユーザーは、セッション構成を使用して同じコンピューター上にローカルループバックセッションを作成できますが、リモートユーザーはアクセスを拒否されます。</span><span class="sxs-lookup"><span data-stu-id="880af-160">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="880af-161">[Remote]\(リモート\)。</span><span class="sxs-lookup"><span data-stu-id="880af-161">Remote.</span></span> <span data-ttu-id="880af-162">**Deny_All** エントリと **Network_Deny_All** エントリをセッション構成のセキュリティ記述子から削除します。</span><span class="sxs-lookup"><span data-stu-id="880af-162">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="880af-163">ローカル コンピューターおよびリモート コンピューターのユーザーは、セッション構成を使用して、このコンピューターでセッションを作成し、コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="880af-163">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="880af-164">既定値は **Remote** です。</span><span class="sxs-lookup"><span data-stu-id="880af-164">The default value is **Remote**.</span></span>

<span data-ttu-id="880af-165">他のコマンドレットでは、後でこのパラメーターの値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="880af-165">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="880af-166">たとえば、 `Enable-PSRemoting` コマンドレットは、コンピューター上のすべてのセッション構成を有効にし、それらへのリモートアクセスを許可し `Disable-PSRemoting` ます。また、コマンドレットは、コンピューター上のすべてのセッション構成へのローカルアクセスのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="880af-166">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="880af-167">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="880af-167">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="880af-168">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="880af-168">-ApplicationBase</span></span>

<span data-ttu-id="880af-169">\* **AssemblyName** パラメーターの値に指定されているアセンブリファイル (.dll) のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-169">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="880af-170">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="880af-170">-AssemblyName</span></span>

<span data-ttu-id="880af-171">アセンブリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-171">Specifies the assembly name.</span></span> <span data-ttu-id="880af-172">このコマンドレットは、アセンブリで定義されているクラスに基づいてセッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="880af-172">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="880af-173">セッション構成を定義するアセンブリ .dll ファイルのファイル名または完全パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="880af-173">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="880af-174">ファイル名だけを入力した場合は、 **ApplicationBase** パラメーターの値でパスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="880af-174">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

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

### <span data-ttu-id="880af-175">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="880af-175">-ConfigurationTypeName</span></span>

<span data-ttu-id="880af-176">**AssemblyName** パラメーターのアセンブリで定義されているセッションの構成の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-176">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="880af-177">指定する型は、 **System.Management.Automation.Remoting.PSSessionConfiguration** クラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="880af-177">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="880af-178">アセンブリ名を指定する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="880af-178">This parameter is required when you specify an assembly name.</span></span>

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

### <span data-ttu-id="880af-179">-Force</span><span class="sxs-lookup"><span data-stu-id="880af-179">-Force</span></span>

<span data-ttu-id="880af-180">すべてのユーザープロンプトを非表示にし、プロンプトを表示せずに **WinRM** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="880af-180">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="880af-181">サービスを再起動すると、構成の変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="880af-181">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="880af-182">再起動を回避し、再起動メッセージを表示しないようにするには、 **NoServiceRestart** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="880af-182">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="880af-183">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="880af-183">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="880af-184">このコンピューターに1つのリモートコマンドで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-184">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="880af-185">データ サイズはメガバイト (MB) 単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="880af-185">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="880af-186">既定値は 50 MB です。</span><span class="sxs-lookup"><span data-stu-id="880af-186">The default is 50 MB.</span></span>

<span data-ttu-id="880af-187">**Configurationtypename** パラメーターで指定された構成の種類でデータサイズの制限が定義されている場合、構成の種類の制限が使用されます。</span><span class="sxs-lookup"><span data-stu-id="880af-187">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="880af-188">このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="880af-188">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="880af-189">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="880af-189">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="880af-190">このコンピューターに1つのオブジェクトで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-190">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="880af-191">データサイズをメガバイト単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="880af-191">Enter the data size in megabytes.</span></span> <span data-ttu-id="880af-192">既定値は 10 MB です。</span><span class="sxs-lookup"><span data-stu-id="880af-192">The default is 10 MB.</span></span>

<span data-ttu-id="880af-193">**Configurationtypename** パラメーターで指定された構成の種類でオブジェクトサイズの制限が定義されている場合、構成の種類の制限が使用されます。</span><span class="sxs-lookup"><span data-stu-id="880af-193">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="880af-194">このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="880af-194">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="880af-195">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="880af-195">-ModulesToImport</span></span>

<span data-ttu-id="880af-196">セッション構成を使用するセッションに自動的にインポートされたモジュールおよびスナップインを指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-196">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="880af-197">モジュール名およびスナップイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="880af-197">Enter the module and snap-in names.</span></span>

<span data-ttu-id="880af-198">既定では、 **PowerShell** のみがセッションにインポートされますが、コマンドレットが除外されていない限り、 `Import-Module` および Add-PSSnapin コマンドレットを使用して、モジュールとスナップインをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="880af-198">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="880af-199">このパラメーター値に指定されたモジュールは、セッション構成ファイル () で指定されたモジュールに追加され `New-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="880af-199">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="880af-200">ただし、セッション構成ファイル内の設定によって、モジュールでエクスポートされたコマンドが非表示になったり、ユーザーが使用できなくなったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="880af-200">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="880af-201">このパラメーター値に指定されたモジュールは、コマンドレットの **ModulesToImport** パラメーターを使用して指定されたモジュールの一覧に置き換わるもの `Register-PSSessionConfiguration` です。</span><span class="sxs-lookup"><span data-stu-id="880af-201">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="880af-202">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="880af-202">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="880af-203">-Name</span><span class="sxs-lookup"><span data-stu-id="880af-203">-Name</span></span>

<span data-ttu-id="880af-204">変更するセッション構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-204">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="880af-205">このパラメーターを使用してセッション構成の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="880af-205">You cannot use this parameter to change the name of the session configuration.</span></span>

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

### <span data-ttu-id="880af-206">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="880af-206">-NoServiceRestart</span></span>

<span data-ttu-id="880af-207">は、 **WinRM** サービスを再起動せず、サービスの再起動を求めるメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="880af-207">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="880af-208">既定では、を実行すると `Set-PSSessionConfiguration` 、新しいセッション構成を有効にするために **WinRM** サービスを再起動するように求められます。</span><span class="sxs-lookup"><span data-stu-id="880af-208">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="880af-209">**WinRM** サービスが再起動されるまで、新しいセッション構成は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="880af-209">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="880af-210">プロンプトを表示せずに **WinRM** サービスを再起動するには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="880af-210">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="880af-211">**WinRM** サービスを手動で再起動するには、コマンドレットを使用し `Restart-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="880af-211">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="880af-212">-Path</span><span class="sxs-lookup"><span data-stu-id="880af-212">-Path</span></span>

<span data-ttu-id="880af-213">セッション構成ファイル (.pssc) のパス (コマンドレットによって作成されたものなど) を指定します `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="880af-213">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="880af-214">パスを省略した場合、既定値は現在のディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="880af-214">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="880af-215">セッション構成ファイルを変更する方法の詳細については、コマンドレットのヘルプトピックを参照してください `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="880af-215">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="880af-216">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="880af-216">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="880af-217">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="880af-217">-PSVersion</span></span>

<span data-ttu-id="880af-218">このセッション構成を使用するセッションの PowerShell のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-218">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="880af-219">このパラメーターの値は、セッション構成ファイルの **PowerShellVersion** キーの値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="880af-219">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="880af-220">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="880af-220">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="880af-221">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="880af-221">-RunAsCredential</span></span>

<span data-ttu-id="880af-222">セッションのコマンドの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-222">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="880af-223">既定では、コマンドは現在のユーザーのアクセス許可で実行されます。</span><span class="sxs-lookup"><span data-stu-id="880af-223">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="880af-224">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="880af-224">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="880af-225">-Security記述子 Sddl</span><span class="sxs-lookup"><span data-stu-id="880af-225">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="880af-226">構成に対して別のセキュリティ記述子定義言語 (SDDL) 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-226">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="880af-227">この文字列によって、新しいセッション構成を使用するために必要なアクセス許可が決定します。</span><span class="sxs-lookup"><span data-stu-id="880af-227">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="880af-228">セッションでセッション構成を使用するには、その構成に対して少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="880af-228">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="880af-229">構成に既定のセキュリティ記述子を使用するには、空の文字列 ("") またはの値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="880af-229">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="880af-230">既定値は、WSMan: ドライブのルート SDDL です。</span><span class="sxs-lookup"><span data-stu-id="880af-230">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="880af-231">セキュリティ記述子が複雑な場合は、このパラメーターの代わりに **Showsecuritydescriptor ui** パラメーターを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="880af-231">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="880af-232">両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="880af-232">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="880af-233">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="880af-233">-SessionTypeOption</span></span>

<span data-ttu-id="880af-234">セッション構成の種類固有のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-234">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="880af-235">コマンドレットが返す **Psworkflowexecutionoption** オブジェクトなど、セッションの種類のオプションオブジェクトを入力し `New-PSWorkflowExecutionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="880af-235">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="880af-236">セッション構成を使用するセッションのオプションは、セッション オプションの値とセッション構成オプションによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="880af-236">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="880af-237">指定しない限り、セッションで設定されているオプション (コマンドレットを使用するなど) は、 `New-PSSessionOption` セッション構成で設定されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="880af-237">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="880af-238">ただし、セッション オプションの値は、セッション構成に設定されている最大値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="880af-238">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="880af-239">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="880af-239">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="880af-240">-Showsecurity記述子 Ui</span><span class="sxs-lookup"><span data-stu-id="880af-240">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="880af-241">このコマンドレットが、セッション構成の新しい SDDL の作成に役立つプロパティシートであることを示します。</span><span class="sxs-lookup"><span data-stu-id="880af-241">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="880af-242">コマンドを実行し `Set-PSSessionConfiguration` てから **WinRM** サービスを再起動すると、プロパティシートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="880af-242">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="880af-243">構成にアクセス許可を設定する場合は、セッションでセッション構成を使用するには、少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="880af-243">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="880af-244">**SecurityDescriptorSDDL** パラメーターとこのパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="880af-244">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="880af-245">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="880af-245">-StartupScript</span></span>

<span data-ttu-id="880af-246">構成のスタートアップスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-246">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="880af-247">PowerShell スクリプトの完全修飾パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="880af-247">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="880af-248">指定されたスクリプトが、セッション構成を使用する新しいセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="880af-248">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="880af-249">セッション構成からスタートアップスクリプトを削除するには、空の文字列 ("") または値を入力し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="880af-249">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="880af-250">スタートアップスクリプトを使用して、ユーザーセッションをさらに構成することができます。</span><span class="sxs-lookup"><span data-stu-id="880af-250">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="880af-251">スクリプトでエラーが発生しても、終了しないエラーが発生しても、セッションは作成されず、 `New-PSSession` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="880af-251">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="880af-252">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="880af-252">-ThreadApartmentState</span></span>

<span data-ttu-id="880af-253">セッションのスレッドのアパートメント状態設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-253">Specifies the apartment state setting for the threads in the session.</span></span>
<span data-ttu-id="880af-254">このパラメーターに指定できる値は、STA、MTA、および Unknown です。</span><span class="sxs-lookup"><span data-stu-id="880af-254">The acceptable values for this parameter are: STA, MTA, and Unknown.</span></span>
<span data-ttu-id="880af-255">既定値は Unknown です。</span><span class="sxs-lookup"><span data-stu-id="880af-255">The default value is Unknown.</span></span>

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:
Accepted values: STA, MTA, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="880af-256">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="880af-256">-ThreadOptions</span></span>

<span data-ttu-id="880af-257">構成のスレッドオプション設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-257">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="880af-258">この設定は、セッションでコマンドが実行されたときのスレッドの作成方法および使用方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="880af-258">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="880af-259">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="880af-259">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="880af-260">Default</span><span class="sxs-lookup"><span data-stu-id="880af-260">Default</span></span>
- <span data-ttu-id="880af-261">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="880af-261">ReuseThread</span></span>
- <span data-ttu-id="880af-262">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="880af-262">UseCurrentThread</span></span>
- <span data-ttu-id="880af-263">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="880af-263">UseNewThread</span></span>

<span data-ttu-id="880af-264">既定値は **UseCurrentThread** です。</span><span class="sxs-lookup"><span data-stu-id="880af-264">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="880af-265">詳細については、「 [Psthreadoptions 列挙型](/dotnet/api/system.management.automation.runspaces.psthreadoptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="880af-265">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

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

### <span data-ttu-id="880af-266">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="880af-266">-TransportOption</span></span>

<span data-ttu-id="880af-267">セッション構成のトランスポートオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="880af-267">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="880af-268">トランスポートオプションオブジェクト (コマンドレットが返す **Wsmanconfigurationoption** オブジェクトなど) を入力し `New-PSTransportOption` ます。</span><span class="sxs-lookup"><span data-stu-id="880af-268">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="880af-269">セッション構成を使用するセッションのオプションは、セッション オプションの値とセッション構成オプションによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="880af-269">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="880af-270">指定しない限り、セッションで設定されているオプション (コマンドレットを使用するなど) は、 `New-PSSessionOption` セッション構成で設定されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="880af-270">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="880af-271">ただし、セッション オプションの値は、セッション構成に設定されている最大値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="880af-271">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="880af-272">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="880af-272">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="880af-273">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="880af-273">-UseSharedProcess</span></span>

<span data-ttu-id="880af-274">同じユーザーによって開始され、同じセッション構成を使用するすべてのセッションをホストするには、1つのプロセスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="880af-274">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="880af-275">既定では、各セッションは、個別のプロセスでホストされます。</span><span class="sxs-lookup"><span data-stu-id="880af-275">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="880af-276">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="880af-276">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="880af-277">-Confirm</span><span class="sxs-lookup"><span data-stu-id="880af-277">-Confirm</span></span>

<span data-ttu-id="880af-278">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="880af-278">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="880af-279">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="880af-279">-WhatIf</span></span>

<span data-ttu-id="880af-280">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="880af-280">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="880af-281">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="880af-281">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="880af-282">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="880af-282">CommonParameters</span></span>

<span data-ttu-id="880af-283">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="880af-283">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="880af-284">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="880af-284">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="880af-285">入力</span><span class="sxs-lookup"><span data-stu-id="880af-285">INPUTS</span></span>

### <span data-ttu-id="880af-286">なし</span><span class="sxs-lookup"><span data-stu-id="880af-286">None</span></span>

<span data-ttu-id="880af-287">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="880af-287">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="880af-288">出力</span><span class="sxs-lookup"><span data-stu-id="880af-288">OUTPUTS</span></span>

### <span data-ttu-id="880af-289">WSManConfigLeafElement のようになります。</span><span class="sxs-lookup"><span data-stu-id="880af-289">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="880af-290">注</span><span class="sxs-lookup"><span data-stu-id="880af-290">NOTES</span></span>

<span data-ttu-id="880af-291">このコマンドレットを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="880af-291">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="880af-292">`Set-PSSessionConfiguration`コマンドレットは構成名を変更せず、 **WSMan** プロバイダーはコマンドレットをサポートしていません `Rename-Item` 。</span><span class="sxs-lookup"><span data-stu-id="880af-292">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="880af-293">セッション構成の名前を変更するには、コマンドレットを使用して構成を削除した後、コマンドレットを使用して、 `Unregister-PSSessionConfiguration` `Register-PSSessionConfiguration` 新しいセッション構成を作成して登録します。</span><span class="sxs-lookup"><span data-stu-id="880af-293">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="880af-294">コマンドレットを使用して、 `Set-PSSessionConfiguration` 既定の microsoft.powershell32 セッション構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="880af-294">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="880af-295">これらの構成は保護されません。</span><span class="sxs-lookup"><span data-stu-id="880af-295">They are not protected.</span></span> <span data-ttu-id="880af-296">既定のセッション構成の元のバージョンに戻すには、コマンドレットを使用して `Unregister-PSSessionConfiguration` 既定のセッション構成を削除してから、コマンドレットを使用し `Enable-PSRemoting` て復元します。</span><span class="sxs-lookup"><span data-stu-id="880af-296">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="880af-297">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="880af-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="880af-298">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="880af-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="880af-299">WSMan: ドライブでコマンドを使用して、セッション構成のプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="880af-299">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="880af-300">ただし、powershell 2.0 で WSMan: ドライブを使用して、 **OutputBufferingMode** などの powershell 3.0 で導入されたセッション構成プロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="880af-300">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="880af-301">Windows PowerShell 2.0 のコマンドではエラーは生成されませんが、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="880af-301">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="880af-302">PowerShell 3.0 で導入されたプロパティを変更するには、PowerShell 3.0 で WSMan: ドライブを使用します。</span><span class="sxs-lookup"><span data-stu-id="880af-302">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="880af-303">関連リンク</span><span class="sxs-lookup"><span data-stu-id="880af-303">RELATED LINKS</span></span>

[<span data-ttu-id="880af-304">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="880af-304">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="880af-305">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="880af-305">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="880af-306">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="880af-306">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="880af-307">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="880af-307">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="880af-308">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="880af-308">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="880af-309">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="880af-309">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="880af-310">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="880af-310">New-PSWorkflowExecutionOption</span></span>](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[<span data-ttu-id="880af-311">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="880af-311">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="880af-312">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="880af-312">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="880af-313">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="880af-313">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="880af-314">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="880af-314">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="880af-315">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="880af-315">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="880af-316">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="880af-316">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="880af-317">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="880af-317">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
