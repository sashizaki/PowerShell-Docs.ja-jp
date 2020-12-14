---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: fe737a8e248c95a39a430f59ae76d7981aa9c33a
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890435"
---
# <span data-ttu-id="c6607-103">Save-Module</span><span class="sxs-lookup"><span data-stu-id="c6607-103">Save-Module</span></span>

## <span data-ttu-id="c6607-104">概要</span><span class="sxs-lookup"><span data-stu-id="c6607-104">SYNOPSIS</span></span>
<span data-ttu-id="c6607-105">モジュールとその依存関係をローカルコンピューターに保存しますが、モジュールはインストールしません。</span><span class="sxs-lookup"><span data-stu-id="c6607-105">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="c6607-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c6607-106">SYNTAX</span></span>

### <span data-ttu-id="c6607-107">NameAndPathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="c6607-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6607-108">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="c6607-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6607-109">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="c6607-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6607-110">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="c6607-110">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c6607-111">Description</span><span class="sxs-lookup"><span data-stu-id="c6607-111">DESCRIPTION</span></span>

<span data-ttu-id="c6607-112">この `Save-Module` コマンドレットは、登録されているリポジトリからモジュールと依存関係をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c6607-112">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="c6607-113">`Save-Module` 最新バージョンのモジュールをダウンロードして保存します。</span><span class="sxs-lookup"><span data-stu-id="c6607-113">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="c6607-114">ファイルは、ローカルコンピューター上の指定されたパスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c6607-114">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="c6607-115">モジュールがインストールされていませんが、管理者が内容を検査することができます。</span><span class="sxs-lookup"><span data-stu-id="c6607-115">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="c6607-116">保存したモジュールは、オフラインコンピューターの適切な場所にコピーでき `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="c6607-116">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="c6607-117">`Get-PSRepository` ローカルコンピューターの登録済みリポジトリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6607-117">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="c6607-118">コマンドレットを使用して、 `Find-Module` 登録されているリポジトリを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c6607-118">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="c6607-119">例</span><span class="sxs-lookup"><span data-stu-id="c6607-119">EXAMPLES</span></span>

### <span data-ttu-id="c6607-120">例 1: モジュールを保存する</span><span class="sxs-lookup"><span data-stu-id="c6607-120">Example 1: Save a module</span></span>

<span data-ttu-id="c6607-121">この例では、モジュールとその依存関係がローカルコンピューターに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c6607-121">In this example, a module and its dependencies are saved to the local computer.</span></span>

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery
Get-ChildItem -Path C:\Test\Modules
```

```Output
    Directory: C:\Test\Modules

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:31                PackageManagement
d-----         7/1/2019     13:31                PowerShellGet
```

<span data-ttu-id="c6607-122">`Save-Module`**Name** パラメーターを使用して、モジュールの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-122">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="c6607-123">**Path** パラメーターでは、ダウンロードしたモジュールを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-123">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="c6607-124">**Repository** パラメーターは、登録されているリポジトリ **PSGallery** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-124">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="c6607-125">ダウンロードが完了すると、 `Get-ChildItem` ファイルが格納されている **パス** の内容がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6607-125">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="c6607-126">例 2: モジュールの特定のバージョンを保存する</span><span class="sxs-lookup"><span data-stu-id="c6607-126">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="c6607-127">この例では、 **MaximumVersion** や **RequiredVersion** などのパラメーターを使用して、モジュールのバージョンを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6607-127">This example shows how to use a parameter such as **MaximumVersion**, or **RequiredVersion** to specify a module version.</span></span>

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery -MaximumVersion 2.1.0
Get-ChildItem -Path C:\Test\Modules\PowerShellGet\
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:40                2.1.0
```

<span data-ttu-id="c6607-128">`Save-Module`**Name** パラメーターを使用して、モジュールの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-128">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="c6607-129">**Path** パラメーターでは、ダウンロードしたモジュールを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-129">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="c6607-130">**Repository** パラメーターは、登録されているリポジトリ **PSGallery** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-130">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="c6607-131">**MaximumVersion** は、バージョン **2.1.0** をダウンロードして保存することを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-131">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="c6607-132">ダウンロードが完了すると、 `Get-ChildItem` ファイルが格納されている **パス** の内容がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6607-132">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="c6607-133">例 3: 特定のバージョンのモジュールを検索して保存する</span><span class="sxs-lookup"><span data-stu-id="c6607-133">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="c6607-134">この例では、必要なモジュールバージョンがリポジトリにあり、ローカルコンピューターに保存されています。</span><span class="sxs-lookup"><span data-stu-id="c6607-134">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery -RequiredVersion 1.6.5 |
  Save-Module -Path C:\Test\Modules
Get-ChildItem -Path C:\Test\Modules\PowerShellGet
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     14:04                1.6.5
```

<span data-ttu-id="c6607-135">`Find-Module`**Name** パラメーターを使用して、モジュールの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-135">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="c6607-136">**Repository** パラメーターは、登録されているリポジトリ **PSGallery** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-136">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="c6607-137">**RequiredVersion** バージョン **1.6.5** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-137">**RequiredVersion** specifies version **1.6.5**.</span></span>

