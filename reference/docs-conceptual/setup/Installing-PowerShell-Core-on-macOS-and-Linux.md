# <a name="installing-powershell-core-on-macos-and-linux"></a><span data-ttu-id="d17d5-101">macOS および Linux への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="d17d5-101">Installing PowerShell Core on macOS and Linux</span></span>

<span data-ttu-id="d17d5-102">[Ubuntu 14.04][u14]、[Ubuntu 16.04][u16]、[Ubuntu 17.04][u17]、[Debian 8][deb8]、[Debian 9][deb9]、[CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[OpenSUSE 42.2][opensuse]、[Fedora 25][fed25]、[Fedora 26][fed26]、[Arch Linux][arch]、[macOS 10.12][mac] に対応しています。</span><span class="sxs-lookup"><span data-stu-id="d17d5-102">Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 17.04][u17], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [OpenSUSE 42.2][opensuse], [Fedora 25][fed25], [Fedora 26][fed26], [Arch Linux][arch], and [macOS 10.12][mac].</span></span>

<span data-ttu-id="d17d5-103">公式にサポートしていない Linux ディストリビューションの場合、[PowerShell AppImage][lai] を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-103">For Linux distributions that are not officially supported, you can try using the [PowerShell AppImage][lai].</span></span>
<span data-ttu-id="d17d5-104">また、Linux [`tar.gz` アーカイブ][tar]で直接、PowerShell バイナリを展開できます。ただし、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-104">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="d17d5-105">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="d17d5-106">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-106">Once the package is installed, run `pwsh` from a terminal.</span></span>

[u14]: #ubuntu-1404
[u16]: #ubuntu-1604
[u17]: #ubuntu-1704
[deb8]: #debian-8
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse-422
[fed25]: #fedora-25
[fed26]: #fedora-26
[arch]: #arch-linux
[lai]: #linux-appimage
[mac]: #macos-1012
[tar]: #binary-archives

## <a name="ubuntu-1404"></a><span data-ttu-id="d17d5-107">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-107">Ubuntu 14.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1404"></a><span data-ttu-id="d17d5-108">パッケージ リポジトリによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-108">Installation via Package Repository - Ubuntu 14.04</span></span>

<span data-ttu-id="d17d5-109">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-109">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="d17d5-110">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-110">This is the preferred method.</span></span>

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

<span data-ttu-id="d17d5-111">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-111">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1404"></a><span data-ttu-id="d17d5-112">直接ダウンロードによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-112">Installation via Direct Download - Ubuntu 14.04</span></span>

<span data-ttu-id="d17d5-113">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.0.0-rc-1.ubuntu.14.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-113">Download the Debian package `powershell_6.0.0-rc-1.ubuntu.14.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="d17d5-114">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-114">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.0-rc-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> <span data-ttu-id="d17d5-115">`dpkg -i` は依存関係が満たされずに失敗しますが、次のコマンド `apt-get install -f` で解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-115">Please note that `dpkg -i` will fail with unmet dependencies; the next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1404"></a><span data-ttu-id="d17d5-116">アンインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-116">Uninstallation - Ubuntu 14.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a><span data-ttu-id="d17d5-117">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-117">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="d17d5-118">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-118">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="d17d5-119">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-119">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="d17d5-120">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-120">This is the preferred method.</span></span>

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
curl https://packages.microsoft.com/config/ubuntu/16.04/prod.list | sudo tee /etc/apt/sources.list.d/microsoft.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="d17d5-121">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-121">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="d17d5-122">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-122">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="d17d5-123">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.0.0-rc-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-123">Download the Debian package `powershell_6.0.0-rc-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="d17d5-124">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-124">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.0-rc-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> <span data-ttu-id="d17d5-125">`dpkg -i` は依存関係が満たされずに失敗しますが、次のコマンド `apt-get install -f` で解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-125">Please note that `dpkg -i` will fail with unmet dependencies; the next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="d17d5-126">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-126">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1704"></a><span data-ttu-id="d17d5-127">Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-127">Ubuntu 17.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1704"></a><span data-ttu-id="d17d5-128">パッケージ リポジトリによるインストール - Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-128">Installation via Package Repository - Ubuntu 17.04</span></span>

