---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
contributor: keithb
title: WMF 5.1 のインストールと構成
ms.openlocfilehash: 241f52be011e1afc87d25c9a934db0c1e0361b76
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147692"
---
# <a name="install-and-configure-wmf-51"></a><span data-ttu-id="5821d-103">WMF 5.1 のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="5821d-103">Install and Configure WMF 5.1</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5821d-104">WMF 5.0 は、WMF 5.1 に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="5821d-104">WMF 5.0 is superseded by WMF 5.1.</span></span> <span data-ttu-id="5821d-105">WMF 5.0 を所有するユーザーがサポートを受けるには、WMF 5.1 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5821d-105">Users with WMF 5.0 must upgrade to WMF 5.1 to receive support.</span></span>
> <span data-ttu-id="5821d-106">**WMF 5.1 には .NET Framework 4.5.2** (またはそれ以上) が必要です。</span><span class="sxs-lookup"><span data-stu-id="5821d-106">**WMF 5.1 requires the .NET Framework 4.5.2** (or above).</span></span> <span data-ttu-id="5821d-107">.NET 4.5.2 (またはそれ以上) がインストールされていない場合、インストールは成功しますが、主な機能は失敗します。</span><span class="sxs-lookup"><span data-stu-id="5821d-107">Installation will succeed, but key features will fail if .NET 4.5.2 (or above) is not installed.</span></span>

## <a name="download-and-install-the-wmf-51-package"></a><span data-ttu-id="5821d-108">WMF 5.1 パッケージのダウンロードとインストール</span><span class="sxs-lookup"><span data-stu-id="5821d-108">Download and install the WMF 5.1 package</span></span>

<span data-ttu-id="5821d-109">インストールするオペレーティング システムとアーキテクチャに合わせて WMF 5.1 パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5821d-109">Download the WMF 5.1 package for the operating system and architecture you wish to install it on:</span></span>

| <span data-ttu-id="5821d-110">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="5821d-110">Operating System</span></span>       | <span data-ttu-id="5821d-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="5821d-111">Prerequisites</span></span>           | <span data-ttu-id="5821d-112">パッケージ リンク</span><span class="sxs-lookup"><span data-stu-id="5821d-112">Package Links</span></span>                          |
|------------------------|-------------------------|----------------------------------------|
| <span data-ttu-id="5821d-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5821d-113">Windows Server 2012 R2</span></span> |                         | <span data-ttu-id="5821d-114">[Win8.1AndW2K12R2-KB3191564-x64.msu][]</span><span class="sxs-lookup"><span data-stu-id="5821d-114">[Win8.1AndW2K12R2-KB3191564-x64.msu][]</span></span> |
| <span data-ttu-id="5821d-115">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="5821d-115">Windows Server 2012</span></span>    |                         | <span data-ttu-id="5821d-116">[W2K12-KB3191565-x64.msu][]</span><span class="sxs-lookup"><span data-stu-id="5821d-116">[W2K12-KB3191565-x64.msu][]</span></span>            |
| <span data-ttu-id="5821d-117">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5821d-117">Windows Server 2008 R2</span></span> | <span data-ttu-id="5821d-118">[.NET Framework 4.5.2][]</span><span class="sxs-lookup"><span data-stu-id="5821d-118">[.NET Framework 4.5.2][]</span></span>| <span data-ttu-id="5821d-119">[Win7AndW2K8R2-KB3191566-x64.ZIP][]</span><span class="sxs-lookup"><span data-stu-id="5821d-119">[Win7AndW2K8R2-KB3191566-x64.ZIP][]</span></span>    |
| <span data-ttu-id="5821d-120">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5821d-120">Windows 8.1</span></span>            |                         | <span data-ttu-id="5821d-121">**x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu][]</span><span class="sxs-lookup"><span data-stu-id="5821d-121">**x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu][]</span></span></br><span data-ttu-id="5821d-122">**x86:** [Win8.1-KB3191564-x86.msu][]</span><span class="sxs-lookup"><span data-stu-id="5821d-122">**x86:** [Win8.1-KB3191564-x86.msu][]</span></span> |
| <span data-ttu-id="5821d-123">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="5821d-123">Windows 7 SP1</span></span>          | <span data-ttu-id="5821d-124">[.NET Framework 4.5.2][]</span><span class="sxs-lookup"><span data-stu-id="5821d-124">[.NET Framework 4.5.2][]</span></span>| <span data-ttu-id="5821d-125">**x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP][]</span><span class="sxs-lookup"><span data-stu-id="5821d-125">**x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP][]</span></span></br><span data-ttu-id="5821d-126">**x86:** [Win7-KB3191566-x86.ZIP][]</span><span class="sxs-lookup"><span data-stu-id="5821d-126">**x86:** [Win7-KB3191566-x86.ZIP][]</span></span> |

