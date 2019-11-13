---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 Desired State Configuration (DSC) の概要
ms.openlocfilehash: b1bc9b9fafd89a1af0f967de38a817bff1f3ffe3
ms.sourcegitcommit: 14b50e5446f69729f72231f5dc6f536cdd1084c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73933844"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-linux"></a><span data-ttu-id="476e7-103">Linux 用 Desired State Configuration (DSC) の概要</span><span class="sxs-lookup"><span data-stu-id="476e7-103">Get started with Desired State Configuration (DSC) for Linux</span></span>

<span data-ttu-id="476e7-104">このトピックでは、Linux 用 PowerShell Desired State Configuration (DSC) の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="476e7-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Linux.</span></span> <span data-ttu-id="476e7-105">DSC に関する一般的な情報については、「[Windows PowerShell Desired State Configuration の概要](../overview/overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="476e7-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-linux-operation-system-versions"></a><span data-ttu-id="476e7-106">サポートされている Linux オペレーティング システム バージョン</span><span class="sxs-lookup"><span data-stu-id="476e7-106">Supported Linux operation system versions</span></span>

<span data-ttu-id="476e7-107">Linux 用 DSC では、次の Linux オペレーティング システム バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="476e7-107">The following Linux operating system versions are supported for DSC for Linux.</span></span>

