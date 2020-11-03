---
description: PowerShell プロバイダーが、コマンドラインから簡単にアクセスできないデータおよびコンポーネントへのアクセスを提供する方法について説明します。 データは、ファイルシステムドライブに似た一貫した形式で表示されます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: 952ab618f1e47f0f912209ba56c37a667c596aaf
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222616"
---
# <a name="about-providers"></a><span data-ttu-id="bceec-105">プロバイダーについて</span><span class="sxs-lookup"><span data-stu-id="bceec-105">About Providers</span></span>

## <a name="short-description"></a><span data-ttu-id="bceec-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="bceec-106">Short description</span></span>
<span data-ttu-id="bceec-107">PowerShell プロバイダーが、コマンドラインから簡単にアクセスできないデータおよびコンポーネントへのアクセスを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bceec-107">Describes how PowerShell providers provide access to data and components that wouldn't otherwise be easily accessible at the command line.</span></span>
<span data-ttu-id="bceec-108">データは、ファイルシステムドライブに似た一貫した形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="bceec-108">The data is presented in a consistent format that resembles a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="bceec-109">長い説明</span><span class="sxs-lookup"><span data-stu-id="bceec-109">Long description</span></span>

<span data-ttu-id="bceec-110">PowerShell プロバイダーは、表示と管理を容易にするために特殊なデータストアへのアクセスを提供する .NET プログラムです。</span><span class="sxs-lookup"><span data-stu-id="bceec-110">PowerShell providers are .NET programs that provide access to specialized data stores for easier viewing and management.</span></span> <span data-ttu-id="bceec-111">データはドライブに表示され、ハードディスクドライブの場合と同様に、パス内のデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bceec-111">The data appears in a drive, and you access the data in a path like you would on a hard disk drive.</span></span> <span data-ttu-id="bceec-112">プロバイダーがサポートする組み込みのコマンドレットのいずれかを使用して、プロバイダードライブのデータを管理できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-112">You can use any of the built-in cmdlets that the provider supports to manage the data in the provider drive.</span></span> <span data-ttu-id="bceec-113">また、特にデータ用に設計されたカスタムコマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bceec-113">And, you can use custom cmdlets that are designed especially for the data.</span></span>

<span data-ttu-id="bceec-114">プロバイダーは、組み込みのコマンドレットに動的パラメーターを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="bceec-114">The providers can also add dynamic parameters to the built-in cmdlets.</span></span> <span data-ttu-id="bceec-115">これらのパラメーターは、プロバイダーデータと共にコマンドレットを使用する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-115">These parameters are only available when you use the cmdlet with the provider data.</span></span>

## <a name="built-in-providers"></a><span data-ttu-id="bceec-116">組み込みプロバイダー</span><span class="sxs-lookup"><span data-stu-id="bceec-116">Built-in providers</span></span>

<span data-ttu-id="bceec-117">PowerShell には、さまざまな種類のデータストアにアクセスするために使用できる一連の組み込みプロバイダーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bceec-117">PowerShell includes a set of built-in providers that you can use to access the different types of data stores.</span></span>

