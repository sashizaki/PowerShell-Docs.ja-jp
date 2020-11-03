---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/enable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-LocalUser
ms.openlocfilehash: 80d062578e7114b69e5cb5f3367b56da3871b9df
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211915"
---
# Enable-LocalUser

## 概要
ローカルユーザーアカウントを有効にします。

## SYNTAX

### InputObject

```
Enable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Default

```
Enable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Enable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**LocalUser** コマンドレットは、ローカルユーザーアカウントを有効にします。
ユーザーアカウントが無効になっている場合、ユーザーはログオンできません。
ユーザーアカウントが有効になっている場合、ユーザーはログオンできます。

> [!NOTE]
> 64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。

## 例

### 例 1: 名前を指定してアカウントを有効にする

```
PS C:\> Enable-LocalUser -Name "Admin02"
```

このコマンドにより、Admin02 という名前のユーザーアカウントが有効になります。

### 例 2: パイプラインを使用してアカウントを有効にする

```
PS C:\> Get-LocalUser -Name "Administrator" | Enable-LocalUser
```

このコマンドは、 **LocalUser** を使用してビルトイン Administrator アカウントを取得し、パイプライン演算子を使用して現在のコマンドレットに渡します。
このコマンドレットは、そのアカウントを有効にします。

## PARAMETERS

### -InputObject
このコマンドレットで有効にするユーザーアカウントの配列を指定します。
ユーザーアカウントを取得するには、Get-LocalUser コマンドレットを使用します。

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
このコマンドレットで有効にするユーザーアカウントの名前の配列を指定します。

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SID
このコマンドレットで有効にするユーザーアカウントの配列を指定します。

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### SecurityAccountsManager、System.string、LocalUser、SecurityIdentifier のように指定されています。
このコマンドレットには、ローカルユーザー、文字列、または SID をパイプすることができます。

## 出力

### なし
このコマンドレットは出力を生成しません。

## 注

* **Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。 考えられるソースは次のとおりです。

- ローカル
- Active Directory
- Azure Active Directory グループ
- Microsoft アカウント

**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。 以前のバージョンの場合、プロパティは空白になります。

## 関連リンク

[Disable-LocalUser](Disable-LocalUser.md)

[Get-LocalUser](Get-LocalUser.md)

[New-LocalUser](New-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
