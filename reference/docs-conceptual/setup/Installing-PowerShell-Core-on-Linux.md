# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="98c90-101">Linux への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="98c90-101">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="98c90-102">[Ubuntu 14.04][u14]、[Ubuntu 16.04][u16]、[Ubuntu 17.10][u17]、[Debian 8][deb8]、[Debian 9][deb9]、[CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[OpenSUSE 42.2][opensuse]、[Fedora 27][fedora]、[Fedora 28][fedora]、[Arch Linux][arch] をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="98c90-102">Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 17.10][u17], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [OpenSUSE 42.2][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="98c90-103">公式にサポートしていない Linux ディストリビューションの場合、[PowerShell AppImage][lai] を利用できます。</span><span class="sxs-lookup"><span data-stu-id="98c90-103">For Linux distributions that are not officially supported, you can try using the [PowerShell AppImage][lai].</span></span>
<span data-ttu-id="98c90-104">また、Linux [`tar.gz` アーカイブ][tar]で直接、PowerShell バイナリを展開できます。ただし、場合によっては、OS に基づいて依存関係を別の手順で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c90-104">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="98c90-105">すべてのパッケージは GitHub [リリース][] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="98c90-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="98c90-106">パッケージがインストールされたら、ターミナルから `pwsh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-106">Once the package is installed, run `pwsh` from a terminal.</span></span>

[u14]: #ubuntu-1404
[u16]: #ubuntu-1604
[u17]: #ubuntu-1710
[deb8]: #debian-8
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse-422
[fedora]: #fedora
[arch]: #arch-linux
[lai]: #linux-appimage
[tar]: #binary-archives

## <a name="installing-preview-releases"></a><span data-ttu-id="98c90-107">プレビュー リリースのインストール</span><span class="sxs-lookup"><span data-stu-id="98c90-107">Installing Preview Releases</span></span>

<span data-ttu-id="98c90-108">パッケージ リポジトリを介して、Linux 用の PowerShell Core Preview リリースをインストールすると、パッケージ名が `powershell` から `powershell-preview` に変わります。</span><span class="sxs-lookup"><span data-stu-id="98c90-108">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="98c90-109">直接ダウンロードによるインストールでは、ファイル名以外は変わりません。</span><span class="sxs-lookup"><span data-stu-id="98c90-109">Installing via direct download does not change, other than the file name.</span></span>

<span data-ttu-id="98c90-110">さまざまなパッケージ マネージャーを使用して、安定したパッケージとプレビュー パッケージをインストールするためのコマンドを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="98c90-110">Here is a table of the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="98c90-111">ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="98c90-111">Distrobution(s)</span></span>|<span data-ttu-id="98c90-112">安定したコマンド</span><span class="sxs-lookup"><span data-stu-id="98c90-112">Stable Command</span></span> | <span data-ttu-id="98c90-113">プレビュー コマンド</span><span class="sxs-lookup"><span data-stu-id="98c90-113">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="98c90-114">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="98c90-114">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="98c90-115">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="98c90-115">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="98c90-116">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="98c90-116">OpenSUSE</span></span> |`sudo zypper install powershell` | `sudo zypper install powershell-preview`|
| <span data-ttu-id="98c90-117">Fedora</span><span class="sxs-lookup"><span data-stu-id="98c90-117">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1404"></a><span data-ttu-id="98c90-118">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="98c90-118">Ubuntu 14.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1404"></a><span data-ttu-id="98c90-119">パッケージ リポジトリによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="98c90-119">Installation via Package Repository - Ubuntu 14.04</span></span>

<span data-ttu-id="98c90-120">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-120">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="98c90-121">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98c90-121">This is the preferred method.</span></span>

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

<span data-ttu-id="98c90-122">スーパーユーザーとして Microsoft リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="98c90-122">As superuser, register the Microsoft repository.</span></span>
<span data-ttu-id="98c90-123">以降は、インストールの更新に `sudo apt-get upgrade powershell` を使用するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="98c90-123">From then on, you just need to use `sudo apt-get upgrade powershell` to update the installation.</span></span>

### <a name="installation-via-direct-download---ubuntu-1404"></a><span data-ttu-id="98c90-124">直接ダウンロードによるインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="98c90-124">Installation via Direct Download - Ubuntu 14.04</span></span>

<span data-ttu-id="98c90-125">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.0.2-1.ubuntu.14.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-125">Download the Debian package `powershell_6.0.2-1.ubuntu.14.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="98c90-126">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-126">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="98c90-127">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="98c90-127">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="98c90-128">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="98c90-128">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1404"></a><span data-ttu-id="98c90-129">アンインストール - Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="98c90-129">Uninstallation - Ubuntu 14.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a><span data-ttu-id="98c90-130">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="98c90-130">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="98c90-131">パッケージ リポジトリによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="98c90-131">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="98c90-132">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-132">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="98c90-133">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98c90-133">This is the preferred method.</span></span>

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

