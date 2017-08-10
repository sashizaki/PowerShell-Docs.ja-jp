---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell Web Access のアンインストール"
ms.openlocfilehash: 7231d5eadceda8e3b28d9a81c2b5dcbe43680ff2
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
#  <a name="uninstall-windows-powershell-web-access"></a><span data-ttu-id="f7fe0-103">Windows PowerShell Web Access をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="f7fe0-103">Uninstall Windows PowerShell Web Access</span></span>

<span data-ttu-id="f7fe0-104">最終更新日: 2013 年 6 月 24 日</span><span class="sxs-lookup"><span data-stu-id="f7fe0-104">Updated: June 24, 2013</span></span>

<span data-ttu-id="f7fe0-105">適用対象: Windows Server 2012 R2、Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f7fe0-105">Applies To: Windows Server 2012 R2, Windows Server 2012</span></span>

<span data-ttu-id="f7fe0-106">Windows Server 2012 R2 または Windows Server 2012 のいずれかを実行しているゲートウェイ サーバーから Windows PowerShell Web Access Web サイトおよびアプリケーションを削除するには、このトピックの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-106">Follow steps in this topic to delete the Windows PowerShell Web Access website and application from the gateway server that is running either Windows Server 2012 R2 or Windows Server 2012.</span></span> <span data-ttu-id="f7fe0-107">開始する前に、Web サイトを削除することを Web ベース コンソールのユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-107">Before you begin, notify users of the web-based console that you are removing the website.</span></span>

<a href="" id="BKMK_uninstall"></a>

------------------------------------------------------------------------

