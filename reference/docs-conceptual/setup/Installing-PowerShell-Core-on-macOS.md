---
title: macOS への PowerShell Core のインストール
description: macOS への PowerShell Core のインストールに関する情報
ms.date: 08/06/2018
ms.openlocfilehash: ff1814d95b3ca3fa8497069dff249fd2ad5576ef
ms.sourcegitcommit: 01ac77cd0b00e4e5e964504563a9212e8002e5e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39587467"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="2a5df-103">macOS への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="2a5df-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="2a5df-104">PowerShell Core は、macOS 10.12 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2a5df-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="2a5df-105">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="2a5df-106">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a5df-106">Once the package is installed, run `pwsh` from a terminal.</span></span>

### <a name="installation-via-homebrew-on-macos-1012"></a><span data-ttu-id="2a5df-107">Homebrew による macOS 10.12 以降へのインストール</span><span class="sxs-lookup"><span data-stu-id="2a5df-107">Installation via Homebrew on macOS 10.12+</span></span>

<span data-ttu-id="2a5df-108">[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="2a5df-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="2a5df-109">ターミナル ウィンドウで「`brew`」と入力して Homebrew を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a5df-109">From a terminal window, type `brew` to run Homebrew.</span></span>  <span data-ttu-id="2a5df-110">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-110">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

> [!NOTE]
> <span data-ttu-id="2a5df-111">過去に Homebrew をインストールした場合は、'brew update-reset' && 'brew update' を実行することを常にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2a5df-111">If you installed Homebrew in the past, it's always a good idea to run 'brew update-reset' && 'brew update'.</span></span>
```sh
brew update-reset
brew update
```

> <span data-ttu-id="2a5df-112">Homebrew の古いバージョンはタップ 'caskroom/cask' を使用していましたが、これは非推奨になり、'homebrew/cask' に移行されています。</span><span class="sxs-lookup"><span data-stu-id="2a5df-112">Older versions of Homebrew used the tap 'caskroom/cask', which has been deprecated, and migrated into 'homebrew/cask'.</span></span>  <span data-ttu-id="2a5df-113">詳しくは、「[Homebrew-cask][cask]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a5df-113">More information can be found at [Homebrew-cask][cask].</span></span> <span data-ttu-id="2a5df-114">現在のタップの一覧を表示するには、'brew tap' コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a5df-114">Use the 'brew tap' command to list your current taps.</span></span>  <span data-ttu-id="2a5df-115">'caskroom/cask' が表示される場合は、'brew update' を使用して Homebrew にタップを移行させることができます。</span><span class="sxs-lookup"><span data-stu-id="2a5df-115">If you see 'caskroom/cask' you can use 'brew update' to have Homebrew migrate the taps.</span></span>

```sh
brew tap
brew update
```

<span data-ttu-id="2a5df-116">Homebrew をインストールまたは更新すると、PowerShell のインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-116">Once you've installed/updated Homebrew, installing PowerShell is easy.</span></span>

<span data-ttu-id="2a5df-117">PowerShell をインストールするには:</span><span class="sxs-lookup"><span data-stu-id="2a5df-117">To install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="2a5df-118">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a5df-118">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="2a5df-119">PowerShell を終了して bash に戻るには、'exit' コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a5df-119">To exit PowerShell, and return to bash, use the 'exit' command.</span></span>
```sh
exit
```

<span data-ttu-id="2a5df-120">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="2a5df-120">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="2a5df-121">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、アップグレードを完了するには、PowerShell シェルを終了し、再起動して、$PSVersionTable に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-121">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in $PSVersionTable.</span></span>

### <a name="installing-preview-via-homebrew-on-macos-1012"></a><span data-ttu-id="2a5df-122">macOS 10.12 以降での Homebrew によるプレビューのインストール</span><span class="sxs-lookup"><span data-stu-id="2a5df-122">Installing Preview via Homebrew on macOS 10.12+</span></span>

<span data-ttu-id="2a5df-123">[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="2a5df-123">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="2a5df-124">ターミナル ウィンドウで「`brew`」と入力して Homebrew を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a5df-124">From a terminal window, type `brew` to run Homebrew.</span></span>  <span data-ttu-id="2a5df-125">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-125">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

> [!NOTE]
> <span data-ttu-id="2a5df-126">過去に Homebrew をインストールした場合は、'brew update-reset' && 'brew update' を実行することを常にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2a5df-126">If you installed Homebrew in the past, it's always a good idea to run 'brew update-reset' && 'brew update'.</span></span>
```sh
brew update-reset
brew update
```

<span data-ttu-id="2a5df-127">次に、`versions` cask リポジトリをタップしてプレビュー パッケージを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-127">Then, you must tap the `versions` casks repository to get the preview package:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="2a5df-128">PowerShell のプレビューをインストールするには:</span><span class="sxs-lookup"><span data-stu-id="2a5df-128">To install PowerShell Preview:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="2a5df-129">最後に、インストールが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a5df-129">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="2a5df-130">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell プレビューをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="2a5df-130">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell Preview:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="2a5df-131">上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、アップグレードを完了するには、PowerShell シェルを終了し、再起動して、$PSVersionTable に表示される値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-131">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in $PSVersionTable.</span></span>

### <a name="installation-via-direct-download"></a><span data-ttu-id="2a5df-132">直接ダウンロードによるインストール</span><span class="sxs-lookup"><span data-stu-id="2a5df-132">Installation via Direct Download</span></span>

<span data-ttu-id="2a5df-133">[リリース][] ページから macOS マシンに PKG パッケージ `powershell-6.0.2-osx.10.12-x64.pkg` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2a5df-133">Download the PKG package `powershell-6.0.2-osx.10.12-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="2a5df-134">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="2a5df-134">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.0.2-osx.10.12-x64.pkg -target /
```

## <a name="binary-archives"></a><span data-ttu-id="2a5df-135">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="2a5df-135">Binary Archives</span></span>

<span data-ttu-id="2a5df-136">macOS プラットフォームと Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2a5df-136">PowerShell binary `tar.gz` archives are provided for macOS and Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="2a5df-137">macOS へのバイナリ アーカイブのインストール</span><span class="sxs-lookup"><span data-stu-id="2a5df-137">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.0.2

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.0.2

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.0.2/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.0.2/pwsh /usr/local/bin/pwsh
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="2a5df-138">PowerShell Core のアンインストール</span><span class="sxs-lookup"><span data-stu-id="2a5df-138">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="2a5df-139">Homebrew で PowerShell をインストールした場合、アンインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-139">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="2a5df-140">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-140">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="2a5df-141">追加の PowerShell パスを削除するには、このドキュメントの「[パス][]」セクションを参照し、`sudo rm` を使用して目的のパスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="2a5df-141">To remove the additional PowerShell paths, please see the [paths][] section in this document and remove the desired the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="2a5df-142">Homebrew でインストールした場合、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="2a5df-142">This is not necessary if you installed with Homebrew.</span></span>

[パス]:#paths
[paths]:#paths

## <a name="paths"></a><span data-ttu-id="2a5df-144">パス</span><span class="sxs-lookup"><span data-stu-id="2a5df-144">Paths</span></span>

* <span data-ttu-id="2a5df-145">`$PSHOME` は `/usr/local/microsoft/powershell/6.0.2/` です</span><span class="sxs-lookup"><span data-stu-id="2a5df-145">`$PSHOME` is `/usr/local/microsoft/powershell/6.0.2/`</span></span>
* <span data-ttu-id="2a5df-146">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2a5df-146">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="2a5df-147">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2a5df-147">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="2a5df-148">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2a5df-148">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="2a5df-149">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2a5df-149">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="2a5df-150">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2a5df-150">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="2a5df-151">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="2a5df-151">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="2a5df-152">プロファイルには、PowerShell のホスト単位の構成が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="2a5df-152">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="2a5df-153">そのため、既定のホスト固有のプロファイルは、同じ場所の `Microsoft.PowerShell_profile.ps1` に存在します。</span><span class="sxs-lookup"><span data-stu-id="2a5df-153">So the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="2a5df-154">PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="2a5df-154">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="2a5df-155">macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a5df-155">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="2a5df-156">そのため、`$PSHOME` は `/usr/local/microsoft/powershell/6.0.2/` です。シンボリックリンクは `/usr/local/bin/pwsh` にあります。</span><span class="sxs-lookup"><span data-stu-id="2a5df-156">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.0.2/`, and the symlink is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2a5df-157">その他の情報</span><span class="sxs-lookup"><span data-stu-id="2a5df-157">Additional Resources</span></span>

* <span data-ttu-id="2a5df-158">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="2a5df-158">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="2a5df-159">[Homebrew Github リポジトリ][GitHub]</span><span class="sxs-lookup"><span data-stu-id="2a5df-159">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="2a5df-160">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="2a5df-160">[Homebrew-Cask][cask]</span></span>


[brew]: http://brew.sh/
[GitHub]: https://github.com/Homebrew
[Cask]: https://github.com/Homebrew/homebrew-cask
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
