---
ms.date: 10/17/2017
contributor: keithb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: プレリリース バージョンのスクリプト
ms.openlocfilehash: c0198c2f575d2c004949ccebab49d93ce54716be
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084642"
---
# <a name="prerelease-versions-of-scripts"></a><span data-ttu-id="a3224-103">プレリリース バージョンのスクリプト</span><span class="sxs-lookup"><span data-stu-id="a3224-103">Prerelease versions of scripts</span></span>

<span data-ttu-id="a3224-104">バージョン 1.6.0 より、PowerShellGet および PowerShell ギャラリーで 1.0.0 以降のバージョンをプレリリースとしてタグ付けできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a3224-104">Starting with version 1.6.0, PowerShellGet and the PowerShell Gallery provide support for tagging versions greater than 1.0.0 as a prerelease.</span></span> <span data-ttu-id="a3224-105">この機能より前では、プレリリース パッケージは 0 で始まるバージョンに制限されていました。</span><span class="sxs-lookup"><span data-stu-id="a3224-105">Prior to this feature, prerelease packages were limited to having a version beginning with 0.</span></span> <span data-ttu-id="a3224-106">この機能の目的は、PowerShell バージョン 3 以降、または既存のバージョンの PowerShellGet との後方互換性を失わずに [SemVer v1.0.0](http://semver.org/spec/v1.0.0.html) のバージョン管理規則に対してより優れたサポートを提供することです。</span><span class="sxs-lookup"><span data-stu-id="a3224-106">The goal of these features is to provide greater support for [SemVer v1.0.0](http://semver.org/spec/v1.0.0.html) versioning convention without breaking backwards compatibility with PowerShell versions 3 and above, or existing versions of PowerShellGet.</span></span> <span data-ttu-id="a3224-107">このトピックでは、スクリプトに固有の機能に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="a3224-107">This topic focuses on the script-specific features.</span></span> <span data-ttu-id="a3224-108">モジュールの同等の機能は、「[Prerelease Module Versions](module-prerelease-support.md)」(プレリリース モジュールのバージョン) のトピックにあります。</span><span class="sxs-lookup"><span data-stu-id="a3224-108">The equivalent features for modules are in the [Prerelease Module Versions](module-prerelease-support.md) topic.</span></span> <span data-ttu-id="a3224-109">これらの機能を使用して、パブリッシャーはスクリプトをバージョン 2.5.0-alpha と識別し、プレリリース バージョンより優先される実稼働可能なバージョン 2.5.0 を後からリリースすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3224-109">Using these features, publishers can identify a script as version 2.5.0-alpha, and later release a production-ready version 2.5.0 that supersedes the prerelease version.</span></span>

<span data-ttu-id="a3224-110">大まかには、プレリリースのスクリプト機能には次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="a3224-110">At a high level, the prerelease script features include:</span></span>

- <span data-ttu-id="a3224-111">スクリプト マニフェストのバージョン文字列に PrereleaseString サフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a3224-111">Adding a PrereleaseString suffix to the version string in the script manifest.</span></span> <span data-ttu-id="a3224-112">スクリプトが PowerShell ギャラリーに発行されると、このデータがマニフェストから抽出され、プレリリース パッケージを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3224-112">When the scripts is published to the PowerShell Gallery, this data is extracted from the manifest, and used to identify prerelease packages.</span></span>
- <span data-ttu-id="a3224-113">プレリリース パッケージを取得するには、-AllowPrerelease フラグを Find-Script、Install-Script、Update-Script、Save-Script の PowerShellGet コマンドに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3224-113">Acquiring prerelease packages requires adding -AllowPrerelease flag to the PowerShellGet commands Find-Script, Install-Script, Update-Script, and Save-Script.</span></span> <span data-ttu-id="a3224-114">フラグが指定されていないと、プレリリース パッケージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="a3224-114">If the flag is not specified, prerelease packages will not be shown.</span></span>
- <span data-ttu-id="a3224-115">Find-Script、Get-InstalledScript、および PowerShell ギャラリーに表示されるスクリプト バージョンには 2.5.0-alpha のように PrereleaseString が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3224-115">Script versions displayed by Find-Script, Get-InstalledScript, and in the PowerShell Gallery will be displayed with the PrereleaseString, as in 2.5.0-alpha.</span></span>

<span data-ttu-id="a3224-116">この機能の詳細については後述します。</span><span class="sxs-lookup"><span data-stu-id="a3224-116">Details for the features are included below.</span></span>

## <a name="identifying-a-script-version-as-a-prerelease"></a><span data-ttu-id="a3224-117">スクリプト バージョンをプレリリースとして識別する</span><span class="sxs-lookup"><span data-stu-id="a3224-117">Identifying a script version as a prerelease</span></span>

