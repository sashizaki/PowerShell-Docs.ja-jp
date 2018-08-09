---
title: Windows への PowerShell Core のインストール
description: Windows への PowerShell Core のインストールに関する情報
ms.date: 08/06/2018
ms.openlocfilehash: 84c158b97519194888cf031c57a2a4634120c456
ms.sourcegitcommit: 01ac77cd0b00e4e5e964504563a9212e8002e5e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39587120"
---
# <a name="installing-powershell-core-on-windows"></a><span data-ttu-id="263d1-103">Windows への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="263d1-103">Installing PowerShell Core on Windows</span></span>

## <a name="msi"></a><span data-ttu-id="263d1-104">MSI</span><span class="sxs-lookup"><span data-stu-id="263d1-104">MSI</span></span>

<span data-ttu-id="263d1-105">PowerShell を Windows クライアントまたは Windows Server にインストールするには (Windows 7 SP1、Server 2008 R2 以降で機能)、MSI パッケージを弊社の GitHub [リリース][] ページからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="263d1-105">To install PowerShell on a Windows client or Windows Server (works on Windows 7 SP1, Server 2008 R2, and later), download the MSI package from our GitHub [releases][] page.</span></span>

<span data-ttu-id="263d1-106">MSI ファイルは、`PowerShell-<version>-win-<os-arch>.msi`
<!-- TODO: should be updated to point to the Download Center as well --> のようになります。</span><span class="sxs-lookup"><span data-stu-id="263d1-106">The MSI file looks like this - `PowerShell-<version>-win-<os-arch>.msi`
<!-- TODO: should be updated to point to the Download Center as well --></span></span>

<span data-ttu-id="263d1-107">ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="263d1-107">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="263d1-108">インストールすると [スタート] メニューにショートカットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="263d1-108">There is a shortcut placed in the Start Menu upon installation.</span></span>

- <span data-ttu-id="263d1-109">パッケージは、既定で `$env:ProgramFiles\PowerShell\<version>` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="263d1-109">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="263d1-110">PowerShell は、スタート メニューまたは  `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` から起動できます。</span><span class="sxs-lookup"><span data-stu-id="263d1-110">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

### <a name="prerequisites"></a><span data-ttu-id="263d1-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="263d1-111">Prerequisites</span></span>

