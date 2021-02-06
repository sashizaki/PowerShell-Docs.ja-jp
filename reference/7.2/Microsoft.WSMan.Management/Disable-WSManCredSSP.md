---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: 3260c88d57e98c0072af8621600a02901c561acb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601226"
---
# <span data-ttu-id="3f296-102">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="3f296-102">Disable-WSManCredSSP</span></span>

## <span data-ttu-id="3f296-103">概要</span><span class="sxs-lookup"><span data-stu-id="3f296-103">SYNOPSIS</span></span>
<span data-ttu-id="3f296-104">コンピューターの CredSSP 認証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f296-104">Disables CredSSP authentication on a computer.</span></span>

## <span data-ttu-id="3f296-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3f296-105">SYNTAX</span></span>

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="3f296-106">Description</span><span class="sxs-lookup"><span data-stu-id="3f296-106">DESCRIPTION</span></span>
<span data-ttu-id="3f296-107">**Enable-wsmancredssp** コマンドレットは、クライアントまたはサーバーコンピューターでの Credential Security Support Provider (CredSSP) 認証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f296-107">The **Disable-WSManCredSSP** cmdlet disables Credential Security Support Provider (CredSSP) authentication on a client or on a server computer.</span></span>
<span data-ttu-id="3f296-108">CredSSP 認証を使用すると、ユーザーの資格情報が認証対象のリモートコンピューターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="3f296-108">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span>

<span data-ttu-id="3f296-109">このコマンドレットを使用して、 *Role* パラメーターに client を指定することにより、クライアントで CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f296-109">Use this cmdlet to disable CredSSP on the client by specifying Client in the *Role* parameter.</span></span>
<span data-ttu-id="3f296-110">このコマンドレットは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f296-110">This cmdlet performs the following actions:</span></span>

- <span data-ttu-id="3f296-111">クライアントで CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f296-111">Disables CredSSP on the client.</span></span> <span data-ttu-id="3f296-112">このコマンドレットは、WS-Management 設定 **\<localhost|computername\> \Client\Auth\CredSSP** を false に設定します。</span><span class="sxs-lookup"><span data-stu-id="3f296-112">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="3f296-113">クライアントの Windows CredSSP ポリシー **AllowFreshCredentials** から WSMan/\* 設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="3f296-113">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="3f296-114">このコマンドレットを使用して、 *ロール* でサーバーを指定することにより、サーバーで CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f296-114">Use this cmdlet to disable CredSSP on the server by specifying Server in *Role*.</span></span>
<span data-ttu-id="3f296-115">このコマンドレットは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f296-115">This cmdlet performs the following action:</span></span>

- <span data-ttu-id="3f296-116">サーバーの CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f296-116">Disables CredSSP on the server.</span></span> <span data-ttu-id="3f296-117">このコマンドレットは、WS-Management 設定 **\<localhost|computername\> \ Service\ Auth\ CredSSP** を false に設定します。</span><span class="sxs-lookup"><span data-stu-id="3f296-117">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

<span data-ttu-id="3f296-118">注意: CredSSP 認証では、ユーザーの資格情報がローカルコンピューターからリモートコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="3f296-118">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="3f296-119">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="3f296-119">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="3f296-120">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f296-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="3f296-121">例</span><span class="sxs-lookup"><span data-stu-id="3f296-121">EXAMPLES</span></span>

### <span data-ttu-id="3f296-122">例 1: クライアントで CredSSP を無効にする</span><span class="sxs-lookup"><span data-stu-id="3f296-122">Example 1: Disable CredSSP on a client</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Client
```

<span data-ttu-id="3f296-123">このコマンドは、クライアントで CredSSP を無効にして、サーバーへの委任を防止します。</span><span class="sxs-lookup"><span data-stu-id="3f296-123">This command disables CredSSP on the client, which prevents delegation to servers.</span></span>

### <span data-ttu-id="3f296-124">例 2: サーバーで CredSSP を無効にする</span><span class="sxs-lookup"><span data-stu-id="3f296-124">Example 2: Disable CredSSP on a server</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Server
```

