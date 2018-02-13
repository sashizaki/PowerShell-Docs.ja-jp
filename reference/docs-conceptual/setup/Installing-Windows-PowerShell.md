---
ms.date: 2017-08-09
keywords: "powershell, コマンドレット, ダウンロード, インストール, セットアップ, windows 10, windows 8.1, windows 8.0, windows 7"
title: "Windows PowerShell のインストール"
ms.openlocfilehash: ec8f09087a5c5f2e7ea6237faa01ea3f447ad1f3
ms.sourcegitcommit: 755d7bc0740573d73613cedcf79981ca3dc81c5e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2018
---
# <a name="installing-windows-powershell"></a><span data-ttu-id="1353e-103">Windows PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="1353e-103">Installing Windows PowerShell</span></span>

<span data-ttu-id="1353e-104">既定では、PowerShell は、Windows 7 SP1 および Windows Server 2008 R2 SP1 以降のすべての Windows にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="1353e-104">PowerShell comes installed by default in every Windows, starting with Windows 7 SP1 and Windows Server 2008 R2 SP1.</span></span>

<span data-ttu-id="1353e-105">**PowerShell 6** (ベータ) をインストールする Linux、macOS、および Windows のユーザーは、自分のマシンで次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1353e-105">Linux, macOS, and Windows users that would like to install **PowerShell 6** (beta), in their machines, need to:</span></span>

