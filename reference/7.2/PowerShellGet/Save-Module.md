---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: df5056b4402664602409388825c8b2b8acd4e02f
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600988"
---
# <span data-ttu-id="1fee8-102">Save-Module</span><span class="sxs-lookup"><span data-stu-id="1fee8-102">Save-Module</span></span>

## <span data-ttu-id="1fee8-103">概要</span><span class="sxs-lookup"><span data-stu-id="1fee8-103">SYNOPSIS</span></span>
<span data-ttu-id="1fee8-104">モジュールとその依存関係をローカルコンピューターに保存しますが、モジュールはインストールしません。</span><span class="sxs-lookup"><span data-stu-id="1fee8-104">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="1fee8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1fee8-105">SYNTAX</span></span>

### <span data-ttu-id="1fee8-106">NameAndPathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="1fee8-106">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1fee8-107">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="1fee8-107">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1fee8-108">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="1fee8-108">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1fee8-109">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="1fee8-109">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1fee8-110">Description</span><span class="sxs-lookup"><span data-stu-id="1fee8-110">DESCRIPTION</span></span>

<span data-ttu-id="1fee8-111">この `Save-Module` コマンドレットは、登録されているリポジトリからモジュールと依存関係をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="1fee8-111">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="1fee8-112">`Save-Module` 最新バージョンのモジュールをダウンロードして保存します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-112">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="1fee8-113">ファイルは、ローカルコンピューター上の指定されたパスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-113">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="1fee8-114">モジュールがインストールされていませんが、管理者が内容を検査することができます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-114">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="1fee8-115">保存したモジュールは、オフラインコンピューターの適切な場所にコピーでき `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-115">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="1fee8-116">`Get-PSRepository` ローカルコンピューターの登録済みリポジトリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-116">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="1fee8-117">コマンドレットを使用して、 `Find-Module` 登録されているリポジトリを検索できます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-117">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="1fee8-118">例</span><span class="sxs-lookup"><span data-stu-id="1fee8-118">EXAMPLES</span></span>

### <span data-ttu-id="1fee8-119">例 1: モジュールを保存する</span><span class="sxs-lookup"><span data-stu-id="1fee8-119">Example 1: Save a module</span></span>

<span data-ttu-id="1fee8-120">この例では、モジュールとその依存関係がローカルコンピューターに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-120">In this example, a module and its dependencies are saved to the local computer.</span></span>

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

<span data-ttu-id="1fee8-121">`Save-Module`**Name** パラメーターを使用して、モジュールの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-121">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="1fee8-122">**Path** パラメーターでは、ダウンロードしたモジュールを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-122">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="1fee8-123">**Repository** パラメーターは、登録されているリポジトリ **PSGallery** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-123">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="1fee8-124">ダウンロードが完了すると、 `Get-ChildItem` ファイルが格納されている **パス** の内容がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-124">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="1fee8-125">例 2: モジュールの特定のバージョンを保存する</span><span class="sxs-lookup"><span data-stu-id="1fee8-125">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="1fee8-126">この例では、 **MaximumVersion** や **RequiredVersion** などのパラメーターを使用して、モジュールのバージョンを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-126">This example shows how to use a parameter such as **MaximumVersion**, or **RequiredVersion** to specify a module version.</span></span>

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

<span data-ttu-id="1fee8-127">`Save-Module`**Name** パラメーターを使用して、モジュールの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-127">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="1fee8-128">**Path** パラメーターでは、ダウンロードしたモジュールを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-128">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="1fee8-129">**Repository** パラメーターは、登録されているリポジトリ **PSGallery** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-129">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="1fee8-130">**MaximumVersion** は、バージョン **2.1.0** をダウンロードして保存することを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-130">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="1fee8-131">ダウンロードが完了すると、 `Get-ChildItem` ファイルが格納されている **パス** の内容がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-131">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="1fee8-132">例 3: 特定のバージョンのモジュールを検索して保存する</span><span class="sxs-lookup"><span data-stu-id="1fee8-132">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="1fee8-133">この例では、必要なモジュールバージョンがリポジトリにあり、ローカルコンピューターに保存されています。</span><span class="sxs-lookup"><span data-stu-id="1fee8-133">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

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

<span data-ttu-id="1fee8-134">`Find-Module`**Name** パラメーターを使用して、モジュールの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-134">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="1fee8-135">**Repository** パラメーターは、登録されているリポジトリ **PSGallery** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-135">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="1fee8-136">**RequiredVersion** バージョン **1.6.5** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-136">**RequiredVersion** specifies version **1.6.5**.</span></span>