- <span data-ttu-id="476e7-108">CentOS 5、6、および 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="476e7-108">CentOS 5, 6, and 7 (x86/x64)</span></span>
- <span data-ttu-id="476e7-109">Debian GNU/Linux 6、7、および 8 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="476e7-109">Debian GNU/Linux 6, 7 and 8 (x86/x64)</span></span>
- <span data-ttu-id="476e7-110">Oracle Linux 5、6 および 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="476e7-110">Oracle Linux 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="476e7-111">Red Hat Enterprise Linux Server 5、6 および 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="476e7-111">Red Hat Enterprise Linux Server 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="476e7-112">SUSE Linux Enterprise Server 10、11、および 12 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="476e7-112">SUSE Linux Enterprise Server 10, 11 and 12 (x86/x64)</span></span>
- <span data-ttu-id="476e7-113">Ubuntu Server 12.04 LTS、14.04 LTS、および 16.04 LTS (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="476e7-113">Ubuntu Server 12.04 LTS, 14.04 LTS and 16.04 LTS (x86/x64)</span></span>

<span data-ttu-id="476e7-114">次の表では、Linux 用 DSC で必要なパッケージの依存関係について説明します。</span><span class="sxs-lookup"><span data-stu-id="476e7-114">The following table describes the required package dependencies for DSC for Linux.</span></span>

|  <span data-ttu-id="476e7-115">必須パッケージ</span><span class="sxs-lookup"><span data-stu-id="476e7-115">Required package</span></span> |  <span data-ttu-id="476e7-116">説明</span><span class="sxs-lookup"><span data-stu-id="476e7-116">Description</span></span> |  <span data-ttu-id="476e7-117">最小バージョン</span><span class="sxs-lookup"><span data-stu-id="476e7-117">Minimum version</span></span> |
|---|---|---|
| <span data-ttu-id="476e7-118">glibc</span><span class="sxs-lookup"><span data-stu-id="476e7-118">glibc</span></span>| <span data-ttu-id="476e7-119">GNU ライブラリ</span><span class="sxs-lookup"><span data-stu-id="476e7-119">GNU Library</span></span>| <span data-ttu-id="476e7-120">2\...4 - 31.30</span><span class="sxs-lookup"><span data-stu-id="476e7-120">2…4 – 31.30</span></span>|
| <span data-ttu-id="476e7-121">python</span><span class="sxs-lookup"><span data-stu-id="476e7-121">python</span></span>| <span data-ttu-id="476e7-122">Python</span><span class="sxs-lookup"><span data-stu-id="476e7-122">Python</span></span>| <span data-ttu-id="476e7-123">2.4 - 3.4</span><span class="sxs-lookup"><span data-stu-id="476e7-123">2.4 – 3.4</span></span>|
| <span data-ttu-id="476e7-124">omiserver</span><span class="sxs-lookup"><span data-stu-id="476e7-124">omiserver</span></span>| <span data-ttu-id="476e7-125">Open Management Infrastructure (オープン管理インフラストラクチャ)</span><span class="sxs-lookup"><span data-stu-id="476e7-125">Open Management Infrastructure</span></span>| <span data-ttu-id="476e7-126">1.0.8.1</span><span class="sxs-lookup"><span data-stu-id="476e7-126">1.0.8.1</span></span>|
| <span data-ttu-id="476e7-127">openssl</span><span class="sxs-lookup"><span data-stu-id="476e7-127">openssl</span></span>| <span data-ttu-id="476e7-128">OpenSSL ライブラリ</span><span class="sxs-lookup"><span data-stu-id="476e7-128">OpenSSL Libraries</span></span>| <span data-ttu-id="476e7-129">0.9.8 または 1.0</span><span class="sxs-lookup"><span data-stu-id="476e7-129">0.9.8 or 1.0</span></span>|
| <span data-ttu-id="476e7-130">ctypes</span><span class="sxs-lookup"><span data-stu-id="476e7-130">ctypes</span></span>| <span data-ttu-id="476e7-131">Python CTypes ライブラリ</span><span class="sxs-lookup"><span data-stu-id="476e7-131">Python CTypes library</span></span>| <span data-ttu-id="476e7-132">Python のバージョンに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="476e7-132">Must match Python version</span></span>|
| <span data-ttu-id="476e7-133">libcurl</span><span class="sxs-lookup"><span data-stu-id="476e7-133">libcurl</span></span>| <span data-ttu-id="476e7-134">cURL http クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="476e7-134">cURL http client library</span></span>| <span data-ttu-id="476e7-135">7.15.1</span><span class="sxs-lookup"><span data-stu-id="476e7-135">7.15.1</span></span>|

## <a name="installing-dsc-for-linux"></a><span data-ttu-id="476e7-136">Linux 用 DSC のインストール</span><span class="sxs-lookup"><span data-stu-id="476e7-136">Installing DSC for Linux</span></span>

<span data-ttu-id="476e7-137">Linux 用 DSC をインストールする前に、[Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="476e7-137">You must install the [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) before installing DSC for Linux.</span></span>

### <a name="installing-omi"></a><span data-ttu-id="476e7-138">OMI のインストール</span><span class="sxs-lookup"><span data-stu-id="476e7-138">Installing OMI</span></span>

<span data-ttu-id="476e7-139">Linux 用 Desired State Configuration には、Open Management Infrastructure (OMI) CIM サーバーの 1.0.8.1 以降のバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="476e7-139">Desired State Configuration for Linux requires the Open Management Infrastructure (OMI) CIM server, version 1.0.8.1 or later.</span></span> <span data-ttu-id="476e7-140">OMI は、Open Group からダウンロードできます:[Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi)。</span><span class="sxs-lookup"><span data-stu-id="476e7-140">OMI can be downloaded from The Open Group: [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi).</span></span>

<span data-ttu-id="476e7-141">OMI をインストールするには、Linux システムに適したパッケージ (.rpm または .deb)、OpenSSL バージョンに適したパッケージ (ssl_098 または ssl_100)、およびアーキテクチャに適したパッケージ (x86/x64) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="476e7-141">To install OMI, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="476e7-142">CentOS、Red Hat Enterprise Linux、SUSE Linux Enterprise Server、および Oracle Linux には、RPM パッケージが適しています。</span><span class="sxs-lookup"><span data-stu-id="476e7-142">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="476e7-143">Debian GNU/Linux および Ubuntu Server には、DEB パッケージが適しています。</span><span class="sxs-lookup"><span data-stu-id="476e7-143">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="476e7-144">OpenSSL 0.9.8 がインストールされているコンピューターには ssl_098 パッケージが適し、OpenSSL 1.0 がインストールされているコンピューターには ssl_100 パッケージが適しています。</span><span class="sxs-lookup"><span data-stu-id="476e7-144">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="476e7-145">インストールされている OpenSSL のバージョンを調べるには、コマンド `openssl version` を実行します。</span><span class="sxs-lookup"><span data-stu-id="476e7-145">To determine the installed OpenSSL version, run the command `openssl version`.</span></span>

<span data-ttu-id="476e7-146">CentOS 7 x64 システムに OMI をインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="476e7-146">Run the following command to install OMI on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh omiserver-1.0.8.ssl_100.rpm`

### <a name="installing-dsc"></a><span data-ttu-id="476e7-147">DSC のインストール</span><span class="sxs-lookup"><span data-stu-id="476e7-147">Installing DSC</span></span>

<span data-ttu-id="476e7-148">Linux 用の DSC は、[こちら](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="476e7-148">DSC for Linux is available for download [here](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-294).</span></span>

<span data-ttu-id="476e7-149">DSC をインストールするには、Linux システムに適したパッケージ (.rpm または .deb)、OpenSSL バージョンに適したパッケージ (ssl_098 または ssl_100)、およびアーキテクチャに適したパッケージ (x86/x64) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="476e7-149">To install DSC, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="476e7-150">CentOS、Red Hat Enterprise Linux、SUSE Linux Enterprise Server、および Oracle Linux には、RPM パッケージが適しています。</span><span class="sxs-lookup"><span data-stu-id="476e7-150">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="476e7-151">Debian GNU/Linux および Ubuntu Server には、DEB パッケージが適しています。</span><span class="sxs-lookup"><span data-stu-id="476e7-151">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="476e7-152">OpenSSL 0.9.8 がインストールされているコンピューターには ssl_098 パッケージが適し、OpenSSL 1.0 がインストールされているコンピューターには ssl_100 パッケージが適しています。</span><span class="sxs-lookup"><span data-stu-id="476e7-152">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="476e7-153">インストールされている OpenSSL のバージョンを調べるには、コマンド openssl version を実行します。</span><span class="sxs-lookup"><span data-stu-id="476e7-153">To determine the installed OpenSSL version, run the command openssl version.</span></span>

<span data-ttu-id="476e7-154">CentOS 7 x64 システムに DSC をインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="476e7-154">Run the following command to install DSC on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh dsc-1.0.0-254.ssl_100.x64.rpm`

## <a name="using-dsc-for-linux"></a><span data-ttu-id="476e7-155">Linux 用 DSC の使用</span><span class="sxs-lookup"><span data-stu-id="476e7-155">Using DSC for Linux</span></span>

<span data-ttu-id="476e7-156">次のセクションでは、Linux コンピューターで DSC 構成を作成し、実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="476e7-156">The following sections explain how to create and run DSC configurations on Linux computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="476e7-157">構成 MOF ドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="476e7-157">Creating a configuration MOF document</span></span>

<span data-ttu-id="476e7-158">Linux コンピューターの構成を作成するには、Windows コンピューターの場合と同じように、Windows PowerShell 構成キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="476e7-158">The Windows PowerShell Configuration keyword is used to create a configuration for Linux computers, just like for Windows computers.</span></span> <span data-ttu-id="476e7-159">次の手順では、Windows PowerShell を使用して Linux コンピューターの構成ドキュメントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="476e7-159">The following steps describe the creation of a configuration document for a Linux computer using Windows PowerShell.</span></span>

1. <span data-ttu-id="476e7-160">nx モジュールのインポート</span><span class="sxs-lookup"><span data-stu-id="476e7-160">Import the nx module.</span></span> <span data-ttu-id="476e7-161">nx Windows PowerShell モジュールには Linux 用 DSC の組み込みリソースのスキーマが含まれており、このモジュールをローカル コンピューターにインストールし、構成にインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="476e7-161">The nx Windows PowerShell module contains the schema for Built-In resources for DSC for Linux, and must be installed to your local computer and imported in the configuration.</span></span>

   - <span data-ttu-id="476e7-162">nx モジュールをインストールするには、nx モジュール ディレクトリを `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` または `$PSHOME\Modules` にコピーします。</span><span class="sxs-lookup"><span data-stu-id="476e7-162">To install the nx module, copy the nx module directory to either `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` or `$PSHOME\Modules`.</span></span> <span data-ttu-id="476e7-163">nx モジュールは、Linux 用 DSC のインストール パッケージに含まれています。</span><span class="sxs-lookup"><span data-stu-id="476e7-163">The nx module is included in the DSC for Linux installation package.</span></span> <span data-ttu-id="476e7-164">構成に nx モジュールをインポートするには、`Import-DSCResource` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="476e7-164">To import the nx module in your configuration, use the `Import-DSCResource` command:</span></span>

   ```powershell
   Configuration ExampleConfiguration{

    Import-DSCResource -Module nx

   }
   ```

2. <span data-ttu-id="476e7-165">構成を定義し、構成ドキュメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="476e7-165">Define a configuration and generate the configuration document:</span></span>

   ```powershell
   Configuration ExampleConfiguration
   {
        Import-DscResource -Module nx

        Node  "linuxhost.contoso.com"
        {
            nxFile ExampleFile 
            {
                DestinationPath = "/tmp/example"
                Contents = "hello world `n"
                Ensure = "Present"
                Type = "File"
            }
        }
   }

   ExampleConfiguration -OutputPath:"C:\temp"
   ```

### <a name="push-the-configuration-to-the-linux-computer"></a><span data-ttu-id="476e7-166">Linux コンピューターへの構成のプッシュ</span><span class="sxs-lookup"><span data-stu-id="476e7-166">Push the configuration to the Linux computer</span></span>

<span data-ttu-id="476e7-167">構成ドキュメント (MOF ファイル) を Linux コンピューターにプッシュするには、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="476e7-167">Configuration documents (MOF files) can be pushed to the Linux computer using the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="476e7-168">Linux コンピューターに対してリモートからこのコマンドレットを [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) と共に使用するか、または [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) コマンドレットを使用するためには、CIMSession を使用する必要あります。</span><span class="sxs-lookup"><span data-stu-id="476e7-168">In order to use this cmdlet, along with the [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration), or [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) cmdlets, remotely to a Linux computer, you must use a CIMSession.</span></span> <span data-ttu-id="476e7-169">Linux コンピューターに CIMSession を作成するには、[New-CimSession](/powershell/module/CimCmdlets/New-CimSession) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="476e7-169">The [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet is used to create a CIMSession to the Linux computer.</span></span>

<span data-ttu-id="476e7-170">次のコードは、Linux 用 DSC の CIMSession を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="476e7-170">The following code shows how to create a CIMSession for DSC for Linux.</span></span>

```powershell
$Node = "ostc-dsc-01"
$Credential = Get-Credential -UserName "root" -Message "Enter Password:"