| <span data-ttu-id="bceec-118">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="bceec-118">Provider</span></span>   |   <span data-ttu-id="bceec-119">ドライブ (s)</span><span class="sxs-lookup"><span data-stu-id="bceec-119">Drive(s)</span></span>  |<span data-ttu-id="bceec-120">OutputType</span><span class="sxs-lookup"><span data-stu-id="bceec-120">OutputType</span></span>                                                    |
|----------- |------------ |--------------------------------------------------------------|
|<span data-ttu-id="bceec-121">エイリアス</span><span class="sxs-lookup"><span data-stu-id="bceec-121">Alias</span></span>       |<span data-ttu-id="bceec-122">エイリアス:</span><span class="sxs-lookup"><span data-stu-id="bceec-122">Alias:</span></span>       |<span data-ttu-id="bceec-123">システム管理. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="bceec-123">System.Management.Automation.AliasInfo</span></span>                        |
|<span data-ttu-id="bceec-124">Certificate</span><span class="sxs-lookup"><span data-stu-id="bceec-124">Certificate</span></span> |<span data-ttu-id="bceec-125">Cert:</span><span class="sxs-lookup"><span data-stu-id="bceec-125">Cert:</span></span>        |<span data-ttu-id="bceec-126">X509StoreLocation です。</span><span class="sxs-lookup"><span data-stu-id="bceec-126">Microsoft.PowerShell.Commands.X509StoreLocation</span></span>               |
|            |             |<span data-ttu-id="bceec-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="bceec-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>|
|<span data-ttu-id="bceec-128">環境</span><span class="sxs-lookup"><span data-stu-id="bceec-128">Environment</span></span> |<span data-ttu-id="bceec-129">Env:</span><span class="sxs-lookup"><span data-stu-id="bceec-129">Env:</span></span>         |<span data-ttu-id="bceec-130">System.string. DictionaryEntry</span><span class="sxs-lookup"><span data-stu-id="bceec-130">System.Collections.DictionaryEntry</span></span>                            |
|<span data-ttu-id="bceec-131">FileSystem (ファイル システム)</span><span class="sxs-lookup"><span data-stu-id="bceec-131">FileSystem</span></span>  |<span data-ttu-id="bceec-132">C: (\*)</span><span class="sxs-lookup"><span data-stu-id="bceec-132">C: (\*)</span></span>       |<span data-ttu-id="bceec-133">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="bceec-133">System.IO.FileInfo</span></span>                                            |
|            |             |<span data-ttu-id="bceec-134">DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="bceec-134">System.IO.DirectoryInfo</span></span>                                       |
|<span data-ttu-id="bceec-135">機能</span><span class="sxs-lookup"><span data-stu-id="bceec-135">Function</span></span>    |<span data-ttu-id="bceec-136">関数:</span><span class="sxs-lookup"><span data-stu-id="bceec-136">Function:</span></span>    |<span data-ttu-id="bceec-137">システム管理. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="bceec-137">System.Management.Automation.FunctionInfo</span></span>                     |
|<span data-ttu-id="bceec-138">レジストリ</span><span class="sxs-lookup"><span data-stu-id="bceec-138">Registry</span></span>    |<span data-ttu-id="bceec-139">HKLM: HKCU:</span><span class="sxs-lookup"><span data-stu-id="bceec-139">HKLM: HKCU:</span></span>  |<span data-ttu-id="bceec-140">Microsoft Win32. RegistryKey</span><span class="sxs-lookup"><span data-stu-id="bceec-140">Microsoft.Win32.RegistryKey</span></span>                                   |
|<span data-ttu-id="bceec-141">変数</span><span class="sxs-lookup"><span data-stu-id="bceec-141">Variable</span></span>    |<span data-ttu-id="bceec-142">変数:</span><span class="sxs-lookup"><span data-stu-id="bceec-142">Variable:</span></span>    |<span data-ttu-id="bceec-143">システム管理. PSVariable</span><span class="sxs-lookup"><span data-stu-id="bceec-143">System.Management.Automation.PSVariable</span></span>                       |
|<span data-ttu-id="bceec-144">WSMan</span><span class="sxs-lookup"><span data-stu-id="bceec-144">WSMan</span></span>       |<span data-ttu-id="bceec-145">WSMan:</span><span class="sxs-lookup"><span data-stu-id="bceec-145">WSMan:</span></span>       |<span data-ttu-id="bceec-146">WSManConfigContainerElement のようになります。</span><span class="sxs-lookup"><span data-stu-id="bceec-146">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>        |

<span data-ttu-id="bceec-147">(\*)ファイルシステムドライブは、システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bceec-147">(\*) The FileSystem drives vary on each system.</span></span>

<span data-ttu-id="bceec-148">独自の PowerShell プロバイダーを作成することもできます。また、他のユーザーが開発するプロバイダーをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bceec-148">You can also create your own PowerShell providers, and you can install providers that others develop.</span></span> <span data-ttu-id="bceec-149">セッションで使用可能なプロバイダーの一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-149">To list the providers that are available in your session, type:</span></span>

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a><span data-ttu-id="bceec-150">プロバイダーのインストールと削除</span><span class="sxs-lookup"><span data-stu-id="bceec-150">Installing and removing providers</span></span>