<span data-ttu-id="a3224-118">プレリリース バージョンに対する PowerShellGet のサポートは、モジュールよりもスクリプトの方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="a3224-118">PowerShellGet support for prerelease versions is easier for scripts than modules.</span></span> <span data-ttu-id="a3224-119">スクリプトのバージョン管理は PowerShellGet でのみサポートされているため、Prerelease 文字列の追加によって生じる互換性の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="a3224-119">Script versioning is only supported by PowerShellGet, so there are no compatibility issues caused by adding the prerelease string.</span></span> <span data-ttu-id="a3224-120">PowerShell ギャラリーのスクリプトをプレリリースとして識別するには、スクリプトのメタデータの適切に書式設定されたバージョン文字列にプレリリースのサフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a3224-120">To identify a script in the PowerShell Gallery as a prerelease, add a prerelease suffix to a properly-formatted version string in the script metadata.</span></span>

<span data-ttu-id="a3224-121">プレリリース バージョンのスクリプト マニフェストの例のセクションは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a3224-121">An example section of a script manifest with a prerelease version would look like the following:</span></span>

```powershell
<#PSScriptInfo

.VERSION 3.2.1-alpha12

.GUID

...

#>
```

<span data-ttu-id="a3224-122">プレリリースのサフィックスを使用するには、バージョン文字列が次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3224-122">To use a prerelease suffix, the version string must meet the following requirements:</span></span>

- <span data-ttu-id="a3224-123">プレリリースのサフィックスは、Major.Minor.Build の Version が 3 セグメントである場合にのみ指定できます</span><span class="sxs-lookup"><span data-stu-id="a3224-123">A prerelease suffix may only be specified when the Version is 3 segments for Major.Minor.Build.</span></span>
  <span data-ttu-id="a3224-124">これは、SemVer v1.0.0 と適合します</span><span class="sxs-lookup"><span data-stu-id="a3224-124">This aligns with SemVer v1.0.0</span></span>
- <span data-ttu-id="a3224-125">プレリリースのサフィックスはハイフンで始まる文字列で、ASCII 英数字 [0-9A-Za-z-] を含めることができます</span><span class="sxs-lookup"><span data-stu-id="a3224-125">The prerelease suffix is a string which begins with a hyphen, and may contain ASCII alphanumerics [0-9A-Za-z-]</span></span>
- <span data-ttu-id="a3224-126">現時点では、SemVer v1.0.0 の Prerelease 文字列のみがサポートされているため、プレリリースのサフィックスに (SemVer 2.0 では許可されている) ピリオドまたは + [.+] のどちらかを含めることは**できません**</span><span class="sxs-lookup"><span data-stu-id="a3224-126">Only SemVer v1.0.0 prerelease strings are supported at this time, so the prerelease suffix **must not** contain either period or + [.+], which are allowed in SemVer 2.0</span></span>
- <span data-ttu-id="a3224-127">サポートされている PrereleaseString 文字列には、-alpha、-alpha1、-BETA、-update20171020 などがあります</span><span class="sxs-lookup"><span data-stu-id="a3224-127">Examples of supported PrereleaseString strings are: -alpha, -alpha1, -BETA, -update20171020</span></span>

### <a name="prerelease-versioning-impact-on-sort-order-and-installation-folders"></a><span data-ttu-id="a3224-128">並べ替え順序およびインストール フォルダーへのプレリリース バージョン管理の影響</span><span class="sxs-lookup"><span data-stu-id="a3224-128">Prerelease versioning impact on sort order and installation folders</span></span>

<span data-ttu-id="a3224-129">並べ替え順序は、PowerShell ギャラリーへの発行時に重要なプレリリース バージョンを使用するときや、PowerShellGet コマンドを使用してスクリプトをインストールするときに変更されます。</span><span class="sxs-lookup"><span data-stu-id="a3224-129">Sort order changes when using a prerelease version, which is important when publishing to the PowerShell Gallery, and when installing scripts using PowerShellGet commands.</span></span> <span data-ttu-id="a3224-130">バージョン番号を含む 2 つのスクリプトのバージョンが存在する場合、並べ替え順序はハイフンの後の文字列部分に基づきます。</span><span class="sxs-lookup"><span data-stu-id="a3224-130">If two scripts versions with the version number exist, the sort order is based on the string portion following the hyphen.</span></span> <span data-ttu-id="a3224-131">そのため、バージョン 2.5.0-alpha は 2.5.0-beta より小さく、2.5.0-beta は 2.5.0-gamma より小さくなります。</span><span class="sxs-lookup"><span data-stu-id="a3224-131">So, version 2.5.0-alpha is less than 2.5.0-beta, which is less than 2.5.0-gamma.</span></span> <span data-ttu-id="a3224-132">2 つのスクリプトに同じバージョン番号が含まれ、うち 1 つにのみ PrereleaseString が含まれる場合は、プレリリースのサフィックスの**ない**スクリプトが実稼働可能なバージョンと見なされ、プレリリース バージョンより後のバージョンとして並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="a3224-132">If two scripts have the same version number, and only one has a PrereleaseString, the script **without** the prerelease suffix is assumed to be the production-ready version and will be sorted as a greater version than the prerelease version.</span></span> <span data-ttu-id="a3224-133">たとえば、2.5.0 と 2.5.0-beta を比較すると、2.5.0 バージョンの方が後だと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a3224-133">As an example, when comparing releases 2.5.0 and 2.5.0-beta, the 2.5.0 version will be considered the greater of the two.</span></span>

