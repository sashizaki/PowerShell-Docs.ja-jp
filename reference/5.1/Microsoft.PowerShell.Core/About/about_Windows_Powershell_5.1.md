---
description: Windows PowerShell 5.1 に含まれる新機能について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/17/2018
online version: https://docs.microsoft.com/powershell/module/?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_5。1
ms.openlocfilehash: 567af048dd137c0287c6eba4ccc42a77055c0c92
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224907"
---
# <a name="about_windows_powershell_51"></a><span data-ttu-id="aca7f-104">about_Windows_PowerShell_5。1</span><span class="sxs-lookup"><span data-stu-id="aca7f-104">about_Windows_PowerShell_5.1</span></span>

## <a name="short-description"></a><span data-ttu-id="aca7f-105">概要</span><span class="sxs-lookup"><span data-stu-id="aca7f-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="aca7f-106">Windows PowerShell 5.1 に含まれる新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-106">Describes new features that are included in Windows PowerShell 5.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="aca7f-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="aca7f-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="aca7f-108">Windows PowerShell 5.1 には、その用途を拡大し、使いやすさを向上させ、Windows ベースの環境をより簡単かつ包括的に制御および管理できるようにする重要な新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aca7f-108">Windows PowerShell 5.1 includes significant new features that extend its use, improve its usability, and allow you to control and manage Windows-based environments more easily and comprehensively.</span></span>

<span data-ttu-id="aca7f-109">Windows PowerShell 5.1 には下位互換性があります。</span><span class="sxs-lookup"><span data-stu-id="aca7f-109">Windows PowerShell 5.1 is backward-compatible.</span></span> <span data-ttu-id="aca7f-110">Windows PowerShell 4.0、Windows PowerShell 3.0、および Windows PowerShell 2.0 向けに設計されたコマンドレット、プロバイダー、モジュール、スナップイン、スクリプト、関数、およびプロファイルは、通常、変更なしで Windows PowerShell 5.1 で動作します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-110">Cmdlets, providers, modules, snap-ins, scripts, functions, and profiles that were designed for Windows PowerShell 4.0, Windows PowerShell 3.0, and Windows PowerShell 2.0 generally work in Windows PowerShell 5.1 without changes.</span></span>

- <span data-ttu-id="aca7f-111">新しいコマンドレット: ローカル ユーザーとグループ、Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="aca7f-111">New cmdlets: local users and groups; Get-ComputerInfo</span></span>
- <span data-ttu-id="aca7f-112">PowerShellGet では、署名付きモジュールの適用や JEA モジュールのインストールなどの機能強化が行われています。</span><span class="sxs-lookup"><span data-stu-id="aca7f-112">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="aca7f-113">PackageManagement では、コンテナー、CBS セットアップ、EXE ベースのセットアップ、CAB パッケージをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="aca7f-113">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="aca7f-114">DSC および PowerShell クラスにおけるデバッグ機能の強化</span><span class="sxs-lookup"><span data-stu-id="aca7f-114">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="aca7f-115">セキュリティの機能強化としては、プル サーバーからもたらされるカタログ署名付きモジュールの適用、PowerShellGet コマンドレットを使用するタイミングなどが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-115">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="aca7f-116">さまざまなユーザー要求と問題への対応</span><span class="sxs-lookup"><span data-stu-id="aca7f-116">Responses to a number of user requests and issues</span></span>

<span data-ttu-id="aca7f-117">Windows PowerShell 5.1 は、windows Server 2016 と Windows 10 に既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-117">Windows PowerShell 5.1 is installed by default on Windows Server 2016 and Windows 10.</span></span> <span data-ttu-id="aca7f-118">Windows Server 2012 R2、Windows 8.1 Enterprise、または Windows 8.1 Pro に Windows PowerShell 5.1 をインストールするには、「 [WMF 5.1 のインストールと構成](/powershell/scripting/wmf/setup/install-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aca7f-118">To install Windows PowerShell 5.1 on Windows Server 2012 R2, Windows 8.1 Enterprise, or Windows 8.1 Pro, see [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>
<span data-ttu-id="aca7f-119">Windows Management Framework 5.1 をインストールする前に、ダウンロードの詳細を読み、すべてのシステム要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aca7f-119">Be sure to read the download details, and meet all system requirements, before you install Windows Management Framework 5.1.</span></span>

<span data-ttu-id="aca7f-120">「 [Windows powershell の新機能](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50)」で、windows powershell 5.1 の変更点を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-120">You can also read about changes to Windows PowerShell 5.1 in [What's New in Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).</span></span>

## <a name="new-scenarios-and-features-in-wmf-51"></a><span data-ttu-id="aca7f-121">WMF 5.1 の新しいシナリオと機能</span><span class="sxs-lookup"><span data-stu-id="aca7f-121">New Scenarios and Features in WMF 5.1</span></span>

> <span data-ttu-id="aca7f-122">注意: この情報は暫定版であり、変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="aca7f-122">Note: This information is preliminary and subject to change.</span></span>

### <a name="powershell-editions"></a><span data-ttu-id="aca7f-123">PowerShell のエディション</span><span class="sxs-lookup"><span data-stu-id="aca7f-123">PowerShell Editions</span></span>
<span data-ttu-id="aca7f-124">PowerShell は、バージョン 5.1 以降、機能セットとプラットフォーム互換性が異なるさまざまなエディションが提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="aca7f-124">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="aca7f-125">**Desktop Edition:** .NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="aca7f-125">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="aca7f-126">**Core Edition:**.NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-126">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="aca7f-127">**PowerShell のエディションの使用に関する詳細**</span><span class="sxs-lookup"><span data-stu-id="aca7f-127">**Learn more about using PowerShell Editions**</span></span>

- [<span data-ttu-id="aca7f-128">$PSVersionTable を使用して PowerShell の実行エディションを特定する</span><span class="sxs-lookup"><span data-stu-id="aca7f-128">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="aca7f-129">PSEdition パラメーターを使用して CompatiblePSEditions で Get-Module の結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="aca7f-129">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="aca7f-130">互換性のある PowerShell のエディションで実行しない場合はスクリプトを実行させない</span><span class="sxs-lookup"><span data-stu-id="aca7f-130">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/scripting/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="aca7f-131">特定の PowerShell バージョンに対するモジュールの互換性を宣言する</span><span class="sxs-lookup"><span data-stu-id="aca7f-131">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a><span data-ttu-id="aca7f-132">カタログ コマンドレット</span><span class="sxs-lookup"><span data-stu-id="aca7f-132">Catalog Cmdlets</span></span>

<span data-ttu-id="aca7f-133">[Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)) モジュールに新しいコマンドレットが 2 つ追加されました。Windows カタログ ファイルを生成し、検証するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="aca7f-133">Two new cmdlets have been added in the [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)) module; these generate and validate Windows catalog files.</span></span>