[.NET Framework 4.5.2]: https://www.microsoft.com/download/details.aspx?id=42642
[W2K12-KB3191565-x64.msu]: https://go.microsoft.com/fwlink/?linkid=839513
[Win7-KB3191566-x86.ZIP]: https://go.microsoft.com/fwlink/?linkid=839522
[Win7AndW2K8R2-KB3191566-x64.ZIP]: https://go.microsoft.com/fwlink/?linkid=839523
[Win8.1-KB3191564-x86.msu]: https://go.microsoft.com/fwlink/?linkid=839521
[Win8.1AndW2K12R2-KB3191564-x64.msu]: https://go.microsoft.com/fwlink/?linkid=839516

- <span data-ttu-id="5821d-133">WMF 5.1 RTM をインストールする前に、WMF 5.1 プレビューをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5821d-133">WMF 5.1 Preview must be uninstalled before installing WMF 5.1 RTM.</span></span>
- <span data-ttu-id="5821d-134">WMF 5.1 は、WMF 5.0 または WMF 4.0 の上に直接インストールできます。</span><span class="sxs-lookup"><span data-stu-id="5821d-134">WMF 5.1 may be installed directly over WMF 5.0 or WMF 4.0.</span></span>
- <span data-ttu-id="5821d-135">Windows 7 および Windows Server 2008 R2 の上に WMF 5.1 をインストールする前に、WMF 4.0 をインストールする**必要はありません**。</span><span class="sxs-lookup"><span data-stu-id="5821d-135">It is **not required** to install WMF 4.0 prior to installing WMF 5.1 on Windows 7 and Windows Server 2008 R2.</span></span>

## <a name="install-wmf-51-for-windows-server-2008-r2-and-windows-7"></a><span data-ttu-id="5821d-136">Windows Server 2008 R2 および Windows 7 で WMF 5.1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="5821d-136">Install WMF 5.1 for Windows Server 2008 R2 and Windows 7</span></span>

> [!NOTE]
> <span data-ttu-id="5821d-137">Windows Server 2008 R2 および Windows 7 でのインストール手順は変更されているため、他のパッケージの手順と異なります。</span><span class="sxs-lookup"><span data-stu-id="5821d-137">Installation instructions for Windows Server 2008 R2 and Windows 7 have changed, and differ from the instructions for the other packages.</span></span> <span data-ttu-id="5821d-138">Windows Server 2012 R2、Windows Server 2012、および Windows 8.1 のインストール手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5821d-138">Installation instructions for Windows Server 2012 R2, Windows Server 2012, and Windows 8.1 are below.</span></span>

### <a name="wmf-51-prerequisites-for-windows-server-2008-r2-sp1-and-windows-7-sp1"></a><span data-ttu-id="5821d-139">Windows Server 2008 R2 SP1 および Windows 7 SP1 での WMF 5.1 の前提条件</span><span class="sxs-lookup"><span data-stu-id="5821d-139">WMF 5.1 Prerequisites for Windows Server 2008 R2 SP1 and Windows 7 SP1</span></span>

<span data-ttu-id="5821d-140">Windows Server 2008 R2 SP1 または Windows 7 SP1 に WMF 5.1 をインストールするには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5821d-140">Installation of WMF 5.1 on either Windows Server 2008 R2 SP1 or Windows 7 SP1, requires the following:</span></span>

