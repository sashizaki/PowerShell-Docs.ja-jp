---
title: Linux への PowerShell Core のインストール
description: さまざまな Linux ディストリビューションへの PowerShell Core のインストールに関する情報
ms.date: 08/06/2018
ms.openlocfilehash: 06194550f4e73f9dd38f8cdc25f6c7f698cafce2
ms.sourcegitcommit: 806cf87488b80800b9f50a8af286e8379519a034
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59293335"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="112b1-103">Linux への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="112b1-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="112b1-104">[Ubuntu 14.04][u14]、[Ubuntu 16.04][u16]、[Ubuntu 18.04][u1804]、[Ubuntu 18.10][u1810]、[Debian 9][deb9]、[CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[openSUSE 42.3][opensuse]、[openSUSE Leap 15][opensuse]、[Fedora 27][fedora]、[Fedora 28][fedora]、および [Arch Linux][arch] をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="112b1-104">Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810],  [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="112b1-105">公式にサポートしていない Linux ディストリビューションの場合、[PowerShell Snap パッケージ][snap]を利用できます。</span><span class="sxs-lookup"><span data-stu-id="112b1-105">For Linux distributions that are not officially supported, you can try using the [PowerShell Snap Package][snap].</span></span>
<span data-ttu-id="112b1-106">また、Linux [`tar.gz` アーカイブ][tar]で直接、PowerShell バイナリを展開できます。ただし、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112b1-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="112b1-107">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="112b1-107">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="112b1-108">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="112b1-108">Once the package is installed, run `pwsh` from a terminal.</span></span>

[u14]: #ubuntu-1404
[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives

## <a name="installing-preview-releases"></a><span data-ttu-id="112b1-109">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="112b1-109">Installing Preview Releases</span></span>

<span data-ttu-id="112b1-110">パッケージ リポジトリを介して、Linux 用の PowerShell Core Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="112b1-110">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="112b1-111">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="112b1-111">Installing via direct download does not change, other than the file name.</span></span>

<span data-ttu-id="112b1-112">さまざまなパッケージ マネージャーを使用して、安定したパッケージとプレビュー パッケージをインストールするためのコマンドを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="112b1-112">Here is a table of the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="112b1-113">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="112b1-113">Distribution(s)</span></span>|<span data-ttu-id="112b1-114">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="112b1-114">Stable Command</span></span> | <span data-ttu-id="112b1-115">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="112b1-115">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="112b1-116">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="112b1-116">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="112b1-117">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="112b1-117">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="112b1-118">Fedora</span><span class="sxs-lookup"><span data-stu-id="112b1-118">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1404"></a><span data-ttu-id="112b1-119">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="112b1-119">Ubuntu 14.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1404"></a><span data-ttu-id="112b1-120">パッケージ リポジトリによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="112b1-120">Installation via Package Repository - Ubuntu 14.04</span></span>

<span data-ttu-id="112b1-121">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="112b1-121">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="112b1-122">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="112b1-122">This is the preferred method.</span></span>

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

<span data-ttu-id="112b1-123">スーパーユーザーとして Microsoft リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="112b1-123">As superuser, register the Microsoft repository.</span></span>
<span data-ttu-id="112b1-124">以降は、インストールの更新に `sudo apt-get upgrade powershell` を使用するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="112b1-124">From then on, you just need to use `sudo apt-get upgrade powershell` to update the installation.</span></span>

### <a name="installation-via-direct-download---ubuntu-1404"></a><span data-ttu-id="112b1-125">直接ダウンロードによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="112b1-125">Installation via Direct Download - Ubuntu 14.04</span></span>

<span data-ttu-id="112b1-126">Debian パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="112b1-126">Download the Debian package</span></span>
`powershell_6.2.0-1.ubuntu.14.04_amd64.deb`
<span data-ttu-id="112b1-127">[リリース][] ページから Ubuntu コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="112b1-127">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="112b1-128">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="112b1-128">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="112b1-129">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="112b1-129">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="112b1-130">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="112b1-130">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1404"></a><span data-ttu-id="112b1-131">アンインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="112b1-131">Uninstallation - Ubuntu 14.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a><span data-ttu-id="112b1-132">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="112b1-132">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="112b1-133">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="112b1-133">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="112b1-134">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="112b1-134">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="112b1-135">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="112b1-135">This is the preferred method.</span></span>

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

<span data-ttu-id="112b1-136">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="112b1-136">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="112b1-137">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="112b1-137">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="112b1-138">Debian パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="112b1-138">Download the Debian package</span></span>
`powershell_6.2.0-1.ubuntu.16.04_amd64.deb`
<span data-ttu-id="112b1-139">[リリース][] ページから Ubuntu コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="112b1-139">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="112b1-140">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="112b1-140">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="112b1-141">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="112b1-141">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="112b1-142">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="112b1-142">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="112b1-143">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="112b1-143">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="112b1-144">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="112b1-144">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="112b1-145">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="112b1-145">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="112b1-146">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="112b1-146">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="112b1-147">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="112b1-147">This is the preferred method.</span></span>

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

<span data-ttu-id="112b1-148">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="112b1-148">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="112b1-149">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="112b1-149">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="112b1-150">Debian パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="112b1-150">Download the Debian package</span></span>
`powershell_6.2.0-1.ubuntu.18.04_amd64.deb`
<span data-ttu-id="112b1-151">[リリース][] ページから Ubuntu コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="112b1-151">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="112b1-152">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="112b1-152">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="112b1-153">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="112b1-153">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="112b1-154">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="112b1-154">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="112b1-155">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="112b1-155">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="112b1-156">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="112b1-156">Ubuntu 18.10</span></span>

> [!NOTE]
> <span data-ttu-id="112b1-157">18.10 が[中間リリース](https://www.ubuntu.com/about/release-cycle)のときに、これは[コミュニティでのみサポートされます](https://docs.microsoft.com/en-us/powershell/scripting/powershell-support-lifecycle?view=powershell-6)。</span><span class="sxs-lookup"><span data-stu-id="112b1-157">As 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle), it is only [community supported](https://docs.microsoft.com/en-us/powershell/scripting/powershell-support-lifecycle?view=powershell-6).</span></span>

<span data-ttu-id="112b1-158">18.10 へのインストールは `snapd` を使用してサポートされます。</span><span class="sxs-lookup"><span data-stu-id="112b1-158">Installing on 18.10 is supported via `snapd`.</span></span> <span data-ttu-id="112b1-159">完全な手順については、「[Snap パッケージ][snap]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="112b1-159">See [Snap Package][snap] for full instructions;</span></span>

## <a name="debian-8"></a><span data-ttu-id="112b1-160">Debian 8</span><span class="sxs-lookup"><span data-stu-id="112b1-160">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="112b1-161">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="112b1-161">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="112b1-162">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="112b1-162">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="112b1-163">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="112b1-163">This is the preferred method.</span></span>

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

<span data-ttu-id="112b1-164">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="112b1-164">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

## <a name="debian-9"></a><span data-ttu-id="112b1-165">Debian 9</span><span class="sxs-lookup"><span data-stu-id="112b1-165">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="112b1-166">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="112b1-166">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="112b1-167">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="112b1-167">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="112b1-168">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="112b1-168">This is the preferred method.</span></span>

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

<span data-ttu-id="112b1-169">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="112b1-169">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="112b1-170">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="112b1-170">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="112b1-171">Debian パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="112b1-171">Download the Debian package</span></span>
`powershell_6.2.0-1.debian.9_amd64.deb`
<span data-ttu-id="112b1-172">[リリース][] ページから Debian コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="112b1-172">from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="112b1-173">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="112b1-173">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="112b1-174">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="112b1-174">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="112b1-175">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="112b1-175">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="112b1-176">このパッケージは Oracle Linux 7 でも動作します。</span><span class="sxs-lookup"><span data-stu-id="112b1-176">This package also works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="112b1-177">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="112b1-177">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="112b1-178">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="112b1-178">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="112b1-179">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="112b1-179">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="112b1-180">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="112b1-180">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="112b1-181">[CentOS 7][] を使用して、RPM パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="112b1-181">Using [CentOS 7][], download the RPM package</span></span>
`powershell-6.2.0-1.rhel.7.x86_64.rpm`
<span data-ttu-id="112b1-182">[リリース][] ページから CentOS コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="112b1-182">from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="112b1-183">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="112b1-183">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="112b1-184">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="112b1-184">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="112b1-185">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="112b1-185">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[<span data-ttu-id="112b1-186">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="112b1-186">CentOS 7</span></span>]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="112b1-187">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="112b1-187">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="112b1-188">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="112b1-188">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="112b1-189">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="112b1-189">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="112b1-190">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="112b1-190">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="112b1-191">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="112b1-191">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="112b1-192">RPM パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="112b1-192">Download the RPM package</span></span>
`powershell-6.2.0-1.rhel.7.x86_64.rpm`
<span data-ttu-id="112b1-193">[リリース][] ページから Red Hat Enterprise Linux コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="112b1-193">from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="112b1-194">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="112b1-194">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="112b1-195">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="112b1-195">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="112b1-196">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="112b1-196">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="112b1-197">openSUSE</span><span class="sxs-lookup"><span data-stu-id="112b1-197">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="112b1-198">インストール - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="112b1-198">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/6.2.0

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.2.0

# Set execute permissions
chmod +x /opt/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/6.2.0/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="112b1-199">インストール - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="112b1-199">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/6.2.0

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.2.0

# Set execute permissions
chmod +x /opt/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/6.2.0/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="112b1-200">アンインストール - openSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="112b1-200">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="112b1-201">Fedora</span><span class="sxs-lookup"><span data-stu-id="112b1-201">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="112b1-202">Fedora 28 は、PowerShell Core 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="112b1-202">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a><span data-ttu-id="112b1-203">パッケージ リポジトリによるインストール (推奨) - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="112b1-203">Installation via Package Repository (preferred) - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="112b1-204">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="112b1-204">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a><span data-ttu-id="112b1-205">直接ダウンロードによるインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="112b1-205">Installation via Direct Download - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="112b1-206">RPM パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="112b1-206">Download the RPM package</span></span>
`powershell-6.2.0-1.rhel.7.x86_64.rpm`
<span data-ttu-id="112b1-207">[リリース][] ページから Fedora コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="112b1-207">from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="112b1-208">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="112b1-208">Then execute the following in the terminal:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="112b1-209">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="112b1-209">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a><span data-ttu-id="112b1-210">アンインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="112b1-210">Uninstallation - Fedora 27, Fedora 28</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="112b1-211">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="112b1-211">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="112b1-212">Arch のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="112b1-212">Arch support is experimental.</span></span>

<span data-ttu-id="112b1-213">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="112b1-213">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="112b1-214">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="112b1-214">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="112b1-215">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="112b1-215">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="112b1-216">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="112b1-216">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="112b1-217">AUR のパッケージはコミュニティにより保守管理されています。公式のサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="112b1-217">Packages in the AUR are community maintained - there is no official support.</span></span>

<span data-ttu-id="112b1-218">AUR からパッケージをインストールする方法については、[Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) かコミュニティ [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="112b1-218">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[<span data-ttu-id="112b1-219">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="112b1-219">Arch Linux</span></span>]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="112b1-220">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="112b1-220">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="112b1-221">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="112b1-221">Getting snapd</span></span>

`snapd` <span data-ttu-id="112b1-222">が Snap を実行するために必要です。</span><span class="sxs-lookup"><span data-stu-id="112b1-222">is required to run snaps.</span></span>
<span data-ttu-id="112b1-223">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="112b1-223">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="112b1-224">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="112b1-224">Installation via Snap</span></span>

<span data-ttu-id="112b1-225">Linux 向け PowerShell Core は [Snap ストア](https://snapcraft.io/store)に公開されるため、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="112b1-225">PowerShell Core, for Linux, is published to the [Snap store](https://snapcraft.io/store) for easy installation (and updates).</span></span>
<span data-ttu-id="112b1-226">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="112b1-226">This is the preferred method.</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="112b1-227">プレビュー バージョンをインストールする場合は、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="112b1-227">If you want to install preview version, use following method.</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="112b1-228">Snap のインストールが自動的にアップグレードされた後も、`sudo snap refresh powershell` または `sudo snap refresh powershell-preview` を使用してアップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="112b1-228">After installing Snap will automatically upgrade, but you can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="112b1-229">アンインストール</span><span class="sxs-lookup"><span data-stu-id="112b1-229">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="112b1-230">または</span><span class="sxs-lookup"><span data-stu-id="112b1-230">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="112b1-231">Kali</span><span class="sxs-lookup"><span data-stu-id="112b1-231">Kali</span></span>

### <a name="installation---kali"></a><span data-ttu-id="112b1-232">インストール - Kali</span><span class="sxs-lookup"><span data-stu-id="112b1-232">Installation - Kali</span></span>

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

### <a name="uninstallation---kali"></a><span data-ttu-id="112b1-233">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="112b1-233">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="112b1-234">Raspbian</span><span class="sxs-lookup"><span data-stu-id="112b1-234">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="112b1-235">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="112b1-235">Raspbian support is experimental.</span></span>

<span data-ttu-id="112b1-236">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="112b1-236">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="112b1-237">また、Core CLR (と PowerShell Core) は Pi 2 および Pi 3 デバイス上でのみ動作します。これは、[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスにはサポートされていないプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="112b1-237">Also CoreCLR (and thus PowerShell Core) will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="112b1-238">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="112b1-238">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="112b1-239">インストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="112b1-239">Installation - Raspbian</span></span>

```sh
# Install prerequisites
sudo apt-get install libunwind8

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.2.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="112b1-240">必要に応じて、"pwsh" バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="112b1-240">Optionally you can create a symbolic link to be able to start PowerShell without specifying path to the "pwsh" binary</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="112b1-241">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="112b1-241">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="112b1-242">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="112b1-242">Binary Archives</span></span>

<span data-ttu-id="112b1-243">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="112b1-243">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="112b1-244">依存関係</span><span class="sxs-lookup"><span data-stu-id="112b1-244">Dependencies</span></span>

<span data-ttu-id="112b1-245">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="112b1-245">PowerShell builds portable binaries for all Linux distributions.</span></span>
<span data-ttu-id="112b1-246">ただし、.NET Core ランタイムはディストリビューションごとに異なる依存関係を必要とします。PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="112b1-246">But .NET Core runtime requires different dependencies on different distributions, and hence PowerShell does the same.</span></span>

<span data-ttu-id="112b1-247">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="112b1-247">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="112b1-248">OS</span><span class="sxs-lookup"><span data-stu-id="112b1-248">OS</span></span>                 | <span data-ttu-id="112b1-249">依存関係</span><span class="sxs-lookup"><span data-stu-id="112b1-249">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="112b1-250">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="112b1-250">Ubuntu 14.04</span></span>       | <span data-ttu-id="112b1-251">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="112b1-251">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="112b1-252">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="112b1-252">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="112b1-253">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="112b1-253">Ubuntu 16.04</span></span>       | <span data-ttu-id="112b1-254">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="112b1-254">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="112b1-255">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="112b1-255">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="112b1-256">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="112b1-256">Ubuntu 17.10</span></span>       | <span data-ttu-id="112b1-257">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="112b1-257">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="112b1-258">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="112b1-258">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="112b1-259">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="112b1-259">Ubuntu 18.04</span></span>       | <span data-ttu-id="112b1-260">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="112b1-260">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="112b1-261">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="112b1-261">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="112b1-262">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="112b1-262">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="112b1-263">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="112b1-263">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="112b1-264">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="112b1-264">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="112b1-265">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="112b1-265">Debian 9 (Stretch)</span></span> | <span data-ttu-id="112b1-266">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="112b1-266">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="112b1-267">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="112b1-267">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="112b1-268">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="112b1-268">CentOS 7</span></span> <br> <span data-ttu-id="112b1-269">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="112b1-269">Oracle Linux 7</span></span> <br> <span data-ttu-id="112b1-270">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="112b1-270">RHEL 7</span></span> | <span data-ttu-id="112b1-271">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="112b1-271">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="112b1-272">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="112b1-272">openSUSE 42.3</span></span> | <span data-ttu-id="112b1-273">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="112b1-273">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="112b1-274">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="112b1-274">openSUSE Leap 15</span></span> | <span data-ttu-id="112b1-275">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="112b1-275">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="112b1-276">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="112b1-276">Fedora 27</span></span> <br> <span data-ttu-id="112b1-277">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="112b1-277">Fedora 28</span></span> | <span data-ttu-id="112b1-278">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="112b1-278">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="112b1-279">公式にサポートされていない Linux ディストリビューションで PowerShell バイナリを展開するには、別の手順で、ターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="112b1-279">To deploy PowerShell binaries on Linux distributions that are not officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span>
<span data-ttu-id="112b1-280">たとえば、[Amazon Linux dockerfile][amazon-dockerfile] は依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="112b1-280">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="112b1-281">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="112b1-281">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="112b1-282">Linux</span><span class="sxs-lookup"><span data-stu-id="112b1-282">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/6.2.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.2.0

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/6.2.0/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="112b1-283">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="112b1-283">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="112b1-284">パス</span><span class="sxs-lookup"><span data-stu-id="112b1-284">Paths</span></span>

* `$PSHOME` <span data-ttu-id="112b1-285">:</span><span class="sxs-lookup"><span data-stu-id="112b1-285">is</span></span> `/opt/microsoft/powershell/6.2.0/`
* <span data-ttu-id="112b1-286">ユーザー プロファイルは次から読み込まれます:</span><span class="sxs-lookup"><span data-stu-id="112b1-286">User profiles will be read from</span></span> `~/.config/powershell/profile.ps1`
* <span data-ttu-id="112b1-287">既定のプロファイルは次から読み込まれます:</span><span class="sxs-lookup"><span data-stu-id="112b1-287">Default profiles will be read from</span></span> `$PSHOME/profile.ps1`
* <span data-ttu-id="112b1-288">ユーザー モジュールは次から読み込まれます:</span><span class="sxs-lookup"><span data-stu-id="112b1-288">User modules will be read from</span></span> `~/.local/share/powershell/Modules`
* <span data-ttu-id="112b1-289">共有モジュールは次から読み込まれます:</span><span class="sxs-lookup"><span data-stu-id="112b1-289">Shared modules will be read from</span></span> `/usr/local/share/powershell/Modules`
* <span data-ttu-id="112b1-290">既定のモジュールは次から読み込まれます:</span><span class="sxs-lookup"><span data-stu-id="112b1-290">Default modules will be read from</span></span> `$PSHOME/Modules`
* <span data-ttu-id="112b1-291">PSReadline 履歴は次に記録されます:</span><span class="sxs-lookup"><span data-stu-id="112b1-291">PSReadline history will be recorded to</span></span> `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`

<span data-ttu-id="112b1-292">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="112b1-292">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="112b1-293">PowerShell は、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="112b1-293">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[<span data-ttu-id="112b1-294">リリース</span><span class="sxs-lookup"><span data-stu-id="112b1-294">releases</span></span>]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
