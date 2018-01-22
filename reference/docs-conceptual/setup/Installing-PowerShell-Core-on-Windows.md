# <a name="installing-powershell-core-on-windows"></a><span data-ttu-id="b65d2-101">Windows への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="b65d2-101">Installing PowerShell Core on Windows</span></span>

## <a name="msi"></a><span data-ttu-id="b65d2-102">MSI</span><span class="sxs-lookup"><span data-stu-id="b65d2-102">MSI</span></span>

<span data-ttu-id="b65d2-103">PowerShell を Windows クライアントまたは Windows Server にインストールするには (Windows 7 SP1、Server 2008 R2 以降で機能)、MSI パッケージを弊社の GitHub [リリース][] ページからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b65d2-103">To install PowerShell on a Windows client or Windows Server (works on Windows 7 SP1, Server 2008 R2, and later), download the MSI package from our GitHub [releases][] page.</span></span>

<span data-ttu-id="b65d2-104">MSI ファイルは、`PowerShell-6.0.0.<buildversion>.<os-arch>.msi` のようになります。</span><span class="sxs-lookup"><span data-stu-id="b65d2-104">The MSI file looks like this - `PowerShell-6.0.0.<buildversion>.<os-arch>.msi`</span></span>
<!-- TODO: should be updated to point to the Download Center as well -->

<span data-ttu-id="b65d2-105">ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="b65d2-105">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="b65d2-106">インストールすると [スタート] メニューにショートカットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b65d2-106">There is a shortcut placed in the Start Menu upon installation.</span></span>

* <span data-ttu-id="b65d2-107">パッケージは、既定で `$env:ProgramFiles\PowerShell\` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b65d2-107">By default the package is installed to `$env:ProgramFiles\PowerShell\`</span></span>
* <span data-ttu-id="b65d2-108">PowerShell は、[スタート] メニューまたは `$env:ProgramFiles\PowerShell\pwsh.exe` から起動できます。</span><span class="sxs-lookup"><span data-stu-id="b65d2-108">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\pwsh.exe`</span></span>

### <a name="prerequisites"></a><span data-ttu-id="b65d2-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="b65d2-109">Prerequisites</span></span>

<span data-ttu-id="b65d2-110">WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b65d2-110">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

