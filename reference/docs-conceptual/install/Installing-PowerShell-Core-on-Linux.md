---
title: Linux への PowerShell のインストール
description: さまざまな Linux ディストリビューションへの PowerShell のインストールに関する情報
ms.date: 03/09/2020
ms.openlocfilehash: 201bb693c3473f6b1f05d860562b1fc132912bb2
ms.sourcegitcommit: 7c7f8bb9afdc592d07bf7ff4179d000a48716f13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82174138"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="57429-103">Linux への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="57429-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="57429-104">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="57429-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="57429-105">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="57429-106">[プレビュー リリース](#installing-preview-releases)をインストールした場合は、`pwsh-preview` を実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="57429-107">PowerShell 7 はインプレース アップグレードで、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="57429-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="57429-108">`/usr/local/microsoft/powershell/6` フォルダーは `/usr/local/microsoft/powershell/7` に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="57429-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="57429-109">PowerShell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[バイナリ アーカイブ](#binary-archives)方法を使用して PowerShell 6 を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="57429-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="57429-110">公式にサポートされていない Linux ディストリビューションの場合は、[PowerShell の Snap パッケージ][snap]を使った PowerShell のインストールを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="57429-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="57429-111">また、Linux [`tar.gz` アーカイブ][tar]を使用して、直接 PowerShell バイナリを展開できますが、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57429-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<span data-ttu-id="57429-112">正式にサポートされているリリース</span><span class="sxs-lookup"><span data-stu-id="57429-112">Officially supported releases</span></span>

- <span data-ttu-id="57429-113">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="57429-113">Ubuntu 16.04</span></span>
- <span data-ttu-id="57429-114">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="57429-114">Ubuntu 18.04</span></span>
- <span data-ttu-id="57429-115">Debian 8</span><span class="sxs-lookup"><span data-stu-id="57429-115">Debian 8</span></span>
- <span data-ttu-id="57429-116">Debian 9</span><span class="sxs-lookup"><span data-stu-id="57429-116">Debian 9</span></span>
- <span data-ttu-id="57429-117">Debian 10</span><span class="sxs-lookup"><span data-stu-id="57429-117">Debian 10</span></span>
- <span data-ttu-id="57429-118">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="57429-118">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="57429-119">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="57429-119">CentOS 7</span></span>
- <span data-ttu-id="57429-120">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="57429-120">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="57429-121">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="57429-121">Fedora 28</span></span>
- <span data-ttu-id="57429-122">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="57429-122">Fedora 29</span></span>
- <span data-ttu-id="57429-123">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="57429-123">Fedora 30</span></span>
- <span data-ttu-id="57429-124">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="57429-124">openSUSE 42.3</span></span>
- <span data-ttu-id="57429-125">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="57429-125">openSUSE Leap 15</span></span>

<span data-ttu-id="57429-126">コミュニティでサポートされているリリース</span><span class="sxs-lookup"><span data-stu-id="57429-126">Community supported releases</span></span>

- <span data-ttu-id="57429-127">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="57429-127">Ubuntu 18.10</span></span>
- <span data-ttu-id="57429-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="57429-128">Ubuntu 19.04</span></span>
- <span data-ttu-id="57429-129">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="57429-129">Arch Linux</span></span>
- <span data-ttu-id="57429-130">Kali</span><span class="sxs-lookup"><span data-stu-id="57429-130">Kali</span></span>
- <span data-ttu-id="57429-131">Raspbian (試験段階)</span><span class="sxs-lookup"><span data-stu-id="57429-131">Raspbian (experimental)</span></span>

<span data-ttu-id="57429-132">代替のインストール方法</span><span class="sxs-lookup"><span data-stu-id="57429-132">Alternate install methods</span></span>

