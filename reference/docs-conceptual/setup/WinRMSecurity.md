---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: WinRMSecurity
ms.openlocfilehash: 65cf12466c9dc8fc8b77d79b0d63a6ae61e64d60
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="powershell-remoting-security-considerations"></a><span data-ttu-id="cda39-103">PowerShell リモート処理のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="cda39-103">PowerShell Remoting Security Considerations</span></span>

<span data-ttu-id="cda39-104">PowerShell リモート処理は、Windows システムの管理に推奨されている方法です。</span><span class="sxs-lookup"><span data-stu-id="cda39-104">PowerShell Remoting is the recommended way to manage Windows systems.</span></span> <span data-ttu-id="cda39-105">Windows Server 2012 R2 では、PowerShell リモート処理が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cda39-105">PowerShell Remoting is enabled by default in Windows Server 2012 R2.</span></span> <span data-ttu-id="cda39-106">このドキュメントでは、PowerShell リモート処理を使用する場合のセキュリティ上の問題、推奨事項、およびベスト プラクティスを取り上げています。</span><span class="sxs-lookup"><span data-stu-id="cda39-106">This document covers security concerns, recommendations, and best practices when using PowerShell Remoting.</span></span>

## <a name="what-is-powershell-remoting"></a><span data-ttu-id="cda39-107">PowerShell リモート処理とは</span><span class="sxs-lookup"><span data-stu-id="cda39-107">What is PowerShell Remoting?</span></span>

