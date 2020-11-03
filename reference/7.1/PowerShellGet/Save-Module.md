---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: 88ce556a366e67a911bf32eb5c13161a543f103f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215640"
---
# <span data-ttu-id="8c2b5-103">Save-Module</span><span class="sxs-lookup"><span data-stu-id="8c2b5-103">Save-Module</span></span>

## <span data-ttu-id="8c2b5-104">概要</span><span class="sxs-lookup"><span data-stu-id="8c2b5-104">SYNOPSIS</span></span>
<span data-ttu-id="8c2b5-105">モジュールとその依存関係をローカルコンピューターに保存しますが、モジュールはインストールしません。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-105">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="8c2b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8c2b5-106">SYNTAX</span></span>

### <span data-ttu-id="8c2b5-107">NameAndPathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="8c2b5-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8c2b5-108">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="8c2b5-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8c2b5-109">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="8c2b5-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8c2b5-110">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="8c2b5-110">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8c2b5-111">Description</span><span class="sxs-lookup"><span data-stu-id="8c2b5-111">DESCRIPTION</span></span>

<span data-ttu-id="8c2b5-112">この `Save-Module` コマンドレットは、登録されているリポジトリからモジュールと依存関係をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-112">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="8c2b5-113">`Save-Module` 最新バージョンのモジュールをダウンロードして保存します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-113">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="8c2b5-114">ファイルは、ローカルコンピューター上の指定されたパスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-114">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="8c2b5-115">モジュールがインストールされていませんが、管理者が内容を検査することができます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-115">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="8c2b5-116">保存したモジュールは、オフラインコンピューターの適切な場所にコピーでき `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-116">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="8c2b5-117">`Get-PSRepository` ローカルコンピューターの登録済みリポジトリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-117">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="8c2b5-118">コマンドレットを使用して、 `Find-Module` 登録されているリポジトリを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-118">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="8c2b5-119">例</span><span class="sxs-lookup"><span data-stu-id="8c2b5-119">EXAMPLES</span></span>

### <span data-ttu-id="8c2b5-120">例 1: モジュールを保存する</span><span class="sxs-lookup"><span data-stu-id="8c2b5-120">Example 1: Save a module</span></span>

<span data-ttu-id="8c2b5-121">この例では、モジュールとその依存関係がローカルコンピューターに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-121">In this example, a module and its dependencies are saved to the local computer.</span></span>

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

<span data-ttu-id="8c2b5-122">`Save-Module`**Name** パラメーターを使用して、モジュールの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-122">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet** .</span></span> <span data-ttu-id="8c2b5-123">**Path** パラメーターでは、ダウンロードしたモジュールを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-123">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="8c2b5-124">**Repository** パラメーターは、登録されているリポジトリ **PSGallery** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-124">The **Repository** parameter specifies a registered repository, **PSGallery** .</span></span> <span data-ttu-id="8c2b5-125">ダウンロードが完了すると、 `Get-ChildItem` ファイルが格納されている **パス** の内容がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-125">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="8c2b5-126">例 2: モジュールの特定のバージョンを保存する</span><span class="sxs-lookup"><span data-stu-id="8c2b5-126">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="8c2b5-127">この例では、 **MaximumVersion** や **RequiredVersion** などのパラメーターを使用して、モジュールのバージョンを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-127">This example shows how to use a parameter such as **MaximumVersion** , or **RequiredVersion** to specify a module version.</span></span>

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

<span data-ttu-id="8c2b5-128">`Save-Module`**Name** パラメーターを使用して、モジュールの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-128">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet** .</span></span> <span data-ttu-id="8c2b5-129">**Path** パラメーターでは、ダウンロードしたモジュールを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-129">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="8c2b5-130">**Repository** パラメーターは、登録されているリポジトリ **PSGallery** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-130">The **Repository** parameter specifies a registered repository, **PSGallery** .</span></span> <span data-ttu-id="8c2b5-131">**MaximumVersion** は、バージョン **2.1.0** をダウンロードして保存することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-131">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="8c2b5-132">ダウンロードが完了すると、 `Get-ChildItem` ファイルが格納されている **パス** の内容がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-132">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="8c2b5-133">例 3: 特定のバージョンのモジュールを検索して保存する</span><span class="sxs-lookup"><span data-stu-id="8c2b5-133">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="8c2b5-134">この例では、必要なモジュールバージョンがリポジトリにあり、ローカルコンピューターに保存されています。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-134">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

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

<span data-ttu-id="8c2b5-135">`Find-Module`**Name** パラメーターを使用して、モジュールの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-135">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet** .</span></span> <span data-ttu-id="8c2b5-136">**Repository** パラメーターは、登録されているリポジトリ **PSGallery** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-136">The **Repository** parameter specifies a registered repository, **PSGallery** .</span></span> <span data-ttu-id="8c2b5-137">**RequiredVersion** バージョン **1.6.5** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-137">**RequiredVersion** specifies version **1.6.5** .</span></span>

<span data-ttu-id="8c2b5-138">オブジェクトは、パイプライン内でに送信され `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-138">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="8c2b5-139">**Path** パラメーターでは、ダウンロードしたモジュールを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-139">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="8c2b5-140">ダウンロードが完了すると、 `Get-ChildItem` ファイルが格納されている **パス** の内容がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-140">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="8c2b5-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8c2b5-141">PARAMETERS</span></span>

