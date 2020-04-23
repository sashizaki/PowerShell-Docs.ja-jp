---
ms.date: 11/06/2018
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery, PsGet
title: ローカルの PSRepositories の操作
ms.openlocfilehash: c1bd905674ae76a3badd3eff50780f0e1bb5fc64
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "75415816"
---
# <a name="working-with-private-powershellget-repositories"></a><span data-ttu-id="b1ec8-103">PowerShellGet プライベート リポジトリの操作</span><span class="sxs-lookup"><span data-stu-id="b1ec8-103">Working with Private PowerShellGet Repositories</span></span>

<span data-ttu-id="b1ec8-104">PowerShellGet モジュールでは、PowerShell ギャラリー以外のリポジトリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-104">The PowerShellGet module support repositories other than the PowerShell Gallery.</span></span>
<span data-ttu-id="b1ec8-105">これらのコマンドレットにより、次のシナリオが可能になります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-105">These cmdlets enable the following scenarios:</span></span>

- <span data-ttu-id="b1ec8-106">環境内で使用するための、信頼された事前検証済みの PowerShell モジュールのセットをサポートする</span><span class="sxs-lookup"><span data-stu-id="b1ec8-106">Support a trusted, pre-validated set of PowerShell modules for use in your environment</span></span>
- <span data-ttu-id="b1ec8-107">PowerShell モジュールまたはスクリプトを構築する CI/CD パイプラインをテストする</span><span class="sxs-lookup"><span data-stu-id="b1ec8-107">Testing a CI/CD pipeline that builds PowerShell modules or scripts</span></span>
- <span data-ttu-id="b1ec8-108">インターネットにアクセスできないシステムに PowerShell スクリプトおよびモジュールを提供する</span><span class="sxs-lookup"><span data-stu-id="b1ec8-108">Deliver PowerShell scripts and modules to systems that can't access the internet</span></span>
- <span data-ttu-id="b1ec8-109">組織でのみ使用できる PowerShell スクリプトとモジュールを提供する</span><span class="sxs-lookup"><span data-stu-id="b1ec8-109">Deliver PowerShell scripts and modules only available to your organization</span></span>

<span data-ttu-id="b1ec8-110">この記事では、ローカル PowerShell リポジトリを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-110">This article describes how to set up a local PowerShell repository.</span></span> <span data-ttu-id="b1ec8-111">また、PowerShell ギャラリーから使用できる [OfflinePowerShellGetDeploy][] モジュールについても説明します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-111">The article also covers the [OfflinePowerShellGetDeploy][] module available from the PowerShell Gallery.</span></span> <span data-ttu-id="b1ec8-112">このモジュールには、ローカル リポジトリに PowerShellGet の最新バージョンをインストールするためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-112">This module contains cmdlets to install the latest version of PowerShellGet into your local repository.</span></span>

## <a name="local-repository-types"></a><span data-ttu-id="b1ec8-113">ローカル リポジトリの種類</span><span class="sxs-lookup"><span data-stu-id="b1ec8-113">Local repository types</span></span>

<span data-ttu-id="b1ec8-114">ローカル PSRepository を作成するには、次の 2 つの方法があります: NuGet サーバーまたはファイル共有。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-114">There are two ways to create a local PSRepository: NuGet server or file share.</span></span> <span data-ttu-id="b1ec8-115">種類ごとに長所と短所があります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-115">Each type has advantages and disadvantages:</span></span>

### <a name="nuget-server"></a><span data-ttu-id="b1ec8-116">NuGet サーバー</span><span class="sxs-lookup"><span data-stu-id="b1ec8-116">NuGet Server</span></span>