<span data-ttu-id="d17d5-129">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-129">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="d17d5-130">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-130">This is the preferred method.</span></span>

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
curl https://packages.microsoft.com/config/ubuntu/17.04/prod.list | sudo tee /etc/apt/sources.list.d/microsoft.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="d17d5-131">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-131">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1704"></a><span data-ttu-id="d17d5-132">直接ダウンロードによるインストール - Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-132">Installation via Direct Download - Ubuntu 17.04</span></span>

<span data-ttu-id="d17d5-133">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.0.0-rc-1.ubuntu.17.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-133">Download the Debian package `powershell_6.0.0-rc-1.ubuntu.17.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="d17d5-134">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-134">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.0-rc-1.ubuntu.17.04_amd64.deb
sudo apt-get install -f
```

> <span data-ttu-id="d17d5-135">`dpkg -i` は依存関係が満たされずに失敗しますが、次のコマンド `apt-get install -f` で解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-135">Please note that `dpkg -i` will fail with unmet dependencies; the next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1704"></a><span data-ttu-id="d17d5-136">アンインストール - Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-136">Uninstallation - Ubuntu 17.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-8"></a><span data-ttu-id="d17d5-137">Debian 8</span><span class="sxs-lookup"><span data-stu-id="d17d5-137">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="d17d5-138">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="d17d5-138">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="d17d5-139">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-139">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="d17d5-140">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-140">This is the preferred method.</span></span>

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

<span data-ttu-id="d17d5-141">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-141">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-8"></a><span data-ttu-id="d17d5-142">直接ダウンロードによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="d17d5-142">Installation via Direct Download - Debian 8</span></span>

<span data-ttu-id="d17d5-143">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_6.0.0-rc-1.debian.8_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-143">Download the Debian package `powershell_6.0.0-rc-1.debian.8_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="d17d5-144">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-144">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.0-rc-1.debian.8_amd64.deb
sudo apt-get install -f
```

> <span data-ttu-id="d17d5-145">`dpkg -i` は依存関係が満たされずに失敗しますが、次のコマンド `apt-get install -f` で解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-145">Please note that `dpkg -i` will fail with unmet dependencies; the next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---debian-8"></a><span data-ttu-id="d17d5-146">アンインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="d17d5-146">Uninstallation - Debian 8</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-9"></a><span data-ttu-id="d17d5-147">Debian 9</span><span class="sxs-lookup"><span data-stu-id="d17d5-147">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="d17d5-148">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="d17d5-148">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="d17d5-149">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-149">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="d17d5-150">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-150">This is the preferred method.</span></span>

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

<span data-ttu-id="d17d5-151">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-151">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="d17d5-152">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="d17d5-152">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="d17d5-153">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_6.0.0-rc-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-153">Download the Debian package `powershell_6.0.0-rc-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="d17d5-154">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-154">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.0-rc-1.debian.9_amd64.deb
sudo apt-get install -f
```

> <span data-ttu-id="d17d5-155">`dpkg -i` は依存関係が満たされずに失敗しますが、次のコマンド `apt-get install -f` で解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-155">Please note that `dpkg -i` will fail with unmet dependencies; the next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---debian-9"></a><span data-ttu-id="d17d5-156">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="d17d5-156">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="d17d5-157">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-157">CentOS 7</span></span>

> <span data-ttu-id="d17d5-158">このパッケージは Oracle Linux 7 でも動作します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-158">This package also works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="d17d5-159">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-159">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="d17d5-160">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-160">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="d17d5-161">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-161">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="d17d5-162">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-162">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="d17d5-163">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-163">Using [CentOS 7][], download the RPM package `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="d17d5-164">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-164">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="d17d5-165">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-165">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="d17d5-166">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-166">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="d17d5-168">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-168">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="d17d5-169">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-169">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="d17d5-170">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-170">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="d17d5-171">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-171">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="d17d5-172">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-172">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="d17d5-173">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-173">Download the RPM package `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="d17d5-174">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-174">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="d17d5-175">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-175">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="d17d5-176">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-176">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse-422"></a><span data-ttu-id="d17d5-177">OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="d17d5-177">OpenSUSE 42.2</span></span>

