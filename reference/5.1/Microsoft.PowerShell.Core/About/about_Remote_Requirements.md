---
description: PowerShell でリモートコマンドを実行するためのシステム要件と構成要件について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_requirements?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Requirements
ms.openlocfilehash: 63971aeaa92eb10a745f2a02e0c7cf00dbf65d8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223267"
---
# <a name="about-remote-requirements"></a><span data-ttu-id="0327e-104">リモートの要件について</span><span class="sxs-lookup"><span data-stu-id="0327e-104">About Remote Requirements</span></span>

## <a name="short-description"></a><span data-ttu-id="0327e-105">概要</span><span class="sxs-lookup"><span data-stu-id="0327e-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="0327e-106">PowerShell でリモートコマンドを実行するためのシステム要件と構成要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="0327e-106">Describes the system requirements and configuration requirements for running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0327e-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="0327e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0327e-108">このトピックでは、PowerShell でリモート接続を確立し、リモートコマンドを実行するためのシステム要件、ユーザー要件、およびリソース要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="0327e-108">This topic describes the system requirements, user requirements, and resource requirements for establishing remote connections and running remote commands in PowerShell.</span></span> <span data-ttu-id="0327e-109">また、リモート操作を構成する手順についても説明します。</span><span class="sxs-lookup"><span data-stu-id="0327e-109">It also provides instructions for configuring remote operations.</span></span>

<span data-ttu-id="0327e-110">注: 多くのコマンドレット (Get Service、Get-wmiobject、、Get EventLog、および Get-WinEvent コマンドレットを含む) は、オブジェクトを取得するために Microsoft .NET Framework メソッドを使用してリモートコンピューターからオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="0327e-110">Note: Many cmdlets (including the Get-Service, Get-Process, Get-WMIObject, Get-EventLog, and Get-WinEvent cmdlets) get objects from remote computers by using Microsoft .NET Framework methods to retrieve the objects.</span></span> <span data-ttu-id="0327e-111">PowerShell リモート処理インフラストラクチャは使用しません。</span><span class="sxs-lookup"><span data-stu-id="0327e-111">They do not use the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="0327e-112">このドキュメントの要件は、これらのコマンドレットには適用されません。</span><span class="sxs-lookup"><span data-stu-id="0327e-112">The requirements in this document do not apply to these cmdlets.</span></span>

<span data-ttu-id="0327e-113">ComputerName パラメーターを持ち、Windows PowerShell リモート処理を使用しないコマンドレットを見つけるには、コマンドレットの ComputerName パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0327e-113">To find the cmdlets that have a ComputerName parameter but do not use Windows PowerShell remoting, read the description of the ComputerName parameter of the cmdlets.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="0327e-114">システム要件</span><span class="sxs-lookup"><span data-stu-id="0327e-114">SYSTEM REQUIREMENTS</span></span>

<span data-ttu-id="0327e-115">Windows PowerShell 3.0 でリモートセッションを実行するには、ローカルコンピューターとリモートコンピューターに次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="0327e-115">To run remote sessions on Windows PowerShell 3.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="0327e-116">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="0327e-116">Windows PowerShell 3.0 or later</span></span>
- <span data-ttu-id="0327e-117">Microsoft .NET Framework 4 以降</span><span class="sxs-lookup"><span data-stu-id="0327e-117">The Microsoft .NET Framework 4 or later</span></span>
- <span data-ttu-id="0327e-118">Windows リモート管理3.0</span><span class="sxs-lookup"><span data-stu-id="0327e-118">Windows Remote Management 3.0</span></span>

<span data-ttu-id="0327e-119">Windows PowerShell 2.0 でリモートセッションを実行するには、ローカルコンピューターとリモートコンピューターに次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="0327e-119">To run remote sessions on Windows PowerShell 2.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="0327e-120">Windows PowerShell 2.0 以降</span><span class="sxs-lookup"><span data-stu-id="0327e-120">Windows PowerShell 2.0 or later</span></span>
- <span data-ttu-id="0327e-121">Microsoft .NET Framework 2.0 以降</span><span class="sxs-lookup"><span data-stu-id="0327e-121">The Microsoft .NET Framework 2.0 or later</span></span>
- <span data-ttu-id="0327e-122">Windows リモート管理2.0</span><span class="sxs-lookup"><span data-stu-id="0327e-122">Windows Remote Management 2.0</span></span>

