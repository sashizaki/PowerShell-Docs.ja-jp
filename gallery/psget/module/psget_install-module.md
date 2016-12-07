---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,コマンドレット,ギャラリー"
ms.date: 2016-10-14
contributor: manikb
title: psget_install module
ms.technology: powershell
ms.openlocfilehash: 82e4bb1ec76b1a51e1a99de85bc77a5429d46e26
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="install-module"></a>Install-Module

PowerShell モジュールをオンライン リポジトリからローカル コンピューターにインストールします。

## <a name="description"></a>説明

Install-Module コマンドレットは、オンライン ギャラリーから 1 つ以上のモジュールをダウンロードして検証し、ローカル コンピューターの指定したインストール スコープにインストールします。

Install-Module コマンドレットは、指定の条件を満たす 1 つ以上のモジュールをオンライン ギャラリーから取得して、検索結果が有効なモジュールであることを確認し、モジュール フォルダーをインストールの場所にコピーします。

スコープが定義されていない場合、または Scope パラメーターの値が AllUsers である場合は、モジュールは %systemdrive%:\Program Files\WindowsPowerShell\Modules にインストールされます。 Scope の値が CurrentUser の場合は、モジュールは $home\Documents\WindowsPowerShell\Modules にインストールされます。

指定したモジュールの最小バージョンのみに基づいて、結果をフィルター処理することができます。

- Windows PowerShell 5.0 以降の Side-by-Side バージョン サポート
- モジュールの依存関係のインストール サポート
- **"信頼されていません" のプロンプト:**信頼されていないリポジトリからモジュールをインストールするには、ユーザーの同意が必要です。
- -Force は、インストール済みのモジュールを再インストールします
- RequiredVersion は、SxS の指定したバージョンを PowerShell バージョン 5.0 以降の既存のバージョンでインストールします。

### <a name="scope"></a>スコープ
モジュールのインストール スコープを指定します。 このパラメーターに使用できる値は、AllUsers と CurrentUser です。

既定のインストール スコープは AllUsers です。

AllUsers スコープでは、モジュールはコンピューターのすべてのユーザーがアクセス可能な場所 "$env:SystemDrive\Program Files\WindowsPowerShell\Modules" にインストールされます。

CurrentUser スコープでは、モジュールは "$home\Documents\WindowsPowerShell\Modules" のみにインストールされるので、モジュールを使用できるのは現在のユーザーのみです。

## <a name="notes"></a>メモ

このコマンドレットは、Windows PowerShell 3.0 または今後のリリースの Windows PowerShell、Windows 7 または Windows 2008 R2、および今後のリリースの Windows で機能します。

インストールされているモジュールをインポートできない場合 (つまり、同じ名前の.psm1、.psd1 または .dll がフォルダー内にない場合)、Force パラメーターをコマンドに追加しない限り、インストールは失敗します。

コンピューター上のモジュールのバージョンが Name パラメーターに指定された値と一致しているときに、MinimumVersion または RequiredVersion パラメーターを追加していない場合は、そのモジュールをインストールせずに Install-Module スクリプトが警告なしで続行されます。 MinimumVersion または RequiredVersion パラメーターが指定されているときに、既存のモジュールがそのパラメーターの値と一致しない場合は、エラーが発生します。 具体的には、現在インストールされているモジュールのバージョンが MinimumVersion パラメーターの値よりも低い、または RequiredVersion パラメーターの値と等しくない場合、エラーが発生します。 インストールされているモジュールのバージョンが MinimumVersion パラメーターの値より大きい、または RequiredVersion パラメーターの値と等しい場合は、そのモジュールをインストールせずに Install-Module スクリプトが警告なしで続行されます。

指定した名前に一致するモジュールがオンライン ギャラリーに存在しない場合、Install-Module はエラーを返します。

複数のモジュールをインストールするには、モジュール名の配列をコンマで区切って指定します。 複数のモジュール名を指定する場合は、MinimumVersion または RequiredVersion を追加できません。

既定では、Windows PowerShell Desired State Configuration (DSC) リソースをインストール中に混乱しないように、モジュールは Program Files フォルダーにインストールされます。複数の PSGetItemInfo オブジェクトを Install-Module にパイプすることができます。これは、複数のモジュールを 1 つのコマンドでインストールするよう指定するための別の方法です。

悪意のあるコードが含まれているモジュールを実行しないようにするため、インストール済みのモジュールはインストールでは自動的にインポートされません。 セキュリティのベスト プラクティスとして、最初にモジュール内のコマンドレットまたは関数を実行する前に、モジュール コードを評価します。


## <a name="cmdlet-syntax"></a>コマンドレット構文
```powershell
Get-Command -Name Install-Module -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a>コマンドレット オンライン ヘルプ リファレンス

[Install-Module](http://go.microsoft.com/fwlink/?LinkID=398573)

## <a name="example-commands"></a>コマンド例

```powershell

