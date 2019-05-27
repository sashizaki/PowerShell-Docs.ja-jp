---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.x のリリース ノート
ms.openlocfilehash: 8bdc423234cf0b104b72b1bee1de35e50783d8a4
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855767"
---
# <a name="windows-management-framework-wmf-5x-release-notes"></a><span data-ttu-id="a6e00-103">Windows Management Framework (WMF) 5.x リリース ノート</span><span class="sxs-lookup"><span data-stu-id="a6e00-103">Windows Management Framework (WMF) 5.x Release Notes</span></span>

## <a name="wmf-50-changes"></a><span data-ttu-id="a6e00-104">WMF 5.0 の変更点</span><span class="sxs-lookup"><span data-stu-id="a6e00-104">WMF 5.0 Changes</span></span>

- <span data-ttu-id="a6e00-105">PowerShell 5.0 への新しい構造化された**情報**ストリームの追加</span><span class="sxs-lookup"><span data-stu-id="a6e00-105">PowerShell 5.0 adds a new structured **Information** stream</span></span>
- <span data-ttu-id="a6e00-106">次の 4 つの新しい DSC リソースを含む、DSC への機能強化</span><span class="sxs-lookup"><span data-stu-id="a6e00-106">Improvements to DSC including four new DSC resources:</span></span>
  - <span data-ttu-id="a6e00-107">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="a6e00-107">WindowsFeatureSet</span></span>
  - <span data-ttu-id="a6e00-108">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="a6e00-108">WindowsOptionalFeatureSet</span></span>
  - <span data-ttu-id="a6e00-109">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="a6e00-109">ServiceSet</span></span>
  - <span data-ttu-id="a6e00-110">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="a6e00-110">ProcessSet</span></span>
- <span data-ttu-id="a6e00-111">PowerShell のリモート処理でのロールベースの管理を可能にする Just Enough Administration の追加</span><span class="sxs-lookup"><span data-stu-id="a6e00-111">Added Just Enough Administration to enable role-based administration through PowerShell remoting</span></span>
- <span data-ttu-id="a6e00-112">PowerShell 5.0 の言語へのユーザー定義のクラスと列挙型の追加による機能拡張</span><span class="sxs-lookup"><span data-stu-id="a6e00-112">PowerShell 5.0 extends the language to include user-defined classes and enumerations</span></span>
- <span data-ttu-id="a6e00-113">PowerShell ISE のデバッグ機能の強化とリモート デバッグの追加</span><span class="sxs-lookup"><span data-stu-id="a6e00-113">Improved debugging features in PowerShell ISE and added remote debugging</span></span>
- <span data-ttu-id="a6e00-114">PowerShellGet モジュールと PackageManagement モジュールの追加</span><span class="sxs-lookup"><span data-stu-id="a6e00-114">Added the PowerShellGet and PackageManagement modules</span></span>
- <span data-ttu-id="a6e00-115">PowerShell スクリプトのログ記録とトランスクリプトの拡張</span><span class="sxs-lookup"><span data-stu-id="a6e00-115">Enhanced PowerShell script logging and transcripts</span></span>
- <span data-ttu-id="a6e00-116">Cryptographic Message Syntax コマンドレットの追加</span><span class="sxs-lookup"><span data-stu-id="a6e00-116">Add Cryptographic Message Syntax cmdlets</span></span>
- <span data-ttu-id="a6e00-117">WMF 5.0 への Windows 用の NetworkSwitchManager モジュールの追加</span><span class="sxs-lookup"><span data-stu-id="a6e00-117">WMF 5.0 includes the NetworkSwitchManager module for Windows</span></span>
- <span data-ttu-id="a6e00-118">Microsoft.PowerShell.ODataUtils モジュールの追加</span><span class="sxs-lookup"><span data-stu-id="a6e00-118">Added the Microsoft.PowerShell.ODataUtils module</span></span>
- <span data-ttu-id="a6e00-119">ソフトウェア インベントリ ログ (SIL) のサポートの追加</span><span class="sxs-lookup"><span data-stu-id="a6e00-119">Added support for Software Inventory Logging (SIL)</span></span>
- <span data-ttu-id="a6e00-120">ユーザーの要求と問題への応答によるサーバーの新規または更新されたコマンドレット</span><span class="sxs-lookup"><span data-stu-id="a6e00-120">Sever new or update cmdlets in response to user requests and issues</span></span>

