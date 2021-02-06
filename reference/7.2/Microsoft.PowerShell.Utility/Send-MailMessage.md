---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 0a68c665e8a0b504cfef416134374c5598ba55a7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599693"
---
# <span data-ttu-id="cd229-102">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="cd229-102">Send-MailMessage</span></span>

## <span data-ttu-id="cd229-103">概要</span><span class="sxs-lookup"><span data-stu-id="cd229-103">SYNOPSIS</span></span>
<span data-ttu-id="cd229-104">電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="cd229-104">Sends an email message.</span></span>

## <span data-ttu-id="cd229-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cd229-105">SYNTAX</span></span>

### <span data-ttu-id="cd229-106">すべて</span><span class="sxs-lookup"><span data-stu-id="cd229-106">All</span></span>

```
Send-MailMessage [-Attachments <String[]>] [-Bcc <String[]>] [[-Body] <String>] [-BodyAsHtml]
 [-Encoding <Encoding>] [-Cc <String[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 -From <String> [[-SmtpServer] <String>] [-Priority <MailPriority>] [-ReplyTo <String[]>]
 [[-Subject] <String>] [-To] <String[]> [-Credential <PSCredential>] [-UseSsl] [-Port <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="cd229-107">Description</span><span class="sxs-lookup"><span data-stu-id="cd229-107">DESCRIPTION</span></span>

<span data-ttu-id="cd229-108">`Send-MailMessage`コマンドレットは、PowerShell 内から電子メールメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="cd229-108">The `Send-MailMessage` cmdlet sends an email message from within PowerShell.</span></span>

<span data-ttu-id="cd229-109">簡易メール転送プロトコル (SMTP) サーバーを指定する必要があります。指定しない場合、 `Send-MailMessage` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="cd229-109">You must specify a Simple Mail Transfer Protocol (SMTP) server or the `Send-MailMessage` command fails.</span></span> <span data-ttu-id="cd229-110">**Smtpserver** パラメーターを使用するか、 `$PSEmailServer` 変数を有効な SMTP サーバーに設定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-110">Use the **SmtpServer** parameter or set the `$PSEmailServer` variable to a valid SMTP server.</span></span>
<span data-ttu-id="cd229-111">に割り当てられた値 `$PSEmailServer` は、PowerShell の既定の SMTP 設定です。</span><span class="sxs-lookup"><span data-stu-id="cd229-111">The value assigned to `$PSEmailServer` is the default SMTP setting for PowerShell.</span></span> <span data-ttu-id="cd229-112">詳細については、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd229-112">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

> [!WARNING]
> <span data-ttu-id="cd229-113">`Send-MailMessage`コマンドレットは互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="cd229-113">The `Send-MailMessage` cmdlet is obsolete.</span></span> <span data-ttu-id="cd229-114">このコマンドレットは、SMTP サーバーへのセキュリティで保護された接続を保証しません。</span><span class="sxs-lookup"><span data-stu-id="cd229-114">This cmdlet does not guarantee secure connections to SMTP servers.</span></span> <span data-ttu-id="cd229-115">PowerShell で使用できる即時置換はありませんが、を使用しないことをお勧め `Send-MailMessage` します。</span><span class="sxs-lookup"><span data-stu-id="cd229-115">While there is no immediate replacement available in PowerShell, we recommend you do not use `Send-MailMessage`.</span></span> <span data-ttu-id="cd229-116">詳細については、「 [Platform Compatibility NOTE DE0005](https://aka.ms/SendMailMessage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd229-116">For more information, see [Platform Compatibility note DE0005](https://aka.ms/SendMailMessage).</span></span>

## <span data-ttu-id="cd229-117">例</span><span class="sxs-lookup"><span data-stu-id="cd229-117">EXAMPLES</span></span>

### <span data-ttu-id="cd229-118">例 1: 1 人のユーザーから別のユーザーに電子メールを送信する</span><span class="sxs-lookup"><span data-stu-id="cd229-118">Example 1: Send an email from one person to another person</span></span>

<span data-ttu-id="cd229-119">この例では、あるユーザーから別のユーザーに電子メールメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="cd229-119">This example sends an email message from one person to another person.</span></span>

<span data-ttu-id="cd229-120">**From**、 **To**、および **Subject** の各パラメーターは、によって要求され `Send-MailMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-120">The **From**, **To**, and **Subject** parameters are required by `Send-MailMessage`.</span></span> <span data-ttu-id="cd229-121">この例では、 `$PSEmailServer` SMTP サーバーの既定の変数を使用するため、 **smtpserver** パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cd229-121">This example uses the default `$PSEmailServer` variable for the SMTP server, so the **SmtpServer** parameter is not needed.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

