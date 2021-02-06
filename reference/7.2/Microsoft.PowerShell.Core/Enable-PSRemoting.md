---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: a3d9506a0fd2adbb9cc093fb24f99e922dc8a938
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605447"
---
# <span data-ttu-id="8acee-102">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="8acee-102">Enable-PSRemoting</span></span>

## <span data-ttu-id="8acee-103">概要</span><span class="sxs-lookup"><span data-stu-id="8acee-103">SYNOPSIS</span></span>
<span data-ttu-id="8acee-104">リモート コマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-104">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="8acee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8acee-105">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8acee-106">Description</span><span class="sxs-lookup"><span data-stu-id="8acee-106">DESCRIPTION</span></span>

<span data-ttu-id="8acee-107">`Enable-PSRemoting`コマンドレットは、WS-Management テクノロジを使用して送信される PowerShell リモートコマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-107">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span> <span data-ttu-id="8acee-108">WS-Management ベースの PowerShell リモート処理は、現在、Windows プラットフォームでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8acee-108">WS-Management based PowerShell remoting is currently supported only on Windows platform.</span></span>

<span data-ttu-id="8acee-109">PowerShell リモート処理は、Windows Server プラットフォームでは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8acee-109">PowerShell remoting is enabled by default on Windows Server platforms.</span></span> <span data-ttu-id="8acee-110">を使用し `Enable-PSRemoting` て、サポートされている他のバージョンの Windows で PowerShell リモート処理を有効にし、無効になった場合にリモート処理を再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8acee-110">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting if it becomes disabled.</span></span>

<span data-ttu-id="8acee-111">このコマンドは、コマンドを受信する各コンピューターで1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8acee-111">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="8acee-112">コマンドを送信するだけのコンピューターで実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8acee-112">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="8acee-113">構成では、リモート接続を受け入れるためにリスナーが開始されるため、必要な場合にのみ実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8acee-113">Because the configuration starts listeners to accept remote connections, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="8acee-114">コンピューターがパブリックネットワーク上にあるときに、Windows のクライアントバージョンで PowerShell リモート処理を有効にすることは、通常は禁止されていますが、 **SkipNetworkProfileCheck** パラメーターを使用してこの制限をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="8acee-114">Enabling PowerShell remoting on client versions of Windows when the computer is on a public network is normally disallowed, but you can skip this restriction by using the **SkipNetworkProfileCheck** parameter.</span></span> <span data-ttu-id="8acee-115">詳細については、**SkipNetworkProfileCheck** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8acee-115">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="8acee-116">複数の PowerShell インストールは、1台のコンピューターにサイドバイサイドで共存できます。</span><span class="sxs-lookup"><span data-stu-id="8acee-116">Multiple PowerShell installations can exist side-by-side on a single computer.</span></span> <span data-ttu-id="8acee-117">を実行する `Enable-PSRemoting` と、コマンドレットを実行している特定のインストールバージョンのリモート処理エンドポイントが構成されます。</span><span class="sxs-lookup"><span data-stu-id="8acee-117">Running `Enable-PSRemoting` will configure a remoting endpoint for the specific installation version that you are running the cmdlet in.</span></span> <span data-ttu-id="8acee-118">`Enable-PSRemoting`Powershell 6.2 の実行中にを実行すると、powershell 6.2 を実行するリモート処理エンドポイントが構成されます。</span><span class="sxs-lookup"><span data-stu-id="8acee-118">So if you run `Enable-PSRemoting` while running PowerShell 6.2, a remoting endpoint will be configured that runs PowerShell 6.2.</span></span> <span data-ttu-id="8acee-119">`Enable-PSRemoting`Powershell 7-preview の実行中にを実行すると、powershell 7-preview を実行するリモート処理エンドポイントが構成されます。</span><span class="sxs-lookup"><span data-stu-id="8acee-119">If you run `Enable-PSRemoting` while running PowerShell 7-preview, a remoting endpoint will be configured that runs PowerShell 7-preview.</span></span>

