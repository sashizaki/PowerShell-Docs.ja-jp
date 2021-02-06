---
description: PowerShell プロバイダーが、コマンドラインから簡単にアクセスできないデータおよびコンポーネントへのアクセスを提供する方法について説明します。 データは、ファイルシステムドライブに似た一貫した形式で表示されます。
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: 6073ef13a6d0a02cded69073d7ffaef903a807ea
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600985"
---
# <a name="about-providers"></a><span data-ttu-id="1efc6-104">プロバイダーについて</span><span class="sxs-lookup"><span data-stu-id="1efc6-104">About Providers</span></span>

## <a name="short-description"></a><span data-ttu-id="1efc6-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="1efc6-105">Short description</span></span>
<span data-ttu-id="1efc6-106">PowerShell プロバイダーが、コマンドラインから簡単にアクセスできないデータおよびコンポーネントへのアクセスを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-106">Describes how PowerShell providers provide access to data and components that wouldn't otherwise be easily accessible at the command line.</span></span>
<span data-ttu-id="1efc6-107">データは、ファイルシステムドライブに似た一貫した形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-107">The data is presented in a consistent format that resembles a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="1efc6-108">長い説明</span><span class="sxs-lookup"><span data-stu-id="1efc6-108">Long description</span></span>

<span data-ttu-id="1efc6-109">PowerShell プロバイダーは、表示と管理を容易にするために特殊なデータストアへのアクセスを提供する .NET プログラムです。</span><span class="sxs-lookup"><span data-stu-id="1efc6-109">PowerShell providers are .NET programs that provide access to specialized data stores for easier viewing and management.</span></span> <span data-ttu-id="1efc6-110">データはドライブに表示され、ハードディスクドライブの場合と同様に、パス内のデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1efc6-110">The data appears in a drive, and you access the data in a path like you would on a hard disk drive.</span></span> <span data-ttu-id="1efc6-111">プロバイダーがサポートする組み込みのコマンドレットのいずれかを使用して、プロバイダードライブのデータを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-111">You can use any of the built-in cmdlets that the provider supports to manage the data in the provider drive.</span></span> <span data-ttu-id="1efc6-112">また、特にデータ用に設計されたカスタムコマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-112">And, you can use custom cmdlets that are designed especially for the data.</span></span>

<span data-ttu-id="1efc6-113">プロバイダーは、組み込みのコマンドレットに動的パラメーターを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-113">The providers can also add dynamic parameters to the built-in cmdlets.</span></span> <span data-ttu-id="1efc6-114">これらのパラメーターは、プロバイダーデータと共にコマンドレットを使用する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-114">These parameters are only available when you use the cmdlet with the provider data.</span></span>

## <a name="built-in-providers"></a><span data-ttu-id="1efc6-115">組み込みプロバイダー</span><span class="sxs-lookup"><span data-stu-id="1efc6-115">Built-in providers</span></span>

<span data-ttu-id="1efc6-116">PowerShell には、さまざまな種類のデータストアにアクセスするために使用できる一連の組み込みプロバイダーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1efc6-116">PowerShell includes a set of built-in providers that you can use to access the different types of data stores.</span></span>

