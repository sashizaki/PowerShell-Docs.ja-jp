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
# New-LocalUser

## 概要

ローカルユーザーアカウントを作成します。

## SYNTAX

### パスワード (既定値)

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> -Password <SecureString> [-PasswordNeverExpires]
 [-UserMayNotChangePassword] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NoPassword

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> [-NoPassword] [-UserMayNotChangePassword] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Description

`New-LocalUser`コマンドレットでは、ローカルユーザーアカウントを作成します。 このコマンドレットは、Microsoft アカウントに接続されているローカルユーザーアカウントまたはローカルユーザーアカウントを作成します。

> [!NOTE]
> 64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。

## 例

### 例 1: ユーザーアカウントを作成する

```
PS C:\> New-LocalUser -Name "User02" -Description "Description of this account." -NoPassword
Name    Enabled  Description
----    -------  -----------
User02  True     Description of this account.
```

このコマンドは、ローカルユーザーアカウントを作成し、 **Accountexpires** パラメーターまたは **Password** パラメーターを指定しません。 このため、既定では、アカウントの有効期限が切れたり、パスワードが設定されたりすることはありません。

### 例 2: パスワードを持つユーザーアカウントを作成する

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account.
```

最初のコマンドは、コマンドレットを使用してパスワードの入力を求め `Read-Host` ます。 このコマンドは、パスワードをセキュリティで保護された文字列として変数に格納 `$Password` します。

2番目のコマンドは、に格納されているパスワードを使用して、ローカルユーザーアカウントを作成し `$Password` ます。 このコマンドでは、ユーザーアカウントのユーザー名、フルネーム、および説明を指定します。

## PARAMETERS

### -AccountExpires

ユーザーアカウントの有効期限を指定します。 **DateTime** オブジェクトを取得するには、 `Get-Date` コマンドレットを使用します。
このパラメーターを指定しない場合、アカウントの有効期限は切れません。

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

### -AccountNeverExpires

アカウントの有効期限が切れていないことを示します。

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

### -Description

ユーザーアカウントのコメントを指定します。
最大長は48文字です。

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

### -Disabled

このコマンドレットによってユーザーアカウントが無効として作成されることを示します。

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

### -FullName

ユーザーアカウントの完全な名前を指定します。 フルネームは、ユーザーアカウントのユーザー名とは異なります。

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

### -Name

ユーザーアカウントのユーザー名を指定します。

ローカルシステムのローカルユーザーアカウントを作成する場合、ユーザー名には、最大20文字の大文字または小文字を含めることができます。 ユーザー名に次の文字を含めることはできません:

`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`

ユーザー名をピリオドまたはスペースのみで構成することはできません `.` 。

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

### -NoPassword

ユーザーアカウントにパスワードがないことを示します。

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

### -Password

ユーザーアカウントのパスワードを指定します。 、、またはを使用して、 `Read-Host -GetCredential` `Get-Credential` `ConvertTo-SecureString` パスワードの **SecureString** オブジェクトを作成できます。

**Password** パラメーターと **nopassword** パラメーターを省略すると、によって `New-LocalUser` 新しいユーザーのパスワードの入力が求められます。

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

### -PasswordNeverExpires

パスワードの有効期限が切れているかどうかを示します。

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

### -User@ Notchangepassword

ユーザーがユーザーアカウントのパスワードを変更できないことを示します。

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

### -Confirm

コマンドレットの実行前に確認を求めるメッセージが表示されます。

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

### -WhatIf

コマンドレットの実行時に発生する内容を示します。
このコマンドレットは実行されません。

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

### 共通パラメーター

このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。 詳細については、「[about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### System.string、System.string、SecureString、システムを指定します。

パイプを使用して、文字列、 **DateTime** オブジェクト、ブール値、またはセキュリティで保護された文字列をこのコマンドレットに送ることができます。

## 出力

### SecurityAccountsManager. LocalUser (システムの管理)

このコマンドレットは、 **LocalUser** オブジェクトを返します。
このオブジェクトは、ユーザーアカウントに関する情報を提供します。

## 注

- コンピューター上の他のユーザー名またはグループ名と同じユーザー名を使用することはできません。 ユーザー名をピリオドまたはスペースのみで構成することはできません `.` 。 ユーザー名には、最大20文字の大文字または小文字を使用できます。 ユーザー名に次の文字を含めることはできません:

`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`

- パスワードには、最大127文字を含めることができます。
- **Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。 考えられるソースは次のとおりです。

  - ローカル
  - Active Directory
  - Azure Active Directory グループ
  - Microsoft アカウント

> [!NOTE]
> **Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。 以前のバージョンの場合、プロパティは空白になります。

## 関連リンク

[Disable-LocalUser](Disable-LocalUser.md)

[Enable-LocalUser](Enable-LocalUser.md)

[Get-LocalUser](Get-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
