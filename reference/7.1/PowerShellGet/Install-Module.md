---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: 463853778b6f2892ae36d55dcd4d886727b1dd51
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892489"
---
# <span data-ttu-id="38f87-103">Install-Module</span><span class="sxs-lookup"><span data-stu-id="38f87-103">Install-Module</span></span>

## <span data-ttu-id="38f87-104">概要</span><span class="sxs-lookup"><span data-stu-id="38f87-104">SYNOPSIS</span></span>
<span data-ttu-id="38f87-105">1つ以上のモジュールをリポジトリからダウンロードし、ローカルコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="38f87-105">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

## <span data-ttu-id="38f87-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="38f87-106">SYNTAX</span></span>

### <span data-ttu-id="38f87-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="38f87-107">NameParameterSet (Default)</span></span>

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="38f87-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="38f87-108">InputObject</span></span>

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="38f87-109">Description</span><span class="sxs-lookup"><span data-stu-id="38f87-109">DESCRIPTION</span></span>

<span data-ttu-id="38f87-110">`Install-Module`コマンドレットは、指定された条件を満たす1つ以上のモジュールをオンラインリポジトリから取得します。</span><span class="sxs-lookup"><span data-stu-id="38f87-110">The `Install-Module` cmdlet gets one or more modules that meet specified criteria from an online repository.</span></span> <span data-ttu-id="38f87-111">コマンドレットでは、検索結果が有効なモジュールであることを確認し、モジュールフォルダーをインストール場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="38f87-111">The cmdlet verifies that search results are valid modules and copies the module folders to the installation location.</span></span> <span data-ttu-id="38f87-112">インストールされたモジュールは、インストール後に自動的にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="38f87-112">Installed modules are not automatically imported after installation.</span></span>
<span data-ttu-id="38f87-113">指定されたモジュールの最小、最大、および正確なバージョンに基づいて、どのモジュールがインストールされているかをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="38f87-113">You can filter which module is installed based on the minimum, maximum, and exact versions of specified modules.</span></span>

<span data-ttu-id="38f87-114">インストールされているモジュールの名前またはバージョンが同じであるか、既存のモジュールにコマンドが含まれている場合は、警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38f87-114">If the module being installed has the same name or version, or contains commands in an existing module, warning messages are displayed.</span></span> <span data-ttu-id="38f87-115">モジュールをインストールして警告をオーバーライドすることを確認したら、 `-Force` パラメーターとパラメーターを使用し `-AllowClobber` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-115">After you confirm that you want to install the module and override the warnings, use the `-Force` and `-AllowClobber` parameters.</span></span> <span data-ttu-id="38f87-116">リポジトリの設定によっては、モジュールのインストールを続行するためのプロンプトが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="38f87-116">Dependent upon your repository settings, you might need to answer a prompt for the module installation to continue.</span></span>