| <span data-ttu-id="1efc6-117">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="1efc6-117">Provider</span></span>   |   <span data-ttu-id="1efc6-118">ドライブ (s)</span><span class="sxs-lookup"><span data-stu-id="1efc6-118">Drive(s)</span></span>  |<span data-ttu-id="1efc6-119">OutputType</span><span class="sxs-lookup"><span data-stu-id="1efc6-119">OutputType</span></span>                                                    |
|----------- |------------ |--------------------------------------------------------------|
|<span data-ttu-id="1efc6-120">エイリアス</span><span class="sxs-lookup"><span data-stu-id="1efc6-120">Alias</span></span>       |<span data-ttu-id="1efc6-121">エイリアス:</span><span class="sxs-lookup"><span data-stu-id="1efc6-121">Alias:</span></span>       |<span data-ttu-id="1efc6-122">システム管理. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="1efc6-122">System.Management.Automation.AliasInfo</span></span>                        |
|<span data-ttu-id="1efc6-123">Certificate</span><span class="sxs-lookup"><span data-stu-id="1efc6-123">Certificate</span></span> |<span data-ttu-id="1efc6-124">Cert:</span><span class="sxs-lookup"><span data-stu-id="1efc6-124">Cert:</span></span>        |<span data-ttu-id="1efc6-125">X509StoreLocation です。</span><span class="sxs-lookup"><span data-stu-id="1efc6-125">Microsoft.PowerShell.Commands.X509StoreLocation</span></span>               |
|            |             |<span data-ttu-id="1efc6-126">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="1efc6-126">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>|
|<span data-ttu-id="1efc6-127">環境</span><span class="sxs-lookup"><span data-stu-id="1efc6-127">Environment</span></span> |<span data-ttu-id="1efc6-128">Env:</span><span class="sxs-lookup"><span data-stu-id="1efc6-128">Env:</span></span>         |<span data-ttu-id="1efc6-129">System.string. DictionaryEntry</span><span class="sxs-lookup"><span data-stu-id="1efc6-129">System.Collections.DictionaryEntry</span></span>                            |
|<span data-ttu-id="1efc6-130">FileSystem (ファイル システム)</span><span class="sxs-lookup"><span data-stu-id="1efc6-130">FileSystem</span></span>  |<span data-ttu-id="1efc6-131">C: (\*)</span><span class="sxs-lookup"><span data-stu-id="1efc6-131">C: (\*)</span></span>       |<span data-ttu-id="1efc6-132">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="1efc6-132">System.IO.FileInfo</span></span>                                            |
|            |             |<span data-ttu-id="1efc6-133">DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="1efc6-133">System.IO.DirectoryInfo</span></span>                                       |
|<span data-ttu-id="1efc6-134">Function</span><span class="sxs-lookup"><span data-stu-id="1efc6-134">Function</span></span>    |<span data-ttu-id="1efc6-135">関数:</span><span class="sxs-lookup"><span data-stu-id="1efc6-135">Function:</span></span>    |<span data-ttu-id="1efc6-136">システム管理. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="1efc6-136">System.Management.Automation.FunctionInfo</span></span>                     |
|<span data-ttu-id="1efc6-137">レジストリ</span><span class="sxs-lookup"><span data-stu-id="1efc6-137">Registry</span></span>    |<span data-ttu-id="1efc6-138">HKLM: HKCU:</span><span class="sxs-lookup"><span data-stu-id="1efc6-138">HKLM: HKCU:</span></span>  |<span data-ttu-id="1efc6-139">Microsoft Win32. RegistryKey</span><span class="sxs-lookup"><span data-stu-id="1efc6-139">Microsoft.Win32.RegistryKey</span></span>                                   |
|<span data-ttu-id="1efc6-140">変数</span><span class="sxs-lookup"><span data-stu-id="1efc6-140">Variable</span></span>    |<span data-ttu-id="1efc6-141">変数:</span><span class="sxs-lookup"><span data-stu-id="1efc6-141">Variable:</span></span>    |<span data-ttu-id="1efc6-142">システム管理. PSVariable</span><span class="sxs-lookup"><span data-stu-id="1efc6-142">System.Management.Automation.PSVariable</span></span>                       |
|<span data-ttu-id="1efc6-143">WSMan</span><span class="sxs-lookup"><span data-stu-id="1efc6-143">WSMan</span></span>       |<span data-ttu-id="1efc6-144">WSMan:</span><span class="sxs-lookup"><span data-stu-id="1efc6-144">WSMan:</span></span>       |<span data-ttu-id="1efc6-145">WSManConfigContainerElement のようになります。</span><span class="sxs-lookup"><span data-stu-id="1efc6-145">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>        |

<span data-ttu-id="1efc6-146">(\*)ファイルシステムドライブは、システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1efc6-146">(\*) The FileSystem drives vary on each system.</span></span>