<span data-ttu-id="263d1-112">WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="263d1-112">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="263d1-113">Windows 10 以前のバージョンの Windows に [ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="263d1-113">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions prior to Windows 10.</span></span>
  <span data-ttu-id="263d1-114">これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="263d1-114">It is available via direct download or Windows Update.</span></span>
  <span data-ttu-id="263d1-115">(オプション パッケージも含め) 修正プログラムはすべて適用されており、サポート対象のシステムには、これが既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="263d1-115">Fully patched (including optional packages), supported systems will already have this installed.</span></span>
- <span data-ttu-id="263d1-116">Windows Management Framework (WMF) 4.0 以降を Windows 7 と Windows Server 2008 R2 にインストールします。</span><span class="sxs-lookup"><span data-stu-id="263d1-116">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span>

## <a name="zip"></a><span data-ttu-id="263d1-117">ZIP</span><span class="sxs-lookup"><span data-stu-id="263d1-117">ZIP</span></span>

<span data-ttu-id="263d1-118">PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="263d1-118">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span>
<span data-ttu-id="263d1-119">なお、ZIP アーカイブを使用する場合、MSI パッケージのような前提条件確認は行われません。</span><span class="sxs-lookup"><span data-stu-id="263d1-119">Be noted that when using the ZIP archive, you won't get the prerequisites check as in the MSI package.</span></span>
<span data-ttu-id="263d1-120">したがって、Windows 10 以前のバージョンで WSMan 経由でのリモート処理が正常に動作するには、[前提条件](#prerequisites)が満たされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="263d1-120">So in order for remoting over WSMan to work properly on Windows versions prior to Windows 10, you need to make sure the [prerequisites](#prerequisites) are met.</span></span>

## <a name="deploying-on-windows-iot"></a><span data-ttu-id="263d1-121">Windows IoT への展開</span><span class="sxs-lookup"><span data-stu-id="263d1-121">Deploying on Windows IoT</span></span>

<span data-ttu-id="263d1-122">Windows IoT には既に Windows PowerShell が付属しており、PowerShell Core 6 の展開に使用します。</span><span class="sxs-lookup"><span data-stu-id="263d1-122">Windows IoT already comes with Windows PowerShell which we will use to deploy PowerShell Core 6.</span></span>

1. <span data-ttu-id="263d1-123">ターゲット デバイスに対して `PSSession` を作成します</span><span class="sxs-lookup"><span data-stu-id="263d1-123">Create `PSSession` to target device</span></span>

   ```powershell
   $s = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="263d1-124">ZIP パッケージをデバイスにコピーします</span><span class="sxs-lookup"><span data-stu-id="263d1-124">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-6.0.2-win-arm32.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="263d1-125">デバイスに接続してアーカイブを展開します</span><span class="sxs-lookup"><span data-stu-id="263d1-125">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   cd u:\users\administrator\downloads
   Expand-Archive .\PowerShell-6.0.2-win-arm32.zip
   ```

4. <span data-ttu-id="263d1-126">PowerShell Core 6 へのリモート処理を設定します</span><span class="sxs-lookup"><span data-stu-id="263d1-126">Setup remoting to PowerShell Core 6</span></span>

   ```powershell
   cd .\PowerShell-6.0.2-win-arm32
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="263d1-127">デバイス上の PowerShell Core 6 エンドポイントに接続します</span><span class="sxs-lookup"><span data-stu-id="263d1-127">Connect to PowerShell Core 6 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.6.0.2
   ```

## <a name="deploying-on-nano-server"></a><span data-ttu-id="263d1-128">Nano Server への展開</span><span class="sxs-lookup"><span data-stu-id="263d1-128">Deploying on Nano Server</span></span>

<span data-ttu-id="263d1-129">これらの手順では、Nano Server イメージ上で PowerShell のバージョンが既に実行されており、それが [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) で生成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="263d1-129">These instructions assume that a version of PowerShell is already running on the Nano Server image and that it has been generated by the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span></span>
<span data-ttu-id="263d1-130">Nano Server は "ヘッドレス" OS です。</span><span class="sxs-lookup"><span data-stu-id="263d1-130">Nano Server is a "headless" OS.</span></span> <span data-ttu-id="263d1-131">コア バイナリを展開するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="263d1-131">Core binaries can be deploy using two different methods.</span></span>

1. <span data-ttu-id="263d1-132">オフライン: Nano Server VHD をマウントし、zip ファイルの中身をマウント イメージ内の選択した場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="263d1-132">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="263d1-133">オンライン: zip ファイルを PowerShell セッションを介して転送し、選択した場所にそれを展開します。</span><span class="sxs-lookup"><span data-stu-id="263d1-133">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="263d1-134">いずれの場合も、Windows 10 x64 ZIP リリース パッケージが必要であり、"管理者" PowerShell インスタンス内でコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="263d1-134">In both cases, you will need the Windows 10 x64 ZIP release package and will need to run the commands within an "Administrator" PowerShell instance.</span></span>

### <a name="offline-deployment-of-powershell-core"></a><span data-ttu-id="263d1-135">PowerShell Core のオフラインでの展開</span><span class="sxs-lookup"><span data-stu-id="263d1-135">Offline Deployment of PowerShell Core</span></span>

1. <span data-ttu-id="263d1-136">お好みの zip ユーティリティを使用して、マウントされた Nano Server イメージ内のディレクトリにパッケージを解凍します。</span><span class="sxs-lookup"><span data-stu-id="263d1-136">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="263d1-137">イメージをマウント解除し、ブートします。</span><span class="sxs-lookup"><span data-stu-id="263d1-137">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="263d1-138">Windows PowerShell のインボックス インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="263d1-138">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="263d1-139">「[別のインスタンスのテクニック](#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="263d1-139">Follow the instructions to create a remoting endpoint using the ["another instance technique"](#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell-core"></a><span data-ttu-id="263d1-140">オンラインでの PowerShell Core の展開</span><span class="sxs-lookup"><span data-stu-id="263d1-140">Online Deployment of PowerShell Core</span></span>

<span data-ttu-id="263d1-141">次の手順では、PowerShell Core を Nano Server の実行中のインスタンスに展開し、そのリモート エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="263d1-141">The following steps guide you through the deployment of PowerShell Core to a running instance of Nano Server and the configuration of its remote endpoint.</span></span>

- <span data-ttu-id="263d1-142">Windows PowerShell のインボックス インスタンスに接続する</span><span class="sxs-lookup"><span data-stu-id="263d1-142">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="263d1-143">Nano Server のインスタンスにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="263d1-143">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="263d1-144">セッションに入る</span><span class="sxs-lookup"><span data-stu-id="263d1-144">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="263d1-145">ZIP ファイルを抽出する</span><span class="sxs-lookup"><span data-stu-id="263d1-145">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
  ```

- <span data-ttu-id="263d1-146">WSMan を使用してリモート処理を行う場合、「[別のインスタンスのテクニック](../core-powershell/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="263d1-146">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../core-powershell/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="instructions-to-create-a-remoting-endpoint"></a><span data-ttu-id="263d1-147">リモート エンドポイントの作成手順</span><span class="sxs-lookup"><span data-stu-id="263d1-147">Instructions to Create a Remoting Endpoint</span></span>

<span data-ttu-id="263d1-148">PowerShell Core は、WSMan と SSH の両方で PowerShell Remoting Protocol (PSRP) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="263d1-148">PowerShell Core supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span>
<span data-ttu-id="263d1-149">詳細については、次のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="263d1-149">For more information, see:</span></span>

- <span data-ttu-id="263d1-150">[PowerShell Core での SSH リモート処理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="263d1-150">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="263d1-151">[PowerShell Core での WSMan リモート処理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="263d1-151">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="artifact-installation-instructions"></a><span data-ttu-id="263d1-152">成果物のインストール手順</span><span class="sxs-lookup"><span data-stu-id="263d1-152">Artifact Installation Instructions</span></span>

<span data-ttu-id="263d1-153">アーカイブは CoreCLR ビットを使用して各 CI ビルドに [AppVeyor][] で公開します。</span><span class="sxs-lookup"><span data-stu-id="263d1-153">We publish an archive with CoreCLR bits on every CI build with [AppVeyor][].</span></span>

<span data-ttu-id="263d1-154">CoreCLR のアーティファクトから PowerShell Core をインストールするには:</span><span class="sxs-lookup"><span data-stu-id="263d1-154">To install PowerShell Core from the CoreCLR Artifact:</span></span>

1. <span data-ttu-id="263d1-155">特定のビルドの **[アーティファクト]** タブから、zip パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="263d1-155">Download ZIP package from **artifacts** tab of the particular build.</span></span>
2. <span data-ttu-id="263d1-156">[エクスプローラー] で右クリックし、[プロパティ] をクリックし、[ブロックの解除] ボックスをオンにして ZIP ファイルのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="263d1-156">Unblock ZIP file: right-click in File Explorer -> Properties -> check 'Unblock' box -> apply</span></span>
3. <span data-ttu-id="263d1-157">zip ファイルを `bin` ディレクトリに抽出します</span><span class="sxs-lookup"><span data-stu-id="263d1-157">Extract zip file to `bin` directory</span></span>
4. `./bin/pwsh.exe`

<!-- [download-center]: TODO -->

[リリース]: https://github.com/PowerShell/PowerShell/releases
[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../core-powershell/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
