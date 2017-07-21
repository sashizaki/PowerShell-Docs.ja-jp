---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 9556f0d9a12807cbfe38aaade6798088f051596d
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="cryptographic-message-syntax-cms-cmdlets"></a><span data-ttu-id="c6301-102">Cryptographic Message Syntax (CMS) コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c6301-102">Cryptographic Message Syntax (CMS) cmdlets</span></span>

<span data-ttu-id="c6301-103">Cryptographic Message Syntax コマンドレットは、[RFC5652](http://tools.ietf.org/html/rfc5652) で説明されているように暗号によってメッセージを保護するための IETF 標準書式を使用して、コンテンツの暗号化と暗号化解除をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c6301-103">The Cryptographic Message Syntax cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages as documented by [RFC5652](http://tools.ietf.org/html/rfc5652).</span></span>

```powershell
Get-CmsMessage [-Content] <string>
Get-CmsMessage [-Path] <string>
Get-CmsMessage [-LiteralPath] <string>
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <string> [[-OutFile] <string>]
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <string> [[-OutFile] <string>]
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <string> [[-OutFile] <string>]
Unprotect-CmsMessage [-EventLogRecord] <EventLogRecord> [[-To] <CmsMessageRecipient[]>] [-IncludeContext]
Unprotect-CmsMessage [-Content] <string> [[-To] <CmsMessageRecipient[]>] [-IncludeContext]
Unprotect-CmsMessage [-Path] <string> [[-To] <CmsMessageRecipient[]>] [-IncludeContext]
Unprotect-CmsMessage [-LiteralPath] <string> [[-To] <CmsMessageRecipient[]>] [-IncludeContext]
```

<span data-ttu-id="c6301-104">CMS 暗号化標準では、公開キー暗号化が実装されます。公開キー暗号化では、コンテンツの暗号化に使用されるキー (*公開キー*) とコンテンツの暗号化解除に使用されるキー (*秘密キー*) が区別されます。</span><span class="sxs-lookup"><span data-stu-id="c6301-104">The CMS encryption standard implements public key cryptography, where the keys used to encrypt content (the *public key*) and the keys used to decrypt content (the *private key*) are separate.</span></span>

<span data-ttu-id="c6301-105">公開キーは広く共有でき、機密性の高いデータではありません。</span><span class="sxs-lookup"><span data-stu-id="c6301-105">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="c6301-106">いずれかのコンテンツがこの公開キーで暗号化された場合、秘密キーのみが暗号化を解除できます。</span><span class="sxs-lookup"><span data-stu-id="c6301-106">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="c6301-107">公開キー暗号化の詳細については、<http://en.wikipedia.org/wiki/Public-key_cryptography> をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6301-107">For more information about Public Key Cryptography, see: <http://en.wikipedia.org/wiki/Public-key_cryptography>.</span></span>

<span data-ttu-id="c6301-108">PowerShell で認識されるためには、暗号化証明書に、データ暗号化証明書として識別するための ('Code Signing'、'Encrypted Mail' の識別子のような) 一意のキー使用法識別子 (EKU) が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6301-108">To be recognized in PowerShell, encryption certificates require a unique key usage identifier (EKU) to identify them as data encryption certificates (like the identifiers for 'Code Signing', 'Encrypted Mail').</span></span>

<span data-ttu-id="c6301-109">ドキュメントの暗号化用の証明書を作成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c6301-109">Here is an example of creating a certificate that is good for Document Encryption:</span></span>

```powershell
(Change the text in **Subject** to your name, email, or other identifier), and put in a file (i.e.: DocumentEncryption.inf):
[Version]
Signature = "$Windows NT$"
[Strings]
szOID\_ENHANCED\_KEY\_USAGE = "2.5.29.37"
szOID\_DOCUMENT\_ENCRYPTION = "1.3.6.1.4.1.311.80.1"
[NewRequest]
Subject = "<cn=me@somewhere.com>"
MachineKeySet = false
KeyLength = 2048
KeySpec = AT\_KEYEXCHANGE
HashAlgorithm = Sha1
Exportable = true
RequestType = Cert
KeyUsage = "CERT\_KEY\_ENCIPHERMENT\_KEY\_USAGE | CERT\_DATA\_ENCIPHERMENT\_KEY\_USAGE"
ValidityPeriod = "Years"
ValidityPeriodUnits = "1000"
[Extensions]
%szOID\_ENHANCED\_KEY\_USAGE% = "{text}%szOID\_DOCUMENT\_ENCRYPTION%"
```

<span data-ttu-id="c6301-110">次に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6301-110">Then run:</span></span>
```powershell
certreq -new DocumentEncryption.inf DocumentEncryption.cer
```

<span data-ttu-id="c6301-111">これで、コンテンツを暗号化および暗号化解除できます。</span><span class="sxs-lookup"><span data-stu-id="c6301-111">And you can now encrypt and decrypt content:</span></span>

```powershell
$protected = "Hello World" | Protect-CmsMessage -To "\*me@somewhere.com\*[](mailto:*leeholm@microsoft.com*)"
$protected
-----BEGIN CMS-----
MIIBqAYJKoZIhvcNAQcDoIIBmTCCAZUCAQAxggFQMIIBTAIBADA0MCAxHjAcBgNVBAMMFWxlZWhv
bG1AbWljcm9zb2Z0LmNvbQIQQYHsbcXnjIJCtH+OhGmc1DANBgkqhkiG9w0BAQcwAASCAQAnkFHM
proJnFy4geFGfyNmxH3yeoPvwEYzdnsoVqqDPAd8D3wao77z7OhJEXwz9GeFLnxD6djKV/tF4PxR
E27aduKSLbnxfpf/sepZ4fUkuGibnwWFrxGE3B1G26MCenHWjYQiqv+Nq32Gc97qEAERrhLv6S4R
G+2dJEnesW8A+z9QPo+DwYU5FzD0Td0ExrkswVckpLNR6j17Yaags3ltNVmbdEXekhi6Psf2MLMP
TSO79lv2L0KeXFGuPOrdzPAwCkV0vNEqTEBeDnZGrjv/5766bM3GW34FXApod9u+VSFpBnqVOCBA
DVDraA6k+xwBt66cV84OHLkh0kT02SIHMDwGCSqGSIb3DQEHATAdBglghkgBZQMEASoEEJbJaiRl
KMnBoD1dkb/FzSWAEBaL8xkFwCu0e1ZtDj7nSJc=
-----END CMS-----

$protected | Unprotect-CmsMessage
Hello World
```

<span data-ttu-id="c6301-112">**CMSMessageRecipient** 型のパラメーターでは、次の形式の識別子がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c6301-112">Any parameter of type **CMSMessageRecipient** supports identifiers in the following formats:</span></span>
- <span data-ttu-id="c6301-113">(証明書プロバイダーから取得された) 実際の証明書</span><span class="sxs-lookup"><span data-stu-id="c6301-113">An actual certificate (as retrieved from the certificate provider)</span></span>
- <span data-ttu-id="c6301-114">証明書を含むファイルのパス</span><span class="sxs-lookup"><span data-stu-id="c6301-114">Path to the a file containing the certificate</span></span>
- <span data-ttu-id="c6301-115">証明書を含むディレクトリのパス</span><span class="sxs-lookup"><span data-stu-id="c6301-115">Path to a directory containing the certificate</span></span>
- <span data-ttu-id="c6301-116">証明書の拇印 (証明書ストア内の検索に使用)</span><span class="sxs-lookup"><span data-stu-id="c6301-116">Thumbprint of the certificate (used to look in the certificate store)</span></span>
- <span data-ttu-id="c6301-117">証明書のサブジェクト名 (証明書ストア内の検索に使用)</span><span class="sxs-lookup"><span data-stu-id="c6301-117">Subject name of the certificate (used to look in the certificate store)</span></span>

<span data-ttu-id="c6301-118">証明書プロバイダーでドキュメントの暗号化証明書を表示するには、**-DocumentEncryptionCert** 動的パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6301-118">To view document encryption certificates in the certificate provider, you can use the **-DocumentEncryptionCert** dynamic parameter:</span></span>

```powershell
dir -DocumentEncryptionCert
```