1. <span data-ttu-id="1353e-106">[GitHub](https://github.com/powershell/powershell#get-powershell) から特定の OS とバージョン用の PowerShell を取得します</span><span class="sxs-lookup"><span data-stu-id="1353e-106">Get PowerShell for the specific OS and version, from [GitHub](https://github.com/powershell/powershell#get-powershell)</span></span>
1. <span data-ttu-id="1353e-107">インストール手順に従って操作します</span><span class="sxs-lookup"><span data-stu-id="1353e-107">Follow the installation instructions</span></span>
  - [<span data-ttu-id="1353e-108">Linux</span><span class="sxs-lookup"><span data-stu-id="1353e-108">Linux</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
  - [<span data-ttu-id="1353e-109">macOS</span><span class="sxs-lookup"><span data-stu-id="1353e-109">macOS</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/macos.md)
  - [<span data-ttu-id="1353e-110">Windows</span><span class="sxs-lookup"><span data-stu-id="1353e-110">Windows</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/windows.md#msi)

<span data-ttu-id="1353e-111">PowerShell 6 は、Docker でも利用できます。[Docker のインストール](https://github.com/PowerShell/PowerShell/tree/master/docker)手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1353e-111">PowerShell 6 is also available for Docker; see [Docker installation](https://github.com/PowerShell/PowerShell/tree/master/docker) instructions.</span></span>

## <a name="finding-powershell-in-windows-10-81-80-and-7"></a><span data-ttu-id="1353e-112">Windows 10、8.1、8.0、7 で PowerShell を見つける</span><span class="sxs-lookup"><span data-stu-id="1353e-112">Finding PowerShell in Windows 10, 8.1, 8.0, and 7</span></span>

<span data-ttu-id="1353e-113">Windows で PowerShell コンソールや ISE (Integrated Scripting Environment) を見つけるのは、その場所が Windows のあるバージョンから次のバージョンへ移動するため、難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="1353e-113">Sometimes locating PowerShell console or ISE (Integrated Scripting Environment) in Windows can be difficult, as it's location moves from one version of Windows to the next.</span></span>

<span data-ttu-id="1353e-114">次の表は、使用している Windows のバージョンで PowerShell を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1353e-114">The following tables should help you find PowerShell in your Windows version.</span></span>
<span data-ttu-id="1353e-115">ここに一覧されているバージョンはすべて、リリース時の元のバージョンです。更新プログラムは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="1353e-115">All versions listed here are the original version, as released, with no updates.</span></span>

### <a name="for-console"></a><span data-ttu-id="1353e-116">コンソールの場合</span><span class="sxs-lookup"><span data-stu-id="1353e-116">For Console</span></span>

<span data-ttu-id="1353e-117">バージョン</span><span class="sxs-lookup"><span data-stu-id="1353e-117">Version</span></span> | <span data-ttu-id="1353e-118">インストール先</span><span class="sxs-lookup"><span data-stu-id="1353e-118">Location</span></span>
-- | --
<span data-ttu-id="1353e-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1353e-119">Windows 10</span></span> | <span data-ttu-id="1353e-120">左下隅にある Windows アイコンをクリックして、「PowerShell」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="1353e-120">Click left lower corner Windows icon, start typing PowerShell</span></span>
<span data-ttu-id="1353e-121">Windows 8.1、8.0</span><span class="sxs-lookup"><span data-stu-id="1353e-121">Windows 8.1, 8.0</span></span> | <span data-ttu-id="1353e-122">スタート画面で、「PowerShell」と入力し始めます。</span><span class="sxs-lookup"><span data-stu-id="1353e-122">On the start screen, start typing PowerShell.</span></span><br/><span data-ttu-id="1353e-123">デスクトップ上の場合は、左下隅にある Windows アイコンをクリックして、「PowerShell」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="1353e-123">If on desktop, click left lower corner Windows icon, start typing PowerShell</span></span>
<span data-ttu-id="1353e-124">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="1353e-124">Windows 7 SP1</span></span> | <span data-ttu-id="1353e-125">左下隅にある Windows アイコンをクリックして、検索ボックスに「PowerShell」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="1353e-125">Click left lower corner Windows icon, on the search box start typing PowerShell</span></span>

### <a name="for-ise"></a><span data-ttu-id="1353e-126">ISE の場合</span><span class="sxs-lookup"><span data-stu-id="1353e-126">For ISE</span></span>

<span data-ttu-id="1353e-127">バージョン</span><span class="sxs-lookup"><span data-stu-id="1353e-127">Version</span></span> | <span data-ttu-id="1353e-128">インストール先</span><span class="sxs-lookup"><span data-stu-id="1353e-128">Location</span></span>
-- | --
<span data-ttu-id="1353e-129">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1353e-129">Windows 10</span></span> | <span data-ttu-id="1353e-130">左下隅にある Windows アイコンをクリックして、「ISE」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="1353e-130">Click left lower corner Windows icon, start typing ISE</span></span>
<span data-ttu-id="1353e-131">Windows 8.1、8.0</span><span class="sxs-lookup"><span data-stu-id="1353e-131">Windows 8.1, 8.0</span></span> | <span data-ttu-id="1353e-132">スタート画面で、「**PowerShell ISE**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1353e-132">On the start screen, type **PowerShell ISE**.</span></span><br/><span data-ttu-id="1353e-133">デスクトップで、左下隅にある Windows アイコンをクリックして、「**PowerShell ISE**」と入力します</span><span class="sxs-lookup"><span data-stu-id="1353e-133">If on desktop, click left lower corner Windows icon, type **PowerShell ISE**</span></span>
<span data-ttu-id="1353e-134">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="1353e-134">Windows 7 SP1</span></span> | <span data-ttu-id="1353e-135">左下隅にある Windows アイコンをクリックして、検索ボックスに「PowerShell」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="1353e-135">Click left lower corner Windows icon, on the search box start typing PowerShell</span></span>

## <a name="finding-powershell-in-windows-server-versions"></a><span data-ttu-id="1353e-136">Windows Server バージョンで PowerShell を見つける</span><span class="sxs-lookup"><span data-stu-id="1353e-136">Finding PowerShell in Windows Server versions</span></span>

<span data-ttu-id="1353e-137">Windows Server 2008 R2 以降では、グラフィカル ユーザー インターフェイス (GUI) を含めずに、Windows オペレーティング システムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1353e-137">Starting with Windows Server 2008 R2, Windows operating system can be installed without the graphical user interface (GUI).</span></span>
<span data-ttu-id="1353e-138">GUI なしの Windows Server のエディションは **Core** エディションという名前で、GUI ありのエディションは **Desktop** という名前です。</span><span class="sxs-lookup"><span data-stu-id="1353e-138">Editions of Windows Server without GUI are named **Core** editions, and editions with the GUI are named **Desktop**.</span></span>

### <a name="windows-server-core-editions"></a><span data-ttu-id="1353e-139">Windows Server Core エディション</span><span class="sxs-lookup"><span data-stu-id="1353e-139">Windows Server Core editions</span></span>

<span data-ttu-id="1353e-140">すべての Core エディションで、サーバーにログインすると、Windows コマンド プロンプト ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1353e-140">In all Core editions, when you log to the server you get a Windows command prompt window.</span></span>

<span data-ttu-id="1353e-141">「`powershell`」と入力して **Enter** キーを押し、コマンド プロンプト セッション内で PowerShell を開始します。</span><span class="sxs-lookup"><span data-stu-id="1353e-141">Type `powershell` and press **ENTER** to start PowerShell inside the command prompt session.</span></span> <span data-ttu-id="1353e-142">「`exit`」と入力して PowerShell セッションを終了し、コマンド プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="1353e-142">Type `exit` to terminate the PowerShell session and return to command prompt.</span></span>

### <a name="windows-server-desktop-editions"></a><span data-ttu-id="1353e-143">Windows Server Desktop エディション</span><span class="sxs-lookup"><span data-stu-id="1353e-143">Windows Server Desktop editions</span></span>

<span data-ttu-id="1353e-144">すべての Desktop エディションで、左下隅にある Windows アイコンをクリックして、「PowerShell」と入力し始めます。</span><span class="sxs-lookup"><span data-stu-id="1353e-144">In all desktop editions, click the left lower corner Windows icon, start typing PowerShell.</span></span>
<span data-ttu-id="1353e-145">コンソールと ISE のオプションが両方表示されます。</span><span class="sxs-lookup"><span data-stu-id="1353e-145">You get both console and ISE options.</span></span>

<span data-ttu-id="1353e-146">上記のルールの例外は、Windows Server 2008 R2 SP1 の ISE のみです。この場合は、左下隅にある Windows アイコンをクリックして、「PowerShell ISE」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1353e-146">The only exception to the above rule is the ISE in Windows Server 2008 R2 SP1; in this case, click the left lower corner Windows icon, type PowerShell ISE.</span></span>

## <a name="how-to-check-the-version-of-powershell"></a><span data-ttu-id="1353e-147">PowerShell のバージョンを確認する方法</span><span class="sxs-lookup"><span data-stu-id="1353e-147">How to check the version of PowerShell</span></span>

<span data-ttu-id="1353e-148">インストールした PowerShell のバージョンを確認するには、PowerShell コンソール (または ISE) を起動し、「`$PSVersionTable`」と入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1353e-148">To find which version of PowerShell you have installed, start a PowerShell console (or the ISE) and type `$PSVersionTable` and press **ENTER**.</span></span>

## <a name="upgrading-existing-windows-powershell"></a><span data-ttu-id="1353e-149">既存の Windows PowerShell をアップグレードする</span><span class="sxs-lookup"><span data-stu-id="1353e-149">Upgrading existing Windows PowerShell</span></span>

<span data-ttu-id="1353e-150">PowerShell のインストール パッケージは、WMF インストーラー内に含まれています。</span><span class="sxs-lookup"><span data-stu-id="1353e-150">The installation package for PowerShell comes inside a WMF installer.</span></span>
<span data-ttu-id="1353e-151">WMF インストーラーのバージョンは、PowerShell のバージョンに一致します。Windows PowerShell に、スタンドアロンのインストーラーはありません。</span><span class="sxs-lookup"><span data-stu-id="1353e-151">The version of the WMF installer matches the version of PowerShell; there's no stand alone installer for Windows PowerShell.</span></span>

<span data-ttu-id="1353e-152">PowerShell の既存のバージョンを更新する場合、Windows では、以下の表を使って、更新する PowerShell のバージョン用のインストーラーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="1353e-152">If you need to update your existing version of PowerShell, in Windows, use the following table to locate the installer for the version of PowerShell you want to update to.</span></span>

<span data-ttu-id="1353e-153">Windows</span><span class="sxs-lookup"><span data-stu-id="1353e-153">Windows</span></span> | <span data-ttu-id="1353e-154">PS 3.0</span><span class="sxs-lookup"><span data-stu-id="1353e-154">PS 3.0</span></span> | <span data-ttu-id="1353e-155">PS 4.0</span><span class="sxs-lookup"><span data-stu-id="1353e-155">PS 4.0</span></span> | <span data-ttu-id="1353e-156">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="1353e-156">PS 5.0</span></span> | <span data-ttu-id="1353e-157">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="1353e-157">PS 5.1</span></span> |
--|--|--|--|--|
<span data-ttu-id="1353e-158">Windows 10 (注 1 を参照してください)</span><span class="sxs-lookup"><span data-stu-id="1353e-158">Windows 10 (see Note1)</span></span><br/><span data-ttu-id="1353e-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1353e-159">Windows Server 2016</span></span> | - | - | - | <span data-ttu-id="1353e-160">インストール済み</span><span class="sxs-lookup"><span data-stu-id="1353e-160">installed</span></span>
<span data-ttu-id="1353e-161">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1353e-161">Windows 8.1</span></span><br/><span data-ttu-id="1353e-162">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1353e-162">Windows Server 2012 R2</span></span> | - | <span data-ttu-id="1353e-163">インストール済み</span><span class="sxs-lookup"><span data-stu-id="1353e-163">installed</span></span> | [<span data-ttu-id="1353e-164">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="1353e-164">WMF 5.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [<span data-ttu-id="1353e-165">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="1353e-165">WMF 5.1</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
<span data-ttu-id="1353e-166">Windows 8</span><span class="sxs-lookup"><span data-stu-id="1353e-166">Windows 8</span></span><br/><span data-ttu-id="1353e-167">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1353e-167">Windows Server 2012</span></span> | <span data-ttu-id="1353e-168">インストール済み</span><span class="sxs-lookup"><span data-stu-id="1353e-168">installed</span></span> | [<span data-ttu-id="1353e-169">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="1353e-169">WMF 4.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [<span data-ttu-id="1353e-170">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="1353e-170">WMF 5.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [<span data-ttu-id="1353e-171">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="1353e-171">WMF 5.1</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
<span data-ttu-id="1353e-172">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="1353e-172">Windows 7 SP1</span></span><br/><span data-ttu-id="1353e-173">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="1353e-173">Windows Server 2008 R2 SP1</span></span> | [<span data-ttu-id="1353e-174">WMF 3.0</span><span class="sxs-lookup"><span data-stu-id="1353e-174">WMF 3.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=34595) | [<span data-ttu-id="1353e-175">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="1353e-175">WMF 4.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [<span data-ttu-id="1353e-176">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="1353e-176">WMF 5.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [<span data-ttu-id="1353e-177">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="1353e-177">WMF 5.1</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)

> <span data-ttu-id="1353e-178">**注 1**:</span><span class="sxs-lookup"><span data-stu-id="1353e-178">**Note 1**:</span></span>
  >>
  >> <span data-ttu-id="1353e-179">自動更新を有効にしている Windows 10 の最初のリリースでは、PowerShell はバージョン 5.0 から 5.1 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="1353e-179">On the initial release of Windows 10, with automatic updates enabled, PowerShell gets updated from version 5.0 to 5.1.</span></span>
  >>
  >> <span data-ttu-id="1353e-180">元のバージョンの Windows 10 が Windows Update によって更新されない場合、PowerShell のバージョンは 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="1353e-180">If the original version of Windows 10 is not updated through Windows Updates, the version of PowerShell is 5.0.</span></span>

## <a name="need-azure-powershell"></a><span data-ttu-id="1353e-181">Azure PowerShell が必要な場合</span><span class="sxs-lookup"><span data-stu-id="1353e-181">Need Azure PowerShell</span></span>

<span data-ttu-id="1353e-182">**Azure PowerShell** を探している場合は、「[Overview of Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure)」 (Azure PowerShell の概要) から開始することができます。</span><span class="sxs-lookup"><span data-stu-id="1353e-182">If you're looking for **Azure PowerShell**, you could start with [Overview of Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure).</span></span>

<span data-ttu-id="1353e-183">その他にも、[Azure PowerShell のインストールと構成](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps)が必要な場合があります</span><span class="sxs-lookup"><span data-stu-id="1353e-183">Otherwise, what you might need is [Install and configure Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps)</span></span>

## <a name="see-also"></a><span data-ttu-id="1353e-184">参照</span><span class="sxs-lookup"><span data-stu-id="1353e-184">See Also</span></span>

- [<span data-ttu-id="1353e-185">Windows PowerShell のシステム要件</span><span class="sxs-lookup"><span data-stu-id="1353e-185">Windows PowerShell System Requirements</span></span>](Windows-PowerShell-System-Requirements.md)
- [<span data-ttu-id="1353e-186">Windows PowerShell の開始</span><span class="sxs-lookup"><span data-stu-id="1353e-186">Starting Windows PowerShell</span></span>](Starting-Windows-PowerShell.md)