<span data-ttu-id="8acee-120">`Enable-PSRemoting` 必要に応じて、2つのリモート処理エンドポイント構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-120">`Enable-PSRemoting` creates two remoting endpoint configurations as needed.</span></span> <span data-ttu-id="8acee-121">エンドポイント構成が既に存在する場合は、単に有効になっていることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="8acee-121">If the endpoint configurations already exist, then they are simply ensured to be enabled.</span></span> <span data-ttu-id="8acee-122">作成された構成は同じですが、名前が異なります。</span><span class="sxs-lookup"><span data-stu-id="8acee-122">The created configurations are identical but have different names.</span></span> <span data-ttu-id="8acee-123">1つは、セッションをホストする PowerShell のバージョンに対応する簡易名を持つことです。</span><span class="sxs-lookup"><span data-stu-id="8acee-123">One will have a simple name corresponding to the PowerShell version that hosts the session.</span></span> <span data-ttu-id="8acee-124">その他の構成名には、セッションをホストする PowerShell のバージョンに関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8acee-124">The other configuration name contains more detailed information about the PowerShell version which hosts the session.</span></span> <span data-ttu-id="8acee-125">たとえば、 `Enable-PSRemoting` powershell 6.2 で実行する場合は、 **powershell. 6**, **6.2.2** という名前の2つのエンドポイントが構成されます。</span><span class="sxs-lookup"><span data-stu-id="8acee-125">For example, when running `Enable-PSRemoting` in PowerShell 6.2, you will get two configured endpoints named **PowerShell.6**, **PowerShell.6.2.2**.</span></span>
<span data-ttu-id="8acee-126">これにより、単純な名前の **powershell. 6** を使用して、powershell 6 ホストの最新バージョンへの接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8acee-126">This allows you to create a connection to the latest PowerShell 6 host version by using the simple name **PowerShell.6**.</span></span> <span data-ttu-id="8acee-127">または、長い名前の **6.2.2** を使用して、特定の powershell ホストバージョンに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="8acee-127">Or you can connect to a specific PowerShell host version by using the longer name **PowerShell.6.2.2**.</span></span>

