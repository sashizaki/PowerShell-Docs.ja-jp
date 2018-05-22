---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
contributor: keithb
title: WMF 5.1 のインストールと構成
ms.openlocfilehash: e5c7968744a442b4be9f1e43a45e91429a6d6165
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="install-and-configure-wmf-51"></a><span data-ttu-id="b3ff3-103">WMF 5.1 のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="b3ff3-103">Install and Configure WMF 5.1</span></span> #


## <a name="download-and-install-the-wmf-51-package"></a><span data-ttu-id="b3ff3-104">WMF 5.1 パッケージのダウンロードとインストール</span><span class="sxs-lookup"><span data-stu-id="b3ff3-104">Download and install the WMF 5.1 package</span></span>

<span data-ttu-id="b3ff3-105">インストールするオペレーティング システムとアーキテクチャに合わせて WMF 5.1 パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-105">Download the WMF 5.1 package for the operating system and architecture you wish to install it on:</span></span>

| <span data-ttu-id="b3ff3-106">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b3ff3-106">Operating System</span></span>       | <span data-ttu-id="b3ff3-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="b3ff3-107">Prerequisites</span></span>           | <span data-ttu-id="b3ff3-108">パッケージ リンク</span><span class="sxs-lookup"><span data-stu-id="b3ff3-108">Package Links</span></span>                          |
|------------------------|-------------------------|----------------------------------------|
| <span data-ttu-id="b3ff3-109">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b3ff3-109">Windows Server 2012 R2</span></span> |                         | <span data-ttu-id="b3ff3-110">[Win8.1AndW2K12R2-KB3191564-x64.msu][]</span><span class="sxs-lookup"><span data-stu-id="b3ff3-110">[Win8.1AndW2K12R2-KB3191564-x64.msu][]</span></span> |
| <span data-ttu-id="b3ff3-111">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b3ff3-111">Windows Server 2012</span></span>    |                         | <span data-ttu-id="b3ff3-112">[W2K12-KB3191565-x64.msu][]</span><span class="sxs-lookup"><span data-stu-id="b3ff3-112">[W2K12-KB3191565-x64.msu][]</span></span>            |
| <span data-ttu-id="b3ff3-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b3ff3-113">Windows Server 2008 R2</span></span> | <span data-ttu-id="b3ff3-114">[.NET Framework 4.5.2][]</span><span class="sxs-lookup"><span data-stu-id="b3ff3-114">[.NET Framework 4.5.2][]</span></span>| <span data-ttu-id="b3ff3-115">[Win7AndW2K8R2-KB3191566-x64.ZIP][]</span><span class="sxs-lookup"><span data-stu-id="b3ff3-115">[Win7AndW2K8R2-KB3191566-x64.ZIP][]</span></span>    |
| <span data-ttu-id="b3ff3-116">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b3ff3-116">Windows 8.1</span></span>            |                         | <span data-ttu-id="b3ff3-117">**x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu][]</span><span class="sxs-lookup"><span data-stu-id="b3ff3-117">**x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu][]</span></span></br><span data-ttu-id="b3ff3-118">**x86:** [Win8.1-KB3191564-x86.msu][]</span><span class="sxs-lookup"><span data-stu-id="b3ff3-118">**x86:** [Win8.1-KB3191564-x86.msu][]</span></span> |
| <span data-ttu-id="b3ff3-119">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="b3ff3-119">Windows 7 SP1</span></span>          | <span data-ttu-id="b3ff3-120">[.NET Framework 4.5.2][]</span><span class="sxs-lookup"><span data-stu-id="b3ff3-120">[.NET Framework 4.5.2][]</span></span>| <span data-ttu-id="b3ff3-121">**x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP][]</span><span class="sxs-lookup"><span data-stu-id="b3ff3-121">**x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP][]</span></span></br><span data-ttu-id="b3ff3-122">**x86:** [Win7-KB3191566-x86.ZIP][]</span><span class="sxs-lookup"><span data-stu-id="b3ff3-122">**x86:** [Win7-KB3191566-x86.ZIP][]</span></span> |

