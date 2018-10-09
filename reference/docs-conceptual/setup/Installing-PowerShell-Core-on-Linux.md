---
title: Linux への PowerShell Core のインストール
description: さまざまな Linux ディストリビューションへの PowerShell Core のインストールに関する情報
ms.date: 08/06/2018
ms.openlocfilehash: d60e1d5a89b6907b67c19b8cfcde969be156bd60
ms.sourcegitcommit: 6749f67c32e05999e10deb9d45f90f45ac21a599
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48851291"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="c513f-103">Linux への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="c513f-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="c513f-104">[Ubuntu 14.04][u14]、[Ubuntu 16.04][u16]、[Ubuntu 18.10][u18]、[Debian 8][deb8]、[Debian 9][deb9]、[CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[OpenSUSE 42.3][opensuse]、[Fedora 27][fedora]、[Fedora 28][fedora]、[Arch Linux][arch] をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c513f-104">Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 18.10][u18], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [OpenSUSE 42.3][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="c513f-105">公式にサポートしていない Linux ディストリビューションの場合、[PowerShell Snap パッケージ][snap]を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c513f-105">For Linux distributions that are not officially supported, you can try using the [PowerShell Snap Package][snap].</span></span>
<span data-ttu-id="c513f-106">また、Linux [`tar.gz` アーカイブ][tar]で直接、PowerShell バイナリを展開できます。ただし、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c513f-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="c513f-107">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="c513f-107">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="c513f-108">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="c513f-108">Once the package is installed, run `pwsh` from a terminal.</span></span>

[u14]: #ubuntu-1404
[u16]: #ubuntu-1604
[u18]: #ubuntu-1810
[u18]: #ubuntu-1804
[deb8]: #debian-8
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse-423
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives

## <a name="installing-preview-releases"></a><span data-ttu-id="c513f-109">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="c513f-109">Installing Preview Releases</span></span>

<span data-ttu-id="c513f-110">パッケージ リポジトリを介して、Linux 用の PowerShell Core Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="c513f-110">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="c513f-111">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="c513f-111">Installing via direct download does not change, other than the file name.</span></span>

<span data-ttu-id="c513f-112">さまざまなパッケージ マネージャーを使用して、安定したパッケージとプレビュー パッケージをインストールするためのコマンドを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c513f-112">Here is a table of the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="c513f-113">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="c513f-113">Distribution(s)</span></span>|<span data-ttu-id="c513f-114">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="c513f-114">Stable Command</span></span> | <span data-ttu-id="c513f-115">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="c513f-115">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="c513f-116">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="c513f-116">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="c513f-117">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="c513f-117">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="c513f-118">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="c513f-118">OpenSUSE</span></span> |`sudo zypper install powershell` | `sudo zypper install powershell-preview`|
| <span data-ttu-id="c513f-119">Fedora</span><span class="sxs-lookup"><span data-stu-id="c513f-119">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1404"></a><span data-ttu-id="c513f-120">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="c513f-120">Ubuntu 14.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1404"></a><span data-ttu-id="c513f-121">パッケージ リポジトリによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="c513f-121">Installation via Package Repository - Ubuntu 14.04</span></span>

<span data-ttu-id="c513f-122">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-122">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="c513f-123">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c513f-123">This is the preferred method.</span></span>

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/14.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="c513f-124">スーパーユーザーとして Microsoft リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="c513f-124">As superuser, register the Microsoft repository.</span></span>
<span data-ttu-id="c513f-125">以降は、インストールの更新に `sudo apt-get upgrade powershell` を使用するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="c513f-125">From then on, you just need to use `sudo apt-get upgrade powershell` to update the installation.</span></span>

### <a name="installation-via-direct-download---ubuntu-1404"></a><span data-ttu-id="c513f-126">直接ダウンロードによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="c513f-126">Installation via Direct Download - Ubuntu 14.04</span></span>

<span data-ttu-id="c513f-127">Debian パッケージ `powershell_6.1.0-1.ubuntu.14.04_amd64.deb` を</span><span class="sxs-lookup"><span data-stu-id="c513f-127">Download the Debian package `powershell_6.1.0-1.ubuntu.14.04_amd64.deb`</span></span>
<span data-ttu-id="c513f-128">[リリース][] ページから Ubuntu コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c513f-128">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="c513f-129">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c513f-129">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="c513f-130">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="c513f-130">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="c513f-131">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="c513f-131">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1404"></a><span data-ttu-id="c513f-132">アンインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="c513f-132">Uninstallation - Ubuntu 14.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a><span data-ttu-id="c513f-133">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="c513f-133">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="c513f-134">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="c513f-134">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="c513f-135">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-135">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="c513f-136">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c513f-136">This is the preferred method.</span></span>

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

<span data-ttu-id="c513f-137">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c513f-137">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="c513f-138">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="c513f-138">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="c513f-139">Debian パッケージ `powershell_6.1.0-1.ubuntu.16.04_amd64.deb` を</span><span class="sxs-lookup"><span data-stu-id="c513f-139">Download the Debian package `powershell_6.1.0-1.ubuntu.16.04_amd64.deb`</span></span>
<span data-ttu-id="c513f-140">[リリース][] ページから Ubuntu コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c513f-140">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="c513f-141">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c513f-141">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="c513f-142">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="c513f-142">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="c513f-143">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="c513f-143">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="c513f-144">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="c513f-144">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="c513f-145">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="c513f-145">Ubuntu 18.04</span></span>

> [!NOTE]
> <span data-ttu-id="c513f-146">Ubuntu 18.04 のサポートは `6.1.0-preview.2` 以降に追加されました。</span><span class="sxs-lookup"><span data-stu-id="c513f-146">Support for Ubuntu 18.04 was added after `6.1.0-preview.2`</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="c513f-147">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="c513f-147">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="c513f-148">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-148">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="c513f-149">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c513f-149">This is the preferred method.</span></span>

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="c513f-150">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c513f-150">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="c513f-151">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="c513f-151">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="c513f-152">Debian パッケージ `powershell_6.1.0-1.ubuntu.18.04_amd64.deb` を</span><span class="sxs-lookup"><span data-stu-id="c513f-152">Download the Debian package `powershell_6.1.0-1.ubuntu.18.04_amd64.deb`</span></span>
<span data-ttu-id="c513f-153">[リリース][] ページから Ubuntu コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c513f-153">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="c513f-154">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c513f-154">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="c513f-155">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="c513f-155">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="c513f-156">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="c513f-156">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="c513f-157">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="c513f-157">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="c513f-158">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="c513f-158">Ubuntu 18.10</span></span>

> [!NOTE]
> <span data-ttu-id="c513f-159">Ubuntu 18.10 のサポートは `6.1.0-preview.3` 以降に追加されました。</span><span class="sxs-lookup"><span data-stu-id="c513f-159">Support for Ubuntu 18.10 was added after `6.1.0-preview.3`.</span></span>
> <span data-ttu-id="c513f-160">18.10 はデイリー ビルドであるため、コミュニティのサポートのみです。</span><span class="sxs-lookup"><span data-stu-id="c513f-160">As 18.10 is a daily build, it is only community supported.</span></span>

<span data-ttu-id="c513f-161">18.10 へのインストールは `snapd` を使用してサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c513f-161">Installing on 18.10 is supported via `snapd`.</span></span> <span data-ttu-id="c513f-162">完全な手順については、「[Snap パッケージ][snap]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c513f-162">See [Snap Package][snap] for full instructions;</span></span>

## <a name="debian-8"></a><span data-ttu-id="c513f-163">Debian 8</span><span class="sxs-lookup"><span data-stu-id="c513f-163">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="c513f-164">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="c513f-164">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="c513f-165">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-165">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="c513f-166">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c513f-166">This is the preferred method.</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install curl apt-transport-https

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

<span data-ttu-id="c513f-167">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c513f-167">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-8"></a><span data-ttu-id="c513f-168">直接ダウンロードによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="c513f-168">Installation via Direct Download - Debian 8</span></span>

<span data-ttu-id="c513f-169">Debian パッケージ `powershell_6.1.0-1.debian.8_amd64.deb` を</span><span class="sxs-lookup"><span data-stu-id="c513f-169">Download the Debian package `powershell_6.1.0-1.debian.8_amd64.deb`</span></span>
<span data-ttu-id="c513f-170">[リリース][] ページから Debian コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c513f-170">from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="c513f-171">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c513f-171">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.debian.8_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="c513f-172">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="c513f-172">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="c513f-173">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="c513f-173">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---debian-8"></a><span data-ttu-id="c513f-174">アンインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="c513f-174">Uninstallation - Debian 8</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-9"></a><span data-ttu-id="c513f-175">Debian 9</span><span class="sxs-lookup"><span data-stu-id="c513f-175">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="c513f-176">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="c513f-176">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="c513f-177">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-177">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="c513f-178">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c513f-178">This is the preferred method.</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install curl gnupg apt-transport-https

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

<span data-ttu-id="c513f-179">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c513f-179">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="c513f-180">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="c513f-180">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="c513f-181">Debian パッケージ `powershell_6.1.0-1.debian.9_amd64.deb` を</span><span class="sxs-lookup"><span data-stu-id="c513f-181">Download the Debian package `powershell_6.1.0-1.debian.9_amd64.deb`</span></span>
<span data-ttu-id="c513f-182">[リリース][] ページから Debian コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c513f-182">from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="c513f-183">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c513f-183">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="c513f-184">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="c513f-184">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="c513f-185">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="c513f-185">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="c513f-186">このパッケージは Oracle Linux 7 でも動作します。</span><span class="sxs-lookup"><span data-stu-id="c513f-186">This package also works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="c513f-187">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="c513f-187">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="c513f-188">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-188">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="c513f-189">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c513f-189">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="c513f-190">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="c513f-190">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="c513f-191">[CentOS 7][] を使用して、RPM パッケージ `powershell-6.1.0-1.rhel.7.x86_64.rpm` を</span><span class="sxs-lookup"><span data-stu-id="c513f-191">Using [CentOS 7][], download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span></span>
<span data-ttu-id="c513f-192">[リリース][] ページから CentOS コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c513f-192">from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="c513f-193">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c513f-193">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="c513f-194">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c513f-194">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="c513f-195">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="c513f-195">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="c513f-197">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="c513f-197">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="c513f-198">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="c513f-198">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="c513f-199">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-199">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="c513f-200">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c513f-200">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="c513f-201">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="c513f-201">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="c513f-202">RPM パッケージ `powershell-6.1.0-1.rhel.7.x86_64.rpm` を</span><span class="sxs-lookup"><span data-stu-id="c513f-202">Download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span></span>
<span data-ttu-id="c513f-203">[リリース][] ページから Red Hat Enterprise Linux コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c513f-203">from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="c513f-204">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c513f-204">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="c513f-205">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c513f-205">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="c513f-206">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="c513f-206">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse-423"></a><span data-ttu-id="c513f-207">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="c513f-207">OpenSUSE 42.3</span></span>

<span data-ttu-id="c513f-208">PowerShell Core をインストールすると、`zypper` から次のエラーが報告されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c513f-208">When installing PowerShell Core, `zypper` may report the following error:</span></span>

```Output
Problem: nothing provides libcurl needed by powershell-6.1.0-1.rhel.7.x86_64
 Solution 1: do not install powershell-6.1.0-1.rhel.7.x86_64
 Solution 2: break powershell-6.1.0-1.rhel.7.x86_64 by ignoring some of its dependencies
```

<span data-ttu-id="c513f-209">この場合、次のコマンドで `libcurl4` パッケージがインストール済みであることを確認して、互換性のある `libcurl` ライブラリが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c513f-209">In this case, verify that a compatible `libcurl` library is present by checking that the following command shows the `libcurl4` package as installed:</span></span>

```sh
zypper search --file-list --match-exact '/usr/lib64/libcurl.so.4'
```

<span data-ttu-id="c513f-210">次に、PowerShell パッケージをインストールするときに `break powershell-6.1.0-1.rhel.7.x86_64 by ignoring some of its dependencies` ソリューションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c513f-210">Then choose the `break powershell-6.1.0-1.rhel.7.x86_64 by ignoring some of its dependencies` solution when installing the PowerShell package.</span></span>

### <a name="installation-via-package-repository-preferred---opensuse-423"></a><span data-ttu-id="c513f-211">パッケージ リポジトリによるインストール (推奨) - OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="c513f-211">Installation via Package Repository (preferred) - OpenSUSE 42.3</span></span>

<span data-ttu-id="c513f-212">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-212">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Add the Microsoft Repository
zypper ar https://packages.microsoft.com/rhel/7/prod/

# Update the list of products
sudo zypper update

# Install PowerShell
sudo zypper install powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---opensuse-423"></a><span data-ttu-id="c513f-213">直接ダウンロードによるインストール - OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="c513f-213">Installation via Direct Download - OpenSUSE 42.3</span></span>

<span data-ttu-id="c513f-214">[リリース][] ページから OpenSUSE コンピューターに RPM パッケージ `powershell-6.1.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c513f-214">Download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the OpenSUSE machine.</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="c513f-215">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c513f-215">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---opensuse-423"></a><span data-ttu-id="c513f-216">アンインストール - OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="c513f-216">Uninstallation - OpenSUSE 42.3</span></span>

```sh
sudo zypper remove powershell
```

## <a name="fedora"></a><span data-ttu-id="c513f-217">Fedora</span><span class="sxs-lookup"><span data-stu-id="c513f-217">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="c513f-218">Fedora 28 は、PowerShell Core 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c513f-218">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a><span data-ttu-id="c513f-219">パッケージ リポジトリによるインストール (推奨) - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="c513f-219">Installation via Package Repository (preferred) - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="c513f-220">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-220">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a><span data-ttu-id="c513f-221">直接ダウンロードによるインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="c513f-221">Installation via Direct Download - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="c513f-222">RPM パッケージ `powershell-6.1.0-1.rhel.7.x86_64.rpm` を</span><span class="sxs-lookup"><span data-stu-id="c513f-222">Download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span></span>
<span data-ttu-id="c513f-223">[リリース][] ページから Fedora コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c513f-223">from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="c513f-224">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c513f-224">Then execute the following in the terminal:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="c513f-225">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c513f-225">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a><span data-ttu-id="c513f-226">アンインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="c513f-226">Uninstallation - Fedora 27, Fedora 28</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="c513f-227">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="c513f-227">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="c513f-228">Arch のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="c513f-228">Arch support is experimental.</span></span>

<span data-ttu-id="c513f-229">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="c513f-229">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="c513f-230">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="c513f-230">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="c513f-231">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="c513f-231">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="c513f-232">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="c513f-232">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="c513f-233">AUR のパッケージはコミュニティにより保守管理されています。公式のサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="c513f-233">Packages in the AUR are community maintained - there is no official support.</span></span>

<span data-ttu-id="c513f-234">AUR からパッケージをインストールする方法については、[Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) かコミュニティ [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c513f-234">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="c513f-236">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="c513f-236">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="c513f-237">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="c513f-237">Getting snapd</span></span>

<span data-ttu-id="c513f-238">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="c513f-238">`snapd` is required to run snaps.</span></span>
<span data-ttu-id="c513f-239">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c513f-239">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="c513f-240">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="c513f-240">Installation via Snap</span></span>

<span data-ttu-id="c513f-241">Linux 向け PowerShell Core は [Snap ストア](https://snapcraft.io/store)に公開されるため、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c513f-241">PowerShell Core, for Linux, is published to the [Snap store](https://snapcraft.io/store) for easy installation (and updates).</span></span>
<span data-ttu-id="c513f-242">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c513f-242">This is the preferred method.</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="c513f-243">Snap のインストールが自動的にアップグレードされた後も、`sudo snap refresh powershell-preview` を使用してアップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="c513f-243">After installing Snap will automatically upgrade, but you can trigger an upgrade using `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="c513f-244">アンインストール</span><span class="sxs-lookup"><span data-stu-id="c513f-244">Uninstallation</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="c513f-245">Kali</span><span class="sxs-lookup"><span data-stu-id="c513f-245">Kali</span></span>

### <a name="installation"></a><span data-ttu-id="c513f-246">インストール</span><span class="sxs-lookup"><span data-stu-id="c513f-246">Installation</span></span>

```sh
# Download & Install prerequisites
wget http://ftp.us.debian.org/debian/pool/main/i/icu/libicu57_57.1-9_amd64.deb
dpkg -i libicu57_57.1-9_amd64.deb
apt-get update && apt-get install -y curl gnupg apt-transport-https

# Add Microsoft public repository key to APT
curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -

# Add Microsoft package repository to the source list
echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" | tee /etc/apt/sources.list.d/powershell.list

# Install PowerShell package
apt-get update && apt-get install -y powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="c513f-247">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="c513f-247">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="c513f-248">Raspbian</span><span class="sxs-lookup"><span data-stu-id="c513f-248">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="c513f-249">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="c513f-249">Raspbian support is experimental.</span></span>

<span data-ttu-id="c513f-250">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c513f-250">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="c513f-251">また、Core CLR (と PowerShell Core) は Pi 2 および Pi 3 デバイス上でのみ動作します。これは、[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスにはサポートされていないプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="c513f-251">Also CoreCLR (and thus PowerShell Core) will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="c513f-252">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="c513f-252">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation"></a><span data-ttu-id="c513f-253">インストール</span><span class="sxs-lookup"><span data-stu-id="c513f-253">Installation</span></span>

```sh
# Install prerequisites
sudo apt-get install libunwind8

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.1.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="c513f-254">必要に応じて、"pwsh" バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="c513f-254">Optionally you can create a symbolic link to be able to start PowerShell without specifying path to the "pwsh" binary</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="c513f-255">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="c513f-255">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="c513f-256">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="c513f-256">Binary Archives</span></span>

<span data-ttu-id="c513f-257">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c513f-257">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="c513f-258">依存関係</span><span class="sxs-lookup"><span data-stu-id="c513f-258">Dependencies</span></span>

<span data-ttu-id="c513f-259">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="c513f-259">PowerShell builds portable binaries for all Linux distributions.</span></span>
<span data-ttu-id="c513f-260">ただし、.NET Core ランタイムはディストリビューションごとに異なる依存関係を必要とします。PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="c513f-260">But .NET Core runtime requires different dependencies on different distributions, and hence PowerShell does the same.</span></span>

<span data-ttu-id="c513f-261">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="c513f-261">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="c513f-262">OS</span><span class="sxs-lookup"><span data-stu-id="c513f-262">OS</span></span>                 | <span data-ttu-id="c513f-263">依存関係</span><span class="sxs-lookup"><span data-stu-id="c513f-263">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="c513f-264">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="c513f-264">Ubuntu 14.04</span></span>       | <span data-ttu-id="c513f-265">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="c513f-265">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="c513f-266">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="c513f-266">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="c513f-267">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="c513f-267">Ubuntu 16.04</span></span>       | <span data-ttu-id="c513f-268">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="c513f-268">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="c513f-269">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="c513f-269">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="c513f-270">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="c513f-270">Ubuntu 17.10</span></span>       | <span data-ttu-id="c513f-271">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="c513f-271">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="c513f-272">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="c513f-272">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="c513f-273">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="c513f-273">Ubuntu 18.04</span></span>       | <span data-ttu-id="c513f-274">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="c513f-274">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="c513f-275">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="c513f-275">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="c513f-276">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="c513f-276">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="c513f-277">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="c513f-277">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="c513f-278">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="c513f-278">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="c513f-279">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="c513f-279">Debian 9 (Stretch)</span></span> | <span data-ttu-id="c513f-280">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="c513f-280">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="c513f-281">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="c513f-281">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="c513f-282">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="c513f-282">CentOS 7</span></span> <br> <span data-ttu-id="c513f-283">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="c513f-283">Oracle Linux 7</span></span> <br> <span data-ttu-id="c513f-284">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="c513f-284">RHEL 7</span></span> <br> <span data-ttu-id="c513f-285">OpenSUSE OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="c513f-285">OpenSUSE OpenSUSE 42.3</span></span> | <span data-ttu-id="c513f-286">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="c513f-286">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="c513f-287">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="c513f-287">Fedora 27</span></span> <br> <span data-ttu-id="c513f-288">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="c513f-288">Fedora 28</span></span> | <span data-ttu-id="c513f-289">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="c513f-289">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="c513f-290">公式にサポートされていない Linux ディストリビューションで PowerShell バイナリを展開するには、別の手順で、ターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c513f-290">To deploy PowerShell binaries on Linux distributions that are not officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span>
<span data-ttu-id="c513f-291">たとえば、[Amazon Linux dockerfile][amazon-dockerfile] は依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c513f-291">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell/blob/master/docker/community/amazonlinux/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="c513f-292">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="c513f-292">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="c513f-293">Linux</span><span class="sxs-lookup"><span data-stu-id="c513f-293">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/6.1.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.1.0

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/6.1.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/6.1.0/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="c513f-294">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="c513f-294">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="c513f-295">パス</span><span class="sxs-lookup"><span data-stu-id="c513f-295">Paths</span></span>

* <span data-ttu-id="c513f-296">`$PSHOME` は `/opt/microsoft/powershell/6.1.0/` です</span><span class="sxs-lookup"><span data-stu-id="c513f-296">`$PSHOME` is `/opt/microsoft/powershell/6.1.0/`</span></span>
* <span data-ttu-id="c513f-297">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="c513f-297">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="c513f-298">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="c513f-298">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="c513f-299">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="c513f-299">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="c513f-300">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="c513f-300">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="c513f-301">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="c513f-301">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="c513f-302">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="c513f-302">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="c513f-303">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="c513f-303">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="c513f-304">PowerShell は、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="c513f-304">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
