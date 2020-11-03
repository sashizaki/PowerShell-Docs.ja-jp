---
description: Windows PowerShell の WS-Management コマンドレットを使用するための背景としての Web Services for Management (WS-MANAGEMENT) の概要について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WS Management_Cmdlets
ms.openlocfilehash: 8bb63126ae9a3b73e2e09e4c8da8f0aeaffd270c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221032"
---
# <a name="about-ws-management-cmdlets"></a><span data-ttu-id="5ea4f-104">WS-Management のコマンドレットについて</span><span class="sxs-lookup"><span data-stu-id="5ea4f-104">About WS-Management Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="5ea4f-105">概要</span><span class="sxs-lookup"><span data-stu-id="5ea4f-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="5ea4f-106">Windows PowerShell の WS-Management コマンドレットを使用するための背景としての Web Services for Management (WS-MANAGEMENT) の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-106">Provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="5ea4f-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="5ea4f-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="5ea4f-108">このトピックでは、Windows PowerShell の WS-Management コマンドレットを使用するための背景としての Web Services for Management (WS-MANAGEMENT) の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-108">This topic provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span> <span data-ttu-id="5ea4f-109">このトピックでは、WS-MANAGEMENT に関する詳細情報へのリンクも示します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-109">This topic also provides links to more information about WS-Management.</span></span> <span data-ttu-id="5ea4f-110">Microsoft による WS-Management の実装は、Windows リモート管理 (WinRM) とも呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-110">The Microsoft implementation of WS-Management is also known as Windows Remote Management (WinRM).</span></span>

## <a name="about-ws-management"></a><span data-ttu-id="5ea4f-111">WS-Management について</span><span class="sxs-lookup"><span data-stu-id="5ea4f-111">About WS-Management</span></span>

<span data-ttu-id="5ea4f-112">Windows リモート管理は、WS-Management プロトコルの Microsoft による実装であり、さまざまなベンダーのハードウェアおよびオペレーティングシステムが相互運用できる標準の SOAP ベースのファイアウォール対応プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-112">Windows Remote Management is the Microsoft implementation of the WS-Management protocol, a standard SOAP-based, firewall-friendly protocol that allows hardware and operating systems from different vendors to interoperate.</span></span> <span data-ttu-id="5ea4f-113">WS-Management プロトコル仕様は、情報技術 (IT) インフラストラクチャを介してシステムが管理情報にアクセスして交換するための一般的な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-113">The WS-Management protocol specification provides a common way for systems to access and exchange management information across an information technology (IT) infrastructure.</span></span> <span data-ttu-id="5ea4f-114">WS-Management とインテリジェントなプラットフォーム管理インターフェイス (IPMI) は、イベントコレクターと共に、Windows ハードウェア管理機能のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-114">WS-Management and Intelligent Platform Management Interface (IPMI), along with the Event Collector, are components of the Windows Hardware Management features.</span></span>

<span data-ttu-id="5ea4f-115">WS-Management プロトコルは、次の標準 Web サービス仕様に基づいています: HTTPS、SOAP over HTTP (WS-I profile)、SOAP 1.2、WS-ADDRESSING、WS-FEDERATION、WS 列挙型、および WS-I イベント。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-115">The WS-Management protocol is based on the following standard Web service specifications: HTTPS, SOAP over HTTP (WS-I profile), SOAP 1.2, WS-Addressing, WS-Transfer, WS-Enumeration, and WS-Eventing.</span></span>

## <a name="ws-management-and-wmi"></a><span data-ttu-id="5ea4f-116">WS-Management と WMI</span><span class="sxs-lookup"><span data-stu-id="5ea4f-116">WS-Management and WMI</span></span>

<span data-ttu-id="5ea4f-117">WS-Management は、Windows Management Instrumentation (WMI) によって公開されるデータを取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-117">WS-Management can be used to retrieve data exposed by Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="5ea4f-118">WMI データは、WS-Management スクリプト API または WinRM コマンドラインツールを使用するスクリプトまたはアプリケーションを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-118">You can obtain WMI data with scripts or applications that use the WS-Management Scripting API or through the WinRM command-line tool.</span></span> <span data-ttu-id="5ea4f-119">WS-Management は、埋め込みオブジェクトなど、使い慣れた WMI のクラスと操作の大部分をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-119">WS-Management supports most of the familiar WMI classes and operations, including embedded objects.</span></span> <span data-ttu-id="5ea4f-120">WS-Management は、WMI を利用して、リソースに関するデータを収集したり、Windows ベースのコンピューター上のリソースを管理したりできます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-120">WS-Management can leverage WMI to collect data about resources or to manage resources on a Windows-based computers.</span></span> <span data-ttu-id="5ea4f-121">つまり、既存の WMI クラスのセットを使用して、企業内のディスク、ネットワークアダプター、サービス、プロセスなどのオブジェクトに関するデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-121">That means that you can obtain data about objects such as disks, network adapters, services, or processes in your enterprise through the existing set of WMI classes.</span></span> <span data-ttu-id="5ea4f-122">標準の WMI IPMI プロバイダーから利用可能なハードウェアデータにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-122">You can also access the hardware data that is available from the standard WMI IPMI provider.</span></span>

