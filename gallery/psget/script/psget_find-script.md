---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,コマンドレット,ギャラリー"
ms.date: 2016-10-14
contributor: manikb
title: psget_find script
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: 5651989acde9d47a7a07fac9284aebae84f28174

---

# Find-Script

指定した条件に一致するオンライン ギャラリーから PowerShell スクリプト ファイルを検索します。

## 説明

Find-Script は、指定した条件に一致する登録されているリポジトリからスクリプト ファイルを検出します。
検出される各スクリプトに対し、Find-Script は、スクリプトをインストールするための Install-Scrip に必要に応じてパイプできる PSRepositoryItemInfo オブジェクトを返します。
Find-Script コマンドレットでは、名前、タグ、フィルター、コマンド名、バージョン範囲、正確なバージョン、すべてのバージョンなどのさまざまな検索条件を使用して、特定またはすべての登録済みリポジトリから、スクリプト ファイルをその依存関係を含めて検出できます。

- Find-Script では、-Command と -Includes の各パラメーターを使用してスクリプトのコンテンツに基づいてフィルター処理できます。
- Find-Script は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、MaximumVersion、RequiredVersion、AllVersions。
  - これらのパラメーターは、MinmimumVersion と MaximumVersion を除いて、同時に使用できません。
  - これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのスクリプト名が指定されている場合にのみ許可されます。
  - RequiredVersion パラメーターが指定されていない場合、Find-Script は指定された最小バージョン以上の最新バージョンのスクリプトを返すか、または最新バージョンのスクリプトを返します (最小バージョンが指定されていない場合)。 
  - RequiredVersion パラメーターが指定されている場合、Find-Script は指定したバージョンに完全に一致するバージョンのスクリプトのみを返します。
- Find-Script では、-Tag パラメーターを使用してスクリプトのメタデータをフィルター処理できます。
- Find-Script では、-Filter パラメーターを使用してリポジトリ固有の検索言語をフィルター処理できます。
- Find-Script では、登録されているリポジトリのすべてまたは一部からスクリプト上でフィルター処理できます。

**注:** 登録されている PSRepository には有効な ScriptSourceLocation が指定されている必要があります。 Set-PSRepository を使用して、ScriptSourceLocation 値を設定できます。

## コマンドレット構文

```powershell
Get-Command -Name Find-Script -Module PowerShellGet -Syntax
```

## コマンドレット オンライン ヘルプ リファレンス

[Find-Script](http://go.microsoft.com/fwlink/?LinkId=619785)

## コマンド例

```powershell
# Find a script from the registered repository with ScriptSourceLocation
Find-Script Connect-AzureVM

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0        Connect-AzureVM                     PSGallery            This runbook sets up a connection to an Azure vi...

# Find multiple scripts
Find-Script -Name Connect-AzureVM, Show-Tree, Connect-O365

# Find scripts with wildcards in -Name
Find-Script -Name *Azure*

# Find all versions of a script
Find-Script -Name Connect-O365 -AllVersions

# Find a script with -MinimumVersion. 
# With MinimumVersion we can find a script whose version is greate than or equal to the specified MinimumVersion value.
Find-Script Connect-O365 -MinimumVersion 1.4

# Find a script with MaximumVersion
Find-Script -Name Connect-O365 -MaximumVersion 1.6.2

# Find a script with both MinimumVersion and MaximumVersion range.
Find-Script -Name Connect-O365 -MinimumVersion 1.1 -MaximumVersion 1.6.2

# Find a script with exact version
Find-Script -Name Connect-O365 -RequiredVersion 1.5.7

# Find a script from the specified repository
Find-Script -Name Fabrikam-ServerScript -Repository MyLocalRepo

# Find available scripts from all registered repositories
Find-Script

# Find available scripts from few registered repositories
Find-Script -Repository PSGallery, PrivatePSGallery

# Find a script along with its dependent modules and scripts
Find-Script -Name Connect-AzureVM -IncludeDependencies

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0        Connect-AzureVM                     PSGallery            This runbook sets up a connection to an Azure vi...
1.4.0      Azure                               PSGallery            Microsoft Azure PowerShell - Service Management
1.1.2      Azure.Storage                       PSGallery            Microsoft Azure PowerShell - Storage service cmd...
1.0.8      AzureRM.profile                     PSGallery            Microsoft Azure PowerShell - Profile credential ...

# Find all scripts with workflows
Find-Script -Includes Workflow

# Find all scripts with functions
Find-Script -Includes Function

# Find scripts with specific commands
Find-Script -Command Log-Message
Find-Script -Command Log-Message, Show-Tree -Includes Function
Find-Script -Command Connect-AzureVM -Includes Workflow

# Find scripts with -Filter based search. -Filter searches in description and names
Find-Script -Filter Windows
Find-Script -Filter Azure

# Find all scripts with tags O365 or Nano
Find-Script -Tag O365, Nano

# Properties of Find-Script returned object
Find-Script Show-Tree | Format-List * -Force
Name                       : Show-Tree
Version                    : 1.0.0
Type                       : Script
Description                : Script to show the layout of PowerShell namespaces (Trees) using ASCII
Author                     : Jeffrey Snover
CompanyName                : jsnover
Copyright                  : (C) Microsoft Corporation. All rights reserved.
PublishedDate              : 2/15/2016 10:15:35 PM
InstalledDate              :
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
AdditionalMetadata         : {versionDownloadCount, ItemType, copyright, PackageManagementProvider...}


# Includes property on PSRepositoryItemInfo object
$t = Find-Script -Includes Workflow -Repository INT -Name Fabrikam-ClientScript
$t.Includes

Name                           Value
----                           -----
Function                       {Test-FunctionFromScript_Fabrikam-ClientScript}
RoleCapability                 {}
Command                        {Test-FunctionFromScript_Fabrikam-ClientScript, Test-WorkflowFromScript_Fabrikam-Clie...
DscResource                    {}
Workflow                       {Test-WorkflowFromScript_Fabrikam-ClientScript}
Cmdlet                         {}


```




<!--HONumber=Oct16_HO2-->


