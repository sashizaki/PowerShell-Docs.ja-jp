---
ms.date: 11/06/2018
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery, PsGet
title: ローカル PSRepositories の操作
ms.openlocfilehash: 94824ea584c097838b24c6f2cd02407b6147a781
ms.sourcegitcommit: 91786b03704fbd2d185f674df0bc67faddfb6288
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51619207"
---
# <a name="working-with-local-powershellget-repositories"></a><span data-ttu-id="888d8-103">ローカルの PowerShellGet リポジトリの操作</span><span class="sxs-lookup"><span data-stu-id="888d8-103">Working with local PowerShellGet Repositories</span></span>

<span data-ttu-id="888d8-104">PowerShell ギャラリー以外の PowerShellGet モジュール サポート リポジトリ。</span><span class="sxs-lookup"><span data-stu-id="888d8-104">The PowerShellGet module support repositories other than the PowerShell Gallery.</span></span>
<span data-ttu-id="888d8-105">これらのコマンドレットは、次のシナリオを有効にします。</span><span class="sxs-lookup"><span data-stu-id="888d8-105">These cmdlets enable the following scenarios:</span></span>

- <span data-ttu-id="888d8-106">環境内で使用するため、信頼されている、事前に検証された PowerShell モジュールのセットをサポートします。</span><span class="sxs-lookup"><span data-stu-id="888d8-106">Support a trusted, pre-validated set of PowerShell modules for use in your environment</span></span>
- <span data-ttu-id="888d8-107">PowerShell モジュールまたはスクリプトをビルドする CI/CD パイプラインをテストします。</span><span class="sxs-lookup"><span data-stu-id="888d8-107">Testing a CI/CD pipeline that builds PowerShell modules or scripts</span></span>
- <span data-ttu-id="888d8-108">インターネットにアクセスできないシステムに PowerShell スクリプトおよびモジュールを配信します。</span><span class="sxs-lookup"><span data-stu-id="888d8-108">Deliver PowerShell scripts and modules to systems that can't access the internet</span></span>

<span data-ttu-id="888d8-109">この記事では、ローカル PowerShell リポジトリを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="888d8-109">This article describes how to set up a local PowerShell repository.</span></span> <span data-ttu-id="888d8-110">についても説明します、 [OfflinePowerShellGetDeploy][] PowerShell ギャラリーからモジュールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="888d8-110">The article also covers the [OfflinePowerShellGetDeploy][] module available from the PowerShell Gallery.</span></span> <span data-ttu-id="888d8-111">このモジュールには、ローカル リポジトリに PowerShellGet の最新バージョンをインストールするためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="888d8-111">This module contains cmdlets to install the latest version of PowerShellGet into your local repository.</span></span>

## <a name="local-repository-types"></a><span data-ttu-id="888d8-112">ローカル リポジトリの種類</span><span class="sxs-lookup"><span data-stu-id="888d8-112">Local repository types</span></span>

<span data-ttu-id="888d8-113">ローカル PSRepository を作成する 2 つの方法があります。 NuGet サーバーまたはファイル共有。</span><span class="sxs-lookup"><span data-stu-id="888d8-113">There are two ways to create a local PSRepository: NuGet server or file share.</span></span> <span data-ttu-id="888d8-114">各種は、長所と短所があります。</span><span class="sxs-lookup"><span data-stu-id="888d8-114">Each type has advantages and disadvantages:</span></span>

<span data-ttu-id="888d8-115">NuGet サーバー</span><span class="sxs-lookup"><span data-stu-id="888d8-115">NuGet Server</span></span>

