---
title: macOS への PowerShell のインストール
description: macOS への PowerShell のインストールに関する情報
ms.date: 08/24/2020
ms.openlocfilehash: 8f38d573d9d67276dbc95cfb70f1fde80af62bb6
ms.sourcegitcommit: ea9270bacee7dd1b9df2519384de277576357ce2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88857899"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="72ae6-103">macOS への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="72ae6-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="72ae6-104">PowerShell は、macOS 10.12 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="72ae6-104">PowerShell supports macOS 10.12 and higher.</span></span> <span data-ttu-id="72ae6-105">PowerShell 7.0.3 以降と PowerShell Preview 7.1.0 以降には、macOS 10.13 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="72ae6-105">PowerShell 7.0.3 or higher and PowerShell Preview 7.1.0 or higher require macOS 10.13 and higher.</span></span> <span data-ttu-id="72ae6-106">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-106">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="72ae6-107">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="72ae6-107">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="72ae6-108">PowerShell 7 はインプレース アップグレードで、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-108">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="72ae6-109">`/usr/local/microsoft/powershell/6` フォルダーは `/usr/local/microsoft/powershell/7` に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="72ae6-109">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="72ae6-110">PowerShell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[バイナリ アーカイブ](#binary-archives)方法を使用して PowerShell 6 を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-110">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="72ae6-111">macOS に PowerShell をインストールするには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-111">There are several ways to install PowerShell on macOS.</span></span> <span data-ttu-id="72ae6-112">以下のいずれかの方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="72ae6-112">Choose one of the following methods:</span></span>

- <span data-ttu-id="72ae6-113">Homebrew を使用してインストールする。</span><span class="sxs-lookup"><span data-stu-id="72ae6-113">Install using Homebrew.</span></span> <span data-ttu-id="72ae6-114">Homebrew は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="72ae6-114">Homebrew is the preferred package manager for macOS.</span></span>
- <span data-ttu-id="72ae6-115">[直接ダウンロード](#installation-via-direct-download)を使用して PowerShell をインストールする。</span><span class="sxs-lookup"><span data-stu-id="72ae6-115">Install PowerShell via [Direct Download](#installation-via-direct-download)</span></span>
- <span data-ttu-id="72ae6-116">[バイナリ アーカイブ](#binary-archives)からインストールする。</span><span class="sxs-lookup"><span data-stu-id="72ae6-116">Install from [binary archives](#binary-archives).</span></span>

<span data-ttu-id="72ae6-117">PowerShell をインストールした後、[OpenSSL](#installing-dependencies) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-117">After installing PowerShell, you should install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="72ae6-118">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="72ae6-118">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="72ae6-119">macOS 10.13 以降で Homebrew を使用した最新の安定版リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="72ae6-119">Installation of latest stable release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="72ae6-120">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-120">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="72ae6-121">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-121">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="72ae6-122">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="72ae6-122">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="72ae6-123">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="72ae6-123">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="72ae6-124">上記のコマンドは PowerShell (pwsh) ホスト内から呼び出すことができますが、その場合、アップグレードを完了するには、PowerShell シェルを終了し、再起動して、`$PSVersionTable` に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-124">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="72ae6-125">macOS 10.13 以降で Homebrew を使用した最新のプレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="72ae6-125">Installation of latest preview release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="72ae6-126">Homebrew をインストールしたら、PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-126">After you've installed Homebrew, you can install PowerShell.</span></span> <span data-ttu-id="72ae6-127">最初に、[Cask-Versions][cask-versions] パッケージをインストールします。これにより、cask パッケージの代替バージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-127">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="72ae6-128">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-128">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="72ae6-129">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="72ae6-129">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="72ae6-130">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="72ae6-130">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="72ae6-131">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、</span><span class="sxs-lookup"><span data-stu-id="72ae6-131">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="72ae6-132">`$PSVersionTable` に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-132">and refresh the values shown in `$PSVersionTable`.</span></span>

<span data-ttu-id="72ae6-133">Homebrew tap メソッドを使用した PowerShell のインストールは、安定バージョンと LTS バージョンでもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="72ae6-133">Installing PowerShell using the Homebrew tap method is also supported for stable and LTS versions.</span></span>

```sh
brew install powershell/tap/powershell
```

<span data-ttu-id="72ae6-134">これで、インストールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-134">You can now verify your install</span></span>

```sh
pwsh
```

<span data-ttu-id="72ae6-135">新しいバージョンの PowerShell がリリースされたら、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="72ae6-135">When new versions of PowerShell are released, simply run the following command.</span></span>

```sh
brew upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="72ae6-136">cask メソッドと tap メソッドのどちらを使用する場合でも、新しいバージョンの PowerShell に更新するときに、PowerShell の初期インストールに使用したものと同じメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="72ae6-136">Whether you use the cask or the tap method, when updating to a newer version of PowerShell, use the same method you used to initially install PowerShell.</span></span> <span data-ttu-id="72ae6-137">別のメソッドを使用する場合、新しい pwsh セッションを開くと、古いバージョンの PowerShell が引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-137">If you use a different method, opening a new pwsh session will continue to use the older version of PowerShell.</span></span>
>
> <span data-ttu-id="72ae6-138">別のメソッドを使用することを選択した場合は、[Homebrew link メソッドを使用して](https://docs.brew.sh/Manpage#link-ln-options-formula)問題を修正する方法があります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-138">If you do decide to use different methods, there are ways to correct the issue using the [Homebrew link method](https://docs.brew.sh/Manpage#link-ln-options-formula).</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="72ae6-139">直接ダウンロードによるインストール</span><span class="sxs-lookup"><span data-stu-id="72ae6-139">Installation via Direct Download</span></span>

<span data-ttu-id="72ae6-140">[リリース][] ページから macOS マシンに PKG パッケージ `powershell-lts-7.0.3-osx-x64.pkg` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-140">Download the PKG package `powershell-lts-7.0.3-osx-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="72ae6-141">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-141">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-lts-7.0.3-osx-x64.pkg -target /
```

<span data-ttu-id="72ae6-142">[OpenSSL](#installing-dependencies) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-142">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="72ae6-143">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="72ae6-143">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="72ae6-144">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="72ae6-144">Install as a .NET Global tool</span></span>

<span data-ttu-id="72ae6-145">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-145">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="72ae6-146">dotnet tool install によって、`PATH` 環境変数に `~/.dotnet/tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-146">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="72ae6-147">ただし、現在実行中のシェルには更新された `PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="72ae6-147">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="72ae6-148">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できるはずです。</span><span class="sxs-lookup"><span data-stu-id="72ae6-148">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

<span data-ttu-id="72ae6-149">[OpenSSL](#installing-dependencies) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-149">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="72ae6-150">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="72ae6-150">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="72ae6-151">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="72ae6-151">Binary Archives</span></span>

<span data-ttu-id="72ae6-152">macOS プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="72ae6-152">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span> <span data-ttu-id="72ae6-153">この方法を使用してインストールする場合は、依存関係を手動でインストールする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-153">When you install using this method you must also manually install any dependencies.</span></span>

<span data-ttu-id="72ae6-154">[OpenSSL](#installing-dependencies) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-154">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="72ae6-155">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="72ae6-155">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="72ae6-156">macOS へのバイナリ アーカイブのインストール</span><span class="sxs-lookup"><span data-stu-id="72ae6-156">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.0.3

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.0.3

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.0.3/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.0.3/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a><span data-ttu-id="72ae6-157">依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="72ae6-157">Installing dependencies</span></span>

<span data-ttu-id="72ae6-158">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="72ae6-158">OpenSSL is required for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="72ae6-159">必要に応じて、MacPorts を使用して OpenSSL をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-159">You can install OpenSSL via MacPorts if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="72ae6-160">MacPorts と Homebrew を同じシステムで一緒に使用すると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-160">MacPorts and Homebrew can have problems when used to together on the same system.</span></span> <span data-ttu-id="72ae6-161">ただし、Homebrew には OpenSSL 1.0 用のパッケージがありません。</span><span class="sxs-lookup"><span data-stu-id="72ae6-161">However, Homebrew does not have a package for OpenSSL 1.0.</span></span> <span data-ttu-id="72ae6-162">詳細については、[MacPorts の FAQ](https://trac.macports.org/wiki/FAQ) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72ae6-162">For more information, see the [MacPorts FAQ](https://trac.macports.org/wiki/FAQ).</span></span>

1. <span data-ttu-id="72ae6-163">Xcode コマンド ライン ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-163">Install the Xcode command-line tools.</span></span> <span data-ttu-id="72ae6-164">MacPorts には Xcode ツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="72ae6-164">The Xcode tools are required by MacPorts.</span></span>

   ```sh
   xcode-select --install
   ```

1. <span data-ttu-id="72ae6-165">MacPorts をインストールします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-165">Install MacPorts.</span></span> <span data-ttu-id="72ae6-166">手順が必要な場合は、[インストール ガイド](https://www.macports.org/install.php)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="72ae6-166">If you need instructions, refer to the [installation guide](https://www.macports.org/install.php).</span></span>
1. <span data-ttu-id="72ae6-167">`sudo port selfupdate` を実行して MacPorts を更新します。</span><span class="sxs-lookup"><span data-stu-id="72ae6-167">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="72ae6-168">`sudo port upgrade outdated` を実行して MacPorts パッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-168">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="72ae6-169">`sudo port install openssl10` を実行して OpenSSL をインストールします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-169">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="72ae6-170">PowerShell で使用できるようにライブラリをリンクします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-170">Link the libraries to make them available to PowerShell:</span></span>

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a><span data-ttu-id="72ae6-171">PowerShell のアンインストール</span><span class="sxs-lookup"><span data-stu-id="72ae6-171">Uninstalling PowerShell</span></span>

<span data-ttu-id="72ae6-172">Homebrew を使って PowerShell をインストールした場合は、次のコマンドを使ってアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="72ae6-172">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="72ae6-173">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-173">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="72ae6-174">追加の PowerShell パスを削除するには、このドキュメントの「[パス](#paths)」セクションを参照し、`sudo rm` を使用してパスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="72ae6-174">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="72ae6-175">Homebrew でインストールした場合、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="72ae6-175">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="72ae6-176">パス</span><span class="sxs-lookup"><span data-stu-id="72ae6-176">Paths</span></span>

- <span data-ttu-id="72ae6-177">`$PSHOME` は `/usr/local/microsoft/powershell/7.0.3/` です</span><span class="sxs-lookup"><span data-stu-id="72ae6-177">`$PSHOME` is `/usr/local/microsoft/powershell/7.0.3/`</span></span>
- <span data-ttu-id="72ae6-178">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="72ae6-178">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="72ae6-179">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="72ae6-179">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="72ae6-180">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="72ae6-180">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="72ae6-181">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="72ae6-181">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="72ae6-182">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="72ae6-182">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="72ae6-183">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="72ae6-183">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="72ae6-184">プロファイルには、PowerShell のホスト単位の構成が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="72ae6-184">The profiles respect PowerShell's per-host configuration.</span></span> <span data-ttu-id="72ae6-185">そのため、既定のホスト固有のプロファイルは、同じ場所の `Microsoft.PowerShell_profile.ps1` に存在します。</span><span class="sxs-lookup"><span data-stu-id="72ae6-185">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="72ae6-186">PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="72ae6-186">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="72ae6-187">macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-187">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span> <span data-ttu-id="72ae6-188">そのため、`$PSHOME` は `/usr/local/microsoft/powershell/7.0.3/` となり、シンボリック リンクは `/usr/local/bin/pwsh` に配置されます。</span><span class="sxs-lookup"><span data-stu-id="72ae6-188">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.0.3/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="installation-support"></a><span data-ttu-id="72ae6-189">インストールのサポート</span><span class="sxs-lookup"><span data-stu-id="72ae6-189">Installation support</span></span>

<span data-ttu-id="72ae6-190">Microsoft では、このドキュメントのインストール方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="72ae6-190">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="72ae6-191">他のソースから別の方法でインストールできる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="72ae6-191">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="72ae6-192">そのようなツールと方法は機能しても、Microsoft ではそれらの方法をサポートできません。</span><span class="sxs-lookup"><span data-stu-id="72ae6-192">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="72ae6-193">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="72ae6-193">Additional Resources</span></span>

- <span data-ttu-id="72ae6-194">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="72ae6-194">[Homebrew Web][brew]</span></span>
- <span data-ttu-id="72ae6-195">[Homebrew Github リポジトリ][GitHub]</span><span class="sxs-lookup"><span data-stu-id="72ae6-195">[Homebrew Github Repository][GitHub]</span></span>
- <span data-ttu-id="72ae6-196">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="72ae6-196">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
