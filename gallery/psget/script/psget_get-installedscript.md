---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: Get-InstalledScript
ms.openlocfilehash: 668327905b0dab40119940a3134b674c452f538d
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="get-installedscript"></a><span data-ttu-id="eeba3-103">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="eeba3-103">Get-InstalledScript</span></span>

<span data-ttu-id="eeba3-104">コンピューター上のインストールされているスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="eeba3-104">Gets installed scripts on a computer.</span></span>

## <a name="description"></a><span data-ttu-id="eeba3-105">説明</span><span class="sxs-lookup"><span data-stu-id="eeba3-105">Description</span></span>

<span data-ttu-id="eeba3-106">Get-InstalledScript コマンドレットは、コンピューター上にインストールされている PowerShell スクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="eeba3-106">The Get-InstalledScript cmdlet gets installed PowerShell scripts on a computer.</span></span>

<span data-ttu-id="eeba3-107">インストールされている各スクリプトに対し、Get-InstalledScript は、インストールされているスクリプトをアンインストールするための Uninstall-Script に必要に応じてパイプできる PSRepositoryItemInfo オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="eeba3-107">For each installed script, Get-InstalledScript returns a PSRepositoryItemInfo object which can optionally be piped to Uninstall-Script for uninstalling the installed scripts.</span></span>

- <span data-ttu-id="eeba3-108">Get-InstalledScript は、名前、バージョン パラメーターに基づいてインストールされているスクリプトをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="eeba3-108">Get-InstalledScript can filter installed scripts based on name, version parameters.</span></span>
- <span data-ttu-id="eeba3-109">Get-InstalledScript は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、MaximumVersion、RequiredVersion、AllVersions。</span><span class="sxs-lookup"><span data-stu-id="eeba3-109">Get-InstalledScript can filter with version parameters: MinimumVersion, MaximumVersion, RequiredVersion, AllVersions.</span></span>
  - <span data-ttu-id="eeba3-110">これらのパラメーターは、MinmimumVersion と MaximumVersion を除いて、同時に使用できません。</span><span class="sxs-lookup"><span data-stu-id="eeba3-110">These parameters are mutually exclusive, except MinmimumVersion and MaximumVersion.</span></span>
  - <span data-ttu-id="eeba3-111">これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのスクリプト名が指定されている場合にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="eeba3-111">These version parameters are allowed only with the single script name without any wildcards.</span></span>
  - <span data-ttu-id="eeba3-112">RequiredVersion パラメーターが指定されていない場合、Get-InstalledScript は指定された最小バージョン以上の最新バージョンのインストールされているスクリプトを返すか、または最新バージョンのスクリプトを返します (最小バージョンが指定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="eeba3-112">If the RequiredVersion parameter is not specified, Get-InstalledScript returns the latest version of the installed script that is equal to or greater than the minimum version specified or the latest version of the script if no minimum version is specified.</span></span>
  - <span data-ttu-id="eeba3-113">RequiredVersion パラメーターが指定されている場合、Get-InstalledScript は指定したバージョンに完全に一致するバージョンのインストールされているスクリプトのみを返します。</span><span class="sxs-lookup"><span data-stu-id="eeba3-113">If the RequiredVersion parameter is specified, Get-InstalledScript only returns the version of installed script that exactly matches the specified version.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="eeba3-114">コマンドレット構文</span><span class="sxs-lookup"><span data-stu-id="eeba3-114">Cmdlet syntax</span></span>

```powershell
Get-Command -Name Get-InstalledScript -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="eeba3-115">コマンドレット オンライン ヘルプ リファレンス</span><span class="sxs-lookup"><span data-stu-id="eeba3-115">Cmdlet online help reference</span></span>

[<span data-ttu-id="eeba3-116">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="eeba3-116">Get-InstalledScript</span></span>](http://go.microsoft.com/fwlink/?LinkId=619790)

## <a name="example-commands"></a><span data-ttu-id="eeba3-117">コマンド例</span><span class="sxs-lookup"><span data-stu-id="eeba3-117">Example commands</span></span>

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