> <span data-ttu-id="d17d5-178">**注記:** PowerShell Core のインストール時、OpenSUSE に `libcurl` を提供するものがないという報告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-178">**Note:** When installing PowerShell Core, OpenSUSE may report that nothing provides `libcurl`.</span></span>
<span data-ttu-id="d17d5-179">`libcurl` は、サポートされているバージョンの OpenSUSE に既にインストールされているはずです。</span><span class="sxs-lookup"><span data-stu-id="d17d5-179">`libcurl` should already be installed on supported versions of OpenSUSE.</span></span>
<span data-ttu-id="d17d5-180">`zypper search libcurl` を実行して確定します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-180">Run `zypper search libcurl` to confirm.</span></span>
<span data-ttu-id="d17d5-181">エラーには 2 つの 'ソリューション' が提示されます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-181">The error will present 2 'solutions'.</span></span> <span data-ttu-id="d17d5-182">'Solution 2' を選び、PowerShell Core のインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-182">Choose 'Solution 2' to continue installing PowerShell Core.</span></span>

### <a name="installation-via-package-repository-preferred---opensuse-422"></a><span data-ttu-id="d17d5-183">パッケージ リポジトリによるインストール (推奨) - OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="d17d5-183">Installation via Package Repository (preferred) - OpenSUSE 42.2</span></span>

<span data-ttu-id="d17d5-184">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-184">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Add the Microsoft Product feed
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/zypp/repos.d/microsoft.repo

# Update the list of products
sudo zypper update

# Install PowerShell
sudo zypper install powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---opensuse-422"></a><span data-ttu-id="d17d5-185">直接ダウンロードによるインストール - OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="d17d5-185">Installation via Direct Download - OpenSUSE 42.2</span></span>

<span data-ttu-id="d17d5-186">[リリース][] ページから OpenSUSE コンピューターに RPM パッケージ `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-186">Download the RPM package `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` from the [releases][] page onto the OpenSUSE machine.</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="d17d5-187">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-187">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---opensuse-422"></a><span data-ttu-id="d17d5-188">アンインストール - OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="d17d5-188">Uninstallation - OpenSUSE 42.2</span></span>

```sh
sudo zypper remove powershell
```

## <a name="fedora-25"></a><span data-ttu-id="d17d5-189">Fedora 25</span><span class="sxs-lookup"><span data-stu-id="d17d5-189">Fedora 25</span></span>

### <a name="installation-via-package-repository-preferred---fedora-25"></a><span data-ttu-id="d17d5-190">パッケージ リポジトリによるインストール (推奨) - Fedora 25</span><span class="sxs-lookup"><span data-stu-id="d17d5-190">Installation via Package Repository (preferred) - Fedora 25</span></span>

<span data-ttu-id="d17d5-191">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-191">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf update

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-25"></a><span data-ttu-id="d17d5-192">直接ダウンロードによるインストール - Fedora 25</span><span class="sxs-lookup"><span data-stu-id="d17d5-192">Installation via Direct Download - Fedora 25</span></span>

<span data-ttu-id="d17d5-193">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-193">Download the RPM package `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="d17d5-194">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-194">Then execute the following in the terminal:</span></span>