<span data-ttu-id="38f87-117">これらの例では、登録されている唯一のリポジトリとして [PowerShell ギャラリー](https://www.powershellgallery.com/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="38f87-117">These examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="38f87-118">`Get-PSRepository` 登録されているリポジトリを表示します。</span><span class="sxs-lookup"><span data-stu-id="38f87-118">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="38f87-119">複数の登録済みリポジトリがある場合は、パラメーターを使用して、 `-Repository` リポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-119">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="38f87-120">例</span><span class="sxs-lookup"><span data-stu-id="38f87-120">EXAMPLES</span></span>

### <span data-ttu-id="38f87-121">例 1: モジュールを検索してインストールする</span><span class="sxs-lookup"><span data-stu-id="38f87-121">Example 1: Find and install a module</span></span>

<span data-ttu-id="38f87-122">この例では、リポジトリ内のモジュールを検索し、モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="38f87-122">This example finds a module in the repository and installs the module.</span></span>

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

<span data-ttu-id="38f87-123">では、 `Find-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="38f87-123">The `Find-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="38f87-124">既定では、最新バージョンのモジュールがリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="38f87-124">By default, the newest version of the module is downloaded from the repository.</span></span> <span data-ttu-id="38f87-125">オブジェクトは、パイプラインを介してコマンドレットに送信され `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-125">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="38f87-126">`Install-Module` のすべてのユーザーのモジュールをインストール `$env:ProgramFiles\PowerShell\Modules` します。</span><span class="sxs-lookup"><span data-stu-id="38f87-126">`Install-Module` installs the module for all users in `$env:ProgramFiles\PowerShell\Modules`.</span></span>

### <span data-ttu-id="38f87-127">例 2: 名前を指定してモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="38f87-127">Example 2: Install a module by name</span></span>

<span data-ttu-id="38f87-128">この例では、 **PowerShellGet** モジュールの最新バージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="38f87-128">In this example, the newest version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet
```

<span data-ttu-id="38f87-129">では、 `Install-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="38f87-129">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="38f87-130">既定では、最新バージョンのモジュールがリポジトリからダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="38f87-130">By default, the newest version of the module is downloaded from the repository and installed.</span></span>

### <span data-ttu-id="38f87-131">例 3: 最小バージョンを使用してモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="38f87-131">Example 3: Install a module using its minimum version</span></span>

<span data-ttu-id="38f87-132">この例では、 **PowerShellGet** モジュールの最小バージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="38f87-132">In this example, the minimum version of the **PowerShellGet** module is installed.</span></span> <span data-ttu-id="38f87-133">**MinimumVersion** パラメーターは、インストールする必要があるモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-133">The **MinimumVersion** parameter specifies the lowest version of the module that should be installed.</span></span> <span data-ttu-id="38f87-134">新しいバージョンのモジュールを使用できる場合は、そのバージョンがダウンロードされ、すべてのユーザーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="38f87-134">If a newer version of the module is available, that version is downloaded and installed for all users.</span></span>

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

<span data-ttu-id="38f87-135">では、 `Install-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="38f87-135">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="38f87-136">**MinimumVersion** パラメーターは、バージョン **2.0.1** がリポジトリからダウンロードされ、インストールされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-136">The **MinimumVersion** parameter specifies that version **2.0.1** is downloaded from the repository and installed.</span></span> <span data-ttu-id="38f87-137">バージョン **2.0.4** が使用可能なので、このバージョンはすべてのユーザーにダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="38f87-137">Because version **2.0.4** is available, that version is downloaded and installed for all users.</span></span>

### <span data-ttu-id="38f87-138">例 4: モジュールの特定のバージョンをインストールする</span><span class="sxs-lookup"><span data-stu-id="38f87-138">Example 4: Install a specific version of a module</span></span>

<span data-ttu-id="38f87-139">この例では、 **PowerShellGet** モジュールの特定のバージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="38f87-139">In this example, a specific version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

<span data-ttu-id="38f87-140">では、 `Install-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="38f87-140">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="38f87-141">**RequiredVersion** パラメーターは、すべてのユーザーにバージョン **2.0.0** がダウンロードされ、インストールされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-141">The **RequiredVersion** parameter specifies that version **2.0.0** is downloaded and installed for all users.</span></span>

### <span data-ttu-id="38f87-142">例 5: 現在のユーザーに対してのみモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="38f87-142">Example 5: Install a module only for the current user</span></span>

<span data-ttu-id="38f87-143">この例では、最新バージョンのモジュールをダウンロードし、現在のユーザーに対してのみインストールします。</span><span class="sxs-lookup"><span data-stu-id="38f87-143">This example downloads and installs the newest version of a module, only for the current user.</span></span>

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

<span data-ttu-id="38f87-144">では、 `Install-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="38f87-144">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>
<span data-ttu-id="38f87-145">`Install-Module` 最新バージョンの **PowerShellGet** をダウンロードし、現在のユーザーのディレクトリ () にインストールし `$home\Documents\PowerShell\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-145">`Install-Module` downloads and installs the newest version of **PowerShellGet** into the current user's directory, `$home\Documents\PowerShell\Modules`.</span></span>

## <span data-ttu-id="38f87-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="38f87-146">PARAMETERS</span></span>

### <span data-ttu-id="38f87-147">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="38f87-147">-AcceptLicense</span></span>

<span data-ttu-id="38f87-148">ライセンスが必要なモジュールの場合、 **Acceptlicense** はインストール中にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="38f87-148">For modules that require a license, **AcceptLicense** automatically accepts the license agreement during installation.</span></span> <span data-ttu-id="38f87-149">詳細については、「ライセンスへの [同意が必要なモジュール](/powershell/scripting/gallery/concepts/module-license-acceptance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38f87-149">For more information, see [Modules Requiring License Acceptance](/powershell/scripting/gallery/concepts/module-license-acceptance).</span></span>

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

### <span data-ttu-id="38f87-150">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="38f87-150">-AllowClobber</span></span>

<span data-ttu-id="38f87-151">コンピューター上の既存のコマンドに関するインストールの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="38f87-151">Overrides warning messages about installation conflicts about existing commands on a computer.</span></span>
<span data-ttu-id="38f87-152">モジュールによってインストールされたコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="38f87-152">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>
<span data-ttu-id="38f87-153">**AllowClobber** と **Force** は、コマンドで一緒に使用でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-153">**AllowClobber** and **Force** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="38f87-154">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="38f87-154">-AllowPrerelease</span></span>

<span data-ttu-id="38f87-155">プレリリースとしてマークされているモジュールをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="38f87-155">Allows you to install a module marked as a pre-release.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="38f87-156">-Confirm</span></span>

<span data-ttu-id="38f87-157">コマンドレットを実行する前に確認メッセージを表示 `Install-Module` します。</span><span class="sxs-lookup"><span data-stu-id="38f87-157">Prompts you for confirmation before running the `Install-Module` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="38f87-158">-Credential</span></span>

<span data-ttu-id="38f87-159">指定したパッケージプロバイダーまたはソースのモジュールをインストールする権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-159">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-160">-Force</span><span class="sxs-lookup"><span data-stu-id="38f87-160">-Force</span></span>

<span data-ttu-id="38f87-161">モジュールをインストールし、モジュールのインストール競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="38f87-161">Installs a module and overrides warning messages about module installation conflicts.</span></span> <span data-ttu-id="38f87-162">同じ名前のモジュールがコンピューターに既に存在する場合、 **Force** では複数のバージョンをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="38f87-162">If a module with the same name already exists on the computer, **Force** allows for multiple versions to be installed.</span></span> <span data-ttu-id="38f87-163">同じ名前とバージョンのモジュールが既に存在する場合、 **強制的** にそのバージョンが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="38f87-163">If there is an existing module with the same name and version, **Force** overwrites that version.</span></span> <span data-ttu-id="38f87-164">**Force** と **AllowClobber** は、コマンドで一緒に使用でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-164">**Force** and **AllowClobber** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="38f87-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="38f87-165">-InputObject</span></span>

<span data-ttu-id="38f87-166">パイプラインの入力に使用されます。</span><span class="sxs-lookup"><span data-stu-id="38f87-166">Used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-167">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="38f87-167">-MaximumVersion</span></span>

<span data-ttu-id="38f87-168">インストールする1つのモジュールの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-168">Specifies the maximum version of a single module to install.</span></span> <span data-ttu-id="38f87-169">インストールされているバージョンは、 **MaximumVersion** 以下である必要があります。</span><span class="sxs-lookup"><span data-stu-id="38f87-169">The version installed must be less than or equal to **MaximumVersion**.</span></span> <span data-ttu-id="38f87-170">複数のモジュールをインストールする場合は、 **MaximumVersion** を使用できません。</span><span class="sxs-lookup"><span data-stu-id="38f87-170">If you want to install multiple modules, you cannot use **MaximumVersion**.</span></span> <span data-ttu-id="38f87-171">**MaximumVersion** と **RequiredVersion** を同じコマンドで使用することはできません `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="38f87-171">**MaximumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-172">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="38f87-172">-MinimumVersion</span></span>

<span data-ttu-id="38f87-173">インストールする1つのモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-173">Specifies the minimum version of a single module to install.</span></span> <span data-ttu-id="38f87-174">インストールされているバージョンは、 **MinimumVersion** 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="38f87-174">The version installed must be greater than or equal to **MinimumVersion**.</span></span> <span data-ttu-id="38f87-175">使用可能な新しいバージョンのモジュールがある場合は、新しいバージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="38f87-175">If there is a newer version of the module available, the newer version is installed.</span></span> <span data-ttu-id="38f87-176">複数のモジュールをインストールする場合は、 **MinimumVersion** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="38f87-176">If you want to install multiple modules, you cannot use **MinimumVersion**.</span></span>
<span data-ttu-id="38f87-177">**MinimumVersion** および **RequiredVersion** を同じコマンドで使用することはできません `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="38f87-177">**MinimumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-178">-Name</span><span class="sxs-lookup"><span data-stu-id="38f87-178">-Name</span></span>

<span data-ttu-id="38f87-179">オンラインギャラリーからインストールするモジュールの正確な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-179">Specifies the exact names of modules to install from the online gallery.</span></span> <span data-ttu-id="38f87-180">モジュール名のコンマ区切りのリストが受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="38f87-180">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="38f87-181">モジュール名は、リポジトリ内のモジュール名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38f87-181">The module name must match the module name in the repository.</span></span> <span data-ttu-id="38f87-182">`Find-Module`モジュール名の一覧を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="38f87-182">Use `Find-Module` to get a list of module names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="38f87-183">-PassThru</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-184">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="38f87-184">-Proxy</span></span>

<span data-ttu-id="38f87-185">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-185">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-186">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="38f87-186">-ProxyCredential</span></span>

<span data-ttu-id="38f87-187">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-187">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-188">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="38f87-188">-Repository</span></span>

<span data-ttu-id="38f87-189">**Repository** パラメーターを使用して、モジュールのダウンロードとインストールに使用するリポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-189">Use the **Repository** parameter to specify which repository is used to download and install a module.</span></span> <span data-ttu-id="38f87-190">複数のリポジトリが登録されている場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="38f87-190">Used when multiple repositories are registered.</span></span> <span data-ttu-id="38f87-191">コマンドで登録されているリポジトリの名前を指定し `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-191">Specifies the name of a registered repository in the `Install-Module` command.</span></span> <span data-ttu-id="38f87-192">リポジトリを登録するには、を使用 `Register-PSRepository` します。</span><span class="sxs-lookup"><span data-stu-id="38f87-192">To register a repository, use `Register-PSRepository`.</span></span>
<span data-ttu-id="38f87-193">登録されているリポジトリを表示するには、を使用 `Get-PSRepository` します。</span><span class="sxs-lookup"><span data-stu-id="38f87-193">To display registered repositories, use `Get-PSRepository`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-194">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="38f87-194">-RequiredVersion</span></span>

<span data-ttu-id="38f87-195">インストールする1つのモジュールの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-195">Specifies the exact version of a single module to install.</span></span> <span data-ttu-id="38f87-196">指定したバージョンのリポジトリに一致するものがない場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38f87-196">If there is no match in the repository for the specified version, an error is displayed.</span></span> <span data-ttu-id="38f87-197">複数のモジュールをインストールする場合は、 **RequiredVersion** を使用できません。</span><span class="sxs-lookup"><span data-stu-id="38f87-197">If you want to install multiple modules, you cannot use **RequiredVersion**.</span></span> <span data-ttu-id="38f87-198">**RequiredVersion** `Install-Module` は、 **MinimumVersion** または **MaximumVersion** と同じコマンドでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="38f87-198">**RequiredVersion** cannot be used in the same `Install-Module` command as **MinimumVersion** or **MaximumVersion**.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-199">-スコープ</span><span class="sxs-lookup"><span data-stu-id="38f87-199">-Scope</span></span>

<span data-ttu-id="38f87-200">モジュールのインストール スコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-200">Specifies the installation scope of the module.</span></span> <span data-ttu-id="38f87-201">このパラメーターに指定できる値は **AllUsers** と **CurrentUser** です。</span><span class="sxs-lookup"><span data-stu-id="38f87-201">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span>

<span data-ttu-id="38f87-202">**AllUsers** スコープは、コンピューターのすべてのユーザーがアクセスできる場所にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="38f87-202">The **AllUsers** scope installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="38f87-203">**CurrentUser** を実行すると、コンピューターの現在のユーザーのみがアクセスできる場所にモジュールがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="38f87-203">The **CurrentUser** installs modules in a location that is accessible only to the current user of the computer.</span></span> <span data-ttu-id="38f87-204">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="38f87-204">For example:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="38f87-205">**スコープ** が定義されていない場合、既定値は PowerShellGet のバージョンに基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="38f87-205">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="38f87-206">PowerShellGet バージョン2.0.0 以降では、既定値は **CurrentUser** で、インストールの昇格は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="38f87-206">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser**, which does not require elevation for install.</span></span>
- <span data-ttu-id="38f87-207">PowerShellGet 1.x バージョンでは、既定値は **AllUsers** で、インストールの昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="38f87-207">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-208">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="38f87-208">-SkipPublisherCheck</span></span>

<span data-ttu-id="38f87-209">コンピューターに既に存在するモジュールの新しいバージョンをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="38f87-209">Allows you to install a newer version of a module that already exists on your computer.</span></span> <span data-ttu-id="38f87-210">たとえば、既存のモジュールが信頼できる発行元によってデジタル署名されていても、新しいバージョンが信頼できる発行元によってデジタル署名されていない場合などです。</span><span class="sxs-lookup"><span data-stu-id="38f87-210">For example, when an existing module is digitally signed by a trusted publisher but the new version is not digitally signed by a trusted publisher.</span></span>

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

### <span data-ttu-id="38f87-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="38f87-211">-WhatIf</span></span>

<span data-ttu-id="38f87-212">`Install-Module`コマンドが実行された場合に何が起こるかを示します。</span><span class="sxs-lookup"><span data-stu-id="38f87-212">Shows what would happen if an `Install-Module` command was run.</span></span> <span data-ttu-id="38f87-213">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="38f87-213">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38f87-214">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="38f87-214">CommonParameters</span></span>

<span data-ttu-id="38f87-215">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="38f87-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="38f87-216">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38f87-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="38f87-217">入力</span><span class="sxs-lookup"><span data-stu-id="38f87-217">INPUTS</span></span>

### <span data-ttu-id="38f87-218">できる psrepositoryiteminfo</span><span class="sxs-lookup"><span data-stu-id="38f87-218">PSRepositoryItemInfo</span></span>

<span data-ttu-id="38f87-219">`Find-Module` パイプラインの下に送信できる **できる psrepositoryiteminfo** オブジェクトを作成し `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-219">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span>

### <span data-ttu-id="38f87-220">System.String[]</span><span class="sxs-lookup"><span data-stu-id="38f87-220">System.String[]</span></span>

### <span data-ttu-id="38f87-221">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="38f87-221">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="38f87-222">System.String</span><span class="sxs-lookup"><span data-stu-id="38f87-222">System.String</span></span>

### <span data-ttu-id="38f87-223">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="38f87-223">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="38f87-224">System.Uri</span><span class="sxs-lookup"><span data-stu-id="38f87-224">System.Uri</span></span>

## <span data-ttu-id="38f87-225">出力</span><span class="sxs-lookup"><span data-stu-id="38f87-225">OUTPUTS</span></span>

### <span data-ttu-id="38f87-226">できる psrepositoryiteminfo です。</span><span class="sxs-lookup"><span data-stu-id="38f87-226">Microsoft.PowerShell.Commands.PSRepositoryItemInfo</span></span>

<span data-ttu-id="38f87-227">**PassThru** パラメーターを使用すると、 `Install-Module` モジュールの **できる psrepositoryiteminfo** オブジェクトが出力されます。</span><span class="sxs-lookup"><span data-stu-id="38f87-227">When using the **PassThru** parameter, `Install-Module` outputs a **PSRepositoryItemInfo** object for the module.</span></span> <span data-ttu-id="38f87-228">これは、コマンドレットから取得した情報と同じです `Find-Module` 。</span><span class="sxs-lookup"><span data-stu-id="38f87-228">This is the same information that you get from the `Find-Module` cmdlet.</span></span>

## <span data-ttu-id="38f87-229">注</span><span class="sxs-lookup"><span data-stu-id="38f87-229">NOTES</span></span>

<span data-ttu-id="38f87-230">`Install-Module` は、windows 7 または Windows 2008 R2 以降のリリースの Windows で、PowerShell 5.0 以降のリリースで実行されます。</span><span class="sxs-lookup"><span data-stu-id="38f87-230">`Install-Module` runs on PowerShell 5.0 or later releases, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38f87-231">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="38f87-231">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="38f87-232">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="38f87-232">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="38f87-233">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="38f87-233">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="38f87-234">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38f87-234">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="38f87-235">セキュリティのベストプラクティスとして、コマンドレットまたは関数を初めて実行する前に、モジュールのコードを評価することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38f87-235">As a security best practice, evaluate a module's code before running any cmdlets or functions for the first time.</span></span> <span data-ttu-id="38f87-236">悪意のあるコードを含むモジュールの実行を防ぐため、インストールされたモジュールはインストール後に自動的にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="38f87-236">To prevent running modules that contain malicious code, installed modules are not automatically imported after installation.</span></span>

<span data-ttu-id="38f87-237">**Name** パラメーターによって指定されたモジュール名がリポジトリに存在しない場合、は `Install-Module` エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="38f87-237">If the module name specified by the **Name** parameter does not exist in the repository, `Install-Module` returns an error.</span></span>

<span data-ttu-id="38f87-238">複数のモジュールをインストールするには、 **Name** パラメーターを使用して、コンマで区切られたモジュール名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-238">To install multiple modules, use the **Name** parameter and specify a comma-separated array of module names.</span></span> <span data-ttu-id="38f87-239">複数のモジュール名を指定する場合は、 **MinimumVersion**、 **MaximumVersion**、または **RequiredVersion** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="38f87-239">If you specify multiple module names, you cannot use **MinimumVersion**, **MaximumVersion**, or **RequiredVersion**.</span></span> <span data-ttu-id="38f87-240">`Find-Module` パイプラインの下に送信できる **できる psrepositoryiteminfo** オブジェクトを作成し `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-240">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span> <span data-ttu-id="38f87-241">パイプラインは、複数のモジュールを指定して1つのコマンドでインストールするもう1つの方法です。</span><span class="sxs-lookup"><span data-stu-id="38f87-241">The pipeline is another way to specify multiple modules to install in a single command.</span></span>

<span data-ttu-id="38f87-242">既定では、 **AllUsers** のスコープのモジュールはにインストールされ `$env:ProgramFiles\PowerShell\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-242">By default, modules for the scope of **AllUsers** are installed in `$env:ProgramFiles\PowerShell\Modules`.</span></span> <span data-ttu-id="38f87-243">既定では、PowerShell Desired State Configuration (DSC) リソースをインストールするときに混乱を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="38f87-243">The default prevents confusion when you install PowerShell Desired State Configuration (DSC) resources.</span></span>

<span data-ttu-id="38f87-244">モジュールのインストールが失敗し、 `.psm1` `.psd1` `.dll` フォルダー内に同じ名前の、、またはがない場合は、インポートできません。</span><span class="sxs-lookup"><span data-stu-id="38f87-244">A module installation fails and cannot be imported if it does not have a `.psm1`, `.psd1`, or `.dll` of the same name within the folder.</span></span> <span data-ttu-id="38f87-245">モジュールをインストールするには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="38f87-245">Use the **Force** parameter to install the module.</span></span>

<span data-ttu-id="38f87-246">既存のモジュールのバージョンが **name** パラメーターで指定された名前と一致し、 **MinimumVersion** または **RequiredVersion** パラメーターが使用されていない場合、は `Install-Module` 警告なしで続行しますが、モジュールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="38f87-246">If an existing module's version matches the name specified by the **Name** parameter, and the **MinimumVersion** or **RequiredVersion** parameter are not used, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="38f87-247">既存のモジュールのバージョンが **MinimumVersion** パラメーターの値より大きいか、または **RequiredVersion** パラメーターの値と等しい場合、は `Install-Module` 警告なしで続行しますが、モジュールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="38f87-247">If an existing module's version is greater than the value of the **MinimumVersion** parameter, or equal to the value of the **RequiredVersion** parameter, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="38f87-248">既存のモジュールが **MinimumVersion** パラメーターまたは **RequiredVersion** パラメーターによって指定された値と一致しない場合、コマンドでエラーが発生し `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="38f87-248">If the existing module does not match the values specified by the **MinimumVersion** or **RequiredVersion** parameters, an error occurs in the `Install-Module` command.</span></span> <span data-ttu-id="38f87-249">たとえば、既存のインストールされているモジュールのバージョンが **MinimumVersion** 値より小さいか、 **RequiredVersion** 値と等しくない場合などです。</span><span class="sxs-lookup"><span data-stu-id="38f87-249">For example, if the version of the existing installed module is lower than the **MinimumVersion** value or not equal to the **RequiredVersion** value.</span></span>

<span data-ttu-id="38f87-250">モジュールをインストールすると、モジュールの発行元によって要求された依存モジュールもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="38f87-250">A module installation will also install any dependent modules specified as required by the module publisher.</span></span>
<span data-ttu-id="38f87-251">発行元は、モジュールマニフェストで必要なモジュールとそのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="38f87-251">The publisher will specify the required modules and their versions in the module manifest.</span></span>

## <span data-ttu-id="38f87-252">関連リンク</span><span class="sxs-lookup"><span data-stu-id="38f87-252">RELATED LINKS</span></span>

[<span data-ttu-id="38f87-253">Find-Module</span><span class="sxs-lookup"><span data-stu-id="38f87-253">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="38f87-254">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="38f87-254">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="38f87-255">Import-Module</span><span class="sxs-lookup"><span data-stu-id="38f87-255">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="38f87-256">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="38f87-256">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="38f87-257">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="38f87-257">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="38f87-258">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="38f87-258">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="38f87-259">Update-Module</span><span class="sxs-lookup"><span data-stu-id="38f87-259">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="38f87-260">about_Module</span><span class="sxs-lookup"><span data-stu-id="38f87-260">about_Module</span></span>](../Microsoft.PowerShell.Core/About/about_Modules.md)
