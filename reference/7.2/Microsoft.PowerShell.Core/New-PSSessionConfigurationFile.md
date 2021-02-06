---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: a41c52bf163aa0a73b54e75b5192389a14da82bb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603220"
---
# <span data-ttu-id="79d6c-102">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="79d6c-102">New-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="79d6c-103">概要</span><span class="sxs-lookup"><span data-stu-id="79d6c-103">SYNOPSIS</span></span>
<span data-ttu-id="79d6c-104">セッション構成を定義するファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-104">Creates a file that defines a session configuration.</span></span>

## <span data-ttu-id="79d6c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="79d6c-105">SYNTAX</span></span>

```
New-PSSessionConfigurationFile [-Path] <String> [-SchemaVersion <Version>] [-Guid <Guid>]
 [-Author <String>] [-Description <String>] [-CompanyName <String>] [-Copyright <String>]
 [-SessionType <SessionType>] [-TranscriptDirectory <String>] [-RunAsVirtualAccount]
 [-RunAsVirtualAccountGroups <String[]>] [-MountUserDrive] [-UserDriveMaximumSize <Int64>]
 [-GroupManagedServiceAccount <String>] [-ScriptsToProcess <String[]>]
 [-RoleDefinitions <IDictionary>] [-RequiredGroups <IDictionary>] [-LanguageMode <PSLanguageMode>]
 [-ExecutionPolicy <ExecutionPolicy>] [-PowerShellVersion <Version>] [-ModulesToImport <Object[]>]
 [-VisibleAliases <String[]>] [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>]
 [-VisibleExternalCommands <String[]>] [-VisibleProviders <String[]>]
 [-AliasDefinitions <IDictionary[]>] [-FunctionDefinitions <IDictionary[]>]
 [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>] [-Full] [<CommonParameters>]
```

## <span data-ttu-id="79d6c-106">Description</span><span class="sxs-lookup"><span data-stu-id="79d6c-106">DESCRIPTION</span></span>

<span data-ttu-id="79d6c-107">この `New-PSSessionConfigurationFile` コマンドレットは、セッション構成を定義する設定のファイルと、セッション構成を使用して作成されたセッションの環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-107">The `New-PSSessionConfigurationFile` cmdlet creates a file of settings that define a session configuration and the environment of sessions that are created by using the session configuration.</span></span>
<span data-ttu-id="79d6c-108">セッション構成でファイルを使用するには、  `Register-PSSessionConfiguration` コマンドレットまたはコマンドレットの Path パラメーターを使用し `Set-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-108">To use the file in a session configuration, use the **Path** parameter of the `Register-PSSessionConfiguration` or `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="79d6c-109">によって作成されるセッション構成ファイル `New-PSSessionConfigurationFile` は、セッション構成のプロパティと値のハッシュテーブルを含む、人間が判読できるテキストファイルです。</span><span class="sxs-lookup"><span data-stu-id="79d6c-109">The session configuration file that `New-PSSessionConfigurationFile` creates is a human-readable text file that contains a hash table of the session configuration properties and values.</span></span> <span data-ttu-id="79d6c-110">ファイル名の拡張子が付いてい `.pssc` ます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-110">The file has a `.pssc` filename extension.</span></span>

<span data-ttu-id="79d6c-111">`New-PSSessionConfigurationFile` **Path** パラメーターを除き、のすべてのパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-111">All parameters of `New-PSSessionConfigurationFile` are optional, except for the **Path** parameter.</span></span>
<span data-ttu-id="79d6c-112">パラメーターを省略すると、パラメーターの説明に記載された部分を除き、セッション構成ファイル内の対応するキーがコメント アウトされます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-112">If you omit a parameter, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span>

