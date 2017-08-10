---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell Web Access のインストールと使用"
ms.openlocfilehash: a860f7c22829da46f0458ea729fa0afd1fe4fb6f
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
#  <a name="install-and-use-windows-powershell-web-access"></a><span data-ttu-id="39980-103">Windows PowerShell Web Access のインストールと使用</span><span class="sxs-lookup"><span data-stu-id="39980-103">Install and Use Windows PowerShell Web Access</span></span>

<span data-ttu-id="39980-104">最終更新日: 2013 年 11 月 5 日</span><span class="sxs-lookup"><span data-stu-id="39980-104">Updated: November 5, 2013</span></span>

<span data-ttu-id="39980-105">適用対象: Windows Server 2012 R2、Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="39980-105">Applies To: Windows Server 2012 R2, Windows Server 2012</span></span>

<span data-ttu-id="39980-106">Windows Server® 2012 で初めて導入された Windows PowerShell® Web Access は、Windows PowerShell ゲートウェイとして機能し、リモート コンピューターを対象とした Web ベースの Windows PowerShell コンソールを提供します。</span><span class="sxs-lookup"><span data-stu-id="39980-106">Windows PowerShell® Web Access, first introduced in Windows Server® 2012, acts as a Windows PowerShell gateway, providing a web-based Windows PowerShell console that is targeted at a remote computer.</span></span> <span data-ttu-id="39980-107">これを使うと、IT 担当者は、クライアント デバイスで必要な Windows PowerShell、リモート管理ソフトウェア、またはブラウザー プラグインをインストールしなくても、Web ブラウザーの Windows PowerShell コンソールから Windows PowerShell コマンドおよびスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39980-107">It enables IT Pros to run Windows PowerShell commands and scripts from a Windows PowerShell console in a web browser, with no Windows PowerShell, remote management software, or browser plug-in installation necessary on the client device.</span></span> <span data-ttu-id="39980-108">Web ベースの Windows PowerShell コンソールを実行するのに必要なのは、適切に構成された Windows PowerShell Web Access ゲートウェイと、JavaScript® をサポートし Cookie を有効にしたクライアント デバイス ブラウザーだけです。</span><span class="sxs-lookup"><span data-stu-id="39980-108">All that is required to run the web-based Windows PowerShell console is a properly-configured Windows PowerShell Web Access gateway, and a client device browser that supports JavaScript® and accepts cookies.</span></span>

<span data-ttu-id="39980-109">クライアント デバイスの例としては、ノート PC、仕事用ではないパーソナル コンピューター、貸与されたコンピューター、タブレット コンピューター、Web キオスク、Windows ベース以外のオペレーティング システムを実行しているコンピューター、および携帯電話のブラウザーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="39980-109">Examples of client devices include laptops, non-work personal computers, borrowed computers, tablet computers, web kiosks, computers that are not running a Windows-based operating system, and cell phone browsers.</span></span> <span data-ttu-id="39980-110">IT 担当者は、インターネットと Web ブラウザーにアクセスできるデバイスを使って、リモートの Windows ベース サーバーの重要な管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39980-110">IT Pros can perform critical management tasks on remote Windows-based servers from devices that have access to an Internet connection and a web browser.</span></span>

<span data-ttu-id="39980-111">ゲートウェイを適切にセットアップおよび構成した後は、Web ブラウザーを使って Windows PowerShell コンソールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="39980-111">After successful gateway setup and configuration, users can access a Windows PowerShell console by using a web browser.</span></span> <span data-ttu-id="39980-112">セキュリティで保護された Windows PowerShell Web Access の Web サイトを開くと、認証成功後に Web ベースの Windows PowerShell コンソールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39980-112">When users open the secured Windows PowerShell Web Access website, they can run a web-based Windows PowerShell console after successful authentication.</span></span>

<span data-ttu-id="39980-113">Windows PowerShell Web Access のセットアップおよび構成プロセスは、次の 3 つの手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="39980-113">Windows PowerShell Web Access setup and configuration is a three-step process:</span></span>

1.  <span data-ttu-id="39980-114">Windows PowerShell Web Access のインストール</span><span class="sxs-lookup"><span data-stu-id="39980-114">Installing Windows PowerShell Web Access</span></span>

2.  <span data-ttu-id="39980-115">ゲートウェイの構成</span><span class="sxs-lookup"><span data-stu-id="39980-115">Configuring the gateway</span></span>

3.  <span data-ttu-id="39980-116">Web ベースの Windows PowerShell コンソールへのアクセスをユーザーに許可する承認規則の構成</span><span class="sxs-lookup"><span data-stu-id="39980-116">Configuring authorization rules that allow users access to the web-based Windows PowerShell console</span></span>

<span data-ttu-id="39980-117">Windows PowerShell Web Access をインストールして構成する前に、このガイドをすべて読むことをお勧めします。このガイドでは、Windows PowerShell Web Access のインストール、セキュリティによる保護、およびアンインストールを行うための手順を説明しています。</span><span class="sxs-lookup"><span data-stu-id="39980-117">Before you install and configure Windows PowerShell Web Access, we recommend that you read this entire guide, which includes instructions about how to install, secure, and uninstall Windows PowerShell Web Access.</span></span> <span data-ttu-id="39980-118">「[Web ベースの Windows PowerShell コンソールの使用](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx)」トピックでは、Web ベースのコンソールにサインインする方法と、Web ベースの Windows PowerShell コンソールと **powershell.exe** コンソールの制限と相違点について説明しています。</span><span class="sxs-lookup"><span data-stu-id="39980-118">The [Use the Web-based Windows PowerShell Console](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx) topic describes how users sign in to the web-based console, and covers limitations and differences between the web-based Windows PowerShell console and the **powershell.exe** console.</span></span> <span data-ttu-id="39980-119">Web ベースのコンソールのエンド ユーザーは「[Web ベースの Windows PowerShell コンソールの使用](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx)」を読んでください。このガイドをこれ以上読む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="39980-119">End users of the web-based console should read [Use the Web-based Windows PowerShell Console](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx), but do not need to read the rest of this guide.</span></span>

<span data-ttu-id="39980-120">このトピックは Web サーバー (IIS) の操作に関する詳しいガイドを提供するものではありません。このトピックでは、Windows PowerShell Web Access ゲートウェイの構成に必要な手順だけを説明します。</span><span class="sxs-lookup"><span data-stu-id="39980-120">This topic does not provide in-depth Web Server (IIS) operations guidance; only those steps required to configure the Windows PowerShell Web Access gateway are described in this topic.</span></span> <span data-ttu-id="39980-121">IIS での Web サイトの構成とセキュリティ保護については、「関連項目」セクションの IIS に関するドキュメント リソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-121">For more information about configuring and securing websites in IIS, see the IIS documentation resources in the See Also section.</span></span>

<span data-ttu-id="39980-122">次の図は、Windows PowerShell Web Access のしくみを示しています。</span><span class="sxs-lookup"><span data-stu-id="39980-122">The following diagram shows how Windows PowerShell Web Access works.</span></span>

<span><img src="https://i-technet.sec.s-msft.com/dynimg/IC564303.jpeg" title="Windows PowerShell Web Access diagram" alt="Windows PowerShell Web Access diagram" id="ee15fa8f-ce13-49e5-933d-514f6d60a2b1" /></span>

<span data-ttu-id="39980-123">このトピックの内容:</span><span class="sxs-lookup"><span data-stu-id="39980-123">In this topic:</span></span>