<span data-ttu-id="1efc6-147">独自の PowerShell プロバイダーを作成することもできます。また、他のユーザーが開発するプロバイダーをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-147">You can also create your own PowerShell providers, and you can install providers that others develop.</span></span> <span data-ttu-id="1efc6-148">セッションで使用可能なプロバイダーの一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-148">To list the providers that are available in your session, type:</span></span>

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a><span data-ttu-id="1efc6-149">プロバイダーのインストールと削除</span><span class="sxs-lookup"><span data-stu-id="1efc6-149">Installing and removing providers</span></span>

<span data-ttu-id="1efc6-150">プロバイダーは通常、PowerShell モジュールを使用してインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-150">Providers are typically installed via PowerShell modules.</span></span> <span data-ttu-id="1efc6-151">モジュールをインポートすると、プロバイダーがセッションに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-151">Importing the module loads the provider into your session.</span></span> <span data-ttu-id="1efc6-152">組み込みプロバイダーをアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1efc6-152">You can't uninstall the built-in providers.</span></span> <span data-ttu-id="1efc6-153">他のモジュールによって読み込まれたプロバイダーをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-153">You can uninstall providers loaded by other modules.</span></span>

<span data-ttu-id="1efc6-154">コマンドレットを使用して、現在のセッションからプロバイダーをアンロードでき `Remove-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-154">You can unload a provider from the current session using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="1efc6-155">このコマンドレットではプロバイダーはアンインストールされませんが、プロバイダーをセッションで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1efc6-155">This cmdlet doesn't uninstall the provider, but it makes the provider unavailable in the session.</span></span>

<span data-ttu-id="1efc6-156">また、コマンドレットを使用して、 `Remove-PSDrive` 現在のセッションから任意のドライブを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-156">You can also use the `Remove-PSDrive` cmdlet to remove any drive from the current session.</span></span> <span data-ttu-id="1efc6-157">ドライブ上のこのデータは影響を受けませんが、そのセッションでは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1efc6-157">This data on the drive isn't affected, but the drive is no longer available in that session.</span></span>

## <a name="viewing-providers"></a><span data-ttu-id="1efc6-158">プロバイダーの表示</span><span class="sxs-lookup"><span data-stu-id="1efc6-158">Viewing providers</span></span>

<span data-ttu-id="1efc6-159">コンピューター上の PowerShell プロバイダーを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-159">To view the PowerShell providers on your computer, type:</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="1efc6-160">出力には、セッションに追加した組み込みプロバイダーとプロバイダーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-160">The output lists the built-in providers and the providers that you added to the session.</span></span>

## <a name="the-provider-cmdlets"></a><span data-ttu-id="1efc6-161">プロバイダーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="1efc6-161">The provider cmdlets</span></span>

<span data-ttu-id="1efc6-162">次のコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="1efc6-162">The following cmdlets are designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="1efc6-163">同じコマンドレットを同じ方法で使用して、プロバイダーが公開するさまざまな種類のデータを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-163">You can use the same cmdlets in the same way to manage the different types of data that providers expose.</span></span> <span data-ttu-id="1efc6-164">1つのプロバイダーのデータを管理する方法を学習したら、任意のプロバイダーのデータと同じ手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-164">After you learn to manage the data of one provider, you can use the same procedures with the data from any provider.</span></span>

<span data-ttu-id="1efc6-165">たとえば、 `New-Item` コマンドレットは新しい項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-165">For example, the `New-Item` cmdlet creates a new item.</span></span> <span data-ttu-id="1efc6-166">FileSystem プロバイダーでサポートされて `C:` いるドライブで、を使用して `New-Item` 新しいファイルまたはフォルダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-166">In the `C:` drive that is supported by the **FileSystem** provider, you can use `New-Item` to create a new file or folder.</span></span> <span data-ttu-id="1efc6-167">**レジストリ** プロバイダーでサポートされているドライブで、を使用して `New-Item` 新しいレジストリキーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-167">In the drives that are supported by the **Registry** provider, you can use `New-Item` to create a new registry key.</span></span> <span data-ttu-id="1efc6-168">ドライブで `Alias:` 、を使用して `New-Item` 新しいエイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-168">In the `Alias:` drive, you can use `New-Item` to create a new alias.</span></span>

<span data-ttu-id="1efc6-169">次のコマンドレットの詳細については、「」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="1efc6-169">For detailed information about any of the following cmdlets, type:</span></span>

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a><span data-ttu-id="1efc6-170">Get-childitem コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1efc6-170">ChildItem cmdlets</span></span>

- [<span data-ttu-id="1efc6-171">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1efc6-171">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a><span data-ttu-id="1efc6-172">コンテンツのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="1efc6-172">Content Cmdlets</span></span>

- [<span data-ttu-id="1efc6-173">Add-Content</span><span class="sxs-lookup"><span data-stu-id="1efc6-173">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="1efc6-174">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="1efc6-174">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="1efc6-175">Get-Content</span><span class="sxs-lookup"><span data-stu-id="1efc6-175">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="1efc6-176">Set-Content</span><span class="sxs-lookup"><span data-stu-id="1efc6-176">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a><span data-ttu-id="1efc6-177">項目のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="1efc6-177">Item Cmdlets</span></span>

- [<span data-ttu-id="1efc6-178">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="1efc6-178">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="1efc6-179">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="1efc6-179">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="1efc6-180">Get-Item</span><span class="sxs-lookup"><span data-stu-id="1efc6-180">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="1efc6-181">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="1efc6-181">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="1efc6-182">Move-Item</span><span class="sxs-lookup"><span data-stu-id="1efc6-182">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="1efc6-183">New-Item</span><span class="sxs-lookup"><span data-stu-id="1efc6-183">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="1efc6-184">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="1efc6-184">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="1efc6-185">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="1efc6-185">Rename-Item</span></span>](xref:Microsoft.PowerShell.Management.Rename-Item)
- [<span data-ttu-id="1efc6-186">Set-Item</span><span class="sxs-lookup"><span data-stu-id="1efc6-186">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a><span data-ttu-id="1efc6-187">Get-itemproperty コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1efc6-187">ItemProperty cmdlets</span></span>

- [<span data-ttu-id="1efc6-188">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1efc6-188">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="1efc6-189">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1efc6-189">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [<span data-ttu-id="1efc6-190">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1efc6-190">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="1efc6-191">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1efc6-191">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [<span data-ttu-id="1efc6-192">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1efc6-192">New-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [<span data-ttu-id="1efc6-193">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1efc6-193">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="1efc6-194">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1efc6-194">Rename-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [<span data-ttu-id="1efc6-195">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1efc6-195">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a><span data-ttu-id="1efc6-196">Location コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1efc6-196">Location cmdlets</span></span>

- [<span data-ttu-id="1efc6-197">Get-Location</span><span class="sxs-lookup"><span data-stu-id="1efc6-197">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="1efc6-198">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="1efc6-198">Pop-Location</span></span>](xref:Microsoft.PowerShell.Management.Pop-Location)
- [<span data-ttu-id="1efc6-199">Push-Location</span><span class="sxs-lookup"><span data-stu-id="1efc6-199">Push-Location</span></span>](xref:Microsoft.PowerShell.Management.Push-Location)
- [<span data-ttu-id="1efc6-200">Set-Location</span><span class="sxs-lookup"><span data-stu-id="1efc6-200">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a><span data-ttu-id="1efc6-201">Path コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1efc6-201">Path cmdlets</span></span>

- [<span data-ttu-id="1efc6-202">Join-Path</span><span class="sxs-lookup"><span data-stu-id="1efc6-202">Join-Path</span></span>](xref:Microsoft.PowerShell.Management.Join-Path)
- [<span data-ttu-id="1efc6-203">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="1efc6-203">Convert-Path</span></span>](xref:Microsoft.PowerShell.Management.Convert-Path)
- [<span data-ttu-id="1efc6-204">Split-Path</span><span class="sxs-lookup"><span data-stu-id="1efc6-204">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)
- [<span data-ttu-id="1efc6-205">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="1efc6-205">Resolve-Path</span></span>](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [<span data-ttu-id="1efc6-206">Test-Path</span><span class="sxs-lookup"><span data-stu-id="1efc6-206">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a><span data-ttu-id="1efc6-207">PSDrive コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1efc6-207">PSDrive cmdlets</span></span>

- [<span data-ttu-id="1efc6-208">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1efc6-208">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="1efc6-209">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1efc6-209">New-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [<span data-ttu-id="1efc6-210">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1efc6-210">Remove-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a><span data-ttu-id="1efc6-211">PSProvider コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1efc6-211">PSProvider Cmdlets</span></span>

- [<span data-ttu-id="1efc6-212">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="1efc6-212">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a><span data-ttu-id="1efc6-213">プロバイダーデータの表示</span><span class="sxs-lookup"><span data-stu-id="1efc6-213">Viewing provider data</span></span>

<span data-ttu-id="1efc6-214">プロバイダーの主な利点は、使い慣れた一貫性のある方法でデータを公開することです。</span><span class="sxs-lookup"><span data-stu-id="1efc6-214">The primary benefit of a provider is that it exposes its data in a familiar and consistent way.</span></span> <span data-ttu-id="1efc6-215">データ表現のモデルは、ファイルシステムドライブです。</span><span class="sxs-lookup"><span data-stu-id="1efc6-215">The model for data presentation is a file system drive.</span></span>

<span data-ttu-id="1efc6-216">プロバイダーを使用すると、ファイルシステム内のデータであるかのように、データストア内の項目を表示、移動、および変更できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-216">The provider allows you to view, navigate, and change items in the data store as though they were data in a file system.</span></span> <span data-ttu-id="1efc6-217">データストアは、サポートしているドライブの名前によってアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-217">The data store is accessed by the name of the drive that it supports.</span></span>

<span data-ttu-id="1efc6-218">このドライブはコマンドレットの既定の表示で表示され `Get-PSProvider` ますが、コマンドレットを使用してプロバイダーのドライブに関する情報を取得でき `Get-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-218">The drive is listed in the default display of the `Get-PSProvider` cmdlet, but you can get information about the provider drive using the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="1efc6-219">たとえば、Function: ドライブのすべてのプロパティを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-219">For example, to get all the properties of the Function: drive, type:</span></span>