<span data-ttu-id="bceec-151">プロバイダーは通常、PowerShell モジュールを使用してインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bceec-151">Providers are typically installed via PowerShell modules.</span></span> <span data-ttu-id="bceec-152">モジュールをインポートすると、プロバイダーがセッションに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="bceec-152">Importing the module loads the provider into your session.</span></span> <span data-ttu-id="bceec-153">組み込みプロバイダーをアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bceec-153">You can't uninstall the built-in providers.</span></span> <span data-ttu-id="bceec-154">他のモジュールによって読み込まれたプロバイダーをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bceec-154">You can uninstall providers loaded by other modules.</span></span>

<span data-ttu-id="bceec-155">コマンドレットを使用して、現在のセッションからプロバイダーをアンロードでき `Remove-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="bceec-155">You can unload a provider from the current session using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="bceec-156">このコマンドレットではプロバイダーはアンインストールされませんが、プロバイダーをセッションで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bceec-156">This cmdlet doesn't uninstall the provider, but it makes the provider unavailable in the session.</span></span>

<span data-ttu-id="bceec-157">また、コマンドレットを使用して、 `Remove-PSDrive` 現在のセッションから任意のドライブを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="bceec-157">You can also use the `Remove-PSDrive` cmdlet to remove any drive from the current session.</span></span> <span data-ttu-id="bceec-158">ドライブ上のこのデータは影響を受けませんが、そのセッションでは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bceec-158">This data on the drive isn't affected, but the drive is no longer available in that session.</span></span>

## <a name="viewing-providers"></a><span data-ttu-id="bceec-159">プロバイダーの表示</span><span class="sxs-lookup"><span data-stu-id="bceec-159">Viewing providers</span></span>

<span data-ttu-id="bceec-160">コンピューター上の PowerShell プロバイダーを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-160">To view the PowerShell providers on your computer, type:</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="bceec-161">出力には、セッションに追加した組み込みプロバイダーとプロバイダーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bceec-161">The output lists the built-in providers and the providers that you added to the session.</span></span>

## <a name="the-provider-cmdlets"></a><span data-ttu-id="bceec-162">プロバイダーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="bceec-162">The provider cmdlets</span></span>

<span data-ttu-id="bceec-163">次のコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bceec-163">The following cmdlets are designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="bceec-164">同じコマンドレットを同じ方法で使用して、プロバイダーが公開するさまざまな種類のデータを管理できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-164">You can use the same cmdlets in the same way to manage the different types of data that providers expose.</span></span> <span data-ttu-id="bceec-165">1つのプロバイダーのデータを管理する方法を学習したら、任意のプロバイダーのデータと同じ手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-165">After you learn to manage the data of one provider, you can use the same procedures with the data from any provider.</span></span>

<span data-ttu-id="bceec-166">たとえば、 `New-Item` コマンドレットは新しい項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="bceec-166">For example, the `New-Item` cmdlet creates a new item.</span></span> <span data-ttu-id="bceec-167">FileSystem プロバイダーでサポートされて `C:` いる **FileSystem** ドライブで、を使用して `New-Item` 新しいファイルまたはフォルダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bceec-167">In the `C:` drive that is supported by the **FileSystem** provider, you can use `New-Item` to create a new file or folder.</span></span> <span data-ttu-id="bceec-168">**レジストリ** プロバイダーでサポートされているドライブで、を使用して `New-Item` 新しいレジストリキーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-168">In the drives that are supported by the **Registry** provider, you can use `New-Item` to create a new registry key.</span></span> <span data-ttu-id="bceec-169">ドライブで `Alias:` 、を使用して `New-Item` 新しいエイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-169">In the `Alias:` drive, you can use `New-Item` to create a new alias.</span></span>

<span data-ttu-id="bceec-170">次のコマンドレットの詳細については、「」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="bceec-170">For detailed information about any of the following cmdlets, type:</span></span>

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a><span data-ttu-id="bceec-171">Get-childitem コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bceec-171">ChildItem cmdlets</span></span>

- [<span data-ttu-id="bceec-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bceec-172">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a><span data-ttu-id="bceec-173">コンテンツのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="bceec-173">Content Cmdlets</span></span>

- [<span data-ttu-id="bceec-174">Add-Content</span><span class="sxs-lookup"><span data-stu-id="bceec-174">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="bceec-175">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="bceec-175">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="bceec-176">Get-Content</span><span class="sxs-lookup"><span data-stu-id="bceec-176">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="bceec-177">Set-Content</span><span class="sxs-lookup"><span data-stu-id="bceec-177">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a><span data-ttu-id="bceec-178">項目のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="bceec-178">Item Cmdlets</span></span>

- [<span data-ttu-id="bceec-179">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="bceec-179">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="bceec-180">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="bceec-180">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="bceec-181">Get-Item</span><span class="sxs-lookup"><span data-stu-id="bceec-181">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="bceec-182">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="bceec-182">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="bceec-183">Move-Item</span><span class="sxs-lookup"><span data-stu-id="bceec-183">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="bceec-184">New-Item</span><span class="sxs-lookup"><span data-stu-id="bceec-184">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="bceec-185">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="bceec-185">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="bceec-186">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="bceec-186">Rename-Item</span></span>](xref:Microsoft.PowerShell.Management.Rename-Item)
- [<span data-ttu-id="bceec-187">Set-Item</span><span class="sxs-lookup"><span data-stu-id="bceec-187">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a><span data-ttu-id="bceec-188">Get-itemproperty コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bceec-188">ItemProperty cmdlets</span></span>

- [<span data-ttu-id="bceec-189">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bceec-189">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="bceec-190">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bceec-190">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [<span data-ttu-id="bceec-191">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bceec-191">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="bceec-192">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bceec-192">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [<span data-ttu-id="bceec-193">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bceec-193">New-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [<span data-ttu-id="bceec-194">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bceec-194">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="bceec-195">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bceec-195">Rename-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [<span data-ttu-id="bceec-196">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bceec-196">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a><span data-ttu-id="bceec-197">Location コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bceec-197">Location cmdlets</span></span>

- [<span data-ttu-id="bceec-198">Get-Location</span><span class="sxs-lookup"><span data-stu-id="bceec-198">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="bceec-199">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="bceec-199">Pop-Location</span></span>](xref:Microsoft.PowerShell.Management.Pop-Location)
- [<span data-ttu-id="bceec-200">Push-Location</span><span class="sxs-lookup"><span data-stu-id="bceec-200">Push-Location</span></span>](xref:Microsoft.PowerShell.Management.Push-Location)
- [<span data-ttu-id="bceec-201">Set-Location</span><span class="sxs-lookup"><span data-stu-id="bceec-201">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a><span data-ttu-id="bceec-202">Path コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bceec-202">Path cmdlets</span></span>

- [<span data-ttu-id="bceec-203">Join-Path</span><span class="sxs-lookup"><span data-stu-id="bceec-203">Join-Path</span></span>](xref:Microsoft.PowerShell.Management.Join-Path)
- [<span data-ttu-id="bceec-204">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="bceec-204">Convert-Path</span></span>](xref:Microsoft.PowerShell.Management.Convert-Path)
- [<span data-ttu-id="bceec-205">Split-Path</span><span class="sxs-lookup"><span data-stu-id="bceec-205">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)
- [<span data-ttu-id="bceec-206">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="bceec-206">Resolve-Path</span></span>](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [<span data-ttu-id="bceec-207">Test-Path</span><span class="sxs-lookup"><span data-stu-id="bceec-207">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a><span data-ttu-id="bceec-208">PSDrive コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bceec-208">PSDrive cmdlets</span></span>

- [<span data-ttu-id="bceec-209">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="bceec-209">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="bceec-210">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="bceec-210">New-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [<span data-ttu-id="bceec-211">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="bceec-211">Remove-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a><span data-ttu-id="bceec-212">PSProvider コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bceec-212">PSProvider Cmdlets</span></span>

- [<span data-ttu-id="bceec-213">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="bceec-213">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a><span data-ttu-id="bceec-214">プロバイダーデータの表示</span><span class="sxs-lookup"><span data-stu-id="bceec-214">Viewing provider data</span></span>

<span data-ttu-id="bceec-215">プロバイダーの主な利点は、使い慣れた一貫性のある方法でデータを公開することです。</span><span class="sxs-lookup"><span data-stu-id="bceec-215">The primary benefit of a provider is that it exposes its data in a familiar and consistent way.</span></span> <span data-ttu-id="bceec-216">データ表現のモデルは、ファイルシステムドライブです。</span><span class="sxs-lookup"><span data-stu-id="bceec-216">The model for data presentation is a file system drive.</span></span>

<span data-ttu-id="bceec-217">プロバイダーを使用すると、ファイルシステム内のデータであるかのように、データストア内の項目を表示、移動、および変更できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-217">The provider allows you to view, navigate, and change items in the data store as though they were data in a file system.</span></span> <span data-ttu-id="bceec-218">データストアは、サポートしているドライブの名前によってアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="bceec-218">The data store is accessed by the name of the drive that it supports.</span></span>

<span data-ttu-id="bceec-219">このドライブはコマンドレットの既定の表示で表示され `Get-PSProvider` ますが、コマンドレットを使用してプロバイダーのドライブに関する情報を取得でき `Get-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="bceec-219">The drive is listed in the default display of the `Get-PSProvider` cmdlet, but you can get information about the provider drive using the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="bceec-220">たとえば、Function: ドライブのすべてのプロパティを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-220">For example, to get all the properties of the Function: drive, type:</span></span>

