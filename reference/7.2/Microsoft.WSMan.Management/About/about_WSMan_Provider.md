---
description: WSMan
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: WSMan プロバイダー
ms.openlocfilehash: 32baaaec3589fc9d6f4c2319f47d56bca777f738
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600807"
---
# <a name="wsman-provider"></a><span data-ttu-id="87f0e-103">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="87f0e-103">WSMan Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="87f0e-104">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="87f0e-104">Provider name</span></span>

<span data-ttu-id="87f0e-105">WSMan</span><span class="sxs-lookup"><span data-stu-id="87f0e-105">WSMan</span></span>

## <a name="drives"></a><span data-ttu-id="87f0e-106">ドライブ</span><span class="sxs-lookup"><span data-stu-id="87f0e-106">Drives</span></span>

`WSMan:`

## <a name="short-description"></a><span data-ttu-id="87f0e-107">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="87f0e-107">Short description</span></span>

<span data-ttu-id="87f0e-108">Web Services for Management (WS-Management) 構成情報へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-108">Provides access to Web Services for Management (WS-Management) configuration information.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="87f0e-109">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="87f0e-109">Detailed description</span></span>

<span data-ttu-id="87f0e-110">**WSMan** Provider for PowerShell を使用すると、ローカルコンピューターまたはリモートコンピューター上の WS-Management 構成データを追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-110">The **WSMan** provider for PowerShell lets you add, change, clear, and delete WS-Management configuration data on local or remote computers.</span></span>

<span data-ttu-id="87f0e-111">**WSMan** プロバイダーは、WS-Management 構成設定の論理グループに対応するディレクトリ構造を持つ PowerShell ドライブを公開します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-111">The **WSMan** provider exposes a PowerShell drive with a directory structure that corresponds to a logical grouping of WS-Management configuration settings.</span></span> <span data-ttu-id="87f0e-112">これらのグループ化はコンテナーと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-112">These groupings are known as containers.</span></span>

<span data-ttu-id="87f0e-113">Windows PowerShell 3.0 以降では、 **WSMan** プロバイダーが更新され、 **OutputBufferingMode** などのセッション構成の新しいプロパティをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="87f0e-113">Beginning in Windows PowerShell 3.0, the **WSMan** provider has been updated to support new properties for session configurations, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="87f0e-114">セッション構成はドライブのプラグインディレクトリに項目として表示され、 `WSMan:` プロパティは各セッション構成の項目として表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-114">The session configurations appear as items in the Plugin directory of the `WSMan:` drive and the properties appear as items in each session configuration.</span></span>

<span data-ttu-id="87f0e-115">**WSMan** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-115">The **WSMan** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="87f0e-116">Get-Location</span><span class="sxs-lookup"><span data-stu-id="87f0e-116">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="87f0e-117">Set-Location</span><span class="sxs-lookup"><span data-stu-id="87f0e-117">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="87f0e-118">Get-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-118">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="87f0e-119">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="87f0e-119">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="87f0e-120">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-120">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="87f0e-121">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-121">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> <span data-ttu-id="87f0e-122">ドライブのコマンドを使用して、 `WSMan:` 新しいプロパティの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-122">You can use commands in the `WSMan:` drive to change the values of the new properties.</span></span> <span data-ttu-id="87f0e-123">ただし、 `WSMan:` powershell 2.0 のドライブを使用して、Windows powershell 3.0 で導入されたプロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-123">However, you cannot use the `WSMan:` drive in PowerShell 2.0 to change properties that are introduced in Windows PowerShell 3.0.</span></span>
> <span data-ttu-id="87f0e-124">エラーは生成されませんが、これらの設定を変更するためのコマンドは有効ではありません。 Windows PowerShell 3.0 で **WSMan** ドライブを使用します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-124">Although no error is generated, the commands are not effective To change these settings, use the **WSMan** drive in Windows PowerShell 3.0.</span></span>

### <a name="organization-of-the-wsman-drive"></a><span data-ttu-id="87f0e-125">WSMan: ドライブの構成</span><span class="sxs-lookup"><span data-stu-id="87f0e-125">Organization of the WSMan: Drive</span></span>

- <span data-ttu-id="87f0e-126">**クライアント**: WS-Management クライアントのさまざまな面を構成できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-126">**Client**: You can configure various aspects of the WS-Management client.</span></span> <span data-ttu-id="87f0e-127">構成情報はレジストリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-127">The configuration information is stored in the registry.</span></span>

- <span data-ttu-id="87f0e-128">**サービス**: WS-Management サービスのさまざまな側面を構成できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-128">**Service**: You can configure various aspects of the WS-Management service.</span></span>
  <span data-ttu-id="87f0e-129">構成情報はレジストリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-129">The configuration information is stored in the registry.</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-130">サービス構成はサーバー構成と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-130">Service configuration is sometimes referred to as Server configuration.</span></span>

