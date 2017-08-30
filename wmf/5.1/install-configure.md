---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
contributor: keithb
title: "WMF 5.1 のインストールと構成"
ms.openlocfilehash: ea9b2fb184f2dd9a8e7a09c3a36278087f795172
ms.sourcegitcommit: a5c0795ca6ec9332967bff9c151a8572feb1a53a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2017
---
# <a name="install-and-configure-wmf-51"></a><span data-ttu-id="a62d7-103">WMF 5.1 のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="a62d7-103">Install and Configure WMF 5.1</span></span> #


## <a name="download-and-install-the-wmf-51-package"></a><span data-ttu-id="a62d7-104">WMF 5.1 パッケージのダウンロードとインストール</span><span class="sxs-lookup"><span data-stu-id="a62d7-104">Download and install the WMF 5.1 package</span></span>

<span data-ttu-id="a62d7-105">インストールするオペレーティング システムとアーキテクチャに合わせて WMF 5.1 パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a62d7-105">Download the WMF 5.1 package for the operating system and architecture you wish to install it on:</span></span>

| <span data-ttu-id="a62d7-106">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="a62d7-106">Operating System</span></span>       | <span data-ttu-id="a62d7-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a62d7-107">Prerequisites</span></span>       | <span data-ttu-id="a62d7-108">パッケージ リンク</span><span class="sxs-lookup"><span data-stu-id="a62d7-108">Package Links</span></span>             |
|------------------------|---------------------|---------------------------|
| <span data-ttu-id="a62d7-109">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a62d7-109">Windows Server 2012 R2</span></span> | | [<span data-ttu-id="a62d7-110">Win8.1AndW2K12R2-KB3191564-x64.msu</span><span class="sxs-lookup"><span data-stu-id="a62d7-110">Win8.1AndW2K12R2-KB3191564-x64.msu</span></span>](https://go.microsoft.com/fwlink/?linkid=839516)|
| <span data-ttu-id="a62d7-111">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a62d7-111">Windows Server 2012</span></span>    | | [<span data-ttu-id="a62d7-112">W2K12-KB3191565-x64.msu</span><span class="sxs-lookup"><span data-stu-id="a62d7-112">W2K12-KB3191565-x64.msu</span></span>](https://go.microsoft.com/fwlink/?linkid=839513)|
| <span data-ttu-id="a62d7-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a62d7-113">Windows Server 2008 R2</span></span> | [<span data-ttu-id="a62d7-114">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="a62d7-114">.NET Framework 4.5.2</span></span>](https://www.microsoft.com/en-ca/download/details.aspx?id=42642) | [<span data-ttu-id="a62d7-115">Win7AndW2K8R2-KB3191566-x64.ZIP</span><span class="sxs-lookup"><span data-stu-id="a62d7-115">Win7AndW2K8R2-KB3191566-x64.ZIP</span></span>](https://go.microsoft.com/fwlink/?linkid=839523) | 
| <span data-ttu-id="a62d7-116">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a62d7-116">Windows 8.1</span></span>            |  | <span data-ttu-id="a62d7-117">**x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu](https://go.microsoft.com/fwlink/?linkid=839516)</span><span class="sxs-lookup"><span data-stu-id="a62d7-117">**x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu](https://go.microsoft.com/fwlink/?linkid=839516)</span></span> </br> <span data-ttu-id="a62d7-118">**x86:** [Win8.1-KB3191564-x86.msu](https://go.microsoft.com/fwlink/?linkid=839521)</span><span class="sxs-lookup"><span data-stu-id="a62d7-118">**x86:** [Win8.1-KB3191564-x86.msu](https://go.microsoft.com/fwlink/?linkid=839521)</span></span> |
| <span data-ttu-id="a62d7-119">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="a62d7-119">Windows 7 SP1</span></span>          | [<span data-ttu-id="a62d7-120">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="a62d7-120">.NET Framework 4.5.2</span></span>](https://www.microsoft.com/en-ca/download/details.aspx?id=42642) | <span data-ttu-id="a62d7-121">**x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP](https://go.microsoft.com/fwlink/?linkid=839523)</span><span class="sxs-lookup"><span data-stu-id="a62d7-121">**x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP](https://go.microsoft.com/fwlink/?linkid=839523)</span></span> </br> <span data-ttu-id="a62d7-122">**x86:** [Win7-KB3191566-x86.ZIP](https://go.microsoft.com/fwlink/?linkid=839522)</span><span class="sxs-lookup"><span data-stu-id="a62d7-122">**x86:** [Win7-KB3191566-x86.ZIP](https://go.microsoft.com/fwlink/?linkid=839522)</span></span>



## <a name="install-wmf-51-for-windows-server-2008-r2-and-windows-7"></a><span data-ttu-id="a62d7-123">Windows Server 2008 R2 および Windows 7 で WMF 5.1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="a62d7-123">Install WMF 5.1 for Windows Server 2008 R2 and Windows 7</span></span>

> <span data-ttu-id="a62d7-124">**注:** Windows Server 2008 R2 および Windows 7 でのインストール手順は変更されているため、他のパッケージの手順と異なります。</span><span class="sxs-lookup"><span data-stu-id="a62d7-124">**Note:** Installation instructions for Windows Server 2008 R2 and Windows 7 have changed, and differ from the instructions for the other packages.</span></span> <span data-ttu-id="a62d7-125">Windows Server 2012 R2、Windows Server 2012、および Windows 8.1 のインストール手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a62d7-125">Installation instructions for Windows Server 2012 R2, Windows Server 2012, and Windows 8.1 are below.</span></span>

<span data-ttu-id="a62d7-126">**Windows Server 2008 R2 および Windows 7 で WMF 5.1 をインストールする**</span><span class="sxs-lookup"><span data-stu-id="a62d7-126">**Installing WMF 5.1 on Windows Server 2008 R2 and Windows 7**</span></span>

1. <span data-ttu-id="a62d7-127">ZIP ファイルをダウンロードしたフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-127">Navigate to the folder into which you downloaded the ZIP file.</span></span> 

2. <span data-ttu-id="a62d7-128">ZIP ファイルを右クリックし、[すべて展開...] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-128">Right-click on the ZIP file, and select "Extract All...".</span></span> <span data-ttu-id="a62d7-129">ZIP ファイルには、MSU ファイルと Install-WMF5.1.PS1 スクリプト ファイルの 2 つのファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a62d7-129">The Zip contains 2 files: an MSU and the Install-WMF5.1.PS1 script file.</span></span> <span data-ttu-id="a62d7-130">ZIP ファイルを展開したら、Windows 7 または Windows Server 2008 R2 を実行する任意のコンピューターにコンテンツをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="a62d7-130">Once you have unpacked the ZIP file, you can copy the contents to any machine running Windows 7 or Windows Server 2008 R2.</span></span>  

3. <span data-ttu-id="a62d7-131">ZIP ファイルを展開した後、管理者として PowerShell を開いて、ZIP ファイルのコンテンツを含むフォルダーに</span><span class="sxs-lookup"><span data-stu-id="a62d7-131">After extracting the ZIP file contents, open PowerShell as administrator, then navigate to the folder containing the</span></span>  
<span data-ttu-id="a62d7-132">移動します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-132">contents of the ZIP file.</span></span> 

4. <span data-ttu-id="a62d7-133">そのフォルダーの Install-Wmf5.1.ps1 スクリプトを実行して、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="a62d7-133">Run the Install-Wmf5.1.ps1 script in that folder, and follow the instructions.</span></span> <span data-ttu-id="a62d7-134">このスクリプトはローカル コンピューターの前提条件を確認し、前提条件を満たしている場合に WMF 5.1 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a62d7-134">This script will check the prerequisites on the local machine, and install WMF 5.1 if the prerequisites have been met.</span></span> <span data-ttu-id="a62d7-135">前提条件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a62d7-135">The prerequisites are listed below.</span></span> 

<span data-ttu-id="a62d7-136">Install-WMF5.1.ps1 は Windows Server 2008 R2 および Windows 7 でのインストールの自動化を容易にするため、次のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a62d7-136">Install-WMF5.1.ps1 takes the following parameters to ease automating the installation on Windows Server 2008 R2 and Windows 7:</span></span>

- <span data-ttu-id="a62d7-137">AcceptEula: このパラメーターが含まれる場合、使用許諾契約書は自動的に受け入れられ、表示はされません。</span><span class="sxs-lookup"><span data-stu-id="a62d7-137">AcceptEula: When this parameter is included, the EULA is automatically accepted and will not be displayed.</span></span>
- <span data-ttu-id="a62d7-138">AllowRestart: このパラメーターは、AcceptEula が指定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a62d7-138">AllowRestart: This parameter can only be used if AcceptEula is specified.</span></span> <span data-ttu-id="a62d7-139">このパラメーターが含まれていて、WMF 5.1 のインストール後に再起動が必要な場合は、インストールが完了した後すぐに、メッセージが表示されることなく再起動が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a62d7-139">If this parameter is included, and a restart is required after installing WMF 5.1, the restart will happen without prompting immediately after the installation is completed.</span></span> 

<span data-ttu-id="a62d7-140">**Windows Server 2008 R2 SP1 および Windows 7 SP1 での WMF 5.1 の前提条件**</span><span class="sxs-lookup"><span data-stu-id="a62d7-140">**WMF 5.1 Prerequisites for Windows Server 2008 R2 SP1 and Windows 7 SP1**</span></span>

<span data-ttu-id="a62d7-141">Windows Server 2008 R2 SP1 または Windows 7 SP1 に WMF 5.1 をインストールするには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a62d7-141">Installation of WMF 5.1 on either Windows Server 2008 R2 SP1 or Windows 7 SP1, requires the following:</span></span>
- <span data-ttu-id="a62d7-142">最新の Service Pack をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a62d7-142">Latest service pack must be installed.</span></span>
- <span data-ttu-id="a62d7-143">WMF 3.0 をインストール**しないでください**。</span><span class="sxs-lookup"><span data-stu-id="a62d7-143">WMF 3.0 **must not** be installed.</span></span> <span data-ttu-id="a62d7-144">WMF 3.0 経由で WMF 5.1 をインストールすると、PSModulePath が失われ、これによって他のアプリケーションで障害が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a62d7-144">Installing WMF 5.1 over WMF 3.0 will result in the loss of the PSModulePath, which can cause other applications to fail.</span></span> <span data-ttu-id="a62d7-145">WMF 5.1 をインストールする前に WMF 3.0 をアンインストールするか、PSModulePath を保存して、WMF 5.1 のインストールが完了した後に手動で復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a62d7-145">Before installing WMF 5.1, you must either un-install WMF 3.0, or save the PSModulePath and then restore it manually after WMF 5.1 installation is complete.</span></span> 
- <span data-ttu-id="a62d7-146">WMF 5.1 には [.NET Framework 4.5.2](https://www.microsoft.com/en-ca/download/details.aspx?id=42642) 以上が必要です。Microsoft .NET Framework 4.5.2 をインストールするには、ダウンロード場所で提供されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="a62d7-146">WMF 5.1 requires at least [.NET Framework 4.5.2](https://www.microsoft.com/en-ca/download/details.aspx?id=42642) You can install Microsoft .NET Framework 4.5.2 by following the instructions at the download location.</span></span>

<span data-ttu-id="a62d7-147">**WinRM の依存関係**</span><span class="sxs-lookup"><span data-stu-id="a62d7-147">**WinRM Dependency**</span></span> 

<span data-ttu-id="a62d7-148">Windows PowerShell Desired State Configuration (DSC) は、WinRM に依存します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-148">Windows PowerShell Desired State Configuration (DSC) depends on WinRM.</span></span> <span data-ttu-id="a62d7-149">WinRM は、Windows Server 2008 R2 および Windows 7 では既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a62d7-149">WinRM is not enabled by default on Windows Server 2008 R2 and Windows 7.</span></span> <span data-ttu-id="a62d7-150">WinRM を有効にするには、Windows PowerShell 管理者特権セッションで `Set-WSManQuickConfig` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-150">Run `Set-WSManQuickConfig`, in a Windows PowerShell elevated session, to enable WinRM.</span></span>


## <a name="install-wmf-51-for-windows-server-2012-r2-windows-server-2012-and-windows-81"></a><span data-ttu-id="a62d7-151">Windows Server 2012 R2、Windows Server 2012、および Windows 8.1 で WMF 5.1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="a62d7-151">Install WMF 5.1 for Windows Server 2012 R2, Windows Server 2012, and Windows 8.1</span></span>
<span data-ttu-id="a62d7-152">**Windows エクスプローラー (または Windows Server 2012 R2 または Windows 8.1 ではファイル エクスプローラー) からインストールする**</span><span class="sxs-lookup"><span data-stu-id="a62d7-152">**Install from Windows Explorer (or File Explorer in Windows Server 2012 R2 or Windows 8.1)**</span></span>

1. <span data-ttu-id="a62d7-153">MSU ファイルをダウンロードしたフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-153">Navigate to the folder into which you downloaded the MSU file.</span></span>

2. <span data-ttu-id="a62d7-154">MSU をダブルクリックして実行します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-154">Double-click the MSU to run it.</span></span>

<span data-ttu-id="a62d7-155">**コマンド プロンプトからインストールする**</span><span class="sxs-lookup"><span data-stu-id="a62d7-155">**Installing from the Command Prompt**</span></span>

1. <span data-ttu-id="a62d7-156">コンピューターのアーキテクチャに適切なパッケージをダウンロードした後、管理者特権 (管理者として実行) を使ってコマンド プロンプト ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="a62d7-156">After downloading the correct package for your computer's architecture, open a Command Prompt window with elevated user rights (Run as Administrator).</span></span> <span data-ttu-id="a62d7-157">Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 SP1 の Server Core インストール オプションで、既定で管理者特権でコマンド プロンプトが開きます。</span><span class="sxs-lookup"><span data-stu-id="a62d7-157">On the Server Core installation options of Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1, Command Prompt opens with elevated user rights by default.</span></span>

2. <span data-ttu-id="a62d7-158">WMF 5.1 のインストール パッケージをダウンロードまたはコピーしたフォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-158">Change directories to the folder into which you have downloaded or copied the WMF 5.1 installation package.</span></span>

3. <span data-ttu-id="a62d7-159">次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-159">Run one of the following commands:</span></span>
    - <span data-ttu-id="a62d7-160">Windows Server 2012 R2 または Windows 8.1 x64 を実行しているコンピューターの場合は、`Win8.1AndW2K12R2-KB3191564-x64.msu /quiet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-160">On computers that are running Windows Server 2012 R2 or Windows 8.1 x64, run `Win8.1AndW2K12R2-KB3191564-x64.msu /quiet`.</span></span>
    - <span data-ttu-id="a62d7-161">Windows Server 2012 を実行しているコンピューターの場合は、`W2K12-KB3191565-x64.msu /quiet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-161">On computers that are running Windows Server 2012, run `W2K12-KB3191565-x64.msu /quiet`.</span></span>
    - <span data-ttu-id="a62d7-162">Windows 8.1 x86 を実行しているコンピューターの場合は、`Win8.1-KB3191564-x86.msu /quiet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a62d7-162">On computers that are running Windows 8.1 x86, run `Win8.1-KB3191564-x86.msu /quiet`.</span></span>
    
