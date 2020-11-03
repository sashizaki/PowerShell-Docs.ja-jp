---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: e2e4dc34fb84a54fb92cc4c809c84d67beafe576
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "93219091"
---
# <span data-ttu-id="48ad2-103">Install-Module</span><span class="sxs-lookup"><span data-stu-id="48ad2-103">Install-Module</span></span>

## <span data-ttu-id="48ad2-104">概要</span><span class="sxs-lookup"><span data-stu-id="48ad2-104">SYNOPSIS</span></span>
<span data-ttu-id="48ad2-105">1つ以上のモジュールをリポジトリからダウンロードし、ローカルコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="48ad2-105">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

## <span data-ttu-id="48ad2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48ad2-106">SYNTAX</span></span>

### <span data-ttu-id="48ad2-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="48ad2-107">NameParameterSet (Default)</span></span>

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="48ad2-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="48ad2-108">InputObject</span></span>

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="48ad2-109">Description</span><span class="sxs-lookup"><span data-stu-id="48ad2-109">DESCRIPTION</span></span>

<span data-ttu-id="48ad2-110">`Install-Module`コマンドレットは、指定された条件を満たす1つ以上のモジュールをオンラインリポジトリから取得します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-110">The `Install-Module` cmdlet gets one or more modules that meet specified criteria from an online repository.</span></span> <span data-ttu-id="48ad2-111">コマンドレットでは、検索結果が有効なモジュールであることを確認し、モジュールフォルダーをインストール場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="48ad2-111">The cmdlet verifies that search results are valid modules and copies the module folders to the installation location.</span></span> <span data-ttu-id="48ad2-112">インストールされたモジュールは、インストール後に自動的にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-112">Installed modules are not automatically imported after installation.</span></span>
<span data-ttu-id="48ad2-113">指定されたモジュールの最小、最大、および正確なバージョンに基づいて、どのモジュールがインストールされているかをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-113">You can filter which module is installed based on the minimum, maximum, and exact versions of specified modules.</span></span>

<span data-ttu-id="48ad2-114">インストールされているモジュールの名前またはバージョンが同じであるか、既存のモジュールにコマンドが含まれている場合は、警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-114">If the module being installed has the same name or version, or contains commands in an existing module, warning messages are displayed.</span></span> <span data-ttu-id="48ad2-115">モジュールをインストールして警告をオーバーライドすることを確認したら、 `-Force` パラメーターとパラメーターを使用し `-AllowClobber` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-115">After you confirm that you want to install the module and override the warnings, use the `-Force` and `-AllowClobber` parameters.</span></span> <span data-ttu-id="48ad2-116">リポジトリの設定によっては、モジュールのインストールを続行するためのプロンプトが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="48ad2-116">Dependent upon your repository settings, you might need to answer a prompt for the module installation to continue.</span></span>

