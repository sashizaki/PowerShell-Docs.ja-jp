---
title: Linux への PowerShell のインストール
description: さまざまな Linux ディストリビューションへの PowerShell のインストールに関する情報
ms.date: 03/09/2020
ms.openlocfilehash: 31da32b81dbbcf4b46fd5f0cd9d921f28f434763
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500547"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="aa18d-103">Linux への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="aa18d-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="aa18d-104">[Ubuntu 16.04][u16]、[Ubuntu 18.04][u1804]、[Ubuntu 18.10][u1810]、[Ubuntu 19.04][u1904]、[Debian 8][deb8]、[Debian 9][deb9]、[Debian 10][deb10]、[Alpine 3.9 および 3.10][alpine]、[CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[openSUSE 42.3][opensuse]、[openSUSE Leap 15][opensuse]、[Fedora 28][fedora]、[Fedora 29][fedora]、[Fedora 30][fedora]、[Arch Linux][arch] がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-104">Supports [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 8][deb8], [Debian 9][deb9], [Debian 10][deb10], [Alpine 3.9 and 3.10][alpine], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 28][fedora], [Fedora 29][fedora], [Fedora 30][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="aa18d-105">公式にサポートされていない Linux ディストリビューションの場合は、[PowerShell の Snap パッケージ][snap]を使った PowerShell のインストールを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-105">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="aa18d-106">また、Linux [`tar.gz` アーカイブ][tar]を使用して、直接 PowerShell バイナリを展開できますが、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa18d-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="aa18d-107">すべてのパッケージは GitHub [ ページから Ubuntu コンピューターに Debian パッケージ ][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="aa18d-107">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="aa18d-108">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-108">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="aa18d-109">`pwsh-preview`プレビュー リリース[をインストールした場合は、](#installing-preview-releases) を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-109">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-110">PowerShell 7 はインプレース アップグレードで、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-110">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="aa18d-111">`/usr/local/microsoft/powershell/6` フォルダーは `/usr/local/microsoft/powershell/7` に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="aa18d-111">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="aa18d-112">Powershell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[バイナリ アーカイブ](#binary-archives)方法を使用して PowerShell 6 を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-112">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[u1904]: #ubuntu-1904
[deb8]: #debian-8
[deb9]: #debian-9
[deb10]: #debian-10
[alpine]: #alpine-39-and-310
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives


## <a name="installing-preview-releases"></a><span data-ttu-id="aa18d-113">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="aa18d-113">Installing Preview Releases</span></span>

<span data-ttu-id="aa18d-114">パッケージ リポジトリを介して、Linux 用の PowerShell Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="aa18d-114">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="aa18d-115">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="aa18d-115">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="aa18d-116">さまざまなパッケージ マネージャーを使用して安定版およびプレビュー版パッケージをインストールするためのコマンドを、以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-116">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="aa18d-117">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="aa18d-117">Distribution(s)</span></span> |            <span data-ttu-id="aa18d-118">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="aa18d-118">Stable Command</span></span>            |               <span data-ttu-id="aa18d-119">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="aa18d-119">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="aa18d-120">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="aa18d-120">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="aa18d-121">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="aa18d-121">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="aa18d-122">Fedora</span><span class="sxs-lookup"><span data-stu-id="aa18d-122">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="ubuntu-1604"></a><span data-ttu-id="aa18d-123">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-123">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="aa18d-124">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-124">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="aa18d-125">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-125">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="aa18d-126">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-126">The preferred method is as follows:</span></span>

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

<span data-ttu-id="aa18d-127">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-127">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="aa18d-128">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-128">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="aa18d-129">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-129">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="aa18d-130">`powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb`リリース[ ページから Ubuntu コンピューターに Debian パッケージ ][] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-130">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="aa18d-131">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-131">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="aa18d-132">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-132">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="aa18d-133">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-133">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="aa18d-134">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-134">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="aa18d-135">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-135">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="aa18d-136">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-136">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="aa18d-137">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-137">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="aa18d-138">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-138">The preferred method is as follows:</span></span>

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

<span data-ttu-id="aa18d-139">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-139">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="aa18d-140">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-140">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="aa18d-141">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-141">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="aa18d-142">`powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb`リリース[ ページから Ubuntu コンピューターに Debian パッケージ ][] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-142">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="aa18d-143">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-143">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="aa18d-144">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-144">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="aa18d-145">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-145">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="aa18d-146">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-146">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="aa18d-147">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="aa18d-147">Ubuntu 18.10</span></span>

<span data-ttu-id="aa18d-148">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-148">Installation is supported via `snapd`.</span></span> <span data-ttu-id="aa18d-149">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aa18d-149">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-150">Ubuntu 18.10 は、[コミュニティでサポートされている](https://www.ubuntu.com/about/release-cycle)[中間リリース](../powershell-support-lifecycle.md)です。</span><span class="sxs-lookup"><span data-stu-id="aa18d-150">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="aa18d-151">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-151">Ubuntu 19.04</span></span>

<span data-ttu-id="aa18d-152">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-152">Installation is supported via `snapd`.</span></span> <span data-ttu-id="aa18d-153">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aa18d-153">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-154">Ubuntu 19.04 は、[コミュニティでサポートされている](https://www.ubuntu.com/about/release-cycle)[中間リリース](../powershell-support-lifecycle.md)です。</span><span class="sxs-lookup"><span data-stu-id="aa18d-154">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="aa18d-155">Debian 8</span><span class="sxs-lookup"><span data-stu-id="aa18d-155">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="aa18d-156">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="aa18d-156">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="aa18d-157">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-157">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="aa18d-158">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-158">The preferred method is as follows:</span></span>

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

<span data-ttu-id="aa18d-159">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-159">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="aa18d-160">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-160">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="aa18d-161">Debian 9</span><span class="sxs-lookup"><span data-stu-id="aa18d-161">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="aa18d-162">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="aa18d-162">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="aa18d-163">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-163">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="aa18d-164">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-164">The preferred method is as follows:</span></span>

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

<span data-ttu-id="aa18d-165">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-165">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="aa18d-166">登録後は、`sudo apt-get upgrade powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-166">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="aa18d-167">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="aa18d-167">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="aa18d-168">`powershell-lts_7.0.0-1.debian.9_amd64.deb`リリース[ ページから Ubuntu コンピューターに Debian パッケージ ][] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-168">Download the Debian package `powershell-lts_7.0.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="aa18d-169">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-169">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="aa18d-170">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="aa18d-170">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="aa18d-171">Debian 10</span><span class="sxs-lookup"><span data-stu-id="aa18d-171">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-172">Debian 10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-172">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="aa18d-173">パッケージ リポジトリによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="aa18d-173">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="aa18d-174">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-174">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="aa18d-175">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-175">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="aa18d-176">直接ダウンロードによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="aa18d-176">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="aa18d-177">`powershell_7.0.0-linux-x64.tar.gz`リリース[ ページから Ubuntu コンピューターに Debian パッケージ ][] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-177">Download the tar.gz package `powershell_7.0.0-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="aa18d-178">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-178">Then, in the terminal, execute the following commands:</span></span>

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="aa18d-179">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="aa18d-179">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-180">Alpine 3.9 および 3.10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-180">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="aa18d-181">直接ダウンロードによるインストール - Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="aa18d-181">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="aa18d-182">`powershell-7.0.0-linux-alpine-x64.tar.gz`リリース[ ページから Ubuntu コンピューターに Debian パッケージ ][] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-182">Download the tar.gz package `powershell-7.0.0-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="aa18d-183">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-183">Then, in the terminal, execute the following commands:</span></span>

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

## <a name="centos-7"></a><span data-ttu-id="aa18d-184">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-184">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-185">このパッケージは Oracle Linux 7 で動作します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-185">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="aa18d-186">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-186">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="aa18d-187">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-187">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="aa18d-188">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-188">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="aa18d-189">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-189">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="aa18d-190">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-190">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="aa18d-191">[CentOS 7][] を利用し、`powershell-lts-7.0.0-1.rhel.7.x86_64.rpm`リリース[ ページから Ubuntu コンピューターに Debian パッケージ ][] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-191">Using [CentOS 7][], download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="aa18d-192">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-192">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="aa18d-193">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-193">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="aa18d-194">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-194">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="aa18d-196">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-196">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="aa18d-197">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-197">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="aa18d-198">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-198">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="aa18d-199">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-199">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="aa18d-200">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-200">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="aa18d-201">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-201">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="aa18d-202">`powershell-lts-7.0.0-1.rhel.7.x86_64.rpm`リリース[ ページから Ubuntu コンピューターに Debian パッケージ ][] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-202">Download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="aa18d-203">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-203">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="aa18d-204">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-204">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="aa18d-205">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-205">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="aa18d-206">openSUSE</span><span class="sxs-lookup"><span data-stu-id="aa18d-206">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="aa18d-207">インストール - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="aa18d-207">Installation - openSUSE 42.3</span></span>

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="aa18d-208">インストール - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="aa18d-208">Installation - openSUSE Leap 15</span></span>

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="aa18d-209">アンインストール - openSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="aa18d-209">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="aa18d-210">Fedora</span><span class="sxs-lookup"><span data-stu-id="aa18d-210">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-211">Fedora 28 は、PowerShell 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-211">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-212">Fedora 29 および 30 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-212">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="aa18d-213">パッケージ リポジトリによるインストール (推奨) - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="aa18d-213">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="aa18d-214">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-214">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="aa18d-215">直接ダウンロードによるインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="aa18d-215">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="aa18d-216">`powershell-7.0.0-1.rhel.7.x86_64.rpm`リリース[ ページから Ubuntu コンピューターに Debian パッケージ ][] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-216">Download the RPM package `powershell-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="aa18d-217">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-217">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="aa18d-218">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-218">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="aa18d-219">アンインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="aa18d-219">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="aa18d-220">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="aa18d-220">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-221">Arch のサポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-221">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="aa18d-222">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-222">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="aa18d-223">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="aa18d-223">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="aa18d-224">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="aa18d-224">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="aa18d-225">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="aa18d-225">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="aa18d-226">AUR のパッケージはコミュニティによって管理されています。公式のサポートは存在しません。</span><span class="sxs-lookup"><span data-stu-id="aa18d-226">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="aa18d-227">AUR からパッケージをインストールする方法については、[Arch Linux の wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) か「[Docker での PowerShell の使用](powershell-in-docker.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa18d-227">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="aa18d-229">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="aa18d-229">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="aa18d-230">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="aa18d-230">Getting snapd</span></span>

<span data-ttu-id="aa18d-231">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa18d-231">`snapd` is required to run snaps.</span></span> <span data-ttu-id="aa18d-232">[ がインストールされているかどうかを確認するには、](https://docs.snapcraft.io/core/install)こちらの手順`snapd`を使用してください。</span><span class="sxs-lookup"><span data-stu-id="aa18d-232">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="aa18d-233">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="aa18d-233">Installation via Snap</span></span>

<span data-ttu-id="aa18d-234">Linux 向けの PowerShell は、インストールと更新を容易にするために [Snap ストア](https://snapcraft.io/store)に公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-234">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="aa18d-235">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-235">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="aa18d-236">プレビュー バージョンをインストールするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-236">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="aa18d-237">インストールしたら、Snap は自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-237">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="aa18d-238">`sudo snap refresh powershell` または `sudo snap refresh powershell-preview` を使って、アップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-238">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="aa18d-239">アンインストール</span><span class="sxs-lookup"><span data-stu-id="aa18d-239">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="aa18d-240">or</span><span class="sxs-lookup"><span data-stu-id="aa18d-240">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="aa18d-241">Kali</span><span class="sxs-lookup"><span data-stu-id="aa18d-241">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-242">Kali サポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-242">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="aa18d-243">インストール - Kali</span><span class="sxs-lookup"><span data-stu-id="aa18d-243">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="aa18d-244">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="aa18d-244">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="aa18d-245">Raspbian</span><span class="sxs-lookup"><span data-stu-id="aa18d-245">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="aa18d-246">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="aa18d-246">Raspbian support is experimental.</span></span>

<span data-ttu-id="aa18d-247">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-247">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="aa18d-248">CoreCLR と PowerShell は、Pi 2 および Pi 3 デバイス上でのみ動作します。[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスには、サポート外のプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-248">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="aa18d-249">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="aa18d-249">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="aa18d-250">インストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="aa18d-250">Installation - Raspbian</span></span>

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

<span data-ttu-id="aa18d-251">必要に応じて、`pwsh` バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="aa18d-251">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="aa18d-252">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="aa18d-252">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="aa18d-253">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="aa18d-253">Install as a .NET Global tool</span></span>

<span data-ttu-id="aa18d-254">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-254">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="aa18d-255">dotnet tool install によって、`~/.dotnet/tools` 環境変数に `PATH` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="aa18d-255">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="aa18d-256">ただし、現在実行中のシェルには更新された `PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="aa18d-256">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="aa18d-257">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できるはずです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-257">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="aa18d-258">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="aa18d-258">Binary Archives</span></span>

<span data-ttu-id="aa18d-259">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-259">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="aa18d-260">依存関係</span><span class="sxs-lookup"><span data-stu-id="aa18d-260">Dependencies</span></span>

<span data-ttu-id="aa18d-261">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="aa18d-261">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="aa18d-262">ただし、.NET Core ランタイムにはディストリビューションごとに異なる依存関係が必要であり、PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-262">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="aa18d-263">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="aa18d-263">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="aa18d-264">OS</span><span class="sxs-lookup"><span data-stu-id="aa18d-264">OS</span></span>                 | <span data-ttu-id="aa18d-265">依存関係</span><span class="sxs-lookup"><span data-stu-id="aa18d-265">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="aa18d-266">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-266">Ubuntu 16.04</span></span>       | <span data-ttu-id="aa18d-267">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="aa18d-267">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="aa18d-268">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="aa18d-268">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="aa18d-269">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="aa18d-269">Ubuntu 17.10</span></span>       | <span data-ttu-id="aa18d-270">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="aa18d-270">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="aa18d-271">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="aa18d-271">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="aa18d-272">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="aa18d-272">Ubuntu 18.04</span></span>       | <span data-ttu-id="aa18d-273">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="aa18d-273">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="aa18d-274">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="aa18d-274">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="aa18d-275">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="aa18d-275">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="aa18d-276">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="aa18d-276">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="aa18d-277">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="aa18d-277">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="aa18d-278">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="aa18d-278">Debian 9 (Stretch)</span></span> | <span data-ttu-id="aa18d-279">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="aa18d-279">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="aa18d-280">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="aa18d-280">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="aa18d-281">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-281">CentOS 7</span></span> <br> <span data-ttu-id="aa18d-282">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-282">Oracle Linux 7</span></span> <br> <span data-ttu-id="aa18d-283">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="aa18d-283">RHEL 7</span></span> | <span data-ttu-id="aa18d-284">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="aa18d-284">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="aa18d-285">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="aa18d-285">openSUSE 42.3</span></span> | <span data-ttu-id="aa18d-286">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="aa18d-286">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="aa18d-287">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="aa18d-287">openSUSE Leap 15</span></span> | <span data-ttu-id="aa18d-288">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="aa18d-288">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="aa18d-289">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="aa18d-289">Fedora 27</span></span> <br> <span data-ttu-id="aa18d-290">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="aa18d-290">Fedora 28</span></span> | <span data-ttu-id="aa18d-291">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="aa18d-291">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="aa18d-292">公式にサポートされていない Linux ディストリビューションに PowerShell バイナリを展開するには、別の手順によってターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa18d-292">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="aa18d-293">たとえば、[Amazon Linux Dockerfile][amazon-dockerfile] では依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="aa18d-293">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="aa18d-294">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="aa18d-294">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="aa18d-295">Linux</span><span class="sxs-lookup"><span data-stu-id="aa18d-295">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="aa18d-296">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="aa18d-296">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="aa18d-297">パス</span><span class="sxs-lookup"><span data-stu-id="aa18d-297">Paths</span></span>

- <span data-ttu-id="aa18d-298">`$PSHOME` は `/opt/microsoft/powershell/7/` です</span><span class="sxs-lookup"><span data-stu-id="aa18d-298">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="aa18d-299">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="aa18d-299">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="aa18d-300">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="aa18d-300">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="aa18d-301">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="aa18d-301">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="aa18d-302">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="aa18d-302">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="aa18d-303">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="aa18d-303">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="aa18d-304">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="aa18d-304">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="aa18d-305">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="aa18d-305">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="aa18d-306">PowerShell では、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="aa18d-306">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[ ページから Ubuntu コンピューターに Debian パッケージ ]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
