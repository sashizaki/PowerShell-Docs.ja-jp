---
ms.date: 2017-08-23
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell Web Access のアンインストール"
ms.openlocfilehash: 6b75eadb7264d7478fb3c9bc2b2ff355772ef4c2
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
#  <a name="uninstall-windows-powershell-web-access"></a><span data-ttu-id="d5e7c-103">Windows PowerShell Web Access をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="d5e7c-103">Uninstall Windows PowerShell Web Access</span></span>

<span data-ttu-id="d5e7c-104">最終更新日: 2013 年 6 月 24 日</span><span class="sxs-lookup"><span data-stu-id="d5e7c-104">Updated: June 24, 2013</span></span>

<span data-ttu-id="d5e7c-105">適用対象: Windows Server 2012 R2、Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d5e7c-105">Applies To: Windows Server 2012 R2, Windows Server 2012</span></span>

<span data-ttu-id="d5e7c-106">このトピックの手順で、Windows PowerShell Web Access Web サイトと該当アプリケーションがインストール先のゲートウェイ サーバーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-106">The steps in this topic remove the Windows PowerShell Web Access website and corresponding application from the gateway server where it is installed.</span></span>

## <a name="notify-users"></a><span data-ttu-id="d5e7c-107">ユーザーに通知</span><span class="sxs-lookup"><span data-stu-id="d5e7c-107">Notify users</span></span>

<span data-ttu-id="d5e7c-108">開始する前に、Web サイトを削除することを Web ベース コンソールのユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-108">Before you begin, notify users of the web-based console that you are removing the website.</span></span>


<span data-ttu-id="d5e7c-109">ゲートウェイ サーバーから Windows PowerShell Web Access をアンインストールする前に、`Uninstall-PswaWebApplication` コマンドレットを実行して Web サイトおよび Windows PowerShell Web Access Web アプリケーションを削除するか、IIS マネージャーの手順「[IIS マネージャーを使って Windows PowerShell Web Access Web サイトおよびアプリケーションを削除するには]()」を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-109">Before you uninstall Windows PowerShell Web Access from the gateway server, either run the `Uninstall-PswaWebApplication` cmdlet to remove the website and Windows PowerShell Web Access web applications, or use the IIS Manager procedure, [to delete the windows powershell web access website and web applications by using iis manager]().</span></span>

<span data-ttu-id="d5e7c-110">Windows PowerShell Web Access の実行に必要なため、Windows PowerShell Web Access をアンインストールしても、自動インストールされた IIS その他の機能はアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-110">Uninstalling Windows PowerShell Web Access does not uninstall IIS or any other features that were installed automatically because Windows PowerShell Web Access requires them to run.</span></span> <span data-ttu-id="d5e7c-111">アンインストール プロセスでは、Windows PowerShell Web Access が依存する機能はそのまま残されるため、必要に応じて手動でアンインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-111">The uninstallation process leaves features installed upon which Windows PowerShell Web Access was dependent; you can uninstall those features separately if needed.</span></span>

## <a name="recommended-quick-uninstallation"></a><span data-ttu-id="d5e7c-112">推奨の (クイック) アンインストール</span><span class="sxs-lookup"><span data-stu-id="d5e7c-112">Recommended (quick) uninstallation</span></span>

<span data-ttu-id="d5e7c-113">このセクションの手順では、Windows PowerShell コマンドレットを利用し、</span><span class="sxs-lookup"><span data-stu-id="d5e7c-113">Procedures in this section help you uninstall both:</span></span>

- <span data-ttu-id="d5e7c-114">Windows PowerShell Web Access Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d5e7c-114">the Windows PowerShell Web Access web application, and</span></span>
- <span data-ttu-id="d5e7c-115">と Windows PowerShell Web Access 機能</span><span class="sxs-lookup"><span data-stu-id="d5e7c-115">the Windows PowerShell Web Access feature</span></span>
 
<span data-ttu-id="d5e7c-116">の両方をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-116">by using Windows PowerShell cmdlets.</span></span>

### <a name="step-1-delete-the-web-application-using-cmdlets"></a><span data-ttu-id="d5e7c-117">手順 1: コマンドレットを利用して Web アプリケーションを削除する</span><span class="sxs-lookup"><span data-stu-id="d5e7c-117">Step 1: Delete the web application using cmdlets</span></span>

