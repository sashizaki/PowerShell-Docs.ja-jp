---
description: Certificate
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/about/about_certificate_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 証明書プロバイダー
ms.openlocfilehash: b3ac701f18ba57d9108a76b7c478b8514075b3ee
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221979"
---
# <a name="certificate-provider"></a><span data-ttu-id="7cb39-104">証明書プロバイダー</span><span class="sxs-lookup"><span data-stu-id="7cb39-104">Certificate Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="7cb39-105">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="7cb39-105">Provider name</span></span>

<span data-ttu-id="7cb39-106">Certificate</span><span class="sxs-lookup"><span data-stu-id="7cb39-106">Certificate</span></span>

## <a name="drives"></a><span data-ttu-id="7cb39-107">ドライブ</span><span class="sxs-lookup"><span data-stu-id="7cb39-107">Drives</span></span>

`Cert:`

## <a name="capabilities"></a><span data-ttu-id="7cb39-108">機能</span><span class="sxs-lookup"><span data-stu-id="7cb39-108">Capabilities</span></span>

<span data-ttu-id="7cb39-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="7cb39-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="7cb39-110">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="7cb39-110">Short description</span></span>

<span data-ttu-id="7cb39-111">PowerShell での x.509 証明書ストアと証明書へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-111">Provides access to X.509 certificate stores and certificates in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="7cb39-112">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="7cb39-112">Detailed description</span></span>

<span data-ttu-id="7cb39-113">Powershell **証明書** プロバイダーを使用すると、powershell で証明書と証明書ストアを取得、追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-113">The PowerShell **Certificate** provider lets you get, add, change, clear, and delete certificates and certificate stores in PowerShell.</span></span>

<span data-ttu-id="7cb39-114">**証明書** ドライブは、コンピューター上の証明書ストアと証明書を含む階層的な名前空間です。</span><span class="sxs-lookup"><span data-stu-id="7cb39-114">The **Certificate** drive is a hierarchical namespace containing the certificate stores and certificates on your computer.</span></span>

<span data-ttu-id="7cb39-115">**証明書** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7cb39-115">The **Certificate** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="7cb39-116">Get-Location</span><span class="sxs-lookup"><span data-stu-id="7cb39-116">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="7cb39-117">Set-Location</span><span class="sxs-lookup"><span data-stu-id="7cb39-117">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="7cb39-118">Get-Item</span><span class="sxs-lookup"><span data-stu-id="7cb39-118">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="7cb39-119">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="7cb39-119">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="7cb39-120">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="7cb39-120">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="7cb39-121">Move-Item</span><span class="sxs-lookup"><span data-stu-id="7cb39-121">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="7cb39-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="7cb39-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="7cb39-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="7cb39-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="7cb39-124">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7cb39-124">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="7cb39-125">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7cb39-125">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="7cb39-126">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="7cb39-126">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="7cb39-127">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="7cb39-127">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="7cb39-128">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="7cb39-128">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="7cb39-129">このプロバイダーによって公開される型</span><span class="sxs-lookup"><span data-stu-id="7cb39-129">Types exposed by this provider</span></span>

<span data-ttu-id="7cb39-130">証明書ドライブは、次の種類を公開します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-130">The Certificate drive exposes the following types.</span></span>

- <span data-ttu-id="7cb39-131">ストアの場所 (X509StoreLocation)。現在のユーザーとすべてのユーザーの証明書をグループ化する高レベルのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="7cb39-131">Store locations (Microsoft.PowerShell.Commands.X509StoreLocation), which are high-level containers that group the certificates for the current user and for all users.</span></span> <span data-ttu-id="7cb39-132">各システムに CurrentUser と LocalMachine (すべてのユーザー) のストアの場所があります。</span><span class="sxs-lookup"><span data-stu-id="7cb39-132">Each system has a CurrentUser and LocalMachine (all users) store location.</span></span>

- <span data-ttu-id="7cb39-133">証明書ストア (System.security.cryptography.x509certificates.x509certificate2. X509Store)。証明書が保存および管理される物理ストアです。</span><span class="sxs-lookup"><span data-stu-id="7cb39-133">Certificates stores (System.Security.Cryptography.X509Certificates.X509Store), which are physical stores in which certificates are saved and managed.</span></span>

- <span data-ttu-id="7cb39-134">X.509 **system.security.cryptography.x509certificates.x509certificate2. X509Certificate2** 証明書。各証明書は、コンピューター上の x.509 証明書を表します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-134">X.509 **System.Security.Cryptography.X509Certificates.X509Certificate2** certificates, each of which represent an X.509 certificate on the computer.</span></span>
  <span data-ttu-id="7cb39-135">証明書は拇印により識別されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-135">Certificates are identified by their thumbprints.</span></span>

## <a name="navigating-the-certificate-drive"></a><span data-ttu-id="7cb39-136">証明書のドライブを移動する</span><span class="sxs-lookup"><span data-stu-id="7cb39-136">Navigating the Certificate drive</span></span>

<span data-ttu-id="7cb39-137">**証明書** プロバイダーは、PowerShell で証明書の名前空間をドライブとして公開し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-137">The **Certificate** provider exposes the certificate namespace as the `Cert:` drive in PowerShell.</span></span> <span data-ttu-id="7cb39-138">このコマンドは、コマンドを使用して、 `Set-Location` 現在の場所を LocalMachine ストアの場所にあるルート証明書ストアに変更します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-138">This command uses the `Set-Location` command to change the current location to the Root certificate store in the LocalMachine store location.</span></span> <span data-ttu-id="7cb39-139">円記号 ( \\ ) またはスラッシュ (/) を使用して、ドライブのレベルを指定し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-139">Use a backslash (\\) or a forward slash (/) to indicate a level of the `Cert:` drive.</span></span>