<span data-ttu-id="cd229-122">`Send-MailMessage`コマンドレットは、 **From** パラメーターを使用して、メッセージの送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-122">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="cd229-123">**To** パラメーターは、メッセージの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-123">The **To** parameter specifies the message's recipient.</span></span> <span data-ttu-id="cd229-124">**Subject** パラメーターは、省略可能な **Body** パラメーターが含まれていないため、テキスト文字列の **テストメール** をメッセージとして使用します。</span><span class="sxs-lookup"><span data-stu-id="cd229-124">The **Subject** parameter uses the text string **Test mail** as the message because the optional **Body** parameter is not included.</span></span>

### <span data-ttu-id="cd229-125">例 2: 添付ファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="cd229-125">Example 2: Send an attachment</span></span>

<span data-ttu-id="cd229-126">この例では、添付ファイルを含む電子メールメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="cd229-126">This example sends an email message with an attachment.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

<span data-ttu-id="cd229-127">`Send-MailMessage`コマンドレットは、 **From** パラメーターを使用して、メッセージの送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-127">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="cd229-128">**To** パラメーターは、メッセージの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-128">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="cd229-129">**Subject** パラメーターは、メッセージの内容を記述します。</span><span class="sxs-lookup"><span data-stu-id="cd229-129">The **Subject** parameter describes the content of the message.</span></span> <span data-ttu-id="cd229-130">**Body** パラメーターは、メッセージの内容です。</span><span class="sxs-lookup"><span data-stu-id="cd229-130">The **Body** parameter is the content of the message.</span></span>

<span data-ttu-id="cd229-131">**Attachments** パラメーターは、電子メールメッセージに添付されている現在のディレクトリ内のファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-131">The **Attachments** parameter specifies the file in the current directory that is attached to the email message.</span></span> <span data-ttu-id="cd229-132">**Priority** パラメーターを指定すると、メッセージは **高** 優先度に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cd229-132">The **Priority** parameter sets the message to **High** priority.</span></span> <span data-ttu-id="cd229-133">**-Deliverynotificationoption** パラメーターには、 **OnSuccess** と **OnFailure** の2つの値が指定されています。</span><span class="sxs-lookup"><span data-stu-id="cd229-133">The **-DeliveryNotificationOption** parameter specifies two values, **OnSuccess** and **OnFailure**.</span></span> <span data-ttu-id="cd229-134">送信側は、メッセージの配信が成功したか失敗したかを確認する電子メール通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="cd229-134">The sender will receive email notifications to confirm the success or failure of the message delivery.</span></span>
<span data-ttu-id="cd229-135">**Smtpserver** パラメーターは、SMTP サーバーを **smtp.fabrikam.com** に設定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-135">The **SmtpServer** parameter sets the SMTP server to **smtp.fabrikam.com**.</span></span>

### <span data-ttu-id="cd229-136">例 3: メーリングリストに電子メールを送信する</span><span class="sxs-lookup"><span data-stu-id="cd229-136">Example 3: Send email to a mailing list</span></span>

<span data-ttu-id="cd229-137">この例では、メーリングリストに電子メールメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="cd229-137">This example sends an email message to a mailing list.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