<span data-ttu-id="98c90-134">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="98c90-134">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="98c90-135">直接ダウンロードによるインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="98c90-135">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="98c90-136">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.0.2-1.ubuntu.16.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-136">Download the Debian package `powershell_6.0.2-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="98c90-137">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-137">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="98c90-138">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="98c90-138">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="98c90-139">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="98c90-139">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="98c90-140">アンインストール - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="98c90-140">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1710"></a><span data-ttu-id="98c90-141">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="98c90-141">Ubuntu 17.10</span></span>

> [!NOTE]
> <span data-ttu-id="98c90-142">Ubuntu 17.04 のサポートは `6.1.0-preview.2` 以降に追加されました。</span><span class="sxs-lookup"><span data-stu-id="98c90-142">Support for Ubuntu 17.04 was added after `6.1.0-preview.2`</span></span>

### <a name="installation-via-package-repository---ubuntu-1710"></a><span data-ttu-id="98c90-143">パッケージ リポジトリによるインストール - Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="98c90-143">Installation via Package Repository - Ubuntu 17.10</span></span>

<span data-ttu-id="98c90-144">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-144">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="98c90-145">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98c90-145">This is the preferred method.</span></span>

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
sudo curl -o /etc/apt/sources.list.d/microsoft.list https://packages.microsoft.com/config/ubuntu/17.10/prod.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="98c90-146">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="98c90-146">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1710"></a><span data-ttu-id="98c90-147">直接ダウンロードによるインストール - Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="98c90-147">Installation via Direct Download - Ubuntu 17.10</span></span>

<span data-ttu-id="98c90-148">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.0.2-1.ubuntu.17.10_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-148">Download the Debian package `powershell_6.0.2-1.ubuntu.17.10_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="98c90-149">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-149">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.ubuntu.17.10_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="98c90-150">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="98c90-150">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="98c90-151">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="98c90-151">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1710"></a><span data-ttu-id="98c90-152">アンインストール - Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="98c90-152">Uninstallation - Ubuntu 17.10</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="98c90-153">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="98c90-153">Ubuntu 18.04</span></span>

> [!NOTE]
> <span data-ttu-id="98c90-154">Ubuntu 18.04 のサポートは `6.1.0-preview.2` 以降に追加されました。</span><span class="sxs-lookup"><span data-stu-id="98c90-154">Support for Ubuntu 18.04 was added after `6.1.0-preview.2`</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="98c90-155">パッケージ リポジトリによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="98c90-155">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="98c90-156">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-156">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="98c90-157">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98c90-157">This is the preferred method.</span></span>

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
pwsh
```

<span data-ttu-id="98c90-158">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="98c90-158">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="98c90-159">直接ダウンロードによるインストール - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="98c90-159">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="98c90-160">[リリース][] ページから Ubuntu コンピューターに Debian パッケージ `powershell_6.1.0-preview.3-1.ubuntu.18.04_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-160">Download the Debian package `powershell_6.1.0-preview.3-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="98c90-161">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-161">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-preview.3-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="98c90-162">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="98c90-162">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="98c90-163">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="98c90-163">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1710"></a><span data-ttu-id="98c90-164">アンインストール - Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="98c90-164">Uninstallation - Ubuntu 17.10</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-8"></a><span data-ttu-id="98c90-165">Debian 8</span><span class="sxs-lookup"><span data-stu-id="98c90-165">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="98c90-166">パッケージ リポジトリによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="98c90-166">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="98c90-167">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-167">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="98c90-168">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98c90-168">This is the preferred method.</span></span>

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

<span data-ttu-id="98c90-169">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="98c90-169">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-8"></a><span data-ttu-id="98c90-170">直接ダウンロードによるインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="98c90-170">Installation via Direct Download - Debian 8</span></span>

