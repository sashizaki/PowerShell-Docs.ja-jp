---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalUser
ms.openlocfilehash: d83f3ad12481df0849ff2fe3f61d553a9ffdcdde
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214672"
---
# <span data-ttu-id="4e713-103">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4e713-103">New-LocalUser</span></span>

## <span data-ttu-id="4e713-104">概要</span><span class="sxs-lookup"><span data-stu-id="4e713-104">SYNOPSIS</span></span>

<span data-ttu-id="4e713-105">ローカルユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e713-105">Creates a local user account.</span></span>

## <span data-ttu-id="4e713-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4e713-106">SYNTAX</span></span>

### <span data-ttu-id="4e713-107">パスワード (既定値)</span><span class="sxs-lookup"><span data-stu-id="4e713-107">Password (Default)</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> -Password <SecureString> [-PasswordNeverExpires]
 [-UserMayNotChangePassword] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4e713-108">NoPassword</span><span class="sxs-lookup"><span data-stu-id="4e713-108">NoPassword</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> [-NoPassword] [-UserMayNotChangePassword] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="4e713-109">Description</span><span class="sxs-lookup"><span data-stu-id="4e713-109">DESCRIPTION</span></span>

<span data-ttu-id="4e713-110">`New-LocalUser`コマンドレットでは、ローカルユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e713-110">The `New-LocalUser` cmdlet creates a local user account.</span></span> <span data-ttu-id="4e713-111">このコマンドレットは、Microsoft アカウントに接続されているローカルユーザーアカウントまたはローカルユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e713-111">This cmdlet creates a local user account or a local user account that is connected to a Microsoft account.</span></span>

> [!NOTE]
> <span data-ttu-id="4e713-112">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4e713-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="4e713-113">例</span><span class="sxs-lookup"><span data-stu-id="4e713-113">EXAMPLES</span></span>

### <span data-ttu-id="4e713-114">例 1: ユーザーアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="4e713-114">Example 1: Create a user account</span></span>

```
PS C:\> New-LocalUser -Name "User02" -Description "Description of this account." -NoPassword
Name    Enabled  Description
----    -------  -----------
User02  True     Description of this account.
```

<span data-ttu-id="4e713-115">このコマンドは、ローカルユーザーアカウントを作成し、 **Accountexpires** パラメーターまたは **Password** パラメーターを指定しません。</span><span class="sxs-lookup"><span data-stu-id="4e713-115">This command creates a local user account and does not specify the **AccountExpires** or **Password** parameters.</span></span> <span data-ttu-id="4e713-116">このため、既定では、アカウントの有効期限が切れたり、パスワードが設定されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="4e713-116">Therefore, the account doesn't expire or have a password by default.</span></span>

### <span data-ttu-id="4e713-117">例 2: パスワードを持つユーザーアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="4e713-117">Example 2: Create a user account that has a password</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account.
```

<span data-ttu-id="4e713-118">最初のコマンドは、コマンドレットを使用してパスワードの入力を求め `Read-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="4e713-118">The first command prompts you for a password by using the `Read-Host` cmdlet.</span></span> <span data-ttu-id="4e713-119">このコマンドは、パスワードをセキュリティで保護された文字列として変数に格納 `$Password` します。</span><span class="sxs-lookup"><span data-stu-id="4e713-119">The command stores the password as a secure string in the `$Password` variable.</span></span>

<span data-ttu-id="4e713-120">2番目のコマンドは、に格納されているパスワードを使用して、ローカルユーザーアカウントを作成し `$Password` ます。</span><span class="sxs-lookup"><span data-stu-id="4e713-120">The second command creates a local user account by using the password stored in `$Password`.</span></span> <span data-ttu-id="4e713-121">このコマンドでは、ユーザーアカウントのユーザー名、フルネーム、および説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e713-121">The command specifies a user name, full name, and description for the user account.</span></span>

## <span data-ttu-id="4e713-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4e713-122">PARAMETERS</span></span>

### <span data-ttu-id="4e713-123">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="4e713-123">-AccountExpires</span></span>