<span data-ttu-id="cd229-138">`Send-MailMessage`コマンドレットは、 **From** パラメーターを使用して、メッセージの送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-138">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="cd229-139">**To** パラメーターは、メッセージの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-139">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="cd229-140">**Cc** パラメーターは、指定された受信者にメッセージのコピーを送信します。</span><span class="sxs-lookup"><span data-stu-id="cd229-140">The **Cc** parameter sends a copy of the message to the specified recipient.</span></span> <span data-ttu-id="cd229-141">**Bcc** パラメーターを指定すると、メッセージのブラインドコピーが送信されます。</span><span class="sxs-lookup"><span data-stu-id="cd229-141">The **Bcc** parameter sends a blind copy of the message.</span></span> <span data-ttu-id="cd229-142">ブラインドコピーは、他の受信者には表示されない電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="cd229-142">A blind copy is an email address that is hidden from the other recipients.</span></span> <span data-ttu-id="cd229-143">省略可能な **Body** パラメーターは含まれていないため、 **Subject** パラメーターはメッセージです。</span><span class="sxs-lookup"><span data-stu-id="cd229-143">The **Subject** parameter is the message because the optional **Body** parameter is not included.</span></span>

<span data-ttu-id="cd229-144">**Credential** パラメーターは、メッセージの送信にドメイン管理者の資格情報を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-144">The **Credential** parameter specifies a domain administrator's credentials are used to send the message.</span></span> <span data-ttu-id="cd229-145">**UseSsl** パラメーターは、Secure Socket LAYER (SSL) がセキュリティで保護された接続を作成することを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-145">The **UseSsl** parameter specifies that Secure Socket Layer (SSL) creates a secure connection.</span></span>

## <span data-ttu-id="cd229-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cd229-146">PARAMETERS</span></span>

### <span data-ttu-id="cd229-147">-添付ファイル</span><span class="sxs-lookup"><span data-stu-id="cd229-147">-Attachments</span></span>

<span data-ttu-id="cd229-148">電子メールメッセージに添付するファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-148">Specifies the path and file names of files to be attached to the email message.</span></span> <span data-ttu-id="cd229-149">このパラメーターを使用するか、パスとファイル名をにパイプすることができ `Send-MailMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-149">You can use this parameter or pipe the paths and file names to `Send-MailMessage`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-150">-Bcc</span><span class="sxs-lookup"><span data-stu-id="cd229-150">-Bcc</span></span>

<span data-ttu-id="cd229-151">メールのコピーを受信するが、メッセージの受信者としては表示されない電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-151">Specifies the email addresses that receive a copy of the mail but are not listed as recipients of the message.</span></span> <span data-ttu-id="cd229-152">名前 (省略可能) と電子メールアドレス (など) を入力し `Name <someone@fabrikam.com>` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-152">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-153">-本文</span><span class="sxs-lookup"><span data-stu-id="cd229-153">-Body</span></span>

<span data-ttu-id="cd229-154">電子メールメッセージの内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-154">Specifies the content of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-155">-BodyAsHtml</span><span class="sxs-lookup"><span data-stu-id="cd229-155">-BodyAsHtml</span></span>

<span data-ttu-id="cd229-156">**Body** パラメーターの値に HTML が含まれていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-156">Specifies that the value of the **Body** parameter contains HTML.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-157">-Cc</span><span class="sxs-lookup"><span data-stu-id="cd229-157">-Cc</span></span>

<span data-ttu-id="cd229-158">電子メールメッセージのカーボンコピー (CC) の送信先となる電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-158">Specifies the email addresses to which a carbon copy (CC) of the email message is sent.</span></span> <span data-ttu-id="cd229-159">名前 (省略可能) と電子メールアドレス (など) を入力し `Name <someone@fabrikam.com>` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-159">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-160">-Credential</span><span class="sxs-lookup"><span data-stu-id="cd229-160">-Credential</span></span>

<span data-ttu-id="cd229-161">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-161">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="cd229-162">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="cd229-162">The default is the current user.</span></span>

<span data-ttu-id="cd229-163">**User01** や **domain01\user01」** などのユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd229-163">Type a user name, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="cd229-164">または、コマンドレットのような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-164">Or, enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="cd229-165">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="cd229-165">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="cd229-166">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd229-166">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-167">-DeliveryNotificationOption</span><span class="sxs-lookup"><span data-stu-id="cd229-167">-DeliveryNotificationOption</span></span>

