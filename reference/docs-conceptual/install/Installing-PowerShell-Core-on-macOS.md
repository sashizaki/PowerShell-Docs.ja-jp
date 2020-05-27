---
title: macOS への PowerShell のインストール
description: macOS への PowerShell のインストールに関する情報
ms.date: 05/21/2020
ms.openlocfilehash: 32b3ebf3eb4017af41fc1a062f2f0a2e08629a58
ms.sourcegitcommit: fd6a33b9fac973b3554fecfea7f51475e650a606
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83791470"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="bdf44-103">macOS への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="bdf44-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="bdf44-104">PowerShell は、macOS 10.12 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bdf44-104">PowerShell supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="bdf44-105">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="bdf44-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="bdf44-106">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="bdf44-106">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="bdf44-107">PowerShell 7 はインプレース アップグレードで、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="bdf44-108">`/usr/local/microsoft/powershell/6` フォルダーは `/usr/local/microsoft/powershell/7` に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="bdf44-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="bdf44-109">PowerShell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[バイナリ アーカイブ](#binary-archives)方法を使用して PowerShell 6 を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

## <a name="about-brew"></a><span data-ttu-id="bdf44-110">Brew について</span><span class="sxs-lookup"><span data-stu-id="bdf44-110">About Brew</span></span>