* <span data-ttu-id="b65d2-111">Windows 10 以前のバージョンの Windows に [ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b65d2-111">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions prior to Windows 10.</span></span>
  <span data-ttu-id="b65d2-112">これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="b65d2-112">It is available via direct download or Windows Update.</span></span>
  <span data-ttu-id="b65d2-113">(オプション パッケージも含め) 修正プログラムはすべて適用されており、サポート対象のシステムには、これが既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="b65d2-113">Fully patched (including optional packages), supported systems will already have this installed.</span></span>
* <span data-ttu-id="b65d2-114">Windows Management Framework (WMF) [4.0](https://www.microsoft.com/download/details.aspx?id=40855) 以降 ([5.1](https://www.microsoft.com/download/details.aspx?id=54616)) を Windows 7 と Windows Server 2008 R2 にインストールします。</span><span class="sxs-lookup"><span data-stu-id="b65d2-114">Install the Windows Management Framework (WMF) [4.0](https://www.microsoft.com/download/details.aspx?id=40855) or newer ([5.1](https://www.microsoft.com/download/details.aspx?id=54616)) on Windows 7 and Windows Server 2008 R2.</span></span>

## <a name="zip"></a><span data-ttu-id="b65d2-115">ZIP</span><span class="sxs-lookup"><span data-stu-id="b65d2-115">ZIP</span></span>

<span data-ttu-id="b65d2-116">PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="b65d2-116">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span>
<span data-ttu-id="b65d2-117">なお、ZIP アーカイブを使用する場合、MSI パッケージのような前提条件確認は行われません。</span><span class="sxs-lookup"><span data-stu-id="b65d2-117">Be noted that when using the ZIP archive, you won't get the prerequisites check as in the MSI package.</span></span>
<span data-ttu-id="b65d2-118">したがって、Windows 10 以前のバージョンで WSMan 経由でのリモート処理が正常に動作するには、[前提条件](#prerequisites)が満たされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b65d2-118">So in order for remoting over WSMan to work properly on Windows versions prior to Windows 10, you need to make sure the [prerequisites](#prerequisites) are met.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="b65d2-119">Nano Server への展開</span><span class="sxs-lookup"><span data-stu-id="b65d2-119">Deploying on Nano Server</span></span>

<span data-ttu-id="b65d2-120">これらの手順では、Nano Server イメージ上で PowerShell のバージョンが既に実行されており、それが [Nano Server Image Builder](https://technet.microsoft.com/windows-server-docs/get-started/deploy-nano-server) で生成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b65d2-120">These instructions assume that a version of PowerShell is already running on the Nano Server image and that it has been generated by the [Nano Server Image Builder](https://technet.microsoft.com/windows-server-docs/get-started/deploy-nano-server).</span></span>
<span data-ttu-id="b65d2-121">Nano Server は、"ヘッドレス" OS であり、PowerShell Core バイナリは次の 2 つの方法で展開できます。</span><span class="sxs-lookup"><span data-stu-id="b65d2-121">Nano Server is a "headless" OS and deployment of PowerShell Core binaries can happen in two different ways:</span></span>

1. <span data-ttu-id="b65d2-122">オフライン: Nano Server VHD をマウントし、zip ファイルの中身をマウント イメージ内の選択した場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="b65d2-122">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="b65d2-123">オンライン: zip ファイルを PowerShell セッションを介して転送し、選択した場所にそれを展開します。</span><span class="sxs-lookup"><span data-stu-id="b65d2-123">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="b65d2-124">いずれの場合も、Windows 10 x64 Zip リリース パッケージが必要であり、"管理者" PowerShell インスタンス内でコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b65d2-124">In both cases, you will need the Windows 10 x64 Zip release package and will need to run the commands within an "Administrator" PowerShell instance.</span></span>

### <a name="offline-deployment-of-powershell-core"></a><span data-ttu-id="b65d2-125">PowerShell Core のオフラインでの展開</span><span class="sxs-lookup"><span data-stu-id="b65d2-125">Offline Deployment of PowerShell Core</span></span>

1. <span data-ttu-id="b65d2-126">お好みの zip ユーティリティを使用して、マウントされた Nano Server イメージ内のディレクトリにパッケージを解凍します。</span><span class="sxs-lookup"><span data-stu-id="b65d2-126">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="b65d2-127">イメージをマウント解除し、ブートします。</span><span class="sxs-lookup"><span data-stu-id="b65d2-127">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="b65d2-128">Windows PowerShell のインボックス インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="b65d2-128">Connect to the inbox instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="b65d2-129">[別のインスタンスのテクニック](#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b65d2-129">Follow the instructions to create a remoting endpoint using the [another instance technique](#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell-core"></a><span data-ttu-id="b65d2-130">オンラインでの PowerShell Core の展開</span><span class="sxs-lookup"><span data-stu-id="b65d2-130">Online Deployment of PowerShell Core</span></span>

<span data-ttu-id="b65d2-131">次の手順では、PowerShell Core を Nano Server の実行中のインスタンスに展開し、そのリモート エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="b65d2-131">The following steps will guide you through the deployment of PowerShell Core to a running instance of Nano Server and the configuration of its remote endpoint.</span></span>

* <span data-ttu-id="b65d2-132">Windows PowerShell のインボックス インスタンスに接続する</span><span class="sxs-lookup"><span data-stu-id="b65d2-132">Connect to the inbox instance of Windows PowerShell</span></span>

```powershell
$session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
```

* <span data-ttu-id="b65d2-133">Nano Server のインスタンスにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="b65d2-133">Copy the file to the Nano Server instance</span></span>

```powershell
Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
```

* <span data-ttu-id="b65d2-134">セッションに入る</span><span class="sxs-lookup"><span data-stu-id="b65d2-134">Enter the session</span></span>

```powershell
Enter-PSSession $session
```

* <span data-ttu-id="b65d2-135">ZIP ファイルを抽出する</span><span class="sxs-lookup"><span data-stu-id="b65d2-135">Extract the Zip file</span></span>

```powershell
# Insert the appropriate version.
Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
```

* <span data-ttu-id="b65d2-136">WSMan を使用してリモート処理を行う場合、[別のインスタンスのテクニック](../core-powershell/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b65d2-136">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the [another instance technique](../core-powershell/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="instructions-to-create-a-remoting-endpoint"></a><span data-ttu-id="b65d2-137">リモート エンドポイントの作成手順</span><span class="sxs-lookup"><span data-stu-id="b65d2-137">Instructions to Create a Remoting Endpoint</span></span>

<span data-ttu-id="b65d2-138">PowerShell Core は、WSMan と SSH の両方で PowerShell Remoting Protocol (PSRP) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b65d2-138">PowerShell Core supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="b65d2-139">詳細については、次のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b65d2-139">For more information, see:</span></span>

* <span data-ttu-id="b65d2-140">[PowerShell Core での SSH リモート処理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="b65d2-140">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
* <span data-ttu-id="b65d2-141">[PowerShell Core での WSMan リモート処理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="b65d2-141">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="artifact-installation-instructions"></a><span data-ttu-id="b65d2-142">成果物のインストール手順</span><span class="sxs-lookup"><span data-stu-id="b65d2-142">Artifact Installation Instructions</span></span>

<span data-ttu-id="b65d2-143">アーカイブは CoreCLR ビットを使用して各 CI ビルドに [AppVeyor][] で公開します。</span><span class="sxs-lookup"><span data-stu-id="b65d2-143">We publish an archive with CoreCLR bits on every CI build with [AppVeyor][].</span></span>

## <a name="coreclr-artifacts"></a><span data-ttu-id="b65d2-144">CoreCLR の成果物</span><span class="sxs-lookup"><span data-stu-id="b65d2-144">CoreCLR Artifacts</span></span>

* <span data-ttu-id="b65d2-145">特定のビルドの **[artifacts]\(成果物\)** タブから、zip パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b65d2-145">Download zip package from **artifacts** tab of the particular build.</span></span>
* <span data-ttu-id="b65d2-146">[エクスプローラー] で右クリックし、[プロパティ] をクリックし、[ブロックの解除] ボックスをオンにして zip ファイルのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="b65d2-146">Unblock zip file: right-click in File Explorer -> Properties -> check 'Unblock' box -> apply</span></span>
* <span data-ttu-id="b65d2-147">zip ファイルを `bin` ディレクトリに抽出します</span><span class="sxs-lookup"><span data-stu-id="b65d2-147">Extract zip file to `bin` directory</span></span>
* `./bin/pwsh.exe`

<!-- [download-center]: TODO -->
[リリース]: https://github.com/PowerShell/PowerShell/releases
[signing]: ../../tools/Sign-Package.ps1
[ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../core-powershell/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