<span data-ttu-id="c6607-138">オブジェクトは、パイプライン内でに送信され `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="c6607-138">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="c6607-139">**Path** パラメーターでは、ダウンロードしたモジュールを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-139">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="c6607-140">ダウンロードが完了すると、 `Get-ChildItem` ファイルが格納されている **パス** の内容がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6607-140">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="c6607-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c6607-141">PARAMETERS</span></span>

### <span data-ttu-id="c6607-142">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="c6607-142">-AcceptLicense</span></span>

<span data-ttu-id="c6607-143">パッケージで必要な場合は、使用許諾契約書に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="c6607-143">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="c6607-144">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="c6607-144">-AllowPrerelease</span></span>

<span data-ttu-id="c6607-145">プレリリースとしてマークされているモジュールを保存できます。</span><span class="sxs-lookup"><span data-stu-id="c6607-145">Allows you to save a module marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c6607-146">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c6607-146">-Confirm</span></span>

<span data-ttu-id="c6607-147">を実行する前に確認メッセージを表示し `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="c6607-147">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="c6607-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="c6607-148">-Credential</span></span>

<span data-ttu-id="c6607-149">モジュールを保存する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-149">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="c6607-150">-Force</span><span class="sxs-lookup"><span data-stu-id="c6607-150">-Force</span></span>

<span data-ttu-id="c6607-151">`Save-Module`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="c6607-151">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c6607-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c6607-152">-InputObject</span></span>

<span data-ttu-id="c6607-153">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c6607-153">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="c6607-154">たとえば、 `Find-Module` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="c6607-154">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObjectAndLiteralPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c6607-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c6607-155">-LiteralPath</span></span>

<span data-ttu-id="c6607-156">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-156">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c6607-157">**LiteralPath** パラメーターの値は、入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6607-157">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="c6607-158">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="c6607-158">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c6607-159">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c6607-159">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="c6607-160">PowerShell では、単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="c6607-160">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndLiteralPathParameterSet, InputObjectAndLiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c6607-161">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c6607-161">-MaximumVersion</span></span>

<span data-ttu-id="c6607-162">保存するモジュールの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-162">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="c6607-163">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6607-163">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c6607-164">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c6607-164">-MinimumVersion</span></span>

<span data-ttu-id="c6607-165">保存する1つのモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-165">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="c6607-166">複数のモジュールをインストールしようとする場合、このパラメーターを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6607-166">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="c6607-167">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6607-167">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c6607-168">-Name</span><span class="sxs-lookup"><span data-stu-id="c6607-168">-Name</span></span>

<span data-ttu-id="c6607-169">保存するモジュールの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-169">Specifies an array of names of modules to save.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c6607-170">-Path</span><span class="sxs-lookup"><span data-stu-id="c6607-170">-Path</span></span>

<span data-ttu-id="c6607-171">保存されているモジュールを格納するローカルコンピューター上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-171">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="c6607-172">ワイルドカード文字を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="c6607-172">Accepts wildcard characters.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="c6607-173">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="c6607-173">-Proxy</span></span>

<span data-ttu-id="c6607-174">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-174">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="c6607-175">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="c6607-175">-ProxyCredential</span></span>

<span data-ttu-id="c6607-176">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-176">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="c6607-177">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="c6607-177">-Repository</span></span>

<span data-ttu-id="c6607-178">を実行して登録されているリポジトリのフレンドリ名を指定し `Register-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="c6607-178">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="c6607-179">`Get-PSRepository`登録されたリポジトリを表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6607-179">Use `Get-PSRepository` to display registered repositories.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c6607-180">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="c6607-180">-RequiredVersion</span></span>

<span data-ttu-id="c6607-181">保存するモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6607-181">Specifies the exact version number of the module to save.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c6607-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c6607-182">-WhatIf</span></span>

<span data-ttu-id="c6607-183">が実行された場合に何が起こるかを示し `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="c6607-183">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="c6607-184">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c6607-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="c6607-185">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6607-185">CommonParameters</span></span>

<span data-ttu-id="c6607-186">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c6607-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c6607-187">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6607-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c6607-188">入力</span><span class="sxs-lookup"><span data-stu-id="c6607-188">INPUTS</span></span>

### <span data-ttu-id="c6607-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="c6607-189">System.String[]</span></span>

### <span data-ttu-id="c6607-190">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="c6607-190">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="c6607-191">System.String</span><span class="sxs-lookup"><span data-stu-id="c6607-191">System.String</span></span>

### <span data-ttu-id="c6607-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="c6607-192">System.Uri</span></span>

### <span data-ttu-id="c6607-193">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="c6607-193">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="c6607-194">出力</span><span class="sxs-lookup"><span data-stu-id="c6607-194">OUTPUTS</span></span>

### <span data-ttu-id="c6607-195">System.Object</span><span class="sxs-lookup"><span data-stu-id="c6607-195">System.Object</span></span>

## <span data-ttu-id="c6607-196">注</span><span class="sxs-lookup"><span data-stu-id="c6607-196">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6607-197">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c6607-197">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c6607-198">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c6607-198">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c6607-199">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6607-199">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c6607-200">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6607-200">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="c6607-201">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c6607-201">RELATED LINKS</span></span>