<span data-ttu-id="cda39-108">PowerShell リモート処理は、[Windows リモート管理 (WinRM)](https://msdn.microsoft.com/en-us/library/windows/desktop/aa384426.aspx) を使用しています。これは、ユーザーがリモート コンピューター上で PowerShell コマンドを実行できるように、Microsoft によって [Web Services for Management (WS-Management)](http://www.dmtf.org/sites/default/files/standards/documents/DSP0226_1.2.0.pdf) プロトコルが実装されたものです。</span><span class="sxs-lookup"><span data-stu-id="cda39-108">PowerShell Remoting uses [Windows Remote Management (WinRM)](https://msdn.microsoft.com/en-us/library/windows/desktop/aa384426.aspx), which is the Microsoft implementation of the [Web Services for Management (WS-Management)](http://www.dmtf.org/sites/default/files/standards/documents/DSP0226_1.2.0.pdf) protocol, to allow users to run PowerShell commands on remote computers.</span></span> <span data-ttu-id="cda39-109">PowerShell リモート処理の使用方法の詳細については、「[リモート コマンドの実行](https://technet.microsoft.com/en-us/library/dd819505.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cda39-109">You can find more information about using PowerShell Remoting at [Running Remote Commands](https://technet.microsoft.com/en-us/library/dd819505.aspx).</span></span>

<span data-ttu-id="cda39-110">PowerShell リモート処理は、コマンドレットの **ComputerName** パラメーターを使用してリモート コンピューターでコマンドを実行することとは異なります。この場合は、基盤となるプロトコルとしてリモート プロシージャ コール (RPC) が使用されています。</span><span class="sxs-lookup"><span data-stu-id="cda39-110">PowerShell Remoting is not the same as using the **ComputerName** parameter of a cmdlet to run it on a remote computer, which uses Remote Procedure Call (RPC) as its underlying protocol.</span></span>

## <a name="powershell-remoting-default-settings"></a><span data-ttu-id="cda39-111">PowerShell リモート処理の既定の設定</span><span class="sxs-lookup"><span data-stu-id="cda39-111">PowerShell Remoting default settings</span></span>

<span data-ttu-id="cda39-112">PowerShell リモート処理 (および WinRM) は、次のポートをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="cda39-112">PowerShell Remoting (and WinRM) listen on the following ports:</span></span>

- <span data-ttu-id="cda39-113">HTTP: 5985</span><span class="sxs-lookup"><span data-stu-id="cda39-113">HTTP: 5985</span></span>
- <span data-ttu-id="cda39-114">HTTPS: 5986</span><span class="sxs-lookup"><span data-stu-id="cda39-114">HTTPS: 5986</span></span>

<span data-ttu-id="cda39-115">既定では、PowerShell リモート処理で許可されている接続は、Administrators グループのメンバーからのもののみです。</span><span class="sxs-lookup"><span data-stu-id="cda39-115">By default, PowerShell Remoting only allows connections from members of the Administrators group.</span></span> <span data-ttu-id="cda39-116">セッションはユーザーのコンテキストで開始されるため、PowerShell リモート処理を介して接続されている間は、個々のユーザーとグループに適用されているオペレーティング システムのアクセス制御がすべて、そのセッションに引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="cda39-116">Sessions are launched under the user's context, so all operating system access controls applied to individual users and groups continue to apply to them while connected over PowerShell Remoting.</span></span>

<span data-ttu-id="cda39-117">プライベート ネットワークの場合、PowerShell リモート処理の既定の Windows ファイアウォール規則はすべての接続を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="cda39-117">On private networks, the default Windows Firewall rule for PowerShell Remoting accepts all connections.</span></span> <span data-ttu-id="cda39-118">パブリック ネットワークの場合、既定の Windows ファイアウォール規則で許可されるのは、同じサブネット内からの PowerShell リモート処理接続のみです。</span><span class="sxs-lookup"><span data-stu-id="cda39-118">On public networks, the default Windows Firewall rule allows PowerShell Remoting connections only from within the same subnet.</span></span> <span data-ttu-id="cda39-119">パブリック ネットワーク上のすべての接続に対して PowerShell リモート処理を可能にするには、その規則を明示的に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cda39-119">You have to explicitly change that rule to open PowerShell Remoting to all connections on a public network.</span></span>

><span data-ttu-id="cda39-120">**警告:** パブリック ネットワークのファイアウォール規則は、悪意のある外部接続からコンピューターを保護することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="cda39-120">**Warning:** The firewall rule for public networks is meant to protect the computer from potentially malicious external connection attempts.</span></span> <span data-ttu-id="cda39-121">この規則を削除する際は注意してください。</span><span class="sxs-lookup"><span data-stu-id="cda39-121">Use caution when removing this rule.</span></span>

## <a name="process-isolation"></a><span data-ttu-id="cda39-122">プロセスの分離</span><span class="sxs-lookup"><span data-stu-id="cda39-122">Process isolation</span></span>

<span data-ttu-id="cda39-123">PowerShell リモート処理では、コンピューター間の通信に [Windows リモート管理 (WinRM)](https://msdn.microsoft.com/en-us/library/windows/desktop/aa384426) を使用します。</span><span class="sxs-lookup"><span data-stu-id="cda39-123">PowerShell Remoting uses [Windows Remote Management (WinRM)](https://msdn.microsoft.com/en-us/library/windows/desktop/aa384426) for communication between computers.</span></span> <span data-ttu-id="cda39-124">WinRM は Network Service アカウントでサービスとして実行されており、ユーザー アカウントとして実行される分離プロセスを生成して、PowerShell インスタンスをホストします。</span><span class="sxs-lookup"><span data-stu-id="cda39-124">WinRM runs as a service under the Network Service account, and spawns isolated processes running as user accounts to host PowerShell instances.</span></span> <span data-ttu-id="cda39-125">1 ユーザーとして実行されている PowerShell のインスタンスは、別のユーザーとして PowerShell のインスタンスを実行しているプロセスにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cda39-125">An instance of PowerShell running as one user has no access to a process running an instance of PowerShell as another user.</span></span>

## <a name="event-logs-generated-by-powershell-remoting"></a><span data-ttu-id="cda39-126">PowerShell リモート処理によって生成されたイベント ログ</span><span class="sxs-lookup"><span data-stu-id="cda39-126">Event logs generated by PowerShell Remoting</span></span>

<span data-ttu-id="cda39-127">FireEye は、PowerShell リモート処理セッションによって生成されたイベント ログやその他のセキュリティ証拠をまとめたものを提供しています。これは、概要をまとめられています。これについては、</span><span class="sxs-lookup"><span data-stu-id="cda39-127">FireEye has provided a good summary of the event logs and other security evidence generated by PowerShell Remoting sessions, available at</span></span>  
<span data-ttu-id="cda39-128">[Investigating PowerShell Attacks (PowerShell 攻撃の調査)」を参照してください](https://www.fireeye.com/content/dam/fireeye-www/global/en/solutions/pdfs/wp-lazanciyan-investigating-powershell-attacks.pdf)。</span><span class="sxs-lookup"><span data-stu-id="cda39-128">[Investigating PowerShell Attacks](https://www.fireeye.com/content/dam/fireeye-www/global/en/solutions/pdfs/wp-lazanciyan-investigating-powershell-attacks.pdf).</span></span>

## <a name="encryption-and-transport-protocols"></a><span data-ttu-id="cda39-129">暗号化とトランスポート プロトコル</span><span class="sxs-lookup"><span data-stu-id="cda39-129">Encryption and transport protocols</span></span>

<span data-ttu-id="cda39-130">PowerShell リモート処理の接続のセキュリティについては、初期認証と進行中の通信という 2 つの観点から考慮することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cda39-130">It is helpful to consider the security of a PowerShell Remoting connection from two perspectives: initial authentication, and ongoing communication.</span></span> 

<span data-ttu-id="cda39-131">使用されているトランスポート プロトコル (HTTP または HTTPS) に関係なく、PowerShell リモート処理では、常にすべての通信が、初期認証後に、セッションごとの AES 256 対称キーを使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="cda39-131">Regardless of the transport protocol used (HTTP or HTTPS), PowerShell Remoting always encrypts all communication after initial authentication with a per-session AES-256 symmetric key.</span></span>
    
### <a name="initial-authentication"></a><span data-ttu-id="cda39-132">初期認証</span><span class="sxs-lookup"><span data-stu-id="cda39-132">Initial authentication</span></span>

<span data-ttu-id="cda39-133">認証では、サーバーに対するクライアントの ID と、理想的にはクライアントに対するサーバーを確認します。</span><span class="sxs-lookup"><span data-stu-id="cda39-133">Authentication confirms the identity of the client to the server - and ideally - the server to the client.</span></span>
    
<span data-ttu-id="cda39-134">クライアントがコンピューター名 (server01 や server01.contoso.com など) を使用してドメイン サーバーに接続する場合、既定の認証プロトコルは [Kerberos](https://msdn.microsoft.com/en-us/library/windows/desktop/aa378747.aspx) です。</span><span class="sxs-lookup"><span data-stu-id="cda39-134">When a client connects to a domain server using its computer name (i.e.: server01, or server01.contoso.com), the default authentication protocol is [Kerberos](https://msdn.microsoft.com/en-us/library/windows/desktop/aa378747.aspx).</span></span>
<span data-ttu-id="cda39-135">Kerberos では、再利用可能な資格情報を送信しなくても、ユーザー ID とサーバー ID の両方が保証されます。</span><span class="sxs-lookup"><span data-stu-id="cda39-135">Kerberos guarantees both the user identity and server identity without sending any sort of reusable credential.</span></span>

<span data-ttu-id="cda39-136">クライアントが IP アドレスを使用してドメイン サーバーに接続する場合、またはワークグループ サーバーに接続する場合は、Kerberos 認証を使用できません。</span><span class="sxs-lookup"><span data-stu-id="cda39-136">When a client connects to a domain server using its IP address, or connects to a workgroup server, Kerberos authentication is not possible.</span></span> <span data-ttu-id="cda39-137">その場合は、PowerShell リモート処理は [NTLM 認証プロトコル](https://msdn.microsoft.com/en-us/library/windows/desktop/aa378749.aspx)を利用します。</span><span class="sxs-lookup"><span data-stu-id="cda39-137">In that case, PowerShell Remoting relies on the [NTLM authentication protocol](https://msdn.microsoft.com/en-us/library/windows/desktop/aa378749.aspx).</span></span> <span data-ttu-id="cda39-138">NTLM 認証プロトコルでは、委任可能な資格情報を送信しなくてもユーザー ID が保証されます。</span><span class="sxs-lookup"><span data-stu-id="cda39-138">The NTLM authentication protocol guarantees the user identity without sending any sort of delegable credential.</span></span> <span data-ttu-id="cda39-139">NTLM プロトコルは、ユーザー ID を証明するために、クライアントとサーバーの両方でユーザーのパスワードからセッション キーを計算することを要求します。パスワード自体は交換しません。</span><span class="sxs-lookup"><span data-stu-id="cda39-139">To prove user identity, the NTLM protocol requires that both the client and server compute a session key from the user's password without ever exchanging the password itself.</span></span> <span data-ttu-id="cda39-140">サーバーは、通常ユーザーのパスワードを知らないため、ドメイン コントローラーと通信します。ドメイン コントローラーがユーザーのパスワードを知っていて、サーバー用にセッション キーを計算します。</span><span class="sxs-lookup"><span data-stu-id="cda39-140">The server typically does not know the user's password, so it communicates with the domain controller, which does know the user's password and calculates the session key for the server.</span></span> 
      
<span data-ttu-id="cda39-141">一方、NTLM プロトコルでは、サーバー ID が保証されません。</span><span class="sxs-lookup"><span data-stu-id="cda39-141">The NTLM protocol does not, however, guarantee server identity.</span></span> <span data-ttu-id="cda39-142">ドメインに参加しているコンピューターのコンピューター アカウントにアクセスできる攻撃者は、認証に NTLM を使用するプロトコルと同様にドメイン コントローラーを呼び出して NTLM セッション キーを計算することで、サーバーになりすます場合があります。</span><span class="sxs-lookup"><span data-stu-id="cda39-142">As with all protocols that use NTLM for authentication, an attacker with access to a domain-joined computer's machine account could invoke the domain controller to compute an NTLM session-key and thereby impersonate the server.</span></span>

<span data-ttu-id="cda39-143">NTLM ベースの認証は既定では無効になっていますが、ターゲット サーバーで SSL を構成するか、クライアントで WinRM TrustedHosts 設定を構成することで許可できます。</span><span class="sxs-lookup"><span data-stu-id="cda39-143">NTLM-based authentication is disabled by default, but may be permitted by either configuring SSL on the target server, or by configuring the WinRM TrustedHosts setting on the client.</span></span>
    
#### <a name="using-ssl-certificates-to-validate-server-identity-during-ntlm-based-connections"></a><span data-ttu-id="cda39-144">NTLM ベースの接続時に SSL 証明書を使用してサーバー ID を検証する</span><span class="sxs-lookup"><span data-stu-id="cda39-144">Using SSL certificates to validate server identity during NTLM-based connections</span></span>

<span data-ttu-id="cda39-145">NTLM 認証プロトコルではターゲット サーバーの ID を保証できないため (パスワードを認識しているだけのため)、PowerShell リモート処理に SSL を使用するようターゲット サーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="cda39-145">Since the NTLM authentication protocol cannot ensure the identity of the target server (only that it already knows your password), you can configure target servers to use SSL for PowerShell Remoting.</span></span> <span data-ttu-id="cda39-146">SSL 証明書をターゲット サーバーに割り当てると (クライアントも信頼している証明機関によって発行されている場合)、ユーザー ID とサーバー ID の両方が保証される NTLM ベースの認証が可能になります。</span><span class="sxs-lookup"><span data-stu-id="cda39-146">Assigning a SSL certificate to the target server (if issued by a Certificate Authority that the client also trusts) enables NTLM-based authentication that guarantees both the user identity and server identity.</span></span>
    
#### <a name="ignoring-ntlm-based-server-identity-errors"></a><span data-ttu-id="cda39-147">NTLM ベースのサーバー ID を無視する</span><span class="sxs-lookup"><span data-stu-id="cda39-147">Ignoring NTLM-based server identity errors</span></span>
      
<span data-ttu-id="cda39-148">SSL 証明書を NTLM 接続用のサーバーに展開できない場合は、そのサーバーを WinRM の **TrustedHosts** 一覧に追加することで ID エラーの発生を抑制できます。</span><span class="sxs-lookup"><span data-stu-id="cda39-148">If deploying a SSL certificate to a server for NTLM connections is infeasible, you may suppress the resulting identity errors by adding the server to the WinRM **TrustedHosts** list.</span></span> <span data-ttu-id="cda39-149">ホスト自体の信頼性を示すために、サーバー名を TrustedHosts の一覧に追加することは考えないでください。NTLM 認証プロトコルでは、実際に接続しているホストが、必ずしも意図して接続しているホストであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="cda39-149">Please note that adding a server name to the TrustedHosts list should not be considered as any form of statement of the trustworthiness of the hosts themselves - as the NTLM authentication protocol cannot guarantee that you are in fact connecting to the host you are intending to connect to.</span></span>
<span data-ttu-id="cda39-150">代わりに、TrustedHosts の設定を、サーバーの ID を確認できないことが原因で生成されたエラーを抑制するホストの一覧と考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="cda39-150">Instead, you should consider the TrustedHosts setting to be the list of hosts for which you wish to suppress the error generated by being unable to verify the server's identity.</span></span>
    
    
### <a name="ongoing-communication"></a><span data-ttu-id="cda39-151">進行中の通信</span><span class="sxs-lookup"><span data-stu-id="cda39-151">Ongoing Communication</span></span>

<span data-ttu-id="cda39-152">初期認証が完了すると、[PowerShell リモート処理プロトコル](https://msdn.microsoft.com/en-us/library/dd357801.aspx)によって、進行中の通信はすべて、セッションごとの AES 256 対称キーを使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="cda39-152">Once initial authentication is complete, the [PowerShell Remoting Protocol](https://msdn.microsoft.com/en-us/library/dd357801.aspx) encrypts all ongoing communication with a per-session AES-256 symmetric key.</span></span>  


## <a name="making-the-second-hop"></a><span data-ttu-id="cda39-153">次ホップの実行</span><span class="sxs-lookup"><span data-stu-id="cda39-153">Making the second hop</span></span>

<span data-ttu-id="cda39-154">PowerShell リモート処理では、既定で、認証に Kerberos (使用可能な場合) または NTLM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cda39-154">By default, PowerShell Remoting uses Kerberos (if available) or NTLM for authentication.</span></span> <span data-ttu-id="cda39-155">このどちらのプロトコルも、資格情報を送信することなく、リモート コンピューターに対して認証を行います。</span><span class="sxs-lookup"><span data-stu-id="cda39-155">Both of these protocols authenticate to the remote machine without sending credentials to it.</span></span>
<span data-ttu-id="cda39-156">これは認証方法としては最も安全ですが、リモート コンピューターにユーザーの資格情報がないため、このリモート コンピューターは、ユーザーに代わって他のコンピューターおよびサービスにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cda39-156">This is the most secure way to authenticate, but because the remote machine does not have the user's credentials, it cannot access other computers and services on the user's behalf.</span></span> <span data-ttu-id="cda39-157">これは "次ホップの問題" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cda39-157">This is known as the "second hop problem".</span></span>

<span data-ttu-id="cda39-158">この問題を回避する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="cda39-158">There are several ways to avoid this problem.</span></span> <span data-ttu-id="cda39-159">これらの方法およびその長所と短所については、「[PowerShell リモート処理での次ホップの実行](PS-remoting-second-hop.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cda39-159">For descriptions of these methods, and the pros and cons of each, see [Making the second hop in PowerShell Remoting](PS-remoting-second-hop.md).</span></span>










