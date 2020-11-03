---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-cmsmessage?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CmsMessage
ms.openlocfilehash: 30e70549b648f7fb63bb250744cf52f0979c201f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214987"
---
# <span data-ttu-id="bcc8e-103">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="bcc8e-103">Get-CmsMessage</span></span>

## <span data-ttu-id="bcc8e-104">概要</span><span class="sxs-lookup"><span data-stu-id="bcc8e-104">SYNOPSIS</span></span>
<span data-ttu-id="bcc8e-105">暗号化メッセージ構文形式を使用して暗号化されたコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-105">Gets content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="bcc8e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bcc8e-106">SYNTAX</span></span>

### <span data-ttu-id="bcc8e-107">ByContent</span><span class="sxs-lookup"><span data-stu-id="bcc8e-107">ByContent</span></span>

```
Get-CmsMessage [-Content] <String> [<CommonParameters>]
```

### <span data-ttu-id="bcc8e-108">ByPath</span><span class="sxs-lookup"><span data-stu-id="bcc8e-108">ByPath</span></span>

```
Get-CmsMessage [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="bcc8e-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="bcc8e-109">ByLiteralPath</span></span>

```
Get-CmsMessage [-LiteralPath] <String> [<CommonParameters>]
```

## <span data-ttu-id="bcc8e-110">Description</span><span class="sxs-lookup"><span data-stu-id="bcc8e-110">DESCRIPTION</span></span>

<span data-ttu-id="bcc8e-111">`Get-CmsMessage`コマンドレットでは、暗号化メッセージ構文 (CMS) 形式を使用して暗号化されたコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-111">The `Get-CmsMessage` cmdlet gets content that has been encrypted using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="bcc8e-112">CMS コマンドレットは、 [RFC5652](https://tools.ietf.org/html/rfc5652)によって説明されているように、メッセージを暗号化して保護するための IETF 形式を使用したコンテンツの暗号化と暗号化解除をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-112">The CMS cmdlets support encryption and decryption of content using the IETF format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="bcc8e-113">CMS 暗号化標準では、公開キー暗号化を使用します。この暗号化では、コンテンツの暗号化に使用されるキー (公開キー) とコンテンツの暗号化を解除するために使用されるキー (秘密キー) は区別されます。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="bcc8e-114">公開キーは広く共有でき、機密性の高いデータではありません。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="bcc8e-115">いずれかのコンテンツがこの公開キーで暗号化された場合、秘密キーのみが暗号化を解除できます。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="bcc8e-116">公開キー暗号化の詳細については、「[公開鍵暗号](https://en.wikipedia.org/wiki/Public-key_cryptography)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="bcc8e-117">`Get-CmsMessage` CMS 形式で暗号化されたコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-117">`Get-CmsMessage` gets content that has been encrypted in CMS format.</span></span> <span data-ttu-id="bcc8e-118">コンテンツの暗号化を解除したり保護を解除したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-118">It does not decrypt or unprotect content.</span></span> <span data-ttu-id="bcc8e-119">このコマンドレットを実行すると、暗号化されたコンテンツを取得できます。そのためには、コマンドレットを実行し `Protect-CmsMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-119">You can run this cmdlet to get content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="bcc8e-120">暗号化を解除するコンテンツを文字列として指定することも、暗号化されたコンテンツへのパスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-120">You can specify content that you want to decrypt as a string, or by path to the encrypted content.</span></span> <span data-ttu-id="bcc8e-121">`Get-CmsMessage` `Unprotect-CmsMessage` コンテンツの暗号化に使用されたドキュメント暗号化証明書に関する情報がある場合は、の結果をにパイプして、コンテンツの暗号化を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-121">You can pipe the results of `Get-CmsMessage` to `Unprotect-CmsMessage` to decrypt the content, provided that you have information about the document encryption certificate that was used to encrypt the content.</span></span>

> [!NOTE]
> <span data-ttu-id="bcc8e-122">このコマンドレットは、Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-122">This cmdlet is only available on Windows.</span></span>

## <span data-ttu-id="bcc8e-123">例</span><span class="sxs-lookup"><span data-stu-id="bcc8e-123">EXAMPLES</span></span>