```powershell
Get-PSDrive Function | Format-List *
```

<span data-ttu-id="1efc6-220">ファイルシステムドライブの場合と同様に、プロバイダードライブのデータを表示したり、移動したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-220">You can view and move through the data in a provider drive just as you would on a file system drive.</span></span>

<span data-ttu-id="1efc6-221">プロバイダードライブの内容を表示するには、Get-Item または Get-ChildItem コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-221">To view the contents of a provider drive, use the Get-Item or Get-ChildItem cmdlets.</span></span> <span data-ttu-id="1efc6-222">ドライブ名の後にコロン (:) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-222">Type the drive name followed by a colon (:).</span></span> <span data-ttu-id="1efc6-223">たとえば、Alias: ドライブの内容を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-223">For example, to view the contents of the Alias: drive, type:</span></span>

```powershell
Get-Item alias:
```

<span data-ttu-id="1efc6-224">パスにドライブ名を含めることで、別のドライブのデータを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-224">You can view and manage the data in any drive from another drive by including the drive name in the path.</span></span> <span data-ttu-id="1efc6-225">たとえば、別のドライブの HKLM: ドライブの、Hklm\software レジストリキーを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-225">For example, to view the HKLM\Software registry key in the HKLM: drive from another drive, type:</span></span>

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

