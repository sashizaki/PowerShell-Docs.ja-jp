---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: e5d50af0551a183b8e9e1995fbd722c331a48486
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603203"
---
# <span data-ttu-id="51dc7-102">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="51dc7-102">Set-WSManQuickConfig</span></span>

## <span data-ttu-id="51dc7-103">概要</span><span class="sxs-lookup"><span data-stu-id="51dc7-103">SYNOPSIS</span></span>
<span data-ttu-id="51dc7-104">ローカル コンピューターをリモート管理用に構成します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-104">Configures the local computer for remote management.</span></span>

## <span data-ttu-id="51dc7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="51dc7-105">SYNTAX</span></span>

### <span data-ttu-id="51dc7-106">すべて</span><span class="sxs-lookup"><span data-stu-id="51dc7-106">All</span></span>

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## <span data-ttu-id="51dc7-107">Description</span><span class="sxs-lookup"><span data-stu-id="51dc7-107">DESCRIPTION</span></span>

<span data-ttu-id="51dc7-108">`Set-WSManQuickConfig`コマンドレットは、Web Services For management (ws-management) テクノロジを使用して送信される PowerShell リモートコマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-108">The `Set-WSManQuickConfig` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the Web Services for Management (WS-Management) technology.</span></span>

<span data-ttu-id="51dc7-109">`Set-WSManQuickConfig` は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-109">`Set-WSManQuickConfig` performs the following actions:</span></span>

- <span data-ttu-id="51dc7-110">WinRM サービスが実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-110">Checks whether the WinRM service is running.</span></span> <span data-ttu-id="51dc7-111">WinRM サービスが実行されていない場合は、サービスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="51dc7-111">If the WinRM service isn't running, the service is started.</span></span>
- <span data-ttu-id="51dc7-112">WinRM サービスのスタートアップの種類を自動に設定します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-112">Sets the WinRM service startup type to automatic.</span></span>
- <span data-ttu-id="51dc7-113">任意の IP アドレスで要求を受け入れるリスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-113">Creates a listener to accept requests on any IP address.</span></span> <span data-ttu-id="51dc7-114">既定のトランスポートは **HTTP** です。</span><span class="sxs-lookup"><span data-stu-id="51dc7-114">The default transport is **HTTP**.</span></span>
- <span data-ttu-id="51dc7-115">WinRM トラフィックのファイアウォールの例外を有効にします。</span><span class="sxs-lookup"><span data-stu-id="51dc7-115">Enables a firewall exception for WinRM traffic.</span></span>

<span data-ttu-id="51dc7-116">を実行するに `Set-WSManQuickConfig` は、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-116">To run `Set-WSManQuickConfig`, start PowerShell with the **Run as Administrator** option.</span></span>

## <span data-ttu-id="51dc7-117">例</span><span class="sxs-lookup"><span data-stu-id="51dc7-117">EXAMPLES</span></span>

### <span data-ttu-id="51dc7-118">例 1: HTTP 経由でローカルコンピューターのリモート管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="51dc7-118">Example 1: Enable remote management of the local computer over HTTP</span></span>

<span data-ttu-id="51dc7-119">この例では、ローカルコンピューターのリモート管理を有効にするために必要な構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-119">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="51dc7-120">既定では、このコマンドは **HTTP** 上に WS-Management リスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-120">By default, this command creates a WS-Management listener on **HTTP**.</span></span>

```powershell
Set-WSManQuickConfig
```

### <span data-ttu-id="51dc7-121">例 2: HTTPS 経由でローカルコンピューターのリモート管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="51dc7-121">Example 2: Enable remote management of the local computer over HTTPS</span></span>

<span data-ttu-id="51dc7-122">この例では、ローカルコンピューターのリモート管理を有効にするために必要な構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-122">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="51dc7-123">**UseSSL** パラメーターは、コンピューターとの通信に **HTTPS** を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-123">The **UseSSL** parameter specifies that **HTTPS** is used to communicate with the computer.</span></span>

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> <span data-ttu-id="51dc7-124">**HTTPS** には手動の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="51dc7-124">**HTTPS** requires manual configuration.</span></span> <span data-ttu-id="51dc7-125">詳細については、 **UseSSL** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51dc7-125">For more information, see the **UseSSL** parameter's description.</span></span>

## <span data-ttu-id="51dc7-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="51dc7-126">PARAMETERS</span></span>

### <span data-ttu-id="51dc7-127">-Force</span><span class="sxs-lookup"><span data-stu-id="51dc7-127">-Force</span></span>

