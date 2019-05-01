---
ms.date: 08/23/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell Web Access のアンインストール
ms.openlocfilehash: 22c874d766445dccedd8494097daf16c30fa66ff
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058151"
---
# <a name="uninstall-windows-powershell-web-access"></a><span data-ttu-id="b7cfa-103">Windows PowerShell Web Access をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="b7cfa-103">Uninstall Windows PowerShell Web Access</span></span>

<span data-ttu-id="b7cfa-104">更新:2013 年 6 月 24 日</span><span class="sxs-lookup"><span data-stu-id="b7cfa-104">Updated: June 24, 2013</span></span>

<span data-ttu-id="b7cfa-105">適用先:Windows Server 2012 R2、Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b7cfa-105">Applies To: Windows Server 2012 R2, Windows Server 2012</span></span>

<span data-ttu-id="b7cfa-106">このトピックの手順で、Windows PowerShell Web Access Web サイトと該当アプリケーションがインストール先のゲートウェイ サーバーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-106">The steps in this topic remove the Windows PowerShell Web Access website and corresponding application from the gateway server where it is installed.</span></span>

## <a name="notify-users"></a><span data-ttu-id="b7cfa-107">ユーザーに通知</span><span class="sxs-lookup"><span data-stu-id="b7cfa-107">Notify users</span></span>

<span data-ttu-id="b7cfa-108">開始する前に、Web サイトを削除することを Web ベース コンソールのユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-108">Before you begin, notify users of the web-based console that you are removing the website.</span></span>

<span data-ttu-id="b7cfa-109">Windows PowerShell Web Access の実行に必要なため、Windows PowerShell Web Access をアンインストールしても、自動インストールされた IIS その他の機能はアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-109">Uninstalling Windows PowerShell Web Access does not uninstall IIS or any other features that were installed automatically because Windows PowerShell Web Access requires them to run.</span></span>
<span data-ttu-id="b7cfa-110">アンインストール プロセスでは、Windows PowerShell Web Access が依存する機能はそのまま残されるため、必要に応じて手動でアンインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-110">The uninstallation process leaves features installed upon which Windows PowerShell Web Access was dependent; you can uninstall those features separately if needed.</span></span>

## <a name="recommended-quick-uninstallation"></a><span data-ttu-id="b7cfa-111">推奨の (クイック) アンインストール</span><span class="sxs-lookup"><span data-stu-id="b7cfa-111">Recommended (quick) uninstallation</span></span>

<span data-ttu-id="b7cfa-112">このセクションの手順では、Windows PowerShell コマンドレットを利用し、</span><span class="sxs-lookup"><span data-stu-id="b7cfa-112">Procedures in this section help you uninstall both:</span></span>

- <span data-ttu-id="b7cfa-113">Windows PowerShell Web Access Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b7cfa-113">the Windows PowerShell Web Access web application, and</span></span>
- <span data-ttu-id="b7cfa-114">と Windows PowerShell Web Access 機能</span><span class="sxs-lookup"><span data-stu-id="b7cfa-114">the Windows PowerShell Web Access feature</span></span>

<span data-ttu-id="b7cfa-115">の両方をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-115">by using Windows PowerShell cmdlets.</span></span>

### <a name="step-1-delete-the-web-application-using-cmdlets"></a><span data-ttu-id="b7cfa-116">手順 1:コマンドレットを利用して Web アプリケーションを削除する</span><span class="sxs-lookup"><span data-stu-id="b7cfa-116">Step 1: Delete the web application using cmdlets</span></span>

1. <span data-ttu-id="b7cfa-117">次のいずれかを実行して Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-117">Do one of the following to open a Windows PowerShell session.</span></span>

    -   <span data-ttu-id="b7cfa-118">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-118">On the Windows desktop, right-click **Windows PowerShell** on the taskbar.</span></span>

    -   <span data-ttu-id="b7cfa-119">Windows の**スタート**画面で、**[Windows PowerShell]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-119">On the Windows **Start** screen, click **Windows PowerShell**.</span></span>

