---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: f32b9300fddcf9086bc670912931001557b91cd8
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224760"
---
# <span data-ttu-id="28759-103">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="28759-103">New-WSManSessionOption</span></span>

## <span data-ttu-id="28759-104">概要</span><span class="sxs-lookup"><span data-stu-id="28759-104">SYNOPSIS</span></span>
<span data-ttu-id="28759-105">WS-Management コマンドレットの入力パラメーターとして使用するセッションオプションハッシュテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="28759-105">Creates session option hash table to use as input parameters for WS-Management cmdlets.</span></span>

## <span data-ttu-id="28759-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="28759-106">SYNTAX</span></span>

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## <span data-ttu-id="28759-107">Description</span><span class="sxs-lookup"><span data-stu-id="28759-107">DESCRIPTION</span></span>
<span data-ttu-id="28759-108">**新しい-WSManSessionOption** コマンドレットは、wsman セッションオプションハッシュテーブルを作成します。これは wsman コマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="28759-108">The **New-WSManSessionOption** cmdlet creates a WSMan Session option hash table which can be passed to WSMan cmdlets:</span></span>

- <span data-ttu-id="28759-109">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28759-109">Get-WSManInstance</span></span>
- <span data-ttu-id="28759-110">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28759-110">Set-WSManInstance</span></span>
- <span data-ttu-id="28759-111">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="28759-111">Invoke-WSManAction</span></span>
- <span data-ttu-id="28759-112">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="28759-112">Connect-WSMan</span></span>

## <span data-ttu-id="28759-113">例</span><span class="sxs-lookup"><span data-stu-id="28759-113">EXAMPLES</span></span>

### <span data-ttu-id="28759-114">例 1: 接続オプションを使用する接続を作成する</span><span class="sxs-lookup"><span data-stu-id="28759-114">Example 1: Create a connection that uses connection options</span></span>

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="28759-115">この例では、 **server01 によっ** て定義された接続オプションを使用して、リモートコンピューターへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="28759-115">This example creates a connection to the remote server01 computer by using the connection options that are defined by **New-WSManSessionOption** .</span></span>

<span data-ttu-id="28759-116">最初のコマンドは、 **New-WSManSessionOption** を使用して、一連の接続設定オプションを $a 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="28759-116">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="28759-117">この場合は、セッション オプションで接続のタイムアウトを 30 秒 (30,000 ミリ秒) に設定します。</span><span class="sxs-lookup"><span data-stu-id="28759-117">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="28759-118">2番目のコマンドは、 *Sessionoption* パラメーターを使用して、$a 変数に格納されている資格情報を **接続 WSMan** に渡します。</span><span class="sxs-lookup"><span data-stu-id="28759-118">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan** .</span></span>
<span data-ttu-id="28759-119">次に、指定されたセッションオプションを使用して、リモートの server01 コンピューターに **接続** します。</span><span class="sxs-lookup"><span data-stu-id="28759-119">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

<span data-ttu-id="28759-120">**接続-wsman** は、通常、リモートコンピューター (この場合は server01 コンピューター) に接続するために wsman プロバイダーのコンテキストで使用されます。</span><span class="sxs-lookup"><span data-stu-id="28759-120">**Connect-WSMan** is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="28759-121">ただし、WSMan プロバイダーに変更する前に、このコマンドレットを使用して、リモート コンピューターへの接続を確立することができます。</span><span class="sxs-lookup"><span data-stu-id="28759-121">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="28759-122">これらの接続は、 **ComputerName** の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="28759-122">Those connections appear in the **ComputerName** list.</span></span>

## <span data-ttu-id="28759-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="28759-123">PARAMETERS</span></span>

### <span data-ttu-id="28759-124">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="28759-124">-NoEncryption</span></span>
<span data-ttu-id="28759-125">接続が HTTP 経由のリモート操作に暗号化を使用しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="28759-125">Indicates that the connection does not use encryption for remote operations over HTTP.</span></span>