<span data-ttu-id="bdf44-111">[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="bdf44-111">[Homebrew][brew] is the preferred package manager for macOS.</span></span> <span data-ttu-id="bdf44-112">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdf44-112">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span> <span data-ttu-id="bdf44-113">それ以外の場合は、[直接ダウンロード](#installation-via-direct-download)によって、または[バイナリアーカイブ](#binary-archives)から PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-113">Otherwise you may install PowerShell via [Direct Download](#installation-via-direct-download) or from [Binary Archives](#binary-archives).</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="bdf44-114">macOS 10.12 以降で Homebrew を使用した最新の安定版リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="bdf44-114">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="bdf44-115">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdf44-115">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="bdf44-116">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-116">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="bdf44-117">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdf44-117">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="bdf44-118">新しいバージョンの PowerShell がリリースされたら、Homebrew のパッケージ定義 (Formula) を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="bdf44-118">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="bdf44-119">上記のコマンドは PowerShell (pwsh) ホスト内から呼び出すことができますが、その場合、アップグレードを完了するには、PowerShell シェルを終了し、再起動して、`$PSVersionTable` に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdf44-119">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="bdf44-120">macOS 10.12 以降で Homebrew を使用した最新のプレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="bdf44-120">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="bdf44-121">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdf44-121">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="bdf44-122">Homebrew をインストールしたら、PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-122">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="bdf44-123">最初に、[Cask-Versions][cask-versions] パッケージをインストールします。これにより、cask パッケージの代替バージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-123">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="bdf44-124">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-124">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="bdf44-125">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdf44-125">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="bdf44-126">新しいバージョンの PowerShell がリリースされたら、Homebrew のパッケージ定義 (Formula) を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="bdf44-126">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="bdf44-127">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、</span><span class="sxs-lookup"><span data-stu-id="bdf44-127">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="bdf44-128">`$PSVersionTable` に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdf44-128">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="bdf44-129">直接ダウンロードによるインストール</span><span class="sxs-lookup"><span data-stu-id="bdf44-129">Installation via Direct Download</span></span>

<span data-ttu-id="bdf44-130">PKG パッケージ `powershell-lts-7.0.1-osx-x64.pkg` を</span><span class="sxs-lookup"><span data-stu-id="bdf44-130">Download the PKG package `powershell-lts-7.0.1-osx-x64.pkg`</span></span>
<span data-ttu-id="bdf44-131">[リリース][] ページから macOS コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-131">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="bdf44-132">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-132">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-lts-7.0.1-osx-x64.pkg -target /
```

<span data-ttu-id="bdf44-133">[OpenSSL](#install-openssl) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-133">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="bdf44-134">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="bdf44-134">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="bdf44-135">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="bdf44-135">Install as a .NET Global tool</span></span>

<span data-ttu-id="bdf44-136">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-136">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="bdf44-137">dotnet tool install によって、`PATH` 環境変数に `~/.dotnet/tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-137">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="bdf44-138">ただし、現在実行中のシェルには更新された `PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="bdf44-138">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="bdf44-139">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できるはずです。</span><span class="sxs-lookup"><span data-stu-id="bdf44-139">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="bdf44-140">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="bdf44-140">Binary Archives</span></span>

<span data-ttu-id="bdf44-141">macOS プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bdf44-141">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="bdf44-142">macOS へのバイナリ アーカイブのインストール</span><span class="sxs-lookup"><span data-stu-id="bdf44-142">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.1/powershell-7.0.1-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.0.1

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.0.1

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.0.1/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.0.1/pwsh /usr/local/bin/pwsh
```

<span data-ttu-id="bdf44-143">[OpenSSL](#install-openssl) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-143">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="bdf44-144">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="bdf44-144">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="bdf44-145">依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="bdf44-145">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="bdf44-146">XCode コマンド ライン ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="bdf44-146">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="bdf44-147">OpenSSL のインストール</span><span class="sxs-lookup"><span data-stu-id="bdf44-147">Install OpenSSL</span></span>

<span data-ttu-id="bdf44-148">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="bdf44-148">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="bdf44-149">MacPorts を介してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-149">You can install via MacPorts.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="bdf44-150">MacPorts を介して OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="bdf44-150">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="bdf44-151">[XCode コマンド ライン ツール](#install-xcode-command-line-tools)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-151">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="bdf44-152">MacPorts をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-152">Install MacPorts.</span></span>
   <span data-ttu-id="bdf44-153">手順が必要な場合は、[インストール ガイド](https://guide.macports.org/chunked/installing.macports.html)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bdf44-153">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="bdf44-154">`sudo port selfupdate` を実行して MacPorts を更新します。</span><span class="sxs-lookup"><span data-stu-id="bdf44-154">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="bdf44-155">`sudo port upgrade outdated` を実行して MacPorts パッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-155">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="bdf44-156">`sudo port install openssl10` を実行して OpenSSL をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-156">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="bdf44-157">PowerShell で使用できるようにライブラリをリンクします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-157">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell"></a><span data-ttu-id="bdf44-158">PowerShell のアンインストール</span><span class="sxs-lookup"><span data-stu-id="bdf44-158">Uninstalling PowerShell</span></span>

<span data-ttu-id="bdf44-159">Homebrew を使って PowerShell をインストールした場合は、次のコマンドを使ってアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="bdf44-159">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="bdf44-160">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdf44-160">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="bdf44-161">追加の PowerShell パスを削除するには、このドキュメントの「[パス](#paths)」セクションを参照し、`sudo rm` を使用してパスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="bdf44-161">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="bdf44-162">Homebrew でインストールした場合、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="bdf44-162">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="bdf44-163">パス</span><span class="sxs-lookup"><span data-stu-id="bdf44-163">Paths</span></span>

* <span data-ttu-id="bdf44-164">`$PSHOME` は `/usr/local/microsoft/powershell/7.0.1/` です</span><span class="sxs-lookup"><span data-stu-id="bdf44-164">`$PSHOME` is `/usr/local/microsoft/powershell/7.0.1/`</span></span>
* <span data-ttu-id="bdf44-165">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bdf44-165">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="bdf44-166">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bdf44-166">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="bdf44-167">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bdf44-167">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="bdf44-168">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bdf44-168">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="bdf44-169">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="bdf44-169">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="bdf44-170">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="bdf44-170">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="bdf44-171">プロファイルには、PowerShell のホスト単位の構成が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="bdf44-171">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="bdf44-172">そのため、既定のホスト固有のプロファイルは、同じ場所の `Microsoft.PowerShell_profile.ps1` に存在します。</span><span class="sxs-lookup"><span data-stu-id="bdf44-172">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="bdf44-173">PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="bdf44-173">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="bdf44-174">macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-174">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="bdf44-175">そのため、`$PSHOME` は `/usr/local/microsoft/powershell/7.0.1/` となり、シンボリック リンクは `/usr/local/bin/pwsh` に配置されます。</span><span class="sxs-lookup"><span data-stu-id="bdf44-175">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.0.1/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bdf44-176">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="bdf44-176">Additional Resources</span></span>

* <span data-ttu-id="bdf44-177">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="bdf44-177">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="bdf44-178">[Homebrew Github リポジトリ][GitHub]</span><span class="sxs-lookup"><span data-stu-id="bdf44-178">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="bdf44-179">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="bdf44-179">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
