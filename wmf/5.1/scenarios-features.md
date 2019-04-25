---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 の新しいシナリオと機能
ms.openlocfilehash: b00069aad7422f86d1462a62a6c4bc8a91e46705
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085460"
---
# <a name="new-scenarios-and-features-in-wmf-51"></a><span data-ttu-id="b2002-103">WMF 5.1 の新しいシナリオと機能</span><span class="sxs-lookup"><span data-stu-id="b2002-103">New Scenarios and Features in WMF 5.1</span></span>

> <span data-ttu-id="b2002-104">注: この情報は暫定的であり、変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b2002-104">Note: This information is preliminary and subject to change.</span></span>

## <a name="powershell-editions"></a><span data-ttu-id="b2002-105">PowerShell のエディション</span><span class="sxs-lookup"><span data-stu-id="b2002-105">PowerShell Editions</span></span>

<span data-ttu-id="b2002-106">バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b2002-106">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="b2002-107">**Desktop Edition:**.NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="b2002-107">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="b2002-108">**Core Edition:**.NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2002-108">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="b2002-109">**PowerShell のエディションの使用に関する詳細**</span><span class="sxs-lookup"><span data-stu-id="b2002-109">**Learn more about using PowerShell Editions**</span></span>

- [<span data-ttu-id="b2002-110">$PSVersionTable を使用して PowerShell の実行エディションを特定する</span><span class="sxs-lookup"><span data-stu-id="b2002-110">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="b2002-111">PSEdition パラメーターを使用して CompatiblePSEditions で Get-Module の結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="b2002-111">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="b2002-112">互換性のある PowerShell のエディションで実行しない場合はスクリプトを実行させない</span><span class="sxs-lookup"><span data-stu-id="b2002-112">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="b2002-113">特定の PowerShell バージョンに対するモジュールの互換性を宣言する</span><span class="sxs-lookup"><span data-stu-id="b2002-113">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/gallery/concepts/module-psedition-support)

## <a name="catalog-cmdlets"></a><span data-ttu-id="b2002-114">カタログ コマンドレット</span><span class="sxs-lookup"><span data-stu-id="b2002-114">Catalog Cmdlets</span></span>

<span data-ttu-id="b2002-115">[Microsoft.PowerShell.Security](/powershell/module/microsoft.powershell.security) モジュールに新しいコマンドレットが 2 つ追加されました。Windows カタログ ファイルを生成し、検証するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="b2002-115">Two new cmdlets have been added in the [Microsoft.PowerShell.Security](/powershell/module/microsoft.powershell.security) module; these generate and validate Windows catalog files.</span></span>

### <a name="new-filecatalog"></a><span data-ttu-id="b2002-116">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="b2002-116">New-FileCatalog</span></span>
--------------------------------

<span data-ttu-id="b2002-117">New-FileCatalog は、一連のフォルダーやファイルに対して Windows カタログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2002-117">New-FileCatalog creates a Windows catalog file for set of folders and files.</span></span>
<span data-ttu-id="b2002-118">このカタログ ファイルには、指定されたパスのすべてのファイルのハッシュが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2002-118">This catalog file contains hashes for all files in specified paths.</span></span>
<span data-ttu-id="b2002-119">ユーザーは一連のフォルダーと共に、それらのフォルダーを表すカタログ ファイルを配信できます。</span><span class="sxs-lookup"><span data-stu-id="b2002-119">Users can distribute the set of folders along with corresponding catalog file representing those folders.</span></span>
<span data-ttu-id="b2002-120">カタログ作成時刻以降、フォルダーに変更が加えられたかどうかを検証するとき、この情報が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b2002-120">This information is useful to validate whether any changes have been made to the folders since catalog creation time.</span></span>

