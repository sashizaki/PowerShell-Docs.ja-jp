---
description: WSMan
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: WSMan プロバイダー
ms.openlocfilehash: 7c693d29c6cc7743f7a423ae347889abb10ad255
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224171"
---
# <a name="wsman-provider"></a><span data-ttu-id="0280d-104">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="0280d-104">WSMan Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="0280d-105">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="0280d-105">Provider name</span></span>

<span data-ttu-id="0280d-106">WSMan</span><span class="sxs-lookup"><span data-stu-id="0280d-106">WSMan</span></span>

## <a name="drives"></a><span data-ttu-id="0280d-107">ドライブ</span><span class="sxs-lookup"><span data-stu-id="0280d-107">Drives</span></span>

`WSMan:`

## <a name="short-description"></a><span data-ttu-id="0280d-108">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="0280d-108">Short description</span></span>

<span data-ttu-id="0280d-109">Web Services for Management (WS-Management) 構成情報へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0280d-109">Provides access to Web Services for Management (WS-Management) configuration information.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="0280d-110">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="0280d-110">Detailed description</span></span>

<span data-ttu-id="0280d-111">**WSMan** Provider for PowerShell を使用すると、ローカルコンピューターまたはリモートコンピューター上の WS-Management 構成データを追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-111">The **WSMan** provider for PowerShell lets you add, change, clear, and delete WS-Management configuration data on local or remote computers.</span></span>

<span data-ttu-id="0280d-112">**WSMan** プロバイダーは、WS-Management 構成設定の論理グループに対応するディレクトリ構造を持つ PowerShell ドライブを公開します。</span><span class="sxs-lookup"><span data-stu-id="0280d-112">The **WSMan** provider exposes a PowerShell drive with a directory structure that corresponds to a logical grouping of WS-Management configuration settings.</span></span> <span data-ttu-id="0280d-113">これらのグループ化はコンテナーと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="0280d-113">These groupings are known as containers.</span></span>

<span data-ttu-id="0280d-114">Windows PowerShell 3.0 以降では、 **WSMan** プロバイダーが更新され、 **OutputBufferingMode** などのセッション構成の新しいプロパティをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="0280d-114">Beginning in Windows PowerShell 3.0, the **WSMan** provider has been updated to support new properties for session configurations, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="0280d-115">セッション構成はドライブのプラグインディレクトリに項目として表示され、 `WSMan:` プロパティは各セッション構成の項目として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-115">The session configurations appear as items in the Plugin directory of the `WSMan:` drive and the properties appear as items in each session configuration.</span></span>

<span data-ttu-id="0280d-116">**WSMan** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0280d-116">The **WSMan** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="0280d-117">Get-Location</span><span class="sxs-lookup"><span data-stu-id="0280d-117">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="0280d-118">Set-Location</span><span class="sxs-lookup"><span data-stu-id="0280d-118">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="0280d-119">Get-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-119">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="0280d-120">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="0280d-120">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="0280d-121">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-121">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="0280d-122">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-122">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> <span data-ttu-id="0280d-123">ドライブのコマンドを使用して、 `WSMan:` 新しいプロパティの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-123">You can use commands in the `WSMan:` drive to change the values of the new properties.</span></span> <span data-ttu-id="0280d-124">ただし、 `WSMan:` powershell 2.0 のドライブを使用して、Windows powershell 3.0 で導入されたプロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0280d-124">However, you cannot use the `WSMan:` drive in PowerShell 2.0 to change properties that are introduced in Windows PowerShell 3.0.</span></span>
> <span data-ttu-id="0280d-125">エラーは生成されませんが、これらの設定を変更するためのコマンドは有効ではありません。 Windows PowerShell 3.0 で **WSMan** ドライブを使用します。</span><span class="sxs-lookup"><span data-stu-id="0280d-125">Although no error is generated, the commands are not effective To change these settings, use the **WSMan** drive in Windows PowerShell 3.0.</span></span>

### <a name="organization-of-the-wsman-drive"></a><span data-ttu-id="0280d-126">WSMan: ドライブの構成</span><span class="sxs-lookup"><span data-stu-id="0280d-126">Organization of the WSMan: Drive</span></span>

- <span data-ttu-id="0280d-127">**クライアント** : WS-Management クライアントのさまざまな面を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-127">**Client** : You can configure various aspects of the WS-Management client.</span></span> <span data-ttu-id="0280d-128">構成情報はレジストリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-128">The configuration information is stored in the registry.</span></span>

- <span data-ttu-id="0280d-129">**サービス** : WS-Management サービスのさまざまな側面を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-129">**Service** : You can configure various aspects of the WS-Management service.</span></span>
  <span data-ttu-id="0280d-130">構成情報はレジストリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-130">The configuration information is stored in the registry.</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-131">サービス構成はサーバー構成と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="0280d-131">Service configuration is sometimes referred to as Server configuration.</span></span>

