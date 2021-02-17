---
title: Linux への PowerShell のインストール
description: さまざまな Linux ディストリビューションへの PowerShell のインストールに関する情報
ms.date: 02/02/2021
ms.openlocfilehash: 1e7fabdc94ba70a91eb5c6425893bc5af640e584
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563302"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="9427a-103">Linux への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="9427a-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="9427a-104">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="9427a-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="9427a-105">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="9427a-106">[プレビュー リリース](#installing-preview-releases)をインストールした場合は、`pwsh-preview` を実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-107">PowerShell 7 はインプレース アップグレードで、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="9427a-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="9427a-108">`/usr/local/microsoft/powershell/6` フォルダーは `/usr/local/microsoft/powershell/7` に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="9427a-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="9427a-109">PowerShell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[バイナリ アーカイブ](#binary-archives)方法を使用して PowerShell 6 を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="9427a-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="9427a-110">公式にサポートされていない Linux ディストリビューションの場合は、[PowerShell の Snap パッケージ][snap]を使った PowerShell のインストールを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="9427a-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="9427a-111">また、Linux [`tar.gz` アーカイブ][tar]を使用して、直接 PowerShell バイナリを展開できますが、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9427a-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<!-- TODO: Update for supported releases v7.0 & v7.1 -->

<span data-ttu-id="9427a-112">PowerShell 7.1 で公式にサポートされているプラットフォーム リリース</span><span class="sxs-lookup"><span data-stu-id="9427a-112">Officially supported platform releases for PowerShell 7.1</span></span>

- <span data-ttu-id="9427a-113">Ubuntu 16.04/18.04/20.04 (ARM64 を含む)</span><span class="sxs-lookup"><span data-stu-id="9427a-113">Ubuntu 16.04/18.04/20.04 (including ARM64)</span></span>
- <span data-ttu-id="9427a-114">Ubuntu 19.10 (スナップ パッケージを使用)</span><span class="sxs-lookup"><span data-stu-id="9427a-114">Ubuntu 19.10 (via Snap package)</span></span>
- <span data-ttu-id="9427a-115">Debian 9/10</span><span class="sxs-lookup"><span data-stu-id="9427a-115">Debian 9/10</span></span>
- <span data-ttu-id="9427a-116">CentOS と RHEL 7/8</span><span class="sxs-lookup"><span data-stu-id="9427a-116">CentOS and RHEL 7/8</span></span>
- <span data-ttu-id="9427a-117">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="9427a-117">Fedora 30</span></span>
- <span data-ttu-id="9427a-118">Alpine 3.11 以降 (ARM64 を含む)</span><span class="sxs-lookup"><span data-stu-id="9427a-118">Alpine 3.11+ (including ARM64)</span></span>

<span data-ttu-id="9427a-119">PowerShell 7.0 で公式にサポートされているプラットフォーム リリース</span><span class="sxs-lookup"><span data-stu-id="9427a-119">Officially supported platform releases for PowerShell 7.0</span></span>

- <span data-ttu-id="9427a-120">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="9427a-120">Ubuntu 16.04</span></span>
- <span data-ttu-id="9427a-121">Ubuntu 18.04 および 20.04</span><span class="sxs-lookup"><span data-stu-id="9427a-121">Ubuntu 18.04 and 20.04</span></span>
- <span data-ttu-id="9427a-122">Debian 8</span><span class="sxs-lookup"><span data-stu-id="9427a-122">Debian 8</span></span>
- <span data-ttu-id="9427a-123">Debian 9</span><span class="sxs-lookup"><span data-stu-id="9427a-123">Debian 9</span></span>
- <span data-ttu-id="9427a-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="9427a-124">Debian 10</span></span>
- <span data-ttu-id="9427a-125">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="9427a-125">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="9427a-126">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="9427a-126">CentOS 7</span></span>
- <span data-ttu-id="9427a-127">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="9427a-127">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="9427a-128">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="9427a-128">Fedora 28</span></span>
- <span data-ttu-id="9427a-129">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="9427a-129">Fedora 29</span></span>
- <span data-ttu-id="9427a-130">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="9427a-130">Fedora 30</span></span>
- <span data-ttu-id="9427a-131">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="9427a-131">openSUSE 42.3</span></span>
- <span data-ttu-id="9427a-132">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="9427a-132">openSUSE Leap 15</span></span>

<span data-ttu-id="9427a-133">コミュニティでサポートされているリリース</span><span class="sxs-lookup"><span data-stu-id="9427a-133">Community supported releases</span></span>

- <span data-ttu-id="9427a-134">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="9427a-134">Ubuntu 18.10</span></span>
- <span data-ttu-id="9427a-135">Ubuntu 19.10 および 20.10</span><span class="sxs-lookup"><span data-stu-id="9427a-135">Ubuntu 19.10 and 20.10</span></span>
- <span data-ttu-id="9427a-136">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="9427a-136">Arch Linux</span></span>
- <span data-ttu-id="9427a-137">Kali</span><span class="sxs-lookup"><span data-stu-id="9427a-137">Kali</span></span>
- <span data-ttu-id="9427a-138">Raspbian (試験段階)</span><span class="sxs-lookup"><span data-stu-id="9427a-138">Raspbian (experimental)</span></span>

<span data-ttu-id="9427a-139">代替のインストール方法</span><span class="sxs-lookup"><span data-stu-id="9427a-139">Alternate install methods</span></span>

- <span data-ttu-id="9427a-140">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="9427a-140">Snap Package</span></span>
- <span data-ttu-id="9427a-141">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="9427a-141">Binary Archives</span></span>
- <span data-ttu-id="9427a-142">.NET グローバル ツール</span><span class="sxs-lookup"><span data-stu-id="9427a-142">.NET Global tool</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="9427a-143">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="9427a-143">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="9427a-144">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="9427a-144">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="9427a-145">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-145">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="9427a-146">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9427a-146">The preferred method is as follows:</span></span>

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

<span data-ttu-id="9427a-147">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="9427a-147">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="9427a-148">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="9427a-148">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="9427a-149">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="9427a-149">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="9427a-150">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_7.1.2-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9427a-150">Download the Debian package `powershell_7.1.2-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="9427a-151">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-151">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.2-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="9427a-152">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="9427a-152">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="9427a-153">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="9427a-153">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="9427a-154">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="9427a-154">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="9427a-155">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="9427a-155">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="9427a-156">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="9427a-156">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="9427a-157">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-157">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="9427a-158">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9427a-158">The preferred method is as follows:</span></span>

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

<span data-ttu-id="9427a-159">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="9427a-159">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="9427a-160">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="9427a-160">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="9427a-161">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="9427a-161">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="9427a-162">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_7.1.2-1.ubuntu.18.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9427a-162">Download the Debian package `powershell_7.1.2-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="9427a-163">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-163">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.2-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="9427a-164">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="9427a-164">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="9427a-165">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="9427a-165">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="9427a-166">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="9427a-166">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-2004"></a><span data-ttu-id="9427a-167">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="9427a-167">Ubuntu 20.04</span></span>

### <a name="installation-via-package-repository---ubuntu-2004"></a><span data-ttu-id="9427a-168">パッケージ リポジトリによるインストール - Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="9427a-168">Installation via Package Repository - Ubuntu 20.04</span></span>

<span data-ttu-id="9427a-169">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-169">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="9427a-170">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9427a-170">The preferred method is as follows:</span></span>

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

<span data-ttu-id="9427a-171">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="9427a-171">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="9427a-172">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="9427a-172">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-2004"></a><span data-ttu-id="9427a-173">直接ダウンロードによるインストール - Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="9427a-173">Installation via Direct Download - Ubuntu 20.04</span></span>

<span data-ttu-id="9427a-174">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_7.1.2-1.ubuntu.20.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9427a-174">Download the Debian package `powershell_7.1.2-1.ubuntu.20.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="9427a-175">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-175">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.2-1.ubuntu.20.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="9427a-176">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="9427a-176">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="9427a-177">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="9427a-177">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-2004"></a><span data-ttu-id="9427a-178">アンインストール - Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="9427a-178">Uninstallation - Ubuntu 20.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="9427a-179">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="9427a-179">Ubuntu 18.10</span></span>

<span data-ttu-id="9427a-180">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9427a-180">Installation is supported via `snapd`.</span></span> <span data-ttu-id="9427a-181">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9427a-181">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-182">Ubuntu 18.10 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="9427a-182">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1910-and-2010"></a><span data-ttu-id="9427a-183">Ubuntu 19.10 および 20.10</span><span class="sxs-lookup"><span data-stu-id="9427a-183">Ubuntu 19.10 and 20.10</span></span>

<span data-ttu-id="9427a-184">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9427a-184">Installation is supported via `snapd`.</span></span> <span data-ttu-id="9427a-185">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9427a-185">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-186">Ubuntu 19.10 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="9427a-186">Ubuntu 19.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="9427a-187">Debian 8</span><span class="sxs-lookup"><span data-stu-id="9427a-187">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="9427a-188">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="9427a-188">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="9427a-189">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-189">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="9427a-190">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9427a-190">The preferred method is as follows:</span></span>

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

<span data-ttu-id="9427a-191">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="9427a-191">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="9427a-192">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="9427a-192">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="9427a-193">Debian 9</span><span class="sxs-lookup"><span data-stu-id="9427a-193">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="9427a-194">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="9427a-194">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="9427a-195">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-195">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="9427a-196">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9427a-196">The preferred method is as follows:</span></span>

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

<span data-ttu-id="9427a-197">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="9427a-197">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="9427a-198">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="9427a-198">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="9427a-199">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="9427a-199">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="9427a-200">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_7.1.2-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9427a-200">Download the Debian package `powershell_7.1.2-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="9427a-201">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-201">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.2-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="9427a-202">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="9427a-202">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="9427a-203">Debian 10</span><span class="sxs-lookup"><span data-stu-id="9427a-203">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-204">Debian 10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9427a-204">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="9427a-205">パッケージ リポジトリによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="9427a-205">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="9427a-206">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-206">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="9427a-207">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9427a-207">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="9427a-208">直接ダウンロードによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="9427a-208">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="9427a-209">[リリース][] ページから Debian コンピューターに tar.gz パッケージ `powershell-7.1.2-linux-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9427a-209">Download the tar.gz package `powershell-7.1.2-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="9427a-210">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-210">Then, in the terminal, execute the following commands:</span></span>

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
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="9427a-211">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="9427a-211">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-212">Alpine 3.9 および 3.10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9427a-212">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="9427a-213">直接ダウンロードによるインストール - Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="9427a-213">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="9427a-214">[リリース][] ページから Alpine コンピューターに tar.gz パッケージ `powershell-7.1.2-linux-alpine-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9427a-214">Download the tar.gz package `powershell-7.1.2-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="9427a-215">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-215">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="centos-7"></a><span data-ttu-id="9427a-216">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="9427a-216">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-217">このパッケージは Oracle Linux 7 で動作します。</span><span class="sxs-lookup"><span data-stu-id="9427a-217">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="9427a-218">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="9427a-218">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="9427a-219">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-219">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="9427a-220">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="9427a-220">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="9427a-221">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="9427a-221">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="9427a-222">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="9427a-222">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="9427a-223">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-7.1.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9427a-223">Using [CentOS 7][], download the RPM package `powershell-7.1.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="9427a-224">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-224">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="9427a-225">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="9427a-225">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="9427a-226">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="9427a-226">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="9427a-228">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="9427a-228">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="9427a-229">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="9427a-229">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="9427a-230">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-230">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="9427a-231">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="9427a-231">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="9427a-232">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="9427a-232">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="9427a-233">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="9427a-233">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="9427a-234">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-7.1.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9427a-234">Download the RPM package `powershell-7.1.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="9427a-235">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-235">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="9427a-236">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="9427a-236">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="9427a-237">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="9427a-237">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="9427a-238">openSUSE</span><span class="sxs-lookup"><span data-stu-id="9427a-238">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="9427a-239">インストール - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="9427a-239">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="9427a-240">インストール - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="9427a-240">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="9427a-241">アンインストール - openSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="9427a-241">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="9427a-242">Fedora</span><span class="sxs-lookup"><span data-stu-id="9427a-242">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-243">Fedora 28 は、PowerShell 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9427a-243">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-244">Fedora 29 および 30 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9427a-244">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="9427a-245">パッケージ リポジトリによるインストール (推奨) - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="9427a-245">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="9427a-246">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-246">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="9427a-247">直接ダウンロードによるインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="9427a-247">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="9427a-248">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-7.1.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9427a-248">Download the RPM package `powershell-7.1.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="9427a-249">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9427a-249">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.1.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="9427a-250">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="9427a-250">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="9427a-251">アンインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="9427a-251">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="9427a-252">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="9427a-252">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-253">Arch のサポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-253">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="9427a-254">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="9427a-254">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="9427a-255">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="9427a-255">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="9427a-256">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="9427a-256">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="9427a-257">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="9427a-257">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="9427a-258">AUR のパッケージはコミュニティによって管理されています。公式のサポートは存在しません。</span><span class="sxs-lookup"><span data-stu-id="9427a-258">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="9427a-259">AUR からパッケージをインストールする方法については、[Arch Linux の wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) か「[Docker での PowerShell の使用](powershell-in-docker.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9427a-259">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="9427a-261">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="9427a-261">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="9427a-262">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="9427a-262">Getting snapd</span></span>

<span data-ttu-id="9427a-263">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="9427a-263">`snapd` is required to run snaps.</span></span> <span data-ttu-id="9427a-264">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="9427a-264">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="9427a-265">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="9427a-265">Installation via Snap</span></span>

<span data-ttu-id="9427a-266">Linux 向けの PowerShell は、インストールと更新を容易にするために [Snap ストア](https://snapcraft.io/store)に公開されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-266">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="9427a-267">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9427a-267">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="9427a-268">プレビュー バージョンをインストールするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9427a-268">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="9427a-269">インストールしたら、Snap は自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="9427a-269">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="9427a-270">`sudo snap refresh powershell` または `sudo snap refresh powershell-preview` を使って、アップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="9427a-270">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="9427a-271">アンインストール</span><span class="sxs-lookup"><span data-stu-id="9427a-271">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="9427a-272">or</span><span class="sxs-lookup"><span data-stu-id="9427a-272">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="9427a-273">Kali</span><span class="sxs-lookup"><span data-stu-id="9427a-273">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-274">Kali サポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-274">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="9427a-275">インストール - Kali</span><span class="sxs-lookup"><span data-stu-id="9427a-275">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="9427a-276">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="9427a-276">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="9427a-277">Raspbian</span><span class="sxs-lookup"><span data-stu-id="9427a-277">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="9427a-278">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="9427a-278">Raspbian support is experimental.</span></span>

<span data-ttu-id="9427a-279">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9427a-279">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="9427a-280">CoreCLR と PowerShell は、Pi 2 および Pi 3 デバイス上でのみ動作します。[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスには、サポート外のプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="9427a-280">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="9427a-281">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="9427a-281">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="9427a-282">インストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="9427a-282">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.1.2-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="9427a-283">必要に応じて、`pwsh` バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="9427a-283">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="9427a-284">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="9427a-284">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="9427a-285">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="9427a-285">Installing Preview Releases</span></span>

<span data-ttu-id="9427a-286">パッケージ リポジトリを介して、Linux 用の PowerShell Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="9427a-286">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="9427a-287">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="9427a-287">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="9427a-288">さまざまなパッケージ マネージャーを使用して安定版およびプレビュー版パッケージをインストールするためのコマンドを、以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="9427a-288">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="9427a-289">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="9427a-289">Distribution(s)</span></span> |            <span data-ttu-id="9427a-290">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="9427a-290">Stable Command</span></span>            |               <span data-ttu-id="9427a-291">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="9427a-291">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="9427a-292">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="9427a-292">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="9427a-293">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="9427a-293">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="9427a-294">Fedora</span><span class="sxs-lookup"><span data-stu-id="9427a-294">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="9427a-295">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="9427a-295">Install as a .NET Global tool</span></span>

<span data-ttu-id="9427a-296">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="9427a-296">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="9427a-297">dotnet tool install によって、`PATH` 環境変数に `~/.dotnet/tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="9427a-297">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="9427a-298">ただし、現在実行中のシェルには更新された `PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="9427a-298">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="9427a-299">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できるはずです。</span><span class="sxs-lookup"><span data-stu-id="9427a-299">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="9427a-300">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="9427a-300">Binary Archives</span></span>

<span data-ttu-id="9427a-301">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9427a-301">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="9427a-302">依存関係</span><span class="sxs-lookup"><span data-stu-id="9427a-302">Dependencies</span></span>

<span data-ttu-id="9427a-303">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="9427a-303">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="9427a-304">ただし、.NET Core ランタイムにはディストリビューションごとに異なる依存関係が必要であり、PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="9427a-304">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="9427a-305">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="9427a-305">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="9427a-306">OS</span><span class="sxs-lookup"><span data-stu-id="9427a-306">OS</span></span>                 | <span data-ttu-id="9427a-307">依存関係</span><span class="sxs-lookup"><span data-stu-id="9427a-307">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="9427a-308">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="9427a-308">Ubuntu 16.04</span></span>       | <span data-ttu-id="9427a-309">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="9427a-309">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="9427a-310">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="9427a-310">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="9427a-311">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="9427a-311">Ubuntu 17.10</span></span>       | <span data-ttu-id="9427a-312">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="9427a-312">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="9427a-313">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="9427a-313">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="9427a-314">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="9427a-314">Ubuntu 18.04</span></span>       | <span data-ttu-id="9427a-315">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="9427a-315">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="9427a-316">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="9427a-316">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="9427a-317">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="9427a-317">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="9427a-318">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="9427a-318">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="9427a-319">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="9427a-319">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="9427a-320">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="9427a-320">Debian 9 (Stretch)</span></span> | <span data-ttu-id="9427a-321">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="9427a-321">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="9427a-322">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="9427a-322">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="9427a-323">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="9427a-323">CentOS 7</span></span> <br> <span data-ttu-id="9427a-324">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="9427a-324">Oracle Linux 7</span></span> <br> <span data-ttu-id="9427a-325">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="9427a-325">RHEL 7</span></span> | <span data-ttu-id="9427a-326">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="9427a-326">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="9427a-327">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="9427a-327">openSUSE 42.3</span></span> | <span data-ttu-id="9427a-328">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="9427a-328">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="9427a-329">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="9427a-329">openSUSE Leap 15</span></span> | <span data-ttu-id="9427a-330">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="9427a-330">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="9427a-331">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="9427a-331">Fedora 27</span></span> <br> <span data-ttu-id="9427a-332">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="9427a-332">Fedora 28</span></span> | <span data-ttu-id="9427a-333">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="9427a-333">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="9427a-334">公式にサポートされていない Linux ディストリビューションに PowerShell バイナリを展開するには、別の手順によってターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9427a-334">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="9427a-335">たとえば、[Amazon Linux Dockerfile][amazon-dockerfile] では依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="9427a-335">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="9427a-336">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="9427a-336">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="9427a-337">Linux</span><span class="sxs-lookup"><span data-stu-id="9427a-337">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="9427a-338">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="9427a-338">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="9427a-339">パス</span><span class="sxs-lookup"><span data-stu-id="9427a-339">Paths</span></span>

- <span data-ttu-id="9427a-340">`$PSHOME` は `/opt/microsoft/powershell/7/` です</span><span class="sxs-lookup"><span data-stu-id="9427a-340">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="9427a-341">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="9427a-341">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="9427a-342">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="9427a-342">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="9427a-343">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="9427a-343">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="9427a-344">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="9427a-344">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="9427a-345">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="9427a-345">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="9427a-346">PSReadLine 履歴は、`~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="9427a-346">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="9427a-347">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="9427a-347">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="9427a-348">PowerShell では、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="9427a-348">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

## <a name="installation-support"></a><span data-ttu-id="9427a-349">インストールのサポート</span><span class="sxs-lookup"><span data-stu-id="9427a-349">Installation support</span></span>

<span data-ttu-id="9427a-350">Microsoft は、このドキュメントでインストール方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9427a-350">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="9427a-351">他のソースには、利用可能な別のインストール方法が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9427a-351">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="9427a-352">そのようなツールや方法が役に立つものであっても、Microsoft は、そのような方法をサポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9427a-352">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->
[リリース]: https://aka.ms/PowerShell-Release?tag=stable
[releases]: https://aka.ms/PowerShell-Release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