<span data-ttu-id="a3224-134">PowerShell ギャラリーに発行すると、既定により、発行されているスクリプトのバージョンが必ず PowerShell ギャラリーにある以前に発行されているバージョンよりも後のバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="a3224-134">When publishing to the PowerShell Gallery, by default the version of the script being published must have a greater version than any previously-published version that is in the PowerShell Gallery.</span></span> <span data-ttu-id="a3224-135">パブリッシャーは 2.5.0-alpha のバージョンを 2.5.0-beta、または 2.5.0 (プレリリースのサフィックスなし) に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="a3224-135">A publisher may update version 2.5.0-alpha with 2.5.0-beta, or with 2.5.0 (with no prerelease suffix).</span></span>

## <a name="finding-and-acquiring-prerelease-packages-using-powershellget-commands"></a><span data-ttu-id="a3224-136">PowerShellGet コマンドを使用してプレリリース パッケージを検索および取得する</span><span class="sxs-lookup"><span data-stu-id="a3224-136">Finding and acquiring prerelease packages using PowerShellGet commands</span></span>

<span data-ttu-id="a3224-137">Find-Script、Install-Script、Update-Script、Save-Script の PowerShellGet コマンドを使用してプレリリース パッケージを操作するには、-AllowPrerelease フラグを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3224-137">Dealing with prerelease packages using PowerShellGet Find-Script, Install-Script, Update-Script, and Save-Script commands requires adding the -AllowPrerelease flag.</span></span> <span data-ttu-id="a3224-138">-AllowPrerelease が指定されていると、プレリリース パッケージが存在する場合にはそのパッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3224-138">If -AllowPrerelease is specified, prerelease packages will be included if they are present.</span></span> <span data-ttu-id="a3224-139">-AllowPrerelease フラグが指定されていないと、プレリリース パッケージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="a3224-139">If -AllowPrerelease flag is not specified, prerelease packages will not be shown.</span></span>

<span data-ttu-id="a3224-140">PowerShellGet スクリプトのコマンドで、これに対する例外が Get-InstalledScript です。場合によっては Uninstall-Script も含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3224-140">The only exceptions to this in the PowerShellGet script commands are Get-InstalledScript, and some cases with Uninstall-Script.</span></span>

- <span data-ttu-id="a3224-141">Get-InstalledScript はバージョン文字列にプレリリース情報がある場合に、常に自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="a3224-141">Get-InstalledScript always will automatically show the prerelease information in the version string if it is present.</span></span>
- <span data-ttu-id="a3224-142">Uninstall-Script は**バージョンが指定されていない**場合に、既定でスクリプトの最新のバージョンをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a3224-142">Uninstall-Script will by default uninstall the most recent version of a script, if **no version** is specified.</span></span> <span data-ttu-id="a3224-143">この動作は変更されていません。</span><span class="sxs-lookup"><span data-stu-id="a3224-143">That behavior has not changed.</span></span> <span data-ttu-id="a3224-144">ただし、`-RequiredVersion` を使用してプレリリース バージョンが指定された場合は、`-AllowPrerelease` が必要になります。</span><span class="sxs-lookup"><span data-stu-id="a3224-144">However, if a prerelease version is specified using `-RequiredVersion`, `-AllowPrerelease` will be required.</span></span>

## <a name="examples"></a><span data-ttu-id="a3224-145">例</span><span class="sxs-lookup"><span data-stu-id="a3224-145">Examples</span></span>

