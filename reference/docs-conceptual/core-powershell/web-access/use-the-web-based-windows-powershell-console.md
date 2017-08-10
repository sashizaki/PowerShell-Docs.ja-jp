---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Web ベースの Windows PowerShell コンソールの使用"
ms.openlocfilehash: 48ed1646c00f909c4e950f197f51a30205060ef0
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
#  <a name="use-the-web-based-windows-powershell-console"></a><span data-ttu-id="fa9a7-103">Web ベースの Windows PowerShell コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="fa9a7-103">Use the Web-based Windows PowerShell Console</span></span>

<span data-ttu-id="fa9a7-104">最終更新日: 2013 年 6 月 24 日</span><span class="sxs-lookup"><span data-stu-id="fa9a7-104">Updated: June 24, 2013</span></span>

<span data-ttu-id="fa9a7-105">適用対象: Windows Server 2012 R2、Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fa9a7-105">Applies To: Windows Server 2012 R2, Windows Server 2012</span></span>

<span data-ttu-id="fa9a7-106">Windows PowerShell® Web Access を使うと、Windows PowerShell® のユーザーは、Secure Sockets Layer (SSL) で保護された Web サイトにサインインして、Windows PowerShell のセッション、コマンドレット、およびスクリプトを使ってリモート コンピューターを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-106">Windows PowerShell® Web Access lets Windows PowerShell® users sign in to a Secure Sockets Layer (SSL)-secured website to use Windows PowerShell sessions, cmdlets, and scripts to manage a remote computer.</span></span> <span data-ttu-id="fa9a7-107">Windows PowerShell コンソールは Web ブラウザー内で実行されるため、携帯電話、タブレット コンピューター、公共のコンピューティング キオスク、ノート PC、共有や貸与されているコンピューターなど、さまざまなクライアント デバイスで表示することができます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-107">Because the Windows PowerShell console runs in a web browser, it can be opened from a variety of client devices, including cell phones, tablet computers, public computing kiosks, laptop computers, or shared or borrowed computers.</span></span> <span data-ttu-id="fa9a7-108">Web ベースの Windows PowerShell コンソールは、サインイン プロセスでユーザーが指定するリモート コンピューターを対象としています。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-108">The web-based Windows PowerShell console is targeted at a remote computer that is specified by users as part of the sign-in process.</span></span> <span data-ttu-id="fa9a7-109">このトピックでは、Windows PowerShell Web Access の Web ベース コンソールにサインインして使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-109">This topic describes how to sign in to and start using the Windows PowerShell Web Access web-based console.</span></span>

<span data-ttu-id="fa9a7-110">Windows PowerShell の使用方法や、コマンドレットまたはスクリプトの実行方法はこのトピックの対象外です。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-110">This topic does not describe how to use Windows PowerShell or run cmdlets or scripts.</span></span> <span data-ttu-id="fa9a7-111">Windows PowerShell およびスクリプト リソースの使用方法の詳細については、このトピックの最後にある「関連項目」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-111">For information about how to use Windows PowerShell, and scripting resources, see the See Also section at the end of this topic.</span></span>

<span data-ttu-id="fa9a7-112">このトピックの内容:</span><span class="sxs-lookup"><span data-stu-id="fa9a7-112">In this topic:</span></span>

