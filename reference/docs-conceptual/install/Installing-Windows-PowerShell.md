---
ms.date: 08/09/2017
keywords: powershell, コマンドレット, ダウンロード, インストール, セットアップ, windows 10, windows 8.1, windows 8.0, windows 7
title: Windows PowerShell のインストール
ms.openlocfilehash: 1630ba445c88953b2729232ae7d80afa326f25e6
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402550"
---
# <a name="installing-windows-powershell"></a><span data-ttu-id="bd0ac-103">Windows PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="bd0ac-103">Installing Windows PowerShell</span></span>

<span data-ttu-id="bd0ac-104">既定では、Windows PowerShell は、Windows 7 SP1 および Windows Server 2008 R2 SP1 以降のすべての Windows にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-104">Windows PowerShell comes installed by default in every Windows, starting with Windows 7 SP1 and Windows Server 2008 R2 SP1.</span></span>

<span data-ttu-id="bd0ac-105">PowerShell 6 以降を使う場合は、Windows PowerShell ではなく PowerShell Core をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-105">If you are interested in PowerShell 6 and later, you need to install PowerShell Core instead of Windows PowerShell.</span></span> <span data-ttu-id="bd0ac-106">詳細については、「[Windows への PowerShell Core のインストール](Installing-PowerShell-Core-on-Windows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-106">For that, see [Installing PowerShell Core on Windows](Installing-PowerShell-Core-on-Windows.md).</span></span>

## <a name="finding-powershell-in-windows-10-81-80-and-7"></a><span data-ttu-id="bd0ac-107">Windows 10、8.1、8.0、7 で PowerShell を見つける</span><span class="sxs-lookup"><span data-stu-id="bd0ac-107">Finding PowerShell in Windows 10, 8.1, 8.0, and 7</span></span>

<span data-ttu-id="bd0ac-108">Windows で PowerShell コンソールや ISE (Integrated Scripting Environment) を見つけるのは、その場所が Windows のあるバージョンから次のバージョンへ移動するため、難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-108">Sometimes locating PowerShell console or ISE (Integrated Scripting Environment) in Windows can be difficult, as it's location moves from one version of Windows to the next.</span></span>

<span data-ttu-id="bd0ac-109">次の表は、使用している Windows のバージョンで PowerShell を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-109">The following tables should help you find PowerShell in your Windows version.</span></span>
<span data-ttu-id="bd0ac-110">ここに一覧されているバージョンはすべて、リリース時の元のバージョンです。更新プログラムは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-110">All versions listed here are the original version, as released, with no updates.</span></span>

### <a name="for-console"></a><span data-ttu-id="bd0ac-111">コンソールの場合</span><span class="sxs-lookup"><span data-stu-id="bd0ac-111">For Console</span></span>

<span data-ttu-id="bd0ac-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="bd0ac-112">Version</span></span> | <span data-ttu-id="bd0ac-113">インストール先</span><span class="sxs-lookup"><span data-stu-id="bd0ac-113">Location</span></span>
-- | --
<span data-ttu-id="bd0ac-114">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bd0ac-114">Windows 10</span></span> | <span data-ttu-id="bd0ac-115">左下隅にある Windows アイコンをクリックして、「PowerShell」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="bd0ac-115">Click left lower corner Windows icon, start typing PowerShell</span></span>
<span data-ttu-id="bd0ac-116">Windows 8.1、8.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-116">Windows 8.1, 8.0</span></span> | <span data-ttu-id="bd0ac-117">スタート画面で、「PowerShell」と入力し始めます。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-117">On the start screen, start typing PowerShell.</span></span><br/><span data-ttu-id="bd0ac-118">デスクトップ上の場合は、左下隅にある Windows アイコンをクリックして、「PowerShell」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="bd0ac-118">If on desktop, click left lower corner Windows icon, start typing PowerShell</span></span>
<span data-ttu-id="bd0ac-119">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-119">Windows 7 SP1</span></span> | <span data-ttu-id="bd0ac-120">左下隅にある Windows アイコンをクリックして、検索ボックスに「PowerShell」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="bd0ac-120">Click left lower corner Windows icon, on the search box start typing PowerShell</span></span>