<span data-ttu-id="4e713-124">ユーザーアカウントの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e713-124">Specifies when the user account expires.</span></span> <span data-ttu-id="4e713-125">**DateTime** オブジェクトを取得するには、 `Get-Date` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e713-125">To obtain a **DateTime** object, use the `Get-Date` cmdlet.</span></span>
<span data-ttu-id="4e713-126">このパラメーターを指定しない場合、アカウントの有効期限は切れません。</span><span class="sxs-lookup"><span data-stu-id="4e713-126">If you do not specify this parameter, the account does not expire.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4e713-127">-AccountNeverExpires</span><span class="sxs-lookup"><span data-stu-id="4e713-127">-AccountNeverExpires</span></span>

<span data-ttu-id="4e713-128">アカウントの有効期限が切れていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="4e713-128">Indicates that the account does not expire.</span></span>

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

### <span data-ttu-id="4e713-129">-Description</span><span class="sxs-lookup"><span data-stu-id="4e713-129">-Description</span></span>

<span data-ttu-id="4e713-130">ユーザーアカウントのコメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e713-130">Specifies a comment for the user account.</span></span>
<span data-ttu-id="4e713-131">最大長は48文字です。</span><span class="sxs-lookup"><span data-stu-id="4e713-131">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4e713-132">-Disabled</span><span class="sxs-lookup"><span data-stu-id="4e713-132">-Disabled</span></span>

<span data-ttu-id="4e713-133">このコマンドレットによってユーザーアカウントが無効として作成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="4e713-133">Indicates that this cmdlet creates the user account as disabled.</span></span>

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

### <span data-ttu-id="4e713-134">-FullName</span><span class="sxs-lookup"><span data-stu-id="4e713-134">-FullName</span></span>

<span data-ttu-id="4e713-135">ユーザーアカウントの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e713-135">Specifies the full name for the user account.</span></span> <span data-ttu-id="4e713-136">フルネームは、ユーザーアカウントのユーザー名とは異なります。</span><span class="sxs-lookup"><span data-stu-id="4e713-136">The full name differs from the user name of the user account.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4e713-137">-Name</span><span class="sxs-lookup"><span data-stu-id="4e713-137">-Name</span></span>

<span data-ttu-id="4e713-138">ユーザーアカウントのユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e713-138">Specifies the user name for the user account.</span></span>

<span data-ttu-id="4e713-139">ローカルシステムのローカルユーザーアカウントを作成する場合、ユーザー名には、最大20文字の大文字または小文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4e713-139">If you create a local user account for the local system, the user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="4e713-140">ユーザー名に次の文字を含めることはできません:</span><span class="sxs-lookup"><span data-stu-id="4e713-140">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="4e713-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="4e713-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

<span data-ttu-id="4e713-142">ユーザー名をピリオドまたはスペースのみで構成することはできません `.` 。</span><span class="sxs-lookup"><span data-stu-id="4e713-142">A user name cannot consist only of periods `.` or spaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4e713-143">-NoPassword</span><span class="sxs-lookup"><span data-stu-id="4e713-143">-NoPassword</span></span>

<span data-ttu-id="4e713-144">ユーザーアカウントにパスワードがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="4e713-144">Indicates that the user account does not have a password.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoPassword
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4e713-145">-Password</span><span class="sxs-lookup"><span data-stu-id="4e713-145">-Password</span></span>

<span data-ttu-id="4e713-146">ユーザーアカウントのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e713-146">Specifies a password for the user account.</span></span> <span data-ttu-id="4e713-147">、、またはを使用して、 `Read-Host -GetCredential` `Get-Credential` `ConvertTo-SecureString` パスワードの **SecureString** オブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4e713-147">You can use `Read-Host -GetCredential`, `Get-Credential`, or `ConvertTo-SecureString` to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="4e713-148">**Password** パラメーターと **nopassword** パラメーターを省略すると、によって `New-LocalUser` 新しいユーザーのパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="4e713-148">If you omit the **Password** and **NoPassword** parameters, `New-LocalUser` prompts you for the new user's password.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: Password
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4e713-149">-PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="4e713-149">-PasswordNeverExpires</span></span>

<span data-ttu-id="4e713-150">パスワードの有効期限が切れているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4e713-150">Indicates whether the password expires.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Password
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4e713-151">-User@ Notchangepassword</span><span class="sxs-lookup"><span data-stu-id="4e713-151">-UserMayNotChangePassword</span></span>