```sh
sudo dnf install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="d17d5-195">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-195">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-25"></a><span data-ttu-id="d17d5-196">アンインストール - Fedora 25</span><span class="sxs-lookup"><span data-stu-id="d17d5-196">Uninstallation - Fedora 25</span></span>

```sh
sudo dnf remove powershell
```

## <a name="fedora-26"></a><span data-ttu-id="d17d5-197">Fedora 26</span><span class="sxs-lookup"><span data-stu-id="d17d5-197">Fedora 26</span></span>

### <a name="installation-via-package-repository-preferred---fedora-26"></a><span data-ttu-id="d17d5-198">パッケージ リポジトリによるインストール (推奨) - Fedora 26</span><span class="sxs-lookup"><span data-stu-id="d17d5-198">Installation via Package Repository (preferred) - Fedora 26</span></span>

<span data-ttu-id="d17d5-199">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d17d5-199">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---fedora-26"></a><span data-ttu-id="d17d5-200">直接ダウンロードによるインストール - Fedora 26</span><span class="sxs-lookup"><span data-stu-id="d17d5-200">Installation via Direct Download - Fedora 26</span></span>

<span data-ttu-id="d17d5-201">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-201">Download the RPM package `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="d17d5-202">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-202">Then execute the following in the terminal:</span></span>

```sh
sudo dnf update
sudo dnf install compat-openssl10
sudo dnf install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="d17d5-203">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-203">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf update
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-26"></a><span data-ttu-id="d17d5-204">アンインストール - Fedora 26</span><span class="sxs-lookup"><span data-stu-id="d17d5-204">Uninstallation - Fedora 26</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="d17d5-205">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="d17d5-205">Arch Linux</span></span>

<span data-ttu-id="d17d5-206">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-206">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="d17d5-207">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="d17d5-207">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="d17d5-208">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="d17d5-208">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="d17d5-209">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="d17d5-209">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="d17d5-210">AUR のパッケージはコミュニティにより保守管理されています。公式のサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="d17d5-210">Packages in the AUR are community maintained - there is no official support.</span></span>

<span data-ttu-id="d17d5-211">AUR からパッケージをインストールする方法については、[Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) かコミュニティ [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d17d5-211">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="linux-appimage"></a><span data-ttu-id="d17d5-213">Linux AppImage</span><span class="sxs-lookup"><span data-stu-id="d17d5-213">Linux AppImage</span></span>

<span data-ttu-id="d17d5-214">最近の Linux ディストリビューションを利用し、[リリース][] ページから Linux コンピューターに AppImage `powershell-6.0.0-rc-x86_64.AppImage` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-214">Using a recent Linux distribution, download the AppImage `powershell-6.0.0-rc-x86_64.AppImage` from the [releases][] page onto the Linux machine.</span></span>

<span data-ttu-id="d17d5-215">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-215">Then execute the following in the terminal:</span></span>

```bash
chmod a+x powershell-6.0.0-rc-x86_64.AppImage
./powershell-6.0.0-rc-x86_64.AppImage
```

<span data-ttu-id="d17d5-216">[AppImage][] では、インストールしなくても PowerShell を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-216">The [AppImage][] lets you run PowerShell without installing it.</span></span>
<span data-ttu-id="d17d5-217">これは PowerShell とその依存関係 (.NET Core のシステム依存関係を含む) を 1 つのまとまったパッケージにバンドルする移植可能なアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="d17d5-217">It is a portable application that bundles PowerShell and its dependencies (including .NET Core's system dependencies) into one cohesive package.</span></span>
<span data-ttu-id="d17d5-218">このパッケージはユーザーの Linux ディストリビューションに依存せずに動作し、1 つのバイナリです。</span><span class="sxs-lookup"><span data-stu-id="d17d5-218">This package works independently of the user's Linux distribution, and is a single binary.</span></span>

[appimage]: http://appimage.org/

## <a name="macos-1012"></a><span data-ttu-id="d17d5-220">macOS 10.12</span><span class="sxs-lookup"><span data-stu-id="d17d5-220">macOS 10.12</span></span>

### <a name="installation-via-homebrew-preferred---macos-1012"></a><span data-ttu-id="d17d5-221">Homebrew によるインストール (preferred) - macOS 10.12</span><span class="sxs-lookup"><span data-stu-id="d17d5-221">Installation via Homebrew (preferred) - macOS 10.12</span></span>

<span data-ttu-id="d17d5-222">[Homebrew][brew] は、macOS で足りないパッケージを管理します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-222">[Homebrew][brew] is the missing package manager for macOS.</span></span>
<span data-ttu-id="d17d5-223">`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-223">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="d17d5-224">Homebrew をインストールすると、PowerShell のインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-224">Once you've installed Homebrew, installing PowerShell is easy.</span></span>
<span data-ttu-id="d17d5-225">最初に [Homebrew-Cask][cask] をインストールします。その後、たくさんのパッケージをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-225">First, install [Homebrew-Cask][cask], so you can install more packages:</span></span>