## <a name="wmf-51-changes"></a><span data-ttu-id="a6e00-121">WMF 5.1 の変更点</span><span class="sxs-lookup"><span data-stu-id="a6e00-121">WMF 5.1 Changes</span></span>

<span data-ttu-id="a6e00-122">WMF 5.1 には、Windows Server 2016 でリリースされた PowerShell、WMI、WinRM、ソフトウェア インベントリ ログ (SIL) のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6e00-122">WMF 5.1 includes the PowerShell, WMI, WinRM, and Software Inventory Logging (SIL) components that were released with Windows Server 2016.</span></span> <span data-ttu-id="a6e00-123">WMF 5.1 は、Windows 7、Windows 8.1、Windows Server 2008 R2、2012、および 2012 R2 にインストールすることができ、WMF 5.0 と比較すると次のいくつかの機能強化があります。</span><span class="sxs-lookup"><span data-stu-id="a6e00-123">WMF 5.1 can be installed on Windows 7, Windows 8.1, Windows Server 2008 R2, 2012, and 2012 R2, and provides several improvements over WMF 5.0 including:</span></span>

- <span data-ttu-id="a6e00-124">新しいコマンドレット</span><span class="sxs-lookup"><span data-stu-id="a6e00-124">New cmdlets</span></span>
- <span data-ttu-id="a6e00-125">PowerShellGet では、署名付きモジュールの適用や JEA モジュールのインストールなどの機能強化が行われています。</span><span class="sxs-lookup"><span data-stu-id="a6e00-125">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="a6e00-126">PackageManagement では、コンテナー、CBS セットアップ、EXE ベースのセットアップ、CAB パッケージをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="a6e00-126">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="a6e00-127">DSC および PowerShell クラスにおけるデバッグ機能の強化</span><span class="sxs-lookup"><span data-stu-id="a6e00-127">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="a6e00-128">セキュリティの機能強化としては、プル サーバーからもたらされるカタログ署名付きモジュールの適用、PowerShellGet コマンドレットを使用するタイミングなどが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-128">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="a6e00-129">さまざまなユーザー要求と問題への対応</span><span class="sxs-lookup"><span data-stu-id="a6e00-129">Responses to a number of user requests and issues</span></span>

## <a name="powershell-editions"></a><span data-ttu-id="a6e00-130">PowerShell のエディション</span><span class="sxs-lookup"><span data-stu-id="a6e00-130">PowerShell Editions</span></span>

<span data-ttu-id="a6e00-131">バージョン 5.1 から、PowerShell は機能セットとプラットフォーム互換性が異なるさまざまなエディションで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a6e00-131">Starting with version 5.1, PowerShell is available in different editions that denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="a6e00-132">**Desktop Edition:**.NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="a6e00-132">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="a6e00-133">**Core Edition:**.NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="a6e00-133">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

### <a name="learn-more-about-using-powershell-editions"></a><span data-ttu-id="a6e00-134">PowerShell のエディションの使用に関する詳細</span><span class="sxs-lookup"><span data-stu-id="a6e00-134">Learn more about using PowerShell Editions</span></span>