```powershell
Get-PSDrive Function | Format-List *
```

<span data-ttu-id="bceec-221">ファイルシステムドライブの場合と同様に、プロバイダードライブのデータを表示したり、移動したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bceec-221">You can view and move through the data in a provider drive just as you would on a file system drive.</span></span>

<span data-ttu-id="bceec-222">プロバイダードライブの内容を表示するには、Get-Item または Get-ChildItem コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bceec-222">To view the contents of a provider drive, use the Get-Item or Get-ChildItem cmdlets.</span></span> <span data-ttu-id="bceec-223">ドライブ名の後にコロン (:) を入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-223">Type the drive name followed by a colon (:).</span></span> <span data-ttu-id="bceec-224">たとえば、Alias: ドライブの内容を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-224">For example, to view the contents of the Alias: drive, type:</span></span>

```powershell
Get-Item alias:
```

<span data-ttu-id="bceec-225">パスにドライブ名を含めることで、別のドライブのデータを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-225">You can view and manage the data in any drive from another drive by including the drive name in the path.</span></span> <span data-ttu-id="bceec-226">たとえば、別のドライブの HKLM: ドライブの、Hklm\software レジストリキーを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-226">For example, to view the HKLM\Software registry key in the HKLM: drive from another drive, type:</span></span>

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