- <span data-ttu-id="5821d-141">最新の Service Pack をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5821d-141">Latest service pack must be installed.</span></span>
- <span data-ttu-id="5821d-142">WMF 3.0 をインストール**しないでください**。</span><span class="sxs-lookup"><span data-stu-id="5821d-142">WMF 3.0 **must not** be installed.</span></span> <span data-ttu-id="5821d-143">WMF 3.0 経由で WMF 5.1 をインストールすると、**PSModulePath** (`$env:PSModulePath`) が失われ、これによって他のアプリケーションで障害が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5821d-143">Installing WMF 5.1 over WMF 3.0 will result in the loss of the **PSModulePath** (`$env:PSModulePath`), which can cause other applications to fail.</span></span> <span data-ttu-id="5821d-144">WMF 5.1 をインストールする前に WMF 3.0 をアンインストールするか、**PSModulePath** を保存して、WMF 5.1 のインストールが完了した後に手動で復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5821d-144">Before installing WMF 5.1, you must either un-install WMF 3.0, or save the **PSModulePath** and then restore it manually after WMF 5.1 installation is complete.</span></span>
- <span data-ttu-id="5821d-145">WMF 5.1には少なくとも [.NET Framework 4.5.2 ](https://www.microsoft.com/download/details.aspx?id=42642)が必要です。</span><span class="sxs-lookup"><span data-stu-id="5821d-145">WMF 5.1 requires at least [.NET Framework 4.5.2](https://www.microsoft.com/download/details.aspx?id=42642).</span></span>
  <span data-ttu-id="5821d-146">Microsoft .NET Framework 4.5.2 をインストールするには、ダウンロード場所で提供されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="5821d-146">You can install Microsoft .NET Framework 4.5.2 by following the instructions at the download location.</span></span>

### <a name="installing-wmf-51-on-windows-server-2008-r2-and-windows-7"></a><span data-ttu-id="5821d-147">Windows Server 2008 R2 および Windows 7 で WMF 5.1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="5821d-147">Installing WMF 5.1 on Windows Server 2008 R2 and Windows 7</span></span>

1. <span data-ttu-id="5821d-148">ZIP ファイルをダウンロードしたフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5821d-148">Navigate to the folder into which you downloaded the ZIP file.</span></span>

2. <span data-ttu-id="5821d-149">ZIP ファイルを右クリックし、 **[すべて展開...]** を選択します。ZIP ファイルには、2 つのファイルが含まれています (MSU と `Install-WMF5.1.ps1` スクリプト ファイル)。</span><span class="sxs-lookup"><span data-stu-id="5821d-149">Right-click on the ZIP file, and select **Extract All...**. The ZIP file contains two files: an MSU and the `Install-WMF5.1.ps1` script file.</span></span> <span data-ttu-id="5821d-150">ZIP ファイルを展開したら、Windows 7 または Windows Server 2008 R2 を実行する任意のコンピューターにコンテンツをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="5821d-150">Once you have unpacked the ZIP file, you can copy the contents to any machine running Windows 7 or Windows Server 2008 R2.</span></span>

3. <span data-ttu-id="5821d-151">ZIP ファイルを展開した後、PowerShell を管理者として開き、その ZIP ファイルの内容を含むフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5821d-151">After extracting the ZIP file contents, open PowerShell as administrator, then navigate to the folder containing the contents of the ZIP file.</span></span>

4. <span data-ttu-id="5821d-152">そのフォルダーの `Install-WMF5.1.ps1` スクリプトを実行して、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="5821d-152">Run the `Install-WMF5.1.ps1` script in that folder, and follow the instructions.</span></span> <span data-ttu-id="5821d-153">このスクリプトはローカル コンピューターの前提条件を確認し、前提条件を満たしている場合に WMF 5.1 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5821d-153">This script will check the prerequisites on the local machine, and install WMF 5.1 if the prerequisites have been met.</span></span> <span data-ttu-id="5821d-154">前提条件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5821d-154">The prerequisites are listed below.</span></span>

   <span data-ttu-id="5821d-155">`Install-WMF5.1.ps1` では、Windows Server 2008 R2 および Windows 7 でのインストールの自動化を容易にするため、次のパラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5821d-155">`Install-WMF5.1.ps1` takes the following parameters to ease automating the installation on Windows Server 2008 R2 and Windows 7:</span></span>

   - <span data-ttu-id="5821d-156">**AcceptEula**:このパラメーターが含まれる場合、使用許諾契約書は自動的に受け入れられ、表示はされません。</span><span class="sxs-lookup"><span data-stu-id="5821d-156">**AcceptEula**: When this parameter is included, the EULA is automatically accepted and will not be displayed.</span></span>
   - <span data-ttu-id="5821d-157">**AllowRestart**:このパラメーターは、AcceptEula が指定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5821d-157">**AllowRestart**: This parameter can only be used if AcceptEula is specified.</span></span> <span data-ttu-id="5821d-158">このパラメーターが含まれていて、WMF 5.1 のインストール後に再起動が必要な場合は、インストールが完了した後すぐに、メッセージが表示されることなく再起動が実行されます。</span><span class="sxs-lookup"><span data-stu-id="5821d-158">If this parameter is included, and a restart is required after installing WMF 5.1, the restart will happen without prompting immediately after the installation is completed.</span></span>

## <a name="winrm-dependency"></a><span data-ttu-id="5821d-159">WinRM の依存関係</span><span class="sxs-lookup"><span data-stu-id="5821d-159">WinRM Dependency</span></span>

<span data-ttu-id="5821d-160">Windows PowerShell Desired State Configuration (DSC) は、WinRM に依存します。</span><span class="sxs-lookup"><span data-stu-id="5821d-160">Windows PowerShell Desired State Configuration (DSC) depends on WinRM.</span></span> <span data-ttu-id="5821d-161">WinRM は、Windows Server 2008 R2 および Windows 7 では既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5821d-161">WinRM is not enabled by default on Windows Server 2008 R2 and Windows 7.</span></span> <span data-ttu-id="5821d-162">WinRM を有効にするには、Windows PowerShell 管理者特権セッションで `Set-WSManQuickConfig` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5821d-162">Run `Set-WSManQuickConfig`, in a Windows PowerShell elevated session, to enable WinRM.</span></span>

## <a name="install-wmf-51-for-windows-server-2012-r2-windows-server-2012-and-windows-81"></a><span data-ttu-id="5821d-163">Windows Server 2012 R2、Windows Server 2012、および Windows 8.1 で WMF 5.1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="5821d-163">Install WMF 5.1 for Windows Server 2012 R2, Windows Server 2012, and Windows 8.1</span></span>

### <a name="install-from-windows-file-explorer"></a><span data-ttu-id="5821d-164">エクスプローラーからインストールする</span><span class="sxs-lookup"><span data-stu-id="5821d-164">Install from Windows File Explorer</span></span>

1. <span data-ttu-id="5821d-165">MSU ファイルをダウンロードしたフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5821d-165">Navigate to the folder into which you downloaded the MSU file.</span></span>
2. <span data-ttu-id="5821d-166">MSU をダブルクリックして実行します。</span><span class="sxs-lookup"><span data-stu-id="5821d-166">Double-click the MSU to run it.</span></span>

### <a name="installing-from-the-command-prompt"></a><span data-ttu-id="5821d-167">コマンド プロンプトからインストールする</span><span class="sxs-lookup"><span data-stu-id="5821d-167">Installing from the Command Prompt</span></span>

1. <span data-ttu-id="5821d-168">コンピューターのアーキテクチャに適切なパッケージをダウンロードした後、管理者特権 (管理者として実行) を使ってコマンド プロンプト ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="5821d-168">After downloading the correct package for your computer's architecture, open a Command Prompt window with elevated user rights (Run as Administrator).</span></span> <span data-ttu-id="5821d-169">Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 SP1 の Server Core インストール オプションで、既定で管理者特権でコマンド プロンプトが開きます。</span><span class="sxs-lookup"><span data-stu-id="5821d-169">On the Server Core installation options of Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1, Command Prompt opens with elevated user rights by default.</span></span>
2. <span data-ttu-id="5821d-170">WMF 5.1 のインストール パッケージをダウンロードまたはコピーしたフォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="5821d-170">Change directories to the folder into which you have downloaded or copied the WMF 5.1 installation package.</span></span>
3. <span data-ttu-id="5821d-171">次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5821d-171">Run one of the following commands:</span></span>
   - <span data-ttu-id="5821d-172">Windows Server 2012 R2 または Windows 8.1 x64 を実行しているコンピューターの場合は、`Win8.1AndW2K12R2-KB3191564-x64.msu /quiet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5821d-172">On computers that are running Windows Server 2012 R2 or Windows 8.1 x64, run `Win8.1AndW2K12R2-KB3191564-x64.msu /quiet`.</span></span>
   - <span data-ttu-id="5821d-173">Windows Server 2012 を実行しているコンピューターの場合は、`W2K12-KB3191565-x64.msu /quiet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5821d-173">On computers that are running Windows Server 2012, run `W2K12-KB3191565-x64.msu /quiet`.</span></span>
   - <span data-ttu-id="5821d-174">Windows 8.1 x86 を実行しているコンピューターの場合は、`Win8.1-KB3191564-x86.msu /quiet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="5821d-174">On computers that are running Windows 8.1 x86, run `Win8.1-KB3191564-x86.msu /quiet`.</span></span>

> [!NOTE]
> <span data-ttu-id="5821d-175">WMF 5.1 をインストールするには、再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="5821d-175">Installing WMF 5.1 requires a reboot.</span></span> <span data-ttu-id="5821d-176">`/quiet` オプションを使用すると、警告なしでシステムが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="5821d-176">Using the `/quiet` option will reboot the system without warning.</span></span> <span data-ttu-id="5821d-177">再起動しないようにするには、`/norestart` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5821d-177">Use the `/norestart` option to avoid rebooting.</span></span> <span data-ttu-id="5821d-178">ただし、再起動が完了するまで、WMF 5.1 はインストールされません。</span><span class="sxs-lookup"><span data-stu-id="5821d-178">However, WMF 5.1 will not be installed until you have rebooted.</span></span>