#Ignore SSL certificate validation
#$opt = New-CimSessionOption -UseSsl $true -SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true

#Options for a trusted SSL certificate
$opt = New-CimSessionOption -UseSsl $true
$Sess=New-CimSession -Credential $credential -ComputerName $Node -Port 5986 -Authentication basic -SessionOption $opt -OperationTimeoutSec 90
```

> [!NOTE]
> <span data-ttu-id="476e7-171">"プッシュ" モードの場合、ユーザーの資格情報は Linux コンピューターの root ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="476e7-171">For "Push" mode, the user credential must be the root user on the Linux computer.</span></span>
> <span data-ttu-id="476e7-172">Linux 用 DSC では SSL/TLS 接続のみがサポートされているため、`New-CimSession` を使用するときは、–UseSSL パラメーターを $true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="476e7-172">Only SSL/TLS connections are supported for DSC for Linux, the `New-CimSession` must be used with the –UseSSL parameter set to $true.</span></span>
> <span data-ttu-id="476e7-173">OMI (DSC 用) で使用される SSL 証明書は、pemfile プロパティと keyfile プロパティを使用して `/etc/opt/omi/conf/omiserver.conf` ファイルに指定します。</span><span class="sxs-lookup"><span data-stu-id="476e7-173">The SSL certificate used by OMI (for DSC) is specified in the file: `/etc/opt/omi/conf/omiserver.conf` with the properties: pemfile and keyfile.</span></span>
> <span data-ttu-id="476e7-174">[New-CimSession](/powershell/module/CimCmdlets/New-CimSession) コマンドレットを実行している Windows コンピューターでこの証明書が信頼されていない場合は、`-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true` の各 CIMSession オプションを使用して証明書の検証を無視することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="476e7-174">If this certificate is not trusted by the Windows computer that you are running the [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet on, you can choose to ignore certificate validation with the CIMSession Options: `-SkipCACheck $true -SkipCNCheck $true -SkipRevocationCheck $true`</span></span>

<span data-ttu-id="476e7-175">Linux ノードに DSC 構成をプッシュするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="476e7-175">Run the following command to push the DSC configuration to the Linux node.</span></span>

`Start-DscConfiguration -Path:"C:\temp" -CimSession $Sess -Wait -Verbose`

### <a name="distribute-the-configuration-with-a-pull-server"></a><span data-ttu-id="476e7-176">プル サーバーを使用した構成の配布</span><span class="sxs-lookup"><span data-stu-id="476e7-176">Distribute the configuration with a pull server</span></span>

<span data-ttu-id="476e7-177">構成を Linux コンピューターに配布するには、Windows コンピューターの場合と同じく、プル サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="476e7-177">Configurations can be distributed to a Linux computer with a pull server, just like for Windows computers.</span></span> <span data-ttu-id="476e7-178">プル サーバーを使用する方法の詳細については、「[DSC Web プル サーバーのセットアップ](../pull-server/pullServer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="476e7-178">For guidance on using a pull server, see [Windows PowerShell Desired State Configuration Pull Servers](../pull-server/pullServer.md).</span></span> <span data-ttu-id="476e7-179">プル サーバーでの Linux コンピューターの使用に関する追加情報および制限事項については、Linux 用 Desired State Configuration のリリース ノートをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="476e7-179">For additional information and limitations related to using Linux computers with a pull server, see the Release Notes for Desired State Configuration for Linux.</span></span>

### <a name="working-with-configurations-locally"></a><span data-ttu-id="476e7-180">ローカルでの構成の操作</span><span class="sxs-lookup"><span data-stu-id="476e7-180">Working with configurations locally</span></span>

<span data-ttu-id="476e7-181">Linux 用 DSC には、ローカルの Linux コンピューターから構成を操作するためのスクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="476e7-181">DSC for Linux includes scripts to work with configuration from the local Linux computer.</span></span> <span data-ttu-id="476e7-182">これらのスクリプトは、`/opt/microsoft/dsc/Scripts` にあり、次のものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="476e7-182">These scripts are locate in `/opt/microsoft/dsc/Scripts` and include the following:</span></span>

- <span data-ttu-id="476e7-183">GetDscConfiguration.py</span><span class="sxs-lookup"><span data-stu-id="476e7-183">GetDscConfiguration.py</span></span>

<span data-ttu-id="476e7-184">コンピューターに適用される現在の構成を返します。</span><span class="sxs-lookup"><span data-stu-id="476e7-184">Returns the current configuration applied to the computer.</span></span> <span data-ttu-id="476e7-185">Windows PowerShell コマンドレットの `Get-DscConfiguration` コマンドレットに似ています。</span><span class="sxs-lookup"><span data-stu-id="476e7-185">Similar to the Windows PowerShell cmdlet `Get-DscConfiguration` cmdlet.</span></span>

`# sudo ./GetDscConfiguration.py`

