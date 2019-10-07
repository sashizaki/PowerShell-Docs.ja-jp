---
title: macOS への PowerShell Core のインストール
description: macOS への PowerShell Core のインストールに関する情報
ms.date: 12/12/2018
ms.openlocfilehash: a53cb5b7e159635dac45fb9ca3df28e86dffc653
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71325277"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="cdc42-103">macOS への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="cdc42-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="cdc42-104">PowerShell Core は、macOS 10.12 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cdc42-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="cdc42-105">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="cdc42-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="cdc42-106">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="cdc42-106">After the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="about-brew"></a><span data-ttu-id="cdc42-107">Brew について</span><span class="sxs-lookup"><span data-stu-id="cdc42-107">About Brew</span></span>

<span data-ttu-id="cdc42-108">[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="cdc42-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="cdc42-109">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdc42-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>
<span data-ttu-id="cdc42-110">それ以外の場合は、[直接ダウンロード](#installation-via-direct-download)によって、または[バイナリアーカイブ](#binary-archives)から PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cdc42-110">Otherwise you may install PowerShell via [Direct Download](#installation-via-direct-download) or from [Binary Archives](#binary-archives).</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="cdc42-111">macOS 10.12 以降で Homebrew を使用した最新の安定版リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="cdc42-111">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="cdc42-112">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdc42-112">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="cdc42-113">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cdc42-113">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="cdc42-114">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cdc42-114">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="cdc42-115">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="cdc42-115">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="cdc42-116">上記のコマンドは PowerShell (pwsh) ホスト内から呼び出すことができますが、その場合、アップグレードを完了するには、PowerShell シェルを終了し、再起動して、`$PSVersionTable` に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdc42-116">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="cdc42-117">macOS 10.12 以降で Homebrew を使用した最新のプレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="cdc42-117">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="cdc42-118">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdc42-118">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="cdc42-119">Homebrew をインストールしたら、PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cdc42-119">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="cdc42-120">最初に、[Cask-Versions][cask-versions] パッケージをインストールします。これにより、cask パッケージの代替バージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="cdc42-120">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="cdc42-121">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cdc42-121">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="cdc42-122">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cdc42-122">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="cdc42-123">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="cdc42-123">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="cdc42-124">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、</span><span class="sxs-lookup"><span data-stu-id="cdc42-124">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="cdc42-125">`$PSVersionTable` に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdc42-125">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="cdc42-126">直接ダウンロードによるインストール</span><span class="sxs-lookup"><span data-stu-id="cdc42-126">Installation via Direct Download</span></span>

<span data-ttu-id="cdc42-127">PKG パッケージ `powershell-6.2.0-osx-x64.pkg` を</span><span class="sxs-lookup"><span data-stu-id="cdc42-127">Download the PKG package `powershell-6.2.0-osx-x64.pkg`</span></span>
<span data-ttu-id="cdc42-128">[リリース][] ページから macOS コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-128">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="cdc42-129">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-129">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.2.0-osx-x64.pkg -target /
```

<span data-ttu-id="cdc42-130">[OpenSSL](#install-openssl) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-130">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="cdc42-131">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="cdc42-131">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="cdc42-132">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="cdc42-132">Binary Archives</span></span>

<span data-ttu-id="cdc42-133">macOS プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="cdc42-133">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="cdc42-134">macOS へのバイナリ アーカイブのインストール</span><span class="sxs-lookup"><span data-stu-id="cdc42-134">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.2.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.2.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.2.0/pwsh /usr/local/bin/pwsh
```

<span data-ttu-id="cdc42-135">[OpenSSL](#install-openssl) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-135">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="cdc42-136">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="cdc42-136">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="cdc42-137">依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="cdc42-137">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="cdc42-138">XCode コマンド ライン ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="cdc42-138">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="cdc42-139">OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="cdc42-139">Install OpenSSL</span></span>

<span data-ttu-id="cdc42-140">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="cdc42-140">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="cdc42-141">MacPorts または Brew を介してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="cdc42-141">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="cdc42-142">Brew を介して OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="cdc42-142">Install OpenSSL via Brew</span></span>

<span data-ttu-id="cdc42-143">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdc42-143">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="cdc42-144">OpenSSL をインストールするには、`brew install openssl` を実行します。</span><span class="sxs-lookup"><span data-stu-id="cdc42-144">To install OpenSSL, run `brew install openssl`.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="cdc42-145">MacPorts を介して OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="cdc42-145">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="cdc42-146">[XCode コマンド ライン ツール](#install-xcode-command-line-tools)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-146">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="cdc42-147">MacPorts をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-147">Install MacPorts.</span></span>
   <span data-ttu-id="cdc42-148">手順が必要な場合は、[インストール ガイド](https://guide.macports.org/chunked/installing.macports.html)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cdc42-148">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="cdc42-149">`sudo port selfupdate` を実行して MacPorts を更新します。</span><span class="sxs-lookup"><span data-stu-id="cdc42-149">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="cdc42-150">`sudo port upgrade outdated` を実行して MacPorts パッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-150">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="cdc42-151">`sudo port install openssl` を実行して OpenSSL をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-151">Install OpenSSL by running `sudo port install openssl`.</span></span>
1. <span data-ttu-id="cdc42-152">PowerShell で使用できるようにライブラリをリンクします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-152">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="cdc42-153">PowerShell Core のアンインストール</span><span class="sxs-lookup"><span data-stu-id="cdc42-153">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="cdc42-154">Homebrew を使って PowerShell をインストールした場合は、次のコマンドを使ってアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="cdc42-154">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="cdc42-155">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdc42-155">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="cdc42-156">追加の PowerShell パスを削除するには、このドキュメントの「[パス](#paths)」セクションを参照し、`sudo rm` を使用してパスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="cdc42-156">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc42-157">Homebrew でインストールした場合、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="cdc42-157">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="cdc42-158">パス</span><span class="sxs-lookup"><span data-stu-id="cdc42-158">Paths</span></span>

* <span data-ttu-id="cdc42-159">`$PSHOME` は `/usr/local/microsoft/powershell/6.2.0/` です</span><span class="sxs-lookup"><span data-stu-id="cdc42-159">`$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="cdc42-160">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="cdc42-160">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="cdc42-161">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="cdc42-161">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="cdc42-162">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="cdc42-162">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="cdc42-163">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="cdc42-163">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="cdc42-164">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="cdc42-164">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="cdc42-165">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="cdc42-165">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="cdc42-166">プロファイルには、PowerShell のホスト単位の構成が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="cdc42-166">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="cdc42-167">そのため、既定のホスト固有のプロファイルは、同じ場所の `Microsoft.PowerShell_profile.ps1` に存在します。</span><span class="sxs-lookup"><span data-stu-id="cdc42-167">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="cdc42-168">PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="cdc42-168">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="cdc42-169">macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdc42-169">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="cdc42-170">そのため、`$PSHOME` は `/usr/local/microsoft/powershell/6.2.0/` となり、シンボリック リンクは `/usr/local/bin/pwsh` に配置されます。</span><span class="sxs-lookup"><span data-stu-id="cdc42-170">So, `$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cdc42-171">その他の情報</span><span class="sxs-lookup"><span data-stu-id="cdc42-171">Additional Resources</span></span>

* <span data-ttu-id="cdc42-172">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="cdc42-172">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="cdc42-173">[Homebrew Github リポジトリ][GitHub]</span><span class="sxs-lookup"><span data-stu-id="cdc42-173">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="cdc42-174">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="cdc42-174">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