| <span data-ttu-id="b1ec8-117">長所</span><span class="sxs-lookup"><span data-stu-id="b1ec8-117">Advantages</span></span>| <span data-ttu-id="b1ec8-118">短所</span><span class="sxs-lookup"><span data-stu-id="b1ec8-118">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="b1ec8-119">PowerShellGallery の機能を正確に模倣します</span><span class="sxs-lookup"><span data-stu-id="b1ec8-119">Closely mimics PowerShellGallery functionality</span></span> | <span data-ttu-id="b1ec8-120">多層アプリでは、運用の計画とサポートが必要です</span><span class="sxs-lookup"><span data-stu-id="b1ec8-120">Multi-tier app requires operations planning & support</span></span> |
| <span data-ttu-id="b1ec8-121">NuGet は、Visual Studio や他のツールと統合します</span><span class="sxs-lookup"><span data-stu-id="b1ec8-121">NuGet integrates with Visual Studio, other tools</span></span> | <span data-ttu-id="b1ec8-122">認証モデルと NuGet アカウントの管理が必要です</span><span class="sxs-lookup"><span data-stu-id="b1ec8-122">Authentication model and NuGet accounts management needed</span></span> |
| <span data-ttu-id="b1ec8-123">NuGet では、`.Nupkg` パッケージ内のメタデータがサポートされます</span><span class="sxs-lookup"><span data-stu-id="b1ec8-123">NuGet supports metadata in `.Nupkg` packages</span></span> | <span data-ttu-id="b1ec8-124">発行には、API キーの管理とメンテナンスが必要です</span><span class="sxs-lookup"><span data-stu-id="b1ec8-124">Publishing requires API Key management & maintenance</span></span> |
| <span data-ttu-id="b1ec8-125">検索、パッケージ管理などが提供されます</span><span class="sxs-lookup"><span data-stu-id="b1ec8-125">Provides search, package administration, etc.</span></span> | |

### <a name="file-share"></a><span data-ttu-id="b1ec8-126">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="b1ec8-126">File Share</span></span>

| <span data-ttu-id="b1ec8-127">長所</span><span class="sxs-lookup"><span data-stu-id="b1ec8-127">Advantages</span></span>| <span data-ttu-id="b1ec8-128">短所</span><span class="sxs-lookup"><span data-stu-id="b1ec8-128">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="b1ec8-129">セットアップ、バックアップ、メンテナンスが簡単です</span><span class="sxs-lookup"><span data-stu-id="b1ec8-129">Easy to set up, back up, and maintain</span></span> | <span data-ttu-id="b1ec8-130">PowerShellGet で使用されるメタデータは使用できません</span><span class="sxs-lookup"><span data-stu-id="b1ec8-130">Metadata used by PowerShellGet isn't available</span></span> |
| <span data-ttu-id="b1ec8-131">セキュリティ モデルがシンプルです (共有に対するユーザーのアクセス許可)</span><span class="sxs-lookup"><span data-stu-id="b1ec8-131">Simple security model - user permissions on the share</span></span> | <span data-ttu-id="b1ec8-132">基本的なファイル共有以外の UI はありません</span><span class="sxs-lookup"><span data-stu-id="b1ec8-132">No UI beyond basic file share</span></span> |
| <span data-ttu-id="b1ec8-133">既存の項目を置換などの制約はありません</span><span class="sxs-lookup"><span data-stu-id="b1ec8-133">No constraints such as replacing existing items</span></span> | <span data-ttu-id="b1ec8-134">セキュリティに制限があり、誰が何を更新したか記録されません</span><span class="sxs-lookup"><span data-stu-id="b1ec8-134">Limited security and no recording of who updates what</span></span> |

<span data-ttu-id="b1ec8-135">PowerShellGet はどちらの種類およびサポートでも動作し、バージョンと依存関係のインストールを特定します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-135">PowerShellGet works with either type and supports locating versions and dependency installation.</span></span>
<span data-ttu-id="b1ec8-136">ただし、PowerShell ギャラリーでは動作するいくつかの機能が、基本の NuGet サーバーまたはファイル共有に対しては使用できません。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-136">However, some features that work for the PowerShell Gallery aren't available for base NuGet servers or file shares.</span></span>

- <span data-ttu-id="b1ec8-137">すべてはパッケージです。スクリプト、モジュール、DSC リソース、ロールの機能の区別はありません。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-137">Everything is a package - no differentiation of scripts, modules, DSC resources, or role capabilities.</span></span>
- <span data-ttu-id="b1ec8-138">ファイル共有サーバーは、タグを含むパッケージのメタデータを認識できません。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-138">File share servers can't see package metadata, including tags.</span></span>

## <a name="creating-a-local-repository"></a><span data-ttu-id="b1ec8-139">ローカル リポジトリを作成する</span><span class="sxs-lookup"><span data-stu-id="b1ec8-139">Creating a local repository</span></span>

<span data-ttu-id="b1ec8-140">次の記事では、独自の NuGet サーバーを設定するための手順が示されています。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-140">The following article lists the steps for setting up your own NuGet Server.</span></span>

- <span data-ttu-id="b1ec8-141">[NuGet.Server][]</span><span class="sxs-lookup"><span data-stu-id="b1ec8-141">[NuGet.Server][]</span></span>

