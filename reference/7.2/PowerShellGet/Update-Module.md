---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: f29c208805894634960085cd3816ce7780b7602f
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99601017"
---
# <span data-ttu-id="e20df-102">Update-Module</span><span class="sxs-lookup"><span data-stu-id="e20df-102">Update-Module</span></span>

## <span data-ttu-id="e20df-103">概要</span><span class="sxs-lookup"><span data-stu-id="e20df-103">SYNOPSIS</span></span>
<span data-ttu-id="e20df-104">指定したモジュールの最新バージョンをオンライン ギャラリーからダウンロードし、ローカル コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="e20df-104">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="e20df-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e20df-105">SYNTAX</span></span>

### <span data-ttu-id="e20df-106">すべて</span><span class="sxs-lookup"><span data-stu-id="e20df-106">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e20df-107">Description</span><span class="sxs-lookup"><span data-stu-id="e20df-107">DESCRIPTION</span></span>

<span data-ttu-id="e20df-108">`Update-Module`コマンドレットは、オンラインギャラリーからモジュールの最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e20df-108">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="e20df-109">更新プログラムをインストールする前に、確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e20df-109">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="e20df-110">更新プログラムは、を使用してローカルコンピューターにインストールされたモジュールに対してのみインストールされ `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e20df-110">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="e20df-111">`Update-Module``$env:PSModulePath`インストールされているモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="e20df-111">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="e20df-112">`Update-Module` パラメーターを指定せずに、インストールされているすべてのモジュールを更新します。</span><span class="sxs-lookup"><span data-stu-id="e20df-112">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="e20df-113">更新するモジュールを指定するには、 **Name** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e20df-113">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="e20df-114">**RequiredVersion** パラメーターを使用して、モジュールの特定のバージョンに更新することができます。</span><span class="sxs-lookup"><span data-stu-id="e20df-114">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="e20df-115">インストールされているモジュールが既に最新バージョンである場合、モジュールは更新されません。</span><span class="sxs-lookup"><span data-stu-id="e20df-115">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="e20df-116">モジュールがに見つからない場合 `$env:PSModulePath` は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e20df-116">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="e20df-117">インストールされているモジュールを表示するには、を使用 `Get-InstalledModule` します。</span><span class="sxs-lookup"><span data-stu-id="e20df-117">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="e20df-118">例</span><span class="sxs-lookup"><span data-stu-id="e20df-118">EXAMPLES</span></span>

### <span data-ttu-id="e20df-119">例 1: すべてのモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="e20df-119">Example 1: Update all modules</span></span>

<span data-ttu-id="e20df-120">この例では、オンラインギャラリーで、インストールされているすべてのモジュールを最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="e20df-120">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="e20df-121">例 2: 名前を指定してモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="e20df-121">Example 2: Update a module by name</span></span>

<span data-ttu-id="e20df-122">この例では、オンラインギャラリーで、特定のモジュールを最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="e20df-122">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="e20df-123">`Update-Module`**Name** パラメーターを使用して、特定のモジュール **SpeculationControl** を更新します。</span><span class="sxs-lookup"><span data-stu-id="e20df-123">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl**.</span></span>

### <span data-ttu-id="e20df-124">例 3: what-if Update-Module 実行を表示する</span><span class="sxs-lookup"><span data-stu-id="e20df-124">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="e20df-125">この例では、what-if シナリオを実行して、が実行された場合の動作を示し `Update-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e20df-125">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="e20df-126">コマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e20df-126">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="e20df-127">`Update-Module`**WhatIf** パラメーターを使用して、が実行された場合の動作を表示し `Update-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e20df-127">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="e20df-128">例 4: 指定したバージョンにモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="e20df-128">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="e20df-129">この例では、モジュールが特定のバージョンに更新されます。</span><span class="sxs-lookup"><span data-stu-id="e20df-129">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="e20df-130">オンラインギャラリーにバージョンが存在する必要があります。指定しないと、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e20df-130">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="e20df-131">`Update-Module`**Name** パラメーターを使用して、モジュール **SpeculationControl** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-131">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="e20df-132">**RequiredVersion** パラメーターは、バージョン **1.0.14** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-132">The **RequiredVersion** parameter specifies the version, **1.0.14**.</span></span>

### <span data-ttu-id="e20df-133">例 5: 確認せずにモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="e20df-133">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="e20df-134">この例では、オンラインギャラリーから最新バージョンにモジュールを更新する確認を要求しません。</span><span class="sxs-lookup"><span data-stu-id="e20df-134">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="e20df-135">モジュールが既にインストールされている場合は、 **Force** パラメーターを指定するとモジュールが再インストールされます。</span><span class="sxs-lookup"><span data-stu-id="e20df-135">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="e20df-136">`Update-Module`**Name** パラメーターを使用して、モジュール **SpeculationControl** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-136">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="e20df-137">**Force** パラメーターは、ユーザーの確認を要求せずにモジュールを更新します。</span><span class="sxs-lookup"><span data-stu-id="e20df-137">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="e20df-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e20df-138">PARAMETERS</span></span>

### <span data-ttu-id="e20df-139">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="e20df-139">-AcceptLicense</span></span>

<span data-ttu-id="e20df-140">パッケージで必要な場合は、インストール中にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="e20df-140">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="e20df-141">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="e20df-141">-AllowPrerelease</span></span>

<span data-ttu-id="e20df-142">では、プレリリースとマークされた新しいモジュールを使用してモジュールを更新できます。</span><span class="sxs-lookup"><span data-stu-id="e20df-142">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="e20df-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e20df-143">-Confirm</span></span>

<span data-ttu-id="e20df-144">実行前に確認メッセージを表示 `Update-Module` します。</span><span class="sxs-lookup"><span data-stu-id="e20df-144">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="e20df-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="e20df-145">-Credential</span></span>

<span data-ttu-id="e20df-146">モジュールを更新する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-146">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="e20df-147">-Force</span><span class="sxs-lookup"><span data-stu-id="e20df-147">-Force</span></span>

<span data-ttu-id="e20df-148">確認を要求するメッセージを表示せずに、指定された各モジュールを強制的に更新します。</span><span class="sxs-lookup"><span data-stu-id="e20df-148">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="e20df-149">モジュールが既にインストールされている場合、 **強制的** にモジュールを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="e20df-149">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="e20df-150">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e20df-150">-MaximumVersion</span></span>

<span data-ttu-id="e20df-151">更新する1つのモジュールの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-151">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="e20df-152">複数のモジュールを更新しようとしている場合、このパラメーターを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="e20df-152">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="e20df-153">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e20df-153">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e20df-154">-Name</span><span class="sxs-lookup"><span data-stu-id="e20df-154">-Name</span></span>

<span data-ttu-id="e20df-155">更新する1つ以上のモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-155">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="e20df-156">`Update-Module``$env:PSModulePath`更新するモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="e20df-156">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="e20df-157">指定したモジュール名のに一致するものが見つからない場合は `$env:PSModulePath` 、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e20df-157">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="e20df-158">モジュール名にはワイルドカードを許容します。</span><span class="sxs-lookup"><span data-stu-id="e20df-158">Wildcards are accepted in module names.</span></span> <span data-ttu-id="e20df-159">指定した名前にワイルドカード文字を追加し、一致するものが見つからない場合は、エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="e20df-159">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="e20df-160">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e20df-160">-PassThru</span></span>

<span data-ttu-id="e20df-161">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e20df-161">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="e20df-162">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="e20df-162">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e20df-163">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="e20df-163">-Proxy</span></span>

<span data-ttu-id="e20df-164">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-164">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="e20df-165">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e20df-165">-ProxyCredential</span></span>

<span data-ttu-id="e20df-166">**プロキシ** パラメーターによって指定されたプロキシサーバーを使用する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-166">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e20df-167">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e20df-167">-RequiredVersion</span></span>

<span data-ttu-id="e20df-168">インストールされている既存のモジュールを更新するための正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-168">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="e20df-169">**RequiredVersion** によって指定されたバージョンがオンラインギャラリーに存在している必要があります。または、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e20df-169">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="e20df-170">1つのコマンドで複数のモジュールが更新された場合、 **RequiredVersion** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e20df-170">If more than one module is updated in a single command, you can't use **RequiredVersion**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e20df-171">-スコープ</span><span class="sxs-lookup"><span data-stu-id="e20df-171">-Scope</span></span>

<span data-ttu-id="e20df-172">モジュールのインストール スコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="e20df-172">Specifies the installation scope of the module.</span></span> <span data-ttu-id="e20df-173">このパラメーターに指定できる値は **AllUsers** と **CurrentUser** です。</span><span class="sxs-lookup"><span data-stu-id="e20df-173">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span> <span data-ttu-id="e20df-174">**スコープ** が指定されていない場合、更新プログラムは **CurrentUser** スコープにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e20df-174">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="e20df-175">**AllUsers** スコープには管理者特権が必要です。また、コンピューターのすべてのユーザーがアクセスできる場所にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e20df-175">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="e20df-176">**CurrentUser** では、昇格されたアクセス許可は必要ありません。また、コンピューターの現在のユーザーのみがアクセスできる場所にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e20df-176">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="e20df-177">**スコープ** が定義されていない場合、既定値は PowerShellGet のバージョンに基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="e20df-177">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="e20df-178">PowerShellGet バージョン2.0.0 以降では、既定値は **CurrentUser** で、インストールの昇格は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e20df-178">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser**, which does not require elevation for install.</span></span>
- <span data-ttu-id="e20df-179">PowerShellGet 1.x バージョンでは、既定値は **AllUsers** で、インストールの昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="e20df-179">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e20df-180">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e20df-180">-WhatIf</span></span>

<span data-ttu-id="e20df-181">が実行された場合に何が起こるか `Update-Module` を示します。</span><span class="sxs-lookup"><span data-stu-id="e20df-181">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="e20df-182">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e20df-182">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="e20df-183">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e20df-183">CommonParameters</span></span>

<span data-ttu-id="e20df-184">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e20df-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e20df-185">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e20df-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e20df-186">入力</span><span class="sxs-lookup"><span data-stu-id="e20df-186">INPUTS</span></span>

### <span data-ttu-id="e20df-187">System.String[]</span><span class="sxs-lookup"><span data-stu-id="e20df-187">System.String[]</span></span>

### <span data-ttu-id="e20df-188">System.String</span><span class="sxs-lookup"><span data-stu-id="e20df-188">System.String</span></span>

### <span data-ttu-id="e20df-189">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="e20df-189">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="e20df-190">System.Uri</span><span class="sxs-lookup"><span data-stu-id="e20df-190">System.Uri</span></span>

## <span data-ttu-id="e20df-191">出力</span><span class="sxs-lookup"><span data-stu-id="e20df-191">OUTPUTS</span></span>

### <span data-ttu-id="e20df-192">System.Object</span><span class="sxs-lookup"><span data-stu-id="e20df-192">System.Object</span></span>

## <span data-ttu-id="e20df-193">注</span><span class="sxs-lookup"><span data-stu-id="e20df-193">NOTES</span></span>

<span data-ttu-id="e20df-194">PowerShell バージョン6.0 以降では、既定のインストールスコープは常に **CurrentUser** です。</span><span class="sxs-lookup"><span data-stu-id="e20df-194">For PowerShell version 6.0 and above, the default installation scope is always **CurrentUser**.</span></span>
<span data-ttu-id="e20df-195">**CurrentUser** のモジュール更新プログラムには、 `$home\Documents\PowerShell\Modules` 昇格されたアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e20df-195">Module updates for **CurrentUser**, `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span> <span data-ttu-id="e20df-196">**AllUsers** のモジュール更新プログラムには、 `$env:ProgramFiles\PowerShell\Modules` 昇格されたアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e20df-196">Module updates for **AllUsers**, `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e20df-197">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="e20df-197">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="e20df-198">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e20df-198">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="e20df-199">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="e20df-199">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="e20df-200">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e20df-200">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="e20df-201">`Update-Module` powershell 3.0 以降の PowerShell で、windows 7 または Windows 2008 R2 以降のリリースの Windows で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e20df-201">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="e20df-202">**Name** パラメーターで指定したモジュールがを使用してインストールされなかった場合は `Install-Module` 、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e20df-202">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="e20df-203">を実行すると `Update-Module` 、オンラインギャラリーからインストールしたモジュールでのみ実行でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e20df-203">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="e20df-204">が `Update-Module` 使用中のバイナリを更新しようとすると、は `Update-Module` 問題のプロセスを識別するエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="e20df-204">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="e20df-205">ユーザーには、プロセスが停止した後に再試行するように通知され `Update-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e20df-205">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="e20df-206">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e20df-206">RELATED LINKS</span></span>

[<span data-ttu-id="e20df-207">Find-Module</span><span class="sxs-lookup"><span data-stu-id="e20df-207">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="e20df-208">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="e20df-208">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="e20df-209">Install-Module</span><span class="sxs-lookup"><span data-stu-id="e20df-209">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="e20df-210">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="e20df-210">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="e20df-211">アンインストール-モジュール</span><span class="sxs-lookup"><span data-stu-id="e20df-211">Uninstall-Module</span></span>](Uninstall-Module.md)
