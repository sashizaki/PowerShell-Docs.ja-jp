---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: 9830d1feb31e9cca735a7ac8d2ed9d2ec50380b5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600383"
---
# <span data-ttu-id="69258-102">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="69258-102">Get-WSManCredSSP</span></span>

## <span data-ttu-id="69258-103">概要</span><span class="sxs-lookup"><span data-stu-id="69258-103">SYNOPSIS</span></span>
<span data-ttu-id="69258-104">クライアントの Credential Security Support Provider 関連の構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="69258-104">Gets the Credential Security Support Provider-related configuration for the client.</span></span>

## <span data-ttu-id="69258-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="69258-105">SYNTAX</span></span>

```
Get-WSManCredSSP [<CommonParameters>]
```

## <span data-ttu-id="69258-106">Description</span><span class="sxs-lookup"><span data-stu-id="69258-106">DESCRIPTION</span></span>
<span data-ttu-id="69258-107">**Enable-wsmancredssp** コマンドレットは、クライアントとサーバーの Credential Security Support Provider 関連の構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="69258-107">The **Get-WSManCredSSP** cmdlet gets the Credential Security Support Provider-related configuration of the client and the server.</span></span>
<span data-ttu-id="69258-108">出力には、Credential Security Support Provider (CredSSP) 認証が有効か無効かが示されます。</span><span class="sxs-lookup"><span data-stu-id="69258-108">The output indicates whether Credential Security Support Provider (CredSSP) authentication is enabled or disabled.</span></span>
<span data-ttu-id="69258-109">このコマンドレットには、CredSSP の **AllowFreshCredentials** ポリシーの構成情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="69258-109">This cmdlet also displays configuration information for the **AllowFreshCredentials** policy of CredSSP.</span></span>

<span data-ttu-id="69258-110">CredSSP 認証を使用すると、ユーザーの資格情報が認証対象のリモートコンピューターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="69258-110">When you use CredSSP authentication, the user credentials are passed to a remote computer to be authenticated.</span></span>
<span data-ttu-id="69258-111">この種類の認証は、別のリモートセッションからリモートセッションを作成するコマンド用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="69258-111">This type of authentication is designed for commands that create a remote session from another remote session.</span></span>
<span data-ttu-id="69258-112">たとえば、リモートコンピューターでバックグラウンドジョブを実行する場合は、この種類の認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="69258-112">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="69258-113">このコマンドレットは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="69258-113">The cmdlet performs the following actions:</span></span>

- <span data-ttu-id="69258-114">クライアントの WS-Management CredSSP 設定 (**\<localhost|computername\> \Client\Auth\CredSSP**) を取得します。</span><span class="sxs-lookup"><span data-stu-id="69258-114">Gets the WS-Management CredSSP setting on the client (**\<localhost|computername\>\Client\Auth\CredSSP**).</span></span>
- <span data-ttu-id="69258-115">Windows CredSSP ポリシー設定 **AllowFreshCredentials** を取得します。</span><span class="sxs-lookup"><span data-stu-id="69258-115">Gets the Windows CredSSP policy setting **AllowFreshCredentials**.</span></span>
- <span data-ttu-id="69258-116">サーバー (\**\<localhost|computername\> \ service\** 認証) の WS-Management CredSSP 設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="69258-116">Gets the WS-Management CredSSP setting on the server (**\<localhost|computername\>\Service\Auth\CredSSP**).</span></span>

<span data-ttu-id="69258-117">注意: CredSSP 認証では、ユーザーの資格情報がローカルコンピューターからリモートコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="69258-117">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="69258-118">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="69258-118">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="69258-119">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="69258-119">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="69258-120">例</span><span class="sxs-lookup"><span data-stu-id="69258-120">EXAMPLES</span></span>

### <span data-ttu-id="69258-121">例 1: CredSSP の構成を表示する</span><span class="sxs-lookup"><span data-stu-id="69258-121">Example 1: Display CredSSP configuration</span></span>

```
PS C:\> Get-WSManCredSSP
```

<span data-ttu-id="69258-122">このコマンドは、クライアントとサーバーの両方の CredSSP 構成情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="69258-122">This command displays CredSSP configuration information for both the client and server.</span></span>

<span data-ttu-id="69258-123">出力には、このコンピューターで CredSSP が構成されているかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="69258-123">The output identifies that this computer is or is not configured for CredSSP.</span></span>

<span data-ttu-id="69258-124">コンピューターで CredSSP が構成されている場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69258-124">If the computer is configured for CredSSP, this is the output:</span></span>

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

<span data-ttu-id="69258-125">コンピューターで CredSSP が構成されていない場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69258-125">If the computer is not configured for CredSSP, this is the output:</span></span>

`The machine is not configured to allow delegating fresh credentials.`

## <span data-ttu-id="69258-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="69258-126">PARAMETERS</span></span>

### <span data-ttu-id="69258-127">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="69258-127">CommonParameters</span></span>
<span data-ttu-id="69258-128">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="69258-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="69258-129">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69258-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="69258-130">入力</span><span class="sxs-lookup"><span data-stu-id="69258-130">INPUTS</span></span>

### <span data-ttu-id="69258-131">なし</span><span class="sxs-lookup"><span data-stu-id="69258-131">None</span></span>
<span data-ttu-id="69258-132">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="69258-132">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="69258-133">出力</span><span class="sxs-lookup"><span data-stu-id="69258-133">OUTPUTS</span></span>

### <span data-ttu-id="69258-134">なし</span><span class="sxs-lookup"><span data-stu-id="69258-134">None</span></span>
<span data-ttu-id="69258-135">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="69258-135">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="69258-136">注</span><span class="sxs-lookup"><span data-stu-id="69258-136">NOTES</span></span>

* <span data-ttu-id="69258-137">CredSSP 認証を無効にするには、Disable-WSManCredSSP コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="69258-137">To disable CredSSP authentication, use the Disable-WSManCredSSP cmdlet.</span></span> <span data-ttu-id="69258-138">CredSSP 認証を有効にするには、Enable-WSManCredSSP コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="69258-138">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

## <span data-ttu-id="69258-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="69258-139">RELATED LINKS</span></span>

[<span data-ttu-id="69258-140">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="69258-140">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="69258-141">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="69258-141">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="69258-142">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="69258-142">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="69258-143">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="69258-143">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="69258-144">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="69258-144">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="69258-145">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="69258-145">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="69258-146">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="69258-146">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="69258-147">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="69258-147">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="69258-148">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="69258-148">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="69258-149">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="69258-149">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="69258-150">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="69258-150">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="69258-151">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="69258-151">Test-WSMan</span></span>](Test-WSMan.md)