### <a name="for-ise"></a><span data-ttu-id="bd0ac-121">ISE の場合</span><span class="sxs-lookup"><span data-stu-id="bd0ac-121">For ISE</span></span>

<span data-ttu-id="bd0ac-122">バージョン</span><span class="sxs-lookup"><span data-stu-id="bd0ac-122">Version</span></span> | <span data-ttu-id="bd0ac-123">インストール先</span><span class="sxs-lookup"><span data-stu-id="bd0ac-123">Location</span></span>
-- | --
<span data-ttu-id="bd0ac-124">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bd0ac-124">Windows 10</span></span> | <span data-ttu-id="bd0ac-125">左下隅にある Windows アイコンをクリックして、「ISE」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="bd0ac-125">Click left lower corner Windows icon, start typing ISE</span></span>
<span data-ttu-id="bd0ac-126">Windows 8.1、8.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-126">Windows 8.1, 8.0</span></span> | <span data-ttu-id="bd0ac-127">スタート画面で、「**PowerShell ISE**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-127">On the start screen, type **PowerShell ISE**.</span></span><br/><span data-ttu-id="bd0ac-128">デスクトップで、左下隅にある Windows アイコンをクリックして、「**PowerShell ISE**」と入力します</span><span class="sxs-lookup"><span data-stu-id="bd0ac-128">If on desktop, click left lower corner Windows icon, type **PowerShell ISE**</span></span>
<span data-ttu-id="bd0ac-129">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-129">Windows 7 SP1</span></span> | <span data-ttu-id="bd0ac-130">左下隅にある Windows アイコンをクリックして、検索ボックスに「PowerShell」と入力し始めます</span><span class="sxs-lookup"><span data-stu-id="bd0ac-130">Click left lower corner Windows icon, on the search box start typing PowerShell</span></span>

## <a name="finding-powershell-in-windows-server-versions"></a><span data-ttu-id="bd0ac-131">Windows Server バージョンで PowerShell を見つける</span><span class="sxs-lookup"><span data-stu-id="bd0ac-131">Finding PowerShell in Windows Server versions</span></span>

<span data-ttu-id="bd0ac-132">Windows Server 2008 R2 以降では、グラフィカル ユーザー インターフェイス (GUI) を含めずに、Windows オペレーティング システムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-132">Starting with Windows Server 2008 R2, Windows operating system can be installed without the graphical user interface (GUI).</span></span>
<span data-ttu-id="bd0ac-133">GUI なしの Windows Server のエディションは **Core** エディションという名前で、GUI ありのエディションは **Desktop** という名前です。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-133">Editions of Windows Server without GUI are named **Core** editions, and editions with the GUI are named **Desktop**.</span></span>

### <a name="windows-server-core-editions"></a><span data-ttu-id="bd0ac-134">Windows Server Core エディション</span><span class="sxs-lookup"><span data-stu-id="bd0ac-134">Windows Server Core editions</span></span>

<span data-ttu-id="bd0ac-135">すべての Core エディションで、サーバーにログインすると、Windows コマンド プロンプト ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-135">In all Core editions, when you log to the server you get a Windows command prompt window.</span></span>

<span data-ttu-id="bd0ac-136">「`powershell`」と入力して **Enter** キーを押し、コマンド プロンプト セッション内で PowerShell を開始します。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-136">Type `powershell` and press **ENTER** to start PowerShell inside the command prompt session.</span></span>
<span data-ttu-id="bd0ac-137">「`exit`」と入力して PowerShell セッションを終了し、コマンド プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-137">Type `exit` to terminate the PowerShell session and return to command prompt.</span></span>