<span data-ttu-id="b1ec8-142">パッケージを追加する時点までの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-142">Follow the steps up to the point of adding packages.</span></span> <span data-ttu-id="b1ec8-143">[パッケージを公開する](#publishing-to-a-local-repository)ための手順は、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-143">The steps for [publishing a package](#publishing-to-a-local-repository) are covered later in this article.</span></span>

<span data-ttu-id="b1ec8-144">ファイル共有ベースのリポジトリでは、ユーザーにファイル共有にアクセスするためのアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-144">For a file share-based repository, make sure that your users have permissions to access the file share.</span></span>

## <a name="registering-a-local-repository"></a><span data-ttu-id="b1ec8-145">ローカル リポジトリを登録する</span><span class="sxs-lookup"><span data-stu-id="b1ec8-145">Registering a local repository</span></span>

<span data-ttu-id="b1ec8-146">リポジトリを使用するには、その前に `Register-PSRepository` コマンドを使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-146">Before a repository can be used, it must be registered using the `Register-PSRepository` command.</span></span>
<span data-ttu-id="b1ec8-147">次の例では、独自のリポジトリを信頼しているという前提で、**InstallationPolicy** を *Trusted* に設定しています。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-147">In the examples below, the **InstallationPolicy** is set to *Trusted*, on the assumption that you trust your own repository.</span></span>

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

<span data-ttu-id="b1ec8-148">2 つのコマンドでの **ScriptSourceLocation** の処理方法の違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-148">Take note of the difference between how the two commands handle **ScriptSourceLocation**.</span></span> <span data-ttu-id="b1ec8-149">ファイル共有ベースのリポジトリでは、**SourceLocation** と **ScriptSourceLocation** が一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-149">For a file share-based repositories, the **SourceLocation** and **ScriptSourceLocation** must match.</span></span> <span data-ttu-id="b1ec8-150">Web ベースのリポジトリでは、それらが異なる必要があるため、この例では、**SourceLocation** の最後に "/" が追加されています。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-150">For a web-based repository, they must be different, so in this example a trailing "/" is added to the **SourceLocation**.</span></span>

<span data-ttu-id="b1ec8-151">新しく作成する PSRepository を既定のリポジトリにする場合は、他のすべての PSRepository の登録を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-151">If you want the newly created PSRepository to be the default repository, you must unregister all other PSRepositories.</span></span> <span data-ttu-id="b1ec8-152">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-152">For example:</span></span>

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> <span data-ttu-id="b1ec8-153">リポジトリ名 "PSGallery" は、PowerShell ギャラリーで使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-153">The repository name 'PSGallery' is reserved for use by the PowerShell Gallery.</span></span> <span data-ttu-id="b1ec8-154">PSGallery を登録解除することはできますが、他のリポジトリに対して名前 PSGallery を再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-154">You can unregister PSGallery, but you cannot reuse the name PSGallery for any other repository.</span></span>

<span data-ttu-id="b1ec8-155">PSGallery を元に戻す必要がある場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-155">If you need to restore the PSGallery, run the following command:</span></span>

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a><span data-ttu-id="b1ec8-156">ローカル リポジトリに発行する</span><span class="sxs-lookup"><span data-stu-id="b1ec8-156">Publishing to a local repository</span></span>

<span data-ttu-id="b1ec8-157">ローカル PSRepository を登録した後は、ローカル PSRepository に対して発行できます。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-157">Once you've registered the local PSRepository, you can publish to your local PSRepository.</span></span> <span data-ttu-id="b1ec8-158">2 つの主な発行シナリオがあります。独自のモジュールの発行と、PSGallery からのモジュールの発行です。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-158">There are two main publishing scenarios: publishing your own module and publishing a module from the PSGallery.</span></span>

### <a name="publishing-a-module-you-authored"></a><span data-ttu-id="b1ec8-159">自分で作成したモジュールを発行する</span><span class="sxs-lookup"><span data-stu-id="b1ec8-159">Publishing a module you authored</span></span>

<span data-ttu-id="b1ec8-160">PowerShell ギャラリーの場合と同じように、`Publish-Module` および `Publish-Script` を使用してローカル環境の PSRepository に自分のモジュールを発行します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-160">Use `Publish-Module` and `Publish-Script` to publish your module to your local PSRepository the same way you do for the PowerShell Gallery.</span></span>

- <span data-ttu-id="b1ec8-161">コードの場所を指定します</span><span class="sxs-lookup"><span data-stu-id="b1ec8-161">Specify the location for your code</span></span>
- <span data-ttu-id="b1ec8-162">API キーを指定します</span><span class="sxs-lookup"><span data-stu-id="b1ec8-162">Supply an API key</span></span>
- <span data-ttu-id="b1ec8-163">リポジトリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-163">Specify the repository name.</span></span> <span data-ttu-id="b1ec8-164">たとえば、`-PSRepository LocalPSRepo` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-164">For example, `-PSRepository LocalPSRepo`</span></span>

> [!NOTE]
> <span data-ttu-id="b1ec8-165">NuGet サーバーにアカウントを作成した後、サインインし、API キーを生成して保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-165">You must create an account in the NuGet server, then sign in to generate and save the API key.</span></span>
> <span data-ttu-id="b1ec8-166">ファイル共有の場合は、NuGetApiKey の値に対して任意の空白でない文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-166">For a file share, use any non-blank string for the NuGetApiKey value.</span></span>

<span data-ttu-id="b1ec8-167">例 :</span><span class="sxs-lookup"><span data-stu-id="b1ec8-167">Examples:</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'
```

```powershell
# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> <span data-ttu-id="b1ec8-168">セキュリティを確保するため、API キーをスクリプトにハード コーディングしてはなりません。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-168">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="b1ec8-169">セキュリティ保護されたキー管理システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-169">Use a secure key management system.</span></span>

### <a name="publishing-a-module-from-the-psgallery"></a><span data-ttu-id="b1ec8-170">PSGallery からモジュールを発行する</span><span class="sxs-lookup"><span data-stu-id="b1ec8-170">Publishing a module from the PSGallery</span></span>

<span data-ttu-id="b1ec8-171">ローカル環境の PSRepository に PSGallery からモジュールを発行するには、"Save-Package" コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-171">To publish a module from the PSGallery to your local PSRepository, you can use the 'Save-Package' cmdlet.</span></span>

- <span data-ttu-id="b1ec8-172">パッケージの名前を指定します</span><span class="sxs-lookup"><span data-stu-id="b1ec8-172">Specify the Name of the Package</span></span>
- <span data-ttu-id="b1ec8-173">プロバイダーとして "NuGet" を指定します</span><span class="sxs-lookup"><span data-stu-id="b1ec8-173">Specify 'NuGet' as the Provider</span></span>
- <span data-ttu-id="b1ec8-174">ソースとして PSGallery の場所を指定します (https://www.powershellgallery.com/api/v2)</span><span class="sxs-lookup"><span data-stu-id="b1ec8-174">Specify the PSGallery location as the source (https://www.powershellgallery.com/api/v2)</span></span>
- <span data-ttu-id="b1ec8-175">ローカル リポジトリへのパスを指定します</span><span class="sxs-lookup"><span data-stu-id="b1ec8-175">Specify the path to your local Repository</span></span>

<span data-ttu-id="b1ec8-176">例:</span><span class="sxs-lookup"><span data-stu-id="b1ec8-176">Example:</span></span>

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider NuGet -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

<span data-ttu-id="b1ec8-177">ローカル PSRepository が Web ベースの場合は、nuget.exe を使用して発行する追加の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-177">If your local PSRepository is web-based, it requires an additional step that uses nuget.exe to publish.</span></span>

<span data-ttu-id="b1ec8-178">[nuget.exe][] の使用についてはドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-178">See the documentation for using [nuget.exe][].</span></span>

## <a name="installing-powershellget-on-a-disconnected-system"></a><span data-ttu-id="b1ec8-179">オフラインのシステムに PowerShellGet をインストールする</span><span class="sxs-lookup"><span data-stu-id="b1ec8-179">Installing PowerShellGet on a disconnected system</span></span>

<span data-ttu-id="b1ec8-180">インターネットに接続されていないシステムが必要な環境に PowerShellGet を展開するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-180">Deploying PowerShellGet is difficult in environments that require systems to be disconnected from the internet.</span></span> <span data-ttu-id="b1ec8-181">PowerShellGet を初めて使用するときは、最新バージョンをインストールするブートストラップ プロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-181">PowerShellGet has a bootstrap process that installs the latest version the first time it's used.</span></span> <span data-ttu-id="b1ec8-182">PowerShell ギャラリーの OfflinePowerShellGetDeploy モジュールでは、このブートストラップ プロセスをサポートするコマンドレットが提供されています。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-182">The OfflinePowerShellGetDeploy module in the PowerShell Gallery provides cmdlets that support this bootstrap process.</span></span>

<span data-ttu-id="b1ec8-183">オフラインの展開をブートストラップするには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-183">To bootstrap an offline deployment, you need to:</span></span>

- <span data-ttu-id="b1ec8-184">OfflinePowerShellGetDeploy をダウンロードし、インターネットに接続されたシステムと接続されていないシステムにインストールします</span><span class="sxs-lookup"><span data-stu-id="b1ec8-184">Download and install the OfflinePowerShellGetDeploy your internet-connected system and your disconnected systems</span></span>
- <span data-ttu-id="b1ec8-185">`Save-PowerShellGetForOffline` コマンドレットを使用して、PowerShellGet とその依存関係をインターネットに接続されたシステムにダウンロードします</span><span class="sxs-lookup"><span data-stu-id="b1ec8-185">Download PowerShellGet and its dependencies on the internet-connected system using the `Save-PowerShellGetForOffline` cmdlet</span></span>
- <span data-ttu-id="b1ec8-186">PowerShellGet とその依存関係を、インターネットに接続されたシステムから切断されたシステムにコピーします</span><span class="sxs-lookup"><span data-stu-id="b1ec8-186">Copy PowerShellGet and its dependencies from the internet-connected system to the disconnected system</span></span>
- <span data-ttu-id="b1ec8-187">切断されたシステムで `Install-PowerShellGetOffline` を使用して、PowerShellGet とその依存関係を適切なフォルダーに配置します</span><span class="sxs-lookup"><span data-stu-id="b1ec8-187">Use the `Install-PowerShellGetOffline` on the disconnected system to place PowerShellGet and its dependencies into the proper folders</span></span>

<span data-ttu-id="b1ec8-188">次のコマンドでは、`Save-PowerShellGetForOffline` を使用してすべてのコンポーネントを `f:\OfflinePowerShellGet` フォルダーに配置します</span><span class="sxs-lookup"><span data-stu-id="b1ec8-188">The following commands use `Save-PowerShellGetForOffline` to put all the components into a folder `f:\OfflinePowerShellGet`</span></span>

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="b1ec8-189">この時点で、`F:\OfflinePowerShellGet` の内容を切断されたシステムで使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-189">At this point, you must make the contents of `F:\OfflinePowerShellGet` available to your disconnected systems.</span></span> <span data-ttu-id="b1ec8-190">`Install-PowerShellGetOffline` コマンドレットを実行し、切断されたシステムに PowerShellGet をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-190">Run the `Install-PowerShellGetOffline` cmdlet to install PowerShellGet on the disconnected system.</span></span>

> [!NOTE]
> <span data-ttu-id="b1ec8-191">これらのコマンドを実行する前に、PowerShell セッションで PowerShellGet を実行しないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-191">It is important that you do not run PowerShellGet in the PowerShell session before running these commands.</span></span> <span data-ttu-id="b1ec8-192">PowerShellGet がセッションに読み込まれた後では、コンポーネントを更新できません。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-192">Once PowerShellGet is loaded into the session, the components cannot be updated.</span></span> <span data-ttu-id="b1ec8-193">誤って PowerShellGet を開始した場合は、終了して、PowerShell を再起動します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-193">If you do start PowerShellGet by mistake, exit and restart PowerShell.</span></span>

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="b1ec8-194">これらのコマンドの実行が済むと、ローカル リポジトリに PowerShellGet を発行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-194">After running these commands, you are ready to publish PowerShellGet to your local repository.</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

## <a name="use-packaging-solutions-to-host-powershellget-repositories"></a><span data-ttu-id="b1ec8-195">パッケージ化ソリューションを使用して PowerShellGet リポジトリをホストする</span><span class="sxs-lookup"><span data-stu-id="b1ec8-195">Use Packaging solutions to host PowerShellGet repositories</span></span>

<span data-ttu-id="b1ec8-196">また、Azure Artifacts などのパッケージ化ソリューションを使用して、プライベートまたはパブリックの PowerShellGet リポジトリをホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-196">You can also use packaging solutions like Azure Artifacts to host a private or public PowerShellGet repository.</span></span> <span data-ttu-id="b1ec8-197">詳細と手順については、[Azure Artifacts のドキュメント](https://docs.microsoft.com/azure/devops/artifacts/tutorials/private-powershell-library)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-197">For more information and instructions, see the [Azure Artifacts documentation](https://docs.microsoft.com/azure/devops/artifacts/tutorials/private-powershell-library).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1ec8-198">セキュリティを確保するため、API キーをスクリプトにハード コーディングしてはなりません。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-198">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="b1ec8-199">セキュリティ保護されたキー管理システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1ec8-199">Use a secure key management system.</span></span>

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