<span data-ttu-id="28759-126">既定では、暗号化されていないトラフィックは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="28759-126">By default, unencrypted traffic is not enabled.</span></span>
<span data-ttu-id="28759-127">ローカル構成で有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="28759-127">It must be enabled in the local configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-128">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="28759-128">-OperationTimeout</span></span>
<span data-ttu-id="28759-129">WS-Management 操作のタイムアウト (ミリ秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="28759-129">Specifies the time-out, in milliseconds, for the WS-Management operation.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-130">-System.management.automation.remoting.proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="28759-130">-ProxyAccessType</span></span>
<span data-ttu-id="28759-131">プロキシ サーバーを検索するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="28759-131">Specifies the mechanism by which the proxy server is located.</span></span>
<span data-ttu-id="28759-132">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="28759-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="28759-133">ProxyIEConfig.</span><span class="sxs-lookup"><span data-stu-id="28759-133">ProxyIEConfig.</span></span>
<span data-ttu-id="28759-134">現在のユーザーに対して Internet Explorer のプロキシ構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="28759-134">Use the Internet Explorer proxy configuration for the current user.</span></span>
- <span data-ttu-id="28759-135">ProxyWinHttpConfig.</span><span class="sxs-lookup"><span data-stu-id="28759-135">ProxyWinHttpConfig.</span></span>
<span data-ttu-id="28759-136">WSMan クライアントは、ProxyCfg.exe ユーティリティを使用して、WinHTTP 用に構成されたプロキシ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="28759-136">The WSMan client uses the proxy settings configured for WinHTTP, using the ProxyCfg.exe utility.</span></span>
- <span data-ttu-id="28759-137">ProxyAutoDetect.</span><span class="sxs-lookup"><span data-stu-id="28759-137">ProxyAutoDetect.</span></span>
<span data-ttu-id="28759-138">プロキシサーバーの自動検出を強制します。</span><span class="sxs-lookup"><span data-stu-id="28759-138">Force auto-detection of a proxy server.</span></span>
- <span data-ttu-id="28759-139">ProxyNoProxyServer.</span><span class="sxs-lookup"><span data-stu-id="28759-139">ProxyNoProxyServer.</span></span>
<span data-ttu-id="28759-140">プロキシサーバーは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="28759-140">Do not use a proxy server.</span></span>
<span data-ttu-id="28759-141">すべてのホスト名をローカルで解決してください。</span><span class="sxs-lookup"><span data-stu-id="28759-141">Resolve all host names locally.</span></span>

<span data-ttu-id="28759-142">既定値は ProxyIEConfig です。</span><span class="sxs-lookup"><span data-stu-id="28759-142">The default value is ProxyIEConfig.</span></span>

```yaml
Type: Microsoft.WSMan.Management.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: ProxyIEConfig, ProxyWinHttpConfig, ProxyAutoDetect, ProxyNoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-143">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="28759-143">-ProxyAuthentication</span></span>
<span data-ttu-id="28759-144">プロキシで使用する認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="28759-144">Specifies the authentication method to use at the proxy.</span></span>
<span data-ttu-id="28759-145">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="28759-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="28759-146">基本。</span><span class="sxs-lookup"><span data-stu-id="28759-146">Basic.</span></span>
<span data-ttu-id="28759-147">Basic は、ユーザー名およびパスワードがクリア テキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="28759-147">Basic is a scheme in which the user name and password are sent in clear-text to the server or proxy.</span></span>
- <span data-ttu-id="28759-148">ダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="28759-148">Digest.</span></span>
<span data-ttu-id="28759-149">Digest は、サーバーで指定されたデータ文字列をチャレンジで使用するチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="28759-149">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="28759-150">Negotiate</span><span class="sxs-lookup"><span data-stu-id="28759-150">Negotiate.</span></span>
<span data-ttu-id="28759-151">Negotiate は、認証で使用するスキームを特定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="28759-151">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine which scheme to use for authentication.</span></span>
<span data-ttu-id="28759-152">たとえば、Kerberos プロトコルや NTLM です。</span><span class="sxs-lookup"><span data-stu-id="28759-152">Examples are the Kerberos protocol and NTLM.</span></span>

<span data-ttu-id="28759-153">既定値は Negotiate です。</span><span class="sxs-lookup"><span data-stu-id="28759-153">The default value is Negotiate.</span></span>

```yaml
Type: Microsoft.WSMan.Management.ProxyAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic, Digest

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-154">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="28759-154">-ProxyCredential</span></span>
<span data-ttu-id="28759-155">中間 Web プロキシ経由でアクセスするためのアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="28759-155">Specifies a user account that has permission to gain access through an intermediate Web proxy.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-156">-SPNPort</span><span class="sxs-lookup"><span data-stu-id="28759-156">-SPNPort</span></span>
<span data-ttu-id="28759-157">リモートサーバーの接続サービスプリンシパル名 (SPN) に追加するポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="28759-157">Specifies a port number to append to the connection Service Principal Name (SPN) of the remote server.</span></span>
<span data-ttu-id="28759-158">SPN は、認証メカニズムが Kerberos またはネゴシエートの場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="28759-158">An SPN is used when the authentication mechanism is Kerberos or Negotiate.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-159">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="28759-159">-SkipCACheck</span></span>
<span data-ttu-id="28759-160">HTTPS 経由で接続する場合、クライアントは、サーバー証明書が信頼された証明機関 (CA) によって署名されているかどうかを検証しません。</span><span class="sxs-lookup"><span data-stu-id="28759-160">Specifies that, when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>
<span data-ttu-id="28759-161">このオプションは、リモートコンピューターが別の方法で信頼されている場合にのみ使用します。たとえば、リモートコンピューターが物理的に安全で分離されているネットワークの一部である場合や、リモートコンピューターが WS-Management 構成で信頼されたホストとして一覧表示されている場合などです。</span><span class="sxs-lookup"><span data-stu-id="28759-161">Use this option only when the remote computer is trusted by another method, for example, if the remote computer is part of a network that is physically secure and isolated or the remote computer is listed as a trusted host in the WS-Management configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-162">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="28759-162">-SkipCNCheck</span></span>
<span data-ttu-id="28759-163">サーバーの証明書の共通名 (CN) がサーバーのホスト名と一致する必要がないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="28759-163">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="28759-164">これは、HTTPS を使用したリモート操作でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="28759-164">This is used only in remote operations using HTTPS.</span></span>
<span data-ttu-id="28759-165">このオプションは、信頼されているコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="28759-165">This option should only be used for trusted computers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-166">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="28759-166">-SkipRevocationCheck</span></span>
<span data-ttu-id="28759-167">接続がサーバー証明書の失効状態を検証しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="28759-167">Indicates that the connection does not validate the revocation status on the server certificate.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-168">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="28759-168">-UseUTF16</span></span>
<span data-ttu-id="28759-169">接続が、要求を UTF8 形式ではなく UTF16 形式でエンコードすることを示します。</span><span class="sxs-lookup"><span data-stu-id="28759-169">Indicates that the connection encodes the request in UTF16 format instead of UTF8 format.</span></span>
<span data-ttu-id="28759-170">既定値は UTF8 エンコードです。</span><span class="sxs-lookup"><span data-stu-id="28759-170">The default is UTF8 encoding.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28759-171">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="28759-171">CommonParameters</span></span>
<span data-ttu-id="28759-172">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="28759-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="28759-173">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28759-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="28759-174">入力</span><span class="sxs-lookup"><span data-stu-id="28759-174">INPUTS</span></span>

## <span data-ttu-id="28759-175">出力</span><span class="sxs-lookup"><span data-stu-id="28759-175">OUTPUTS</span></span>

### <span data-ttu-id="28759-176">SessionOption</span><span class="sxs-lookup"><span data-stu-id="28759-176">SessionOption</span></span>

## <span data-ttu-id="28759-177">注</span><span class="sxs-lookup"><span data-stu-id="28759-177">NOTES</span></span>

## <span data-ttu-id="28759-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="28759-178">RELATED LINKS</span></span>

[<span data-ttu-id="28759-179">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="28759-179">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="28759-180">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="28759-180">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="28759-181">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="28759-181">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="28759-182">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="28759-182">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="28759-183">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="28759-183">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="28759-184">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28759-184">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="28759-185">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="28759-185">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="28759-186">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28759-186">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="28759-187">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28759-187">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="28759-188">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="28759-188">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="28759-189">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="28759-189">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="28759-190">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="28759-190">Test-WSMan</span></span>](Test-WSMan.md)