```powershell
# Assume the PowerShell Gallery has TestPackage versions 1.8.0 and 1.9.0-alpha.
# If -AllowPrerelease is not specified, only version 1.8.0 will be returned.
C:\windows\system32> Find-Script TestPackage

Version        Name                                Repository           Description
-------        ----                                ----------           -----------
1.8.0          TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

C:\windows\system32> Find-Script TestPackage -AllowPrerelease

Version        Name                                Repository           Description
-------        ----                                ----------           -----------
1.9.0-alpha    TestPackage                         PSGallery            Package used to validate changes to PowerShe...

# To install a prerelease, you must specify -AllowPrerelease. Specifying a prerelease version string is not sufficient.

C:\windows\system32> Install-Script TestPackage -RequiredVersion 1.9.0-alpha

PackageManagement\Find-Package : No match was found for the specified search criteria and script name 'TestPackage'.
Try Get-PSRepository to see all available registered script repositories.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PSModule.psm1:1455 char:3
+         PackageManagement\Find-Package @PSBoundParameters | Microsoft ...
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Microsoft.Power...ets.FindPackage:FindPackage)[Find-Package], Exception
    + FullyQualifiedErrorId : NoMatchFoundForCriteria,Microsoft.PowerShell.PackageManagement.Cmdlets.FindPackage

# The previous command failed because -AllowPrerelease was not specified.
# Adding -AllowPrerelease will result in success.

C:\windows\system32> Install-Script TestPackage -RequiredVersion 1.9.0-alpha -AllowPrerelease
C:\windows\system32> Get-InstalledScript TestPackage

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.9.0-alpha     TestPackage                         PSGallery            Package used to validate changes to PowerShe...

# Note that Get-InstalledScript shows the prerelease version.
# If -RequiredVersion is not specified, all installed scripts will be displayed by Get-InstalledScript
```

<span data-ttu-id="a3224-146">-RequiredVersion が指定されていない場合、Uninstall-Script によってスクリプトの最新バージョンが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a3224-146">Uninstall-Script will remove the current version of a script when -RequiredVersion is not supplied.</span></span>
<span data-ttu-id="a3224-147">-RequiredVersion が指定されていて、これがプレリリースである場合、-AllowPrerelease をコマンドに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3224-147">If -RequiredVersion is specified, and is a prerelease, -AllowPrerelease must be added to the command.</span></span>

``` powershell
C:\windows\system32> Get-InstalledScript TestPackage

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.9.0-alpha     TestPackage                         PSGallery            Package used to validate changes to PowerShe...

C:\windows\system32> Uninstall-Script TestPackage -RequiredVersion 1.9.0-alpha
Uninstall-Script: The '-AllowPrerelease' parameter must be specified when using the Prerelease string in
MinimumVersion, MaximumVersion, or RequiredVersion.
At line:1 char:1
+ Uninstall-Script TestPackage -RequiredVersion 1.9.0-beta
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Uninstall-Script], ArgumentException
    + FullyQualifiedErrorId : AllowPrereleaseRequiredToUsePrereleaseStringInVersion,Uninstall-script


C:\windows\system32> Uninstall-Script TestPackage -RequiredVersion 1.9.0-alpha -AllowPrerelease
# Since script versions are not installed side-by-side, the above could be simply "Uninstall-Script TestPackage"

C:\windows\system32> Get-Installedscript TestPackage
PackageManagement\Get-Package : No match was found for the specified search criteria and script names 'testpackage'.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.5.0.0\PSModule.psm1:4088 char:9
+         PackageManagement\Get-Package @PSBoundParameters | Microsoft. ...
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Microsoft.Power...lets.GetPackage:GetPackage) [Get-Package], Exception
    + FullyQualifiedErrorId : NoMatchFound,Microsoft.PowerShell.PackageManagement.Cmdlets.GetPackage
```

## <a name="more-details"></a><span data-ttu-id="a3224-148">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a3224-148">More details</span></span>

- [<span data-ttu-id="a3224-149">プレリリース モジュールのバージョン</span><span class="sxs-lookup"><span data-stu-id="a3224-149">Prerelease Module Versions</span></span>](module-prerelease-support.md)
- [<span data-ttu-id="a3224-150">Find-script</span><span class="sxs-lookup"><span data-stu-id="a3224-150">Find-script</span></span>](/powershell/module/powershellget/find-script)
- [<span data-ttu-id="a3224-151">Install-script</span><span class="sxs-lookup"><span data-stu-id="a3224-151">Install-script</span></span>](/powershell/module/powershellget/install-script)
- [<span data-ttu-id="a3224-152">Save-script</span><span class="sxs-lookup"><span data-stu-id="a3224-152">Save-script</span></span>](/powershell/module/powershellget/save-script)
- [<span data-ttu-id="a3224-153">Update-script</span><span class="sxs-lookup"><span data-stu-id="a3224-153">Update-script</span></span>](/powershell/module/powershellget/update-script)
- [<span data-ttu-id="a3224-154">Get-Installedscript</span><span class="sxs-lookup"><span data-stu-id="a3224-154">Get-Installedscript</span></span>](/powershell/module/powershellget/get-installedscript)
- [<span data-ttu-id="a3224-155">Uninstall-script</span><span class="sxs-lookup"><span data-stu-id="a3224-155">UnInstall-script</span></span>](/powershell/module/powershellget/uninstall-script)