<span data-ttu-id="0327e-123">Windows PowerShell 2.0 と Windows PowerShell 3.0 を実行しているコンピューター間にリモートセッションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0327e-123">You can create remote sessions between computers running Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span> <span data-ttu-id="0327e-124">ただし、セッションを切断して再接続する機能など、Windows PowerShell 3.0 でのみ実行される機能は、両方のコンピューターで Windows PowerShell 3.0 を実行している場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0327e-124">However, features that run only on Windows PowerShell 3.0, such as the ability to disconnect and reconnect to sessions, are available only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="0327e-125">インストールされている PowerShell のバージョン番号を確認するには、$PSVersionTable 自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="0327e-125">To find the version number of an installed version of PowerShell, use the $PSVersionTable automatic variable.</span></span>

<span data-ttu-id="0327e-126">Windows リモート管理 (WinRM) 3.0 および Microsoft .NET Framework 4 は、windows 8、Windows Server 2012、および Windows オペレーティングシステムの新しいリリースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="0327e-126">Windows Remote Management (WinRM) 3.0 and Microsoft .NET Framework 4 are included in Windows 8, Windows Server 2012, and newer releases of the Windows operating system.</span></span> <span data-ttu-id="0327e-127">WinRM 3.0 は、以前のオペレーティングシステム用の Windows Management Framework 3.0 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="0327e-127">WinRM 3.0 is included in Windows Management Framework 3.0 for older operating systems.</span></span> <span data-ttu-id="0327e-128">コンピューターに必要なバージョンの WinRM または Microsoft .NET Framework がインストールされていない場合、インストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0327e-128">If the computer does not have the required version of WinRM or the Microsoft .NET Framework, the installation fails.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="0327e-129">ユーザーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0327e-129">USER PERMISSIONS</span></span>

<span data-ttu-id="0327e-130">リモートセッションを作成してリモートコマンドを実行するには、既定で、現在のユーザーがリモートコンピューターの Administrators グループのメンバーであるか、管理者の資格情報を提供している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0327e-130">To create remote sessions and run remote commands, by default, the current user must be a member of the Administrators group on the remote computer or provide the credentials of an administrator.</span></span> <span data-ttu-id="0327e-131">それ以外の場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0327e-131">Otherwise, the command fails.</span></span>

<span data-ttu-id="0327e-132">リモートコンピューター (またはローカルコンピューター上のリモートセッション) でセッションを作成し、コマンドを実行するために必要なアクセス許可は、セッションの接続先となるリモートコンピューター上のセッション構成 ("エンドポイント" とも呼ばれます) によって確立されます。</span><span class="sxs-lookup"><span data-stu-id="0327e-132">The permissions required to create sessions and run commands on a remote computer (or in a remote session on the local computer) are established by the session configuration (also known as an "endpoint") on the remote computer to which the session connects.</span></span> <span data-ttu-id="0327e-133">具体的には、セッション構成のセキュリティ記述子は、セッション構成にアクセスできるユーザーと、それを使用して接続するユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="0327e-133">Specifically, the security descriptor on the session configuration determines who has access to the session configuration and who can use it to connect.</span></span>

<span data-ttu-id="0327e-134">既定のセッション構成のセキュリティ記述子、Microsoft.powershell32、および Microsoft. PowerShell は、Administrators グループのメンバーのみにアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="0327e-134">The security descriptors on the default session configurations, Microsoft.PowerShell, Microsoft.PowerShell32, and Microsoft.PowerShell.Workflow, allow access only to members of the Administrators group.</span></span>

<span data-ttu-id="0327e-135">現在のユーザーがセッション構成を使用するアクセス許可を持っていない場合は、コマンドを実行して (一時セッションを使用)、またはリモートコンピューターで永続的なセッションを作成するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0327e-135">If the current user doesn't have permission to use the session configuration, the command to run a command (which uses a temporary session) or create a persistent session on the remote computer fails.</span></span> <span data-ttu-id="0327e-136">ユーザーは、セッションを作成するコマンドレットの ConfigurationName パラメーターを使用して、別のセッション構成 (使用可能な場合) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0327e-136">The user can use the ConfigurationName parameter of cmdlets that create sessions to select a different session configuration, if one is available.</span></span>

<span data-ttu-id="0327e-137">コンピューターの Administrators グループのメンバーは、既定のセッション構成のセキュリティ記述子を変更し、異なるセキュリティ記述子を使用して新しいセッション構成を作成することによって、コンピューターにリモート接続するアクセス許可を持つユーザーを判断できます。</span><span class="sxs-lookup"><span data-stu-id="0327e-137">Members of the Administrators group on a computer can determine who has permission to connect to the computer remotely by changing the security descriptors on the default session configurations and by creating new session configurations with different security descriptors.</span></span>

