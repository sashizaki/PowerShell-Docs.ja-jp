---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: 29ba3907a349257f63e127739786ab6e210c0f82
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210208"
---
# <span data-ttu-id="cfa9f-103">Update-Module</span><span class="sxs-lookup"><span data-stu-id="cfa9f-103">Update-Module</span></span>

## <span data-ttu-id="cfa9f-104">概要</span><span class="sxs-lookup"><span data-stu-id="cfa9f-104">SYNOPSIS</span></span>
<span data-ttu-id="cfa9f-105">指定したモジュールの最新バージョンをオンライン ギャラリーからダウンロードし、ローカル コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-105">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="cfa9f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cfa9f-106">SYNTAX</span></span>

### <span data-ttu-id="cfa9f-107">All</span><span class="sxs-lookup"><span data-stu-id="cfa9f-107">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cfa9f-108">Description</span><span class="sxs-lookup"><span data-stu-id="cfa9f-108">DESCRIPTION</span></span>

<span data-ttu-id="cfa9f-109">`Update-Module`コマンドレットは、オンラインギャラリーからモジュールの最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-109">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="cfa9f-110">更新プログラムをインストールする前に、確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-110">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="cfa9f-111">更新プログラムは、を使用してローカルコンピューターにインストールされたモジュールに対してのみインストールされ `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-111">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="cfa9f-112">`Update-Module``$env:PSModulePath`インストールされているモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-112">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="cfa9f-113">`Update-Module` パラメーターを指定せずに、インストールされているすべてのモジュールを更新します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-113">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="cfa9f-114">更新するモジュールを指定するには、 **Name** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-114">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="cfa9f-115">**RequiredVersion** パラメーターを使用して、モジュールの特定のバージョンに更新することができます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-115">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="cfa9f-116">インストールされているモジュールが既に最新バージョンである場合、モジュールは更新されません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-116">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="cfa9f-117">モジュールがに見つからない場合 `$env:PSModulePath` は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-117">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="cfa9f-118">インストールされているモジュールを表示するには、を使用 `Get-InstalledModule` します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-118">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="cfa9f-119">例</span><span class="sxs-lookup"><span data-stu-id="cfa9f-119">EXAMPLES</span></span>

### <span data-ttu-id="cfa9f-120">例 1: すべてのモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="cfa9f-120">Example 1: Update all modules</span></span>

<span data-ttu-id="cfa9f-121">この例では、オンラインギャラリーで、インストールされているすべてのモジュールを最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-121">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="cfa9f-122">例 2: 名前を指定してモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="cfa9f-122">Example 2: Update a module by name</span></span>

<span data-ttu-id="cfa9f-123">この例では、オンラインギャラリーで、特定のモジュールを最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-123">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="cfa9f-124">`Update-Module`**Name** パラメーターを使用して、特定のモジュール **SpeculationControl** を更新します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-124">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl** .</span></span>

### <span data-ttu-id="cfa9f-125">例 3: what-if Update-Module 実行を表示する</span><span class="sxs-lookup"><span data-stu-id="cfa9f-125">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="cfa9f-126">この例では、what-if シナリオを実行して、が実行された場合の動作を示し `Update-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-126">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="cfa9f-127">コマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-127">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="cfa9f-128">`Update-Module`**WhatIf** パラメーターを使用して、が実行された場合の動作を表示し `Update-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-128">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="cfa9f-129">例 4: 指定したバージョンにモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="cfa9f-129">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="cfa9f-130">この例では、モジュールが特定のバージョンに更新されます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-130">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="cfa9f-131">オンラインギャラリーにバージョンが存在する必要があります。指定しないと、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-131">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="cfa9f-132">`Update-Module`**Name** パラメーターを使用して、モジュール **SpeculationControl** を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-132">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl** .</span></span> <span data-ttu-id="cfa9f-133">**RequiredVersion** パラメーターは、バージョン **1.0.14** を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-133">The **RequiredVersion** parameter specifies the version, **1.0.14** .</span></span>

### <span data-ttu-id="cfa9f-134">例 5: 確認せずにモジュールを更新する</span><span class="sxs-lookup"><span data-stu-id="cfa9f-134">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="cfa9f-135">この例では、オンラインギャラリーから最新バージョンにモジュールを更新する確認を要求しません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-135">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="cfa9f-136">モジュールが既にインストールされている場合は、 **Force** パラメーターを指定するとモジュールが再インストールされます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-136">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="cfa9f-137">`Update-Module`**Name** パラメーターを使用して、モジュール **SpeculationControl** を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-137">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl** .</span></span> <span data-ttu-id="cfa9f-138">**Force** パラメーターは、ユーザーの確認を要求せずにモジュールを更新します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-138">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="cfa9f-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cfa9f-139">PARAMETERS</span></span>

### <span data-ttu-id="cfa9f-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="cfa9f-140">-AcceptLicense</span></span>

<span data-ttu-id="cfa9f-141">パッケージで必要な場合は、インストール中にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="cfa9f-142">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="cfa9f-142">-AllowPrerelease</span></span>

<span data-ttu-id="cfa9f-143">では、プレリリースとマークされた新しいモジュールを使用してモジュールを更新できます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-143">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="cfa9f-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cfa9f-144">-Confirm</span></span>

<span data-ttu-id="cfa9f-145">実行前に確認メッセージを表示 `Update-Module` します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-145">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="cfa9f-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="cfa9f-146">-Credential</span></span>

<span data-ttu-id="cfa9f-147">モジュールを更新する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-147">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="cfa9f-148">-Force</span><span class="sxs-lookup"><span data-stu-id="cfa9f-148">-Force</span></span>

<span data-ttu-id="cfa9f-149">確認を要求するメッセージを表示せずに、指定された各モジュールを強制的に更新します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-149">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="cfa9f-150">モジュールが既にインストールされている場合、 **強制的** にモジュールを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-150">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="cfa9f-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="cfa9f-151">-MaximumVersion</span></span>

<span data-ttu-id="cfa9f-152">更新する1つのモジュールの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-152">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="cfa9f-153">複数のモジュールを更新しようとしている場合、このパラメーターを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-153">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="cfa9f-154">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-154">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="cfa9f-155">-Name</span><span class="sxs-lookup"><span data-stu-id="cfa9f-155">-Name</span></span>

<span data-ttu-id="cfa9f-156">更新する1つ以上のモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-156">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="cfa9f-157">`Update-Module``$env:PSModulePath`更新するモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-157">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="cfa9f-158">指定したモジュール名のに一致するものが見つからない場合は `$env:PSModulePath` 、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-158">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="cfa9f-159">モジュール名にはワイルドカードを許容します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-159">Wildcards are accepted in module names.</span></span> <span data-ttu-id="cfa9f-160">指定した名前にワイルドカード文字を追加し、一致するものが見つからない場合は、エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-160">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

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

### <span data-ttu-id="cfa9f-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="cfa9f-161">-PassThru</span></span>

<span data-ttu-id="cfa9f-162">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-162">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="cfa9f-163">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-163">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="cfa9f-164">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="cfa9f-164">-Proxy</span></span>

<span data-ttu-id="cfa9f-165">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-165">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="cfa9f-166">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="cfa9f-166">-ProxyCredential</span></span>

<span data-ttu-id="cfa9f-167">**プロキシ** パラメーターによって指定されたプロキシサーバーを使用する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-167">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="cfa9f-168">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="cfa9f-168">-RequiredVersion</span></span>

<span data-ttu-id="cfa9f-169">インストールされている既存のモジュールを更新するための正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-169">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="cfa9f-170">**RequiredVersion** によって指定されたバージョンがオンラインギャラリーに存在している必要があります。または、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-170">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="cfa9f-171">1つのコマンドで複数のモジュールが更新された場合、 **RequiredVersion** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-171">If more than one module is updated in a single command, you can't use **RequiredVersion** .</span></span>

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

### <span data-ttu-id="cfa9f-172">-スコープ</span><span class="sxs-lookup"><span data-stu-id="cfa9f-172">-Scope</span></span>

<span data-ttu-id="cfa9f-173">モジュールのインストール スコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-173">Specifies the installation scope of the module.</span></span> <span data-ttu-id="cfa9f-174">このパラメーターに指定できる値は **AllUsers** と **CurrentUser** です。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-174">The acceptable values for this parameter are **AllUsers** and **CurrentUser** .</span></span> <span data-ttu-id="cfa9f-175">**スコープ** が指定されていない場合、更新プログラムは **CurrentUser** スコープにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-175">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="cfa9f-176">**AllUsers** スコープには管理者特権が必要です。また、コンピューターのすべてのユーザーがアクセスできる場所にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-176">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="cfa9f-177">**CurrentUser** では、昇格されたアクセス許可は必要ありません。また、コンピューターの現在のユーザーのみがアクセスできる場所にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-177">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="cfa9f-178">**スコープ** が定義されていない場合、既定値は PowerShellGet のバージョンに基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-178">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="cfa9f-179">PowerShellGet バージョン2.1.0 以降では、既定値は **CurrentUser** で、インストールの昇格は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-179">In PowerShellGet versions 2.1.0 and above, the default is **CurrentUser** , which does not require elevation for install.</span></span>
- <span data-ttu-id="cfa9f-180">PowerShellGet 1.x バージョンでは、 **Scope** パラメーターは使用できません。既定値は **AllUsers** で、インストールの昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-180">In PowerShellGet 1.x - 2.0.x versions, the **Scope** parameter is not available and the default is **AllUsers** , which requires elevation for install.</span></span>

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

### <span data-ttu-id="cfa9f-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cfa9f-181">-WhatIf</span></span>

<span data-ttu-id="cfa9f-182">が実行された場合に何が起こるか `Update-Module` を示します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-182">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="cfa9f-183">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-183">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="cfa9f-184">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfa9f-184">CommonParameters</span></span>

<span data-ttu-id="cfa9f-185">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cfa9f-186">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cfa9f-187">入力</span><span class="sxs-lookup"><span data-stu-id="cfa9f-187">INPUTS</span></span>

### <span data-ttu-id="cfa9f-188">System.String[]</span><span class="sxs-lookup"><span data-stu-id="cfa9f-188">System.String[]</span></span>

### <span data-ttu-id="cfa9f-189">System.String</span><span class="sxs-lookup"><span data-stu-id="cfa9f-189">System.String</span></span>

### <span data-ttu-id="cfa9f-190">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="cfa9f-190">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="cfa9f-191">System.Uri</span><span class="sxs-lookup"><span data-stu-id="cfa9f-191">System.Uri</span></span>

## <span data-ttu-id="cfa9f-192">出力</span><span class="sxs-lookup"><span data-stu-id="cfa9f-192">OUTPUTS</span></span>

### <span data-ttu-id="cfa9f-193">System.Object</span><span class="sxs-lookup"><span data-stu-id="cfa9f-193">System.Object</span></span>

## <span data-ttu-id="cfa9f-194">注</span><span class="sxs-lookup"><span data-stu-id="cfa9f-194">NOTES</span></span>

<span data-ttu-id="cfa9f-195">PowerShell バージョン6.0 以降では、既定のインストールスコープは常に **CurrentUser** です。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-195">For PowerShell version 6.0 and above, the default installation scope is always **CurrentUser** .</span></span>
<span data-ttu-id="cfa9f-196">**CurrentUser** のモジュール更新プログラムには、 `$home\Documents\PowerShell\Modules` 昇格されたアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-196">Module updates for **CurrentUser** , `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span> <span data-ttu-id="cfa9f-197">**AllUsers** のモジュール更新プログラムには、 `$env:ProgramFiles\PowerShell\Modules` 昇格されたアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-197">Module updates for **AllUsers** , `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span>