2. <span data-ttu-id="b7cfa-120">「`Uninstall-PswaWebApplication`」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-120">Type `Uninstall-PswaWebApplication`, and then press **Enter**.</span></span>
   1. <span data-ttu-id="b7cfa-121">独自のカスタム Web サイト名を指定した場合は、コマンドに `-WebsiteName` パラメーターを追加し、Web サイト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-121">If you have specified your own, custom website name, add the `-WebsiteName` parameter to your command, and specify the website name.</span></span>

        `Uninstall-PswaWebApplication -WebsiteName <web-site-name>`
   1. <span data-ttu-id="b7cfa-122">(既定のアプリケーション **pswa** ではなく) カスタム Web アプリケーションを使用している場合は、コマンドに `-WebApplicationName` パラメーターを追加し、Web アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-122">If you have used a custom web application (not the default application, **pswa**, add the `-WebApplicationName` parameter to your command, and specify the name of the web application.</span></span>

        `Uninstall-PswaWebApplication -WebApplicationName <web-application-name>`
   1. <span data-ttu-id="b7cfa-123">テスト証明書使っている場合、次の例のように `DeleteTestCertificate` パラメーターをコマンドレットに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-123">If you are using a test certificate, add the `DeleteTestCertificate` parameter to the cmdlet, as shown in the following example.</span></span>

        `Uninstall-PswaWebApplication -DeleteTestCertificate`

### <a name="step-2-uninstall-windows-powershell-web-access-using-cmdlets"></a><span data-ttu-id="b7cfa-124">手順 2:コマンドレットを利用し、Windows PowerShell Web Access をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="b7cfa-124">Step 2: Uninstall Windows PowerShell Web Access using cmdlets</span></span>