- <span data-ttu-id="87f0e-131">**シェル**: リモートシェルアクセスを許可する設定 (**AllowRemoteShellAccess**) や、許可される同時ユーザーの最大数 (**MaxConcurrentUsers**) など、WS-Management シェルのさまざまな側面を構成できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-131">**Shell**: You can configure various aspects of the WS-Management shell, such as the setting to allow remote shell access (**AllowRemoteShellAccess**) and the maximum number of concurrent users allowed (**MaxConcurrentUsers**).</span></span>

- <span data-ttu-id="87f0e-132">**リスナー**: リスナーを作成して構成できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-132">**Listener**: You can create and configure a listener.</span></span> <span data-ttu-id="87f0e-133">リスナーは WS-Management プロトコルを実装し、メッセージを送受信する管理サービスです。</span><span class="sxs-lookup"><span data-stu-id="87f0e-133">A listener is a management service that implements the WS-Management protocol to send and to receive messages.</span></span>

- <span data-ttu-id="87f0e-134">**プラグイン**: プラグインが読み込まれ、さまざまな機能を提供するために WS-Management サービスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-134">**Plugin**: Plug-ins are loaded and used by the WS-Management service to provide various functions.</span></span> <span data-ttu-id="87f0e-135">既定では、PowerShell には次の3つのプラグインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-135">By default, PowerShell provides three plug-ins:</span></span>
  - <span data-ttu-id="87f0e-136">イベント転送プラグイン。</span><span class="sxs-lookup"><span data-stu-id="87f0e-136">The Event Forwarding plug-in.</span></span>
  - <span data-ttu-id="87f0e-137">Microsoft PowerShell プラグイン。</span><span class="sxs-lookup"><span data-stu-id="87f0e-137">The Microsoft.PowerShell plug-in.</span></span>
  - <span data-ttu-id="87f0e-138">Windows Management Instrumentation (WMI) プロバイダープラグイン。</span><span class="sxs-lookup"><span data-stu-id="87f0e-138">The Windows Management Instrumentation (WMI) Provider plug-in.</span></span>
  <span data-ttu-id="87f0e-139">この3つのプラグインは、イベントの転送、構成、および WMI アクセスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-139">These three plug-ins support event forwarding, configuration, and WMI access.</span></span>

- <span data-ttu-id="87f0e-140">**ClientCertificate**: クライアント証明書を作成して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-140">**ClientCertificate**: You can create and configure a client certificate.</span></span>
  <span data-ttu-id="87f0e-141">証明書認証を使用するように WS-Management クライアントが構成されているとき、クライアント証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-141">A client certificate is used when the WS-Management client is configured to use certificate authentication.</span></span>

### <a name="directory-hierarchy-of-the-wsman-provider"></a><span data-ttu-id="87f0e-142">WSMan プロバイダーのディレクトリ階層</span><span class="sxs-lookup"><span data-stu-id="87f0e-142">Directory Hierarchy of the WSMan Provider</span></span>

<span data-ttu-id="87f0e-143">ローカルコンピューターの WSMan プロバイダーのディレクトリ階層は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87f0e-143">The directory hierarchy of the WSMan provider for the local computer is as follows.</span></span>

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

<span data-ttu-id="87f0e-144">リモート コンピューターの WSMan プロバイダーのディレクトリ階層はローカル コンピューターと同じです。</span><span class="sxs-lookup"><span data-stu-id="87f0e-144">The directory hierarchy of the WSMan provider for a remote computer is the same as a local computer.</span></span> <span data-ttu-id="87f0e-145">ただし、リモート コンピューターの構成設定にアクセスするには、[Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan) を利用し、リモート コンピューターに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-145">However, in order to access the configuration settings of a remote computer, you need to make a connection to the remote computer using [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span> <span data-ttu-id="87f0e-146">リモート コンピューターに接続すると、リモート コンピューターの名前がプロバイダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-146">Once a connection is made to a remote computer, the name of the remote computer shows up in the provider.</span></span>

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a><span data-ttu-id="87f0e-147">WSMan: ドライブの移動</span><span class="sxs-lookup"><span data-stu-id="87f0e-147">Navigating the WSMan: Drive</span></span>

<span data-ttu-id="87f0e-148">このコマンドは、コマンドレットを使用して、 `Set-Location` 現在の場所をドライブに変更し `WSMan:` ます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-148">This command uses the `Set-Location` cmdlet to change the current location to the `WSMan:` drive.</span></span>

```powershell
Set-Location WSMan:
```

<span data-ttu-id="87f0e-149">ファイル システム ドライブに戻るには、ドライブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-149">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="87f0e-150">たとえば、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-150">For example, type.</span></span>

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a><span data-ttu-id="87f0e-151">リモートシステムストアの場所への移動</span><span class="sxs-lookup"><span data-stu-id="87f0e-151">Navigating to a remote system store location</span></span>

