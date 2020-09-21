---
title: Linux への PowerShell のインストール
description: さまざまな Linux ディストリビューションへの PowerShell のインストールに関する情報
ms.date: 07/30/2020
ms.openlocfilehash: ce69f75416eb326e38d42991a4ae85a3a7298c5d
ms.sourcegitcommit: 79d430fe48ad77a058f42b6bc9955d21b657987e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "87441764"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="051c3-103">Linux への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="051c3-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="051c3-104">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="051c3-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="051c3-105">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="051c3-106">[プレビュー リリース](#installing-preview-releases)をインストールした場合は、`pwsh-preview` を実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-107">PowerShell 7 はインプレース アップグレードで、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="051c3-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="051c3-108">`/usr/local/microsoft/powershell/6` フォルダーは `/usr/local/microsoft/powershell/7` に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="051c3-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="051c3-109">PowerShell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[バイナリ アーカイブ](#binary-archives)方法を使用して PowerShell 6 を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="051c3-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="051c3-110">公式にサポートされていない Linux ディストリビューションの場合は、[PowerShell の Snap パッケージ][snap]を使った PowerShell のインストールを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="051c3-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="051c3-111">また、Linux [`tar.gz` アーカイブ][tar]を使用して、直接 PowerShell バイナリを展開できますが、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="051c3-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<span data-ttu-id="051c3-112">正式にサポートされているリリース</span><span class="sxs-lookup"><span data-stu-id="051c3-112">Officially supported releases</span></span>

- <span data-ttu-id="051c3-113">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="051c3-113">Ubuntu 16.04</span></span>
- <span data-ttu-id="051c3-114">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="051c3-114">Ubuntu 18.04</span></span>
- <span data-ttu-id="051c3-115">Debian 8</span><span class="sxs-lookup"><span data-stu-id="051c3-115">Debian 8</span></span>
- <span data-ttu-id="051c3-116">Debian 9</span><span class="sxs-lookup"><span data-stu-id="051c3-116">Debian 9</span></span>
- <span data-ttu-id="051c3-117">Debian 10</span><span class="sxs-lookup"><span data-stu-id="051c3-117">Debian 10</span></span>
- <span data-ttu-id="051c3-118">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="051c3-118">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="051c3-119">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="051c3-119">CentOS 7</span></span>
- <span data-ttu-id="051c3-120">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="051c3-120">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="051c3-121">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="051c3-121">Fedora 28</span></span>
- <span data-ttu-id="051c3-122">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="051c3-122">Fedora 29</span></span>
- <span data-ttu-id="051c3-123">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="051c3-123">Fedora 30</span></span>
- <span data-ttu-id="051c3-124">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="051c3-124">openSUSE 42.3</span></span>
- <span data-ttu-id="051c3-125">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="051c3-125">openSUSE Leap 15</span></span>

<span data-ttu-id="051c3-126">コミュニティでサポートされているリリース</span><span class="sxs-lookup"><span data-stu-id="051c3-126">Community supported releases</span></span>

- <span data-ttu-id="051c3-127">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="051c3-127">Ubuntu 18.10</span></span>
- <span data-ttu-id="051c3-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="051c3-128">Ubuntu 19.04</span></span>
- <span data-ttu-id="051c3-129">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="051c3-129">Arch Linux</span></span>
- <span data-ttu-id="051c3-130">Kali</span><span class="sxs-lookup"><span data-stu-id="051c3-130">Kali</span></span>
- <span data-ttu-id="051c3-131">Raspbian (試験段階)</span><span class="sxs-lookup"><span data-stu-id="051c3-131">Raspbian (experimental)</span></span>

<span data-ttu-id="051c3-132">代替のインストール方法</span><span class="sxs-lookup"><span data-stu-id="051c3-132">Alternate install methods</span></span>

- <span data-ttu-id="051c3-133">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="051c3-133">Snap Package</span></span>
- <span data-ttu-id="051c3-134">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="051c3-134">Binary Archives</span></span>
- <span data-ttu-id="051c3-135">.NET グローバル ツール</span><span class="sxs-lookup"><span data-stu-id="051c3-135">.NET Global tool</span></span>

<span data-ttu-id="051c3-136">現在、サポートされていません</span><span class="sxs-lookup"><span data-stu-id="051c3-136">Not currently supported</span></span>

- <span data-ttu-id="051c3-137">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="051c3-137">Ubuntu 20.04</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-138">PowerShell は、.NET でサポートされているディストリビューションのみをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="051c3-138">PowerShell can only support the distributions that are supported by .NET.</span></span> <span data-ttu-id="051c3-139">サポートされているディストリビューションの一覧については、[.NET Core リリース ノート][distros]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="051c3-139">See the [.NET Core release notes][distros] for a list of supported distributions.</span></span> <span data-ttu-id="051c3-140">この一覧に記載されていない、.NET でサポートされているディストリビューションがある場合は、そのディストリビューションのサポートの追加を要求できます。</span><span class="sxs-lookup"><span data-stu-id="051c3-140">If there is a distrbution supported by .NET that is not listed here, you can request that support for the distribution be added.</span></span> <span data-ttu-id="051c3-141">[ディストリビューション サポート リクエスト][] テンプレートを使用して、要求を提出してください。</span><span class="sxs-lookup"><span data-stu-id="051c3-141">Please file a request using the [Distribution Support Request][] template.</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="051c3-142">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="051c3-142">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="051c3-143">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="051c3-143">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="051c3-144">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-144">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="051c3-145">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="051c3-145">The preferred method is as follows:</span></span>

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

<span data-ttu-id="051c3-146">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="051c3-146">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="051c3-147">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="051c3-147">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="051c3-148">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="051c3-148">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="051c3-149">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell-lts_7.0.3-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="051c3-149">Download the Debian package `powershell-lts_7.0.3-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="051c3-150">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-150">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.3-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="051c3-151">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="051c3-151">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="051c3-152">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="051c3-152">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="051c3-153">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="051c3-153">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="051c3-154">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="051c3-154">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="051c3-155">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="051c3-155">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="051c3-156">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-156">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="051c3-157">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="051c3-157">The preferred method is as follows:</span></span>

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

<span data-ttu-id="051c3-158">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="051c3-158">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="051c3-159">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="051c3-159">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="051c3-160">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="051c3-160">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="051c3-161">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell-lts_7.0.3-1.ubuntu.18.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="051c3-161">Download the Debian package `powershell-lts_7.0.3-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="051c3-162">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-162">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.3-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="051c3-163">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="051c3-163">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="051c3-164">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="051c3-164">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="051c3-165">アンインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="051c3-165">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="051c3-166">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="051c3-166">Ubuntu 18.10</span></span>

<span data-ttu-id="051c3-167">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="051c3-167">Installation is supported via `snapd`.</span></span> <span data-ttu-id="051c3-168">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="051c3-168">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-169">Ubuntu 18.10 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="051c3-169">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="051c3-170">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="051c3-170">Ubuntu 19.04</span></span>

<span data-ttu-id="051c3-171">`snapd` によるインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="051c3-171">Installation is supported via `snapd`.</span></span> <span data-ttu-id="051c3-172">手順については、「[Snap パッケージ][snap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="051c3-172">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-173">Ubuntu 19.04 は、[コミュニティでサポートされている](../powershell-support-lifecycle.md)[中間リリース](https://www.ubuntu.com/about/release-cycle)です。</span><span class="sxs-lookup"><span data-stu-id="051c3-173">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-2004"></a><span data-ttu-id="051c3-174">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="051c3-174">Ubuntu 20.04</span></span>

<span data-ttu-id="051c3-175">Ubuntu 20.04 は LTS リリースです。</span><span class="sxs-lookup"><span data-stu-id="051c3-175">Ubuntu 20.04 is an LTS release.</span></span> <span data-ttu-id="051c3-176">現在、PowerShell はこのバージョンをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="051c3-176">PowerShell does not currently support this version.</span></span> <span data-ttu-id="051c3-177">このバージョンのサポートは、PowerShell 7.1 リリースで考慮されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-177">Support for this version is being considered for the PowerShell 7.1 release.</span></span> <span data-ttu-id="051c3-178">Ubuntu 20.04 のサポートを希望する場合は、この[要求](https://github.com/PowerShell/PowerShell/issues/12626)にご投票ください。</span><span class="sxs-lookup"><span data-stu-id="051c3-178">Please upvote this [request](https://github.com/PowerShell/PowerShell/issues/12626) if you would like support for Ubuntu 20.04.</span></span>

## <a name="debian-8"></a><span data-ttu-id="051c3-179">Debian 8</span><span class="sxs-lookup"><span data-stu-id="051c3-179">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="051c3-180">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="051c3-180">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="051c3-181">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-181">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="051c3-182">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="051c3-182">The preferred method is as follows:</span></span>

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

<span data-ttu-id="051c3-183">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="051c3-183">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="051c3-184">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="051c3-184">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="051c3-185">Debian 9</span><span class="sxs-lookup"><span data-stu-id="051c3-185">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="051c3-186">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="051c3-186">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="051c3-187">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-187">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="051c3-188">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="051c3-188">The preferred method is as follows:</span></span>

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

<span data-ttu-id="051c3-189">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="051c3-189">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="051c3-190">登録後は、`sudo apt-get install powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="051c3-190">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="051c3-191">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="051c3-191">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="051c3-192">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell-lts_7.0.3-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="051c3-192">Download the Debian package `powershell-lts_7.0.3-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="051c3-193">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-193">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.3-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="051c3-194">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="051c3-194">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="051c3-195">Debian 10</span><span class="sxs-lookup"><span data-stu-id="051c3-195">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-196">Debian 10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="051c3-196">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="051c3-197">パッケージ リポジトリによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="051c3-197">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="051c3-198">Linux 向けの PowerShell は、インストールと更新を容易にするためにパッケージ リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-198">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="051c3-199">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="051c3-199">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="051c3-200">直接ダウンロードによるインストール - Debian 10</span><span class="sxs-lookup"><span data-stu-id="051c3-200">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="051c3-201">[リリース][] ページから Debian コンピューターに tar.gz パッケージ `powershell-7.0.3-linux-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="051c3-201">Download the tar.gz package `powershell-7.0.3-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="051c3-202">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-202">Then, in the terminal, execute the following commands:</span></span>

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
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="051c3-203">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="051c3-203">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-204">Alpine 3.9 および 3.10 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="051c3-204">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="051c3-205">直接ダウンロードによるインストール - Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="051c3-205">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="051c3-206">[リリース][] ページから Alpine コンピューターに tar.gz パッケージ `powershell-7.0.3-linux-alpine-x64.tar.gz` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="051c3-206">Download the tar.gz package `powershell-7.0.3-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="051c3-207">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-207">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="centos-7"></a><span data-ttu-id="051c3-208">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="051c3-208">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-209">このパッケージは Oracle Linux 7 で動作します。</span><span class="sxs-lookup"><span data-stu-id="051c3-209">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="051c3-210">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="051c3-210">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="051c3-211">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-211">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="051c3-212">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="051c3-212">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="051c3-213">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="051c3-213">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="051c3-214">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="051c3-214">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="051c3-215">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="051c3-215">Using [CentOS 7][], download the RPM package `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="051c3-216">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-216">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="051c3-217">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="051c3-217">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="051c3-218">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="051c3-218">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="051c3-220">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="051c3-220">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="051c3-221">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="051c3-221">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="051c3-222">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-222">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="051c3-223">スーパーユーザーとして、Microsoft リポジトリを 1 回登録します。</span><span class="sxs-lookup"><span data-stu-id="051c3-223">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="051c3-224">登録後は、`sudo yum update powershell` を使って PowerShell を更新できます。</span><span class="sxs-lookup"><span data-stu-id="051c3-224">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="051c3-225">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="051c3-225">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="051c3-226">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="051c3-226">Download the RPM package `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="051c3-227">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-227">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="051c3-228">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="051c3-228">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="051c3-229">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="051c3-229">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="051c3-230">openSUSE</span><span class="sxs-lookup"><span data-stu-id="051c3-230">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="051c3-231">インストール - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="051c3-231">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="051c3-232">インストール - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="051c3-232">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="051c3-233">アンインストール - openSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="051c3-233">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="051c3-234">Fedora</span><span class="sxs-lookup"><span data-stu-id="051c3-234">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-235">Fedora 28 は、PowerShell 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="051c3-235">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-236">Fedora 29 および 30 は、PowerShell 7.0 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="051c3-236">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="051c3-237">パッケージ リポジトリによるインストール (推奨) - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="051c3-237">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="051c3-238">Linux 向け PowerShell は、インストールと更新を容易にするために、公式の Microsoft リポジトリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-238">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="051c3-239">直接ダウンロードによるインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="051c3-239">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="051c3-240">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-7.0.3-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="051c3-240">Download the RPM package `powershell-7.0.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="051c3-241">次に、ターミナルで、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="051c3-241">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="051c3-242">ダウンロードという中間の手順なしで RPM をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="051c3-242">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="051c3-243">アンインストール - Fedora 28、29、および 30</span><span class="sxs-lookup"><span data-stu-id="051c3-243">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="051c3-244">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="051c3-244">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-245">Arch のサポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-245">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="051c3-246">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="051c3-246">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="051c3-247">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="051c3-247">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="051c3-248">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="051c3-248">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="051c3-249">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="051c3-249">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="051c3-250">AUR のパッケージはコミュニティによって管理されています。公式のサポートは存在しません。</span><span class="sxs-lookup"><span data-stu-id="051c3-250">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="051c3-251">AUR からパッケージをインストールする方法については、[Arch Linux の wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) か「[Docker での PowerShell の使用](powershell-in-docker.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="051c3-251">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="051c3-253">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="051c3-253">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="051c3-254">Snapd の取得</span><span class="sxs-lookup"><span data-stu-id="051c3-254">Getting snapd</span></span>

<span data-ttu-id="051c3-255">Snap を実行するには、`snapd` が必要です。</span><span class="sxs-lookup"><span data-stu-id="051c3-255">`snapd` is required to run snaps.</span></span> <span data-ttu-id="051c3-256">`snapd` がインストールされているかどうかを確認するには、[こちらの手順](https://docs.snapcraft.io/core/install)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="051c3-256">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="051c3-257">Snap を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="051c3-257">Installation via Snap</span></span>

<span data-ttu-id="051c3-258">Linux 向けの PowerShell は、インストールと更新を容易にするために [Snap ストア](https://snapcraft.io/store)に公開されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-258">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="051c3-259">推奨される方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="051c3-259">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="051c3-260">プレビュー バージョンをインストールするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="051c3-260">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="051c3-261">インストールしたら、Snap は自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="051c3-261">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="051c3-262">`sudo snap refresh powershell` または `sudo snap refresh powershell-preview` を使って、アップグレードをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="051c3-262">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="051c3-263">アンインストール</span><span class="sxs-lookup"><span data-stu-id="051c3-263">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="051c3-264">or</span><span class="sxs-lookup"><span data-stu-id="051c3-264">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="051c3-265">Kali</span><span class="sxs-lookup"><span data-stu-id="051c3-265">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-266">Kali サポートは、Microsoft では正式にサポートされておらず、コミュニティによって維持されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-266">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="051c3-267">インストール - Kali</span><span class="sxs-lookup"><span data-stu-id="051c3-267">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="051c3-268">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="051c3-268">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="051c3-269">Raspbian</span><span class="sxs-lookup"><span data-stu-id="051c3-269">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="051c3-270">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="051c3-270">Raspbian support is experimental.</span></span>

<span data-ttu-id="051c3-271">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="051c3-271">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="051c3-272">CoreCLR と PowerShell は、Pi 2 および Pi 3 デバイス上でのみ動作します。[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスには、サポート外のプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="051c3-272">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="051c3-273">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="051c3-273">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="051c3-274">インストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="051c3-274">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.0.3-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="051c3-275">必要に応じて、`pwsh` バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="051c3-275">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="051c3-276">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="051c3-276">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="051c3-277">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="051c3-277">Installing Preview Releases</span></span>

<span data-ttu-id="051c3-278">パッケージ リポジトリを介して、Linux 用の PowerShell Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="051c3-278">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="051c3-279">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="051c3-279">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="051c3-280">さまざまなパッケージ マネージャーを使用して安定版およびプレビュー版パッケージをインストールするためのコマンドを、以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="051c3-280">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="051c3-281">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="051c3-281">Distribution(s)</span></span> |            <span data-ttu-id="051c3-282">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="051c3-282">Stable Command</span></span>            |               <span data-ttu-id="051c3-283">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="051c3-283">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="051c3-284">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="051c3-284">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="051c3-285">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="051c3-285">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="051c3-286">Fedora</span><span class="sxs-lookup"><span data-stu-id="051c3-286">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="051c3-287">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="051c3-287">Install as a .NET Global tool</span></span>

<span data-ttu-id="051c3-288">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="051c3-288">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="051c3-289">dotnet tool install によって、`PATH` 環境変数に `~/.dotnet/tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="051c3-289">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="051c3-290">ただし、現在実行中のシェルには更新された `PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="051c3-290">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="051c3-291">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できるはずです。</span><span class="sxs-lookup"><span data-stu-id="051c3-291">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="051c3-292">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="051c3-292">Binary Archives</span></span>

<span data-ttu-id="051c3-293">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="051c3-293">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="051c3-294">依存関係</span><span class="sxs-lookup"><span data-stu-id="051c3-294">Dependencies</span></span>

<span data-ttu-id="051c3-295">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="051c3-295">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="051c3-296">ただし、.NET Core ランタイムにはディストリビューションごとに異なる依存関係が必要であり、PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="051c3-296">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="051c3-297">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="051c3-297">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="051c3-298">OS</span><span class="sxs-lookup"><span data-stu-id="051c3-298">OS</span></span>                 | <span data-ttu-id="051c3-299">依存関係</span><span class="sxs-lookup"><span data-stu-id="051c3-299">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="051c3-300">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="051c3-300">Ubuntu 16.04</span></span>       | <span data-ttu-id="051c3-301">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="051c3-301">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="051c3-302">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="051c3-302">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="051c3-303">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="051c3-303">Ubuntu 17.10</span></span>       | <span data-ttu-id="051c3-304">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="051c3-304">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="051c3-305">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="051c3-305">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="051c3-306">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="051c3-306">Ubuntu 18.04</span></span>       | <span data-ttu-id="051c3-307">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="051c3-307">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="051c3-308">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="051c3-308">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="051c3-309">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="051c3-309">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="051c3-310">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="051c3-310">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="051c3-311">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="051c3-311">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="051c3-312">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="051c3-312">Debian 9 (Stretch)</span></span> | <span data-ttu-id="051c3-313">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="051c3-313">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="051c3-314">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="051c3-314">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="051c3-315">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="051c3-315">CentOS 7</span></span> <br> <span data-ttu-id="051c3-316">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="051c3-316">Oracle Linux 7</span></span> <br> <span data-ttu-id="051c3-317">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="051c3-317">RHEL 7</span></span> | <span data-ttu-id="051c3-318">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="051c3-318">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="051c3-319">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="051c3-319">openSUSE 42.3</span></span> | <span data-ttu-id="051c3-320">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="051c3-320">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="051c3-321">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="051c3-321">openSUSE Leap 15</span></span> | <span data-ttu-id="051c3-322">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="051c3-322">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="051c3-323">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="051c3-323">Fedora 27</span></span> <br> <span data-ttu-id="051c3-324">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="051c3-324">Fedora 28</span></span> | <span data-ttu-id="051c3-325">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="051c3-325">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="051c3-326">公式にサポートされていない Linux ディストリビューションに PowerShell バイナリを展開するには、別の手順によってターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="051c3-326">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="051c3-327">たとえば、[Amazon Linux Dockerfile][amazon-dockerfile] では依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="051c3-327">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="051c3-328">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="051c3-328">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="051c3-329">Linux</span><span class="sxs-lookup"><span data-stu-id="051c3-329">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="051c3-330">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="051c3-330">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="051c3-331">パス</span><span class="sxs-lookup"><span data-stu-id="051c3-331">Paths</span></span>

- <span data-ttu-id="051c3-332">`$PSHOME` は `/opt/microsoft/powershell/7/` です</span><span class="sxs-lookup"><span data-stu-id="051c3-332">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="051c3-333">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="051c3-333">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="051c3-334">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="051c3-334">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="051c3-335">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="051c3-335">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="051c3-336">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="051c3-336">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="051c3-337">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="051c3-337">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="051c3-338">PSReadLine 履歴は、`~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="051c3-338">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="051c3-339">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="051c3-339">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="051c3-340">PowerShell では、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="051c3-340">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

## <a name="installation-support"></a><span data-ttu-id="051c3-341">インストールのサポート</span><span class="sxs-lookup"><span data-stu-id="051c3-341">Installation support</span></span>

<span data-ttu-id="051c3-342">Microsoft は、このドキュメントでインストール方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="051c3-342">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="051c3-343">他のソースには、利用可能な別のインストール方法が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="051c3-343">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="051c3-344">そのようなツールや方法が役に立つものであっても、Microsoft は、そのような方法をサポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="051c3-344">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[ディストリビューション サポート リクエスト]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