<span data-ttu-id="98c90-171">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_6.0.2-1.debian.8_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-171">Download the Debian package `powershell_6.0.2-1.debian.8_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="98c90-172">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-172">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.debian.8_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="98c90-173">`dpkg -i` コマンドは依存関係が満たされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="98c90-173">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="98c90-174">次のコマンド `apt-get install -f` でこれらの問題は解決され、PowerShell パッケージの構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="98c90-174">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---debian-8"></a><span data-ttu-id="98c90-175">アンインストール - Debian 8</span><span class="sxs-lookup"><span data-stu-id="98c90-175">Uninstallation - Debian 8</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-9"></a><span data-ttu-id="98c90-176">Debian 9</span><span class="sxs-lookup"><span data-stu-id="98c90-176">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="98c90-177">パッケージ リポジトリによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="98c90-177">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="98c90-178">Linux 向け PowerShell Core はパッケージ リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-178">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="98c90-179">この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98c90-179">This is the preferred method.</span></span>

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

<span data-ttu-id="98c90-180">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo apt-get upgrade powershell` を使用する更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="98c90-180">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="98c90-181">直接ダウンロードによるインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="98c90-181">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="98c90-182">[リリース][] ページから Debian コンピューターに Debian パッケージ `powershell_6.0.2-1.debian.9_amd64.deb` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-182">Download the Debian package `powershell_6.0.2-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="98c90-183">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-183">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="98c90-184">アンインストール - Debian 9</span><span class="sxs-lookup"><span data-stu-id="98c90-184">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="98c90-185">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="98c90-185">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="98c90-186">このパッケージは Oracle Linux 7 でも動作します。</span><span class="sxs-lookup"><span data-stu-id="98c90-186">This package also works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="98c90-187">パッケージ リポジトリによるインストール (推奨) - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="98c90-187">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="98c90-188">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-188">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="98c90-189">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="98c90-189">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="98c90-190">直接ダウンロードによるインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="98c90-190">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="98c90-191">[CentOS 7][] を利用し、[リリース][] ページから CentOS コンピューターに RPM パッケージ `powershell-6.0.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-191">Using [CentOS 7][], download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="98c90-192">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-192">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="98c90-193">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="98c90-193">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="98c90-194">アンインストール - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="98c90-194">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="98c90-196">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="98c90-196">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="98c90-197">パッケージ リポジトリによるインストール (推奨) - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="98c90-197">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="98c90-198">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-198">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="98c90-199">スーパーユーザーとして Microsoft リポジトリを一度登録すれば、その後は `sudo yum update powershell` を使用する PowerShell の更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="98c90-199">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="98c90-200">直接ダウンロードによるインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="98c90-200">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="98c90-201">[リリース][] ページから Red Hat Enterprise Linux コンピューターに RPM パッケージ `powershell-6.0.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-201">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="98c90-202">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-202">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="98c90-203">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="98c90-203">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="98c90-204">アンインストール - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="98c90-204">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse-422"></a><span data-ttu-id="98c90-205">OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="98c90-205">OpenSUSE 42.2</span></span>

<span data-ttu-id="98c90-206">PowerShell Core をインストールすると、`zypper` から次のエラーが報告されることがあります。</span><span class="sxs-lookup"><span data-stu-id="98c90-206">When installing PowerShell Core, `zypper` may report the following error:</span></span>

```Output
Problem: nothing provides libcurl needed by powershell-6.0.1-1.rhel.7.x86_64
 Solution 1: do not install powershell-6.0.1-1.rhel.7.x86_64
 Solution 2: break powershell-6.0.1-1.rhel.7.x86_64 by ignoring some of its dependencies
```

<span data-ttu-id="98c90-207">この場合、次のコマンドで `libcurl4` パッケージがインストール済みであることを確認して、互換性のある `libcurl` ライブラリが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="98c90-207">In this case, verify that a compatible `libcurl` library is present by checking that the following command shows the `libcurl4` package as installed:</span></span>

```sh
zypper search --file-list --match-exact '/usr/lib64/libcurl.so.4'
```

<span data-ttu-id="98c90-208">次に、PowerShell パッケージをインストールするときに `break powershell-6.0.1-1.rhel.7.x86_64 by ignoring some of its dependencies` ソリューションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c90-208">Then choose the `break powershell-6.0.1-1.rhel.7.x86_64 by ignoring some of its dependencies` solution when installing the PowerShell package.</span></span>

