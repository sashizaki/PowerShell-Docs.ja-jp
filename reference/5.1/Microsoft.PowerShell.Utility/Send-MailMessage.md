---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 6f98c95e6c0144f76393e9d28454833097894512
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213720"
---
# <span data-ttu-id="b60e7-103">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="b60e7-103">Send-MailMessage</span></span>

## <span data-ttu-id="b60e7-104">概要</span><span class="sxs-lookup"><span data-stu-id="b60e7-104">SYNOPSIS</span></span>
<span data-ttu-id="b60e7-105">電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-105">Sends an email message.</span></span>

## <span data-ttu-id="b60e7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b60e7-106">SYNTAX</span></span>

### <span data-ttu-id="b60e7-107">All</span><span class="sxs-lookup"><span data-stu-id="b60e7-107">All</span></span>

```
Send-MailMessage [-To] <string[]> [-Subject] <string> [[-Body] <string>] [[-SmtpServer] <string>]
 -From <string> [-Attachments <string[]>] [-Bcc <string[]>] [-BodyAsHtml] [-Encoding <Encoding>]
 [-Cc <string[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 [-Priority <MailPriority>] [-Credential <pscredential>] [-UseSsl] [-Port <int>]
 [<CommonParameters>]
```

## <span data-ttu-id="b60e7-108">Description</span><span class="sxs-lookup"><span data-stu-id="b60e7-108">DESCRIPTION</span></span>

<span data-ttu-id="b60e7-109">`Send-MailMessage`コマンドレットは、PowerShell 内から電子メールメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-109">The `Send-MailMessage` cmdlet sends an email message from within PowerShell.</span></span>

<span data-ttu-id="b60e7-110">簡易メール転送プロトコル (SMTP) サーバーを指定する必要があります。指定しない場合、 `Send-MailMessage` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-110">You must specify a Simple Mail Transfer Protocol (SMTP) server or the `Send-MailMessage` command fails.</span></span> <span data-ttu-id="b60e7-111">**Smtpserver** パラメーターを使用するか、 `$PSEmailServer` 変数を有効な SMTP サーバーに設定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-111">Use the **SmtpServer** parameter or set the `$PSEmailServer` variable to a valid SMTP server.</span></span>
<span data-ttu-id="b60e7-112">に割り当てられた値 `$PSEmailServer` は、PowerShell の既定の SMTP 設定です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-112">The value assigned to `$PSEmailServer` is the default SMTP setting for PowerShell.</span></span> <span data-ttu-id="b60e7-113">詳細については、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b60e7-113">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

