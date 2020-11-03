---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: 5b22eb9334510267d9c4e3757b39810cfdba1fd3
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224747"
---
# <span data-ttu-id="fe50f-103">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="fe50f-103">Set-WSManQuickConfig</span></span>

## <span data-ttu-id="fe50f-104">概要</span><span class="sxs-lookup"><span data-stu-id="fe50f-104">SYNOPSIS</span></span>
<span data-ttu-id="fe50f-105">ローカル コンピューターをリモート管理用に構成します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-105">Configures the local computer for remote management.</span></span>

## <span data-ttu-id="fe50f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fe50f-106">SYNTAX</span></span>

### <span data-ttu-id="fe50f-107">All</span><span class="sxs-lookup"><span data-stu-id="fe50f-107">All</span></span>

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## <span data-ttu-id="fe50f-108">Description</span><span class="sxs-lookup"><span data-stu-id="fe50f-108">DESCRIPTION</span></span>

<span data-ttu-id="fe50f-109">`Set-WSManQuickConfig`コマンドレットは、Web Services For management (ws-management) テクノロジを使用して送信される PowerShell リモートコマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-109">The `Set-WSManQuickConfig` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the Web Services for Management (WS-Management) technology.</span></span>

<span data-ttu-id="fe50f-110">`Set-WSManQuickConfig` は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-110">`Set-WSManQuickConfig` performs the following actions:</span></span>

- <span data-ttu-id="fe50f-111">WinRM サービスが実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-111">Checks whether the WinRM service is running.</span></span> <span data-ttu-id="fe50f-112">WinRM サービスが実行されていない場合は、サービスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="fe50f-112">If the WinRM service isn't running, the service is started.</span></span>
- <span data-ttu-id="fe50f-113">WinRM サービスのスタートアップの種類を自動に設定します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-113">Sets the WinRM service startup type to automatic.</span></span>
- <span data-ttu-id="fe50f-114">任意の IP アドレスで要求を受け入れるリスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-114">Creates a listener to accept requests on any IP address.</span></span> <span data-ttu-id="fe50f-115">既定のトランスポートは **HTTP** です。</span><span class="sxs-lookup"><span data-stu-id="fe50f-115">The default transport is **HTTP** .</span></span>
- <span data-ttu-id="fe50f-116">WinRM トラフィックのファイアウォールの例外を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fe50f-116">Enables a firewall exception for WinRM traffic.</span></span>

<span data-ttu-id="fe50f-117">を実行するに `Set-WSManQuickConfig` は、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-117">To run `Set-WSManQuickConfig`, start PowerShell with the **Run as Administrator** option.</span></span>

## <span data-ttu-id="fe50f-118">例</span><span class="sxs-lookup"><span data-stu-id="fe50f-118">EXAMPLES</span></span>

### <span data-ttu-id="fe50f-119">例 1: HTTP 経由でローカルコンピューターのリモート管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="fe50f-119">Example 1: Enable remote management of the local computer over HTTP</span></span>

<span data-ttu-id="fe50f-120">この例では、ローカルコンピューターのリモート管理を有効にするために必要な構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-120">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="fe50f-121">既定では、このコマンドは **HTTP** 上に WS-Management リスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-121">By default, this command creates a WS-Management listener on **HTTP** .</span></span>

```powershell
Set-WSManQuickConfig
```

### <span data-ttu-id="fe50f-122">例 2: HTTPS 経由でローカルコンピューターのリモート管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="fe50f-122">Example 2: Enable remote management of the local computer over HTTPS</span></span>

<span data-ttu-id="fe50f-123">この例では、ローカルコンピューターのリモート管理を有効にするために必要な構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-123">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="fe50f-124">**UseSSL** パラメーターは、コンピューターとの通信に **HTTPS** を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-124">The **UseSSL** parameter specifies that **HTTPS** is used to communicate with the computer.</span></span>

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> <span data-ttu-id="fe50f-125">**HTTPS** には手動の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="fe50f-125">**HTTPS** requires manual configuration.</span></span> <span data-ttu-id="fe50f-126">詳細については、 **UseSSL** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe50f-126">For more information, see the **UseSSL** parameter's description.</span></span>

## <span data-ttu-id="fe50f-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fe50f-127">PARAMETERS</span></span>

### <span data-ttu-id="fe50f-128">-Force</span><span class="sxs-lookup"><span data-stu-id="fe50f-128">-Force</span></span>

