---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "93218040"
---
# <span data-ttu-id="a5778-103">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="a5778-103">Enable-PSRemoting</span></span>

## <span data-ttu-id="a5778-104">概要</span><span class="sxs-lookup"><span data-stu-id="a5778-104">SYNOPSIS</span></span>
<span data-ttu-id="a5778-105">リモート コマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="a5778-105">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="a5778-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5778-106">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a5778-107">Description</span><span class="sxs-lookup"><span data-stu-id="a5778-107">DESCRIPTION</span></span>

<span data-ttu-id="a5778-108">`Enable-PSRemoting`コマンドレットは、WS-Management テクノロジを使用して送信される PowerShell リモートコマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="a5778-108">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span>

<span data-ttu-id="a5778-109">PowerShell リモート処理は、Windows Server 2012 では既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a5778-109">PowerShell remoting is enabled by default on Windows Server 2012.</span></span> <span data-ttu-id="a5778-110">を使用し `Enable-PSRemoting` て、サポートされている他のバージョンの windows で PowerShell リモート処理を有効にしたり、Windows Server 2012 が無効になった場合にリモート処理を再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5778-110">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting on Windows Server 2012 if it becomes disabled.</span></span>

<span data-ttu-id="a5778-111">このコマンドは、コマンドを受信する各コンピューターで1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5778-111">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="a5778-112">コマンドを送信するだけのコンピューターで実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a5778-112">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="a5778-113">構成はリスナーを開始するため、必要な場合にのみ実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5778-113">Because the configuration starts listeners, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="a5778-114">PowerShell 3.0 以降では、 `Enable-PSRemoting` コンピューターがパブリックネットワーク上にある場合、コマンドレットを使用して、クライアントバージョンの Windows で PowerShell リモート処理を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5778-114">Beginning in PowerShell 3.0, the `Enable-PSRemoting` cmdlet can enable PowerShell remoting on client versions of Windows when the computer is on a public network.</span></span> <span data-ttu-id="a5778-115">詳細については、 **SkipNetworkProfileCheck** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5778-115">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="a5778-116">`Enable-PSRemoting`コマンドレットでは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5778-116">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="a5778-117">次のタスクを実行する [set-wsmanquickconfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5778-117">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="a5778-118">WinRM サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="a5778-118">Starts the WinRM service.</span></span>
  - <span data-ttu-id="a5778-119">WinRM サービスのスタートアップの種類を自動に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5778-119">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="a5778-120">任意の IP アドレスで要求を受け入れるリスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5778-120">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="a5778-121">WS-Management 通信に対してファイアウォールの例外を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5778-121">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="a5778-122">まだ登録されていない場合は、 **Microsoft powershell** および **microsoft の powershell** セッション構成を登録します。</span><span class="sxs-lookup"><span data-stu-id="a5778-122">Registers the **Microsoft.PowerShell** and **Microsoft.PowerShell.Workflow** session configurations, if it they are not already registered.</span></span>
  - <span data-ttu-id="a5778-123">**Microsoft.powershell32** セッション構成がまだ登録されていない場合は、64ビットコンピューターに登録します。</span><span class="sxs-lookup"><span data-stu-id="a5778-123">Registers the **Microsoft.PowerShell32** session configuration on 64-bit computers, if it is not already registered.</span></span>
  - <span data-ttu-id="a5778-124">すべてのセッション構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5778-124">Enables all session configurations.</span></span>
  - <span data-ttu-id="a5778-125">リモートアクセスを許可するように、すべてのセッション構成のセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="a5778-125">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="a5778-126">WinRM サービスを再起動して、上記の変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5778-126">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="a5778-127">Windows プラットフォームでこのコマンドレットを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="a5778-127">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="a5778-128">これは、Linux または MacOS バージョンの PowerShell には適用されません。</span><span class="sxs-lookup"><span data-stu-id="a5778-128">This does not apply to Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="a5778-129">Powershell 3.0 と PowerShell 2.0 の両方がインストールされているシステムでは、PowerShell 2.0 を使用して、 `Enable-PSRemoting` `Disable-PSRemoting` コマンドレットとコマンドレットを実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="a5778-129">On systems that have both PowerShell 3.0 and PowerShell 2.0, do not use PowerShell 2.0 to run the `Enable-PSRemoting` and `Disable-PSRemoting` cmdlets.</span></span> <span data-ttu-id="a5778-130">コマンドが正常に完了したように見えても、リモート処理が正しく構成されません。</span><span class="sxs-lookup"><span data-stu-id="a5778-130">The commands might appear to succeed, but the remoting is not configured correctly.</span></span> <span data-ttu-id="a5778-131">リモートコマンドを使用してリモート処理を有効または無効にしようとすると、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5778-131">Remote commands and later attempts to enable and disable remoting, are likely to fail.</span></span>

## <span data-ttu-id="a5778-132">例</span><span class="sxs-lookup"><span data-stu-id="a5778-132">EXAMPLES</span></span>

### <span data-ttu-id="a5778-133">例 1: リモートコマンドを受信するようにコンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="a5778-133">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="a5778-134">このコマンドは、リモート コマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="a5778-134">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

### <span data-ttu-id="a5778-135">例 2: 確認プロンプトを表示せずにリモートコマンドを受信するようにコンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="a5778-135">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="a5778-136">このコマンドは、リモート コマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="a5778-136">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="a5778-137">**Force** パラメーターを指定すると、ユーザーにプロンプトが表示されません。</span><span class="sxs-lookup"><span data-stu-id="a5778-137">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

### <span data-ttu-id="a5778-138">例 3: クライアントでリモートアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="a5778-138">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="a5778-139">この例では、Windows オペレーティングシステムのクライアントバージョンでパブリックネットワークからのリモートアクセスを許可する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5778-139">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="a5778-140">ファイアウォール規則の名前は、Windows のバージョンによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5778-140">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="a5778-141">を使用し `Get-NetFirewallRule` て、ルールの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a5778-141">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="a5778-142">ファイアウォール規則を有効にする前に、規則のセキュリティ設定を表示して、構成が環境に適していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5778-142">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

<span data-ttu-id="a5778-143">既定では、は、 `Enable-PSRemoting` プライベートネットワークとドメインネットワークからのリモートアクセスを許可するネットワークルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5778-143">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="a5778-144">このコマンドでは、 **SkipNetworkProfileCheck** パラメーターを使用して、同じローカル サブネット内のパブリック ネットワークからのリモート アクセスを許可しています。</span><span class="sxs-lookup"><span data-stu-id="a5778-144">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="a5778-145">このコマンドは、確認メッセージを抑制する **Force** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5778-145">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="a5778-146">**SkipNetworkProfileCheck** パラメーターは、既定で同じローカルサブネット内のパブリックネットワークからのリモートアクセスを許可する Windows オペレーティングシステムのサーバーバージョンには影響しません。</span><span class="sxs-lookup"><span data-stu-id="a5778-146">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="a5778-147">`Set-NetFirewallRule` **Netsecurity** モジュールのコマンドレットは、任意のリモートの場所からのパブリックネットワークからのリモートアクセスを許可するファイアウォール規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="a5778-147">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="a5778-148">これには、異なるサブネット内の場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5778-148">This includes locations in different subnets.</span></span>

> [!NOTE]
> <span data-ttu-id="a5778-149">ファイアウォール規則の名前は、Windows のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a5778-149">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="a5778-150">コマンドレットを使用して、 `Get-NetFirewallRule` システム上のルールの名前を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a5778-150">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="a5778-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5778-151">PARAMETERS</span></span>

### <span data-ttu-id="a5778-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a5778-152">-Confirm</span></span>

<span data-ttu-id="a5778-153">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5778-153">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a5778-154">-Force</span><span class="sxs-lookup"><span data-stu-id="a5778-154">-Force</span></span>

<span data-ttu-id="a5778-155">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5778-155">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a5778-156">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="a5778-156">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="a5778-157">コンピューターがパブリックネットワーク上にある場合に、Windows オペレーティングシステムのクライアントバージョンでリモート処理を有効にすることを示します。</span><span class="sxs-lookup"><span data-stu-id="a5778-157">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="a5778-158">このパラメーターは、同じローカル サブネット内のコンピューターに対してのみリモート アクセスを許可する、パブリック ネットワークのファイアウォール規則を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5778-158">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="a5778-159">このパラメーターは、Windows オペレーティングシステムのサーバーバージョンには影響しません。既定では、パブリックネットワーク用のローカルサブネットファイアウォール規則があります。</span><span class="sxs-lookup"><span data-stu-id="a5778-159">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="a5778-160">サーバーのバージョンでローカルサブネットファイアウォールルールが無効になっている場合は、 `Enable-PSRemoting` このパラメーターの値に関係なく、再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5778-160">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="a5778-161">ローカルサブネットの制限を削除し、パブリックネットワーク上のすべての場所からのリモートアクセスを有効にするには、 `Set-NetFirewallRule` **netsecurity** モジュールのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5778-161">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="a5778-162">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a5778-162">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a5778-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a5778-163">-WhatIf</span></span>

<span data-ttu-id="a5778-164">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a5778-164">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a5778-165">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a5778-165">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a5778-166">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5778-166">CommonParameters</span></span>

<span data-ttu-id="a5778-167">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a5778-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a5778-168">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5778-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a5778-169">入力</span><span class="sxs-lookup"><span data-stu-id="a5778-169">INPUTS</span></span>

### <span data-ttu-id="a5778-170">なし</span><span class="sxs-lookup"><span data-stu-id="a5778-170">None</span></span>

<span data-ttu-id="a5778-171">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a5778-171">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a5778-172">出力</span><span class="sxs-lookup"><span data-stu-id="a5778-172">OUTPUTS</span></span>

### <span data-ttu-id="a5778-173">System.String</span><span class="sxs-lookup"><span data-stu-id="a5778-173">System.String</span></span>

<span data-ttu-id="a5778-174">このコマンドレットは、結果を説明する文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="a5778-174">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="a5778-175">注</span><span class="sxs-lookup"><span data-stu-id="a5778-175">NOTES</span></span>

<span data-ttu-id="a5778-176">PowerShell 3.0 では、は `Enable-PSRemoting` WS-Management 通信に対して次のファイアウォール例外を作成します。</span><span class="sxs-lookup"><span data-stu-id="a5778-176">In PowerShell 3.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="a5778-177">Windows オペレーティングシステムのサーバーバージョンでは、は、 `Enable-PSRemoting` リモートアクセスを許可するプライベートネットワークとドメインネットワーク用のファイアウォール規則を作成し、同じローカルサブネット内のコンピューターからのみリモートアクセスを許可するパブリックネットワーク用のファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="a5778-177">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="a5778-178">Windows オペレーティングシステムのクライアントバージョンでは、 `Enable-PSRemoting` PowerShell 3.0 で、無制限のリモートアクセスを許可するプライベートネットワークとドメインネットワークのファイアウォール規則が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a5778-178">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 3.0 creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="a5778-179">パブリック ネットワークに対して同じローカル サブネットからのリモート アクセスを許可するファイアウォール規則を作成するには、 **SkipNetworkProfileCheck** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5778-179">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="a5778-180">Windows オペレーティングシステムのクライアントまたはサーバーバージョンで、ローカルサブネットの制限を削除し、リモートアクセスを許可するパブリックネットワーク用のファイアウォール規則を作成するには、NetSecurity モジュールのコマンドレットを使用して `Set-NetFirewallRule` 次のコマンドを実行します。 `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="a5778-180">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="a5778-181">PowerShell 2.0 では、は `Enable-PSRemoting` WS-Management 通信に対して次のファイアウォール例外を作成します。</span><span class="sxs-lookup"><span data-stu-id="a5778-181">In PowerShell 2.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="a5778-182">Windows オペレーティングシステムのサーバーバージョンでは、リモートアクセスを許可するすべてのネットワークに対してファイアウォール規則が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a5778-182">On server versions of the Windows operating system, it creates firewall rules for all networks that allow remote access.</span></span>

<span data-ttu-id="a5778-183">Windows オペレーティングシステムのクライアントバージョンでは、 `Enable-PSRemoting` PowerShell 2.0 では、ドメインとプライベートネットワークの場所に対してのみファイアウォールの例外が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a5778-183">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 2.0 creates a firewall exception only for domain and private network locations.</span></span> <span data-ttu-id="a5778-184">セキュリティ上のリスクを最小限に抑えるため、で `Enable-PSRemoting` は、クライアントバージョンの Windows にパブリックネットワークのファイアウォール規則は作成されません。</span><span class="sxs-lookup"><span data-stu-id="a5778-184">To minimize security risks, `Enable-PSRemoting` does not create a firewall rule for public networks on client versions of Windows.</span></span> <span data-ttu-id="a5778-185">現在のネットワークの場所がパブリックの場合、は `Enable-PSRemoting` 次のメッセージを返します: ファイアウォールの状態を確認できません。</span><span class="sxs-lookup"><span data-stu-id="a5778-185">When the current network location is public, `Enable-PSRemoting` returns the following message: Unable to check the status of the firewall.</span></span>

<span data-ttu-id="a5778-186">PowerShell 3.0 以降では、すべて `Enable-PSRemoting` のセッション構成の **Enabled** プロパティの値をに設定することによって、すべてのセッション構成を有効にし `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="a5778-186">Starting in PowerShell 3.0, `Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="a5778-187">PowerShell 2.0 で、は、 `Enable-PSRemoting` セッション構成のセキュリティ記述子から **Deny_All** 設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="a5778-187">In PowerShell 2.0, `Enable-PSRemoting` removes the **Deny_All** setting from the security descriptor of session configurations.</span></span> <span data-ttu-id="a5778-188">PowerShell 3.0 では、 `Enable-PSRemoting` **Deny_All** と **Network_Deny_All** の設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="a5778-188">In PowerShell 3.0, `Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="a5778-189">これにより、ローカルでの使用のために予約されているセッション構成へのリモートアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="a5778-189">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="a5778-190">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a5778-190">RELATED LINKS</span></span>

[<span data-ttu-id="a5778-191">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="a5778-191">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="a5778-192">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="a5778-192">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="a5778-193">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="a5778-193">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="a5778-194">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="a5778-194">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="a5778-195">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="a5778-195">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="a5778-196">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="a5778-196">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="a5778-197">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="a5778-197">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="a5778-198">about_Remote</span><span class="sxs-lookup"><span data-stu-id="a5778-198">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="a5778-199">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="a5778-199">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)