## <a name="ws-management-windows-powershell-provider-wsman"></a><span data-ttu-id="5ea4f-123">Windows PowerShell プロバイダー (WSMan) の WS-Management</span><span class="sxs-lookup"><span data-stu-id="5ea4f-123">WS-Management Windows PowerShell Provider (WSMan)</span></span>

<span data-ttu-id="5ea4f-124">WSMan プロバイダーは、使用可能な WS-Management 構成設定の階層ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-124">The WSMan provider provides a hierarchical view into the available WS-Management configuration settings.</span></span> <span data-ttu-id="5ea4f-125">プロバイダーでは、さまざまな WS-Management 構成オプションを調べて設定することができます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-125">The provider allows you to explore and set the various WS-Management configuration options.</span></span>

## <a name="ws-management-configuration"></a><span data-ttu-id="5ea4f-126">WS-Management 構成</span><span class="sxs-lookup"><span data-stu-id="5ea4f-126">WS-Management Configuration</span></span>

<span data-ttu-id="5ea4f-127">WS-Management がインストールおよび構成されていない場合、Windows PowerShell リモート処理は使用できません。 WS-Management のコマンドレットは実行されず、WS-Management スクリプトは実行されず、WSMan プロバイダーはデータ操作を実行できません。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-127">If WS-Management is not installed and configured, Windows PowerShell remoting is not available, the WS-Management cmdlets do not run, WS-Management scripts do not run, and the WSMan provider cannot perform data operations.</span></span> <span data-ttu-id="5ea4f-128">WS-Management コマンドラインツール、WinRM、およびイベント転送は、WS-Management の構成にも依存します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-128">The WS-Management command-line tool, WinRM, and event forwarding also depend on the WS-Management configuration.</span></span>

## <a name="ws-management-cmdlets"></a><span data-ttu-id="5ea4f-129">WS-Management コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5ea4f-129">WS-Management Cmdlets</span></span>

<span data-ttu-id="5ea4f-130">WS-Management 機能は、一連のコマンドレットと WSMan プロバイダーを含むモジュールを使用して、Windows PowerShell に実装されます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-130">WS-Management functionality is implemented in Windows PowerShell through a module that contains a set of cmdlets and the WSMan provider.</span></span> <span data-ttu-id="5ea4f-131">これらのコマンドレットを使用して、ローカルコンピューターとリモートコンピューターの WS-Management 設定を管理するために必要なエンドツーエンドのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-131">You can use these cmdlets to complete the end-to-end tasks necessary to manage WS-Management settings on local and remote computers.</span></span>

<span data-ttu-id="5ea4f-132">次の WS-Management コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-132">The following WS-Management cmdlets are available.</span></span>

## <a name="connection-cmdlets"></a><span data-ttu-id="5ea4f-133">接続コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5ea4f-133">Connection Cmdlets</span></span>

- <span data-ttu-id="5ea4f-134">接続-WSMan: ローカルコンピューターをリモートコンピューター上の WS-Management (WinRM) サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-134">Connect-WSMan: Connects the local computer to the WS-Management (WinRM) service on a remote computer.</span></span>

- <span data-ttu-id="5ea4f-135">切断-WSMan: ローカルコンピューターをリモートコンピューター上の WS-Management (WinRM) サービスから切断します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-135">Disconnect-WSMan: Disconnects the local computer from the WS-Management (WinRM) service on a remote computer.</span></span>

## <a name="management-data-cmdlets"></a><span data-ttu-id="5ea4f-136">Management-Data コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5ea4f-136">Management-Data Cmdlets</span></span>

- <span data-ttu-id="5ea4f-137">Get-WSManInstance: リソース URI によって指定されたリソースインスタンスの管理情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-137">Get-WSManInstance: Displays management information for a resource instance that is specified by a resource URI.</span></span>