```powershell
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>] [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="b2002-121">カタログ バージョン 1 と 2 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b2002-121">Catalog versions 1 and 2 are supported.</span></span>
<span data-ttu-id="b2002-122">バージョン 1 は SHA1 ハッシュ アルゴリズムを使用して、バージョン 2 は SHA256 ハッシュ アルゴリズムを使用してファイル ハッシュを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2002-122">Version 1 uses the SHA1 hashing algorithm to create file hashes; version 2 uses SHA256.</span></span>
<span data-ttu-id="b2002-123">*Windows Server 2008 R2* と *Windows 7* はカタログ バージョン 2 に対応していません。</span><span class="sxs-lookup"><span data-stu-id="b2002-123">Catalog version 2 is not supported on *Windows Server 2008 R2* or *Windows 7*.</span></span>
<span data-ttu-id="b2002-124">カタログ バージョン 2 は *Windows 8*、*Windows Server 2012* 以降のオペレーティング システムで利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2002-124">You should use catalog version 2 on *Windows 8*, *Windows Server 2012*, and later operating systems.</span></span>

![](../images/NewFileCatalog.jpg)

<span data-ttu-id="b2002-125">これはカタログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2002-125">This creates the catalog file.</span></span>

![](../images/CatalogFile1.jpg)

![](../images/CatalogFile2.jpg)

<span data-ttu-id="b2002-126">カタログ ファイルの整合性を検証するために (上記の例では Pester.cat)、[Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature) コマンドレットで署名します。</span><span class="sxs-lookup"><span data-stu-id="b2002-126">To verify the integrity of catalog file (Pester.cat in above example), sign it using [Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature) cmdlet.</span></span>

### <a name="test-filecatalog"></a><span data-ttu-id="b2002-127">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="b2002-127">Test-FileCatalog</span></span>
--------------------------------

<span data-ttu-id="b2002-128">Test-FileCatalog は、一連のフォルダーを表すカタログを検証します。</span><span class="sxs-lookup"><span data-stu-id="b2002-128">Test-FileCatalog validates the catalog representing a set of folders.</span></span>

```powershell
Test-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>] [-Detailed] [-FilesToSkip <string[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

![](../images/TestFileCatalog.jpg)

<span data-ttu-id="b2002-129">このコマンドレットは、*カタログ*で見つかったすべてのファイル ハッシュとその相対パスを*ディスク*のそれらと比較します。</span><span class="sxs-lookup"><span data-stu-id="b2002-129">This cmdlet compares all the files hashes and their relative paths found in *catalog* with ones on *disk*.</span></span>
<span data-ttu-id="b2002-130">ファイル ハッシュとパスの間に不一致が検出された場合、*ValidationFailed* というステータスを返します。</span><span class="sxs-lookup"><span data-stu-id="b2002-130">If it detects any mismatch between file hashes and paths it returns the status as *ValidationFailed*.</span></span>
<span data-ttu-id="b2002-131">*-Detailed* パラメーターを利用し、この情報をすべて取得できます。</span><span class="sxs-lookup"><span data-stu-id="b2002-131">Users can retrieve all this information by using the *-Detailed* parameter.</span></span>
<span data-ttu-id="b2002-132">*署名*プロパティには、カタログの署名ステータスも表示されます。これは、カタログ ファイルで [Get-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Get-AuthenticodeSignature) コマンドレットを呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="b2002-132">It also displays signing status of catalog in *Signature* property which is equivalent to calling [Get-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Get-AuthenticodeSignature) cmdlet on the catalog file.</span></span>
<span data-ttu-id="b2002-133">*-FilesToSkip* パラメーターを利用し、検証中にファイルをスキップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b2002-133">Users can also skip any file during validation by using the *-FilesToSkip* parameter.</span></span>

## <a name="module-analysis-cache"></a><span data-ttu-id="b2002-134">モジュール分析キャッシュ</span><span class="sxs-lookup"><span data-stu-id="b2002-134">Module Analysis Cache</span></span>

<span data-ttu-id="b2002-135">WMF 5.1 以降の PowerShell では、エクスポートするコマンドなど、モジュールに関するデータのキャッシュに使用されるファイルを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b2002-135">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="b2002-136">既定では、このキャッシュは `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b2002-136">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span>
<span data-ttu-id="b2002-137">キャッシュは、通常、起動時にコマンドを検索するときに読み取られ、モジュールのインポート後しばらくしてバックグラウンド スレッドで書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b2002-137">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="b2002-138">キャッシュの既定の場所を変更するには、PowerShell を開始する前に、環境変数 `$env:PSModuleAnalysisCachePath` を設定します。</span><span class="sxs-lookup"><span data-stu-id="b2002-138">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span>
<span data-ttu-id="b2002-139">この環境変数の変更は、子プロセスのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="b2002-139">Changes to this environment variable will only affect children processes.</span></span>
<span data-ttu-id="b2002-140">値には、PowerShell がファイルの作成および書き込みアクセス許可を持つ完全なパス (ファイル名を含む) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2002-140">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span>
<span data-ttu-id="b2002-141">ファイル キャッシュを無効にするには、たとえば次のような無効な場所をこの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="b2002-141">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="b2002-142">これは、パスを無効なデバイスに設定します。</span><span class="sxs-lookup"><span data-stu-id="b2002-142">This sets the path to an invalid device.</span></span>
<span data-ttu-id="b2002-143">PowerShell がパスに書き込めない場合、エラーは返されませんが、トレーサーでエラー レポートを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="b2002-143">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

<span data-ttu-id="b2002-144">キャッシュの書き込み時、PowerShell は存在しなくなったモジュールを確認することで、キャッシュが不必要に大きくなるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="b2002-144">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span>
<span data-ttu-id="b2002-145">このような確認が望ましくないことがあり、その場合は無効に設定できます。</span><span class="sxs-lookup"><span data-stu-id="b2002-145">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="b2002-146">この環境変数の設定は、現在のプロセスで直ちに有効になります。</span><span class="sxs-lookup"><span data-stu-id="b2002-146">Setting this environment variable will take effect immediately in the current process.</span></span>

## <a name="specifying-module-version"></a><span data-ttu-id="b2002-147">モジュールのバージョンの指定</span><span class="sxs-lookup"><span data-stu-id="b2002-147">Specifying module version</span></span>

<span data-ttu-id="b2002-148">WMF 5.1 では、`using module` は PowerShell の他のモジュール関連構造と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="b2002-148">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span>
<span data-ttu-id="b2002-149">以前は、モジュールの特定のバージョンを指定する方法はありませんでした。複数のバージョンが存在する場合、エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b2002-149">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="b2002-150">WMF 5.1 では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b2002-150">In WMF 5.1:</span></span>

- <span data-ttu-id="b2002-151">[ModuleSpecification コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b2002-151">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
<span data-ttu-id="b2002-152">このハッシュ テーブルの形式は `Get-Module -FullyQualifiedName` と同じです。</span><span class="sxs-lookup"><span data-stu-id="b2002-152">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

<span data-ttu-id="b2002-153">**例:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="b2002-153">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

- <span data-ttu-id="b2002-154">モジュールに複数のバージョンがある場合、PowerShell は**同じ解決ロジック**を `Import-Module` として使用し、エラーを返しません。`Import-Module` および `Import-DscResource` と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="b2002-154">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

## <a name="improvements-to-pester"></a><span data-ttu-id="b2002-155">Pester の機能強化</span><span class="sxs-lookup"><span data-stu-id="b2002-155">Improvements to Pester</span></span>

<span data-ttu-id="b2002-156">WMF 5.1 では、PowerShell で出荷される Pester のバージョンが 3.3.5 から 3.4.0 に更新され、コミット https://github.com/pester/Pester/pull/484/commits/3854ae8a1f215b39697ac6c2607baf42257b102e が追加されました。Nano Server での Pester の動作を改善します。</span><span class="sxs-lookup"><span data-stu-id="b2002-156">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0, with the addition of commit https://github.com/pester/Pester/pull/484/commits/3854ae8a1f215b39697ac6c2607baf42257b102e, which enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="b2002-157">バージョン 3.3.5 から 3.4.0 の変更点については、 https://github.com/pester/Pester/blob/master/CHANGELOG.md の ChangeLog.md ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2002-157">You can review the changes in versions 3.3.5 to 3.4.0 by inspecting the ChangeLog.md file at: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span></span>
