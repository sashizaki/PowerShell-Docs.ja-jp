---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: 3f1b72c2cbdf5d7b9ef4b77bcca7277ccbe8b021
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218728"
---
# <span data-ttu-id="1e8eb-103">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1e8eb-103">Enable-WSManCredSSP</span></span>

## <span data-ttu-id="1e8eb-104">概要</span><span class="sxs-lookup"><span data-stu-id="1e8eb-104">SYNOPSIS</span></span>
<span data-ttu-id="1e8eb-105">コンピューターで Credential Security Support Provider (CredSSP) 認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-105">Enables Credential Security Support Provider (CredSSP) authentication on a computer.</span></span>

## <span data-ttu-id="1e8eb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1e8eb-106">SYNTAX</span></span>

### <span data-ttu-id="1e8eb-107">All</span><span class="sxs-lookup"><span data-stu-id="1e8eb-107">All</span></span>

```
Enable-WSManCredSSP [[-DelegateComputer] <String[]>] [-Force] [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="1e8eb-108">Description</span><span class="sxs-lookup"><span data-stu-id="1e8eb-108">DESCRIPTION</span></span>

<span data-ttu-id="1e8eb-109">`Enable-WSManCredSSP`コマンドレットでは、クライアントまたはサーバーコンピューターで CredSSP 認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-109">The `Enable-WSManCredSSP` cmdlet enables CredSSP authentication on a client or on a server computer.</span></span>
<span data-ttu-id="1e8eb-110">CredSSP 認証を使用すると、ユーザーの資格情報が認証対象のリモートコンピューターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-110">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span> <span data-ttu-id="1e8eb-111">この種類の認証は、別のリモートセッションからリモートセッションを作成するコマンド用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-111">This type of authentication is designed for commands that create a remote session from another remote session.</span></span> <span data-ttu-id="1e8eb-112">たとえば、リモートコンピューターでバックグラウンドジョブを実行する場合は、この種類の認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-112">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="1e8eb-113">`Enable-WSManCredSSP`**クライアント** または **サーバー** で CredSSP を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-113">`Enable-WSManCredSSP` can enable CredSSP on a **Client** or a **Server**.</span></span> <span data-ttu-id="1e8eb-114">クライアントで CredSSP を有効にするには、 **Role** パラメーターに **client** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-114">To enable CredSSP on a client, specify **Client** in the **Role** parameter.</span></span> <span data-ttu-id="1e8eb-115">サーバー認証が行われると、クライアントは明示的な資格情報をサーバーに委任します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-115">Clients delegate explicit credentials to a server when server authentication is achieved.</span></span> <span data-ttu-id="1e8eb-116">サーバーで CredSSP を有効にするには、 **Role** パラメーターに **server** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-116">To enable CredSSP on a server, specify **Server** in the **Role** parameter.</span></span> <span data-ttu-id="1e8eb-117">サーバーは、クライアントの代理として機能します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-117">A server acts as a delegate for clients.</span></span> <span data-ttu-id="1e8eb-118">詳細については、「パラメーター」セクションの「 **Role** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-118">For more details, see **Role** in the Parameters section.</span></span>

> [!CAUTION]
> <span data-ttu-id="1e8eb-119">CredSSP 認証では、ユーザーの資格情報がローカルコンピューターからリモートコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-119">CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="1e8eb-120">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-120">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="1e8eb-121">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-121">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="1e8eb-122">例</span><span class="sxs-lookup"><span data-stu-id="1e8eb-122">EXAMPLES</span></span>

### <span data-ttu-id="1e8eb-123">例 1: クライアントの資格情報を委任する</span><span class="sxs-lookup"><span data-stu-id="1e8eb-123">Example 1: Delegate client credentials</span></span>

<span data-ttu-id="1e8eb-124">この例では、完全修飾ドメイン名を使用して、クライアントの資格情報をコンピューターに委任できます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-124">This example allows the client credentials to be delegated to a computer by using the fully qualified domain name.</span></span>

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "Server02.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### <span data-ttu-id="1e8eb-125">例 2: ドメイン内のすべてのコンピューターにクライアントの資格情報を委任する</span><span class="sxs-lookup"><span data-stu-id="1e8eb-125">Example 2: Delegate client credentials to all computers in a domain</span></span>

<span data-ttu-id="1e8eb-126">この例では、 **fabrikam.com** ドメイン内のすべてのコンピューターにクライアントの資格情報を委任できます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-126">This example allows the client credentials to be delegated to all the computers in the **fabrikam.com** domain.</span></span> <span data-ttu-id="1e8eb-127">アスタリスク ( `*` ) ワイルドカードは、すべてのコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-127">The asterisk (`*`) wildcard specifies all computers.</span></span>

> [!NOTE]
> <span data-ttu-id="1e8eb-128">**DelegateComputer** パラメーターでワイルドカードを使用すると、必要以上に多くのコンピューターで CredSSP を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-128">Using wildcards with the **DelegateComputer** parameter can enable CredSSP on more computers than necessary.</span></span>

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "*.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### <span data-ttu-id="1e8eb-129">例 3: 複数のコンピューターにクライアントの資格情報を委任する</span><span class="sxs-lookup"><span data-stu-id="1e8eb-129">Example 3: Delegate client credentials to multiple computers</span></span>

<span data-ttu-id="1e8eb-130">この例では、クライアントの資格情報を複数のコンピューターに委任できます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-130">This example allows the client credentials to be delegated to multiple computers.</span></span>

```powershell
$servers = "server02.fabrikam.com", "server03.fabrikam.com", "server04.fabrikam.com"
Enable-WSManCredSSP -Role "Client" -DelegateComputer $servers
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