<span data-ttu-id="bceec-227">ドライブを開くには、Set-Location コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bceec-227">To open the drive, use the Set-Location cmdlet.</span></span> <span data-ttu-id="bceec-228">ドライブパスを指定するときは、コロンを忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="bceec-228">Remember the colon when you specify the drive path.</span></span> <span data-ttu-id="bceec-229">たとえば、場所を Cert: ドライブのルートディレクトリに変更するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-229">For example, to change your location to the root directory of the Cert: drive, type:</span></span>

```powershell
Set-Location cert:
```

<span data-ttu-id="bceec-230">次に、Cert: ドライブの内容を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-230">Then, to view the contents of the Cert: drive, type:</span></span>

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a><span data-ttu-id="bceec-231">階層データの移動</span><span class="sxs-lookup"><span data-stu-id="bceec-231">Moving through hierarchical data</span></span>

<span data-ttu-id="bceec-232">ハードディスクドライブの場合と同様に、プロバイダードライブ間を移動することができます。</span><span class="sxs-lookup"><span data-stu-id="bceec-232">You can move through a provider drive just as you would a hard disk drive.</span></span>
<span data-ttu-id="bceec-233">項目内の項目の階層にデータが配置されている場合は、円記号 () を使用して `\` 子項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="bceec-233">If the data is arranged in a hierarchy of items within items, use a backslash (`\`) to indicate a child item.</span></span> <span data-ttu-id="bceec-234">次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="bceec-234">Use the following format:</span></span>

```
drive:\location\child-location\...
```

<span data-ttu-id="bceec-235">たとえば、場所を、Hklm\software レジストリキーに変更するには、次のように Set-Location コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-235">For example, to change your location to the HKLM\Software registry key, type a Set-Location command, such as:</span></span>

```powershell
Set-Location HKLM:\SOFTWARE\
```

<span data-ttu-id="bceec-236">完全修飾名の要素にスペースが含まれている場合は、名前を二重引用符 () で囲む必要があり `"` ます。</span><span class="sxs-lookup"><span data-stu-id="bceec-236">If any element in the fully qualified name includes spaces, you must enclose the name in double-quotation marks (`"`).</span></span> <span data-ttu-id="bceec-237">次の例は、スペースを含む完全修飾パスを示しています。</span><span class="sxs-lookup"><span data-stu-id="bceec-237">The following example shows a fully qualified path that includes spaces.</span></span>

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

<span data-ttu-id="bceec-238">また、相対参照を使用して場所を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="bceec-238">You can also use relative references to locations.</span></span> <span data-ttu-id="bceec-239">ドット () は、 `.` 現在の場所を表します。</span><span class="sxs-lookup"><span data-stu-id="bceec-239">A dot (`.`) represents the current location.</span></span> <span data-ttu-id="bceec-240">たとえば、 `HKLM:\Software\Microsoft` レジストリキーを使用していて、キーのレジストリサブキーを一覧表示する場合は、 `HKLM:\Software\Microsoft\PowerShell` 次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="bceec-240">For example, if you are in the `HKLM:\Software\Microsoft` registry key, and you want to list the registry subkeys in the `HKLM:\Software\Microsoft\PowerShell` key, type the following command:</span></span>

```powershell
Get-ChildItem .\PowerShell
```

<span data-ttu-id="bceec-241">また、二重ドット () は、 `..` 現在の場所のすぐ上にあるディレクトリまたはコンテナーを参照します。</span><span class="sxs-lookup"><span data-stu-id="bceec-241">Also, double-dots (`..`) refers to the directory or container directly above your current location.</span></span> <span data-ttu-id="bceec-242">2つのドット ( `..` ) を使用して、プロバイダー階層内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-242">You can use double-dots (`..`) to navigate through a provider hierarchy.</span></span>

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a><span data-ttu-id="bceec-243">プロバイダーホーム</span><span class="sxs-lookup"><span data-stu-id="bceec-243">Provider Home</span></span>

<span data-ttu-id="bceec-244">また、プロバイダーには **ホーム** の場所もあります。</span><span class="sxs-lookup"><span data-stu-id="bceec-244">Providers also have a **Home** location.</span></span>  <span data-ttu-id="bceec-245">この場所は、プロバイダーによってサポートされるすべてので共有され `PSDrives` ます。</span><span class="sxs-lookup"><span data-stu-id="bceec-245">This location is shared by all `PSDrives` backed by the provider.</span></span> <span data-ttu-id="bceec-246">プロバイダーの **Home** プロパティを表示することによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-246">It can be retrieved by viewing the **Home** property of the provider.</span></span>

```powershell
Get-PSProvider | Format-Table Name, Home
```

```Output
Name        Home
----        ----
Registry
Alias
Environment
FileSystem  C:\Users\username
Function
Variable
Certificate
```

<span data-ttu-id="bceec-247">**FileSystem** プロバイダーは、 **Home** の既定値を持つ唯一のプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="bceec-247">The **FileSystem** provider is the only provider that has a default value for **Home**.</span></span> <span data-ttu-id="bceec-248">と同じ値 `$Home` です。</span><span class="sxs-lookup"><span data-stu-id="bceec-248">It's the same value as `$Home`.</span></span> <span data-ttu-id="bceec-249">詳細については、「 [about_Automatic_Variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bceec-249">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="bceec-250">現在のセッションでは、そのプロパティを使用して、プロバイダーの **ホーム** ディレクトリを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-250">You can set the **Home** directory for a provider, for the current session, using its property.</span></span>

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

<span data-ttu-id="bceec-251">この `~` 文字は、プロバイダーのホームディレクトリを表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-251">The `~` character can be used to represent the provider's home directory.</span></span>
<span data-ttu-id="bceec-252">プロバイダーに **ホーム** の場所が設定されていない場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bceec-252">If the provider doesn't have a **Home** location set, you see an error.</span></span>

```powershell
Cert:\> Set-Location ~
```

```Output
Set-Location : Home location for this provider isn't set. To set the home
location, call "(get-psprovider 'Certificate').Home = 'path'".
At line:1 char:1
+ Set-Location ~
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Set-Location],
                              PSInvalidOperationException
