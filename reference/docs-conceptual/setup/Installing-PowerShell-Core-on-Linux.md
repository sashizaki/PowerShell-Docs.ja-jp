---
title: Linux への PowerShell Core のインストール
description: さまざまな Linux ディストリビューションへの PowerShell Core のインストールに関する情報
ms.date: 08/06/2018
ms.openlocfilehash: a6b0e3003f84ea6dc99cffcc7edf1b5b6963aa21
ms.sourcegitcommit: 01ac77cd0b00e4e5e964504563a9212e8002e5e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39587450"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="711c5-103">Linux への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="711c5-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="711c5-104">[Ubuntu 14.04][u14]、[Ubuntu 16.04][u16]、[Ubuntu 18.10][u18]、[Debian 8][deb8]、[Debian 9][deb9]、[CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[OpenSUSE 42.3][opensuse]、[Fedora 27][fedora]、[Fedora 28][fedora]、[Arch Linux][arch] をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="711c5-104">Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 18.10][u18], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [OpenSUSE 42.3][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="711c5-105">公式にサポートしていない Linux ディストリビューションの場合、[PowerShell Snap パッケージ][snap]を利用できます。</span><span class="sxs-lookup"><span data-stu-id="711c5-105">For Linux distributions that are not officially supported, you can try using the [PowerShell Snap Package][snap].</span></span>
<span data-ttu-id="711c5-106">また、Linux [`tar.gz` アーカイブ][tar]で直接、PowerShell バイナリを展開できます。ただし、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="711c5-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="711c5-107">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="711c5-107">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="711c5-108">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-108">Once the package is installed, run `pwsh` from a terminal.</span></span>

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

## <a name="installing-preview-releases"></a><span data-ttu-id="711c5-109">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="711c5-109">Installing Preview Releases</span></span>

<span data-ttu-id="711c5-110">パッケージ リポジトリを介して、Linux 用の PowerShell Core Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="711c5-110">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="711c5-111">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="711c5-111">Installing via direct download does not change, other than the file name.</span></span>

<span data-ttu-id="711c5-112">さまざまなパッケージ マネージャーを使用して、安定したパッケージとプレビュー パッケージをインストールするためのコマンドを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="711c5-112">Here is a table of the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="711c5-113">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="711c5-113">Distribution(s)</span></span>|<span data-ttu-id="711c5-114">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="711c5-114">Stable Command</span></span> | <span data-ttu-id="711c5-115">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="711c5-115">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="711c5-116">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="711c5-116">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="711c5-117">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="711c5-117">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="711c5-118">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="711c5-118">OpenSUSE</span></span> |`sudo zypper install powershell` | `sudo zypper install powershell-preview`|
| <span data-ttu-id="711c5-119">Fedora</span><span class="sxs-lookup"><span data-stu-id="711c5-119">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1404"></a><span data-ttu-id="711c5-120">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="711c5-120">Ubuntu 14.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1404"></a><span data-ttu-id="711c5-121">パッケージ リポジトリによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="711c5-121">Installation via Package Repository - Ubuntu 14.04</span></span>

<span data-ttu-id="711c5-122">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-122">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="711c5-123">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="711c5-123">This is the preferred method.</span></span>

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
curl https://packages.microsoft.com/config/ubuntu/14.04/prod.list | sudo tee /etc/apt/sources.list.d/microsoft.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="711c5-124">スーパーユーザーとして Microsoft リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="711c5-124">As superuser, register the Microsoft repository.</span></span>
<span data-ttu-id="711c5-125">以降は、インストールの更新に `sudo apt-get upgrade powershell` を使用するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="711c5-125">From then on, you just need to use `sudo apt-get upgrade powershell` to update the installation.</span></span>

### <a name="installation-via-direct-download---ubuntu-1404"></a><span data-ttu-id="711c5-126">直接ダウンロードによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="711c5-126">Installation via Direct Download - Ubuntu 14.04</span></span>

<span data-ttu-id="711c5-127">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.0.2-1.ubuntu.14.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-127">Download the Debian package `powershell_6.0.2-1.ubuntu.14.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="711c5-128">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-128">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="711c5-129">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="711c5-129">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="711c5-130">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="711c5-130">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1404"></a><span data-ttu-id="711c5-131">アンインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="711c5-131">Uninstallation - Ubuntu 14.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a><span data-ttu-id="711c5-132">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="711c5-132">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="711c5-133">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="711c5-133">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="711c5-134">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-134">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="711c5-135">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="711c5-135">This is the preferred method.</span></span>

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
sudo curl -o /etc/apt/sources.list.d/microsoft.list https://packages.microsoft.com/config/ubuntu/16.04/prod.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="711c5-136">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="711c5-136">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="711c5-137">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="711c5-137">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="711c5-138">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.0.2-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-138">Download the Debian package `powershell_6.0.2-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="711c5-139">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-139">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="711c5-140">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="711c5-140">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="711c5-141">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="711c5-141">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="711c5-142">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="711c5-142">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="711c5-143">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="711c5-143">Ubuntu 18.04</span></span>

> [!NOTE]
> <span data-ttu-id="711c5-144">Ubuntu 18.04 のサポートは `6.1.0-preview.2` 以降に追加されました。</span><span class="sxs-lookup"><span data-stu-id="711c5-144">Support for Ubuntu 18.04 was added after `6.1.0-preview.2`</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="711c5-145">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="711c5-145">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="711c5-146">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-146">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="711c5-147">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="711c5-147">This is the preferred method.</span></span>

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
sudo curl -o /etc/apt/sources.list.d/microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell-preview

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="711c5-148">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="711c5-148">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="711c5-149">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="711c5-149">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="711c5-150">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.1.0-preview.3-1.ubuntu.18.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-150">Download the Debian package `powershell_6.1.0-preview.3-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="711c5-151">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-151">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-preview.3-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="711c5-152">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="711c5-152">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="711c5-153">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="711c5-153">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="711c5-154">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="711c5-154">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="711c5-155">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="711c5-155">Ubuntu 18.10</span></span>

> [!NOTE]
> <span data-ttu-id="711c5-156">Ubuntu 18.10 のサポートは `6.1.0-preview.3` 以降に追加されました。</span><span class="sxs-lookup"><span data-stu-id="711c5-156">Support for Ubuntu 18.10 was added after `6.1.0-preview.3`.</span></span>
> <span data-ttu-id="711c5-157">18.10 はデイリー ビルドであるため、コミュニティのサポートのみです。</span><span class="sxs-lookup"><span data-stu-id="711c5-157">As 18.10 is a daily build, it is only community supported.</span></span>

<span data-ttu-id="711c5-158">18.10 へのインストールは `snapd` を使用してサポートされます。</span><span class="sxs-lookup"><span data-stu-id="711c5-158">Installing on 18.10 is supported via `snapd`.</span></span> <span data-ttu-id="711c5-159">完全な手順については、「[Snap パッケージ][snap]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="711c5-159">See [Snap Package][snap] for full instructions;</span></span>

## <a name="debian-8"></a><span data-ttu-id="711c5-160">Debian 8</span><span class="sxs-lookup"><span data-stu-id="711c5-160">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="711c5-161">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="711c5-161">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="711c5-162">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-162">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="711c5-163">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="711c5-163">This is the preferred method.</span></span>

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

<span data-ttu-id="711c5-164">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="711c5-164">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-8"></a><span data-ttu-id="711c5-165">直接ダウンロードによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="711c5-165">Installation via Direct Download - Debian 8</span></span>

<span data-ttu-id="711c5-166">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_6.0.2-1.debian.8_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-166">Download the Debian package `powershell_6.0.2-1.debian.8_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="711c5-167">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-167">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.debian.8_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="711c5-168">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="711c5-168">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="711c5-169">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="711c5-169">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---debian-8"></a><span data-ttu-id="711c5-170">アンインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="711c5-170">Uninstallation - Debian 8</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-9"></a><span data-ttu-id="711c5-171">Debian 9</span><span class="sxs-lookup"><span data-stu-id="711c5-171">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="711c5-172">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="711c5-172">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="711c5-173">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-173">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="711c5-174">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="711c5-174">This is the preferred method.</span></span>

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

<span data-ttu-id="711c5-175">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="711c5-175">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="711c5-176">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="711c5-176">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="711c5-177">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_6.0.2-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-177">Download the Debian package `powershell_6.0.2-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="711c5-178">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-178">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="711c5-179">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="711c5-179">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="711c5-180">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="711c5-180">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="711c5-181">このパッケージは Oracle Linux 7 でも動作します。</span><span class="sxs-lookup"><span data-stu-id="711c5-181">This package also works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="711c5-182">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="711c5-182">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="711c5-183">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-183">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="711c5-184">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="711c5-184">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="711c5-185">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="711c5-185">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="711c5-186">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-6.0.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-186">Using [CentOS 7][], download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="711c5-187">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-187">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="711c5-188">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="711c5-188">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="711c5-189">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="711c5-189">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="711c5-191">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="711c5-191">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="711c5-192">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="711c5-192">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="711c5-193">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-193">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="711c5-194">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="711c5-194">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="711c5-195">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="711c5-195">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="711c5-196">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-6.0.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-196">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="711c5-197">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-197">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="711c5-198">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="711c5-198">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="711c5-199">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="711c5-199">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse-423"></a><span data-ttu-id="711c5-200">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="711c5-200">OpenSUSE 42.3</span></span>

<span data-ttu-id="711c5-201">PowerShell Core をインストールすると、`zypper` から次のエラーが報告されることがあります。</span><span class="sxs-lookup"><span data-stu-id="711c5-201">When installing PowerShell Core, `zypper` may report the following error:</span></span>

```Output
Problem: nothing provides libcurl needed by powershell-6.0.1-1.rhel.7.x86_64
 Solution 1: do not install powershell-6.0.1-1.rhel.7.x86_64
 Solution 2: break powershell-6.0.1-1.rhel.7.x86_64 by ignoring some of its dependencies
```

<span data-ttu-id="711c5-202">この場合、次のコマンドで `libcurl4` パッケージがインストール済みであることを確認して、互換性のある `libcurl` ライブラリが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="711c5-202">In this case, verify that a compatible `libcurl` library is present by checking that the following command shows the `libcurl4` package as installed:</span></span>

```sh
zypper search --file-list --match-exact '/usr/lib64/libcurl.so.4'
```

<span data-ttu-id="711c5-203">次に、PowerShell パッケージをインストールするときに `break powershell-6.0.1-1.rhel.7.x86_64 by ignoring some of its dependencies` ソリューションを選択します。</span><span class="sxs-lookup"><span data-stu-id="711c5-203">Then choose the `break powershell-6.0.1-1.rhel.7.x86_64 by ignoring some of its dependencies` solution when installing the PowerShell package.</span></span>

### <a name="installation-via-package-repository-preferred---opensuse-423"></a><span data-ttu-id="711c5-204">パッケージ リポジトリによるインストール (推奨) - OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="711c5-204">Installation via Package Repository (preferred) - OpenSUSE 42.3</span></span>

<span data-ttu-id="711c5-205">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-205">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---opensuse-423"></a><span data-ttu-id="711c5-206">直接ダウンロードによるインストール - OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="711c5-206">Installation via Direct Download - OpenSUSE 42.3</span></span>

<span data-ttu-id="711c5-207">[リリース][] ページから OpenSUSE コンピューターに RPM パッケージ `powershell-6.0.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-207">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the OpenSUSE machine.</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="711c5-208">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="711c5-208">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---opensuse-423"></a><span data-ttu-id="711c5-209">アンインストール - OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="711c5-209">Uninstallation - OpenSUSE 42.3</span></span>

```sh
sudo zypper remove powershell
```

## <a name="fedora"></a><span data-ttu-id="711c5-210">Fedora</span><span class="sxs-lookup"><span data-stu-id="711c5-210">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="711c5-211">Fedora 28 は、PowerShell Core 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="711c5-211">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a><span data-ttu-id="711c5-212">パッケージ リポジトリによるインストール (推奨) - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="711c5-212">Installation via Package Repository (preferred) - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="711c5-213">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-213">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a><span data-ttu-id="711c5-214">直接ダウンロードによるインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="711c5-214">Installation via Direct Download - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="711c5-215">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-6.0.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-215">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="711c5-216">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-216">Then execute the following in the terminal:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="711c5-217">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="711c5-217">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a><span data-ttu-id="711c5-218">アンインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="711c5-218">Uninstallation - Fedora 27, Fedora 28</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="711c5-219">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="711c5-219">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="711c5-220">Arch のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="711c5-220">Arch support is experimental.</span></span>

<span data-ttu-id="711c5-221">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="711c5-221">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="711c5-222">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="711c5-222">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="711c5-223">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="711c5-223">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="711c5-224">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="711c5-224">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="711c5-225">AUR のパッケージはコミュニティにより保守管理されています。公式のサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="711c5-225">Packages in the AUR are community maintained - there is no official support.</span></span>

<span data-ttu-id="711c5-226">AUR からパッケージをインストールする方法については、[Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) かコミュニティ [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="711c5-226">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="711c5-228">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="711c5-228">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="711c5-229">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="711c5-229">Getting snapd</span></span>

<span data-ttu-id="711c5-230">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="711c5-230">`snapd` is required to run snaps.</span></span>  <span data-ttu-id="711c5-231">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="711c5-231">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="711c5-232">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="711c5-232">Installation via Snap</span></span>

<span data-ttu-id="711c5-233">Linux 向け PowerShell Core は [Snap ストア](https://snapcraft.io/store)に公開されるため、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="711c5-233">PowerShell Core, for Linux, is published to the [Snap store](https://snapcraft.io/store) for easy installation (and updates).</span></span>
<span data-ttu-id="711c5-234">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="711c5-234">This is the preferred method.</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="711c5-235">Snap のインストールが自動的にアップグレードされた後も、`sudo snap refresh powershell-preview` を使用してアップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="711c5-235">After installing Snap will automatically upgrade, but you can trigger an upgrade using `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="711c5-236">アンインストール</span><span class="sxs-lookup"><span data-stu-id="711c5-236">Uninstallation</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="linux-appimage"></a><span data-ttu-id="711c5-237">Linux AppImage</span><span class="sxs-lookup"><span data-stu-id="711c5-237">Linux AppImage</span></span>

> [!NOTE]
> <span data-ttu-id="711c5-238">AppImage のサポートは試験段階です</span><span class="sxs-lookup"><span data-stu-id="711c5-238">AppImage support is experimental</span></span>

<span data-ttu-id="711c5-239">最近の Linux ディストリビューションを利用し、[リリース][] ページから Linux コンピューターに AppImage `powershell-6.0.1-x86_64.AppImage` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="711c5-239">Using a recent Linux distribution, download the AppImage `powershell-6.0.1-x86_64.AppImage` from the [releases][] page onto the Linux machine.</span></span>

<span data-ttu-id="711c5-240">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="711c5-240">Then execute the following in the terminal:</span></span>

```bash
chmod a+x powershell-6.0.1-x86_64.AppImage
./powershell-6.0.1-x86_64.AppImage
```

<span data-ttu-id="711c5-241">[AppImage][] では、インストールしなくても PowerShell を実行できます。</span><span class="sxs-lookup"><span data-stu-id="711c5-241">The [AppImage][] lets you run PowerShell without installing it.</span></span>
<span data-ttu-id="711c5-242">これは PowerShell とその依存関係 (.NET Core のシステム依存関係を含む) を 1 つのまとまったパッケージにバンドルする移植可能なアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="711c5-242">It is a portable application that bundles PowerShell and its dependencies (including .NET Core's system dependencies) into one cohesive package.</span></span>
<span data-ttu-id="711c5-243">このパッケージは、ユーザーの Linux ディストリビューションに依存せずに動作する 1 つのバイナリです。</span><span class="sxs-lookup"><span data-stu-id="711c5-243">This package is a single binary that works independently of the user's Linux distribution.</span></span>

[appimage]: http://appimage.org/

## <a name="kali"></a><span data-ttu-id="711c5-245">Kali</span><span class="sxs-lookup"><span data-stu-id="711c5-245">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="711c5-246">Kali のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="711c5-246">Kali support is experimental.</span></span>

### <a name="installation"></a><span data-ttu-id="711c5-247">インストール</span><span class="sxs-lookup"><span data-stu-id="711c5-247">Installation</span></span>

```sh
# Download & Install prerequisites
sudo apt-get install libunwind8 libicu55
wget http://security.debian.org/debian-security/pool/updates/main/o/openssl/libssl1.0.0_1.0.1t-1+deb8u6_amd64.deb
sudo dpkg -i libssl1.0.0_1.0.1t-1+deb8u6_amd64.deb

# Install PowerShell
sudo dpkg -i powershell_6.0.2-1.ubuntu.16.04_amd64.deb

# Start PowerShell
pwsh
```

### <a name="run-powershell-in-latest-kali-kali-gnulinux-rolling-without-installing-it"></a><span data-ttu-id="711c5-248">最新の Kali (Kali GNU/Linux Rolling) でインストールせずに PowerShell を実行する</span><span class="sxs-lookup"><span data-stu-id="711c5-248">Run PowerShell in latest Kali (Kali GNU/Linux Rolling) without installing it</span></span>

```sh
# Grab the latest App Image
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-x86_64.AppImage

# Make executable
chmod a+x powershell-6.0.2-x86_64.AppImage

# Start PowerShell
./powershell-6.0.2-x86_64.AppImage
```

### <a name="uninstallation---kali"></a><span data-ttu-id="711c5-249">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="711c5-249">Uninstallation - Kali</span></span>

```sh
sudo dpkg -r powershell_6.0.2-1.ubuntu.16.04_amd64.deb
```

## <a name="raspbian"></a><span data-ttu-id="711c5-250">Raspbian</span><span class="sxs-lookup"><span data-stu-id="711c5-250">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="711c5-251">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="711c5-251">Raspbian support is experimental.</span></span>

<span data-ttu-id="711c5-252">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="711c5-252">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="711c5-253">また、Core CLR (と PowerShell Core) は Pi 2 および Pi 3 デバイス上でのみ動作します。これは、[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスにはサポートされていないプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="711c5-253">Also CoreCLR (and thus PowerShell Core) will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="711c5-254">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="711c5-254">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation"></a><span data-ttu-id="711c5-255">インストール</span><span class="sxs-lookup"><span data-stu-id="711c5-255">Installation</span></span>

```sh
# Install prerequisites
sudo apt-get install libunwind8

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.0.2-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="711c5-256">必要に応じて、"pwsh" バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="711c5-256">Optionally you can create a symbolic link to be able to start PowerShell without specifying path to the "pwsh" binary</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="711c5-257">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="711c5-257">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="711c5-258">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="711c5-258">Binary Archives</span></span>

<span data-ttu-id="711c5-259">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="711c5-259">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="711c5-260">依存関係</span><span class="sxs-lookup"><span data-stu-id="711c5-260">Dependencies</span></span>

<span data-ttu-id="711c5-261">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="711c5-261">PowerShell builds portable binaries for all Linux distributions.</span></span>
<span data-ttu-id="711c5-262">ただし、.NET Core ランタイムはディストリビューションごとに異なる依存関係を必要とします。PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="711c5-262">But .NET Core runtime requires different dependencies on different distributions, and hence PowerShell does the same.</span></span>

<span data-ttu-id="711c5-263">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="711c5-263">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="711c5-264">OS</span><span class="sxs-lookup"><span data-stu-id="711c5-264">OS</span></span>                 | <span data-ttu-id="711c5-265">依存関係</span><span class="sxs-lookup"><span data-stu-id="711c5-265">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="711c5-266">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="711c5-266">Ubuntu 14.04</span></span>       | <span data-ttu-id="711c5-267">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="711c5-267">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="711c5-268">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="711c5-268">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="711c5-269">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="711c5-269">Ubuntu 16.04</span></span>       | <span data-ttu-id="711c5-270">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="711c5-270">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="711c5-271">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="711c5-271">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="711c5-272">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="711c5-272">Ubuntu 17.10</span></span>       | <span data-ttu-id="711c5-273">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="711c5-273">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="711c5-274">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="711c5-274">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="711c5-275">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="711c5-275">Ubuntu 18.04</span></span>       | <span data-ttu-id="711c5-276">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="711c5-276">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="711c5-277">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="711c5-277">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="711c5-278">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="711c5-278">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="711c5-279">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="711c5-279">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="711c5-280">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="711c5-280">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="711c5-281">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="711c5-281">Debian 9 (Stretch)</span></span> | <span data-ttu-id="711c5-282">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="711c5-282">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="711c5-283">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="711c5-283">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="711c5-284">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="711c5-284">CentOS 7</span></span> <br> <span data-ttu-id="711c5-285">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="711c5-285">Oracle Linux 7</span></span> <br> <span data-ttu-id="711c5-286">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="711c5-286">RHEL 7</span></span> <br> <span data-ttu-id="711c5-287">OpenSUSE OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="711c5-287">OpenSUSE OpenSUSE 42.3</span></span> | <span data-ttu-id="711c5-288">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="711c5-288">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="711c5-289">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="711c5-289">Fedora 27</span></span> <br> <span data-ttu-id="711c5-290">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="711c5-290">Fedora 28</span></span> | <span data-ttu-id="711c5-291">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="711c5-291">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="711c5-292">公式にサポートされていない Linux ディストリビューションで PowerShell バイナリを展開するには、別の手順で、ターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="711c5-292">To deploy PowerShell binaries on Linux distributions that are not officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span>
<span data-ttu-id="711c5-293">たとえば、[Amazon Linux dockerfile][amazon-dockerfile] は依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="711c5-293">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell/blob/master/docker/community/amazonlinux/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="711c5-294">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="711c5-294">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="711c5-295">Linux</span><span class="sxs-lookup"><span data-stu-id="711c5-295">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/6.0.2

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.0.2

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/6.0.2/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/6.0.2/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="711c5-296">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="711c5-296">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="711c5-297">パス</span><span class="sxs-lookup"><span data-stu-id="711c5-297">Paths</span></span>

* <span data-ttu-id="711c5-298">`$PSHOME` は `/opt/microsoft/powershell/6.0.2/` です</span><span class="sxs-lookup"><span data-stu-id="711c5-298">`$PSHOME` is `/opt/microsoft/powershell/6.0.2/`</span></span>
* <span data-ttu-id="711c5-299">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="711c5-299">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="711c5-300">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="711c5-300">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="711c5-301">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="711c5-301">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="711c5-302">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="711c5-302">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="711c5-303">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="711c5-303">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="711c5-304">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="711c5-304">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="711c5-305">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="711c5-305">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="711c5-306">PowerShell は、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="711c5-306">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
