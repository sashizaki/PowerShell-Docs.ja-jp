---
title: macOS への PowerShell Core のインストール
description: macOS への PowerShell Core のインストールに関する情報
ms.date: 12/12/2018
ms.openlocfilehash: 91e64cace7d4ed988da56109dde9bf2a80528eb4
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402558"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="3e5ba-103">macOS への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="3e5ba-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="3e5ba-104">PowerShell Core は、macOS 10.12 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="3e5ba-105">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="3e5ba-106">パッケージをインストール後、実行`pwsh`端末から。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-106">After the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="about-brew"></a><span data-ttu-id="3e5ba-107">Brew について</span><span class="sxs-lookup"><span data-stu-id="3e5ba-107">About Brew</span></span>

<span data-ttu-id="3e5ba-108">[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="3e5ba-109">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="3e5ba-110">macOS 10.12 以降で Homebrew を使用した最新の安定版リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="3e5ba-110">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="3e5ba-111">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-111">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="3e5ba-112">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-112">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="3e5ba-113">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-113">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="3e5ba-114">PowerShell の新しいバージョンがリリースされるは、Homebrew の式を更新および PowerShell をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-114">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="3e5ba-115">上記のコマンドは、PowerShell (pwsh) ホスト内から呼び出すことができますが、PowerShell シェルを終了および、アップグレードを完了してに表示される値を更新するには再起動する必要がある`$PSVersionTable`します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-115">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="3e5ba-116">macOS 10.12 以降で Homebrew を使用した最新のプレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="3e5ba-116">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="3e5ba-117">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-117">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="3e5ba-118">Homebrew をインストールした後は、PowerShell をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-118">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="3e5ba-119">最初に、インストール、 [Cask バージョン][ cask-versions]パッケージ cask パッケージの代替バージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-119">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="3e5ba-120">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-120">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="3e5ba-121">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="3e5ba-122">PowerShell の新しいバージョンがリリースされるは、Homebrew の式を更新および PowerShell をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-122">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="3e5ba-123">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、</span><span class="sxs-lookup"><span data-stu-id="3e5ba-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="3e5ba-124">表示される値を更新および`$PSVersionTable`します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-124">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="3e5ba-125">直接ダウンロードによるインストール</span><span class="sxs-lookup"><span data-stu-id="3e5ba-125">Installation via Direct Download</span></span>

<span data-ttu-id="3e5ba-126">PKG パッケージ `powershell-6.1.0-osx-x64.pkg` を</span><span class="sxs-lookup"><span data-stu-id="3e5ba-126">Download the PKG package `powershell-6.1.0-osx-x64.pkg`</span></span>
<span data-ttu-id="3e5ba-127">[リリース][] ページから macOS コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-127">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="3e5ba-128">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-128">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.1.0-osx-x64.pkg -target /
```

<span data-ttu-id="3e5ba-129">[OpenSSL](#install-openssl) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-129">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="3e5ba-130">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-130">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="3e5ba-131">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="3e5ba-131">Binary Archives</span></span>

<span data-ttu-id="3e5ba-132">macOS プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-132">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="3e5ba-133">macOS へのバイナリ アーカイブのインストール</span><span class="sxs-lookup"><span data-stu-id="3e5ba-133">Installing binary archives on macOS</span></span>

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

<span data-ttu-id="3e5ba-134">[OpenSSL](#install-openssl) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-134">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="3e5ba-135">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-135">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="3e5ba-136">依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="3e5ba-136">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="3e5ba-137">XCode コマンド ライン ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="3e5ba-137">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="3e5ba-138">OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="3e5ba-138">Install OpenSSL</span></span>

<span data-ttu-id="3e5ba-139">PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-139">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="3e5ba-140">MacPorts または Brew を介してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-140">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="3e5ba-141">Brew を介して OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="3e5ba-141">Install OpenSSL via Brew</span></span>

<span data-ttu-id="3e5ba-142">Brew の詳細については、「[Brew について](#about-brew)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-142">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="3e5ba-143">OpenSSL をインストールする実行`brew install openssl`します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-143">To install OpenSSL, run `brew install openssl`.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="3e5ba-144">MacPorts を介して OpenSSL をインストールする</span><span class="sxs-lookup"><span data-stu-id="3e5ba-144">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="3e5ba-145">インストール、 [XCode コマンド ライン ツール](#install-xcode-command-line-tools)します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-145">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="3e5ba-146">MacPorts をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-146">Install MacPorts.</span></span>
   <span data-ttu-id="3e5ba-147">手順が必要な場合を参照してください、[インストール ガイド](https://guide.macports.org/chunked/installing.macports.html)します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-147">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="3e5ba-148">`sudo port selfupdate` を実行して MacPorts を更新します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-148">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="3e5ba-149">`sudo port upgrade outdated` を実行して MacPorts パッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-149">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="3e5ba-150">実行して OpenSSL をインストール`sudo port install openssl`します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-150">Install OpenSSL by running `sudo port install openssl`.</span></span>
1. <span data-ttu-id="3e5ba-151">PowerShell を使用できるようにするライブラリをリンクします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-151">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="3e5ba-152">PowerShell Core のアンインストール</span><span class="sxs-lookup"><span data-stu-id="3e5ba-152">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="3e5ba-153">Homebrew で PowerShell をインストールした場合は、次のコマンドを使用して、アンインストールします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-153">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="3e5ba-154">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-154">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="3e5ba-155">追加の PowerShell パスを削除するを参照してください、[パス](#paths)このドキュメントでセクションし、を使用してパスの削除`sudo rm`します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-155">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="3e5ba-156">Homebrew でインストールした場合、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-156">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="3e5ba-157">パス</span><span class="sxs-lookup"><span data-stu-id="3e5ba-157">Paths</span></span>

* <span data-ttu-id="3e5ba-158">`$PSHOME` は `/usr/local/microsoft/powershell/6.1.0/` です</span><span class="sxs-lookup"><span data-stu-id="3e5ba-158">`$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`</span></span>
* <span data-ttu-id="3e5ba-159">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="3e5ba-159">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="3e5ba-160">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="3e5ba-160">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="3e5ba-161">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="3e5ba-161">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="3e5ba-162">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="3e5ba-162">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="3e5ba-163">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="3e5ba-163">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="3e5ba-164">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="3e5ba-164">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="3e5ba-165">プロファイルには、PowerShell のホスト単位の構成が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-165">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="3e5ba-166">既定のホスト固有プロファイルが存在するように`Microsoft.PowerShell_profile.ps1`同じ場所にします。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-166">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="3e5ba-167">PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-167">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="3e5ba-168">macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-168">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="3e5ba-169">そのため、`$PSHOME`は`/usr/local/microsoft/powershell/6.1.0/`、シンボリック リンクが配置されると`/usr/local/bin/pwsh`します。</span><span class="sxs-lookup"><span data-stu-id="3e5ba-169">So, `$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e5ba-170">その他の情報</span><span class="sxs-lookup"><span data-stu-id="3e5ba-170">Additional Resources</span></span>

* <span data-ttu-id="3e5ba-171">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="3e5ba-171">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="3e5ba-172">[Homebrew Github リポジトリ][GitHub]</span><span class="sxs-lookup"><span data-stu-id="3e5ba-172">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="3e5ba-173">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="3e5ba-173">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
