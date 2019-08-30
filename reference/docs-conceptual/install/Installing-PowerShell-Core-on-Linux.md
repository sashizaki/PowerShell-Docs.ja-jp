---
title: Linux への PowerShell Core のインストール
description: さまざまな Linux ディストリビューションへの PowerShell Core のインストールに関する情報
ms.date: 07/19/2019
ms.openlocfilehash: be11a2a873af71c193730d0a9e723da2dc70a62d
ms.sourcegitcommit: 5a004064f33acc0145ccd414535763e95f998c89
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69986731"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="498af-103">Linux への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="498af-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="498af-104">[Ubuntu 16.04][u16]、[Ubuntu 18.04][u1804]、[Ubuntu 18.10][u1810]、[Ubuntu 19.04][u1904]、[Debian 9][deb9]、[CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[openSUSE 42.3][opensuse]、[openSUSE Leap 15][opensuse]、[Fedora 27][fedora]、[Fedora 28][fedora]、および [Arch Linux][arch] をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="498af-104">Supports [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="498af-105">公式にサポートされていない Linux ディストリビューションの場合は、[PowerShell の Snap パッケージ][snap]を使った PowerShell のインストールを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="498af-105">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="498af-106">また、Linux [`tar.gz` アーカイブ][tar]を使用して、直接 PowerShell バイナリを展開できますが、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="498af-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="498af-107">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="498af-107">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="498af-108">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="498af-108">After the package is installed, run `pwsh` from a terminal.</span></span>

[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[u1904]: #ubuntu-1904
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives

## <a name="installing-preview-releases"></a><span data-ttu-id="498af-109">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="498af-109">Installing Preview Releases</span></span>

<span data-ttu-id="498af-110">パッケージ リポジトリを介して、Linux 用の PowerShell Core Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="498af-110">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="498af-111">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="498af-111">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="498af-112">さまざまなパッケージ マネージャーを使用して安定版およびプレビュー版パッケージをインストールするためのコマンドを、以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="498af-112">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="498af-113">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="498af-113">Distribution(s)</span></span>|<span data-ttu-id="498af-114">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="498af-114">Stable Command</span></span> | <span data-ttu-id="498af-115">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="498af-115">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="498af-116">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="498af-116">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="498af-117">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="498af-117">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="498af-118">Fedora</span><span class="sxs-lookup"><span data-stu-id="498af-118">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1604"></a><span data-ttu-id="498af-119">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="498af-119">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="498af-120">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="498af-120">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="498af-121">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="498af-121">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="498af-122">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="498af-122">The preferred method is as follows:</span></span>

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

<span data-ttu-id="498af-123">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="498af-123">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="498af-124">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="498af-124">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="498af-125">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="498af-125">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="498af-126">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="498af-126">Download the Debian package `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="498af-127">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="498af-127">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="498af-128">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="498af-128">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="498af-129">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="498af-129">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="498af-130">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="498af-130">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="498af-131">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="498af-131">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="498af-132">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="498af-132">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="498af-133">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="498af-133">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="498af-134">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="498af-134">The preferred method is as follows:</span></span>

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

<span data-ttu-id="498af-135">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="498af-135">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="498af-136">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="498af-136">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="498af-137">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="498af-137">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="498af-138">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="498af-138">Download the Debian package `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="498af-139">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="498af-139">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="498af-140">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="498af-140">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="498af-141">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="498af-141">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="498af-142">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="498af-142">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="498af-143">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="498af-143">Ubuntu 18.10</span></span>

<span data-ttu-id="498af-144">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="498af-144">Installation is supported via `snapd`.</span></span> <span data-ttu-id="498af-145">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="498af-145">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="498af-146">Ubuntu 18.10 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="498af-146">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="498af-147">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="498af-147">Ubuntu 19.04</span></span>

<span data-ttu-id="498af-148">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="498af-148">Installation is supported via `snapd`.</span></span> <span data-ttu-id="498af-149">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="498af-149">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="498af-150">Ubuntu 19.04 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="498af-150">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="498af-151">Debian 8</span><span class="sxs-lookup"><span data-stu-id="498af-151">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="498af-152">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="498af-152">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="498af-153">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="498af-153">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="498af-154">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="498af-154">The preferred method is as follows:</span></span>

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

<span data-ttu-id="498af-155">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="498af-155">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="498af-156">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="498af-156">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="498af-157">Debian 9</span><span class="sxs-lookup"><span data-stu-id="498af-157">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="498af-158">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="498af-158">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="498af-159">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="498af-159">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="498af-160">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="498af-160">The preferred method is as follows:</span></span>

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

<span data-ttu-id="498af-161">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="498af-161">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="498af-162">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="498af-162">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="498af-163">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="498af-163">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="498af-164">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_6.2.0-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="498af-164">Download the Debian package `powershell_6.2.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="498af-165">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="498af-165">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="498af-166">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="498af-166">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="498af-167">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="498af-167">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="498af-168">このパッケージは Oracle Linux 7 で動作します。</span><span class="sxs-lookup"><span data-stu-id="498af-168">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="498af-169">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="498af-169">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="498af-170">Linux 向け PowerShell Core は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="498af-170">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="498af-171">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="498af-171">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="498af-172">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="498af-172">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="498af-173">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="498af-173">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="498af-174">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-6.2.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="498af-174">Using [CentOS 7][], download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="498af-175">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="498af-175">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="498af-176">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="498af-176">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="498af-177">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="498af-177">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="498af-179">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="498af-179">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="498af-180">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="498af-180">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="498af-181">Linux 向け PowerShell Core は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="498af-181">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="498af-182">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="498af-182">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="498af-183">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="498af-183">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="498af-184">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="498af-184">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="498af-185">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-6.2.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="498af-185">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="498af-186">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="498af-186">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="498af-187">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="498af-187">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="498af-188">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="498af-188">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="498af-189">openSUSE</span><span class="sxs-lookup"><span data-stu-id="498af-189">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="498af-190">インストール - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="498af-190">Installation - openSUSE 42.3</span></span>

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="498af-191">インストール - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="498af-191">Installation - openSUSE Leap 15</span></span>

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="498af-192">アンインストール - openSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="498af-192">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="498af-193">Fedora</span><span class="sxs-lookup"><span data-stu-id="498af-193">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="498af-194">Fedora 28 は、PowerShell Core 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="498af-194">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a><span data-ttu-id="498af-195">パッケージ リポジトリによるインストール (推奨) - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="498af-195">Installation via Package Repository (preferred) - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="498af-196">Linux 向け PowerShell Core は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="498af-196">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a><span data-ttu-id="498af-197">直接ダウンロードによるインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="498af-197">Installation via Direct Download - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="498af-198">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-6.2.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="498af-198">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="498af-199">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="498af-199">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="498af-200">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="498af-200">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a><span data-ttu-id="498af-201">アンインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="498af-201">Uninstallation - Fedora 27, Fedora 28</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="498af-202">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="498af-202">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="498af-203">Arch のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="498af-203">Arch support is experimental.</span></span>

<span data-ttu-id="498af-204">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="498af-204">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="498af-205">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="498af-205">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="498af-206">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="498af-206">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="498af-207">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="498af-207">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="498af-208">AUR のパッケージはコミュニティによって管理されています。公式のサポートは存在しません。</span><span class="sxs-lookup"><span data-stu-id="498af-208">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="498af-209">AUR からパッケージをインストールする方法については、[Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) かコミュニティ [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="498af-209">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="498af-211">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="498af-211">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="498af-212">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="498af-212">Getting snapd</span></span>

<span data-ttu-id="498af-213">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="498af-213">`snapd` is required to run snaps.</span></span> <span data-ttu-id="498af-214">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="498af-214">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="498af-215">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="498af-215">Installation via Snap</span></span>

<span data-ttu-id="498af-216">Linux 向けの PowerShell Core は、インストールと更新を容易にするために [Snap ストア](https://snapcraft.io/store)に公開されています。</span><span class="sxs-lookup"><span data-stu-id="498af-216">PowerShell Core for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="498af-217">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="498af-217">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="498af-218">プレビュー バージョンをインストールするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="498af-218">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="498af-219">インストールしたら、Snap は自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="498af-219">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="498af-220">`sudo snap refresh powershell` または `sudo snap refresh powershell-preview` を使って、アップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="498af-220">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="498af-221">アンインストール</span><span class="sxs-lookup"><span data-stu-id="498af-221">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="498af-222">または</span><span class="sxs-lookup"><span data-stu-id="498af-222">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="498af-223">Kali</span><span class="sxs-lookup"><span data-stu-id="498af-223">Kali</span></span>

### <a name="installation---kali"></a><span data-ttu-id="498af-224">インストール - Kali</span><span class="sxs-lookup"><span data-stu-id="498af-224">Installation - Kali</span></span>

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

### <a name="uninstallation---kali"></a><span data-ttu-id="498af-225">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="498af-225">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="498af-226">Raspbian</span><span class="sxs-lookup"><span data-stu-id="498af-226">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="498af-227">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="498af-227">Raspbian support is experimental.</span></span>

<span data-ttu-id="498af-228">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="498af-228">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="498af-229">CoreCLR と PowerShell Core は、Pi 2 および Pi 3 デバイス上でのみ動作します。[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスには、サポート外のプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="498af-229">CoreCLR and PowerShell Core will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="498af-230">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="498af-230">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="498af-231">インストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="498af-231">Installation - Raspbian</span></span>

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

<span data-ttu-id="498af-232">必要に応じて、`pwsh` バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="498af-232">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="498af-233">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="498af-233">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="498af-234">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="498af-234">Binary Archives</span></span>

<span data-ttu-id="498af-235">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="498af-235">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="498af-236">依存関係</span><span class="sxs-lookup"><span data-stu-id="498af-236">Dependencies</span></span>

<span data-ttu-id="498af-237">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="498af-237">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="498af-238">ただし、.NET Core ランタイムにはディストリビューションごとに異なる依存関係が必要であり、PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="498af-238">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="498af-239">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="498af-239">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="498af-240">OS</span><span class="sxs-lookup"><span data-stu-id="498af-240">OS</span></span>                 | <span data-ttu-id="498af-241">依存関係</span><span class="sxs-lookup"><span data-stu-id="498af-241">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="498af-242">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="498af-242">Ubuntu 16.04</span></span>       | <span data-ttu-id="498af-243">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="498af-243">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="498af-244">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="498af-244">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="498af-245">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="498af-245">Ubuntu 17.10</span></span>       | <span data-ttu-id="498af-246">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="498af-246">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="498af-247">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="498af-247">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="498af-248">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="498af-248">Ubuntu 18.04</span></span>       | <span data-ttu-id="498af-249">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="498af-249">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="498af-250">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="498af-250">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="498af-251">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="498af-251">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="498af-252">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="498af-252">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="498af-253">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="498af-253">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="498af-254">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="498af-254">Debian 9 (Stretch)</span></span> | <span data-ttu-id="498af-255">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="498af-255">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="498af-256">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="498af-256">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="498af-257">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="498af-257">CentOS 7</span></span> <br> <span data-ttu-id="498af-258">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="498af-258">Oracle Linux 7</span></span> <br> <span data-ttu-id="498af-259">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="498af-259">RHEL 7</span></span> | <span data-ttu-id="498af-260">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="498af-260">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="498af-261">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="498af-261">openSUSE 42.3</span></span> | <span data-ttu-id="498af-262">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="498af-262">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="498af-263">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="498af-263">openSUSE Leap 15</span></span> | <span data-ttu-id="498af-264">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="498af-264">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="498af-265">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="498af-265">Fedora 27</span></span> <br> <span data-ttu-id="498af-266">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="498af-266">Fedora 28</span></span> | <span data-ttu-id="498af-267">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="498af-267">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="498af-268">公式にサポートされていない Linux ディストリビューションに PowerShell バイナリを展開するには、別の手順によってターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="498af-268">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="498af-269">たとえば、[Amazon Linux Dockerfile][amazon-dockerfile] では依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="498af-269">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="498af-270">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="498af-270">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="498af-271">Linux</span><span class="sxs-lookup"><span data-stu-id="498af-271">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="498af-272">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="498af-272">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="498af-273">パス</span><span class="sxs-lookup"><span data-stu-id="498af-273">Paths</span></span>

* <span data-ttu-id="498af-274">`$PSHOME` は `/opt/microsoft/powershell/6.2.0/` です</span><span class="sxs-lookup"><span data-stu-id="498af-274">`$PSHOME` is `/opt/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="498af-275">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="498af-275">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="498af-276">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="498af-276">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="498af-277">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="498af-277">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="498af-278">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="498af-278">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="498af-279">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="498af-279">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="498af-280">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="498af-280">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="498af-281">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="498af-281">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="498af-282">PowerShell では、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="498af-282">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