<span data-ttu-id="fe50f-129">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-129">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="fe50f-130">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="fe50f-130">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="fe50f-131">コンピューターがパブリックネットワーク上にある場合に、リモート処理用に Windows クライアントのバージョンを構成します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-131">Configures Windows client versions for remoting when the computer is on a public network.</span></span> <span data-ttu-id="fe50f-132">このパラメーターは、同じローカル サブネット内のコンピューターに対してのみリモート アクセスを許可する、パブリック ネットワークのファイアウォール規則を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fe50f-132">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="fe50f-133">このパラメーターは、Windows のサーバーバージョンには影響しません。既定では、パブリックネットワーク用のローカルサブネットファイアウォール規則があります。</span><span class="sxs-lookup"><span data-stu-id="fe50f-133">This parameter has no effect on server versions of Windows, that by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="fe50f-134">サーバーバージョンの Windows でローカルサブネットファイアウォールルールが無効になっている場合は、 `Enable-PSRemoting` このパラメーターの値に関係なく、再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="fe50f-134">If the local subnet firewall rule is disabled on the server version of Windows, `Enable-PSRemoting` re-enables it, regardless of this parameter's value.</span></span>

<span data-ttu-id="fe50f-135">ローカルサブネットの制限を削除し、パブリックネットワーク上のすべての場所からのリモートアクセスを有効にするには、 `Set-NetFirewallRule` **netsecurity** モジュールのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-135">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="fe50f-136">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fe50f-136">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fe50f-137">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="fe50f-137">-UseSSL</span></span>

<span data-ttu-id="fe50f-138">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-138">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span> <span data-ttu-id="fe50f-139">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="fe50f-139">By default, SSL isn't used.</span></span>

<span data-ttu-id="fe50f-140">WS-Management は、ネットワーク経由で転送されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-140">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="fe50f-141">**UseSSL** パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fe50f-141">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="fe50f-142">このパラメーターを使用していて、接続に使用されているポートで SSL が使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe50f-142">If you use this parameter and SSL isn't available on the port that's used for the connection, the command fails.</span></span>

<span data-ttu-id="fe50f-143">**HTTPS** では、WinRM とファイアウォール規則を手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe50f-143">**HTTPS** requires manual configuration of WinRM and firewall rules.</span></span> <span data-ttu-id="fe50f-144">詳細については、「 [How to: CONFIGURE WINRM FOR HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe50f-144">For more information, see [How To: Configure WINRM for HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span></span>

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

### <span data-ttu-id="fe50f-145">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe50f-145">CommonParameters</span></span>

<span data-ttu-id="fe50f-146">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fe50f-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fe50f-147">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe50f-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fe50f-148">入力</span><span class="sxs-lookup"><span data-stu-id="fe50f-148">INPUTS</span></span>

### <span data-ttu-id="fe50f-149">なし</span><span class="sxs-lookup"><span data-stu-id="fe50f-149">None</span></span>

<span data-ttu-id="fe50f-150">このコマンドレットは入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="fe50f-150">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="fe50f-151">出力</span><span class="sxs-lookup"><span data-stu-id="fe50f-151">OUTPUTS</span></span>

### <span data-ttu-id="fe50f-152">なし</span><span class="sxs-lookup"><span data-stu-id="fe50f-152">None</span></span>

<span data-ttu-id="fe50f-153">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="fe50f-153">This cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="fe50f-154">注</span><span class="sxs-lookup"><span data-stu-id="fe50f-154">NOTES</span></span>

## <span data-ttu-id="fe50f-155">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fe50f-155">RELATED LINKS</span></span>

[<span data-ttu-id="fe50f-156">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="fe50f-156">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="fe50f-157">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fe50f-157">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="fe50f-158">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="fe50f-158">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="fe50f-159">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="fe50f-159">Enable-PSRemoting</span></span>](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[<span data-ttu-id="fe50f-160">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fe50f-160">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="fe50f-161">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fe50f-161">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="fe50f-162">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fe50f-162">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="fe50f-163">方法: WINRM を HTTPS 用に構成する</span><span class="sxs-lookup"><span data-stu-id="fe50f-163">How To: Configure WINRM for HTTPS</span></span>](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[<span data-ttu-id="fe50f-164">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="fe50f-164">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="fe50f-165">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="fe50f-165">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="fe50f-166">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fe50f-166">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="fe50f-167">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="fe50f-167">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="fe50f-168">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="fe50f-168">Test-WSMan</span></span>](Test-WSMan.md)
