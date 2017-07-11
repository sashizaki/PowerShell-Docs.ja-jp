---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: Get-InstalledModule
ms.openlocfilehash: 6f485d04503ea6d9a51a68ae7ec3d0dc2e6facab
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="get-installedmodule" class="xliff"></a>

# Get-InstalledModule

コンピューター上のインストールされているモジュールを取得します。

<a id="description" class="xliff"></a>

## 説明

Get-InstalledModule コマンドレットは、Install-Module コマンドレットを使用してインストールされたコンピューター上にインストールされている PowerShell モジュールを取得します。

インストールされている各モジュールに対し、Get-InstalledModule は、インストールされているモジュールをアンインストールするための Uninstall-Module に必要に応じてパイプできる PSRepositoryItemInfo オブジェクトを返します。

- Get-InstalledModule は、名前、バージョン パラメーターに基づいてインストールされているモジュールをフィルター処理できます。
- Get-InstalledModule は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、MaximumVersion、RequiredVersion、AllVersions。
  - これらのパラメーターは、MinmimumVersion と MaximumVersion を除いて、同時に使用できません。
  - これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのモジュール名が指定されている場合にのみ許可されます。
  - RequiredVersion パラメーターが指定されていない場合、Get-InstalledModule は指定された最小バージョン以上の最新バージョンのインストールされているモジュールを返すか、または最新バージョンのモジュールを返します (最小バージョンが指定されていない場合)。 
  - RequiredVersion パラメーターが指定されている場合、Get-InstalledModule は指定したバージョンに完全に一致するバージョンのインストールされているモジュールのみを返します。

<a id="cmdlet-syntax" class="xliff"></a>

## コマンドレット構文
```powershell
Get-Command -Name Get-InstalledModule -Module PowerShellGet -Syntax
```

<a id="cmdlet-online-help-reference" class="xliff"></a>

## コマンドレット オンライン ヘルプ リファレンス

[Get-InstalledModule](http://go.microsoft.com/fwlink/?LinkId=526863)

<a id="example-commands" class="xliff"></a>

## コマンド例

```powershell

# Get all modules installed using PowerShellGet cmdlets
Get-InstalledModule

# Get a specific installed module
Get-InstalledModule DJoin

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0        DJoin                               PSGallery            This is a PowerShell frontend to the DJOIN.exe c...

# Get installed module with wildcards
Get-InstalledModule -Name AzureRM*

# Get all versions of an installed module
Get-InstalledModule -Name AzureRM.Automation -AllVersions

# Get installed module with MinimumVersion
Get-InstalledModule -Name AzureRM.Automation -MinimumVersion 1.0.0

# Get installed module with MaximumVersion
Get-InstalledModule -Name AzureRM.Automation -MaximumVersion 1.0.8

# Get installed module with version range
Get-InstalledModule -Name AzureRM.Automation -MinimumVersion 1.0.0 -MaximumVersion 1.0.8

# Get installed module with RequiredVersion
Get-InstalledScript -Name AzureRM.Automation -RequiredVersion 1.0.3

# Properties of Get-InstalledModule returned object
Get-InstalledModule DJoin | Format-List * -Force

Name                       : DJoin
Version                    : 1.0
Type                       : Module
Description                : This is a PowerShell frontend to the DJOIN.exe command which provides better
                             discoverability and usability.
Author                     : Jeffrey Snover
CompanyName                : jsnover
Copyright                  : (C) Microsoft Corporation. All rights reserved.
PublishedDate              : 2/15/2016 7:12:37 PM
InstalledDate              : 4/5/2016 4:13:39 PM
UpdatedDate                :
LicenseUri                 :
ProjectUri                 :
IconUri                    :
Tags                       : {Nano, PSModule}
Includes                   : {Function, RoleCapability, Command, DscResource...}
PowerShellGetFormatVersion :
ReleaseNotes               :
Dependencies               : {}
RepositorySourceLocation   : https://www.powershellgallery.com/api/v2/
Repository                 : PSGallery
PackageManagementProvider  : NuGet
AdditionalMetadata         : {description, installeddate, tags, PackageManagementProvider...}
InstalledLocation          : C:\Program Files\WindowsPowerShell\Modules\DJoin\1.0

```



<a id="installeddate-and-updateddate-properties-in-psgetrepositoryiteminfo-object" class="xliff"></a>

## PSGetRepositoryItemInfo オブジェクトの InstalledDate および UpdatedDate プロパティ

    During the install operation:
        InstalledDate: current DateTime (Get-Date) value
        UpdatedDate: null

    During the Update operation:
        InstalledDate: InstalledDate from the previous installation otherwise current DateTime (Get-Date) value
        UpdatedDate: current DateTime (Get-Date) value

```powershell
Install-Module -Name ContosoServer -RequiredVersion 1.0 -Repository INT
Get-InstalledModule -Name ContosoServer | Format-Table Name, InstalledDate, UpdatedDate

Name          InstalledDate         UpdatedDate
----          -------------         -----------
ContosoServer 2/29/2016 11:59:14 AM


\Update-Module -Name ContosoServer
Get-InstalledModule -Name ContosoServer | Format-Table Name, InstalledDate, UpdatedDate

Name          InstalledDate         UpdatedDate
----          -------------         -----------
ContosoServer 2/29/2016 11:59:14 AM 2/29/2016 12:00:15 PM
```

