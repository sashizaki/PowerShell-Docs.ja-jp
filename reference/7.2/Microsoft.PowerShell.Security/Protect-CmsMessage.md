---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/protect-cmsmessage?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Protect-CmsMessage
ms.openlocfilehash: 57213b72bee5733f6e8089ff7dcbb9be82104d8a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601021"
---
# <span data-ttu-id="868d4-102">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="868d4-102">Protect-CmsMessage</span></span>

## <span data-ttu-id="868d4-103">概要</span><span class="sxs-lookup"><span data-stu-id="868d4-103">SYNOPSIS</span></span>
<span data-ttu-id="868d4-104">暗号化メッセージ構文形式を使用してコンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="868d4-104">Encrypts content by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="868d4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="868d4-105">SYNTAX</span></span>

### <span data-ttu-id="868d4-106">ByContent (既定)</span><span class="sxs-lookup"><span data-stu-id="868d4-106">ByContent (Default)</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <PSObject> [[-OutFile] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="868d4-107">ByPath</span><span class="sxs-lookup"><span data-stu-id="868d4-107">ByPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <String> [[-OutFile] <String>] [<CommonParameters>]
```

### <span data-ttu-id="868d4-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="868d4-108">ByLiteralPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <String> [[-OutFile] <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="868d4-109">Description</span><span class="sxs-lookup"><span data-stu-id="868d4-109">DESCRIPTION</span></span>

<span data-ttu-id="868d4-110">コマンドレットでは、 `Protect-CmsMessage` 暗号化メッセージ構文 (CMS) 形式を使用してコンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="868d4-110">The `Protect-CmsMessage` cmdlet encrypts content by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="868d4-111">CMS コマンドレットは、 [RFC5652](https://tools.ietf.org/html/rfc5652.html)によって説明されているように、IETF 形式を使用したコンテンツの暗号化と暗号化解除をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="868d4-111">The CMS cmdlets support encryption and decryption of content using the IETF format as documented by [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span></span>

<span data-ttu-id="868d4-112">CMS 暗号化標準では、公開キー暗号化を使用します。この暗号化では、コンテンツの暗号化に使用されるキー (公開キー) とコンテンツの暗号化を解除するために使用されるキー (秘密キー) は区別されます。</span><span class="sxs-lookup"><span data-stu-id="868d4-112">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="868d4-113">公開キーは広く共有でき、機密性の高いデータではありません。</span><span class="sxs-lookup"><span data-stu-id="868d4-113">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="868d4-114">いずれかのコンテンツがこの公開キーで暗号化された場合、秘密キーのみが暗号化を解除できます。</span><span class="sxs-lookup"><span data-stu-id="868d4-114">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="868d4-115">公開キー暗号化の詳細については、「[公開鍵暗号](https://en.wikipedia.org/wiki/Public-key_cryptography)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="868d4-115">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="868d4-116">コマンドレットを実行するには、事前に `Protect-CmsMessage` 暗号化証明書を設定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="868d4-116">Before you can run the `Protect-CmsMessage` cmdlet, you must have an encryption certificate set up.</span></span>
<span data-ttu-id="868d4-117">PowerShell で認識されるようにするには、暗号化証明書をデータ暗号化証明書として識別するために一意の拡張キー使用法 ([EKU](/windows/desktop/SecCrypto/eku)) ID が必要です (コード署名および暗号化されたメールの id など)。</span><span class="sxs-lookup"><span data-stu-id="868d4-117">To be recognized in PowerShell, encryption certificates require a unique extended key usage ([EKU](/windows/desktop/SecCrypto/eku)) ID to identify them as data encryption certificates (such as the IDs for Code Signing and Encrypted Mail).</span></span> <span data-ttu-id="868d4-118">ドキュメントの暗号化に使用する証明書の例については、このトピックの例1を参照してください。</span><span class="sxs-lookup"><span data-stu-id="868d4-118">For an example of a certificate that would work for document encryption, see Example 1 in this topic.</span></span>

<span data-ttu-id="868d4-119">PowerShell 7.1 では、Linux と macOS のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="868d4-119">Support for Linux and macOS was added in PowerShell 7.1.</span></span>

## <span data-ttu-id="868d4-120">例</span><span class="sxs-lookup"><span data-stu-id="868d4-120">EXAMPLES</span></span>

### <span data-ttu-id="868d4-121">例 1: コンテンツを暗号化するための証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="868d4-121">Example 1: Create a certificate for encrypting content</span></span>

<span data-ttu-id="868d4-122">コマンドレットを実行する前に `Protect-CmsMessage` 、暗号化証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="868d4-122">Before you can run the `Protect-CmsMessage` cmdlet, you must create an encryption certificate.</span></span> <span data-ttu-id="868d4-123">次のテキストを使用して、件名行の名前を名前、電子メール、またはその他の識別子に変更し、証明書をファイルに保存し `DocumentEncryption.inf` ます (この例で示すように)。</span><span class="sxs-lookup"><span data-stu-id="868d4-123">Using the following text, change the name in the Subject line to your name, email, or other identifier, and save the certificate in a file (such as `DocumentEncryption.inf`, as shown in this example).</span></span>

```powershell
# Create .INF file for certreq
{[Version]
Signature = "$Windows NT$"

[Strings]
szOID_ENHANCED_KEY_USAGE = "2.5.29.37"
szOID_DOCUMENT_ENCRYPTION = "1.3.6.1.4.1.311.80.1"

[NewRequest]
Subject = "cn=youralias@emailaddress.com"
MachineKeySet = false
KeyLength = 2048
KeySpec = AT_KEYEXCHANGE
HashAlgorithm = Sha1
Exportable = true
RequestType = Cert
KeyUsage = "CERT_KEY_ENCIPHERMENT_KEY_USAGE | CERT_DATA_ENCIPHERMENT_KEY_USAGE"
ValidityPeriod = "Years"
ValidityPeriodUnits = "1000"

[Extensions]
%szOID_ENHANCED_KEY_USAGE% = "{text}%szOID_DOCUMENT_ENCRYPTION%"
} | Out-File -FilePath DocumentEncryption.inf