- <span data-ttu-id="476e7-186">GetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="476e7-186">GetDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="476e7-187">コンピューターに適用される現在のメタ構成を返します。</span><span class="sxs-lookup"><span data-stu-id="476e7-187">Returns the current meta-configuration applied to the computer.</span></span> <span data-ttu-id="476e7-188">[Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) コマンドレットに似ています。</span><span class="sxs-lookup"><span data-stu-id="476e7-188">Similar to the cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) cmdlet.</span></span>

`# sudo ./GetDscLocalConfigurationManager.py`

- <span data-ttu-id="476e7-189">InstallModule.py</span><span class="sxs-lookup"><span data-stu-id="476e7-189">InstallModule.py</span></span>

<span data-ttu-id="476e7-190">カスタムの DSC リソース モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="476e7-190">Installs a custom DSC resource module.</span></span> <span data-ttu-id="476e7-191">モジュール共有オブジェクト ライブラリおよびスキーマ MOF ファイルが含まれている .zip ファイルへのパスが必要です。</span><span class="sxs-lookup"><span data-stu-id="476e7-191">Requires the path to a .zip file containing the module shared object library and schema MOF files.</span></span>

`# sudo ./InstallModule.py /tmp/cnx_Resource.zip`

- <span data-ttu-id="476e7-192">RemoveModule.py</span><span class="sxs-lookup"><span data-stu-id="476e7-192">RemoveModule.py</span></span>

