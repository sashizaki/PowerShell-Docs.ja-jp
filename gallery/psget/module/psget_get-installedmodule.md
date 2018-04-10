---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: Get-InstalledModule
ms.openlocfilehash: f82d8f3b6b6a9283deef44c2705b97d4717b634c
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="get-installedmodule"></a><span data-ttu-id="4f8e9-103">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="4f8e9-103">Get-InstalledModule</span></span>

<span data-ttu-id="4f8e9-104">コンピューター上のインストールされているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="4f8e9-104">Gets installed modules on a computer.</span></span>

## <a name="description"></a><span data-ttu-id="4f8e9-105">説明</span><span class="sxs-lookup"><span data-stu-id="4f8e9-105">Description</span></span>

<span data-ttu-id="4f8e9-106">Get-InstalledModule コマンドレットは、Install-Module コマンドレットを使用してインストールされたコンピューター上にインストールされている PowerShell モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="4f8e9-106">The Get-InstalledModule cmdlet gets installed PowerShell modules on a computer which were installed using Install-Module cmdlet.</span></span>

<span data-ttu-id="4f8e9-107">インストールされている各モジュールに対し、Get-InstalledModule は、インストールされているモジュールをアンインストールするための Uninstall-Module に必要に応じてパイプできる PSRepositoryItemInfo オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4f8e9-107">For each installed module, Get-InstalledModule returns a PSRepositoryItemInfo object which can optionally be piped to Uninstall-Module for uninstalling the installed modules.</span></span>

- <span data-ttu-id="4f8e9-108">Get-InstalledModule は、名前、バージョン パラメーターに基づいてインストールされているモジュールをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4f8e9-108">Get-InstalledModule can filter installed modules based on name, version parameters.</span></span>
- <span data-ttu-id="4f8e9-109">Get-InstalledModule は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、MaximumVersion、RequiredVersion、AllVersions。</span><span class="sxs-lookup"><span data-stu-id="4f8e9-109">Get-InstalledModule can filter with version parameters: MinimumVersion, MaximumVersion, RequiredVersion, AllVersions.</span></span>
  - <span data-ttu-id="4f8e9-110">これらのパラメーターは、MinmimumVersion と MaximumVersion を除いて、同時に使用できません。</span><span class="sxs-lookup"><span data-stu-id="4f8e9-110">These parameters are mutually exclusive, except MinmimumVersion and MaximumVersion.</span></span>
  - <span data-ttu-id="4f8e9-111">これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのモジュール名が指定されている場合にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="4f8e9-111">These version parameters are allowed only with the single module name without any wildcards.</span></span>
  - <span data-ttu-id="4f8e9-112">RequiredVersion パラメーターが指定されていない場合、Get-InstalledModule は指定された最小バージョン以上の最新バージョンのインストールされているモジュールを返すか、または最新バージョンのモジュールを返します (最小バージョンが指定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="4f8e9-112">If the RequiredVersion parameter is not specified, Get-InstalledModule returns the latest version of the installed module that is equal to or greater than the minimum version specified or the latest version of the module if no minimum version is specified.</span></span>
  - <span data-ttu-id="4f8e9-113">RequiredVersion パラメーターが指定されている場合、Get-InstalledModule は指定したバージョンに完全に一致するバージョンのインストールされているモジュールのみを返します。</span><span class="sxs-lookup"><span data-stu-id="4f8e9-113">If the RequiredVersion parameter is specified, Get-InstalledModule only returns the version of installed module that exactly matches the specified version.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="4f8e9-114">コマンドレット構文</span><span class="sxs-lookup"><span data-stu-id="4f8e9-114">Cmdlet syntax</span></span>
```powershell
Get-Command -Name Get-InstalledModule -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="4f8e9-115">コマンドレット オンライン ヘルプ リファレンス</span><span class="sxs-lookup"><span data-stu-id="4f8e9-115">Cmdlet online help reference</span></span>

[<span data-ttu-id="4f8e9-116">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="4f8e9-116">Get-InstalledModule</span></span>](http://go.microsoft.com/fwlink/?LinkId=526863)

## <a name="example-commands"></a><span data-ttu-id="4f8e9-117">コマンド例</span><span class="sxs-lookup"><span data-stu-id="4f8e9-117">Example commands</span></span>

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



## <a name="installeddate-and-updateddate-properties-in-psgetrepositoryiteminfo-object"></a><span data-ttu-id="4f8e9-118">PSGetRepositoryItemInfo オブジェクトの InstalledDate および UpdatedDate プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f8e9-118">InstalledDate and UpdatedDate properties in PSGetRepositoryItemInfo object</span></span>

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