<span data-ttu-id="1efc6-226">ドライブを開くには、Set-Location コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-226">To open the drive, use the Set-Location cmdlet.</span></span> <span data-ttu-id="1efc6-227">ドライブパスを指定するときは、コロンを忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1efc6-227">Remember the colon when you specify the drive path.</span></span> <span data-ttu-id="1efc6-228">たとえば、場所を Cert: ドライブのルートディレクトリに変更するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-228">For example, to change your location to the root directory of the Cert: drive, type:</span></span>

```powershell
Set-Location cert:
```

<span data-ttu-id="1efc6-229">次に、Cert: ドライブの内容を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-229">Then, to view the contents of the Cert: drive, type:</span></span>

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a><span data-ttu-id="1efc6-230">階層データの移動</span><span class="sxs-lookup"><span data-stu-id="1efc6-230">Moving through hierarchical data</span></span>

<span data-ttu-id="1efc6-231">ハードディスクドライブの場合と同様に、プロバイダードライブ間を移動することができます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-231">You can move through a provider drive just as you would a hard disk drive.</span></span>
<span data-ttu-id="1efc6-232">項目内の項目の階層にデータが配置されている場合は、円記号 () を使用して `\` 子項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-232">If the data is arranged in a hierarchy of items within items, use a backslash (`\`) to indicate a child item.</span></span> <span data-ttu-id="1efc6-233">次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-233">Use the following format:</span></span>

```
drive:\location\child-location\...
```

<span data-ttu-id="1efc6-234">たとえば、場所を、Hklm\software レジストリキーに変更するには、次のように Set-Location コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-234">For example, to change your location to the HKLM\Software registry key, type a Set-Location command, such as:</span></span>

```powershell
Set-Location HKLM:\SOFTWARE\
```

<span data-ttu-id="1efc6-235">完全修飾名の要素にスペースが含まれている場合は、名前を二重引用符 () で囲む必要があり `"` ます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-235">If any element in the fully qualified name includes spaces, you must enclose the name in double-quotation marks (`"`).</span></span> <span data-ttu-id="1efc6-236">次の例は、スペースを含む完全修飾パスを示しています。</span><span class="sxs-lookup"><span data-stu-id="1efc6-236">The following example shows a fully qualified path that includes spaces.</span></span>

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

