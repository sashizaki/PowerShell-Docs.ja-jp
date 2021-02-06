---
description: PowerShell でのリモート操作のトラブルシューティング方法について説明します。
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Troubleshooting
ms.openlocfilehash: cedf38f3982f4036aae59a2019ab72b556e50cfd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600969"
---
# <a name="about-remote-troubleshooting"></a><span data-ttu-id="b0c22-103">リモートトラブルシューティングについて</span><span class="sxs-lookup"><span data-stu-id="b0c22-103">About Remote Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="b0c22-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="b0c22-104">Short description</span></span>
<span data-ttu-id="b0c22-105">PowerShell でのリモート操作のトラブルシューティング方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-105">Describes how to troubleshoot remote operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="b0c22-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="b0c22-106">Long description</span></span>

<span data-ttu-id="b0c22-107">このセクションでは、WS-Management テクノロジに基づく PowerShell のリモート処理機能を使用する場合に発生する可能性がある問題のいくつかについて説明します。また、これらの問題に対する解決策を提案します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-107">This section describes some of the problems that you might encounter when using the remoting features of PowerShell that are based on WS-Management technology and it suggests solutions to these problems.</span></span>

<span data-ttu-id="b0c22-108">PowerShell リモート処理を使用する前に、構成と基本的な使用方法について [about_Remote](about_remote.md) と [about_Remote_Requirements](about_Remote_Requirements.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-108">Before using PowerShell remoting, see [about_Remote](about_remote.md) and [about_Remote_Requirements](about_Remote_Requirements.md) for guidance on configuration and basic use.</span></span> <span data-ttu-id="b0c22-109">また、各リモート処理コマンドレットのヘルプトピック (特にパラメーターの説明) には、問題を回避するために設計された有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0c22-109">Also, the Help topics for each of the remoting cmdlets, particularly the parameter descriptions, have useful information that is designed to help you avoid problems.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c22-110">WSMan: ドライブ内のローカルコンピューターの設定を表示または変更するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-110">To view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="troubleshooting-permission-and-authentication-issues"></a><span data-ttu-id="b0c22-111">アクセス許可と認証の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0c22-111">Troubleshooting permission and authentication issues</span></span>

<span data-ttu-id="b0c22-112">ここでは、ユーザーおよびコンピューターのアクセス許可とリモート処理の要件に関連するリモート処理の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-112">This section discusses remoting problems that are related to user and computer permissions and remoting requirements.</span></span>

### <a name="how-to-run-as-administrator"></a><span data-ttu-id="b0c22-113">管理者として実行する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-113">How to run as administrator</span></span>

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

<span data-ttu-id="b0c22-114">ローカルコンピューターでリモートセッションを開始したり、WSMan: ドライブのローカルコンピューターの設定を表示または変更したりするには、[ **管理者として実行** ] オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-114">To start a remote session on the local computer, or to view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start Windows PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="b0c22-115">[ **管理者として実行** ] オプションを使用して Windows PowerShell を起動するには</span><span class="sxs-lookup"><span data-stu-id="b0c22-115">To start Windows PowerShell with the **Run as administrator** option:</span></span>

- <span data-ttu-id="b0c22-116">Windows PowerShell (または Windows PowerShell ISE) アイコンを右クリックし、[ **管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-116">Right-click a Windows PowerShell (or Windows PowerShell ISE) icon and then click **Run as administrator**.</span></span>

  <span data-ttu-id="b0c22-117">Windows 7 と Windows Server 2008 R2 で [ **管理者として実行** ] オプションを使用して windows PowerShell を起動するには</span><span class="sxs-lookup"><span data-stu-id="b0c22-117">To start Windows PowerShell with the **Run as administrator** option in Windows 7 and Windows Server 2008 R2.</span></span>

- <span data-ttu-id="b0c22-118">Windows タスクバーで、Windows PowerShell アイコンを右クリックし、[ **管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-118">In the Windows taskbar, right-click the Windows PowerShell icon, and then click **Run as administrator**.</span></span>

  <span data-ttu-id="b0c22-119">Windows Server 2008 R2 では、Windows PowerShell アイコンが既定でタスクバーに固定されています。</span><span class="sxs-lookup"><span data-stu-id="b0c22-119">In Windows Server 2008 R2, the Windows PowerShell icon is pinned to the taskbar by default.</span></span>

### <a name="how-to-enable-remoting"></a><span data-ttu-id="b0c22-120">リモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-120">How to enable remoting</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

<span data-ttu-id="b0c22-121">コンピューターがリモートコマンドを送信できるようにするための構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-121">No configuration is required to enable a computer to send remote commands.</span></span>
<span data-ttu-id="b0c22-122">ただし、リモートコマンドを受信するには、コンピューターで PowerShell リモート処理を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-122">However, to receive remote commands, PowerShell remoting must be enabled on the computer.</span></span> <span data-ttu-id="b0c22-123">を有効にするには、WinRM サービスの開始、WinRM サービスのスタートアップの種類の自動への設定、HTTP 接続と HTTPS 接続のためのリスナーの作成、既定のセッション構成の作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-123">Enabling includes starting the WinRM service, setting the startup type for the WinRM service to Automatic, creating listeners for HTTP and HTTPS connections, and creating default session configurations.</span></span>

<span data-ttu-id="b0c22-124">Windows PowerShell リモート処理は、windows server 2012 以降の windows Server の既定のリリースで有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b0c22-124">Windows PowerShell remoting is enabled on Windows Server 2012 and newer releases of Windows Server by default.</span></span> <span data-ttu-id="b0c22-125">他のすべてのシステムでは、コマンドレットを実行して `Enable-PSRemoting` リモート処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-125">On all other systems, run the `Enable-PSRemoting` cmdlet to enable remoting.</span></span> <span data-ttu-id="b0c22-126">`Enable-PSRemoting`リモート処理が無効になっている場合は、コマンドレットを実行して、windows server 2012 および Windows server の新しいリリースでリモート処理を再度有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-126">You can also run the `Enable-PSRemoting` cmdlet to re-enable remoting on Windows Server 2012 and newer releases of Windows Server if remoting is disabled.</span></span>

<span data-ttu-id="b0c22-127">リモートコマンドを受信するようにコンピューターを構成するには、コマンドレットを使用し `Enable-PSRemoting` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-127">To configure a computer to receive remote commands, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="b0c22-128">次のコマンドは、必要なすべてのリモート設定を有効にし、セッション構成を有効にして、WinRM サービスを再起動して変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-128">The following command enables all required remote settings, enables the session configurations, and restarts the WinRM service to make the changes effective.</span></span>

`Enable-PSRemoting`

<span data-ttu-id="b0c22-129">すべてのユーザープロンプトを非表示にするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-129">To suppress all user prompts, type:</span></span>

`Enable-PSRemoting -Force`

<span data-ttu-id="b0c22-130">詳細については、「 [enable-psremoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-130">For more information, see [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span></span>

### <a name="how-to-enable-remoting-in-an-enterprise"></a><span data-ttu-id="b0c22-131">企業でリモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-131">How to enable remoting in an enterprise</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="b0c22-132">1台のコンピューターでリモート PowerShell コマンドを受信して接続を受け入れるには、コマンドレットを使用し `Enable-PSRemoting` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-132">To enable a single computer to receive remote PowerShell commands and accept connections, use the `Enable-PSRemoting` cmdlet.</span></span>

<span data-ttu-id="b0c22-133">企業内の複数のコンピューターでリモート処理を有効にするには、次のスケーリングされたオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-133">To enable remoting for multiple computers in an enterprise, you can use the following scaled options.</span></span>

- <span data-ttu-id="b0c22-134">リモート処理のリスナーを構成するには、[ **リスナーの自動構成を許可** する] グループポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-134">To configure listeners for remoting, enable the **Allow automatic configuration of listeners** group policy.</span></span>

- <span data-ttu-id="b0c22-135">複数のコンピューターで Windows リモート管理 (WinRM) のスタートアップの種類を [自動] に設定するには、コマンドレットを使用し `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-135">To set the startup type of the Windows Remote Management (WinRM) to Automatic on multiple computers, use the `Set-Service` cmdlet.</span></span>

- <span data-ttu-id="b0c22-136">ファイアウォールの例外を有効にするには、[ **Windows ファイアウォール: ローカルポートの例外を許可** する] グループポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-136">To enable a firewall exception, use the **Windows Firewall: Allow Local Port Exceptions** group policy.</span></span>

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a><span data-ttu-id="b0c22-137">グループポリシーを使用してリスナーを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-137">How to enable listeners by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="b0c22-138">ドメイン内のすべてのコンピューターのリスナーを構成するには、次のグループポリシーパスで [ **リスナーの自動構成を許可** する] ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-138">To configure the listeners for all computers in a domain, enable the **Allow automatic configuration of listeners** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

<span data-ttu-id="b0c22-139">ポリシーを有効にし、IPv4 フィルターと IPv6 フィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-139">Enable the policy and specify the IPv4 and IPv6 filters.</span></span> <span data-ttu-id="b0c22-140">ワイルドカード ( `*` ) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-140">Wildcards (`*`) are permitted.</span></span>

### <a name="how-to-enable-remoting-on-public-networks"></a><span data-ttu-id="b0c22-141">パブリックネットワークでリモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-141">How to enable remoting on public networks</span></span>

```
ERROR:  Unable to check the status of the firewall
```

<span data-ttu-id="b0c22-142">`Enable-PSRemoting`コマンドレットは、ローカルネットワークがパブリックで、 **SkipNetworkProfileCheck** パラメーターがコマンドで使用されていない場合に、このエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-142">The `Enable-PSRemoting` cmdlet returns this error when the local network is public and the **SkipNetworkProfileCheck** parameter is not used in the command.</span></span>

<span data-ttu-id="b0c22-143">Windows のサーバーバージョンでは、は `Enable-PSRemoting` すべてのネットワークの場所の種類に対して成功します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-143">On server versions of Windows, `Enable-PSRemoting` succeeds on all network location types.</span></span> <span data-ttu-id="b0c22-144">プライベートおよびドメイン ("ホーム" および "作業") ネットワークへのリモートアクセスを許可するファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-144">It creates firewall rules that allow remote access to private and domain ("Home" and "Work") networks.</span></span> <span data-ttu-id="b0c22-145">パブリックネットワークの場合、同じローカルサブネットからのリモートアクセスを許可するファイアウォール規則が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-145">For public networks, it creates firewall rules that allows remote access from the same local subnet.</span></span>

<span data-ttu-id="b0c22-146">Windows のクライアントバージョンでは、は `Enable-PSRemoting` プライベートネットワークとドメインネットワークで成功します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-146">On client versions of Windows, `Enable-PSRemoting` succeeds on private and domain networks.</span></span> <span data-ttu-id="b0c22-147">既定では、パブリックネットワークでは失敗しますが、 **SkipNetworkProfileCheck** パラメーターを使用すると、は `Enable-PSRemoting` 成功し、同じローカルサブネットからのトラフィックを許可するファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-147">By default, it fails on public networks, but if you use the **SkipNetworkProfileCheck** parameter, `Enable-PSRemoting` succeeds and creates a firewall rule that allows traffic from the same local subnet.</span></span>

<span data-ttu-id="b0c22-148">パブリックネットワークのローカルサブネットの制限を削除し、任意の場所からのリモートアクセスを許可するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-148">To remove the local subnet restriction on public networks and allow remote access from any location, run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="b0c22-149">`Set-NetFirewallRule`コマンドレットは、NetSecurity モジュールによってエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-149">The `Set-NetFirewallRule` cmdlet is exported by the NetSecurity module.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c22-150">Windows PowerShell 2.0 では、サーバーバージョンの Windows を実行しているコンピューターで、 `Enable-PSRemoting` プライベート、ドメイン、およびパブリックネットワークでのリモートアクセスを許可するファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-150">In Windows PowerShell 2.0, on computers running server versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access on private, domain and public networks.</span></span> <span data-ttu-id="b0c22-151">クライアントバージョンの Windows を実行しているコンピューターでは、は、 `Enable-PSRemoting` プライベートネットワークとドメインネットワーク上でのみリモートアクセスを許可するファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-151">On computers running client versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access only on private and domain networks.</span></span>

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a><span data-ttu-id="b0c22-152">グループポリシーを使用してファイアウォールの例外を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-152">How to enable a firewall exception by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="b0c22-153">ドメイン内のすべてのコンピューターでのファイアウォールの例外を有効にするには、次のグループポリシーパスで [ **Windows ファイアウォール: ローカルポートの例外を許可** する] ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-153">To enable a firewall exception for in all computers in a domain, enable the **Windows Firewall: Allow local port exceptions** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

<span data-ttu-id="b0c22-154">このポリシーにより、コンピューターの Administrators グループのメンバーは、**コントロールパネル** の **Windows ファイアウォール** を使用して、Windows リモート管理サービスのファイアウォールの例外を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-154">This policy allows members of the Administrators group on the computer to use **Windows Firewall** in **Control Panel** to create a firewall exception for the Windows Remote Management service.</span></span>

<span data-ttu-id="b0c22-155">ポリシーの構成が正しくない場合は、次のエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-155">If the policy configuration is incorrect you may receive the following error:</span></span>

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

<span data-ttu-id="b0c22-156">ポリシーの構成エラーが発生すると、 **ListeningOn** プロパティの値が空になります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-156">A configuration error in the policy results in an empty value for the **ListeningOn** property.</span></span> <span data-ttu-id="b0c22-157">次のコマンドを使用して、値を確認します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-157">Use the following command to check the value.</span></span>

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

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a><span data-ttu-id="b0c22-158">WinRM サービスのスタートアップの種類を設定する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-158">How to set the startup type of the WinRM service</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="b0c22-159">PowerShell リモート処理は、Windows リモート管理 (WinRM) サービスに依存します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-159">PowerShell remoting depends upon the Windows Remote Management (WinRM) service.</span></span>
<span data-ttu-id="b0c22-160">リモートコマンドをサポートするには、サービスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-160">The service must be running to support remote commands.</span></span>

<span data-ttu-id="b0c22-161">Windows のサーバーバージョンでは、Windows リモート管理 (WinRM) サービスのスタートアップの種類が [自動] になります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-161">On server versions of Windows, the startup type of the Windows Remote Management (WinRM) service is Automatic.</span></span>

<span data-ttu-id="b0c22-162">ただし、クライアントバージョンの Windows では、WinRM サービスは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b0c22-162">However, on client versions of Windows, the WinRM service is disabled by default.</span></span>

<span data-ttu-id="b0c22-163">リモートコンピューター上のサービスのスタートアップの種類を設定するには、 `Set-Service` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-163">To set the startup type of a service on a remote computer, use the `Set-Service` cmdlet.</span></span>

<span data-ttu-id="b0c22-164">複数のコンピューターでコマンドを実行するには、コンピューター名のテキストファイルまたは CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-164">To run the command on multiple computers, you can create a text file or CSV file of the computer names.</span></span>

<span data-ttu-id="b0c22-165">たとえば、次のコマンドは、ファイルからコンピューター名の一覧を取得 `Servers.txt` し、すべてのコンピューター上の WinRM サービスのスタートアップの種類を **自動** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-165">For example, the following commands get a list of computer names from the `Servers.txt` file and then sets the startup type of the WinRM service on all of the computers to **Automatic**.</span></span>

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

<span data-ttu-id="b0c22-166">結果を表示するには、 `Get-WMIObject` コマンドレットを **Win32_Service** オブジェクトと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-166">To see the results use the `Get-WMIObject` cmdlet with the **Win32_Service** object.</span></span> <span data-ttu-id="b0c22-167">詳細については、「 [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-167">For more information, see [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span></span>

### <a name="how-to-recreate-the-default-session-configurations"></a><span data-ttu-id="b0c22-168">既定のセッション構成を再作成する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-168">How to recreate the default session configurations</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="b0c22-169">ローカルコンピューターに接続してコマンドをリモートで実行するには、ローカルコンピューターにリモートコマンドのセッション構成が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-169">To connect to the local computer and run commands remotely, the local computer must include session configurations for remote commands.</span></span>

<span data-ttu-id="b0c22-170">を使用すると `Enable-PSRemoting` 、ローカルコンピューター上に既定のセッション構成が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-170">When you use `Enable-PSRemoting`, it creates default session configurations on the local computer.</span></span> <span data-ttu-id="b0c22-171">リモートユーザーは、リモートコマンドに **ConfigurationName** パラメーターが含まれていない場合に、これらのセッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-171">Remote users use these session configurations whenever a remote command does not include the **ConfigurationName** parameter.</span></span>

<span data-ttu-id="b0c22-172">コンピューターの既定の構成が登録解除または削除されている場合は、コマンドレットを使用して `Enable-PSRemoting` 再作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-172">If the default configurations on a computer are unregistered or deleted, use the `Enable-PSRemoting` cmdlet to recreate them.</span></span> <span data-ttu-id="b0c22-173">このコマンドレットを繰り返し使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-173">You can use this cmdlet repeatedly.</span></span> <span data-ttu-id="b0c22-174">機能が既に構成されている場合、エラーは生成されません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-174">It does not generate errors if a feature is already configured.</span></span>

<span data-ttu-id="b0c22-175">既定のセッション構成を変更し、元の既定のセッション構成を復元する場合は、コマンドレットを使用して `Unregister-PSSessionConfiguration` 変更されたセッション構成を削除してから、コマンドレットを使用して `Enable-PSRemoting` 復元します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-175">If you change the default session configurations and want to restore the original default session configurations, use the `Unregister-PSSessionConfiguration` cmdlet to delete the changed session configurations and then use the `Enable-PSRemoting` cmdlet to restore them.</span></span>
<span data-ttu-id="b0c22-176">`Enable-PSRemoting` では、既存のセッション構成は変更されません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-176">`Enable-PSRemoting` does not change existing session configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c22-177">は、既定のセッション構成を復元するときに、 `Enable-PSRemoting` 構成に対して明示的なセキュリティ記述子を作成しません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-177">When `Enable-PSRemoting` restores the default session configuration, it does not create explicit security descriptors for the configurations.</span></span> <span data-ttu-id="b0c22-178">代わりに、構成は RootSDDL のセキュリティ記述子を継承します。これは既定ではセキュリティで保護されています。</span><span class="sxs-lookup"><span data-stu-id="b0c22-178">Instead, the configurations inherit the security descriptor of the RootSDDL, which is secure by default.</span></span>

<span data-ttu-id="b0c22-179">RootSDDL セキュリティ記述子を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-179">To see the RootSDDL security descriptor, type:</span></span>

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

<span data-ttu-id="b0c22-180">RootSDDL を変更するには、 `Set-Item` WSMan: ドライブのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-180">To change the RootSDDL, use the `Set-Item` cmdlet in the WSMan: drive.</span></span> <span data-ttu-id="b0c22-181">セッション構成のセキュリティ記述子を変更するには、 `Set-PSSessionConfiguration` コマンドレットを **Securitydescriptor sddl** または **showsecuritydescriptor ui** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-181">To change the security descriptor of a session configuration, use the `Set-PSSessionConfiguration` cmdlet with the **SecurityDescriptorSDDL** or **ShowSecurityDescriptorUI** parameters.</span></span>

<span data-ttu-id="b0c22-182">WSMan: ドライブの詳細については、WSMan プロバイダーのヘルプトピック ("Get-help WSMan") を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-182">For more information about the WSMan: drive, see the Help topic for the WSMan provider ("Get-Help wsman").</span></span>

### <a name="how-to-provide-administrator-credentials"></a><span data-ttu-id="b0c22-183">管理者の資格情報を指定する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-183">How to provide administrator credentials</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="b0c22-184">リモートコンピューターで PSSession を作成したりコマンドを実行したりするには、既定では、現在のユーザーがリモートコンピューターの Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-184">To create a PSSession or run commands on a remote computer, by default, the current user must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="b0c22-185">現在のユーザーが Administrators グループのメンバーであるアカウントにログオンしている場合でも、資格情報が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-185">Credentials are sometimes required even when the current user is logged on to an account that is a member of the Administrators group.</span></span>

<span data-ttu-id="b0c22-186">現在のユーザーがリモートコンピューターの Administrators グループのメンバーである場合、または Administrators グループのメンバーの資格情報を提供できる場合は、、、またはコマンドレットの **Credential** パラメーターを使用して `New-PSSession` 、 `Enter-PSSession` `Invoke-Command` リモートで接続します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-186">If the current user is a member of the Administrators group on the remote computer, or can provide the credentials of a member of the Administrators group, use the **Credential** parameter of the `New-PSSession`, `Enter-PSSession` or `Invoke-Command` cmdlets to connect remotely.</span></span>

<span data-ttu-id="b0c22-187">たとえば、次のコマンドは、管理者の資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-187">For example, the following command provides the credentials of an Administrator.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="b0c22-188">**Credential** パラメーターの詳細については、「 [New-pssession](xref:Microsoft.PowerShell.Core.New-PSSession)」、「 [-pssession](xref:Microsoft.PowerShell.Core.Enter-PSSession) 」、または「 [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-188">For more information about the **Credential** parameter, see [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span></span>

### <a name="how-to-enable-remoting-for-non-administrative-users"></a><span data-ttu-id="b0c22-189">管理者以外のユーザーのリモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-189">How to enable remoting for non-administrative users</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="b0c22-190">リモートコンピューター上で PSSession を確立したりコマンドを実行したりするには、リモートコンピューターでセッション構成を使用するためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="b0c22-190">To establish a PSSession or run a command on a remote computer, the user must have permission to use the session configurations on the remote computer.</span></span>

<span data-ttu-id="b0c22-191">既定では、コンピューターの Administrators グループのメンバーだけが、既定のセッション構成を使用するアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="b0c22-191">By default, only members of the Administrators group on a computer have permission to use the default session configurations.</span></span> <span data-ttu-id="b0c22-192">したがって、Administrators グループのメンバーだけがリモートでコンピューターに接続できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-192">Therefore, only members of the Administrators group can connect to the computer remotely.</span></span>

<span data-ttu-id="b0c22-193">他のユーザーがローカルコンピューターに接続できるようにするには、ローカルコンピューター上の既定のセッション構成に対する実行アクセス許可をユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-193">To allow other users to connect to the local computer, give the user Execute permissions to the default session configurations on the local computer.</span></span>

<span data-ttu-id="b0c22-194">次のコマンドを実行すると、プロパティシートが開き、ローカルコンピューター上の既定の Microsoft PowerShell セッション構成のセキュリティ記述子を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-194">The following command opens a property sheet that lets you change the security descriptor of the default Microsoft.PowerShell session configuration on the local computer.</span></span>

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

<span data-ttu-id="b0c22-195">詳細については、「 [about_Session_Configurations](about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-195">For more information, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a><span data-ttu-id="b0c22-196">他のドメインの管理者のリモート処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-196">How to enable remoting for administrators in other domains</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="b0c22-197">別のドメインのユーザーがローカルコンピューターの Administrators グループのメンバーである場合、ユーザーは管理者特権でローカルコンピューターにリモート接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-197">When a user in another domain is a member of the Administrators group on the local computer, the user cannot connect to the local computer remotely with Administrator privileges.</span></span> <span data-ttu-id="b0c22-198">既定では、他のドメインからのリモート接続は、標準のユーザー特権トークンのみを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-198">By default, remote connections from other domains run with only standard user privilege tokens.</span></span>

<span data-ttu-id="b0c22-199">ただし、 **LocalAccountTokenFilterPolicy** レジストリエントリを使用して既定の動作を変更し、Administrators グループのメンバーであるリモートユーザーが管理者特権で実行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-199">However, you can use the **LocalAccountTokenFilterPolicy** registry entry to change the default behavior and allow remote users who are members of the Administrators group to run with Administrator privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="b0c22-200">**LocalAccountTokenFilterPolicy** エントリは、影響を受けるすべてのコンピューターのすべてのユーザーに対するユーザーアカウント制御 (UAC) リモート制限を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-200">The **LocalAccountTokenFilterPolicy** entry disables user account control (UAC) remote restrictions for all users of all affected computers.</span></span> <span data-ttu-id="b0c22-201">ポリシーを変更する前に、この設定の影響を慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-201">Consider the implications of this setting carefully before changing the policy.</span></span>

<span data-ttu-id="b0c22-202">ポリシーを変更するには、次のコマンドを使用して、 **LocalAccountTokenFilterPolicy** レジストリエントリの値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-202">To change the policy, use the following command to set the value of the **LocalAccountTokenFilterPolicy** registry entry to 1.</span></span>

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a><span data-ttu-id="b0c22-203">リモートコマンドで ip アドレスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-203">How to use an ip address in a remote command</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="b0c22-204">、、およびコマンドレットの **ComputerName** パラメーターは、 `New-PSSession` `Enter-PSSession` `Invoke-Command` IP アドレスを有効な値として受け入れます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-204">The **ComputerName** parameter of the `New-PSSession`, `Enter-PSSession` and `Invoke-Command` cmdlets accepts an IP address as a valid value.</span></span> <span data-ttu-id="b0c22-205">ただし、Kerberos 認証では IP アドレスがサポートされないため、IP アドレスを指定するたびに、NTLM 認証が既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-205">However, because Kerberos authentication does not support IP addresses, NTLM authentication is used by default whenever you specify an IP address.</span></span>

<span data-ttu-id="b0c22-206">NTLM 認証を使用する場合、リモート処理には次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="b0c22-206">When using NTLM authentication, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="b0c22-207">HTTPS トランスポート用にコンピューターを構成するか、ローカルコンピューターの TrustedHosts の一覧にリモートコンピューターの IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-207">Configure the computer for HTTPS transport or add the IP addresses of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="b0c22-208">すべてのリモートコマンドで **Credential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-208">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="b0c22-209">これは、現在のユーザーの資格情報を送信する場合でも必要です。</span><span class="sxs-lookup"><span data-stu-id="b0c22-209">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a><span data-ttu-id="b0c22-210">ワークグループベースのコンピューターからリモート接続する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-210">How to connect remotely from a workgroup-based computer</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="b0c22-211">ローカルコンピューターがドメイン内にない場合、リモート処理には次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="b0c22-211">When the local computer is not in a domain, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="b0c22-212">HTTPS トランスポート用にコンピューターを構成するか、ローカルコンピューターの TrustedHosts の一覧にリモートコンピューターの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-212">Configure the computer for HTTPS transport or add the names of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="b0c22-213">ワークグループベースのコンピューターにパスワードが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-213">Verify that a password is set on the workgroup-based computer.</span></span> <span data-ttu-id="b0c22-214">パスワードが設定されていない場合、またはパスワード値が空の場合は、リモートコマンドを実行できません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-214">If a password is not set or the password value is empty, you cannot run remote commands.</span></span>

   <span data-ttu-id="b0c22-215">ユーザーアカウントのパスワードを設定するには、コントロールパネルの [ユーザーアカウント] を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-215">To set password for your user account, use User Accounts in Control Panel.</span></span>

1. <span data-ttu-id="b0c22-216">すべてのリモートコマンドで **Credential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-216">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="b0c22-217">これは、現在のユーザーの資格情報を送信する場合でも必要です。</span><span class="sxs-lookup"><span data-stu-id="b0c22-217">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a><span data-ttu-id="b0c22-218">信頼されたホストの一覧にコンピューターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-218">How to add a computer to the trusted hosts list</span></span>

<span data-ttu-id="b0c22-219">TrustedHosts 項目には、コンピューター名、IP アドレス、および完全修飾ドメイン名のコンマ区切りの一覧を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-219">The TrustedHosts item can contain a comma-separated list of computer names, IP addresses, and fully-qualified domain names.</span></span> <span data-ttu-id="b0c22-220">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-220">Wildcards are permitted.</span></span>

<span data-ttu-id="b0c22-221">信頼されたホストの一覧を表示または変更するには、WSMan: ドライブを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-221">To view or change the trusted host list, use the WSMan: drive.</span></span> <span data-ttu-id="b0c22-222">TrustedHost 項目は `WSMan:\localhost\Client` ノードにあります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-222">The TrustedHost item is in the `WSMan:\localhost\Client` node.</span></span>

<span data-ttu-id="b0c22-223">コンピューターの Administrators グループのメンバーだけが、コンピューター上の信頼されたホストの一覧を変更するアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="b0c22-223">Only members of the Administrators group on the computer have permission to change the list of trusted hosts on the computer.</span></span>

<span data-ttu-id="b0c22-224">注意: TrustedHosts 項目に対して設定した値は、コンピューターのすべてのユーザーに影響します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-224">Caution: The value that you set for the TrustedHosts item affects all users of the computer.</span></span>

<span data-ttu-id="b0c22-225">信頼されたホストの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-225">To view the list of trusted hosts, use the following command:</span></span>

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

<span data-ttu-id="b0c22-226">また、 `Set-Location` コマンドレット (alias = cd) を使用して、WSMan: ドライブを場所に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-226">You can also use the `Set-Location` cmdlet (alias = cd) to navigate though the WSMan: drive to the location.</span></span> <span data-ttu-id="b0c22-227">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-227">For example:</span></span>

```powershell
cd WSMan:\localhost\Client; dir
```

<span data-ttu-id="b0c22-228">すべてのコンピューターを信頼されたホストの一覧に追加するには、次のコマンドを使用します。このコマンドは、ComputerName に \* (all) の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-228">To add all computers to the list of trusted hosts, use the following command, which places a value of \* (all) in the ComputerName</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

<span data-ttu-id="b0c22-229">ワイルドカード文字 () を使用し `*` て、特定のドメインにあるすべてのコンピューターを、信頼されたホストの一覧に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-229">You can also use a wildcard character (`*`) to add all computers in a particular domain to the list of trusted hosts.</span></span> <span data-ttu-id="b0c22-230">たとえば、次のコマンドは、Fabrikam ドメインにあるすべてのコンピューターを、信頼されたホストの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-230">For example, the following command adds all of the computers in the Fabrikam domain to the list of trusted hosts.</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

<span data-ttu-id="b0c22-231">特定のコンピューターの名前を信頼されたホストの一覧に追加するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-231">To add the names of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

<span data-ttu-id="b0c22-232">各値 `<ComputerName>` の形式は次のとおりでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-232">where each value `<ComputerName>` must have the following format:</span></span>

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

<span data-ttu-id="b0c22-233">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-233">For example:</span></span>

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

<span data-ttu-id="b0c22-234">既存の信頼されたホストの一覧にコンピューター名を追加するには、まず、現在の値を変数に保存し、その値を、現在の値と新しい値を含むコンマ区切りのリストに設定します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-234">To add a computer name to an existing list of trusted hosts, first save the current value in a variable, and then set the value to a comma-separated list that includes the current and new values.</span></span>

<span data-ttu-id="b0c22-235">たとえば、Server01 コンピューターを既存の信頼されたホストの一覧に追加するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-235">For example, to add the Server01 computer to an existing list of trusted hosts, use the following command</span></span>

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

<span data-ttu-id="b0c22-236">特定のコンピューターの IP アドレスを信頼されたホストの一覧に追加するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-236">To add the IP addresses of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

<span data-ttu-id="b0c22-237">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-237">For example:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

<span data-ttu-id="b0c22-238">コンピューターをリモートコンピューターの TrustedHosts の一覧に追加するには、コマンドレットを使用して、 `Connect-WSMan` リモートコンピューターのノードをローカルコンピューターの WSMan: ドライブに追加します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-238">To add a computer to the TrustedHosts list of a remote computer, use the `Connect-WSMan` cmdlet to add a node for the remote computer to the WSMan: drive on the local computer.</span></span> <span data-ttu-id="b0c22-239">次に、コマンドを使用し `Set-Item` てコンピューターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-239">Then use a `Set-Item` command to add the computer.</span></span>

<span data-ttu-id="b0c22-240">コマンドレットの詳細につい `Connect-WSMan` ては、「 [接続-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-240">For more information about the `Connect-WSMan` cmdlet, see [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span>

## <a name="troubleshooting-computer-configuration-issues"></a><span data-ttu-id="b0c22-241">コンピューターの構成に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0c22-241">Troubleshooting computer configuration issues</span></span>

<span data-ttu-id="b0c22-242">ここでは、コンピューター、ドメイン、または企業の特定の構成に関連するリモート処理の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-242">This section discusses remoting problems that are related to particular configurations of a computer, domain, or enterprise.</span></span>

### <a name="how-to-configure-remoting-on-alternate-ports"></a><span data-ttu-id="b0c22-243">代替ポートでリモート処理を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-243">How to configure remoting on alternate ports</span></span>

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="b0c22-244">PowerShell リモート処理では、既定で HTTP トランスポートにポート80を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-244">PowerShell remoting uses port 80 for HTTP transport by default.</span></span> <span data-ttu-id="b0c22-245">既定のポートは、ユーザーがリモートコマンドで **Connectionuri** または **ポート** パラメーターを指定していない場合に常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-245">The default port is used whenever the user does not specify the **ConnectionURI** or **Port** parameters in a remote command.</span></span>

<span data-ttu-id="b0c22-246">PowerShell が使用する既定のポートを変更するには、WSMan: ドライブのコマンドレットを使用して、 `Set-Item` リスナーのリーフノードのポート値を変更します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-246">To change the default port that PowerShell uses, use `Set-Item` cmdlet in the WSMan: drive to change the Port value in the listener leaf node.</span></span>

<span data-ttu-id="b0c22-247">たとえば、次のコマンドは、既定のポートを8080に変更します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-247">For example, the following command changes the default port to 8080.</span></span>

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a><span data-ttu-id="b0c22-248">プロキシサーバーを使用してリモート処理を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-248">How to configure remoting with a proxy server</span></span>

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

<span data-ttu-id="b0c22-249">PowerShell リモート処理は HTTP プロトコルを使用するため、HTTP プロキシ設定の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-249">Because PowerShell remoting uses the HTTP protocol, it is affected by HTTP proxy settings.</span></span> <span data-ttu-id="b0c22-250">プロキシサーバーを使用している企業では、ユーザーは PowerShell リモートコンピューターに直接アクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-250">In enterprises that have proxy servers, users cannot access a PowerShell remote computer directly.</span></span>

<span data-ttu-id="b0c22-251">この問題を解決するには、リモートコマンドでプロキシ設定オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-251">To resolve this problem, use proxy setting options in your remote command.</span></span> <span data-ttu-id="b0c22-252">次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-252">The following settings are available:</span></span>

- <span data-ttu-id="b0c22-253">System.management.automation.remoting.proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="b0c22-253">ProxyAccessType</span></span>
- <span data-ttu-id="b0c22-254">ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="b0c22-254">ProxyAuthentication</span></span>
- <span data-ttu-id="b0c22-255">ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="b0c22-255">ProxyCredential</span></span>

<span data-ttu-id="b0c22-256">特定のコマンドに対してこれらのオプションを設定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b0c22-256">To set these options for a particular command, use the following procedure:</span></span>

1. <span data-ttu-id="b0c22-257">コマンドレットの **system.management.automation.remoting.proxyaccesstype**、 **Proxyauthentication**、および **proxyauthentication** パラメーターを使用して、 `New-PSSessionOption` 企業のプロキシ設定を使用してセッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-257">Use the **ProxyAccessType**, **ProxyAuthentication**, and **ProxyCredential** parameters of the `New-PSSessionOption` cmdlet to create a session option object with the proxy settings for your enterprise.</span></span> <span data-ttu-id="b0c22-258">[保存] オプションオブジェクトは変数です。</span><span class="sxs-lookup"><span data-stu-id="b0c22-258">Save the option object is a variable.</span></span>

1. <span data-ttu-id="b0c22-259">、、またはコマンドの **Sessionoption** パラメーターの値として、option オブジェクトを含む変数を使用し `New-PSSession` `Enter-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-259">Use the variable that contains the option object as the value of the **SessionOption** parameter of a `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` command.</span></span>

<span data-ttu-id="b0c22-260">たとえば、次のコマンドは、プロキシセッションオプションを使用してセッションオプションオブジェクトを作成し、オブジェクトを使用してリモートセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-260">For example, the following command creates a session option object with proxy session options and then uses the object to create a remote session.</span></span>

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

<span data-ttu-id="b0c22-261">コマンドレットの詳細につい `New-PSSessionOption` ては、「 [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-261">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="b0c22-262">現在のセッションのすべてのリモートコマンドに対してこれらのオプションを設定するには、ユーザー `New-PSSessionOption` 設定変数の値にを作成する option オブジェクトを使用し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-262">To set these options for all remote commands in the current session, use the option object that `New-PSSessionOption` creates in the value of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="b0c22-263">詳細については、「 [about_Preference_Variables](about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-263">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="b0c22-264">すべてのリモートコマンドに対して、ローカルコンピューター上のすべての PowerShell セッションに対してこれらのオプションを設定するには、 `$PSSessionOption` ユーザー設定変数を powershell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-264">To set these options for all remote commands all PowerShell sessions on the local computer, add the `$PSSessionOption` preference variable to your PowerShell profile.</span></span> <span data-ttu-id="b0c22-265">PowerShell プロファイルの詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-265">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a><span data-ttu-id="b0c22-266">64ビットコンピューターで32ビットセッションを検出する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-266">How to detect a 32-bit session on a 64-bit computer</span></span>

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="b0c22-267">リモートコンピューターが64ビットバージョンの Windows を実行していて、リモートコマンドが Microsoft.powershell32 などの32ビットのセッション構成を使用している場合、Windows リモート管理 (WinRM) は WOW64 プロセスを読み込み、Windows はディレクトリへのすべての参照をディレクトリに自動的にリダイレクトし `$env:Windir\System32` `$env:Windir\SysWOW64` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-267">If the remote computer is running a 64-bit version of Windows, and the remote command is using a 32-bit session configuration, such as Microsoft.PowerShell32, Windows Remote Management (WinRM) loads a WOW64 process and Windows automatically redirects all references to the `$env:Windir\System32` directory to the `$env:Windir\SysWOW64` directory.</span></span>

<span data-ttu-id="b0c22-268">このため、のように、SysWow64 ディレクトリ (など) に対応するものがない System32 ディレクトリ内のツールを使用しようとすると、 `Defrag.exe` ツールがディレクトリに見つかりません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-268">As a result, if you try to use tools in the System32 directory that do not have counterparts in the SysWow64 directory, such as `Defrag.exe`, the tools cannot be found in the directory.</span></span>

<span data-ttu-id="b0c22-269">セッションで使用されているプロセッサアーキテクチャを確認するには、 **PROCESSOR_ARCHITECTURE** 環境変数の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-269">To find the processor architecture that is being used in the session, use the value of the **PROCESSOR_ARCHITECTURE** environment variable.</span></span> <span data-ttu-id="b0c22-270">次のコマンドは、変数内のセッションのプロセッサアーキテクチャを検索し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-270">The following command finds the processor architecture of the session in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

<span data-ttu-id="b0c22-271">セッション構成の詳細については、「 [about_Session_Configurations](about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-271">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="troubleshooting-policy-and-preference-issues"></a><span data-ttu-id="b0c22-272">ポリシーと基本設定に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0c22-272">Troubleshooting policy and preference issues</span></span>

<span data-ttu-id="b0c22-273">ここでは、ローカルコンピューターとリモートコンピューターで設定されたポリシーと基本設定に関連するリモート処理の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-273">This section discusses remoting problems that are related to policies and preferences set on the local and remote computers.</span></span>

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a><span data-ttu-id="b0c22-274">Import-PSSession および Import-Module の実行ポリシーを変更する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-274">How to change the execution policy for Import-PSSession and Import-Module</span></span>

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

<span data-ttu-id="b0c22-275">`Import-PSSession`および `Export-PSSession` コマンドレットは、署名されていないスクリプトファイルとフォーマットファイルを含むモジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-275">The `Import-PSSession` and `Export-PSSession` cmdlets create modules that contains unsigned script files and formatting files.</span></span>

<span data-ttu-id="b0c22-276">またはを使用してこれらのコマンドレットによって作成されたモジュールをインポートするには、 `Import-PSSession` `Import-Module` 現在のセッションの実行ポリシーを制限することも AllSigned することもできません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-276">To import the modules that are created by these cmdlets, either by using `Import-PSSession` or `Import-Module`, the execution policy in the current session cannot be Restricted or AllSigned.</span></span> <span data-ttu-id="b0c22-277">PowerShell 実行ポリシーの詳細については、「 [about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-277">For information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="b0c22-278">レジストリに設定されているローカルコンピューターの実行ポリシーを変更せずにモジュールをインポートするには、の **Scope** パラメーターを使用して、 `Set-ExecutionPolicy` 1 つのプロセスに対して制限の少ない実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-278">To import the modules without changing the execution policy for the local computer that is set in the registry, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>

<span data-ttu-id="b0c22-279">たとえば、次のコマンドは、実行ポリシーを使用してプロセスを開始し `RemoteSigned` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-279">For example, the following command starts a process with the `RemoteSigned` execution policy.</span></span> <span data-ttu-id="b0c22-280">実行ポリシーの変更は現在のプロセスのみに影響し、PowerShell **set-executionpolicy** レジストリ設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-280">The execution policy change affects only the current process and does not change the PowerShell **ExecutionPolicy** registry setting.</span></span>

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="b0c22-281">の **set-executionpolicy** パラメーターを使用して、 `PowerShell.exe` より制限の少ない実行ポリシーで1つのセッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-281">You can also use the **ExecutionPolicy** parameter of `PowerShell.exe` to start a single session with a less restrictive execution policy.</span></span>

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="b0c22-282">実行ポリシーの詳細については、「 [about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-282">For more information about execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span> <span data-ttu-id="b0c22-283">詳細を表示するには「`PowerShell.exe -?`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-283">For more information, type `PowerShell.exe -?`.</span></span>

### <a name="how-to-set-and-change-quotas"></a><span data-ttu-id="b0c22-284">クォータを設定および変更する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-284">How to set and change quotas</span></span>

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

<span data-ttu-id="b0c22-285">クォータを使用すると、ローカルコンピューターとリモートコンピューターが、偶発的でも悪意のあるリソースでも使用されないように保護することができます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-285">You can use quotas to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span>

<span data-ttu-id="b0c22-286">基本構成では、次のクォータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-286">The following quotas are available in the basic configuration.</span></span>

- <span data-ttu-id="b0c22-287">WSMan プロバイダー (WSMan:)では、ノードの **MaxEnvelopeSizeKB** および **maxproviderrequests** 設定、 `WSMan:<ComputerName>` ノードの **MaxConcurrentOperations**、 **maxconcurrentoperationsperuser プロパティ**、 **MaxConnections** の各設定など、いくつかのクォータ設定が提供され `WSMan:<ComputerName>\Service` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-287">The WSMan provider (WSMan:) provides several quota settings, such as the **MaxEnvelopeSizeKB** and **MaxProviderRequests** settings in the `WSMan:<ComputerName>` node and the **MaxConcurrentOperations**, **MaxConcurrentOperationsPerUser**, and **MaxConnections** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="b0c22-288">コマンドレットとユーザー設定変数の **MaximumReceivedDataSizePerCommand** パラメーターと **MaximumReceivedObjectSize** パラメーターを使用して、ローカルコンピューターを保護することができ `New-PSSessionOption` `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-288">You can protect the local computer by using the **MaximumReceivedDataSizePerCommand** and **MaximumReceivedObjectSize** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="b0c22-289">コマンドレットの **MaximumReceivedDataSizePerCommandMB** パラメーターと **MaximumReceivedObjectSizeMB** パラメーターを使用するなどして、セッション構成に制限を追加することで、リモートコンピューターを保護することができ `Register-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-289">You can protect the remote computer by adding restrictions to the session configurations, such as by using the **MaximumReceivedDataSizePerCommandMB** and **MaximumReceivedObjectSizeMB** parameters of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="b0c22-290">クォータがコマンドと競合している場合は、PowerShell によってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-290">When quotas conflict with a command, PowerShell generates an error.</span></span>

<span data-ttu-id="b0c22-291">このエラーを解決するには、クォータに準拠するようにリモートコマンドを変更します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-291">To resolve the error, change the remote command to comply with the quota.</span></span> <span data-ttu-id="b0c22-292">または、クォータのソースを特定し、クォータを増やしてコマンドを完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-292">Or, determine the source of the quota, and then increase the quota to allow the command to complete.</span></span>

<span data-ttu-id="b0c22-293">たとえば、次のコマンドは、リモートコンピューター上の Microsoft PowerShell セッション構成のオブジェクトサイズクォータを 10 MB (既定値) から 11 MB に増やします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-293">For example, the following command increases the object size quota in the Microsoft.PowerShell session configuration on the remote computer from 10 MB (the default value) to 11 MB.</span></span>

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

<span data-ttu-id="b0c22-294">コマンドレットの詳細については `New-PSSessionOption` 、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="b0c22-294">For more information about the `New-PSSessionOption` cmdlet, see `New-PSSessionOption`.</span></span>

<span data-ttu-id="b0c22-295">WS-Management クォータの詳細については、「 [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-295">For more information about the WS-Management quotas, see [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span></span>

### <a name="how-to-resolve-timeout-errors"></a><span data-ttu-id="b0c22-296">タイムアウトエラーを解決する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-296">How to resolve timeout errors</span></span>

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

<span data-ttu-id="b0c22-297">タイムアウトを使用して、ローカルコンピューターとリモートコンピューターが、偶発的でも悪意のあるリソースでも使用されないように保護することができます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-297">You can use timeouts to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span> <span data-ttu-id="b0c22-298">ローカルコンピューターとリモートコンピューターの両方でタイムアウトが設定されている場合、PowerShell では最短タイムアウト設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-298">When timeouts are set on both the local and remote computer, PowerShell uses the shortest timeout settings.</span></span>

<span data-ttu-id="b0c22-299">基本構成では、次のタイムアウトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-299">The following timeouts are available in the basic configuration.</span></span>

- <span data-ttu-id="b0c22-300">WSMan プロバイダー (WSMan:)では、ノードの **Maxtimeoutms** 設定 `WSMan:<ComputerName>` やノードの **EnumerationTimeoutms** と **MaxPacketRetrievalTimeSeconds** の設定など、クライアント側とサービス側のタイムアウト設定がいくつか提供されて `WSMan:<ComputerName>\Service` います。</span><span class="sxs-lookup"><span data-stu-id="b0c22-300">The WSMan provider (WSMan:) provides several client-side and service-side timeout settings, such as the **MaxTimeoutms** setting in the `WSMan:<ComputerName>` node and the **EnumerationTimeoutms** and **MaxPacketRetrievalTimeSeconds** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="b0c22-301">コマンドレットとユーザー設定変数の **canceltimeout**、 **IdleTimeout**、 **OpenTimeout**、および **operationtimeout** パラメーターを使用して、ローカルコンピューターを保護することができ `New-PSSessionOption` `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-301">You can protect the local computer by using the **CancelTimeout**, **IdleTimeout**, **OpenTimeout**, and **OperationTimeout** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="b0c22-302">セッションのセッション構成でタイムアウト値をプログラムによって設定することで、リモートコンピューターを保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-302">You can also protect the remote computer by setting timeout values programmatically in the session configuration for the session.</span></span>

<span data-ttu-id="b0c22-303">タイムアウト値によって操作の完了が許可されていない場合、PowerShell は操作を終了し、エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-303">When a timeout value does not permit a operation to complete, PowerShell terminates the operation and generates an error.</span></span>

<span data-ttu-id="b0c22-304">このエラーを解決するには、タイムアウト間隔内に完了するようにコマンドを変更するか、タイムアウト制限のソースを特定し、タイムアウト間隔を長くしてコマンドを完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b0c22-304">To resolve the error, change the command to complete within the timeout interval or determine the source of the timeout limit and increase the timeout interval to allow the command to complete.</span></span>

<span data-ttu-id="b0c22-305">たとえば、次のコマンドでは、コマンドレットを使用して、 `New-PSSessionOption` **operationtimeout** 値が4分 (ミリ秒) のセッションオプションオブジェクトを作成し、そのセッションオプションオブジェクトを使用してリモートセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-305">For example, the following commands use the `New-PSSessionOption` cmdlet to create a session option object with an **OperationTimeout** value of 4 minutes (in MS) and then use the session option object to create a remote session.</span></span>

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

<span data-ttu-id="b0c22-306">WS-Management タイムアウトの詳細については、WSMan プロバイダーのヘルプトピック (型) を参照してください `Get-Help WSMan` 。</span><span class="sxs-lookup"><span data-stu-id="b0c22-306">For more information about the WS-Management timeouts, see the Help topic for the WSMan provider (type `Get-Help WSMan`).</span></span>

<span data-ttu-id="b0c22-307">コマンドレットの詳細につい `New-PSSessionOption` ては、「 [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-307">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="troubleshooting-unresponsive-behavior"></a><span data-ttu-id="b0c22-308">応答しない動作のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0c22-308">Troubleshooting unresponsive behavior</span></span>

<span data-ttu-id="b0c22-309">このセクションでは、コマンドが完了しないようにするリモート処理の問題について説明し、PowerShell プロンプトを返します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-309">This section discusses remoting problems that prevent a command from completing and prevent or delay the return of the PowerShell prompt.</span></span>

### <a name="how-to-interrupt-a-command"></a><span data-ttu-id="b0c22-310">コマンドを中断する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-310">How to interrupt a command</span></span>

<span data-ttu-id="b0c22-311">ユーザーインターフェイスを備えたプログラム、入力を要求するコンソールアプリケーション、Win32 コンソール API を使用するコンソールアプリケーションなど、一部のネイティブ Windows プログラムは、PowerShell リモートホストでは正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="b0c22-311">Some native Windows programs, such as programs with a user interface, console applications that prompt for input, and console applications that use the Win32 console API, do not work correctly in the PowerShell remote host.</span></span>

<span data-ttu-id="b0c22-312">これらのプログラムを使用すると、出力がない、部分的な出力、または完了していないリモートコマンドなど、予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-312">When you use these programs, you might see unexpected behavior, such as no output, partial output, or a remote command that does not complete.</span></span>

<span data-ttu-id="b0c22-313">応答しないプログラムを終了するには、 <kbd>CTRL C キーを押し</kbd> + <kbd></kbd>ます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-313">To end an unresponsive program, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="b0c22-314">報告された可能性があるエラーを表示するには、 `$error` ローカルホストとリモートセッションを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-314">To view any errors that might have been reported, type `$error` in the local host and the remote session.</span></span>

## <a name="how-to-recover-from-an-operation-failure"></a><span data-ttu-id="b0c22-315">操作エラーから回復する方法</span><span class="sxs-lookup"><span data-stu-id="b0c22-315">How to recover from an operation failure</span></span>

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

<span data-ttu-id="b0c22-316">このエラーは、操作が完了する前に操作が終了したときに返されます。</span><span class="sxs-lookup"><span data-stu-id="b0c22-316">This error is returned when an operation is terminated before it completes.</span></span>
<span data-ttu-id="b0c22-317">通常、このエラーは、他の WinRM 操作の実行中に WinRM サービスが停止または再起動したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-317">Typically, it occurs when the WinRM service stops or restarts while other WinRM operations are in progress.</span></span>

<span data-ttu-id="b0c22-318">この問題を解決するには、WinRM サービスが実行されていることを確認してから、コマンドを再試行してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-318">To resolve this issue, verify that the WinRM service is running and try the command again.</span></span>

1. <span data-ttu-id="b0c22-319">[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-319">Start PowerShell with the **Run as administrator** option.</span></span>
1. <span data-ttu-id="b0c22-320">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-320">Run the following command:</span></span>

   `Start-Service WinRM`

1. <span data-ttu-id="b0c22-321">エラーを生成したコマンドを再実行します。</span><span class="sxs-lookup"><span data-stu-id="b0c22-321">Re-run the command that generated the error.</span></span>

## <a name="linux-and-macos-limitations"></a><span data-ttu-id="b0c22-322">Linux と macOS の制限事項</span><span class="sxs-lookup"><span data-stu-id="b0c22-322">Linux and macOS limitations</span></span>

### <a name="authentication"></a><span data-ttu-id="b0c22-323">認証</span><span class="sxs-lookup"><span data-stu-id="b0c22-323">Authentication</span></span>

<span data-ttu-id="b0c22-324">MacOS では基本認証のみが機能し、他の認証方式を使用しようとするとプロセスがクラッシュする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b0c22-324">Only basic authentication works on macOS and attempting to use other authentication schemes may result in the process crashing.</span></span>

<span data-ttu-id="b0c22-325">[Omi 認証](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows)の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c22-325">Please see the [OMI authentication](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0c22-326">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0c22-326">SEE ALSO</span></span>

[<span data-ttu-id="b0c22-327">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="b0c22-327">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[<span data-ttu-id="b0c22-328">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="b0c22-328">Export-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[<span data-ttu-id="b0c22-329">Import-Module</span><span class="sxs-lookup"><span data-stu-id="b0c22-329">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="b0c22-330">about_Remote</span><span class="sxs-lookup"><span data-stu-id="b0c22-330">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="b0c22-331">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="b0c22-331">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="b0c22-332">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="b0c22-332">about_Remote_Variables</span></span>](about_Remote_Variables.md)
