---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: e88f230575e1e3106efc211e3f95dd82ec62146c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211720"
---
# <span data-ttu-id="a5124-103">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a5124-103">Disable-WSManCredSSP</span></span>

## <span data-ttu-id="a5124-104">概要</span><span class="sxs-lookup"><span data-stu-id="a5124-104">SYNOPSIS</span></span>
<span data-ttu-id="a5124-105">コンピューターの CredSSP 認証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5124-105">Disables CredSSP authentication on a computer.</span></span>

## <span data-ttu-id="a5124-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5124-106">SYNTAX</span></span>

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="a5124-107">Description</span><span class="sxs-lookup"><span data-stu-id="a5124-107">DESCRIPTION</span></span>
<span data-ttu-id="a5124-108">**Enable-wsmancredssp** コマンドレットは、クライアントまたはサーバーコンピューターでの Credential Security Support Provider (CredSSP) 認証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5124-108">The **Disable-WSManCredSSP** cmdlet disables Credential Security Support Provider (CredSSP) authentication on a client or on a server computer.</span></span>
<span data-ttu-id="a5124-109">CredSSP 認証を使用すると、ユーザーの資格情報が認証対象のリモートコンピューターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="a5124-109">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span>

<span data-ttu-id="a5124-110">このコマンドレットを使用して、 *Role* パラメーターに client を指定することにより、クライアントで CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5124-110">Use this cmdlet to disable CredSSP on the client by specifying Client in the *Role* parameter.</span></span>
<span data-ttu-id="a5124-111">このコマンドレットは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5124-111">This cmdlet performs the following actions:</span></span>

- <span data-ttu-id="a5124-112">クライアントで CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5124-112">Disables CredSSP on the client.</span></span> <span data-ttu-id="a5124-113">このコマンドレットは、WS-Management 設定 **\<localhost|computername\> \Client\Auth\CredSSP** を false に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5124-113">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="a5124-114">クライアントの Windows CredSSP ポリシー **AllowFreshCredentials** から WSMan/\* 設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="a5124-114">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="a5124-115">このコマンドレットを使用して、 *ロール* でサーバーを指定することにより、サーバーで CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5124-115">Use this cmdlet to disable CredSSP on the server by specifying Server in *Role* .</span></span>
<span data-ttu-id="a5124-116">このコマンドレットは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5124-116">This cmdlet performs the following action:</span></span>

- <span data-ttu-id="a5124-117">サーバーの CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5124-117">Disables CredSSP on the server.</span></span> <span data-ttu-id="a5124-118">このコマンドレットは、WS-Management 設定 **\<localhost|computername\> \ Service\ Auth\ CredSSP** を false に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5124-118">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

<span data-ttu-id="a5124-119">注意: CredSSP 認証では、ユーザーの資格情報がローカルコンピューターからリモートコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="a5124-119">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="a5124-120">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="a5124-120">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="a5124-121">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5124-121">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="a5124-122">例</span><span class="sxs-lookup"><span data-stu-id="a5124-122">EXAMPLES</span></span>

### <span data-ttu-id="a5124-123">例 1: クライアントで CredSSP を無効にする</span><span class="sxs-lookup"><span data-stu-id="a5124-123">Example 1: Disable CredSSP on a client</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Client
```

<span data-ttu-id="a5124-124">このコマンドは、クライアントで CredSSP を無効にして、サーバーへの委任を防止します。</span><span class="sxs-lookup"><span data-stu-id="a5124-124">This command disables CredSSP on the client, which prevents delegation to servers.</span></span>

### <span data-ttu-id="a5124-125">例 2: サーバーで CredSSP を無効にする</span><span class="sxs-lookup"><span data-stu-id="a5124-125">Example 2: Disable CredSSP on a server</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Server
```

<span data-ttu-id="a5124-126">このコマンドは、サーバーで CredSSP を無効にして、クライアントからの委任を防止します。</span><span class="sxs-lookup"><span data-stu-id="a5124-126">This command disables CredSSP on the server, which prevents delegation from clients.</span></span>

## <span data-ttu-id="a5124-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5124-127">PARAMETERS</span></span>

### <span data-ttu-id="a5124-128">-ロール</span><span class="sxs-lookup"><span data-stu-id="a5124-128">-Role</span></span>
<span data-ttu-id="a5124-129">CredSSP をクライアントとして、またはサーバーとして無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5124-129">Specifies whether to disable CredSSP as a client or as a server.</span></span>
<span data-ttu-id="a5124-130">このパラメーターに指定できる値は、Client および Server です。</span><span class="sxs-lookup"><span data-stu-id="a5124-130">The acceptable values for this parameter are: Client and Server.</span></span>

<span data-ttu-id="a5124-131">クライアントを指定すると、このコマンドレットは次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5124-131">If you specify Client, this cmdlet performs the following actions:</span></span>

- <span data-ttu-id="a5124-132">クライアントで CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5124-132">Disables CredSSP on the client.</span></span> <span data-ttu-id="a5124-133">このコマンドレットは WS-Management 設定 **\<localhost|computername\> \Client\Auth\CredSSP** を false に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5124-133">This cmdlet sets WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="a5124-134">クライアントの Windows CredSSP ポリシー **AllowFreshCredentials** から WSMan/\* 設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="a5124-134">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="a5124-135">Server を指定した場合、このコマンドレットは次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5124-135">If you specify Server, this cmdlet performs the following action:</span></span>

- <span data-ttu-id="a5124-136">サーバーの CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5124-136">Disables CredSSP on the server.</span></span> <span data-ttu-id="a5124-137">このコマンドレットは、WS-Management 設定 **\<localhost|computername\> \ Service\ Auth\ CredSSP** を false に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5124-137">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

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

### <span data-ttu-id="a5124-138">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5124-138">CommonParameters</span></span>
<span data-ttu-id="a5124-139">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a5124-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a5124-140">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5124-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a5124-141">入力</span><span class="sxs-lookup"><span data-stu-id="a5124-141">INPUTS</span></span>

### <span data-ttu-id="a5124-142">なし</span><span class="sxs-lookup"><span data-stu-id="a5124-142">None</span></span>
<span data-ttu-id="a5124-143">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="a5124-143">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="a5124-144">出力</span><span class="sxs-lookup"><span data-stu-id="a5124-144">OUTPUTS</span></span>

### <span data-ttu-id="a5124-145">なし</span><span class="sxs-lookup"><span data-stu-id="a5124-145">None</span></span>
<span data-ttu-id="a5124-146">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a5124-146">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a5124-147">注</span><span class="sxs-lookup"><span data-stu-id="a5124-147">NOTES</span></span>

* <span data-ttu-id="a5124-148">CredSSP 認証を有効にするには、Enable-WSManCredSSP コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5124-148">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

*

## <span data-ttu-id="a5124-149">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a5124-149">RELATED LINKS</span></span>

[<span data-ttu-id="a5124-150">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="a5124-150">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="a5124-151">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="a5124-151">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="a5124-152">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a5124-152">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="a5124-153">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a5124-153">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="a5124-154">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a5124-154">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="a5124-155">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="a5124-155">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="a5124-156">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a5124-156">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="a5124-157">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="a5124-157">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="a5124-158">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a5124-158">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="a5124-159">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a5124-159">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="a5124-160">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="a5124-160">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="a5124-161">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="a5124-161">Test-WSMan</span></span>](Test-WSMan.md)