- <span data-ttu-id="0280d-132">**シェル** : リモートシェルアクセスを許可する設定 ( **AllowRemoteShellAccess** ) や、許可される同時ユーザーの最大数 ( **MaxConcurrentUsers** ) など、WS-Management シェルのさまざまな側面を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-132">**Shell** : You can configure various aspects of the WS-Management shell, such as the setting to allow remote shell access ( **AllowRemoteShellAccess** ) and the maximum number of concurrent users allowed ( **MaxConcurrentUsers** ).</span></span>

- <span data-ttu-id="0280d-133">**リスナー** : リスナーを作成して構成できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-133">**Listener** : You can create and configure a listener.</span></span> <span data-ttu-id="0280d-134">リスナーは WS-Management プロトコルを実装し、メッセージを送受信する管理サービスです。</span><span class="sxs-lookup"><span data-stu-id="0280d-134">A listener is a management service that implements the WS-Management protocol to send and to receive messages.</span></span>

- <span data-ttu-id="0280d-135">**プラグイン** : プラグインが読み込まれ、さまざまな機能を提供するために WS-Management サービスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-135">**Plugin** : Plug-ins are loaded and used by the WS-Management service to provide various functions.</span></span> <span data-ttu-id="0280d-136">既定では、PowerShell には次の3つのプラグインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0280d-136">By default, PowerShell provides three plug-ins:</span></span>
  - <span data-ttu-id="0280d-137">イベント転送プラグイン。</span><span class="sxs-lookup"><span data-stu-id="0280d-137">The Event Forwarding plug-in.</span></span>
  - <span data-ttu-id="0280d-138">Microsoft PowerShell プラグイン。</span><span class="sxs-lookup"><span data-stu-id="0280d-138">The Microsoft.PowerShell plug-in.</span></span>
  - <span data-ttu-id="0280d-139">Windows Management Instrumentation (WMI) プロバイダープラグイン。</span><span class="sxs-lookup"><span data-stu-id="0280d-139">The Windows Management Instrumentation (WMI) Provider plug-in.</span></span>
  <span data-ttu-id="0280d-140">この3つのプラグインは、イベントの転送、構成、および WMI アクセスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0280d-140">These three plug-ins support event forwarding, configuration, and WMI access.</span></span>

- <span data-ttu-id="0280d-141">**ClientCertificate** : クライアント証明書を作成して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0280d-141">**ClientCertificate** : You can create and configure a client certificate.</span></span>
  <span data-ttu-id="0280d-142">証明書認証を使用するように WS-Management クライアントが構成されているとき、クライアント証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-142">A client certificate is used when the WS-Management client is configured to use certificate authentication.</span></span>

### <a name="directory-hierarchy-of-the-wsman-provider"></a><span data-ttu-id="0280d-143">WSMan プロバイダーのディレクトリ階層</span><span class="sxs-lookup"><span data-stu-id="0280d-143">Directory Hierarchy of the WSMan Provider</span></span>

<span data-ttu-id="0280d-144">ローカルコンピューターの WSMan プロバイダーのディレクトリ階層は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0280d-144">The directory hierarchy of the WSMan provider for the local computer is as follows.</span></span>

```
WSMan:\localhost
--- Client
--- Service
--- Shell
--- Listener
------ <Specific_Listener>
--- Plugin
------ Event Forwarding Plugin
--------- InitializationParameters
--------- Resources
------------ Security
------ Microsoft.Powershell
--------- InitializationParameters
--------- Resources
------------ Security
------ WMI Provider
--------- InitializationParameters
--------- Resources
------------ Security
--- ClientCertificate
```

<span data-ttu-id="0280d-145">リモート コンピューターの WSMan プロバイダーのディレクトリ階層はローカル コンピューターと同じです。</span><span class="sxs-lookup"><span data-stu-id="0280d-145">The directory hierarchy of the WSMan provider for a remote computer is the same as a local computer.</span></span> <span data-ttu-id="0280d-146">ただし、リモート コンピューターの構成設定にアクセスするには、[Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan) を利用し、リモート コンピューターに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-146">However, in order to access the configuration settings of a remote computer, you need to make a connection to the remote computer using [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span> <span data-ttu-id="0280d-147">リモート コンピューターに接続すると、リモート コンピューターの名前がプロバイダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-147">Once a connection is made to a remote computer, the name of the remote computer shows up in the provider.</span></span>

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a><span data-ttu-id="0280d-148">WSMan: ドライブの移動</span><span class="sxs-lookup"><span data-stu-id="0280d-148">Navigating the WSMan: Drive</span></span>

<span data-ttu-id="0280d-149">このコマンドは、コマンドレットを使用して、 `Set-Location` 現在の場所をドライブに変更し `WSMan:` ます。</span><span class="sxs-lookup"><span data-stu-id="0280d-149">This command uses the `Set-Location` cmdlet to change the current location to the `WSMan:` drive.</span></span>

```powershell
Set-Location WSMan:
```