<span data-ttu-id="cd229-168">電子メールメッセージの配信通知オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-168">Specifies the delivery notification options for the email message.</span></span> <span data-ttu-id="cd229-169">複数の値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="cd229-169">You can specify multiple values.</span></span>
<span data-ttu-id="cd229-170">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="cd229-170">None is the default value.</span></span> <span data-ttu-id="cd229-171">このパラメーターのエイリアスは **Dno** です。</span><span class="sxs-lookup"><span data-stu-id="cd229-171">The alias for this parameter is **DNO**.</span></span>

<span data-ttu-id="cd229-172">配信通知は、 **From** パラメーターのアドレスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="cd229-172">The delivery notifications are sent to the address in the **From** parameter.</span></span>

<span data-ttu-id="cd229-173">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cd229-173">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="cd229-174">`None`: 通知がありません。</span><span class="sxs-lookup"><span data-stu-id="cd229-174">`None`: No notification.</span></span>
- <span data-ttu-id="cd229-175">`OnSuccess`: 配信が成功した場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="cd229-175">`OnSuccess`: Notify if the delivery is successful.</span></span>
- <span data-ttu-id="cd229-176">`OnFailure`: 配信に失敗した場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="cd229-176">`OnFailure`: Notify if the delivery is unsuccessful.</span></span>
- <span data-ttu-id="cd229-177">`Delay`: 配信が遅延した場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="cd229-177">`Delay`: Notify if the delivery is delayed.</span></span>
- <span data-ttu-id="cd229-178">`Never`: 通知しないでください。</span><span class="sxs-lookup"><span data-stu-id="cd229-178">`Never`: Never notify.</span></span>

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-179">-Encoding</span><span class="sxs-lookup"><span data-stu-id="cd229-179">-Encoding</span></span>

<span data-ttu-id="cd229-180">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-180">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="cd229-181">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="cd229-181">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="cd229-182">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cd229-182">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="cd229-183">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd229-183">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="cd229-184">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="cd229-184">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="cd229-185">`bigendianutf32`: ビッグエンディアンのバイト順を使用して、32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="cd229-185">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="cd229-186">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd229-186">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="cd229-187">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="cd229-187">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="cd229-188">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="cd229-188">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="cd229-189">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="cd229-189">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="cd229-190">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="cd229-190">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="cd229-191">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="cd229-191">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="cd229-192">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="cd229-192">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="cd229-193">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-193">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="cd229-194">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd229-194">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-195">-From</span><span class="sxs-lookup"><span data-stu-id="cd229-195">-From</span></span>

<span data-ttu-id="cd229-196">**From** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd229-196">The **From** parameter is required.</span></span> <span data-ttu-id="cd229-197">このパラメーターは、送信者の電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-197">This parameter specifies the sender's email address.</span></span> <span data-ttu-id="cd229-198">名前 (省略可能) と電子メールアドレス (など) を入力し `Name <someone@fabrikam.com>` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-198">Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-199">-Port</span><span class="sxs-lookup"><span data-stu-id="cd229-199">-Port</span></span>

<span data-ttu-id="cd229-200">SMTP サーバーの代替ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-200">Specifies an alternate port on the SMTP server.</span></span> <span data-ttu-id="cd229-201">既定値は 25 です。これは、既定の SMTP ポートです。</span><span class="sxs-lookup"><span data-stu-id="cd229-201">The default value is 25, which is the default SMTP port.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-202">-Priority</span><span class="sxs-lookup"><span data-stu-id="cd229-202">-Priority</span></span>

<span data-ttu-id="cd229-203">電子メールメッセージの優先度を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-203">Specifies the priority of the email message.</span></span> <span data-ttu-id="cd229-204">既定値は Normal です。</span><span class="sxs-lookup"><span data-stu-id="cd229-204">Normal is the default.</span></span> <span data-ttu-id="cd229-205">このパラメーターに指定できる値は、Normal、High、および Low です。</span><span class="sxs-lookup"><span data-stu-id="cd229-205">The acceptable values for this parameter are Normal, High, and Low.</span></span>

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-206">-ReplyTo</span><span class="sxs-lookup"><span data-stu-id="cd229-206">-ReplyTo</span></span>

