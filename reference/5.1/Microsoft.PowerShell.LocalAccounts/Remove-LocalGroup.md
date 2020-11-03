---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroup
ms.openlocfilehash: 6a2f921972fef1794581b301df6e7439e56c7f47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214675"
---
# Remove-LocalGroup

## 概要
ローカルセキュリティグループを削除します。

## SYNTAX

### InputObject

```
Remove-LocalGroup [-InputObject] <LocalGroup[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Default

```
Remove-LocalGroup [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Remove-LocalGroup [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**LocalGroup** コマンドレットは、ローカルセキュリティグループを削除します。
このコマンドレットは、ローカルグループのみを削除します。
そのグループに属するユーザーアカウント、コンピューターアカウント、またはグループアカウントは削除されません。
削除されたグループを回復することはできません。

グループを削除してから、同じグループ名を持つ別のグループを作成する場合は、新しいグループに新しいアクセス許可を設定する必要があります。
新しいグループは、そのグループに割り当てられたアクセス許可を継承しません。

> [!NOTE]
> 64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。

## 例

### 例 1: セキュリティグループを削除する

```
PS C:\> Remove-LocalGroup -Name "SecurityGroup04"
```

このコマンドは、SecurityGroup04 という名前のグループを削除します。

## PARAMETERS

### -InputObject
このコマンドレットが削除するセキュリティグループの配列を指定します。
グループを取得するには、Get-LocalGroup コマンドレットを使用します。

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
このコマンドレットが削除するセキュリティグループの名前の配列を指定します。

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
このコマンドレットが削除するセキュリティグループのセキュリティ Id (Sid) の配列を指定します。

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

### SecurityAccountsManager、System.string、LocalGroup、SecurityIdentifier のように指定されています。
このコマンドレットには、セキュリティグループ、文字列、または SID をパイプすることができます。

## 出力

### なし
このコマンドレットは出力を生成しません。

## 注

* このコマンドレットでは、次の既定のグループを削除することはできません。

- 管理者
- Backup Operators
- Cryptographic Operators
- Distributed COM Users
- イベント ログ リーダー
- ゲスト
- Hyper-V 管理者
- IIS_IUSRS
- Network Configuration Operators
- パフォーマンス ログ ユーザー
- パフォーマンス モニター ユーザー
- Power Users
- Remote Desktop Users
- リモート管理ユーザー
- レプリケーター
- ユーザー
- WinRMRemoteWMIUsers__

* **Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。 考えられるソースは次のとおりです。

- ローカル
- Active Directory
- Azure Active Directory グループ
- Microsoft アカウント

**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。 以前のバージョンの場合、プロパティは空白になります。

## 関連リンク

[Get-LocalGroup](Get-LocalGroup.md)

[New-LocalGroup](New-LocalGroup.md)

[Rename-LocalGroup](Rename-LocalGroup.md)

[Set-LocalGroup](Set-LocalGroup.md)