- <span data-ttu-id="5ea4f-138">Invoke-WSManAction: リソース URI およびセレクターによって指定されたターゲットオブジェクトに対してアクションを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-138">Invoke-WSManAction: Invokes an action on the target object that is specified by the resource URI and by the selectors.</span></span>

- <span data-ttu-id="5ea4f-139">新規-WSManInstance: 新しい管理リソースインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-139">New-WSManInstance: Creates a new management resource instance.</span></span>

- <span data-ttu-id="5ea4f-140">-WSManInstance の削除: 管理リソースインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-140">Remove-WSManInstance: Deletes a management resource instance.</span></span>

- <span data-ttu-id="5ea4f-141">設定-WSManInstance: リソースに関連する管理情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-141">Set-WSManInstance: Modifies the management information that is related to a resource.</span></span>

## <a name="setup-and-configuration-cmdlets"></a><span data-ttu-id="5ea4f-142">セットアップと構成のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5ea4f-142">Setup and Configuration Cmdlets</span></span>

- <span data-ttu-id="5ea4f-143">Set-wsmanquickconfig: リモート管理用にローカルコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-143">Set-WSManQuickConfig: Configures the local computer for remote management.</span></span>
  <span data-ttu-id="5ea4f-144">Set-WSManQuickConfig コマンドレットを使用して WS-Management を構成し、WS-Management (WinRM) サービスへのリモート接続を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-144">You can use the Set-WSManQuickConfig cmdlet to configure WS-Management to allow remote connections to the WS-Management (WinRM) service.</span></span> <span data-ttu-id="5ea4f-145">Set-WSManQuickConfig コマンドレットは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-145">The Set-WSManQuickConfig cmdlet performs the following operations:</span></span>
  - <span data-ttu-id="5ea4f-146">WS-Management (WinRM) サービスが実行されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-146">It determines whether the WS-Management (WinRM) service is running.</span></span> <span data-ttu-id="5ea4f-147">WinRM サービスが実行されていない場合は、Set-WSManQuickConfig コマンドレットによってサービスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-147">If the WinRM service is not running, the Set-WSManQuickConfig cmdlet starts the service.</span></span>
  - <span data-ttu-id="5ea4f-148">WS-Management (WinRM) サービスのスタートアップの種類が [自動] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-148">It sets the WS-Management (WinRM) service startup type to automatic.</span></span>
  - <span data-ttu-id="5ea4f-149">任意の IP アドレスからの要求を受け入れるリスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-149">It creates a listener that accepts requests from any IP address.</span></span> <span data-ttu-id="5ea4f-150">既定のトランスポートプロトコルは HTTP です。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-150">The default transport protocol is HTTP.</span></span>
  - <span data-ttu-id="5ea4f-151">WS-Management トラフィックに対してファイアウォールの例外を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-151">It enables a firewall exception for WS-Management traffic.</span></span>

  <span data-ttu-id="5ea4f-152">注: windows Vista、Windows Server 2008、およびそれ以降のバージョンの Windows でこのコマンドレットを実行するには、[管理者として実行] オプションを使用して Windows PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-152">Note: To run this cmdlet in Windows Vista, Windows Server 2008, and later versions of Windows, you must start Windows PowerShell with the "Run as administrator" option.</span></span>

- <span data-ttu-id="5ea4f-153">テスト WSMan: WS-Management がインストールおよび構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-153">Test-WSMan: Verifies that WS-Management is installed and configured.</span></span> <span data-ttu-id="5ea4f-154">Test-WSMan コマンドレットは、WS-Management (WinRM) サービスが実行されていて、ローカルまたはリモートのコンピューターで構成されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-154">The Test-WSMan cmdlet tests whether the WS-Management (WinRM) service is running and configured on a local or remote computer.</span></span>

- <span data-ttu-id="5ea4f-155">Enable-wsmancredssp: クライアントコンピューターで CredSSP 認証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-155">Disable-WSManCredSSP: Disables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="5ea4f-156">Enable-wsmancredssp: クライアントコンピューターで CredSSP 認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-156">Enable-WSManCredSSP: Enables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="5ea4f-157">Enable-wsmancredssp: クライアントコンピューターの CredSSP 関連の構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-157">Get-WSManCredSSP: Gets the CredSSP-related configuration for a client computer.</span></span>

## <a name="ws-management-specific-cmdlets"></a><span data-ttu-id="5ea4f-158">WS-MANAGEMENT 固有のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5ea4f-158">WS-Management-Specific Cmdlets</span></span>

