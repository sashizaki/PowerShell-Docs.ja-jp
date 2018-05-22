---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 3679c13c2d28f28f3102b24f6369f1dc264d6884
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="installation-instructions"></a><span data-ttu-id="fee5a-102">インストール手順</span><span class="sxs-lookup"><span data-stu-id="fee5a-102">Installation Instructions</span></span>

<span data-ttu-id="fee5a-103">お使いのオペレーティング システムとアーキテクチャに該当する適切なパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="fee5a-103">Download the correct package for your operating system and architecture:</span></span>

| <span data-ttu-id="fee5a-104">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="fee5a-104">Operating System</span></span>       | <span data-ttu-id="fee5a-105">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="fee5a-105">Architecture</span></span> | <span data-ttu-id="fee5a-106">パッケージ名</span><span class="sxs-lookup"><span data-stu-id="fee5a-106">Package Name</span></span>              |
|------------------------|--------------|---------------------------|
| <span data-ttu-id="fee5a-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="fee5a-107">Windows Server 2012 R2</span></span> | <span data-ttu-id="fee5a-108">x64</span><span class="sxs-lookup"><span data-stu-id="fee5a-108">x64</span></span>      | [<span data-ttu-id="fee5a-109">Win8.1AndW2K12R2-KB3134758-x64.msu</span><span class="sxs-lookup"><span data-stu-id="fee5a-109">Win8.1AndW2K12R2-KB3134758-x64.msu</span></span>](http://go.microsoft.com/fwlink/?LinkId=717507) |
| <span data-ttu-id="fee5a-110">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fee5a-110">Windows Server 2012</span></span>    | <span data-ttu-id="fee5a-111">x64</span><span class="sxs-lookup"><span data-stu-id="fee5a-111">x64</span></span>      | [<span data-ttu-id="fee5a-112">W2K12-KB3134759-x64.msu</span><span class="sxs-lookup"><span data-stu-id="fee5a-112">W2K12-KB3134759-x64.msu</span></span>](http://go.microsoft.com/fwlink/?LinkId=717506) |
| <span data-ttu-id="fee5a-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="fee5a-113">Windows Server 2008 R2</span></span> | <span data-ttu-id="fee5a-114">x64</span><span class="sxs-lookup"><span data-stu-id="fee5a-114">x64</span></span>      | [<span data-ttu-id="fee5a-115">Win7AndW2K8R2-KB3134760-x64.msu</span><span class="sxs-lookup"><span data-stu-id="fee5a-115">Win7AndW2K8R2-KB3134760-x64.msu</span></span>](http://go.microsoft.com/fwlink/?LinkId=717504) |
| <span data-ttu-id="fee5a-116">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="fee5a-116">Windows 8.1</span></span>            | <span data-ttu-id="fee5a-117">x64</span><span class="sxs-lookup"><span data-stu-id="fee5a-117">x64</span></span>          | [<span data-ttu-id="fee5a-118">Win8.1AndW2K12R2-KB3134758-x64.msu</span><span class="sxs-lookup"><span data-stu-id="fee5a-118">Win8.1AndW2K12R2-KB3134758-x64.msu</span></span>](http://go.microsoft.com/fwlink/?LinkId=717507) |
| <span data-ttu-id="fee5a-119">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="fee5a-119">Windows 8.1</span></span>            | <span data-ttu-id="fee5a-120">x86</span><span class="sxs-lookup"><span data-stu-id="fee5a-120">x86</span></span>          | [<span data-ttu-id="fee5a-121">Win8.1-KB3134758-x86.msu</span><span class="sxs-lookup"><span data-stu-id="fee5a-121">Win8.1-KB3134758-x86.msu</span></span>](http://go.microsoft.com/fwlink/?LinkID=717963) |
| <span data-ttu-id="fee5a-122">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="fee5a-122">Windows 7 SP1</span></span>          | <span data-ttu-id="fee5a-123">x64</span><span class="sxs-lookup"><span data-stu-id="fee5a-123">x64</span></span>          | [<span data-ttu-id="fee5a-124">Win7AndW2K8R2-KB3134760-x64.msu</span><span class="sxs-lookup"><span data-stu-id="fee5a-124">Win7AndW2K8R2-KB3134760-x64.msu</span></span>](http://go.microsoft.com/fwlink/?LinkId=717504) |
| <span data-ttu-id="fee5a-125">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="fee5a-125">Windows 7 SP1</span></span>          | <span data-ttu-id="fee5a-126">x86</span><span class="sxs-lookup"><span data-stu-id="fee5a-126">x86</span></span>          | [<span data-ttu-id="fee5a-127">Win7-KB3134760-x86.msu</span><span class="sxs-lookup"><span data-stu-id="fee5a-127">Win7-KB3134760-x86.msu</span></span>](http://go.microsoft.com/fwlink/?LinkID=717962) |


<span data-ttu-id="fee5a-128">**Windows エクスプローラー (または Windows Server 2012 R2 および Windows 8.1 ではファイル エクスプローラー) から WMF 5.0 をインストールするには:**</span><span class="sxs-lookup"><span data-stu-id="fee5a-128">**To install WMF 5.0 from Windows Explorer (or File Explorer in Windows Server 2012 R2 and Windows 8.1):**</span></span>

1. <span data-ttu-id="fee5a-129">MSU ファイルをダウンロードしたフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-129">Navigate to the folder into which you downloaded the MSU file.</span></span>

2. <span data-ttu-id="fee5a-130">MSU をダブルクリックして実行します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-130">Double-click the MSU to run it.</span></span>

<span data-ttu-id="fee5a-131">**コマンド プロンプトから WMF 5.0 をインストールするには:**</span><span class="sxs-lookup"><span data-stu-id="fee5a-131">**To install WMF 5.0 from Command Prompt:**</span></span>

1. <span data-ttu-id="fee5a-132">コンピューターのアーキテクチャに適切なパッケージをダウンロードした後、管理者特権 (管理者として実行) を使ってコマンド プロンプト ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="fee5a-132">After downloading the correct package for your computer's architecture, open a Command Prompt window with elevated user rights (Run as Administrator).</span></span> <span data-ttu-id="fee5a-133">Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 SP1 の Server Core インストール オプションで、既定で管理者特権でコマンド プロンプトが開きます。</span><span class="sxs-lookup"><span data-stu-id="fee5a-133">On the Server Core installation options of Windows Server 2012 R2 or Windows Server 2012 or Windows Server 2008 R2 SP1, Command Prompt opens with elevated user rights by default.</span></span>

2. <span data-ttu-id="fee5a-134">WMF 5.0 のインストール パッケージをダウンロードまたはコピーしたフォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-134">Change directories to the folder into which you have downloaded or copied the WMF 5.0 installation package.</span></span>

3. <span data-ttu-id="fee5a-135">次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-135">Run one of the following commands:</span></span>
    - <span data-ttu-id="fee5a-136">Windows Server 2012 R2 または Windows 8.1 x64 を実行しているコンピューターで、**Win8.1AndW2K12R2-KB3134758-x64.msu /quiet** を実行します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-136">On computers that are running Windows Server 2012 R2 or Windows 8.1 x64, run **Win8.1AndW2K12R2-KB3134758-x64.msu /quiet**.</span></span>
    - <span data-ttu-id="fee5a-137">Windows Server 2012 を実行しているコンピューターで、**W2K12-KB3134759-x64.msu /quiet** を実行します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-137">On computers that are running Windows Server 2012, run **W2K12-KB3134759-x64.msu /quiet**.</span></span>
    - <span data-ttu-id="fee5a-138">Windows Server 2008 R2 SP1 または Windows 7 SP1 x64 を実行しているコンピューターで、**Win7AndW2K8R2-KB3134760-x64.msu /quiet** を実行します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-138">On computers that are running Windows Server 2008 R2 SP1 or Windows 7 SP1 x64, run **Win7AndW2K8R2-KB3134760-x64.msu /quiet**.</span></span>
    - <span data-ttu-id="fee5a-139">Windows 8.1 x86 を実行しているコンピューターで、**Win8.1-KB3134758-x86.msu /quiet** を実行します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-139">On computers that are running Windows 8.1 x86, run **Win8.1-KB3134758-x86.msu /quiet**.</span></span>
    - <span data-ttu-id="fee5a-140">Windows 7 SP1 x86 を実行しているコンピューターで、**Win7-KB3134760-x86.msu /quiet** を実行します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-140">On computers that are running Windows 7 SP1 x86, run **Win7-KB3134760-x86.msu /quiet**.</span></span>

<span data-ttu-id="fee5a-141">**Windows Server 2008 SP1 および Windows 7 SP1 でのインストールに関する追加の注記:**</span><span class="sxs-lookup"><span data-stu-id="fee5a-141">**Additional Installation Notes for Windows Server 2008 SP1 and Windows 7 SP1:**</span></span>

<span data-ttu-id="fee5a-142">次の前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-142">Ensure following prerequisites have been met:</span></span>
- <span data-ttu-id="fee5a-143">最新のサービス パックがインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="fee5a-143">Latest service pack is installed.</span></span>
- <span data-ttu-id="fee5a-144">[WMF 4.0](http://www.microsoft.com/en-us/download/details.aspx?id=40855) がインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="fee5a-144">[WMF 4.0](http://www.microsoft.com/en-us/download/details.aspx?id=40855) is installed</span></span>

<span data-ttu-id="fee5a-145">*WinRM の依存関係:* Windows PowerShell Desired State Configuration (DSC) は、WinRM に依存します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-145">*WinRM Dependency:* Windows PowerShell Desired State Configuration (DSC) depends on WinRM.</span></span> <span data-ttu-id="fee5a-146">WinRM は、Windows Server 2008 R2 および Windows 7 では既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="fee5a-146">WinRM is not enabled by default on Windows Server 2008 R2 and Windows 7.</span></span> <span data-ttu-id="fee5a-147">WinRM を有効にするには、Windows PowerShell 管理者特権セッションで **Set-WSManQuickConfig** を実行します。</span><span class="sxs-lookup"><span data-stu-id="fee5a-147">To enable WinRM, in a Windows PowerShell elevated session, run **Set-WSManQuickConfig**.</span></span>
