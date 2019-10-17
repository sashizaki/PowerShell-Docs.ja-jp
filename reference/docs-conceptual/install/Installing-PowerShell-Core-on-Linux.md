---
title: Linux への PowerShell Core のインストール
description: さまざまな Linux ディストリビューションへの PowerShell Core のインストールに関する情報
ms.date: 07/19/2019
ms.openlocfilehash: fc5a278f0fc10733a0d60fb856d0400332ba2719
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72350193"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="472da-103">Linux への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="472da-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="472da-104">[Ubuntu 16.04][u16]、[Ubuntu 18.04][u1804]、[Ubuntu 18.10][u1810]、[Ubuntu 19.04][u1904]、[Debian 8][deb8]、[Debian 9][deb9]、[CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[openSUSE 42.3][opensuse]、[openSUSE Leap 15][opensuse]、[Fedora 27][fedora]、[Fedora 28][fedora]、および [Arch Linux][arch] をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="472da-104">Supports [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 8][deb8],  [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="472da-105">公式にサポートされていない Linux ディストリビューションの場合は、[PowerShell の Snap パッケージ][snap]を使った PowerShell のインストールを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="472da-105">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="472da-106">また、Linux [`tar.gz` アーカイブ][tar]を使用して、直接 PowerShell バイナリを展開できますが、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="472da-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="472da-107">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="472da-107">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="472da-108">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-108">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="472da-109">[プレビュー リリース](#installing-preview-releases)をインストールした場合は、`pwsh-preview` を実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-109">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[u1904]: #ubuntu-1904
[deb8]: #debian-8
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives

## <a name="installing-preview-releases"></a><span data-ttu-id="472da-110">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="472da-110">Installing Preview Releases</span></span>

<span data-ttu-id="472da-111">パッケージ リポジトリを介して、Linux 用の PowerShell Core Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="472da-111">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="472da-112">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="472da-112">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="472da-113">さまざまなパッケージ マネージャーを使用して安定版およびプレビュー版パッケージをインストールするためのコマンドを、以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="472da-113">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="472da-114">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="472da-114">Distribution(s)</span></span>|<span data-ttu-id="472da-115">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="472da-115">Stable Command</span></span> | <span data-ttu-id="472da-116">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="472da-116">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="472da-117">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="472da-117">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="472da-118">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="472da-118">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="472da-119">Fedora</span><span class="sxs-lookup"><span data-stu-id="472da-119">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1604"></a><span data-ttu-id="472da-120">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="472da-120">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="472da-121">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="472da-121">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="472da-122">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="472da-122">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="472da-123">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="472da-123">The preferred method is as follows:</span></span>

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

<span data-ttu-id="472da-124">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="472da-124">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="472da-125">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="472da-125">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="472da-126">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="472da-126">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="472da-127">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="472da-127">Download the Debian package `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="472da-128">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-128">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="472da-129">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="472da-129">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="472da-130">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="472da-130">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="472da-131">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="472da-131">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="472da-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="472da-132">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="472da-133">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="472da-133">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="472da-134">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="472da-134">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="472da-135">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="472da-135">The preferred method is as follows:</span></span>

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

<span data-ttu-id="472da-136">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="472da-136">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="472da-137">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="472da-137">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="472da-138">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="472da-138">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="472da-139">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="472da-139">Download the Debian package `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="472da-140">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-140">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="472da-141">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="472da-141">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="472da-142">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="472da-142">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="472da-143">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="472da-143">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="472da-144">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="472da-144">Ubuntu 18.10</span></span>

<span data-ttu-id="472da-145">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="472da-145">Installation is supported via `snapd`.</span></span> <span data-ttu-id="472da-146">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="472da-146">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="472da-147">Ubuntu 18.10 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="472da-147">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="472da-148">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="472da-148">Ubuntu 19.04</span></span>

<span data-ttu-id="472da-149">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="472da-149">Installation is supported via `snapd`.</span></span> <span data-ttu-id="472da-150">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="472da-150">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="472da-151">Ubuntu 19.04 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="472da-151">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="472da-152">Debian 8</span><span class="sxs-lookup"><span data-stu-id="472da-152">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="472da-153">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="472da-153">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="472da-154">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="472da-154">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="472da-155">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="472da-155">The preferred method is as follows:</span></span>

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

<span data-ttu-id="472da-156">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="472da-156">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="472da-157">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="472da-157">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="472da-158">Debian 9</span><span class="sxs-lookup"><span data-stu-id="472da-158">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="472da-159">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="472da-159">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="472da-160">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="472da-160">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="472da-161">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="472da-161">The preferred method is as follows:</span></span>

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

<span data-ttu-id="472da-162">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="472da-162">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="472da-163">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="472da-163">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="472da-164">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="472da-164">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="472da-165">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_6.2.0-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="472da-165">Download the Debian package `powershell_6.2.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="472da-166">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-166">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="472da-167">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="472da-167">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="472da-168">Debian 10</span><span class="sxs-lookup"><span data-stu-id="472da-168">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="472da-169">Debian 10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="472da-169">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="472da-170">直接ダウンロードによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="472da-170">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="472da-171">[リリース][] ページから Debian コンピューターに tar.gz パッケージ `powershell_7.0.0-preview-7-linux-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="472da-171">Download the tar.gz package `powershell_7.0.0-preview-7-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="472da-172">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-172">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0-preview.4/powershell-7.0.0-preview.4-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7-preview

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7-preview

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7-preview/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7-preview/pwsh /usr/bin/pwsh-preview

# Start PowerShell
pwsh-preview
```

## <a name="alpine-39-and-310"></a><span data-ttu-id="472da-173">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="472da-173">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="472da-174">Alpine 3.9 および 3.10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="472da-174">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="472da-175">直接ダウンロードによるインストール - Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="472da-175">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="472da-176">[リリース][] ページから Alpine コンピューターに tar.gz パッケージ `powershell_7.0.0-preview-7-linux-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="472da-176">Download the tar.gz package `powershell_7.0.0-preview-7-linux-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="472da-177">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-177">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0-preview.4/powershell-7.0.0-preview.4-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7-preview

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7-preview

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7-preview/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7-preview/pwsh /usr/bin/pwsh-preview

# Start PowerShell
pwsh-preview
```

## <a name="centos-7"></a><span data-ttu-id="472da-178">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="472da-178">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="472da-179">このパッケージは Oracle Linux 7 で動作します。</span><span class="sxs-lookup"><span data-stu-id="472da-179">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="472da-180">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="472da-180">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="472da-181">Linux 向け PowerShell Core は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="472da-181">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="472da-182">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="472da-182">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="472da-183">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="472da-183">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="472da-184">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="472da-184">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="472da-185">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-6.2.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="472da-185">Using [CentOS 7][], download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="472da-186">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-186">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="472da-187">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="472da-187">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="472da-188">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="472da-188">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="472da-190">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="472da-190">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="472da-191">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="472da-191">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="472da-192">Linux 向け PowerShell Core は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="472da-192">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="472da-193">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="472da-193">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="472da-194">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="472da-194">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="472da-195">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="472da-195">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="472da-196">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-6.2.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="472da-196">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="472da-197">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-197">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="472da-198">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="472da-198">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="472da-199">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="472da-199">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="472da-200">openSUSE</span><span class="sxs-lookup"><span data-stu-id="472da-200">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="472da-201">インストール - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="472da-201">Installation - openSUSE 42.3</span></span>

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="472da-202">インストール - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="472da-202">Installation - openSUSE Leap 15</span></span>

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="472da-203">アンインストール - openSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="472da-203">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="472da-204">Fedora</span><span class="sxs-lookup"><span data-stu-id="472da-204">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="472da-205">Fedora 28 は、PowerShell Core 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="472da-205">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="472da-206">Fedora 29 および 30 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="472da-206">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="472da-207">パッケージ リポジトリによるインストール (推奨) - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="472da-207">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="472da-208">Linux 向け PowerShell Core は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="472da-208">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="472da-209">直接ダウンロードによるインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="472da-209">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="472da-210">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-6.2.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="472da-210">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="472da-211">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="472da-211">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="472da-212">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="472da-212">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="472da-213">アンインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="472da-213">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="472da-214">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="472da-214">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="472da-215">Arch のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="472da-215">Arch support is experimental.</span></span>

<span data-ttu-id="472da-216">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="472da-216">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="472da-217">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="472da-217">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="472da-218">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="472da-218">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="472da-219">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="472da-219">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="472da-220">AUR のパッケージはコミュニティによって管理されています。公式のサポートは存在しません。</span><span class="sxs-lookup"><span data-stu-id="472da-220">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="472da-221">AUR からパッケージをインストールする方法については、[Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) かコミュニティ [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="472da-221">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="472da-223">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="472da-223">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="472da-224">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="472da-224">Getting snapd</span></span>

<span data-ttu-id="472da-225">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="472da-225">`snapd` is required to run snaps.</span></span> <span data-ttu-id="472da-226">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="472da-226">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="472da-227">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="472da-227">Installation via Snap</span></span>

<span data-ttu-id="472da-228">Linux 向けの PowerShell Core は、インストールと更新を容易にするために [Snap ストア](https://snapcraft.io/store)に公開されています。</span><span class="sxs-lookup"><span data-stu-id="472da-228">PowerShell Core for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="472da-229">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="472da-229">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="472da-230">プレビュー バージョンをインストールするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="472da-230">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="472da-231">インストールしたら、Snap は自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="472da-231">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="472da-232">`sudo snap refresh powershell` または `sudo snap refresh powershell-preview` を使って、アップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="472da-232">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="472da-233">アンインストール</span><span class="sxs-lookup"><span data-stu-id="472da-233">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="472da-234">または</span><span class="sxs-lookup"><span data-stu-id="472da-234">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="472da-235">Kali</span><span class="sxs-lookup"><span data-stu-id="472da-235">Kali</span></span>

### <a name="installation---kali"></a><span data-ttu-id="472da-236">インストール - Kali</span><span class="sxs-lookup"><span data-stu-id="472da-236">Installation - Kali</span></span>

```sh
# Download & Install prerequisites
wget http://ftp.us.debian.org/debian/pool/main/i/icu/libicu57_57.1-6+deb9u2_amd64.deb
dpkg -i libicu57_57.1-6+deb9u2_amd64.deb
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

### <a name="uninstallation---kali"></a><span data-ttu-id="472da-237">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="472da-237">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="472da-238">Raspbian</span><span class="sxs-lookup"><span data-stu-id="472da-238">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="472da-239">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="472da-239">Raspbian support is experimental.</span></span>

<span data-ttu-id="472da-240">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="472da-240">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="472da-241">CoreCLR と PowerShell Core は、Pi 2 および Pi 3 デバイス上でのみ動作します。[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスには、サポート外のプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="472da-241">CoreCLR and PowerShell Core will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="472da-242">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="472da-242">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="472da-243">インストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="472da-243">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.2.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="472da-244">必要に応じて、`pwsh` バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="472da-244">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="472da-245">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="472da-245">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="472da-246">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="472da-246">Binary Archives</span></span>

<span data-ttu-id="472da-247">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="472da-247">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="472da-248">依存関係</span><span class="sxs-lookup"><span data-stu-id="472da-248">Dependencies</span></span>

<span data-ttu-id="472da-249">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="472da-249">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="472da-250">ただし、.NET Core ランタイムにはディストリビューションごとに異なる依存関係が必要であり、PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="472da-250">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="472da-251">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="472da-251">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="472da-252">OS</span><span class="sxs-lookup"><span data-stu-id="472da-252">OS</span></span>                 | <span data-ttu-id="472da-253">依存関係</span><span class="sxs-lookup"><span data-stu-id="472da-253">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="472da-254">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="472da-254">Ubuntu 16.04</span></span>       | <span data-ttu-id="472da-255">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="472da-255">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="472da-256">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="472da-256">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="472da-257">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="472da-257">Ubuntu 17.10</span></span>       | <span data-ttu-id="472da-258">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="472da-258">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="472da-259">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="472da-259">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="472da-260">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="472da-260">Ubuntu 18.04</span></span>       | <span data-ttu-id="472da-261">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="472da-261">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="472da-262">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="472da-262">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="472da-263">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="472da-263">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="472da-264">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="472da-264">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="472da-265">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="472da-265">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="472da-266">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="472da-266">Debian 9 (Stretch)</span></span> | <span data-ttu-id="472da-267">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="472da-267">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="472da-268">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="472da-268">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="472da-269">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="472da-269">CentOS 7</span></span> <br> <span data-ttu-id="472da-270">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="472da-270">Oracle Linux 7</span></span> <br> <span data-ttu-id="472da-271">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="472da-271">RHEL 7</span></span> | <span data-ttu-id="472da-272">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="472da-272">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="472da-273">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="472da-273">openSUSE 42.3</span></span> | <span data-ttu-id="472da-274">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="472da-274">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="472da-275">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="472da-275">openSUSE Leap 15</span></span> | <span data-ttu-id="472da-276">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="472da-276">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="472da-277">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="472da-277">Fedora 27</span></span> <br> <span data-ttu-id="472da-278">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="472da-278">Fedora 28</span></span> | <span data-ttu-id="472da-279">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="472da-279">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="472da-280">公式にサポートされていない Linux ディストリビューションに PowerShell バイナリを展開するには、別の手順によってターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="472da-280">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="472da-281">たとえば、[Amazon Linux Dockerfile][amazon-dockerfile] では依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="472da-281">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="472da-282">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="472da-282">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="472da-283">Linux</span><span class="sxs-lookup"><span data-stu-id="472da-283">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="472da-284">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="472da-284">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="472da-285">パス</span><span class="sxs-lookup"><span data-stu-id="472da-285">Paths</span></span>

* <span data-ttu-id="472da-286">`$PSHOME` は `/opt/microsoft/powershell/6.2.0/` です</span><span class="sxs-lookup"><span data-stu-id="472da-286">`$PSHOME` is `/opt/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="472da-287">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="472da-287">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="472da-288">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="472da-288">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="472da-289">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="472da-289">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="472da-290">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="472da-290">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="472da-291">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="472da-291">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="472da-292">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="472da-292">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="472da-293">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="472da-293">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="472da-294">PowerShell では、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="472da-294">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