### <a name="installation-via-package-repository-preferred---opensuse-422"></a><span data-ttu-id="98c90-209">パッケージ リポジトリによるインストール (推奨) - OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="98c90-209">Installation via Package Repository (preferred) - OpenSUSE 42.2</span></span>

<span data-ttu-id="98c90-210">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-210">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---opensuse-422"></a><span data-ttu-id="98c90-211">直接ダウンロードによるインストール - OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="98c90-211">Installation via Direct Download - OpenSUSE 42.2</span></span>

<span data-ttu-id="98c90-212">[リリース][] ページから OpenSUSE コンピューターに RPM パッケージ `powershell-6.0.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-212">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the OpenSUSE machine.</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="98c90-213">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="98c90-213">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---opensuse-422"></a><span data-ttu-id="98c90-214">アンインストール - OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="98c90-214">Uninstallation - OpenSUSE 42.2</span></span>

```sh
sudo zypper remove powershell
```

## <a name="fedora"></a><span data-ttu-id="98c90-215">Fedora</span><span class="sxs-lookup"><span data-stu-id="98c90-215">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="98c90-216">Fedora 28 は、PowerShell Core 6.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="98c90-216">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a><span data-ttu-id="98c90-217">パッケージ リポジトリによるインストール (推奨) - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="98c90-217">Installation via Package Repository (preferred) - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="98c90-218">Linux 向け PowerShell Core は公式 Microsoft リポジトリに公開され、インストール (と更新) が簡単です。</span><span class="sxs-lookup"><span data-stu-id="98c90-218">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a><span data-ttu-id="98c90-219">直接ダウンロードによるインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="98c90-219">Installation via Direct Download - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="98c90-220">[リリース][] ページから Fedora コンピューターに RPM パッケージ `powershell-6.0.2-1.rhel.7.x86_64.rpm` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-220">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="98c90-221">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-221">Then execute the following in the terminal:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="98c90-222">ダウンロードという中間の手順なしでも RPM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="98c90-222">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a><span data-ttu-id="98c90-223">アンインストール - Fedora 27、Fedora 28</span><span class="sxs-lookup"><span data-stu-id="98c90-223">Uninstallation - Fedora 27, Fedora 28</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="98c90-224">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="98c90-224">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="98c90-225">Arch のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="98c90-225">Arch support is experimental.</span></span>

<span data-ttu-id="98c90-226">PowerShell は [Arch Linux][] User Repository (AUR) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="98c90-226">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="98c90-227">[タグが付けられた最新のリリース][arch-release]でコンパイルできます</span><span class="sxs-lookup"><span data-stu-id="98c90-227">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="98c90-228">[最新のコミットからマスターに][arch-git]コンパイルできます</span><span class="sxs-lookup"><span data-stu-id="98c90-228">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="98c90-229">[最新のリリース バイナリ][arch-bin]でインストールできます</span><span class="sxs-lookup"><span data-stu-id="98c90-229">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="98c90-230">AUR のパッケージはコミュニティにより保守管理されています。公式のサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="98c90-230">Packages in the AUR are community maintained - there is no official support.</span></span>

<span data-ttu-id="98c90-231">AUR からパッケージをインストールする方法については、[Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) かコミュニティ [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="98c90-231">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="linux-appimage"></a><span data-ttu-id="98c90-233">Linux AppImage</span><span class="sxs-lookup"><span data-stu-id="98c90-233">Linux AppImage</span></span>

> [!NOTE]
> <span data-ttu-id="98c90-234">AppImage のサポートは試験段階です</span><span class="sxs-lookup"><span data-stu-id="98c90-234">AppImage support is experimental</span></span>

<span data-ttu-id="98c90-235">最近の Linux ディストリビューションを利用し、[リリース][] ページから Linux コンピューターに AppImage `powershell-6.0.1-x86_64.AppImage` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="98c90-235">Using a recent Linux distribution, download the AppImage `powershell-6.0.1-x86_64.AppImage` from the [releases][] page onto the Linux machine.</span></span>

<span data-ttu-id="98c90-236">次にターミナルで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="98c90-236">Then execute the following in the terminal:</span></span>

```bash
chmod a+x powershell-6.0.1-x86_64.AppImage
./powershell-6.0.1-x86_64.AppImage
```

<span data-ttu-id="98c90-237">[AppImage][] では、インストールしなくても PowerShell を実行できます。</span><span class="sxs-lookup"><span data-stu-id="98c90-237">The [AppImage][] lets you run PowerShell without installing it.</span></span>
<span data-ttu-id="98c90-238">これは PowerShell とその依存関係 (.NET Core のシステム依存関係を含む) を 1 つのまとまったパッケージにバンドルする移植可能なアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="98c90-238">It is a portable application that bundles PowerShell and its dependencies (including .NET Core's system dependencies) into one cohesive package.</span></span>
<span data-ttu-id="98c90-239">このパッケージは、ユーザーの Linux ディストリビューションに依存せずに動作する 1 つのバイナリです。</span><span class="sxs-lookup"><span data-stu-id="98c90-239">This package  is a single binary that works independently of the user's Linux distribution.</span></span>

[appimage]: http://appimage.org/

## <a name="kali"></a><span data-ttu-id="98c90-241">Kali</span><span class="sxs-lookup"><span data-stu-id="98c90-241">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="98c90-242">Kali のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="98c90-242">Kali support is experimental.</span></span>

### <a name="installation"></a><span data-ttu-id="98c90-243">インストール</span><span class="sxs-lookup"><span data-stu-id="98c90-243">Installation</span></span>

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

### <a name="run-powershell-in-latest-kali-kali-gnulinux-rolling-without-installing-it"></a><span data-ttu-id="98c90-244">最新の Kali (Kali GNU/Linux Rolling) でインストールせずに PowerShell を実行する</span><span class="sxs-lookup"><span data-stu-id="98c90-244">Run PowerShell in latest Kali (Kali GNU/Linux Rolling) without installing it</span></span>

```sh
# Grab the latest App Image
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-x86_64.AppImage