<span data-ttu-id="cd229-207">このメッセージに返信するために使用する追加の電子メールアドレスを指定します (差出人アドレス以外)。</span><span class="sxs-lookup"><span data-stu-id="cd229-207">Specifies additional email addresses (other than the From address) to use to reply to this message.</span></span>
<span data-ttu-id="cd229-208">名前 (省略可能) と電子メールアドレス (など) を入力し `Name <someone@fabrikam.com>` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-208">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

<span data-ttu-id="cd229-209">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd229-209">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-210">-SmtpServer</span><span class="sxs-lookup"><span data-stu-id="cd229-210">-SmtpServer</span></span>

<span data-ttu-id="cd229-211">電子メールメッセージを送信する SMTP サーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-211">Specifies the name of the SMTP server that sends the email message.</span></span>

<span data-ttu-id="cd229-212">既定値は、ユーザー設定変数の値です `$PSEmailServer` 。</span><span class="sxs-lookup"><span data-stu-id="cd229-212">The default value is the value of the `$PSEmailServer` preference variable.</span></span> <span data-ttu-id="cd229-213">ユーザー設定変数が設定されておらず、このパラメーターが使用されていない場合、 `Send-MailMessage` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="cd229-213">If the preference variable is not set and this parameter is not used, the `Send-MailMessage` command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-214">-Subject</span><span class="sxs-lookup"><span data-stu-id="cd229-214">-Subject</span></span>

<span data-ttu-id="cd229-215">**Subject** パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cd229-215">The **Subject** parameter isn't required.</span></span> <span data-ttu-id="cd229-216">このパラメーターは、電子メールメッセージの件名を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-216">This parameter specifies the subject of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-217">-To</span><span class="sxs-lookup"><span data-stu-id="cd229-217">-To</span></span>

<span data-ttu-id="cd229-218">**To** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd229-218">The **To** parameter is required.</span></span> <span data-ttu-id="cd229-219">このパラメーターは、受信者の電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd229-219">This parameter specifies the recipient's email address.</span></span> <span data-ttu-id="cd229-220">複数の受信者がいる場合は、それらのアドレスをコンマ () で区切り `,` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-220">If there are multiple recipients, separate their addresses with a comma (`,`).</span></span> <span data-ttu-id="cd229-221">名前 (省略可能) と電子メールアドレス (など) を入力し `Name <someone@fabrikam.com>` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-221">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-222">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="cd229-222">-UseSsl</span></span>

<span data-ttu-id="cd229-223">リモートコンピューターへのセキュリティで保護された接続を確立してメールを送信するには、Secure Sockets Layer (SSL) プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd229-223">The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail.</span></span> <span data-ttu-id="cd229-224">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="cd229-224">By default, SSL is not used.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd229-225">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd229-225">CommonParameters</span></span>

<span data-ttu-id="cd229-226">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cd229-226">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cd229-227">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd229-227">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cd229-228">入力</span><span class="sxs-lookup"><span data-stu-id="cd229-228">INPUTS</span></span>

### <span data-ttu-id="cd229-229">System.String</span><span class="sxs-lookup"><span data-stu-id="cd229-229">System.String</span></span>

<span data-ttu-id="cd229-230">パイプを使用して、添付ファイルのパスとファイル名をにパイプすることができ `Send-MailMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="cd229-230">You can pipe the path and file names of attachments to `Send-MailMessage`.</span></span>

## <span data-ttu-id="cd229-231">出力</span><span class="sxs-lookup"><span data-stu-id="cd229-231">OUTPUTS</span></span>

### <span data-ttu-id="cd229-232">なし</span><span class="sxs-lookup"><span data-stu-id="cd229-232">None</span></span>

<span data-ttu-id="cd229-233">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="cd229-233">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="cd229-234">注</span><span class="sxs-lookup"><span data-stu-id="cd229-234">NOTES</span></span>

## <span data-ttu-id="cd229-235">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cd229-235">RELATED LINKS</span></span>

[<span data-ttu-id="cd229-236">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="cd229-236">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="cd229-237">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="cd229-237">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

