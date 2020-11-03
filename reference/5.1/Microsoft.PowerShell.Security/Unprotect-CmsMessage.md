---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: 794ff376c11d6956b71b3feb48f058c92a2e7d17
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214195"
---
# <span data-ttu-id="243ec-103">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="243ec-103">Unprotect-CmsMessage</span></span>

## <span data-ttu-id="243ec-104">概要</span><span class="sxs-lookup"><span data-stu-id="243ec-104">SYNOPSIS</span></span>
<span data-ttu-id="243ec-105">暗号化メッセージの構文形式を使用して暗号化されたコンテンツを復号化します。</span><span class="sxs-lookup"><span data-stu-id="243ec-105">Decrypts content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="243ec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="243ec-106">SYNTAX</span></span>

### <span data-ttu-id="243ec-107">ByWinEvent (既定値)</span><span class="sxs-lookup"><span data-stu-id="243ec-107">ByWinEvent (Default)</span></span>

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="243ec-108">ByContent</span><span class="sxs-lookup"><span data-stu-id="243ec-108">ByContent</span></span>

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="243ec-109">ByPath</span><span class="sxs-lookup"><span data-stu-id="243ec-109">ByPath</span></span>

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="243ec-110">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="243ec-110">ByLiteralPath</span></span>

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="243ec-111">Description</span><span class="sxs-lookup"><span data-stu-id="243ec-111">DESCRIPTION</span></span>