<span data-ttu-id="79d6c-113">セッション構成は、エンドポイントとも呼ばれ、コンピューターに接続する PowerShell **セッション (pssession**) の環境を定義するローカルコンピューター上の設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="79d6c-113">A session configuration, also known as an endpoint, is a collection of settings on the local computer that define the environment for PowerShell sessions (**PSSessions**) that connect to the computer.</span></span> <span data-ttu-id="79d6c-114">すべての pssession は、セッション構成を **使用します** 。</span><span class="sxs-lookup"><span data-stu-id="79d6c-114">All **PSSessions** use a session configuration.</span></span> <span data-ttu-id="79d6c-115">特定のセッション構成を指定するには、コマンドレットなど、セッションを作成するコマンドレットの **ConfigurationName** パラメーターを使用し `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-115">To specify a particular session configuration, use the **ConfigurationName** parameter of cmdlets that create a session, such as the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="79d6c-116">session configuration file は、セッション構成の定義をより容易にします。複雑なスクリプトやコード アセンブリは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-116">A session configuration file makes it easy to define a session configuration without complex scripts or code assemblies.</span></span> <span data-ttu-id="79d6c-117">ファイルの設定は、セッション構成内のオプションのスタートアップスクリプトとアセンブリで使用されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-117">The settings in the file are used with the optional startup script and any assemblies in the session configuration.</span></span>

<span data-ttu-id="79d6c-118">セッション構成とセッション構成ファイルの詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md) 」および「 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d6c-118">For more information about session configurations and session configuration files, see [about_Session_Configurations](About/about_Session_Configurations.md) and [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="79d6c-119">このコマンドレットは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="79d6c-119">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="79d6c-120">例</span><span class="sxs-lookup"><span data-stu-id="79d6c-120">EXAMPLES</span></span>

### <span data-ttu-id="79d6c-121">例 1: NoLanguage セッションの作成と使用</span><span class="sxs-lookup"><span data-stu-id="79d6c-121">Example 1: Creating and using a NoLanguage session</span></span>

<span data-ttu-id="79d6c-122">この例では、言語なしのセッションを使用してを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-122">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="79d6c-123">これには次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-123">The steps include:</span></span>

1. <span data-ttu-id="79d6c-124">新しい構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-124">Create a new configuration file.</span></span>
1. <span data-ttu-id="79d6c-125">構成を登録します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-125">Register the configuration.</span></span>
1. <span data-ttu-id="79d6c-126">構成を使用する新しいセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-126">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="79d6c-127">その新しいセッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-127">Run commands in that new session.</span></span>

<span data-ttu-id="79d6c-128">この例のコマンドを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-128">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="79d6c-129">このオプションは、コマンドレットを実行するために必要です `Register-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="79d6c-129">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode NoLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name NoLanguage -Force
$NoLanguageSession = New-PSSession -ComputerName Srv01 -ConfigurationName NoLanguage
Invoke-Command -Session $NoLanguageSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
The syntax is not supported by this runspace. This might be because it is in no-language mode.
    + CategoryInfo          : ParserError: (if ((Get-Date) ...') {'Before'}  :String) [], ParseException
    + FullyQualifiedErrorId : ScriptsNotAllowed
    + PSComputerName        : localhost
```

<span data-ttu-id="79d6c-130">この例では、 `Invoke-Command` **LanguageMode** が **nolanguage** に設定されているため、は失敗します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-130">In this example, the `Invoke-Command` fails because the **LanguageMode** is set to **NoLanguage**.</span></span>

### <span data-ttu-id="79d6c-131">例 2: RestrictedLanguage セッションの作成と使用</span><span class="sxs-lookup"><span data-stu-id="79d6c-131">Example 2: Creating and using a RestrictedLanguage session</span></span>

<span data-ttu-id="79d6c-132">この例では、言語なしのセッションを使用してを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-132">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="79d6c-133">これには次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-133">The steps include:</span></span>

1. <span data-ttu-id="79d6c-134">新しい構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-134">Create a new configuration file.</span></span>
1. <span data-ttu-id="79d6c-135">構成を登録します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-135">Register the configuration.</span></span>
1. <span data-ttu-id="79d6c-136">構成を使用する新しいセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-136">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="79d6c-137">その新しいセッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-137">Run commands in that new session.</span></span>

<span data-ttu-id="79d6c-138">この例のコマンドを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-138">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="79d6c-139">このオプションは、コマンドレットを実行するために必要です `Register-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="79d6c-139">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode RestrictedLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name RestrictedLanguage -Force
$RestrictedSession = New-PSSession -ComputerName Srv01 -ConfigurationName RestrictedLanguage
Invoke-Command -Session $RestrictedSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
Before
```

<span data-ttu-id="79d6c-140">この例では、 `Invoke-Command` **LanguageMode** が **RestrictedLanguage** に設定されているため、は成功します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-140">In this example, the `Invoke-Command` succeeds because the **LanguageMode** is set to **RestrictedLanguage**.</span></span>

### <span data-ttu-id="79d6c-141">例 3: セッション構成ファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="79d6c-141">Example 3: Changing a Session Configuration File</span></span>

<span data-ttu-id="79d6c-142">この例では、"ITTasks" という名前の既存のセッションで使用されているセッション構成ファイルを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-142">This example shows how to change the session configuration file that is used in an existing session named "ITTasks".</span></span> <span data-ttu-id="79d6c-143">以前は、これらのセッションにはコアモジュールと内部 **Ittasks** モジュールのみがありました。</span><span class="sxs-lookup"><span data-stu-id="79d6c-143">Previously, these sessions had only the core modules and an internal **ITTasks** module.</span></span> <span data-ttu-id="79d6c-144">管理者は、ITTasks セッション構成を使用して作成されたセッションに **Psscheduledjob** モジュールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d6c-144">The administrator wants to add the **PSScheduledJob** module to sessions created by using the ITTasks session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

<span data-ttu-id="79d6c-145">コマンドレットを作成して、 `New-PSSessionConfigurationFile` 必要なモジュールをインポートするセッション構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-145">The `New-PSSessionConfigurationFile` cmdlet to create a session configuration file that imports the required modules.</span></span> <span data-ttu-id="79d6c-146">コマンドレットでは、 `Set-PSSessionConfiguration` 現在の構成ファイルを新しい構成ファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-146">The `Set-PSSessionConfiguration` cmdlet replaces the current configuration file with the new one.</span></span> <span data-ttu-id="79d6c-147">この新しい構成は、変更後に作成された新しいセッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-147">This new configuration only affects new sessions created after the change.</span></span>
<span data-ttu-id="79d6c-148">既存の "ITTasks" セッションは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-148">Existing "ITTasks" sessions are not affected.</span></span>

### <span data-ttu-id="79d6c-149">例 4: セッション構成ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="79d6c-149">Example 4: Editing a Session Configuration File</span></span>

<span data-ttu-id="79d6c-150">この例は、構成ファイルのアクティブなセッション構成のコピーを編集することで、セッション構成を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-150">This example shows how to change a session configuration by editing the active session configuration copy of the configuration file.</span></span> <span data-ttu-id="79d6c-151">構成ファイルのセッション構成のコピーを変更するには、ファイルへのフルコントロールアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d6c-151">To modify the session configuration copy of the configuration file, you must have full control access to the file.</span></span> <span data-ttu-id="79d6c-152">このため、ファイルのアクセス許可を変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="79d6c-152">This may require you to change the permissions on the file.</span></span>

<span data-ttu-id="79d6c-153">このシナリオでは、 `Select-String` アクティブな構成ファイルを編集して、コマンドレットの新しいエイリアスを追加します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-153">In this scenario, we want to add a new alias for the `Select-String` cmdlet by editing the active configuration file.</span></span>

<span data-ttu-id="79d6c-154">次のコード例では、次の手順を実行してこの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="79d6c-154">The example code below performs the following steps to make this change:</span></span>

1. <span data-ttu-id="79d6c-155">ITConfig セッションの構成ファイルのパスを取得します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-155">Get the configuration file path for the ITConfig session.</span></span>
1. <span data-ttu-id="79d6c-156">ユーザーは、 **Notepad.exe** を使用して構成ファイルを編集し、 **エイリアス定義** の値を次のように変更します `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` 。</span><span class="sxs-lookup"><span data-stu-id="79d6c-156">The user edits the configuration file using **Notepad.exe** to change the **AliasDefinitions** value as follows: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})`.</span></span>
1. <span data-ttu-id="79d6c-157">更新された構成ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="79d6c-157">Test the updated configuration file.</span></span>

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

<span data-ttu-id="79d6c-158">で **Verbose** パラメーターを使用して、 `Test-PSSessionConfigurationFile` 検出されたエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-158">Use the **Verbose** parameter with `Test-PSSessionConfigurationFile` to display any errors that are detected.</span></span> <span data-ttu-id="79d6c-159">`$True`ファイルでエラーが検出されなかった場合、コマンドレットはを返します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-159">The cmdlet returns `$True` if no errors are detected in the file.</span></span>

### <span data-ttu-id="79d6c-160">例 5: サンプル構成ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="79d6c-160">Example 5: Create a sample configuration file</span></span>

<span data-ttu-id="79d6c-161">この例は `New-PSSessionConfigurationFile` 、すべてのコマンドレットパラメーターを使用するコマンドを示しています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-161">This example shows a `New-PSSessionConfigurationFile` command that uses all the cmdlet parameters.</span></span>
<span data-ttu-id="79d6c-162">各パラメーターの正しい入力形式を示すために含まれています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-162">It is included to show the correct input format for each parameter.</span></span>

<span data-ttu-id="79d6c-163">最終的な SampleFile.pssc が出力に表示されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-163">The resulting SampleFile.pssc is displayed in the output.</span></span>

```powershell
$configSettings = @{
    Path = '.\SampleFile.pssc'
    SchemaVersion = '1.0.0.0'
    Author = 'User01'
    Copyright = '(c) Fabrikam Corporation. All rights reserved.'
    CompanyName = 'Fabrikam Corporation'
    Description = 'This is a sample file.'
    ExecutionPolicy = 'AllSigned'
    PowerShellVersion = '3.0'
    LanguageMode = 'FullLanguage'
    SessionType = 'Default'
    EnvironmentVariables = @{TESTSHARE='\\Test2\Test'}
    ModulesToImport = @{ModuleName='PSScheduledJob'; ModuleVersion='1.0.0.0'; GUID='50cdb55f-5ab7-489f-9e94-4ec21ff51e59'},'PSDiagnostics'
    AssembliesToLoad = 'System.Web.Services','FSharp.Compiler.CodeDom.dll'
    TypesToProcess = 'Types1.ps1xml','Types2.ps1xml'
    FormatsToProcess = 'CustomFormats.ps1xml'
    ScriptsToProcess = 'Get-Inputs.ps1'
    AliasDefinitions = @{Name='hlp';Value='Get-Help';Description='Gets help.';Options='AllScope'},
        @{Name='Update';Value='Update-Help';Description='Updates help';Options='ReadOnly'}
    FunctionDefinitions = @{Name='Get-Function';ScriptBlock={Get-Command -CommandType Function};Options='ReadOnly'}
    VariableDefinitions = @{Name='WarningPreference';Value='SilentlyContinue'}
    VisibleAliases = 'c*','g*','i*','s*'
    VisibleCmdlets = 'Get*'
    VisibleFunctions = 'Get*'
    VisibleProviders = 'FileSystem','Function','Variable'
    RunAsVirtualAccount = $true
    RunAsVirtualAccountGroups = 'Backup Operators'
}
New-PSSessionConfigurationFile @configSettings
Get-Content SampleFile.pssc
```

```Output
@{

# Version number of the schema used for this document
SchemaVersion = '1.0.0.0'

# ID used to uniquely identify this document
GUID = '1caeff7f-27ca-4360-97cf-37846f594235'

# Author of this document
Author = 'User01'

# Description of the functionality provided by these settings
Description = 'This is a sample file.'

# Company associated with this document
CompanyName = 'Fabrikam Corporation'

# Copyright statement for this document
Copyright = '(c) Fabrikam Corporation. All rights reserved.'

# Session type defaults to apply for this session configuration. Can be 'RestrictedRemoteServer' (recommended), 'Empty', or 'Default'
SessionType = 'Default'

# Directory to place session transcripts for this session configuration
# TranscriptDirectory = 'C:\Transcripts\'

# Whether to run this session configuration as the machine's (virtual) administrator account
RunAsVirtualAccount = $true

# Groups associated with machine's (virtual) administrator account
RunAsVirtualAccountGroups = 'Backup Operators'

# Scripts to run when applied to a session
ScriptsToProcess = 'Get-Inputs.ps1'

# User roles (security groups), and the role capabilities that should be applied to them when applied to a session
# RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\SqlManaged' = @{ RoleCapabilityFiles = 'C:\RoleCapability\SqlManaged.psrc' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }

# Language mode to apply when applied to a session. Can be 'NoLanguage' (recommended), 'RestrictedLanguage', 'ConstrainedLanguage', or 'FullLanguage'
LanguageMode = 'FullLanguage'

# Execution policy to apply when applied to a session
ExecutionPolicy = 'AllSigned'

# Version of the PowerShell engine to use when applied to a session
PowerShellVersion = '3.0'

# Modules to import when applied to a session
ModulesToImport = @{
    'GUID' = '50cdb55f-5ab7-489f-9e94-4ec21ff51e59'
    'ModuleName' = 'PSScheduledJob'
    'ModuleVersion' = '1.0.0.0' }, 'PSDiagnostics'

# Aliases to make visible when applied to a session
VisibleAliases = 'c*', 'g*', 'i*', 's*'

# Cmdlets to make visible when applied to a session
VisibleCmdlets = 'Get*'

# Functions to make visible when applied to a session
VisibleFunctions = 'Get*'

# Providers to make visible when applied to a session
VisibleProviders = 'FileSystem', 'Function', 'Variable'

# Aliases to be defined when applied to a session
AliasDefinitions = @{
    'Description' = 'Gets help.'
    'Name' = 'hlp'
    'Options' = 'AllScope'
    'Value' = 'Get-Help' }, @{
    'Description' = 'Updates help'
    'Name' = 'Update'
    'Options' = 'ReadOnly'
    'Value' = 'Update-Help' }

# Functions to define when applied to a session
FunctionDefinitions = @{
    'Name' = 'Get-Function'
    'Options' = 'ReadOnly'
    'ScriptBlock' = {Get-Command -CommandType Function} }

# Variables to define when applied to a session
VariableDefinitions = @{
    'Name' = 'WarningPreference'
    'Value' = 'SilentlyContinue' }

# Environment variables to define when applied to a session
EnvironmentVariables = @{
    'TESTSHARE' = '\\Test2\Test' }

# Type files (.ps1xml) to load when applied to a session
TypesToProcess = 'Types1.ps1xml', 'Types2.ps1xml'

# Format files (.ps1xml) to load when applied to a session
FormatsToProcess = 'CustomFormats.ps1xml'

# Assemblies to load when applied to a session
AssembliesToLoad = 'System.Web.Services', 'FSharp.Compiler.CodeDom.dll'

}
```

## <span data-ttu-id="79d6c-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="79d6c-164">PARAMETERS</span></span>

### <span data-ttu-id="79d6c-165">-エイリアスの定義</span><span class="sxs-lookup"><span data-stu-id="79d6c-165">-AliasDefinitions</span></span>

<span data-ttu-id="79d6c-166">セッション構成を使用するセッションに、指定されたエイリアスを追加します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-166">Adds the specified aliases to sessions that use the session configuration.</span></span> <span data-ttu-id="79d6c-167">ハッシュ テーブルに次のキーを入力します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-167">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="79d6c-168">名前-エイリアスの名前。</span><span class="sxs-lookup"><span data-stu-id="79d6c-168">Name - Name of the alias.</span></span> <span data-ttu-id="79d6c-169">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-169">This key is required.</span></span>
- <span data-ttu-id="79d6c-170">Value-エイリアスが表すコマンド。</span><span class="sxs-lookup"><span data-stu-id="79d6c-170">Value - The command that the alias represents.</span></span> <span data-ttu-id="79d6c-171">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-171">This key is required.</span></span>
- <span data-ttu-id="79d6c-172">Description-エイリアスを説明するテキスト文字列。</span><span class="sxs-lookup"><span data-stu-id="79d6c-172">Description - A text string that describes the alias.</span></span> <span data-ttu-id="79d6c-173">このキーはオプションです。</span><span class="sxs-lookup"><span data-stu-id="79d6c-173">This key is optional.</span></span>
- <span data-ttu-id="79d6c-174">オプション-エイリアスオプション。</span><span class="sxs-lookup"><span data-stu-id="79d6c-174">Options - Alias options.</span></span> <span data-ttu-id="79d6c-175">このキーはオプションです。</span><span class="sxs-lookup"><span data-stu-id="79d6c-175">This key is optional.</span></span> <span data-ttu-id="79d6c-176">既定値は **None** です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-176">The default value is **None**.</span></span> <span data-ttu-id="79d6c-177">このパラメーターに指定できる値は、None、ReadOnly、Constant、Private、または AllScope です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-177">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="79d6c-178">例: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span><span class="sxs-lookup"><span data-stu-id="79d6c-178">For example: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-179">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="79d6c-179">-AssembliesToLoad</span></span>

<span data-ttu-id="79d6c-180">セッション構成を使用するセッションに読み込むためのアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-180">Specifies the assemblies to load into the sessions that use the session configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-181">-作成者</span><span class="sxs-lookup"><span data-stu-id="79d6c-181">-Author</span></span>

<span data-ttu-id="79d6c-182">セッション構成または構成ファイルの作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-182">Specifies the author of the session configuration or the configuration file.</span></span> <span data-ttu-id="79d6c-183">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="79d6c-183">The default is the current user.</span></span> <span data-ttu-id="79d6c-184">このパラメーターの値は、セッション構成ファイルに表示されますが、セッション構成オブジェクトのプロパティではありません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-184">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="79d6c-185">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="79d6c-185">-CompanyName</span></span>

<span data-ttu-id="79d6c-186">セッション構成または構成ファイルを作成した会社を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-186">Specifies the company that created the session configuration or the configuration file.</span></span> <span data-ttu-id="79d6c-187">既定値は **Unknown** です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-187">The default value is **Unknown**.</span></span> <span data-ttu-id="79d6c-188">このパラメーターの値は、セッション構成ファイルに表示されますが、セッション構成オブジェクトのプロパティではありません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-188">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Unknown
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-189">-Copyright</span><span class="sxs-lookup"><span data-stu-id="79d6c-189">-Copyright</span></span>

<span data-ttu-id="79d6c-190">セッション構成ファイルの著作権を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-190">Specifies a copyright the session configuration file.</span></span> <span data-ttu-id="79d6c-191">このパラメーターの値は、セッション構成ファイルに表示されますが、セッション構成オブジェクトのプロパティではありません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-191">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

<span data-ttu-id="79d6c-192">このパラメーターを省略すると、は `New-PSSessionConfigurationFile` **Author** パラメーターの値を使用して著作権情報ステートメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-192">If you omit this parameter, `New-PSSessionConfigurationFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="79d6c-193">-Description</span><span class="sxs-lookup"><span data-stu-id="79d6c-193">-Description</span></span>

<span data-ttu-id="79d6c-194">セッション構成またはセッション構成ファイルの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-194">Specifies a description of the session configuration or the session configuration file.</span></span> <span data-ttu-id="79d6c-195">このパラメーターの値は、セッション構成ファイルに表示されますが、セッション構成オブジェクトのプロパティではありません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-195">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="79d6c-196">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="79d6c-196">-EnvironmentVariables</span></span>

<span data-ttu-id="79d6c-197">環境変数をセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-197">Adds environment variables to the session.</span></span> <span data-ttu-id="79d6c-198">キーが環境変数名で、値が環境変数値のハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-198">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="79d6c-199">例: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span><span class="sxs-lookup"><span data-stu-id="79d6c-199">For example: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-200">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="79d6c-200">-ExecutionPolicy</span></span>

<span data-ttu-id="79d6c-201">セッション構成を使用するセッションの実行ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-201">Specifies the execution policy of sessions that use the session configuration.</span></span> <span data-ttu-id="79d6c-202">このパラメーターを省略すると、セッション構成ファイルの **set-executionpolicy** キーの値が **制限** されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-202">If you omit this parameter, the value of the **ExecutionPolicy** key in the session configuration file is **Restricted**.</span></span> <span data-ttu-id="79d6c-203">PowerShell の実行ポリシーの詳細については、「 [about_Execution_Policies](about/about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d6c-203">For information about execution policies in PowerShell, see [about_Execution_Policies](about/about_Execution_Policies.md).</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: Unrestricted, RemoteSigned, AllSigned, Restricted, Default, Bypass, Undefined

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-204">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="79d6c-204">-FormatsToProcess</span></span>

<span data-ttu-id="79d6c-205">セッション構成を使用するセッションで実行する書式設定ファイル (.ps1xml) を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-205">Specifies the formatting files (.ps1xml) that run in sessions that use the session configuration.</span></span>
<span data-ttu-id="79d6c-206">このパラメーターの値は、書式設定ファイルの完全パスまたは絶対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d6c-206">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-207">-Full</span><span class="sxs-lookup"><span data-stu-id="79d6c-207">-Full</span></span>

<span data-ttu-id="79d6c-208">この操作に、セッション構成ファイルで使用可能なすべての構成プロパティが含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-208">Indicates that this operation includes all possible configuration properties in the session configuration file.</span></span>

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

### <span data-ttu-id="79d6c-209">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="79d6c-209">-FunctionDefinitions</span></span>

<span data-ttu-id="79d6c-210">セッション構成を使用するセッションに、指定された関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-210">Adds the specified functions to sessions that use the session configuration.</span></span> <span data-ttu-id="79d6c-211">ハッシュ テーブルに次のキーを入力します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-211">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="79d6c-212">名前-関数の名前。</span><span class="sxs-lookup"><span data-stu-id="79d6c-212">Name - Name of the function.</span></span> <span data-ttu-id="79d6c-213">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-213">This key is required.</span></span>
- <span data-ttu-id="79d6c-214">ScriptBlock-関数本体。</span><span class="sxs-lookup"><span data-stu-id="79d6c-214">ScriptBlock - Function body.</span></span> <span data-ttu-id="79d6c-215">スクリプト ブロックを入力します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-215">Enter a script block.</span></span> <span data-ttu-id="79d6c-216">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-216">This key is required.</span></span>
- <span data-ttu-id="79d6c-217">オプション-関数のオプション。</span><span class="sxs-lookup"><span data-stu-id="79d6c-217">Options - Function options.</span></span> <span data-ttu-id="79d6c-218">このキーはオプションです。</span><span class="sxs-lookup"><span data-stu-id="79d6c-218">This key is optional.</span></span> <span data-ttu-id="79d6c-219">既定値は **None** です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-219">The default value is **None**.</span></span> <span data-ttu-id="79d6c-220">このパラメーターに指定できる値は、None、ReadOnly、Constant、Private、または AllScope です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-220">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="79d6c-221">例: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="79d6c-221">For example: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-222">-GroupManagedServiceAccount</span><span class="sxs-lookup"><span data-stu-id="79d6c-222">-GroupManagedServiceAccount</span></span>

<span data-ttu-id="79d6c-223">このセッション構成を使用して、指定したグループの管理されたサービスアカウントのコンテキストで実行するセッションを構成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-223">Configures sessions using this session configuration to run under the context of the specified Group Managed Service Account.</span></span> <span data-ttu-id="79d6c-224">セッション構成が登録されているコンピューターには、セッションが正常に作成されるためには、gMSA パスワードを要求するアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-224">The machine where this session configuration is registered must have permission to request the gMSA password in order for sessions to be created successfully.</span></span> <span data-ttu-id="79d6c-225">このフィールドは、 **RunAsVirtualAccount** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-225">This field cannot be used with the **RunAsVirtualAccount** parameter.</span></span>

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

### <span data-ttu-id="79d6c-226">-Guid</span><span class="sxs-lookup"><span data-stu-id="79d6c-226">-Guid</span></span>

<span data-ttu-id="79d6c-227">セッション構成ファイルの一意の識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-227">Specifies a unique identifier for the session configuration file.</span></span> <span data-ttu-id="79d6c-228">このパラメーターを省略すると、に `New-PSSessionConfigurationFile` よってファイルの GUID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-228">If you omit this parameter, `New-PSSessionConfigurationFile` generates a GUID for the file.</span></span> <span data-ttu-id="79d6c-229">PowerShell で新しい GUID を作成するには、「」と入力 `New-Guid` します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-229">To create a new GUID in PowerShell, type `New-Guid`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-230">-LanguageMode</span><span class="sxs-lookup"><span data-stu-id="79d6c-230">-LanguageMode</span></span>

<span data-ttu-id="79d6c-231">このセッション構成を使用するセッションで許可される PowerShell 言語の要素を決定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-231">Determines which elements of the PowerShell language are permitted in sessions that use this session configuration.</span></span> <span data-ttu-id="79d6c-232">このパラメーターを使用して、特定のユーザーがコンピューター上で実行できるコマンドを制限できます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-232">You can use this parameter to restrict the commands that particular users can run on the computer.</span></span>

<span data-ttu-id="79d6c-233">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="79d6c-233">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="79d6c-234">FullLanguage-すべての言語要素が許可されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-234">FullLanguage - All language elements are permitted.</span></span>
- <span data-ttu-id="79d6c-235">ConstrainedLanguage-評価対象のスクリプトが含まれているコマンドは使用できません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-235">ConstrainedLanguage - Commands that contain scripts to be evaluated are not allowed.</span></span> <span data-ttu-id="79d6c-236">ConstrainedLanguage モードは、ユーザーのアクセスを Microsoft .NET Framework の型、オブジェクト、またはメソッドに制限します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-236">The ConstrainedLanguage mode restricts user access to Microsoft .NET Framework types, objects, or methods.</span></span>
- <span data-ttu-id="79d6c-237">NoLanguage-ユーザーはコマンドレットと関数を実行できますが、スクリプトブロック、変数、または演算子などの言語要素の使用は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-237">NoLanguage - Users may run cmdlets and functions, but are not permitted to use any language elements, such as script blocks, variables, or operators.</span></span>
- <span data-ttu-id="79d6c-238">RestrictedLanguage-ユーザーはコマンドレットと関数を実行できますが、、、 `$PSCulture` `$PSUICulture` `$True` 、 `$False` 、およびの各変数を除き、スクリプトブロックや変数の使用は許可されていません `$Null` 。</span><span class="sxs-lookup"><span data-stu-id="79d6c-238">RestrictedLanguage - Users may run cmdlets and functions, but are not permitted to use script blocks or variables except for the following permitted variables: `$PSCulture`, `$PSUICulture`, `$True`, `$False`, and `$Null`.</span></span> <span data-ttu-id="79d6c-239">ユーザーは、基本的な比較演算子 (、、) のみを使用でき `-eq` `-gt` `-lt` ます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-239">Users may use only the basic comparison operators (`-eq`, `-gt`, `-lt`).</span></span> <span data-ttu-id="79d6c-240">代入ステートメント、プロパティ参照、およびメソッド呼び出しは許可されません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-240">Assignment statements, property references, and method calls are not permitted.</span></span>

<span data-ttu-id="79d6c-241">**LanguageMode** パラメーターの既定値は、**SessionType** パラメーターの値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="79d6c-241">The default value of the **LanguageMode** parameter depends on the value of the **SessionType** parameter.</span></span>

- <span data-ttu-id="79d6c-242">空-NoLanguage</span><span class="sxs-lookup"><span data-stu-id="79d6c-242">Empty - NoLanguage</span></span>
- <span data-ttu-id="79d6c-243">RestrictedRemoteServer-NoLanguage</span><span class="sxs-lookup"><span data-stu-id="79d6c-243">RestrictedRemoteServer - NoLanguage</span></span>
- <span data-ttu-id="79d6c-244">既定値-FullLanguage</span><span class="sxs-lookup"><span data-stu-id="79d6c-244">Default - FullLanguage</span></span>

```yaml
Type: System.Management.Automation.PSLanguageMode
Parameter Sets: (All)
Aliases:
Accepted values: FullLanguage, RestrictedLanguage, NoLanguage, ConstrainedLanguage

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-245">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="79d6c-245">-ModulesToImport</span></span>

<span data-ttu-id="79d6c-246">セッション構成を使用するセッションに自動的にインポートされたモジュールおよびスナップインを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-246">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="79d6c-247">既定では、リモートセッションにインポートされるのは、 **Microsoft の PowerShell** のみですが、コマンドレットが除外されていない限り、ユーザーはコマンドレットとコマンドレットを使用して、 `Import-Module` `Add-PSSnapin` モジュールとスナップインをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-247">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into remote sessions, but unless the cmdlets are excluded, users can use the `Import-Module` and `Add-PSSnapin` cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="79d6c-248">このパラメーターの値の各モジュールまたはスナップインを、文字列によって、またはハッシュ テーブルとして表すことができます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-248">Each module or snap-in in the value of this parameter can be represented by a string or as a hash table.</span></span> <span data-ttu-id="79d6c-249">モジュール文字列は、モジュールまたはスナップインの名前のみで構成されています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-249">A module string consists only of the name of the module or snap-in.</span></span> <span data-ttu-id="79d6c-250">モジュールハッシュテーブルには、 **ModuleName**、 **ModuleVersion**、および **GUID** キーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-250">A module hash table can include **ModuleName**, **ModuleVersion**, and **GUID** keys.</span></span> <span data-ttu-id="79d6c-251">**ModuleName** キーのみが必須です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-251">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="79d6c-252">たとえば、次の値は文字列とハッシュ テーブルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-252">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="79d6c-253">任意の順序での文字列とハッシュ テーブルの組み合わせは有効です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-253">Any combination of strings and hash tables, in any order, is valid.</span></span>

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

<span data-ttu-id="79d6c-254">コマンドレットの **ModulesToImport** パラメーターの値は、 `Register-PSSessionConfiguration` セッション構成ファイルの **ModulesToImport** キーの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-254">The value of the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **ModulesToImport** key in the session configuration file.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-255">-MountUserDrive</span><span class="sxs-lookup"><span data-stu-id="79d6c-255">-MountUserDrive</span></span>

<span data-ttu-id="79d6c-256">このセッション構成を使用して PSDrive を公開するセッションを構成し `User:` ます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-256">Configures sessions that use this session configuration to expose the `User:` PSDrive.</span></span> <span data-ttu-id="79d6c-257">ユーザードライブは、接続しているユーザーごとに一意であり、ファイルシステムプロバイダーが公開されていない場合でも、ユーザーは PowerShell エンドポイントとの間でデータのコピーを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-257">User drives are unique for each connecting user and allow users to copy data to and from PowerShell endpoints even if the File System provider is not exposed.</span></span> <span data-ttu-id="79d6c-258">ユーザードライブのルートは、の下に作成され `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` ます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-258">User drive roots are created under `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\`.</span></span> <span data-ttu-id="79d6c-259">このエンドポイントに接続するユーザーには、それぞれ `$env:USERDOMAIN_$env:USERNAME` という名前のフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-259">For each user connecting to the endpoint, a folder is created with the name `$env:USERDOMAIN_$env:USERNAME`.</span></span>

<span data-ttu-id="79d6c-260">ユーザードライブの内容はユーザーセッション間で保持されるため、自動的には削除されません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-260">Contents in the user drive persist across user sessions and are not automatically removed.</span></span> <span data-ttu-id="79d6c-261">既定では、ユーザーは最大 50 MB のデータをユーザードライブに保存できます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-261">By default, users can only store up to 50MB of data in the user drive.</span></span> <span data-ttu-id="79d6c-262">これは、 **UserDriveMaximumSize** パラメーターを使用してカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-262">This can be customized with the **UserDriveMaximumSize** parameter.</span></span>

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

### <span data-ttu-id="79d6c-263">-Path</span><span class="sxs-lookup"><span data-stu-id="79d6c-263">-Path</span></span>

<span data-ttu-id="79d6c-264">セッション構成ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-264">Specifies the path and filename of the session configuration file.</span></span> <span data-ttu-id="79d6c-265">ファイルには `.pssc` ファイル名拡張子が必要です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-265">The file must have a `.pssc` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-266">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="79d6c-266">-PowerShellVersion</span></span>

<span data-ttu-id="79d6c-267">セッション構成を使用するセッションの PowerShell エンジンのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-267">Specifies the version of the PowerShell engine in sessions that use the session configuration.</span></span> <span data-ttu-id="79d6c-268">このパラメーターに指定できる値は、2.0 と3.0 です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-268">The acceptable values for this parameter are: 2.0 and 3.0.</span></span> <span data-ttu-id="79d6c-269">このパラメーターを省略すると、 **powershellversion** キーがコメントアウトされ、最新バージョンの PowerShell がセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-269">If you omit this parameter, the **PowerShellVersion** key is commented-out and newest version of PowerShell runs in the session.</span></span>

<span data-ttu-id="79d6c-270">コマンドレットの **psversion** パラメーターの値は、 `Register-PSSessionConfiguration` セッション構成ファイルの **powershellversion** キーの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-270">The value of the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-271">-RequiredGroups</span><span class="sxs-lookup"><span data-stu-id="79d6c-271">-RequiredGroups</span></span>

<span data-ttu-id="79d6c-272">このセッション構成を使用するセッションに接続するユーザーの条件付きアクセス規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-272">Specifies conditional access rules for users connecting to sessions that use this session configuration.</span></span>

<span data-ttu-id="79d6c-273">ハッシュテーブル (' および ' または ') ごとに1つのキーのみを使用してルールの一覧を作成するためのハッシュテーブルを入力し、値をセキュリティグループ名または追加のハッシュテーブルの配列に設定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-273">Enter a hashtable to compose your list of rules using only 1 key per hashtable, 'And' or 'Or', and set the value to an array of security group names or additional hashtables.</span></span>

<span data-ttu-id="79d6c-274">1つのグループのメンバーとしてユーザーを接続する必要がある例: `@{ And = 'MyRequiredGroup' }`</span><span class="sxs-lookup"><span data-stu-id="79d6c-274">Example requiring connecting users to be members of a single group: `@{ And = 'MyRequiredGroup' }`</span></span>

<span data-ttu-id="79d6c-275">エンドポイントにアクセスするために、ユーザーがグループ A またはグループ B と C の両方に属している必要がある例を次に示します。 `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span><span class="sxs-lookup"><span data-stu-id="79d6c-275">Example requiring users to belong to group A, or both groups B and C, to access the endpoint: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-276">-RoleDefinitions</span><span class="sxs-lookup"><span data-stu-id="79d6c-276">-RoleDefinitions</span></span>

<span data-ttu-id="79d6c-277">セキュリティグループ (またはユーザー) とロール機能の間のマッピングを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-277">Specifies the mapping between security groups (or users) and role capabilities.</span></span> <span data-ttu-id="79d6c-278">ユーザーには、セッションの作成時にグループメンバーシップに適用されるすべてのロール機能へのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-278">Users will be granted access to all role capabilities which apply to their group membership at the time the session is created.</span></span>

<span data-ttu-id="79d6c-279">キーがセキュリティグループの名前で、値がセキュリティグループで使用できるようにする必要があるロール機能の一覧を含むハッシュテーブルであるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-279">Enter a hash table in which the keys are the name of the security group and the values are hash tables that contain a list of role capabilities that should be made available to the security group.</span></span>

<span data-ttu-id="79d6c-280">例: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span><span class="sxs-lookup"><span data-stu-id="79d6c-280">For example: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-281">-RunAsVirtualAccount</span><span class="sxs-lookup"><span data-stu-id="79d6c-281">-RunAsVirtualAccount</span></span>

<span data-ttu-id="79d6c-282">このセッション構成を使用して、コンピューターの (仮想) 管理者アカウントとして実行されるセッションを構成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-282">Configures sessions using this session configuration to be run as the computer's (virtual) administrator account.</span></span> <span data-ttu-id="79d6c-283">このフィールドは、 **Groupmanagedserviceaccount** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-283">This field cannot be used with the **GroupManagedServiceAccount** parameter.</span></span>

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

### <span data-ttu-id="79d6c-284">-RunAsVirtualAccountGroups</span><span class="sxs-lookup"><span data-stu-id="79d6c-284">-RunAsVirtualAccountGroups</span></span>

<span data-ttu-id="79d6c-285">セッション構成を使用するセッションが仮想アカウントとして実行されるときに、仮想アカウントに関連付けるセキュリティグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-285">Specifies the security groups to be associated with the virtual account when a session that uses the session configuration is run as a virtual account.</span></span> <span data-ttu-id="79d6c-286">省略した場合、仮想アカウントは、他のすべてのコンピューター上のドメインコントローラーおよび管理者の Domain Admins に属しています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-286">If omitted, the virtual account belongs to Domain Admins on domain controllers and Administrators on all other computers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-287">-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="79d6c-287">-SchemaVersion</span></span>

<span data-ttu-id="79d6c-288">セッション構成ファイル スキーマのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-288">Specifies the version of the session configuration file schema.</span></span> <span data-ttu-id="79d6c-289">既定値は "1.0.0.0" です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-289">The default value is "1.0.0.0".</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-290">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="79d6c-290">-ScriptsToProcess</span></span>

<span data-ttu-id="79d6c-291">セッション構成を使用するセッションに、指定されたスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-291">Adds the specified scripts to sessions that use the session configuration.</span></span> <span data-ttu-id="79d6c-292">スクリプトのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-292">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="79d6c-293">このパラメーターの値には、スクリプトファイル名の完全パスまたは絶対パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d6c-293">The value of this parameter must be a full or absolute path of script file names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-294">-SessionType</span><span class="sxs-lookup"><span data-stu-id="79d6c-294">-SessionType</span></span>

<span data-ttu-id="79d6c-295">セッション構成を使用して作成されるセッションの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-295">Specifies the type of session that is created by using the session configuration.</span></span> <span data-ttu-id="79d6c-296">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-296">The default value is Default.</span></span> <span data-ttu-id="79d6c-297">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="79d6c-297">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="79d6c-298">Empty-既定では、モジュールはセッションに追加されません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-298">Empty - No modules are added to session by default.</span></span> <span data-ttu-id="79d6c-299">このコマンドレットのパラメーターを使用して、モジュール、関数、スクリプト、およびその他の機能をセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-299">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span> <span data-ttu-id="79d6c-300">このオプションは、選択したコマンドを追加することによってカスタムセッションを作成するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-300">This option is designed for you to create custom sessions by adding selected commands.</span></span> <span data-ttu-id="79d6c-301">空のセッションにコマンドを追加しないと、セッションは式に制限され、使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="79d6c-301">If you do not add commands to an empty session, the session is limited to expressions and might not be usable.</span></span>
- <span data-ttu-id="79d6c-302">既定-セッションに対して、PowerShell のコアモジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-302">Default - Adds the Microsoft.PowerShell.Core module to the session.</span></span> <span data-ttu-id="79d6c-303">このモジュールには、 `Import-Module` このコマンドレットを明示的に禁止していない限り、ユーザーが他のモジュールをインポートするために使用できるコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-303">This module includes the `Import-Module` cmdlet that users can use to import other modules unless you explicitly prohibit this cmdlet.</span></span>
- <span data-ttu-id="79d6c-304">RestrictedRemoteServer.</span><span class="sxs-lookup"><span data-stu-id="79d6c-304">RestrictedRemoteServer.</span></span> <span data-ttu-id="79d6c-305">には、、、、、 `Exit-PSSession` 、 `Get-Command` `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` 、および `Select-Object` の各プロキシ関数のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-305">Includes only the following proxy functions: `Exit-PSSession`, `Get-Command`, `Get-FormatData`, `Get-Help`, `Measure-Object`, `Out-Default`, and `Select-Object`.</span></span>
  <span data-ttu-id="79d6c-306">このコマンドレットのパラメーターを使用して、モジュール、関数、スクリプト、およびその他の機能をセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-306">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span>

```yaml
Type: System.Management.Automation.Remoting.SessionType
Parameter Sets: (All)
Aliases:
Accepted values: Empty, RestrictedRemoteServer, Default

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-307">-TranscriptDirectory</span><span class="sxs-lookup"><span data-stu-id="79d6c-307">-TranscriptDirectory</span></span>

<span data-ttu-id="79d6c-308">このセッション構成を使用しているセッションのセッションのトランスクリプトを配置するディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-308">Specifies the directory to place session transcripts for sessions using this session configuration.</span></span>

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

### <span data-ttu-id="79d6c-309">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="79d6c-309">-TypesToProcess</span></span>

<span data-ttu-id="79d6c-310">`.ps1xml`セッション構成を使用するセッションに、指定された種類のファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-310">Adds the specified `.ps1xml` type files to sessions that use the session configuration.</span></span> <span data-ttu-id="79d6c-311">種類のファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-311">Enter the type filenames.</span></span> <span data-ttu-id="79d6c-312">このパラメーターの値には、型のファイル名への完全パスまたは絶対パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d6c-312">The value of this parameter must be a full or absolute path to type filenames.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-313">-UserDriveMaximumSize</span><span class="sxs-lookup"><span data-stu-id="79d6c-313">-UserDriveMaximumSize</span></span>

<span data-ttu-id="79d6c-314">このセッション構成を使用するセッションで公開されているユーザードライブの最大サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-314">Specifies the maximum size for user drives exposed in sessions that use this session configuration.</span></span>
<span data-ttu-id="79d6c-315">省略した場合、各ドライブルートの既定のサイズ `User:` は 50 mb です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-315">When omitted, the default size of each `User:` drive root is 50MB.</span></span>

<span data-ttu-id="79d6c-316">このパラメーターは **MountUserDrive** と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d6c-316">This parameter should be used with **MountUserDrive**.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-317">-変数の定義</span><span class="sxs-lookup"><span data-stu-id="79d6c-317">-VariableDefinitions</span></span>

<span data-ttu-id="79d6c-318">セッション構成を使用するセッションに、指定された変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-318">Adds the specified variables to sessions that use the session configuration.</span></span> <span data-ttu-id="79d6c-319">ハッシュ テーブルに次のキーを入力します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-319">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="79d6c-320">名前-変数の名前。</span><span class="sxs-lookup"><span data-stu-id="79d6c-320">Name - Name of the variable.</span></span> <span data-ttu-id="79d6c-321">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-321">This key is required.</span></span>
- <span data-ttu-id="79d6c-322">値-変数の値。</span><span class="sxs-lookup"><span data-stu-id="79d6c-322">Value - Variable value.</span></span> <span data-ttu-id="79d6c-323">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-323">This key is required.</span></span>
- <span data-ttu-id="79d6c-324">オプション-変数オプション。</span><span class="sxs-lookup"><span data-stu-id="79d6c-324">Options - Variable options.</span></span> <span data-ttu-id="79d6c-325">このキーはオプションです。</span><span class="sxs-lookup"><span data-stu-id="79d6c-325">This key is optional.</span></span> <span data-ttu-id="79d6c-326">既定値は **None** です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-326">The default value is **None**.</span></span> <span data-ttu-id="79d6c-327">このパラメーターに指定できる値は、None、ReadOnly、Constant、Private、または AllScope です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-327">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="79d6c-328">例: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="79d6c-328">For example: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-329">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="79d6c-329">-VisibleAliases</span></span>

<span data-ttu-id="79d6c-330">セッションのエイリアスを、このパラメーターの値に指定されたエイリアスと、**AliasDefinition** パラメーターに定義するエイリアスに制限します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-330">Limits the aliases in the session to those specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="79d6c-331">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-331">Wildcard characters are supported.</span></span> <span data-ttu-id="79d6c-332">既定では、PowerShell エンジンによって定義されたすべてのエイリアスとモジュールがエクスポートするすべてのエイリアスがセッションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-332">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="79d6c-333">例: `VisibleAliases='gcm', 'gp'`</span><span class="sxs-lookup"><span data-stu-id="79d6c-333">For example: `VisibleAliases='gcm', 'gp'`</span></span>

<span data-ttu-id="79d6c-334">セッション構成ファイルに **表示** されているパラメーターがある場合は、PowerShell によって、 `Import-Module` コマンドレットとその ipmo エイリアスがセッションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-334">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="79d6c-335">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="79d6c-335">-VisibleCmdlets</span></span>

<span data-ttu-id="79d6c-336">セッションのコマンドレットを、このパラメーターの値に指定されたコマンドレットに制限します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-336">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="79d6c-337">ワイルドカード文字とモジュール修飾名がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-337">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="79d6c-338">既定では、セッション内のモジュールがエクスポートするすべてのコマンドレットが、セッションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-338">By default, all cmdlets that modules in the session export are visible in the session.</span></span> <span data-ttu-id="79d6c-339">**SessionType** および **ModulesToImport** パラメーターを使用して、どのモジュールとスナップインをセッションにインポートするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-339">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="79d6c-340">**ModulesToImport** 内のモジュールがコマンドレットを公開していない場合、適切なモジュールは自動読み込みを試行します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-340">If no modules in **ModulesToImport** expose the cmdlet, the appropriate module will attempt to be autoloaded.</span></span>

<span data-ttu-id="79d6c-341">セッション構成ファイルに **表示** されているパラメーターがある場合は、PowerShell によって、 `Import-Module` コマンドレットとその ipmo エイリアスがセッションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-341">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d6c-342">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="79d6c-342">-VisibleExternalCommands</span></span>

<span data-ttu-id="79d6c-343">セッションで実行できる外部バイナリ、スクリプト、およびコマンドを、このパラメーターの値で指定されているものに制限します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-343">Limits the external binaries, scripts, and commands that can be executed in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="79d6c-344">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-344">Wildcard characters are supported.</span></span>

<span data-ttu-id="79d6c-345">既定では、セッションに外部コマンドは表示されません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-345">By default, no external commands are visible in the session.</span></span>

<span data-ttu-id="79d6c-346">セッション構成ファイルに **表示** されているパラメーターがある場合は、PowerShell によって、 `Import-Module` セッションからコマンドレットとその ipmo エイリアスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-346">When any **Visible** parameter is included in the session configuration file, PowerShell, removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="79d6c-347">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="79d6c-347">-VisibleFunctions</span></span>

<span data-ttu-id="79d6c-348">セッションの関数を、このパラメーターの値に指定された関数と、**FunctionDefinition** パラメーターに定義する関数に制限します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-348">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinition** parameter.</span></span> <span data-ttu-id="79d6c-349">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-349">Wildcard characters are supported.</span></span>

<span data-ttu-id="79d6c-350">既定では、セッション内のモジュールがエクスポートするすべての関数が、セッションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-350">By default, all functions that modules in the session export are visible in the session.</span></span> <span data-ttu-id="79d6c-351">**SessionType** および **ModulesToImport** パラメーターを使用して、どのモジュールとスナップインをセッションにインポートするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-351">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span>

<span data-ttu-id="79d6c-352">セッション構成ファイルに **表示** されているパラメーターがある場合は、PowerShell によって、 `Import-Module` コマンドレットとその ipmo エイリアスがセッションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-352">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="79d6c-353">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="79d6c-353">-VisibleProviders</span></span>

<span data-ttu-id="79d6c-354">セッション内の PowerShell プロバイダーを、このパラメーターの値に指定されているものに制限します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-354">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="79d6c-355">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-355">Wildcard characters are supported.</span></span>

<span data-ttu-id="79d6c-356">既定では、セッション内のモジュールがエクスポートするすべてのプロバイダーが、セッションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-356">By default, all providers that modules in the session export are visible in the session.</span></span> <span data-ttu-id="79d6c-357">セッションにインポートするモジュールを特定するには、 **Sessiontype** パラメーターと **ModulesToImport** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-357">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="79d6c-358">セッション構成ファイルに **表示** されているパラメーターがある場合は、PowerShell によって `Import-Module` コマンドレットとそのエイリアスがセッションから削除され `ipmo` ます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-358">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="79d6c-359">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="79d6c-359">CommonParameters</span></span>

<span data-ttu-id="79d6c-360">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="79d6c-360">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="79d6c-361">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d6c-361">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="79d6c-362">入力</span><span class="sxs-lookup"><span data-stu-id="79d6c-362">INPUTS</span></span>

### <span data-ttu-id="79d6c-363">なし</span><span class="sxs-lookup"><span data-stu-id="79d6c-363">None</span></span>

<span data-ttu-id="79d6c-364">パイプを使用してこのコマンドレットにオブジェクトを送ることはできません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-364">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="79d6c-365">出力</span><span class="sxs-lookup"><span data-stu-id="79d6c-365">OUTPUTS</span></span>

### <span data-ttu-id="79d6c-366">なし</span><span class="sxs-lookup"><span data-stu-id="79d6c-366">None</span></span>

<span data-ttu-id="79d6c-367">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-367">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="79d6c-368">注</span><span class="sxs-lookup"><span data-stu-id="79d6c-368">NOTES</span></span>

<span data-ttu-id="79d6c-369">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-369">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="79d6c-370">**VisibleCmdlets** や **VisibleProviders** などのパラメーターでは、セッションに項目がインポートされません。</span><span class="sxs-lookup"><span data-stu-id="79d6c-370">Parameters, such as **VisibleCmdlets** and **VisibleProviders**, do not import items into the session.</span></span> <span data-ttu-id="79d6c-371">代わりに、セッションにインポートされた項目の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-371">Instead, they select from among the items imported into the session.</span></span> <span data-ttu-id="79d6c-372">たとえば、VisibleProviders パラメーターの値が証明書プロバイダーであるにもかかわらず、 **ModulesToImport** パラメーターで証明書プロバイダーが含まれるモジュールが指定されていない場合、証明書プロバイダーはセッションに表示されませ **ん。**</span><span class="sxs-lookup"><span data-stu-id="79d6c-372">For example, if the value of the **VisibleProviders** parameter is the Certificate provider, but the **ModulesToImport** parameter does not specify the **Microsoft.PowerShell.Security** module that contains the Certificate provider, the Certificate provider is not visible in the session.</span></span>
- <span data-ttu-id="79d6c-373">`New-PSSessionConfigurationFile`**path** パラメーターで指定したパスに .pssc ファイル名拡張子を持つセッション構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-373">`New-PSSessionConfigurationFile` creates a session configuration file that has a .pssc file name extension in the path that you specify in the **Path** parameter.</span></span> <span data-ttu-id="79d6c-374">セッション構成ファイルを使用してセッション構成を作成すると、このコマンドレットによって `Register-PSSessionConfiguration` 構成ファイルがコピーされ、ファイルのアクティブなコピーがディレクトリの **sessionconfig** サブディレクトリに保存され `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-374">When you use the session configuration file to create a session configuration, the `Register-PSSessionConfiguration` cmdlet copies the configuration file and saves an active copy of the file in the **SessionConfig** subdirectory of the `$PSHOME` directory.</span></span>

  <span data-ttu-id="79d6c-375">セッション構成の **Configfilepath** プロパティには、アクティブなセッション構成ファイルの完全修飾パスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="79d6c-375">The **ConfigFilePath** property of the session configuration contains the fully qualified path of the active session configuration file.</span></span> <span data-ttu-id="79d6c-376">任意の `$PSHOME` テキストエディターを使用して、ディレクトリ内のアクティブな構成ファイルをいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="79d6c-376">You can modify the active configuration file in the `$PSHOME` directory at any time using any text editor.</span></span> <span data-ttu-id="79d6c-377">加えた変更は、既存のセッションではなく、セッション構成を使用するすべての新しいセッションに影響します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-377">The changes that you make affect all new sessions that use the session configuration, but not existing sessions.</span></span>

  <span data-ttu-id="79d6c-378">編集されたセッション構成ファイルを使用する前に、コマンドレットを使用して、 `Test-PSSessionConfigurationFile` 構成ファイルのエントリが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79d6c-378">Before using an edited session configuration file, use the `Test-PSSessionConfigurationFile` cmdlet to verify that the configuration file entries are valid.</span></span>

## <span data-ttu-id="79d6c-379">関連リンク</span><span class="sxs-lookup"><span data-stu-id="79d6c-379">RELATED LINKS</span></span>

[<span data-ttu-id="79d6c-380">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="79d6c-380">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="79d6c-381">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="79d6c-381">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="79d6c-382">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="79d6c-382">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="79d6c-383">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="79d6c-383">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="79d6c-384">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="79d6c-384">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="79d6c-385">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="79d6c-385">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="79d6c-386">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="79d6c-386">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="79d6c-387">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="79d6c-387">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="79d6c-388">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="79d6c-388">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="79d6c-389">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="79d6c-389">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