-   [<span data-ttu-id="fa9a7-113">サポートされているブラウザーとクライアント デバイス</span><span class="sxs-lookup"><span data-stu-id="fa9a7-113">Supported browsers and client devices</span></span>](#BKMK_browser)

-   [<span data-ttu-id="fa9a7-114">Windows PowerShell Web Access へのサインイン</span><span class="sxs-lookup"><span data-stu-id="fa9a7-114">Signing in to Windows PowerShell Web Access</span></span>](#BKMK_sign)

-   [<span data-ttu-id="fa9a7-115">サインアウトとタイムアウト</span><span class="sxs-lookup"><span data-stu-id="fa9a7-115">Signing out and timing out</span></span>](#BKMK_timeout)

-   [<span data-ttu-id="fa9a7-116">Web ベースの Windows PowerShell コンソールにおける相違点</span><span class="sxs-lookup"><span data-stu-id="fa9a7-116">Differences in the web-based Windows PowerShell console</span></span>](#BKMK_web)

<a href="" id="BKMK_browser"></a>
------------------------------------------------------------------------

<span data-ttu-id="fa9a7-117">Windows PowerShell Web Access は次のインターネット ブラウザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-117">Windows PowerShell Web Access supports the following Internet browsers.</span></span> <span data-ttu-id="fa9a7-118">モバイル ブラウザーは公式にはサポートされていませんが、それらの多くが Web ベースの Windows PowerShell コンソールを実行できるようです。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-118">Although mobile browsers are not officially supported, many may be able to run the web-based Windows PowerShell console.</span></span> <span data-ttu-id="fa9a7-119">その他のブラウザーも、Cookie の許可、JavaScript の実行、および HTTPS Web サイトの実行に対応している場合は動作すると思われますが、公式にはテストされていません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-119">Other browsers that accept cookies, run JavaScript, and run HTTPS websites are expected to work, but are not officially tested.</span></span>

###

<span data-ttu-id="fa9a7-120"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">サポート対象のデスクトップ コンピューター ブラウザー</span></a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-120"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Supported desktop computer browsers</span></a></span></span>

------------------------------------------------------------------------

-   <span data-ttu-id="fa9a7-121">Windows® Internet Explorer® for Microsoft Windows® 8.0、9.0、10.0、および 11.0</span><span class="sxs-lookup"><span data-stu-id="fa9a7-121">Windows® Internet Explorer® for Microsoft Windows® 8.0, 9.0, 10.0, and 11.0</span></span>

-   <span data-ttu-id="fa9a7-122">Mozilla Firefox® 10.0.2</span><span class="sxs-lookup"><span data-stu-id="fa9a7-122">Mozilla Firefox® 10.0.2</span></span>

-   <span data-ttu-id="fa9a7-123">Google Chrome™ 17.0.963.56m for Windows</span><span class="sxs-lookup"><span data-stu-id="fa9a7-123">Google Chrome™ 17.0.963.56m for Windows</span></span>

-   <span data-ttu-id="fa9a7-124">Apple Safari® 5.1.2 for Windows</span><span class="sxs-lookup"><span data-stu-id="fa9a7-124">Apple Safari® 5.1.2 for Windows</span></span>

-   <span data-ttu-id="fa9a7-125">Apple Safari 5.1.2 for Mac OS®</span><span class="sxs-lookup"><span data-stu-id="fa9a7-125">Apple Safari 5.1.2 for Mac OS®</span></span>

###

<span data-ttu-id="fa9a7-126"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">最低限のテストを実施済みのモバイル デバイスまたはブラウザー</span></a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-126"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Minimally-tested mobile devices or browsers</span></a></span></span>

------------------------------------------------------------------------

-   <span data-ttu-id="fa9a7-127">Windows Phone 7 および 7.5</span><span class="sxs-lookup"><span data-stu-id="fa9a7-127">Windows Phone 7 and 7.5</span></span>

-   <span data-ttu-id="fa9a7-128">Google Android WebKit 3.1 Browser Android 2.2.1 (Kernel 2.6)</span><span class="sxs-lookup"><span data-stu-id="fa9a7-128">Google Android WebKit 3.1 Browser Android 2.2.1 (Kernel 2.6)</span></span>

-   <span data-ttu-id="fa9a7-129">Apple Safari for iPhone operating system 5.0.1</span><span class="sxs-lookup"><span data-stu-id="fa9a7-129">Apple Safari for iPhone operating system 5.0.1</span></span>

-   <span data-ttu-id="fa9a7-130">Apple Safari for iPad 2 operating system 5.0.1</span><span class="sxs-lookup"><span data-stu-id="fa9a7-130">Apple Safari for iPad 2 operating system 5.0.1</span></span>

###

<span data-ttu-id="fa9a7-131"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">ブラウザーの要件</span></a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-131"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Browser requirements</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="fa9a7-132">Web ベースの Windows PowerShell コンソールを使うには、ブラウザーが次の操作を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-132">To use the Windows PowerShell Web Access web-based console, browsers must do the following.</span></span>

-   <span data-ttu-id="fa9a7-133">Windows PowerShell Web Access ゲートウェイ Web サイトの Cookie を許可する。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-133">Allow cookies from the Windows PowerShell Web Access gateway website.</span></span>

-   <span data-ttu-id="fa9a7-134">HTTPS ページを開き、読み取る。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-134">Be able to open and read HTTPS pages.</span></span>

-   <span data-ttu-id="fa9a7-135">JavaScript を使う Web サイトを開き、実行する。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-135">Open and run websites that use JavaScript.</span></span>

<a href="" id="BKMK_sign"></a>

<span data-ttu-id="fa9a7-136"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Windows PowerShell Web Access へのサインイン</span></a>
<a href="/en-us/library/hh831417(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-136"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Signing in to Windows PowerShell Web Access</span></a>
<a href="/en-us/library/hh831417(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="fa9a7-137">Windows PowerShell Web Access 管理者は、所属組織の Windows PowerShell Web Access ゲートウェイ Web サイトのアドレスを示す URL を担当者に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-137">Your Windows PowerShell Web Access administrator should provide you with a URL that is the address of your organization’s Windows PowerShell Web Access gateway website.</span></span> <span data-ttu-id="fa9a7-138">この Web サイトのアドレスは、既定で https://&lt;server_name&gt;/pswa となっています。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-138">By default, this website address is https://&lt;server_name&gt;/pswa.</span></span> <span data-ttu-id="fa9a7-139">Windows PowerShell Web Access にサインインする前に、管理対象のリモート コンピューターの名前または IP アドレスがわかっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-139">Before you sign in to Windows PowerShell Web Access, be sure that you have the name or IP address of the remote computer that you want to manage.</span></span> <span data-ttu-id="fa9a7-140">また担当者がリモート コンピューターの承認済みユーザーであることと、リモート コンピューターがリモート管理を許可するよう構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-140">You must be an authorized user on the remote computer, and it must be configured to allow remote management.</span></span> <span data-ttu-id="fa9a7-141">リモート管理を許可するようコンピューターを構成する方法の詳細については、[Windows PowerShell でのリモート コマンドの有効化および使用](https://technet.microsoft.com/magazine/ff700227.aspx)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-141">For more information about configuring your computer to allow remote management, see [Enable and Use Remote Commands in Windows PowerShell](https://technet.microsoft.com/magazine/ff700227.aspx).</span></span> <span data-ttu-id="fa9a7-142">コンピューターを構成してリモート管理を有効にする最も簡単な方法は、Windows PowerShell セッションを管理者特権で開き (**[管理者として実行]**)、コンピューター上で **Enable-PSRemoting -force** コマンドレットを実行することです。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-142">The simplest method of configuring your computer to allow remote management is to run the **Enable-PSRemoting -force** cmdlet on the computer, in a Windows PowerShell session that has been opened with elevated user rights (**Run as Administrator**).</span></span>

### <a name="to-sign-in-to-windows-powershell-web-access"></a><span data-ttu-id="fa9a7-143">Windows PowerShell Web Access にサインインするには</span><span class="sxs-lookup"><span data-stu-id="fa9a7-143">To sign in to Windows PowerShell Web Access</span></span>

1.  <span data-ttu-id="fa9a7-144">Windows PowerShell Web Access Web サイトをインターネット ブラウザーのウィンドウまたはタブで開きます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-144">Open the Windows PowerShell Web Access website in an Internet browser window or tab.</span></span>

2.  <span data-ttu-id="fa9a7-145">Windows PowerShell Web Access のサインイン ページで、ネットワーク ユーザー名、パスワード、および管理対象の (自分が承認済みユーザーとなっている) コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-145">On the Windows PowerShell Web Access sign-in page, provide your network user name, password, and the name of the computer that you want to manage (and on which you are an authorized user).</span></span> <span data-ttu-id="fa9a7-146">コンピューター名の代わりにカスタム サイトまたはプロキシ サーバーの URI を使うよう Windows PowerShell Web Access 管理者から指示されている場合は、**"接続の種類"** フィールドの **[接続 URI]** を選択し、URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-146">If the Windows PowerShell Web Access administrator has instructed you to use a URI to a custom site or proxy server instead of a computer name, select **Connection URI** in the **Connection type** field, and then provide the URI.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="fa9a7-147"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="fa9a7-147"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><ul>
    <li><p><span data-ttu-id="fa9a7-148">対象のコンピューターがワークグループに含まれる場合は、&lt;<em>ワークグループ名</em>&gt;\&lt;<em>ユーザー名</em>&gt; の構文を使ってユーザー名を入力し、コンピューターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-148">If the destination computer is in a workgroup, use the following syntax to provide your user name and sign in to the computer:&lt;<em>workgroup_name</em>&gt;\&lt;<em>user_name</em>&gt;.</span></span></p></li>
    <li><p><span data-ttu-id="fa9a7-149">対象のコンピューターがゲートウェイ サーバーの場合、<strong>[コンピューター名]</strong> フィールドで <strong>localhost</strong> を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-149">If the destination computer is the gateway server, you can specify <strong>localhost</strong> in the <strong>Computer name</strong> field.</span></span></p></li>
    <li><p><span data-ttu-id="fa9a7-150">対象のコンピューターがゲートウェイ サーバーで、そのゲートウェイ サーバーがワークグループに含まれている場合、<strong>[コンピューター名]</strong> フィールドで <strong>localhost</strong> を使用できます。ただし <strong>[ユーザー名]</strong> フィールドでは localhost\&lt;<em>user_name</em>&gt; を使わないでください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-150">If the destination computer is the gateway server, and the gateway server is in a workgroup, you can use <strong>localhost</strong> in the <strong>Computer name</strong> field, but do not use localhost\&lt;<em>user_name</em>&gt; in the <strong>User name</strong> field.</span></span> <span data-ttu-id="fa9a7-151">&lt;<em>ワークグループ名</em>&gt;\&lt;<em>ユーザー名</em>&gt; を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-151">You must use &lt;<em>workgroup name</em>&gt;\&lt;<em>user_name</em>&gt;.</span></span></p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="fa9a7-152">**[オプションの接続設定]** セクションは、管理対象のリモート コンピューターの承認要件に関連しています。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-152">The **Optional Connection Settings** section relates to the authorization requirements of the remote computer that you want to manage.</span></span> <span data-ttu-id="fa9a7-153">オプションの接続設定に相当するパラメーターの詳細については、[Enter-PSSession コマンドレットのヘルプ](https://technet.microsoft.com/library/dd315384.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-153">For more information about the parameters that are equivalent to optional connection settings, see the [Enter-PSSession cmdlet Help](https://technet.microsoft.com/library/dd315384.aspx).</span></span>

    <span data-ttu-id="fa9a7-154">通常、Windows PowerShell Web Access ゲートウェイの通過に使う資格情報は、管理対象のリモート コンピューターが認識する資格情報と同じです。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-154">Typically, the credentials you use to pass through the Windows PowerShell Web Access gateway are the same that are recognized by the remote computer that you want to manage.</span></span> <span data-ttu-id="fa9a7-155">ただし、手順 2. で指定したリモート コンピューターを別の資格情報を使って管理する場合、**[オプションの接続設定]** セクションを展開して、別の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-155">However, if you want to use different credentials to manage the remote computer that you specified in step 2, expand the **Optional Connection Settings** section, and provide the alternate credentials.</span></span> <span data-ttu-id="fa9a7-156">それ以外の場合、手順 6. に進みます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-156">Otherwise, skip to step 6.</span></span>

4.  <span data-ttu-id="fa9a7-157">Windows PowerShell Web Access 管理者が Windows PowerShell Web Access ユーザー用にカスタムのセッション構成を作成している場合、そのセッション構成の名前を **"構成名"** フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-157">If the Windows PowerShell Web Access administrator has created a custom session configuration for Windows PowerShell Web Access users, type the name of the session configuration name in the **Configuration name** field.</span></span> <span data-ttu-id="fa9a7-158">セッション構成の詳細については、Microsoft Web サイトの「[about_Session_Configurations](https://technet.microsoft.com/library/dd819508.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-158">For more information about session configurations, see [about_Session_Configurations](https://technet.microsoft.com/library/dd819508.aspx) on the Microsoft website.</span></span>

5.  <span data-ttu-id="fa9a7-159">**[認証の種類]** の設定は、それ以外にするよう Windows PowerShell Web Access 管理者から指示された場合を除き、**[既定]** が設定されたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-159">Keep the **Authentication type** set to **Default** unless you have been instructed to do otherwise by the Windows PowerShell Web Access administrator.</span></span>

6.  <span data-ttu-id="fa9a7-160">**[サインイン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-160">Click **Sign in**.</span></span>

<a href="" id="BKMK_timeout"></a>

<span data-ttu-id="fa9a7-161"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">サインアウトとタイムアウト</span></a>
<a href="/en-us/library/hh831417(v=ws.11).aspx#Anchor_2" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-161"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Signing out and timing out</span></a>
<a href="/en-us/library/hh831417(v=ws.11).aspx#Anchor_2" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="fa9a7-162">次のいずれかの操作を実行すると、Web ベースの Windows PowerShell セッションからサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-162">Any of the following signs you out of a web-based Windows PowerShell session.</span></span>

-   <span data-ttu-id="fa9a7-163">コンソールの右下隅にある **[サインアウト]** をクリックする</span><span class="sxs-lookup"><span data-stu-id="fa9a7-163">Clicking **Sign out** in the lower right corner of the console.</span></span> <span data-ttu-id="fa9a7-164">(Windows Server 2012 のみ)</span><span class="sxs-lookup"><span data-stu-id="fa9a7-164">(Windows Server 2012 only)</span></span>

-   <span data-ttu-id="fa9a7-165">コンソールの右下隅にある **[保存]** または **[終了]** をクリックする (Windows Server 2012 R2 のみ)。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-165">Clicking **Save** or **Exit** in the lower right corner of the console (Windows Server 2012 R2 only).</span></span> <span data-ttu-id="fa9a7-166">**[保存]** をクリックすると Windows PowerShell Web Access セッションが保存されて閉じます。後でセッションに再接続できます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-166">Clicking **Save** saves and closes your Windows PowerShell Web Access session; you can reconnect to the session later.</span></span> <span data-ttu-id="fa9a7-167">Windows PowerShell Web Access に再びサインインすると、保存したセッションの一覧が Windows PowerShell Web Access に表示されます。保存されているセッションを選択して再接続することも、新しいセッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-167">When you sign in to Windows PowerShell Web Access again, Windows PowerShell Web Access displays a list of your saved sessions; you can either select and reconnect to a saved session, or start a new session.</span></span> <span data-ttu-id="fa9a7-168">ユーザーが開くことのできるセッションの最大数 (保存されているものとアクティブの両方) は、ゲートウェイの管理者が構成します。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-168">The maximum number of open sessions that users are allowed, both saved and active, is configured by the gateway administrator.</span></span>

    <span data-ttu-id="fa9a7-169">**[終了]** をクリックすると、Windows PowerShell Web Access セッションが保存されずにサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-169">Clicking **Exit** signs you out of the Windows PowerShell Web Access session without saving it.</span></span>

-   <span data-ttu-id="fa9a7-170">同じブラウザー セッションまたは同じブラウザー セッションの新しいタブで、別のリモート コンピューターを管理するためにサインインする。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-170">Attempting to sign in to manage a different remote computer in the same browser session, or in a new tab of the same browser session.</span></span> <span data-ttu-id="fa9a7-171">(これは、ゲートウェイ サーバーが Windows Server 2012 R2 を実行している場合は適用されません。Windows Server 2012 R2 で実行している Windows PowerShell Web Access では、同じブラウザー セッションの新しいタブで複数のユーザー セッションを開くことができます)。同じコンピューターで複数のアクティブ セッションを使う方法の詳細については、このトピックの「[Web ベース コンソールの制限事項](#BKMK_limits)」セクションの「複数の対象コンピューターへの同時接続」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-171">(This does not apply if the gateway server is running Windows Server 2012 R2; Windows PowerShell Web Access running on Windows Server 2012 R2 does allow multiple user sessions in new tabs in the same browser session.) For more information about how to use more than one active session on the same computer, see “Connecting to multiple target computers simultaneously” in the [Limitations of the web-based console](#BKMK_limits) section of this topic.</span></span>

-   <span data-ttu-id="fa9a7-172">セッションの非アクティブな状態が 20 分続いた場合。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-172">20 minutes of inactivity in the session.</span></span> <span data-ttu-id="fa9a7-173">ゲートウェイの管理者は、非アクティブ状態によるタイムアウトの長さをカスタマイズできます。詳細については、「[セッションの管理](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx#BKMK_sesmgmt)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-173">The gateway administrator can customize the inactivity time-out period; for more information, see [Session management](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx#BKMK_sesmgmt).</span></span>

    -   <span data-ttu-id="fa9a7-174">ユーザー自身がセッションを閉じたためではなく、ネットワーク エラーまたはその他の予期しないシャットダウンや障害のために、ユーザーがセッションから切断された場合、クライアント側でタイムアウト期間が経過するまで Windows PowerShell Web Access セッションは実行を続け、ターゲット コンピューターに接続されたままになります。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-174">If you are disconnected from a session in the web-based console because of a network error or other unplanned shutdown or failure, and not because you have closed the session yourself, the Windows PowerShell Web Access session continues to run, connected to the target computer, until the time-out period on the client side lapses.</span></span> <span data-ttu-id="fa9a7-175">既定ではこのタイムアウト期間は 20 分であり、ゲートウェイ管理者が構成します。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-175">By default, this time-out period is 20 minutes, and is configured by the gateway administrator.</span></span> <span data-ttu-id="fa9a7-176">既定の 20 分またはゲートウェイ管理者が指定したタイムアウト期間のどちらか短い方が経過すると、セッションは切断されます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-176">The session is disconnected after either the default 20 minutes, or after the time-out period specified by the gateway administrator, whichever is shorter.</span></span>

        <span data-ttu-id="fa9a7-177">ゲートウェイ サーバーが Windows Server 2012 R2 を実行している場合の Windows PowerShell Web Access では、ユーザーは保存されているセッションに再接続できますが、ゲートウェイ管理者によって指定されたタイムアウト期間が経過するまでは、保存されているセッションを表示または再接続できません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-177">If the gateway server is running Windows Server 2012 R2, Windows PowerShell Web Access lets users reconnect to saved sessions at a later time, but you cannot see or reconnect to saved sessions until after the time-out period specified by the gateway administrator has lapsed.</span></span>

-   <span data-ttu-id="fa9a7-178">ブラウザー ウィンドウまたはタブを閉じる。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-178">Closing the browser window or tab.</span></span>

-   <span data-ttu-id="fa9a7-179">ブラウザーが実行されているクライアント デバイスの電源を切る、またはネットワークから切断する。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-179">Turning off the client device on which the browser is running, or disconnecting it from the network.</span></span>

-   <span data-ttu-id="fa9a7-180">Web コンソールで **[終了]** コマンドを実行する。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-180">Running the **Exit** command in the web console.</span></span> <span data-ttu-id="fa9a7-181">接続先のセッション構成が [NoLanguage](https://msdn.microsoft.com/library/windows/desktop/system.management.automation.pslanguagemode.aspx) モードをサポートするよう構成されている場合、または制限付き実行空間が指定されている場合は、このコマンドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-181">This command does not work if the session configuration to which you are connected to is configured to support [NoLanguage](https://msdn.microsoft.com/library/windows/desktop/system.management.automation.pslanguagemode.aspx) mode, or is in a restricted runspace.</span></span>

<span data-ttu-id="fa9a7-182">もう一度サインインする場合は、Windows PowerShell Web Access の Web ページをもう一度開き、このトピックの「[Windows PowerShell Web Access にサインインするには](#BKMK_signin)」の手順に従ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-182">If you want to sign in again, open the Windows PowerShell Web Access web page again, and sign in by following the steps in [To sign in to Windows PowerShell Web Access](#BKMK_signin) in this topic.</span></span>

<a href="" id="BKMK_web"></a>

<span data-ttu-id="fa9a7-183"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Web ベースの Windows PowerShell コンソールにおける相違点</span></a>
<a href="/en-us/library/hh831417(v=ws.11).aspx#Anchor_3" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-183"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Differences in the web-based Windows PowerShell console</span></a>
<a href="/en-us/library/hh831417(v=ws.11).aspx#Anchor_3" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="fa9a7-184">Windows PowerShell Web Access にサインインすると、Web ベースの Windows PowerShell コンソールがブラウザー ウィンドウまたはタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-184">After signing in to Windows PowerShell Web Access, a web-based Windows PowerShell console opens in your browser window or tab.</span></span> <span data-ttu-id="fa9a7-185">コンソールはサインイン プロセスで指定したリモート コンピューターに接続されているため、このコンソールで使える Windows PowerShell コマンドレットまたはスクリプトは、対象のリモート コンピューターで利用可能なものだけです。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-185">Because the console is connected to the remote computer that you specified during the sign-in process, only those Windows PowerShell cmdlets or scripts that are available on the remote computer can be used in the console.</span></span> <span data-ttu-id="fa9a7-186">このセクションでは、Windows PowerShell Web Access コンソールにおけるその他の制限事項と、Windows PowerShell Web Access コンソールとインストール型の **PowerShell.exe** コンソールとの間の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-186">This section describes other limitations of Windows PowerShell Web Access consoles, and differences between Windows PowerShell Web Access consoles and the installed **PowerShell.exe** console.</span></span>

###

<span data-ttu-id="fa9a7-187"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">PowerShell.exe との機能面の相違点</span></a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-187"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Functional disparity with PowerShell.exe</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="fa9a7-188">Windows PowerShell のホスト機能の大部分は Windows PowerShell Web Access の Web ベース コンソールでも利用できますが、いくつかの機能は利用できません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-188">The majority of Windows PowerShell host functionality is available in the Windows PowerShell Web Access web-based console, but there are some features that are not available.</span></span>

-   <span data-ttu-id="fa9a7-189"><span class="label">入れ子になった進行状況の表示:</span> </span><span class="sxs-lookup"><span data-stu-id="fa9a7-189"><span class="label">Nested progress displays.</span></span></span>  <span data-ttu-id="fa9a7-190">進行状況を報告するコマンドレットを使用すると、Windows PowerShell Web Access が表示する進行状況 GUI には、最上位レベルの情報だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-190">Windows PowerShell Web Access displays a progress GUI for cmdlets that report progress, but only top-level progress information is displayed.</span></span>

-   <span data-ttu-id="fa9a7-191"><span class="label">入力色の変更:</span> </span><span class="sxs-lookup"><span data-stu-id="fa9a7-191"><span class="label">Input color modification.</span></span></span>  <span data-ttu-id="fa9a7-192">入力色 (前景と背景) は変更できません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-192">The input color (both foreground and background) cannot be changed.</span></span> <span data-ttu-id="fa9a7-193">出力、警告、詳細、およびエラー メッセージのスタイルは、スクリプトを実行することで変更できます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-193">The style of output, warning, verbose, and error messages can all be changed by running a script.</span></span>

-   <span data-ttu-id="fa9a7-194"><span class="label">PSHostRawUserInterface:</span> </span><span class="sxs-lookup"><span data-stu-id="fa9a7-194"><span class="label">PSHostRawUserInterface.</span></span></span>  <span data-ttu-id="fa9a7-195">Windows PowerShell Web Accessは Windows PowerShell リモート管理経由で実装され、リモートの実行空間を使います。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-195">Windows PowerShell Web Access is implemented over Windows PowerShell remote management, and uses a remote runspace.</span></span> <span data-ttu-id="fa9a7-196">たとえば Windows コンソールへの書き込みを実行するあらゆるコマンドなど、一部のメソッドは Windows PowerShell Web Access によってこのインターフェイスに実装されません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-196">Windows PowerShell Web Access does not implement some methods in this interface; for example, any command that writes to the Windows console.</span></span> <span data-ttu-id="fa9a7-197">**PowerTab** などのコマンドは、Windows PowerShell Web Access では動作しません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-197">Commands such as **PowerTab** do not work in Windows PowerShell Web Access.</span></span>

-   <span data-ttu-id="fa9a7-198"><span class="label">ファンクション キー:</span> </span><span class="sxs-lookup"><span data-stu-id="fa9a7-198"><span class="label">Function keys.</span></span></span>  <span data-ttu-id="fa9a7-199">一部のファンクション キーは Windows PowerShell Web Access によってサポートされません。多くの場合、それらのコマンドがブラウザーによって予約されていることが原因です。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-199">Windows PowerShell Web Access does not support some function keys, in many cases because the commands are reserved by the browser.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fa9a7-200">サポートされないファンクション キー</span><span class="sxs-lookup"><span data-stu-id="fa9a7-200">Unsupported Function Key</span></span></p></th>
<th><p><span data-ttu-id="fa9a7-201">操作</span><span class="sxs-lookup"><span data-stu-id="fa9a7-201">Action</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-202">Ctrl+C</span><span class="sxs-lookup"><span data-stu-id="fa9a7-202">Ctrl+C</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-203">Windows PowerShell Web Access では、<strong>Ctrl + C</strong> はブラウザーによるコンテンツのコピーに使われます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-203">In Windows PowerShell Web Access, <strong>Ctrl+C</strong> is used by the browser to copy content.</span></span> <span data-ttu-id="fa9a7-204">コンソールが提供する <strong>[キャンセル]</strong> ボタンのほか、ユーザーは <strong>Ctrl + Q</strong> を使ってコマンドをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-204">The console offers a <strong>Cancel</strong> button, and users can also use <strong>Ctrl+Q</strong> to cancel commands.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-205">Alt + Space、e、l</span><span class="sxs-lookup"><span data-stu-id="fa9a7-205">Alt-space, e, l</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-206">画面バッファーをスクロール</span><span class="sxs-lookup"><span data-stu-id="fa9a7-206">Scroll through the screen buffer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-207">Alt + Space、e、f</span><span class="sxs-lookup"><span data-stu-id="fa9a7-207">Alt+Space, e, f</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-208">画面バッファー内のテキストを検索</span><span class="sxs-lookup"><span data-stu-id="fa9a7-208">Search for text in the screen buffer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-209">Alt + Space、e、k</span><span class="sxs-lookup"><span data-stu-id="fa9a7-209">Alt+Space, e, k</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-210">Select text to be copied from the screen bufferコピーするテキストを画面バッファーから選択</span><span class="sxs-lookup"><span data-stu-id="fa9a7-210">Select text to be copied from the screen buffer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-211">Alt + Space、e、p</span><span class="sxs-lookup"><span data-stu-id="fa9a7-211">Alt+Space, e, p</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-212">クリップボードのコンテンツを Windows PowerShell コンソールに貼り付け</span><span class="sxs-lookup"><span data-stu-id="fa9a7-212">Paste clipboard contents into the Windows PowerShell console</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-213">Alt + Space、c</span><span class="sxs-lookup"><span data-stu-id="fa9a7-213">Alt+Space, c</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-214">Windows PowerShell コンソールを閉じる</span><span class="sxs-lookup"><span data-stu-id="fa9a7-214">Close the Windows PowerShell console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-215">Ctrl + Break</span><span class="sxs-lookup"><span data-stu-id="fa9a7-215">Ctrl+Break</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-216">Windows PowerShell ウィンドウを強制的に閉じる</span><span class="sxs-lookup"><span data-stu-id="fa9a7-216">Force the Windows PowerShell window to close</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-217">Ctrl + Home</span><span class="sxs-lookup"><span data-stu-id="fa9a7-217">Ctrl+Home</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-218">現在のコマンド ラインの先頭から削除</span><span class="sxs-lookup"><span data-stu-id="fa9a7-218">Deletes from the beginning of the current command line</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-219">Ctrl + End</span><span class="sxs-lookup"><span data-stu-id="fa9a7-219">Ctrl+End</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-220">コマンド ラインの末尾まで削除</span><span class="sxs-lookup"><span data-stu-id="fa9a7-220">Deletes to end of the command line</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-221">F1</span><span class="sxs-lookup"><span data-stu-id="fa9a7-221">F1</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-222">コマンド ライン上でカーソルを 1 文字分移動</span><span class="sxs-lookup"><span data-stu-id="fa9a7-222">Move cursor one character to the right on your command line</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-223">F2</span><span class="sxs-lookup"><span data-stu-id="fa9a7-223">F2</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-224">最後のコマンドをコピーし、入力する文字に合わせて新しいコマンドを作成</span><span class="sxs-lookup"><span data-stu-id="fa9a7-224">Creates a new command by copying your last command up to the character that you type</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-225">F3</span><span class="sxs-lookup"><span data-stu-id="fa9a7-225">F3</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-226">最後のコマンド ラインの内容を使ってコマンド ラインを完成させる</span><span class="sxs-lookup"><span data-stu-id="fa9a7-226">Complete the command line with content from your last command line</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-227">F4</span><span class="sxs-lookup"><span data-stu-id="fa9a7-227">F4</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-228">カーソル位置から文字を削除</span><span class="sxs-lookup"><span data-stu-id="fa9a7-228">Deletes characters from cursor position</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-229">F5</span><span class="sxs-lookup"><span data-stu-id="fa9a7-229">F5</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-230">コマンド履歴をさかのぼってスキャン</span><span class="sxs-lookup"><span data-stu-id="fa9a7-230">Scan backward through your command history.</span></span> <span data-ttu-id="fa9a7-231">Windows PowerShell Web Access のコマンド履歴にあるコマンドにアクセスするには、Web ベース コンソールで <strong>[履歴]</strong> スクロール ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-231">To access commands in the command history in Windows PowerShell Web Access, click the <strong>History</strong> scroll buttons in the web-based console.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-232">F7</span><span class="sxs-lookup"><span data-stu-id="fa9a7-232">F7</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-233">コマンド履歴のコマンドを対話的に選択</span><span class="sxs-lookup"><span data-stu-id="fa9a7-233">Interactively select a command from your command history</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-234">F8</span><span class="sxs-lookup"><span data-stu-id="fa9a7-234">F8</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-235">現在のテキストに一致するコマンドが表示された履歴をスキャン</span><span class="sxs-lookup"><span data-stu-id="fa9a7-235">Scan history displaying commands that match current text</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-236">F9</span><span class="sxs-lookup"><span data-stu-id="fa9a7-236">F9</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-237">履歴から特定の番号の付いたコマンドを実行</span><span class="sxs-lookup"><span data-stu-id="fa9a7-237">Run a specific numbered command from history</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-238">PageUp</span><span class="sxs-lookup"><span data-stu-id="fa9a7-238">Page Up</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-239">履歴内の最初のコマンドを実行</span><span class="sxs-lookup"><span data-stu-id="fa9a7-239">Run the first command in the history</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9a7-240">PageDown</span><span class="sxs-lookup"><span data-stu-id="fa9a7-240">Page Down</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-241">履歴内の最後のコマンドを実行</span><span class="sxs-lookup"><span data-stu-id="fa9a7-241">Run the last command in the history</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9a7-242">Alt + F7</span><span class="sxs-lookup"><span data-stu-id="fa9a7-242">Alt+F7</span></span></p></td>
<td><p><span data-ttu-id="fa9a7-243">コマンド履歴の一覧を消去</span><span class="sxs-lookup"><span data-stu-id="fa9a7-243">Clear the command history list</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="fa9a7-244">

<a href="" id="BKMK_limits"></a>
###

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Web ベース コンソールの制限事項</span></a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-244">

<a href="" id="BKMK_limits"></a>
###

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Limitations of the web-based console</span></a></span></span>

------------------------------------------------------------------------

-   <span data-ttu-id="fa9a7-245"><span class="label">ダブルホップ:</span> </span><span class="sxs-lookup"><span data-stu-id="fa9a7-245"><span class="label">Double-hop.</span></span></span>   <span data-ttu-id="fa9a7-246">Windows PowerShell Web Access を使って新しいセッションを作成または操作しようとすると、ダブルホップ (最初の接続から 2 つ目のコンピューターに接続すること) の制限が発生します。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-246">You can encounter the double-hop (or connecting to a second computer from the first connection) limitation if you try to create or work on a new session by using Windows PowerShell Web Access.</span></span> <span data-ttu-id="fa9a7-247">Windows PowerShell Web Access はリモートの実行空間を使いますが、現時点では、リモートの実行空間から 2 つ目のコンピューターへのリモート接続の確立を **PowerShell.exe** がサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-247">Windows PowerShell Web Access uses a remote runspace, and currently, **PowerShell.exe** does not support establishing a remote connection to a second computer from a remote runspace.</span></span> <span data-ttu-id="fa9a7-248">たとえば、**Enter-PSSession** コマンドレットを使って既存の接続から 2 つ目のリモート コンピューターに接続しようとすると、"ネットワーク リソースを取得できません" など、さまざまなエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-248">If you attempt to connect to a second remote computer from an existing connection by using the **Enter-PSSession** cmdlet, for example, you can get various errors, such as “Cannot get network resources.”</span></span>

    <span data-ttu-id="fa9a7-249">ダブルホップのエラーを避けるには、管理者が組織のネットワーク環境に CredSSP 認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-249">To avoid double-hop errors, your administrator should configure CredSSP authentication in your organization’s network environment.</span></span> <span data-ttu-id="fa9a7-250">CredSSP 認証の構成方法の詳細については、Microsoft Web サイトの [CredSSP による次ホップのリモート処理](http://blogs.msdn.com/b/powershell/archive/2008/06/05/credssp-for-second-hop-remoting-part-i-domain-account.aspx)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-250">For more information about configuring CredSSP authentication, see [CredSSP for second-hop remoting](http://blogs.msdn.com/b/powershell/archive/2008/06/05/credssp-for-second-hop-remoting-part-i-domain-account.aspx) on the Microsoft website.</span></span> <span data-ttu-id="fa9a7-251">2 つ目のリモート コンピューターを管理する場合、明示的な資格情報を提供することも可能です。暗黙的な資格情報の場合、次ホップが許可される可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-251">You can also provide explicit credentials when you want to manage a second remote computer; implicit credentials are unlikely to allow the second hop.</span></span>

-   <span data-ttu-id="fa9a7-252">Windows PowerShell Web Access に使用され適用される制限事項は、リモートの Windows PowerShell セッションと同じです。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-252">Windows PowerShell Web Access uses and has the same limitations as a remote Windows PowerShell session.</span></span> <span data-ttu-id="fa9a7-253">コンソールベースのエディターやテキストベースのメニュー プログラムなど、Windows コンソール API を直接呼び出すコマンドは動作しません。これは、これらのコマンドが、標準入力、出力、エラーの各パイプの読み取りと書き込みを実行しないためです。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-253">Commands that directly call Windows console APIs, such as those for console-based editors or text-based menu programs, do not work because the commands do not read or write to standard input, output, and error pipes.</span></span> <span data-ttu-id="fa9a7-254">このため、実行可能ファイルを起動するコマンド (**notepad.exe** など) や GUI を表示するコマンド (<span class="code">OpenGridView</span> や <span class="code">ogv</span> など) は動作しません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-254">Therefore, commands that launch an executable file, such as **notepad.exe**, or display a GUI, such as <span class="code">OpenGridView</span> or <span class="code">ogv</span>, do not work.</span></span> <span data-ttu-id="fa9a7-255">この動作は担当者のエクスペリエンスに影響を与えます。つまり、担当者には Windows PowerShell Web Access がコマンドに応答していないように見えます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-255">Your experience is affected by this behavior; to you, it appears that Windows PowerShell Web Access is not responding to your command.</span></span>

-   <span data-ttu-id="fa9a7-256">タブ補完は、制限付き実行空間が指定されたセッション構成、または **NoLanguage** モードのセッション構成では動作しません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-256">Tab completion does not work in a session configuration with a restricted runspace or one that is in **NoLanguage** mode.</span></span> <span data-ttu-id="fa9a7-257">管理者がタブ補完をサポートするようセッションを構成できますが、承認されていないユーザーに次の情報が公開される可能性があるというセキュリティ上の理由から推奨されません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-257">Although administrators can configure a session to support tab completion, it is discouraged for security reasons, because it can expose the following information to unauthorized users.</span></span>

    -   <span data-ttu-id="fa9a7-258">内部ファイル システムのパス</span><span class="sxs-lookup"><span data-stu-id="fa9a7-258">Internal file system paths</span></span>

    -   <span data-ttu-id="fa9a7-259">内部コンピューターの共有フォルダー</span><span class="sxs-lookup"><span data-stu-id="fa9a7-259">Shared folders on internal computers</span></span>

    -   <span data-ttu-id="fa9a7-260">実行空間の変数</span><span class="sxs-lookup"><span data-stu-id="fa9a7-260">Variables in the runspace</span></span>

    -   <span data-ttu-id="fa9a7-261">読み込まれる型または .NET Framework の名前空間</span><span class="sxs-lookup"><span data-stu-id="fa9a7-261">Loaded types or.NET Framework namespaces</span></span>

    -   <span data-ttu-id="fa9a7-262">環境変数</span><span class="sxs-lookup"><span data-stu-id="fa9a7-262">Environment variables</span></span>

-   <span data-ttu-id="fa9a7-263">**NoLanguage** の Windows PowerShell Web Access セッション構成または制限付き実行空間にサインインしているユーザーは **[終了]** コマンドを実行してセッションを終了できません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-263">Users who are signed in to a **NoLanguage** session configuration or a restricted runspace in Windows PowerShell Web Access cannot run the **Exit** command to end the session.</span></span> <span data-ttu-id="fa9a7-264">サインアウトするには、コンソール ページの **[サインアウト]** をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-264">To sign out, users should click **Sign Out** on the console page.</span></span>

-   <span data-ttu-id="fa9a7-265"><span class="label">複数の対象コンピューターへの同時接続:</span> </span><span class="sxs-lookup"><span data-stu-id="fa9a7-265"><span class="label">Connecting to multiple target computers simultaneously.</span></span></span>   <span data-ttu-id="fa9a7-266">ゲートウェイ サーバーが Windows Server 2012 を実行している場合、Windows PowerShell Web Access では、ブラウザー セッションごとに接続できるリモート コンピューターは 1 つだけです。一度サインインした後に別のブラウザー タブを使って複数のリモート コンピューターに接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-266">If the gateway server is running Windows Server 2012, Windows PowerShell Web Access allows only one remote computer connection per browser session; it does not allow users to sign in once, and connect to multiple remote computers by using separate browser tabs.</span></span> <span data-ttu-id="fa9a7-267">新しいタブまたはブラウザー ウィンドウを開くと、現在のセッションの切断と新しいセッションの開始を確認するメッセージが Windows PowerShell Web Access により表示されます。このメッセージから新しい (または同じ) リモート コンピューターに接続できます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-267">When you open a new tab or new browser window, Windows PowerShell Web Access prompts you to disconnect your current session and start a new session, so that you can connect to the new (or the same) remote computer.</span></span> <span data-ttu-id="fa9a7-268">ただし、異なるリモート コンピューターに対して個別のセッションを 2 つ以上実行する必要がある場合、Internet Explorer の機能を使って新しいセッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-268">If two or more separate sessions to different remote computers are desired, however, a feature in Internet Explorer lets you create a new session.</span></span> <span data-ttu-id="fa9a7-269">Internet Explorer で新しいブラウザー セッションを開始するには、**Alt** キーを押して **[ファイル]** メニューを開き、**[新しいセッション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-269">To start a new browser session in Internet Explorer, press **ALT**, open the **File** menu, and then select **New Session**.</span></span> <span data-ttu-id="fa9a7-270">次に新しいセッションで Windows PowerShell Web Access の Web サイトを開き、サインインして別のリモート コンピューターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-270">Then, open the Windows PowerShell Web Access website in the new session, and sign in to access another remote computer.</span></span>

    <span data-ttu-id="fa9a7-271">Windows PowerShell Web Access ゲートウェイが Windows Server 2012 R2 で実行されている場合、ユーザーは異なるブラウザー タブでリモート コンピューターへの複数の接続を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-271">When the Windows PowerShell Web Access gateway is running on Windows Server 2012 R2, users can open multiple connections to remote computers in different browser tabs.</span></span> <span data-ttu-id="fa9a7-272">Web ベースの Windows PowerShell コンソールを使用してリモート コンピューターへの複数の接続を開く必要がある場合は、ゲートウェイ サーバーがこの機能をサポートしているかどうかを Windows PowerShell Web Access ゲートウェイ管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-272">If you want to open more than one connection to a remote computer by using the web-based Windows PowerShell console, check with your Windows PowerShell Web Access gateway administrator to see if this feature is supported by the gateway server.</span></span>

-   <span data-ttu-id="fa9a7-273"><span class="label">永続的な Windows PowerShell セッション (再接続):</span> </span><span class="sxs-lookup"><span data-stu-id="fa9a7-273"><span class="label">Persistent Windows PowerShell sessions (Reconnection).</span></span></span>   <span data-ttu-id="fa9a7-274">Windows PowerShell Web Access ゲートウェイがタイムアウトすると、ゲートウェイと対象コンピューターとのリモート接続は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-274">After you time out of the Windows PowerShell Web Access gateway, the remote connection between the gateway and the target computer is closed.</span></span> <span data-ttu-id="fa9a7-275">これによって、現在処理中のすべてのコマンドレットとスクリプトが停止されます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-275">This stops any cmdlets or scripts that are currently in process.</span></span> <span data-ttu-id="fa9a7-276">実行時間の長いタスクを実行している場合は、Windows PowerShell の **-Job** インフラストラクチャを使うことが推奨されます。これにより、ジョブを開始し、コンピューターから切断した後に再接続して、ジョブを永続的なものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-276">You are encouraged to use the Windows PowerShell **-Job** infrastructure when you are performing long-running tasks, so that you can start jobs, disconnect from the computer, reconnect later, and have jobs persist.</span></span> <span data-ttu-id="fa9a7-277">**-Job** コマンドレットを使うもう 1 つのメリットは、Windows PowerShell Web Access を使ってジョブを開始し、サインアウトした後に、Windows PowerShell Web Access またはその他のホスト (Windows PowerShell® 統合スクリプティング環境 (ISE) など) を使って再接続できる点です。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-277">Another benefit of using **-Job** cmdlets is that you can start them by using Windows PowerShell Web Access, sign out, and then reconnect later, either by running Windows PowerShell Web Access or another host (such as Windows PowerShell® Integrated Scripting Environment (ISE)).</span></span>

-   <span data-ttu-id="fa9a7-278"><span class="label">コンソールのサイズ変更:</span> </span><span class="sxs-lookup"><span data-stu-id="fa9a7-278"><span class="label">Console resizing.</span></span></span>   <span data-ttu-id="fa9a7-279">**PowerShell.exe** コンソール ウィンドウのサイズは次の 3 つの方法で変更できます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-279">The **PowerShell.exe** console window can be resized in the following three ways.</span></span>

    -   <span data-ttu-id="fa9a7-280">マウスを使ってコンソール ウィンドウをドラッグして調整する</span><span class="sxs-lookup"><span data-stu-id="fa9a7-280">Drag and adjust the console window size with a mouse</span></span>

    -   <span data-ttu-id="fa9a7-281">コンソール プロパティの GUI を使って高さと幅のプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="fa9a7-281">Change the height and width properties by using a GUI for console properties</span></span>

    -   <span data-ttu-id="fa9a7-282">コマンドレットを使ってコンソール ウィンドウの高さと幅を変更する</span><span class="sxs-lookup"><span data-stu-id="fa9a7-282">Changing the height and width of console windows with a cmdlet</span></span>

        <span data-ttu-id="fa9a7-283">Windows PowerShell Web Access のコンソール ウィンドウは、次のコマンドレットを使って構成できます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-283">The console window for Windows PowerShell Web Access can be configured by using the cmdlets as follows.</span></span> <span data-ttu-id="fa9a7-284">次の例では、ユーザーが Windows PowerShell Web Access コンソールの幅を **20** に変更しています。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-284">In the following example, a user changes the width of Windows PowerShell Web Access console to **20**.</span></span>

        [<span data-ttu-id="fa9a7-285">Copy</span><span class="sxs-lookup"><span data-stu-id="fa9a7-285">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_778d5e55-9195-4bd7-b313-d1fbca7876e4'); "Copy to clipboard.")

            $newSize = $Host.UI.RawUI.WindowSize
            $newSize.Width = $newSize.Width - 20

            $oldSize = $Host.UI.RawUI.WindowSize

            $Host.UI.RawUI.WindowSize = $newSize

        <span data-ttu-id="fa9a7-286">同じ方法でコンソールの高さを変更できます。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-286">You can change the height of the console in a similar manner.</span></span>

        <span data-ttu-id="fa9a7-287">コンソール ビューをカスタマイズするその他の例については、[Windows PowerShell チームのブログ](http://blogs.msdn.com/b/powershell/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-287">Additional examples for customizing the console view are available in the [Windows PowerShell Team Blog](http://blogs.msdn.com/b/powershell/).</span></span>

<span data-ttu-id="fa9a7-288"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">関連項目</span></a>
<a href="/en-us/library/hh831417(v=ws.11).aspx#Anchor_4" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-288"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">See Also</span></a>
<a href="/en-us/library/hh831417(v=ws.11).aspx#Anchor_4" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="fa9a7-289">スクリプト センター - Hey, Scripting Guy! のページ[Windows PowerShell コマンドレット リファレンス](https://technet.microsoft.com/library/ee407531(ws.10).aspx)
[Microsoft TechNet の Windows PowerShell](https://technet.microsoft.com/library/bb978526.aspx)
[TTechNet スクリプト センター リポジトリ](http://gallery.technet.microsoft.com/scriptcenter)
[スクリプト センター - Hey, Scripting Guy!](https://technet.microsoft.com/scriptcenter)
[Windows PowerShell チーム ブログ](http://blogs.msdn.com/b/powershell/)</span><span class="sxs-lookup"><span data-stu-id="fa9a7-289">[Windows PowerShell Cmdlet Reference](https://technet.microsoft.com/library/ee407531(ws.10).aspx)
[Windows PowerShell on Microsoft TechNet](https://technet.microsoft.com/library/bb978526.aspx)
[TechNet Script Center Repository](http://gallery.technet.microsoft.com/scriptcenter)
[Script Center - Hey, Scripting Guy!](https://technet.microsoft.com/scriptcenter)
[Windows PowerShell Team Blog](http://blogs.msdn.com/b/powershell/)</span></span>

<span data-ttu-id="fa9a7-290"><span>表示:</span> 継承 保護</span><span class="sxs-lookup"><span data-stu-id="fa9a7-290"><span>Show:</span> Inherited Protected</span></span>

<span data-ttu-id="fa9a7-291"><span class="stdr-votetitle">このページは役に立ちましたか。</span></span><span class="sxs-lookup"><span data-stu-id="fa9a7-291"><span class="stdr-votetitle">Was this page helpful?</span></span></span>
<span data-ttu-id="fa9a7-292">はい いいえ</span><span class="sxs-lookup"><span data-stu-id="fa9a7-292">Yes No</span></span>

<span data-ttu-id="fa9a7-293">その他にご意見はありますか。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-293">Additional feedback?</span></span>

<span data-ttu-id="fa9a7-294">残り <span class="stdr-count"><span class="stdr-charcnt">1500</span> 文字</span> 送信 スキップする</span><span class="sxs-lookup"><span data-stu-id="fa9a7-294"><span class="stdr-count"><span class="stdr-charcnt">1500</span> characters remaining</span> Submit Skip this</span></span>

<span data-ttu-id="fa9a7-295"><span class="stdr-thankyou">ありがとうございました。</span></span><span class="sxs-lookup"><span data-stu-id="fa9a7-295"><span class="stdr-thankyou">Thank you!</span></span></span> <span data-ttu-id="fa9a7-296"><span class="stdr-appreciate">ご意見をお送りいただきありがとうございます。</span></span><span class="sxs-lookup"><span data-stu-id="fa9a7-296"><span class="stdr-appreciate">We appreciate your feedback.</span></span></span>

[<span data-ttu-id="fa9a7-297">プロファイル (個人情報) の管理</span><span class="sxs-lookup"><span data-stu-id="fa9a7-297">Manage Your Profile</span></span>](https://social.technet.microsoft.com/profile)

|

<span data-ttu-id="fa9a7-298"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"><img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span>サイトのフィードバック</a> サイトのフィードバック</span><span class="sxs-lookup"><span data-stu-id="fa9a7-298"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"> <img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span> Site Feedback</a> Site Feedback</span></span>

<span data-ttu-id="fa9a7-299"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">X</a></span><span class="sxs-lookup"><span data-stu-id="fa9a7-299"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">x</a></span></span>

<span data-ttu-id="fa9a7-300">お客様のご体験をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-300">Tell us about your experience...</span></span>

<span data-ttu-id="fa9a7-301">ページはすばやく表示されましたか?</span><span class="sxs-lookup"><span data-stu-id="fa9a7-301">Did the page load quickly?</span></span>

<span data-ttu-id="fa9a7-302"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="fa9a7-302"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="fa9a7-303">ページのデザインは気に入りましたか?</span><span class="sxs-lookup"><span data-stu-id="fa9a7-303">Do you like the page design?</span></span>

<span data-ttu-id="fa9a7-304"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="fa9a7-304"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="fa9a7-305">詳しくお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-305">Tell us more</span></span>

-   [<span data-ttu-id="fa9a7-306">Flash ニュースレター</span><span class="sxs-lookup"><span data-stu-id="fa9a7-306">Flash Newsletter</span></span>](https://technet.microsoft.com/cc543196.aspx)
-   |
-   [<span data-ttu-id="fa9a7-307">お問い合わせ先</span><span class="sxs-lookup"><span data-stu-id="fa9a7-307">Contact Us</span></span>](https://technet.microsoft.com/cc512759.aspx)
-   |
-   [<span data-ttu-id="fa9a7-308">プライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="fa9a7-308">Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
-   |
-   [<span data-ttu-id="fa9a7-309">使用条件</span><span class="sxs-lookup"><span data-stu-id="fa9a7-309">Terms of Use</span></span>](https://technet.microsoft.com/cc300389.aspx)
-   |
-   [<span data-ttu-id="fa9a7-310">商標</span><span class="sxs-lookup"><span data-stu-id="fa9a7-310">Trademarks</span></span>](https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/)
-   |

<span data-ttu-id="fa9a7-311">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa9a7-311">© 2016 Microsoft</span></span>

<span data-ttu-id="fa9a7-312">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa9a7-312">© 2016 Microsoft</span></span>

<span data-ttu-id="fa9a7-313">サードパーティのスクリプトやコード、サードパーティから本 Web サイトへのリンク、あるいは本サイトからサードパーティへのリンクは、マイクロソフトではなく、そのようなコードの所有者によってお客様にライセンス供与されています。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-313">Third party scripts and code linked to or referenced from this website are licensed to you by the parties that own such code, not by Microsoft.</span></span> <span data-ttu-id="fa9a7-314">ASP.NET Ajax CDN の使用条件 - http://www.asp.net/ajaxlibrary/CDN.ashx を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9a7-314">See ASP.NET Ajax CDN Terms of Use - http://www.asp.net/ajaxlibrary/CDN.ashx.</span></span>
<img src="https://m.webtrends.com/dcsjwb9vb00000c932fd0rjc7_5p3t/njs.gif?dcsuri=/nojavascript&amp;WT.js=No" alt="DCSIMG" id="Img1" width="1" height="1" />