- <span data-ttu-id="57429-133">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="57429-133">Snap Package</span></span>
- <span data-ttu-id="57429-134">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="57429-134">Binary Archives</span></span>
- <span data-ttu-id="57429-135">.NET グローバル ツール</span><span class="sxs-lookup"><span data-stu-id="57429-135">.NET Global tool</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="57429-136">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="57429-136">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="57429-137">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="57429-137">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="57429-138">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="57429-138">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="57429-139">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57429-139">The preferred method is as follows:</span></span>

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="57429-140">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="57429-140">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="57429-141">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="57429-141">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="57429-142">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="57429-142">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="57429-143">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="57429-143">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="57429-144">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-144">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="57429-145">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="57429-145">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="57429-146">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="57429-146">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="57429-147">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="57429-147">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="57429-148">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="57429-148">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="57429-149">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="57429-149">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="57429-150">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="57429-150">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="57429-151">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57429-151">The preferred method is as follows:</span></span>

```sh
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

<span data-ttu-id="57429-152">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="57429-152">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="57429-153">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="57429-153">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="57429-154">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="57429-154">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="57429-155">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="57429-155">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="57429-156">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-156">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="57429-157">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="57429-157">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="57429-158">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="57429-158">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="57429-159">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="57429-159">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="57429-160">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="57429-160">Ubuntu 18.10</span></span>

<span data-ttu-id="57429-161">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="57429-161">Installation is supported via `snapd`.</span></span> <span data-ttu-id="57429-162">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="57429-162">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="57429-163">Ubuntu 18.10 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="57429-163">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="57429-164">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="57429-164">Ubuntu 19.04</span></span>

<span data-ttu-id="57429-165">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="57429-165">Installation is supported via `snapd`.</span></span> <span data-ttu-id="57429-166">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="57429-166">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="57429-167">Ubuntu 19.04 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="57429-167">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="57429-168">Debian 8</span><span class="sxs-lookup"><span data-stu-id="57429-168">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="57429-169">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="57429-169">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="57429-170">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="57429-170">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="57429-171">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57429-171">The preferred method is as follows:</span></span>

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

<span data-ttu-id="57429-172">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="57429-172">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="57429-173">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="57429-173">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="57429-174">Debian 9</span><span class="sxs-lookup"><span data-stu-id="57429-174">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="57429-175">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="57429-175">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="57429-176">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="57429-176">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="57429-177">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57429-177">The preferred method is as follows:</span></span>

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

<span data-ttu-id="57429-178">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="57429-178">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="57429-179">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="57429-179">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="57429-180">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="57429-180">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="57429-181">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell-lts_7.0.0-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="57429-181">Download the Debian package `powershell-lts_7.0.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="57429-182">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-182">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="57429-183">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="57429-183">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="57429-184">Debian 10</span><span class="sxs-lookup"><span data-stu-id="57429-184">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="57429-185">Debian 10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="57429-185">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="57429-186">パッケージ リポジトリによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="57429-186">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="57429-187">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="57429-187">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="57429-188">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57429-188">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="57429-189">直接ダウンロードによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="57429-189">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="57429-190">[リリース][] ページから Debian コンピューターに tar.gz パッケージ `powershell_7.0.0-linux-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="57429-190">Download the tar.gz package `powershell_7.0.0-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="57429-191">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-191">Then, in the terminal, execute the following commands:</span></span>

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
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="57429-192">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="57429-192">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="57429-193">Alpine 3.9 および 3.10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="57429-193">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="57429-194">直接ダウンロードによるインストール - Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="57429-194">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="57429-195">[リリース][] ページから Alpine コンピューターに tar.gz パッケージ `powershell-7.0.0-linux-alpine-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="57429-195">Download the tar.gz package `powershell-7.0.0-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="57429-196">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-196">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="centos-7"></a><span data-ttu-id="57429-197">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="57429-197">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="57429-198">このパッケージは Oracle Linux 7 で動作します。</span><span class="sxs-lookup"><span data-stu-id="57429-198">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="57429-199">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="57429-199">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="57429-200">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="57429-200">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="57429-201">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="57429-201">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="57429-202">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="57429-202">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="57429-203">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="57429-203">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="57429-204">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="57429-204">Using [CentOS 7][], download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="57429-205">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-205">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="57429-206">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="57429-206">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="57429-207">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="57429-207">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="57429-209">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="57429-209">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="57429-210">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="57429-210">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="57429-211">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="57429-211">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="57429-212">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="57429-212">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="57429-213">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="57429-213">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="57429-214">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="57429-214">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="57429-215">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="57429-215">Download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="57429-216">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-216">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="57429-217">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="57429-217">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="57429-218">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="57429-218">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="57429-219">openSUSE</span><span class="sxs-lookup"><span data-stu-id="57429-219">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="57429-220">インストール - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="57429-220">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="57429-221">インストール - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="57429-221">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="57429-222">アンインストール - openSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="57429-222">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="57429-223">Fedora</span><span class="sxs-lookup"><span data-stu-id="57429-223">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="57429-224">Fedora 28 は、PowerShell 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="57429-224">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="57429-225">Fedora 29 および 30 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="57429-225">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="57429-226">パッケージ リポジトリによるインストール (推奨) - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="57429-226">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="57429-227">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="57429-227">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf update

