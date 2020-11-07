---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/protect-cmsmessage?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Protect-CmsMessage
ms.openlocfilehash: de72454f4c50746ca22853dd51e2ec0447bed101
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347637"
---
# <span data-ttu-id="4edcb-103">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="4edcb-103">Protect-CmsMessage</span></span>

## <span data-ttu-id="4edcb-104">概要</span><span class="sxs-lookup"><span data-stu-id="4edcb-104">SYNOPSIS</span></span>
<span data-ttu-id="4edcb-105">暗号化メッセージ構文形式を使用してコンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="4edcb-105">Encrypts content by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="4edcb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4edcb-106">SYNTAX</span></span>

### <span data-ttu-id="4edcb-107">ByContent (既定)</span><span class="sxs-lookup"><span data-stu-id="4edcb-107">ByContent (Default)</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <PSObject> [[-OutFile] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="4edcb-108">ByPath</span><span class="sxs-lookup"><span data-stu-id="4edcb-108">ByPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <String> [[-OutFile] <String>] [<CommonParameters>]
```

### <span data-ttu-id="4edcb-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="4edcb-109">ByLiteralPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <String> [[-OutFile] <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="4edcb-110">Description</span><span class="sxs-lookup"><span data-stu-id="4edcb-110">DESCRIPTION</span></span>

<span data-ttu-id="4edcb-111">コマンドレットでは、 `Protect-CmsMessage` 暗号化メッセージ構文 (CMS) 形式を使用してコンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="4edcb-111">The `Protect-CmsMessage` cmdlet encrypts content by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="4edcb-112">CMS コマンドレットは、 [RFC5652](https://tools.ietf.org/html/rfc5652.html)によって説明されているように、IETF 形式を使用したコンテンツの暗号化と暗号化解除をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4edcb-112">The CMS cmdlets support encryption and decryption of content using the IETF format as documented by [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span></span>

<span data-ttu-id="4edcb-113">CMS 暗号化標準では、公開キー暗号化を使用します。この暗号化では、コンテンツの暗号化に使用されるキー (公開キー) とコンテンツの暗号化を解除するために使用されるキー (秘密キー) は区別されます。</span><span class="sxs-lookup"><span data-stu-id="4edcb-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="4edcb-114">公開キーは広く共有でき、機密性の高いデータではありません。</span><span class="sxs-lookup"><span data-stu-id="4edcb-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="4edcb-115">いずれかのコンテンツがこの公開キーで暗号化された場合、秘密キーのみが暗号化を解除できます。</span><span class="sxs-lookup"><span data-stu-id="4edcb-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="4edcb-116">公開キー暗号化の詳細については、「[公開鍵暗号](https://en.wikipedia.org/wiki/Public-key_cryptography)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edcb-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="4edcb-117">コマンドレットを実行するには、事前に `Protect-CmsMessage` 暗号化証明書を設定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="4edcb-117">Before you can run the `Protect-CmsMessage` cmdlet, you must have an encryption certificate set up.</span></span>
<span data-ttu-id="4edcb-118">PowerShell で認識されるようにするには、暗号化証明書をデータ暗号化証明書として識別するために一意の拡張キー使用法 ([EKU](/windows/desktop/SecCrypto/eku)) ID が必要です (コード署名および暗号化されたメールの id など)。</span><span class="sxs-lookup"><span data-stu-id="4edcb-118">To be recognized in PowerShell, encryption certificates require a unique extended key usage ([EKU](/windows/desktop/SecCrypto/eku)) ID to identify them as data encryption certificates (such as the IDs for Code Signing and Encrypted Mail).</span></span> <span data-ttu-id="4edcb-119">ドキュメントの暗号化に使用する証明書の例については、このトピックの例1を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edcb-119">For an example of a certificate that would work for document encryption, see Example 1 in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="4edcb-120">このコマンドレットは、Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4edcb-120">This cmdlet is only available on Windows.</span></span>

## <span data-ttu-id="4edcb-121">例</span><span class="sxs-lookup"><span data-stu-id="4edcb-121">EXAMPLES</span></span>

### <span data-ttu-id="4edcb-122">例 1: コンテンツを暗号化するための証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="4edcb-122">Example 1: Create a certificate for encrypting content</span></span>

<span data-ttu-id="4edcb-123">コマンドレットを実行する前に `Protect-CmsMessage` 、暗号化証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4edcb-123">Before you can run the `Protect-CmsMessage` cmdlet, you must create an encryption certificate.</span></span> <span data-ttu-id="4edcb-124">次のテキストを使用して、件名行の名前を名前、電子メール、またはその他の識別子に変更し、証明書をファイルに保存し `DocumentEncryption.inf` ます (この例で示すように)。</span><span class="sxs-lookup"><span data-stu-id="4edcb-124">Using the following text, change the name in the Subject line to your name, email, or other identifier, and save the certificate in a file (such as `DocumentEncryption.inf`, as shown in this example).</span></span>

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

### <span data-ttu-id="4edcb-125">例 2: 電子メールで送信されたメッセージを暗号化する</span><span class="sxs-lookup"><span data-stu-id="4edcb-125">Example 2: Encrypt a message sent by email</span></span>

```powershell
$Protected = "Hello World" | Protect-CmsMessage -To "*youralias@emailaddress.com*"
```

<span data-ttu-id="4edcb-126">次の例では、メッセージ "Hello World" をコマンドレットにパイプして暗号化し、 `Protect-CmsMessage` 暗号化されたメッセージを変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="4edcb-126">In the following example, you encrypt a message, "Hello World", by piping it to the `Protect-CmsMessage` cmdlet, and then save the encrypted message in a variable.</span></span> <span data-ttu-id="4edcb-127">**To** パラメーターは、証明書の Subject 行の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="4edcb-127">The **To** parameter uses the value of the Subject line in the certificate.</span></span>

### <span data-ttu-id="4edcb-128">例 3: ドキュメントの暗号化証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="4edcb-128">Example 3: View document encryption certificates</span></span>

```
PS C:\> cd Cert:\CurrentUser\My
PS Cert:\CurrentUser\My> Get-ChildItem -DocumentEncryptionCert
```

<span data-ttu-id="4edcb-129">証明書プロバイダーでドキュメントの暗号化証明書を表示するには、 [get-childitem](../Microsoft.PowerShell.Management/Get-ChildItem.md)の **documentencryptioncert** 動的パラメーターを追加します。このパラメーターは、証明書プロバイダーが読み込まれたときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4edcb-129">To view document encryption certificates in the certificate provider, you can add the **DocumentEncryptionCert** dynamic parameter of [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md), available only when the certificate provider is loaded.</span></span>

## <span data-ttu-id="4edcb-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4edcb-130">PARAMETERS</span></span>

### <span data-ttu-id="4edcb-131">-コンテンツ</span><span class="sxs-lookup"><span data-stu-id="4edcb-131">-Content</span></span>

<span data-ttu-id="4edcb-132">暗号化するコンテンツを含む **PSObject** を指定します。</span><span class="sxs-lookup"><span data-stu-id="4edcb-132">Specifies a **PSObject** that contains content that you want to encrypt.</span></span> <span data-ttu-id="4edcb-133">たとえば、イベントメッセージの内容を暗号化し、そのメッセージを含む変数 ( `$Event` この例では) を **content** パラメーターの値として使用できます `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1` 。</span><span class="sxs-lookup"><span data-stu-id="4edcb-133">For example, you can encrypt the content of an event message, and then use the variable containing the message (`$Event`, in this example) as the value of the **Content** parameter: `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1`.</span></span> <span data-ttu-id="4edcb-134">また、コマンドレットを使用し `Get-Content` て、Microsoft Word 文書などのファイルの内容を取得し **、content** パラメーターの値として使用する変数にコンテンツを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="4edcb-134">You can also use the `Get-Content` cmdlet to get the contents of a file, such as a Microsoft Word document, and save the content in a variable that you use as the value of the **Content** parameter.</span></span>

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

### <span data-ttu-id="4edcb-135">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4edcb-135">-LiteralPath</span></span>

<span data-ttu-id="4edcb-136">暗号化するコンテンツへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4edcb-136">Specifies the path to content that you want to encrypt.</span></span> <span data-ttu-id="4edcb-137">**Path** とは異なり、 **LiteralPath** の値は入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="4edcb-137">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="4edcb-138">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="4edcb-138">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="4edcb-139">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="4edcb-139">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="4edcb-140">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="4edcb-140">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="4edcb-141">-出力</span><span class="sxs-lookup"><span data-stu-id="4edcb-141">-OutFile</span></span>

<span data-ttu-id="4edcb-142">暗号化されたコンテンツを送信するファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4edcb-142">Specifies the path and file name of a file to which you want to send the encrypted content.</span></span>

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

### <span data-ttu-id="4edcb-143">-Path</span><span class="sxs-lookup"><span data-stu-id="4edcb-143">-Path</span></span>

<span data-ttu-id="4edcb-144">暗号化するコンテンツへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4edcb-144">Specifies the path to content that you want to encrypt.</span></span>

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

### <span data-ttu-id="4edcb-145">-To</span><span class="sxs-lookup"><span data-stu-id="4edcb-145">-To</span></span>

<span data-ttu-id="4edcb-146">次のいずれかの形式で識別される、1つまたは複数の CMS メッセージ受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="4edcb-146">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="4edcb-147">(証明書プロバイダーから取得された) 実際の証明書。</span><span class="sxs-lookup"><span data-stu-id="4edcb-147">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="4edcb-148">証明書を含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="4edcb-148">Path to the file containing the certificate.</span></span>
- <span data-ttu-id="4edcb-149">証明書が格納されているディレクトリへのパス。</span><span class="sxs-lookup"><span data-stu-id="4edcb-149">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="4edcb-150">証明書の拇印 (証明書ストアを検索するために使用されます)。</span><span class="sxs-lookup"><span data-stu-id="4edcb-150">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="4edcb-151">証明書のサブジェクト名 (証明書ストアを検索するために使用されます)。</span><span class="sxs-lookup"><span data-stu-id="4edcb-151">Subject name of the certificate (used to look in the certificate store).</span></span>

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

### <span data-ttu-id="4edcb-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4edcb-152">CommonParameters</span></span>

<span data-ttu-id="4edcb-153">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="4edcb-153">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="4edcb-154">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4edcb-154">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4edcb-155">入力</span><span class="sxs-lookup"><span data-stu-id="4edcb-155">INPUTS</span></span>

## <span data-ttu-id="4edcb-156">出力</span><span class="sxs-lookup"><span data-stu-id="4edcb-156">OUTPUTS</span></span>

## <span data-ttu-id="4edcb-157">注</span><span class="sxs-lookup"><span data-stu-id="4edcb-157">NOTES</span></span>

<span data-ttu-id="4edcb-158">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4edcb-158">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="4edcb-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4edcb-159">RELATED LINKS</span></span>

[<span data-ttu-id="4edcb-160">about_Providers</span><span class="sxs-lookup"><span data-stu-id="4edcb-160">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="4edcb-161">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="4edcb-161">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="4edcb-162">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="4edcb-162">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