<span data-ttu-id="476e7-193">カスタムの DSC リソース モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="476e7-193">Removes a custom DSC resource module.</span></span> <span data-ttu-id="476e7-194">削除するモジュールの名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="476e7-194">Requires the name of the module to remove.</span></span>

`# sudo ./RemoveModule.py cnx_Resource`

- <span data-ttu-id="476e7-195">StartDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="476e7-195">StartDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="476e7-196">構成 MOF ファイルをコンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="476e7-196">Applies a configuration MOF file to the computer.</span></span> <span data-ttu-id="476e7-197">[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットに似ています。</span><span class="sxs-lookup"><span data-stu-id="476e7-197">Similar to the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="476e7-198">適用する構成 MOF へのパスが必要です。</span><span class="sxs-lookup"><span data-stu-id="476e7-198">Requires the path to the configuration MOF to apply.</span></span>

`# sudo ./StartDscLocalConfigurationManager.py –configurationmof /tmp/localhost.mof`

- <span data-ttu-id="476e7-199">SetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="476e7-199">SetDscLocalConfigurationManager.py</span></span>

<span data-ttu-id="476e7-200">メタ構成 MOF ファイルをコンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="476e7-200">Applies a Meta Configuration MOF file to the computer.</span></span> <span data-ttu-id="476e7-201">[Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) コマンドレットに似ています。</span><span class="sxs-lookup"><span data-stu-id="476e7-201">Similar to the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="476e7-202">適用するメタ構成 MOF へのパスが必要です。</span><span class="sxs-lookup"><span data-stu-id="476e7-202">Requires the path to the Meta Configuration MOF to apply.</span></span>

`# sudo ./SetDscLocalConfigurationManager.py –configurationmof /tmp/localhost.meta.mof`

## <a name="powershell-desired-state-configuration-for-linux-log-files"></a><span data-ttu-id="476e7-203">Linux 用 PowerShell Desired State Configuration のログ ファイル</span><span class="sxs-lookup"><span data-stu-id="476e7-203">PowerShell Desired State Configuration for Linux Log Files</span></span>

<span data-ttu-id="476e7-204">Linux 用 DSC のメッセージのために次のログ ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="476e7-204">The following log files are generated for DSC for Linux messages.</span></span>

|<span data-ttu-id="476e7-205">ログ ファイル</span><span class="sxs-lookup"><span data-stu-id="476e7-205">Log file</span></span>|<span data-ttu-id="476e7-206">Directory</span><span class="sxs-lookup"><span data-stu-id="476e7-206">Directory</span></span>|<span data-ttu-id="476e7-207">説明</span><span class="sxs-lookup"><span data-stu-id="476e7-207">Description</span></span>|
|---|---|---|
|<span data-ttu-id="476e7-208">**omiserver.log**</span><span class="sxs-lookup"><span data-stu-id="476e7-208">**omiserver.log**</span></span>|`/var/opt/omi/log`|<span data-ttu-id="476e7-209">OMI CIM サーバーの操作に関連するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="476e7-209">Messages relating to the operation of the OMI CIM server.</span></span>|
|<span data-ttu-id="476e7-210">**dsc.log**</span><span class="sxs-lookup"><span data-stu-id="476e7-210">**dsc.log**</span></span>|`/var/opt/omi/log`|<span data-ttu-id="476e7-211">ローカル構成マネージャー (LCM) と DSC リソースの操作に関連するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="476e7-211">Messages relating to the operation of the Local Configuration Manager (LCM) and DSC resource operations.</span></span>|