### <span data-ttu-id="bcc8e-124">例 1: 暗号化されたコンテンツを取得する</span><span class="sxs-lookup"><span data-stu-id="bcc8e-124">Example 1: Get encrypted content</span></span>

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg.Content
```

```Output
-----BEGIN CMS-----
MIIBqAYJKoZIhvcNAQcDoIIBmTCCAZUCAQAxggFQMIIBTAIBADA0MCAxHjAcBgNVBAMBFWxlZWhv
bG1AbGljcm9zb2Z0LmNvbQIQQYHsbcXnjIJCtH+OhGmc1DANBgkqhkiG9w0BAQcwAASCAQAnkFHM
proJnFy4geFGfyNmxH3yeoPvwEYzdnsoVqqDPAd8D3wao77z7OhJEXwz9GeFLnxD6djKV/tF4PxR
E27aduKSLbnxfpf/sepZ4fUkuGibnwWFrxGE3B1G26MCenHWjYQiqv+Nq32Gc97qEAERrhLv6S4R
G+2dJEnesW8A+z9QPo+DwYP5FzD0Td0ExrkswVckpLNR6j17Yaags3ltNXmbdEXekhi6Psf2MLMP
TSO79lv2L0KeXFGuPOrdzPRwCkV0vNEqTEBeDnZGrjv/5766bM3GW34FXApod9u+VSFpBnqVOCBA
DVDraA6k+xwBt66cV84AHLkh0kT02SIHMDwGCSqGSIb3DQEHATAdBglghkgBZQMEASoEEJbJaiRl
KMnBoD1dkb/FzSWAEBaL8xkFwCu0e1AtDj7nSJc=
-----END CMS-----
```

<span data-ttu-id="bcc8e-125">このコマンドは、C:\Users\Test\Documents\PowerShell\Future_Plans.txt にある暗号化されたコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-125">This command gets encrypted content located at C:\Users\Test\Documents\PowerShell\Future_Plans.txt.</span></span>

### <span data-ttu-id="bcc8e-126">例 2: パイプで暗号化されたコンテンツを Unprotect-CmsMessage に</span><span class="sxs-lookup"><span data-stu-id="bcc8e-126">Example 2: Pipe encrypted content to Unprotect-CmsMessage</span></span>

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg | Unprotect-CmsMessage -To "cn=youralias@emailaddress.com"
```

```Output
Try the new Break All command
```

<span data-ttu-id="bcc8e-127">このコマンドは、コマンドレットの結果を `Get-CmsMessage` 例1からにパイプし、 `Unprotect-CmsMessage` メッセージの暗号化を解除してプレーンテキストで読み取ります。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-127">This command pipes the results of the `Get-CmsMessage` cmdlet from Example 1 to `Unprotect-CmsMessage`, to decrypt the message and read it in plain text.</span></span> <span data-ttu-id="bcc8e-128">この場合、 **To** パラメーターの値は、暗号化された証明書の件名行の値になります。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-128">In this case, the value of the **To** parameter is the value of the encrypting certificate's Subject line.</span></span> <span data-ttu-id="bcc8e-129">暗号化が解除されたことを示します。 "新しい Break All コマンドを試してください" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-129">The decrypted message, "Try the new Break All command," is the result.</span></span>

## <span data-ttu-id="bcc8e-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bcc8e-130">PARAMETERS</span></span>

### <span data-ttu-id="bcc8e-131">-コンテンツ</span><span class="sxs-lookup"><span data-stu-id="bcc8e-131">-Content</span></span>

<span data-ttu-id="bcc8e-132">暗号化された文字列、または暗号化された文字列を含む変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-132">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

```yaml
Type: System.String
Parameter Sets: ByContent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bcc8e-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bcc8e-133">-LiteralPath</span></span>

<span data-ttu-id="bcc8e-134">取得する暗号化されたコンテンツへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-134">Specifies the path to encrypted content that you want to get.</span></span> <span data-ttu-id="bcc8e-135">**Path** とは異なり、 **LiteralPath** の値は入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-135">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="bcc8e-136">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-136">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="bcc8e-137">パスにエスケープ文字が含まれている場合は、それぞれを単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-137">If the path includes escape characters, enclose each one in single quotation marks.</span></span>
<span data-ttu-id="bcc8e-138">単一引用符で囲まれた文字はエスケープ文字として解釈されません。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-138">Single quotation marks tell PowerShell not to interpret enclosed characters as escape characters.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcc8e-139">-Path</span><span class="sxs-lookup"><span data-stu-id="bcc8e-139">-Path</span></span>

<span data-ttu-id="bcc8e-140">暗号化を解除する暗号化されたコンテンツへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-140">Specifies the path to encrypted content that you want to decrypt.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcc8e-141">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcc8e-141">CommonParameters</span></span>

<span data-ttu-id="bcc8e-142">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bcc8e-143">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8e-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bcc8e-144">入力</span><span class="sxs-lookup"><span data-stu-id="bcc8e-144">INPUTS</span></span>

## <span data-ttu-id="bcc8e-145">出力</span><span class="sxs-lookup"><span data-stu-id="bcc8e-145">OUTPUTS</span></span>

## <span data-ttu-id="bcc8e-146">注</span><span class="sxs-lookup"><span data-stu-id="bcc8e-146">NOTES</span></span>

## <span data-ttu-id="bcc8e-147">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bcc8e-147">RELATED LINKS</span></span>

[<span data-ttu-id="bcc8e-148">about_Providers</span><span class="sxs-lookup"><span data-stu-id="bcc8e-148">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="bcc8e-149">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="bcc8e-149">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)

[<span data-ttu-id="bcc8e-150">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="bcc8e-150">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
