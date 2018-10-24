---
title: macOS への PowerShell Core のインストール
description: macOS への PowerShell Core のインストールに関する情報
ms.date: 08/06/2018
ms.openlocfilehash: 042c933dfa83f3ab52e315036e4f817145116d00
ms.sourcegitcommit: aa41249f153bbc6e11667ade60c878980c15abc6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45611489"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="996ae-103">macOS への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="996ae-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="996ae-104">PowerShell Core は、macOS 10.12 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="996ae-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="996ae-105">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="996ae-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="996ae-106">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="996ae-106">Once the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="996ae-107">macOS 10.12 以降で Homebrew を使用した最新の安定版リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="996ae-107">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="996ae-108">[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="996ae-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="996ae-109">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="996ae-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="996ae-110">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="996ae-110">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="996ae-111">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="996ae-111">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="996ae-112">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="996ae-112">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="996ae-113">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、</span><span class="sxs-lookup"><span data-stu-id="996ae-113">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="996ae-114">$PSVersionTable に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="996ae-114">and refresh the values shown in $PSVersionTable.</span></span>

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="996ae-115">macOS 10.12 以降で Homebrew を使用した最新のプレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="996ae-115">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="996ae-116">[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="996ae-116">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="996ae-117">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="996ae-117">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="996ae-118">Homebrew をインストールすると、PowerShell のインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="996ae-118">Once you've installed Homebrew, installing PowerShell is easy.</span></span>
<span data-ttu-id="996ae-119">最初に、[Cask-Versions][cask-versions] をインストールします。これにより、cask パッケージの代替バージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="996ae-119">First, install [Cask-Versions][cask-versions] which lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="996ae-120">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="996ae-120">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="996ae-121">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="996ae-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="996ae-122">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="996ae-122">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="996ae-123">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、</span><span class="sxs-lookup"><span data-stu-id="996ae-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="996ae-124">$PSVersionTable に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="996ae-124">and refresh the values shown in $PSVersionTable.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="996ae-125">直接ダウンロードによるインストール</span><span class="sxs-lookup"><span data-stu-id="996ae-125">Installation via Direct Download</span></span>

<span data-ttu-id="996ae-126">PKG パッケージ `powershell-6.1.0-osx-x64.pkg` を</span><span class="sxs-lookup"><span data-stu-id="996ae-126">Download the PKG package `powershell-6.1.0-osx-x64.pkg`</span></span>
<span data-ttu-id="996ae-127">[リリース][] ページから macOS コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="996ae-127">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="996ae-128">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="996ae-128">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.1.0-osx-x64.pkg -target /
```

## <a name="binary-archives"></a><span data-ttu-id="996ae-129">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="996ae-129">Binary Archives</span></span>

<span data-ttu-id="996ae-130">macOS プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="996ae-130">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="996ae-131">macOS へのバイナリ アーカイブのインストール</span><span class="sxs-lookup"><span data-stu-id="996ae-131">Installing binary archives on macOS</span></span>

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

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="996ae-132">PowerShell Core のアンインストール</span><span class="sxs-lookup"><span data-stu-id="996ae-132">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="996ae-133">Homebrew で PowerShell をインストールした場合、アンインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="996ae-133">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="996ae-134">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="996ae-134">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="996ae-135">追加の PowerShell パスを削除するには、このドキュメントの「[パス](#paths)」セクションを参照し、`sudo rm` を使用して目的のパスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="996ae-135">To remove the additional PowerShell paths, please see the [paths](#paths) section in this document and remove the desired the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="996ae-136">Homebrew でインストールした場合、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="996ae-136">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="996ae-137">パス</span><span class="sxs-lookup"><span data-stu-id="996ae-137">Paths</span></span>

* <span data-ttu-id="996ae-138">`$PSHOME` は `/usr/local/microsoft/powershell/6.1.0/` です</span><span class="sxs-lookup"><span data-stu-id="996ae-138">`$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`</span></span>
* <span data-ttu-id="996ae-139">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="996ae-139">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="996ae-140">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="996ae-140">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="996ae-141">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="996ae-141">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="996ae-142">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="996ae-142">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="996ae-143">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="996ae-143">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="996ae-144">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="996ae-144">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="996ae-145">プロファイルには、PowerShell のホスト単位の構成が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="996ae-145">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="996ae-146">そのため、既定のホスト固有のプロファイルは、同じ場所の `Microsoft.PowerShell_profile.ps1` に存在します。</span><span class="sxs-lookup"><span data-stu-id="996ae-146">So the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="996ae-147">PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="996ae-147">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="996ae-148">macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="996ae-148">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="996ae-149">そのため、`$PSHOME` は `/usr/local/microsoft/powershell/6.1.0/` です。シンボリックリンクは `/usr/local/bin/pwsh` にあります。</span><span class="sxs-lookup"><span data-stu-id="996ae-149">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`, and the symlink is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="996ae-150">その他の情報</span><span class="sxs-lookup"><span data-stu-id="996ae-150">Additional Resources</span></span>

* <span data-ttu-id="996ae-151">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="996ae-151">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="996ae-152">[Homebrew Github リポジトリ][GitHub]</span><span class="sxs-lookup"><span data-stu-id="996ae-152">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="996ae-153">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="996ae-153">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