<span data-ttu-id="1e8eb-131">変数には、 `$servers` サーバー名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-131">The `$servers` variable contains a list of server names.</span></span> <span data-ttu-id="1e8eb-132">`Enable-WSManCredSSP`**role** パラメーターを使用して、 **クライアント** ロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-132">`Enable-WSManCredSSP` uses the **Role** parameter to specify the **Client** role.</span></span> <span data-ttu-id="1e8eb-133">**DelegateComputer** は、変数からコンピューター名を取得し `$servers` ます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-133">The **DelegateComputer** gets the computer names from the `$servers` variable.</span></span>

### <span data-ttu-id="1e8eb-134">例 4: コンピューターが代理として動作できるようにする</span><span class="sxs-lookup"><span data-stu-id="1e8eb-134">Example 4: Allow a computer to act as a delegate</span></span>

<span data-ttu-id="1e8eb-135">この例では、コンピューターを別ののデリゲートとして動作させることができます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-135">This example allows a computer to act as a delegate for another.</span></span> <span data-ttu-id="1e8eb-136">この `Enable-WSManCredSSP` コマンドレットは、前の例で示したように、クライアントで CredSSP 認証のみを有効にし、代理として動作できるリモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-136">The `Enable-WSManCredSSP` cmdlet, shown in the earlier examples, only enables CredSSP authentication on the client, and specifies the remote computers that can act on its behalf.</span></span> <span data-ttu-id="1e8eb-137">リモートコンピューターがクライアントの代理として機能するためには、WSMan の **サービス** ノードの CredSSP 項目を true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-137">In order for the remote computer to act as a delegate for the client, the CredSSP item in the **Service** node of WSMan must be set to true.</span></span> <span data-ttu-id="1e8eb-138">この例では、WSMan の **Service** ノードの CredSSP 項目を true に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-138">This example sets the CredSSP item in the **Service** node of WSMan to true.</span></span>

```powershell
Enable-WSManCredSSP -Role "Server"
```

### <span data-ttu-id="1e8eb-139">例 5: Set-Item を使用してコンピューターが代理人として機能することを許可する</span><span class="sxs-lookup"><span data-stu-id="1e8eb-139">Example 5: Allow a computer to act as a delegate by using Set-Item</span></span>

<span data-ttu-id="1e8eb-140">この例では、コンピューターを別のコンピューターの代理として動作させることができます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-140">This example allows a computer to act as a delegate for another computer.</span></span> <span data-ttu-id="1e8eb-141">`Enable-WSManCredSSP`前の例で示したコマンドは、クライアントコンピューターでのみ CredSSP 認証を有効にし、クライアントコンピューターの代理として動作できるリモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-141">The `Enable-WSManCredSSP` commands, shown in the earlier examples, enable CredSSP authentication only on the client computer, and they specify the remote computers that can act on behalf of the client computer.</span></span> <span data-ttu-id="1e8eb-142">リモート コンピューターがクライアント コンピューターの代理として動作するためには、WSMan プロバイダーの Service ディレクトリの CredSSP 項目を true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-142">For the remote computer to act as a delegate for the client computer, the CredSSP item in the Service directory of the WSMan provider must be set to true.</span></span>

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

<span data-ttu-id="1e8eb-143">`Connect-WSMan` リモートコンピューター server02 への接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-143">`Connect-WSMan` creates a connection to the remote computer, server02.</span></span> <span data-ttu-id="1e8eb-144">`Set-Item`**Path** パラメーターを使用して、 **WSMan** プロバイダーの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-144">`Set-Item` uses the **Path** parameter to specify the **WSMan** provider's location.</span></span> <span data-ttu-id="1e8eb-145">**Value** パラメーターは、 **サービス** 設定を true に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-145">The **Value** parameter sets the **Service** setting to true.</span></span>

## <span data-ttu-id="1e8eb-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1e8eb-146">PARAMETERS</span></span>

### <span data-ttu-id="1e8eb-147">-DelegateComputer</span><span class="sxs-lookup"><span data-stu-id="1e8eb-147">-DelegateComputer</span></span>

<span data-ttu-id="1e8eb-148">クライアント資格情報を委任するサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-148">Specifies servers to which client credentials are delegated.</span></span> <span data-ttu-id="1e8eb-149">完全修飾ドメイン名を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-149">The best practice is to use fully qualified domain names.</span></span>

<span data-ttu-id="1e8eb-150">ワイルドカードは受け入れられますが、必要以上に多くのコンピューターで CredSSP を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-150">Wildcards are accepted, but can enable CredSSP on more computers than necessary.</span></span>