# Install a module by name
Install-Module -Name MyDscModule

# Install multiple modules
Install-Module ContosoClient,ContosoServer

# Install a module using its minimum version
Install-Module -Name ContosoServer -MinimumVersion 1.0

# Install a specific version of a module
Install-Module -Name ContosoServer -RequiredVersion 1.1.3

# Install the latest version of a module to $home\Documents\WindowsPowerShell\Modules.
Install-Module -Name ContosoServer -Scope CurrentUser

# if a module is already available under $env:PSModulePath, below command fails with 'ModuleAlreadyInstalled,Install-Package,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage'
Install-Module ContosoServer -RequiredVersion 1.5

# if a module is already available under $env:PSModulePath, below command fails with 'ModuleAlreadyInstalled,Install-Package,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage'
Install-Module ContosoServer -MinimumVersion 2.5

# Install multiple modules from multiple registered repositories
Install-Module ContosoClient,ContosoServer -Repository PSGallery, PrivatePSGallery

# Install a module with -WhatIf
Install-Module ContosoClient -WhatIf

# Install a module with -Confirm. A prompt will be displayed to confirm the installation.
Install-Module ContosoClient -WhatIf

# -Force option reinstalls the installed module
Install-Module ContosoClient -Force

# Install a module with dependencies
Install-Module -Name 
```

## <a name="install-module-cmdlet-in-pipeline-operations"></a>パイプライン操作での Install-Module コマンドレット

```powershell

# Find a module and install it
Find-Module -Name "MyDSC*" | Install-Module

# Find a module and install it to the CurrentUser scope
Find-Module -Name "MyDSC*" | Install-Module -Scope CurrentUser

# Find commands by name and install them
# The first command finds the specified commands in the INT repository, and then uses the pipeline operator to pass them to Install-Module to install them.
# The second command uses Get-InstalledModule to verify the modules from the prior command are installed.
Find-Command -Repository "INT" -Name Get-ContosoClient,Get-ContosoServer | Install-Module
Get-InstalledModule

# This command finds the resource named MyResource and passes it to the Install-Module cmdlet by using the pipeline operator. The Install-Module cmdlet installs the module for the resource. 
# If you pipe multiple resources to the Install-Module cmdlet from the same module, Install-Module attempts to install the module only once. 
Find-DscResource -Name "MyResource" | Install-Module
Get-InstalledModule

# Find multiple role capabilities and install them
Find-RoleCapability -Name MyJeaRole, Maintenance | Install-Module
Get-InstalledModule

```

## <a name="side-by-side-version-support-on-powershell-50-or-newer"></a>PowerShell 5.0 以降の Side-by-Side バージョン サポート

PowerShellGet は、Windows PowerShell 5.0 以降で実行される Install-Module、Update-Module および Publish-Module の各コマンドレットの Side-by-Side (SxS) モジュール バージョン サポートに対応しています。

### <a name="install-module-examples"></a>Install-Module の例

```powershell
# Install a version of the module
Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.0 -Repository PSGallery
Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase

Name : PSScriptAnalyzer
Version : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

# Install another version of the module in Side-by-Side with already installed version.
Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.1 -Repository PSGallery
Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase

Name       : PSScriptAnalyzer 
Version    : 1.1.1
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.1
Name       : PSScriptAnalyzer
Version    : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

# Get all versions of an installed module
Get-InstalledModule -Name PSScriptAnalyzer -AllVersions
Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.1.0      PSScriptAnalyzer                    PSGallery            PSScriptAnalyzer provides script analysis... 
1.1.1      PSScriptAnalyzer                    PSGallery            PSScriptAnalyzer provides script analysis...


```

## <a name="install-module-with-its-dependencies"></a>モジュールを依存関係と共にインストールする

```powershell

# Find a module
Find-Module -Name TypePx -Repository PSGallery

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
2.0.1.20   TypePx                              PSGallery            The TypePx module adds properties and methods to the m...

# Find a module and its dependencies
Find-Module -Name TypePx -Repository PSGallery -IncludeDependencies

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
2.0.1.20   TypePx                              PSGallery            The TypePx module adds properties and methods to the m...
1.0.5.18   SnippetPx                           PSGallery            The SnippetPx module enhances the snippet experience i...

# Discover the dependencies list without adding -IncludeDependencies
$result = Find-Module -Name TypePx -Repository PSGallery
$result.Dependencies

Name                           Value
----                           -----
Name                           SnippetPx
CanonicalId                    powershellget:SnippetPx/#https://www.powershellgallery.com/api/v2/


# Now install the module along with its dependencies
Install-Module -Name TypePx -Repository PSGallery -Verbose