<span data-ttu-id="243ec-112">この `Unprotect-CmsMessage` コマンドレットは、暗号化メッセージ構文 (CMS) 形式を使用して暗号化されたコンテンツを復号化します。</span><span class="sxs-lookup"><span data-stu-id="243ec-112">The `Unprotect-CmsMessage` cmdlet decrypts content that has been encrypted by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="243ec-113">CMS コマンドレットは、 [RFC5652](https://tools.ietf.org/html/rfc5652)によって説明されているように、メッセージを暗号化して保護するための IETF 標準形式を使用したコンテンツの暗号化と暗号化解除をサポートします。</span><span class="sxs-lookup"><span data-stu-id="243ec-113">The CMS cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="243ec-114">CMS 暗号化標準では、公開キー暗号化を使用します。この暗号化では、コンテンツの暗号化に使用されるキー (公開キー) とコンテンツの暗号化を解除するために使用されるキー (秘密キー) は区別されます。</span><span class="sxs-lookup"><span data-stu-id="243ec-114">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="243ec-115">公開キーは広く共有でき、機密性の高いデータではありません。</span><span class="sxs-lookup"><span data-stu-id="243ec-115">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="243ec-116">いずれかのコンテンツがこの公開キーで暗号化された場合、秘密キーのみが暗号化を解除できます。</span><span class="sxs-lookup"><span data-stu-id="243ec-116">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="243ec-117">公開キー暗号化の詳細については、「[公開鍵暗号](https://en.wikipedia.org/wiki/Public-key_cryptography)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="243ec-117">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="243ec-118">`Unprotect-CmsMessage` CMS 形式で暗号化されたコンテンツを復号化します。</span><span class="sxs-lookup"><span data-stu-id="243ec-118">`Unprotect-CmsMessage` decrypts content that has been encrypted in CMS format.</span></span> <span data-ttu-id="243ec-119">このコマンドレットを実行すると、コマンドレットを実行して暗号化したコンテンツの暗号化を解除でき `Protect-CmsMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="243ec-119">You can run this cmdlet to decrypt content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="243ec-120">暗号化を解除するコンテンツを文字列として指定したり、暗号化イベントログの ID 番号を使用したり、暗号化されたコンテンツへのパスを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="243ec-120">You can specify content that you want to decrypt as a string, by the encryption event log record ID number, or by path to the encrypted content.</span></span> <span data-ttu-id="243ec-121">コマンドレットにより、復号化され `Unprotect-CmsMessage` たコンテンツが返されます。</span><span class="sxs-lookup"><span data-stu-id="243ec-121">The `Unprotect-CmsMessage` cmdlet returns the decrypted content.</span></span>

## <span data-ttu-id="243ec-122">例</span><span class="sxs-lookup"><span data-stu-id="243ec-122">EXAMPLES</span></span>

### <span data-ttu-id="243ec-123">例 1: メッセージの暗号化を解除する</span><span class="sxs-lookup"><span data-stu-id="243ec-123">Example 1: Decrypt a message</span></span>

<span data-ttu-id="243ec-124">次の例では、リテラルパスにあるコンテンツの暗号化を解除し `C:\Users\Test\Documents\PowerShell` ます。</span><span class="sxs-lookup"><span data-stu-id="243ec-124">In the following example, you decrypt content that is located at the literal path `C:\Users\Test\Documents\PowerShell`.</span></span> <span data-ttu-id="243ec-125">[ **必須]** パラメーターの値の場合、この例では、暗号化の実行に使用された証明書のサムプリントを使用します。</span><span class="sxs-lookup"><span data-stu-id="243ec-125">For the value of the required **To** parameter, this example uses the thumbprint of the certificate that was used to perform the encryption.</span></span> <span data-ttu-id="243ec-126">暗号化が解除されたことを示します。 "新しい Break All コマンドを試してください" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="243ec-126">The decrypted message, "Try the new Break All command," is the result.</span></span>

```powershell
$parameters = @{
  LiteralPath = "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
  To = '0f 8j b1 ab e0 ce 35 1d 67 d2 f2 6f a2 d2 00 cl 22 z9 m9 85'
}
Unprotect-CmsMessage -LiteralPath @parameters
```

```Output
Try the new Break All command
```

## <span data-ttu-id="243ec-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="243ec-127">PARAMETERS</span></span>

### <span data-ttu-id="243ec-128">-コンテンツ</span><span class="sxs-lookup"><span data-stu-id="243ec-128">-Content</span></span>

<span data-ttu-id="243ec-129">暗号化された文字列、または暗号化された文字列を含む変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="243ec-129">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

```yaml
Type: System.String
Parameter Sets: ByContent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="243ec-130">-EventLogRecord</span><span class="sxs-lookup"><span data-stu-id="243ec-130">-EventLogRecord</span></span>

<span data-ttu-id="243ec-131">CMS 暗号化操作を表すイベントログレコード ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="243ec-131">Specifies an event log record ID that represents a CMS encryption operation.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByWinEvent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="243ec-132">-IncludeContext</span><span class="sxs-lookup"><span data-stu-id="243ec-132">-IncludeContext</span></span>

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

### <span data-ttu-id="243ec-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="243ec-133">-LiteralPath</span></span>

<span data-ttu-id="243ec-134">暗号化を解除する暗号化されたコンテンツへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="243ec-134">Specifies the path to encrypted content that you want to decrypt.</span></span> <span data-ttu-id="243ec-135">**Path** とは異なり、 **LiteralPath** の値は入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="243ec-135">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="243ec-136">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="243ec-136">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="243ec-137">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="243ec-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="243ec-138">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="243ec-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="243ec-139">-Path</span><span class="sxs-lookup"><span data-stu-id="243ec-139">-Path</span></span>

<span data-ttu-id="243ec-140">暗号化を解除する暗号化されたコンテンツへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="243ec-140">Specifies the path to encrypted content that you want to decrypt.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="243ec-141">-To</span><span class="sxs-lookup"><span data-stu-id="243ec-141">-To</span></span>

<span data-ttu-id="243ec-142">次のいずれかの形式で識別される、1つまたは複数の CMS メッセージ受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="243ec-142">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="243ec-143">(証明書プロバイダーから取得された) 実際の証明書。</span><span class="sxs-lookup"><span data-stu-id="243ec-143">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="243ec-144">証明書を含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="243ec-144">Path to the a file containing the certificate.</span></span>
- <span data-ttu-id="243ec-145">証明書が格納されているディレクトリへのパス。</span><span class="sxs-lookup"><span data-stu-id="243ec-145">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="243ec-146">証明書の拇印 (証明書ストアを検索するために使用されます)。</span><span class="sxs-lookup"><span data-stu-id="243ec-146">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="243ec-147">証明書のサブジェクト名 (証明書ストアを検索するために使用されます)。</span><span class="sxs-lookup"><span data-stu-id="243ec-147">Subject name of the certificate (used to look in the certificate store).</span></span>

```yaml
Type: System.Management.Automation.CmsMessageRecipient[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="243ec-148">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="243ec-148">CommonParameters</span></span>

<span data-ttu-id="243ec-149">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="243ec-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="243ec-150">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="243ec-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="243ec-151">入力</span><span class="sxs-lookup"><span data-stu-id="243ec-151">INPUTS</span></span>

### <span data-ttu-id="243ec-152">EventLogRecord または System.string を指定します。</span><span class="sxs-lookup"><span data-stu-id="243ec-152">System.Diagnostics.Eventing.Reader.EventLogRecord or System.String</span></span>

<span data-ttu-id="243ec-153">パイプを使用して、暗号化されたコンテンツを含むオブジェクトをにパイプすることができ `Unprotect-CmsMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="243ec-153">You can pipe an object containing encrypted content to `Unprotect-CmsMessage`.</span></span>

## <span data-ttu-id="243ec-154">出力</span><span class="sxs-lookup"><span data-stu-id="243ec-154">OUTPUTS</span></span>

### <span data-ttu-id="243ec-155">System.String</span><span class="sxs-lookup"><span data-stu-id="243ec-155">System.String</span></span>

<span data-ttu-id="243ec-156">暗号化されていないメッセージ。</span><span class="sxs-lookup"><span data-stu-id="243ec-156">The unencrypted message.</span></span>

## <span data-ttu-id="243ec-157">注</span><span class="sxs-lookup"><span data-stu-id="243ec-157">NOTES</span></span>

## <span data-ttu-id="243ec-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="243ec-158">RELATED LINKS</span></span>

[<span data-ttu-id="243ec-159">about_Providers</span><span class="sxs-lookup"><span data-stu-id="243ec-159">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="243ec-160">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="243ec-160">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="243ec-161">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="243ec-161">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)