<span data-ttu-id="8acee-128">新しく有効にされたリモート処理エンドポイントを使用するには `Invoke-Command` 、、、コマンドレットを使用してリモート接続を作成するときに、ConfigurationName パラメーターを使用して名前で指定する必要があり `New-PSSession` `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="8acee-128">To use the newly enabled remoting endpoints, you must specify them by name with the **ConfigurationName** parameter when creating a remote connection using the `Invoke-Command`,`New-PSSession`,`Enter-PSSession` cmdlets.</span></span> <span data-ttu-id="8acee-129">詳細については、例4を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8acee-129">For more information, see Example 4.</span></span>

<span data-ttu-id="8acee-130">`Enable-PSRemoting`コマンドレットでは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8acee-130">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="8acee-131">次のタスクを実行する [set-wsmanquickconfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8acee-131">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="8acee-132">WinRM サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8acee-132">Starts the WinRM service.</span></span>
  - <span data-ttu-id="8acee-133">WinRM サービスのスタートアップの種類を自動に設定します。</span><span class="sxs-lookup"><span data-stu-id="8acee-133">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="8acee-134">任意の IP アドレスで要求を受け入れるリスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-134">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="8acee-135">WS-Management 通信に対してファイアウォールの例外を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8acee-135">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="8acee-136">必要に応じて、simple および long name セッションエンドポイント構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-136">Creates the simple and long name session endpoint configurations if needed.</span></span>
  - <span data-ttu-id="8acee-137">すべてのセッション構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8acee-137">Enables all session configurations.</span></span>
  - <span data-ttu-id="8acee-138">リモートアクセスを許可するように、すべてのセッション構成のセキュリティ記述子を変更します。</span><span class="sxs-lookup"><span data-stu-id="8acee-138">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="8acee-139">WinRM サービスを再起動して、上記の変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8acee-139">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="8acee-140">Windows プラットフォームでこのコマンドレットを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="8acee-140">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="8acee-141">このコマンドレットは、Linux または MacOS バージョンの PowerShell では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8acee-141">This cmdlet is not available on Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="8acee-142">このコマンドレットは、Windows PowerShell によって作成されたリモートエンドポイント構成には影響しません。</span><span class="sxs-lookup"><span data-stu-id="8acee-142">This cmdlet does not affect remote endpoint configurations created by Windows PowerShell.</span></span>
> <span data-ttu-id="8acee-143">PowerShell バージョン6以降で作成されたエンドポイントにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="8acee-143">It only affects endpoints created with PowerShell version 6 and greater.</span></span> <span data-ttu-id="8acee-144">Windows PowerShell でホストされている PowerShell リモート処理エンドポイントを有効または無効にするには、 `Enable-PSRemoting` Windows powershell セッション内からコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8acee-144">To enable and disable PowerShell remoting endpoints that are hosted by Windows PowerShell, run the `Enable-PSRemoting` cmdlet from within a Windows PowerShell session.</span></span>

## <span data-ttu-id="8acee-145">例</span><span class="sxs-lookup"><span data-stu-id="8acee-145">EXAMPLES</span></span>

### <span data-ttu-id="8acee-146">例 1: リモートコマンドを受信するようにコンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="8acee-146">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="8acee-147">このコマンドは、リモート コマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-147">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="8acee-148">例 2: 確認プロンプトを表示せずにリモートコマンドを受信するようにコンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="8acee-148">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="8acee-149">このコマンドは、リモート コマンドを受信するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-149">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="8acee-150">**Force** パラメーターを指定すると、ユーザーにプロンプトが表示されません。</span><span class="sxs-lookup"><span data-stu-id="8acee-150">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="8acee-151">例 3: クライアントでリモートアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="8acee-151">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="8acee-152">この例では、Windows オペレーティングシステムのクライアントバージョンでパブリックネットワークからのリモートアクセスを許可する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8acee-152">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="8acee-153">ファイアウォール規則の名前は、Windows のバージョンによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8acee-153">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="8acee-154">を使用し `Get-NetFirewallRule` て、ルールの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="8acee-154">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="8acee-155">ファイアウォール規則を有効にする前に、規則のセキュリティ設定を表示して、構成が環境に適していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8acee-155">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

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

<span data-ttu-id="8acee-156">既定では、は、 `Enable-PSRemoting` プライベートネットワークとドメインネットワークからのリモートアクセスを許可するネットワークルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-156">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="8acee-157">このコマンドでは、**SkipNetworkProfileCheck** パラメーターを使用して、同じローカル サブネット内のパブリック ネットワークからのリモート アクセスを許可しています。</span><span class="sxs-lookup"><span data-stu-id="8acee-157">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="8acee-158">このコマンドは、確認メッセージを抑制する **Force** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="8acee-158">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="8acee-159">**SkipNetworkProfileCheck** パラメーターは、既定で同じローカルサブネット内のパブリックネットワークからのリモートアクセスを許可する Windows オペレーティングシステムのサーバーバージョンには影響しません。</span><span class="sxs-lookup"><span data-stu-id="8acee-159">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="8acee-160">`Set-NetFirewallRule` **Netsecurity** モジュールのコマンドレットは、任意のリモートの場所からのパブリックネットワークからのリモートアクセスを許可するファイアウォール規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="8acee-160">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="8acee-161">これには、異なるサブネット内の場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8acee-161">This includes locations in different subnets.</span></span>

### <span data-ttu-id="8acee-162">例 4: 新しく有効化されたエンドポイント構成へのリモートセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="8acee-162">Example 4: Create a remote session to the newly enabled endpoint configuration</span></span>

<span data-ttu-id="8acee-163">この例では、コンピューターで PowerShell リモート処理を有効にする方法、構成されているエンドポイント名を検索する方法、およびいずれかのエンドポイントへのリモートセッションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8acee-163">This example shows how to enable PowerShell remoting on a computer, find the configured endpoint names, and create a remote session to one of the endpoints.</span></span>

<span data-ttu-id="8acee-164">最初のコマンドは、コンピューター上の PowerShell リモート処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8acee-164">The first command enables PowerShell remoting on the computer.</span></span>

<span data-ttu-id="8acee-165">2番目のコマンドは、エンドポイントの構成を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8acee-165">The second command lists the endpoint configurations.</span></span>

<span data-ttu-id="8acee-166">3番目のコマンドは、同じコンピューターに対してリモート PowerShell セッションを作成し、名前で **powershell. 6** エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8acee-166">The third command creates a remote PowerShell session to the same machine, specifying the **PowerShell.6** endpoint by name.</span></span> <span data-ttu-id="8acee-167">リモートセッションは、最新の PowerShell 6 バージョン (6.2.2) でホストされます。</span><span class="sxs-lookup"><span data-stu-id="8acee-167">The remote session will be hosted with the latest PowerShell 6 version (6.2.2).</span></span>

<span data-ttu-id="8acee-168">最後のコマンドは、リモートセッションの変数にアクセスして、 `$PSVersionTable` セッションをホストしている PowerShell のバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="8acee-168">The last command accesses the `$PSVersionTable` variable in the remote session to display the PowerShell version that is hosting the session.</span></span>

```powershell
Enable-PSRemoting -Force

Get-PSSessionConfiguration

$session = New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6

