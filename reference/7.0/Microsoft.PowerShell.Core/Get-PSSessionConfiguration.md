---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionConfiguration
ms.openlocfilehash: d0c5f0a967ecd6eb07d7268cc9e25be93cc5f34c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218680"
---
# <span data-ttu-id="dffb1-103">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dffb1-103">Get-PSSessionConfiguration</span></span>

## <span data-ttu-id="dffb1-104">概要</span><span class="sxs-lookup"><span data-stu-id="dffb1-104">SYNOPSIS</span></span>
<span data-ttu-id="dffb1-105">コンピューターに登録されたセッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-105">Gets the registered session configurations on the computer.</span></span>

## <span data-ttu-id="dffb1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dffb1-106">SYNTAX</span></span>

```
Get-PSSessionConfiguration [[-Name] <String[]>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="dffb1-107">Description</span><span class="sxs-lookup"><span data-stu-id="dffb1-107">DESCRIPTION</span></span>

<span data-ttu-id="dffb1-108">`Get-PSSessionConfiguration`コマンドレットは、ローカルコンピューターに登録されているセッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-108">The `Get-PSSessionConfiguration` cmdlet gets the session configurations that have been registered on the local computer.</span></span> <span data-ttu-id="dffb1-109">これは、ユーザーに応じてカスタマイズされたセッション構成を管理するために、システム管理者向けに設計された高度なコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="dffb1-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="dffb1-110">PowerShell 3.0 以降では、セッション構成 (.pssc) ファイルを使用して、セッション構成のプロパティを定義できます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-110">Beginning in PowerShell 3.0, you can define the properties of a session configuration by using a session configuration (.pssc) file.</span></span> <span data-ttu-id="dffb1-111">この機能を使用すると、コンピューター プログラムを記述せずに、カスタマイズされ、制限されたセッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-111">This feature lets you create customized and restricted sessions without writing a computer program.</span></span> <span data-ttu-id="dffb1-112">セッション構成ファイルの詳細については、「[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb1-112">For more information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="dffb1-113">また、PowerShell 3.0 以降では、を返すセッション構成オブジェクトに新しい note プロパティが追加されてい `Get-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-113">Also, beginning in PowerShell 3.0, new note properties have been added to the session configuration object that `Get-PSSessionConfiguration` returns.</span></span> <span data-ttu-id="dffb1-114">ユーザーとセッション構成の作成者は、これらのプロパティによって、セッション構成の比較検討が容易になります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-114">These properties make it easier for users and session configuration authors to examine and compare session configurations.</span></span>