### <a name="windows-server-desktop-editions"></a><span data-ttu-id="bd0ac-138">Windows Server Desktop エディション</span><span class="sxs-lookup"><span data-stu-id="bd0ac-138">Windows Server Desktop editions</span></span>

<span data-ttu-id="bd0ac-139">すべての Desktop エディションで、左下隅にある Windows アイコンをクリックして、「PowerShell」と入力し始めます。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-139">In all desktop editions, click the left lower corner Windows icon, start typing PowerShell.</span></span>
<span data-ttu-id="bd0ac-140">コンソールと ISE のオプションが両方表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-140">You get both console and ISE options.</span></span>

<span data-ttu-id="bd0ac-141">上記のルールの例外は、Windows Server 2008 R2 SP1 の ISE のみです。この場合は、左下隅にある Windows アイコンをクリックして、「PowerShell ISE」と入力します。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-141">The only exception to the above rule is the ISE in Windows Server 2008 R2 SP1; in this case, click the left lower corner Windows icon, type PowerShell ISE.</span></span>

## <a name="how-to-check-the-version-of-powershell"></a><span data-ttu-id="bd0ac-142">PowerShell のバージョンを確認する方法</span><span class="sxs-lookup"><span data-stu-id="bd0ac-142">How to check the version of PowerShell</span></span>

<span data-ttu-id="bd0ac-143">インストールした PowerShell のバージョンを確認するには、PowerShell コンソール (または ISE) を起動し、「`$PSVersionTable`」と入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-143">To find which version of PowerShell you have installed, start a PowerShell console (or the ISE) and type `$PSVersionTable` and press **ENTER**.</span></span> <span data-ttu-id="bd0ac-144">`PSVersion` の値を探します。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-144">Look for the `PSVersion` value.</span></span>

## <a name="upgrading-existing-windows-powershell"></a><span data-ttu-id="bd0ac-145">既存の Windows PowerShell をアップグレードする</span><span class="sxs-lookup"><span data-stu-id="bd0ac-145">Upgrading existing Windows PowerShell</span></span>

<span data-ttu-id="bd0ac-146">PowerShell のインストール パッケージは、WMF インストーラー内に含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-146">The installation package for PowerShell comes inside a WMF installer.</span></span>
<span data-ttu-id="bd0ac-147">WMF インストーラーのバージョンは、PowerShell のバージョンに一致します。Windows PowerShell に、スタンドアロンのインストーラーはありません。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-147">The version of the WMF installer matches the version of PowerShell; there's no stand alone installer for Windows PowerShell.</span></span>

<span data-ttu-id="bd0ac-148">PowerShell の既存のバージョンを更新する場合、Windows では、以下の表を使って、更新する PowerShell のバージョン用のインストーラーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-148">If you need to update your existing version of PowerShell, in Windows, use the following table to locate the installer for the version of PowerShell you want to update to.</span></span>

