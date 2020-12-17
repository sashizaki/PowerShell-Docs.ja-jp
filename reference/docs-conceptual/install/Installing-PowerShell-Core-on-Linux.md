---
title: Linux への PowerShell のインストール
description: さまざまな Linux ディストリビューションへの PowerShell のインストールに関する情報
ms.date: 12/10/2020
ms.openlocfilehash: 1bf96bc6bfb3f6544d8a4fd5b287dd6d659691ec
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "97069871"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="e62f6-103">Linux への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="e62f6-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="e62f6-104">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="e62f6-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="e62f6-105">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="e62f6-106">[プレビュー リリース](#installing-preview-releases)をインストールした場合は、`pwsh-preview` を実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-107">PowerShell 7 はインプレース アップグレードで、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="e62f6-108">`/usr/local/microsoft/powershell/6` フォルダーは `/usr/local/microsoft/powershell/7` に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="e62f6-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="e62f6-109">PowerShell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[バイナリ アーカイブ](#binary-archives)方法を使用して PowerShell 6 を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="e62f6-110">公式にサポートされていない Linux ディストリビューションの場合は、[PowerShell の Snap パッケージ][snap]を使った PowerShell のインストールを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="e62f6-111">また、Linux [`tar.gz` アーカイブ][tar]を使用して、直接 PowerShell バイナリを展開できますが、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e62f6-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<!-- TODO: Update for supported releases v7.0 & v7.1 -->

<span data-ttu-id="e62f6-112">PowerShell 7.1 で公式にサポートされているプラットフォーム リリース</span><span class="sxs-lookup"><span data-stu-id="e62f6-112">Officially supported platform releases for PowerShell 7.1</span></span>

- <span data-ttu-id="e62f6-113">Ubuntu 16.04/18.04/20.04 (ARM64 を含む)</span><span class="sxs-lookup"><span data-stu-id="e62f6-113">Ubuntu 16.04/18.04/20.04 (including ARM64)</span></span>
- <span data-ttu-id="e62f6-114">Ubuntu 19.10 (スナップ パッケージを使用)</span><span class="sxs-lookup"><span data-stu-id="e62f6-114">Ubuntu 19.10 (via Snap package)</span></span>
- <span data-ttu-id="e62f6-115">Debian 9/10</span><span class="sxs-lookup"><span data-stu-id="e62f6-115">Debian 9/10</span></span>
- <span data-ttu-id="e62f6-116">CentOS と RHEL 7/8</span><span class="sxs-lookup"><span data-stu-id="e62f6-116">CentOS and RHEL 7/8</span></span>
- <span data-ttu-id="e62f6-117">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="e62f6-117">Fedora 30</span></span>
- <span data-ttu-id="e62f6-118">Alpine 3.11 以降 (ARM64 を含む)</span><span class="sxs-lookup"><span data-stu-id="e62f6-118">Alpine 3.11+ (including ARM64)</span></span>

<span data-ttu-id="e62f6-119">PowerShell 7.0 で公式にサポートされているプラットフォーム リリース</span><span class="sxs-lookup"><span data-stu-id="e62f6-119">Officially supported platform releases for PowerShell 7.0</span></span>

- <span data-ttu-id="e62f6-120">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-120">Ubuntu 16.04</span></span>
- <span data-ttu-id="e62f6-121">Ubuntu 18.04 および 20.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-121">Ubuntu 18.04 and 20.04</span></span>
- <span data-ttu-id="e62f6-122">Debian 8</span><span class="sxs-lookup"><span data-stu-id="e62f6-122">Debian 8</span></span>
- <span data-ttu-id="e62f6-123">Debian 9</span><span class="sxs-lookup"><span data-stu-id="e62f6-123">Debian 9</span></span>
- <span data-ttu-id="e62f6-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="e62f6-124">Debian 10</span></span>
- <span data-ttu-id="e62f6-125">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="e62f6-125">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="e62f6-126">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-126">CentOS 7</span></span>
- <span data-ttu-id="e62f6-127">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-127">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="e62f6-128">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="e62f6-128">Fedora 28</span></span>
- <span data-ttu-id="e62f6-129">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="e62f6-129">Fedora 29</span></span>
- <span data-ttu-id="e62f6-130">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="e62f6-130">Fedora 30</span></span>
- <span data-ttu-id="e62f6-131">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="e62f6-131">openSUSE 42.3</span></span>
- <span data-ttu-id="e62f6-132">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="e62f6-132">openSUSE Leap 15</span></span>

<span data-ttu-id="e62f6-133">コミュニティでサポートされているリリース</span><span class="sxs-lookup"><span data-stu-id="e62f6-133">Community supported releases</span></span>

- <span data-ttu-id="e62f6-134">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="e62f6-134">Ubuntu 18.10</span></span>
- <span data-ttu-id="e62f6-135">Ubuntu 19.10 および 20.10</span><span class="sxs-lookup"><span data-stu-id="e62f6-135">Ubuntu 19.10 and 20.10</span></span>
- <span data-ttu-id="e62f6-136">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="e62f6-136">Arch Linux</span></span>
- <span data-ttu-id="e62f6-137">Kali</span><span class="sxs-lookup"><span data-stu-id="e62f6-137">Kali</span></span>
- <span data-ttu-id="e62f6-138">Raspbian (試験段階)</span><span class="sxs-lookup"><span data-stu-id="e62f6-138">Raspbian (experimental)</span></span>

<span data-ttu-id="e62f6-139">代替のインストール方法</span><span class="sxs-lookup"><span data-stu-id="e62f6-139">Alternate install methods</span></span>

- <span data-ttu-id="e62f6-140">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="e62f6-140">Snap Package</span></span>
- <span data-ttu-id="e62f6-141">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="e62f6-141">Binary Archives</span></span>
- <span data-ttu-id="e62f6-142">.NET グローバル ツール</span><span class="sxs-lookup"><span data-stu-id="e62f6-142">.NET Global tool</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="e62f6-143">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-143">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="e62f6-144">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-144">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="e62f6-145">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-145">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e62f6-146">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-146">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of packages after we added packages.microsoft.com
sudo apt-get update
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

<span data-ttu-id="e62f6-147">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-147">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e62f6-148">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-148">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="e62f6-149">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-149">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="e62f6-150">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_7.1.0-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-150">Download the Debian package `powershell_7.1.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="e62f6-151">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-151">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="e62f6-152">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-152">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="e62f6-153">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-153">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="e62f6-154">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-154">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="e62f6-155">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-155">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="e62f6-156">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-156">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="e62f6-157">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-157">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e62f6-158">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-158">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of products
sudo apt-get update
# Enable the "universe" repositories
sudo add-apt-repository universe
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

<span data-ttu-id="e62f6-159">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-159">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e62f6-160">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-160">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="e62f6-161">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-161">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="e62f6-162">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_7.1.0-1.ubuntu.18.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-162">Download the Debian package `powershell_7.1.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="e62f6-163">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-163">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="e62f6-164">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-164">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="e62f6-165">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-165">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="e62f6-166">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-166">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-2004"></a><span data-ttu-id="e62f6-167">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-167">Ubuntu 20.04</span></span>

### <a name="installation-via-package-repository---ubuntu-2004"></a><span data-ttu-id="e62f6-168">パッケージ リポジトリによるインストール - Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-168">Installation via Package Repository - Ubuntu 20.04</span></span>

<span data-ttu-id="e62f6-169">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-169">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e62f6-170">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-170">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of products
sudo apt-get update
# Enable the "universe" repositories
sudo add-apt-repository universe
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

<span data-ttu-id="e62f6-171">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-171">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e62f6-172">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-172">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-2004"></a><span data-ttu-id="e62f6-173">直接ダウンロードによるインストール - Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-173">Installation via Direct Download - Ubuntu 20.04</span></span>

<span data-ttu-id="e62f6-174">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_7.1.0-1.ubuntu.20.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-174">Download the Debian package `powershell_7.1.0-1.ubuntu.20.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="e62f6-175">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-175">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.0-1.ubuntu.20.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="e62f6-176">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-176">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="e62f6-177">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-177">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-2004"></a><span data-ttu-id="e62f6-178">アンインストール - Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-178">Uninstallation - Ubuntu 20.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="e62f6-179">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="e62f6-179">Ubuntu 18.10</span></span>

<span data-ttu-id="e62f6-180">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-180">Installation is supported via `snapd`.</span></span> <span data-ttu-id="e62f6-181">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e62f6-181">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-182">Ubuntu 18.10 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="e62f6-182">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1910-and-2010"></a><span data-ttu-id="e62f6-183">Ubuntu 19.10 および 20.10</span><span class="sxs-lookup"><span data-stu-id="e62f6-183">Ubuntu 19.10 and 20.10</span></span>

<span data-ttu-id="e62f6-184">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-184">Installation is supported via `snapd`.</span></span> <span data-ttu-id="e62f6-185">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e62f6-185">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-186">Ubuntu 19.10 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="e62f6-186">Ubuntu 19.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="e62f6-187">Debian 8</span><span class="sxs-lookup"><span data-stu-id="e62f6-187">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="e62f6-188">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="e62f6-188">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="e62f6-189">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-189">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e62f6-190">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-190">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="e62f6-191">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-191">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e62f6-192">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-192">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="e62f6-193">Debian 9</span><span class="sxs-lookup"><span data-stu-id="e62f6-193">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="e62f6-194">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="e62f6-194">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="e62f6-195">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-195">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e62f6-196">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-196">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl gnupg apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="e62f6-197">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-197">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e62f6-198">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-198">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="e62f6-199">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="e62f6-199">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="e62f6-200">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_7.1.0-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-200">Download the Debian package `powershell_7.1.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="e62f6-201">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-201">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="e62f6-202">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="e62f6-202">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="e62f6-203">Debian 10</span><span class="sxs-lookup"><span data-stu-id="e62f6-203">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-204">Debian 10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-204">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="e62f6-205">パッケージ リポジトリによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="e62f6-205">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="e62f6-206">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-206">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="e62f6-207">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-207">The preferred method is as follows:</span></span>

```sh
# Download the Microsoft repository GPG keys
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="e62f6-208">直接ダウンロードによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="e62f6-208">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="e62f6-209">[リリース][] ページから Debian コンピューターに tar.gz パッケージ `powershell-7.1.0-linux-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-209">Download the tar.gz package `powershell-7.1.0-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="e62f6-210">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-210">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo apt-get update
# install the requirements
sudo apt-get install -y \
        less \
        locales \
        ca-certificates \
        libicu63 \
        libssl1.1 \
        libc6 \
        libgcc1 \
        libgssapi-krb5-2 \
        liblttng-ust0 \
        libstdc++6 \
        zlib1g \
        curl

# Download the powershell '.tar.gz' archive
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="alpine-39-and-310"></a><span data-ttu-id="e62f6-211">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="e62f6-211">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-212">Alpine 3.9 および 3.10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-212">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="e62f6-213">直接ダウンロードによるインストール - Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="e62f6-213">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="e62f6-214">[リリース][] ページから Alpine コンピューターに tar.gz パッケージ `powershell-7.1.0-linux-alpine-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-214">Download the tar.gz package `powershell-7.1.0-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="e62f6-215">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-215">Then, in the terminal, execute the following commands:</span></span>

```sh
# install the requirements
sudo apk add --no-cache \
    ca-certificates \
    less \
    ncurses-terminfo-base \
    krb5-libs \
    libgcc \
    libintl \
    libssl1.1 \
    libstdc++ \
    tzdata \
    userspace-rcu \
    zlib \
    icu-libs \
    curl

sudo apk -X https://dl-cdn.alpinelinux.org/alpine/edge/main add --no-cache \
    lttng-ust

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="centos-7"></a><span data-ttu-id="e62f6-216">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-216">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-217">このパッケージは Oracle Linux 7 で動作します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-217">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="e62f6-218">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-218">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="e62f6-219">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-219">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="e62f6-220">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-220">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e62f6-221">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-221">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="e62f6-222">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-222">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="e62f6-223">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-7.1.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-223">Using [CentOS 7][], download the RPM package `powershell-7.1.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="e62f6-224">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-224">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="e62f6-225">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-225">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="e62f6-226">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-226">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="e62f6-228">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-228">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="e62f6-229">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-229">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="e62f6-230">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-230">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="e62f6-231">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-231">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="e62f6-232">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-232">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="e62f6-233">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-233">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="e62f6-234">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-7.1.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-234">Download the RPM package `powershell-7.1.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="e62f6-235">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-235">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="e62f6-236">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-236">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="e62f6-237">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-237">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="e62f6-238">openSUSE</span><span class="sxs-lookup"><span data-stu-id="e62f6-238">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="e62f6-239">インストール - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="e62f6-239">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="e62f6-240">インストール - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="e62f6-240">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="e62f6-241">アンインストール - openSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="e62f6-241">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="e62f6-242">Fedora</span><span class="sxs-lookup"><span data-stu-id="e62f6-242">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-243">Fedora 28 は、PowerShell 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-243">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-244">Fedora 29 および 30 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-244">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="e62f6-245">パッケージ リポジトリによるインストール (推奨) - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="e62f6-245">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="e62f6-246">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-246">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf check-update

# Install a system component
sudo dnf install compat-openssl10

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="e62f6-247">直接ダウンロードによるインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="e62f6-247">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="e62f6-248">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-7.1.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-248">Download the RPM package `powershell-7.1.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="e62f6-249">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-249">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="e62f6-250">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-250">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="e62f6-251">アンインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="e62f6-251">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="e62f6-252">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="e62f6-252">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-253">Arch のサポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-253">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="e62f6-254">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-254">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="e62f6-255">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="e62f6-255">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="e62f6-256">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="e62f6-256">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="e62f6-257">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="e62f6-257">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="e62f6-258">AUR のパッケージはコミュニティによって管理されています。公式のサポートは存在しません。</span><span class="sxs-lookup"><span data-stu-id="e62f6-258">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="e62f6-259">AUR からパッケージをインストールする方法については、[Arch Linux の wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) か「[Docker での PowerShell の使用](powershell-in-docker.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e62f6-259">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="e62f6-261">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="e62f6-261">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="e62f6-262">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="e62f6-262">Getting snapd</span></span>

<span data-ttu-id="e62f6-263">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="e62f6-263">`snapd` is required to run snaps.</span></span> <span data-ttu-id="e62f6-264">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e62f6-264">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="e62f6-265">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="e62f6-265">Installation via Snap</span></span>

<span data-ttu-id="e62f6-266">Linux 向けの PowerShell は、インストールと更新を容易にするために [Snap ストア](https://snapcraft.io/store)に公開されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-266">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="e62f6-267">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-267">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="e62f6-268">プレビュー バージョンをインストールするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-268">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="e62f6-269">インストールしたら、Snap は自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-269">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="e62f6-270">`sudo snap refresh powershell` または `sudo snap refresh powershell-preview` を使って、アップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-270">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="e62f6-271">アンインストール</span><span class="sxs-lookup"><span data-stu-id="e62f6-271">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="e62f6-272">or</span><span class="sxs-lookup"><span data-stu-id="e62f6-272">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="e62f6-273">Kali</span><span class="sxs-lookup"><span data-stu-id="e62f6-273">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-274">Kali サポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-274">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="e62f6-275">インストール - Kali</span><span class="sxs-lookup"><span data-stu-id="e62f6-275">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="e62f6-276">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="e62f6-276">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="e62f6-277">Raspbian</span><span class="sxs-lookup"><span data-stu-id="e62f6-277">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="e62f6-278">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="e62f6-278">Raspbian support is experimental.</span></span>

<span data-ttu-id="e62f6-279">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-279">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="e62f6-280">CoreCLR と PowerShell は、Pi 2 および Pi 3 デバイス上でのみ動作します。[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスには、サポート外のプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-280">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="e62f6-281">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="e62f6-281">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="e62f6-282">インストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="e62f6-282">Installation - Raspbian</span></span>

```sh
###################################
# Prerequisites

# Update package lists
sudo apt-get update

# Install libunwind8 and libssl1.0
# Regex is used to ensure that we do not install libssl1.0-dev, as it is a variant that is not required
sudo apt-get install '^libssl1.0.[0-9]$' libunwind8 -y

###################################
# Download and extract PowerShell

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.1.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="e62f6-283">必要に応じて、`pwsh` バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="e62f6-283">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="e62f6-284">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="e62f6-284">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="e62f6-285">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="e62f6-285">Installing Preview Releases</span></span>

<span data-ttu-id="e62f6-286">パッケージ リポジトリを介して、Linux 用の PowerShell Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="e62f6-286">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="e62f6-287">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="e62f6-287">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="e62f6-288">さまざまなパッケージ マネージャーを使用して安定版およびプレビュー版パッケージをインストールするためのコマンドを、以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-288">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="e62f6-289">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="e62f6-289">Distribution(s)</span></span> |            <span data-ttu-id="e62f6-290">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="e62f6-290">Stable Command</span></span>            |               <span data-ttu-id="e62f6-291">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="e62f6-291">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="e62f6-292">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="e62f6-292">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="e62f6-293">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="e62f6-293">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="e62f6-294">Fedora</span><span class="sxs-lookup"><span data-stu-id="e62f6-294">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="e62f6-295">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="e62f6-295">Install as a .NET Global tool</span></span>

<span data-ttu-id="e62f6-296">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-296">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="e62f6-297">dotnet tool install によって、`PATH` 環境変数に `~/.dotnet/tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="e62f6-297">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="e62f6-298">ただし、現在実行中のシェルには更新された `PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="e62f6-298">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="e62f6-299">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できるはずです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-299">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="e62f6-300">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="e62f6-300">Binary Archives</span></span>

<span data-ttu-id="e62f6-301">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-301">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="e62f6-302">依存関係</span><span class="sxs-lookup"><span data-stu-id="e62f6-302">Dependencies</span></span>

<span data-ttu-id="e62f6-303">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e62f6-303">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="e62f6-304">ただし、.NET Core ランタイムにはディストリビューションごとに異なる依存関係が必要であり、PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-304">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="e62f6-305">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="e62f6-305">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="e62f6-306">OS</span><span class="sxs-lookup"><span data-stu-id="e62f6-306">OS</span></span>                 | <span data-ttu-id="e62f6-307">依存関係</span><span class="sxs-lookup"><span data-stu-id="e62f6-307">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="e62f6-308">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-308">Ubuntu 16.04</span></span>       | <span data-ttu-id="e62f6-309">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="e62f6-309">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e62f6-310">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="e62f6-310">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="e62f6-311">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="e62f6-311">Ubuntu 17.10</span></span>       | <span data-ttu-id="e62f6-312">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="e62f6-312">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e62f6-313">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="e62f6-313">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="e62f6-314">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e62f6-314">Ubuntu 18.04</span></span>       | <span data-ttu-id="e62f6-315">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="e62f6-315">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e62f6-316">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="e62f6-316">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="e62f6-317">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="e62f6-317">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="e62f6-318">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="e62f6-318">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e62f6-319">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="e62f6-319">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="e62f6-320">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="e62f6-320">Debian 9 (Stretch)</span></span> | <span data-ttu-id="e62f6-321">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="e62f6-321">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="e62f6-322">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="e62f6-322">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="e62f6-323">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-323">CentOS 7</span></span> <br> <span data-ttu-id="e62f6-324">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-324">Oracle Linux 7</span></span> <br> <span data-ttu-id="e62f6-325">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="e62f6-325">RHEL 7</span></span> | <span data-ttu-id="e62f6-326">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="e62f6-326">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="e62f6-327">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="e62f6-327">openSUSE 42.3</span></span> | <span data-ttu-id="e62f6-328">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="e62f6-328">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="e62f6-329">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="e62f6-329">openSUSE Leap 15</span></span> | <span data-ttu-id="e62f6-330">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="e62f6-330">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="e62f6-331">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="e62f6-331">Fedora 27</span></span> <br> <span data-ttu-id="e62f6-332">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="e62f6-332">Fedora 28</span></span> | <span data-ttu-id="e62f6-333">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="e62f6-333">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="e62f6-334">公式にサポートされていない Linux ディストリビューションに PowerShell バイナリを展開するには、別の手順によってターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e62f6-334">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="e62f6-335">たとえば、[Amazon Linux Dockerfile][amazon-dockerfile] では依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="e62f6-335">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="e62f6-336">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="e62f6-336">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="e62f6-337">Linux</span><span class="sxs-lookup"><span data-stu-id="e62f6-337">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="e62f6-338">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="e62f6-338">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="e62f6-339">パス</span><span class="sxs-lookup"><span data-stu-id="e62f6-339">Paths</span></span>

- <span data-ttu-id="e62f6-340">`$PSHOME` は `/opt/microsoft/powershell/7/` です</span><span class="sxs-lookup"><span data-stu-id="e62f6-340">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="e62f6-341">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="e62f6-341">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="e62f6-342">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="e62f6-342">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="e62f6-343">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="e62f6-343">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="e62f6-344">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="e62f6-344">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="e62f6-345">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="e62f6-345">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="e62f6-346">PSReadLine 履歴は、`~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="e62f6-346">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="e62f6-347">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="e62f6-347">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="e62f6-348">PowerShell では、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-348">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

## <a name="installation-support"></a><span data-ttu-id="e62f6-349">インストールのサポート</span><span class="sxs-lookup"><span data-stu-id="e62f6-349">Installation support</span></span>

<span data-ttu-id="e62f6-350">Microsoft は、このドキュメントでインストール方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e62f6-350">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="e62f6-351">他のソースには、利用可能な別のインストール方法が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e62f6-351">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="e62f6-352">そのようなツールや方法が役に立つものであっても、Microsoft は、そのような方法をサポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e62f6-352">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