<span data-ttu-id="f7fe0-108">ゲートウェイ サーバーから Windows PowerShell Web Access をアンインストールする前に、<span class="code">Uninstall-PswaWebApplication</span> コマンドレットを実行して Web サイトおよび Windows PowerShell Web Access Web アプリケーションを削除するか、IIS マネージャーの手順「[IIS マネージャーを使って Windows PowerShell Web Access Web サイトおよびアプリケーションを削除するには](#BKMK_delsite)」を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-108">Before you uninstall Windows PowerShell Web Access from the gateway server, either run the <span class="code">Uninstall-PswaWebApplication</span> cmdlet to remove the website and Windows PowerShell Web Access web applications, or use the IIS Manager procedure, [To delete the Windows PowerShell Web Access website and web applications by using IIS Manager](#BKMK_delsite).</span></span>

<span data-ttu-id="f7fe0-109">Windows PowerShell Web Access の実行に必要なため、Windows PowerShell Web Access をアンインストールしても、自動インストールされた IIS その他の機能はアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-109">Uninstalling Windows PowerShell Web Access does not uninstall IIS or any other features that were installed automatically because Windows PowerShell Web Access requires them to run.</span></span> <span data-ttu-id="f7fe0-110">アンインストール プロセスでは、Windows PowerShell Web Access が依存する機能はそのまま残されるため、必要に応じて手動でアンインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-110">The uninstallation process leaves features installed upon which Windows PowerShell Web Access was dependent; you can uninstall those features separately if needed.</span></span>

<span data-ttu-id="f7fe0-111"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">推奨の (クイック) アンインストール</span></a>
<a href="/en-us/library/dn282396(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="f7fe0-111"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Recommended (quick) uninstallation</span></a>
<a href="/en-us/library/dn282396(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="f7fe0-112">このセクションの手順では、Windows PowerShell コマンドレットを使用して Windows PowerShell Web Access Web アプリケーションと Windows PowerShell Web Access 機能の両方をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-112">Procedures in this section help you uninstall both the Windows PowerShell Web Access web application and the Windows PowerShell Web Access feature by using Windows PowerShell cmdlets.</span></span>

###

<span data-ttu-id="f7fe0-113"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 1: Web アプリケーションを削除する</span></a></span><span class="sxs-lookup"><span data-stu-id="f7fe0-113"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 1: Delete the web application</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="f7fe0-114">独自のカスタム Web サイト名を指定した場合は、コマンドに <span class="code">WebsiteName</span> パラメーターを追加し、Web サイト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-114">If you have specified your own, custom website name, add the <span class="code">WebsiteName</span> parameter to your command, and specify the website name.</span></span> <span data-ttu-id="f7fe0-115">(既定のアプリケーション **pswa** ではなく) カスタム Web アプリケーションを使用している場合は、コマンドに <span class="code">WebApplicationName</span> パラメーターを追加し、Web アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-115">If you have used a custom web application (not the default application, **pswa**, add the <span class="code">WebApplicationName</span> parameter to your command, and specify the name of the web application.</span></span>

#### <a name="to-delete-the-website-and-web-applications-by-using-the-uninstall-pswawebapplication-cmdlet"></a><span data-ttu-id="f7fe0-116">Uninstall-PswaWebApplication コマンドレットを使って Web サイトおよびアプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="f7fe0-116">To delete the website and web applications by using the Uninstall-PswaWebApplication cmdlet</span></span>

1.  <span data-ttu-id="f7fe0-117">次のいずれかを実行して Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-117">Do one of the following to open a Windows PowerShell session.</span></span>

    -   <span data-ttu-id="f7fe0-118">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-118">On the Windows desktop, right-click **Windows PowerShell** on the taskbar.</span></span>

    -   <span data-ttu-id="f7fe0-119">Windows の**スタート**画面で、**[Windows PowerShell]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-119">On the Windows **Start** screen, click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="f7fe0-120">「**Uninstall-PswaWebApplication**」と入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-120">Type **Uninstall-PswaWebApplication**, and then press **Enter**.</span></span>

3.  <span data-ttu-id="f7fe0-121">テスト証明書使用している場合、次の例のように <span class="code">DeleteTestCertificate</span> パラメーターをコマンドレットに追加します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-121">If you are using a test certificate, add the <span class="code">DeleteTestCertificate</span> parameter to the cmdlet, as shown in the following example.</span></span>

    [<span data-ttu-id="f7fe0-122">Copy</span><span class="sxs-lookup"><span data-stu-id="f7fe0-122">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_28147344-ab2f-49e7-b1c2-6dbe649d4366'); "Copy to clipboard.")

        Uninstall-PswaWebApplication -DeleteTestCertificate

###

<span data-ttu-id="f7fe0-123"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 2: Windows PowerShell Web Access をアンインストールする</span></a></span><span class="sxs-lookup"><span data-stu-id="f7fe0-123"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 2: Uninstall Windows PowerShell Web Access</span></a></span></span>

------------------------------------------------------------------------

#### <a name="to-uninstall-windows-powershell-web-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f7fe0-124">Windows PowerShell コマンドレットを使って Windows PowerShell Web Access をアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="f7fe0-124">To uninstall Windows PowerShell Web Access by using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="f7fe0-125">次のいずれかを実行して、管理者特権を使って Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-125">Do one of the following to open a Windows PowerShell session with elevated user rights.</span></span> <span data-ttu-id="f7fe0-126">セッションを既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-126">If a session is already open, go on to the next step.</span></span>

    -   <span data-ttu-id="f7fe0-127">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-127">On the Windows desktop, right-click **Windows PowerShell** on the taskbar, and then click **Run as Administrator**.</span></span>

    -   <span data-ttu-id="f7fe0-128">Windows の**スタート**画面で、**[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-128">On the Windows **Start** screen, right-click **Windows PowerShell**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="f7fe0-129">次のように入力して **Enter** キーを押します。*computer_name* は、Windows PowerShell Web Access を削除するリモート サーバーです。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-129">Type the following, and then press **Enter**, where *computer_name* represents a remote server from which you want to remove Windows PowerShell Web Access.</span></span> <span data-ttu-id="f7fe0-130"><span class="code">-Restart</span> パラメーターによって、対象サーバーが自動的に再起動されます (削除で必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-130">The <span class="code">-Restart</span> parameter automatically restarts destination servers if required by the removal.</span></span>

    [<span data-ttu-id="f7fe0-131">Copy</span><span class="sxs-lookup"><span data-stu-id="f7fe0-131">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_7b534520-f292-471f-89e3-a1079c03e369'); "Copy to clipboard.")

        Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -ComputerName <computer_name> -Restart

    <span data-ttu-id="f7fe0-132">オフライン VHD に役割や機能を削除するには、<span class="code">-ComputerName</span> パラメーターと <span class="code">-VHD</span> パラメーターの両方を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-132">To remove roles and features from an offline VHD, you must add both the <span class="code">-ComputerName</span> parameter and the <span class="code">-VHD</span> parameter.</span></span> <span data-ttu-id="f7fe0-133"><span class="code">-ComputerName</span> パラメーターには VHD のマウント先のサーバー名が格納され、<span class="code">-VHD</span> パラメーターには指定したサーバー上の VHD ファイルへのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-133">The <span class="code">-ComputerName</span> parameter contains the name of the server on which to mount the VHD, and the <span class="code">-VHD</span> parameter contains the path to the VHD file on the specified server.</span></span>

    [<span data-ttu-id="f7fe0-134">Copy</span><span class="sxs-lookup"><span data-stu-id="f7fe0-134">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_5d8f91ee-b91a-4653-b7df-e745187fd72d'); "Copy to clipboard.")

        Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -VHD <path> -ComputerName <computer_name> -Restart

3.  <span data-ttu-id="f7fe0-135">削除が完了したら、Windows PowerShell Web Access が削除されていることを確認します。これには、サーバー マネージャーの **[すべてのサーバー]** ページを開き、機能を削除したサーバーを選択して、選択したサーバーのページで **[役割と機能]** タイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-135">When removal is finished, verify that you removed Windows PowerShell Web Access by opening the **All Servers** page in Server Manager, selecting a server from which you removed the feature, and viewing the **Roles and Features** tile on the page for the selected server.</span></span> <span data-ttu-id="f7fe0-136">また、選択したサーバーを対象として <span class="code">Get-WindowsFeature</span> コマンドレット (Get-WindowsFeature -ComputerName &lt;*computer_name*&gt;) を実行し、サーバーにインストールされている役割と機能の一覧を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-136">You can also run the <span class="code">Get-WindowsFeature</span> cmdlet targeted at the selected server (Get-WindowsFeature -ComputerName &lt;*computer_name*&gt;) to view a list of roles and features that are installed on the server.</span></span>

<span data-ttu-id="f7fe0-137"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">カスタム アンインストール</span></a>
<a href="/en-us/library/dn282396(v=ws.11).aspx#Anchor_2" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="f7fe0-137"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Custom uninstallation</span></a>
<a href="/en-us/library/dn282396(v=ws.11).aspx#Anchor_2" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="f7fe0-138">このセクションの手順では、サーバー マネージャーの役割と機能の削除ウィザード、および IIS マネージャー コンソールを使用して Windows PowerShell Web Access の Web アプリケーションと Windows PowerShell Web Access 機能の両方をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-138">Procedures in this section help you uninstall both the Windows PowerShell Web Access web application and the Windows PowerShell Web Access feature by using the Remove Roles and Features Wizard in Server Manager, and the IIS Manager console.</span></span>

###

<span data-ttu-id="f7fe0-139"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 1: Web アプリケーションを削除する</span></a></span><span class="sxs-lookup"><span data-stu-id="f7fe0-139"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 1: Delete the web application</span></a></span></span>

------------------------------------------------------------------------

#### <a name="to-delete-the-windows-powershell-web-access-website-and-web-applications-by-using-iis-manager"></a><span data-ttu-id="f7fe0-140">IIS マネージャーを使って Windows PowerShell Web Access Web サイトおよびアプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="f7fe0-140">To delete the Windows PowerShell Web Access website and web applications by using IIS Manager</span></span>

1.  <span data-ttu-id="f7fe0-141">次のいずれかの方法で IIS マネージャー コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-141">Open the IIS Manager console by doing one of the following.</span></span> <span data-ttu-id="f7fe0-142">既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-142">If it is already open, go on to the next step.</span></span>

    -   <span data-ttu-id="f7fe0-143">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-143">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span> <span data-ttu-id="f7fe0-144">[サーバー マネージャー] の **[ツール]** メニューで **[インターネット インフォメーション サービス (IIS) マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-144">On the **Tools** menu in Server Manager, click **Internet Information Services (IIS) Manager**.</span></span>

    -   <span data-ttu-id="f7fe0-145">Windows の**スタート**画面で、**インターネット インフォメーション サービス (IIS) マネージャー**という名前の任意の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-145">On the Windows **Start** screen, type any part of the name **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="f7fe0-146">**[アプリ]** の結果に表示されたショートカットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-146">Click the shortcut when it is displayed in the **Apps** results.</span></span>

2.  <span data-ttu-id="f7fe0-147">IIS マネージャーのツリー ウィンドウで、Windows PowerShell Web Access Web アプリケーションを実行している Web サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-147">In the IIS Manager tree pane, select the website that is running the Windows PowerShell Web Access web application.</span></span>

3.  <span data-ttu-id="f7fe0-148">**[操作]** ウィンドウの **[Web サイトの管理]** で **[停止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-148">In the **Actions** pane, under **Manage Website**, click **Stop**.</span></span>

4.  <span data-ttu-id="f7fe0-149">ツリー ウィンドウで、Windows PowerShell Web Access Web アプリケーションを実行している Web サイトの Web アプリケーションを右クリックして、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-149">In the tree pane, right-click the web application in the website that is running the Windows PowerShell Web Access web application, and then click **Remove**.</span></span>

5.  <span data-ttu-id="f7fe0-150">ツリー ウィンドウで **[アプリケーション プール]** を選択し、Windows PowerShell Web Access アプリケーション プールのフォルダーを選択して、**[操作]** ウィンドウの **[停止]** をクリックし、コンテンツ ウィンドウの **[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-150">In the tree pane, select **Application Pools**, select the Windows PowerShell Web Access application pool folder, click **Stop** in the **Actions** pane, and then click **Remove** in the content pane.</span></span>

6.  <span data-ttu-id="f7fe0-151">IIS マネージャーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-151">Close IIS Manager.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="f7fe0-152"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="f7fe0-152"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="f7fe0-153">アンインストールでは証明書は削除されません。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-153">The certificate is not deleted during uninstallation.</span></span> <span data-ttu-id="f7fe0-154">自己署名証明書を作成している場合、または使用したテスト証明書を削除する場合は、IIS マネージャーで証明書を削除できます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-154">If you created a self-signed certificate or used a test certificate and want to remove it, delete the certificate in IIS Manager.</span></span></p></td>
    </tr>
    </tbody>
    </table>

###

<span data-ttu-id="f7fe0-155"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">手順 2: Windows PowerShell Web Access をアンインストールする</span></a></span><span class="sxs-lookup"><span data-stu-id="f7fe0-155"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Step 2: Uninstall Windows PowerShell Web Access</span></a></span></span>

------------------------------------------------------------------------

#### <a name="to-uninstall-windows-powershell-web-access-by-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="f7fe0-156">役割と機能の削除ウィザードを使って Windows PowerShell Web Access をアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="f7fe0-156">To uninstall Windows PowerShell Web Access by using the Remove Roles and Features Wizard</span></span>

1.  <span data-ttu-id="f7fe0-157">サーバー マネージャーを既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-157">If Server Manager is already open, go on to the next step.</span></span> <span data-ttu-id="f7fe0-158">サーバー マネージャーをまだ開いていない場合は、次のいずれかの方法で開きます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-158">If Server Manager is not already open, open it by doing one of the following.</span></span>

    -   <span data-ttu-id="f7fe0-159">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-159">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span>

    -   <span data-ttu-id="f7fe0-160">Windows の**スタート**画面で、**[サーバー マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-160">On the Windows **Start** screen, click **Server Manager**.</span></span>

2.  <span data-ttu-id="f7fe0-161">**[管理]** メニューの **[役割と機能の削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-161">On the **Manage** menu, click **Remove Roles and Features**.</span></span>

3.  <span data-ttu-id="f7fe0-162">**[対象サーバーの選択]** ページで、削除対象の機能を備えているサーバーまたはオフライン VHD を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-162">On the **Select destination server** page, select the server or offline VHD from which you want to remove the feature.</span></span> <span data-ttu-id="f7fe0-163">オフライン VHD を選択するには、最初に VHD マウント先のサーバーを選択してから、VHD ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-163">To select an offline VHD, first select the server on which to mount the VHD, and then select the VHD file.</span></span> <span data-ttu-id="f7fe0-164">対象サーバーを選択したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-164">After you have selected the destination server, click **Next**.</span></span>

4.  <span data-ttu-id="f7fe0-165">もう一度 **[次へ]** をクリックして **[機能の削除]** ページにスキップします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-165">Click **Next** again to skip to the **Remove features** page.</span></span>

5.  <span data-ttu-id="f7fe0-166">**[Windows PowerShell Web Access]** のチェック ボックスをすべてオフにして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-166">Clear the check box for **Windows PowerShell Web Access**, and then click **Next**.</span></span>

6.  <span data-ttu-id="f7fe0-167">**[削除オプションの確認]** ページで、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-167">On the **Confirm removal selections** page, click **Remove**.</span></span>

<span data-ttu-id="f7fe0-168"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">関連項目</span></a>
<a href="/en-us/library/dn282396(v=ws.11).aspx#Anchor_3" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="f7fe0-168"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">See Also</span></a>
<a href="/en-us/library/dn282396(v=ws.11).aspx#Anchor_3" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="f7fe0-169">[Windows PowerShell Web Access のインストールと使用](https://technet.microsoft.com/en-us/library/hh831611(v=ws.11).aspx)
[IIS マネージャー ヘルプ](https://technet.microsoft.com/library/cc732664.aspx)</span><span class="sxs-lookup"><span data-stu-id="f7fe0-169">[Install and Use Windows PowerShell Web Access](https://technet.microsoft.com/en-us/library/hh831611(v=ws.11).aspx)
[IIS Manager 7.0 Help](https://technet.microsoft.com/library/cc732664.aspx)</span></span>

<span data-ttu-id="f7fe0-170"><span>表示:</span> 継承 保護</span><span class="sxs-lookup"><span data-stu-id="f7fe0-170"><span>Show:</span> Inherited Protected</span></span>

<span data-ttu-id="f7fe0-171"><span class="stdr-votetitle">このページは役に立ちましたか。</span></span><span class="sxs-lookup"><span data-stu-id="f7fe0-171"><span class="stdr-votetitle">Was this page helpful?</span></span></span>
<span data-ttu-id="f7fe0-172">はい いいえ</span><span class="sxs-lookup"><span data-stu-id="f7fe0-172">Yes No</span></span>

<span data-ttu-id="f7fe0-173">その他にご意見はありますか。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-173">Additional feedback?</span></span>

<span data-ttu-id="f7fe0-174">残り <span class="stdr-count"><span class="stdr-charcnt">1500</span> 文字</span> 送信 スキップする</span><span class="sxs-lookup"><span data-stu-id="f7fe0-174"><span class="stdr-count"><span class="stdr-charcnt">1500</span> characters remaining</span> Submit Skip this</span></span>

<span data-ttu-id="f7fe0-175"><span class="stdr-thankyou">ありがとうございました。</span></span><span class="sxs-lookup"><span data-stu-id="f7fe0-175"><span class="stdr-thankyou">Thank you!</span></span></span> <span data-ttu-id="f7fe0-176"><span class="stdr-appreciate">ご意見をお送りいただきありがとうございます。</span></span><span class="sxs-lookup"><span data-stu-id="f7fe0-176"><span class="stdr-appreciate">We appreciate your feedback.</span></span></span>

[<span data-ttu-id="f7fe0-177">プロファイル (個人情報) の管理</span><span class="sxs-lookup"><span data-stu-id="f7fe0-177">Manage Your Profile</span></span>](https://social.technet.microsoft.com/profile)

|

<span data-ttu-id="f7fe0-178"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"><img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span>サイトのフィードバック</a> サイトのフィードバック</span><span class="sxs-lookup"><span data-stu-id="f7fe0-178"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"> <img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span> Site Feedback</a> Site Feedback</span></span>

<span data-ttu-id="f7fe0-179"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">X</a></span><span class="sxs-lookup"><span data-stu-id="f7fe0-179"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">x</a></span></span>

<span data-ttu-id="f7fe0-180">お客様のご体験をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-180">Tell us about your experience...</span></span>

<span data-ttu-id="f7fe0-181">ページはすばやく表示されましたか?</span><span class="sxs-lookup"><span data-stu-id="f7fe0-181">Did the page load quickly?</span></span>

<span data-ttu-id="f7fe0-182"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="f7fe0-182"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="f7fe0-183">ページのデザインは気に入りましたか?</span><span class="sxs-lookup"><span data-stu-id="f7fe0-183">Do you like the page design?</span></span>

<span data-ttu-id="f7fe0-184"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="f7fe0-184"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="f7fe0-185">詳しくお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-185">Tell us more</span></span>

-   [<span data-ttu-id="f7fe0-186">Flash ニュースレター</span><span class="sxs-lookup"><span data-stu-id="f7fe0-186">Flash Newsletter</span></span>](https://technet.microsoft.com/cc543196.aspx)
-   |
-   [<span data-ttu-id="f7fe0-187">お問い合わせ先</span><span class="sxs-lookup"><span data-stu-id="f7fe0-187">Contact Us</span></span>](https://technet.microsoft.com/cc512759.aspx)
-   |
-   [<span data-ttu-id="f7fe0-188">プライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="f7fe0-188">Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
-   |
-   [<span data-ttu-id="f7fe0-189">使用条件</span><span class="sxs-lookup"><span data-stu-id="f7fe0-189">Terms of Use</span></span>](https://technet.microsoft.com/cc300389.aspx)
-   |
-   [<span data-ttu-id="f7fe0-190">商標</span><span class="sxs-lookup"><span data-stu-id="f7fe0-190">Trademarks</span></span>](https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/)
-   |

<span data-ttu-id="f7fe0-191">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="f7fe0-191">© 2016 Microsoft</span></span>

<span data-ttu-id="f7fe0-192">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="f7fe0-192">© 2016 Microsoft</span></span>

<span data-ttu-id="f7fe0-193">サードパーティのスクリプトやコード、サードパーティから本 Web サイトへのリンク、あるいは本サイトからサードパーティへのリンクは、マイクロソフトではなく、そのようなコードの所有者によってお客様にライセンス供与されています。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-193">Third party scripts and code linked to or referenced from this website are licensed to you by the parties that own such code, not by Microsoft.</span></span> <span data-ttu-id="f7fe0-194">ASP.NET Ajax CDN の使用条件 - http://www.asp.net/ajaxlibrary/CDN.ashx を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-194">See ASP.NET Ajax CDN Terms of Use - http://www.asp.net/ajaxlibrary/CDN.ashx.</span></span>
<img src="https://m.webtrends.com/dcsjwb9vb00000c932fd0rjc7_5p3t/njs.gif?dcsuri=/nojavascript&amp;WT.js=No" alt="DCSIMG" id="Img1" width="1" height="1" />