[.NET Framework 4.5.2]: https://www.microsoft.com/download/details.aspx?id=42642
[W2K12-KB3191565-x64.msu]: https://go.microsoft.com/fwlink/?linkid=839513
[Win7-KB3191566-x86.ZIP]: https://go.microsoft.com/fwlink/?linkid=839522
[Win7AndW2K8R2-KB3191566-x64.ZIP]: https://go.microsoft.com/fwlink/?linkid=839523
[Win8.1-KB3191564-x86.msu]: https://go.microsoft.com/fwlink/?linkid=839521
[Win8.1AndW2K12R2-KB3191564-x64.msu]: https://go.microsoft.com/fwlink/?linkid=839516

## <a name="install-wmf-51-for-windows-server-2008-r2-and-windows-7"></a><span data-ttu-id="b3ff3-129">Windows Server 2008 R2 および Windows 7 で WMF 5.1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="b3ff3-129">Install WMF 5.1 for Windows Server 2008 R2 and Windows 7</span></span>

> <span data-ttu-id="b3ff3-130">**注:** Windows Server 2008 R2 および Windows 7 でのインストール手順は変更されているため、他のパッケージの手順と異なります。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-130">**Note:** Installation instructions for Windows Server 2008 R2 and Windows 7 have changed, and differ from the instructions for the other packages.</span></span> <span data-ttu-id="b3ff3-131">Windows Server 2012 R2、Windows Server 2012、および Windows 8.1 のインストール手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-131">Installation instructions for Windows Server 2012 R2, Windows Server 2012, and Windows 8.1 are below.</span></span>

<span data-ttu-id="b3ff3-132">**Windows Server 2008 R2 および Windows 7 で WMF 5.1 をインストールする**</span><span class="sxs-lookup"><span data-stu-id="b3ff3-132">**Installing WMF 5.1 on Windows Server 2008 R2 and Windows 7**</span></span>

1. <span data-ttu-id="b3ff3-133">ZIP ファイルをダウンロードしたフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-133">Navigate to the folder into which you downloaded the ZIP file.</span></span>

2. <span data-ttu-id="b3ff3-134">ZIP ファイルを右クリックし、[すべて展開...] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-134">Right-click on the ZIP file, and select "Extract All...".</span></span> <span data-ttu-id="b3ff3-135">ZIP ファイルには、MSU ファイルと Install-WMF5.1.PS1 スクリプト ファイルの 2 つのファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-135">The Zip contains 2 files: an MSU and the Install-WMF5.1.PS1 script file.</span></span>
<span data-ttu-id="b3ff3-136">ZIP ファイルを展開したら、Windows 7 または Windows Server 2008 R2 を実行する任意のコンピューターにコンテンツをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-136">Once you have unpacked the ZIP file, you can copy the contents to any machine running Windows 7 or Windows Server 2008 R2.</span></span>

3. <span data-ttu-id="b3ff3-137">ZIP ファイルを展開した後、PowerShell を管理者として開き、その ZIP ファイルの内容を含むフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-137">After extracting the ZIP file contents, open PowerShell as administrator, then navigate to the folder containing the contents of the ZIP file.</span></span>

4. <span data-ttu-id="b3ff3-138">そのフォルダーの Install-Wmf5.1.ps1 スクリプトを実行して、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-138">Run the Install-Wmf5.1.ps1 script in that folder, and follow the instructions.</span></span> <span data-ttu-id="b3ff3-139">このスクリプトはローカル コンピューターの前提条件を確認し、前提条件を満たしている場合に WMF 5.1 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-139">This script will check the prerequisites on the local machine, and install WMF 5.1 if the prerequisites have been met.</span></span> <span data-ttu-id="b3ff3-140">前提条件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-140">The prerequisites are listed below.</span></span>

<span data-ttu-id="b3ff3-141">Install-WMF5.1.ps1 は Windows Server 2008 R2 および Windows 7 でのインストールの自動化を容易にするため、次のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-141">Install-WMF5.1.ps1 takes the following parameters to ease automating the installation on Windows Server 2008 R2 and Windows 7:</span></span>