<span data-ttu-id="dffb1-115">セッション構成を作成して登録するには、コマンドレットを使用し `Register-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-115">To create and register a session configuration, use the `Register-PSSessionConfiguration` cmdlet.</span></span>
<span data-ttu-id="dffb1-116">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb1-116">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="dffb1-117">例</span><span class="sxs-lookup"><span data-stu-id="dffb1-117">EXAMPLES</span></span>

### <span data-ttu-id="dffb1-118">例 1-ローカルコンピューター上のセッション構成を取得する</span><span class="sxs-lookup"><span data-stu-id="dffb1-118">Example 1 - Get session configurations on the local computer</span></span>

```powershell
Get-PSSessionConfiguration
```

### <span data-ttu-id="dffb1-119">例 2-既定の2つのセッション構成を取得する</span><span class="sxs-lookup"><span data-stu-id="dffb1-119">Example 2 - Get the two default session configurations</span></span>

<span data-ttu-id="dffb1-120">このコマンドは、の **Name** パラメーターを使用して、 `Get-PSSessionConfiguration` 名前が "Microsoft" で始まるセッション構成のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-120">The command uses the **Name** parameter of `Get-PSSessionConfiguration` to get only the session configurations with names that begin with "Microsoft".</span></span>

```powershell
Get-PSSessionConfiguration -Name Microsoft*
```

```Output
Name                      PSVersion  StartupScript        Permission
----                      ---------  -------------        ----------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll...
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll...
```

### <span data-ttu-id="dffb1-121">例 3-セッション構成のプロパティと値を取得する</span><span class="sxs-lookup"><span data-stu-id="dffb1-121">Example 3 - Get the properties and values of a session configuration</span></span>

<span data-ttu-id="dffb1-122">この例は、セッション構成ファイルを使用して作成されたセッション構成のプロパティとプロパティ値を示しています。</span><span class="sxs-lookup"><span data-stu-id="dffb1-122">This example shows the properties and property values of a session configuration that was created by using a session configuration file.</span></span>

```powershell
Get-PSSessionConfiguration -Name Full  | Format-List -Property *
```

```Output
Copyright                     : (c) 2011 User01. All rights reserved.
AliasDefinitions              : {System.Collections.Hashtable}
SessionType                   : Default
CompanyName                   : Unknown
GUID                          : 1e9cb265-dae0-4bd3-89a9-8338a47698a1
Author                        : User01
ExecutionPolicy               : Restricted
SchemaVersion                 : 1.0.0.0
LanguageMode                  : FullLanguage
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/Full
MaxConcurrentCommandsPerShell : 1500
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 10
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
configfilepath                : C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 300
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 1
Name                          : Full
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 25
Enabled                       : True
MaxShellsPerUser              : 30
Permission                    :
```

<span data-ttu-id="dffb1-123">この例では、コマンドレットを使用して、 `Get-PSSessionConfiguration` 完全なセッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-123">The example uses the `Get-PSSessionConfiguration` cmdlet to get the full session configuration.</span></span> <span data-ttu-id="dffb1-124">パイプライン演算子は、完全なセッション構成をコマンドレットに送信し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-124">A pipeline operator sends the Full session configuration to the `Format-List` cmdlet.</span></span> <span data-ttu-id="dffb1-125">**プロパティ** パラメーターの値が (all) の場合は、 `*` `Format-List` リスト内のオブジェクトのすべてのプロパティと値を表示するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-125">The **Property** parameter with a value of `*` (all) directs `Format-List` to display all the properties and values of the object in a list.</span></span>

<span data-ttu-id="dffb1-126">出力には、セッション構成の作成者、セッションの種類、言語モード、このセッション構成で作成されたセッションの実行ポリシー、セッションクォータ、セッション構成ファイルへの完全パスなど、有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dffb1-126">The output includes useful information, including the author of the session configuration, the session type, language mode, and execution policy of sessions that are created with this session configuration, session quotas, and the full path to the session configuration file.</span></span>

<span data-ttu-id="dffb1-127">このセッション構成の表示は、セッション構成ファイルを含むセッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-127">This view of a session configuration is used for sessions that include a session configuration file.</span></span>
<span data-ttu-id="dffb1-128">セッション構成ファイルの詳細については、「[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb1-128">For more information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

### <span data-ttu-id="dffb1-129">例 4-セッション構成を確認する別の方法</span><span class="sxs-lookup"><span data-stu-id="dffb1-129">Example 4 - Another way to look at the session configurations</span></span>

<span data-ttu-id="dffb1-130">この例では、 `Get-ChildItem` WSMan: provider ドライブのコマンドレット (エイリアス) を使用して、 `dir` プラグインノードの内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-130">This example uses the `Get-ChildItem` cmdlet (alias `dir`) in the WSMan: provider drive to look at the content of the Plugin node.</span></span> <span data-ttu-id="dffb1-131">これは、コンピューター上のセッション構成を確認するもう 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="dffb1-131">This is another way to look at the session configurations on the computer.</span></span>

```powershell
dir wsman:\localhost\plugin
```

```Output
Type            Keys                                Name
----            ----                                ----
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=WMI Provider}                 WMI Provider
```

<span data-ttu-id="dffb1-132">**プラグイン** ノードには、登録済みの PowerShell セッション構成を表す **ContainerElement** オブジェクト (WSMANCONFIGCONTAINERELEMENT) と、ws-management 用の他のプラグインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dffb1-132">The **PlugIn** node contains **ContainerElement** objects (Microsoft.WSMan.Management.WSManConfigContainerElement) that represent the registered PowerShell session configurations, along with other plug-ins for WS-Management.</span></span>

### <span data-ttu-id="dffb1-133">例 6-リモートコンピューター上のセッション構成を表示する</span><span class="sxs-lookup"><span data-stu-id="dffb1-133">Example 6 - View session configurations on a remote computer</span></span>

<span data-ttu-id="dffb1-134">この例は、WSMan プロバイダーを使用して、リモート コンピューター上のセッション構成を表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dffb1-134">This example shows how to use the WSMan provider to view the session configurations on a remote computer.</span></span> <span data-ttu-id="dffb1-135">この方法では、コマンドほど多くの情報は提供されません `Get-PSSessionConfiguration` が、このコマンドレットを実行するには、ユーザーが Administrators グループのメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dffb1-135">This method does not provide as much information as a `Get-PSSessionConfiguration` command, but the user does not need to be a member of the Administrators group to run this cmdlet.</span></span>

```powershell
Connect-WSMan -ComputerName Server01
dir WSMan:\Server01\Plugin
```

```Output
   WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=Empty}                        Empty
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=NoLanguage}                   NoLanguage
Container       {Name=RestrictedLang}               RestrictedLang
Container       {Name=RRS}                          RRS
Container       {Name=SEL Plugin}                   SEL Plugin
Container       {Name=WithProfile}                  WithProfile
Container       {Name=WMI Provider}                 WMI Provider
```

<span data-ttu-id="dffb1-136">`Connect-WSMan`コマンドレットは、Server01 リモートコンピューター上の WinRM サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-136">The `Connect-WSMan` cmdlet connects to the WinRM service on the Server01 remote computer.</span></span> <span data-ttu-id="dffb1-137">`Get-ChildItem`WSMan: ドライブのコマンドレット (エイリアス) は、 `dir` **Server01\Plugin** パス内の項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-137">The `Get-ChildItem` cmdlet (alias `dir`) of the WSMan: drive gets the items in the **Server01\Plugin** path.</span></span> <span data-ttu-id="dffb1-138">出力は、Server01 コンピューターの プラグイン ディレクトリにあるアイテムを示しています。</span><span class="sxs-lookup"><span data-stu-id="dffb1-138">The output shows the items in the Plugin directory on the Server01 computer.</span></span> <span data-ttu-id="dffb1-139">このアイテムには、WSMan プラグインの一種であるセッション構成のほか、コンピューター上にあるその他の種類のプラグインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-139">The items include the session configurations, which are a type of WSMan plug-in, along with other types of plug-ins on the computer.</span></span>

### <span data-ttu-id="dffb1-140">例 7-リモートコンピューターから詳細なセッション構成を取得する</span><span class="sxs-lookup"><span data-stu-id="dffb1-140">Example 7 - Get detailed session configurations from a remote computer</span></span>

<span data-ttu-id="dffb1-141">この例では、リモートコンピューターでコマンドを実行する方法を示し `Get-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-141">This example shows how to run a `Get-PSSessionConfiguration` command on a remote computer.</span></span> <span data-ttu-id="dffb1-142">例に挙げたコマンドは、ローカル コンピューター上のクライアント設定およびリモート コンピューター上のサービス設定で、CredSSP 委任が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-142">The command requires that CredSSP delegation be enabled in the client settings on the local computer and in the service settings on the remote computer.</span></span>