<span data-ttu-id="1fee8-137">オブジェクトは、パイプライン内でに送信され `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-137">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="1fee8-138">**Path** パラメーターでは、ダウンロードしたモジュールを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-138">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="1fee8-139">ダウンロードが完了すると、 `Get-ChildItem` ファイルが格納されている **パス** の内容がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-139">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="1fee8-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1fee8-140">PARAMETERS</span></span>

### <span data-ttu-id="1fee8-141">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="1fee8-141">-AcceptLicense</span></span>

<span data-ttu-id="1fee8-142">パッケージで必要な場合は、使用許諾契約書に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-142">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="1fee8-143">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="1fee8-143">-AllowPrerelease</span></span>

<span data-ttu-id="1fee8-144">プレリリースとしてマークされているモジュールを保存できます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-144">Allows you to save a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="1fee8-145">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1fee8-145">-Confirm</span></span>

<span data-ttu-id="1fee8-146">を実行する前に確認メッセージを表示し `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-146">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="1fee8-147">-Credential</span><span class="sxs-lookup"><span data-stu-id="1fee8-147">-Credential</span></span>

<span data-ttu-id="1fee8-148">モジュールを保存する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-148">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="1fee8-149">-Force</span><span class="sxs-lookup"><span data-stu-id="1fee8-149">-Force</span></span>

<span data-ttu-id="1fee8-150">`Save-Module`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-150">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="1fee8-151">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1fee8-151">-InputObject</span></span>

<span data-ttu-id="1fee8-152">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1fee8-152">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="1fee8-153">たとえば、 `Find-Module` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-153">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="1fee8-154">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1fee8-154">-LiteralPath</span></span>

<span data-ttu-id="1fee8-155">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-155">Specifies a path to one or more locations.</span></span> <span data-ttu-id="1fee8-156">**LiteralPath** パラメーターの値は、入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-156">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="1fee8-157">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="1fee8-157">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="1fee8-158">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-158">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="1fee8-159">PowerShell では、単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="1fee8-159">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="1fee8-160">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="1fee8-160">-MaximumVersion</span></span>

<span data-ttu-id="1fee8-161">保存するモジュールの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-161">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="1fee8-162">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1fee8-162">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="1fee8-163">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="1fee8-163">-MinimumVersion</span></span>

<span data-ttu-id="1fee8-164">保存する1つのモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-164">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="1fee8-165">複数のモジュールをインストールしようとする場合、このパラメーターを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="1fee8-165">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="1fee8-166">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1fee8-166">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="1fee8-167">-Name</span><span class="sxs-lookup"><span data-stu-id="1fee8-167">-Name</span></span>

<span data-ttu-id="1fee8-168">保存するモジュールの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-168">Specifies an array of names of modules to save.</span></span>

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

### <span data-ttu-id="1fee8-169">-Path</span><span class="sxs-lookup"><span data-stu-id="1fee8-169">-Path</span></span>

<span data-ttu-id="1fee8-170">保存されているモジュールを格納するローカルコンピューター上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-170">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="1fee8-171">ワイルドカード文字を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-171">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="1fee8-172">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="1fee8-172">-Proxy</span></span>

<span data-ttu-id="1fee8-173">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-173">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="1fee8-174">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="1fee8-174">-ProxyCredential</span></span>

<span data-ttu-id="1fee8-175">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-175">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="1fee8-176">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="1fee8-176">-Repository</span></span>

<span data-ttu-id="1fee8-177">を実行して登録されているリポジトリのフレンドリ名を指定し `Register-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-177">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="1fee8-178">`Get-PSRepository`登録されたリポジトリを表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-178">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="1fee8-179">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="1fee8-179">-RequiredVersion</span></span>

<span data-ttu-id="1fee8-180">保存するモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-180">Specifies the exact version number of the module to save.</span></span>

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

### <span data-ttu-id="1fee8-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1fee8-181">-WhatIf</span></span>

<span data-ttu-id="1fee8-182">が実行された場合に何が起こるかを示し `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1fee8-182">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="1fee8-183">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1fee8-183">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="1fee8-184">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fee8-184">CommonParameters</span></span>

<span data-ttu-id="1fee8-185">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1fee8-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1fee8-186">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fee8-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1fee8-187">入力</span><span class="sxs-lookup"><span data-stu-id="1fee8-187">INPUTS</span></span>

### <span data-ttu-id="1fee8-188">System.String[]</span><span class="sxs-lookup"><span data-stu-id="1fee8-188">System.String[]</span></span>

### <span data-ttu-id="1fee8-189">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="1fee8-189">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="1fee8-190">System.String</span><span class="sxs-lookup"><span data-stu-id="1fee8-190">System.String</span></span>

### <span data-ttu-id="1fee8-191">System.Uri</span><span class="sxs-lookup"><span data-stu-id="1fee8-191">System.Uri</span></span>

### <span data-ttu-id="1fee8-192">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="1fee8-192">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="1fee8-193">出力</span><span class="sxs-lookup"><span data-stu-id="1fee8-193">OUTPUTS</span></span>

### <span data-ttu-id="1fee8-194">System.Object</span><span class="sxs-lookup"><span data-stu-id="1fee8-194">System.Object</span></span>

## <span data-ttu-id="1fee8-195">注</span><span class="sxs-lookup"><span data-stu-id="1fee8-195">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fee8-196">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="1fee8-196">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="1fee8-197">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1fee8-197">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="1fee8-198">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="1fee8-198">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="1fee8-199">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fee8-199">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="1fee8-200">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1fee8-200">RELATED LINKS</span></span>