- <span data-ttu-id="b3ff3-142">AcceptEula: このパラメーターが含まれる場合、使用許諾契約書は自動的に受け入れられ、表示はされません。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-142">AcceptEula: When this parameter is included, the EULA is automatically accepted and will not be displayed.</span></span>
- <span data-ttu-id="b3ff3-143">AllowRestart: このパラメーターは、AcceptEula が指定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-143">AllowRestart: This parameter can only be used if AcceptEula is specified.</span></span> <span data-ttu-id="b3ff3-144">このパラメーターが含まれていて、WMF 5.1 のインストール後に再起動が必要な場合は、インストールが完了した後すぐに、メッセージが表示されることなく再起動が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-144">If this parameter is included, and a restart is required after installing WMF 5.1, the restart will happen without prompting immediately after the installation is completed.</span></span>

<span data-ttu-id="b3ff3-145">**Windows Server 2008 R2 SP1 および Windows 7 SP1 での WMF 5.1 の前提条件**</span><span class="sxs-lookup"><span data-stu-id="b3ff3-145">**WMF 5.1 Prerequisites for Windows Server 2008 R2 SP1 and Windows 7 SP1**</span></span>

<span data-ttu-id="b3ff3-146">Windows Server 2008 R2 SP1 または Windows 7 SP1 に WMF 5.1 をインストールするには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-146">Installation of WMF 5.1 on either Windows Server 2008 R2 SP1 or Windows 7 SP1, requires the following:</span></span>
- <span data-ttu-id="b3ff3-147">最新の Service Pack をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-147">Latest service pack must be installed.</span></span>
- <span data-ttu-id="b3ff3-148">WMF 3.0 をインストール**しないでください**。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-148">WMF 3.0 **must not** be installed.</span></span> <span data-ttu-id="b3ff3-149">WMF 3.0 経由で WMF 5.1 をインストールすると、PSModulePath が失われ、これによって他のアプリケーションで障害が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-149">Installing WMF 5.1 over WMF 3.0 will result in the loss of the PSModulePath, which can cause other applications to fail.</span></span> <span data-ttu-id="b3ff3-150">WMF 5.1 をインストールする前に WMF 3.0 をアンインストールするか、PSModulePath を保存して、WMF 5.1 のインストールが完了した後に手動で復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-150">Before installing WMF 5.1, you must either un-install WMF 3.0, or save the PSModulePath and then restore it manually after WMF 5.1 installation is complete.</span></span>
- <span data-ttu-id="b3ff3-151">WMF 5.1には少なくとも [.NET Framework 4.5.2 ](https://www.microsoft.com/en-ca/download/details.aspx?id=42642)が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-151">WMF 5.1 requires at least [.NET Framework 4.5.2](https://www.microsoft.com/en-ca/download/details.aspx?id=42642).</span></span>
<span data-ttu-id="b3ff3-152">Microsoft .NET Framework 4.5.2 をインストールするには、ダウンロード場所で提供されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-152">You can install Microsoft .NET Framework 4.5.2 by following the instructions at the download location.</span></span>

<span data-ttu-id="b3ff3-153">**WinRM の依存関係**</span><span class="sxs-lookup"><span data-stu-id="b3ff3-153">**WinRM Dependency**</span></span>

<span data-ttu-id="b3ff3-154">Windows PowerShell Desired State Configuration (DSC) は、WinRM に依存します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-154">Windows PowerShell Desired State Configuration (DSC) depends on WinRM.</span></span>
<span data-ttu-id="b3ff3-155">WinRM は、Windows Server 2008 R2 および Windows 7 では既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-155">WinRM is not enabled by default on Windows Server 2008 R2 and Windows 7.</span></span>
<span data-ttu-id="b3ff3-156">WinRM を有効にするには、Windows PowerShell 管理者特権セッションで `Set-WSManQuickConfig` を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-156">Run `Set-WSManQuickConfig`, in a Windows PowerShell elevated session, to enable WinRM.</span></span>


## <a name="install-wmf-51-for-windows-server-2012-r2-windows-server-2012-and-windows-81"></a><span data-ttu-id="b3ff3-157">Windows Server 2012 R2、Windows Server 2012、および Windows 8.1 で WMF 5.1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="b3ff3-157">Install WMF 5.1 for Windows Server 2012 R2, Windows Server 2012, and Windows 8.1</span></span>
<span data-ttu-id="b3ff3-158">**Windows エクスプローラー (または Windows Server 2012 R2 または Windows 8.1 ではファイル エクスプローラー) からインストールする**</span><span class="sxs-lookup"><span data-stu-id="b3ff3-158">**Install from Windows Explorer (or File Explorer in Windows Server 2012 R2 or Windows 8.1)**</span></span>

1. <span data-ttu-id="b3ff3-159">MSU ファイルをダウンロードしたフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-159">Navigate to the folder into which you downloaded the MSU file.</span></span>
2. <span data-ttu-id="b3ff3-160">MSU をダブルクリックして実行します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-160">Double-click the MSU to run it.</span></span>

<span data-ttu-id="b3ff3-161">**コマンド プロンプトからインストールする**</span><span class="sxs-lookup"><span data-stu-id="b3ff3-161">**Installing from the Command Prompt**</span></span>

1. <span data-ttu-id="b3ff3-162">コンピューターのアーキテクチャに適切なパッケージをダウンロードした後、管理者特権 (管理者として実行) を使ってコマンド プロンプト ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-162">After downloading the correct package for your computer's architecture, open a Command Prompt window with elevated user rights (Run as Administrator).</span></span> <span data-ttu-id="b3ff3-163">Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 SP1 の Server Core インストール オプションで、既定で管理者特権でコマンド プロンプトが開きます。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-163">On the Server Core installation options of Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1, Command Prompt opens with elevated user rights by default.</span></span>
2. <span data-ttu-id="b3ff3-164">WMF 5.1 のインストール パッケージをダウンロードまたはコピーしたフォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-164">Change directories to the folder into which you have downloaded or copied the WMF 5.1 installation package.</span></span>
3. <span data-ttu-id="b3ff3-165">次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-165">Run one of the following commands:</span></span>
   - <span data-ttu-id="b3ff3-166">Windows Server 2012 R2 または Windows 8.1 x64 を実行しているコンピューターの場合は、`Win8.1AndW2K12R2-KB3191564-x64.msu /quiet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-166">On computers that are running Windows Server 2012 R2 or Windows 8.1 x64, run `Win8.1AndW2K12R2-KB3191564-x64.msu /quiet`.</span></span>
   - <span data-ttu-id="b3ff3-167">Windows Server 2012 を実行しているコンピューターの場合は、`W2K12-KB3191565-x64.msu /quiet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-167">On computers that are running Windows Server 2012, run `W2K12-KB3191565-x64.msu /quiet`.</span></span>
   - <span data-ttu-id="b3ff3-168">Windows 8.1 x86 を実行しているコンピューターの場合は、`Win8.1-KB3191564-x86.msu /quiet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-168">On computers that are running Windows 8.1 x86, run `Win8.1-KB3191564-x86.msu /quiet`.</span></span>

> [!NOTE]
> <span data-ttu-id="b3ff3-169">WMF 5.1 をインストールするには、再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-169">Installing WMF 5.1 requires a reboot.</span></span> <span data-ttu-id="b3ff3-170">`/quiet` オプションを使用すると、警告なしでシステムが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-170">Using the `/quiet` option will reboot the system without warning.</span></span>
> <span data-ttu-id="b3ff3-171">再起動しないようにするには、`/norestart` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-171">Use the `/norestart` option to avoid rebooting.</span></span> <span data-ttu-id="b3ff3-172">ただし、再起動が完了するまで、WMF 5.1 はインストールされません。</span><span class="sxs-lookup"><span data-stu-id="b3ff3-172">However, WMF 5.1 will not be installed until you have rebooted.</span></span>