<span data-ttu-id="4e713-152">ユーザーがユーザーアカウントのパスワードを変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="4e713-152">Indicates that the user cannot change the password on the user account.</span></span>

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

### <span data-ttu-id="4e713-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4e713-153">-Confirm</span></span>

<span data-ttu-id="4e713-154">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e713-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4e713-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4e713-155">-WhatIf</span></span>

<span data-ttu-id="4e713-156">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4e713-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4e713-157">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4e713-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4e713-158">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e713-158">CommonParameters</span></span>

<span data-ttu-id="4e713-159">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="4e713-159">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="4e713-160">詳細については、「[about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e713-160">For more information, see [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4e713-161">入力</span><span class="sxs-lookup"><span data-stu-id="4e713-161">INPUTS</span></span>

### <span data-ttu-id="4e713-162">System.string、System.string、SecureString、システムを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e713-162">System.String, System.DateTime, System.Boolean, System.Security.SecureString</span></span>

<span data-ttu-id="4e713-163">パイプを使用して、文字列、 **DateTime** オブジェクト、ブール値、またはセキュリティで保護された文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="4e713-163">You can pipe a string, a **DateTime** object, a boolean value, or a secure string to this cmdlet.</span></span>

## <span data-ttu-id="4e713-164">出力</span><span class="sxs-lookup"><span data-stu-id="4e713-164">OUTPUTS</span></span>

### <span data-ttu-id="4e713-165">SecurityAccountsManager. LocalUser (システムの管理)</span><span class="sxs-lookup"><span data-stu-id="4e713-165">System.Management.Automation.SecurityAccountsManager.LocalUser</span></span>

<span data-ttu-id="4e713-166">このコマンドレットは、 **LocalUser** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4e713-166">This cmdlet returns a **LocalUser** object.</span></span>
<span data-ttu-id="4e713-167">このオブジェクトは、ユーザーアカウントに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e713-167">This object provides information about the user account.</span></span>

## <span data-ttu-id="4e713-168">注</span><span class="sxs-lookup"><span data-stu-id="4e713-168">NOTES</span></span>

- <span data-ttu-id="4e713-169">コンピューター上の他のユーザー名またはグループ名と同じユーザー名を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4e713-169">A user name cannot be identical to any other user name or group name on the computer.</span></span> <span data-ttu-id="4e713-170">ユーザー名をピリオドまたはスペースのみで構成することはできません `.` 。</span><span class="sxs-lookup"><span data-stu-id="4e713-170">A user name cannot consist only of periods `.` or spaces.</span></span> <span data-ttu-id="4e713-171">ユーザー名には、最大20文字の大文字または小文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e713-171">A user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="4e713-172">ユーザー名に次の文字を含めることはできません:</span><span class="sxs-lookup"><span data-stu-id="4e713-172">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="4e713-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="4e713-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

- <span data-ttu-id="4e713-174">パスワードには、最大127文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4e713-174">A password can contain up to 127 characters.</span></span>
- <span data-ttu-id="4e713-175">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="4e713-175">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="4e713-176">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4e713-176">The possible sources are as follows:</span></span>

  - <span data-ttu-id="4e713-177">ローカル</span><span class="sxs-lookup"><span data-stu-id="4e713-177">Local</span></span>
  - <span data-ttu-id="4e713-178">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4e713-178">Active Directory</span></span>
  - <span data-ttu-id="4e713-179">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="4e713-179">Azure Active Directory group</span></span>
  - <span data-ttu-id="4e713-180">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="4e713-180">Microsoft Account</span></span>

> [!NOTE]
> <span data-ttu-id="4e713-181">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4e713-181">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="4e713-182">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="4e713-182">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="4e713-183">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4e713-183">RELATED LINKS</span></span>

[<span data-ttu-id="4e713-184">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4e713-184">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="4e713-185">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4e713-185">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="4e713-186">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4e713-186">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="4e713-187">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4e713-187">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="4e713-188">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4e713-188">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="4e713-189">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4e713-189">Set-LocalUser</span></span>](Set-LocalUser.md)