<span data-ttu-id="87f0e-152">このコマンドは、コマンドを使用して、 `Set-Location` 現在の場所をリモートシステムストアの場所のルートの場所に変更します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-152">This command uses the `Set-Location` command to change the current location to the root location in the remote system store location.</span></span> <span data-ttu-id="87f0e-153">`\` `/` ドライブのレベルを示すには、円記号またはスラッシュを使用し `WSMan:` ます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-153">Use a backslash `\` or forward slash `/` to indicate a level of the `WSMan:` drive.</span></span>

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="87f0e-154">上記のコマンドでは、リモート システムにすでに接続しているものと仮定しています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-154">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="displaying-the-contents-of-the-wsman-drive"></a><span data-ttu-id="87f0e-155">WSMan: ドライブの内容を表示しています</span><span class="sxs-lookup"><span data-stu-id="87f0e-155">Displaying the Contents of the WSMan: Drive</span></span>

<span data-ttu-id="87f0e-156">このコマンドは、 `Get-Childitem` コマンドレットを使用して、Localhost ストアの場所に WS-Management ストアを表示します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-156">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the Localhost store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\Localhost
```

<span data-ttu-id="87f0e-157">ドライブにいる場合は、 `WSMan:` ドライブ名を省略できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-157">If you are in the `WSMan:` drive, you can omit the drive name.</span></span>

<span data-ttu-id="87f0e-158">このコマンドは、 `Get-Childitem` コマンドレットを使用して、リモートコンピューター "SERVER01" ストアの場所に WS-Management ストアを表示します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-158">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the remote computer "SERVER01" store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="87f0e-159">上記のコマンドでは、リモート システムにすでに接続しているものと仮定しています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-159">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a><span data-ttu-id="87f0e-160">WSMAN: ドライブ内の項目の値を設定する</span><span class="sxs-lookup"><span data-stu-id="87f0e-160">Setting the value of items in the  WSMAN: drive</span></span>

<span data-ttu-id="87f0e-161">`Set-Item`コマンドレットを使用して、ドライブの構成設定を変更でき `WSMAN` ます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-161">You can use the `Set-Item` cmdlet to change configuration settings in the `WSMAN` drive.</span></span> <span data-ttu-id="87f0e-162">次の例では、"contoso.com" というサフィックスが付いたすべてのホストを受け入れるように **TrustedHosts** 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-162">The following example sets the **TrustedHosts** value to accept all hosts with the suffix "contoso.com".</span></span>

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

<span data-ttu-id="87f0e-163">コマンドレットでは、 `Set-Item` `-Concatenate` 値を変更する代わりに値を追加する追加のパラメーターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-163">The `Set-Item` cmdlet supports an additional parameter `-Concatenate` that appends a value instead of changing it.</span></span> <span data-ttu-id="87f0e-164">次の例では、新しい値 "\*. domain2.com" を、に格納されている古い値に追加します。 `TrustedHost:`</span><span class="sxs-lookup"><span data-stu-id="87f0e-164">The following example will append a new value "\*.domain2.com" to the old value stored in `TrustedHost:`</span></span>

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a><span data-ttu-id="87f0e-165">WSMAN: ドライブに項目を作成する</span><span class="sxs-lookup"><span data-stu-id="87f0e-165">Creating items in the WSMAN: drive</span></span>

### <a name="creating-a-new-listener"></a><span data-ttu-id="87f0e-166">新しいリスナーの作成</span><span class="sxs-lookup"><span data-stu-id="87f0e-166">Creating a new listener</span></span>

<span data-ttu-id="87f0e-167">コマンドレットでは、 `New-Item` プロバイダードライブ内に項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-167">The `New-Item` cmdlet creates items within a provider drive.</span></span> <span data-ttu-id="87f0e-168">各プロバイダーには、さまざまな種類のアイテムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-168">Each provider has different item types that you can create.</span></span> <span data-ttu-id="87f0e-169">ドライブでは `WSMAN:` 、リモート要求を受信して応答するように構成する *リスナー* を作成できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-169">In the `WSMAN:` drive, you can create *Listeners* which you configure to receive and respond to remote requests.</span></span> <span data-ttu-id="87f0e-170">次のコマンドは、コマンドレットを使用して新しい HTTP リスナーを作成し `New-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-170">The following command creates a new HTTP listener using the `New-Item` cmdlet.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a><span data-ttu-id="87f0e-171">新しいプラグインの作成</span><span class="sxs-lookup"><span data-stu-id="87f0e-171">Creating a new plug-in</span></span>

<span data-ttu-id="87f0e-172">このコマンドを実行すると、WS-Management サービスのプラグインが作成 (登録) されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-172">This command creates (registers) a plug-in for the WS-Management service.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a><span data-ttu-id="87f0e-173">新しいリソースエントリを作成しています</span><span class="sxs-lookup"><span data-stu-id="87f0e-173">Creating a new resource entry</span></span>

