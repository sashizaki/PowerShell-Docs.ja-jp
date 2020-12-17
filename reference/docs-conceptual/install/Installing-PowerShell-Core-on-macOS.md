---
title: macOS への PowerShell のインストール
description: macOS への PowerShell のインストールに関する情報
ms.date: 11/11/2020
ms.openlocfilehash: 1ce96e993d8fc87edd93fca840ede250d5632577
ms.sourcegitcommit: 3ab2951a5460a39ca5fb3d25ffcb1d8868f4e011
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "96535102"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="4a94e-103">macOS への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="4a94e-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="4a94e-104">PowerShell 7.0 以降には macOS 10.13 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a94e-104">PowerShell 7.0 or higher require macOS 10.13 and higher.</span></span> <span data-ttu-id="4a94e-105">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-105">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="4a94e-106">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="4a94e-106">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="4a94e-107">PowerShell 7.1 はインプレース アップグレードで、PowerShell Core 6.x と 7.0 は削除されます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-107">PowerShell 7.1 is an in-place upgrade that removes PowerShell Core 6.x and 7.0.</span></span>
>
> <span data-ttu-id="4a94e-108">`/usr/local/microsoft/powershell/6` フォルダーは `/usr/local/microsoft/powershell/7` に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="4a94e-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="4a94e-109">PowerShell コアの旧バージョンを PowerShell 7.1 と side-by-side 実行する必要がある場合、[バイナリ アーカイブ](#binary-archives)手法を使用し、必要なバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-109">If you need to run and older version of PowerShell core side-by-side with PowerShell 7.1, install the version you want using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="4a94e-110">macOS に PowerShell をインストールするには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-110">There are several ways to install PowerShell on macOS.</span></span> <span data-ttu-id="4a94e-111">以下のいずれかの方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="4a94e-111">Choose one of the following methods:</span></span>