-   [<span data-ttu-id="39980-124">Windows PowerShell Web Access の実行に関する要件</span><span class="sxs-lookup"><span data-stu-id="39980-124">Requirements for running Windows PowerShell Web Access</span></span>](#BKMK_reqs)

-   [<span data-ttu-id="39980-125">ブラウザーとクライアント デバイスのサポート</span><span class="sxs-lookup"><span data-stu-id="39980-125">Browser and client device support</span></span>](#BKMK_browser)

-   [<span data-ttu-id="39980-126">推奨される (クイック) デプロイ</span><span class="sxs-lookup"><span data-stu-id="39980-126">Recommended (quick) deployment</span></span>](#BKMK_recm)

-   [<span data-ttu-id="39980-127">カスタム デプロイ</span><span class="sxs-lookup"><span data-stu-id="39980-127">Custom deployment</span></span>](#BKMK_custom)

-   [<span data-ttu-id="39980-128">正規の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="39980-128">Configure a genuine certificate</span></span>](#BKMK_configcert)

<a href="" id="BKMK_reqs"></a>

<span data-ttu-id="39980-129"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Windows PowerShell Web Access の実行に関する要件</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_0" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="39980-129"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Requirements for running Windows PowerShell Web Access</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_0" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-130">Windows PowerShell Web Access を使用するには、ゲートウェイを実行するサーバーで Web サーバー (IIS)、.NET Framework 4.5、Windows PowerShell 3.0 または Windows PowerShell 4.0 が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="39980-130">Windows PowerShell Web Access requires Web Server (IIS), .NET Framework 4.5, and Windows PowerShell 3.0 or Windows PowerShell 4.0 to be running on the server on which you want to run the gateway.</span></span> <span data-ttu-id="39980-131">Windows PowerShell Web Access は、サーバー マネージャーの役割および機能の追加ウィザードを使用するか、サーバー マネージャーの Windows PowerShell のデプロイ コマンドレットを使用して、Windows Server 2012 R2 または Windows Server 2012 を実行中のサーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="39980-131">You can install Windows PowerShell Web Access on a server that is running Windows Server 2012 R2 or Windows Server 2012 by using either the Add Roles and Features Wizard in Server Manager, or Windows PowerShell deployment cmdlets for Server Manager.</span></span> <span data-ttu-id="39980-132">サーバー マネージャーまたはデプロイ コマンドレットを使って Windows PowerShell Web Access をインストールすると、インストール プロセスの一環として、必要な役割と機能が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="39980-132">When you install Windows PowerShell Web Access by using Server Manager or its deployment cmdlets, required roles and features are automatically added as part of the installation process.</span></span>

<span data-ttu-id="39980-133">Windows PowerShell Web Access により、リモート ユーザーは Web ブラウザーで Windows PowerShell を使って、組織内のコンピューターにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="39980-133">Windows PowerShell Web Access allows remote users to access computers in your organization by using Windows PowerShell in a web browser.</span></span> <span data-ttu-id="39980-134">Windows PowerShell Web Access は便利で強力な管理ツールですが、Web ベースのアクセスを利用するとセキュリティ上のリスクが生じるため、できる限りセキュリティを確保して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39980-134">Although Windows PowerShell Web Access is a convenient and powerful management tool, the web-based access poses security risks, and should be configured as securely as possible.</span></span> <span data-ttu-id="39980-135">Windows PowerShell Web Access ゲートウェイを構成する管理者は、利用可能なセキュリティ層を使うことをお勧めします。このセキュリティ層とは、Windows PowerShell Web Access に含まれるコマンドレット ベースの承認規則と、Web サーバー (IIS) およびサード パーティ アプリケーションで使うことができるセキュリティ層の両方です。</span><span class="sxs-lookup"><span data-stu-id="39980-135">We recommend that administrators who configure the Windows PowerShell Web Access gateway use available security layers, both the cmdlet-based authorization rules included with Windows PowerShell Web Access, and security layers that are available in Web Server (IIS) and third-party applications.</span></span> <span data-ttu-id="39980-136">このドキュメントには、テスト環境にのみ推奨される安全でない例と、セキュリティ保護された展開に推奨される例の両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="39980-136">This documentation includes both unsecure examples that are only recommended for test environments, as well as examples that are recommended for secure deployments.</span></span>

<a href="" id="BKMK_browser"></a>

<span data-ttu-id="39980-137"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">ブラウザーとクライアント デバイスのサポート</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="39980-137"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Browser and client device support</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-138">Windows PowerShell Web Access は次のインターネット ブラウザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="39980-138">Windows PowerShell Web Access supports the following Internet browsers.</span></span> <span data-ttu-id="39980-139">モバイル ブラウザーは公式にはサポートされていませんが、それらの多くが Web ベースの Windows PowerShell コンソールを実行できるようです。</span><span class="sxs-lookup"><span data-stu-id="39980-139">Although mobile browsers are not officially supported, many may be able to run the web-based Windows PowerShell console.</span></span> <span data-ttu-id="39980-140">その他のブラウザーも、Cookie の許可、JavaScript の実行、および HTTPS Web サイトの実行に対応している場合は動作すると思われますが、公式にはテストされていません。</span><span class="sxs-lookup"><span data-stu-id="39980-140">Other browsers that accept cookies, run JavaScript, and run HTTPS websites are expected to work, but are not officially tested.</span></span>

###

<span data-ttu-id="39980-141"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">サポート対象のデスクトップ コンピューター ブラウザー</span></a></span><span class="sxs-lookup"><span data-stu-id="39980-141"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Supported desktop computer browsers</span></a></span></span>

------------------------------------------------------------------------

-   <span data-ttu-id="39980-142">Windows® Internet Explorer® for Microsoft Windows® 8.0、9.0、10.0、および 11.0</span><span class="sxs-lookup"><span data-stu-id="39980-142">Windows® Internet Explorer® for Microsoft Windows® 8.0, 9.0, 10.0, and 11.0</span></span>

-   <span data-ttu-id="39980-143">Mozilla Firefox® 10.0.2</span><span class="sxs-lookup"><span data-stu-id="39980-143">Mozilla Firefox® 10.0.2</span></span>

-   <span data-ttu-id="39980-144">Google Chrome™ 17.0.963.56m for Windows</span><span class="sxs-lookup"><span data-stu-id="39980-144">Google Chrome™ 17.0.963.56m for Windows</span></span>

-   <span data-ttu-id="39980-145">Apple Safari® 5.1.2 for Windows</span><span class="sxs-lookup"><span data-stu-id="39980-145">Apple Safari® 5.1.2 for Windows</span></span>

-   <span data-ttu-id="39980-146">Apple Safari 5.1.2 for Mac OS®</span><span class="sxs-lookup"><span data-stu-id="39980-146">Apple Safari 5.1.2 for Mac OS®</span></span>

###

<span data-ttu-id="39980-147"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">最低限のテストを実施済みのモバイル デバイスまたはブラウザー</span></a></span><span class="sxs-lookup"><span data-stu-id="39980-147"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Minimally-tested mobile devices or browsers</span></a></span></span>

------------------------------------------------------------------------

-   <span data-ttu-id="39980-148">Windows Phone 7 および 7.5</span><span class="sxs-lookup"><span data-stu-id="39980-148">Windows Phone 7 and 7.5</span></span>

-   <span data-ttu-id="39980-149">Google Android WebKit 3.1 Browser Android 2.2.1 (Kernel 2.6)</span><span class="sxs-lookup"><span data-stu-id="39980-149">Google Android WebKit 3.1 Browser Android 2.2.1 (Kernel 2.6)</span></span>

-   <span data-ttu-id="39980-150">Apple Safari for iPhone operating system 5.0.1</span><span class="sxs-lookup"><span data-stu-id="39980-150">Apple Safari for iPhone operating system 5.0.1</span></span>

-   <span data-ttu-id="39980-151">Apple Safari for iPad 2 operating system 5.0.1</span><span class="sxs-lookup"><span data-stu-id="39980-151">Apple Safari for iPad 2 operating system 5.0.1</span></span>

###

<span data-ttu-id="39980-152"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">ブラウザーの要件</span></a></span><span class="sxs-lookup"><span data-stu-id="39980-152"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Browser requirements</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-153">Web ベースの Windows PowerShell コンソールを使うには、ブラウザーが次の操作を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="39980-153">To use the Windows PowerShell Web Access web-based console, browsers must do the following.</span></span>

-   <span data-ttu-id="39980-154">Windows PowerShell Web Access ゲートウェイ Web サイトの Cookie を許可する。</span><span class="sxs-lookup"><span data-stu-id="39980-154">Allow cookies from the Windows PowerShell Web Access gateway website.</span></span>

-   <span data-ttu-id="39980-155">HTTPS ページを開き、読み取る。</span><span class="sxs-lookup"><span data-stu-id="39980-155">Be able to open and read HTTPS pages.</span></span>

-   <span data-ttu-id="39980-156">JavaScript を使う Web サイトを開き、実行する。</span><span class="sxs-lookup"><span data-stu-id="39980-156">Open and run websites that use JavaScript.</span></span>

<a href="" id="BKMK_recm"></a>

<span data-ttu-id="39980-157"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">推奨される (クイック) デプロイ</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_2" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="39980-157"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Recommended (quick) deployment</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_2" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-158">Windows PowerShell Web Access ゲートウェイは、Windows PowerShell コマンドレットを使用するか、サーバー マネージャーから開く役割および機能の追加ウィザードを使用して、Windows Server 2012 R2 または Windows Server 2012 を実行中のサーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="39980-158">You can install the Windows PowerShell Web Access gateway on a server that is running Windows Server 2012 R2 or Windows Server 2012 by using either Windows PowerShell cmdlets, or by using the Add Roles and Features Wizard that is opened from within Server Manager.</span></span> <span data-ttu-id="39980-159">クイック インストールと構成では、このセクションで説明する Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="39980-159">For quick installation and configuration, use Windows PowerShell cmdlets, as described in this section.</span></span>

-   [<span data-ttu-id="39980-160">手順 1: Windows PowerShell Web Access をインストールする</span><span class="sxs-lookup"><span data-stu-id="39980-160">Step 1: Install Windows PowerShell Web Access</span></span>](#BKMK_step1)

-   [<span data-ttu-id="39980-161">手順 2: ゲートウェイを構成する</span><span class="sxs-lookup"><span data-stu-id="39980-161">Step 2: Configure the gateway</span></span>](#BKMK_step2)

-   [<span data-ttu-id="39980-162">手順 3: 制限的な承認規則を構成する</span><span class="sxs-lookup"><span data-stu-id="39980-162">Step 3: Configure a restrictive authorization rule</span></span>](#BKMK_step3)

<a href="" id="BKMK_step1"></a>
###

<span data-ttu-id="39980-163"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 1: Windows PowerShell Web Access をインストールする</span></a></span><span class="sxs-lookup"><span data-stu-id="39980-163"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 1: Install Windows PowerShell Web Access</span></a></span></span>

------------------------------------------------------------------------

#### <a name="to-install-windows-powershell-web-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="39980-164">Windows PowerShell コマンドレットを使って Windows PowerShell Web Access をインストールするには</span><span class="sxs-lookup"><span data-stu-id="39980-164">To install Windows PowerShell Web Access by using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="39980-165">次のいずれかを実行して、管理者特権を使って Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-165">Do one of the following to open a Windows PowerShell session with elevated user rights.</span></span>

    -   <span data-ttu-id="39980-166">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-166">On the Windows desktop, right-click **Windows PowerShell** on the taskbar, and then click **Run as Administrator**.</span></span>

    -   <span data-ttu-id="39980-167">Windows の**スタート**画面で、**[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-167">On the Windows **Start** screen, right-click **Windows PowerShell**, and then click **Run as Administrator**.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="39980-168"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="39980-168"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="39980-169">Windows PowerShell 3.0 と 4.0 では、サーバー マネージャー コマンドレット モジュールに含まれるコマンドレットを実行する前に、そのモジュールを Windows PowerShell セッションにインポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="39980-169">In Windows PowerShell 3.0 and 4.0, there is no need to import the Server Manager cmdlet module into the Windows PowerShell session before running cmdlets that are part of the module.</span></span> <span data-ttu-id="39980-170">モジュールは、モジュールに含まれるコマンドレットを初めて実行するときに自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="39980-170">A module is automatically imported the first time you run a cmdlet that is part of the module.</span></span> <span data-ttu-id="39980-171">また、Windows PowerShell のコマンドレットでは、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="39980-171">Also, Windows PowerShell cmdlets are not case-sensitive.</span></span></p></td>
    </tr>
    </tbody>
    </table>

2.  <span data-ttu-id="39980-172">次のように入力して **Enter** キーを押します。*computer_name* は、Windows PowerShell Web Access をインストールするリモート コンピューターの名前です (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="39980-172">Type the following, and then press **Enter**, where *computer_name* represents a remote computer on which you want to install Windows PowerShell Web Access, if applicable.</span></span> <span data-ttu-id="39980-173"><span class="code">Restart</span> パラメーターによって、対象サーバーが自動的に再起動されます (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="39980-173">The <span class="code">Restart</span> parameter automatically restarts destination servers if required.</span></span>

    [<span data-ttu-id="39980-174">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-174">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_374a9c21-4f6e-471e-b957-bb190a594533'); "Copy to clipboard.")

        Install-WindowsFeature -Name WindowsPowerShellWebAccess -ComputerName <computer_name> -IncludeManagementTools -Restart

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="39980-175"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="39980-175"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="39980-176">Windows PowerShell のコマンドレットを使って Windows PowerShell Web Access をインストールする場合、Web サーバー (IIS) の管理ツールは既定では追加されません。</span><span class="sxs-lookup"><span data-stu-id="39980-176">Installing Windows PowerShell Web Access by using Windows PowerShell cmdlets does not add Web Server (IIS) management tools by default.</span></span> <span data-ttu-id="39980-177">Windows PowerShell Web Access ゲートウェイと同じサーバーに管理ツールをインストールする場合、<span class="code">IncludeManagementTools</span> パラメーターをインストール コマンドに追加します (この手順でも追加しています)。</span><span class="sxs-lookup"><span data-stu-id="39980-177">If you want to install the management tools on the same server as the Windows PowerShell Web Access gateway, add the <span class="code">IncludeManagementTools</span> parameter to the installation command (as provided in this step).</span></span> <span data-ttu-id="39980-178">Windows PowerShell Web Access の Web サイトをリモート コンピューターから管理する場合は、ゲートウェイの管理元となるコンピューターに <a href="http://go.microsoft.com/fwlink/?LinkID=304145">Remote Server Administration Tools for Windows 8.1</a> または <a href="http://go.microsoft.com/fwlink/p/?LinkID=238560">Remote Server Administration Tools for Windows 8</a> をインストールすることで、IIS マネージャー スナップインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="39980-178">If you are managing the Windows PowerShell Web Access website from a remote computer, install the IIS Manager snap-in by installing <a href="http://go.microsoft.com/fwlink/?LinkID=304145">Remote Server Administration Tools for Windows 8.1</a> or <a href="http://go.microsoft.com/fwlink/p/?LinkID=238560">Remote Server Administration Tools for Windows 8</a> on the computer from which you want to manage the gateway.</span></span></p></td>
    </tr>
    </tbody>
    </table>

    <span data-ttu-id="39980-179">オフライン VHD に役割や機能をインストールするには、<span class="code">ComputerName</span> パラメーターと <span class="code">VHD</span> パラメーターの両方を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39980-179">To install roles and features on an offline VHD, you must add both the <span class="code">ComputerName</span> parameter and the <span class="code">VHD</span> parameter.</span></span> <span data-ttu-id="39980-180"><span class="code">ComputerName</span> パラメーターには VHD のマウント先のサーバー名が格納され、<span class="code">VHD</span> パラメーターには指定したサーバー上の VHD ファイルへのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="39980-180">The <span class="code">ComputerName</span> parameter contains the name of the server on which to mount the VHD, and the <span class="code">VHD</span> parameter contains the path to the VHD file on the specified server.</span></span>

    [<span data-ttu-id="39980-181">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-181">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_d841d509-347e-49d0-bf54-8d1f306bece6'); "Copy to clipboard.")

        Install-WindowsFeature -Name WindowsPowerShellWebAccess -VHD <path> -ComputerName <computer_name> -IncludeManagementTools -Restart

3.  <span data-ttu-id="39980-182">インストールが完了したら、対象サーバーに Windows PowerShell Web Access がインストールされたことを確認します。これには、管理者特権で開いた Windows PowerShell コンソールで、対象サーバーに対して **Get-WindowsFeature** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="39980-182">When installation is complete, verify that Windows PowerShell Web Access was installed on destination servers by running the **Get-WindowsFeature** cmdlet on a destination server, in a Windows PowerShell console that has been opened with elevated user rights.</span></span> <span data-ttu-id="39980-183">また、サーバー マネージャー コンソールに Windows PowerShell Web Access がインストールされたことも確認できます。これには、**[すべてのサーバー]** ページで対象サーバーを選択し、選択したサーバーの **[役割と機能]** タイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="39980-183">You can also verify that Windows PowerShell Web Access was installed in the Server Manager console, by selecting a destination server on the **All Servers** page, and then viewing the **Roles and Features** tile for the selected server.</span></span> <span data-ttu-id="39980-184">Windows PowerShell Web Access の Readme ファイルも表示できます。</span><span class="sxs-lookup"><span data-stu-id="39980-184">You can also view the readme file for Windows PowerShell Web Access.</span></span>

4.  <span data-ttu-id="39980-185">Windows PowerShell Web Access がインストールされると、基本的かつ必須のゲートウェイ セットアップ手順を記載した Readme ファイルの確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39980-185">After Windows PowerShell Web Access is installed, you are prompted to review the readme file, which contains basic, required setup instructions for the gateway.</span></span> <span data-ttu-id="39980-186">これらのセットアップ手順は、次の「[手順 2. ゲートウェイを構成する](#BKMK_step2)」セクションでも説明します。</span><span class="sxs-lookup"><span data-stu-id="39980-186">These setup instructions are also in the following section, [Step 2: Configure the gateway](#BKMK_step2).</span></span> <span data-ttu-id="39980-187">Readme ファイルのパスは <span class="computerOutputInline">C:\\Windows\\Web\\PowerShellWebAccess\\wwwroot\\README.txt</span> です。</span><span class="sxs-lookup"><span data-stu-id="39980-187">The path to the readme file is <span class="computerOutputInline">C:\\Windows\\Web\\PowerShellWebAccess\\wwwroot\\README.txt</span>.</span></span>

<a href="" id="BKMK_step2"></a>
###

<span data-ttu-id="39980-188"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 2: ゲートウェイを構成する</span></a></span><span class="sxs-lookup"><span data-stu-id="39980-188"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 2: Configure the gateway</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-189">**Install-PswaWebApplication** コマンドレットを使うと Windows PowerShell Web Access を簡単に構成できます。</span><span class="sxs-lookup"><span data-stu-id="39980-189">The **Install-PswaWebApplication** cmdlet is a quick way to get Windows PowerShell Web Access configured.</span></span> <span data-ttu-id="39980-190"><span class="code">UseTestCertificate</span> パラメーターを <span class="code">Install-PswaWebApplication</span> コマンドレットに追加することで、テスト用の自己署名 SSL 証明書をインストールできますが、これは安全ではありません。運用環境のセキュリティ保護のため、常に証明機関 (CA) によって署名された有効な SSL 証明書を使ってください。</span><span class="sxs-lookup"><span data-stu-id="39980-190">Although you can add the <span class="code">UseTestCertificate</span> parameter to the <span class="code">Install-PswaWebApplication</span> cmdlet to install a self-signed SSL certificate for test purposes, this is not secure; for a secure production environment, always use a valid SSL certificate that has been signed by a certification authority (CA).</span></span> <span data-ttu-id="39980-191">管理者は IIS マネージャー コンソールを使ってテスト証明書を任意の署名済み証明書に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="39980-191">Administrators can replace the test certificate with a signed certificate of their choice by using the IIS Manager console.</span></span>

<span data-ttu-id="39980-192">Windows PowerShell Web Access の Web アプリケーションの構成を完了するには、<span class="code">Install-PswaWebApplication</span> コマンドレットを実行するか、IIS マネージャーの GUI ベースの構成手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39980-192">You can complete Windows PowerShell Web Access web application configuration either by running the <span class="code">Install-PswaWebApplication</span> cmdlet or by performing GUI-based configuration steps in IIS Manager.</span></span> <span data-ttu-id="39980-193">既定では、コマンドレットによって **pswa** Web アプリケーション (および専用の **pswa_pool** というアプリケーション プール) が **[既定の Web サイト]** コンテナーにインストールされ、IIS マネージャーで確認できます。必要な場合、コマンドレットに指定して Web アプリケーションの既定のサイト コンテナーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="39980-193">By default, the cmdlet installs the web application, **pswa** (and an application pool for it, **pswa_pool**), in the **Default Web Site** container, as shown in IIS Manager; if desired, you can instruct the cmdlet to change the default site container of the web application.</span></span> <span data-ttu-id="39980-194">IIS マネージャーは、ポート番号や Secure Sockets Layer (SSL) 証明書の変更など、Web アプリケーションで利用できる構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="39980-194">IIS Manager offers configuration options that are available for web applications, such as changing the port number or the Secure Sockets Layer (SSL) certificate.</span></span>

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39980-195"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC17938.jpeg" title="System_CAPS_security" alt="System_CAPS_security" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-security" /></span><span class="alertTitle">セキュリティ メモ</span></span><span class="sxs-lookup"><span data-stu-id="39980-195"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC17938.jpeg" title="System_CAPS_security" alt="System_CAPS_security" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-security" /></span><span class="alertTitle"> Security Note </span></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39980-196">管理者には、CA によって署名された有効な証明書を使うようゲートウェイを構成することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39980-196">We strongly recommend that administrators configure the gateway to use a valid certificate that has been signed by a CA.</span></span></p></td>
</tr>
</tbody>
</table>

-   [<span data-ttu-id="39980-197">Install-PswaWebApplication を使って、テスト証明書を使う Windows PowerShell Web Access Web ゲートウェイを構成するには</span><span class="sxs-lookup"><span data-stu-id="39980-197">To configure the Windows PowerShell Web Access gateway with a test certificate by using Install-PswaWebApplication</span></span>](#BKMK_testcert)

-   [<span data-ttu-id="39980-198">正規の証明書を持つ Windows PowerShell Web Access ゲートウェイを Install-PswaWebApplication と IIS Manager を使用して構成するには</span><span class="sxs-lookup"><span data-stu-id="39980-198">To configure the Windows PowerShell Web Access gateway with a genuine certificate by using Install-PswaWebApplication and IIS Manager</span></span>](#BKMK_gencert)

#### <a name="to-configure-the-windows-powershell-web-access-gateway-with-a-test-certificate-by-using-install-pswawebapplication"></a><span data-ttu-id="39980-199">Install-PswaWebApplication を使って、テスト証明書を使う Windows PowerShell Web Access Web ゲートウェイを構成するには</span><span class="sxs-lookup"><span data-stu-id="39980-199">To configure the Windows PowerShell Web Access gateway with a test certificate by using Install-PswaWebApplication</span></span>

1.  <span data-ttu-id="39980-200">次のいずれかを実行して Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-200">Do one of the following to open a Windows PowerShell session.</span></span>

    -   <span data-ttu-id="39980-201">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-201">On the Windows desktop, right-click **Windows PowerShell** on the taskbar.</span></span>

    -   <span data-ttu-id="39980-202">Windows の**スタート**画面で、**[Windows PowerShell]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-202">On the Windows **Start** screen, click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="39980-203">次のように入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="39980-203">Type the following, and then press **Enter**.</span></span>

    <span data-ttu-id="39980-204">**Install-PswaWebApplication -UseTestCertificate**</span><span class="sxs-lookup"><span data-stu-id="39980-204">**Install-PswaWebApplication -UseTestCertificate**</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="39980-205"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC17938.jpeg" title="System_CAPS_security" alt="System_CAPS_security" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-security" /></span><span class="alertTitle">セキュリティ メモ</span></span><span class="sxs-lookup"><span data-stu-id="39980-205"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC17938.jpeg" title="System_CAPS_security" alt="System_CAPS_security" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-security" /></span><span class="alertTitle"> Security Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="39980-206"><span class="code">UseTestCertificate</span> パラメーターはプライベートなテスト環境でのみ使ってください。</span><span class="sxs-lookup"><span data-stu-id="39980-206">The <span class="code">UseTestCertificate</span> parameter should only be used in a private test environment.</span></span> <span data-ttu-id="39980-207">運用環境のセキュリティ保護のため、CA によって署名された有効な証明書を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39980-207">For a secure production environment, we recommend using a valid certificate that has been signed by a CA.</span></span></p></td>
    </tr>
    </tbody>
    </table>

    <span data-ttu-id="39980-208">コマンドレットを実行すると、IIS の [既定の Web サイト] コンテナーに Windows PowerShell Web Access の Web アプリケーションがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="39980-208">Running the cmdlet installs the Windows PowerShell Web Access web application within the IIS Default Web Site container.</span></span> <span data-ttu-id="39980-209">このコマンドレットにより、既定の Web サイト (https://&lt;server_name&gt;/pswa) で Windows PowerShell Web Access を実行するために必要なインフラストラクチャが作成されます。</span><span class="sxs-lookup"><span data-stu-id="39980-209">The cmdlet creates the infrastructure required to run Windows PowerShell Web Access on the default website, https://&lt;server_name&gt;/pswa.</span></span> <span data-ttu-id="39980-210">Web アプリケーションを別の Web サイトにインストールするには、<span class="code">WebSiteName</span> パラメーターを追加して Web サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="39980-210">To install the web application in a different website, provide the website name by adding the <span class="code">WebSiteName</span> parameter.</span></span> <span data-ttu-id="39980-211">Web アプリケーションの名前 (既定値は <span class="code">pswa</span>) を変更するには、<span class="code">WebApplicationName</span> パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="39980-211">To change the name of the web application (the default is <span class="code">pswa</span>), add the <span class="code">WebApplicationName</span> parameter.</span></span>

    <span data-ttu-id="39980-212">コマンドレットの実行により次の設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="39980-212">The following settings are configured by running the cmdlet.</span></span> <span data-ttu-id="39980-213">これらの設定は、必要に応じて IIS マネージャー コンソールで変更できます。</span><span class="sxs-lookup"><span data-stu-id="39980-213">You can change these manually in the IIS Manager console, if desired.</span></span>

    -   <span data-ttu-id="39980-214">Path: /pswa</span><span class="sxs-lookup"><span data-stu-id="39980-214">Path: /pswa</span></span>

    -   <span data-ttu-id="39980-215">ApplicationPool: pswa_pool</span><span class="sxs-lookup"><span data-stu-id="39980-215">ApplicationPool: pswa_pool</span></span>

    -   <span data-ttu-id="39980-216">EnabledProtocols: http</span><span class="sxs-lookup"><span data-stu-id="39980-216">EnabledProtocols: http</span></span>

    -   <span data-ttu-id="39980-217">PhysicalPath: %*windir*%/Web/PowerShellWebAccess/wwwroot</span><span class="sxs-lookup"><span data-stu-id="39980-217">PhysicalPath: %*windir*%/Web/PowerShellWebAccess/wwwroot</span></span>

    <span data-ttu-id="39980-218"><span class="label">例:</span> <span class="code">Install-PswaWebApplication -webApplicationName myWebApp -useTestCertificate</span></span><span class="sxs-lookup"><span data-stu-id="39980-218"><span class="label">Example:</span> <span class="code">Install-PswaWebApplication -webApplicationName myWebApp -useTestCertificate</span></span></span>

    <span data-ttu-id="39980-219">この例では、Windows PowerShell Web Access の最終的な Web サイトは https://&lt;*server_name*&gt;/myWebApp になります。</span><span class="sxs-lookup"><span data-stu-id="39980-219">In this example, the resulting website for Windows PowerShell Web Access is https://&lt; *server_name*&gt;/myWebApp.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="39980-220"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="39980-220"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="39980-221">サインインできるのは、承認規則の追加によって Web サイトへのアクセスが許可されたユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="39980-221">You cannot sign in until users have been granted access to the website by adding authorization rules.</span></span> <span data-ttu-id="39980-222">詳細については、「<a href="#BKMK_step3">手順 3. 制限的な承認規則を構成する</a>」と「<a href="https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx">Windows PowerShell Web Access の承認規則とセキュリティ機能</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-222">For more information, see <a href="#BKMK_step3">Step 3: Configure a restrictive authorization rule</a> and <a href="https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx">Authorization Rules and Security Features of Windows PowerShell Web Access</a>.</span></span></p></td>
    </tr>
    </tbody>
    </table>

#### <a name="to-configure-the-windows-powershell-web-access-gateway-with-a-genuine-certificate-by-using-install-pswawebapplication-and-iis-manager"></a><span data-ttu-id="39980-223">正規の証明書を持つ Windows PowerShell Web Access ゲートウェイを Install-PswaWebApplication と IIS Manager を使用して構成するには</span><span class="sxs-lookup"><span data-stu-id="39980-223">To configure the Windows PowerShell Web Access gateway with a genuine certificate by using Install-PswaWebApplication and IIS Manager</span></span>

1.  <span data-ttu-id="39980-224">次のいずれかを実行して Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-224">Do one of the following to open a Windows PowerShell session.</span></span>

    -   <span data-ttu-id="39980-225">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-225">On the Windows desktop, right-click **Windows PowerShell** on the taskbar.</span></span>

    -   <span data-ttu-id="39980-226">Windows の**スタート**画面で、**[Windows PowerShell]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-226">On the Windows **Start** screen, click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="39980-227">次のように入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="39980-227">Type the following, and then press **Enter**.</span></span>

    <span data-ttu-id="39980-228">**Install-PswaWebApplication**</span><span class="sxs-lookup"><span data-stu-id="39980-228">**Install-PswaWebApplication**</span></span>

    <span data-ttu-id="39980-229">コマンドレットの実行により次のゲートウェイ設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="39980-229">The following gateway settings are configured by running the cmdlet.</span></span> <span data-ttu-id="39980-230">これらの設定は、必要に応じて IIS マネージャー コンソールで変更できます。</span><span class="sxs-lookup"><span data-stu-id="39980-230">You can change these manually in the IIS Manager console, if desired.</span></span> <span data-ttu-id="39980-231"><span class="code">WebsiteName</span> コマンドレットの <span class="code">WebApplicationName</span> および <span class="code">Install-PswaWebApplication</span> パラメーターの値を指定することも可能です。</span><span class="sxs-lookup"><span data-stu-id="39980-231">You can also specify values for the <span class="code">WebsiteName</span> and <span class="code">WebApplicationName</span> parameters of the <span class="code">Install-PswaWebApplication</span> cmdlet.</span></span>

    -   <span data-ttu-id="39980-232">Path: /pswa</span><span class="sxs-lookup"><span data-stu-id="39980-232">Path: /pswa</span></span>

    -   <span data-ttu-id="39980-233">ApplicationPool: pswa_pool</span><span class="sxs-lookup"><span data-stu-id="39980-233">ApplicationPool: pswa_pool</span></span>

    -   <span data-ttu-id="39980-234">EnabledProtocols: http</span><span class="sxs-lookup"><span data-stu-id="39980-234">EnabledProtocols: http</span></span>

    -   <span data-ttu-id="39980-235">PhysicalPath: %*windir*%/Web/PowerShellWebAccess/wwwroot</span><span class="sxs-lookup"><span data-stu-id="39980-235">PhysicalPath: %*windir*%/Web/PowerShellWebAccess/wwwroot</span></span>

3.  <span data-ttu-id="39980-236">次のいずれかの方法で IIS マネージャー コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-236">Open the IIS Manager console by doing one of the following.</span></span>

    -   <span data-ttu-id="39980-237">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="39980-237">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span> <span data-ttu-id="39980-238">[サーバー マネージャー] の **[ツール]** メニューで **[インターネット インフォメーション サービス (IIS) マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-238">On the **Tools** menu in Server Manager, click **Internet Information Services (IIS) Manager**.</span></span>

    -   <span data-ttu-id="39980-239">Windows の**スタート**画面で、**[サーバー マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-239">On the Windows **Start** screen, click **Server Manager**.</span></span>

4.  <span data-ttu-id="39980-240">IIS マネージャーのツリー ウィンドウで、Windows PowerShell Web Access がインストールされているサーバーのノードを展開し、**[サイト]** フォルダーを表示させます。</span><span class="sxs-lookup"><span data-stu-id="39980-240">In the IIS Manager tree pane, expand the node for the server on which Windows PowerShell Web Access is installed until the **Sites** folder is visible.</span></span> <span data-ttu-id="39980-241">**[サイト]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="39980-241">Expand the **Sites** folder.</span></span>

5.  <span data-ttu-id="39980-242">Windows PowerShell Web Access の Web アプリケーションをインストールした Web サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-242">Select the website in which you have installed the Windows PowerShell Web Access web application.</span></span> <span data-ttu-id="39980-243">**[操作]** ウィンドウで、**[バインド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-243">In the **Actions** pane, click **Bindings**.</span></span>

6.  <span data-ttu-id="39980-244">**[サイト バインド]** ダイアログ ボックスの **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-244">In the **Site Binding** dialog box, click **Add**.</span></span>

7.  <span data-ttu-id="39980-245">**[サイト バインドの追加]** ダイアログ ボックスの **[種類]** フィールドで、**[https]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-245">In the **Add Site Binding** dialog box, in the **Type** field, select **https**.</span></span>

8.  <span data-ttu-id="39980-246">**"SSL 証明書"** フィールドのドロップダウン メニューから、署名済み証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-246">In the **SSL certificate** field, select your signed certificate from the drop-down menu.</span></span> <span data-ttu-id="39980-247">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-247">Click **OK**.</span></span> <span data-ttu-id="39980-248">証明書の取得方法の詳細については、このトピックの「[IIS マネージャーで SSL 証明書を構成するには](#BKMK_cert)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-248">See [To configure an SSL certificate in IIS Manager](#BKMK_cert) in this topic for more information about how to obtain a certificate.</span></span>

    <span data-ttu-id="39980-249">これで、Windows PowerShell Web Access の Web アプリケーションが署名済み SSL 証明書を使うよう構成されました。</span><span class="sxs-lookup"><span data-stu-id="39980-249">The Windows PowerShell Web Access web application is now configured to use your signed SSL certificate.</span></span> <span data-ttu-id="39980-250">ブラウザー ウィンドウで https://&lt;server_name&gt;/pswa を開くと Windows PowerShell Web Access にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="39980-250">You can access Windows PowerShell Web Access by opening https://&lt;server_name&gt;/pswa in a browser window.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="39980-251"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="39980-251"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="39980-252">サインインできるのは、承認規則の追加によって Web サイトへのアクセスが許可されたユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="39980-252">You cannot sign in until users have been granted access to the website by adding authorization rules.</span></span> <span data-ttu-id="39980-253">詳細については、「<a href="#BKMK_step3">手順 3. 制限的な承認規則を構成する</a>」と「<a href="https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx">Windows PowerShell Web Access の承認規則とセキュリティ機能</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-253">For more information, see <a href="#BKMK_step3">Step 3: Configure a restrictive authorization rule</a> and <a href="https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx">Authorization Rules and Security Features of Windows PowerShell Web Access</a>.</span></span></p></td>
    </tr>
    </tbody>
    </table><span data-ttu-id="39980-254">

<a href="" id="BKMK_step3"></a>
###

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 3: 制限的な承認規則を構成する</span></a></span><span class="sxs-lookup"><span data-stu-id="39980-254">

<a href="" id="BKMK_step3"></a>
###

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 3: Configure a restrictive authorization rule</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-255">Windows PowerShell Web Access をインストールし、ゲートウェイを構成すると、ユーザーがブラウザーでサインイン ページを開けるようになります。ただし、Windows PowerShell Web Access 管理者によってアクセスを明示的に許可されない限りサインインできません。</span><span class="sxs-lookup"><span data-stu-id="39980-255">After Windows PowerShell Web Access is installed and the gateway is configured, users can open the sign-in page in a browser, but they cannot sign in until the Windows PowerShell Web Access administrator grants users access explicitly.</span></span> <span data-ttu-id="39980-256">Windows PowerShell Web Access のアクセス制御は、次の表に示す一連の Windows PowerShell コマンドレットによって管理します。</span><span class="sxs-lookup"><span data-stu-id="39980-256">Windows PowerShell Web Access access control is managed by using the set of Windows PowerShell cmdlets described in the following table.</span></span> <span data-ttu-id="39980-257">承認規則の追加と管理に関しては、相当する GUI はありません。</span><span class="sxs-lookup"><span data-stu-id="39980-257">There is no comparable GUI for adding or managing authorization rules.</span></span> <span data-ttu-id="39980-258">Windows PowerShell Web Access コマンドレットの詳細については、コマンドレット リファレンス トピック「[Windows PowerShell Web Access Cmdlets](https://technet.microsoft.com/library/hh918342.aspx)」(Windows PowerShell Web Access コマンドレット) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-258">For more detailed information about Windows PowerShell Web Access cmdlets, see the cmdlet reference topics, [Windows PowerShell Web Access Cmdlets](https://technet.microsoft.com/library/hh918342.aspx).</span></span>

<span data-ttu-id="39980-259">Windows PowerShell Web Access の承認規則とセキュリティの詳細については、「[Windows PowerShell Web Access の承認規則とセキュリティ機能](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-259">For more detail about Windows PowerShell Web Access authorization rules and security, see [Authorization Rules and Security Features of Windows PowerShell Web Access](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx).</span></span>

#### <a name="to-add-a-restrictive-authorization-rule"></a><span data-ttu-id="39980-260">制限的な承認規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="39980-260">To add a restrictive authorization rule</span></span>

1.  <span data-ttu-id="39980-261">次のいずれかを実行して、管理者特権を使って Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-261">Do one of the following to open a Windows PowerShell session with elevated user rights.</span></span>

    -   <span data-ttu-id="39980-262">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-262">On the Windows desktop, right-click **Windows PowerShell** on the taskbar, and then click **Run as Administrator**.</span></span>

    -   <span data-ttu-id="39980-263">Windows の**スタート**画面で、**[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-263">On the Windows **Start** screen, right-click **Windows PowerShell**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="39980-264"><span class="label">セッション構成を使用してユーザー アクセスを制限するためのオプション手順:</span> 規則内で使用するセッション構成が既に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="39980-264"><span class="label">Optional step for restricting user access by using session configurations:</span> Verify that session configurations that you want to use in your rules already exist.</span></span> <span data-ttu-id="39980-265">まだ作成されていない場合は、MSDN の「[about_Session_Configuration_Files](https://msdn.microsoft.com/library/windows/desktop/hh847838.aspx)」に記載されているセッション構成の作成手順を使用してください。</span><span class="sxs-lookup"><span data-stu-id="39980-265">If they have not yet been created, use instructions for creating session configurations in [about_Session_Configuration_Files](https://msdn.microsoft.com/library/windows/desktop/hh847838.aspx) on MSDN.</span></span>

3.  <span data-ttu-id="39980-266">次のように入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="39980-266">Type the following, and then press **Enter**.</span></span>

    [<span data-ttu-id="39980-267">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-267">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_f9e7959b-75d0-4d63-8f8e-02334a8dd09d'); "Copy to clipboard.")

        Add-PswaAuthorizationRule -UserName <domain\user | computer\user> -ComputerName <computer_name> -ConfigurationName <session_configuration_name>

    <span data-ttu-id="39980-268">この承認規則により、特定のユーザー 1 人が、通常アクセスが許可されているネットワーク上の 1 つのコンピューターにアクセスして、このユーザーが通常必要とするスクリプトとコマンドレットに制限された特定の 1 つのセッション構成にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="39980-268">This authorization rule allows a specific user access to one computer on the network to which they typically have access, with access to a specific session configuration that is scoped to the user’s typical scripting and cmdlet needs.</span></span> <span data-ttu-id="39980-269">次の例では、<span class="code">Contoso</span> ドメインの <span class="code">JSmith</span> というユーザーに、<span class="code">Contoso_214</span> というコンピューターを管理し、<span class="code">NewAdminsOnly</span> というセッション構成を使うためのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="39980-269">In the following example, a user named <span class="code">JSmith</span> in the <span class="code">Contoso</span> domain is granted access to manage the computer <span class="code">Contoso_214</span>, and use a session configuration named <span class="code">NewAdminsOnly</span>.</span></span>

    [<span data-ttu-id="39980-270">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-270">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_ebd5bc5e-ec5d-4955-a86a-63843e480e37'); "Copy to clipboard.")

        Add-PswaAuthorizationRule -UserName Contoso\JSmith -ComputerName Contoso_214 -ConfigurationName NewAdminsOnly

4.  <span data-ttu-id="39980-271">**Get-PswaAuthorizationRule** コマンドレットまたは **Test-PswaAuthorizationRule -UserName &lt;domain\\user | computer\\user&gt; -ComputerName** &lt;computer_name&gt; を実行して、規則が作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="39980-271">Verify that the rule has been created by running either the **Get-PswaAuthorizationRule** cmdlet, or **Test-PswaAuthorizationRule -UserName &lt;domain\\user | computer\\user&gt; -ComputerName** &lt;computer_name&gt;.</span></span> <span data-ttu-id="39980-272">例: **Test-PswaAuthorizationRule -UserName Contoso\\JSmith -ComputerName Contoso_214**。</span><span class="sxs-lookup"><span data-stu-id="39980-272">For example, **Test-PswaAuthorizationRule -UserName Contoso\\JSmith -ComputerName Contoso_214**.</span></span>

<span data-ttu-id="39980-273">承認規則が構成されたため、承認されたユーザーは Web ベースのコンソールにサインインして Windows PowerShell Web Access の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="39980-273">After you have configured an authorization rule, you are ready for authorized users to sign in to the web-based console and begin using Windows PowerShell Web Access.</span></span>

<a href="" id="BKMK_custom"></a>

<span data-ttu-id="39980-274"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">カスタム デプロイ</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_3" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="39980-274"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Custom deployment</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_3" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-275">Windows PowerShell Web Access ゲートウェイは、サーバー マネージャーの役割および機能の追加ウィザードを使用して、Windows Server 2012 R2 または Windows Server 2012 を実行中のサーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="39980-275">You can install the Windows PowerShell Web Access gateway on a server that is running Windows Server 2012 R2 or Windows Server 2012 by using the Add Roles and Features Wizard in Server Manager.</span></span> <span data-ttu-id="39980-276">Windows PowerShell Web Access をインストールした後、IIS Manager でゲートウェイの構成をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="39980-276">After Windows PowerShell Web Access is installed, you can customize the configuration of the gateway in IIS Manager.</span></span>

<a href="" id="BKMK_custom1"></a>
###

<span data-ttu-id="39980-277"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 1: Windows PowerShell Web Access をインストールする</span></a></span><span class="sxs-lookup"><span data-stu-id="39980-277"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 1: Install Windows PowerShell Web Access</span></a></span></span>

------------------------------------------------------------------------

#### <a name="to-install-windows-powershell-web-access-by-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="39980-278">役割と機能の追加ウィザードを使って Windows PowerShell Web Access をインストールするには</span><span class="sxs-lookup"><span data-stu-id="39980-278">To install Windows PowerShell Web Access by using the Add Roles and Features Wizard</span></span>

1.  <span data-ttu-id="39980-279">サーバー マネージャーを既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="39980-279">If Server Manager is already open, go on to the next step.</span></span> <span data-ttu-id="39980-280">サーバー マネージャーをまだ開いていない場合は、次のいずれかの方法で開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-280">If Server Manager is not already open, open it by doing one of the following.</span></span>

    -   <span data-ttu-id="39980-281">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="39980-281">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span>

    -   <span data-ttu-id="39980-282">Windows の**スタート**画面で、**[サーバー マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-282">On the Windows **Start** screen, click **Server Manager**.</span></span>

2.  <span data-ttu-id="39980-283">**[管理]** メニューの **[役割と機能の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-283">On the **Manage** menu, click **Add Roles and Features**.</span></span>

3.  <span data-ttu-id="39980-284">**[インストールの種類の選択]** ページで **[役割ベースまたは機能ベースのインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-284">On the **Select installation type** page, select **Role-based or feature-based installation**.</span></span> <span data-ttu-id="39980-285">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-285">Click **Next**.</span></span>

4.  <span data-ttu-id="39980-286">**[対象サーバーの選択]** ページで、サーバー プールからサーバーを選択するか、オフライン VHD を選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-286">On the **Select destination server** page, select a server from the server pool, or select an offline VHD.</span></span> <span data-ttu-id="39980-287">対象サーバーとしてオフライン VHD を選択するには、まず VHD マウント先のサーバーを選択してから、VHD ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-287">To select an offline VHD as your destination server, first select the server on which to mount the VHD, and then select the VHD file.</span></span> <span data-ttu-id="39980-288">サーバーをサーバー プールに追加する方法については、サーバー マネージャーのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-288">For information about how to add servers to your server pool, see the Server Manager Help.</span></span> <span data-ttu-id="39980-289">対象サーバーを選択したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-289">After you have selected the destination server, click **Next**.</span></span>

5.  <span data-ttu-id="39980-290">ウィザードの **[機能の選択]** ページで **[Windows PowerShell]** を展開し、**[Windows PowerShell Web Access]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-290">On the **Select features** page of the wizard, expand **Windows PowerShell**, and then select **Windows PowerShell Web Access**.</span></span>

6.  <span data-ttu-id="39980-291">.NET Framework 4.5 や Web サーバー (IIS) の役割サービスなど、必要な機能の追加を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39980-291">Note that you are prompted to add required features, such as .NET Framework 4.5, and role services of Web Server (IIS).</span></span> <span data-ttu-id="39980-292">必要な機能を追加して続行します。</span><span class="sxs-lookup"><span data-stu-id="39980-292">Add required features and continue.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="39980-293"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="39980-293"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="39980-294">Windows PowerShell Web Access を使って役割および機能の追加ウィザードをインストールすると、IIS マネージャー スナップインを含む Web サーバー (IIS) もインストールされます。</span><span class="sxs-lookup"><span data-stu-id="39980-294">Installing Windows PowerShell Web Access by using the Add Roles and Features Wizard also installs Web Server (IIS), including the IIS Manager snap-in.</span></span> <span data-ttu-id="39980-295">このスナップインとその他の IIS 管理ツールは、役割および機能の追加ウィザードを使う場合に既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="39980-295">The snap-in and other IIS management tools are installed by default if you use Add Roles and Features Wizard.</span></span> <span data-ttu-id="39980-296">後の手順で説明する Windows PowerShell コマンドレットを使って Windows PowerShell Web Access をインストールする場合、これらの管理ツールは既定では追加されません。</span><span class="sxs-lookup"><span data-stu-id="39980-296">If you install Windows PowerShell Web Access by using Windows PowerShell cmdlets as described in the following procedure, management tools are not added by default.</span></span></p></td>
    </tr>
    </tbody>
    </table>

7.  <span data-ttu-id="39980-297">**[インストール オプションの確認]** ページで、手順 4. で選択した対象サーバーに Windows PowerShell Web Access の機能のファイルが保存されていない場合、**[代替ソース パスの指定]** をクリックして機能ファイルのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="39980-297">On the **Confirm installation selections** page, if the feature files for Windows PowerShell Web Access are not stored on the destination server that you selected in step 4, click **Specify an alternate source path**, and provide the path to the feature files.</span></span> <span data-ttu-id="39980-298">それ以外の場合、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-298">Otherwise, click **Install**.</span></span>

8.  <span data-ttu-id="39980-299">**[インストール]** をクリックすると、**[インストールの進行状況]** ページには、インストールの進行状況、結果、メッセージ (警告、エラー、Windows PowerShell Web Access に必要なインストール後の構成手順など) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39980-299">After you click **Install**, the **Installation progress** page displays installation progress, results, and messages such as warnings, failures, or post-installation configuration steps that are required for Windows PowerShell Web Access.</span></span> <span data-ttu-id="39980-300">Windows PowerShell Web Access がインストールされると、基本的かつ必須のゲートウェイ セットアップ手順を記載した Readme ファイルの確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39980-300">After Windows PowerShell Web Access is installed, you are prompted to review the readme file, which contains basic, required setup instructions for the gateway.</span></span> <span data-ttu-id="39980-301">これらの手順も、このドキュメントで説明しています。</span><span class="sxs-lookup"><span data-stu-id="39980-301">These instructions are also included in this topic.</span></span> <span data-ttu-id="39980-302">Readme ファイルのパスは <span class="computerOutputInline">C:\\Windows\\Web\\PowerShellWebAccess\\wwwroot\\README.txt</span> です。</span><span class="sxs-lookup"><span data-stu-id="39980-302">The path to the readme file is <span class="computerOutputInline">C:\\Windows\\Web\\PowerShellWebAccess\\wwwroot\\README.txt</span>.</span></span>

###

<span data-ttu-id="39980-303"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 2: ゲートウェイを構成する</span></a></span><span class="sxs-lookup"><span data-stu-id="39980-303"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 2: Configure the gateway</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-304">このセクションの手順は、Windows PowerShell Web Access の Web アプリケーションを Web サイトのルート ディレクトリではなくサブディレクトリにインストールするための手順です。</span><span class="sxs-lookup"><span data-stu-id="39980-304">Instructions in this section are for installing the Windows PowerShell Web Access web application in a subdirectory—and not in the root directory—of your website.</span></span> <span data-ttu-id="39980-305">この手順では、<span class="code">Install-PswaWebApplication</span> コマンドレットで実行する操作に相当する内容を GUI ベースで実行しています。</span><span class="sxs-lookup"><span data-stu-id="39980-305">This procedure is the GUI-based equivalent of the actions performed by the <span class="code">Install-PswaWebApplication</span> cmdlet.</span></span> <span data-ttu-id="39980-306">さらにこのセクションでは、IIS マネージャーを使って Windows PowerShell Web Access ゲートウェイをルート Web サイトとして構成するための手順も説明します。</span><span class="sxs-lookup"><span data-stu-id="39980-306">This section also includes instructions for how to use IIS Manager to configure the Windows PowerShell Web Access gateway as a root website.</span></span>

-   [<span data-ttu-id="39980-307">IIS マネージャーを使って既存の Web サイトにゲートウェイを構成するには</span><span class="sxs-lookup"><span data-stu-id="39980-307">To use IIS Manager to configure the gateway in an existing website</span></span>](#BKMK_configman)

-   [<span data-ttu-id="39980-308">IIS マネージャーを使用してテスト証明書を持つゲートウェイをルート Web サイトとして構成するには</span><span class="sxs-lookup"><span data-stu-id="39980-308">To use IIS Manager to configure the gateway as a root website with a test certificate</span></span>](#BKMK_configroot)

-   

#### <a name="to-use-iis-manager-to-configure-the-gateway-in-an-existing-website"></a><span data-ttu-id="39980-309">IIS マネージャーを使って既存の Web サイトにゲートウェイを構成するには</span><span class="sxs-lookup"><span data-stu-id="39980-309">To use IIS Manager to configure the gateway in an existing website</span></span>

1.  <span data-ttu-id="39980-310">次のいずれかの方法で IIS マネージャー コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-310">Open the IIS Manager console by doing one of the following.</span></span>

    -   <span data-ttu-id="39980-311">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="39980-311">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span> <span data-ttu-id="39980-312">[サーバー マネージャー] の **[ツール]** メニューで **[インターネット インフォメーション サービス (IIS) マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-312">On the **Tools** menu in Server Manager, click **Internet Information Services (IIS) Manager**.</span></span>

    -   <span data-ttu-id="39980-313">Windows の**スタート**画面で、**インターネット インフォメーション サービス (IIS) マネージャー**という名前の任意の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="39980-313">On the Windows **Start** screen, type any part of the name **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="39980-314">**[アプリ]** の結果に表示されたショートカットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-314">Click the shortcut when it is displayed in the **Apps** results.</span></span>

2.  <span data-ttu-id="39980-315">Windows PowerShell Web Access 用の新しいアプリケーション プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="39980-315">Create a new application pool for Windows PowerShell Web Access.</span></span> <span data-ttu-id="39980-316">IIS マネージャーのツリー ウィンドウでゲートウェイ サーバーのノードを展開して、**[アプリケーション プール]** を選択し、**[操作]** ウィンドウの **[アプリケーション プールの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-316">Expand the node of the gateway server in the IIS Manager tree pane, select **Application Pools**, and click **Add Application Pool** in the **Actions** pane.</span></span>

3.  <span data-ttu-id="39980-317">新しいアプリケーション プールを **pswa_pool** という名前で追加するか、別の名前を指定して追加します。</span><span class="sxs-lookup"><span data-stu-id="39980-317">Add a new application pool with the name **pswa_pool**, or provide another name.</span></span> <span data-ttu-id="39980-318">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-318">Click **OK**.</span></span>

4.  <span data-ttu-id="39980-319">IIS マネージャーのツリー ウィンドウで、Windows PowerShell Web Access がインストールされているサーバーのノードを展開し、**[サイト]** フォルダーを表示させます。</span><span class="sxs-lookup"><span data-stu-id="39980-319">In the IIS Manager tree pane, expand the node for the server on which Windows PowerShell Web Access is installed until the **Sites** folder is visible.</span></span> <span data-ttu-id="39980-320">**[サイト]** フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-320">Select the **Sites** folder.</span></span>

5.  <span data-ttu-id="39980-321">Windows PowerShell Web Access の Web サイトの追加先となる Web サイト (**[既定の Web サイト]** など) を右クリックして、**[アプリケーションの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-321">Right-click the website (for example, **Default Web Site**) to which you would like to add the Windows PowerShell Web Access website, and then click **Add Application**.</span></span>

6.  <span data-ttu-id="39980-322">**"エイリアス"** フィールドに「pswa」と入力するか、別のエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="39980-322">In the **Alias** field, type pswa, or provide another alias.</span></span> <span data-ttu-id="39980-323">このエイリアスが仮想ディレクトリ名となります。</span><span class="sxs-lookup"><span data-stu-id="39980-323">The alias becomes the virtual directory name.</span></span> <span data-ttu-id="39980-324">たとえば、次の URL の **pswa** は、この手順で指定されたエイリアスを表します。https://&lt;server_name&gt;/pswa</span><span class="sxs-lookup"><span data-stu-id="39980-324">For example, **pswa** in the following URL represents the alias specified in this step: https://&lt;server_name&gt;/pswa.</span></span>

7.  <span data-ttu-id="39980-325">**"アプリケーション プール"** フィールドで、手順 3. で作成したアプリケーション プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-325">In the **Application pool** field, select the application pool that you created in step 3.</span></span>

8.  <span data-ttu-id="39980-326">**"物理パス"** フィールドで、アプリケーションの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="39980-326">In the **Physical path** field, browse for the location of the application.</span></span> <span data-ttu-id="39980-327">既定の場所 (%windir%/Web/PowerShellWebAccess/wwwroot) を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="39980-327">You can use the default location, %windir%/Web/PowerShellWebAccess/wwwroot.</span></span> <span data-ttu-id="39980-328">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-328">Click **OK**.</span></span>

9.  <span data-ttu-id="39980-329">このトピックの「 [IIS マネージャーで SSL 証明書を構成するには](#BKMK_cert) 」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="39980-329">Follow the steps in the procedure [To configure an SSL certificate in IIS Manager](#BKMK_cert) in this topic.</span></span>

10. <span data-ttu-id="39980-330"><span class="label">セキュリティに関する手順 (オプション):</span> ツリー ウィンドウで Web サイトが選択された状態で、コンテンツ ウィンドウの **[SSL 設定]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-330"><span class="label">Optional security step:</span> With the website selected in the tree pane, double-click **SSL Settings** in the content pane.</span></span> <span data-ttu-id="39980-331">**[SSL が必要]** を選択して、**[操作]** ウィンドウで **[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-331">Select **Require SSL**, and then in the **Actions** pane, click **Apply**.</span></span> <span data-ttu-id="39980-332">必要に応じて、**[SSL 設定]** ウィンドウを使って、Windows PowerShell Web Access の Web サイトに接続するユーザーに対してクライアント証明書の所有を要求できます。</span><span class="sxs-lookup"><span data-stu-id="39980-332">Optionally, in the **SSL Settings** pane, you can require that users connecting to the Windows PowerShell Web Access website have client certificates.</span></span> <span data-ttu-id="39980-333">クライアント証明書により、クライアント デバイスのユーザーの ID を検証できます。</span><span class="sxs-lookup"><span data-stu-id="39980-333">Client certificates help to verify the identity of a client device user.</span></span> <span data-ttu-id="39980-334">クライアント証明書の要求によって Windows PowerShell Web Access のセキュリティを強化する方法の詳細については、このトピックの「[Windows PowerShell Web Access の承認規則とセキュリティ機能](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-334">For more information about how requiring client certificates can increase the security of Windows PowerShell Web Access, see [Authorization Rules and Security Features of Windows PowerShell Web Access](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx) in this guide.</span></span>

11. <span data-ttu-id="39980-335">クライアント デバイスでブラウザー セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-335">Open a browser session on a client device.</span></span> <span data-ttu-id="39980-336">サポートされるブラウザーとデバイスの詳細については、このトピックの「[ブラウザーとクライアント デバイスのサポート](#BKMK_browser)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-336">For more information about supported browsers and devices, see [Browser and client device support](#BKMK_browser) in this topic.</span></span>

12. <span data-ttu-id="39980-337">新しい Windows PowerShell Web Access Web サイト https://&lt;*gateway_server_name*&gt;/pswa を開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-337">Open the new Windows PowerShell Web Access website, https://&lt; *gateway_server_name*&gt;/pswa.</span></span>

    <span data-ttu-id="39980-338">ブラウザーには Windows PowerShell Web Access コンソールのサインイン ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39980-338">The browser should display the Windows PowerShell Web Access console sign-in page.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="39980-339"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="39980-339"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="39980-340">サインインできるのは、承認規則の追加によって Web サイトへのアクセスが許可されたユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="39980-340">You cannot sign in until users have been granted access to the website by adding authorization rules.</span></span></p></td>
    </tr>
    </tbody>
    </table>

13. <span data-ttu-id="39980-341">管理者特権で開かれた ([管理者として実行]) Windows PowerShell セッションで、次のスクリプトを実行します。*application_pool_name* は、手順 3. で作成したアプリケーション プールの名前です。これによって承認ファイルへのアクセス権がアプリケーション プールに付与されます。</span><span class="sxs-lookup"><span data-stu-id="39980-341">In a Windows PowerShell session that has been opened with elevated user rights (Run as Administrator), run the following script, in which *application_pool_name* represents the name of the application pool that you created in step 3, to give the application pool access rights to the authorization file.</span></span>

    [<span data-ttu-id="39980-342">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-342">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_c1a80a93-8fcf-4beb-a025-5f81bfb8bdae'); "Copy to clipboard.")

        $applicationPoolName = "<application_pool_name>"
        $authorizationFile = "C:\windows\web\powershellwebaccess\data\AuthorizationRules.xml"
        c:\windows\system32\icacls.exe $authorizationFile /grant ('"' + "IIS AppPool\$applicationPoolName" + '":R') > $null

    <span data-ttu-id="39980-343">承認ファイルに対する既存のアクセス権を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="39980-343">To view existing access rights on the authorization file, run the following command:</span></span>

    [<span data-ttu-id="39980-344">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-344">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_ac2179c2-9548-4a17-8663-267fdd105380'); "Copy to clipboard.")

        c:\windows\system32\icacls.exe $authorizationFile

#### <a name="to-use-iis-manager-to-configure-the-gateway-as-a-root-website-with-a-test-certificate"></a><span data-ttu-id="39980-345">IIS マネージャーを使用してテスト証明書を持つゲートウェイをルート Web サイトとして構成するには</span><span class="sxs-lookup"><span data-stu-id="39980-345">To use IIS Manager to configure the gateway as a root website with a test certificate</span></span>

1.  <span data-ttu-id="39980-346">次のいずれかの方法で IIS マネージャー コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-346">Open the IIS Manager console by doing one of the following.</span></span>

    -   <span data-ttu-id="39980-347">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="39980-347">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span> <span data-ttu-id="39980-348">[サーバー マネージャー] の **[ツール]** メニューで **[インターネット インフォメーション サービス (IIS) マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-348">On the **Tools** menu in Server Manager, click **Internet Information Services (IIS) Manager**.</span></span>

    -   <span data-ttu-id="39980-349">Windows の**スタート**画面で、**インターネット インフォメーション サービス (IIS) マネージャー**という名前の任意の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="39980-349">On the Windows **Start** screen, type any part of the name **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="39980-350">**[アプリ]** の結果に表示されたショートカットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-350">Click the shortcut when it is displayed in the **Apps** results.</span></span>

2.  <span data-ttu-id="39980-351">IIS マネージャーのツリー ウィンドウで、Windows PowerShell Web Access がインストールされているサーバーのノードを展開し、**[サイト]** フォルダーを表示させます。</span><span class="sxs-lookup"><span data-stu-id="39980-351">In the IIS Manager tree pane, expand the node for the server on which Windows PowerShell Web Access is installed until the **Sites** folder is visible.</span></span> <span data-ttu-id="39980-352">**[サイト]** フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-352">Select the **Sites** folder.</span></span>

3.  <span data-ttu-id="39980-353">**[操作]** ウィンドウで **[Web サイトの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-353">In the **Actions** pane, click **Add Website**.</span></span>

4.  <span data-ttu-id="39980-354">Web サイトの名前 (**Windows PowerShell Web Access** など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="39980-354">Type a name for the website, such as **Windows PowerShell Web Access**.</span></span>

5.  <span data-ttu-id="39980-355">新しい Web サイト用のアプリケーション プールが自動で作成されます。</span><span class="sxs-lookup"><span data-stu-id="39980-355">An application pool is automatically created for the new website.</span></span> <span data-ttu-id="39980-356">別のアプリケーション プールを使うには、**[選択]** をクリックして、新しい Web サイトに関連付けるアプリケーション プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-356">To use a different application pool, click **Select** to select an application pool to associate with the new website.</span></span> <span data-ttu-id="39980-357">**[アプリケーション プールの選択]** ダイアログ ボックスで別のアプリケーション プールを選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-357">Select the alternate application pool in the **Select Application Pool** dialog box, and then click **OK**.</span></span>

6.  <span data-ttu-id="39980-358">**[物理パス]** テキスト ボックスで、%*windir*%/Web/PowerShellWebAccess/wwwroot に移動します。</span><span class="sxs-lookup"><span data-stu-id="39980-358">In the **Physical path** text box, navigate to %*windir*%/Web/PowerShellWebAccess/wwwroot.</span></span>

7.  <span data-ttu-id="39980-359">**[バインド]** 領域の **[種類]** フィールドで、**[https]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-359">In the **Type** field of the **Binding** area, select **https**.</span></span>

8.  <span data-ttu-id="39980-360">別のサイトまたはアプリケーションがまだ使っていないポート番号を Web サイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="39980-360">Assign a port number to the website that is not already in use by another site or application.</span></span> <span data-ttu-id="39980-361">未使用のポートを調べるには、コマンド プロンプト ウィンドウで **netstat** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="39980-361">To locate open ports, you can run the **netstat** command in a Command Prompt window.</span></span> <span data-ttu-id="39980-362">既定のポート番号は 443 です。</span><span class="sxs-lookup"><span data-stu-id="39980-362">The default port number is 443.</span></span>

    <span data-ttu-id="39980-363">別の Web サイトが既に 443 を使っている場合、またはポート番号を変更するセキュリティ上の理由がある場合は、既定のポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="39980-363">Change the default port if another website is already using 443, or if you have other security reasons for changing the port number.</span></span> <span data-ttu-id="39980-364">選択したポートを、ゲートウェイ サーバー上で実行されている別の Web サイトが使っている場合は、**[Web サイトの追加]** ダイアログ ボックスで **[OK]** をクリックすると警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39980-364">If another website that is running on your gateway server is using your selected port, a warning is displayed when you click **OK** in the **Add Website** dialog box.</span></span> <span data-ttu-id="39980-365">Windows PowerShell Web Access を実行するには未使用のポートを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="39980-365">You must use an unused port to run Windows PowerShell Web Access.</span></span>

9.  <span data-ttu-id="39980-366">組織の必要に応じて、組織またはユーザーがわかりやすいホスト名を指定します (**www.contoso.com** など)。</span><span class="sxs-lookup"><span data-stu-id="39980-366">Optionally, if needed for your organization, specify a host name that makes sense to your organization and users, such as **www.contoso.com**.</span></span> <span data-ttu-id="39980-367">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-367">Click **OK**.</span></span>

10. <span data-ttu-id="39980-368">運用環境のセキュリティ保護を強化するため、CA によって署名された有効な証明書を提供することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39980-368">For a more secure production environment, we strongly recommend providing a valid certificate that has been signed by a CA.</span></span> <span data-ttu-id="39980-369">ユーザーは HTTPS Web サイトを経由しないと Windows PowerShell Web Access に接続できないため、SSL 証明書は必ず提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39980-369">You must provide an SSL certificate, because users can only connect to Windows PowerShell Web Access through an HTTPS website.</span></span> <span data-ttu-id="39980-370">証明書の取得方法の詳細については、このトピックの「[IIS マネージャーで SSL 証明書を構成するには](#BKMK_cert)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-370">See [To configure an SSL certificate in IIS Manager](#BKMK_cert) in this topic for more information about how to obtain a certificate.</span></span>

11. <span data-ttu-id="39980-371">**[OK]** をクリックして **[Web サイトの追加]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="39980-371">Click **OK** to close the **Add Website** dialog box.</span></span>

12. <span data-ttu-id="39980-372">管理者特権で開かれた ([管理者として実行]) Windows PowerShell セッションで、次のスクリプトを実行します。*application_pool_name* は、手順 4. で作成したアプリケーション プールの名前です。これによって承認ファイルへのアクセス権がアプリケーション プールに付与されます。</span><span class="sxs-lookup"><span data-stu-id="39980-372">In a Windows PowerShell session that has been opened with elevated user rights (Run as Administrator), run the following script, in which *application_pool_name* represents the name of the application pool that you created in step 4, to give the application pool access rights to the authorization file.</span></span>

    [<span data-ttu-id="39980-373">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-373">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_35ae9944-ca44-4af7-9c96-616083b3e3db'); "Copy to clipboard.")

        $applicationPoolName = "<application_pool_name>"
        $authorizationFile = "C:\windows\web\powershellwebaccess\data\AuthorizationRules.xml"
        c:\windows\system32\icacls.exe $authorizationFile /grant ('"' + "IIS AppPool\$applicationPoolName" + '":R') > $null

    <span data-ttu-id="39980-374">承認ファイルに対する既存のアクセス権を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="39980-374">To view existing access rights on the authorization file, run the following command:</span></span>

    [<span data-ttu-id="39980-375">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-375">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_0eb6d70a-2807-498b-b088-fa5233ed68d5'); "Copy to clipboard.")

        c:\windows\system32\icacls.exe $authorizationFile

13. <span data-ttu-id="39980-376">IIS マネージャーのツリー ウィンドウで新しい Web サイトが選択された状態で、**[操作]** ウィンドウの **[開始]** をクリックすると、Web サイトが開設されます。</span><span class="sxs-lookup"><span data-stu-id="39980-376">With the new website selected in the IIS Manager tree pane, click **Start** in the **Actions** pane to start the website.</span></span>

14. <span data-ttu-id="39980-377">クライアント デバイスでブラウザー セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-377">Open a browser session on a client device.</span></span> <span data-ttu-id="39980-378">サポートされるブラウザーとデバイスの詳細については、このドキュメントの「[ブラウザーとクライアント デバイスのサポート](#BKMK_browser)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-378">For more information about supported browsers and devices, see [Browser and client device support](#BKMK_browser) in this document.</span></span>

15. <span data-ttu-id="39980-379">新しい Windows PowerShell Web Access の Web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-379">Open the new Windows PowerShell Web Access website.</span></span>

    <span data-ttu-id="39980-380">ルート Web サイトは Windows PowerShell Web Access フォルダーを参照しているため、https://&lt;*gateway_server_name*&gt; を開くと、ブラウザーには Windows PowerShell Web Access のサインイン ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39980-380">Because the root website points to the Windows PowerShell Web Access folder, the browser should display the Windows PowerShell Web Access sign-in page when you open https://&lt; *gateway_server_name*&gt;.</span></span> <span data-ttu-id="39980-381">URL に **/pswa** を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="39980-381">You should not need to add **/pswa** to the URL.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="39980-382"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="39980-382"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="39980-383">サインインできるのは、承認規則の追加によって Web サイトへのアクセスが許可されたユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="39980-383">You cannot sign in until users have been granted access to the website by adding authorization rules.</span></span></p></td>
    </tr>
    </tbody>
    </table>

###

<span data-ttu-id="39980-384"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 3: 制限的な承認規則を構成する</span></a></span><span class="sxs-lookup"><span data-stu-id="39980-384"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 3: Configure a restrictive authorization rule</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-385">Windows PowerShell Web Access をインストールし、ゲートウェイを構成すると、ユーザーがブラウザーでサインイン ページを開けるようになります。ただし、Windows PowerShell Web Access 管理者によってアクセスを明示的に許可されない限りサインインできません。</span><span class="sxs-lookup"><span data-stu-id="39980-385">After Windows PowerShell Web Access is installed and the gateway is configured, users can open the sign-in page in a browser, but they cannot sign in until the Windows PowerShell Web Access administrator grants users access explicitly.</span></span> <span data-ttu-id="39980-386">Windows PowerShell Web Access のアクセス制御は、次の表に示す一連の Windows PowerShell コマンドレットによって管理します。</span><span class="sxs-lookup"><span data-stu-id="39980-386">Windows PowerShell Web Access access control is managed by using the set of Windows PowerShell cmdlets described in the following table.</span></span> <span data-ttu-id="39980-387">承認規則の追加と管理に関しては、相当する GUI はありません。</span><span class="sxs-lookup"><span data-stu-id="39980-387">There is no comparable GUI for adding or managing authorization rules.</span></span> <span data-ttu-id="39980-388">Windows PowerShell Web Access コマンドレットの詳細については、コマンドレット リファレンス トピック「[Windows PowerShell Web Access Cmdlets](https://technet.microsoft.com/library/hh918342.aspx)」(Windows PowerShell Web Access コマンドレット) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-388">For more detailed information about Windows PowerShell Web Access cmdlets, see the cmdlet reference topics, [Windows PowerShell Web Access Cmdlets](https://technet.microsoft.com/library/hh918342.aspx).</span></span>

<span data-ttu-id="39980-389">Windows PowerShell Web Access の承認規則とセキュリティの詳細については、「[Windows PowerShell Web Access の承認規則とセキュリティ機能](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-389">For more detail about Windows PowerShell Web Access authorization rules and security, see [Authorization Rules and Security Features of Windows PowerShell Web Access](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx).</span></span>

#### <a name="to-add-a-restrictive-authorization-rule"></a><span data-ttu-id="39980-390">制限的な承認規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="39980-390">To add a restrictive authorization rule</span></span>

1.  <span data-ttu-id="39980-391">次のいずれかを実行して、管理者特権を使って Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="39980-391">Do one of the following to open a Windows PowerShell session with elevated user rights.</span></span>

    -   <span data-ttu-id="39980-392">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-392">On the Windows desktop, right-click **Windows PowerShell** on the taskbar, and then click **Run as Administrator**.</span></span>

    -   <span data-ttu-id="39980-393">Windows の**スタート**画面で、**[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-393">On the Windows **Start** screen, right-click **Windows PowerShell**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="39980-394"><span class="label">セッション構成を使用してユーザー アクセスを制限するためのオプション手順:</span> 規則内で使用するセッション構成が既に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="39980-394"><span class="label">Optional step for restricting user access by using session configurations:</span> Verify that session configurations that you want to use in your rules already exist.</span></span> <span data-ttu-id="39980-395">まだ作成されていない場合は、MSDN の「[about_Session_Configuration_Files](https://msdn.microsoft.com/library/windows/desktop/hh847838.aspx)」に記載されているセッション構成の作成手順を使用してください。</span><span class="sxs-lookup"><span data-stu-id="39980-395">If they have not yet been created, use instructions for creating session configurations in [about_Session_Configuration_Files](https://msdn.microsoft.com/library/windows/desktop/hh847838.aspx) on MSDN.</span></span>

3.  <span data-ttu-id="39980-396">次のように入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="39980-396">Type the following, and then press **Enter**.</span></span>

    [<span data-ttu-id="39980-397">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-397">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_4df22c91-f56f-4bb5-91e7-99f9b365ed5d'); "Copy to clipboard.")

        Add-PswaAuthorizationRule -UserName <domain\user | computer\user> -ComputerName <computer_name> -ConfigurationName <session_configuration_name>

    <span data-ttu-id="39980-398">この承認規則により、特定のユーザー 1 人が、通常アクセスが許可されているネットワーク上の 1 つのコンピューターにアクセスして、このユーザーが通常必要とするスクリプトとコマンドレットに制限された特定の 1 つのセッション構成にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="39980-398">This authorization rule allows a specific user access to one computer on the network to which they typically have access, with access to a specific session configuration that is scoped to the user’s typical scripting and cmdlet needs.</span></span> <span data-ttu-id="39980-399">次の例では、<span class="code">Contoso</span> ドメインの <span class="code">JSmith</span> というユーザーに、<span class="code">Contoso_214</span> というコンピューターを管理し、<span class="code">NewAdminsOnly</span> というセッション構成を使うためのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="39980-399">In the following example, a user named <span class="code">JSmith</span> in the <span class="code">Contoso</span> domain is granted access to manage the computer <span class="code">Contoso_214</span>, and use a session configuration named <span class="code">NewAdminsOnly</span>.</span></span>

    [<span data-ttu-id="39980-400">Copy</span><span class="sxs-lookup"><span data-stu-id="39980-400">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_efc3999a-2905-453f-86cd-014b41658ffc'); "Copy to clipboard.")

        Add-PswaAuthorizationRule -UserName Contoso\JSmith -ComputerName Contoso_214 -ConfigurationName NewAdminsOnly

4.  <span data-ttu-id="39980-401">**Get-PswaAuthorizationRule** コマンドレットまたは **Test-PswaAuthorizationRule -UserName &lt;domain\\user | computer\\user&gt; -ComputerName** &lt;computer_name&gt; を実行して、規則が作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="39980-401">Verify that the rule has been created by running either the **Get-PswaAuthorizationRule** cmdlet, or **Test-PswaAuthorizationRule -UserName &lt;domain\\user | computer\\user&gt; -ComputerName** &lt;computer_name&gt;.</span></span> <span data-ttu-id="39980-402">例: **Test-PswaAuthorizationRule -UserName Contoso\\JSmith -ComputerName Contoso_214**。</span><span class="sxs-lookup"><span data-stu-id="39980-402">For example, **Test-PswaAuthorizationRule -UserName Contoso\\JSmith -ComputerName Contoso_214**.</span></span>

<span data-ttu-id="39980-403">承認規則が構成されたため、承認されたユーザーは Web ベースのコンソールにサインインして Windows PowerShell Web Access の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="39980-403">After you have configured an authorization rule, you are ready for authorized users to sign in to the web-based console and begin using Windows PowerShell Web Access.</span></span>

<a href="" id="BKMK_configcert"></a>

<span data-ttu-id="39980-404"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">正規の証明書を構成する</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_4" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="39980-404"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Configure a genuine certificate</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_4" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-405">運用環境のセキュリティ保護のため、証明機関 (CA) によって署名されている有効な SSL 証明書を常に使用してください。</span><span class="sxs-lookup"><span data-stu-id="39980-405">For a secure production environment, always use a valid SSL certificate that has been signed by a certification authority (CA).</span></span> <span data-ttu-id="39980-406">このセクションの手順では、有効な SSL 証明書を CA から取得して適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39980-406">The procedure in this section describes how to obtain and apply a valid SSL certificate from a CA.</span></span>

### <a name="to-configure-an-ssl-certificate-in-iis-manager"></a><span data-ttu-id="39980-407">IIS マネージャーで SSL 証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="39980-407">To configure an SSL certificate in IIS Manager</span></span>

1.  <span data-ttu-id="39980-408">IIS マネージャーのツリー ウィンドウで、Windows PowerShell Web Access がインストールされているサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="39980-408">In the IIS Manager tree pane, select the server on which Windows PowerShell Web Access is installed.</span></span>

2.  <span data-ttu-id="39980-409">コンテンツ ウィンドウで **[サーバー証明書]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-409">In the content pane, double click **Server Certificates**.</span></span>

3.  <span data-ttu-id="39980-410">**[操作]** ウィンドウで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="39980-410">In the **Actions** pane, do one of the following.</span></span> <span data-ttu-id="39980-411">IIS でサーバー証明書を構成する方法の詳細については、「[IIS 7 でサーバー証明書を構成する](https://technet.microsoft.com/library/cc732230.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-411">For more information about configuring server certificates in IIS, see [Configuring Server Certificates in IIS 7](https://technet.microsoft.com/library/cc732230.aspx).</span></span>

    -   <span data-ttu-id="39980-412">**[インポート]** をクリックして、ネットワーク内の場所にある既存の有効な証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="39980-412">Click **Import** to import an existing, valid certificate from a location on your network.</span></span>

    -   <span data-ttu-id="39980-413">**[証明書の要求の作成]** をクリックして、VeriSign™、Thawte、GeoTrust® などの CA に証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="39980-413">Click **Create Certificate Request** to request a certificate from a CA such as VeriSign™, Thawte, or GeoTrust®.</span></span> <span data-ttu-id="39980-414">証明書の共通名が要求のホスト ヘッダーと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="39980-414">The certificate's common name must match the host header in the request.</span></span> <span data-ttu-id="39980-415">たとえば、クライアントのブラウザーが http://www.contoso.com/ を要求する場合、共通名も http://www.contoso.com/ でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="39980-415">For example, if the client browser requests http://www.contoso.com/, then the common name must also be http://www.contoso.com/.</span></span> <span data-ttu-id="39980-416">これは、証明書を使う Windows PowerShell Web Access ゲートウェイを提供する場合に最も安全かつ推奨されるオプションです。</span><span class="sxs-lookup"><span data-stu-id="39980-416">This is the most secure and recommended option for providing the Windows PowerShell Web Access gateway with a certificate.</span></span>

    -   <span data-ttu-id="39980-417">**[自己署名証明書を作成する]** をクリックして証明書を作成します。この証明書はすぐに使うことができ、必要な場合は後でCAが署名できます。</span><span class="sxs-lookup"><span data-stu-id="39980-417">Click **Create a Self-Signed Certificate** to create a certificate that you can use immediately, and have signed later by a CA if desired.</span></span> <span data-ttu-id="39980-418">自己署名証明書にわかりやすい名前を指定します (**Windows PowerShell Web Access** など)。</span><span class="sxs-lookup"><span data-stu-id="39980-418">Specify a friendly name for the self-signed certificate, such as **Windows PowerShell Web Access**.</span></span> <span data-ttu-id="39980-419">これは、安全と見なされない、プライベートなテスト環境にのみ推奨されるオプションです。</span><span class="sxs-lookup"><span data-stu-id="39980-419">This option is not considered secure, and is recommended only for a private test environment.</span></span>

4.  <span data-ttu-id="39980-420">証明書を作成または取得した後、IIS マネージャーのツリー ウィンドウで、証明書を適用する Web サイト (**[既定の Web サイト]** など) を選択して、**[操作]** ウィンドウの **[バインド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-420">After creating or obtaining a certificate, select the website to which the certificate is applied (for example, **Default Web Site**) in the IIS Manager tree pane, and then click **Bindings** in the **Actions** pane.</span></span>

5.  <span data-ttu-id="39980-421">**[サイト バインドの追加]** ダイアログ ボックスで、サイトの **[https]** バインドを追加します (表示されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="39980-421">In the **Add Site Binding** dialog box, add an **https** binding for the site, if one is not already displayed.</span></span> <span data-ttu-id="39980-422">自己署名証明書を使っていない場合、手順 3. のホスト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="39980-422">If you are not using a self-signed certificate, specify the host name from step 3 of this procedure.</span></span> <span data-ttu-id="39980-423">自己署名証明書を使っている場合、この手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="39980-423">If you are using a self-signed certificate, this step is not required.</span></span>

6.  <span data-ttu-id="39980-424">手順 3. で取得または作成した証明書を選択して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39980-424">Select the certificate that you obtained or created in step 3 of this procedure, and then click **OK**.</span></span>

<a href="" id="BKMK_using"></a>

<span data-ttu-id="39980-425"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Web ベースの Windows PowerShell コンソールの使用</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_5" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="39980-425"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Using the web-based Windows PowerShell console</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_5" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-426">このトピックの説明に従って Windows PowerShell Web Access のインストールとゲートウェイ構成が完了したら、Web ベースの Windows PowerShell コンソールを使えるようになります。</span><span class="sxs-lookup"><span data-stu-id="39980-426">After Windows PowerShell Web Access is installed and the gateway configuration is finished as described in this topic, the Windows PowerShell web-based console is ready to use.</span></span> <span data-ttu-id="39980-427">Web ベース コンソールの概要については、「[Web ベースの Windows PowerShell コンソールの使用](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-427">For more information about getting started in the web-based console, see [Use the Web-based Windows PowerShell Console](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx).</span></span>

<span data-ttu-id="39980-428"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">関連項目</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_6" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="39980-428"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">See Also</span></a>
<a href="/en-us/library/hh831611(v=ws.11).aspx#Anchor_6" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="39980-429">[インターネット インフォメーション サービス (IIS) 7.0 のドキュメント](https://technet.microsoft.com/library/cc753433.aspx)
[IIS マネージャー 7.0 ヘルプ](https://technet.microsoft.com/library/cc732664.aspx)
[Web サーバーのセキュリティを構成する (IIS 7)](https://technet.microsoft.com/library/cc731278.aspx)
[IPsec 展開のリソース](https://technet.microsoft.com/network/bb531150)</span><span class="sxs-lookup"><span data-stu-id="39980-429">[Internet Information Services (IIS) 7.0 Documentation](https://technet.microsoft.com/library/cc753433.aspx)
[IIS Manager 7.0 Help](https://technet.microsoft.com/library/cc732664.aspx)
[Configure Web Server Security (IIS 7)](https://technet.microsoft.com/library/cc731278.aspx)
[IPsec Deployment Resources](https://technet.microsoft.com/network/bb531150)</span></span>

<span data-ttu-id="39980-430"><span>表示:</span> 継承 保護</span><span class="sxs-lookup"><span data-stu-id="39980-430"><span>Show:</span> Inherited Protected</span></span>

<span data-ttu-id="39980-431"><span class="stdr-votetitle">このページは役に立ちましたか。</span></span><span class="sxs-lookup"><span data-stu-id="39980-431"><span class="stdr-votetitle">Was this page helpful?</span></span></span>
<span data-ttu-id="39980-432">はい いいえ</span><span class="sxs-lookup"><span data-stu-id="39980-432">Yes No</span></span>

<span data-ttu-id="39980-433">その他にご意見はありますか。</span><span class="sxs-lookup"><span data-stu-id="39980-433">Additional feedback?</span></span>

<span data-ttu-id="39980-434">残り <span class="stdr-count"><span class="stdr-charcnt">1500</span> 文字</span> 送信 スキップする</span><span class="sxs-lookup"><span data-stu-id="39980-434"><span class="stdr-count"><span class="stdr-charcnt">1500</span> characters remaining</span> Submit Skip this</span></span>

<span data-ttu-id="39980-435"><span class="stdr-thankyou">ありがとうございました。</span></span><span class="sxs-lookup"><span data-stu-id="39980-435"><span class="stdr-thankyou">Thank you!</span></span></span> <span data-ttu-id="39980-436"><span class="stdr-appreciate">ご意見をお送りいただきありがとうございます。</span></span><span class="sxs-lookup"><span data-stu-id="39980-436"><span class="stdr-appreciate">We appreciate your feedback.</span></span></span>

[<span data-ttu-id="39980-437">プロファイル (個人情報) の管理</span><span class="sxs-lookup"><span data-stu-id="39980-437">Manage Your Profile</span></span>](https://social.technet.microsoft.com/profile)

|

<span data-ttu-id="39980-438"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"><img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span>サイトのフィードバック</a> サイトのフィードバック</span><span class="sxs-lookup"><span data-stu-id="39980-438"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"> <img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span> Site Feedback</a> Site Feedback</span></span>

<span data-ttu-id="39980-439"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">X</a></span><span class="sxs-lookup"><span data-stu-id="39980-439"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">x</a></span></span>

<span data-ttu-id="39980-440">お客様のご体験をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="39980-440">Tell us about your experience...</span></span>

<span data-ttu-id="39980-441">ページはすばやく表示されましたか?</span><span class="sxs-lookup"><span data-stu-id="39980-441">Did the page load quickly?</span></span>

<span data-ttu-id="39980-442"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="39980-442"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="39980-443">ページのデザインは気に入りましたか?</span><span class="sxs-lookup"><span data-stu-id="39980-443">Do you like the page design?</span></span>

<span data-ttu-id="39980-444"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="39980-444"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="39980-445">詳しくお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="39980-445">Tell us more</span></span>

-   [<span data-ttu-id="39980-446">Flash ニュースレター</span><span class="sxs-lookup"><span data-stu-id="39980-446">Flash Newsletter</span></span>](https://technet.microsoft.com/cc543196.aspx)
-   |
-   [<span data-ttu-id="39980-447">お問い合わせ先</span><span class="sxs-lookup"><span data-stu-id="39980-447">Contact Us</span></span>](https://technet.microsoft.com/cc512759.aspx)
-   |
-   [<span data-ttu-id="39980-448">プライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="39980-448">Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
-   |
-   [<span data-ttu-id="39980-449">使用条件</span><span class="sxs-lookup"><span data-stu-id="39980-449">Terms of Use</span></span>](https://technet.microsoft.com/cc300389.aspx)
-   |
-   [<span data-ttu-id="39980-450">商標</span><span class="sxs-lookup"><span data-stu-id="39980-450">Trademarks</span></span>](https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/)
-   |

<span data-ttu-id="39980-451">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="39980-451">© 2016 Microsoft</span></span>

<span data-ttu-id="39980-452">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="39980-452">© 2016 Microsoft</span></span>

<span data-ttu-id="39980-453">サードパーティのスクリプトやコード、サードパーティから本 Web サイトへのリンク、あるいは本サイトからサードパーティへのリンクは、マイクロソフトではなく、そのようなコードの所有者によってお客様にライセンス供与されています。</span><span class="sxs-lookup"><span data-stu-id="39980-453">Third party scripts and code linked to or referenced from this website are licensed to you by the parties that own such code, not by Microsoft.</span></span> <span data-ttu-id="39980-454">ASP.NET Ajax CDN の使用条件 - http://www.asp.net/ajaxlibrary/CDN.ashx を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39980-454">See ASP.NET Ajax CDN Terms of Use - http://www.asp.net/ajaxlibrary/CDN.ashx.</span></span>
<img src="https://m.webtrends.com/dcsjwb9vb00000c932fd0rjc7_5p3t/njs.gif?dcsuri=/nojavascript&amp;WT.js=No" alt="DCSIMG" id="Img1" width="1" height="1" />

