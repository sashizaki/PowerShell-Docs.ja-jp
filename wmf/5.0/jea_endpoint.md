---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 66db78cfb136f22cad9078d7113dad085ee667a5
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="creating-and-connecting-to-a-jea-endpoint"></a><span data-ttu-id="c100e-102">JEA エンドポイントの作成および接続</span><span class="sxs-lookup"><span data-stu-id="c100e-102">Creating and Connecting to a JEA Endpoint</span></span>
<span data-ttu-id="c100e-103">JEA エンドポイントを作成するには、特別に構成された PowerShell セッション構成ファイルを作成し、登録する必要があります。このファイルは、**New-PSSessionConfigurationFile** コマンドレットで登録できます。</span><span class="sxs-lookup"><span data-stu-id="c100e-103">To create a JEA endpoint, you need to create and register a specially-configured PowerShell Session Configuration file, which can be generated with the **New-PSSessionConfigurationFile** cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -TranscriptDirectory "C:\ProgramData\JEATranscripts" -RunAsVirtualAccount -RoleDefinitions @{ 'CONTOSO\NonAdmin_Operators' = @{ RoleCapabilities = 'Maintenance' }} -Path "$env:ProgramData\JEAConfiguration\Demo.pssc"
```

<span data-ttu-id="c100e-104">これにより、次のようなセッション構成ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c100e-104">This will create a session configuration file that looks like this:</span></span>
```powershell
@{

# Version number of the schema used for this document
SchemaVersion = '2.0.0.0'

# ID used to uniquely identify this document
GUID = 'a384fdd3-5830-4a2c-ac86-cdd1822c3afd'

# Author of this document
Author = 'Administrator'

# Description of the functionality provided by these settings
# Description = ''

# Session type defaults to apply for this session configuration. Can be 'RestrictedRemoteServer' (recommended), 'Empty', or 'Default'
SessionType = 'RestrictedRemoteServer'

# Directory to place session transcripts for this session configuration
TranscriptDirectory = 'C:\ProgramData\JEATranscripts'

# Whether to run this session configuration as the machine's (virtual) administrator account
RunAsVirtualAccount = $true

# Groups associated with machine's (virtual) administrator account
# RunAsVirtualAccountGroups = 'Remote Desktop Users', 'Remote Management Users'

# Scripts to run when applied to a session
# ScriptsToProcess = 'C:\ConfigData\InitScript1.ps1', 'C:\ConfigData\InitScript2.ps1'

# User roles (security groups), and the Role Capabilities that should be applied to them when applied to a session
RoleDefinitions = @{
    'CONTOSO\NonAdmin_Operators' = @{
        'RoleCapabilities' = 'Maintenance' } }

}
```
<span data-ttu-id="c100e-105">JEA エンドポイントを作成する場合は、コマンドの次のパラメーター (およびファイル内の対応するキー) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c100e-105">When creating a JEA endpoint, the following parameters of the command (and corresponding keys in the file) must be set:</span></span>
1.  <span data-ttu-id="c100e-106">SessionType を RestrictedRemoteServer に</span><span class="sxs-lookup"><span data-stu-id="c100e-106">SessionType to RestrictedRemoteServer</span></span>
2.  <span data-ttu-id="c100e-107">RunAsVirtualAccount を **$true** に</span><span class="sxs-lookup"><span data-stu-id="c100e-107">RunAsVirtualAccount to **$true**</span></span>
3.  <span data-ttu-id="c100e-108">TranscriptPath を各セッションの後 "over the shoulder" トランスクリプトが保存されるディレクトリに</span><span class="sxs-lookup"><span data-stu-id="c100e-108">TranscriptPath to the directory where “over the shoulder” transcripts will be saved after each session</span></span>
4.  <span data-ttu-id="c100e-109">RoleDefinitions をどのグループがどの "ロール機能" にアクセスできるかを定義するハッシュテーブルに設定します。</span><span class="sxs-lookup"><span data-stu-id="c100e-109">RoleDefinitions to a hashtable that defines which groups have access to which “Role Capabilities.”</span></span>  <span data-ttu-id="c100e-110">このフィールドでは、このエンドポイントで**どのユーザー**が**どの操作**を実行できるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="c100e-110">This field defines **who** can do **what** on this endpoint.</span></span>   <span data-ttu-id="c100e-111">ロール機能は特別なファイルで、これについては後で説明します。</span><span class="sxs-lookup"><span data-stu-id="c100e-111">Role Capabilities are special files that will be explained shortly.</span></span>


<span data-ttu-id="c100e-112">RoleDefinitions フィールドでは、どのグループがどのロール機能にアクセスできるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="c100e-112">The RoleDefinitions field defines which groups had access to which Role Capabilities.</span></span>  <span data-ttu-id="c100e-113">ロール機能は、接続ユーザーに公開される一連の機能を定義するファイルです。</span><span class="sxs-lookup"><span data-stu-id="c100e-113">A Role Capability is a file that defines a set of capabilities that will be exposed to connecting users.</span></span>  <span data-ttu-id="c100e-114">ロール機能は、**New-PSRoleCapabilityFile** コマンドを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="c100e-114">You can create Role Capabilities with the **New-PSRoleCapabilityFile** command.</span></span>

```powershell
New-PSRoleCapabilityFile -Path "$env:ProgramFiles\WindowsPowerShell\Modules\DemoModule\RoleCapabilities\Maintenance.psrc"
```

<span data-ttu-id="c100e-115">これにより、次のようなテンプレート ロール機能が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c100e-115">This will generate a template role capability that looks like this:</span></span>
```
@{

# ID used to uniquely identify this document
GUID = '9287a34f-3f0e-4fbe-9dd7-f1361ba9fd65'

# Author of this document
Author = 'Administrator'

# Description of the functionality provided by these settings
# Description = ''

# Company associated with this document
CompanyName = 'Unknown'

# Copyright statement for this document
Copyright = '(c) 2015 Administrator. All rights reserved.'

# Modules to import when applied to a session
# ModulesToImport = 'MyCustomModule', @{ ModuleName = 'MyCustomModule'; ModuleVersion = '1.0.0.0'; GUID = '4d30d5f0-cb16-4898-812d-f20a6c596bdf' }

# Aliases to make visible when applied to a session
# VisibleAliases = 'Item1', 'Item2'

# Cmdlets to make visible when applied to a session
# VisibleCmdlets = 'Invoke-Cmdlet1', @{ Name = 'Invoke-Cmdlet2'; Parameters = @{ Name = 'Parameter1'; ValidateSet = 'Item1', 'Item2' }, @{ Name = 'Parameter2'; ValidatePattern = 'L*' } }

# Functions to make visible when applied to a session
# VisibleFunctions = 'Invoke-Function1', @{ Name = 'Invoke-Function2'; Parameters = @{ Name = 'Parameter1'; ValidateSet = 'Item1', 'Item2' }, @{ Name = 'Parameter2'; ValidatePattern = 'L*' } }

# External commands (scripts and applications) to make visible when applied to a session
# VisibleExternalCommands = 'Item1', 'Item2'

# Providers to make visible when applied to a session
# VisibleProviders = 'Item1', 'Item2'

# Scripts to run when applied to a session
# ScriptsToProcess = 'C:\ConfigData\InitScript1.ps1', 'C:\ConfigData\InitScript2.ps1'

# Aliases to be defined when applied to a session
# AliasDefinitions = @{ Name = 'Alias1'; Value = 'Invoke-Alias1'}, @{ Name = 'Alias2'; Value = 'Invoke-Alias2'}

# Functions to define when applied to a session
# FunctionDefinitions = @{ Name = 'MyFunction'; ScriptBlock = { param($MyInput) $MyInput } }

# Variables to define when applied to a session
# VariableDefinitions = @{ Name = 'Variable1'; Value = { 'Dynamic' + 'InitialValue' } }, @{ Name = 'Variable2'; Value = 'StaticInitialValue' }

# Environment variables to define when applied to a session
# EnvironmentVariables = @{ Variable1 = 'Value1'; Variable2 = 'Value2' }

# Type files (.ps1xml) to load when applied to a session
# TypesToProcess = 'C:\ConfigData\MyTypes.ps1xml', 'C:\ConfigData\OtherTypes.ps1xml'

# Format files (.ps1xml) to load when applied to a session
# FormatsToProcess = 'C:\ConfigData\MyFormats.ps1xml', 'C:\ConfigData\OtherFormats.ps1xml'

# Assemblies to load when applied to a session
# AssembliesToLoad = 'System.Web', 'System.OtherAssembly, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'

}