1. <span data-ttu-id="b7cfa-125">次のいずれかを実行して、管理者特権を使って Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-125">Do one of the following to open a Windows PowerShell session with elevated user rights.</span></span> <span data-ttu-id="b7cfa-126">セッションを既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-126">If a session is already open, go on to the next step.</span></span>

    -   <span data-ttu-id="b7cfa-127">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-127">On the Windows desktop, right-click **Windows PowerShell** on the taskbar, and then click **Run as Administrator**.</span></span>

    -   <span data-ttu-id="b7cfa-128">Windows の**スタート**画面で、**[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-128">On the Windows **Start** screen, right-click **Windows PowerShell**, and then click **Run as Administrator**.</span></span>

1. <span data-ttu-id="b7cfa-129">次のように入力して **Enter** キーを押します。*computer_name* は、Windows PowerShell Web Access を削除するリモート サーバーです。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-129">Type the following, and then press **Enter**, where *computer_name* represents a remote server from which you want to remove Windows PowerShell Web Access.</span></span> <span data-ttu-id="b7cfa-130">`-Restart` パラメーターによって、対象サーバーが自動的に再起動されます (削除で必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-130">The `-Restart` parameter automatically restarts destination servers if required by the removal.</span></span>

        Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -ComputerName <computer_name> -Restart

    <span data-ttu-id="b7cfa-131">オフライン VHD から役割と機能を削除するには、 `-ComputerName` パラメーターと `-VHD` パラメーターの両方を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-131">To remove roles and features from an offline VHD, you must add both the `-ComputerName` parameter and the `-VHD` parameter.</span></span> <span data-ttu-id="b7cfa-132">`-ComputerName` パラメーターには VHD のマウント先のサーバー名が格納され、 `-VHD` パラメーターには指定したサーバー上の VHD ファイルへのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-132">The `-ComputerName` parameter contains the name of the server on which to mount the VHD, and the `-VHD` parameter contains the path to the VHD file on the specified server.</span></span>

        Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -VHD <path> -ComputerName <computer_name> -Restart

1. <span data-ttu-id="b7cfa-133">削除が完了したら、Windows PowerShell Web Access が削除されていることを確認します。これには、サーバー マネージャーの **[すべてのサーバー]** ページを開き、機能を削除したサーバーを選択して、選択したサーバーのページで **[役割と機能]** タイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-133">When removal is finished, verify that you removed Windows PowerShell Web Access by opening the **All Servers** page in Server Manager, selecting a server from which you removed the feature, and viewing the **Roles and Features** tile on the page for the selected server.</span></span>

    <span data-ttu-id="b7cfa-134">また、選択したサーバーを対象として `Get-WindowsFeature` コマンドレット (Get-WindowsFeature -ComputerName &lt;*computer_name*&gt;) を実行し、サーバーにインストールされている役割と機能の一覧を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-134">You can also run the `Get-WindowsFeature` cmdlet targeted at the selected server (Get-WindowsFeature -ComputerName &lt;*computer_name*&gt;) to view a list of roles and features that are installed on the server.</span></span>

## <a name="custom-uninstallation"></a><span data-ttu-id="b7cfa-135">カスタム アンインストール</span><span class="sxs-lookup"><span data-stu-id="b7cfa-135">Custom uninstallation</span></span>

<span data-ttu-id="b7cfa-136">このセクションの手順では、サーバー マネージャーの役割と機能の削除ウィザード、および IIS マネージャー コンソールを使用して Windows PowerShell Web Access の Web アプリケーションと Windows PowerShell Web Access 機能の両方をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-136">Procedures in this section help you uninstall both the Windows PowerShell Web Access web application and the Windows PowerShell Web Access feature by using the Remove Roles and Features Wizard in Server Manager, and the IIS Manager console.</span></span>

### <a name="step-1-delete-the-web-application-using-iis-manager"></a><span data-ttu-id="b7cfa-137">手順 1:IIS マネージャーを利用して Web アプリケーションを削除する</span><span class="sxs-lookup"><span data-stu-id="b7cfa-137">Step 1: Delete the web application using IIS Manager</span></span>


1. <span data-ttu-id="b7cfa-138">次のいずれかの方法で IIS マネージャー コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-138">Open the IIS Manager console by doing one of the following.</span></span> <span data-ttu-id="b7cfa-139">既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-139">If it is already open, go on to the next step.</span></span>

    -   <span data-ttu-id="b7cfa-140">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-140">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span> <span data-ttu-id="b7cfa-141">[サーバー マネージャー] の **[ツール]** メニューで **[インターネット インフォメーション サービス (IIS) マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-141">On the **Tools** menu in Server Manager, click **Internet Information Services (IIS) Manager**.</span></span>

    -   <span data-ttu-id="b7cfa-142">Windows の**スタート**画面で、**インターネット インフォメーション サービス (IIS) マネージャー**という名前の任意の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-142">On the Windows **Start** screen, type any part of the name **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="b7cfa-143">**[アプリ]** の結果に表示されたショートカットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-143">Click the shortcut when it is displayed in the **Apps** results.</span></span>

1. <span data-ttu-id="b7cfa-144">IIS マネージャーのツリー ウィンドウで、Windows PowerShell Web Access Web アプリケーションを実行している Web サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-144">In the IIS Manager tree pane, select the website that is running the Windows PowerShell Web Access web application.</span></span>

1. <span data-ttu-id="b7cfa-145">**[操作]** ウィンドウの **[Web サイトの管理]** で **[停止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-145">In the **Actions** pane, under **Manage Website**, click **Stop**.</span></span>

1. <span data-ttu-id="b7cfa-146">ツリー ウィンドウで、Windows PowerShell Web Access Web アプリケーションを実行している Web サイトの Web アプリケーションを右クリックして、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-146">In the tree pane, right-click the web application in the website that is running the Windows PowerShell Web Access web application, and then click **Remove**.</span></span>

1. <span data-ttu-id="b7cfa-147">ツリー ウィンドウで **[アプリケーション プール]** を選択し、Windows PowerShell Web Access アプリケーション プールのフォルダーを選択して、**[操作]** ウィンドウの **[停止]** をクリックし、コンテンツ ウィンドウの **[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-147">In the tree pane, select **Application Pools**, select the Windows PowerShell Web Access application pool folder, click **Stop** in the **Actions** pane, and then click **Remove** in the content pane.</span></span>

1. <span data-ttu-id="b7cfa-148">IIS マネージャーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-148">Close IIS Manager.</span></span>

> <span data-ttu-id="b7cfa-149">![警告](images/SecurityNote.jpeg)**注**:</span><span class="sxs-lookup"><span data-stu-id="b7cfa-149">![Warning note](images/SecurityNote.jpeg)**Note**:</span></span>
>
> <span data-ttu-id="b7cfa-150">アンインストールでは証明書は削除されません。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-150">The certificate is not deleted during uninstallation.</span></span>
>
> <span data-ttu-id="b7cfa-151">自己署名証明書を作成している場合、または使用したテスト証明書を削除する場合は、IIS マネージャーで証明書を削除できます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-151">If you created a self-signed certificate or used a test certificate and want to remove it, delete the certificate in IIS Manager.</span></span>

### <a name="step-2-uninstall-windows-powershell-web-access-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="b7cfa-152">手順 2:役割と機能の削除ウィザードを使って Windows PowerShell Web Access をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="b7cfa-152">Step 2: Uninstall Windows PowerShell Web Access using the Remove Roles and Features Wizard</span></span>

1. <span data-ttu-id="b7cfa-153">サーバー マネージャーを既に開いている場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-153">If Server Manager is already open, go on to the next step.</span></span> <span data-ttu-id="b7cfa-154">サーバー マネージャーをまだ開いていない場合は、次のいずれかの方法で開きます。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-154">If Server Manager is not already open, open it by doing one of the following.</span></span>

    -   <span data-ttu-id="b7cfa-155">Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-155">On the Windows desktop, start Server Manager by clicking **Server Manager** in the Windows taskbar.</span></span>

    -   <span data-ttu-id="b7cfa-156">Windows の**スタート**画面で、**[サーバー マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-156">On the Windows **Start** screen, click **Server Manager**.</span></span>

1. <span data-ttu-id="b7cfa-157">**[管理]** メニューの **[役割と機能の削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-157">On the **Manage** menu, click **Remove Roles and Features**.</span></span>

1. <span data-ttu-id="b7cfa-158">**[対象サーバーの選択]** ページで、削除対象の機能を備えているサーバーまたはオフライン VHD を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-158">On the **Select destination server** page, select the server or offline VHD from which you want to remove the feature.</span></span> <span data-ttu-id="b7cfa-159">オフライン VHD を選択するには、最初に VHD マウント先のサーバーを選択してから、VHD ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-159">To select an offline VHD, first select the server on which to mount the VHD, and then select the VHD file.</span></span> <span data-ttu-id="b7cfa-160">対象サーバーを選択したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-160">After you have selected the destination server, click **Next**.</span></span>

1. <span data-ttu-id="b7cfa-161">もう一度 **[次へ]** をクリックして **[機能の削除]** ページにスキップします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-161">Click **Next** again to skip to the **Remove features** page.</span></span>

1. <span data-ttu-id="b7cfa-162">**[Windows PowerShell Web Access]** のチェック ボックスをすべてオフにして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-162">Clear the check box for **Windows PowerShell Web Access**, and then click **Next**.</span></span>

1. <span data-ttu-id="b7cfa-163">**[削除オプションの確認]** ページで、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-163">On the **Confirm removal selections** page, click **Remove**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7cfa-164">参照</span><span class="sxs-lookup"><span data-stu-id="b7cfa-164">See Also</span></span>

- [<span data-ttu-id="b7cfa-165">Windows PowerShell Web Access のインストールと使用</span><span class="sxs-lookup"><span data-stu-id="b7cfa-165">Install and Use Windows PowerShell Web Access</span></span>](install-and-use-windows-powershell-web-access.md)
- [<span data-ttu-id="b7cfa-166">IIS マネージャー 7.0 ヘルプ</span><span class="sxs-lookup"><span data-stu-id="b7cfa-166">IIS Manager 7.0 Help</span></span>](https://technet.microsoft.com/library/cc732664.aspx)