- [<span data-ttu-id="a6e00-135">$PSVersionTable を使用して PowerShell の実行エディションを特定する</span><span class="sxs-lookup"><span data-stu-id="a6e00-135">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="a6e00-136">PSEdition パラメーターを使用して CompatiblePSEditions で Get-Module の結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a6e00-136">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="a6e00-137">互換性のある PowerShell のエディションで実行しない場合はスクリプトを実行させない</span><span class="sxs-lookup"><span data-stu-id="a6e00-137">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="a6e00-138">特定の PowerShell バージョンに対するモジュールの互換性を宣言する</span><span class="sxs-lookup"><span data-stu-id="a6e00-138">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/gallery/concepts/module-psedition-support)

## <a name="module-analysis-cache"></a><span data-ttu-id="a6e00-139">モジュール分析キャッシュ</span><span class="sxs-lookup"><span data-stu-id="a6e00-139">Module Analysis Cache</span></span>

<span data-ttu-id="a6e00-140">WMF 5.1 以降の PowerShell では、エクスポートするコマンドなど、モジュールに関するデータのキャッシュに使用されるファイルを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-140">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="a6e00-141">既定では、このキャッシュは `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-141">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="a6e00-142">キャッシュは、通常、起動時にコマンドを検索するときに読み取られ、モジュールのインポート後しばらくしてバックグラウンド スレッドで書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-142">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="a6e00-143">キャッシュの既定の場所を変更するには、PowerShell を開始する前に、環境変数 `$env:PSModuleAnalysisCachePath` を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6e00-143">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="a6e00-144">この環境変数の変更は、子プロセスのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="a6e00-144">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="a6e00-145">値には、PowerShell がファイルの作成および書き込みアクセス許可を持つ完全なパス (ファイル名を含む) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e00-145">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="a6e00-146">ファイル キャッシュを無効にするには、たとえば次のような無効な場所をこの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6e00-146">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="a6e00-147">これは、パスを無効なデバイスに設定します。</span><span class="sxs-lookup"><span data-stu-id="a6e00-147">This sets the path to an invalid device.</span></span> <span data-ttu-id="a6e00-148">PowerShell がパスに書き込めない場合、エラーは返されませんが、トレーサーでエラー レポートを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-148">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

<span data-ttu-id="a6e00-149">キャッシュの書き込み時、PowerShell は存在しなくなったモジュールを確認することで、キャッシュが不必要に大きくなるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-149">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="a6e00-150">このような確認が望ましくないことがあり、その場合は無効に設定できます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-150">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="a6e00-151">この環境変数の設定は、現在のプロセスで直ちに有効になります。</span><span class="sxs-lookup"><span data-stu-id="a6e00-151">Setting this environment variable will take effect immediately in the current process.</span></span>

## <a name="specifying-module-version"></a><span data-ttu-id="a6e00-152">モジュールのバージョンの指定</span><span class="sxs-lookup"><span data-stu-id="a6e00-152">Specifying module version</span></span>

<span data-ttu-id="a6e00-153">WMF 5.1 では、`using module` は PowerShell の他のモジュール関連構造と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="a6e00-153">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span>
<span data-ttu-id="a6e00-154">以前は、モジュールの特定のバージョンを指定する方法はありませんでした。複数のバージョンが存在する場合、エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a6e00-154">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="a6e00-155">WMF 5.1 では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a6e00-155">In WMF 5.1:</span></span>

- <span data-ttu-id="a6e00-156">[ModuleSpecification コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-156">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
  <span data-ttu-id="a6e00-157">このハッシュ テーブルの形式は `Get-Module -FullyQualifiedName` と同じです。</span><span class="sxs-lookup"><span data-stu-id="a6e00-157">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

  <span data-ttu-id="a6e00-158">**例:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="a6e00-158">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

- <span data-ttu-id="a6e00-159">モジュールに複数のバージョンがある場合、PowerShell は**同じ解決ロジック**を `Import-Module` として使用し、エラーを返しません。`Import-Module` および `Import-DscResource` と同じ動作です。</span><span class="sxs-lookup"><span data-stu-id="a6e00-159">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

## <a name="improvements-to-pester"></a><span data-ttu-id="a6e00-160">Pester の機能強化</span><span class="sxs-lookup"><span data-stu-id="a6e00-160">Improvements to Pester</span></span>

<span data-ttu-id="a6e00-161">WMF 5.1 では、PowerShell で出荷される Pester のバージョンが 3.3.5 から 3.4.0 に更新されました。</span><span class="sxs-lookup"><span data-stu-id="a6e00-161">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0.</span></span>
<span data-ttu-id="a6e00-162">この更新プログラムにより、Nano Server での Pester の動作が改善されます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-162">This update enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="a6e00-163">Pest の変更は、GitHub リポジトリの [ChangeLog](https://github.com/pester/Pester/blob/master/CHANGELOG.md) で確認できます。</span><span class="sxs-lookup"><span data-stu-id="a6e00-163">You can review the changes in Pest by inspecting the [ChangeLog](https://github.com/pester/Pester/blob/master/CHANGELOG.md) in the GitHub repository.</span></span>