Invoke-Command -Session $session -ScriptBlock { $PSVersionTable }
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name                           Value
----                           -----
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0…}
PSEdition                      Core
PSRemotingProtocolVersion      2.3
Platform                       Win32NT
SerializationVersion           1.1.0.1
GitCommitId                    6.2.2
WSManStackVersion              3.0
PSVersion                      6.2.2
OS                             Microsoft Windows 10.0.18363
```

> [!NOTE]
> <span data-ttu-id="8acee-169">ファイアウォール規則の名前は、Windows のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8acee-169">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="8acee-170">コマンドレットを使用して、 `Get-NetFirewallRule` システム上のルールの名前を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8acee-170">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="8acee-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8acee-171">PARAMETERS</span></span>

### <span data-ttu-id="8acee-172">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8acee-172">-Confirm</span></span>

<span data-ttu-id="8acee-173">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8acee-173">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8acee-174">-Force</span><span class="sxs-lookup"><span data-stu-id="8acee-174">-Force</span></span>

<span data-ttu-id="8acee-175">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8acee-175">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="8acee-176">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="8acee-176">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="8acee-177">コンピューターがパブリックネットワーク上にある場合に、Windows オペレーティングシステムのクライアントバージョンでリモート処理を有効にすることを示します。</span><span class="sxs-lookup"><span data-stu-id="8acee-177">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="8acee-178">このパラメーターは、同じローカル サブネット内のコンピューターに対してのみリモート アクセスを許可する、パブリック ネットワークのファイアウォール規則を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8acee-178">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="8acee-179">このパラメーターは、Windows オペレーティングシステムのサーバーバージョンには影響しません。既定では、パブリックネットワーク用のローカルサブネットファイアウォール規則があります。</span><span class="sxs-lookup"><span data-stu-id="8acee-179">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="8acee-180">サーバーのバージョンでローカルサブネットファイアウォールルールが無効になっている場合は、 `Enable-PSRemoting` このパラメーターの値に関係なく、再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="8acee-180">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="8acee-181">ローカルサブネットの制限を削除し、パブリックネットワーク上のすべての場所からのリモートアクセスを有効にするには、 `Set-NetFirewallRule` **netsecurity** モジュールのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8acee-181">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="8acee-182">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8acee-182">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8acee-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8acee-183">-WhatIf</span></span>

<span data-ttu-id="8acee-184">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="8acee-184">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8acee-185">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8acee-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8acee-186">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8acee-186">CommonParameters</span></span>

<span data-ttu-id="8acee-187">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8acee-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8acee-188">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8acee-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8acee-189">入力</span><span class="sxs-lookup"><span data-stu-id="8acee-189">INPUTS</span></span>

### <span data-ttu-id="8acee-190">なし</span><span class="sxs-lookup"><span data-stu-id="8acee-190">None</span></span>

<span data-ttu-id="8acee-191">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8acee-191">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8acee-192">出力</span><span class="sxs-lookup"><span data-stu-id="8acee-192">OUTPUTS</span></span>

### <span data-ttu-id="8acee-193">System.String</span><span class="sxs-lookup"><span data-stu-id="8acee-193">System.String</span></span>

<span data-ttu-id="8acee-194">このコマンドレットは、結果を説明する文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="8acee-194">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="8acee-195">注</span><span class="sxs-lookup"><span data-stu-id="8acee-195">NOTES</span></span>

<span data-ttu-id="8acee-196">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8acee-196">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="8acee-197">Windows オペレーティングシステムのサーバーバージョンでは、は、 `Enable-PSRemoting` リモートアクセスを許可するプライベートネットワークとドメインネットワーク用のファイアウォール規則を作成し、同じローカルサブネット内のコンピューターからのみリモートアクセスを許可するパブリックネットワーク用のファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-197">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="8acee-198">Windows オペレーティングシステムのクライアントバージョンでは、は、 `Enable-PSRemoting` 無制限のリモートアクセスを許可するプライベートネットワークとドメインネットワーク用のファイアウォール規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="8acee-198">On client versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="8acee-199">パブリック ネットワークに対して同じローカル サブネットからのリモート アクセスを許可するファイアウォール規則を作成するには、**SkipNetworkProfileCheck** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8acee-199">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="8acee-200">Windows オペレーティングシステムのクライアントまたはサーバーバージョンで、ローカルサブネットの制限を削除し、リモートアクセスを許可するパブリックネットワーク用のファイアウォール規則を作成するには、NetSecurity モジュールのコマンドレットを使用して `Set-NetFirewallRule` 次のコマンドを実行します。 `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="8acee-200">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="8acee-201">`Enable-PSRemoting` すべてのセッション構成の **Enabled** プロパティの値をに設定することにより、すべてのセッション構成を有効に `$True` します。</span><span class="sxs-lookup"><span data-stu-id="8acee-201">`Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="8acee-202">`Enable-PSRemoting`**Deny_All** と **Network_Deny_All** の設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="8acee-202">`Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="8acee-203">これにより、ローカルでの使用のために予約されているセッション構成へのリモートアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="8acee-203">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="8acee-204">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8acee-204">RELATED LINKS</span></span>

[<span data-ttu-id="8acee-205">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8acee-205">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="8acee-206">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8acee-206">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="8acee-207">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8acee-207">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="8acee-208">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8acee-208">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="8acee-209">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8acee-209">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="8acee-210">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="8acee-210">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="8acee-211">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="8acee-211">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="8acee-212">about_Remote</span><span class="sxs-lookup"><span data-stu-id="8acee-212">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="8acee-213">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="8acee-213">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)