<span data-ttu-id="0280d-150">ファイル システム ドライブに戻るには、ドライブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="0280d-150">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="0280d-151">たとえば、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0280d-151">For example, type.</span></span>

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a><span data-ttu-id="0280d-152">リモートシステムストアの場所への移動</span><span class="sxs-lookup"><span data-stu-id="0280d-152">Navigating to a remote system store location</span></span>

<span data-ttu-id="0280d-153">このコマンドは、コマンドを使用して、 `Set-Location` 現在の場所をリモートシステムストアの場所のルートの場所に変更します。</span><span class="sxs-lookup"><span data-stu-id="0280d-153">This command uses the `Set-Location` command to change the current location to the root location in the remote system store location.</span></span> <span data-ttu-id="0280d-154">`\` `/` ドライブのレベルを示すには、円記号またはスラッシュを使用し `WSMan:` ます。</span><span class="sxs-lookup"><span data-stu-id="0280d-154">Use a backslash `\` or forward slash `/` to indicate a level of the `WSMan:` drive.</span></span>

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="0280d-155">上記のコマンドでは、リモート システムにすでに接続しているものと仮定しています。</span><span class="sxs-lookup"><span data-stu-id="0280d-155">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="displaying-the-contents-of-the-wsman-drive"></a><span data-ttu-id="0280d-156">WSMan: ドライブの内容を表示しています</span><span class="sxs-lookup"><span data-stu-id="0280d-156">Displaying the Contents of the WSMan: Drive</span></span>

<span data-ttu-id="0280d-157">このコマンドは、 `Get-Childitem` コマンドレットを使用して、Localhost ストアの場所に WS-Management ストアを表示します。</span><span class="sxs-lookup"><span data-stu-id="0280d-157">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the Localhost store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\Localhost
```

<span data-ttu-id="0280d-158">ドライブにいる場合は、 `WSMan:` ドライブ名を省略できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-158">If you are in the `WSMan:` drive, you can omit the drive name.</span></span>

<span data-ttu-id="0280d-159">このコマンドは、 `Get-Childitem` コマンドレットを使用して、リモートコンピューター "SERVER01" ストアの場所に WS-Management ストアを表示します。</span><span class="sxs-lookup"><span data-stu-id="0280d-159">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the remote computer "SERVER01" store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="0280d-160">上記のコマンドでは、リモート システムにすでに接続しているものと仮定しています。</span><span class="sxs-lookup"><span data-stu-id="0280d-160">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a><span data-ttu-id="0280d-161">WSMAN: ドライブ内の項目の値を設定する</span><span class="sxs-lookup"><span data-stu-id="0280d-161">Setting the value of items in the  WSMAN: drive</span></span>

<span data-ttu-id="0280d-162">`Set-Item`コマンドレットを使用して、ドライブの構成設定を変更でき `WSMAN` ます。</span><span class="sxs-lookup"><span data-stu-id="0280d-162">You can use the `Set-Item` cmdlet to change configuration settings in the `WSMAN` drive.</span></span> <span data-ttu-id="0280d-163">次の例では、"contoso.com" というサフィックスが付いたすべてのホストを受け入れるように **TrustedHosts** 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-163">The following example sets the **TrustedHosts** value to accept all hosts with the suffix "contoso.com".</span></span>

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

<span data-ttu-id="0280d-164">コマンドレットでは、 `Set-Item` `-Concatenate` 値を変更する代わりに値を追加する追加のパラメーターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0280d-164">The `Set-Item` cmdlet supports an additional parameter `-Concatenate` that appends a value instead of changing it.</span></span> <span data-ttu-id="0280d-165">次の例では、新しい値 "\*. domain2.com" を、に格納されている古い値に追加します。 `TrustedHost:`</span><span class="sxs-lookup"><span data-stu-id="0280d-165">The following example will append a new value "\*.domain2.com" to the old value stored in `TrustedHost:`</span></span>

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a><span data-ttu-id="0280d-166">WSMAN: ドライブに項目を作成する</span><span class="sxs-lookup"><span data-stu-id="0280d-166">Creating items in the WSMAN: drive</span></span>

### <a name="creating-a-new-listener"></a><span data-ttu-id="0280d-167">新しいリスナーの作成</span><span class="sxs-lookup"><span data-stu-id="0280d-167">Creating a new listener</span></span>