<span data-ttu-id="bd0ac-149">Windows</span><span class="sxs-lookup"><span data-stu-id="bd0ac-149">Windows</span></span> | <span data-ttu-id="bd0ac-150">PS 3.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-150">PS 3.0</span></span> | <span data-ttu-id="bd0ac-151">PS 4.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-151">PS 4.0</span></span> | <span data-ttu-id="bd0ac-152">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-152">PS 5.0</span></span> | <span data-ttu-id="bd0ac-153">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-153">PS 5.1</span></span> |
--|--|--|--|--|
<span data-ttu-id="bd0ac-154">Windows 10 (注 1 を参照してください)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-154">Windows 10 (see Note1)</span></span><br/><span data-ttu-id="bd0ac-155">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="bd0ac-155">Windows Server 2016</span></span> | - | - | - | <span data-ttu-id="bd0ac-156">インストール済み</span><span class="sxs-lookup"><span data-stu-id="bd0ac-156">installed</span></span>
<span data-ttu-id="bd0ac-157">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-157">Windows 8.1</span></span><br/><span data-ttu-id="bd0ac-158">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bd0ac-158">Windows Server 2012 R2</span></span> | - | <span data-ttu-id="bd0ac-159">インストール済み</span><span class="sxs-lookup"><span data-stu-id="bd0ac-159">installed</span></span> | [<span data-ttu-id="bd0ac-160">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-160">WMF 5.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [<span data-ttu-id="bd0ac-161">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-161">WMF 5.1</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
<span data-ttu-id="bd0ac-162">Windows 8</span><span class="sxs-lookup"><span data-stu-id="bd0ac-162">Windows 8</span></span><br/><span data-ttu-id="bd0ac-163">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="bd0ac-163">Windows Server 2012</span></span> | <span data-ttu-id="bd0ac-164">インストール済み</span><span class="sxs-lookup"><span data-stu-id="bd0ac-164">installed</span></span> | [<span data-ttu-id="bd0ac-165">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-165">WMF 4.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [<span data-ttu-id="bd0ac-166">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-166">WMF 5.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [<span data-ttu-id="bd0ac-167">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-167">WMF 5.1</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
<span data-ttu-id="bd0ac-168">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-168">Windows 7 SP1</span></span><br/><span data-ttu-id="bd0ac-169">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-169">Windows Server 2008 R2 SP1</span></span> | [<span data-ttu-id="bd0ac-170">WMF 3.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-170">WMF 3.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=34595) | [<span data-ttu-id="bd0ac-171">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-171">WMF 4.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [<span data-ttu-id="bd0ac-172">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="bd0ac-172">WMF 5.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [<span data-ttu-id="bd0ac-173">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-173">WMF 5.1</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)

> [!NOTE]
>
> <span data-ttu-id="bd0ac-174">自動更新を有効にしている Windows 10 の最初のリリースでは、PowerShell はバージョン 5.0 から 5.1 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-174">On the initial release of Windows 10, with automatic updates enabled, PowerShell gets updated from version 5.0 to 5.1.</span></span>
>
> <span data-ttu-id="bd0ac-175">元のバージョンの Windows 10 が Windows Update によって更新されない場合、PowerShell のバージョンは 5.0 です。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-175">If the original version of Windows 10 is not updated through Windows Updates, the version of PowerShell is 5.0.</span></span>

## <a name="need-azure-powershell"></a><span data-ttu-id="bd0ac-176">Azure PowerShell が必要な場合</span><span class="sxs-lookup"><span data-stu-id="bd0ac-176">Need Azure PowerShell</span></span>

<span data-ttu-id="bd0ac-177">**Azure PowerShell** を探している場合は、「[Overview of Azure PowerShell](/powershell/azure/overview)」 (Azure PowerShell の概要) から開始することができます。</span><span class="sxs-lookup"><span data-stu-id="bd0ac-177">If you're looking for **Azure PowerShell**, you could start with [Overview of Azure PowerShell](/powershell/azure/overview).</span></span>

<span data-ttu-id="bd0ac-178">その他にも、[Azure PowerShell のインストールと構成](/powershell/azure/install-azurerm-ps)が必要な場合があります</span><span class="sxs-lookup"><span data-stu-id="bd0ac-178">Otherwise, what you might need is [Install and configure Azure PowerShell](/powershell/azure/install-azurerm-ps)</span></span>

## <a name="see-also"></a><span data-ttu-id="bd0ac-179">参照</span><span class="sxs-lookup"><span data-stu-id="bd0ac-179">See Also</span></span>

[<span data-ttu-id="bd0ac-180">Windows PowerShell のシステム要件</span><span class="sxs-lookup"><span data-stu-id="bd0ac-180">Windows PowerShell System Requirements</span></span>](Windows-PowerShell-System-Requirements.md)

[<span data-ttu-id="bd0ac-181">Windows PowerShell の開始</span><span class="sxs-lookup"><span data-stu-id="bd0ac-181">Starting Windows PowerShell</span></span>](../getting-started/Starting-Windows-PowerShell.md)