```sh
brew tap caskroom/cask
```

<span data-ttu-id="d17d5-226">これで PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-226">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="d17d5-227">新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="d17d5-227">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask reinstall powershell
```

> <span data-ttu-id="d17d5-228">注: [Cask のこの問題](https://github.com/caskroom/homebrew-cask/issues/29301)に起因し、現在のところ、アップグレードには再インストールが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-228">Note: because of [this issue in Cask](https://github.com/caskroom/homebrew-cask/issues/29301), you currently have to do a reinstall to upgrade.</span></span>

[brew]: http://brew.sh/
[cask]: https://caskroom.github.io/

### <a name="installation-via-direct-download---macos-1012"></a><span data-ttu-id="d17d5-229">直接ダウンロードによるインストール - macOS 10.12</span><span class="sxs-lookup"><span data-stu-id="d17d5-229">Installation via Direct Download - macOS 10.12</span></span>

<span data-ttu-id="d17d5-230">macOS 10.12 を利用し、[リリース][] ページから macOS コンピューターに PKG パッケージ `powershell-6.0.0-rc-osx.10.12-x64.pkg` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-230">Using macOS 10.12, download the PKG package `powershell-6.0.0-rc-osx.10.12-x64.pkg` from the [releases][] page onto the macOS machine.</span></span>

<span data-ttu-id="d17d5-231">ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-231">Either double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.0.0-rc-osx.10.12-x64.pkg -target /
```

### <a name="uninstallation---macos-1012"></a><span data-ttu-id="d17d5-232">アンインストール - macOS 10.12</span><span class="sxs-lookup"><span data-stu-id="d17d5-232">Uninstallation - macOS 10.12</span></span>

<span data-ttu-id="d17d5-233">Homebrew で PowerShell をインストールした場合、アンインストールが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-233">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="d17d5-234">直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-234">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="d17d5-235">追加の PowerShell パス (ユーザー プロファイル パスなど) をアンインストールするには、このドキュメントの「[パス][paths]」セクションを参照し、`sudo rm` でパスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="d17d5-235">To uninstall the additional PowerShell paths (such as the user profile path) please see the [paths][paths] section below in this document and remove the desired the paths with `sudo rm`.</span></span>
<span data-ttu-id="d17d5-236">(注: Homebrew でインストールした場合、これは不要です。)</span><span class="sxs-lookup"><span data-stu-id="d17d5-236">(Note: this is not necessary if you installed with Homebrew.)</span></span>

[paths]:#paths

## <a name="kali"></a><span data-ttu-id="d17d5-237">Kali</span><span class="sxs-lookup"><span data-stu-id="d17d5-237">Kali</span></span>

### <a name="installation"></a><span data-ttu-id="d17d5-238">インストール</span><span class="sxs-lookup"><span data-stu-id="d17d5-238">Installation</span></span>

```sh
# Install prerequisites
apt-get install libunwind8 libicu55
wget http://security.debian.org/debian-security/pool/updates/main/o/openssl/libssl1.0.0_1.0.1t-1+deb8u6_amd64.deb
dpkg -i libssl1.0.0_1.0.1t-1+deb8u6_amd64.deb

# Install PowerShell
dpkg -i powershell_6.0.0-rc-1.ubuntu.16.04_amd64.deb

# Start PowerShell
pwsh
```