<span data-ttu-id="87f0e-174">このコマンドは、TestPlugin の Resources ディレクトリにリソースエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-174">This command creates a resource entry in the Resources directory of a TestPlugin.</span></span> <span data-ttu-id="87f0e-175">このコマンドは、TestPlugin が個別のコマンドを使用して作成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-175">This command assumes that a TestPlugin has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a><span data-ttu-id="87f0e-176">リソースの新しいセキュリティエントリを作成する</span><span class="sxs-lookup"><span data-stu-id="87f0e-176">Creating a new security entry for a resource</span></span>

<span data-ttu-id="87f0e-177">このコマンドを実行すると、Resource_5967683 (特定のリソース) の Security ディレクトリでセキュリティ エンティティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-177">This command creates a security entry in the Security directory of Resource_5967683 (a specific resource).</span></span> <span data-ttu-id="87f0e-178">このコマンドは、リソースエントリが個別のコマンドを使用して作成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-178">This command assumes that the resource entry has been created using a separate command.</span></span>

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a><span data-ttu-id="87f0e-179">新しいクライアント証明書の作成</span><span class="sxs-lookup"><span data-stu-id="87f0e-179">Creating a new Client Certificate</span></span>

<span data-ttu-id="87f0e-180">このコマンドは、WS-Management クライアントが使用できる **ClientCertificate** エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-180">This command creates **ClientCertificate** entry that can be used by the WS-Management client.</span></span> <span data-ttu-id="87f0e-181">新しい **ClientCertificate** は、 **ClientCertificate** ディレクトリの下に "ClientCertificate_1234567890" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-181">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="87f0e-182">すべてのパラメーターが必須です。</span><span class="sxs-lookup"><span data-stu-id="87f0e-182">All of the parameters are mandatory.</span></span> <span data-ttu-id="87f0e-183">**発行者** は、発行者証明書の拇印である必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-183">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a><span data-ttu-id="87f0e-184">新しい初期化パラメーターの作成</span><span class="sxs-lookup"><span data-stu-id="87f0e-184">Creating a new Initialization Parameter</span></span>

<span data-ttu-id="87f0e-185">このコマンドは、"InitializationParameters" ディレクトリに "testparametername" という名前の初期化パラメーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-185">This command creates an Initialization parameter named "testparametername" in the "InitializationParameters" directory.</span></span> <span data-ttu-id="87f0e-186">このコマンドは、"TestPlugin" が別のコマンドを使用して作成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-186">This command assumes that the "TestPlugin" has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a><span data-ttu-id="87f0e-187">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="87f0e-187">Dynamic parameters</span></span>

<span data-ttu-id="87f0e-188">動的パラメーターは、PowerShell プロバイダーによって追加されるコマンドレットパラメーターであり、プロバイダーに対応したドライブでコマンドレットが使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-188">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="address-string"></a><span data-ttu-id="87f0e-189">アドレス \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-189">Address \<String\></span></span>

<span data-ttu-id="87f0e-190">このリスナーが作成されたアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-190">Specifies the address for which this listener was created.</span></span> <span data-ttu-id="87f0e-191">値は次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-191">The value can be one of the following:</span></span>

- <span data-ttu-id="87f0e-192">リテラル文字列 "\*"。</span><span class="sxs-lookup"><span data-stu-id="87f0e-192">The literal string "\*".</span></span> <span data-ttu-id="87f0e-193">(ワイルドカード文字 () を使用すると、すべての IP アドレスがすべての `*` ネットワークアダプターにバインドされます)。</span><span class="sxs-lookup"><span data-stu-id="87f0e-193">(The wildcard character (`*`) makes the command bind all the IP addresses on all the network adapters.)</span></span>
- <span data-ttu-id="87f0e-194">リテラル文字列 "IP:" の後に、IPv4 のドット区切り10進数形式または IPv6 で複製された16進数形式の有効な IP アドレスが続きます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-194">The literal string "IP:" followed by a valid IP address in either IPv4 dotted-decimal format or in IPv6 cloned-hexadecimal format.</span></span>
- <span data-ttu-id="87f0e-195">リテラル文字列 "MAC:" の後にアダプターの MAC アドレスが続きます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-195">The literal string "MAC:" followed by the MAC address of an adapter.</span></span>
  <span data-ttu-id="87f0e-196">例: MAC:32-a3-58-90-cc。</span><span class="sxs-lookup"><span data-stu-id="87f0e-196">For example: MAC:32-a3-58-90-be-cc.</span></span>

> [!NOTE]
> <span data-ttu-id="87f0e-197">Address 値はリスナーの作成時に設定されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-197">The Address value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-198">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-198">Cmdlets supported</span></span>