1. <span data-ttu-id="d5e7c-118">次のいずれかを実行して Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-118">Do one of the following to open a Windows PowerShell session.</span></span>

    -   <span data-ttu-id="d5e7c-119">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-119">On the Windows desktop, right-click **Windows PowerShell** on the taskbar.</span></span>

    -   <span data-ttu-id="d5e7c-120">Windows の**スタート**画面で、**[Windows PowerShell]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-120">On the Windows **Start** screen, click **Windows PowerShell**.</span></span>

2. <span data-ttu-id="d5e7c-121">「`Uninstall-PswaWebApplication`」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-121">Type `Uninstall-PswaWebApplication`, and then press **Enter**.</span></span>
   1. <span data-ttu-id="d5e7c-122">独自のカスタム Web サイト名を指定した場合は、コマンドに `-WebsiteName` パラメーターを追加し、Web サイト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-122">If you have specified your own, custom website name, add the `-WebsiteName` parameter to your command, and specify the website name.</span></span>

        `Uninstall-PswaWebApplication -WebsiteName <web-site-name>`
   1. <span data-ttu-id="d5e7c-123">(既定のアプリケーション **pswa** ではなく) カスタム Web アプリケーションを使用している場合は、コマンドに `-WebApplicationName` パラメーターを追加し、Web アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-123">If you have used a custom web application (not the default application, **pswa**, add the `-WebApplicationName` parameter to your command, and specify the name of the web application.</span></span>

        `Uninstall-PswaWebApplication -WebApplicationName <web-application-name>`
   1. <span data-ttu-id="d5e7c-124">テスト証明書使っている場合、次の例のように `DeleteTestCertificate` パラメーターをコマンドレットに追加します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-124">If you are using a test certificate, add the `DeleteTestCertificate` parameter to the cmdlet, as shown in the following example.</span></span>

        `Uninstall-PswaWebApplication -DeleteTestCertificate`

### <a name="step-2-uninstall-windows-powershell-web-access-using-cmdlets"></a><span data-ttu-id="d5e7c-125">手順 2: コマンドレットを利用し、Windows PowerShell Web Access をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="d5e7c-125">Step 2: Uninstall Windows PowerShell Web Access using cmdlets</span></span>