...
```

## <a name="finding-dynamic-parameters"></a><span data-ttu-id="bceec-253">動的パラメーターの検索</span><span class="sxs-lookup"><span data-stu-id="bceec-253">Finding dynamic parameters</span></span>

<span data-ttu-id="bceec-254">動的パラメーターは、プロバイダーによってコマンドレットに追加されるコマンドレットパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="bceec-254">Dynamic parameters are cmdlet parameters that are added to a cmdlet by a provider.</span></span> <span data-ttu-id="bceec-255">これらのパラメーターは、コマンドレットを追加したプロバイダーと共に使用する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bceec-255">These parameters are available only when the cmdlet is used with the provider that added them.</span></span>

<span data-ttu-id="bceec-256">たとえば、ドライブは、 `Cert:` およびコマンドレットに **Codesigningcert** パラメーターを追加し `Get-Item` `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="bceec-256">For example, the `Cert:` drive adds the **CodeSigningCert** parameter to the `Get-Item` and `Get-ChildItem` cmdlets.</span></span> <span data-ttu-id="bceec-257">このパラメーターは `Get-Item` 、ドライブでまたはを使用する場合にのみ使用でき `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="bceec-257">You can use this parameter only when you use `Get-Item` or `Get-ChildItem` in the `Cert:` drive.</span></span>

<span data-ttu-id="bceec-258">プロバイダーがサポートする動的パラメーターの一覧については、プロバイダーのヘルプファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bceec-258">For a list of the dynamic parameters that a provider supports, see the Help file for the provider.</span></span> <span data-ttu-id="bceec-259">型:</span><span class="sxs-lookup"><span data-stu-id="bceec-259">Type:</span></span>

```
Get-Help <provider-name>
```

<span data-ttu-id="bceec-260">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bceec-260">For example:</span></span>

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a><span data-ttu-id="bceec-261">プロバイダーについて学習する</span><span class="sxs-lookup"><span data-stu-id="bceec-261">Learning about providers</span></span>

<span data-ttu-id="bceec-262">すべてのプロバイダーデータはドライブに表示されますが、同じメソッドを使用して移動すると、類似性が停止します。</span><span class="sxs-lookup"><span data-stu-id="bceec-262">Although all provider data appears in drives and you use the same methods to move through them, the similarity stops there.</span></span> <span data-ttu-id="bceec-263">プロバイダーによって公開されるデータストアは、Active Directory の場所や Microsoft Exchange Server のメールボックスと同じように変化することがあります。</span><span class="sxs-lookup"><span data-stu-id="bceec-263">The data stores that the provider exposes can be as varied as Active Directory locations and Microsoft Exchange Server mailboxes.</span></span>

<span data-ttu-id="bceec-264">個々の PowerShell プロバイダーの詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="bceec-264">For information about individual PowerShell providers, type:</span></span>

```
Get-Help <ProviderName>
```

<span data-ttu-id="bceec-265">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bceec-265">For example:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="bceec-266">プロバイダーに関するヘルプトピックの一覧を表示するには、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="bceec-266">For a list of Help topics about the providers, type:</span></span>

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a><span data-ttu-id="bceec-267">関連項目</span><span class="sxs-lookup"><span data-stu-id="bceec-267">See also</span></span>

[<span data-ttu-id="bceec-268">about_Locations</span><span class="sxs-lookup"><span data-stu-id="bceec-268">about_Locations</span></span>](about_Locations.md)

[<span data-ttu-id="bceec-269">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="bceec-269">about_Path_Syntax</span></span>](about_Path_Syntax.md)