> [!WARNING]
> <span data-ttu-id="b60e7-114">`Send-MailMessage`コマンドレットは互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="b60e7-114">The `Send-MailMessage` cmdlet is obsolete.</span></span> <span data-ttu-id="b60e7-115">このコマンドレットは、SMTP サーバーへのセキュリティで保護された接続を保証しません。</span><span class="sxs-lookup"><span data-stu-id="b60e7-115">This cmdlet does not guarantee secure connections to SMTP servers.</span></span> <span data-ttu-id="b60e7-116">PowerShell で使用できる即時置換はありませんが、を使用しないことをお勧め `Send-MailMessage` します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-116">While there is no immediate replacement available in PowerShell, we recommend you do not use `Send-MailMessage`.</span></span> <span data-ttu-id="b60e7-117">詳細については、「 [Platform Compatibility NOTE DE0005](https://aka.ms/SendMailMessage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b60e7-117">For more information, see [Platform Compatibility note DE0005](https://aka.ms/SendMailMessage).</span></span>

## <span data-ttu-id="b60e7-118">例</span><span class="sxs-lookup"><span data-stu-id="b60e7-118">EXAMPLES</span></span>

### <span data-ttu-id="b60e7-119">例 1: 1 人のユーザーから別のユーザーに電子メールを送信する</span><span class="sxs-lookup"><span data-stu-id="b60e7-119">Example 1: Send an email from one person to another person</span></span>

<span data-ttu-id="b60e7-120">この例では、あるユーザーから別のユーザーに電子メールメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-120">This example sends an email message from one person to another person.</span></span>

<span data-ttu-id="b60e7-121">**From** 、 **To** 、および **Subject** の各パラメーターは、によって要求され `Send-MailMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-121">The **From** , **To** , and **Subject** parameters are required by `Send-MailMessage`.</span></span> <span data-ttu-id="b60e7-122">この例では、 `$PSEmailServer` SMTP サーバーの既定の変数を使用するため、 **smtpserver** パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b60e7-122">This example uses the default `$PSEmailServer` variable for the SMTP server, so the **SmtpServer** parameter is not needed.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

<span data-ttu-id="b60e7-123">`Send-MailMessage`コマンドレットは、 **From** パラメーターを使用して、メッセージの送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-123">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="b60e7-124">**To** パラメーターは、メッセージの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-124">The **To** parameter specifies the message's recipient.</span></span> <span data-ttu-id="b60e7-125">**Subject** パラメーターは、省略可能な **Body** パラメーターが含まれていないため、テキスト文字列の **テストメール** をメッセージとして使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-125">The **Subject** parameter uses the text string **Test mail** as the message because the optional **Body** parameter is not included.</span></span>

### <span data-ttu-id="b60e7-126">例 2: 添付ファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="b60e7-126">Example 2: Send an attachment</span></span>

<span data-ttu-id="b60e7-127">この例では、添付ファイルを含む電子メールメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-127">This example sends an email message with an attachment.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

<span data-ttu-id="b60e7-128">`Send-MailMessage`コマンドレットは、 **From** パラメーターを使用して、メッセージの送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-128">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="b60e7-129">**To** パラメーターは、メッセージの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-129">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="b60e7-130">**Subject** パラメーターは、メッセージの内容を記述します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-130">The **Subject** parameter describes the content of the message.</span></span> <span data-ttu-id="b60e7-131">**Body** パラメーターは、メッセージの内容です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-131">The **Body** parameter is the content of the message.</span></span>

<span data-ttu-id="b60e7-132">**Attachments** パラメーターは、電子メールメッセージに添付されている現在のディレクトリ内のファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-132">The **Attachments** parameter specifies the file in the current directory that is attached to the email message.</span></span> <span data-ttu-id="b60e7-133">**Priority** パラメーターを指定すると、メッセージは **高** 優先度に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-133">The **Priority** parameter sets the message to **High** priority.</span></span> <span data-ttu-id="b60e7-134">**-Deliverynotificationoption** パラメーターには、 **OnSuccess** と **OnFailure** の2つの値が指定されています。</span><span class="sxs-lookup"><span data-stu-id="b60e7-134">The **-DeliveryNotificationOption** parameter specifies two values, **OnSuccess** and **OnFailure** .</span></span> <span data-ttu-id="b60e7-135">送信側は、メッセージの配信が成功したか失敗したかを確認する電子メール通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-135">The sender will receive email notifications to confirm the success or failure of the message delivery.</span></span>
<span data-ttu-id="b60e7-136">**Smtpserver** パラメーターは、SMTP サーバーを **smtp.fabrikam.com** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-136">The **SmtpServer** parameter sets the SMTP server to **smtp.fabrikam.com** .</span></span>

### <span data-ttu-id="b60e7-137">例 3: メーリングリストに電子メールを送信する</span><span class="sxs-lookup"><span data-stu-id="b60e7-137">Example 3: Send email to a mailing list</span></span>

<span data-ttu-id="b60e7-138">この例では、メーリングリストに電子メールメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-138">This example sends an email message to a mailing list.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

<span data-ttu-id="b60e7-139">`Send-MailMessage`コマンドレットは、 **From** パラメーターを使用して、メッセージの送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-139">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="b60e7-140">**To** パラメーターは、メッセージの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-140">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="b60e7-141">**Cc** パラメーターは、指定された受信者にメッセージのコピーを送信します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-141">The **Cc** parameter sends a copy of the message to the specified recipient.</span></span> <span data-ttu-id="b60e7-142">**Bcc** パラメーターを指定すると、メッセージのブラインドコピーが送信されます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-142">The **Bcc** parameter sends a blind copy of the message.</span></span> <span data-ttu-id="b60e7-143">ブラインドコピーは、他の受信者には表示されない電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="b60e7-143">A blind copy is an email address that is hidden from the other recipients.</span></span> <span data-ttu-id="b60e7-144">省略可能な **Body** パラメーターは含まれていないため、 **Subject** パラメーターはメッセージです。</span><span class="sxs-lookup"><span data-stu-id="b60e7-144">The **Subject** parameter is the message because the optional **Body** parameter is not included.</span></span>

<span data-ttu-id="b60e7-145">**Credential** パラメーターは、メッセージの送信にドメイン管理者の資格情報を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-145">The **Credential** parameter specifies a domain administrator's credentials are used to send the message.</span></span> <span data-ttu-id="b60e7-146">**UseSsl** パラメーターは、Secure Socket LAYER (SSL) がセキュリティで保護された接続を作成することを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-146">The **UseSsl** parameter specifies that Secure Socket Layer (SSL) creates a secure connection.</span></span>

## <span data-ttu-id="b60e7-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b60e7-147">PARAMETERS</span></span>

### <span data-ttu-id="b60e7-148">-添付ファイル</span><span class="sxs-lookup"><span data-stu-id="b60e7-148">-Attachments</span></span>

<span data-ttu-id="b60e7-149">電子メールメッセージに添付するファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-149">Specifies the path and file names of files to be attached to the email message.</span></span> <span data-ttu-id="b60e7-150">このパラメーターを使用するか、パスとファイル名をにパイプすることができ `Send-MailMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-150">You can use this parameter or pipe the paths and file names to `Send-MailMessage`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-151">-Bcc</span><span class="sxs-lookup"><span data-stu-id="b60e7-151">-Bcc</span></span>

<span data-ttu-id="b60e7-152">メールのコピーを受信するが、メッセージの受信者としては表示されない電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-152">Specifies the email addresses that receive a copy of the mail but are not listed as recipients of the message.</span></span> <span data-ttu-id="b60e7-153">名前 (省略可能) と電子メールアドレス (など) を入力し `Name <someone@fabrikam.com>` ます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-153">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-154">-本文</span><span class="sxs-lookup"><span data-stu-id="b60e7-154">-Body</span></span>

<span data-ttu-id="b60e7-155">電子メールメッセージの内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-155">Specifies the content of the email message.</span></span>

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

### <span data-ttu-id="b60e7-156">-BodyAsHtml</span><span class="sxs-lookup"><span data-stu-id="b60e7-156">-BodyAsHtml</span></span>

<span data-ttu-id="b60e7-157">**Body** パラメーターの値に HTML が含まれていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-157">Specifies that the value of the **Body** parameter contains HTML.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-158">-Cc</span><span class="sxs-lookup"><span data-stu-id="b60e7-158">-Cc</span></span>

<span data-ttu-id="b60e7-159">電子メールメッセージのカーボンコピー (CC) の送信先となる電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-159">Specifies the email addresses to which a carbon copy (CC) of the email message is sent.</span></span> <span data-ttu-id="b60e7-160">名前 (省略可能) と電子メールアドレス (など) を入力し `Name <someone@fabrikam.com>` ます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-160">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="b60e7-161">-Credential</span></span>

<span data-ttu-id="b60e7-162">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-162">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="b60e7-163">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b60e7-163">The default is the current user.</span></span>

<span data-ttu-id="b60e7-164">**User01** や **domain01\user01」** などのユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-164">Type a user name, such as **User01** or **Domain01\User01** .</span></span> <span data-ttu-id="b60e7-165">または、コマンドレットのような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-165">Or, enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="b60e7-166">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="b60e7-167">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b60e7-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-168">-DeliveryNotificationOption</span><span class="sxs-lookup"><span data-stu-id="b60e7-168">-DeliveryNotificationOption</span></span>

<span data-ttu-id="b60e7-169">電子メールメッセージの配信通知オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-169">Specifies the delivery notification options for the email message.</span></span> <span data-ttu-id="b60e7-170">複数の値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-170">You can specify multiple values.</span></span>
<span data-ttu-id="b60e7-171">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-171">None is the default value.</span></span> <span data-ttu-id="b60e7-172">このパラメーターのエイリアスは **Dno** です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-172">The alias for this parameter is **DNO** .</span></span>

<span data-ttu-id="b60e7-173">配信通知は、 **From** パラメーターのアドレスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-173">The delivery notifications are sent to the address in the **From** parameter.</span></span>

<span data-ttu-id="b60e7-174">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b60e7-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b60e7-175">`None`: 通知がありません。</span><span class="sxs-lookup"><span data-stu-id="b60e7-175">`None`: No notification.</span></span>
- <span data-ttu-id="b60e7-176">`OnSuccess`: 配信が成功した場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-176">`OnSuccess`: Notify if the delivery is successful.</span></span>
- <span data-ttu-id="b60e7-177">`OnFailure`: 配信に失敗した場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-177">`OnFailure`: Notify if the delivery is unsuccessful.</span></span>
- <span data-ttu-id="b60e7-178">`Delay`: 配信が遅延した場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-178">`Delay`: Notify if the delivery is delayed.</span></span>
- <span data-ttu-id="b60e7-179">`Never`: 通知しないでください。</span><span class="sxs-lookup"><span data-stu-id="b60e7-179">`Never`: Never notify.</span></span>

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-180">-Encoding</span><span class="sxs-lookup"><span data-stu-id="b60e7-180">-Encoding</span></span>

<span data-ttu-id="b60e7-181">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-181">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="b60e7-182">既定値は `Default` です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-182">The default value is `Default`.</span></span>

<span data-ttu-id="b60e7-183">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b60e7-183">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b60e7-184">`ASCII` ASCII (7 ビット) 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-184">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="b60e7-185">`BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-185">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="b60e7-186">`Default` は、システムのアクティブなコードページ (通常は ANSI) に対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-186">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="b60e7-187">`OEM` は、システムの現在の OEM コードページに対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-187">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="b60e7-188">`Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-188">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="b60e7-189">`UTF7` UTF-7 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-189">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="b60e7-190">`UTF8` UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-190">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="b60e7-191">`UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-191">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-192">-From</span><span class="sxs-lookup"><span data-stu-id="b60e7-192">-From</span></span>

<span data-ttu-id="b60e7-193">**From** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-193">The **From** parameter is required.</span></span> <span data-ttu-id="b60e7-194">このパラメーターは、送信者の電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-194">This parameter specifies the sender's email address.</span></span> <span data-ttu-id="b60e7-195">名前 (省略可能) と電子メールアドレス (など) を入力し `Name <someone@fabrikam.com>` ます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-195">Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-196">-Port</span><span class="sxs-lookup"><span data-stu-id="b60e7-196">-Port</span></span>

<span data-ttu-id="b60e7-197">SMTP サーバーの代替ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-197">Specifies an alternate port on the SMTP server.</span></span> <span data-ttu-id="b60e7-198">既定値は 25 です。これは、既定の SMTP ポートです。</span><span class="sxs-lookup"><span data-stu-id="b60e7-198">The default value is 25, which is the default SMTP port.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-199">-Priority</span><span class="sxs-lookup"><span data-stu-id="b60e7-199">-Priority</span></span>

<span data-ttu-id="b60e7-200">電子メールメッセージの優先度を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-200">Specifies the priority of the email message.</span></span> <span data-ttu-id="b60e7-201">既定値は Normal です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-201">Normal is the default.</span></span> <span data-ttu-id="b60e7-202">このパラメーターに指定できる値は、Normal、High、および Low です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-202">The acceptable values for this parameter are Normal, High, and Low.</span></span>

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-203">-SmtpServer</span><span class="sxs-lookup"><span data-stu-id="b60e7-203">-SmtpServer</span></span>

<span data-ttu-id="b60e7-204">電子メールメッセージを送信する SMTP サーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-204">Specifies the name of the SMTP server that sends the email message.</span></span>

<span data-ttu-id="b60e7-205">既定値は、ユーザー設定変数の値です `$PSEmailServer` 。</span><span class="sxs-lookup"><span data-stu-id="b60e7-205">The default value is the value of the `$PSEmailServer` preference variable.</span></span> <span data-ttu-id="b60e7-206">ユーザー設定変数が設定されておらず、このパラメーターが使用されていない場合、 `Send-MailMessage` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-206">If the preference variable is not set and this parameter is not used, the `Send-MailMessage` command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-207">-Subject</span><span class="sxs-lookup"><span data-stu-id="b60e7-207">-Subject</span></span>

<span data-ttu-id="b60e7-208">**Subject** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-208">The **Subject** parameter is required.</span></span> <span data-ttu-id="b60e7-209">このパラメーターは、電子メールメッセージの件名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-209">This parameter specifies the subject of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-210">-To</span><span class="sxs-lookup"><span data-stu-id="b60e7-210">-To</span></span>

<span data-ttu-id="b60e7-211">**To** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-211">The **To** parameter is required.</span></span> <span data-ttu-id="b60e7-212">このパラメーターは、受信者の電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-212">This parameter specifies the recipient's email address.</span></span> <span data-ttu-id="b60e7-213">複数の受信者がいる場合は、それらのアドレスをコンマ () で区切り `,` ます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-213">If there are multiple recipients, separate their addresses with a comma (`,`).</span></span> <span data-ttu-id="b60e7-214">名前 (省略可能) と電子メールアドレス (など) を入力し `Name <someone@fabrikam.com>` ます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-214">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b60e7-215">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="b60e7-215">-UseSsl</span></span>

<span data-ttu-id="b60e7-216">リモートコンピューターへのセキュリティで保護された接続を確立してメールを送信するには、Secure Sockets Layer (SSL) プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b60e7-216">The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail.</span></span> <span data-ttu-id="b60e7-217">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="b60e7-217">By default, SSL is not used.</span></span>

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

### <span data-ttu-id="b60e7-218">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b60e7-218">CommonParameters</span></span>

<span data-ttu-id="b60e7-219">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b60e7-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b60e7-220">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b60e7-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b60e7-221">入力</span><span class="sxs-lookup"><span data-stu-id="b60e7-221">INPUTS</span></span>

### <span data-ttu-id="b60e7-222">System.String</span><span class="sxs-lookup"><span data-stu-id="b60e7-222">System.String</span></span>

<span data-ttu-id="b60e7-223">パイプを使用して、添付ファイルのパスとファイル名をにパイプすることができ `Send-MailMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="b60e7-223">You can pipe the path and file names of attachments to `Send-MailMessage`.</span></span>

## <span data-ttu-id="b60e7-224">出力</span><span class="sxs-lookup"><span data-stu-id="b60e7-224">OUTPUTS</span></span>

### <span data-ttu-id="b60e7-225">なし</span><span class="sxs-lookup"><span data-stu-id="b60e7-225">None</span></span>

<span data-ttu-id="b60e7-226">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="b60e7-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b60e7-227">注</span><span class="sxs-lookup"><span data-stu-id="b60e7-227">NOTES</span></span>

## <span data-ttu-id="b60e7-228">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b60e7-228">RELATED LINKS</span></span>

[<span data-ttu-id="b60e7-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="b60e7-229">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="b60e7-230">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="b60e7-230">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)