### <span data-ttu-id="8c2b5-142">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="8c2b5-142">-AcceptLicense</span></span>

<span data-ttu-id="8c2b5-143">パッケージで必要な場合は、使用許諾契約書に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-143">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="8c2b5-144">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="8c2b5-144">-AllowPrerelease</span></span>

<span data-ttu-id="8c2b5-145">プレリリースとしてマークされているモジュールを保存できます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-145">Allows you to save a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="8c2b5-146">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8c2b5-146">-Confirm</span></span>

<span data-ttu-id="8c2b5-147">を実行する前に確認メッセージを表示し `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-147">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="8c2b5-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="8c2b5-148">-Credential</span></span>

<span data-ttu-id="8c2b5-149">モジュールを保存する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-149">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="8c2b5-150">-Force</span><span class="sxs-lookup"><span data-stu-id="8c2b5-150">-Force</span></span>

<span data-ttu-id="8c2b5-151">`Save-Module`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-151">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="8c2b5-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8c2b5-152">-InputObject</span></span>

<span data-ttu-id="8c2b5-153">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-153">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="8c2b5-154">たとえば、 `Find-Module` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-154">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="8c2b5-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8c2b5-155">-LiteralPath</span></span>

<span data-ttu-id="8c2b5-156">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-156">Specifies a path to one or more locations.</span></span> <span data-ttu-id="8c2b5-157">**LiteralPath** パラメーターの値は、入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-157">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="8c2b5-158">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-158">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8c2b5-159">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-159">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="8c2b5-160">PowerShell では、単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-160">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="8c2b5-161">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="8c2b5-161">-MaximumVersion</span></span>

<span data-ttu-id="8c2b5-162">保存するモジュールの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-162">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="8c2b5-163">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-163">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="8c2b5-164">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="8c2b5-164">-MinimumVersion</span></span>

<span data-ttu-id="8c2b5-165">保存する1つのモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-165">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="8c2b5-166">複数のモジュールをインストールしようとする場合、このパラメーターを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-166">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="8c2b5-167">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-167">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="8c2b5-168">-Name</span><span class="sxs-lookup"><span data-stu-id="8c2b5-168">-Name</span></span>

<span data-ttu-id="8c2b5-169">保存するモジュールの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-169">Specifies an array of names of modules to save.</span></span>

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

### <span data-ttu-id="8c2b5-170">-Path</span><span class="sxs-lookup"><span data-stu-id="8c2b5-170">-Path</span></span>

<span data-ttu-id="8c2b5-171">保存されているモジュールを格納するローカルコンピューター上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-171">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="8c2b5-172">ワイルドカード文字を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-172">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="8c2b5-173">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="8c2b5-173">-Proxy</span></span>

<span data-ttu-id="8c2b5-174">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-174">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="8c2b5-175">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="8c2b5-175">-ProxyCredential</span></span>

<span data-ttu-id="8c2b5-176">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-176">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="8c2b5-177">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="8c2b5-177">-Repository</span></span>

<span data-ttu-id="8c2b5-178">を実行して登録されているリポジトリのフレンドリ名を指定し `Register-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-178">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="8c2b5-179">`Get-PSRepository`登録されたリポジトリを表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-179">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="8c2b5-180">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="8c2b5-180">-RequiredVersion</span></span>

<span data-ttu-id="8c2b5-181">保存するモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-181">Specifies the exact version number of the module to save.</span></span>

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

### <span data-ttu-id="8c2b5-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8c2b5-182">-WhatIf</span></span>

<span data-ttu-id="8c2b5-183">が実行された場合に何が起こるかを示し `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-183">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="8c2b5-184">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="8c2b5-185">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c2b5-185">CommonParameters</span></span>

<span data-ttu-id="8c2b5-186">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8c2b5-187">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c2b5-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8c2b5-188">入力</span><span class="sxs-lookup"><span data-stu-id="8c2b5-188">INPUTS</span></span>

### <span data-ttu-id="8c2b5-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="8c2b5-189">System.String[]</span></span>

### <span data-ttu-id="8c2b5-190">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="8c2b5-190">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="8c2b5-191">System.String</span><span class="sxs-lookup"><span data-stu-id="8c2b5-191">System.String</span></span>

### <span data-ttu-id="8c2b5-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="8c2b5-192">System.Uri</span></span>

### <span data-ttu-id="8c2b5-193">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="8c2b5-193">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="8c2b5-194">出力</span><span class="sxs-lookup"><span data-stu-id="8c2b5-194">OUTPUTS</span></span>

### <span data-ttu-id="8c2b5-195">System.Object</span><span class="sxs-lookup"><span data-stu-id="8c2b5-195">System.Object</span></span>

## <span data-ttu-id="8c2b5-196">注</span><span class="sxs-lookup"><span data-stu-id="8c2b5-196">NOTES</span></span>

## <span data-ttu-id="8c2b5-197">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8c2b5-197">RELATED LINKS</span></span>