<span data-ttu-id="51dc7-128">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-128">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="51dc7-129">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="51dc7-129">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="51dc7-130">コンピューターがパブリックネットワーク上にある場合に、リモート処理用に Windows クライアントのバージョンを構成します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-130">Configures Windows client versions for remoting when the computer is on a public network.</span></span> <span data-ttu-id="51dc7-131">このパラメーターは、同じローカル サブネット内のコンピューターに対してのみリモート アクセスを許可する、パブリック ネットワークのファイアウォール規則を有効にします。</span><span class="sxs-lookup"><span data-stu-id="51dc7-131">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="51dc7-132">このパラメーターは、Windows のサーバーバージョンには影響しません。既定では、パブリックネットワーク用のローカルサブネットファイアウォール規則があります。</span><span class="sxs-lookup"><span data-stu-id="51dc7-132">This parameter has no effect on server versions of Windows, that by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="51dc7-133">サーバーバージョンの Windows でローカルサブネットファイアウォールルールが無効になっている場合は、 `Enable-PSRemoting` このパラメーターの値に関係なく、再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="51dc7-133">If the local subnet firewall rule is disabled on the server version of Windows, `Enable-PSRemoting` re-enables it, regardless of this parameter's value.</span></span>

<span data-ttu-id="51dc7-134">ローカルサブネットの制限を削除し、パブリックネットワーク上のすべての場所からのリモートアクセスを有効にするには、 `Set-NetFirewallRule` **netsecurity** モジュールのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-134">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="51dc7-135">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="51dc7-135">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="51dc7-136">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="51dc7-136">-UseSSL</span></span>

<span data-ttu-id="51dc7-137">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-137">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span> <span data-ttu-id="51dc7-138">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="51dc7-138">By default, SSL isn't used.</span></span>

<span data-ttu-id="51dc7-139">WS-Management は、ネットワーク経由で転送されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-139">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="51dc7-140">**UseSSL** パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="51dc7-140">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="51dc7-141">このパラメーターを使用していて、接続に使用されているポートで SSL が使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="51dc7-141">If you use this parameter and SSL isn't available on the port that's used for the connection, the command fails.</span></span>

<span data-ttu-id="51dc7-142">**HTTPS** では、WinRM とファイアウォール規則を手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51dc7-142">**HTTPS** requires manual configuration of WinRM and firewall rules.</span></span> <span data-ttu-id="51dc7-143">詳細については、「 [How to: CONFIGURE WINRM FOR HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51dc7-143">For more information, see [How To: Configure WINRM for HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span></span>

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

### <span data-ttu-id="51dc7-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="51dc7-144">CommonParameters</span></span>

<span data-ttu-id="51dc7-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="51dc7-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="51dc7-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51dc7-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="51dc7-147">入力</span><span class="sxs-lookup"><span data-stu-id="51dc7-147">INPUTS</span></span>

### <span data-ttu-id="51dc7-148">なし</span><span class="sxs-lookup"><span data-stu-id="51dc7-148">None</span></span>

<span data-ttu-id="51dc7-149">このコマンドレットは入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="51dc7-149">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="51dc7-150">出力</span><span class="sxs-lookup"><span data-stu-id="51dc7-150">OUTPUTS</span></span>

### <span data-ttu-id="51dc7-151">なし</span><span class="sxs-lookup"><span data-stu-id="51dc7-151">None</span></span>

<span data-ttu-id="51dc7-152">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="51dc7-152">This cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="51dc7-153">注</span><span class="sxs-lookup"><span data-stu-id="51dc7-153">NOTES</span></span>

## <span data-ttu-id="51dc7-154">関連リンク</span><span class="sxs-lookup"><span data-stu-id="51dc7-154">RELATED LINKS</span></span>

[<span data-ttu-id="51dc7-155">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="51dc7-155">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="51dc7-156">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="51dc7-156">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="51dc7-157">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="51dc7-157">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="51dc7-158">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="51dc7-158">Enable-PSRemoting</span></span>](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[<span data-ttu-id="51dc7-159">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="51dc7-159">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="51dc7-160">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="51dc7-160">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="51dc7-161">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="51dc7-161">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="51dc7-162">方法: WINRM を HTTPS 用に構成する</span><span class="sxs-lookup"><span data-stu-id="51dc7-162">How To: Configure WINRM for HTTPS</span></span>](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[<span data-ttu-id="51dc7-163">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="51dc7-163">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="51dc7-164">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="51dc7-164">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="51dc7-165">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="51dc7-165">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="51dc7-166">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="51dc7-166">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="51dc7-167">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="51dc7-167">Test-WSMan</span></span>](Test-WSMan.md)