#### <a name="new-filecatalog"></a><span data-ttu-id="aca7f-134">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="aca7f-134">New-FileCatalog</span></span>

<span data-ttu-id="aca7f-135">New-FileCatalog は、一連のフォルダーやファイルに対して Windows カタログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-135">New-FileCatalog creates a Windows catalog file for set of folders and files.</span></span>
<span data-ttu-id="aca7f-136">このカタログ ファイルには、指定されたパスのすべてのファイルのハッシュが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aca7f-136">This catalog file contains hashes for all files in specified paths.</span></span> <span data-ttu-id="aca7f-137">ユーザーは一連のフォルダーと共に、それらのフォルダーを表すカタログ ファイルを配信できます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-137">Users can distribute the set of folders along with corresponding catalog file representing those folders.</span></span> <span data-ttu-id="aca7f-138">カタログ作成時刻以降、フォルダーに変更が加えられたかどうかを検証するとき、この情報が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-138">This information is useful to validate whether any changes have been made to the folders since catalog creation time.</span></span>

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="aca7f-139">カタログ バージョン 1 と 2 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aca7f-139">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="aca7f-140">バージョン 1 は SHA1 ハッシュ アルゴリズムを使用して、バージョン 2 は SHA256 ハッシュ アルゴリズムを使用してファイル ハッシュを作成します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-140">Version 1 uses the SHA1 hashing algorithm to create file hashes; version 2 uses SHA256.</span></span> <span data-ttu-id="aca7f-141">*Windows Server 2008 R2* と *Windows 7* はカタログ バージョン 2 に対応していません。</span><span class="sxs-lookup"><span data-stu-id="aca7f-141">Catalog version 2 is not supported on *Windows Server 2008 R2* or *Windows 7*.</span></span> <span data-ttu-id="aca7f-142">カタログ バージョン 2 は *Windows 8* 、 *Windows Server 2012* 以降のオペレーティング システムで利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aca7f-142">You should use catalog version 2 on *Windows 8* , *Windows Server 2012* , and later operating systems.</span></span>

<span data-ttu-id="aca7f-143">カタログ ファイルの整合性を検証するために (上記の例では Pester.cat)、[Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) コマンドレットで署名します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-143">To verify the integrity of catalog file (Pester.cat in above example), sign it using [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) cmdlet.</span></span>

#### <a name="test-filecatalog"></a><span data-ttu-id="aca7f-144">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="aca7f-144">Test-FileCatalog</span></span>

<span data-ttu-id="aca7f-145">Test-FileCatalog は、一連のフォルダーを表すカタログを検証します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-145">Test-FileCatalog validates the catalog representing a set of folders.</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="aca7f-146">このコマンドレットは、 *カタログ* で見つかったすべてのファイル ハッシュとその相対パスを *ディスク* のそれらと比較します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-146">This cmdlet compares all the files hashes and their relative paths found in *catalog* with ones on *disk*.</span></span> <span data-ttu-id="aca7f-147">ファイル ハッシュとパスの間に不一致が検出された場合、 *ValidationFailed* というステータスを返します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-147">If it detects any mismatch between file hashes and paths it returns the status as *ValidationFailed*.</span></span> <span data-ttu-id="aca7f-148">*-Detailed* パラメーターを利用し、この情報をすべて取得できます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-148">Users can retrieve all this information by using the *-Detailed* parameter.</span></span> <span data-ttu-id="aca7f-149">*署名* プロパティには、カタログの署名ステータスも表示されます。これは、カタログ ファイルで [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) コマンドレットを呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="aca7f-149">It also displays signing status of catalog in *Signature* property which is equivalent to calling [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) cmdlet on the catalog file.</span></span> <span data-ttu-id="aca7f-150">*-FilesToSkip* パラメーターを利用し、検証中にファイルをスキップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-150">Users can also skip any file during validation by using the *-FilesToSkip* parameter.</span></span>