<span data-ttu-id="1e8eb-151">**Role** パラメーターが **Client** の場合は、このパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-151">If the **Role** parameter is **Client** , you must specify this parameter.</span></span> <span data-ttu-id="1e8eb-152">**Role** が **Server** の場合は、このパラメーターを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-152">If **Role** is **Server** , don't specify this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1e8eb-153">-Force</span><span class="sxs-lookup"><span data-stu-id="1e8eb-153">-Force</span></span>

<span data-ttu-id="1e8eb-154">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-154">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e8eb-155">-ロール</span><span class="sxs-lookup"><span data-stu-id="1e8eb-155">-Role</span></span>

<span data-ttu-id="1e8eb-156">クライアントとして、またはサーバーとして CredSSP を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-156">Specifies whether to enable CredSSP as a client or as a server.</span></span> <span data-ttu-id="1e8eb-157">このパラメーターに指定できる値は、 **Client** および **Server** です。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-157">The acceptable values for this parameter are: **Client** and **Server**.</span></span>

<span data-ttu-id="1e8eb-158">**クライアント** を指定すると、次のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-158">If you specify **Client** , the following actions are performed.</span></span> <span data-ttu-id="1e8eb-159">これらの設定では、サーバー認証が実行されるときに、クライアントがサーバーに明示的な資格情報を委任することが許可されます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-159">These settings allow the client to delegate explicit credentials to a server when server authentication is achieved.</span></span>

- <span data-ttu-id="1e8eb-160">クライアントで CredSSP を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-160">Enables CredSSP on the client.</span></span>
- <span data-ttu-id="1e8eb-161">WS-Management 設定を `\<localhost|computername\>\Client\Auth\CredSSP` true に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-161">Sets the WS-Management setting `\<localhost|computername\>\Client\Auth\CredSSP` to true.</span></span>
- <span data-ttu-id="1e8eb-162">Windows CredSSP ポリシー **AllowFreshCredentials** をクライアントの **WSMan/Delegate** に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-162">Sets the Windows CredSSP policy **AllowFreshCredentials** to **WSMan/Delegate** on the client.</span></span>

<span data-ttu-id="1e8eb-163">**サーバー** を指定した場合は、次のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-163">If you specify **Server** , the following actions are performed.</span></span> <span data-ttu-id="1e8eb-164">このポリシー設定では、サーバーがクライアントの代理として動作することが許可されます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-164">This policy setting allows the server to act as a delegate for clients.</span></span>

- <span data-ttu-id="1e8eb-165">サーバーで CredSSP を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-165">Enables CredSSP on the server.</span></span>
- <span data-ttu-id="1e8eb-166">WS-Management 設定を `\<localhost|computername\>\Service\Auth\CredSSP` true に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-166">Sets the WS-Management setting `\<localhost|computername\>\Service\Auth\CredSSP` to true.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e8eb-167">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e8eb-167">CommonParameters</span></span>

<span data-ttu-id="1e8eb-168">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1e8eb-169">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1e8eb-170">入力</span><span class="sxs-lookup"><span data-stu-id="1e8eb-170">INPUTS</span></span>

### <span data-ttu-id="1e8eb-171">なし</span><span class="sxs-lookup"><span data-stu-id="1e8eb-171">None</span></span>

<span data-ttu-id="1e8eb-172">このコマンドレットは入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-172">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="1e8eb-173">出力</span><span class="sxs-lookup"><span data-stu-id="1e8eb-173">OUTPUTS</span></span>

### <span data-ttu-id="1e8eb-174">System.Xml.Xml要素</span><span class="sxs-lookup"><span data-stu-id="1e8eb-174">System.Xml.XmlElement</span></span>

<span data-ttu-id="1e8eb-175">CredSSP 認証が正常に有効になっている場合、このコマンドレットは **XMLElement** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-175">If CredSSP authentication is successfully enabled, this cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="1e8eb-176">注</span><span class="sxs-lookup"><span data-stu-id="1e8eb-176">NOTES</span></span>

<span data-ttu-id="1e8eb-177">CredSSP 認証を無効にするには、コマンドレットを使用し `Disable-WSManCredSSP` ます。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-177">To disable CredSSP authentication, use the `Disable-WSManCredSSP` cmdlet.</span></span>

## <span data-ttu-id="1e8eb-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1e8eb-178">RELATED LINKS</span></span>

[<span data-ttu-id="1e8eb-179">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="1e8eb-179">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="1e8eb-180">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1e8eb-180">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="1e8eb-181">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="1e8eb-181">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="1e8eb-182">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1e8eb-182">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="1e8eb-183">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1e8eb-183">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="1e8eb-184">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="1e8eb-184">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="1e8eb-185">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1e8eb-185">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="1e8eb-186">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="1e8eb-186">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="1e8eb-187">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1e8eb-187">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="1e8eb-188">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1e8eb-188">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="1e8eb-189">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="1e8eb-189">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="1e8eb-190">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="1e8eb-190">Test-WSMan</span></span>](Test-WSMan.md)