- <span data-ttu-id="5ea4f-159">New-WSManSessionOption: WS-Management コマンドレットの1つ以上のパラメーターへの入力として使用する WSManSessionOption オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-159">New-WSManSessionOption: Creates a WSManSessionOption object to use as input to one or more parameters of a WS-Management cmdlet.</span></span>

## <a name="additional-ws-management-information"></a><span data-ttu-id="5ea4f-160">その他の WS-Management 情報</span><span class="sxs-lookup"><span data-stu-id="5ea4f-160">Additional WS-Management Information</span></span>

<span data-ttu-id="5ea4f-161">WS-MANAGEMENT の詳細については、MSDN (Microsoft Developer Network) ライブラリの次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ea4f-161">For more information about WS-Management, see the following topics in the MSDN (Microsoft Developer Network) library.</span></span>

[<span data-ttu-id="5ea4f-162">Windows リモート管理</span><span class="sxs-lookup"><span data-stu-id="5ea4f-162">Windows Remote Management</span></span>](/windows/win32/winrm/portal)

[<span data-ttu-id="5ea4f-163">Windows リモート管理について</span><span class="sxs-lookup"><span data-stu-id="5ea4f-163">About Windows Remote Management</span></span>](/windows/win32/winrm/about-windows-remote-management)

[<span data-ttu-id="5ea4f-164">Windows リモート管理のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="5ea4f-164">Installation and Configuration for Windows Remote Management</span></span>](/windows/win32/winrm/installation-and-configuration-for-windows-remote-management)

[<span data-ttu-id="5ea4f-165">Windows リモート管理アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="5ea4f-165">Windows Remote Management Architecture</span></span>](/windows/win32/winrm/windows-remote-management-architecture)

[<span data-ttu-id="5ea4f-166">WS-Management Protocol (WS-Management プロトコル)</span><span class="sxs-lookup"><span data-stu-id="5ea4f-166">WS-Management Protocol</span></span>](/windows/win32/winrm/ws-management-protocol)

[<span data-ttu-id="5ea4f-167">Windows リモート管理と WMI</span><span class="sxs-lookup"><span data-stu-id="5ea4f-167">Windows Remote Management and WMI</span></span>](/windows/win32/winrm/windows-remote-management-and-wmi)

[<span data-ttu-id="5ea4f-168">リソース URI</span><span class="sxs-lookup"><span data-stu-id="5ea4f-168">Resource URIs</span></span>](/windows/win32/winrm/resource-uris)

[<span data-ttu-id="5ea4f-169">リモートハードウェア管理</span><span class="sxs-lookup"><span data-stu-id="5ea4f-169">Remote Hardware Management</span></span>](/windows/win32/winrm/remote-hardware-management)

[<span data-ttu-id="5ea4f-170">イベント</span><span class="sxs-lookup"><span data-stu-id="5ea4f-170">Events</span></span>](/windows/win32/winrm/events)

## <a name="see-also"></a><span data-ttu-id="5ea4f-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ea4f-171">SEE ALSO</span></span>

[<span data-ttu-id="5ea4f-172">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="5ea4f-172">Connect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Connect-WSMan)

[<span data-ttu-id="5ea4f-173">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="5ea4f-173">Disable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Disable-WSManCredSSP)

[<span data-ttu-id="5ea4f-174">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="5ea4f-174">Disconnect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Disconnect-WSMan)

[<span data-ttu-id="5ea4f-175">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="5ea4f-175">Enable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Enable-WSManCredSSP)

[<span data-ttu-id="5ea4f-176">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="5ea4f-176">Get-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Get-WSManCredSSP)

[<span data-ttu-id="5ea4f-177">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="5ea4f-177">Get-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Get-WSManInstance)

[<span data-ttu-id="5ea4f-178">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="5ea4f-178">Invoke-WSManAction</span></span>](xref:Microsoft.WSMan.Management.Invoke-WSManAction)

[<span data-ttu-id="5ea4f-179">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="5ea4f-179">New-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.New-WSManInstance)

[<span data-ttu-id="5ea4f-180">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="5ea4f-180">Remove-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Remove-WSManInstance)

[<span data-ttu-id="5ea4f-181">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="5ea4f-181">Set-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Set-WSManInstance)

[<span data-ttu-id="5ea4f-182">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="5ea4f-182">Set-WSManQuickConfig</span></span>](xref:Microsoft.WSMan.Management.Set-WSManQuickConfig)

[<span data-ttu-id="5ea4f-183">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="5ea4f-183">Test-WSMan</span></span>](xref:Microsoft.WSMan.Management.Test-WSMan)