<span data-ttu-id="1efc6-237">また、相対参照を使用して場所を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-237">You can also use relative references to locations.</span></span> <span data-ttu-id="1efc6-238">ドット () は、 `.` 現在の場所を表します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-238">A dot (`.`) represents the current location.</span></span> <span data-ttu-id="1efc6-239">たとえば、 `HKLM:\Software\Microsoft` レジストリキーを使用していて、キーのレジストリサブキーを一覧表示する場合は、 `HKLM:\Software\Microsoft\PowerShell` 次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-239">For example, if you are in the `HKLM:\Software\Microsoft` registry key, and you want to list the registry subkeys in the `HKLM:\Software\Microsoft\PowerShell` key, type the following command:</span></span>

```powershell
Get-ChildItem .\PowerShell
```

<span data-ttu-id="1efc6-240">また、二重ドット () は、 `..` 現在の場所のすぐ上にあるディレクトリまたはコンテナーを参照します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-240">Also, double-dots (`..`) refers to the directory or container directly above your current location.</span></span> <span data-ttu-id="1efc6-241">2つのドット ( `..` ) を使用して、プロバイダー階層内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-241">You can use double-dots (`..`) to navigate through a provider hierarchy.</span></span>

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a><span data-ttu-id="1efc6-242">プロバイダーホーム</span><span class="sxs-lookup"><span data-stu-id="1efc6-242">Provider Home</span></span>

<span data-ttu-id="1efc6-243">また、プロバイダーには **ホーム** の場所もあります。</span><span class="sxs-lookup"><span data-stu-id="1efc6-243">Providers also have a **Home** location.</span></span>  <span data-ttu-id="1efc6-244">この場所は、プロバイダーによってサポートされるすべてので共有され `PSDrives` ます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-244">This location is shared by all `PSDrives` backed by the provider.</span></span> <span data-ttu-id="1efc6-245">プロバイダーの **Home** プロパティを表示することによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-245">It can be retrieved by viewing the **Home** property of the provider.</span></span>

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

<span data-ttu-id="1efc6-246">**FileSystem** プロバイダーは、 **Home** の既定値を持つ唯一のプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="1efc6-246">The **FileSystem** provider is the only provider that has a default value for **Home**.</span></span> <span data-ttu-id="1efc6-247">と同じ値 `$Home` です。</span><span class="sxs-lookup"><span data-stu-id="1efc6-247">It's the same value as `$Home`.</span></span> <span data-ttu-id="1efc6-248">詳細については、「 [about_Automatic_Variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efc6-248">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="1efc6-249">現在のセッションでは、そのプロパティを使用して、プロバイダーの **ホーム** ディレクトリを設定できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-249">You can set the **Home** directory for a provider, for the current session, using its property.</span></span>

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

