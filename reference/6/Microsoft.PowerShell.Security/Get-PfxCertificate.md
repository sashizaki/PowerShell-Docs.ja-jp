---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: 67bb56a50f452475ba12abb2fccaeeaf5785c8b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216899"
---
# <span data-ttu-id="2368c-103">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="2368c-103">Get-PfxCertificate</span></span>

## <span data-ttu-id="2368c-104">概要</span><span class="sxs-lookup"><span data-stu-id="2368c-104">SYNOPSIS</span></span>
<span data-ttu-id="2368c-105">コンピューター上の PFX 証明書ファイルに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2368c-105">Gets information about PFX certificate files on the computer.</span></span>

## <span data-ttu-id="2368c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2368c-106">SYNTAX</span></span>

### <span data-ttu-id="2368c-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="2368c-107">ByPath (Default)</span></span>

```
Get-PfxCertificate [-FilePath] <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

### <span data-ttu-id="2368c-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="2368c-108">ByLiteralPath</span></span>

```
Get-PfxCertificate -LiteralPath <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

## <span data-ttu-id="2368c-109">Description</span><span class="sxs-lookup"><span data-stu-id="2368c-109">DESCRIPTION</span></span>

<span data-ttu-id="2368c-110">`Get-PfxCertificate`コマンドレットは、指定された各 PFX 証明書ファイルを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="2368c-110">The `Get-PfxCertificate` cmdlet gets an object representing each specified PFX certificate file.</span></span>
<span data-ttu-id="2368c-111">PFX ファイルには、証明書と秘密キーの両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2368c-111">A PFX file includes both the certificate and a private key.</span></span>

## <span data-ttu-id="2368c-112">例</span><span class="sxs-lookup"><span data-stu-id="2368c-112">EXAMPLES</span></span>

### <span data-ttu-id="2368c-113">例 1: PFX 証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="2368c-113">Example 1: Get a PFX certificate</span></span>

```powershell
Get-PfxCertificate -FilePath "C:\windows\system32\Test.pfx"
```

```output
Password: ******
Signer Certificate:      David Chew (Self Certificate)
Time Certificate:
Time Stamp:
Path:                    C:\windows\system32\zap.pfx
```

<span data-ttu-id="2368c-114">このコマンドは、システム上のテスト .pfx 証明書ファイルに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2368c-114">This command gets information about the Test.pfx certificate file on the system.</span></span>

### <span data-ttu-id="2368c-115">例 2: リモートコンピューターから PFX 証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="2368c-115">Example 2: Get a PFX certificate from a remote computer</span></span>

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

<span data-ttu-id="2368c-116">このコマンドは、Server01 リモートコンピューターから PFX 証明書ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="2368c-116">This command gets a PFX certificate file from the Server01 remote computer.</span></span> <span data-ttu-id="2368c-117">を使用して `Invoke-Command` `Get-PfxCertificate` コマンドをリモートで実行します。</span><span class="sxs-lookup"><span data-stu-id="2368c-117">It uses `Invoke-Command` to run a `Get-PfxCertificate` command remotely.</span></span>

<span data-ttu-id="2368c-118">PFX 証明書ファイルがパスワードで保護されていない場合、の **Authentication** パラメーターの値は `Invoke-Command` CredSSP である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2368c-118">When the PFX certificate file is not password-protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="2368c-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2368c-119">PARAMETERS</span></span>

### <span data-ttu-id="2368c-120">-FilePath</span><span class="sxs-lookup"><span data-stu-id="2368c-120">-FilePath</span></span>

<span data-ttu-id="2368c-121">セキュリティで保護されたファイルの PFX ファイルへの完全パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2368c-121">Specifies the full path to the PFX file of the secured file.</span></span> <span data-ttu-id="2368c-122">このパラメーターの値を指定する場合は、コマンドラインでを入力する必要はありません `-FilePath` 。</span><span class="sxs-lookup"><span data-stu-id="2368c-122">If you specify a value for this parameter, it is not necessary to type `-FilePath` at the command line.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2368c-123">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2368c-123">-LiteralPath</span></span>

<span data-ttu-id="2368c-124">セキュリティで保護されたファイルの PFX ファイルへの完全パスです。</span><span class="sxs-lookup"><span data-stu-id="2368c-124">The full path to the PFX file of the secured file.</span></span> <span data-ttu-id="2368c-125">**FilePath** とは異なり、 **LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2368c-125">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="2368c-126">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="2368c-126">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2368c-127">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="2368c-127">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="2368c-128">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="2368c-128">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="2368c-129">-NoPromptForPassword</span><span class="sxs-lookup"><span data-stu-id="2368c-129">-NoPromptForPassword</span></span>

<span data-ttu-id="2368c-130">パスワードの入力を求めるメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="2368c-130">Suppresses prompting for a password.</span></span>

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

### <span data-ttu-id="2368c-131">-Password</span><span class="sxs-lookup"><span data-stu-id="2368c-131">-Password</span></span>

<span data-ttu-id="2368c-132">証明書ファイルにアクセスするために必要なパスワードを指定し `.pfx` ます。</span><span class="sxs-lookup"><span data-stu-id="2368c-132">Specifies a password required to access a `.pfx` certificate file.</span></span>

<span data-ttu-id="2368c-133">このパラメーターは、PowerShell 6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2368c-133">This parameter was introduced in PowerShell 6.1.</span></span>

> [!NOTE]
> <span data-ttu-id="2368c-134">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2368c-134">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2368c-135">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2368c-135">CommonParameters</span></span>

<span data-ttu-id="2368c-136">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2368c-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2368c-137">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2368c-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2368c-138">入力</span><span class="sxs-lookup"><span data-stu-id="2368c-138">INPUTS</span></span>

### <span data-ttu-id="2368c-139">System.String</span><span class="sxs-lookup"><span data-stu-id="2368c-139">System.String</span></span>

<span data-ttu-id="2368c-140">パイプを使用して、ファイルパスを含む文字列をにパイプすることができ `Get-PfxCertificate` ます。</span><span class="sxs-lookup"><span data-stu-id="2368c-140">You can pipe a string that contains a file path to `Get-PfxCertificate`.</span></span>

## <span data-ttu-id="2368c-141">出力</span><span class="sxs-lookup"><span data-stu-id="2368c-141">OUTPUTS</span></span>

### <span data-ttu-id="2368c-142">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="2368c-142">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>

<span data-ttu-id="2368c-143">`Get-PfxCertificate` 取得した証明書ごとにオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2368c-143">`Get-PfxCertificate` returns an object for each certificate that it gets.</span></span>

## <span data-ttu-id="2368c-144">注</span><span class="sxs-lookup"><span data-stu-id="2368c-144">NOTES</span></span>

<span data-ttu-id="2368c-145">コマンドレットを使用して `Invoke-Command` コマンドをリモートで実行 `Get-PfxCertificate` し、PFX 証明書ファイルがパスワードで保護されていない場合、の **Authentication** パラメーターの値は `Invoke-Command` CredSSP である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2368c-145">When using the `Invoke-Command` cmdlet to run a `Get-PfxCertificate` command remotely, and the PFX certificate file is not password protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="2368c-146">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2368c-146">RELATED LINKS</span></span>

[<span data-ttu-id="2368c-147">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="2368c-147">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="2368c-148">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="2368c-148">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)