<span data-ttu-id="0327e-138">セッション構成の詳細については、「 [about_Session_Configurations](about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0327e-138">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="windows-network-locations"></a><span data-ttu-id="0327e-139">WINDOWS ネットワークの場所</span><span class="sxs-lookup"><span data-stu-id="0327e-139">WINDOWS NETWORK LOCATIONS</span></span>

<span data-ttu-id="0327e-140">Windows PowerShell 3.0 以降では、Enable-PSRemoting コマンドレットを使用して、プライベート、ドメイン、およびパブリックネットワーク上の Windows のクライアントおよびサーバーバージョンでリモート処理を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0327e-140">Beginning in Windows PowerShell 3.0, the Enable-PSRemoting cmdlet can enable remoting on client and server versions of Windows on private, domain, and public networks.</span></span>

<span data-ttu-id="0327e-141">プライベートネットワークとドメインネットワークを使用する Windows のサーバーバージョンでは、Enable-PSRemoting コマンドレットにより、無制限のリモートアクセスを許可するファイアウォール規則が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0327e-141">On server versions of Windows with private and domain networks, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span> <span data-ttu-id="0327e-142">また、同じローカルサブネット内のコンピューターからのリモートアクセスのみを許可する、パブリックネットワーク用のファイアウォール規則も作成します。</span><span class="sxs-lookup"><span data-stu-id="0327e-142">It also creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="0327e-143">このローカルサブネットファイアウォール規則は、パブリックネットワーク上の Windows のサーバーバージョンでは既定で有効になっていますが、変更または削除された場合には、規則が再適用 Enable-PSRemoting ます。</span><span class="sxs-lookup"><span data-stu-id="0327e-143">This local subnet firewall rule is enabled by default on server versions of Windows on public networks, but Enable-PSRemoting reapplies the rule in case it was changed or deleted.</span></span>

<span data-ttu-id="0327e-144">プライベートネットワークとドメインネットワークを使用する Windows のクライアントバージョンでは、Enable-PSRemoting コマンドレットによって、無制限のリモートアクセスを許可するファイアウォール規則が既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="0327e-144">On client versions of Windows with private and domain networks, by default, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span>

<span data-ttu-id="0327e-145">パブリックネットワークを使用してクライアントバージョンの Windows でリモート処理を有効にするには、Enable-PSRemoting コマンドレットの SkipNetworkProfileCheck パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="0327e-145">To enable remoting on client versions of Windows with public networks, use the SkipNetworkProfileCheck parameter of the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="0327e-146">同じローカルサブネット内のコンピューターからのリモートアクセスのみを許可するファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="0327e-146">It creates a firewall rule that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="0327e-147">パブリックネットワークのローカルサブネットの制限を削除し、クライアントバージョンとサーバーバージョンの Windows 上のすべての場所からのリモートアクセスを許可するには、NetSecurity モジュールの Set-NetFirewallRule コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0327e-147">To remove the local subnet restriction on public networks and allow remote access from all locations on client and server versions of Windows, use the Set-NetFirewallRule cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="0327e-148">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0327e-148">Run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="0327e-149">Windows PowerShell 2.0 では、サーバーバージョンの Windows では、Enable-PSRemoting によって、すべてのネットワークでのリモートアクセスを許可するファイアウォール規則が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0327e-149">In Windows PowerShell 2.0, on server versions of Windows, Enable-PSRemoting creates firewall rules that permit remote access on all networks.</span></span>

<span data-ttu-id="0327e-150">Windows PowerShell 2.0 では、クライアントバージョンの Windows では、Enable-PSRemoting は、プライベートネットワークとドメインネットワークにのみファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="0327e-150">In Windows PowerShell 2.0, on client versions of Windows, Enable-PSRemoting creates firewall rules only on private and domain networks.</span></span> <span data-ttu-id="0327e-151">ネットワークの場所がパブリックの場合、Enable-PSRemoting は失敗します。</span><span class="sxs-lookup"><span data-stu-id="0327e-151">If the network location is public, Enable-PSRemoting fails.</span></span>

## <a name="run-as-administrator"></a><span data-ttu-id="0327e-152">管理者として実行</span><span class="sxs-lookup"><span data-stu-id="0327e-152">RUN AS ADMINISTRATOR</span></span>

<span data-ttu-id="0327e-153">次のリモート処理操作には、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="0327e-153">Administrator privileges are required for the following remoting operations:</span></span>

- <span data-ttu-id="0327e-154">ローカルコンピューターへのリモート接続を確立する。</span><span class="sxs-lookup"><span data-stu-id="0327e-154">Establishing a remote connection to the local computer.</span></span> <span data-ttu-id="0327e-155">これは、一般的に "ループバック" シナリオと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0327e-155">This is commonly known as a "loopback" scenario.</span></span>

- <span data-ttu-id="0327e-156">ローカルコンピューター上のセッション構成を管理する。</span><span class="sxs-lookup"><span data-stu-id="0327e-156">Managing session configurations on the local computer.</span></span>

- <span data-ttu-id="0327e-157">ローカルコンピューター上の WS-Management 設定を表示および変更します。</span><span class="sxs-lookup"><span data-stu-id="0327e-157">Viewing and changing WS-Management settings on the local computer.</span></span> <span data-ttu-id="0327e-158">WSMAN: ドライブの LocalHost ノードの設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0327e-158">These are the settings in the LocalHost node of the WSMAN: drive.</span></span>

<span data-ttu-id="0327e-159">これらのタスクを実行するには、ローカルコンピューターの Administrators グループのメンバーであっても、[管理者として実行] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0327e-159">To perform these tasks, you must start PowerShell with the "Run as administrator" option even if you are a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="0327e-160">Windows 7 と Windows Server 2008 R2 で、[管理者として実行] オプションを使用して Windows PowerShell を起動するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="0327e-160">In Windows 7 and in Windows Server 2008 R2, to start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="0327e-161">[スタート]、[すべてのプログラム]、[アクセサリ] の順にクリックし、[Windows PowerShell] フォルダーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0327e-161">Click Start, click All Programs, click Accessories, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="0327e-162">[Windows PowerShell] を右クリックし、[管理者として実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0327e-162">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="0327e-163">[管理者として実行] オプションを使用して Windows PowerShell を起動するには</span><span class="sxs-lookup"><span data-stu-id="0327e-163">To start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="0327e-164">[スタート] をクリックし、[すべてのプログラム] をクリックして、[Windows PowerShell] フォルダーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0327e-164">Click Start, click All Programs, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="0327e-165">[Windows PowerShell] を右クリックし、[管理者として実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0327e-165">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="0327e-166">[管理者として実行] オプションは、Windows PowerShell の他のエクスプローラーエントリ (ショートカットを含む) でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="0327e-166">The "Run as administrator" option is also available in other Windows Explorer entries for Windows PowerShell, including shortcuts.</span></span> <span data-ttu-id="0327e-167">項目を右クリックし、[管理者として実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0327e-167">Just right-click the item, and then click "Run as administrator".</span></span>

<span data-ttu-id="0327e-168">Cmd.exe などの別のプログラムから Windows PowerShell を起動する場合は、[管理者として実行] オプションを使用してプログラムを起動します。</span><span class="sxs-lookup"><span data-stu-id="0327e-168">When you start Windows PowerShell from another program such as Cmd.exe, use the "Run as administrator" option to start the program.</span></span>

## <a name="how-to-configure-your-computer-for-remoting"></a><span data-ttu-id="0327e-169">リモート処理用にコンピューターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="0327e-169">HOW TO CONFIGURE YOUR COMPUTER FOR REMOTING</span></span>

<span data-ttu-id="0327e-170">サポートされているすべてのバージョンの Windows を実行しているコンピューターは、PowerShell でリモート接続を確立し、構成なしでリモートコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0327e-170">Computers running all supported versions of Windows can establish remote connections to and run remote commands in PowerShell without any configuration.</span></span> <span data-ttu-id="0327e-171">ただし、接続を受信し、ローカルおよびリモートのユーザー管理 PowerShell セッション ("PSSessions") をユーザーが作成して、ローカルコンピューターでコマンドを実行できるようにするには、コンピューターで PowerShell リモート処理を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0327e-171">However, to receive connections, and allow users to create local and remote user-managed PowerShell sessions ("PSSessions") and run commands on the local computer, you must enable PowerShell remoting on the computer.</span></span>

<span data-ttu-id="0327e-172">Windows server 2012 および Windows Server の新しいリリースでは、PowerShell リモート処理が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0327e-172">Windows Server 2012 and newer releases of Windows Server are enabled for PowerShell remoting by default.</span></span> <span data-ttu-id="0327e-173">設定が変更された場合は、Enable-PSRemoting コマンドレットを実行して既定の設定を復元できます。</span><span class="sxs-lookup"><span data-stu-id="0327e-173">If the settings are changed, you can restore the default settings by running the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="0327e-174">その他のサポートされているすべてのバージョンの Windows では、Enable-PSRemoting コマンドレットを実行して PowerShell リモート処理を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0327e-174">On all other supported versions of Windows, you need to run the Enable-PSRemoting cmdlet to enable PowerShell remoting.</span></span>

<span data-ttu-id="0327e-175">PowerShell のリモート処理機能は、WinRM サービスによってサポートされています。これは、Web Services for Management (WS-MANAGEMENT) プロトコルの Microsoft による実装です。</span><span class="sxs-lookup"><span data-stu-id="0327e-175">The remoting features of PowerShell are supported by the WinRM service, which is the Microsoft implementation of the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="0327e-176">PowerShell リモート処理を有効にした場合、WS-Management の既定の構成を変更し、ユーザーが WS-MANAGEMENT に接続できるようにするシステム構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="0327e-176">When you enable PowerShell remoting, you change the default configuration of WS-Management and add system configuration that allow users to connect to WS-Management.</span></span>

<span data-ttu-id="0327e-177">リモートコマンドを受信するように PowerShell を構成するには</span><span class="sxs-lookup"><span data-stu-id="0327e-177">To configure PowerShell to receive remote commands:</span></span>

1. <span data-ttu-id="0327e-178">[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="0327e-178">Start PowerShell with the "Run as administrator" option.</span></span>
2. <span data-ttu-id="0327e-179">コマンド プロンプトに `Enable-PSRemoting` を入力します。</span><span class="sxs-lookup"><span data-stu-id="0327e-179">At the command prompt, type: `Enable-PSRemoting`</span></span>

<span data-ttu-id="0327e-180">リモート処理が正しく構成されていることを確認するには、次のコマンドのようなテストコマンドを実行します。このコマンドは、ローカルコンピューターでリモートセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0327e-180">To verify that remoting is configured correctly, run a test command such as the following command, which creates a remote session on the local computer.</span></span>

```powershell
New-PSSession
```

<span data-ttu-id="0327e-181">リモート処理が正しく構成されている場合、コマンドはローカルコンピューター上にセッションを作成し、そのセッションを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="0327e-181">If remoting is configured correctly, the command will create a session on the local computer and return an object that represents the session.</span></span> <span data-ttu-id="0327e-182">出力は次のサンプル出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="0327e-182">The output should resemble the following sample output:</span></span>

```output
Id Name        ComputerName    State    ConfigurationName
-- ----        ------------    -----    -----
1  Session1    localhost       Opened   Microsoft.PowerShell
```

<span data-ttu-id="0327e-183">コマンドが失敗した場合は、「 [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0327e-183">If the command fails, for assistance, see [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).</span></span>

## <a name="understand-policies"></a><span data-ttu-id="0327e-184">ポリシーを理解する</span><span class="sxs-lookup"><span data-stu-id="0327e-184">UNDERSTAND POLICIES</span></span>

<span data-ttu-id="0327e-185">リモートで作業する場合は、PowerShell の2つのインスタンスを使用します。1つはローカルコンピューター上に、もう1つはリモートコンピューター上にあります。</span><span class="sxs-lookup"><span data-stu-id="0327e-185">When you work remotely, you use two instances of PowerShell, one on the local computer and one on the remote computer.</span></span> <span data-ttu-id="0327e-186">その結果、ローカルコンピューターとリモートコンピューターの Windows ポリシーと PowerShell ポリシーの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="0327e-186">As a result, your work is affected by the Windows policies and the PowerShell policies on the local and remote computers.</span></span>

<span data-ttu-id="0327e-187">一般に、接続を確立する前に、ローカルコンピューター上のポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="0327e-187">In general, before you connect and as you are establishing the connection, the policies on the local computer are in effect.</span></span> <span data-ttu-id="0327e-188">接続を使用すると、リモートコンピューター上のポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="0327e-188">When you are using the connection, the policies on the remote computer are in effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="0327e-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="0327e-189">SEE ALSO</span></span>

[<span data-ttu-id="0327e-190">about_Remote</span><span class="sxs-lookup"><span data-stu-id="0327e-190">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="0327e-191">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="0327e-191">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="0327e-192">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="0327e-192">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="0327e-193">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="0327e-193">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="0327e-194">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="0327e-194">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="0327e-195">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="0327e-195">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
