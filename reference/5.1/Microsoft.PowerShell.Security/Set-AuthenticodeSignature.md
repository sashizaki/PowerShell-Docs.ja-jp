---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AuthenticodeSignature
ms.openlocfilehash: 4ec4261326e43b2f811d201bf45e6854b4f478ea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214208"
---
# <span data-ttu-id="12ea8-103">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="12ea8-103">Set-AuthenticodeSignature</span></span>

## <span data-ttu-id="12ea8-104">概要</span><span class="sxs-lookup"><span data-stu-id="12ea8-104">SYNOPSIS</span></span>
<span data-ttu-id="12ea8-105">[Authenticode](/windows-hardware/drivers/install/authenticode)署名を PowerShell スクリプトまたはその他のファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-105">Adds an [Authenticode](/windows-hardware/drivers/install/authenticode) signature to a PowerShell script or other file.</span></span>

## <span data-ttu-id="12ea8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12ea8-106">SYNTAX</span></span>

### <span data-ttu-id="12ea8-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="12ea8-107">ByPath (Default)</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] [-FilePath] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="12ea8-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="12ea8-108">ByLiteralPath</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -LiteralPath <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="12ea8-109">ByContent</span><span class="sxs-lookup"><span data-stu-id="12ea8-109">ByContent</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -SourcePathOrExtension <String[]>
 -Content <Byte[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="12ea8-110">Description</span><span class="sxs-lookup"><span data-stu-id="12ea8-110">DESCRIPTION</span></span>

<span data-ttu-id="12ea8-111">コマンドレットでは、 `Set-AuthenticodeSignature` Subject Interface Package (SIP) をサポートする任意のファイルに Authenticode 署名を追加します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-111">The `Set-AuthenticodeSignature` cmdlet adds an Authenticode signature to any file that supports Subject Interface Package (SIP).</span></span>

<span data-ttu-id="12ea8-112">PowerShell スクリプトファイルでは、署名は、スクリプトで実行される命令の最後を示すテキストのブロックの形式になります。</span><span class="sxs-lookup"><span data-stu-id="12ea8-112">In a PowerShell script file, the signature takes the form of a block of text that indicates the end of the instructions that are executed in the script.</span></span> <span data-ttu-id="12ea8-113">このコマンドレットが実行されるときにファイル内に署名がある場合、その署名は削除されます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-113">If there is a signature in the file when this cmdlet runs, that signature is removed.</span></span>

## <span data-ttu-id="12ea8-114">例</span><span class="sxs-lookup"><span data-stu-id="12ea8-114">EXAMPLES</span></span>

### <span data-ttu-id="12ea8-115">例 1-ローカル証明書ストアの証明書を使用してスクリプトに署名する</span><span class="sxs-lookup"><span data-stu-id="12ea8-115">Example 1 - Sign a script using a certificate from the local certificate store</span></span>

<span data-ttu-id="12ea8-116">これらのコマンドは、PowerShell 証明書プロバイダーからコード署名証明書を取得し、それを使用して PowerShell スクリプトに署名します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-116">These commands retrieve a code-signing certificate from the PowerShell certificate provider and use it to sign a PowerShell script.</span></span>

```powershell
$cert=Get-ChildItem -Path Cert:\CurrentUser\My -CodeSigningCert
Set-AuthenticodeSignature -FilePath PsTestInternet2.ps1 -Certificate $cert
```

<span data-ttu-id="12ea8-117">最初のコマンドは、 `Get-ChildItem` コマンドレットと PowerShell 証明書プロバイダーを使用して、 `Cert:\CurrentUser\My` 証明書ストアのサブディレクトリにある証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-117">The first command uses the `Get-ChildItem` cmdlet and the PowerShell certificate provider to get the certificates in the `Cert:\CurrentUser\My` subdirectory of the certificate store.</span></span> <span data-ttu-id="12ea8-118">ドライブは、 `Cert:` 証明書プロバイダーによって公開されているドライブです。</span><span class="sxs-lookup"><span data-stu-id="12ea8-118">The `Cert:` drive is the drive exposed by the certificate provider.</span></span> <span data-ttu-id="12ea8-119">**Codesigningcert** パラメーターは、証明書プロバイダーによってのみサポートされます。これにより、取得される証明書は、コード署名権限を持つ証明書に限定されます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-119">The **CodeSigningCert** parameter, which is supported only by the certificate provider, limits the certificates retrieved to those with code-signing authority.</span></span> <span data-ttu-id="12ea8-120">このコマンドは、変数に結果を格納し `$cert` ます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-120">The command stores the result in the `$cert` variable.</span></span>

<span data-ttu-id="12ea8-121">2番目のコマンドは、 `Set-AuthenticodeSignature` コマンドレットを使用してスクリプトに署名し `PSTestInternet2.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-121">The second command uses the `Set-AuthenticodeSignature` cmdlet to sign the `PSTestInternet2.ps1` script.</span></span> <span data-ttu-id="12ea8-122">**FilePath** パラメーターを使用してスクリプトの名前を指定し、 **certificate** パラメーターを使用して、証明書が変数に格納されることを指定し `$cert` ます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-122">It uses the **FilePath** parameter to specify the name of the script and the **Certificate** parameter to specify that the certificate is stored in the `$cert` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="12ea8-123">**Codesigningcert** パラメーターをと共に使用する `Get-ChildItem` と、コード署名権限を持ち、秘密キーを含む証明書のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-123">Using the **CodeSigningCert** parameter with `Get-ChildItem` only returns certificates that have code-signing authority and contain a private key.</span></span> <span data-ttu-id="12ea8-124">秘密キーがない場合、証明書を署名に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="12ea8-124">If there is no private key, the certificates cannot be used for signing.</span></span>

### <span data-ttu-id="12ea8-125">例 2-PFX ファイルの証明書を使用してスクリプトに署名する</span><span class="sxs-lookup"><span data-stu-id="12ea8-125">Example 2 - Sign a script using a certificate from a PFX file</span></span>

<span data-ttu-id="12ea8-126">これらのコマンドは、 `Get-PfxCertificate` コマンドレットを使用してコード署名証明書を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-126">These commands use the `Get-PfxCertificate` cmdlet to load a code signing certificate.</span></span> <span data-ttu-id="12ea8-127">次に、それを使用して PowerShell スクリプトに署名します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-127">Then, use it to sign a PowerShell script.</span></span>

```powershell
$cert = Get-PfxCertificate -FilePath C:\Test\Mysign.pfx
Set-AuthenticodeSignature -FilePath ServerProps.ps1 -Certificate $cert
```

<span data-ttu-id="12ea8-128">最初のコマンドは、 `Get-PfxCertificate` コマンドレットを使用して、C:\Test\MySign.pfx 証明書を変数に読み込み `$cert` ます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-128">The first command uses the `Get-PfxCertificate` cmdlet to load the C:\Test\MySign.pfx certificate into the `$cert` variable.</span></span>

<span data-ttu-id="12ea8-129">2番目のコマンドは、を使用して `Set-AuthenticodeSignature` スクリプトに署名します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-129">The second command uses `Set-AuthenticodeSignature` to sign the script.</span></span> <span data-ttu-id="12ea8-130">の **FilePath** パラメーターでは、 `Set-AuthenticodeSignature` 署名されているスクリプトファイルへのパスを指定します。 **Cert** パラメーターは、 `$cert` 証明書を含む変数をに渡し `Set-AuthenticodeSignature` ます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-130">The **FilePath** parameter of `Set-AuthenticodeSignature` specifies the path to the script file being signed and the **Cert** parameter passes the `$cert` variable containing the certificate to `Set-AuthenticodeSignature`.</span></span>

<span data-ttu-id="12ea8-131">証明書ファイルがパスワードで保護されている場合、PowerShell はパスワードの入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-131">If the certificate file is password protected, PowerShell prompts you for the password.</span></span>

### <span data-ttu-id="12ea8-132">例 3-ルート証明機関を含む署名を追加する</span><span class="sxs-lookup"><span data-stu-id="12ea8-132">Example 3 - Add a signature that includes the root authority</span></span>

<span data-ttu-id="12ea8-133">このコマンドは、信頼チェーンのルート証明機関を含むデジタル署名を追加します。これは、サードパーティのタイムスタンプ サーバーにより署名されます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-133">This command adds a digital signature that includes the root authority in the trust chain, and it is signed by a third-party timestamp server.</span></span>

```powershell
Set-AuthenticodeSignature -FilePath c:\scripts\Remodel.ps1 -Certificate $cert -IncludeChain All -TimestampServer "http://timestamp.fabrikam.com/scripts/timstamper.dll"
```

<span data-ttu-id="12ea8-134">このコマンドは、 **FilePath** パラメーターを使用して署名されるスクリプトを指定し、 **certificate** パラメーターを使用して、変数に保存されている証明書を指定し `$cert` ます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-134">The command uses the **FilePath** parameter to specify the script being signed and the **Certificate** parameter to specify the certificate that is saved in the `$cert` variable.</span></span> <span data-ttu-id="12ea8-135">**IncludeChain** パラメーターを使用して、ルート証明機関を含む、信頼チェーン内のすべての署名を含めます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-135">It uses the **IncludeChain** parameter to include all of the signatures in the trust chain, including the root authority.</span></span> <span data-ttu-id="12ea8-136">また、timestamp **サーバー** パラメーターを使用して、署名にタイムスタンプを追加します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-136">It also uses the **TimeStampServer** parameter to add a timestamp to the signature.</span></span>
<span data-ttu-id="12ea8-137">これにより、証明の有効期限が切れた場合にもスクリプトは失敗しません。</span><span class="sxs-lookup"><span data-stu-id="12ea8-137">This prevents the script from failing when the certificate expires.</span></span>

## <span data-ttu-id="12ea8-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12ea8-138">PARAMETERS</span></span>

### <span data-ttu-id="12ea8-139">-証明書</span><span class="sxs-lookup"><span data-stu-id="12ea8-139">-Certificate</span></span>

<span data-ttu-id="12ea8-140">スクリプトまたはファイルへの署名に使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-140">Specifies the certificate that will be used to sign the script or file.</span></span> <span data-ttu-id="12ea8-141">証明書を表すオブジェクトを格納する変数、または証明書を取得する式を入力します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-141">Enter a variable that stores an object representing the certificate or an expression that gets the certificate.</span></span>

<span data-ttu-id="12ea8-142">証明書を検索するには、を使用する `Get-PfxCertificate` か、 `Get-ChildItem` 証明書ドライブのコマンドレットを使用し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-142">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate `Cert:` drive.</span></span> <span data-ttu-id="12ea8-143">証明書が有効でない場合、または権限を持っていない場合 `code-signing` 、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-143">If the certificate is not valid or does not have `code-signing` authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12ea8-144">-FilePath</span><span class="sxs-lookup"><span data-stu-id="12ea8-144">-FilePath</span></span>

<span data-ttu-id="12ea8-145">署名するファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-145">Specifies the path to a file that is being signed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="12ea8-146">-Force</span><span class="sxs-lookup"><span data-stu-id="12ea8-146">-Force</span></span>

<span data-ttu-id="12ea8-147">コマンドレットで読み取り専用ファイルに署名を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="12ea8-147">Allows the cmdlet to append a signature to a read-only file.</span></span> <span data-ttu-id="12ea8-148">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="12ea8-148">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="12ea8-149">-HashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="12ea8-149">-HashAlgorithm</span></span>

<span data-ttu-id="12ea8-150">Windows でファイルのデジタル署名の計算に使用されるハッシュ アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-150">Specifies the hashing algorithm that Windows uses to compute the digital signature for the file.</span></span>

<span data-ttu-id="12ea8-151">PowerShell 3.0 の既定値は SHA256 で、これは Windows の既定のハッシュアルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="12ea8-151">For PowerShell 3.0, the default is SHA256, which is the Windows default hashing algorithm.</span></span> <span data-ttu-id="12ea8-152">PowerShell 2.0 の場合、既定値は SHA1 です。</span><span class="sxs-lookup"><span data-stu-id="12ea8-152">For PowerShell 2.0, the default is SHA1.</span></span> <span data-ttu-id="12ea8-153">異なるハッシュ アルゴリズムで署名されたファイルは、他のシステムで認識されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12ea8-153">Files that are signed with a different hashing algorithm might not be recognized on other systems.</span></span> <span data-ttu-id="12ea8-154">サポートされるアルゴリズムは、オペレーティングシステムのバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="12ea8-154">Which algorithms are supported depends on the version of the operating system.</span></span>

<span data-ttu-id="12ea8-155">使用可能な値の一覧については、「 [2Csystem.security.cryptography.hashalgorithmname Struct](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ea8-155">For a list of possible values, see [HashAlgorithmName Struct](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SHA256
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12ea8-156">-IncludeChain</span><span class="sxs-lookup"><span data-stu-id="12ea8-156">-IncludeChain</span></span>

<span data-ttu-id="12ea8-157">証明書の信頼チェーン内のどの証明書がデジタル署名に含まれているかを判断します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-157">Determines which certificates in the certificate trust chain are included in the digital signature.</span></span>
<span data-ttu-id="12ea8-158">**Notroot** が既定値です。</span><span class="sxs-lookup"><span data-stu-id="12ea8-158">**NotRoot** is the default.</span></span>

<span data-ttu-id="12ea8-159">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="12ea8-159">Valid values are:</span></span>

- <span data-ttu-id="12ea8-160">署名者: 署名者の証明書のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-160">Signer: Includes only the signer's certificate.</span></span>
- <span data-ttu-id="12ea8-161">NotRoot: ルート証明機関を除く、証明書チェーン内のすべての証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-161">NotRoot: Includes all of the certificates in the certificate chain, except for the root authority.</span></span>
- <span data-ttu-id="12ea8-162">All: 証明書チェーン内のすべての証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-162">All: Includes all the certificates in the certificate chain.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NotRoot
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12ea8-163">-タイムスタンプサーバー</span><span class="sxs-lookup"><span data-stu-id="12ea8-163">-TimestampServer</span></span>

<span data-ttu-id="12ea8-164">指定されたタイム スタンプ サーバーを使用して、署名にタイム スタンプを追加します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-164">Uses the specified time stamp server to add a time stamp to the signature.</span></span> <span data-ttu-id="12ea8-165">タイム スタンプ サーバーの URL を文字列として入力します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-165">Type the URL of the time stamp server as a string.</span></span>

<span data-ttu-id="12ea8-166">タイム スタンプは、証明書がファイルに追加された正確な時間を表します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-166">The time stamp represents the exact time that the certificate was added to the file.</span></span> <span data-ttu-id="12ea8-167">タイム スタンプを使用すると、署名時に証明書が有効だったことをユーザーとプログラムで検証できるため、証明書の期限が過ぎている場合であってもスクリプトは失敗しません。</span><span class="sxs-lookup"><span data-stu-id="12ea8-167">A time stamp prevents the script from failing if the certificate expires because users and programs can verify that the certificate was valid at the time of signing.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12ea8-168">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="12ea8-168">-LiteralPath</span></span>

<span data-ttu-id="12ea8-169">署名するファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-169">Specifies the path to a file that is being signed.</span></span> <span data-ttu-id="12ea8-170">**FilePath** とは異なり、 **LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-170">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="12ea8-171">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="12ea8-171">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="12ea8-172">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-172">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="12ea8-173">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="12ea8-173">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="12ea8-174">-SourcePathOrExtension</span><span class="sxs-lookup"><span data-stu-id="12ea8-174">-SourcePathOrExtension</span></span>

<span data-ttu-id="12ea8-175">デジタル署名が追加されるコンテンツのファイルまたはファイルの種類へのパス。</span><span class="sxs-lookup"><span data-stu-id="12ea8-175">Path to the file or file type of the content for which the digital signature is added.</span></span> <span data-ttu-id="12ea8-176">このパラメーターは、ファイルの内容がバイト配列として渡される **コンテンツ** で使用されます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-176">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="12ea8-177">-コンテンツ</span><span class="sxs-lookup"><span data-stu-id="12ea8-177">-Content</span></span>

<span data-ttu-id="12ea8-178">デジタル署名が追加されるバイト配列としてのファイルの内容。</span><span class="sxs-lookup"><span data-stu-id="12ea8-178">Contents of a file as a byte array for which the digital signature is added.</span></span> <span data-ttu-id="12ea8-179">このパラメーターは、 **Sourcepathorextension** パラメーターと共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12ea8-179">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="12ea8-180">ファイルの内容は Unicode (16LE) 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="12ea8-180">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="12ea8-181">-Confirm</span><span class="sxs-lookup"><span data-stu-id="12ea8-181">-Confirm</span></span>

<span data-ttu-id="12ea8-182">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-182">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="12ea8-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="12ea8-183">-WhatIf</span></span>

<span data-ttu-id="12ea8-184">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="12ea8-184">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="12ea8-185">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="12ea8-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="12ea8-186">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="12ea8-186">CommonParameters</span></span>

<span data-ttu-id="12ea8-187">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="12ea8-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12ea8-188">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ea8-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="12ea8-189">入力</span><span class="sxs-lookup"><span data-stu-id="12ea8-189">INPUTS</span></span>

### <span data-ttu-id="12ea8-190">System.String</span><span class="sxs-lookup"><span data-stu-id="12ea8-190">System.String</span></span>

<span data-ttu-id="12ea8-191">パイプを使用して、ファイルパスを含む文字列をにパイプすることができ `Set-AuthenticodeSignature` ます。</span><span class="sxs-lookup"><span data-stu-id="12ea8-191">You can pipe a string that contains the file path to `Set-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="12ea8-192">出力</span><span class="sxs-lookup"><span data-stu-id="12ea8-192">OUTPUTS</span></span>

### <span data-ttu-id="12ea8-193">システム... Automation. 署名</span><span class="sxs-lookup"><span data-stu-id="12ea8-193">System.Management.Automation.Signature</span></span>

## <span data-ttu-id="12ea8-194">注</span><span class="sxs-lookup"><span data-stu-id="12ea8-194">NOTES</span></span>

## <span data-ttu-id="12ea8-195">関連リンク</span><span class="sxs-lookup"><span data-stu-id="12ea8-195">RELATED LINKS</span></span>

[<span data-ttu-id="12ea8-196">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="12ea8-196">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="12ea8-197">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="12ea8-197">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="12ea8-198">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="12ea8-198">Get-PfxCertificate</span></span>](Get-PfxCertificate.md)

[<span data-ttu-id="12ea8-199">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="12ea8-199">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="12ea8-200">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="12ea8-200">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="12ea8-201">about_Signing</span><span class="sxs-lookup"><span data-stu-id="12ea8-201">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
