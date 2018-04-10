---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: Find-Script
ms.openlocfilehash: 1f5076d94015c0b1041591144f1f0fe36819204b
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="find-script"></a><span data-ttu-id="ce51b-103">Find-Script</span><span class="sxs-lookup"><span data-stu-id="ce51b-103">Find-Script</span></span>

<span data-ttu-id="ce51b-104">指定した条件に一致するオンライン ギャラリーから PowerShell スクリプト ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="ce51b-104">Finds the PowerShell script files from an online gallery that match specified criteria.</span></span>

## <a name="description"></a><span data-ttu-id="ce51b-105">説明</span><span class="sxs-lookup"><span data-stu-id="ce51b-105">Description</span></span>

<span data-ttu-id="ce51b-106">Find-Script は、指定した条件に一致する登録されているリポジトリからスクリプト ファイルを検出します。</span><span class="sxs-lookup"><span data-stu-id="ce51b-106">Find-Script discovers the script files from registered repositories that matches the specified criteria.</span></span>
<span data-ttu-id="ce51b-107">検出される各スクリプトに対し、Find-Script は、スクリプトをインストールするための Install-Scrip に必要に応じてパイプできる PSRepositoryItemInfo オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ce51b-107">For each script found, Find-Script returns a PSRepositoryItemInfo object which can optionally be piped to Install-Script for installing the scripts.</span></span>
<span data-ttu-id="ce51b-108">Find-Script コマンドレットでは、名前、タグ、フィルター、コマンド名、バージョン範囲、正確なバージョン、すべてのバージョンなどのさまざまな検索条件を使用して、特定またはすべての登録済みリポジトリから、スクリプト ファイルをその依存関係を含めて検出できます。</span><span class="sxs-lookup"><span data-stu-id="ce51b-108">Find-Script cmdlet lets you to discover the script files with different search criteria like name, tag, filter, command name, version range, exact version, all versions, including its dependencies and from specific or all registered repositories.</span></span>

- <span data-ttu-id="ce51b-109">Find-Script では、-Command と -Includes の各パラメーターを使用してスクリプトのコンテンツに基づいてフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="ce51b-109">Find-Script can filter based on script contents with the -Command and -Includes parameters.</span></span>
- <span data-ttu-id="ce51b-110">Find-Script は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、MaximumVersion、RequiredVersion、AllVersions。</span><span class="sxs-lookup"><span data-stu-id="ce51b-110">Find-Script can filter with version parameters: MinimumVersion, MaximumVersion, RequiredVersion, AllVersions.</span></span>
  - <span data-ttu-id="ce51b-111">これらのパラメーターは、MinmimumVersion と MaximumVersion を除いて、同時に使用できません。</span><span class="sxs-lookup"><span data-stu-id="ce51b-111">These parameters are mutually exclusive, except MinmimumVersion and MaximumVersion.</span></span>
  - <span data-ttu-id="ce51b-112">これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのスクリプト名が指定されている場合にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="ce51b-112">These version parameters are allowed only with the single script name without any wildcards.</span></span>
  - <span data-ttu-id="ce51b-113">RequiredVersion パラメーターが指定されていない場合、Find-Script は指定された最小バージョン以上の最新バージョンのスクリプトを返すか、または最新バージョンのスクリプトを返します (最小バージョンが指定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="ce51b-113">If the RequiredVersion parameter is not specified, Find-Script returns the latest version of the script that is equal to or greater than the minimum version specified or the latest version of the script if no minimum version is specified.</span></span>
  - <span data-ttu-id="ce51b-114">RequiredVersion パラメーターが指定されている場合、Find-Script は指定したバージョンに完全に一致するバージョンのスクリプトのみを返します。</span><span class="sxs-lookup"><span data-stu-id="ce51b-114">If the RequiredVersion parameter is specified, Find-Script only returns the version of script that exactly matches the specified version.</span></span>
- <span data-ttu-id="ce51b-115">Find-Script では、-Tag パラメーターを使用してスクリプトのメタデータをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="ce51b-115">Find-Script can filter on script metadata with the -Tag parameter.</span></span>
- <span data-ttu-id="ce51b-116">Find-Script では、-Filter パラメーターを使用してリポジトリ固有の検索言語をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="ce51b-116">Find-Script can filter on repository-specific search language with the -Filter parameter.</span></span>
- <span data-ttu-id="ce51b-117">Find-Script では、登録されているリポジトリのすべてまたは一部からスクリプト上でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="ce51b-117">Find-Script can filter on scripts from all or few of the registered repositories.</span></span>

<span data-ttu-id="ce51b-118">**注:** 登録されている PSRepository には有効な ScriptSourceLocation が指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce51b-118">**NOTE:** Registered PSRepository should have a valid ScriptSourceLocation.</span></span> <span data-ttu-id="ce51b-119">Set-PSRepository を使用して、ScriptSourceLocation 値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ce51b-119">You can use the Set-PSRepository to set ScriptSourceLocation value.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="ce51b-120">コマンドレット構文</span><span class="sxs-lookup"><span data-stu-id="ce51b-120">Cmdlet syntax</span></span>

```powershell
Get-Command -Name Find-Script -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="ce51b-121">コマンドレット オンライン ヘルプ リファレンス</span><span class="sxs-lookup"><span data-stu-id="ce51b-121">Cmdlet online help reference</span></span>

[<span data-ttu-id="ce51b-122">Find-Script</span><span class="sxs-lookup"><span data-stu-id="ce51b-122">Find-Script</span></span>](http://go.microsoft.com/fwlink/?LinkId=619785)

## <a name="example-commands"></a><span data-ttu-id="ce51b-123">コマンド例</span><span class="sxs-lookup"><span data-stu-id="ce51b-123">Example commands</span></span>

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

# Find a script with a specific pre-release version
Find-Script -Name Connect-O365 -RequiredVersion 1.3.2-alpha -AllowPrerelease

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