```
<span data-ttu-id="c100e-116">JEA セッション構成で使用するには、ロール機能を有効な PowerShell モジュールとして "RoleCapabilities" という名前のディレクトリに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c100e-116">To be used by a JEA session configuration, Role Capabilities must be saved as a valid PowerShell module in a directory named “RoleCapabilities”.</span></span> <span data-ttu-id="c100e-117">必要に応じて、1 つのモジュールに複数のロール機能ファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c100e-117">A module may have multiple role capability files, if desired.</span></span>

<span data-ttu-id="c100e-118">ユーザーが JEA セッションに接続するときにどのコマンドレット、関数、エイリアス、およびスクリプトにアクセスできるかの構成を開始するには、コメント アウトされたテンプレートに従ってロール機能ファイルに独自のルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="c100e-118">To start configuring which cmdlets, functions, aliases, and scripts a user may access when connecting to a JEA session, add your own rules to the Role Capability file following the commented out templates.</span></span> <span data-ttu-id="c100e-119">ロール機能を構成する方法の詳細については、完全な[エクスペリエンス ガイド](http://aka.ms/JEA)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c100e-119">For a deeper look into how you can configure Role Capabilities, check out the full [experience guide](http://aka.ms/JEA).</span></span>

<span data-ttu-id="c100e-120">最後に、セッション構成と関連ロール機能のカスタマイズが完了した後、このセッション構成を登録し、**Register-PSSessionConfiguration** を実行してエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c100e-120">Finally, once you have finished customizing your session configuration and related Role Capabilities, register this session configuration and create the endpoint by running **Register-PSSessionConfiguration**.</span></span>

```powershell
Register-PSSessionConfiguration -Name Maintenance -Path "C:\ProgramData\JEAConfiguration\Demo.pssc"
```

## <a name="connect-to-a-jea-endpoint"></a><span data-ttu-id="c100e-121">JEA エンドポイントへの接続</span><span class="sxs-lookup"><span data-stu-id="c100e-121">Connect to a JEA Endpoint</span></span>
<span data-ttu-id="c100e-122">JEA エンドポイントへの接続は、他の PowerShell エンドポイントへの接続と同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="c100e-122">Connecting to a JEA Endpoint works the same way connecting to any other PowerShell endpoint works.</span></span>  <span data-ttu-id="c100e-123">**New-PSSession**、**Invoke-Command**、または **Enter-PSSession** の "ConfigurationName" パラメーターとして JEA エンドポイント名を付けることのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="c100e-123">You simply have to give your JEA endpoint name as the “ConfigurationName” parameter for **New-PSSession**, **Invoke-Command**, or **Enter-PSSession**.</span></span>

```powershell
Enter-PSSession -ConfigurationName Maintenance -ComputerName localhost
```
<span data-ttu-id="c100e-124">JEA セッションに接続した後は、自分がアクセス権を持つロール機能のホワイトリストに登録されたコマンドのみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c100e-124">Once you have connected to the JEA session, you will be limited to running the commands whitelisted in the Role Capabilities that you have access to.</span></span> <span data-ttu-id="c100e-125">ロールに許可されていないコマンドを実行しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c100e-125">If you try to run any command not allowed for your role, you will encounter an error.</span></span>