# Make executable
chmod a+x powershell-6.0.2-x86_64.AppImage

# Start PowerShell
./powershell-6.0.2-x86_64.AppImage
```

### <a name="uninstallation---kali"></a><span data-ttu-id="98c90-245">アンインストール - Kali</span><span class="sxs-lookup"><span data-stu-id="98c90-245">Uninstallation - Kali</span></span>

```sh
sudo dpkg -r powershell_6.0.2-1.ubuntu.16.04_amd64.deb
```

## <a name="raspbian"></a><span data-ttu-id="98c90-246">Raspbian</span><span class="sxs-lookup"><span data-stu-id="98c90-246">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="98c90-247">Raspbian のサポートは試験段階です。</span><span class="sxs-lookup"><span data-stu-id="98c90-247">Raspbian support is experimental.</span></span>

<span data-ttu-id="98c90-248">現在のところ、PowerShell は Raspbian Stretch でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="98c90-248">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="98c90-249">また、Core CLR (と PowerShell Core) は Pi 2 および Pi 3 デバイス上でのみ動作します。これは、[Pi Zero](https://github.com/dotnet/coreclr/issues/10605) のような他のデバイスにはサポートされていないプロセッサが搭載されているためです。</span><span class="sxs-lookup"><span data-stu-id="98c90-249">Also CoreCLR (and thus PowerShell Core) will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="98c90-250">[Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) をダウンロードし、[インストール手順](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)に従って Pi にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="98c90-250">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation"></a><span data-ttu-id="98c90-251">インストール</span><span class="sxs-lookup"><span data-stu-id="98c90-251">Installation</span></span>

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

<span data-ttu-id="98c90-252">必要に応じて、"pwsh" バイナリへのパスを指定せずに、シンボリック リンクを作成して PowerShell を起動することができます</span><span class="sxs-lookup"><span data-stu-id="98c90-252">Optionally you can create a symbolic link to be able to start PowerShell without specifying path to the "pwsh" binary</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="98c90-253">アンインストール - Raspbian</span><span class="sxs-lookup"><span data-stu-id="98c90-253">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="98c90-254">バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="98c90-254">Binary Archives</span></span>

<span data-ttu-id="98c90-255">Linux プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="98c90-255">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="98c90-256">依存関係</span><span class="sxs-lookup"><span data-stu-id="98c90-256">Dependencies</span></span>

<span data-ttu-id="98c90-257">PowerShell はすべての Linux ディストリビューションに移植可能なバイナリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="98c90-257">PowerShell builds portable binaries for all Linux distributions.</span></span>
<span data-ttu-id="98c90-258">ただし、.NET Core ランタイムはディストリビューションごとに異なる依存関係を必要とします。PowerShell でも同じです。</span><span class="sxs-lookup"><span data-stu-id="98c90-258">But .NET Core runtime requires different dependencies on different distributions, and hence PowerShell does the same.</span></span>

<span data-ttu-id="98c90-259">次の表は、公式にサポートされている Linux ディストリビューションと .NET Core 2.0 の依存関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="98c90-259">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="98c90-260">OS</span><span class="sxs-lookup"><span data-stu-id="98c90-260">OS</span></span>                 | <span data-ttu-id="98c90-261">依存関係</span><span class="sxs-lookup"><span data-stu-id="98c90-261">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="98c90-262">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="98c90-262">Ubuntu 14.04</span></span>       | <span data-ttu-id="98c90-263">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="98c90-263">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="98c90-264">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="98c90-264">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="98c90-265">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="98c90-265">Ubuntu 16.04</span></span>       | <span data-ttu-id="98c90-266">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="98c90-266">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="98c90-267">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="98c90-267">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="98c90-268">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="98c90-268">Ubuntu 17.10</span></span>       | <span data-ttu-id="98c90-269">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="98c90-269">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="98c90-270">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="98c90-270">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="98c90-271">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="98c90-271">Ubuntu 18.04</span></span>       | <span data-ttu-id="98c90-272">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="98c90-272">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="98c90-273">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="98c90-273">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="98c90-274">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="98c90-274">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="98c90-275">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="98c90-275">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="98c90-276">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="98c90-276">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="98c90-277">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="98c90-277">Debian 9 (Stretch)</span></span> | <span data-ttu-id="98c90-278">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="98c90-278">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="98c90-279">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="98c90-279">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="98c90-280">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="98c90-280">CentOS 7</span></span> <br> <span data-ttu-id="98c90-281">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="98c90-281">Oracle Linux 7</span></span> <br> <span data-ttu-id="98c90-282">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="98c90-282">RHEL 7</span></span> <br> <span data-ttu-id="98c90-283">OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="98c90-283">OpenSUSE 42.2</span></span> | <span data-ttu-id="98c90-284">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="98c90-284">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="98c90-285">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="98c90-285">Fedora 27</span></span> <br> <span data-ttu-id="98c90-286">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="98c90-286">Fedora 28</span></span> | <span data-ttu-id="98c90-287">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="98c90-287">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="98c90-288">公式にサポートされていない Linux ディストリビューションで PowerShell バイナリを展開するには、別の手順で、ターゲット OS に必要な依存関係をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c90-288">To deploy PowerShell binaries on Linux distributions that are not officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span>
<span data-ttu-id="98c90-289">たとえば、[Amazon Linux dockerfile][amazon-dockerfile] は依存関係を先にインストールし、それから Linux `tar.gz` アーカイブを抽出します。</span><span class="sxs-lookup"><span data-stu-id="98c90-289">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell/blob/master/docker/community/amazonlinux/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="98c90-290">インストール - バイナリ アーカイブ</span><span class="sxs-lookup"><span data-stu-id="98c90-290">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="98c90-291">Linux</span><span class="sxs-lookup"><span data-stu-id="98c90-291">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="98c90-292">バイナリ アーカイブのアンインストール</span><span class="sxs-lookup"><span data-stu-id="98c90-292">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="98c90-293">パス</span><span class="sxs-lookup"><span data-stu-id="98c90-293">Paths</span></span>

* <span data-ttu-id="98c90-294">`$PSHOME` は `/opt/microsoft/powershell/6.0.2/` です</span><span class="sxs-lookup"><span data-stu-id="98c90-294">`$PSHOME` is `/opt/microsoft/powershell/6.0.2/`</span></span>
* <span data-ttu-id="98c90-295">ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="98c90-295">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="98c90-296">既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="98c90-296">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="98c90-297">ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="98c90-297">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="98c90-298">共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="98c90-298">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="98c90-299">既定のモジュールは `$PSHOME/Modules` から読み込まれます</span><span class="sxs-lookup"><span data-stu-id="98c90-299">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="98c90-300">PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます</span><span class="sxs-lookup"><span data-stu-id="98c90-300">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="98c90-301">プロファイルは PowerShell のホスト別構成を順守します。そのため、既定のホスト固有プロファイルは同じ場所の `Microsoft.PowerShell_profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="98c90-301">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="98c90-302">PowerShell は、Linux の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。</span><span class="sxs-lookup"><span data-stu-id="98c90-302">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