| <span data-ttu-id="888d8-116">長所</span><span class="sxs-lookup"><span data-stu-id="888d8-116">Advantages</span></span>| <span data-ttu-id="888d8-117">短所</span><span class="sxs-lookup"><span data-stu-id="888d8-117">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="888d8-118">PowerShellGallery 機能を正確に模倣します。</span><span class="sxs-lookup"><span data-stu-id="888d8-118">Closely mimics PowerShellGallery functionality</span></span> | <span data-ttu-id="888d8-119">多層アプリケーションは、操作の計画とサポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="888d8-119">Multi-tier app requires operations planning & support</span></span> |
| <span data-ttu-id="888d8-120">NuGet は、Visual Studio、その他のツールと統合します。</span><span class="sxs-lookup"><span data-stu-id="888d8-120">NuGet integrates with Visual Studio, other tools</span></span> | <span data-ttu-id="888d8-121">認証モデルと必要な NuGet アカウント管理</span><span class="sxs-lookup"><span data-stu-id="888d8-121">Authentication model and NuGet accounts management needed</span></span> |
| <span data-ttu-id="888d8-122">NuGet でメタデータをサポートする`.Nupkg`パッケージ</span><span class="sxs-lookup"><span data-stu-id="888d8-122">NuGet supports metadata in `.Nupkg` packages</span></span> | <span data-ttu-id="888d8-123">発行は、API キーの管理とメンテナンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="888d8-123">Publishing requires API Key management & maintenance</span></span> |
| <span data-ttu-id="888d8-124">検索、パッケージの管理などを提供します。</span><span class="sxs-lookup"><span data-stu-id="888d8-124">Provides search, package administration, etc.</span></span> | |

<span data-ttu-id="888d8-125">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="888d8-125">File Share</span></span>

| <span data-ttu-id="888d8-126">長所</span><span class="sxs-lookup"><span data-stu-id="888d8-126">Advantages</span></span>| <span data-ttu-id="888d8-127">短所</span><span class="sxs-lookup"><span data-stu-id="888d8-127">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="888d8-128">簡単設定、バックアップ、および管理するには</span><span class="sxs-lookup"><span data-stu-id="888d8-128">Easy to set up, back up, and maintain</span></span> | <span data-ttu-id="888d8-129">PowerShellGet で使用されるメタデータは使用できません。</span><span class="sxs-lookup"><span data-stu-id="888d8-129">Metadata used by PowerShellGet isn't available</span></span> |
| <span data-ttu-id="888d8-130">単純なセキュリティ モデル、共有のユーザーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="888d8-130">Simple security model - user permissions on the share</span></span> | <span data-ttu-id="888d8-131">基本的なファイル共有を超える UI なし</span><span class="sxs-lookup"><span data-stu-id="888d8-131">No UI beyond basic file share</span></span> |
| <span data-ttu-id="888d8-132">既存の項目を置換などの制約のないです。</span><span class="sxs-lookup"><span data-stu-id="888d8-132">No constraints such as replacing existing items</span></span> | <span data-ttu-id="888d8-133">限られたセキュリティと内容を更新するユーザーの記録がありません。</span><span class="sxs-lookup"><span data-stu-id="888d8-133">Limited security and no recording of who updates what</span></span> |

<span data-ttu-id="888d8-134">PowerShellGet は、特定のバージョンと依存関係のインストールをサポートして型のいずれかで動作します。</span><span class="sxs-lookup"><span data-stu-id="888d8-134">PowerShellGet works with either type and supports locating versions and dependency installation.</span></span>
<span data-ttu-id="888d8-135">ただし、PowerShell ギャラリーを使用できるいくつかの機能は、基本の NuGet サーバーやファイル共有に対して使用できません。</span><span class="sxs-lookup"><span data-stu-id="888d8-135">However, some features that work for the PowerShell Gallery aren't available for base NuGet servers or file shares.</span></span>

- <span data-ttu-id="888d8-136">すべては、パッケージのスクリプトやモジュール、DSC リソース、ロール機能のない差別化要因です。</span><span class="sxs-lookup"><span data-stu-id="888d8-136">Everything is a package - no differentiation of scripts, modules, DSC resources, or role capabilities.</span></span>
- <span data-ttu-id="888d8-137">ファイル共有サーバーには、タグを含むパッケージのメタデータを表示できません。</span><span class="sxs-lookup"><span data-stu-id="888d8-137">File share servers can't see package metadata, including tags.</span></span>

## <a name="creating-a-local-repository"></a><span data-ttu-id="888d8-138">ローカル リポジトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="888d8-138">Creating a local repository</span></span>

<span data-ttu-id="888d8-139">次の記事では、独自の NuGet サーバーを設定するための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="888d8-139">The following article lists the steps for setting up your own NuGet Server.</span></span>

- <span data-ttu-id="888d8-140">[NuGet.Server][]</span><span class="sxs-lookup"><span data-stu-id="888d8-140">[NuGet.Server][]</span></span>

