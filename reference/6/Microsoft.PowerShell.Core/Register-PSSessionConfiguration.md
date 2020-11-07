---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSSessionConfiguration
ms.openlocfilehash: 6417881880cb7f317e7a42d6749b8b7f2cb712fb
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345478"
---
# <span data-ttu-id="f4794-103">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4794-103">Register-PSSessionConfiguration</span></span>

## <span data-ttu-id="f4794-104">概要</span><span class="sxs-lookup"><span data-stu-id="f4794-104">SYNOPSIS</span></span>
<span data-ttu-id="f4794-105">新しいセッション構成を作成して登録します。</span><span class="sxs-lookup"><span data-stu-id="f4794-105">Creates and registers a new session configuration.</span></span>

## <span data-ttu-id="f4794-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4794-106">SYNTAX</span></span>

### <span data-ttu-id="f4794-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="f4794-107">NameParameterSet (Default)</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-SessionType <PSSessionType>]
 [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f4794-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="f4794-108">AssemblyNameParameterSet</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-AssemblyName] <String>
 [-ApplicationBase <String>] [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f4794-109">セッションのすべてのもの</span><span class="sxs-lookup"><span data-stu-id="f4794-109">SessionConfigurationFile</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String>
 [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f4794-110">Description</span><span class="sxs-lookup"><span data-stu-id="f4794-110">DESCRIPTION</span></span>

<span data-ttu-id="f4794-111">`Register-PSSessionConfiguration`コマンドレットは、新しいセッション構成を作成し、ローカルコンピューターに登録します。</span><span class="sxs-lookup"><span data-stu-id="f4794-111">The `Register-PSSessionConfiguration` cmdlet creates and registers a new session configuration on the local computer.</span></span> <span data-ttu-id="f4794-112">これは、リモートユーザー向けのカスタムセッションの作成に使用できる高度なコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="f4794-112">This is an advanced cmdlet that you can use to create custom sessions for remote users.</span></span>

<span data-ttu-id="f4794-113">すべての PowerShell セッション ( **PSSession** ) は、エンドポイントとも呼ばれるセッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4794-113">Every PowerShell session ( **PSSession** ) uses a session configuration, also known as an endpoint.</span></span>
<span data-ttu-id="f4794-114">ユーザーは、コンピューターに接続するセッションを作成するときに、セッション構成を選択するか、PowerShell リモート処理を有効にしたときに登録される既定のセッション構成を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f4794-114">When users create a session that connects to the computer, they can select a session configuration or use the default session configuration that is registered when you enable PowerShell remoting.</span></span>
<span data-ttu-id="f4794-115">また、現在のセッションで作成されたリモート セッション用の既定の構成を指定する、$PSSessionConfigurationName 設定変数を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4794-115">Users can also set the $PSSessionConfigurationName preference variable, which specifies a default configuration for remote sessions created in the current session.</span></span>

<span data-ttu-id="f4794-116">このセッション構成は、リモート セッションの環境を定義します。</span><span class="sxs-lookup"><span data-stu-id="f4794-116">The session configuration defines the environment for the remote session.</span></span> <span data-ttu-id="f4794-117">この構成により、セッションで使用できるコマンドおよび言語要素を決定できます。これには、セッションがリモートで取得できる 1 つのオブジェクトまたはコマンド内のデータの量を制限する設定など、コンピューターを保護する設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f4794-117">The configuration can determine which commands and language elements are available in the session, and it can include settings that protect the computer, such as those that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="f4794-118">セッション構成のセキュリティ記述子によって、セッション構成を使用するアクセス許可を持つユーザーが決定されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-118">The security descriptor of the session configuration determines which users have permission to use the session configuration.</span></span>

<span data-ttu-id="f4794-119">構成の要素を定義するには、新しい構成クラスを実装するアセンブリを使用するか、セッションで実行されるスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4794-119">You can define the elements of configuration by using an assembly that implements a new configuration class and by using a script that runs in the session.</span></span> <span data-ttu-id="f4794-120">PowerShell 3.0 以降では、セッション構成ファイルを使用してセッション構成を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4794-120">Beginning in PowerShell 3.0, you can also use a session configuration file to define the session configuration.</span></span>

<span data-ttu-id="f4794-121">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4794-121">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>
<span data-ttu-id="f4794-122">セッション構成ファイルの詳細については、「 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4794-122">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

## <span data-ttu-id="f4794-123">例</span><span class="sxs-lookup"><span data-stu-id="f4794-123">EXAMPLES</span></span>

### <span data-ttu-id="f4794-124">例 1: NewShell セッション構成を登録する</span><span class="sxs-lookup"><span data-stu-id="f4794-124">Example 1: Register a NewShell session configuration</span></span>

<span data-ttu-id="f4794-125">この例では、 **Newshell** セッション構成を登録します。</span><span class="sxs-lookup"><span data-stu-id="f4794-125">In this example, we register the **NewShell** session configuration.</span></span> <span data-ttu-id="f4794-126">**AssemblyName** パラメーターと **ApplicationBase** パラメーターは、セッション構成のコマンドレットとプロバイダーを指定する **MyShell.dll** ファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-126">The **AssemblyName** and **ApplicationBase** parameters specify the location of the **MyShell.dll** file, which specifies the cmdlets and providers in the session configuration.</span></span> <span data-ttu-id="f4794-127">**Configurationtypename** パラメーターは、アセンブリから使用する構成クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-127">The **ConfigurationTypeName** parameter specifies the configuration class to use from the assembly.</span></span>

```powershell
$sessionConfiguration = @{
    Name='NewShell'
    ApplicationBase='c:\MyShells\'
    AssemblyName='MyShell.dll'
    ConfigurationTypeName='MyClass'
}
Register-PSSessionConfiguration @sessionConfiguration
```

<span data-ttu-id="f4794-128">この構成を使用するには、「」と入力 `New-PSSession -ConfigurationName newshell` します。</span><span class="sxs-lookup"><span data-stu-id="f4794-128">To use this configuration, type `New-PSSession -ConfigurationName newshell`.</span></span>

### <span data-ttu-id="f4794-129">例 2: MaintenanceShell セッション構成を登録する</span><span class="sxs-lookup"><span data-stu-id="f4794-129">Example 2: Register a MaintenanceShell session configuration</span></span>

<span data-ttu-id="f4794-130">この例では、ローカルコンピューターに **MaintenanceShell** セッション構成を登録します。</span><span class="sxs-lookup"><span data-stu-id="f4794-130">This example registers the **MaintenanceShell** session configuration on the local computer.</span></span> <span data-ttu-id="f4794-131">**Startupscript** パラメーターは、スクリプトを指定し `Maintenance.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="f4794-131">The **StartupScript** parameter specifies the `Maintenance.ps1` script.</span></span>

```powershell
Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
```

<span data-ttu-id="f4794-132">ユーザーがコマンドを使用 `New-PSSession` して **MaintenanceShell** 構成を選択すると、 `Maintenance.ps1` スクリプトは新しいセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-132">When a user uses a `New-PSSession` command and selects the **MaintenanceShell** configuration, the `Maintenance.ps1` script runs in the new session.</span></span> <span data-ttu-id="f4794-133">このスクリプトでは、セッションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f4794-133">The script can configure the session.</span></span> <span data-ttu-id="f4794-134">これには、モジュールのインポートや、セッションの実行ポリシーの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4794-134">This includes importing modules and setting the execution policy for the session.</span></span> <span data-ttu-id="f4794-135">スクリプトによってエラー (終了しないエラーを含む) が生成された場合、 `New-PSSession` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4794-135">If the script generates any errors, including non-terminating errors, the `New-PSSession` command fails.</span></span>

### <span data-ttu-id="f4794-136">例 3: セッション構成を登録する</span><span class="sxs-lookup"><span data-stu-id="f4794-136">Example 3: Register a session configuration</span></span>

<span data-ttu-id="f4794-137">この例では、 **Adminshell** セッション構成を登録します。</span><span class="sxs-lookup"><span data-stu-id="f4794-137">This example registers the **AdminShell** session configuration.</span></span>

<span data-ttu-id="f4794-138">変数は、 `$sessionParams` すべてのパラメーター値を含むハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="f4794-138">The `$sessionParams` variable is a hashtable containing all the parameter values.</span></span> <span data-ttu-id="f4794-139">このハッシュテーブルは、PowerShell スプラッティングを使用してコマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-139">This hashtable is passed to the cmdlet using PowerShell splatting.</span></span> <span data-ttu-id="f4794-140">このコマンドでは、 `Register-PSSessionConfiguration` **SecurityDescritorSDDL** パラメーターを使用して変数の値に SDDL を指定し、MaximumReceivedObjectSizeMB パラメーターを使用して `$sddl` オブジェクトサイズの制限を増やしています。 **MaximumReceivedObjectSizeMB**</span><span class="sxs-lookup"><span data-stu-id="f4794-140">The `Register-PSSessionConfiguration` command uses the **SecurityDescritorSDDL** parameter to specify the SDDL in the value of the `$sddl` variable and the **MaximumReceivedObjectSizeMB** parameter to increase the object size limit.</span></span> <span data-ttu-id="f4794-141">また、 **StartupScript** パラメーターを使用して、セッションを構成するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-141">It also uses the **StartupScript** parameter to specify a script that configures the session.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;FA;SA;GWGX;;WD)"
$sessionParams = @{
    Name="AdminShell"
    SecurityDescriptorSDDL=$sddl
    MaximumReceivedObjectSizeMB=20
    StartupScript="C:\scripts\AdminShell.ps1"
}
Register-PSSessionConfiguration @sessionParams
```

### <span data-ttu-id="f4794-142">例 4: 構成コンテナー要素を返す</span><span class="sxs-lookup"><span data-stu-id="f4794-142">Example 4: Return a configuration container element</span></span>

<span data-ttu-id="f4794-143">この例では、 **MaintenanceShell** 構成を登録する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f4794-143">This example shows how to register the **MaintenanceShell** configuration.</span></span>
<span data-ttu-id="f4794-144">`Register-PSSessionConfiguration` 変数に格納されている **WSManConfigContainerElement** オブジェクトを返し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="f4794-144">`Register-PSSessionConfiguration` returns a **WSManConfigContainerElement** object stored in the `$s` variable.</span></span> <span data-ttu-id="f4794-145">`Format-List` 返されたオブジェクトのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="f4794-145">`Format-List` displays all the properties of the returned object.</span></span> <span data-ttu-id="f4794-146">**PSPath** プロパティは、オブジェクトが WSMan: ドライブのディレクトリに格納されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f4794-146">The **PSPath** property shows that the object is stored in a directory of the WSMan: drive.</span></span> <span data-ttu-id="f4794-147">`Get-ChildItem` (エイリアス `dir` )パス内の項目を表示 `WSMan:\LocalHost\PlugIn` します。</span><span class="sxs-lookup"><span data-stu-id="f4794-147">`Get-ChildItem` (alias `dir`) displays the items in the `WSMan:\LocalHost\PlugIn` path.</span></span> <span data-ttu-id="f4794-148">これには、新しい **MaintenanceShell** 構成と、PowerShell に付属する2つの既定の構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4794-148">These include the new **MaintenanceShell** configuration and the two default configurations that come with PowerShell.</span></span>

```powershell
$s = Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
$s | Format-List -Property *
dir WSMan:\LocalHost\Plugin
```

```Output
PSPath            : Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell
PSParentPath      : Microsoft.WSMan.Management\WSMan::localhost\Plugin
PSChildName       : MaintenanceShell
PSDrive           : WSMan
PSProvider        : Microsoft.WSMan.Management\WSMan
PSIsContainer     : True
Keys              : {Name=MaintenanceShell}
Name              : MaintenanceShell
TypeNameOfElement : Container

Name                      Type                 Keys
----                      ----                 ----
MaintenanceShell          Container            {Name=MaintenanceShell}
microsoft.powershell      Container            {Name=microsoft.powershell}
microsoft.powershell32    Container            {Name=microsoft.powershell32}
```

### <span data-ttu-id="f4794-149">例 5: スタートアップスクリプトを使用してセッション構成を登録する</span><span class="sxs-lookup"><span data-stu-id="f4794-149">Example 5: Register a session configuration with a startup script</span></span>

<span data-ttu-id="f4794-150">この例では、 **Withprofile** セッション構成を作成して登録します。</span><span class="sxs-lookup"><span data-stu-id="f4794-150">In this example we create and register the **WithProfile** session configuration.</span></span> <span data-ttu-id="f4794-151">**Startupscript** パラメーターは、セッション構成を使用するすべてのセッションに対して、指定されたスクリプトを実行するように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="f4794-151">The **StartupScript** parameter directs PowerShell to run the specified script for any session that uses the session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name WithProfile -StartupScript Add-Profile.ps1
```

<span data-ttu-id="f4794-152">このスクリプトには、ドット ソースを使用してセッションの現在のスコープでユーザーの **CurrentUserAllHosts** プロファイルを実行する、1 つのコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4794-152">The script contains a single command that uses dot sourcing to run the user's **CurrentUserAllHosts** profile in the current scope of the session.</span></span>

<span data-ttu-id="f4794-153">プロファイルの詳細については、「[about_Profiles](./About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4794-153">For more information about profiles, see [about_Profiles](./About/about_Profiles.md).</span></span> <span data-ttu-id="f4794-154">ドット ソースの詳細については、「[about_Scopes](./About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4794-154">For more information about dot sourcing, see [about_Scopes](./About/about_Scopes.md).</span></span>

## <span data-ttu-id="f4794-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4794-155">PARAMETERS</span></span>

### <span data-ttu-id="f4794-156">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="f4794-156">-AccessMode</span></span>

<span data-ttu-id="f4794-157">セッション構成を有効化および無効化し、コンピューター上のリモート セッションまたはローカル セッションにセッション構成を使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-157">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="f4794-158">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4794-158">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f4794-159">無効にします。</span><span class="sxs-lookup"><span data-stu-id="f4794-159">Disabled.</span></span> <span data-ttu-id="f4794-160">セッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f4794-160">Disables the session configuration.</span></span> <span data-ttu-id="f4794-161">コンピューターへのリモート アクセスまたはローカル アクセスに使用できません。</span><span class="sxs-lookup"><span data-stu-id="f4794-161">It cannot be used for remote or local access to the computer.</span></span>
- <span data-ttu-id="f4794-162">Local。</span><span class="sxs-lookup"><span data-stu-id="f4794-162">Local.</span></span> <span data-ttu-id="f4794-163">ローカルコンピューターのユーザーがセッション構成を使用して、同じコンピューター上にローカルループバックセッションを作成できますが、リモートユーザーへのアクセスは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-163">Allows users of the local computer to use the session configuration to create a local loopback session on the same computer, but denies access to remote users.</span></span>
- <span data-ttu-id="f4794-164">[Remote]\(リモート\)。</span><span class="sxs-lookup"><span data-stu-id="f4794-164">Remote.</span></span> <span data-ttu-id="f4794-165">ローカル ユーザーおよびリモート ユーザーは、セッション構成を使用して、このコンピューターでセッションを作成し、コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f4794-165">Allows local and remote users to use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="f4794-166">既定値は Remote です。</span><span class="sxs-lookup"><span data-stu-id="f4794-166">The default value is Remote.</span></span>

<span data-ttu-id="f4794-167">他のコマンドレットでは、後でこのパラメーターの値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="f4794-167">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="f4794-168">たとえば、 `Enable-PSRemoting` コマンドレットを使用すると、すべてのセッション構成へのリモートアクセスが可能になり、コマンドレットによって `Enable-PSSessionConfiguration` セッション構成が有効になります。また、コマンドレットにより、 `Disable-PSRemoting` すべてのセッション構成へのリモートアクセスが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-168">For example, the `Enable-PSRemoting` cmdlet allows for remote access to all session configurations, the `Enable-PSSessionConfiguration` cmdlet enables session configurations, and the `Disable-PSRemoting` cmdlet prevents remote access to all session configurations.</span></span>

<span data-ttu-id="f4794-169">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f4794-169">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f4794-170">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="f4794-170">-ApplicationBase</span></span>

<span data-ttu-id="f4794-171">\* **AssemblyName** パラメーターの値に指定されているアセンブリファイル (.dll) のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-171">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span> <span data-ttu-id="f4794-172">**AssemblyName** パラメーターの値にパスが含まれていない場合は、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4794-172">Use this parameter when the value of the **AssemblyName** parameter does not include a path.</span></span> <span data-ttu-id="f4794-173">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="f4794-173">The default is the current directory.</span></span>

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

### <span data-ttu-id="f4794-174">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="f4794-174">-AssemblyName</span></span>

<span data-ttu-id="f4794-175">構成の種類が定義されているアセンブリファイル (.dll) の名前を指定し \* ます。</span><span class="sxs-lookup"><span data-stu-id="f4794-175">Specifies the name of an assembly file (\*.dll) in which the configuration type is defined.</span></span> <span data-ttu-id="f4794-176">このパラメーターに .dll のパスを指定することも、 **ApplicationBase** パラメーターの値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4794-176">You can specify the path of the .dll in this parameter or in the value of the **ApplicationBase** parameter.</span></span>

<span data-ttu-id="f4794-177">**Configurationtypename** パラメーターを指定する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4794-177">This parameter is required when you specify the **ConfigurationTypeName** parameter.</span></span>

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

### <span data-ttu-id="f4794-178">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="f4794-178">-ConfigurationTypeName</span></span>

<span data-ttu-id="f4794-179">この構成に使用される Microsoft .NET Framework の型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-179">Specifies the fully qualified name of the Microsoft .NET Framework type that is used for this configuration.</span></span> <span data-ttu-id="f4794-180">指定する型は、 **System.Management.Automation.Remoting.PSSessionConfiguration** クラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4794-180">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="f4794-181">構成の種類を実装するアセンブリファイル (.dll) を指定するには \* 、 **AssemblyName** パラメーターと **ApplicationBase** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-181">To specify the assembly file (\*.dll) that implements the configuration type, specify the **AssemblyName** and **ApplicationBase** parameters.</span></span>

<span data-ttu-id="f4794-182">型を作成すると、コマンドレットの特定のパラメーターを公開または非表示にしたり、ユーザーが上書きできないデータサイズやオブジェクトサイズの制限を設定したりするなど、セッション構成のさまざまな側面を制御できます。</span><span class="sxs-lookup"><span data-stu-id="f4794-182">Creating a type lets you control more aspects of the session configuration, such as exposing or hiding certain parameters of cmdlets, or setting data size and object size limits that users cannot override.</span></span>

<span data-ttu-id="f4794-183">このパラメーターを省略すると、 **DefaultRemotePowerShellConfiguration** クラスがセッション構成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-183">If you omit this parameter, the **DefaultRemotePowerShellConfiguration** class is used for the session configuration.</span></span>

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

### <span data-ttu-id="f4794-184">-Force</span><span class="sxs-lookup"><span data-stu-id="f4794-184">-Force</span></span>

<span data-ttu-id="f4794-185">すべてのユーザーにプロンプトを表示せずに、 **WinRM** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f4794-185">Suppresses all user prompts and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="f4794-186">サービスを再起動すると、構成の変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="f4794-186">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="f4794-187">再起動を回避し、再起動のプロンプトを非表示にするには、 **NoServiceRestart** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-187">To prevent a restart and suppress the restart prompt, specify the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="f4794-188">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="f4794-188">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="f4794-189">このコンピューターに1つのリモートコマンドで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-189">Specifies a limit for the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="f4794-190">データ サイズはメガバイト (MB) 単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f4794-190">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="f4794-191">既定値は 50 MB です。</span><span class="sxs-lookup"><span data-stu-id="f4794-191">The default is 50 MB.</span></span>

<span data-ttu-id="f4794-192">**ConfigurationTypeName** パラメーターで指定された構成の種類でデータ サイズの制限が定義されている場合、構成の種類の制限が使用され、このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-192">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="f4794-193">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="f4794-193">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="f4794-194">このコンピューターに1つのオブジェクトで送信できるデータ量の制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-194">Specifies a limit for the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="f4794-195">データサイズをメガバイト単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f4794-195">Enter the data size in megabytes.</span></span> <span data-ttu-id="f4794-196">既定値は 10 MB です。</span><span class="sxs-lookup"><span data-stu-id="f4794-196">The default is 10 MB.</span></span>

<span data-ttu-id="f4794-197">**ConfigurationTypeName** パラメーターで指定された構成の種類でオブジェクト サイズの制限が定義されている場合、構成の種類の制限が使用され、このパラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-197">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="f4794-198">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="f4794-198">-ModulesToImport</span></span>

<span data-ttu-id="f4794-199">セッション構成を使用するセッションに自動的にインポートされるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-199">Specifies the modules that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="f4794-200">既定では、セッションにインポートされるのは、 **Microsoft. PowerShell** だけです。</span><span class="sxs-lookup"><span data-stu-id="f4794-200">By default, only **Microsoft.PowerShell.Core** is imported into sessions.</span></span> <span data-ttu-id="f4794-201">コマンドレットが除外されていない限り、を使用し `Import-Module` てモジュールをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f4794-201">Unless the cmdlets are excluded, you can use `Import-Module` to add modules to the session.</span></span>

<span data-ttu-id="f4794-202">このパラメーター値に指定されているモジュールは、 **Sessiontype** パラメーターによって指定されたモジュールと、セッション構成ファイル () の **ModulesToImport** キーに記載されているモジュールに追加され `New-PSSessionConfigurationFile` ます。</span><span class="sxs-lookup"><span data-stu-id="f4794-202">The modules specified in this parameter value are imported in additions to modules that are specified by the **SessionType** parameter and those listed in the **ModulesToImport** key in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="f4794-203">ただし、セッション構成ファイル内の設定によって、モジュールでエクスポートされたコマンドが非表示になったり、ユーザーが使用できなくなったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="f4794-203">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="f4794-204">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f4794-204">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f4794-205">-Name</span><span class="sxs-lookup"><span data-stu-id="f4794-205">-Name</span></span>

<span data-ttu-id="f4794-206">セッション構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-206">Specifies a name for the session configuration.</span></span> <span data-ttu-id="f4794-207">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4794-207">This parameter is required.</span></span>

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

### <span data-ttu-id="f4794-208">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="f4794-208">-NoServiceRestart</span></span>

<span data-ttu-id="f4794-209">は、 **WinRM** サービスを再起動せず、サービスの再起動を求めるメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="f4794-209">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="f4794-210">既定では、コマンドを実行すると、 `Register-PSSessionConfiguration` 新しいセッション構成を有効にするために **WinRM** サービスを再起動するように求められます。</span><span class="sxs-lookup"><span data-stu-id="f4794-210">By default, when you run a `Register-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="f4794-211">**WinRM** サービスが再起動されるまで、新しいセッション構成は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="f4794-211">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="f4794-212">プロンプトを表示せずに **WinRM** サービスを再起動するには、 **Force** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-212">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="f4794-213">**WinRM** サービスを手動で再起動するには、コマンドレットを使用し `Restart-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="f4794-213">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="f4794-214">-Path</span><span class="sxs-lookup"><span data-stu-id="f4794-214">-Path</span></span>

<span data-ttu-id="f4794-215">によって作成されたセッション構成ファイル (.pssc) のパスとファイル名を指定します `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="f4794-215">Specifies the path and filename of a session configuration file (.pssc), such as one created by `New-PSSessionConfigurationFile`.</span></span> <span data-ttu-id="f4794-216">パスを省略した場合、既定値は現在のディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="f4794-216">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="f4794-217">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f4794-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f4794-218">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="f4794-218">-ProcessorArchitecture</span></span>

<span data-ttu-id="f4794-219">このセッション構成を使用するセッションで、32ビットバージョンまたは64ビット版の PowerShell プロセスが開始されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4794-219">Determines whether a 32-bit or 64-bit version of the PowerShell process is started in sessions that use this session configuration.</span></span> <span data-ttu-id="f4794-220">このパラメーターに指定できる値は、x86 (32 ビット) と AMD64 (64 ビット) です。</span><span class="sxs-lookup"><span data-stu-id="f4794-220">The acceptable values for this parameter are: x86 (32-bit) and AMD64 (64-bit).</span></span> <span data-ttu-id="f4794-221">既定値は、セッション構成をホストするプロセッサ アーキテクチャにより決定されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-221">The default value is determined by the processor architecture of the computer that hosts the session configuration.</span></span>

<span data-ttu-id="f4794-222">このパラメーターを使用すると、64 ビット コンピューターで 32 ビット セッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f4794-222">You can use this parameter to create a 32-bit session on a 64-bit computer.</span></span> <span data-ttu-id="f4794-223">32 ビット コンピューターでの 64 ビット プロセスの作成を試行します。</span><span class="sxs-lookup"><span data-stu-id="f4794-223">Attempts to create a 64-bit process on a 32-bit computer fail.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PA
Accepted values: x86, amd64

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4794-224">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="f4794-224">-PSVersion</span></span>

<span data-ttu-id="f4794-225">このセッション構成を使用するセッションの PowerShell のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-225">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="f4794-226">このパラメーターの値は、セッション構成ファイルの **PowerShellVersion** キーの値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-226">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="f4794-227">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f4794-227">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f4794-228">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="f4794-228">-RunAsCredential</span></span>

<span data-ttu-id="f4794-229">セッションのコマンドの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-229">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="f4794-230">既定では、コマンドは現在のユーザーのアクセス許可で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-230">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="f4794-231">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f4794-231">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f4794-232">-Security記述子 Sddl</span><span class="sxs-lookup"><span data-stu-id="f4794-232">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="f4794-233">構成のセキュリティ記述子定義言語 (SDDL) 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-233">Specifies a Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="f4794-234">この文字列によって、新しいセッション構成を使用するために必要なアクセス許可が決定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-234">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="f4794-235">セッションでセッション構成を使用するには、その構成に対して少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4794-235">To use a session configuration in a session, users must have at least Execute (Invoke) permission for the configuration.</span></span>

<span data-ttu-id="f4794-236">セキュリティ記述子が複雑な場合は、このパラメーターの代わりに **ShowSecurityDescriptorUI** パラメーターを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f4794-236">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this parameter.</span></span> <span data-ttu-id="f4794-237">両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4794-237">You cannot use both parameters in the same command.</span></span>

<span data-ttu-id="f4794-238">このパラメーターを省略した場合、 **WinRM** サービスのルート SDDL がこの構成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-238">If you omit this parameter, the root SDDL for the **WinRM** service is used for this configuration.</span></span>
<span data-ttu-id="f4794-239">ルート SDDL を表示または変更するには、WSMan プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4794-239">To view or change the root SDDL, use the WSMan provider.</span></span> <span data-ttu-id="f4794-240">たとえば、「 `Get-Item wsman:\localhost\service\rootSDDL` 」のように指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-240">For example `Get-Item wsman:\localhost\service\rootSDDL`.</span></span> <span data-ttu-id="f4794-241">WSMan プロバイダーの詳細については、「」と入力 `Get-Help wsman` してください。</span><span class="sxs-lookup"><span data-stu-id="f4794-241">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

### <span data-ttu-id="f4794-242">-SessionType</span><span class="sxs-lookup"><span data-stu-id="f4794-242">-SessionType</span></span>

<span data-ttu-id="f4794-243">セッション構成を使用して作成されるセッションの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-243">Specifies the type of session that is created by using the session configuration.</span></span> <span data-ttu-id="f4794-244">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4794-244">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f4794-245">[空]。</span><span class="sxs-lookup"><span data-stu-id="f4794-245">Empty.</span></span> <span data-ttu-id="f4794-246">既定では、セッションに追加されるモジュールはありません。</span><span class="sxs-lookup"><span data-stu-id="f4794-246">No modules are added to session by default.</span></span> <span data-ttu-id="f4794-247">このコマンドレットのパラメーターを使用して、モジュール、関数、スクリプト、およびその他の機能をセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f4794-247">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span>
- <span data-ttu-id="f4794-248">既定値。</span><span class="sxs-lookup"><span data-stu-id="f4794-248">Default.</span></span> <span data-ttu-id="f4794-249">セッションに Microsoft. PowerShell. Core を追加します。</span><span class="sxs-lookup"><span data-stu-id="f4794-249">Adds Microsoft.PowerShell.Core to the session.</span></span> <span data-ttu-id="f4794-250">このモジュールには、 `Import-Module` コマンドレットを明示的に禁止している場合を除き、他のモジュールをインポートするためにユーザーが使用できるコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4794-250">This module includes the `Import-Module` cmdlet that users can use to import other modules unless you explicitly prohibit the cmdlet.</span></span>
- <span data-ttu-id="f4794-251">RestrictedRemoteServer.</span><span class="sxs-lookup"><span data-stu-id="f4794-251">RestrictedRemoteServer.</span></span> <span data-ttu-id="f4794-252">には、、、 `Exit-PSSession` 、、 `Get-Command` 、 `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` 、および `Select-Object` の各コマンドレットだけが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4794-252">Includes only the following cmdlets: `Exit-PSSession`, `Get-Command`, `Get-FormatData`, `Get-Help`, `Measure-Object`, `Out-Default`, and `Select-Object`.</span></span> <span data-ttu-id="f4794-253">スクリプトまたはアセンブリを使用するか、セッション構成ファイルのキーを使用して、モジュール、関数、スクリプト、およびその他の機能をセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f4794-253">Use a script or assembly, or the keys in the session configuration file, to add modules, functions, scripts, and other features to the session.</span></span>

<span data-ttu-id="f4794-254">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="f4794-254">The default value is Default.</span></span>

<span data-ttu-id="f4794-255">このパラメーターの値は、セッション構成ファイルの **Sessiontype** キーの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-255">The value of this parameter takes precedence over the value of the **SessionType** key in the session configuration file.</span></span>

<span data-ttu-id="f4794-256">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f4794-256">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSessionType
Parameter Sets: NameParameterSet
Aliases:
Accepted values: DefaultRemoteShell, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4794-257">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="f4794-257">-SessionTypeOption</span></span>

<span data-ttu-id="f4794-258">セッション構成の種類固有のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-258">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="f4794-259">コマンドレットが返す **Psworkflowexecutionoption** オブジェクトなど、セッションの種類のオプションオブジェクトを入力し `New-PSWorkflowExecutionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="f4794-259">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="f4794-260">セッション構成を使用するセッションのオプションは、セッション オプションの値とセッション構成オプションによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-260">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="f4794-261">指定しない限り、セッションで設定されているオプション (コマンドレットを使用するなど) は、 `New-PSSessionOption` セッション構成で設定されたオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-261">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="f4794-262">ただし、セッション オプションの値は、セッション構成に設定されている最大値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="f4794-262">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="f4794-263">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f4794-263">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f4794-264">-Showsecurity記述子 Ui</span><span class="sxs-lookup"><span data-stu-id="f4794-264">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="f4794-265">このコマンドレットによって、セッション構成の SDDL の作成に役立つプロパティシートが表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f4794-265">Indicates that this cmdlet displays a property sheet that helps you create the SDDL for the session configuration.</span></span> <span data-ttu-id="f4794-266">コマンドを入力 `Register-PSSessionConfiguration` してから **WinRM** サービスを再起動すると、プロパティシートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-266">The property sheet appears after you enter the `Register-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="f4794-267">構成のアクセス許可を設定する場合は、セッションでセッション構成を使用するには、少なくとも実行 (Invoke) アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4794-267">When setting the permissions for the configuration, remember that users must have at least Execute (Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="f4794-268">**SecurityDescriptorSDDL** パラメーターとこのパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4794-268">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="f4794-269">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="f4794-269">-StartupScript</span></span>

<span data-ttu-id="f4794-270">PowerShell スクリプトの完全修飾パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-270">Specifies the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="f4794-271">指定されたスクリプトが、セッション構成を使用する新しいセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-271">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="f4794-272">スクリプトを使用すると、セッションをさらに構成できます。</span><span class="sxs-lookup"><span data-stu-id="f4794-272">You can use the script to additionally configure the session.</span></span> <span data-ttu-id="f4794-273">スクリプトでエラーが発生しても、終了しないエラーが発生しても、セッションは作成されず、 `New-PSSession` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4794-273">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="f4794-274">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="f4794-274">-ThreadOptions</span></span>

<span data-ttu-id="f4794-275">セッションでコマンドを実行するときに、スレッドを作成して使用する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-275">Specifies how threads are created and used when a command runs in the session.</span></span> <span data-ttu-id="f4794-276">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4794-276">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f4794-277">Default</span><span class="sxs-lookup"><span data-stu-id="f4794-277">Default</span></span>
- <span data-ttu-id="f4794-278">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="f4794-278">ReuseThread</span></span>
- <span data-ttu-id="f4794-279">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="f4794-279">UseCurrentThread</span></span>
- <span data-ttu-id="f4794-280">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="f4794-280">UseNewThread</span></span>

<span data-ttu-id="f4794-281">既定値は **UseCurrentThread** です。</span><span class="sxs-lookup"><span data-stu-id="f4794-281">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="f4794-282">詳細については、「 [Psthreadoptions 列挙型](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4794-282">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span></span>

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

### <span data-ttu-id="f4794-283">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="f4794-283">-TransportOption</span></span>

<span data-ttu-id="f4794-284">トランスポートオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4794-284">Specifies the transport option.</span></span>

<span data-ttu-id="f4794-285">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f4794-285">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f4794-286">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="f4794-286">-UseSharedProcess</span></span>

<span data-ttu-id="f4794-287">同じユーザーによって開始され、同じセッション構成を使用するすべてのセッションをホストするには、1つのプロセスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4794-287">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="f4794-288">既定では、各セッションは、個別のプロセスでホストされます。</span><span class="sxs-lookup"><span data-stu-id="f4794-288">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="f4794-289">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f4794-289">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f4794-290">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f4794-290">-Confirm</span></span>

<span data-ttu-id="f4794-291">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4794-291">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f4794-292">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f4794-292">-WhatIf</span></span>

<span data-ttu-id="f4794-293">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="f4794-293">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f4794-294">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f4794-294">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f4794-295">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f4794-295">CommonParameters</span></span>

<span data-ttu-id="f4794-296">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f4794-296">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f4794-297">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4794-297">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f4794-298">入力</span><span class="sxs-lookup"><span data-stu-id="f4794-298">INPUTS</span></span>

### <span data-ttu-id="f4794-299">なし</span><span class="sxs-lookup"><span data-stu-id="f4794-299">None</span></span>

<span data-ttu-id="f4794-300">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f4794-300">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f4794-301">出力</span><span class="sxs-lookup"><span data-stu-id="f4794-301">OUTPUTS</span></span>

### <span data-ttu-id="f4794-302">WSManConfigContainerElement のようになります。</span><span class="sxs-lookup"><span data-stu-id="f4794-302">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>

## <span data-ttu-id="f4794-303">注</span><span class="sxs-lookup"><span data-stu-id="f4794-303">NOTES</span></span>

<span data-ttu-id="f4794-304">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4794-304">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="f4794-305">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4794-305">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="f4794-306">このコマンドレットは、管理用 Web サービス (WS-MANAGEMENT) プラグイン構成を表す XML を生成し、XML を WS-MANAGEMENT に送信します。これにより、ローカルコンピューター () にプラグインが登録され `New-Item wsman:\localhost\plugin` ます。</span><span class="sxs-lookup"><span data-stu-id="f4794-306">This cmdlet generates XML that represents a Web Services for Management (WS-Management) plug-in configuration and sends the XML to WS-Management, which registers the plug-in on the local computer (`New-Item wsman:\localhost\plugin`).</span></span>

<span data-ttu-id="f4794-307">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f4794-307">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="f4794-308">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f4794-308">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="f4794-309">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f4794-309">RELATED LINKS</span></span>

[<span data-ttu-id="f4794-310">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4794-310">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="f4794-311">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4794-311">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="f4794-312">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4794-312">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="f4794-313">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f4794-313">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="f4794-314">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4794-314">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="f4794-315">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f4794-315">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="f4794-316">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4794-316">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="f4794-317">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f4794-317">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="f4794-318">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="f4794-318">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="f4794-319">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="f4794-319">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