<span data-ttu-id="dffb1-143">この例のコマンドを実行するには、ローカルコンピューターとリモートコンピューターの Administrators グループのメンバーである必要があります。また、[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-143">To run the commands in this example, you must be a member of the Administrators group on the local and remote computers and you must start PowerShell with the **Run as administrator** option.</span></span>

```powershell
Enable-WSManCredSSP -Delegate Server02
Connect-WSMan Server02
Set-Item WSMan:\Server02*\Service\Auth\CredSSP -Value $true
Invoke-Command -ScriptBlock {Get-PSSessionConfiguration} -ComputerName Server02 -Authentication CredSSP -Credential Domain01\Admin01
```

```Output
Name                      PSVersion  StartupScript        Permission                          PSComputerName
----                      ---------  -------------        ----------                          --------------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
MyX86Shell                5.1        c:\test\x86Shell.ps1 BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
```

<span data-ttu-id="dffb1-144">コマンドレットでは、 `Enable-WSManCredSSP` ローカルコンピューター Server01 の **CredSSP** 委任を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dffb1-144">The `Enable-WSManCredSSP` cmdlet enables **CredSSP** delegation on Server01, the local computer.</span></span> <span data-ttu-id="dffb1-145">`Connect-WSMan`コマンドレットは、Server02 コンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-145">The `Connect-WSMan` cmdlet connects to Server02 computer.</span></span> <span data-ttu-id="dffb1-146">この操作により、Server02 のノードがローカルコンピューターの WSMan: ドライブに追加され、Server02 コンピューターの WS-Management 設定を表示および変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-146">This action adds a node for Server02 to the WSMan: drive on the local computer, allowing you to view and change the WS-Management settings on the Server02 computer.</span></span> <span data-ttu-id="dffb1-147">この `Set-Item` コマンドレットは、Server02 コンピューターのサービスノードの **CredSSP** 項目の値を **True** に変更します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-147">The `Set-Item` cmdlet changes the value of the **CredSSP** item in the Service node of the Server02 computer to **True**.</span></span> <span data-ttu-id="dffb1-148">これによってリモート コンピューターのサービス設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-148">This configures the service settings on the remote computer.</span></span> <span data-ttu-id="dffb1-149">`Invoke-Command`コマンドレットは、 `Get-PSSessionConfiguration` Server02 コンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-149">The `Invoke-Command` cmdlet runs the`Get-PSSessionConfiguration` command on the Server02 computer.</span></span> <span data-ttu-id="dffb1-150">このコマンドは、 **Credential** パラメーターを使用します。また、 **Authentication** パラメーターを **CredSSP** という値で使用します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-150">The command uses the **Credential** parameter, and it uses the **Authentication** parameter with a value of **CredSSP**.</span></span> <span data-ttu-id="dffb1-151">出力は、Server02 リモート コンピューター上のセッション構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="dffb1-151">The output shows the session configurations on the Server02 remote computer.</span></span>

### <span data-ttu-id="dffb1-152">例 8-セッション構成のリソース URI を取得する</span><span class="sxs-lookup"><span data-stu-id="dffb1-152">Example 8 - Get the resource URI of a session configuration</span></span>

<span data-ttu-id="dffb1-153">この例は `$PSSessionConfigurationName` 、リソース URI を受け取るユーザー設定変数の値を設定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dffb1-153">This example is useful for setting the value of the `$PSSessionConfigurationName` preference variable, which takes a resource URI.</span></span>

```powershell
(Get-PSSessionConfiguration -Name CustomShell).resourceURI
```

```Output
http://schemas.microsoft.com/powershell/microsoft.CustomShell
```

<span data-ttu-id="dffb1-154">変数は、 `$PSSessionConfigurationName` セッションを作成するときに使用される既定の構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-154">The `$PSSessionConfigurationName` variable specifies the default configuration that is used when you create a session.</span></span> <span data-ttu-id="dffb1-155">この変数は、ローカル コンピューターで設定されますが、リモート コンピューターの構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-155">This variable is set on the local computer, but it specifies a configuration on the remote computer.</span></span> <span data-ttu-id="dffb1-156">変数の詳細については `$PSSessionConfiguration` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb1-156">For more information about the `$PSSessionConfiguration` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="dffb1-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dffb1-157">PARAMETERS</span></span>

### <span data-ttu-id="dffb1-158">-Force</span><span class="sxs-lookup"><span data-stu-id="dffb1-158">-Force</span></span>

<span data-ttu-id="dffb1-159">WinRM サービスが実行されていない場合に、WinRM サービスの再起動を求めるメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="dffb1-159">Suppresses the prompt to restart the WinRM service, if the service is not already running.</span></span>

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

### <span data-ttu-id="dffb1-160">-Name</span><span class="sxs-lookup"><span data-stu-id="dffb1-160">-Name</span></span>

<span data-ttu-id="dffb1-161">指定された名前または名前パターンのセッション構成のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-161">Gets only the session configurations with the specified name or name pattern.</span></span> <span data-ttu-id="dffb1-162">1 つ以上のセッション構成名を入力します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-162">Enter one or more session configuration names.</span></span> <span data-ttu-id="dffb1-163">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-163">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All session configurations on the local computer
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="dffb1-164">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="dffb1-164">CommonParameters</span></span>

<span data-ttu-id="dffb1-165">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="dffb1-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dffb1-166">詳細については、「[about_CommonParameters](./About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb1-166">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="dffb1-167">入力</span><span class="sxs-lookup"><span data-stu-id="dffb1-167">INPUTS</span></span>

### <span data-ttu-id="dffb1-168">なし</span><span class="sxs-lookup"><span data-stu-id="dffb1-168">None</span></span>

<span data-ttu-id="dffb1-169">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="dffb1-169">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="dffb1-170">出力</span><span class="sxs-lookup"><span data-stu-id="dffb1-170">OUTPUTS</span></span>

### <span data-ttu-id="dffb1-171">Register-pssessionconfiguration # のコマンド # には、</span><span class="sxs-lookup"><span data-stu-id="dffb1-171">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

## <span data-ttu-id="dffb1-172">注</span><span class="sxs-lookup"><span data-stu-id="dffb1-172">NOTES</span></span>

- <span data-ttu-id="dffb1-173">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-173">To run this cmdlet, start PowerShell with the **Run as administrator** option.</span></span>

- <span data-ttu-id="dffb1-174">コンピューター上のセッション構成を表示するには、そのコンピューターの Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-174">To view the session configurations on the computer, you must be a member of the Administrators group on the computer.</span></span>

- <span data-ttu-id="dffb1-175">リモートコンピューターでコマンドを実行するには `Get-PSSessionConfiguration` 、ローカルコンピューターのクライアント設定で (コマンドレットを使用して) Credential Security Service Provider (CredSSP) 認証を有効にし、リモートコンピューターのサービス設定で有効にする必要があり `Enable-WSManCredSSP` ます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-175">To run a `Get-PSSessionConfiguration` command on a remote computer, Credential Security Service Provider (CredSSP) authentication must be enabled in the client settings on the local computer (by using the `Enable-WSManCredSSP` cmdlet) and in the service settings on the remote computer.</span></span> <span data-ttu-id="dffb1-176">また、リモートセッションを確立するときには、 **Authentication** パラメーターの **CredSSP** 値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-176">Also, you must use the **CredSSP** value of the **Authentication** parameter when establishing the remote session.</span></span> <span data-ttu-id="dffb1-177">使用しない場合は、アクセスが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-177">Otherwise, access is denied.</span></span>

- <span data-ttu-id="dffb1-178">が返すオブジェクトのメモプロパティは、 `Get-PSSessionConfiguration` 値がある場合にのみオブジェクトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-178">The note properties of the object that `Get-PSSessionConfiguration` returns appear on the object only when they have a value.</span></span> <span data-ttu-id="dffb1-179">セッション構成ファイルを使用して作成されたセッション構成にのみ、すべての定義済みプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-179">Only session configurations that were created by using a session configuration file have all the defined properties.</span></span>

- <span data-ttu-id="dffb1-180">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-180">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="dffb1-181">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-181">Also, session configurations that use a session configuration file have additional properties.</span></span>

- <span data-ttu-id="dffb1-182">WSMan: ドライブでコマンドを使用して、セッション構成のプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="dffb1-182">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
  <span data-ttu-id="dffb1-183">ただし、powershell 2.0 で WSMan: ドライブを使用して、 **OutputBufferingMode** などの powershell 3.0 で導入されたセッション構成プロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="dffb1-183">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="dffb1-184">PowerShell 2.0 のコマンドではエラーは生成されませんが、無効になります。</span><span class="sxs-lookup"><span data-stu-id="dffb1-184">PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="dffb1-185">PowerShell 3.0 で導入されたプロパティを変更するには、PowerShell 3.0 で WSMan: ドライブを使用します。</span><span class="sxs-lookup"><span data-stu-id="dffb1-185">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="dffb1-186">関連リンク</span><span class="sxs-lookup"><span data-stu-id="dffb1-186">RELATED LINKS</span></span>

[<span data-ttu-id="dffb1-187">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dffb1-187">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="dffb1-188">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dffb1-188">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="dffb1-189">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dffb1-189">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="dffb1-190">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="dffb1-190">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="dffb1-191">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="dffb1-191">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="dffb1-192">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dffb1-192">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="dffb1-193">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dffb1-193">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="dffb1-194">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="dffb1-194">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="dffb1-195">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="dffb1-195">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="dffb1-196">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="dffb1-196">WSMan Provider</span></span>](../microsoft.wsman.management/about/about_WSMan_Provider.md)

[<span data-ttu-id="dffb1-197">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="dffb1-197">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="dffb1-198">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="dffb1-198">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