VERBOSE: Repository details, Name = 'PSGallery', Location = 'https://www.powershellgallery.com/api/v2/'; IsTrusted =
'False'; IsRegistered = 'True'.
VERBOSE: Using the provider 'PowerShellGet' for searching packages.
VERBOSE: Using the specified source names : 'PSGallery'.
VERBOSE: Getting the provider object for the PackageManagement Provider 'NuGet'.
VERBOSE: The specified Location is 'https://www.powershellgallery.com/api/v2/' and PackageManagementProvider is
'NuGet'.
VERBOSE: Searching repository 'https://www.powershellgallery.com/api/v2/FindPackagesById()?id='TypePx'' for ''.
VERBOSE: Total package yield:'1' for the specified package 'TypePx'.
VERBOSE: Performing the operation "Install-Module" on target "Version '2.0.1.20' of module 'TypePx'".

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change its
InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from
'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
VERBOSE: The installation scope is specified to be 'AllUsers'.
VERBOSE: The specified module will be installed in 'C:\Program Files\WindowsPowerShell\Modules'.
VERBOSE: The specified Location is 'NuGet' and PackageManagementProvider is 'NuGet'.
VERBOSE: Downloading module 'TypePx' with version '2.0.1.20' from the repository
'https://www.powershellgallery.com/api/v2/'.
VERBOSE: Searching repository 'https://www.powershellgallery.com/api/v2/FindPackagesById()?id='TypePx'' for ''.
VERBOSE: Searching repository 'https://www.powershellgallery.com/api/v2/FindPackagesById()?id='SnippetPx'' for ''.
VERBOSE: InstallPackage' - name='SnippetPx',
version='1.0.5.18',destination='C:\Users\manikb\AppData\Local\Temp\1027042896'
VERBOSE: DownloadPackage' - name='SnippetPx',
version='1.0.5.18',destination='C:\Users\manikb\AppData\Local\Temp\1027042896\SnippetPx\SnippetPx.nupkg',
uri='https://www.powershellgallery.com/api/v2/package/SnippetPx/1.0.5.18'
VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/SnippetPx/1.0.5.18'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/SnippetPx/1.0.5.18'.
VERBOSE: Completed downloading 'SnippetPx'.
VERBOSE: Hash for package 'SnippetPx' does not match hash provided from the server.
VERBOSE: InstallPackageLocal' - name='SnippetPx',
version='1.0.5.18',destination='C:\Users\manikb\AppData\Local\Temp\1027042896'
VERBOSE: InstallPackage' - name='TypePx',
version='2.0.1.20',destination='C:\Users\manikb\AppData\Local\Temp\1027042896'
VERBOSE: DownloadPackage' - name='TypePx',
version='2.0.1.20',destination='C:\Users\manikb\AppData\Local\Temp\1027042896\TypePx\TypePx.nupkg',
uri='https://www.powershellgallery.com/api/v2/package/TypePx/2.0.1.20'
VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/TypePx/2.0.1.20'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/TypePx/2.0.1.20'.
VERBOSE: Completed downloading 'TypePx'.
VERBOSE: Hash for package 'TypePx' does not match hash provided from the server.
VERBOSE: InstallPackageLocal' - name='TypePx',
version='2.0.1.20',destination='C:\Users\manikb\AppData\Local\Temp\1027042896'
VERBOSE: Installing the dependency module 'SnippetPx' with version '1.0.5.18' for the module 'TypePx'.
VERBOSE: Module 'SnippetPx' was installed successfully to path 'C:\Program
Files\WindowsPowerShell\Modules\SnippetPx\1.0.5.18'.
VERBOSE: Module 'TypePx' was installed successfully to path 'C:\Program
Files\WindowsPowerShell\Modules\TypePx\2.0.1.20'.


# Get the installed modules
Get-InstalledModule

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0.5.18   SnippetPx                           PSGallery            The SnippetPx module enhances the snippet experience i...
2.0.1.20   TypePx                              PSGallery            The TypePx module adds properties and methods to the m...

```

## <a name="error-scenarios"></a>エラー シナリオ

```powershell

# Below command fails with 'NameShouldNotContainWildcardCharacters,Install-Module'
Install-Module ContosoServe*

# Below command fails with 'VersionRangeAndRequiredVersionCannotBeSpecifiedTogether,Install-Module'
Install-Module ContosoServer -MinimumVersion 1.0 -RequiredVersion 5.0

# Below command fails with 'VersionParametersAreAllowedOnlyWithSingleName,Install-Module'
Install-Module ContosoClient,ContosoServer -RequiredVersion 2.0

# Below command fails with 'VersionParametersAreAllowedOnlyWithSingleName,Install-Module'
Install-Module ContosoClient,ContosoServer -MinimumVersion 2.0

```