### <a name="run-powershell-in-latest-kali-kali-gnulinux-rolling-without-installing-it"></a><span data-ttu-id="d17d5-239">最新の Kali (Kali GNU/Linux Rolling) でインストールせずに PowerShell を実行する</span><span class="sxs-lookup"><span data-stu-id="d17d5-239">Run PowerShell in latest Kali (Kali GNU/Linux Rolling) without installing it</span></span>

```sh
# Grab the latest App Image
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0-rc-x86_64.AppImage

# Make executable
chmod a+x powershell-6.0.0-rc-x86_64.AppImage

# Start PowerShell
./powershell-6.0.0-rc-x86_64.AppImage
```

### <a name="uninstallation---kali"></a><span data-ttu-id="d17d5-240">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="d17d5-240">Uninstallation - Kali</span></span>

```sh
dpkg -r powershell_6.0.0-rc-1.ubuntu.16.04_amd64.deb
```

## <a name="raspbian"></a><span data-ttu-id="d17d5-241">Raspbian</span><span class="sxs-lookup"><span data-stu-id="d17d5-241">Raspbian</span></span>

<span data-ttu-id="d17d5-242">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d17d5-242">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

### <a name="installation"></a><span data-ttu-id="d17d5-243">インストール</span><span class="sxs-lookup"><span data-stu-id="d17d5-243">Installation</span></span>

```sh
# Install prerequisites
sudo apt-get install libunwind8

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0-rc-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.0.0-rc-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="d17d5-244">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="d17d5-244">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="d17d5-245">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="d17d5-245">Binary Archives</span></span>

<span data-ttu-id="d17d5-246">macOS プラットフォームと Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d17d5-246">PowerShell binary `tar.gz` archives are provided for macOS and Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="d17d5-247">依存関係</span><span class="sxs-lookup"><span data-stu-id="d17d5-247">Dependencies</span></span>

<span data-ttu-id="d17d5-248">Linux の場合、PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d17d5-248">For Linux, PowerShell builds portable binaries for all Linux distributions.</span></span>
<span data-ttu-id="d17d5-249">ただし、.NET Core ランタイムはディストリビューションごとに異なる依存関係を必要とします。PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="d17d5-249">But .NET Core runtime requires different dependencies on different distributions, and hence PowerShell does the same.</span></span>

<span data-ttu-id="d17d5-250">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="d17d5-250">The following chart shows the .NET Core 2.0 dependencies on different Linux distributions that are officially supported.</span></span>

| <span data-ttu-id="d17d5-251">OS</span><span class="sxs-lookup"><span data-stu-id="d17d5-251">OS</span></span>                 | <span data-ttu-id="d17d5-252">依存関係</span><span class="sxs-lookup"><span data-stu-id="d17d5-252">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="d17d5-253">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-253">Ubuntu 14.04</span></span>       | <span data-ttu-id="d17d5-254">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="d17d5-254">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d17d5-255">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="d17d5-255">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="d17d5-256">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-256">Ubuntu 16.04</span></span>       | <span data-ttu-id="d17d5-257">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="d17d5-257">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d17d5-258">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="d17d5-258">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="d17d5-259">Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="d17d5-259">Ubuntu 17.04</span></span>       | <span data-ttu-id="d17d5-260">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="d17d5-260">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d17d5-261">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="d17d5-261">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="d17d5-262">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="d17d5-262">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="d17d5-263">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="d17d5-263">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d17d5-264">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="d17d5-264">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="d17d5-265">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="d17d5-265">Debian 9 (Stretch)</span></span> | <span data-ttu-id="d17d5-266">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="d17d5-266">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d17d5-267">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="d17d5-267">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="d17d5-268">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-268">CentOS 7</span></span> <br> <span data-ttu-id="d17d5-269">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-269">Oracle Linux 7</span></span> <br> <span data-ttu-id="d17d5-270">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="d17d5-270">RHEL 7</span></span> <br> <span data-ttu-id="d17d5-271">OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="d17d5-271">OpenSUSE 42.2</span></span> <br> <span data-ttu-id="d17d5-272">Fedora 25</span><span class="sxs-lookup"><span data-stu-id="d17d5-272">Fedora 25</span></span> | <span data-ttu-id="d17d5-273">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="d17d5-273">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="d17d5-274">Fedora 26</span><span class="sxs-lookup"><span data-stu-id="d17d5-274">Fedora 26</span></span>          | <span data-ttu-id="d17d5-275">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="d17d5-275">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="d17d5-276">公式にサポートされていない Linux ディストリビューションで PowerShell バイナリを展開するには、別の手順で、ターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-276">In order to deploy PowerShell binaries on Linux distributions that are not officially supported, you would need to install the necessary dependencies for the target OS in separate steps.</span></span>
<span data-ttu-id="d17d5-277">たとえば、[Amazon Linux dockerfile][amazon-dockerfile] は依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-277">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell/blob/master/docker/community/amazonlinux/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="d17d5-278">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="d17d5-278">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="d17d5-279">Linux</span><span class="sxs-lookup"><span data-stu-id="d17d5-279">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0-rc-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/6.0.0-rc

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.0.0-rc

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.0.0-rc/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/6.0.0-rc/pwsh /usr/bin/pwsh
```

