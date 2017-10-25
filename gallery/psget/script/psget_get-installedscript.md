---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: Get-InstalledScript
ms.openlocfilehash: f35e57cdadd1448bd9032ab007d692003c4cf4a2
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="get-installedscript"></a>Get-InstalledScript

コンピューター上のインストールされているスクリプトを取得します。

## <a name="description"></a>説明

Get-InstalledScript コマンドレットは、コンピューター上にインストールされている PowerShell スクリプトを取得します。

インストールされている各スクリプトに対し、Get-InstalledScript は、インストールされているスクリプトをアンインストールするための Uninstall-Script に必要に応じてパイプできる PSRepositoryItemInfo オブジェクトを返します。

- Get-InstalledScript は、名前、バージョン パラメーターに基づいてインストールされているスクリプトをフィルター処理できます。
- Get-InstalledScript は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、MaximumVersion、RequiredVersion、AllVersions。
  - これらのパラメーターは、MinmimumVersion と MaximumVersion を除いて、同時に使用できません。
  - これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのスクリプト名が指定されている場合にのみ許可されます。
  - RequiredVersion パラメーターが指定されていない場合、Get-InstalledScript は指定された最小バージョン以上の最新バージョンのインストールされているスクリプトを返すか、または最新バージョンのスクリプトを返します (最小バージョンが指定されていない場合)。 
  - RequiredVersion パラメーターが指定されている場合、Get-InstalledScript は指定したバージョンに完全に一致するバージョンのインストールされているスクリプトのみを返します。

## <a name="cmdlet-syntax"></a>コマンドレット構文

```powershell
Get-Command -Name Get-InstalledScript -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a>コマンドレット オンライン ヘルプ リファレンス

[Get-InstalledScript](http://go.microsoft.com/fwlink/?LinkId=619790)

## <a name="example-commands"></a>コマンド例

```powershell

# Get all scripts installed using PowerShellGet cmdlets
Get-InstalledScript

# Get a specific installed script
Get-InstalledScript Show-Tree

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0.0      Show-Tree                           PSGallery            Script to show the layout of PowerShell namespaces (Tr...

# Get installed script with wildcards
Get-InstalledScript -Name *Azure*

# Get all versions of an installed script
Get-InstalledScript -Name Connect-O365 -AllVersions

# Get installed script with MinimumVersion
Get-InstalledScript -Name Connect-O365 -MinimumVersion 1.1

# Get installed script with MaximumVersion
Get-InstalledScript -Name Connect-O365 -MaximumVersion 1.6.3

# Get installed script with version range
Get-InstalledScript -Name Connect-O365 -MinimumVersion 1.1 -MaximumVersion 1.6.3

# Get installed script with RequiredVersion
Get-InstalledScript -Name Connect-O365 -RequiredVersion 1.4

# Properties of Get-InstalledScript returned object
Get-InstalledScript Show-Tree | Format-List * -Force

Name                       : Show-Tree
Version                    : 1.0.0
Type                       : Script
Description                : Script to show the layout of PowerShell namespaces (Trees) using ASCII
Author                     : Jeffrey Snover
CompanyName                : jsnover
Copyright                  : (C) Microsoft Corporation. All rights reserved.
PublishedDate              : 2/15/2016 10:15:35 PM
InstalledDate              : 5/4/2016 11:44:13 PM
UpdatedDate                :
LicenseUri                 :
ProjectUri                 :
IconUri                    :
Tags                       : {Nano, PSScript}
Includes                   : {Function, RoleCapability, Command, DscResource...}
PowerShellGetFormatVersion :
ReleaseNotes               :
Dependencies               : {}
RepositorySourceLocation   : https://www.powershellgallery.com/api/v2/
Repository                 : PSGallery
PackageManagementProvider  : NuGet
AdditionalMetadata         : {description, installeddate, tags, PackageManagementProvider...}
InstalledLocation          : C:\Program Files\WindowsPowerShell\Scripts


```