- [<span data-ttu-id="87f0e-199">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-199">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a><span data-ttu-id="87f0e-200">Capability \<Enumeration\></span><span class="sxs-lookup"><span data-stu-id="87f0e-200">Capability \<Enumeration\></span></span>

<span data-ttu-id="87f0e-201">*プラグイン* を使用する場合、このパラメーターは、この UNIFORM RESOURCE IDENTIFIER (URI) でサポートされる操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-201">When working with *Plug-ins* this parameter specifies an operation that is supported on this Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="87f0e-202">URI でサポートされる操作の種類ごとに 1 つのエントリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-202">You have to create one entry for each type of operation that the URI supports.</span></span> <span data-ttu-id="87f0e-203">操作でサポートされている場合は、特定の操作に対して有効な属性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-203">You can specify any valid attributes for a given operation, if the operation supports it.</span></span>

<span data-ttu-id="87f0e-204">これらの属性には、 **Supportsfiltering** や **supportsfiltering** などがあります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-204">These attributes include **SupportsFiltering** and **SupportsFragment**.</span></span>

- <span data-ttu-id="87f0e-205">**Create**: 作成操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-205">**Create**: Create operations are supported on the URI.</span></span>
  - <span data-ttu-id="87f0e-206">Create 操作で概念がサポートされている場合は、 **Supportfragment**  属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-206">The **SupportFragment**  attribute is used if the Create operation supports the concept.</span></span>
  - <span data-ttu-id="87f0e-207">**Supportfiltering** 属性は作成操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-207">The **SupportFiltering** attribute is NOT valid for Create operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-208">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-208">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="87f0e-209">**Delete**: delete 操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-209">**Delete**: Delete operations are supported on the URI.</span></span>
  - <span data-ttu-id="87f0e-210">削除操作で概念がサポートされている場合は、 **Supportfragment** 属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-210">The **SupportFragment** attribute is used if the Delete operation supports the concept.</span></span>
  - <span data-ttu-id="87f0e-211">**Supportfiltering** 属性は削除操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-211">The **SupportFiltering** attribute is NOT valid for Delete operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-212">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-212">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="87f0e-213">**列挙**: 列挙操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-213">**Enumerate**: Enumerate operations are supported on the URI.</span></span>
  - <span data-ttu-id="87f0e-214">**Supportfragment** 属性は、列挙操作ではサポートされていません。 False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-214">The **SupportFragment** attribute is NOT supported for Enumerate operations and should be set to False.</span></span>
  - <span data-ttu-id="87f0e-215">**Supportfiltering** 属性は有効で、プラグインがフィルター処理をサポートしている場合は、この属性を "True" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-215">The **SupportFiltering** attribute is valid, and if the plug-in supports filtering, this attribute should be set to "True".</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-216">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-216">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="87f0e-217">**Get**: URI で get 操作がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-217">**Get**: Get operations are supported on the URI.</span></span>
  - <span data-ttu-id="87f0e-218">Get 操作で概念がサポートされている場合は、 **Supportfragment** 属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-218">The **SupportFragment** attribute is used if the Get operation supports the concept.</span></span>
  - <span data-ttu-id="87f0e-219">**Supportfiltering** 属性は Get 操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-219">The **SupportFiltering** attribute is NOT valid for Get operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-220">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-220">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="87f0e-221">**Invoke**: 呼び出し操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-221">**Invoke**: Invoke operations are supported on the URI.</span></span>
  - <span data-ttu-id="87f0e-222">**Supportfragment** 属性は、呼び出し操作ではサポートされていません。 False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-222">The **SupportFragment** attribute is not supported for Invoke operations and should be set to False.</span></span>
  - <span data-ttu-id="87f0e-223">**Supportfiltering** 属性は無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-223">The **SupportFiltering** attribute is not valid and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-224">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-224">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="87f0e-225">**Put**: put 操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-225">**Put**: Put operations are supported on the URI.</span></span>
  - <span data-ttu-id="87f0e-226">Put 操作で概念がサポートされている場合は、 **Supportfragment** 属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-226">The **SupportFragment** attribute is used if the Put operation supports the concept.</span></span>
  - <span data-ttu-id="87f0e-227">**Supportfiltering** 属性は、Put 操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-227">The **SupportFiltering** attribute is not valid for Put operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-228">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-228">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="87f0e-229">**Subscribe**: サブスクライブ操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-229">**Subscribe**: Subscribe operations are supported on the URI.</span></span>
  - <span data-ttu-id="87f0e-230">**Supportfragment** 属性は、サブスクライブ操作ではサポートされていません。 False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-230">The **SupportFragment** attribute is not supported for Subscribe operations and should be set to False.</span></span>
  - <span data-ttu-id="87f0e-231">**Supportfiltering** 属性はサブスクライブ操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-231">The **SupportFiltering** attribute is not valid for Subscribe operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-232">Shell 操作もサポートされている場合、URI に対してこの操作は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-232">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="87f0e-233">**Shell**: シェル操作は URI でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-233">**Shell**: Shell operations are supported on the URI.</span></span>
  - <span data-ttu-id="87f0e-234">**Supportfragment** 属性はシェル操作ではサポートされていないため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-234">The **SupportFragment** attribute is not supported for Shell operations and should be set to "False".</span></span>
  - <span data-ttu-id="87f0e-235">**Supportfiltering** 属性はシェル操作に対して無効であるため、"False" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-235">The **SupportFiltering** attribute is not valid for Shell operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-236">他の操作もサポートされている場合、この操作は URI に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="87f0e-236">This operation is not valid for a URI if ANY other operation is also supported.</span></span>
  > [!NOTE]
  > <span data-ttu-id="87f0e-237">Shell 操作が URI に構成されている場合、Get、Put、Create、Delete、Invoke、Enumerate 操作は WS-Management (WinRM) サービスの内部で処理され、シェルを管理します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-237">If a Shell operation is configured for a URI, Get, Put, Create, Delete, Invoke, and Enumerate operations are processed internally within the WS-Management (WinRM) service to manage shells.</span></span> <span data-ttu-id="87f0e-238">結果として、プラグインは操作を処理できません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-238">As a result, the plug-in cannot handle the operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-239">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-239">Cmdlets supported</span></span>

- [<span data-ttu-id="87f0e-240">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-240">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a><span data-ttu-id="87f0e-241">CertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-241">CertificateThumbprint \<String\></span></span>

<span data-ttu-id="87f0e-242">サービス証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-242">Specifies the thumbprint of the service certificate.</span></span>

<span data-ttu-id="87f0e-243">この値は証明書の拇印フィールドの 2 桁の 16 進数値の文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-243">This value represents the string of two-digit hexadecimal values in the Thumbprint field of the certificate.</span></span> <span data-ttu-id="87f0e-244">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-244">It specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="87f0e-245">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-245">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="87f0e-246">これらの証明書はローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="87f0e-246">They can be mapped only to local user accounts, and they do not work with domain accounts.</span></span> <span data-ttu-id="87f0e-247">証明書の拇印を取得するに `Get-Item` は、PowerShell ドライブのまたはコマンドレットを使用し `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-247">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell `Cert:` drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-248">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-248">Cmdlets supported</span></span>

- [<span data-ttu-id="87f0e-249">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-249">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a><span data-ttu-id="87f0e-250">Enabled \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="87f0e-250">Enabled \<Boolean\></span></span>

<span data-ttu-id="87f0e-251">リスナーが有効であるか、無効であるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-251">Specifies whether the listener is enabled or disabled.</span></span> <span data-ttu-id="87f0e-252">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="87f0e-252">The default is True.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-253">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-253">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-254">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-254">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a><span data-ttu-id="87f0e-255">FileName (Plugin) \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-255">FileName (Plugin) \<String\></span></span>

<span data-ttu-id="87f0e-256">操作プラグインのファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-256">Specifies the file name of the operations plug-in.</span></span> <span data-ttu-id="87f0e-257">このエントリに格納されている環境変数は、要求が受信されると、ユーザーのコンテキストで展開されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-257">Any environment variables that are put in this entry will be expanded in the users' context when a request is received.</span></span> <span data-ttu-id="87f0e-258">各ユーザーは同じ環境変数の異なるバージョンを持つことができるため、各ユーザーが異なるプラグインを持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-258">Because each user could have a different version of the same environment variable, each user could have a different plug-in.</span></span> <span data-ttu-id="87f0e-259">このエントリを空白にすることはできず、有効なプラグインをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-259">This entry cannot be blank and must point to a valid plug-in.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-260">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-260">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-261">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-261">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a><span data-ttu-id="87f0e-262">HostName \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-262">HostName \<String\></span></span>

<span data-ttu-id="87f0e-263">WS-Management (WinRM) サービスが実行されているコンピューターのホスト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-263">Specifies the host name of the computer on which the WS-Management (WinRM) service is running.</span></span>

<span data-ttu-id="87f0e-264">値は完全修飾ドメイン名、IPv4 または IPv6 のリテラル文字列、またはワイルドカード文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-264">The value must be a fully qualified domain name, an IPv4 or IPv6 literal string, or a wildcard character.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-265">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-265">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-266">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-266">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a><span data-ttu-id="87f0e-267">Issuer \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-267">Issuer \<String\></span></span>

<span data-ttu-id="87f0e-268">証明書を発行した証明機関の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-268">Specifies the name of the certification authority that issued the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-269">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-269">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-270">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-270">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a><span data-ttu-id="87f0e-271">プラグイン \<\> WS-Management プラグインはネイティブダイナミックリンクライブラリ (dll) です。</span><span class="sxs-lookup"><span data-stu-id="87f0e-271">Plugin \<\> WS-Management plug-ins are native dynamic link libraries (DLLs)</span></span>

<span data-ttu-id="87f0e-272">これにより、WS-Management の機能に接続して拡張します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-272">that plug in to and extend the functionality of WS-Management .</span></span> <span data-ttu-id="87f0e-273">WSW-Management プラグイン API は、サポートされているリソース Uri と操作に対して特定の Api を実装することによって、ユーザーがプラグインを記述できるようにする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-273">The WSW-Management Plug-in API provides functionality that enables a user to write plug-ins by implementing certain APIs for supported resource URIs and operations.</span></span> <span data-ttu-id="87f0e-274">WS-Management (WinRM) サービスと Internet Information Services (IIS) のいずれかにプラグインを構成すると、WS-Management ホストと IIS ホストにそれぞれプラグインが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-274">After the plug-ins are configured for either the WS-Management (WinRM) service or for Internet Information Services (IIS), the plug-ins are loaded in the WS-Management host or in the IIS host, respectively.</span></span> <span data-ttu-id="87f0e-275">リモート要求はこれらのプラグイン エントリ ポイントに送信され、操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-275">Remote requests are routed to these plug-in entry points to perform operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-276">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-276">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-277">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-277">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a><span data-ttu-id="87f0e-278">Port \<Unsigned Short Integer\></span><span class="sxs-lookup"><span data-stu-id="87f0e-278">Port \<Unsigned Short Integer\></span></span>

<span data-ttu-id="87f0e-279">このリスナーが作成された TCP ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-279">Specifies the TCP port for which this listener is created.</span></span> <span data-ttu-id="87f0e-280">1 から 65535 までの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-280">You can specify any value from 1 through 65535.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-281">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-281">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-282">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-282">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="87f0e-283">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-283">Resource \<String\></span></span>

<span data-ttu-id="87f0e-284">はっきりと識別できる種類の管理操作または値を表すエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-284">Specifies an endpoint that represents a distinct type of management operation or value.</span></span> <span data-ttu-id="87f0e-285">サービスは 1 つまたは複数のリソースを公開します。一部のリソースには複数のインスタンスが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-285">A service exposes one or more resources, and some resources can have more than one instance.</span></span> <span data-ttu-id="87f0e-286">管理リソースは WMI クラスまたはデータベース テーブルに似ています。インスタンスはクラスのインスタンスまたはテーブルの行に似ています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-286">A management resource is similar to a WMI class or to a database table, and an instance is similar to an instance of the class or to a row in the table.</span></span> <span data-ttu-id="87f0e-287">たとえば、 **Win32_LogicalDisk** クラスはリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-287">For example, the **Win32_LogicalDisk** class represents a resource.</span></span> <span data-ttu-id="87f0e-288">`Win32_LogicalDisk="C:\\"` は、リソースの特定のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="87f0e-288">`Win32_LogicalDisk="C:\\"` is a specific instance of the resource.</span></span>

<span data-ttu-id="87f0e-289">Uniform Resource Identifier (URI) にはリソースの接頭辞とパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-289">A Uniform Resource Identifier (URI) contains a prefix and a path to a resource.</span></span>
<span data-ttu-id="87f0e-290">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-290">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-291">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-291">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-292">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-292">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="87f0e-293">Resource \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-293">Resource \<String\></span></span>

<span data-ttu-id="87f0e-294">ディスクまたはプロセスなど、コンピューター上の特定のリソースを識別する Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-294">Specifies the Uniform Resource Identifier (URI) that identifies a specific type of resource, such as a disk or a process, on a computer.</span></span>

<span data-ttu-id="87f0e-295">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-295">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="87f0e-296">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-296">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-297">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-297">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-298">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-298">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a><span data-ttu-id="87f0e-299">SDKVersion \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-299">SDKVersion \<String\></span></span>

<span data-ttu-id="87f0e-300">WS-Management プラグイン SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-300">Specifies the version of the WS-Management plug-in SDK.</span></span> <span data-ttu-id="87f0e-301">唯一の有効な値  です。</span><span class="sxs-lookup"><span data-stu-id="87f0e-301">The only valid value is</span></span>
1.

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-302">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-302">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-303">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-303">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a><span data-ttu-id="87f0e-304">Subject \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-304">Subject \<String\></span></span>

<span data-ttu-id="87f0e-305">証明書で識別されるエンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-305">Specifies the entity that is identified by the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-306">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-306">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-307">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-307">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a><span data-ttu-id="87f0e-308">Transport \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-308">Transport \<String\></span></span>

<span data-ttu-id="87f0e-309">WS-Management プロトコルの要求と応答を送受信するためのトランスポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-309">Specifies the transport to use to send and receive WS-Management protocol requests and responses.</span></span> <span data-ttu-id="87f0e-310">値は HTTP と HTTPS のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-310">The value must be either HTTP or HTTPS.</span></span>

<span data-ttu-id="87f0e-311">注: トランスポート値はリスナーの作成時に設定されます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-311">Note: The Transport value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-312">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-312">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-313">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-313">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a><span data-ttu-id="87f0e-314">URI \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-314">URI \<String\></span></span>

<span data-ttu-id="87f0e-315">アクセスが Sddl パラメーターの値に基づいて認証される URI を識別します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-315">Identifies the URI for which access is authorized based on the value of the Sddl parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-316">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-316">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-317">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-317">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a><span data-ttu-id="87f0e-318">URLPrefix \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-318">URLPrefix \<String\></span></span>

<span data-ttu-id="87f0e-319">HTTP 要求または HTTPS 要求を受け取る URL 接頭辞。</span><span class="sxs-lookup"><span data-stu-id="87f0e-319">A URL prefix on which to accept HTTP or HTTPS requests.</span></span> <span data-ttu-id="87f0e-320">これは、文字、、 `[a-z]` `[A-Z]` `[9-0]` 、アンダースコア ( `_` )、および円記号 ( `/` ) のみを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="87f0e-320">This is a string containing only the characters `[a-z]`, `[A-Z]`, `[9-0]`, underscore (`_`) and backslash (`/`).</span></span> <span data-ttu-id="87f0e-321">文字列の先頭または末尾を円記号 () にすることはできません `/` 。</span><span class="sxs-lookup"><span data-stu-id="87f0e-321">The string must not start with or end with a backslash (`/`).</span></span> <span data-ttu-id="87f0e-322">たとえば、コンピューター名が "SampleComputer" の場合、WS-Management クライアントは `http://SampleMachine/URLPrefix` 宛先アドレスでを指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-322">For example, if the computer name is "SampleComputer", the WS-Management client would specify `http://SampleMachine/URLPrefix` in the destination address.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-323">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-323">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-324">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-324">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a><span data-ttu-id="87f0e-325">Value \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-325">Value \<String\></span></span>

<span data-ttu-id="87f0e-326">構成オプションを指定するプラグイン固有値である初期化パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-326">Specifies the value of an initialization parameter, which is a plug-in-specific value that is used to specify configuration options.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-327">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-327">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-328">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-328">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a><span data-ttu-id="87f0e-329">XMLRenderingType \<String\></span><span class="sxs-lookup"><span data-stu-id="87f0e-329">XMLRenderingType \<String\></span></span>

<span data-ttu-id="87f0e-330">**WSMAN_DATA** オブジェクトを使用して、XML がプラグインに渡される形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-330">Specifies the format in which XML is passed to plug-ins through the **WSMAN_DATA** object.</span></span> <span data-ttu-id="87f0e-331">有効な値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="87f0e-331">The following are valid values:</span></span>

- <span data-ttu-id="87f0e-332">Text: 受信 XML データは **WSMAN_DATA_TYPE_TEXT** 構造体に含まれており、これは Xml を **PCWSTR** メモリバッファーとして表します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-332">Text: Incoming XML data is contained in a **WSMAN_DATA_TYPE_TEXT** structure, which represents the XML as a **PCWSTR** memory buffer.</span></span>
- <span data-ttu-id="87f0e-333">XMLReader: 受信 XML データは **WSMAN_DATA_TYPE_WS_XML_READER** 構造体に含まれています。これは、Xml を **XmlReader** オブジェクトとして表します。これは、"resource.h" ヘッダーファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="87f0e-333">XMLReader: Incoming XML data is contained in a **WSMAN_DATA_TYPE_WS_XML_READER** structure, which represents the XML as an **XmlReader** object, which is defined in the "WebServices.h" header file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="87f0e-334">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87f0e-334">Cmdlets Supported</span></span>

- [<span data-ttu-id="87f0e-335">New-Item</span><span class="sxs-lookup"><span data-stu-id="87f0e-335">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="87f0e-336">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="87f0e-336">Using the pipeline</span></span>

<span data-ttu-id="87f0e-337">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-337">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="87f0e-338">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="87f0e-338">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="87f0e-339">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f0e-339">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="87f0e-340">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="87f0e-340">Getting help</span></span>

<span data-ttu-id="87f0e-341">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-341">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="87f0e-342">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するには、ファイルシステムドライブで [get-help](xref:Microsoft.PowerShell.Core.Get-Help) コマンドを実行するか、 `-Path` [get-help](xref:Microsoft.PowerShell.Core.Get-Help) のパラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="87f0e-342">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a><span data-ttu-id="87f0e-343">関連項目</span><span class="sxs-lookup"><span data-stu-id="87f0e-343">See also</span></span>

[<span data-ttu-id="87f0e-344">about_Providers</span><span class="sxs-lookup"><span data-stu-id="87f0e-344">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

