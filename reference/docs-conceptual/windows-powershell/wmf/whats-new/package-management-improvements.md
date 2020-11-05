---
ms.date: 06/12/2017
title: WMF 5.1 のパッケージ管理の機能強化
description: Windows PowerShell 5.1 には、更新された Package Management コマンドレットが含まれています。
ms.openlocfilehash: 572ebd1f0aa3cf09579e13c3ea52ae3e979e421f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663189"
---
# <a name="improvements-to-package-management-in-wmf-51"></a><span data-ttu-id="9122e-103">WMF 5.1 のパッケージ管理の機能強化</span><span class="sxs-lookup"><span data-stu-id="9122e-103">Improvements to Package Management in WMF 5.1</span></span>

<span data-ttu-id="9122e-104">WMF 5.1 で行われた修正:</span><span class="sxs-lookup"><span data-stu-id="9122e-104">The following are the fixes made in the WMF 5.1:</span></span>

## <a name="version-alias"></a><span data-ttu-id="9122e-105">バージョン エイリアス</span><span class="sxs-lookup"><span data-stu-id="9122e-105">Version Alias</span></span>

<span data-ttu-id="9122e-106">**シナリオ** : パッケージ P1 のバージョン 1.0 および 2.0 がシステムにインストールされていて、バージョン 1.0 をアンインストールしたい場合、`Uninstall-Package -Name P1 -Version 1.0` を実行し、このコマンドレットを実行するとバージョン 1.0 がアンインストールされるものと期待します。</span><span class="sxs-lookup"><span data-stu-id="9122e-106">**Scenario** : If you have version 1.0 and 2.0 of a package, P1, installed on your system, and you want to uninstall version 1.0, you would run `Uninstall-Package -Name P1 -Version 1.0` and expect version 1.0 to be uninstalled after running the cmdlet.</span></span> <span data-ttu-id="9122e-107">しかし、結果はバージョン 2.0 がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9122e-107">However the result is that version 2.0 gets uninstalled.</span></span>

<span data-ttu-id="9122e-108">このようになるのは、`-Version` パラメーターが `-MinimumVersion` パラメーターのエイリアスであるためです。</span><span class="sxs-lookup"><span data-stu-id="9122e-108">This occurs because the `-Version` parameter is an alias of the `-MinimumVersion` parameter.</span></span> <span data-ttu-id="9122e-109">PackageManagement は、最小バージョンが 1.0 という条件を満たすパッケージを探して、最新のバージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="9122e-109">When PackageManagement is looking for a qualified package with the minimum version of 1.0, it returns the latest version.</span></span> <span data-ttu-id="9122e-110">たいていの場合は最新バージョンを探すのが目的の結果なので、この動作は通常であれば想定したものです。</span><span class="sxs-lookup"><span data-stu-id="9122e-110">This behavior is expected in normal cases because finding the latest version is usually the desired result.</span></span> <span data-ttu-id="9122e-111">ただし、`Uninstall-Package` の場合には当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="9122e-111">However, it should not apply to the `Uninstall-Package` case.</span></span>

<span data-ttu-id="9122e-112">**解決策** : PackageManagement (別名 OneGet) および PowerShellGet で `-Version` エイリアス全体を削除しました</span><span class="sxs-lookup"><span data-stu-id="9122e-112">**Solution** :removed `-Version` alias entirely in PackageManagement (a.k.a.</span></span> <span data-ttu-id="9122e-113">。</span><span class="sxs-lookup"><span data-stu-id="9122e-113">OneGet) and PowerShellGet.</span></span>

## <a name="multiple-prompts-for-bootstrapping-the-nuget-provider"></a><span data-ttu-id="9122e-114">NuGet プロバイダーのブートストラップに対する複数のプロンプト</span><span class="sxs-lookup"><span data-stu-id="9122e-114">Multiple prompts for bootstrapping the NuGet provider</span></span>

<span data-ttu-id="9122e-115">**シナリオ** : `Find-Module`、`Install-Module` または他の PackageManagement コマンドレットをコンピューターで初めて実行すると、PackageManagement は NuGet プロバイダーをブートストラップしようとします。</span><span class="sxs-lookup"><span data-stu-id="9122e-115">**Scenario** : When you run `Find-Module` or `Install-Module` or other PackageManagement cmdlets on your computer for the first time, PackageManagement tries to bootstrap the NuGet provider.</span></span> <span data-ttu-id="9122e-116">これは、PowerShellGet プロバイダーは PowerShell モジュールをダウンロードするために NuGet プロバイダーも使用するためです。</span><span class="sxs-lookup"><span data-stu-id="9122e-116">It does this because the PowerShellGet provider also uses the NuGet provider to download PowerShell modules.</span></span>
<span data-ttu-id="9122e-117">そのとき、PackageManagement は NuGet プロバイダーをインストールする許可をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="9122e-117">PackageManagement then prompts the user for permission to install the NuGet provider.</span></span> <span data-ttu-id="9122e-118">ユーザーがブートストラップに対して "はい" を選択すると、最新バージョンの NuGet プロバイダーがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9122e-118">After the user selects "yes" for the bootstrapping, the latest version of the NuGet provider will be installed.</span></span>