```powershell
Set-Location Cert:
```

<span data-ttu-id="7cb39-140">他の PowerShell ドライブから証明書プロバイダーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-140">You can also work with the certificate provider from any other PowerShell drive.</span></span> <span data-ttu-id="7cb39-141">別の場所からエイリアスを参照するには、 `Cert:` パス内のドライブ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-141">To reference an alias from another location, use the `Cert:` drive name in the path.</span></span>

```powershell
PS Cert:\> Set-Location -Path LocalMachine\Root
```

<span data-ttu-id="7cb39-142">ファイル システム ドライブに戻るには、ドライブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-142">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="7cb39-143">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-143">For example, type:</span></span>

```powershell
Set-Location C:
```

> [!NOTE]
> <span data-ttu-id="7cb39-144">PowerShell では、エイリアスを使用して、プロバイダーパスを操作するための使い慣れた方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="7cb39-145">`dir`やなどのコマンド `ls` は、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)のエイリアスです。これ `cd` は、 [Set Location](xref:Microsoft.PowerShell.Management.Set-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="7cb39-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span>
> <span data-ttu-id="7cb39-146">と `pwd` は、 [Get Location](xref:Microsoft.PowerShell.Management.Get-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="7cb39-146">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-contents-of-the-cert-drive"></a><span data-ttu-id="7cb39-147">Cert: ドライブの内容を表示しています</span><span class="sxs-lookup"><span data-stu-id="7cb39-147">Displaying the Contents of the Cert: drive</span></span>

<span data-ttu-id="7cb39-148">このコマンドは、 `Get-ChildItem` コマンドレットを使用して、CurrentUser 証明書ストアの場所に証明書ストアを表示します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-148">This command uses the `Get-ChildItem` cmdlet to display the certificate stores in the CurrentUser certificate store location.</span></span>

<span data-ttu-id="7cb39-149">ドライブにない場合は `Cert:` 、絶対パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-149">If you are not in the `Cert:` drive, use an absolute path.</span></span>

```powershell
PS Cert:\CurrentUser\> Get-ChildItem
```

### <a name="displaying-certificate-properties-within-the-cert-drive"></a><span data-ttu-id="7cb39-150">Cert: ドライブ内の証明書のプロパティを表示しています</span><span class="sxs-lookup"><span data-stu-id="7cb39-150">Displaying certificate properties within the Cert: drive</span></span>

<span data-ttu-id="7cb39-151">この例では、を使用して証明書を取得 `Get-Item` し、変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-151">This example gets a certificate with `Get-Item` and stores it in a variable.</span></span>
<span data-ttu-id="7cb39-152">この例では、を使用して、新しい証明書スクリプトプロパティ ( **DnsNameList** 、 **EnhancedKeyUsageList** 、 **SendAsTrustedIssuer** ) を示し `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-152">The example shows the new certificate script properties ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) using `Select-Object`.</span></span>

```powershell
$c = Get-Item cert:\LocalMachine\My\52A149D0393CE8A8D4AF0B172ED667A9E3A1F44E
$c | Format-List DnsNameList, EnhancedKeyUsageList, SendAsTrustedIssuer
```

```output
DnsNameList          : {SERVER01.contoso.com}
EnhancedKeyUsageList : {WiFi-Machine (1.3.6.1.4.1.311.42.2.6),
                       Client Authentication (1.3.6.1.5.5.7.3.2)}
SendAsTrustedIssuer  : False
```

### <a name="find-all-codesigning-certificates"></a><span data-ttu-id="7cb39-153">すべてのコード署名証明書の検索</span><span class="sxs-lookup"><span data-stu-id="7cb39-153">Find all CodeSigning certificates</span></span>

<span data-ttu-id="7cb39-154">このコマンドは、コマンドレットの **Codesigningcert** と **再帰** パラメーターを使用して、 `Get-ChildItem` コード署名機関を持つコンピューター上のすべての証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-154">This command uses the **CodeSigningCert** and **Recurse** parameters of the `Get-ChildItem` cmdlet to get all of the certificates on the computer that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path cert: -CodeSigningCert -Recurse
```

### <a name="find-expired-certificates"></a><span data-ttu-id="7cb39-155">期限切れの証明書の検索</span><span class="sxs-lookup"><span data-stu-id="7cb39-155">Find expired certificates</span></span>

<span data-ttu-id="7cb39-156">このコマンドは、コマンドレットの **ExpiringInDays** パラメーターを使用して、 `Get-ChildItem` 次の30日以内に有効期限が切れる証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-156">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet to get certificates that will expire within the next 30 days.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\WebHosting -ExpiringInDays 30
```

### <a name="find-server-ssl-certificates"></a><span data-ttu-id="7cb39-157">サーバーの SSL 証明書を検索する</span><span class="sxs-lookup"><span data-stu-id="7cb39-157">Find Server SSL Certificates</span></span>

<span data-ttu-id="7cb39-158">このコマンドは、コマンドレットの **Sslserverauthentication** パラメーターを使用して `Get-ChildItem` 、My および webhosting ストア内のすべてのサーバー SSL 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-158">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get all Server SSL Certificates in the My and WebHosting stores.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\My, cert:\LocalMachine\WebHosting `
  -SSLServerAuthentication
```

### <a name="find-expired-certificates-on-remote-computers"></a><span data-ttu-id="7cb39-159">リモートコンピューターで有効期限が切れた証明書を検索する</span><span class="sxs-lookup"><span data-stu-id="7cb39-159">Find expired certificates on remote computers</span></span>

<span data-ttu-id="7cb39-160">このコマンドは、コマンドレットを使用して、 `Invoke-Command` `Get-ChildItem` Srv01 コンピューターと Srv02 コンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-160">This command uses the `Invoke-Command` cmdlet to run a `Get-ChildItem` command on the Srv01 and Srv02 computers.</span></span> <span data-ttu-id="7cb39-161">**ExpiringInDays** パラメーターの値がゼロ (0) の場合、Srv01 コンピューターと Srv02 コンピューターの有効期限が切れている証明書が取得されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-161">A value of zero (0) in the **ExpiringInDays** parameter gets certificates on the Srv01 and Srv02 computers that have expired.</span></span>

```powershell
Invoke-Command -ComputerName Srv01, Srv02 {Get-ChildItem -Path cert:\* `
  -Recurse -ExpiringInDays 0}
```

### <a name="combining-filters-to-find-a-specific-set-of-certificates"></a><span data-ttu-id="7cb39-162">フィルターを組み合わせて特定の証明書セットを検索する</span><span class="sxs-lookup"><span data-stu-id="7cb39-162">Combining filters to find a specific set of certificates</span></span>

<span data-ttu-id="7cb39-163">このコマンドは、LocalMachine ストアの場所にある、次の属性を持つすべての証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-163">This command gets all certificates in the LocalMachine store location that have the following attributes:</span></span>

- <span data-ttu-id="7cb39-164">DNS 名に "fabrikam"</span><span class="sxs-lookup"><span data-stu-id="7cb39-164">"fabrikam" in their DNS name</span></span>
- <span data-ttu-id="7cb39-165">EKU 内の "クライアント認証"</span><span class="sxs-lookup"><span data-stu-id="7cb39-165">"Client Authentication" in their EKU</span></span>
- <span data-ttu-id="7cb39-166">`$true` **SendAsTrustedIssuer** プロパティの値</span><span class="sxs-lookup"><span data-stu-id="7cb39-166">a value of `$true` for the **SendAsTrustedIssuer** property</span></span>
- <span data-ttu-id="7cb39-167">次の30日以内に期限切れにならないようにします。</span><span class="sxs-lookup"><span data-stu-id="7cb39-167">do not expire within the next 30 days.</span></span>

<span data-ttu-id="7cb39-168">**Notafter** プロパティには、証明書の有効期限が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-168">The **NotAfter** property stores the certificate expiration date.</span></span>

```powershell
[DateTime] $ValidThrough = (Get-Date) + (New-TimeSpan -Days 30)
Get-ChildItem -Path cert:\* -Recurse -DNSName "*fabrikam*" `
  -EKU "*Client Authentication*" | Where-Object {
                                     $_.SendAsTrustedIssuer -and `
                                     $_.NotAfter -gt $ValidThrough
                                   }
```

## <a name="opening-the-certificates-mmc-snap-in"></a><span data-ttu-id="7cb39-169">証明書 MMC スナップインを開く</span><span class="sxs-lookup"><span data-stu-id="7cb39-169">Opening the Certificates MMC Snap-in</span></span>

<span data-ttu-id="7cb39-170">`Invoke-Item`コマンドレットは、既定のアプリケーションを使用して、指定したパスを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-170">The `Invoke-Item` cmdlet will use the default application to open a path you specify.</span></span> <span data-ttu-id="7cb39-171">証明書の場合、既定のアプリケーションは証明書 MMC スナップインです。</span><span class="sxs-lookup"><span data-stu-id="7cb39-171">For certificates, the default application is the Certificates MMC snap-in.</span></span>

<span data-ttu-id="7cb39-172">このコマンドを実行すると、証明書 MMC スナップインが開きます。特定の証明書を管理できます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-172">This command opens the Certificates MMC snap-in to manage the specified certificate.</span></span>

```powershell
Invoke-Item cert:\CurrentUser\my\6B8223358119BB08840DEE50FD8AF9EA776CE66B
```

## <a name="copying-certificates"></a><span data-ttu-id="7cb39-173">証明書のコピー</span><span class="sxs-lookup"><span data-stu-id="7cb39-173">Copying Certificates</span></span>

<span data-ttu-id="7cb39-174">証明書のコピーは **証明書** プロバイダーでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7cb39-174">Copying certificates is not supported by the **Certificate** provider.</span></span> <span data-ttu-id="7cb39-175">証明書をコピーしようとすると、このエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-175">When you attempt to copy a certificate, you see this error.</span></span>

```
$path = "Cert:\LocalMachine\Root\E2C0F6662D3C569705B4B31FE2CBF3434094B254"
PS Cert:\LocalMachine\> Copy-Item -Path $path -Destination .\CA\
Copy-Item : Provider operation stopped because the provider does not support
this operation.
At line:1 char:1
+ Copy-Item -Path $path -Destination .\CA\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotImplemented: (:) [Copy-Item],
                              PSNotSupportedException
    + FullyQualifiedErrorId : NotSupported,
                              Microsoft.PowerShell.Commands.CopyItemCommand
```

## <a name="moving-certificates"></a><span data-ttu-id="7cb39-176">証明書の移動</span><span class="sxs-lookup"><span data-stu-id="7cb39-176">Moving Certificates</span></span>

### <a name="move-all-ssl-server-authentication-certs-to-the-webhosting-store"></a><span data-ttu-id="7cb39-177">すべての SSL サーバー認証証明書を Web ホスティングストアに移動する</span><span class="sxs-lookup"><span data-stu-id="7cb39-177">Move all SSL Server authentication certs to the WebHosting store</span></span>

<span data-ttu-id="7cb39-178">このコマンドは、 `Move-Item` コマンドレットを使用して、My ストアから WebHosting ストアに証明書を移動します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-178">This command uses the `Move-Item` cmdlet to move a certificate from the My store to the WebHosting store.</span></span>

<span data-ttu-id="7cb39-179">`Move-Item` は、証明書ストアを移動せず、証明書を LocalMachine から CurrentUser に移動するなど、別のストアの場所に証明書を移動しません。</span><span class="sxs-lookup"><span data-stu-id="7cb39-179">`Move-Item` will not move certificate stores and it will not move certificates to a different store location, such as moving a certificate from LocalMachine to CurrentUser.</span></span> <span data-ttu-id="7cb39-180">`Move-Item`コマンドレットでは証明書を移動しますが、秘密キーは移動しません。</span><span class="sxs-lookup"><span data-stu-id="7cb39-180">The `Move-Item` cmdlet moves certificates, but it does not move private keys.</span></span>

<span data-ttu-id="7cb39-181">このコマンドは、コマンドレットの **Sslserverauthentication** パラメーターを使用して `Get-ChildItem` 、MY 証明書ストア内の SSL サーバー認証証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-181">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get SSL server authentication certificates in the MY certificate store.</span></span>

<span data-ttu-id="7cb39-182">返された証明書はコマンドレットにパイプ処理され、 `Move-Item` 証明書が WebHosting ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-182">The returned certificates are piped to the `Move-Item` cmdlet, which moves the certificates to the WebHosting store.</span></span>

```powershell
Get-ChildItem cert:\LocalMachine\My -SSLServerAuthentication | Move-Item `
  -Destination cert:\LocalMachine\WebHosting
```

## <a name="deleting-certificates-and-private-keys"></a><span data-ttu-id="7cb39-183">証明書と秘密キーを削除する</span><span class="sxs-lookup"><span data-stu-id="7cb39-183">Deleting Certificates and Private Keys</span></span>

<span data-ttu-id="7cb39-184">`Remove-Item`コマンドレットは、指定した証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-184">The `Remove-Item` cmdlet will remove certificates that you specify.</span></span> <span data-ttu-id="7cb39-185">`-DeleteKey`動的パラメーターは、秘密キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-185">The `-DeleteKey` dynamic parameter deletes the private key.</span></span>

### <a name="delete-a-certificate-from-the-ca-store"></a><span data-ttu-id="7cb39-186">CA ストアから証明書を削除する</span><span class="sxs-lookup"><span data-stu-id="7cb39-186">Delete a Certificate from the CA store</span></span>

<span data-ttu-id="7cb39-187">このコマンドは CA 証明書ストアから証明書を削除するが、関連付けられている秘密キーはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="7cb39-187">This command deletes a certificate from the CA certificate store, but leaves the associated private key intact.</span></span>

<span data-ttu-id="7cb39-188">ドライブでは、 `Cert:` `Remove-Item` コマンドレットは **deletekey** 、 **Path** 、 **WhatIf** 、 **Confirm** パラメーターのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7cb39-188">In the `Cert:` drive, the `Remove-Item` cmdlet supports only the **DeleteKey** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="7cb39-189">その他のパラメーターはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-189">All other parameters are ignored.</span></span>

```powershell
Remove-Item cert:\LocalMachine\CA\5DDC44652E62BF9AA1116DC41DE44AB47C87BDD0
```

### <a name="delete-a-certificate-using-a-wildcards-in-the-dns-name"></a><span data-ttu-id="7cb39-190">DNS 名にワイルドカードを使用して証明書を削除する</span><span class="sxs-lookup"><span data-stu-id="7cb39-190">Delete a Certificate using a wildcards in the DNS name</span></span>

<span data-ttu-id="7cb39-191">このコマンドは、DNS 名に「Fabrikam」が含まれるすべての証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-191">This command deletes all certificates that have a DNS name that contains "Fabrikam".</span></span> <span data-ttu-id="7cb39-192">コマンドレットの **DNSName** パラメーターを使用して `Get-ChildItem` 証明書を取得し、コマンドレットを使用して証明書を `Remove-Item` 削除します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-192">It uses the **DNSName** parameter of the `Get-ChildItem` cmdlet to get the certificates and the `Remove-Item` cmdlet to delete them.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine -DnsName *Fabrikam* | Remove-Item
```

### <a name="delete-private-keys-from-a-remote-computer"></a><span data-ttu-id="7cb39-193">リモートコンピューターから秘密キーを削除する</span><span class="sxs-lookup"><span data-stu-id="7cb39-193">Delete private keys from a remote computer</span></span>

<span data-ttu-id="7cb39-194">この一連のコマンドは委任を有効化し、リモート コンピューターにある証明書と関連秘密キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-194">This series of commands enables delegation and then deletes the certificate and associated private key on a remote computer.</span></span> <span data-ttu-id="7cb39-195">リモート コンピューターの秘密キーを削除するには、委任された資格情報を利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cb39-195">To delete a private key on a remote computer, you must use delegated credentials.</span></span>

<span data-ttu-id="7cb39-196">コマンドレットを使用して、 `Enable-WSManCredSSP` S1 リモートコンピューター上のクライアントで Credential Security Service Provider (CredSSP) 認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7cb39-196">Use the `Enable-WSManCredSSP` cmdlet to enable Credential Security Service Provider (CredSSP) authentication on a client on the S1 remote computer.</span></span>
<span data-ttu-id="7cb39-197">CredSSP は委任認証を許可します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-197">CredSSP permits delegated authentication.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer S1
```

<span data-ttu-id="7cb39-198">コマンドレットを使用して、 `Connect-WSMan` S1 コンピューターをローカルコンピューター上の WinRM サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-198">Use the `Connect-WSMan` cmdlet to connect the S1 computer to the WinRM service on the local computer.</span></span> <span data-ttu-id="7cb39-199">このコマンドが完了すると、S1 コンピューターが PowerShell のローカルドライブに表示され `WSMan:` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-199">When this command completes, the S1 computer appears in the local `WSMan:` drive in PowerShell.</span></span>

```powershell
Connect-WSMan -ComputerName S1 -Credential Domain01\Admin01
```

<span data-ttu-id="7cb39-200">これで、WSMan: ドライブの Set-Item コマンドレットを使用して、WinRM サービスの CredSSP 属性を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-200">Now, you can use the Set-Item cmdlet in the WSMan: drive to enable the CredSSP attribute for the WinRM service.</span></span>

```powershell
Set-Item -Path WSMan:\S1\Service\Auth\CredSSP -Value $true
```

<span data-ttu-id="7cb39-201">コマンドレットを使用して s1 コンピューターでリモートセッションを開始 `New-PSSession` し、CredSSP 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-201">Start a remote session on the s1 computer using the `New-PSSession` cmdlet, and specify CredSSP authentication.</span></span> <span data-ttu-id="7cb39-202">変数にセッションを保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-202">Saves the session in the `$s` variable.</span></span>

```powershell
$s  = New-PSSession S1 -Authentication CredSSP -Credential Domain01\Admin01
```

<span data-ttu-id="7cb39-203">最後に、コマンドレットを使用して、 `Invoke-Command` `Remove-Item` 変数内のセッションでコマンドを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-203">Finally, use the `Invoke-Command` cmdlet to run a `Remove-Item` command in the session in the `$s` variable.</span></span> <span data-ttu-id="7cb39-204">この `Remove-Item` コマンドは、 **deletekey** パラメーターを使用して、指定された証明書と共に秘密キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-204">The `Remove-Item` command uses the **DeleteKey** parameter to remove the private key along with the specified certificate.</span></span>

```powershell
Invoke-Command -Session $s { Remove-Item `
  -Path cert:\LocalMachine\My\D2D38EBA60CAA1C12055A2E1C83B15AD450110C2 `
  -DeleteKey
  }
```

### <a name="delete-expired-certificates"></a><span data-ttu-id="7cb39-205">期限切れの証明書の削除</span><span class="sxs-lookup"><span data-stu-id="7cb39-205">Delete expired Certificates</span></span>

<span data-ttu-id="7cb39-206">このコマンドは、コマンドレットの **ExpiringInDays** パラメーターに値0を指定して、 `Get-ChildItem` 有効期限が切れた web ホスティングストア内の証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-206">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet with a value of 0 to get certificates in the WebHosting store that have expired.</span></span>

<span data-ttu-id="7cb39-207">返された証明書を含む変数は、パイプを使用してコマンドレットに渡され `Remove-Item` 、削除されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-207">The variable containing the returned certificates is piped to the `Remove-Item` cmdlet, which deletes them.</span></span> <span data-ttu-id="7cb39-208">このコマンドは、 **deletekey** パラメーターを使用して、証明書と共に秘密キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-208">The command uses the **DeleteKey** parameter to delete the private key along with the certificate.</span></span>

```powershell
$expired = Get-ChildItem cert:\LocalMachine\WebHosting -ExpiringInDays 0
$expired | Remove-Item -DeleteKey
```

## <a name="creating-certificates"></a><span data-ttu-id="7cb39-209">証明書の作成</span><span class="sxs-lookup"><span data-stu-id="7cb39-209">Creating Certificates</span></span>

<span data-ttu-id="7cb39-210">`New-Item`コマンドレットでは、 **証明書** プロバイダーに新しい証明書を作成しません。</span><span class="sxs-lookup"><span data-stu-id="7cb39-210">The `New-Item` cmdlet does not create new certificates in the **Certificate** provider.</span></span> <span data-ttu-id="7cb39-211">[新しい-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate)コマンドレットを使用して、テスト用の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-211">Use the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet to create a certificate for testing purposes.</span></span>

## <a name="creating-certificate-stores"></a><span data-ttu-id="7cb39-212">証明書ストアの作成</span><span class="sxs-lookup"><span data-stu-id="7cb39-212">Creating Certificate Stores</span></span>

<span data-ttu-id="7cb39-213">Cert: ドライブでは、 `New-Item` コマンドレットは LocalMachine ストアの場所に証明書ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-213">In the Cert: drive, the `New-Item` cmdlet creates certificate stores in the LocalMachine store location.</span></span> <span data-ttu-id="7cb39-214">**Name** 、 **Path** 、 **WhatIf** 、 **Confirm** の各パラメーターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7cb39-214">It supports the **Name** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="7cb39-215">その他のパラメーターはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-215">All other parameters are ignored.</span></span> <span data-ttu-id="7cb39-216">このコマンドは、新しい証明書ストアを表す **system.security.cryptography.x509certificates.x509certificate2. X509Store** を返します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-216">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

<span data-ttu-id="7cb39-217">このコマンドは LocalMachine ストアの場所で「CustomStore」という名前の新しい証明書ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-217">This command creates a new certificate store named "CustomStore" in the LocalMachine store location.</span></span>

```powershell
New-Item -Path cert:\LocalMachine\CustomStore
```

### <a name="create-a-new-certificate-store-on-a-remote-computer"></a><span data-ttu-id="7cb39-218">リモートコンピューターに新しい証明書ストアを作成する</span><span class="sxs-lookup"><span data-stu-id="7cb39-218">Create a new certificate store on a remote computer</span></span>

<span data-ttu-id="7cb39-219">このコマンドは Server01 コンピューターの LocalMachine ストアの場所で「HostingStore」という名前の新しい証明書ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-219">This command creates a new certificate store named "HostingStore" in the LocalMachine store location on the Server01 computer.</span></span>

<span data-ttu-id="7cb39-220">このコマンドは、コマンドレットを使用して、 `Invoke-Command` `New-Item` Server01 コンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-220">The command uses the `Invoke-Command` cmdlet to run a `New-Item` command on the Server01 computer.</span></span> <span data-ttu-id="7cb39-221">このコマンドは、新しい証明書ストアを表す **system.security.cryptography.x509certificates.x509certificate2. X509Store** を返します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-221">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

```powershell
Invoke-Command { New-Item -Path cert:\LocalMachine\CustomStore } `
  -ComputerName Server01
```

## <a name="creating-client-certificates-for-ws-man"></a><span data-ttu-id="7cb39-222">WS-Man 用のクライアント証明書の作成</span><span class="sxs-lookup"><span data-stu-id="7cb39-222">Creating Client Certificates for WS-Man</span></span>

<span data-ttu-id="7cb39-223">このコマンドは、 **ws-management** クライアントが使用できる **ClientCertificate** エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-223">This command creates **ClientCertificate** entry that can be used by the **WS-Management** client.</span></span> <span data-ttu-id="7cb39-224">新しい **ClientCertificate** は、 **ClientCertificate** ディレクトリの下に "ClientCertificate_1234567890" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-224">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="7cb39-225">すべてのパラメーターが必須です。</span><span class="sxs-lookup"><span data-stu-id="7cb39-225">All of the parameters are mandatory.</span></span> <span data-ttu-id="7cb39-226">**発行者** は、発行者証明書の拇印である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cb39-226">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* -Credential $cred
```

## <a name="deleting-certificate-stores"></a><span data-ttu-id="7cb39-227">証明書ストアの削除</span><span class="sxs-lookup"><span data-stu-id="7cb39-227">Deleting Certificate Stores</span></span>

### <a name="delete-a-certificate-store-from-a-remote-computer"></a><span data-ttu-id="7cb39-228">リモートコンピューターから証明書ストアを削除する</span><span class="sxs-lookup"><span data-stu-id="7cb39-228">Delete a certificate store from a remote computer</span></span>

<span data-ttu-id="7cb39-229">このコマンドは、コマンドレットを使用して、 `Invoke-Command` `Remove-Item` S1 および S2 コンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-229">This command uses the `Invoke-Command` cmdlet to run a `Remove-Item` command on the S1 and S2 computers.</span></span> <span data-ttu-id="7cb39-230">このコマンドには、 `Remove-Item` **再帰** パラメーターが含まれています。これにより、ストア内の証明書が削除されてからストアが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-230">The `Remove-Item` command includes the **Recurse** parameter, which deletes the certificates in the store before it deletes the store.</span></span>

```powershell
Invoke-Command { Remove-Item -Path cert:\LocalMachine\TestStore -Recurse } `
  -ComputerName S1, S2
```

## <a name="dynamic-parameters"></a><span data-ttu-id="7cb39-231">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="7cb39-231">Dynamic parameters</span></span>

<span data-ttu-id="7cb39-232">動的パラメーターは、PowerShell プロバイダーによって追加されるコマンドレットパラメーターであり、プロバイダーに対応したドライブでコマンドレットが使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-232">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span> <span data-ttu-id="7cb39-233">これらのパラメーターは証明書プロバイダーのすべてのサブディレクトリで有効ですが、証明書に対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="7cb39-233">These parameters are valid in all subdirectories of the Certificate provider, but are effective only on certificates.</span></span>

> [!NOTE]
> <span data-ttu-id="7cb39-234">プロパティに対してフィルター処理を実行するパラメーター `EnhancedKeyUsageList` も、空のプロパティ値を持つ項目を返し `EnhancedKeyUsageList` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-234">Parameters that perform filtering against the `EnhancedKeyUsageList` property also return items with an empty `EnhancedKeyUsageList` property value.</span></span>
> <span data-ttu-id="7cb39-235">空の **EnhancedKeyUsageList** が含まれている証明書は、すべての目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-235">Certificates that have an empty **EnhancedKeyUsageList** can be used for all purposes.</span></span>

### <a name="codesigningcert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="7cb39-236">CodeSigningCert は、<の></span><span class="sxs-lookup"><span data-stu-id="7cb39-236">CodeSigningCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="7cb39-237">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7cb39-237">Cmdlets supported</span></span>

- [<span data-ttu-id="7cb39-238">Get-Item</span><span class="sxs-lookup"><span data-stu-id="7cb39-238">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="7cb39-239">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="7cb39-239">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="7cb39-240">このパラメーターは、 **EnhancedKeyUsageList** プロパティ値に "コード署名" が含まれている証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-240">This parameter gets certificates that have "Code Signing" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="deletekey-systemmanagementautomationswitchparameter"></a><span data-ttu-id="7cb39-241">DeleteKey <を削除します。 SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="7cb39-241">DeleteKey <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="7cb39-242">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7cb39-242">Cmdlets supported</span></span>

- [<span data-ttu-id="7cb39-243">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="7cb39-243">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

<span data-ttu-id="7cb39-244">このパラメーターは、証明書を削除するときに、関連付けられている秘密キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-244">This parameter deletes the associated private key when it deletes the certificate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7cb39-245">リモートコンピューター上のストア内のユーザー証明書に関連付けられている秘密キーを削除するには `Cert:\CurrentUser` 、委任された資格情報を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cb39-245">To delete a private key that is associated with a user certificate in the `Cert:\CurrentUser` store on a remote computer, you must use delegated credentials.</span></span> <span data-ttu-id="7cb39-246">`Invoke-Command`コマンドレットでは、 **CredSSP** パラメーターを使用した資格情報の委任がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7cb39-246">The `Invoke-Command` cmdlet supports credential delegation using the **CredSSP** parameter.</span></span> <span data-ttu-id="7cb39-247">`Remove-Item`との資格情報の委任を使用する前に、セキュリティ上のリスクを考慮する必要があり `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-247">You should consider any security risks before using `Remove-Item` with `Invoke-Command` and credential delegation.</span></span>

<span data-ttu-id="7cb39-248">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7cb39-248">This parameter was introduced in PowerShell 3.0.</span></span>

### <a name="dnsname-microsoftpowershellcommandsdnsnamerepresentation"></a><span data-ttu-id="7cb39-249">DnsName <、> のようになります。</span><span class="sxs-lookup"><span data-stu-id="7cb39-249">DnsName <Microsoft.PowerShell.Commands.DnsNameRepresentation></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="7cb39-250">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7cb39-250">Cmdlets supported</span></span>

- [<span data-ttu-id="7cb39-251">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="7cb39-251">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="7cb39-252">このパラメーターは、証明書の **DNSNameList** プロパティに指定されたドメイン名または名前パターンを持つ証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-252">This parameter gets certificates that have the specified domain name or name pattern in the **DNSNameList** property of the certificate.</span></span> <span data-ttu-id="7cb39-253">このパラメーターの値には、"Unicode" または "ASCII" を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-253">The value of this parameter can either be "Unicode" or "ASCII".</span></span> <span data-ttu-id="7cb39-254">Punycode 値は Unicode に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-254">Punycode values are converted to Unicode.</span></span> <span data-ttu-id="7cb39-255">ワイルドカード文字 ( `*` ) が許可されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-255">Wildcard characters (`*`) are permitted.</span></span>

<span data-ttu-id="7cb39-256">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7cb39-256">This parameter was introduced in PowerShell 3.0.</span></span>

### <a name="documentencryptioncert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="7cb39-257">DocumentEncryptionCert <を> します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-257">DocumentEncryptionCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="7cb39-258">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7cb39-258">Cmdlets supported</span></span>

- [<span data-ttu-id="7cb39-259">Get-Item</span><span class="sxs-lookup"><span data-stu-id="7cb39-259">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="7cb39-260">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="7cb39-260">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="7cb39-261">このパラメーターは、 **EnhancedKeyUsageList** プロパティ値に "Document Encryption" が含まれている証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-261">This parameter gets certificates that have "Document Encryption" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="eku-systemstring"></a><span data-ttu-id="7cb39-262">EKU <System.string></span><span class="sxs-lookup"><span data-stu-id="7cb39-262">EKU <System.String></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="7cb39-263">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7cb39-263">Cmdlets supported</span></span>

- [<span data-ttu-id="7cb39-264">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="7cb39-264">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="7cb39-265">このパラメーターは、証明書のプロパティに指定されたテキストまたはテキストパターンを持つ証明書を取得し `EnhancedKeyUsageList` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-265">This parameter gets certificates that have the specified text or text pattern in the `EnhancedKeyUsageList` property of the certificate.</span></span> <span data-ttu-id="7cb39-266">ワイルドカード文字 ( `*` ) が許可されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-266">Wildcard characters (`*`) are permitted.</span></span> <span data-ttu-id="7cb39-267">プロパティには、 `EnhancedKeyUsageList` EKU のフレンドリ名と OID フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7cb39-267">The `EnhancedKeyUsageList` property contains the friendly name and the OID fields of the EKU.</span></span>

<span data-ttu-id="7cb39-268">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7cb39-268">This parameter was introduced in PowerShell 3.0.</span></span>

### <a name="expiringindays-systemint32"></a><span data-ttu-id="7cb39-269">ExpiringInDays <system.string></span><span class="sxs-lookup"><span data-stu-id="7cb39-269">ExpiringInDays <System.Int32></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="7cb39-270">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7cb39-270">Cmdlets supported</span></span>

- [<span data-ttu-id="7cb39-271">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="7cb39-271">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="7cb39-272">このパラメーターは、指定した日数以内に期限切れになる証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-272">This parameter gets certificates that are expiring in or before the specified number of days.</span></span> <span data-ttu-id="7cb39-273">値に 0 (zero) を指定した場合、失効している証明書が取得されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-273">A value of 0 (zero) gets certificates that have expired.</span></span>

<span data-ttu-id="7cb39-274">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7cb39-274">This parameter was introduced in PowerShell 3.0.</span></span>

### <a name="itemtype-string"></a><span data-ttu-id="7cb39-275">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="7cb39-275">ItemType \<String\></span></span>

<span data-ttu-id="7cb39-276">このパラメーターを使用すると、によって作成される項目の型を指定でき `New-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-276">This parameter allows you to specify the type of item created by `New-Item`.</span></span>

<span data-ttu-id="7cb39-277">ドライブでは、 `Certificate` 次の値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-277">In a `Certificate` drive, the following values are allowed:</span></span>

- <span data-ttu-id="7cb39-278">証明書プロバイダー</span><span class="sxs-lookup"><span data-stu-id="7cb39-278">Certificate Provider</span></span>
- <span data-ttu-id="7cb39-279">Certificate</span><span class="sxs-lookup"><span data-stu-id="7cb39-279">Certificate</span></span>
- <span data-ttu-id="7cb39-280">ストア</span><span class="sxs-lookup"><span data-stu-id="7cb39-280">Store</span></span>
- <span data-ttu-id="7cb39-281">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="7cb39-281">StoreLocation</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="7cb39-282">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7cb39-282">Cmdlets Supported</span></span>

- [<span data-ttu-id="7cb39-283">New-Item</span><span class="sxs-lookup"><span data-stu-id="7cb39-283">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sslserverauthentication-systemmanagementautomationswitchparameter"></a><span data-ttu-id="7cb39-284">SSLServerAuthentication は、<の> を指定します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-284">SSLServerAuthentication <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="7cb39-285">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7cb39-285">Cmdlets supported</span></span>

- [<span data-ttu-id="7cb39-286">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="7cb39-286">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="7cb39-287">SSL Web ホスティングのサーバー証明書のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-287">Gets only server certificates for SSL web hosting.</span></span> <span data-ttu-id="7cb39-288">このパラメーターは、プロパティ値に "サーバー認証" が含まれている証明書を取得し `EnhancedKeyUsageList` ます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-288">This parameter gets certificates that have "Server Authentication" in their `EnhancedKeyUsageList` property value.</span></span>

<span data-ttu-id="7cb39-289">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7cb39-289">This parameter was introduced in PowerShell 3.0.</span></span>

## <a name="script-properties"></a><span data-ttu-id="7cb39-290">スクリプトのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7cb39-290">Script properties</span></span>

<span data-ttu-id="7cb39-291">証明書を表す新しいスクリプトプロパティが **x509Certificate2** オブジェクトに追加され、証明書の検索と管理を簡単に行えるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7cb39-291">New script properties have been added to the **x509Certificate2** object that represents the certificates to make it easy to search and manage the certificates.</span></span>

- <span data-ttu-id="7cb39-292">`DnsNameList`: プロパティを設定するために、 `DnsNameList` 証明書プロバイダーは、DNSName エントリ (SAN) 拡張機能のコンテンツをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7cb39-292">`DnsNameList`: To populate the `DnsNameList` property, the Certificate provider copies the content from the DNSName entry in the SubjectAlternativeName (SAN) extension.</span></span> <span data-ttu-id="7cb39-293">SAN 拡張子が空の場合、証明書の Subject フィールドのコンテンツがプロパティに入力されます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-293">If the SAN extension is empty, the property is populated with content from the Subject field of the certificate.</span></span>

- <span data-ttu-id="7cb39-294">`EnhancedKeyUsageList`: プロパティを設定するために、証明書 `EnhancedKeyUsageList` プロバイダーは証明書の EnhancedKeyUsage (EKU) フィールドの OID プロパティをコピーして、そのフレンドリ名を作成します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-294">`EnhancedKeyUsageList`: To populate the `EnhancedKeyUsageList` property, the Certificate provider copies the OID properties of the EnhancedKeyUsage (EKU) field in the certificate and creates a friendly name for it.</span></span>

- <span data-ttu-id="7cb39-295">`SendAsTrustedIssuer`: プロパティを設定するために、証明書 `SendAsTrustedIssuer` プロバイダーは `SendAsTrustedIssuer` 証明書からプロパティをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7cb39-295">`SendAsTrustedIssuer`: To populate the `SendAsTrustedIssuer` property, the Certificate provider copies the `SendAsTrustedIssuer` property from the certificate.</span></span>  <span data-ttu-id="7cb39-296">詳細については、「 [クライアント認証の信頼された発行者の管理](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cb39-296">For more information see [Management of trusted issuers for client authentication](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span></span>

<span data-ttu-id="7cb39-297">これらの新機能を利用すると、DNS 名と有効期限に基づいて証明書を検索したり、拡張キー使用法 (EKU) プロパティの値でクライアントとサーバーの認証証明書を区別したりできます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-297">These new features let you search for certificates based on their DNS names and expiration dates, and distinguish client and server authentication certificates by the value of their Enhanced Key Usage (EKU) properties.</span></span>

## <a name="using-the-pipeline"></a><span data-ttu-id="7cb39-298">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="7cb39-298">Using the pipeline</span></span>

<span data-ttu-id="7cb39-299">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-299">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="7cb39-300">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-300">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="7cb39-301">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cb39-301">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="7cb39-302">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="7cb39-302">Getting help</span></span>

<span data-ttu-id="7cb39-303">PowerShell 3.0 以降では、プロバイダーコマンドレットのヘルプトピックをカスタマイズして、ファイルシステムドライブでそれらのコマンドレットがどのように動作するかを説明できます。</span><span class="sxs-lookup"><span data-stu-id="7cb39-303">Beginning in PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="7cb39-304">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するには、ファイルシステムドライブで [get-help](xref:Microsoft.PowerShell.Core.Get-Help) コマンドを実行するか、のパラメーターを使用して `-Path` `Get-Help` ファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="7cb39-304">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of `Get-Help` to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path cert:
```

## <a name="see-also"></a><span data-ttu-id="7cb39-305">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cb39-305">See also</span></span>

[<span data-ttu-id="7cb39-306">about_Providers</span><span class="sxs-lookup"><span data-stu-id="7cb39-306">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="7cb39-307">about_Signing</span><span class="sxs-lookup"><span data-stu-id="7cb39-307">about_Signing</span></span>](../../Microsoft.PowerShell.Core/About/about_Signing.md)

[<span data-ttu-id="7cb39-308">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="7cb39-308">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)

[<span data-ttu-id="7cb39-309">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="7cb39-309">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[<span data-ttu-id="7cb39-310">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="7cb39-310">Get-PfxCertificate</span></span>](xref:Microsoft.PowerShell.Security.Get-PfxCertificate)
