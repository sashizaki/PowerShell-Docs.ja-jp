---
title: macOS への PowerShell Core のインストール
description: macOS への PowerShell Core のインストールに関する情報
ms.date: 11/02/2018
ms.openlocfilehash: 162e841bf71d708e9db84ea1bb2dbef13924783b
ms.sourcegitcommit: f4247d3f91d06ec392c4cd66921ce7d0456a2bd9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2018
ms.locfileid: "50998505"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="7a16e-103">macOS への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="7a16e-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="7a16e-104">PowerShell Core は、macOS 10.12 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7a16e-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="7a16e-105">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="7a16e-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="7a16e-106">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a16e-106">Once the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="about-brew"></a><span data-ttu-id="7a16e-107">Brew について</span><span class="sxs-lookup"><span data-stu-id="7a16e-107">About Brew</span></span>

<span data-ttu-id="7a16e-108">[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="7a16e-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="7a16e-109">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a16e-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="7a16e-110">macOS 10.12 以降で Homebrew を使用した最新の安定版リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="7a16e-110">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="7a16e-111">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a16e-111">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="7a16e-112">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7a16e-112">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="7a16e-113">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a16e-113">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="7a16e-114">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="7a16e-114">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="7a16e-115">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、アップグレードを完了するには、PowerShell シェルを終了し、再起動して、$PSVersionTable に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a16e-115">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in $PSVersionTable.</span></span>

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="7a16e-116">macOS 10.12 以降で Homebrew を使用した最新のプレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="7a16e-116">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="7a16e-117">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a16e-117">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="7a16e-118">Homebrew をインストールすると、PowerShell のインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="7a16e-118">Once you've installed Homebrew, installing PowerShell is easy.</span></span>
<span data-ttu-id="7a16e-119">最初に、[Cask-Versions][cask-versions] をインストールします。これにより、cask パッケージの代替バージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a16e-119">First, install [Cask-Versions][cask-versions] which lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="7a16e-120">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7a16e-120">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="7a16e-121">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a16e-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="7a16e-122">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="7a16e-122">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="7a16e-123">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、</span><span class="sxs-lookup"><span data-stu-id="7a16e-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="7a16e-124">$PSVersionTable に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a16e-124">and refresh the values shown in $PSVersionTable.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="7a16e-125">直接ダウンロードによるインストール</span><span class="sxs-lookup"><span data-stu-id="7a16e-125">Installation via Direct Download</span></span>

<span data-ttu-id="7a16e-126">PKG パッケージ `powershell-6.1.0-osx-x64.pkg` を</span><span class="sxs-lookup"><span data-stu-id="7a16e-126">Download the PKG package `powershell-6.1.0-osx-x64.pkg`</span></span>
<span data-ttu-id="7a16e-127">[リリース][] ページから macOS コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-127">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="7a16e-128">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-128">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.1.0-osx-x64.pkg -target /
```

<span data-ttu-id="7a16e-129">PowerShell リモート処理および CIM 操作の場合に [OpenSSL](#install-openssl) が必要となるので、これをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-129">Install [OpenSSL](#install-openssl) as this is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="7a16e-130">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="7a16e-130">Binary Archives</span></span>

<span data-ttu-id="7a16e-131">macOS プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7a16e-131">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="7a16e-132">macOS へのバイナリ アーカイブのインストール</span><span class="sxs-lookup"><span data-stu-id="7a16e-132">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.1.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.1.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.1.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.1.0/pwsh /usr/local/bin/pwsh
```

<span data-ttu-id="7a16e-133">PowerShell リモート処理および CIM 操作の場合に [OpenSSL](#install-openssl) が必要となるので、これをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-133">Install [OpenSSL](#install-openssl) as this is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="7a16e-134">依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="7a16e-134">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="7a16e-135">XCode コマンド ライン ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="7a16e-135">Install XCode command line tools</span></span>

```shell
xcode-select -install
```

### <a name="install-openssl"></a><span data-ttu-id="7a16e-136">OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="7a16e-136">Install OpenSSL</span></span>

<span data-ttu-id="7a16e-137">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="7a16e-137">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>  <span data-ttu-id="7a16e-138">MacPorts または Brew を介してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a16e-138">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="7a16e-139">Brew を介して OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="7a16e-139">Install OpenSSL via Brew</span></span>

<span data-ttu-id="7a16e-140">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a16e-140">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="7a16e-141">`brew install openssl` を実行することで、OpenSSL をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-141">Run `brew install openssl` to install OpenSSL.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="7a16e-142">MacPorts を介して OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="7a16e-142">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="7a16e-143">[XCode コマンド ライン ツール](#install-xcode-command-line-tools)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-143">Instal the [XCode command line tools](#install-xcode-command-line-tools)</span></span>
1. <span data-ttu-id="7a16e-144">MacPorts をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-144">Install MacPorts.</span></span>
   <span data-ttu-id="7a16e-145">手順の説明が必要な場合は、[インストール ガイド](https://guide.macports.org/chunked/installing.macports.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a16e-145">See the [installation guide](https://guide.macports.org/chunked/installing.macports.html) if you need instructions.</span></span>
1. <span data-ttu-id="7a16e-146">`sudo port selfupdate` を実行して MacPorts を更新します。</span><span class="sxs-lookup"><span data-stu-id="7a16e-146">Update MacPorts by running `sudo port selfupdate`</span></span>
1. <span data-ttu-id="7a16e-147">`sudo port upgrade outdated` を実行して MacPorts パッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-147">Upgrade MacPorts packages by running `sudo port upgrade outdated`</span></span>
1. <span data-ttu-id="7a16e-148">`sudo port instal openssl` を実行して OpenSSL をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-148">Install OpenSSL by running by running `sudo port instal openssl`</span></span>
1. <span data-ttu-id="7a16e-149">ライブラリを PowerShell で使用できるようにリンクします。</span><span class="sxs-lookup"><span data-stu-id="7a16e-149">Link the libraries so that PowerShell can use it.</span></span>

```shell
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="7a16e-150">PowerShell Core のアンインストール</span><span class="sxs-lookup"><span data-stu-id="7a16e-150">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="7a16e-151">Homebrew で PowerShell をインストールした場合、アンインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="7a16e-151">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="7a16e-152">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a16e-152">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="7a16e-153">追加の PowerShell パスを削除するには、このドキュメントの「[パス](#paths)」セクションを参照し、`sudo rm` を使用して目的のパスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="7a16e-153">To remove the additional PowerShell paths, please see the [paths](#paths) section in this document and remove the desired the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="7a16e-154">Homebrew でインストールした場合、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="7a16e-154">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="7a16e-155">パス</span><span class="sxs-lookup"><span data-stu-id="7a16e-155">Paths</span></span>

* <span data-ttu-id="7a16e-156">`$PSHOME` は `/usr/local/microsoft/powershell/6.1.0/` です</span><span class="sxs-lookup"><span data-stu-id="7a16e-156">`$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`</span></span>
* <span data-ttu-id="7a16e-157">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="7a16e-157">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="7a16e-158">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="7a16e-158">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="7a16e-159">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="7a16e-159">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="7a16e-160">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="7a16e-160">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="7a16e-161">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="7a16e-161">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="7a16e-162">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="7a16e-162">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="7a16e-163">プロファイルには、PowerShell のホスト単位の構成が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="7a16e-163">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="7a16e-164">そのため、既定のホスト固有のプロファイルは、同じ場所の `Microsoft.PowerShell_profile.ps1` に存在します。</span><span class="sxs-lookup"><span data-stu-id="7a16e-164">So the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="7a16e-165">PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="7a16e-165">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="7a16e-166">macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a16e-166">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="7a16e-167">そのため、`$PSHOME` は `/usr/local/microsoft/powershell/6.1.0/` となり、シンボリック リンクは `/usr/local/bin/pwsh` に配置されます。</span><span class="sxs-lookup"><span data-stu-id="7a16e-167">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7a16e-168">その他の情報</span><span class="sxs-lookup"><span data-stu-id="7a16e-168">Additional Resources</span></span>

* <span data-ttu-id="7a16e-169">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="7a16e-169">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="7a16e-170">[Homebrew Github リポジトリ][GitHub]</span><span class="sxs-lookup"><span data-stu-id="7a16e-170">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="7a16e-171">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="7a16e-171">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