<span data-ttu-id="9122e-119">ただし、古いバージョンの NuGet プロバイダーがコンピューターにインストールされている場合があり、古いバージョンの NuGet が PowerShell セッションに最初に読み込まれることがあります (PackageManagement での競合状態)。</span><span class="sxs-lookup"><span data-stu-id="9122e-119">However, in some cases, when you have an old version of NuGet provider installed on your computer, the older version of NuGet sometimes gets loaded first into the PowerShell session (that's the race condition in PackageManagement).</span></span> <span data-ttu-id="9122e-120">ただし、PowerShellGet が動作するには新しいバージョンの NuGet プロバイダーが必要なので、PowerShellGet は PackageManagement に NuGet プロバイダーのブートストラップを再び要求します。</span><span class="sxs-lookup"><span data-stu-id="9122e-120">However PowerShellGet requires the later version of the NuGet provider to work, so PowerShellGet asks PackageManagement to bootstrap the NuGet provider again.</span></span>
<span data-ttu-id="9122e-121">これにより、NuGet プロバイダーのブートストラップで複数のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9122e-121">This results in multiple prompts for bootstrapping the NuGet provider.</span></span>

<span data-ttu-id="9122e-122">**解決策** : WMF 5.1 では、PackageManagement は、NuGet プロバイダーのブートストラップに対して複数のプロンプトが表示されるのを避けるため、NuGet プロバイダーの最新バージョンを読み込むようになっています。</span><span class="sxs-lookup"><span data-stu-id="9122e-122">**Solution** : In WMF5.1, PackageManagement loads the latest version of the NuGet provider to avoid multiple prompts for bootstrapping the NuGet provider.</span></span>

<span data-ttu-id="9122e-123">この問題を回避策することもできます。古いバージョンの NuGet プロバイダー (NuGet-Anycpu.exe) が存在する場合は、$env:ProgramFiles\PackageManagement\ProviderAssemblies または $env:LOCALAPPDATA\PackageManagement\ProviderAssemblies から手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="9122e-123">You could also work around this issue by manually deleting the old version of the NuGet provider (NuGet-Anycpu.exe) if exists from $env:ProgramFiles\PackageManagement\ProviderAssemblies $env:LOCALAPPDATA\PackageManagement\ProviderAssemblies</span></span>

## <a name="support-for-packagemanagement-on-computers-with-intranet-access-only"></a><span data-ttu-id="9122e-124">イントラネット アクセスのみのコンピューターでの PackageManagement のサポート</span><span class="sxs-lookup"><span data-stu-id="9122e-124">Support for PackageManagement on computers with Intranet access only</span></span>

<span data-ttu-id="9122e-125">**シナリオ** : エンタープライズのシナリオで、ユーザーはイントラネットのみでインターネット アクセスのない環境で作業しています。</span><span class="sxs-lookup"><span data-stu-id="9122e-125">**Scenario** : For the enterprise scenario, people are working under an environment where there is no Internet access but Intranet only.</span></span> <span data-ttu-id="9122e-126">PackageManagement は WMF 5.0 でこのケースをサポートしていませんでした。</span><span class="sxs-lookup"><span data-stu-id="9122e-126">PackageManagement did not support this case in WMF 5.0.</span></span>

<span data-ttu-id="9122e-127">**シナリオ** : WMF 5.0 の PackageManagement は、イントラネット アクセスしかない (インターネットにアクセスできない) コンピューターをサポートしませんでした。</span><span class="sxs-lookup"><span data-stu-id="9122e-127">**Scenario** : In WMF 5.0, PackageManagement did not support computers that have only Intranet (but not Internet) access.</span></span>

<span data-ttu-id="9122e-128">**解決策** : WMF 5.1 では、以下のようにして、イントラネット接続のみのコンピューターで PackageManagement を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9122e-128">**Solution** : In WMF 5.1, you can follow these steps to allow Intranet computers to use PackageManagement:</span></span>

1. <span data-ttu-id="9122e-129">インターネットに接続できる別のコンピューターで、`Install-PackageProvider -Name NuGet` を使用して、NuGet プロバイダーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9122e-129">Download the NuGet provider using another computer that has an Internet connection by using `Install-PackageProvider -Name NuGet`.</span></span>

2. <span data-ttu-id="9122e-130">`$env:ProgramFiles\PackageManagement\ProviderAssemblies\nuget` または `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\nuget` のいずれかで NuGet プロバイダーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="9122e-130">Find the NuGet provider under either `$env:ProgramFiles\PackageManagement\ProviderAssemblies\nuget` or `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\nuget`.</span></span>

3. <span data-ttu-id="9122e-131">イントラネット コンピューターがアクセスできるフォルダーまたはネットワーク共有の場所にバイナリをコピーし、`Install-PackageProvider -Name NuGet -Source <Path to folder>` を使用して NuGet プロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9122e-131">Copy the binaries to a folder or network share location that the Intranet computer can access, and then install the NuGet provider with `Install-PackageProvider -Name NuGet -Source <Path to folder>`.</span></span>

## <a name="event-logging-improvements"></a><span data-ttu-id="9122e-132">イベント ログの機能強化</span><span class="sxs-lookup"><span data-stu-id="9122e-132">Event logging improvements</span></span>

<span data-ttu-id="9122e-133">パッケージをインストールすると、コンピューターの状態が変化します。</span><span class="sxs-lookup"><span data-stu-id="9122e-133">When you install packages, you are changing the state of the computer.</span></span> <span data-ttu-id="9122e-134">WMF 5.1 の PackageManagement は、`Install-Package`、`Uninstall-Package`、`Save-Package` アクティビティのイベントを Windows イベント ログに記録するようになりました。</span><span class="sxs-lookup"><span data-stu-id="9122e-134">In WMF 5.1, PackageManagement now logs events to the Windows event log for `Install-Package`, `Uninstall-Package`, and `Save-Package` activities.</span></span> <span data-ttu-id="9122e-135">イベント ログは PowerShell の場合と同じで、`Microsoft-Windows-PowerShell, Operational` です。</span><span class="sxs-lookup"><span data-stu-id="9122e-135">The Event log is the same as for PowerShell, that is, `Microsoft-Windows-PowerShell, Operational`.</span></span>

## <a name="support-for-basic-authentication"></a><span data-ttu-id="9122e-136">基本認証のサポート</span><span class="sxs-lookup"><span data-stu-id="9122e-136">Support for basic authentication</span></span>

<span data-ttu-id="9122e-137">WMF 5.1 の PackageManagement は、基本認証を必要とするリポジトリからのパッケージの検索とインストールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9122e-137">In WMF 5.1, PackageManagement supports finding and installing packages from a repository that requires basic authentication.</span></span> <span data-ttu-id="9122e-138">`Find-Package` および `Install-Package` コマンドレットに資格情報を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="9122e-138">You can supply your credentials to the `Find-Package` and `Install-Package` cmdlets.</span></span> <span data-ttu-id="9122e-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9122e-139">For example:</span></span>

```powershell
Find-Package -Source <SourceWithCredential> -Credential (Get-Credential)
```

## <a name="support-for-using-packagemanagement-behind-a-proxy"></a><span data-ttu-id="9122e-140">プロキシの背後での PackageManagement の使用のサポート</span><span class="sxs-lookup"><span data-stu-id="9122e-140">Support for using PackageManagement behind a proxy</span></span>

<span data-ttu-id="9122e-141">WMF 5.1 の PackageManagement は、新しいプロキシ パラメーター `-ProxyCredential` と `-Proxy` を受け取るようになりました。</span><span class="sxs-lookup"><span data-stu-id="9122e-141">In WMF 5.1, PackageManagement now takes new proxy parameters `-ProxyCredential` and `-Proxy`.</span></span> <span data-ttu-id="9122e-142">これらのパラメーターを使用すると、プロキシの URL と資格情報を PackageManagement コマンドレットに対して指定できます。</span><span class="sxs-lookup"><span data-stu-id="9122e-142">Using these parameters, you can specify the proxy URL and credentials to PackageManagement cmdlets.</span></span> <span data-ttu-id="9122e-143">既定では、システムのプロキシ設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9122e-143">By default, system proxy settings are used.</span></span> <span data-ttu-id="9122e-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9122e-144">For example:</span></span>

```powershell
Find-Package -Source https://www.nuget.org/api/v2/ -Proxy http://www.myproxyserver.com -ProxyCredential (Get-Credential)
```