<span data-ttu-id="1efc6-250">この `~` 文字は、プロバイダーのホームディレクトリを表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-250">The `~` character can be used to represent the provider's home directory.</span></span>
<span data-ttu-id="1efc6-251">プロバイダーに **ホーム** の場所が設定されていない場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-251">If the provider doesn't have a **Home** location set, you see an error.</span></span>

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

## <a name="finding-dynamic-parameters"></a><span data-ttu-id="1efc6-252">動的パラメーターの検索</span><span class="sxs-lookup"><span data-stu-id="1efc6-252">Finding dynamic parameters</span></span>

<span data-ttu-id="1efc6-253">動的パラメーターは、プロバイダーによってコマンドレットに追加されるコマンドレットパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="1efc6-253">Dynamic parameters are cmdlet parameters that are added to a cmdlet by a provider.</span></span> <span data-ttu-id="1efc6-254">これらのパラメーターは、コマンドレットを追加したプロバイダーと共に使用する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-254">These parameters are available only when the cmdlet is used with the provider that added them.</span></span>

<span data-ttu-id="1efc6-255">たとえば、ドライブは、 `Cert:` およびコマンドレットに **Codesigningcert** パラメーターを追加し `Get-Item` `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-255">For example, the `Cert:` drive adds the **CodeSigningCert** parameter to the `Get-Item` and `Get-ChildItem` cmdlets.</span></span> <span data-ttu-id="1efc6-256">このパラメーターは `Get-Item` 、ドライブでまたはを使用する場合にのみ使用でき `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="1efc6-256">You can use this parameter only when you use `Get-Item` or `Get-ChildItem` in the `Cert:` drive.</span></span>

<span data-ttu-id="1efc6-257">プロバイダーがサポートする動的パラメーターの一覧については、プロバイダーのヘルプファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efc6-257">For a list of the dynamic parameters that a provider supports, see the Help file for the provider.</span></span> <span data-ttu-id="1efc6-258">型:</span><span class="sxs-lookup"><span data-stu-id="1efc6-258">Type:</span></span>

```
Get-Help <provider-name>
```

<span data-ttu-id="1efc6-259">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-259">For example:</span></span>

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a><span data-ttu-id="1efc6-260">プロバイダーについて学習する</span><span class="sxs-lookup"><span data-stu-id="1efc6-260">Learning about providers</span></span>

<span data-ttu-id="1efc6-261">すべてのプロバイダーデータはドライブに表示されますが、同じメソッドを使用して移動すると、類似性が停止します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-261">Although all provider data appears in drives and you use the same methods to move through them, the similarity stops there.</span></span> <span data-ttu-id="1efc6-262">プロバイダーによって公開されるデータストアは、Active Directory の場所や Microsoft Exchange Server のメールボックスと同じように変化することがあります。</span><span class="sxs-lookup"><span data-stu-id="1efc6-262">The data stores that the provider exposes can be as varied as Active Directory locations and Microsoft Exchange Server mailboxes.</span></span>

<span data-ttu-id="1efc6-263">個々の PowerShell プロバイダーの詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="1efc6-263">For information about individual PowerShell providers, type:</span></span>

```
Get-Help <ProviderName>
```

<span data-ttu-id="1efc6-264">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1efc6-264">For example:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="1efc6-265">プロバイダーに関するヘルプトピックの一覧を表示するには、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="1efc6-265">For a list of Help topics about the providers, type:</span></span>

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a><span data-ttu-id="1efc6-266">関連項目</span><span class="sxs-lookup"><span data-stu-id="1efc6-266">See also</span></span>

[<span data-ttu-id="1efc6-267">about_Locations</span><span class="sxs-lookup"><span data-stu-id="1efc6-267">about_Locations</span></span>](about_Locations.md)

[<span data-ttu-id="1efc6-268">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="1efc6-268">about_Path_Syntax</span></span>](about_Path_Syntax.md)

