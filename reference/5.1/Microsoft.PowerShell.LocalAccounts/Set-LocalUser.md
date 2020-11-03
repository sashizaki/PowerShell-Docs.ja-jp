---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalUser
ms.openlocfilehash: a6352611b757dae828a2efef07f9ce65abaa5e2e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215616"
---
# <span data-ttu-id="7aeed-103">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7aeed-103">Set-LocalUser</span></span>

## <span data-ttu-id="7aeed-104">概要</span><span class="sxs-lookup"><span data-stu-id="7aeed-104">SYNOPSIS</span></span>
<span data-ttu-id="7aeed-105">ローカルユーザーアカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-105">Modifies a local user account.</span></span>

## <span data-ttu-id="7aeed-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7aeed-106">SYNTAX</span></span>

### <span data-ttu-id="7aeed-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="7aeed-107">Name (Default)</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Name] <String> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7aeed-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="7aeed-108">InputObject</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-InputObject] <LocalUser> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7aeed-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="7aeed-109">SecurityIdentifier</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Password <SecureString>] [-PasswordNeverExpires <Boolean>] [-SID] <SecurityIdentifier>
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7aeed-110">Description</span><span class="sxs-lookup"><span data-stu-id="7aeed-110">DESCRIPTION</span></span>
<span data-ttu-id="7aeed-111">**LocalUser** コマンドレットは、ローカルユーザーアカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-111">The **Set-LocalUser** cmdlet modifies a local user account.</span></span>
<span data-ttu-id="7aeed-112">このコマンドレットでは、ローカルユーザーアカウントのパスワードをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="7aeed-112">This cmdlet can reset the password of a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="7aeed-113">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="7aeed-113">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="7aeed-114">例</span><span class="sxs-lookup"><span data-stu-id="7aeed-114">EXAMPLES</span></span>

### <span data-ttu-id="7aeed-115">例 1: ユーザーアカウントの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="7aeed-115">Example 1: Change a description of a user account</span></span>

```
PS C:\> Set-LocalUser -Name "Admin07" -Description "Description of this account."
```

<span data-ttu-id="7aeed-116">このコマンドは、Admin07 という名前のユーザーアカウントの説明を変更します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-116">This command changes the description of a user account named Admin07.</span></span>

