---
description: PowerShell でのリモート操作のトラブルシューティング方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Troubleshooting
ms.openlocfilehash: 33661392583393b69723449a914ace84f394fc94
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "93225283"
---
# <a name="about-remote-troubleshooting"></a><span data-ttu-id="2dcd5-104">リモートトラブルシューティングについて</span><span class="sxs-lookup"><span data-stu-id="2dcd5-104">About Remote Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="2dcd5-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="2dcd5-105">Short description</span></span>
<span data-ttu-id="2dcd5-106">PowerShell でのリモート操作のトラブルシューティング方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-106">Describes how to troubleshoot remote operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="2dcd5-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="2dcd5-107">Long description</span></span>

<span data-ttu-id="2dcd5-108">このセクションでは、WS-Management テクノロジに基づく PowerShell のリモート処理機能を使用する場合に発生する可能性がある問題のいくつかについて説明します。また、これらの問題に対する解決策を提案します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-108">This section describes some of the problems that you might encounter when using the remoting features of PowerShell that are based on WS-Management technology and it suggests solutions to these problems.</span></span>

<span data-ttu-id="2dcd5-109">PowerShell リモート処理を使用する前に、構成と基本的な使用方法について [about_Remote](about_remote.md) と [about_Remote_Requirements](about_Remote_Requirements.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-109">Before using PowerShell remoting, see [about_Remote](about_remote.md) and [about_Remote_Requirements](about_Remote_Requirements.md) for guidance on configuration and basic use.</span></span> <span data-ttu-id="2dcd5-110">また、各リモート処理コマンドレットのヘルプトピック (特にパラメーターの説明) には、問題を回避するために設計された有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-110">Also, the Help topics for each of the remoting cmdlets, particularly the parameter descriptions, have useful information that is designed to help you avoid problems.</span></span>

> [!NOTE]
> <span data-ttu-id="2dcd5-111">WSMan: ドライブ内のローカルコンピューターの設定を表示または変更するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-111">To view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="troubleshooting-permission-and-authentication-issues"></a><span data-ttu-id="2dcd5-112">アクセス許可と認証の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2dcd5-112">Troubleshooting permission and authentication issues</span></span>

<span data-ttu-id="2dcd5-113">ここでは、ユーザーおよびコンピューターのアクセス許可とリモート処理の要件に関連するリモート処理の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-113">This section discusses remoting problems that are related to user and computer permissions and remoting requirements.</span></span>

### <a name="how-to-run-as-administrator"></a><span data-ttu-id="2dcd5-114">管理者として実行する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-114">How to run as administrator</span></span>

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

<span data-ttu-id="2dcd5-115">ローカルコンピューターでリモートセッションを開始したり、WSMan: ドライブのローカルコンピューターの設定を表示または変更したりするには、[ **管理者として実行** ] オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-115">To start a remote session on the local computer, or to view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start Windows PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="2dcd5-116">[ **管理者として実行** ] オプションを使用して Windows PowerShell を起動するには</span><span class="sxs-lookup"><span data-stu-id="2dcd5-116">To start Windows PowerShell with the **Run as administrator** option:</span></span>

- <span data-ttu-id="2dcd5-117">Windows PowerShell (または Windows PowerShell ISE) アイコンを右クリックし、[ **管理者として実行** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-117">Right-click a Windows PowerShell (or Windows PowerShell ISE) icon and then click **Run as administrator**.</span></span>

  <span data-ttu-id="2dcd5-118">Windows 7 と Windows Server 2008 R2 で [ **管理者として実行** ] オプションを使用して windows PowerShell を起動するには</span><span class="sxs-lookup"><span data-stu-id="2dcd5-118">To start Windows PowerShell with the **Run as administrator** option in Windows 7 and Windows Server 2008 R2.</span></span>

- <span data-ttu-id="2dcd5-119">Windows タスクバーで、Windows PowerShell アイコンを右クリックし、[ **管理者として実行** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-119">In the Windows taskbar, right-click the Windows PowerShell icon, and then click **Run as administrator**.</span></span>

  <span data-ttu-id="2dcd5-120">Windows Server 2008 R2 では、Windows PowerShell アイコンが既定でタスクバーに固定されています。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-120">In Windows Server 2008 R2, the Windows PowerShell icon is pinned to the taskbar by default.</span></span>

### <a name="how-to-enable-remoting"></a><span data-ttu-id="2dcd5-121">リモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-121">How to enable remoting</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

<span data-ttu-id="2dcd5-122">コンピューターがリモートコマンドを送信できるようにするための構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-122">No configuration is required to enable a computer to send remote commands.</span></span>
<span data-ttu-id="2dcd5-123">ただし、リモートコマンドを受信するには、コンピューターで PowerShell リモート処理を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-123">However, to receive remote commands, PowerShell remoting must be enabled on the computer.</span></span> <span data-ttu-id="2dcd5-124">を有効にするには、WinRM サービスの開始、WinRM サービスのスタートアップの種類の自動への設定、HTTP 接続と HTTPS 接続のためのリスナーの作成、既定のセッション構成の作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-124">Enabling includes starting the WinRM service, setting the startup type for the WinRM service to Automatic, creating listeners for HTTP and HTTPS connections, and creating default session configurations.</span></span>

<span data-ttu-id="2dcd5-125">Windows PowerShell リモート処理は、windows server 2012 以降の windows Server の既定のリリースで有効になっています。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-125">Windows PowerShell remoting is enabled on Windows Server 2012 and newer releases of Windows Server by default.</span></span> <span data-ttu-id="2dcd5-126">他のすべてのシステムでは、コマンドレットを実行して `Enable-PSRemoting` リモート処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-126">On all other systems, run the `Enable-PSRemoting` cmdlet to enable remoting.</span></span> <span data-ttu-id="2dcd5-127">`Enable-PSRemoting`リモート処理が無効になっている場合は、コマンドレットを実行して、windows server 2012 および Windows server の新しいリリースでリモート処理を再度有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-127">You can also run the `Enable-PSRemoting` cmdlet to re-enable remoting on Windows Server 2012 and newer releases of Windows Server if remoting is disabled.</span></span>

<span data-ttu-id="2dcd5-128">リモートコマンドを受信するようにコンピューターを構成するには、コマンドレットを使用し `Enable-PSRemoting` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-128">To configure a computer to receive remote commands, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="2dcd5-129">次のコマンドは、必要なすべてのリモート設定を有効にし、セッション構成を有効にして、WinRM サービスを再起動して変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-129">The following command enables all required remote settings, enables the session configurations, and restarts the WinRM service to make the changes effective.</span></span>

`Enable-PSRemoting`

<span data-ttu-id="2dcd5-130">すべてのユーザープロンプトを非表示にするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-130">To suppress all user prompts, type:</span></span>

`Enable-PSRemoting -Force`

<span data-ttu-id="2dcd5-131">詳細については、「 [enable-psremoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-131">For more information, see [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span></span>

### <a name="how-to-enable-remoting-in-an-enterprise"></a><span data-ttu-id="2dcd5-132">企業でリモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-132">How to enable remoting in an enterprise</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="2dcd5-133">1台のコンピューターでリモート PowerShell コマンドを受信して接続を受け入れるには、コマンドレットを使用し `Enable-PSRemoting` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-133">To enable a single computer to receive remote PowerShell commands and accept connections, use the `Enable-PSRemoting` cmdlet.</span></span>

<span data-ttu-id="2dcd5-134">企業内の複数のコンピューターでリモート処理を有効にするには、次のスケーリングされたオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-134">To enable remoting for multiple computers in an enterprise, you can use the following scaled options.</span></span>

- <span data-ttu-id="2dcd5-135">リモート処理のリスナーを構成するには、[ **リスナーの自動構成を許可** する] グループポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-135">To configure listeners for remoting, enable the **Allow automatic configuration of listeners** group policy.</span></span>

- <span data-ttu-id="2dcd5-136">複数のコンピューターで Windows リモート管理 (WinRM) のスタートアップの種類を [自動] に設定するには、コマンドレットを使用し `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-136">To set the startup type of the Windows Remote Management (WinRM) to Automatic on multiple computers, use the `Set-Service` cmdlet.</span></span>

- <span data-ttu-id="2dcd5-137">ファイアウォールの例外を有効にするには、[ **Windows ファイアウォール: ローカルポートの例外を許可** する] グループポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-137">To enable a firewall exception, use the **Windows Firewall: Allow Local Port Exceptions** group policy.</span></span>

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a><span data-ttu-id="2dcd5-138">グループポリシーを使用してリスナーを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-138">How to enable listeners by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="2dcd5-139">ドメイン内のすべてのコンピューターのリスナーを構成するには、次のグループポリシーパスで [ **リスナーの自動構成を許可** する] ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-139">To configure the listeners for all computers in a domain, enable the **Allow automatic configuration of listeners** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

<span data-ttu-id="2dcd5-140">ポリシーを有効にし、IPv4 フィルターと IPv6 フィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-140">Enable the policy and specify the IPv4 and IPv6 filters.</span></span> <span data-ttu-id="2dcd5-141">ワイルドカード ( `*` ) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-141">Wildcards (`*`) are permitted.</span></span>

### <a name="how-to-enable-remoting-on-public-networks"></a><span data-ttu-id="2dcd5-142">パブリックネットワークでリモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-142">How to enable remoting on public networks</span></span>

```
ERROR:  Unable to check the status of the firewall
```

<span data-ttu-id="2dcd5-143">`Enable-PSRemoting`コマンドレットは、ローカルネットワークがパブリックで、 **SkipNetworkProfileCheck** パラメーターがコマンドで使用されていない場合に、このエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-143">The `Enable-PSRemoting` cmdlet returns this error when the local network is public and the **SkipNetworkProfileCheck** parameter is not used in the command.</span></span>

<span data-ttu-id="2dcd5-144">Windows のサーバーバージョンでは、は `Enable-PSRemoting` すべてのネットワークの場所の種類に対して成功します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-144">On server versions of Windows, `Enable-PSRemoting` succeeds on all network location types.</span></span> <span data-ttu-id="2dcd5-145">プライベートおよびドメイン ("ホーム" および "作業") ネットワークへのリモートアクセスを許可するファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-145">It creates firewall rules that allow remote access to private and domain ("Home" and "Work") networks.</span></span> <span data-ttu-id="2dcd5-146">パブリックネットワークの場合、同じローカルサブネットからのリモートアクセスを許可するファイアウォール規則が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-146">For public networks, it creates firewall rules that allows remote access from the same local subnet.</span></span>

<span data-ttu-id="2dcd5-147">Windows のクライアントバージョンでは、は `Enable-PSRemoting` プライベートネットワークとドメインネットワークで成功します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-147">On client versions of Windows, `Enable-PSRemoting` succeeds on private and domain networks.</span></span> <span data-ttu-id="2dcd5-148">既定では、パブリックネットワークでは失敗しますが、 **SkipNetworkProfileCheck** パラメーターを使用すると、は `Enable-PSRemoting` 成功し、同じローカルサブネットからのトラフィックを許可するファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-148">By default, it fails on public networks, but if you use the **SkipNetworkProfileCheck** parameter, `Enable-PSRemoting` succeeds and creates a firewall rule that allows traffic from the same local subnet.</span></span>

<span data-ttu-id="2dcd5-149">パブリックネットワークのローカルサブネットの制限を削除し、任意の場所からのリモートアクセスを許可するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-149">To remove the local subnet restriction on public networks and allow remote access from any location, run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="2dcd5-150">`Set-NetFirewallRule`コマンドレットは、NetSecurity モジュールによってエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-150">The `Set-NetFirewallRule` cmdlet is exported by the NetSecurity module.</span></span>

> [!NOTE]
> <span data-ttu-id="2dcd5-151">Windows PowerShell 2.0 では、サーバーバージョンの Windows を実行しているコンピューターで、 `Enable-PSRemoting` プライベート、ドメイン、およびパブリックネットワークでのリモートアクセスを許可するファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-151">In Windows PowerShell 2.0, on computers running server versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access on private, domain and public networks.</span></span> <span data-ttu-id="2dcd5-152">クライアントバージョンの Windows を実行しているコンピューターでは、は、 `Enable-PSRemoting` プライベートネットワークとドメインネットワーク上でのみリモートアクセスを許可するファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-152">On computers running client versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access only on private and domain networks.</span></span>

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a><span data-ttu-id="2dcd5-153">グループポリシーを使用してファイアウォールの例外を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-153">How to enable a firewall exception by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="2dcd5-154">ドメイン内のすべてのコンピューターでのファイアウォールの例外を有効にするには、次のグループポリシーパスで [ **Windows ファイアウォール: ローカルポートの例外を許可** する] ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-154">To enable a firewall exception for in all computers in a domain, enable the **Windows Firewall: Allow local port exceptions** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

<span data-ttu-id="2dcd5-155">このポリシーにより、コンピューターの Administrators グループのメンバーは、 **コントロールパネル** の **Windows ファイアウォール** を使用して、Windows リモート管理サービスのファイアウォールの例外を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-155">This policy allows members of the Administrators group on the computer to use **Windows Firewall** in **Control Panel** to create a firewall exception for the Windows Remote Management service.</span></span>

<span data-ttu-id="2dcd5-156">ポリシーの構成が正しくない場合は、次のエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-156">If the policy configuration is incorrect you may receive the following error:</span></span>

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

<span data-ttu-id="2dcd5-157">ポリシーの構成エラーが発生すると、 **ListeningOn** プロパティの値が空になります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-157">A configuration error in the policy results in an empty value for the **ListeningOn** property.</span></span> <span data-ttu-id="2dcd5-158">次のコマンドを使用して、値を確認します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-158">Use the following command to check the value.</span></span>

```powershell
PS> Get-WSManInstance winrm/config/listener -Enumerate

cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
Source                : GPO
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 5985
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {}
```

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a><span data-ttu-id="2dcd5-159">WinRM サービスのスタートアップの種類を設定する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-159">How to set the startup type of the WinRM service</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="2dcd5-160">PowerShell リモート処理は、Windows リモート管理 (WinRM) サービスに依存します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-160">PowerShell remoting depends upon the Windows Remote Management (WinRM) service.</span></span>
<span data-ttu-id="2dcd5-161">リモートコマンドをサポートするには、サービスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-161">The service must be running to support remote commands.</span></span>

<span data-ttu-id="2dcd5-162">Windows のサーバーバージョンでは、Windows リモート管理 (WinRM) サービスのスタートアップの種類が [自動] になります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-162">On server versions of Windows, the startup type of the Windows Remote Management (WinRM) service is Automatic.</span></span>

<span data-ttu-id="2dcd5-163">ただし、クライアントバージョンの Windows では、WinRM サービスは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-163">However, on client versions of Windows, the WinRM service is disabled by default.</span></span>

<span data-ttu-id="2dcd5-164">リモートコンピューター上のサービスのスタートアップの種類を設定するには、 `Set-Service` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-164">To set the startup type of a service on a remote computer, use the `Set-Service` cmdlet.</span></span>

<span data-ttu-id="2dcd5-165">複数のコンピューターでコマンドを実行するには、コンピューター名のテキストファイルまたは CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-165">To run the command on multiple computers, you can create a text file or CSV file of the computer names.</span></span>

<span data-ttu-id="2dcd5-166">たとえば、次のコマンドは、ファイルからコンピューター名の一覧を取得 `Servers.txt` し、すべてのコンピューター上の WinRM サービスのスタートアップの種類を **自動** に設定します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-166">For example, the following commands get a list of computer names from the `Servers.txt` file and then sets the startup type of the WinRM service on all of the computers to **Automatic**.</span></span>

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

<span data-ttu-id="2dcd5-167">結果を表示するには、 `Get-WMIObject` コマンドレットを **Win32_Service** オブジェクトと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-167">To see the results use the `Get-WMIObject` cmdlet with the **Win32_Service** object.</span></span> <span data-ttu-id="2dcd5-168">詳細については、「 [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-168">For more information, see [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span></span>

### <a name="how-to-recreate-the-default-session-configurations"></a><span data-ttu-id="2dcd5-169">既定のセッション構成を再作成する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-169">How to recreate the default session configurations</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="2dcd5-170">ローカルコンピューターに接続してコマンドをリモートで実行するには、ローカルコンピューターにリモートコマンドのセッション構成が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-170">To connect to the local computer and run commands remotely, the local computer must include session configurations for remote commands.</span></span>

<span data-ttu-id="2dcd5-171">を使用すると `Enable-PSRemoting` 、ローカルコンピューター上に既定のセッション構成が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-171">When you use `Enable-PSRemoting`, it creates default session configurations on the local computer.</span></span> <span data-ttu-id="2dcd5-172">リモートユーザーは、リモートコマンドに **ConfigurationName** パラメーターが含まれていない場合に、これらのセッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-172">Remote users use these session configurations whenever a remote command does not include the **ConfigurationName** parameter.</span></span>

<span data-ttu-id="2dcd5-173">コンピューターの既定の構成が登録解除または削除されている場合は、コマンドレットを使用して `Enable-PSRemoting` 再作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-173">If the default configurations on a computer are unregistered or deleted, use the `Enable-PSRemoting` cmdlet to recreate them.</span></span> <span data-ttu-id="2dcd5-174">このコマンドレットを繰り返し使用できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-174">You can use this cmdlet repeatedly.</span></span> <span data-ttu-id="2dcd5-175">機能が既に構成されている場合、エラーは生成されません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-175">It does not generate errors if a feature is already configured.</span></span>

<span data-ttu-id="2dcd5-176">既定のセッション構成を変更し、元の既定のセッション構成を復元する場合は、コマンドレットを使用して `Unregister-PSSessionConfiguration` 変更されたセッション構成を削除してから、コマンドレットを使用して `Enable-PSRemoting` 復元します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-176">If you change the default session configurations and want to restore the original default session configurations, use the `Unregister-PSSessionConfiguration` cmdlet to delete the changed session configurations and then use the `Enable-PSRemoting` cmdlet to restore them.</span></span>
<span data-ttu-id="2dcd5-177">`Enable-PSRemoting` では、既存のセッション構成は変更されません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-177">`Enable-PSRemoting` does not change existing session configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="2dcd5-178">は、既定のセッション構成を復元するときに、 `Enable-PSRemoting` 構成に対して明示的なセキュリティ記述子を作成しません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-178">When `Enable-PSRemoting` restores the default session configuration, it does not create explicit security descriptors for the configurations.</span></span> <span data-ttu-id="2dcd5-179">代わりに、構成は RootSDDL のセキュリティ記述子を継承します。これは既定ではセキュリティで保護されています。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-179">Instead, the configurations inherit the security descriptor of the RootSDDL, which is secure by default.</span></span>

<span data-ttu-id="2dcd5-180">RootSDDL セキュリティ記述子を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-180">To see the RootSDDL security descriptor, type:</span></span>

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

<span data-ttu-id="2dcd5-181">RootSDDL を変更するには、 `Set-Item` WSMan: ドライブのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-181">To change the RootSDDL, use the `Set-Item` cmdlet in the WSMan: drive.</span></span> <span data-ttu-id="2dcd5-182">セッション構成のセキュリティ記述子を変更するには、 `Set-PSSessionConfiguration` コマンドレットを **Securitydescriptor sddl** または **showsecuritydescriptor ui** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-182">To change the security descriptor of a session configuration, use the `Set-PSSessionConfiguration` cmdlet with the **SecurityDescriptorSDDL** or **ShowSecurityDescriptorUI** parameters.</span></span>

<span data-ttu-id="2dcd5-183">WSMan: ドライブの詳細については、WSMan プロバイダーのヘルプトピック ("Get-help WSMan") を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-183">For more information about the WSMan: drive, see the Help topic for the WSMan provider ("Get-Help wsman").</span></span>

### <a name="how-to-provide-administrator-credentials"></a><span data-ttu-id="2dcd5-184">管理者の資格情報を指定する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-184">How to provide administrator credentials</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="2dcd5-185">リモートコンピューターで PSSession を作成したりコマンドを実行したりするには、既定では、現在のユーザーがリモートコンピューターの Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-185">To create a PSSession or run commands on a remote computer, by default, the current user must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="2dcd5-186">現在のユーザーが Administrators グループのメンバーであるアカウントにログオンしている場合でも、資格情報が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-186">Credentials are sometimes required even when the current user is logged on to an account that is a member of the Administrators group.</span></span>

<span data-ttu-id="2dcd5-187">現在のユーザーがリモートコンピューターの Administrators グループのメンバーである場合、または Administrators グループのメンバーの資格情報を提供できる場合は、、、またはコマンドレットの **Credential** パラメーターを使用して `New-PSSession` 、 `Enter-PSSession` `Invoke-Command` リモートで接続します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-187">If the current user is a member of the Administrators group on the remote computer, or can provide the credentials of a member of the Administrators group, use the **Credential** parameter of the `New-PSSession`, `Enter-PSSession` or `Invoke-Command` cmdlets to connect remotely.</span></span>

<span data-ttu-id="2dcd5-188">たとえば、次のコマンドは、管理者の資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-188">For example, the following command provides the credentials of an Administrator.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="2dcd5-189">**Credential** パラメーターの詳細については、「 [New-pssession](xref:Microsoft.PowerShell.Core.New-PSSession)」、「 [-pssession](xref:Microsoft.PowerShell.Core.Enter-PSSession) 」、または「 [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-189">For more information about the **Credential** parameter, see [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span></span>

### <a name="how-to-enable-remoting-for-non-administrative-users"></a><span data-ttu-id="2dcd5-190">管理者以外のユーザーのリモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-190">How to enable remoting for non-administrative users</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="2dcd5-191">リモートコンピューター上で PSSession を確立したりコマンドを実行したりするには、リモートコンピューターでセッション構成を使用するためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-191">To establish a PSSession or run a command on a remote computer, the user must have permission to use the session configurations on the remote computer.</span></span>

<span data-ttu-id="2dcd5-192">既定では、コンピューターの Administrators グループのメンバーだけが、既定のセッション構成を使用するアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-192">By default, only members of the Administrators group on a computer have permission to use the default session configurations.</span></span> <span data-ttu-id="2dcd5-193">したがって、Administrators グループのメンバーだけがリモートでコンピューターに接続できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-193">Therefore, only members of the Administrators group can connect to the computer remotely.</span></span>

<span data-ttu-id="2dcd5-194">他のユーザーがローカルコンピューターに接続できるようにするには、ローカルコンピューター上の既定のセッション構成に対する実行アクセス許可をユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-194">To allow other users to connect to the local computer, give the user Execute permissions to the default session configurations on the local computer.</span></span>

<span data-ttu-id="2dcd5-195">次のコマンドを実行すると、プロパティシートが開き、ローカルコンピューター上の既定の Microsoft PowerShell セッション構成のセキュリティ記述子を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-195">The following command opens a property sheet that lets you change the security descriptor of the default Microsoft.PowerShell session configuration on the local computer.</span></span>

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

<span data-ttu-id="2dcd5-196">詳細については、「 [about_Session_Configurations](about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-196">For more information, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a><span data-ttu-id="2dcd5-197">他のドメインの管理者のリモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-197">How to enable remoting for administrators in other domains</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="2dcd5-198">別のドメインのユーザーがローカルコンピューターの Administrators グループのメンバーである場合、ユーザーは管理者特権でローカルコンピューターにリモート接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-198">When a user in another domain is a member of the Administrators group on the local computer, the user cannot connect to the local computer remotely with Administrator privileges.</span></span> <span data-ttu-id="2dcd5-199">既定では、他のドメインからのリモート接続は、標準のユーザー特権トークンのみを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-199">By default, remote connections from other domains run with only standard user privilege tokens.</span></span>

<span data-ttu-id="2dcd5-200">ただし、 **LocalAccountTokenFilterPolicy** レジストリエントリを使用して既定の動作を変更し、Administrators グループのメンバーであるリモートユーザーが管理者特権で実行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-200">However, you can use the **LocalAccountTokenFilterPolicy** registry entry to change the default behavior and allow remote users who are members of the Administrators group to run with Administrator privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="2dcd5-201">**LocalAccountTokenFilterPolicy** エントリは、影響を受けるすべてのコンピューターのすべてのユーザーに対するユーザーアカウント制御 (UAC) リモート制限を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-201">The **LocalAccountTokenFilterPolicy** entry disables user account control (UAC) remote restrictions for all users of all affected computers.</span></span> <span data-ttu-id="2dcd5-202">ポリシーを変更する前に、この設定の影響を慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-202">Consider the implications of this setting carefully before changing the policy.</span></span>

<span data-ttu-id="2dcd5-203">ポリシーを変更するには、次のコマンドを使用して、 **LocalAccountTokenFilterPolicy** レジストリエントリの値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-203">To change the policy, use the following command to set the value of the **LocalAccountTokenFilterPolicy** registry entry to 1.</span></span>

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a><span data-ttu-id="2dcd5-204">リモートコマンドで ip アドレスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-204">How to use an ip address in a remote command</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="2dcd5-205">、、およびコマンドレットの **ComputerName** パラメーターは、 `New-PSSession` `Enter-PSSession` `Invoke-Command` IP アドレスを有効な値として受け入れます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-205">The **ComputerName** parameter of the `New-PSSession`, `Enter-PSSession` and `Invoke-Command` cmdlets accepts an IP address as a valid value.</span></span> <span data-ttu-id="2dcd5-206">ただし、Kerberos 認証では IP アドレスがサポートされないため、IP アドレスを指定するたびに、NTLM 認証が既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-206">However, because Kerberos authentication does not support IP addresses, NTLM authentication is used by default whenever you specify an IP address.</span></span>

<span data-ttu-id="2dcd5-207">NTLM 認証を使用する場合、リモート処理には次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-207">When using NTLM authentication, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="2dcd5-208">HTTPS トランスポート用にコンピューターを構成するか、ローカルコンピューターの TrustedHosts の一覧にリモートコンピューターの IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-208">Configure the computer for HTTPS transport or add the IP addresses of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="2dcd5-209">すべてのリモートコマンドで **Credential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-209">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="2dcd5-210">これは、現在のユーザーの資格情報を送信する場合でも必要です。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-210">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a><span data-ttu-id="2dcd5-211">ワークグループベースのコンピューターからリモート接続する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-211">How to connect remotely from a workgroup-based computer</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="2dcd5-212">ローカルコンピューターがドメイン内にない場合、リモート処理には次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-212">When the local computer is not in a domain, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="2dcd5-213">HTTPS トランスポート用にコンピューターを構成するか、ローカルコンピューターの TrustedHosts の一覧にリモートコンピューターの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-213">Configure the computer for HTTPS transport or add the names of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="2dcd5-214">ワークグループベースのコンピューターにパスワードが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-214">Verify that a password is set on the workgroup-based computer.</span></span> <span data-ttu-id="2dcd5-215">パスワードが設定されていない場合、またはパスワード値が空の場合は、リモートコマンドを実行できません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-215">If a password is not set or the password value is empty, you cannot run remote commands.</span></span>

   <span data-ttu-id="2dcd5-216">ユーザーアカウントのパスワードを設定するには、コントロールパネルの [ユーザーアカウント] を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-216">To set password for your user account, use User Accounts in Control Panel.</span></span>

1. <span data-ttu-id="2dcd5-217">すべてのリモートコマンドで **Credential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-217">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="2dcd5-218">これは、現在のユーザーの資格情報を送信する場合でも必要です。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-218">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a><span data-ttu-id="2dcd5-219">信頼されたホストの一覧にコンピューターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-219">How to add a computer to the trusted hosts list</span></span>

<span data-ttu-id="2dcd5-220">TrustedHosts 項目には、コンピューター名、IP アドレス、および完全修飾ドメイン名のコンマ区切りの一覧を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-220">The TrustedHosts item can contain a comma-separated list of computer names, IP addresses, and fully-qualified domain names.</span></span> <span data-ttu-id="2dcd5-221">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-221">Wildcards are permitted.</span></span>

<span data-ttu-id="2dcd5-222">信頼されたホストの一覧を表示または変更するには、WSMan: ドライブを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-222">To view or change the trusted host list, use the WSMan: drive.</span></span> <span data-ttu-id="2dcd5-223">TrustedHost 項目は `WSMan:\localhost\Client` ノードにあります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-223">The TrustedHost item is in the `WSMan:\localhost\Client` node.</span></span>

<span data-ttu-id="2dcd5-224">コンピューターの Administrators グループのメンバーだけが、コンピューター上の信頼されたホストの一覧を変更するアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-224">Only members of the Administrators group on the computer have permission to change the list of trusted hosts on the computer.</span></span>

<span data-ttu-id="2dcd5-225">注意: TrustedHosts 項目に対して設定した値は、コンピューターのすべてのユーザーに影響します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-225">Caution: The value that you set for the TrustedHosts item affects all users of the computer.</span></span>

<span data-ttu-id="2dcd5-226">信頼されたホストの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-226">To view the list of trusted hosts, use the following command:</span></span>

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

<span data-ttu-id="2dcd5-227">また、 `Set-Location` コマンドレット (alias = cd) を使用して、WSMan: ドライブを場所に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-227">You can also use the `Set-Location` cmdlet (alias = cd) to navigate though the WSMan: drive to the location.</span></span> <span data-ttu-id="2dcd5-228">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-228">For example:</span></span>

```powershell
cd WSMan:\localhost\Client; dir
```

<span data-ttu-id="2dcd5-229">すべてのコンピューターを信頼されたホストの一覧に追加するには、次のコマンドを使用します。このコマンドは、ComputerName に \* (all) の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-229">To add all computers to the list of trusted hosts, use the following command, which places a value of \* (all) in the ComputerName</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

<span data-ttu-id="2dcd5-230">ワイルドカード文字 () を使用し `*` て、特定のドメインにあるすべてのコンピューターを、信頼されたホストの一覧に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-230">You can also use a wildcard character (`*`) to add all computers in a particular domain to the list of trusted hosts.</span></span> <span data-ttu-id="2dcd5-231">たとえば、次のコマンドは、Fabrikam ドメインにあるすべてのコンピューターを、信頼されたホストの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-231">For example, the following command adds all of the computers in the Fabrikam domain to the list of trusted hosts.</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

<span data-ttu-id="2dcd5-232">特定のコンピューターの名前を信頼されたホストの一覧に追加するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-232">To add the names of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

<span data-ttu-id="2dcd5-233">各値 `<ComputerName>` の形式は次のとおりでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-233">where each value `<ComputerName>` must have the following format:</span></span>

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

<span data-ttu-id="2dcd5-234">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-234">For example:</span></span>

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

<span data-ttu-id="2dcd5-235">既存の信頼されたホストの一覧にコンピューター名を追加するには、まず、現在の値を変数に保存し、その値を、現在の値と新しい値を含むコンマ区切りのリストに設定します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-235">To add a computer name to an existing list of trusted hosts, first save the current value in a variable, and then set the value to a comma-separated list that includes the current and new values.</span></span>

<span data-ttu-id="2dcd5-236">たとえば、Server01 コンピューターを既存の信頼されたホストの一覧に追加するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-236">For example, to add the Server01 computer to an existing list of trusted hosts, use the following command</span></span>

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

<span data-ttu-id="2dcd5-237">特定のコンピューターの IP アドレスを信頼されたホストの一覧に追加するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-237">To add the IP addresses of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

<span data-ttu-id="2dcd5-238">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-238">For example:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

<span data-ttu-id="2dcd5-239">コンピューターをリモートコンピューターの TrustedHosts の一覧に追加するには、コマンドレットを使用して、 `Connect-WSMan` リモートコンピューターのノードをローカルコンピューターの WSMan: ドライブに追加します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-239">To add a computer to the TrustedHosts list of a remote computer, use the `Connect-WSMan` cmdlet to add a node for the remote computer to the WSMan: drive on the local computer.</span></span> <span data-ttu-id="2dcd5-240">次に、コマンドを使用し `Set-Item` てコンピューターを追加します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-240">Then use a `Set-Item` command to add the computer.</span></span>

<span data-ttu-id="2dcd5-241">コマンドレットの詳細につい `Connect-WSMan` ては、「 [接続-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-241">For more information about the `Connect-WSMan` cmdlet, see [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span>

## <a name="troubleshooting-computer-configuration-issues"></a><span data-ttu-id="2dcd5-242">コンピューターの構成に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2dcd5-242">Troubleshooting computer configuration issues</span></span>

<span data-ttu-id="2dcd5-243">ここでは、コンピューター、ドメイン、または企業の特定の構成に関連するリモート処理の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-243">This section discusses remoting problems that are related to particular configurations of a computer, domain, or enterprise.</span></span>

### <a name="how-to-configure-remoting-on-alternate-ports"></a><span data-ttu-id="2dcd5-244">代替ポートでリモート処理を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-244">How to configure remoting on alternate ports</span></span>

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="2dcd5-245">PowerShell リモート処理では、既定で HTTP トランスポートにポート80を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-245">PowerShell remoting uses port 80 for HTTP transport by default.</span></span> <span data-ttu-id="2dcd5-246">既定のポートは、ユーザーがリモートコマンドで **Connectionuri** または **ポート** パラメーターを指定していない場合に常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-246">The default port is used whenever the user does not specify the **ConnectionURI** or **Port** parameters in a remote command.</span></span>

<span data-ttu-id="2dcd5-247">PowerShell が使用する既定のポートを変更するには、WSMan: ドライブのコマンドレットを使用して、 `Set-Item` リスナーのリーフノードのポート値を変更します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-247">To change the default port that PowerShell uses, use `Set-Item` cmdlet in the WSMan: drive to change the Port value in the listener leaf node.</span></span>

<span data-ttu-id="2dcd5-248">たとえば、次のコマンドは、既定のポートを8080に変更します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-248">For example, the following command changes the default port to 8080.</span></span>

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a><span data-ttu-id="2dcd5-249">プロキシサーバーを使用してリモート処理を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-249">How to configure remoting with a proxy server</span></span>

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

<span data-ttu-id="2dcd5-250">PowerShell リモート処理は HTTP プロトコルを使用するため、HTTP プロキシ設定の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-250">Because PowerShell remoting uses the HTTP protocol, it is affected by HTTP proxy settings.</span></span> <span data-ttu-id="2dcd5-251">プロキシサーバーを使用している企業では、ユーザーは PowerShell リモートコンピューターに直接アクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-251">In enterprises that have proxy servers, users cannot access a PowerShell remote computer directly.</span></span>

<span data-ttu-id="2dcd5-252">この問題を解決するには、リモートコマンドでプロキシ設定オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-252">To resolve this problem, use proxy setting options in your remote command.</span></span> <span data-ttu-id="2dcd5-253">次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-253">The following settings are available:</span></span>

- <span data-ttu-id="2dcd5-254">System.management.automation.remoting.proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="2dcd5-254">ProxyAccessType</span></span>
- <span data-ttu-id="2dcd5-255">ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="2dcd5-255">ProxyAuthentication</span></span>
- <span data-ttu-id="2dcd5-256">ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="2dcd5-256">ProxyCredential</span></span>

<span data-ttu-id="2dcd5-257">特定のコマンドに対してこれらのオプションを設定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-257">To set these options for a particular command, use the following procedure:</span></span>

1. <span data-ttu-id="2dcd5-258">コマンドレットの **system.management.automation.remoting.proxyaccesstype** 、 **Proxyauthentication** 、および **proxyauthentication** パラメーターを使用して、 `New-PSSessionOption` 企業のプロキシ設定を使用してセッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-258">Use the **ProxyAccessType** , **ProxyAuthentication** , and **ProxyCredential** parameters of the `New-PSSessionOption` cmdlet to create a session option object with the proxy settings for your enterprise.</span></span> <span data-ttu-id="2dcd5-259">[保存] オプションオブジェクトは変数です。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-259">Save the option object is a variable.</span></span>

1. <span data-ttu-id="2dcd5-260">、、またはコマンドの **Sessionoption** パラメーターの値として、option オブジェクトを含む変数を使用し `New-PSSession` `Enter-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-260">Use the variable that contains the option object as the value of the **SessionOption** parameter of a `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` command.</span></span>

<span data-ttu-id="2dcd5-261">たとえば、次のコマンドは、プロキシセッションオプションを使用してセッションオプションオブジェクトを作成し、オブジェクトを使用してリモートセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-261">For example, the following command creates a session option object with proxy session options and then uses the object to create a remote session.</span></span>

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

<span data-ttu-id="2dcd5-262">コマンドレットの詳細につい `New-PSSessionOption` ては、「 [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-262">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="2dcd5-263">現在のセッションのすべてのリモートコマンドに対してこれらのオプションを設定するには、ユーザー `New-PSSessionOption` 設定変数の値にを作成する option オブジェクトを使用し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-263">To set these options for all remote commands in the current session, use the option object that `New-PSSessionOption` creates in the value of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="2dcd5-264">詳細については、「 [about_Preference_Variables](about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-264">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="2dcd5-265">すべてのリモートコマンドに対して、ローカルコンピューター上のすべての PowerShell セッションに対してこれらのオプションを設定するには、 `$PSSessionOption` ユーザー設定変数を powershell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-265">To set these options for all remote commands all PowerShell sessions on the local computer, add the `$PSSessionOption` preference variable to your PowerShell profile.</span></span> <span data-ttu-id="2dcd5-266">PowerShell プロファイルの詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-266">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a><span data-ttu-id="2dcd5-267">64ビットコンピューターで32ビットセッションを検出する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-267">How to detect a 32-bit session on a 64-bit computer</span></span>

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="2dcd5-268">リモートコンピューターが64ビットバージョンの Windows を実行していて、リモートコマンドが Microsoft.powershell32 などの32ビットのセッション構成を使用している場合、Windows リモート管理 (WinRM) は WOW64 プロセスを読み込み、Windows はディレクトリへのすべての参照をディレクトリに自動的にリダイレクトし `$env:Windir\System32` `$env:Windir\SysWOW64` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-268">If the remote computer is running a 64-bit version of Windows, and the remote command is using a 32-bit session configuration, such as Microsoft.PowerShell32, Windows Remote Management (WinRM) loads a WOW64 process and Windows automatically redirects all references to the `$env:Windir\System32` directory to the `$env:Windir\SysWOW64` directory.</span></span>

<span data-ttu-id="2dcd5-269">このため、のように、SysWow64 ディレクトリ (など) に対応するものがない System32 ディレクトリ内のツールを使用しようとすると、 `Defrag.exe` ツールがディレクトリに見つかりません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-269">As a result, if you try to use tools in the System32 directory that do not have counterparts in the SysWow64 directory, such as `Defrag.exe`, the tools cannot be found in the directory.</span></span>

<span data-ttu-id="2dcd5-270">セッションで使用されているプロセッサアーキテクチャを確認するには、 **PROCESSOR_ARCHITECTURE** 環境変数の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-270">To find the processor architecture that is being used in the session, use the value of the **PROCESSOR_ARCHITECTURE** environment variable.</span></span> <span data-ttu-id="2dcd5-271">次のコマンドは、変数内のセッションのプロセッサアーキテクチャを検索し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-271">The following command finds the processor architecture of the session in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

<span data-ttu-id="2dcd5-272">セッション構成の詳細については、「 [about_Session_Configurations](about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-272">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="troubleshooting-policy-and-preference-issues"></a><span data-ttu-id="2dcd5-273">ポリシーと基本設定に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2dcd5-273">Troubleshooting policy and preference issues</span></span>

<span data-ttu-id="2dcd5-274">ここでは、ローカルコンピューターとリモートコンピューターで設定されたポリシーと基本設定に関連するリモート処理の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-274">This section discusses remoting problems that are related to policies and preferences set on the local and remote computers.</span></span>

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a><span data-ttu-id="2dcd5-275">Import-PSSession および Import-Module の実行ポリシーを変更する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-275">How to change the execution policy for Import-PSSession and Import-Module</span></span>

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

<span data-ttu-id="2dcd5-276">`Import-PSSession`および `Export-PSSession` コマンドレットは、署名されていないスクリプトファイルとフォーマットファイルを含むモジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-276">The `Import-PSSession` and `Export-PSSession` cmdlets create modules that contains unsigned script files and formatting files.</span></span>

<span data-ttu-id="2dcd5-277">またはを使用してこれらのコマンドレットによって作成されたモジュールをインポートするには、 `Import-PSSession` `Import-Module` 現在のセッションの実行ポリシーを制限することも AllSigned することもできません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-277">To import the modules that are created by these cmdlets, either by using `Import-PSSession` or `Import-Module`, the execution policy in the current session cannot be Restricted or AllSigned.</span></span> <span data-ttu-id="2dcd5-278">PowerShell 実行ポリシーの詳細については、「 [about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-278">For information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="2dcd5-279">レジストリに設定されているローカルコンピューターの実行ポリシーを変更せずにモジュールをインポートするには、の **Scope** パラメーターを使用して、 `Set-ExecutionPolicy` 1 つのプロセスに対して制限の少ない実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-279">To import the modules without changing the execution policy for the local computer that is set in the registry, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>

<span data-ttu-id="2dcd5-280">たとえば、次のコマンドは、実行ポリシーを使用してプロセスを開始し `RemoteSigned` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-280">For example, the following command starts a process with the `RemoteSigned` execution policy.</span></span> <span data-ttu-id="2dcd5-281">実行ポリシーの変更は現在のプロセスのみに影響し、PowerShell **set-executionpolicy** レジストリ設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-281">The execution policy change affects only the current process and does not change the PowerShell **ExecutionPolicy** registry setting.</span></span>

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="2dcd5-282">の **set-executionpolicy** パラメーターを使用して、 `PowerShell.exe` より制限の少ない実行ポリシーで1つのセッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-282">You can also use the **ExecutionPolicy** parameter of `PowerShell.exe` to start a single session with a less restrictive execution policy.</span></span>

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="2dcd5-283">実行ポリシーの詳細については、「 [about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-283">For more information about execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span> <span data-ttu-id="2dcd5-284">詳細を表示するには「`PowerShell.exe -?`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-284">For more information, type `PowerShell.exe -?`.</span></span>

### <a name="how-to-set-and-change-quotas"></a><span data-ttu-id="2dcd5-285">クォータを設定および変更する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-285">How to set and change quotas</span></span>

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

<span data-ttu-id="2dcd5-286">クォータを使用すると、ローカルコンピューターとリモートコンピューターが、偶発的でも悪意のあるリソースでも使用されないように保護することができます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-286">You can use quotas to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span>

<span data-ttu-id="2dcd5-287">基本構成では、次のクォータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-287">The following quotas are available in the basic configuration.</span></span>

- <span data-ttu-id="2dcd5-288">WSMan プロバイダー (WSMan:)では、ノードの **MaxEnvelopeSizeKB** および **maxproviderrequests** 設定、 `WSMan:<ComputerName>` ノードの **MaxConcurrentOperations** 、 **maxconcurrentoperationsperuser プロパティ** 、 **MaxConnections** の各設定など、いくつかのクォータ設定が提供され `WSMan:<ComputerName>\Service` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-288">The WSMan provider (WSMan:) provides several quota settings, such as the **MaxEnvelopeSizeKB** and **MaxProviderRequests** settings in the `WSMan:<ComputerName>` node and the **MaxConcurrentOperations** , **MaxConcurrentOperationsPerUser** , and **MaxConnections** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="2dcd5-289">コマンドレットとユーザー設定変数の **MaximumReceivedDataSizePerCommand** パラメーターと **MaximumReceivedObjectSize** パラメーターを使用して、ローカルコンピューターを保護することができ `New-PSSessionOption` `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-289">You can protect the local computer by using the **MaximumReceivedDataSizePerCommand** and **MaximumReceivedObjectSize** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="2dcd5-290">コマンドレットの **MaximumReceivedDataSizePerCommandMB** パラメーターと **MaximumReceivedObjectSizeMB** パラメーターを使用するなどして、セッション構成に制限を追加することで、リモートコンピューターを保護することができ `Register-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-290">You can protect the remote computer by adding restrictions to the session configurations, such as by using the **MaximumReceivedDataSizePerCommandMB** and **MaximumReceivedObjectSizeMB** parameters of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="2dcd5-291">クォータがコマンドと競合している場合は、PowerShell によってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-291">When quotas conflict with a command, PowerShell generates an error.</span></span>

<span data-ttu-id="2dcd5-292">このエラーを解決するには、クォータに準拠するようにリモートコマンドを変更します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-292">To resolve the error, change the remote command to comply with the quota.</span></span> <span data-ttu-id="2dcd5-293">または、クォータのソースを特定し、クォータを増やしてコマンドを完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-293">Or, determine the source of the quota, and then increase the quota to allow the command to complete.</span></span>

<span data-ttu-id="2dcd5-294">たとえば、次のコマンドは、リモートコンピューター上の Microsoft PowerShell セッション構成のオブジェクトサイズクォータを 10 MB (既定値) から 11 MB に増やします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-294">For example, the following command increases the object size quota in the Microsoft.PowerShell session configuration on the remote computer from 10 MB (the default value) to 11 MB.</span></span>

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

<span data-ttu-id="2dcd5-295">コマンドレットの詳細については `New-PSSessionOption` 、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-295">For more information about the `New-PSSessionOption` cmdlet, see `New-PSSessionOption`.</span></span>

<span data-ttu-id="2dcd5-296">WS-Management クォータの詳細については、「 [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-296">For more information about the WS-Management quotas, see [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span></span>

### <a name="how-to-resolve-timeout-errors"></a><span data-ttu-id="2dcd5-297">タイムアウトエラーを解決する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-297">How to resolve timeout errors</span></span>

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

<span data-ttu-id="2dcd5-298">タイムアウトを使用して、ローカルコンピューターとリモートコンピューターが、偶発的でも悪意のあるリソースでも使用されないように保護することができます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-298">You can use timeouts to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span> <span data-ttu-id="2dcd5-299">ローカルコンピューターとリモートコンピューターの両方でタイムアウトが設定されている場合、PowerShell では最短タイムアウト設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-299">When timeouts are set on both the local and remote computer, PowerShell uses the shortest timeout settings.</span></span>

<span data-ttu-id="2dcd5-300">基本構成では、次のタイムアウトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-300">The following timeouts are available in the basic configuration.</span></span>

- <span data-ttu-id="2dcd5-301">WSMan プロバイダー (WSMan:)では、ノードの **Maxtimeoutms** 設定 `WSMan:<ComputerName>` やノードの **EnumerationTimeoutms** と **MaxPacketRetrievalTimeSeconds** の設定など、クライアント側とサービス側のタイムアウト設定がいくつか提供されて `WSMan:<ComputerName>\Service` います。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-301">The WSMan provider (WSMan:) provides several client-side and service-side timeout settings, such as the **MaxTimeoutms** setting in the `WSMan:<ComputerName>` node and the **EnumerationTimeoutms** and **MaxPacketRetrievalTimeSeconds** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="2dcd5-302">コマンドレットとユーザー設定変数の **canceltimeout** 、 **IdleTimeout** 、 **OpenTimeout** 、および **operationtimeout** パラメーターを使用して、ローカルコンピューターを保護することができ `New-PSSessionOption` `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-302">You can protect the local computer by using the **CancelTimeout** , **IdleTimeout** , **OpenTimeout** , and **OperationTimeout** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="2dcd5-303">セッションのセッション構成でタイムアウト値をプログラムによって設定することで、リモートコンピューターを保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-303">You can also protect the remote computer by setting timeout values programmatically in the session configuration for the session.</span></span>

<span data-ttu-id="2dcd5-304">タイムアウト値によって操作の完了が許可されていない場合、PowerShell は操作を終了し、エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-304">When a timeout value does not permit a operation to complete, PowerShell terminates the operation and generates an error.</span></span>

<span data-ttu-id="2dcd5-305">このエラーを解決するには、タイムアウト間隔内に完了するようにコマンドを変更するか、タイムアウト制限のソースを特定し、タイムアウト間隔を長くしてコマンドを完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-305">To resolve the error, change the command to complete within the timeout interval or determine the source of the timeout limit and increase the timeout interval to allow the command to complete.</span></span>

<span data-ttu-id="2dcd5-306">たとえば、次のコマンドでは、コマンドレットを使用して、 `New-PSSessionOption` **operationtimeout** 値が4分 (ミリ秒) のセッションオプションオブジェクトを作成し、そのセッションオプションオブジェクトを使用してリモートセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-306">For example, the following commands use the `New-PSSessionOption` cmdlet to create a session option object with an **OperationTimeout** value of 4 minutes (in MS) and then use the session option object to create a remote session.</span></span>

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

<span data-ttu-id="2dcd5-307">WS-Management タイムアウトの詳細については、WSMan プロバイダーのヘルプトピック (型) を参照してください `Get-Help WSMan` 。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-307">For more information about the WS-Management timeouts, see the Help topic for the WSMan provider (type `Get-Help WSMan`).</span></span>

<span data-ttu-id="2dcd5-308">コマンドレットの詳細につい `New-PSSessionOption` ては、「 [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-308">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="troubleshooting-unresponsive-behavior"></a><span data-ttu-id="2dcd5-309">応答しない動作のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2dcd5-309">Troubleshooting unresponsive behavior</span></span>

<span data-ttu-id="2dcd5-310">このセクションでは、コマンドが完了しないようにするリモート処理の問題について説明し、PowerShell プロンプトを返します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-310">This section discusses remoting problems that prevent a command from completing and prevent or delay the return of the PowerShell prompt.</span></span>

### <a name="how-to-interrupt-a-command"></a><span data-ttu-id="2dcd5-311">コマンドを中断する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-311">How to interrupt a command</span></span>

<span data-ttu-id="2dcd5-312">ユーザーインターフェイスを備えたプログラム、入力を要求するコンソールアプリケーション、Win32 コンソール API を使用するコンソールアプリケーションなど、一部のネイティブ Windows プログラムは、PowerShell リモートホストでは正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-312">Some native Windows programs, such as programs with a user interface, console applications that prompt for input, and console applications that use the Win32 console API, do not work correctly in the PowerShell remote host.</span></span>

<span data-ttu-id="2dcd5-313">これらのプログラムを使用すると、出力がない、部分的な出力、または完了していないリモートコマンドなど、予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-313">When you use these programs, you might see unexpected behavior, such as no output, partial output, or a remote command that does not complete.</span></span>

<span data-ttu-id="2dcd5-314">応答しないプログラムを終了するには、 <kbd>CTRL C キーを押し</kbd> + <kbd>C</kbd>ます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-314">To end an unresponsive program, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="2dcd5-315">報告された可能性があるエラーを表示するには、 `$error` ローカルホストとリモートセッションを入力します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-315">To view any errors that might have been reported, type `$error` in the local host and the remote session.</span></span>

## <a name="how-to-recover-from-an-operation-failure"></a><span data-ttu-id="2dcd5-316">操作エラーから回復する方法</span><span class="sxs-lookup"><span data-stu-id="2dcd5-316">How to recover from an operation failure</span></span>

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

<span data-ttu-id="2dcd5-317">このエラーは、操作が完了する前に操作が終了したときに返されます。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-317">This error is returned when an operation is terminated before it completes.</span></span>
<span data-ttu-id="2dcd5-318">通常、このエラーは、他の WinRM 操作の実行中に WinRM サービスが停止または再起動したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-318">Typically, it occurs when the WinRM service stops or restarts while other WinRM operations are in progress.</span></span>

<span data-ttu-id="2dcd5-319">この問題を解決するには、WinRM サービスが実行されていることを確認してから、コマンドを再試行してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-319">To resolve this issue, verify that the WinRM service is running and try the command again.</span></span>

1. <span data-ttu-id="2dcd5-320">[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-320">Start PowerShell with the **Run as administrator** option.</span></span>
1. <span data-ttu-id="2dcd5-321">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-321">Run the following command:</span></span>

   `Start-Service WinRM`

1. <span data-ttu-id="2dcd5-322">エラーを生成したコマンドを再実行します。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-322">Re-run the command that generated the error.</span></span>

## <a name="linux-and-macos-limitations"></a><span data-ttu-id="2dcd5-323">Linux と macOS の制限事項</span><span class="sxs-lookup"><span data-stu-id="2dcd5-323">Linux and macOS limitations</span></span>

### <a name="authentication"></a><span data-ttu-id="2dcd5-324">認証</span><span class="sxs-lookup"><span data-stu-id="2dcd5-324">Authentication</span></span>

<span data-ttu-id="2dcd5-325">MacOS では基本認証のみが機能し、他の認証方式を使用しようとするとプロセスがクラッシュする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-325">Only basic authentication works on macOS and attempting to use other authentication schemes may result in the process crashing.</span></span>

<span data-ttu-id="2dcd5-326">[Omi 認証](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows)の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dcd5-326">Please see the [OMI authentication](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dcd5-327">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dcd5-327">SEE ALSO</span></span>

[<span data-ttu-id="2dcd5-328">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="2dcd5-328">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[<span data-ttu-id="2dcd5-329">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="2dcd5-329">Export-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[<span data-ttu-id="2dcd5-330">Import-Module</span><span class="sxs-lookup"><span data-stu-id="2dcd5-330">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="2dcd5-331">about_Remote</span><span class="sxs-lookup"><span data-stu-id="2dcd5-331">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="2dcd5-332">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="2dcd5-332">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="2dcd5-333">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="2dcd5-333">about_Remote_Variables</span></span>](about_Remote_Variables.md)