<span data-ttu-id="888d8-141">パッケージを追加する時点までの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="888d8-141">Follow the steps up to the point of adding packages.</span></span> <span data-ttu-id="888d8-142">手順[パッケージを公開する](#publishing-to-a-local-repository)はこの記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="888d8-142">The steps for [publishing a package](#publishing-to-a-local-repository) are covered later in this article.</span></span>

<span data-ttu-id="888d8-143">ファイル共有ベースのリポジトリでは、ユーザーにファイル共有にアクセスする権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="888d8-143">For a file share-based repository, make sure that your users have permissions to access the file share.</span></span>

## <a name="registering-a-local-repository"></a><span data-ttu-id="888d8-144">ローカル リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="888d8-144">Registering a local repository</span></span>

<span data-ttu-id="888d8-145">リポジトリを使用できますが、前に、登録する必要を使用して、`Register-PSRepository`コマンド。</span><span class="sxs-lookup"><span data-stu-id="888d8-145">Before a repository can be used, it must be registered using the `Register-PSRepository` command.</span></span>
<span data-ttu-id="888d8-146">以下の例で、 **InstallationPolicy**に設定されている*信頼済み*、独自のリポジトリを信頼できることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="888d8-146">In the examples below, the **InstallationPolicy** is set to *Trusted*, on the assumption that you trust your own repository.</span></span>

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

<span data-ttu-id="888d8-147">2 つのコマンドを処理する方法の違いをメモしておきます**ScriptSourceLocation**します。</span><span class="sxs-lookup"><span data-stu-id="888d8-147">Take note of the difference between how the two commands handle **ScriptSourceLocation**.</span></span> <span data-ttu-id="888d8-148">ファイル共有ベースのリポジトリでは、 **SourceLocation**と**ScriptSourceLocation**と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="888d8-148">For a file share-based repositories, the **SourceLocation** and **ScriptSourceLocation** must match.</span></span> <span data-ttu-id="888d8-149">Web ベースのリポジトリでは、する必要があるさまざまな、最後には、この例では「/」に追加されます、 **SourceLocation**します。</span><span class="sxs-lookup"><span data-stu-id="888d8-149">For a web-based repository, they must be different, so in this example a trailing "/" is added to the **SourceLocation**.</span></span>

<span data-ttu-id="888d8-150">既定のリポジトリを新しく作成された PSRepository にする場合は、その他のすべての PSRepositories の登録を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="888d8-150">If you want the newly created PSRepository to be the default repository, you must unregister all other PSRepositories.</span></span> <span data-ttu-id="888d8-151">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="888d8-151">For example:</span></span>

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> <span data-ttu-id="888d8-152">リポジトリ名 'PSGallery' は、PowerShell ギャラリーで使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="888d8-152">The repository name 'PSGallery' is reserved for use by the PowerShell Gallery.</span></span> <span data-ttu-id="888d8-153">PSGallery、登録を解除することができますが、その他の任意のリポジトリの名前 PSGallery を再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="888d8-153">You can unregister PSGallery, but you cannot reuse the name PSGallery for any other repository.</span></span>

<span data-ttu-id="888d8-154">PSGallery を復元する必要がある場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="888d8-154">If you need to restore the PSGallery, run the following command:</span></span>

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a><span data-ttu-id="888d8-155">ローカル リポジトリに公開します。</span><span class="sxs-lookup"><span data-stu-id="888d8-155">Publishing to a local repository</span></span>

<span data-ttu-id="888d8-156">ローカル PSRepository を登録したら、ローカル、PSRepository に発行できます。</span><span class="sxs-lookup"><span data-stu-id="888d8-156">Once you've registered the local PSRepository, you can publish to your local PSRepository.</span></span> <span data-ttu-id="888d8-157">2 つの主な発行シナリオがあります。 独自のモジュールを発行および PSGallery からモジュールを発行します。</span><span class="sxs-lookup"><span data-stu-id="888d8-157">There are two main publishing scenarios: publishing your own module and publishing a module from the PSGallery.</span></span>

### <a name="publishing-a-module-you-authored"></a><span data-ttu-id="888d8-158">作成したモジュールの発行</span><span class="sxs-lookup"><span data-stu-id="888d8-158">Publishing a module you authored</span></span>

<span data-ttu-id="888d8-159">使用`Publish-Module`と`Publish-Script`PowerShell ギャラリーのと同じ方法をローカル PSRepository にモジュールを発行します。</span><span class="sxs-lookup"><span data-stu-id="888d8-159">Use `Publish-Module` and `Publish-Script` to publish your module to your local PSRepository the same way you do for the PowerShell Gallery.</span></span>

- <span data-ttu-id="888d8-160">コードの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="888d8-160">Specify the location for your code</span></span>
- <span data-ttu-id="888d8-161">API キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="888d8-161">Supply an API key</span></span>
- <span data-ttu-id="888d8-162">リポジトリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="888d8-162">Specify the repository name.</span></span> <span data-ttu-id="888d8-163">たとえば、`-PSRepository LocalPSRepo` と記述します。</span><span class="sxs-lookup"><span data-stu-id="888d8-163">For example, `-PSRepository LocalPSRepo`</span></span>

> [!NOTE]
> <span data-ttu-id="888d8-164">NuGet のサーバーでアカウントを作成しにサインインを生成し、API キーを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="888d8-164">You must create an account in the NuGet server, then sign in to generate and save the API key.</span></span>
> <span data-ttu-id="888d8-165">ファイル共有の場合は、NuGetApiKey 値の任意の空白でない文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="888d8-165">For a file share, use any non-blank string for the NuGetApiKey value.</span></span>

<span data-ttu-id="888d8-166">例:</span><span class="sxs-lookup"><span data-stu-id="888d8-166">Examples:</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> <span data-ttu-id="888d8-167">セキュリティを確保するには、API キーのスクリプトにハード コーディングされてはなりません。</span><span class="sxs-lookup"><span data-stu-id="888d8-167">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="888d8-168">セキュリティで保護されたキー管理システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="888d8-168">Use a secure key management system.</span></span>

### <a name="publishing-a-module-from-the-psgallery"></a><span data-ttu-id="888d8-169">PSGallery からモジュールの発行</span><span class="sxs-lookup"><span data-stu-id="888d8-169">Publishing a module from the PSGallery</span></span>

<span data-ttu-id="888d8-170">ローカル、PSRepository に PSGallery からモジュールを発行するには、' Save-package ' コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="888d8-170">To publish a module from the PSGallery to your local PSRepository, you can use the 'Save-Package' cmdlet.</span></span>

- <span data-ttu-id="888d8-171">パッケージの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="888d8-171">Specify the Name of the Package</span></span>
- <span data-ttu-id="888d8-172">プロバイダーとしての 'NuGet' の指定します。</span><span class="sxs-lookup"><span data-stu-id="888d8-172">Specify 'NuGet' as the Provider</span></span>
- <span data-ttu-id="888d8-173">ソース (として PSGallery 場所を指定します。 https://www.powershellgallery.com/api/v2)</span><span class="sxs-lookup"><span data-stu-id="888d8-173">Specify the PSGallery location as the source (https://www.powershellgallery.com/api/v2)</span></span>
- <span data-ttu-id="888d8-174">ローカル リポジトリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="888d8-174">Specify the path to your local Repository</span></span>

<span data-ttu-id="888d8-175">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="888d8-175">Example:</span></span>

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider Nuget -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

<span data-ttu-id="888d8-176">場合は、ローカル PSRepository には web ベースでは、nuget.exe を使用して発行する追加の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="888d8-176">If your local PSRepository is web-based, it requires an additional step that uses nuget.exe to publish.</span></span>

<span data-ttu-id="888d8-177">使用してドキュメントを参照して[nuget.exe][]します。</span><span class="sxs-lookup"><span data-stu-id="888d8-177">See the documentation for using [nuget.exe][].</span></span>

## <a name="installing-powershellget-on-a-disconnected-system"></a><span data-ttu-id="888d8-178">接続されていないシステムに PowerShellGet をインストールします。</span><span class="sxs-lookup"><span data-stu-id="888d8-178">Installing PowerShellGet on a disconnected system</span></span>

<span data-ttu-id="888d8-179">PowerShellGet の展開は、システムがインターネットから切断する必要がある環境では困難です。</span><span class="sxs-lookup"><span data-stu-id="888d8-179">Deploying PowerShellGet is difficult in environments that require systems to be disconnected from the internet.</span></span> <span data-ttu-id="888d8-180">PowerShellGet では、最初に使用されるときに、最新バージョンをインストールするブートス トラップ プロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="888d8-180">PowerShellGet has a bootstrap process that installs the latest version the first time it's used.</span></span> <span data-ttu-id="888d8-181">PowerShell ギャラリーで OfflinePowerShellGetDeploy モジュールは、このブートス トラップ プロセスをサポートするコマンドレットを提供します。</span><span class="sxs-lookup"><span data-stu-id="888d8-181">The OfflinePowerShellGetDeploy module in the PowerShell Gallery provides cmdlets that support this bootstrap process.</span></span>

<span data-ttu-id="888d8-182">オフラインの展開をブートス トラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="888d8-182">To bootstrap an offline deployment, you need to:</span></span>

- <span data-ttu-id="888d8-183">インターネットに接続されたは、OfflinePowerShellGetDeploy システムと、接続されていないシステム ダウンロードしてインストール</span><span class="sxs-lookup"><span data-stu-id="888d8-183">Download and install the OfflinePowerShellGetDeploy your internet-connected system and your disconnected systems</span></span>
- <span data-ttu-id="888d8-184">PowerShellGet とその依存関係を使用して、インターネットに接続されたシステムでダウンロード、`Save-PowerShellGetForOffline`コマンドレット</span><span class="sxs-lookup"><span data-stu-id="888d8-184">Download PowerShellGet and its dependencies on the internet-connected system using the `Save-PowerShellGetForOffline` cmdlet</span></span>
- <span data-ttu-id="888d8-185">インターネットに接続されたシステムから切断されているシステムに PowerShellGet とその依存関係をコピーします。</span><span class="sxs-lookup"><span data-stu-id="888d8-185">Copy PowerShellGet and its dependencies from the internet-connected system to the disconnected system</span></span>
- <span data-ttu-id="888d8-186">使用して、`Install-PowerShellGetOffline`切断されているシステムに PowerShellGet とその依存関係を適切なフォルダーに配置</span><span class="sxs-lookup"><span data-stu-id="888d8-186">Use the `Install-PowerShellGetOffline` on the disconnected system to place PowerShellGet and its dependencies into the proper folders</span></span>

<span data-ttu-id="888d8-187">使用して、次のコマンド`Save-PowerShellGetForOffline`フォルダーにすべてのコンポーネントを配置するには `f:\OfflinePowerShellGet`</span><span class="sxs-lookup"><span data-stu-id="888d8-187">The following commands use `Save-PowerShellGetForOffline` to put all the components into a folder `f:\OfflinePowerShellGet`</span></span>

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="888d8-188">この時点での内容を行う必要があります`F:\OfflinePowerShellGet`切断されているシステムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="888d8-188">At this point, you must make the contents of `F:\OfflinePowerShellGet` available to your disconnected systems.</span></span> <span data-ttu-id="888d8-189">実行、`Install-PowerShellGetOffline`コマンドレットを切断されているシステムに PowerShellGet をインストールします。</span><span class="sxs-lookup"><span data-stu-id="888d8-189">Run the `Install-PowerShellGetOffline` cmdlet to install PowerShellGet on the disconnected system.</span></span>

> [!NOTE]
> <span data-ttu-id="888d8-190">これらのコマンドを実行する前に、PowerShell セッションで PowerShellGet を実行しないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="888d8-190">It is important that you do not run PowerShellGet in the PowerShell session before running these commands.</span></span> <span data-ttu-id="888d8-191">PowerShellGet がセッションに読み込まれると、コンポーネントを更新できません。</span><span class="sxs-lookup"><span data-stu-id="888d8-191">Once PowerShellGet is loaded into the session, the components cannot be updated.</span></span> <span data-ttu-id="888d8-192">PowerShellGet を誤ってを開始する実行を終了し、PowerShell を再起動します。</span><span class="sxs-lookup"><span data-stu-id="888d8-192">If you do start PowerShellGet by mistake, exit and restart PowerShell.</span></span>

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="888d8-193">これらのコマンドを実行した後、ローカル リポジトリに PowerShellGet を発行する準備が完了したら。</span><span class="sxs-lookup"><span data-stu-id="888d8-193">After running these commands, you are ready to publish PowerShellGet to your local repository.</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> <span data-ttu-id="888d8-194">セキュリティを確保するには、API キーのスクリプトにハード コーディングされてはなりません。</span><span class="sxs-lookup"><span data-stu-id="888d8-194">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="888d8-195">セキュリティで保護されたキー管理システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="888d8-195">Use a secure key management system.</span></span>

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