<span data-ttu-id="cfa9f-198">`Update-Module` powershell 3.0 以降の PowerShell で、windows 7 または Windows 2008 R2 以降のリリースの Windows で実行されます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-198">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="cfa9f-199">**Name** パラメーターで指定したモジュールがを使用してインストールされなかった場合は `Install-Module` 、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-199">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="cfa9f-200">を実行すると `Update-Module` 、オンラインギャラリーからインストールしたモジュールでのみ実行でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-200">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="cfa9f-201">が `Update-Module` 使用中のバイナリを更新しようとすると、は `Update-Module` 問題のプロセスを識別するエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-201">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="cfa9f-202">ユーザーには、プロセスが停止した後に再試行するように通知され `Update-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="cfa9f-202">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="cfa9f-203">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cfa9f-203">RELATED LINKS</span></span>

[<span data-ttu-id="cfa9f-204">Find-Module</span><span class="sxs-lookup"><span data-stu-id="cfa9f-204">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="cfa9f-205">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="cfa9f-205">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="cfa9f-206">Install-Module</span><span class="sxs-lookup"><span data-stu-id="cfa9f-206">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="cfa9f-207">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="cfa9f-207">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="cfa9f-208">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="cfa9f-208">Uninstall-Module</span></span>](Uninstall-Module.md)