<span data-ttu-id="0280d-168">コマンドレットでは、 `New-Item` プロバイダードライブ内に項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="0280d-168">The `New-Item` cmdlet creates items within a provider drive.</span></span> <span data-ttu-id="0280d-169">各プロバイダーには、さまざまな種類のアイテムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-169">Each provider has different item types that you can create.</span></span> <span data-ttu-id="0280d-170">ドライブでは `WSMAN:` 、リモート要求を受信して応答するように構成する *リスナー* を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-170">In the `WSMAN:` drive, you can create *Listeners* which you configure to receive and respond to remote requests.</span></span> <span data-ttu-id="0280d-171">次のコマンドは、コマンドレットを使用して新しい HTTP リスナーを作成し `New-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="0280d-171">The following command creates a new HTTP listener using the `New-Item` cmdlet.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a><span data-ttu-id="0280d-172">新しいプラグインの作成</span><span class="sxs-lookup"><span data-stu-id="0280d-172">Creating a new plug-in</span></span>

<span data-ttu-id="0280d-173">このコマンドを実行すると、WS-Management サービスのプラグインが作成 (登録) されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-173">This command creates (registers) a plug-in for the WS-Management service.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a><span data-ttu-id="0280d-174">新しいリソースエントリを作成しています</span><span class="sxs-lookup"><span data-stu-id="0280d-174">Creating a new resource entry</span></span>

<span data-ttu-id="0280d-175">このコマンドは、TestPlugin の Resources ディレクトリにリソースエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="0280d-175">This command creates a resource entry in the Resources directory of a TestPlugin.</span></span> <span data-ttu-id="0280d-176">このコマンドは、TestPlugin が個別のコマンドを使用して作成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0280d-176">This command assumes that a TestPlugin has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a><span data-ttu-id="0280d-177">リソースの新しいセキュリティエントリを作成する</span><span class="sxs-lookup"><span data-stu-id="0280d-177">Creating a new security entry for a resource</span></span>

<span data-ttu-id="0280d-178">このコマンドを実行すると、Resource_5967683 (特定のリソース) の Security ディレクトリでセキュリティ エンティティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-178">This command creates a security entry in the Security directory of Resource_5967683 (a specific resource).</span></span> <span data-ttu-id="0280d-179">このコマンドは、リソースエントリが個別のコマンドを使用して作成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0280d-179">This command assumes that the resource entry has been created using a separate command.</span></span>

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a><span data-ttu-id="0280d-180">新しいクライアント証明書の作成</span><span class="sxs-lookup"><span data-stu-id="0280d-180">Creating a new Client Certificate</span></span>

<span data-ttu-id="0280d-181">このコマンドは、WS-Management クライアントが使用できる **ClientCertificate** エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="0280d-181">This command creates **ClientCertificate** entry that can be used by the WS-Management client.</span></span> <span data-ttu-id="0280d-182">新しい **ClientCertificate** は、 **ClientCertificate** ディレクトリの下に "ClientCertificate_1234567890" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-182">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="0280d-183">すべてのパラメーターが必須です。</span><span class="sxs-lookup"><span data-stu-id="0280d-183">All of the parameters are mandatory.</span></span> <span data-ttu-id="0280d-184">**発行者** は、発行者証明書の拇印である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-184">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a><span data-ttu-id="0280d-185">新しい初期化パラメーターの作成</span><span class="sxs-lookup"><span data-stu-id="0280d-185">Creating a new Initialization Parameter</span></span>

<span data-ttu-id="0280d-186">このコマンドは、"InitializationParameters" ディレクトリに "testparametername" という名前の初期化パラメーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="0280d-186">This command creates an Initialization parameter named "testparametername" in the "InitializationParameters" directory.</span></span> <span data-ttu-id="0280d-187">このコマンドは、"TestPlugin" が別のコマンドを使用して作成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0280d-187">This command assumes that the "TestPlugin" has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a><span data-ttu-id="0280d-188">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="0280d-188">Dynamic parameters</span></span>

<span data-ttu-id="0280d-189">動的パラメーターは、PowerShell プロバイダーによって追加されるコマンドレットパラメーターであり、プロバイダーに対応したドライブでコマンドレットが使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-189">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="address-string"></a><span data-ttu-id="0280d-190">アドレス \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-190">Address \<String\></span></span>

<span data-ttu-id="0280d-191">このリスナーが作成されたアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-191">Specifies the address for which this listener was created.</span></span> <span data-ttu-id="0280d-192">値は次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="0280d-192">The value can be one of the following:</span></span>

- <span data-ttu-id="0280d-193">リテラル文字列 "\*"。</span><span class="sxs-lookup"><span data-stu-id="0280d-193">The literal string "\*".</span></span> <span data-ttu-id="0280d-194">(ワイルドカード文字 () を使用すると、すべての IP アドレスがすべての `*` ネットワークアダプターにバインドされます)。</span><span class="sxs-lookup"><span data-stu-id="0280d-194">(The wildcard character (`*`) makes the command bind all the IP addresses on all the network adapters.)</span></span>
- <span data-ttu-id="0280d-195">リテラル文字列 "IP:" の後に、IPv4 のドット区切り10進数形式または IPv6 で複製された16進数形式の有効な IP アドレスが続きます。</span><span class="sxs-lookup"><span data-stu-id="0280d-195">The literal string "IP:" followed by a valid IP address in either IPv4 dotted-decimal format or in IPv6 cloned-hexadecimal format.</span></span>
- <span data-ttu-id="0280d-196">リテラル文字列 "MAC:" の後にアダプターの MAC アドレスが続きます。</span><span class="sxs-lookup"><span data-stu-id="0280d-196">The literal string "MAC:" followed by the MAC address of an adapter.</span></span>
  <span data-ttu-id="0280d-197">例: MAC:32-a3-58-90-cc。</span><span class="sxs-lookup"><span data-stu-id="0280d-197">For example: MAC:32-a3-58-90-be-cc.</span></span>

> [!NOTE]
> <span data-ttu-id="0280d-198">Address 値はリスナーの作成時に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-198">The Address value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-199">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-199">Cmdlets supported</span></span>

- [<span data-ttu-id="0280d-200">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-200">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a><span data-ttu-id="0280d-201">Capability \<Enumeration\></span><span class="sxs-lookup"><span data-stu-id="0280d-201">Capability \<Enumeration\></span></span>

<span data-ttu-id="0280d-202">*プラグイン* を使用する場合、このパラメーターは、この UNIFORM RESOURCE IDENTIFIER (URI) でサポートされる操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-202">When working with *Plug-ins* this parameter specifies an operation that is supported on this Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="0280d-203">URI でサポートされる操作の種類ごとに 1 つのエントリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-203">You have to create one entry for each type of operation that the URI supports.</span></span> <span data-ttu-id="0280d-204">操作でサポートされている場合は、特定の操作に対して有効な属性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-204">You can specify any valid attributes for a given operation, if the operation supports it.</span></span>

<span data-ttu-id="0280d-205">これらの属性には、 **Supportsfiltering** や **supportsfiltering** などがあります。</span><span class="sxs-lookup"><span data-stu-id="0280d-205">These attributes include **SupportsFiltering** and **SupportsFragment**.</span></span>

- <span data-ttu-id="0280d-206">**Create** : 作成操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0280d-206">**Create** : Create operations are supported on the URI.</span></span>
  - <span data-ttu-id="0280d-207">Create 操作で概念がサポートされている場合は、 **Supportfragment**  属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-207">The **SupportFragment**  attribute is used if the Create operation supports the concept.</span></span>
  - <span data-ttu-id="0280d-208">**Supportfiltering** 属性は作成操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-208">The **SupportFiltering** attribute is NOT valid for Create operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-209">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="0280d-209">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="0280d-210">**Delete** : delete 操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0280d-210">**Delete** : Delete operations are supported on the URI.</span></span>
  - <span data-ttu-id="0280d-211">削除操作で概念がサポートされている場合は、 **Supportfragment** 属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-211">The **SupportFragment** attribute is used if the Delete operation supports the concept.</span></span>
  - <span data-ttu-id="0280d-212">**Supportfiltering** 属性は削除操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-212">The **SupportFiltering** attribute is NOT valid for Delete operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-213">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="0280d-213">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="0280d-214">**列挙** : 列挙操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0280d-214">**Enumerate** : Enumerate operations are supported on the URI.</span></span>
  - <span data-ttu-id="0280d-215">**Supportfragment** 属性は、列挙操作ではサポートされていません。 False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-215">The **SupportFragment** attribute is NOT supported for Enumerate operations and should be set to False.</span></span>
  - <span data-ttu-id="0280d-216">**Supportfiltering** 属性は有効で、プラグインがフィルター処理をサポートしている場合は、この属性を "True" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-216">The **SupportFiltering** attribute is valid, and if the plug-in supports filtering, this attribute should be set to "True".</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-217">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="0280d-217">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="0280d-218">**Get** : URI で get 操作がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0280d-218">**Get** : Get operations are supported on the URI.</span></span>
  - <span data-ttu-id="0280d-219">Get 操作で概念がサポートされている場合は、 **Supportfragment** 属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-219">The **SupportFragment** attribute is used if the Get operation supports the concept.</span></span>
  - <span data-ttu-id="0280d-220">**Supportfiltering** 属性は Get 操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-220">The **SupportFiltering** attribute is NOT valid for Get operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-221">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="0280d-221">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="0280d-222">**Invoke** : 呼び出し操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0280d-222">**Invoke** : Invoke operations are supported on the URI.</span></span>
  - <span data-ttu-id="0280d-223">**Supportfragment** 属性は、呼び出し操作ではサポートされていません。 False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-223">The **SupportFragment** attribute is not supported for Invoke operations and should be set to False.</span></span>
  - <span data-ttu-id="0280d-224">**Supportfiltering** 属性は無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-224">The **SupportFiltering** attribute is not valid and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-225">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="0280d-225">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="0280d-226">**Put** : put 操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0280d-226">**Put** : Put operations are supported on the URI.</span></span>
  - <span data-ttu-id="0280d-227">Put 操作で概念がサポートされている場合は、 **Supportfragment** 属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-227">The **SupportFragment** attribute is used if the Put operation supports the concept.</span></span>
  - <span data-ttu-id="0280d-228">**Supportfiltering** 属性は、Put 操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-228">The **SupportFiltering** attribute is not valid for Put operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-229">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="0280d-229">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="0280d-230">**Subscribe** : サブスクライブ操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0280d-230">**Subscribe** : Subscribe operations are supported on the URI.</span></span>
  - <span data-ttu-id="0280d-231">**Supportfragment** 属性は、サブスクライブ操作ではサポートされていません。 False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-231">The **SupportFragment** attribute is not supported for Subscribe operations and should be set to False.</span></span>
  - <span data-ttu-id="0280d-232">**Supportfiltering** 属性はサブスクライブ操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-232">The **SupportFiltering** attribute is not valid for Subscribe operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-233">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="0280d-233">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="0280d-234">**Shell** : シェル操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0280d-234">**Shell** : Shell operations are supported on the URI.</span></span>
  - <span data-ttu-id="0280d-235">**Supportfragment** 属性はシェル操作ではサポートされていないため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-235">The **SupportFragment** attribute is not supported for Shell operations and should be set to "False".</span></span>
  - <span data-ttu-id="0280d-236">**Supportfiltering** 属性はシェル操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-236">The **SupportFiltering** attribute is not valid for Shell operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-237">他の操作もサポートされている場合、この操作は URI に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="0280d-237">This operation is not valid for a URI if ANY other operation is also supported.</span></span>
  > [!NOTE]
  > <span data-ttu-id="0280d-238">Shell 操作が URI に構成されている場合、Get、Put、Create、Delete、Invoke、Enumerate 操作は WS-Management (WinRM) サービスの内部で処理され、シェルを管理します。</span><span class="sxs-lookup"><span data-stu-id="0280d-238">If a Shell operation is configured for a URI, Get, Put, Create, Delete, Invoke, and Enumerate operations are processed internally within the WS-Management (WinRM) service to manage shells.</span></span> <span data-ttu-id="0280d-239">結果として、プラグインは操作を処理できません。</span><span class="sxs-lookup"><span data-stu-id="0280d-239">As a result, the plug-in cannot handle the operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-240">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-240">Cmdlets supported</span></span>

- [<span data-ttu-id="0280d-241">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-241">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a><span data-ttu-id="0280d-242">CertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-242">CertificateThumbprint \<String\></span></span>

<span data-ttu-id="0280d-243">サービス証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-243">Specifies the thumbprint of the service certificate.</span></span>

<span data-ttu-id="0280d-244">この値は証明書の拇印フィールドの 2 桁の 16 進数値の文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="0280d-244">This value represents the string of two-digit hexadecimal values in the Thumbprint field of the certificate.</span></span> <span data-ttu-id="0280d-245">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-245">It specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="0280d-246">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-246">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="0280d-247">これらの証明書はローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="0280d-247">They can be mapped only to local user accounts, and they do not work with domain accounts.</span></span> <span data-ttu-id="0280d-248">証明書の拇印を取得するに `Get-Item` は、PowerShell ドライブのまたはコマンドレットを使用し `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="0280d-248">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell `Cert:` drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-249">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-249">Cmdlets supported</span></span>