<span data-ttu-id="3f296-125">このコマンドは、サーバーで CredSSP を無効にして、クライアントからの委任を防止します。</span><span class="sxs-lookup"><span data-stu-id="3f296-125">This command disables CredSSP on the server, which prevents delegation from clients.</span></span>

## <span data-ttu-id="3f296-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3f296-126">PARAMETERS</span></span>

### <span data-ttu-id="3f296-127">-ロール</span><span class="sxs-lookup"><span data-stu-id="3f296-127">-Role</span></span>
<span data-ttu-id="3f296-128">CredSSP をクライアントとして、またはサーバーとして無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f296-128">Specifies whether to disable CredSSP as a client or as a server.</span></span>
<span data-ttu-id="3f296-129">このパラメーターに指定できる値は、Client および Server です。</span><span class="sxs-lookup"><span data-stu-id="3f296-129">The acceptable values for this parameter are: Client and Server.</span></span>

<span data-ttu-id="3f296-130">クライアントを指定すると、このコマンドレットは次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f296-130">If you specify Client, this cmdlet performs the following actions:</span></span>

- <span data-ttu-id="3f296-131">クライアントで CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f296-131">Disables CredSSP on the client.</span></span> <span data-ttu-id="3f296-132">このコマンドレットは WS-Management 設定 **\<localhost|computername\> \Client\Auth\CredSSP** を false に設定します。</span><span class="sxs-lookup"><span data-stu-id="3f296-132">This cmdlet sets WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="3f296-133">クライアントの Windows CredSSP ポリシー **AllowFreshCredentials** から WSMan/\* 設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="3f296-133">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="3f296-134">Server を指定した場合、このコマンドレットは次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f296-134">If you specify Server, this cmdlet performs the following action:</span></span>

- <span data-ttu-id="3f296-135">サーバーの CredSSP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f296-135">Disables CredSSP on the server.</span></span> <span data-ttu-id="3f296-136">このコマンドレットは、WS-Management 設定 **\<localhost|computername\> \ Service\ Auth\ CredSSP** を false に設定します。</span><span class="sxs-lookup"><span data-stu-id="3f296-136">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

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

### <span data-ttu-id="3f296-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f296-137">CommonParameters</span></span>
<span data-ttu-id="3f296-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3f296-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3f296-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f296-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3f296-140">入力</span><span class="sxs-lookup"><span data-stu-id="3f296-140">INPUTS</span></span>

### <span data-ttu-id="3f296-141">なし</span><span class="sxs-lookup"><span data-stu-id="3f296-141">None</span></span>
<span data-ttu-id="3f296-142">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="3f296-142">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="3f296-143">出力</span><span class="sxs-lookup"><span data-stu-id="3f296-143">OUTPUTS</span></span>

### <span data-ttu-id="3f296-144">なし</span><span class="sxs-lookup"><span data-stu-id="3f296-144">None</span></span>
<span data-ttu-id="3f296-145">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="3f296-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3f296-146">注</span><span class="sxs-lookup"><span data-stu-id="3f296-146">NOTES</span></span>

* <span data-ttu-id="3f296-147">CredSSP 認証を有効にするには、Enable-WSManCredSSP コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f296-147">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

*

## <span data-ttu-id="3f296-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3f296-148">RELATED LINKS</span></span>

[<span data-ttu-id="3f296-149">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="3f296-149">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="3f296-150">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="3f296-150">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="3f296-151">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="3f296-151">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="3f296-152">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="3f296-152">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="3f296-153">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3f296-153">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="3f296-154">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="3f296-154">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="3f296-155">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3f296-155">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="3f296-156">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="3f296-156">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="3f296-157">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3f296-157">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="3f296-158">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3f296-158">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="3f296-159">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="3f296-159">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="3f296-160">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="3f296-160">Test-WSMan</span></span>](Test-WSMan.md)