1.  <span data-ttu-id="d5e7c-126">次のいずれかを実行して、管理者特権を使って Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-126">Do one of the following to open a Windows PowerShell session with elevated user rights.</span></span> <span data-ttu-id="d5e7c-127">セッションを既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-127">If a session is already open, go on to the next step.</span></span>

    -   <span data-ttu-id="d5e7c-128">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-128">On the Windows desktop, right-click **Windows PowerShell** on the taskbar, and then click **Run as Administrator**.</span></span>

    -   <span data-ttu-id="d5e7c-129">Windows の**スタート**画面で、**[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-129">On the Windows **Start** screen, right-click **Windows PowerShell**, and then click **Run as Administrator**.</span></span>

1. <span data-ttu-id="d5e7c-130">次のように入力して **Enter** キーを押します。*computer_name* は、Windows PowerShell Web Access を削除するリモート サーバーです。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-130">Type the following, and then press **Enter**, where *computer_name* represents a remote server from which you want to remove Windows PowerShell Web Access.</span></span> <span data-ttu-id="d5e7c-131">`-Restart` パラメーターによって、対象サーバーが自動的に再起動されます (削除で必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-131">The `-Restart` parameter automatically restarts destination servers if required by the removal.</span></span>

        Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -ComputerName <computer_name> -Restart

    <span data-ttu-id="d5e7c-132">オフライン VHD から役割と機能を削除するには、`-ComputerName` パラメーターと `-VHD` パラメーターの両方を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-132">To remove roles and features from an offline VHD, you must add both the `-ComputerName` parameter and the `-VHD` parameter.</span></span> <span data-ttu-id="d5e7c-133">`-ComputerName` パラメーターには VHD のマウント先のサーバー名が格納され、`-VHD` パラメーターには指定したサーバー上の VHD ファイルへのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-133">The `-ComputerName` parameter contains the name of the server on which to mount the VHD, and the `-VHD` parameter contains the path to the VHD file on the specified server.</span></span>

        Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -VHD <path> -ComputerName <computer_name> -Restart

1. <span data-ttu-id="d5e7c-134">削除が完了したら、Windows PowerShell Web Access が削除されていることを確認します。これには、サーバー マネージャーの **[すべてのサーバー]** ページを開き、機能を削除したサーバーを選択して、選択したサーバーのページで **[役割と機能]** タイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-134">When removal is finished, verify that you removed Windows PowerShell Web Access by opening the **All Servers** page in Server Manager, selecting a server from which you removed the feature, and viewing the **Roles and Features** tile on the page for the selected server.</span></span>

    <span data-ttu-id="d5e7c-135">また、選択したサーバーを対象として `Get-WindowsFeature` コマンドレット (Get-WindowsFeature -ComputerName &lt;*computer_name*&gt;) を実行し、サーバーにインストールされている役割と機能の一覧を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-135">You can also run the `Get-WindowsFeature` cmdlet targeted at the selected server (Get-WindowsFeature -ComputerName &lt;*computer_name*&gt;) to view a list of roles and features that are installed on the server.</span></span>

## <a name="custom-uninstallation"></a><span data-ttu-id="d5e7c-136">カスタム アンインストール</span><span class="sxs-lookup"><span data-stu-id="d5e7c-136">Custom uninstallation</span></span>

<span data-ttu-id="d5e7c-137">このセクションの手順では、サーバー マネージャーの役割と機能の削除ウィザード、および IIS マネージャー コンソールを使用して Windows PowerShell Web Access の Web アプリケーションと Windows PowerShell Web Access 機能の両方をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-137">Procedures in this section help you uninstall both the Windows PowerShell Web Access web application and the Windows PowerShell Web Access feature by using the Remove Roles and Features Wizard in Server Manager, and the IIS Manager console.</span></span>

### <a name="step-1-delete-the-web-application-using-iis-manager"></a><span data-ttu-id="d5e7c-138">手順 1: IIS マネージャーを利用して Web アプリケーションを削除する</span><span class="sxs-lookup"><span data-stu-id="d5e7c-138">Step 1: Delete the web application using IIS Manager</span></span>


1. <span data-ttu-id="d5e7c-139">次のいずれかの方法で IIS マネージャー コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-139">Open the IIS Manager console by doing one of the following.</span></span> <span data-ttu-id="d5e7c-140">既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-140">If it is already open, go on to the next step.</span></span>

    -   <span data-ttu-id="d5e7c-141">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-141">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span> <span data-ttu-id="d5e7c-142">[サーバー マネージャー] の **[ツール]** メニューで **[インターネット インフォメーション サービス (IIS) マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-142">On the **Tools** menu in Server Manager, click **Internet Information Services (IIS) Manager**.</span></span>

    -   <span data-ttu-id="d5e7c-143">Windows の**スタート**画面で、**インターネット インフォメーション サービス (IIS) マネージャー**という名前の任意の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-143">On the Windows **Start** screen, type any part of the name **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="d5e7c-144">**[アプリ]** の結果に表示されたショートカットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-144">Click the shortcut when it is displayed in the **Apps** results.</span></span>

1. <span data-ttu-id="d5e7c-145">IIS マネージャーのツリー ウィンドウで、Windows PowerShell Web Access Web アプリケーションを実行している Web サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-145">In the IIS Manager tree pane, select the website that is running the Windows PowerShell Web Access web application.</span></span>

1. <span data-ttu-id="d5e7c-146">**[操作]** ウィンドウの **[Web サイトの管理]** で **[停止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-146">In the **Actions** pane, under **Manage Website**, click **Stop**.</span></span>

1. <span data-ttu-id="d5e7c-147">ツリー ウィンドウで、Windows PowerShell Web Access Web アプリケーションを実行している Web サイトの Web アプリケーションを右クリックして、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-147">In the tree pane, right-click the web application in the website that is running the Windows PowerShell Web Access web application, and then click **Remove**.</span></span>

1. <span data-ttu-id="d5e7c-148">ツリー ウィンドウで **[アプリケーション プール]** を選択し、Windows PowerShell Web Access アプリケーション プールのフォルダーを選択して、**[操作]** ウィンドウの **[停止]** をクリックし、コンテンツ ウィンドウの **[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-148">In the tree pane, select **Application Pools**, select the Windows PowerShell Web Access application pool folder, click **Stop** in the **Actions** pane, and then click **Remove** in the content pane.</span></span>

1. <span data-ttu-id="d5e7c-149">IIS マネージャーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-149">Close IIS Manager.</span></span>

> <span data-ttu-id="d5e7c-150">![警告](images/SecurityNote.jpeg)**注**:</span><span class="sxs-lookup"><span data-stu-id="d5e7c-150">![Warning note](images/SecurityNote.jpeg)**Note**:</span></span>
>
> <span data-ttu-id="d5e7c-151">アンインストールでは証明書は削除されません。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-151">The certificate is not deleted during uninstallation.</span></span> 
>
> <span data-ttu-id="d5e7c-152">自己署名証明書を作成している場合、または使用したテスト証明書を削除する場合は、IIS マネージャーで証明書を削除できます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-152">If you created a self-signed certificate or used a test certificate and want to remove it, delete the certificate in IIS Manager.</span></span> 

### <a name="step-2-uninstall-windows-powershell-web-access-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="d5e7c-153">手順 2: 役割と機能の削除ウィザードを使って Windows PowerShell Web Access をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="d5e7c-153">Step 2: Uninstall Windows PowerShell Web Access using the Remove Roles and Features Wizard</span></span>

1. <span data-ttu-id="d5e7c-154">サーバー マネージャーを既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-154">If Server Manager is already open, go on to the next step.</span></span> <span data-ttu-id="d5e7c-155">サーバー マネージャーをまだ開いていない場合は、次のいずれかの方法で開きます。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-155">If Server Manager is not already open, open it by doing one of the following.</span></span>

    -   <span data-ttu-id="d5e7c-156">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-156">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span>

    -   <span data-ttu-id="d5e7c-157">Windows の**スタート**画面で、**[サーバー マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-157">On the Windows **Start** screen, click **Server Manager**.</span></span>

1. <span data-ttu-id="d5e7c-158">**[管理]** メニューの **[役割と機能の削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-158">On the **Manage** menu, click **Remove Roles and Features**.</span></span>

1. <span data-ttu-id="d5e7c-159">**[対象サーバーの選択]** ページで、削除対象の機能を備えているサーバーまたはオフライン VHD を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-159">On the **Select destination server** page, select the server or offline VHD from which you want to remove the feature.</span></span> <span data-ttu-id="d5e7c-160">オフライン VHD を選択するには、最初に VHD マウント先のサーバーを選択してから、VHD ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-160">To select an offline VHD, first select the server on which to mount the VHD, and then select the VHD file.</span></span> <span data-ttu-id="d5e7c-161">対象サーバーを選択したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-161">After you have selected the destination server, click **Next**.</span></span>

1. <span data-ttu-id="d5e7c-162">もう一度 **[次へ]** をクリックして **[機能の削除]** ページにスキップします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-162">Click **Next** again to skip to the **Remove features** page.</span></span>

1. <span data-ttu-id="d5e7c-163">**[Windows PowerShell Web Access]** のチェック ボックスをすべてオフにして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-163">Clear the check box for **Windows PowerShell Web Access**, and then click **Next**.</span></span>

1. <span data-ttu-id="d5e7c-164">**[削除オプションの確認]** ページで、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e7c-164">On the **Confirm removal selections** page, click **Remove**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5e7c-165">参照</span><span class="sxs-lookup"><span data-stu-id="d5e7c-165">See Also</span></span>

- [<span data-ttu-id="d5e7c-166">Windows PowerShell Web Access のインストールと使用</span><span class="sxs-lookup"><span data-stu-id="d5e7c-166">Install and Use Windows PowerShell Web Access</span></span>](install-and-use-windows-powershell-web-access.md)
- [<span data-ttu-id="d5e7c-167">IIS マネージャー 7.0 ヘルプ</span><span class="sxs-lookup"><span data-stu-id="d5e7c-167">IIS Manager 7.0 Help</span></span>](https://technet.microsoft.com/library/cc732664.aspx)