- [<span data-ttu-id="0280d-250">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-250">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a><span data-ttu-id="0280d-251">Enabled \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="0280d-251">Enabled \<Boolean\></span></span>

<span data-ttu-id="0280d-252">リスナーが有効であるか、無効であるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-252">Specifies whether the listener is enabled or disabled.</span></span> <span data-ttu-id="0280d-253">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="0280d-253">The default is True.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-254">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-254">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-255">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-255">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a><span data-ttu-id="0280d-256">FileName (Plugin) \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-256">FileName (Plugin) \<String\></span></span>

<span data-ttu-id="0280d-257">操作プラグインのファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-257">Specifies the file name of the operations plug-in.</span></span> <span data-ttu-id="0280d-258">このエントリに格納されている環境変数は、要求が受信されると、ユーザーのコンテキストで展開されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-258">Any environment variables that are put in this entry will be expanded in the users' context when a request is received.</span></span> <span data-ttu-id="0280d-259">各ユーザーは同じ環境変数の異なるバージョンを持つことができるため、各ユーザーが異なるプラグインを持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-259">Because each user could have a different version of the same environment variable, each user could have a different plug-in.</span></span> <span data-ttu-id="0280d-260">このエントリを空白にすることはできず、有効なプラグインをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-260">This entry cannot be blank and must point to a valid plug-in.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-261">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-261">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-262">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-262">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a><span data-ttu-id="0280d-263">HostName \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-263">HostName \<String\></span></span>

<span data-ttu-id="0280d-264">WS-Management (WinRM) サービスが実行されているコンピューターのホスト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-264">Specifies the host name of the computer on which the WS-Management (WinRM) service is running.</span></span>

<span data-ttu-id="0280d-265">値は完全修飾ドメイン名、IPv4 または IPv6 のリテラル文字列、またはワイルドカード文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0280d-265">The value must be a fully qualified domain name, an IPv4 or IPv6 literal string, or a wildcard character.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-266">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-266">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-267">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-267">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a><span data-ttu-id="0280d-268">Issuer \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-268">Issuer \<String\></span></span>

<span data-ttu-id="0280d-269">証明書を発行した証明機関の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-269">Specifies the name of the certification authority that issued the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-270">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-270">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-271">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-271">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a><span data-ttu-id="0280d-272">プラグイン \<\> WS-Management プラグインはネイティブダイナミックリンクライブラリ (dll) です。</span><span class="sxs-lookup"><span data-stu-id="0280d-272">Plugin \<\> WS-Management plug-ins are native dynamic link libraries (DLLs)</span></span>

<span data-ttu-id="0280d-273">これにより、WS-Management の機能に接続して拡張します。</span><span class="sxs-lookup"><span data-stu-id="0280d-273">that plug in to and extend the functionality of WS-Management .</span></span> <span data-ttu-id="0280d-274">WSW-Management プラグイン API は、サポートされているリソース Uri と操作に対して特定の Api を実装することによって、ユーザーがプラグインを記述できるようにする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="0280d-274">The WSW-Management Plug-in API provides functionality that enables a user to write plug-ins by implementing certain APIs for supported resource URIs and operations.</span></span> <span data-ttu-id="0280d-275">WS-Management (WinRM) サービスと Internet Information Services (IIS) のいずれかにプラグインを構成すると、WS-Management ホストと IIS ホストにそれぞれプラグインが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="0280d-275">After the plug-ins are configured for either the WS-Management (WinRM) service or for Internet Information Services (IIS), the plug-ins are loaded in the WS-Management host or in the IIS host, respectively.</span></span> <span data-ttu-id="0280d-276">リモート要求はこれらのプラグイン エントリ ポイントに送信され、操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-276">Remote requests are routed to these plug-in entry points to perform operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-277">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-277">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-278">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-278">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a><span data-ttu-id="0280d-279">Port \<Unsigned Short Integer\></span><span class="sxs-lookup"><span data-stu-id="0280d-279">Port \<Unsigned Short Integer\></span></span>

<span data-ttu-id="0280d-280">このリスナーが作成された TCP ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-280">Specifies the TCP port for which this listener is created.</span></span> <span data-ttu-id="0280d-281">1 から 65535 までの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0280d-281">You can specify any value from 1 through 65535.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-282">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-282">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-283">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-283">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="0280d-284">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-284">Resource \<String\></span></span>

<span data-ttu-id="0280d-285">はっきりと識別できる種類の管理操作または値を表すエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-285">Specifies an endpoint that represents a distinct type of management operation or value.</span></span> <span data-ttu-id="0280d-286">サービスは 1 つまたは複数のリソースを公開します。一部のリソースには複数のインスタンスが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="0280d-286">A service exposes one or more resources, and some resources can have more than one instance.</span></span> <span data-ttu-id="0280d-287">管理リソースは WMI クラスまたはデータベース テーブルに似ています。インスタンスはクラスのインスタンスまたはテーブルの行に似ています。</span><span class="sxs-lookup"><span data-stu-id="0280d-287">A management resource is similar to a WMI class or to a database table, and an instance is similar to an instance of the class or to a row in the table.</span></span> <span data-ttu-id="0280d-288">たとえば、 **Win32_LogicalDisk** クラスはリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="0280d-288">For example, the **Win32_LogicalDisk** class represents a resource.</span></span> <span data-ttu-id="0280d-289">`Win32_LogicalDisk="C:\\"` は、リソースの特定のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="0280d-289">`Win32_LogicalDisk="C:\\"` is a specific instance of the resource.</span></span>

<span data-ttu-id="0280d-290">Uniform Resource Identifier (URI) にはリソースの接頭辞とパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0280d-290">A Uniform Resource Identifier (URI) contains a prefix and a path to a resource.</span></span>
<span data-ttu-id="0280d-291">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0280d-291">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-292">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-292">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-293">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-293">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="0280d-294">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-294">Resource \<String\></span></span>

<span data-ttu-id="0280d-295">ディスクまたはプロセスなど、コンピューター上の特定のリソースを識別する Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-295">Specifies the Uniform Resource Identifier (URI) that identifies a specific type of resource, such as a disk or a process, on a computer.</span></span>

<span data-ttu-id="0280d-296">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-296">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="0280d-297">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0280d-297">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-298">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-298">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-299">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-299">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a><span data-ttu-id="0280d-300">SDKVersion \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-300">SDKVersion \<String\></span></span>

<span data-ttu-id="0280d-301">WS-Management プラグイン SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-301">Specifies the version of the WS-Management plug-in SDK.</span></span> <span data-ttu-id="0280d-302">唯一の有効な値  です。</span><span class="sxs-lookup"><span data-stu-id="0280d-302">The only valid value is</span></span>
1.

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-303">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-303">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-304">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-304">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a><span data-ttu-id="0280d-305">Subject \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-305">Subject \<String\></span></span>

<span data-ttu-id="0280d-306">証明書で識別されるエンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-306">Specifies the entity that is identified by the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-307">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-307">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-308">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-308">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a><span data-ttu-id="0280d-309">Transport \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-309">Transport \<String\></span></span>

<span data-ttu-id="0280d-310">WS-Management プロトコルの要求と応答を送受信するためのトランスポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-310">Specifies the transport to use to send and receive WS-Management protocol requests and responses.</span></span> <span data-ttu-id="0280d-311">値は HTTP と HTTPS のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="0280d-311">The value must be either HTTP or HTTPS.</span></span>

<span data-ttu-id="0280d-312">注: トランスポート値はリスナーの作成時に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0280d-312">Note: The Transport value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-313">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-313">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-314">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-314">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a><span data-ttu-id="0280d-315">URI \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-315">URI \<String\></span></span>

<span data-ttu-id="0280d-316">アクセスが Sddl パラメーターの値に基づいて認証される URI を識別します。</span><span class="sxs-lookup"><span data-stu-id="0280d-316">Identifies the URI for which access is authorized based on the value of the Sddl parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-317">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-317">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-318">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-318">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a><span data-ttu-id="0280d-319">URLPrefix \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-319">URLPrefix \<String\></span></span>

<span data-ttu-id="0280d-320">HTTP 要求または HTTPS 要求を受け取る URL 接頭辞。</span><span class="sxs-lookup"><span data-stu-id="0280d-320">A URL prefix on which to accept HTTP or HTTPS requests.</span></span> <span data-ttu-id="0280d-321">これは、文字、、 `[a-z]` `[A-Z]` `[9-0]` 、アンダースコア ( `_` )、および円記号 ( `/` ) のみを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="0280d-321">This is a string containing only the characters `[a-z]`, `[A-Z]`, `[9-0]`, underscore (`_`) and backslash (`/`).</span></span> <span data-ttu-id="0280d-322">文字列の先頭または末尾を円記号 () にすることはできません `/` 。</span><span class="sxs-lookup"><span data-stu-id="0280d-322">The string must not start with or end with a backslash (`/`).</span></span> <span data-ttu-id="0280d-323">たとえば、コンピューター名が "SampleComputer" の場合、WS-Management クライアントは `http://SampleMachine/URLPrefix` 宛先アドレスでを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-323">For example, if the computer name is "SampleComputer", the WS-Management client would specify `http://SampleMachine/URLPrefix` in the destination address.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-324">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-324">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-325">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-325">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a><span data-ttu-id="0280d-326">Value \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-326">Value \<String\></span></span>

<span data-ttu-id="0280d-327">構成オプションを指定するプラグイン固有値である初期化パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-327">Specifies the value of an initialization parameter, which is a plug-in-specific value that is used to specify configuration options.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-328">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-328">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-329">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-329">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a><span data-ttu-id="0280d-330">XMLRenderingType \<String\></span><span class="sxs-lookup"><span data-stu-id="0280d-330">XMLRenderingType \<String\></span></span>

<span data-ttu-id="0280d-331">**WSMAN_DATA** オブジェクトを使用して、XML がプラグインに渡される形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-331">Specifies the format in which XML is passed to plug-ins through the **WSMAN_DATA** object.</span></span> <span data-ttu-id="0280d-332">有効な値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0280d-332">The following are valid values:</span></span>

- <span data-ttu-id="0280d-333">Text: 受信 XML データは **WSMAN_DATA_TYPE_TEXT** 構造体に含まれており、これは Xml を **PCWSTR** メモリバッファーとして表します。</span><span class="sxs-lookup"><span data-stu-id="0280d-333">Text: Incoming XML data is contained in a **WSMAN_DATA_TYPE_TEXT** structure, which represents the XML as a **PCWSTR** memory buffer.</span></span>
- <span data-ttu-id="0280d-334">XMLReader: 受信 XML データは **WSMAN_DATA_TYPE_WS_XML_READER** 構造体に含まれています。これは、Xml を **XmlReader** オブジェクトとして表します。これは、"resource.h" ヘッダーファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="0280d-334">XMLReader: Incoming XML data is contained in a **WSMAN_DATA_TYPE_WS_XML_READER** structure, which represents the XML as an **XmlReader** object, which is defined in the "WebServices.h" header file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="0280d-335">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0280d-335">Cmdlets Supported</span></span>

- [<span data-ttu-id="0280d-336">New-Item</span><span class="sxs-lookup"><span data-stu-id="0280d-336">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="0280d-337">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="0280d-337">Using the pipeline</span></span>

<span data-ttu-id="0280d-338">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0280d-338">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="0280d-339">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0280d-339">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="0280d-340">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0280d-340">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="0280d-341">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="0280d-341">Getting help</span></span>

<span data-ttu-id="0280d-342">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="0280d-342">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="0280d-343">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するには、ファイルシステムドライブで [get-help](xref:Microsoft.PowerShell.Core.Get-Help) コマンドを実行するか、 `-Path` [get-help](xref:Microsoft.PowerShell.Core.Get-Help) のパラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="0280d-343">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a><span data-ttu-id="0280d-344">関連項目</span><span class="sxs-lookup"><span data-stu-id="0280d-344">See also</span></span>

[<span data-ttu-id="0280d-345">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0280d-345">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