# Install a system component
sudo dnf install compat-openssl10

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="57429-228">直接ダウンロードによるインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="57429-228">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="57429-229">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-7.0.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="57429-229">Download the RPM package `powershell-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="57429-230">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57429-230">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="57429-231">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="57429-231">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="57429-232">アンインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="57429-232">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="57429-233">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="57429-233">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="57429-234">Arch のサポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="57429-234">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="57429-235">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="57429-235">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="57429-236">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="57429-236">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="57429-237">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="57429-237">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="57429-238">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="57429-238">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="57429-239">AUR のパッケージはコミュニティによって管理されています。公式のサポートは存在しません。</span><span class="sxs-lookup"><span data-stu-id="57429-239">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="57429-240">AUR からパッケージをインストールする方法については、[Arch Linux の wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) か「[Docker での PowerShell の使用](powershell-in-docker.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57429-240">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="57429-242">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="57429-242">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="57429-243">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="57429-243">Getting snapd</span></span>

<span data-ttu-id="57429-244">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="57429-244">`snapd` is required to run snaps.</span></span> <span data-ttu-id="57429-245">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="57429-245">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="57429-246">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="57429-246">Installation via Snap</span></span>

<span data-ttu-id="57429-247">Linux 向けの PowerShell は、インストールと更新を容易にするために [Snap ストア](https://snapcraft.io/store)に公開されています。</span><span class="sxs-lookup"><span data-stu-id="57429-247">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="57429-248">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57429-248">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="57429-249">プレビュー バージョンをインストールするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="57429-249">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="57429-250">インストールしたら、Snap は自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="57429-250">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="57429-251">`sudo snap refresh powershell` または `sudo snap refresh powershell-preview` を使って、アップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="57429-251">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="57429-252">アンインストール</span><span class="sxs-lookup"><span data-stu-id="57429-252">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="57429-253">or</span><span class="sxs-lookup"><span data-stu-id="57429-253">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="57429-254">Kali</span><span class="sxs-lookup"><span data-stu-id="57429-254">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="57429-255">Kali サポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="57429-255">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="57429-256">インストール - Kali</span><span class="sxs-lookup"><span data-stu-id="57429-256">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="57429-257">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="57429-257">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="57429-258">Raspbian</span><span class="sxs-lookup"><span data-stu-id="57429-258">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="57429-259">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="57429-259">Raspbian support is experimental.</span></span>

<span data-ttu-id="57429-260">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="57429-260">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="57429-261">CoreCLR と PowerShell は、Pi 2 および Pi 3 デバイス上でのみ動作します。[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスには、サポート外のプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="57429-261">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="57429-262">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="57429-262">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="57429-263">インストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="57429-263">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.0.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="57429-264">必要に応じて、`pwsh` バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="57429-264">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="57429-265">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="57429-265">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="57429-266">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="57429-266">Installing Preview Releases</span></span>

<span data-ttu-id="57429-267">パッケージ リポジトリを介して、Linux 用の PowerShell Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="57429-267">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="57429-268">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="57429-268">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="57429-269">さまざまなパッケージ マネージャーを使用して安定版およびプレビュー版パッケージをインストールするためのコマンドを、以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="57429-269">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="57429-270">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="57429-270">Distribution(s)</span></span> |            <span data-ttu-id="57429-271">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="57429-271">Stable Command</span></span>            |               <span data-ttu-id="57429-272">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="57429-272">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="57429-273">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="57429-273">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="57429-274">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="57429-274">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="57429-275">Fedora</span><span class="sxs-lookup"><span data-stu-id="57429-275">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="57429-276">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="57429-276">Install as a .NET Global tool</span></span>

<span data-ttu-id="57429-277">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="57429-277">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="57429-278">dotnet tool install によって、`PATH` 環境変数に `~/.dotnet/tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="57429-278">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="57429-279">ただし、現在実行中のシェルには更新された `PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="57429-279">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="57429-280">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できるはずです。</span><span class="sxs-lookup"><span data-stu-id="57429-280">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="57429-281">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="57429-281">Binary Archives</span></span>

<span data-ttu-id="57429-282">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="57429-282">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="57429-283">依存関係</span><span class="sxs-lookup"><span data-stu-id="57429-283">Dependencies</span></span>

<span data-ttu-id="57429-284">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="57429-284">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="57429-285">ただし、.NET Core ランタイムにはディストリビューションごとに異なる依存関係が必要であり、PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="57429-285">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="57429-286">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="57429-286">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="57429-287">OS</span><span class="sxs-lookup"><span data-stu-id="57429-287">OS</span></span>                 | <span data-ttu-id="57429-288">依存関係</span><span class="sxs-lookup"><span data-stu-id="57429-288">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="57429-289">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="57429-289">Ubuntu 16.04</span></span>       | <span data-ttu-id="57429-290">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="57429-290">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="57429-291">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="57429-291">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="57429-292">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="57429-292">Ubuntu 17.10</span></span>       | <span data-ttu-id="57429-293">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="57429-293">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="57429-294">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="57429-294">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="57429-295">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="57429-295">Ubuntu 18.04</span></span>       | <span data-ttu-id="57429-296">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="57429-296">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="57429-297">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="57429-297">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="57429-298">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="57429-298">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="57429-299">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="57429-299">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="57429-300">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="57429-300">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="57429-301">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="57429-301">Debian 9 (Stretch)</span></span> | <span data-ttu-id="57429-302">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="57429-302">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="57429-303">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="57429-303">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="57429-304">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="57429-304">CentOS 7</span></span> <br> <span data-ttu-id="57429-305">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="57429-305">Oracle Linux 7</span></span> <br> <span data-ttu-id="57429-306">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="57429-306">RHEL 7</span></span> | <span data-ttu-id="57429-307">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="57429-307">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="57429-308">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="57429-308">openSUSE 42.3</span></span> | <span data-ttu-id="57429-309">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="57429-309">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="57429-310">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="57429-310">openSUSE Leap 15</span></span> | <span data-ttu-id="57429-311">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="57429-311">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="57429-312">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="57429-312">Fedora 27</span></span> <br> <span data-ttu-id="57429-313">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="57429-313">Fedora 28</span></span> | <span data-ttu-id="57429-314">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="57429-314">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="57429-315">公式にサポートされていない Linux ディストリビューションに PowerShell バイナリを展開するには、別の手順によってターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="57429-315">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="57429-316">たとえば、[Amazon Linux Dockerfile][amazon-dockerfile] では依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="57429-316">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="57429-317">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="57429-317">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="57429-318">Linux</span><span class="sxs-lookup"><span data-stu-id="57429-318">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="57429-319">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="57429-319">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="57429-320">パス</span><span class="sxs-lookup"><span data-stu-id="57429-320">Paths</span></span>

- <span data-ttu-id="57429-321">`$PSHOME` は `/opt/microsoft/powershell/7/` です</span><span class="sxs-lookup"><span data-stu-id="57429-321">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="57429-322">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="57429-322">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="57429-323">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="57429-323">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="57429-324">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="57429-324">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="57429-325">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="57429-325">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="57429-326">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="57429-326">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="57429-327">PSReadLine 履歴は、`~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="57429-327">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="57429-328">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="57429-328">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="57429-329">PowerShell では、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="57429-329">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