# After you have created your certificate file, run the following command to add
# the certificate file to the certificate store. Now you are ready to encrypt and
# decrypt content with the next two examples.
certreq.exe -new DocumentEncryption.inf DocumentEncryption.cer
```

### <span data-ttu-id="868d4-124">例 2: 電子メールで送信されたメッセージを暗号化する</span><span class="sxs-lookup"><span data-stu-id="868d4-124">Example 2: Encrypt a message sent by email</span></span>

```powershell
$Protected = "Hello World" | Protect-CmsMessage -To "*youralias@emailaddress.com*"
```

<span data-ttu-id="868d4-125">次の例では、メッセージ "Hello World" をコマンドレットにパイプして暗号化し、 `Protect-CmsMessage` 暗号化されたメッセージを変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="868d4-125">In the following example, you encrypt a message, "Hello World", by piping it to the `Protect-CmsMessage` cmdlet, and then save the encrypted message in a variable.</span></span> <span data-ttu-id="868d4-126">**To** パラメーターは、証明書の Subject 行の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="868d4-126">The **To** parameter uses the value of the Subject line in the certificate.</span></span>

### <span data-ttu-id="868d4-127">例 3: ドキュメントの暗号化証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="868d4-127">Example 3: View document encryption certificates</span></span>

```
PS C:\> cd Cert:\CurrentUser\My
PS Cert:\CurrentUser\My> Get-ChildItem -DocumentEncryptionCert
```

<span data-ttu-id="868d4-128">証明書プロバイダーでドキュメントの暗号化証明書を表示するには、 [get-childitem](../Microsoft.PowerShell.Management/Get-ChildItem.md)の **documentencryptioncert** 動的パラメーターを追加します。このパラメーターは、証明書プロバイダーが読み込まれたときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="868d4-128">To view document encryption certificates in the certificate provider, you can add the **DocumentEncryptionCert** dynamic parameter of [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md), available only when the certificate provider is loaded.</span></span>

## <span data-ttu-id="868d4-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="868d4-129">PARAMETERS</span></span>

### <span data-ttu-id="868d4-130">-コンテンツ</span><span class="sxs-lookup"><span data-stu-id="868d4-130">-Content</span></span>

<span data-ttu-id="868d4-131">暗号化するコンテンツを含む **PSObject** を指定します。</span><span class="sxs-lookup"><span data-stu-id="868d4-131">Specifies a **PSObject** that contains content that you want to encrypt.</span></span> <span data-ttu-id="868d4-132">たとえば、イベントメッセージの内容を暗号化し、そのメッセージを含む変数 ( `$Event` この例では) を **content** パラメーターの値として使用できます `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1` 。</span><span class="sxs-lookup"><span data-stu-id="868d4-132">For example, you can encrypt the content of an event message, and then use the variable containing the message (`$Event`, in this example) as the value of the **Content** parameter: `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1`.</span></span> <span data-ttu-id="868d4-133">また、コマンドレットを使用し `Get-Content` て、Microsoft Word 文書などのファイルの内容を取得し **、content** パラメーターの値として使用する変数にコンテンツを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="868d4-133">You can also use the `Get-Content` cmdlet to get the contents of a file, such as a Microsoft Word document, and save the content in a variable that you use as the value of the **Content** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByContent
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="868d4-134">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="868d4-134">-LiteralPath</span></span>

<span data-ttu-id="868d4-135">暗号化するコンテンツへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="868d4-135">Specifies the path to content that you want to encrypt.</span></span> <span data-ttu-id="868d4-136">**Path** とは異なり、**LiteralPath** の値は入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="868d4-136">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="868d4-137">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="868d4-137">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="868d4-138">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="868d4-138">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="868d4-139">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="868d4-139">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="868d4-140">-出力</span><span class="sxs-lookup"><span data-stu-id="868d4-140">-OutFile</span></span>

<span data-ttu-id="868d4-141">暗号化されたコンテンツを送信するファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="868d4-141">Specifies the path and file name of a file to which you want to send the encrypted content.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="868d4-142">-Path</span><span class="sxs-lookup"><span data-stu-id="868d4-142">-Path</span></span>

<span data-ttu-id="868d4-143">暗号化するコンテンツへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="868d4-143">Specifies the path to content that you want to encrypt.</span></span>

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

### <span data-ttu-id="868d4-144">-To</span><span class="sxs-lookup"><span data-stu-id="868d4-144">-To</span></span>

<span data-ttu-id="868d4-145">次のいずれかの形式で識別される、1つまたは複数の CMS メッセージ受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="868d4-145">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="868d4-146">(証明書プロバイダーから取得された) 実際の証明書。</span><span class="sxs-lookup"><span data-stu-id="868d4-146">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="868d4-147">証明書を含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="868d4-147">Path to the file containing the certificate.</span></span>
- <span data-ttu-id="868d4-148">証明書が格納されているディレクトリへのパス。</span><span class="sxs-lookup"><span data-stu-id="868d4-148">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="868d4-149">証明書の拇印 (証明書ストアを検索するために使用されます)。</span><span class="sxs-lookup"><span data-stu-id="868d4-149">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="868d4-150">証明書のサブジェクト名 (証明書ストアを検索するために使用されます)。</span><span class="sxs-lookup"><span data-stu-id="868d4-150">Subject name of the certificate (used to look in the certificate store).</span></span>

```yaml
Type: System.Management.Automation.CmsMessageRecipient[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="868d4-151">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="868d4-151">CommonParameters</span></span>

<span data-ttu-id="868d4-152">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="868d4-152">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="868d4-153">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="868d4-153">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="868d4-154">入力</span><span class="sxs-lookup"><span data-stu-id="868d4-154">INPUTS</span></span>

## <span data-ttu-id="868d4-155">出力</span><span class="sxs-lookup"><span data-stu-id="868d4-155">OUTPUTS</span></span>

## <span data-ttu-id="868d4-156">注</span><span class="sxs-lookup"><span data-stu-id="868d4-156">NOTES</span></span>

## <span data-ttu-id="868d4-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="868d4-157">RELATED LINKS</span></span>

[<span data-ttu-id="868d4-158">about_Providers</span><span class="sxs-lookup"><span data-stu-id="868d4-158">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="868d4-159">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="868d4-159">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="868d4-160">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="868d4-160">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
