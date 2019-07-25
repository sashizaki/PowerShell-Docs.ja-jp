---
title: Linux への PowerShell Core のインストール
description: さまざまな Linux ディストリビューションへの PowerShell Core のインストールに関する情報
ms.date: 07/19/2019
ms.openlocfilehash: 929b153ef784f3203cd31a0e2fc52e744a07532f
ms.sourcegitcommit: 118eb294d5a84a772e6449d42a9d9324e18ef6b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2019
ms.locfileid: "68372202"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="2c6be-103">Linux への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="2c6be-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="2c6be-104">[Ubuntu 16.04][u16], [Ubuntu 18.04][u1804]、[Ubuntu 18.10][u1810]、[Debian 9][deb9],
 [CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[openSUSE 42.3][opensuse]、[openSUSE Leap 15][opensuse], [Fedora 27][fedora]、[Fedora 28][fedora]、[Arch Linux][arch] がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-104">Supports [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Debian 9][deb9],
 [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="2c6be-105">公式にサポートされていない Linux ディストリビューションの場合は、[PowerShell の Snap パッケージ][snap]を使った PowerShell のインストールを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-105">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="2c6be-106">また、Linux [`tar.gz` アーカイブ][tar]を使用して、直接 PowerShell バイナリを展開できますが、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c6be-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="2c6be-107">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="2c6be-107">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="2c6be-108">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-108">After the package is installed, run `pwsh` from a terminal.</span></span>

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

## <a name="installing-preview-releases"></a><span data-ttu-id="2c6be-109">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="2c6be-109">Installing Preview Releases</span></span>

<span data-ttu-id="2c6be-110">パッケージ リポジトリを介して、Linux 用の PowerShell Core Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="2c6be-110">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="2c6be-111">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="2c6be-111">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="2c6be-112">さまざまなパッケージ マネージャーを使用して安定版およびプレビュー版パッケージをインストールするためのコマンドを、以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-112">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="2c6be-113">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="2c6be-113">Distribution(s)</span></span>|<span data-ttu-id="2c6be-114">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="2c6be-114">Stable Command</span></span> | <span data-ttu-id="2c6be-115">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="2c6be-115">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="2c6be-116">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="2c6be-116">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="2c6be-117">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="2c6be-117">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="2c6be-118">Fedora</span><span class="sxs-lookup"><span data-stu-id="2c6be-118">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1604"></a><span data-ttu-id="2c6be-119">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-119">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="2c6be-120">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-120">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="2c6be-121">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-121">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="2c6be-122">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2c6be-122">The preferred method is as follows:</span></span>

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

<span data-ttu-id="2c6be-123">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-123">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="2c6be-124">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-124">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="2c6be-125">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-125">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="2c6be-126">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2c6be-126">Download the Debian package `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="2c6be-127">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-127">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="2c6be-128">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-128">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="2c6be-129">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-129">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="2c6be-130">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-130">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="2c6be-131">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-131">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="2c6be-132">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-132">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="2c6be-133">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-133">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="2c6be-134">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2c6be-134">The preferred method is as follows:</span></span>

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

<span data-ttu-id="2c6be-135">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-135">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="2c6be-136">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-136">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="2c6be-137">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-137">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="2c6be-138">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2c6be-138">Download the Debian package `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="2c6be-139">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-139">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="2c6be-140">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-140">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="2c6be-141">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-141">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="2c6be-142">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-142">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="2c6be-143">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="2c6be-143">Ubuntu 18.10</span></span>

> [!NOTE]
> <span data-ttu-id="2c6be-144">18.10 が[中間リリース](https://www.ubuntu.com/about/release-cycle)のときに、これは[コミュニティでのみサポートされます](https://docs.microsoft.com/en-us/powershell/scripting/powershell-support-lifecycle?view=powershell-6)。</span><span class="sxs-lookup"><span data-stu-id="2c6be-144">As 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle), it is only [community supported](https://docs.microsoft.com/en-us/powershell/scripting/powershell-support-lifecycle?view=powershell-6).</span></span>

<span data-ttu-id="2c6be-145">18.10 へのインストールは `snapd` を使用してサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-145">Installing on 18.10 is supported via `snapd`.</span></span> <span data-ttu-id="2c6be-146">完全な手順については、「[Snap パッケージ][snap]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c6be-146">See [Snap Package][snap] for full instructions;</span></span>

## <a name="debian-8"></a><span data-ttu-id="2c6be-147">Debian 8</span><span class="sxs-lookup"><span data-stu-id="2c6be-147">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="2c6be-148">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="2c6be-148">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="2c6be-149">Linux 向けの PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-149">PowerShell Core, for Linux, is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="2c6be-150">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2c6be-150">The preferred method is as follows:</span></span>

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

<span data-ttu-id="2c6be-151">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-151">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="2c6be-152">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-152">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="2c6be-153">Debian 9</span><span class="sxs-lookup"><span data-stu-id="2c6be-153">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="2c6be-154">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="2c6be-154">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="2c6be-155">Linux 向け PowerShell Core は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-155">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="2c6be-156">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2c6be-156">The preferred method is as follows:</span></span>

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

<span data-ttu-id="2c6be-157">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-157">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="2c6be-158">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-158">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="2c6be-159">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="2c6be-159">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="2c6be-160">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_6.2.0-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2c6be-160">Download the Debian package `powershell_6.2.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="2c6be-161">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-161">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="2c6be-162">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="2c6be-162">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="2c6be-163">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-163">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="2c6be-164">このパッケージは Oracle Linux 7 で動作します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-164">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="2c6be-165">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-165">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="2c6be-166">Linux 向け PowerShell Core は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-166">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="2c6be-167">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-167">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="2c6be-168">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-168">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="2c6be-169">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-169">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="2c6be-170">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-6.2.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2c6be-170">Using [CentOS 7][], download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="2c6be-171">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-171">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="2c6be-172">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-172">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="2c6be-173">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-173">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="2c6be-175">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-175">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="2c6be-176">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-176">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="2c6be-177">Linux 向け PowerShell Core は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-177">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="2c6be-178">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-178">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="2c6be-179">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-179">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="2c6be-180">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-180">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="2c6be-181">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-6.2.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2c6be-181">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="2c6be-182">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-182">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="2c6be-183">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-183">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="2c6be-184">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-184">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="2c6be-185">openSUSE</span><span class="sxs-lookup"><span data-stu-id="2c6be-185">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="2c6be-186">インストール - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="2c6be-186">Installation - openSUSE 42.3</span></span>

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="2c6be-187">インストール - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="2c6be-187">Installation - openSUSE Leap 15</span></span>

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="2c6be-188">アンインストール - openSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="2c6be-188">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="2c6be-189">Fedora</span><span class="sxs-lookup"><span data-stu-id="2c6be-189">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="2c6be-190">Fedora 28 は、PowerShell Core 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-190">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a><span data-ttu-id="2c6be-191">パッケージ リポジトリによるインストール (推奨) - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="2c6be-191">Installation via Package Repository (preferred) - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="2c6be-192">Linux 向け PowerShell Core は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-192">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a><span data-ttu-id="2c6be-193">直接ダウンロードによるインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="2c6be-193">Installation via Direct Download - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="2c6be-194">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-6.2.0-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2c6be-194">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="2c6be-195">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-195">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="2c6be-196">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-196">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a><span data-ttu-id="2c6be-197">アンインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="2c6be-197">Uninstallation - Fedora 27, Fedora 28</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="2c6be-198">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="2c6be-198">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="2c6be-199">Arch のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="2c6be-199">Arch support is experimental.</span></span>

<span data-ttu-id="2c6be-200">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-200">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="2c6be-201">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="2c6be-201">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="2c6be-202">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="2c6be-202">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="2c6be-203">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="2c6be-203">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="2c6be-204">AUR のパッケージはコミュニティによって管理されています。公式のサポートは存在しません。</span><span class="sxs-lookup"><span data-stu-id="2c6be-204">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="2c6be-205">AUR からパッケージをインストールする方法については、[Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) かコミュニティ [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c6be-205">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="2c6be-207">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="2c6be-207">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="2c6be-208">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="2c6be-208">Getting snapd</span></span>

<span data-ttu-id="2c6be-209">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="2c6be-209">`snapd` is required to run snaps.</span></span> <span data-ttu-id="2c6be-210">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2c6be-210">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="2c6be-211">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="2c6be-211">Installation via Snap</span></span>

<span data-ttu-id="2c6be-212">Linux 向けの PowerShell Core は、インストールと更新を容易にするために [Snap ストア](https://snapcraft.io/store)に公開されています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-212">PowerShell Core for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="2c6be-213">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2c6be-213">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="2c6be-214">プレビュー バージョンをインストールするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-214">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="2c6be-215">インストールしたら、Snap は自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-215">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="2c6be-216">`sudo snap refresh powershell` または `sudo snap refresh powershell-preview` を使って、アップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="2c6be-216">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="2c6be-217">アンインストール</span><span class="sxs-lookup"><span data-stu-id="2c6be-217">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="2c6be-218">または</span><span class="sxs-lookup"><span data-stu-id="2c6be-218">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="2c6be-219">Kali</span><span class="sxs-lookup"><span data-stu-id="2c6be-219">Kali</span></span>

### <a name="installation---kali"></a><span data-ttu-id="2c6be-220">インストール - Kali</span><span class="sxs-lookup"><span data-stu-id="2c6be-220">Installation - Kali</span></span>

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

### <a name="uninstallation---kali"></a><span data-ttu-id="2c6be-221">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="2c6be-221">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="2c6be-222">Raspbian</span><span class="sxs-lookup"><span data-stu-id="2c6be-222">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="2c6be-223">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="2c6be-223">Raspbian support is experimental.</span></span>

<span data-ttu-id="2c6be-224">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-224">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="2c6be-225">CoreCLR と PowerShell Core は、Pi 2 および Pi 3 デバイス上でのみ動作します。[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスには、サポート外のプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="2c6be-225">CoreCLR and PowerShell Core will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="2c6be-226">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="2c6be-226">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="2c6be-227">インストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="2c6be-227">Installation - Raspbian</span></span>

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

<span data-ttu-id="2c6be-228">必要に応じて、`pwsh` バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="2c6be-228">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="2c6be-229">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="2c6be-229">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="2c6be-230">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="2c6be-230">Binary Archives</span></span>

<span data-ttu-id="2c6be-231">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-231">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="2c6be-232">依存関係</span><span class="sxs-lookup"><span data-stu-id="2c6be-232">Dependencies</span></span>

<span data-ttu-id="2c6be-233">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="2c6be-233">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="2c6be-234">ただし、.NET Core ランタイムにはディストリビューションごとに異なる依存関係が必要であり、PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="2c6be-234">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="2c6be-235">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="2c6be-235">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="2c6be-236">OS</span><span class="sxs-lookup"><span data-stu-id="2c6be-236">OS</span></span>                 | <span data-ttu-id="2c6be-237">依存関係</span><span class="sxs-lookup"><span data-stu-id="2c6be-237">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="2c6be-238">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-238">Ubuntu 16.04</span></span>       | <span data-ttu-id="2c6be-239">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="2c6be-239">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="2c6be-240">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="2c6be-240">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="2c6be-241">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="2c6be-241">Ubuntu 17.10</span></span>       | <span data-ttu-id="2c6be-242">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="2c6be-242">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="2c6be-243">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="2c6be-243">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="2c6be-244">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="2c6be-244">Ubuntu 18.04</span></span>       | <span data-ttu-id="2c6be-245">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="2c6be-245">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="2c6be-246">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="2c6be-246">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="2c6be-247">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="2c6be-247">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="2c6be-248">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="2c6be-248">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="2c6be-249">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="2c6be-249">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="2c6be-250">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="2c6be-250">Debian 9 (Stretch)</span></span> | <span data-ttu-id="2c6be-251">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="2c6be-251">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="2c6be-252">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="2c6be-252">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="2c6be-253">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-253">CentOS 7</span></span> <br> <span data-ttu-id="2c6be-254">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-254">Oracle Linux 7</span></span> <br> <span data-ttu-id="2c6be-255">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="2c6be-255">RHEL 7</span></span> | <span data-ttu-id="2c6be-256">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="2c6be-256">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="2c6be-257">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="2c6be-257">openSUSE 42.3</span></span> | <span data-ttu-id="2c6be-258">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="2c6be-258">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="2c6be-259">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="2c6be-259">openSUSE Leap 15</span></span> | <span data-ttu-id="2c6be-260">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="2c6be-260">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="2c6be-261">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="2c6be-261">Fedora 27</span></span> <br> <span data-ttu-id="2c6be-262">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="2c6be-262">Fedora 28</span></span> | <span data-ttu-id="2c6be-263">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="2c6be-263">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="2c6be-264">公式にサポートされていない Linux ディストリビューションに PowerShell バイナリを展開するには、別の手順によってターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c6be-264">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="2c6be-265">たとえば、[Amazon Linux Dockerfile][amazon-dockerfile] では依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2c6be-265">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="2c6be-266">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="2c6be-266">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="2c6be-267">Linux</span><span class="sxs-lookup"><span data-stu-id="2c6be-267">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="2c6be-268">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="2c6be-268">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="2c6be-269">パス</span><span class="sxs-lookup"><span data-stu-id="2c6be-269">Paths</span></span>

* <span data-ttu-id="2c6be-270">`$PSHOME` は `/opt/microsoft/powershell/6.2.0/` です</span><span class="sxs-lookup"><span data-stu-id="2c6be-270">`$PSHOME` is `/opt/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="2c6be-271">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2c6be-271">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="2c6be-272">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2c6be-272">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="2c6be-273">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2c6be-273">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="2c6be-274">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2c6be-274">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="2c6be-275">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="2c6be-275">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="2c6be-276">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="2c6be-276">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="2c6be-277">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="2c6be-277">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="2c6be-278">PowerShell では、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="2c6be-278">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