### <a name="module-analysis-cache"></a><span data-ttu-id="aca7f-151">モジュール分析キャッシュ</span><span class="sxs-lookup"><span data-stu-id="aca7f-151">Module Analysis Cache</span></span>

<span data-ttu-id="aca7f-152">WMF 5.1 以降の PowerShell では、エクスポートするコマンドなど、モジュールに関するデータのキャッシュに使用されるファイルを制御できます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-152">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="aca7f-153">既定では、このキャッシュは `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-153">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="aca7f-154">キャッシュは、通常、起動時にコマンドを検索するときに読み取られ、モジュールのインポート後しばらくしてバックグラウンド スレッドで書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-154">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="aca7f-155">キャッシュの既定の場所を変更するには、PowerShell を開始する前に、環境変数 `$env:PSModuleAnalysisCachePath` を設定します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-155">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="aca7f-156">この環境変数の変更は、子プロセスのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-156">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="aca7f-157">値には、PowerShell がファイルの作成および書き込みアクセス許可を持つ完全なパス (ファイル名を含む) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aca7f-157">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="aca7f-158">ファイル キャッシュを無効にするには、たとえば次のような無効な場所をこの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-158">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="aca7f-159">これは、パスを無効なデバイスに設定します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-159">This sets the path to an invalid device.</span></span> <span data-ttu-id="aca7f-160">PowerShell がパスに書き込めない場合、エラーは返されませんが、トレーサーでエラー レポートを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-160">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

<span data-ttu-id="aca7f-161">キャッシュの書き込み時、PowerShell は存在しなくなったモジュールを確認することで、キャッシュが不必要に大きくなるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-161">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="aca7f-162">このような確認が望ましくないことがあり、その場合は無効に設定できます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-162">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="aca7f-163">この環境変数の設定は、現在のプロセスで直ちに有効になります。</span><span class="sxs-lookup"><span data-stu-id="aca7f-163">Setting this environment variable will take effect immediately in the current process.</span></span>

### <a name="specifying-module-version"></a><span data-ttu-id="aca7f-164">モジュールのバージョンの指定</span><span class="sxs-lookup"><span data-stu-id="aca7f-164">Specifying module version</span></span>

<span data-ttu-id="aca7f-165">WMF 5.1 では、`using module` は PowerShell の他のモジュール関連構造と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-165">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span> <span data-ttu-id="aca7f-166">以前は、モジュールの特定のバージョンを指定する方法はありませんでした。複数のバージョンが存在する場合、エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="aca7f-166">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="aca7f-167">WMF 5.1 では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="aca7f-167">In WMF 5.1:</span></span>

* <span data-ttu-id="aca7f-168">[ModuleSpecification コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aca7f-168">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor).</span></span>
  <span data-ttu-id="aca7f-169">このハッシュ テーブルの形式は `Get-Module -FullyQualifiedName` と同じです。</span><span class="sxs-lookup"><span data-stu-id="aca7f-169">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

  <span data-ttu-id="aca7f-170">**例:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="aca7f-170">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

* <span data-ttu-id="aca7f-171">モジュールに複数のバージョンがある場合、PowerShell は **同じ解決ロジック** を `Import-Module` として使用し、エラーを返しません。`Import-Module` および `Import-DscResource` と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="aca7f-171">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

### <a name="improvements-to-pester"></a><span data-ttu-id="aca7f-172">Pester の機能強化</span><span class="sxs-lookup"><span data-stu-id="aca7f-172">Improvements to Pester</span></span>

<span data-ttu-id="aca7f-173">WMF 5.1 では、PowerShell に付属するバージョンの pester が3.4.0 からに更新され、GitHub [PR # 484](https://github.com/pester/Pester/pull/484)が追加されました。これにより、Nano Server での pester の動作が向上します。</span><span class="sxs-lookup"><span data-stu-id="aca7f-173">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0, with the addition of GitHub [PR# 484](https://github.com/pester/Pester/pull/484), which enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="aca7f-174">バージョン 3.3.5 から 3.4.0 の変更点については、https://github.com/pester/Pester/blob/master/CHANGELOG.md の ChangeLog.md ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aca7f-174">You can review the changes in versions 3.3.5 to 3.4.0 by inspecting the ChangeLog.md file at: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span></span>

## <a name="keywords"></a><span data-ttu-id="aca7f-175">KEYWORDS</span><span class="sxs-lookup"><span data-stu-id="aca7f-175">KEYWORDS</span></span>

<span data-ttu-id="aca7f-176">Windows PowerShell 5.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="aca7f-176">What's New in Windows PowerShell 5.1</span></span>