- <span data-ttu-id="4a94e-112">Homebrew を使用してインストールする。</span><span class="sxs-lookup"><span data-stu-id="4a94e-112">Install using Homebrew.</span></span> <span data-ttu-id="4a94e-113">Homebrew は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="4a94e-113">Homebrew is the preferred package manager for macOS.</span></span>
- <span data-ttu-id="4a94e-114">[直接ダウンロード](#installation-via-direct-download)を使用して PowerShell をインストールする。</span><span class="sxs-lookup"><span data-stu-id="4a94e-114">Install PowerShell via [Direct Download](#installation-via-direct-download)</span></span>
- <span data-ttu-id="4a94e-115">[バイナリ アーカイブ](#binary-archives)からインストールする。</span><span class="sxs-lookup"><span data-stu-id="4a94e-115">Install from [binary archives](#binary-archives).</span></span>

<span data-ttu-id="4a94e-116">PowerShell をインストールした後、[OpenSSL](#installing-dependencies) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-116">After installing PowerShell, you should install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="4a94e-117">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a94e-117">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="4a94e-118">macOS 10.13 以降で Homebrew を使用した最新の安定版リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="4a94e-118">Installation of latest stable release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="4a94e-119">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-119">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="4a94e-120">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-120">Now, you can install PowerShell:</span></span>

```sh
brew install --cask powershell
```

<span data-ttu-id="4a94e-121">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a94e-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="4a94e-122">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="4a94e-122">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell --cask
```

> [!NOTE]
> <span data-ttu-id="4a94e-123">上記のコマンドは PowerShell (pwsh) ホスト内から呼び出すことができますが、その場合、アップグレードを完了するには、PowerShell シェルを終了し、再起動して、`$PSVersionTable` に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="4a94e-124">macOS 10.13 以降で Homebrew を使用した最新のプレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="4a94e-124">Installation of latest preview release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="4a94e-125">Homebrew をインストールしたら、PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-125">After you've installed Homebrew, you can install PowerShell.</span></span> <span data-ttu-id="4a94e-126">最初に、[Cask-Versions][cask-versions] パッケージをインストールします。これにより、cask パッケージの代替バージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-126">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="4a94e-127">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-127">Now, you can install PowerShell:</span></span>

```sh
brew install --cask powershell-preview
```

<span data-ttu-id="4a94e-128">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a94e-128">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="4a94e-129">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="4a94e-129">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell-preview --cask
```

> [!NOTE]
> <span data-ttu-id="4a94e-130">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、</span><span class="sxs-lookup"><span data-stu-id="4a94e-130">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="4a94e-131">`$PSVersionTable` に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-131">and refresh the values shown in `$PSVersionTable`.</span></span>

<span data-ttu-id="4a94e-132">Homebrew tap メソッドを使用した PowerShell のインストールは、安定バージョンと LTS バージョンでもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4a94e-132">Installing PowerShell using the Homebrew tap method is also supported for stable and LTS versions.</span></span>

```sh
brew install powershell/tap/powershell
```

<span data-ttu-id="4a94e-133">これで、インストールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-133">You can now verify your install</span></span>

```sh
pwsh
```

<span data-ttu-id="4a94e-134">新しいバージョンの PowerShell がリリースされたら、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a94e-134">When new versions of PowerShell are released, simply run the following command.</span></span>

```sh
brew upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="4a94e-135">cask メソッドと tap メソッドのどちらを使用する場合でも、新しいバージョンの PowerShell に更新するときに、PowerShell の初期インストールに使用したものと同じメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a94e-135">Whether you use the cask or the tap method, when updating to a newer version of PowerShell, use the same method you used to initially install PowerShell.</span></span> <span data-ttu-id="4a94e-136">別のメソッドを使用する場合、新しい pwsh セッションを開くと、古いバージョンの PowerShell が引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-136">If you use a different method, opening a new pwsh session will continue to use the older version of PowerShell.</span></span>
>
> <span data-ttu-id="4a94e-137">別のメソッドを使用することを選択した場合は、[Homebrew link メソッドを使用して](https://docs.brew.sh/Manpage#link-ln-options-formula)問題を修正する方法があります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-137">If you do decide to use different methods, there are ways to correct the issue using the [Homebrew link method](https://docs.brew.sh/Manpage#link-ln-options-formula).</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="4a94e-138">直接ダウンロードによるインストール</span><span class="sxs-lookup"><span data-stu-id="4a94e-138">Installation via Direct Download</span></span>

<span data-ttu-id="4a94e-139">[リリース][] ページから macOS マシンに PKG パッケージ `powershell-7.1.0-osx-x64.pkg` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-139">Download the PKG package `powershell-7.1.0-osx-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="4a94e-140">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-140">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-7.1.0-osx-x64.pkg -target /
```

<span data-ttu-id="4a94e-141">[OpenSSL](#installing-dependencies) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-141">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="4a94e-142">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a94e-142">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="4a94e-143">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="4a94e-143">Install as a .NET Global tool</span></span>

<span data-ttu-id="4a94e-144">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-144">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="4a94e-145">dotnet tool install によって、`PATH` 環境変数に `~/.dotnet/tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-145">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="4a94e-146">ただし、現在実行中のシェルには更新された `PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="4a94e-146">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="4a94e-147">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できるはずです。</span><span class="sxs-lookup"><span data-stu-id="4a94e-147">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

<span data-ttu-id="4a94e-148">[OpenSSL](#installing-dependencies) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-148">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="4a94e-149">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a94e-149">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="4a94e-150">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="4a94e-150">Binary Archives</span></span>

<span data-ttu-id="4a94e-151">macOS プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4a94e-151">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span> <span data-ttu-id="4a94e-152">この方法を使用してインストールする場合は、依存関係を手動でインストールする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-152">When you install using this method you must also manually install any dependencies.</span></span>

<span data-ttu-id="4a94e-153">[OpenSSL](#installing-dependencies) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-153">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="4a94e-154">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a94e-154">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="4a94e-155">macOS へのバイナリ アーカイブのインストール</span><span class="sxs-lookup"><span data-stu-id="4a94e-155">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.1.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.1.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.1.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.1.0/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a><span data-ttu-id="4a94e-156">依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="4a94e-156">Installing dependencies</span></span>

<span data-ttu-id="4a94e-157">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a94e-157">OpenSSL is required for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="4a94e-158">必要に応じて、MacPorts を使用して OpenSSL をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-158">You can install OpenSSL via MacPorts if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="4a94e-159">MacPorts と Homebrew を同じシステムで一緒に使用すると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-159">MacPorts and Homebrew can have problems when used to together on the same system.</span></span> <span data-ttu-id="4a94e-160">ただし、Homebrew には OpenSSL 1.0 用のパッケージがありません。</span><span class="sxs-lookup"><span data-stu-id="4a94e-160">However, Homebrew does not have a package for OpenSSL 1.0.</span></span> <span data-ttu-id="4a94e-161">詳細については、[MacPorts の FAQ](https://trac.macports.org/wiki/FAQ) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a94e-161">For more information, see the [MacPorts FAQ](https://trac.macports.org/wiki/FAQ).</span></span>

1. <span data-ttu-id="4a94e-162">Xcode コマンド ライン ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-162">Install the Xcode command-line tools.</span></span> <span data-ttu-id="4a94e-163">MacPorts には Xcode ツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4a94e-163">The Xcode tools are required by MacPorts.</span></span>

   ```sh
   xcode-select --install
   ```

1. <span data-ttu-id="4a94e-164">MacPorts をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-164">Install MacPorts.</span></span> <span data-ttu-id="4a94e-165">手順が必要な場合は、[インストール ガイド](https://www.macports.org/install.php)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4a94e-165">If you need instructions, refer to the [installation guide](https://www.macports.org/install.php).</span></span>
1. <span data-ttu-id="4a94e-166">`sudo port selfupdate` を実行して MacPorts を更新します。</span><span class="sxs-lookup"><span data-stu-id="4a94e-166">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="4a94e-167">`sudo port upgrade outdated` を実行して MacPorts パッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-167">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="4a94e-168">`sudo port install openssl10` を実行して OpenSSL をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-168">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="4a94e-169">PowerShell で使用できるようにライブラリをリンクします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-169">Link the libraries to make them available to PowerShell:</span></span>

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a><span data-ttu-id="4a94e-170">PowerShell のアンインストール</span><span class="sxs-lookup"><span data-stu-id="4a94e-170">Uninstalling PowerShell</span></span>

<span data-ttu-id="4a94e-171">Homebrew を使って PowerShell をインストールした場合は、次のコマンドを使ってアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="4a94e-171">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="4a94e-172">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-172">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="4a94e-173">追加の PowerShell パスを削除するには、このドキュメントの「[パス](#paths)」セクションを参照し、`sudo rm` を使用してパスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="4a94e-173">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="4a94e-174">Homebrew でインストールした場合、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="4a94e-174">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="4a94e-175">パス</span><span class="sxs-lookup"><span data-stu-id="4a94e-175">Paths</span></span>

- <span data-ttu-id="4a94e-176">`$PSHOME` は `/usr/local/microsoft/powershell/7.1.0/` です</span><span class="sxs-lookup"><span data-stu-id="4a94e-176">`$PSHOME` is `/usr/local/microsoft/powershell/7.1.0/`</span></span>
- <span data-ttu-id="4a94e-177">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="4a94e-177">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="4a94e-178">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="4a94e-178">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="4a94e-179">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="4a94e-179">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="4a94e-180">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="4a94e-180">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="4a94e-181">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="4a94e-181">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="4a94e-182">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="4a94e-182">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="4a94e-183">プロファイルには、PowerShell のホスト単位の構成が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="4a94e-183">The profiles respect PowerShell's per-host configuration.</span></span> <span data-ttu-id="4a94e-184">そのため、既定のホスト固有のプロファイルは、同じ場所の `Microsoft.PowerShell_profile.ps1` に存在します。</span><span class="sxs-lookup"><span data-stu-id="4a94e-184">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="4a94e-185">PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="4a94e-185">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="4a94e-186">macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-186">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span> <span data-ttu-id="4a94e-187">そのため、`$PSHOME` は `/usr/local/microsoft/powershell/7.1.0/` となり、シンボリック リンクは `/usr/local/bin/pwsh` に配置されます。</span><span class="sxs-lookup"><span data-stu-id="4a94e-187">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.1.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="installation-support"></a><span data-ttu-id="4a94e-188">インストールのサポート</span><span class="sxs-lookup"><span data-stu-id="4a94e-188">Installation support</span></span>

<span data-ttu-id="4a94e-189">Microsoft は、このドキュメントでインストール方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4a94e-189">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="4a94e-190">他のソースには、利用可能な別のインストール方法が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a94e-190">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="4a94e-191">そのようなツールと方法は機能しても、Microsoft ではそれらの方法をサポートできません。</span><span class="sxs-lookup"><span data-stu-id="4a94e-191">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4a94e-192">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="4a94e-192">Additional Resources</span></span>

- <span data-ttu-id="4a94e-193">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="4a94e-193">[Homebrew Web][brew]</span></span>
- <span data-ttu-id="4a94e-194">[Homebrew Github リポジトリ][GitHub]</span><span class="sxs-lookup"><span data-stu-id="4a94e-194">[Homebrew Github Repository][GitHub]</span></span>
- <span data-ttu-id="4a94e-195">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="4a94e-195">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