#### <a name="macos"></a><span data-ttu-id="d17d5-280">macOS</span><span class="sxs-lookup"><span data-stu-id="d17d5-280">macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0-rc-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.0.0-rc

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.0.0-rc

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.0.0-rc/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.0.0-rc/pwsh /usr/local/bin/pwsh
```

### <a name="uninstallation---binary-archives"></a><span data-ttu-id="d17d5-281">アンインストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="d17d5-281">Uninstallation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="d17d5-282">Linux</span><span class="sxs-lookup"><span data-stu-id="d17d5-282">Linux</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

#### <a name="macos"></a><span data-ttu-id="d17d5-283">macOS</span><span class="sxs-lookup"><span data-stu-id="d17d5-283">macOS</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="d17d5-284">パス</span><span class="sxs-lookup"><span data-stu-id="d17d5-284">Paths</span></span>

* <span data-ttu-id="d17d5-285">`$PSHOME` は `/opt/microsoft/powershell/6.0.0-rc/` です</span><span class="sxs-lookup"><span data-stu-id="d17d5-285">`$PSHOME` is `/opt/microsoft/powershell/6.0.0-rc/`</span></span>
* <span data-ttu-id="d17d5-286">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="d17d5-286">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="d17d5-287">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="d17d5-287">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="d17d5-288">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="d17d5-288">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="d17d5-289">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="d17d5-289">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="d17d5-290">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="d17d5-290">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="d17d5-291">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="d17d5-291">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="d17d5-292">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-292">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="d17d5-293">Linux と macOS では、[XDG Base Directory Specification][xdg-bds] を順守します。</span><span class="sxs-lookup"><span data-stu-id="d17d5-293">On Linux and macOS, the [XDG Base Directory Specification][xdg-bds] is respected.</span></span>

<span data-ttu-id="d17d5-294">macOS は BSD から派生しているため、`/opt` ではなく、`/usr/local` がプレフィックスとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d17d5-294">Note that because macOS is a derivation of BSD, instead of `/opt`, the prefix used is `/usr/local`.</span></span>
<span data-ttu-id="d17d5-295">そのため、`$PSHOME` は `/usr/local/microsoft/powershell/6.0.0-rc/` です。シンボリックリンクは `/usr/local/bin/pwsh` にあります。</span><span class="sxs-lookup"><span data-stu-id="d17d5-295">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.0.0-rc/`, and the symlink is placed at `/usr/local/bin/pwsh`.</span></span>

[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