<span data-ttu-id="48ad2-117">これらの例では、登録されている唯一のリポジトリとして [PowerShell ギャラリー](https://www.powershellgallery.com/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-117">These examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="48ad2-118">`Get-PSRepository` 登録されているリポジトリを表示します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-118">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="48ad2-119">複数の登録済みリポジトリがある場合は、パラメーターを使用して、 `-Repository` リポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-119">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="48ad2-120">例</span><span class="sxs-lookup"><span data-stu-id="48ad2-120">EXAMPLES</span></span>

### <span data-ttu-id="48ad2-121">例 1: モジュールを検索してインストールする</span><span class="sxs-lookup"><span data-stu-id="48ad2-121">Example 1: Find and install a module</span></span>

<span data-ttu-id="48ad2-122">この例では、リポジトリ内のモジュールを検索し、モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="48ad2-122">This example finds a module in the repository and installs the module.</span></span>

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

<span data-ttu-id="48ad2-123">では、 `Find-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="48ad2-123">The `Find-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="48ad2-124">既定では、最新バージョンのモジュールがリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-124">By default, the newest version of the module is downloaded from the repository.</span></span> <span data-ttu-id="48ad2-125">オブジェクトは、パイプラインを介してコマンドレットに送信され `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-125">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="48ad2-126">`Install-Module` のすべてのユーザーのモジュールをインストール `$env:ProgramFiles\PowerShell\Modules` します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-126">`Install-Module` installs the module for all users in `$env:ProgramFiles\PowerShell\Modules`.</span></span>

### <span data-ttu-id="48ad2-127">例 2: 名前を指定してモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="48ad2-127">Example 2: Install a module by name</span></span>

<span data-ttu-id="48ad2-128">この例では、 **PowerShellGet** モジュールの最新バージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="48ad2-128">In this example, the newest version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet
```

<span data-ttu-id="48ad2-129">では、 `Install-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="48ad2-129">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="48ad2-130">既定では、最新バージョンのモジュールがリポジトリからダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-130">By default, the newest version of the module is downloaded from the repository and installed.</span></span>

### <span data-ttu-id="48ad2-131">例 3: 最小バージョンを使用してモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="48ad2-131">Example 3: Install a module using its minimum version</span></span>

<span data-ttu-id="48ad2-132">この例では、 **PowerShellGet** モジュールの最小バージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="48ad2-132">In this example, the minimum version of the **PowerShellGet** module is installed.</span></span> <span data-ttu-id="48ad2-133">**MinimumVersion** パラメーターは、インストールする必要があるモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-133">The **MinimumVersion** parameter specifies the lowest version of the module that should be installed.</span></span> <span data-ttu-id="48ad2-134">新しいバージョンのモジュールを使用できる場合は、そのバージョンがダウンロードされ、すべてのユーザーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-134">If a newer version of the module is available, that version is downloaded and installed for all users.</span></span>

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

<span data-ttu-id="48ad2-135">では、 `Install-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="48ad2-135">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="48ad2-136">**MinimumVersion** パラメーターは、バージョン **2.0.1** がリポジトリからダウンロードされ、インストールされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-136">The **MinimumVersion** parameter specifies that version **2.0.1** is downloaded from the repository and installed.</span></span> <span data-ttu-id="48ad2-137">バージョン **2.0.4** が使用可能なので、このバージョンはすべてのユーザーにダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-137">Because version **2.0.4** is available, that version is downloaded and installed for all users.</span></span>

### <span data-ttu-id="48ad2-138">例 4: モジュールの特定のバージョンをインストールする</span><span class="sxs-lookup"><span data-stu-id="48ad2-138">Example 4: Install a specific version of a module</span></span>

<span data-ttu-id="48ad2-139">この例では、 **PowerShellGet** モジュールの特定のバージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="48ad2-139">In this example, a specific version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

<span data-ttu-id="48ad2-140">では、 `Install-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="48ad2-140">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="48ad2-141">**RequiredVersion** パラメーターは、すべてのユーザーにバージョン **2.0.0** がダウンロードされ、インストールされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-141">The **RequiredVersion** parameter specifies that version **2.0.0** is downloaded and installed for all users.</span></span>

### <span data-ttu-id="48ad2-142">例 5: 現在のユーザーに対してのみモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="48ad2-142">Example 5: Install a module only for the current user</span></span>

<span data-ttu-id="48ad2-143">この例では、最新バージョンのモジュールをダウンロードし、現在のユーザーに対してのみインストールします。</span><span class="sxs-lookup"><span data-stu-id="48ad2-143">This example downloads and installs the newest version of a module, only for the current user.</span></span>

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

<span data-ttu-id="48ad2-144">では、 `Install-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="48ad2-144">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>
<span data-ttu-id="48ad2-145">`Install-Module` 最新バージョンの **PowerShellGet** をダウンロードし、現在のユーザーのディレクトリ () にインストールし `$home\Documents\PowerShell\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-145">`Install-Module` downloads and installs the newest version of **PowerShellGet** into the current user's directory, `$home\Documents\PowerShell\Modules`.</span></span>

## <span data-ttu-id="48ad2-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="48ad2-146">PARAMETERS</span></span>

### <span data-ttu-id="48ad2-147">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="48ad2-147">-AcceptLicense</span></span>

<span data-ttu-id="48ad2-148">ライセンスが必要なモジュールの場合、 **Acceptlicense** はインストール中にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-148">For modules that require a license, **AcceptLicense** automatically accepts the license agreement during installation.</span></span> <span data-ttu-id="48ad2-149">詳細については、「ライセンスへの [同意が必要なモジュール](/powershell/scripting/gallery/concepts/module-license-acceptance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48ad2-149">For more information, see [Modules Requiring License Acceptance](/powershell/scripting/gallery/concepts/module-license-acceptance).</span></span>

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

### <span data-ttu-id="48ad2-150">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="48ad2-150">-AllowClobber</span></span>

<span data-ttu-id="48ad2-151">コンピューター上の既存のコマンドに関するインストールの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="48ad2-151">Overrides warning messages about installation conflicts about existing commands on a computer.</span></span>
<span data-ttu-id="48ad2-152">モジュールによってインストールされたコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="48ad2-152">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>
<span data-ttu-id="48ad2-153">**AllowClobber** と **Force** は、コマンドで一緒に使用でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-153">**AllowClobber** and **Force** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="48ad2-154">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="48ad2-154">-AllowPrerelease</span></span>

<span data-ttu-id="48ad2-155">プレリリースとしてマークされているモジュールをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-155">Allows you to install a module marked as a pre-release.</span></span>

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

### <span data-ttu-id="48ad2-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="48ad2-156">-Confirm</span></span>

<span data-ttu-id="48ad2-157">コマンドレットを実行する前に確認メッセージを表示 `Install-Module` します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-157">Prompts you for confirmation before running the `Install-Module` cmdlet.</span></span>

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

### <span data-ttu-id="48ad2-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="48ad2-158">-Credential</span></span>

<span data-ttu-id="48ad2-159">指定したパッケージプロバイダーまたはソースのモジュールをインストールする権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-159">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="48ad2-160">-Force</span><span class="sxs-lookup"><span data-stu-id="48ad2-160">-Force</span></span>

<span data-ttu-id="48ad2-161">モジュールをインストールし、モジュールのインストール競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="48ad2-161">Installs a module and overrides warning messages about module installation conflicts.</span></span> <span data-ttu-id="48ad2-162">同じ名前のモジュールがコンピューターに既に存在する場合、 **Force** では複数のバージョンをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-162">If a module with the same name already exists on the computer, **Force** allows for multiple versions to be installed.</span></span> <span data-ttu-id="48ad2-163">同じ名前とバージョンのモジュールが既に存在する場合、 **強制的** にそのバージョンが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-163">If there is an existing module with the same name and version, **Force** overwrites that version.</span></span> <span data-ttu-id="48ad2-164">**Force** と **AllowClobber** は、コマンドで一緒に使用でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-164">**Force** and **AllowClobber** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="48ad2-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="48ad2-165">-InputObject</span></span>

<span data-ttu-id="48ad2-166">パイプラインの入力に使用されます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-166">Used for pipeline input.</span></span>

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

### <span data-ttu-id="48ad2-167">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="48ad2-167">-MaximumVersion</span></span>

<span data-ttu-id="48ad2-168">インストールする1つのモジュールの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-168">Specifies the maximum version of a single module to install.</span></span> <span data-ttu-id="48ad2-169">インストールされているバージョンは、 **MaximumVersion** 以下である必要があります。</span><span class="sxs-lookup"><span data-stu-id="48ad2-169">The version installed must be less than or equal to **MaximumVersion**.</span></span> <span data-ttu-id="48ad2-170">複数のモジュールをインストールする場合は、 **MaximumVersion** を使用できません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-170">If you want to install multiple modules, you cannot use **MaximumVersion**.</span></span> <span data-ttu-id="48ad2-171">**MaximumVersion** と **RequiredVersion** を同じコマンドで使用することはできません `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="48ad2-171">**MaximumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

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

### <span data-ttu-id="48ad2-172">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="48ad2-172">-MinimumVersion</span></span>

<span data-ttu-id="48ad2-173">インストールする1つのモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-173">Specifies the minimum version of a single module to install.</span></span> <span data-ttu-id="48ad2-174">インストールされているバージョンは、 **MinimumVersion** 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="48ad2-174">The version installed must be greater than or equal to **MinimumVersion**.</span></span> <span data-ttu-id="48ad2-175">使用可能な新しいバージョンのモジュールがある場合は、新しいバージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-175">If there is a newer version of the module available, the newer version is installed.</span></span> <span data-ttu-id="48ad2-176">複数のモジュールをインストールする場合は、 **MinimumVersion** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-176">If you want to install multiple modules, you cannot use **MinimumVersion**.</span></span>
<span data-ttu-id="48ad2-177">**MinimumVersion** および **RequiredVersion** を同じコマンドで使用することはできません `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="48ad2-177">**MinimumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

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

### <span data-ttu-id="48ad2-178">-Name</span><span class="sxs-lookup"><span data-stu-id="48ad2-178">-Name</span></span>

<span data-ttu-id="48ad2-179">オンラインギャラリーからインストールするモジュールの正確な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-179">Specifies the exact names of modules to install from the online gallery.</span></span> <span data-ttu-id="48ad2-180">モジュール名のコンマ区切りのリストが受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-180">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="48ad2-181">モジュール名は、リポジトリ内のモジュール名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48ad2-181">The module name must match the module name in the repository.</span></span> <span data-ttu-id="48ad2-182">`Find-Module`モジュール名の一覧を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-182">Use `Find-Module` to get a list of module names.</span></span>

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

### <span data-ttu-id="48ad2-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="48ad2-183">-PassThru</span></span>

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

### <span data-ttu-id="48ad2-184">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="48ad2-184">-Proxy</span></span>

<span data-ttu-id="48ad2-185">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-185">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="48ad2-186">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="48ad2-186">-ProxyCredential</span></span>

<span data-ttu-id="48ad2-187">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-187">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="48ad2-188">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="48ad2-188">-Repository</span></span>

<span data-ttu-id="48ad2-189">**Repository** パラメーターを使用して、モジュールのダウンロードとインストールに使用するリポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-189">Use the **Repository** parameter to specify which repository is used to download and install a module.</span></span> <span data-ttu-id="48ad2-190">複数のリポジトリが登録されている場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-190">Used when multiple repositories are registered.</span></span> <span data-ttu-id="48ad2-191">コマンドで登録されているリポジトリの名前を指定し `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-191">Specifies the name of a registered repository in the `Install-Module` command.</span></span> <span data-ttu-id="48ad2-192">リポジトリを登録するには、を使用 `Register-PSRepository` します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-192">To register a repository, use `Register-PSRepository`.</span></span>
<span data-ttu-id="48ad2-193">登録されているリポジトリを表示するには、を使用 `Get-PSRepository` します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-193">To display registered repositories, use `Get-PSRepository`.</span></span>

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

### <span data-ttu-id="48ad2-194">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="48ad2-194">-RequiredVersion</span></span>

<span data-ttu-id="48ad2-195">インストールする1つのモジュールの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-195">Specifies the exact version of a single module to install.</span></span> <span data-ttu-id="48ad2-196">指定したバージョンのリポジトリに一致するものがない場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-196">If there is no match in the repository for the specified version, an error is displayed.</span></span> <span data-ttu-id="48ad2-197">複数のモジュールをインストールする場合は、 **RequiredVersion** を使用できません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-197">If you want to install multiple modules, you cannot use **RequiredVersion**.</span></span> <span data-ttu-id="48ad2-198">**RequiredVersion** `Install-Module` は、 **MinimumVersion** または **MaximumVersion** と同じコマンドでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-198">**RequiredVersion** cannot be used in the same `Install-Module` command as **MinimumVersion** or **MaximumVersion**.</span></span>

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

### <span data-ttu-id="48ad2-199">-スコープ</span><span class="sxs-lookup"><span data-stu-id="48ad2-199">-Scope</span></span>

<span data-ttu-id="48ad2-200">モジュールのインストール スコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-200">Specifies the installation scope of the module.</span></span> <span data-ttu-id="48ad2-201">このパラメーターに指定できる値は **AllUsers** と **CurrentUser** です。</span><span class="sxs-lookup"><span data-stu-id="48ad2-201">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span>

<span data-ttu-id="48ad2-202">**AllUsers** スコープは、コンピューターのすべてのユーザーがアクセスできる場所にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="48ad2-202">The **AllUsers** scope installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="48ad2-203">**CurrentUser** を実行すると、コンピューターの現在のユーザーのみがアクセスできる場所にモジュールがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-203">The **CurrentUser** installs modules in a location that is accessible only to the current user of the computer.</span></span> <span data-ttu-id="48ad2-204">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-204">For example:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="48ad2-205">**スコープ** が定義されていない場合、既定値は PowerShellGet のバージョンに基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-205">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="48ad2-206">PowerShellGet バージョン2.0.0 以降では、既定値は **CurrentUser** で、インストールの昇格は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-206">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser** , which does not require elevation for install.</span></span>
- <span data-ttu-id="48ad2-207">PowerShellGet 1.x バージョンでは、既定値は **AllUsers** で、インストールの昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="48ad2-207">In PowerShellGet 1.x versions, the default is **AllUsers** , which requires elevation for install.</span></span>

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

### <span data-ttu-id="48ad2-208">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="48ad2-208">-SkipPublisherCheck</span></span>

<span data-ttu-id="48ad2-209">コンピューターに既に存在するモジュールの新しいバージョンをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-209">Allows you to install a newer version of a module that already exists on your computer.</span></span> <span data-ttu-id="48ad2-210">たとえば、既存のモジュールが信頼できる発行元によってデジタル署名されていても、新しいバージョンが信頼できる発行元によってデジタル署名されていない場合などです。</span><span class="sxs-lookup"><span data-stu-id="48ad2-210">For example, when an existing module is digitally signed by a trusted publisher but the new version is not digitally signed by a trusted publisher.</span></span>

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

### <span data-ttu-id="48ad2-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="48ad2-211">-WhatIf</span></span>

<span data-ttu-id="48ad2-212">`Install-Module`コマンドが実行された場合に何が起こるかを示します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-212">Shows what would happen if an `Install-Module` command was run.</span></span> <span data-ttu-id="48ad2-213">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="48ad2-214">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="48ad2-214">CommonParameters</span></span>

<span data-ttu-id="48ad2-215">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="48ad2-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48ad2-216">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48ad2-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="48ad2-217">入力</span><span class="sxs-lookup"><span data-stu-id="48ad2-217">INPUTS</span></span>

### <span data-ttu-id="48ad2-218">できる psrepositoryiteminfo</span><span class="sxs-lookup"><span data-stu-id="48ad2-218">PSRepositoryItemInfo</span></span>

<span data-ttu-id="48ad2-219">`Find-Module` パイプラインの下に送信できる **できる psrepositoryiteminfo** オブジェクトを作成し `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-219">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span>

### <span data-ttu-id="48ad2-220">System.String[]</span><span class="sxs-lookup"><span data-stu-id="48ad2-220">System.String[]</span></span>

### <span data-ttu-id="48ad2-221">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="48ad2-221">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="48ad2-222">System.String</span><span class="sxs-lookup"><span data-stu-id="48ad2-222">System.String</span></span>

### <span data-ttu-id="48ad2-223">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="48ad2-223">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="48ad2-224">System.Uri</span><span class="sxs-lookup"><span data-stu-id="48ad2-224">System.Uri</span></span>

## <span data-ttu-id="48ad2-225">出力</span><span class="sxs-lookup"><span data-stu-id="48ad2-225">OUTPUTS</span></span>

### <span data-ttu-id="48ad2-226">できる psrepositoryiteminfo です。</span><span class="sxs-lookup"><span data-stu-id="48ad2-226">Microsoft.PowerShell.Commands.PSRepositoryItemInfo</span></span>

<span data-ttu-id="48ad2-227">**PassThru** パラメーターを使用すると、 `Install-Module` モジュールの **できる psrepositoryiteminfo** オブジェクトが出力されます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-227">When using the **PassThru** parameter, `Install-Module` outputs a **PSRepositoryItemInfo** object for the module.</span></span> <span data-ttu-id="48ad2-228">これは、コマンドレットから取得した情報と同じです `Find-Module` 。</span><span class="sxs-lookup"><span data-stu-id="48ad2-228">This is the same information that you get from the `Find-Module` cmdlet.</span></span>

## <span data-ttu-id="48ad2-229">注</span><span class="sxs-lookup"><span data-stu-id="48ad2-229">NOTES</span></span>

<span data-ttu-id="48ad2-230">`Install-Module` は、windows 7 または Windows 2008 R2 以降のリリースの Windows で、PowerShell 5.0 以降のリリースで実行されます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-230">`Install-Module` runs on PowerShell 5.0 or later releases, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="48ad2-231">セキュリティのベストプラクティスとして、コマンドレットまたは関数を初めて実行する前に、モジュールのコードを評価することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="48ad2-231">As a security best practice, evaluate a module's code before running any cmdlets or functions for the first time.</span></span> <span data-ttu-id="48ad2-232">悪意のあるコードを含むモジュールの実行を防ぐため、インストールされたモジュールはインストール後に自動的にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-232">To prevent running modules that contain malicious code, installed modules are not automatically imported after installation.</span></span>

<span data-ttu-id="48ad2-233">**Name** パラメーターによって指定されたモジュール名がリポジトリに存在しない場合、は `Install-Module` エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-233">If the module name specified by the **Name** parameter does not exist in the repository, `Install-Module` returns an error.</span></span>

<span data-ttu-id="48ad2-234">複数のモジュールをインストールするには、 **Name** パラメーターを使用して、コンマで区切られたモジュール名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-234">To install multiple modules, use the **Name** parameter and specify a comma-separated array of module names.</span></span> <span data-ttu-id="48ad2-235">複数のモジュール名を指定する場合は、 **MinimumVersion** 、 **MaximumVersion** 、または **RequiredVersion** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-235">If you specify multiple module names, you cannot use **MinimumVersion** , **MaximumVersion** , or **RequiredVersion**.</span></span> <span data-ttu-id="48ad2-236">`Find-Module` パイプラインの下に送信できる **できる psrepositoryiteminfo** オブジェクトを作成し `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-236">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span> <span data-ttu-id="48ad2-237">パイプラインは、複数のモジュールを指定して1つのコマンドでインストールするもう1つの方法です。</span><span class="sxs-lookup"><span data-stu-id="48ad2-237">The pipeline is another way to specify multiple modules to install in a single command.</span></span>

<span data-ttu-id="48ad2-238">既定では、 **AllUsers** のスコープのモジュールはにインストールされ `$env:ProgramFiles\PowerShell\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-238">By default, modules for the scope of **AllUsers** are installed in `$env:ProgramFiles\PowerShell\Modules`.</span></span> <span data-ttu-id="48ad2-239">既定では、PowerShell Desired State Configuration (DSC) リソースをインストールするときに混乱を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-239">The default prevents confusion when you install PowerShell Desired State Configuration (DSC) resources.</span></span>

<span data-ttu-id="48ad2-240">モジュールのインストールが失敗し、 `.psm1` `.psd1` `.dll` フォルダー内に同じ名前の、、またはがない場合は、インポートできません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-240">A module installation fails and cannot be imported if it does not have a `.psm1`, `.psd1`, or `.dll` of the same name within the folder.</span></span> <span data-ttu-id="48ad2-241">モジュールをインストールするには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-241">Use the **Force** parameter to install the module.</span></span>

<span data-ttu-id="48ad2-242">既存のモジュールのバージョンが **name** パラメーターで指定された名前と一致し、 **MinimumVersion** または **RequiredVersion** パラメーターが使用されていない場合、は `Install-Module` 警告なしで続行しますが、モジュールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-242">If an existing module's version matches the name specified by the **Name** parameter, and the **MinimumVersion** or **RequiredVersion** parameter are not used, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="48ad2-243">既存のモジュールのバージョンが **MinimumVersion** パラメーターの値より大きいか、または **RequiredVersion** パラメーターの値と等しい場合、は `Install-Module` 警告なしで続行しますが、モジュールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-243">If an existing module's version is greater than the value of the **MinimumVersion** parameter, or equal to the value of the **RequiredVersion** parameter, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="48ad2-244">既存のモジュールが **MinimumVersion** パラメーターまたは **RequiredVersion** パラメーターによって指定された値と一致しない場合、コマンドでエラーが発生し `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-244">If the existing module does not match the values specified by the **MinimumVersion** or **RequiredVersion** parameters, an error occurs in the `Install-Module` command.</span></span> <span data-ttu-id="48ad2-245">たとえば、既存のインストールされているモジュールのバージョンが **MinimumVersion** 値より小さいか、 **RequiredVersion** 値と等しくない場合などです。</span><span class="sxs-lookup"><span data-stu-id="48ad2-245">For example, if the version of the existing installed module is lower than the **MinimumVersion** value or not equal to the **RequiredVersion** value.</span></span>

<span data-ttu-id="48ad2-246">モジュールをインストールすると、モジュールの発行元によって要求された依存モジュールもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-246">A module installation will also install any dependent modules specified as required by the module publisher.</span></span>
<span data-ttu-id="48ad2-247">発行元は、モジュールマニフェストで必要なモジュールとそのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-247">The publisher will specify the required modules and their versions in the module manifest.</span></span>

## <span data-ttu-id="48ad2-248">関連リンク</span><span class="sxs-lookup"><span data-stu-id="48ad2-248">RELATED LINKS</span></span>

[<span data-ttu-id="48ad2-249">Find-Module</span><span class="sxs-lookup"><span data-stu-id="48ad2-249">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="48ad2-250">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="48ad2-250">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="48ad2-251">Import-Module</span><span class="sxs-lookup"><span data-stu-id="48ad2-251">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="48ad2-252">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="48ad2-252">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="48ad2-253">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="48ad2-253">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="48ad2-254">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="48ad2-254">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="48ad2-255">Update-Module</span><span class="sxs-lookup"><span data-stu-id="48ad2-255">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="48ad2-256">about_Module</span><span class="sxs-lookup"><span data-stu-id="48ad2-256">about_Module</span></span>](../Microsoft.PowerShell.Core/About/about_Modules.md)