### <span data-ttu-id="7aeed-117">例 2: アカウントのパスワードを変更する</span><span class="sxs-lookup"><span data-stu-id="7aeed-117">Example 2: Change the password on an account</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> $UserAccount = Get-LocalUser -Name "User02"
PS C:\> $UserAccount | Set-LocalUser -Password $Password
```

<span data-ttu-id="7aeed-118">最初のコマンドは、Read-Host コマンドレットを使用して、パスワードの入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="7aeed-118">The first command prompts you for a password by using the Read-Host cmdlet.</span></span>
<span data-ttu-id="7aeed-119">このコマンドは、パスワードをセキュリティで保護された文字列として $Password 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-119">The command stores the password as a secure string in the $Password variable.</span></span>

<span data-ttu-id="7aeed-120">2番目のコマンドは、 **LocalUser** を使用して、User02 という名前のユーザーアカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-120">The second command gets a user account named User02 by using **Get-LocalUser** .</span></span>
<span data-ttu-id="7aeed-121">このコマンドは、アカウントを $UserAccount 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-121">The command stores the account in the $UserAccount variable.</span></span>

<span data-ttu-id="7aeed-122">3番目のコマンドは、$UserAccount に格納されているユーザーアカウントに新しいパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-122">The third command sets the new password on the user account stored in $UserAccount.</span></span>

## <span data-ttu-id="7aeed-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7aeed-123">PARAMETERS</span></span>

### <span data-ttu-id="7aeed-124">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="7aeed-124">-AccountExpires</span></span>
<span data-ttu-id="7aeed-125">ユーザーアカウントの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-125">Specifies when the user account expires.</span></span>
<span data-ttu-id="7aeed-126">**DateTime** オブジェクトを取得するには、Get-Date コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-126">To obtain a **DateTime** object, use the Get-Date cmdlet.</span></span>

<span data-ttu-id="7aeed-127">アカウントの有効期限が切れないようにするには、 *AccountNeverExpires* パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-127">If you do not want the account to expire, specify the *AccountNeverExpires* parameter.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7aeed-128">-AccountNeverExpires</span><span class="sxs-lookup"><span data-stu-id="7aeed-128">-AccountNeverExpires</span></span>
<span data-ttu-id="7aeed-129">アカウントの有効期限が切れていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-129">Indicates that the account does not expire.</span></span>

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

### <span data-ttu-id="7aeed-130">-Description</span><span class="sxs-lookup"><span data-stu-id="7aeed-130">-Description</span></span>
<span data-ttu-id="7aeed-131">ユーザーアカウントのコメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-131">Specifies a comment for the user account.</span></span>
<span data-ttu-id="7aeed-132">最大長は48文字です。</span><span class="sxs-lookup"><span data-stu-id="7aeed-132">The maximum length is 48 characters.</span></span>

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

### <span data-ttu-id="7aeed-133">-FullName</span><span class="sxs-lookup"><span data-stu-id="7aeed-133">-FullName</span></span>
<span data-ttu-id="7aeed-134">ユーザーアカウントの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-134">Specifies the full name for the user account.</span></span>
<span data-ttu-id="7aeed-135">フルネームは、ユーザーアカウントのユーザー名とは異なります。</span><span class="sxs-lookup"><span data-stu-id="7aeed-135">The full name differs from the user name of the user account.</span></span>

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

### <span data-ttu-id="7aeed-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7aeed-136">-InputObject</span></span>
<span data-ttu-id="7aeed-137">このコマンドレットが変更するユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-137">Specifies the user account that this cmdlet changes.</span></span>
<span data-ttu-id="7aeed-138">ユーザーアカウントを取得するには、Get-LocalUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-138">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7aeed-139">-Name</span><span class="sxs-lookup"><span data-stu-id="7aeed-139">-Name</span></span>
<span data-ttu-id="7aeed-140">このコマンドレットが変更するユーザーアカウントの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-140">Specifies the name of the user account that this cmdlet changes.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7aeed-141">-Password</span><span class="sxs-lookup"><span data-stu-id="7aeed-141">-Password</span></span>
<span data-ttu-id="7aeed-142">ユーザーアカウントのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-142">Specifies a password for the user account.</span></span>
<span data-ttu-id="7aeed-143">ユーザーアカウントが Microsoft アカウントに接続されている場合は、パスワードを設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="7aeed-143">If the user account is connected to a Microsoft account, do not set a password.</span></span>

<span data-ttu-id="7aeed-144">`Read-Host -GetCredential`、SecureString、または ConvertTo-SecureString を使用して、パスワードの **SecureString** オブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7aeed-144">You can use `Read-Host -GetCredential`, Get-Credential, or ConvertTo-SecureString to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="7aeed-145">*Password* パラメーターと *nopassword* パラメーターを省略した場合、 **LocalUser** によってユーザーのパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="7aeed-145">If you omit the *Password* and *NoPassword* parameters, **Set-LocalUser** prompts you for the user's password.</span></span>

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

### <span data-ttu-id="7aeed-146">-PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="7aeed-146">-PasswordNeverExpires</span></span>
<span data-ttu-id="7aeed-147">パスワードの有効期限が切れているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-147">Indicates whether the password expires.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7aeed-148">-SID</span><span class="sxs-lookup"><span data-stu-id="7aeed-148">-SID</span></span>
<span data-ttu-id="7aeed-149">このコマンドレットが変更するユーザーアカウントのセキュリティ ID (SID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-149">Specifies the security ID (SID) of the user account that this cmdlet changes.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7aeed-150">-User@ Changepassword</span><span class="sxs-lookup"><span data-stu-id="7aeed-150">-UserMayChangePassword</span></span>
<span data-ttu-id="7aeed-151">ユーザーがユーザーアカウントのパスワードを変更できることを示します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-151">Indicates that the user can change the password on the user account.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7aeed-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7aeed-152">-Confirm</span></span>
<span data-ttu-id="7aeed-153">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7aeed-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7aeed-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7aeed-154">-WhatIf</span></span>
<span data-ttu-id="7aeed-155">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="7aeed-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7aeed-156">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7aeed-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7aeed-157">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7aeed-157">CommonParameters</span></span>
<span data-ttu-id="7aeed-158">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7aeed-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7aeed-159">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aeed-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7aeed-160">入力</span><span class="sxs-lookup"><span data-stu-id="7aeed-160">INPUTS</span></span>

### <span data-ttu-id="7aeed-161">SecurityAccountsManager、System.string、LocalUser、SecurityIdentifier のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="7aeed-161">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="7aeed-162">このコマンドレットには、ローカルユーザー、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="7aeed-162">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="7aeed-163">出力</span><span class="sxs-lookup"><span data-stu-id="7aeed-163">OUTPUTS</span></span>

### <span data-ttu-id="7aeed-164">なし</span><span class="sxs-lookup"><span data-stu-id="7aeed-164">None</span></span>
<span data-ttu-id="7aeed-165">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="7aeed-165">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7aeed-166">注</span><span class="sxs-lookup"><span data-stu-id="7aeed-166">NOTES</span></span>

* <span data-ttu-id="7aeed-167">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="7aeed-167">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="7aeed-168">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7aeed-168">The possible sources are as follows:</span></span>

- <span data-ttu-id="7aeed-169">ローカル</span><span class="sxs-lookup"><span data-stu-id="7aeed-169">Local</span></span>
- <span data-ttu-id="7aeed-170">Active Directory</span><span class="sxs-lookup"><span data-stu-id="7aeed-170">Active Directory</span></span>
- <span data-ttu-id="7aeed-171">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="7aeed-171">Azure Active Directory group</span></span>
- <span data-ttu-id="7aeed-172">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="7aeed-172">Microsoft Account</span></span>

<span data-ttu-id="7aeed-173">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7aeed-173">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="7aeed-174">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="7aeed-174">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="7aeed-175">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7aeed-175">RELATED LINKS</span></span>

[<span data-ttu-id="7aeed-176">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7aeed-176">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="7aeed-177">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7aeed-177">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="7aeed-178">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7aeed-178">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="7aeed-179">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7aeed-179">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="7aeed-180">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7aeed-180">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="7aeed-181">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7aeed-181">Rename-LocalUser</span></span>](Rename-LocalUser.md)
