---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-LocalGroupMember
ms.openlocfilehash: 06993c8f6618472f4809e37fbf83d298d13ae515
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211928"
---
# Add-LocalGroupMember

## 概要
ローカルグループにメンバーを追加します。

## SYNTAX

### グループ

```
Add-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Default

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Description

`Add-LocalGroupMember`コマンドレットでは、ユーザーまたはグループをローカルセキュリティグループに追加します。 グループに割り当てられているすべての権利とアクセス許可が、そのグループのすべてのメンバーに割り当てられます。

ローカル コンピューター上の Administrators グループのメンバーはそのコンピューター上でフル コントロールのアクセス許可を持ちます。 Administrators グループのユーザー数を制限します。

コンピューターがドメインに参加している場合、そのドメインと信頼される側のドメインから、ユーザー アカウント、コンピューター アカウント、およびグループ アカウントをローカル グループに追加できます。

> [!NOTE]
> コンピューターがドメインに参加していて、ドメインのメンバーと同じ名前を持つローカルユーザーを追加しようとすると、ドメインメンバーが追加されます。

## 例

### 例 1: Administrators グループにメンバーを追加する

このコマンドは、ローカルの Administrators グループに複数のメンバーを追加します。 新しいメンバーには、ローカルユーザーアカウント、Microsoft アカウント、Azure Active Directory アカウント、ドメイングループが含まれます。 この例では、Outlook.com のアカウントのユーザー名にプレースホルダー値を使用します。

```powershell
Add-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

## PARAMETERS

### -Group

このコマンドレットがメンバーを追加するセキュリティグループを指定します。

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -メンバー

このコマンドレットによってセキュリティグループに追加されるユーザーまたはグループの配列を指定します。 名前、セキュリティ ID (SID)、または **Localprincipal** オブジェクトを使用して、ユーザーまたはグループを指定できます。

```yaml
Type: Microsoft.PowerShell.Commands.LocalPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

このコマンドレットがメンバーを追加するセキュリティグループの名前を指定します。

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SID

このコマンドレットがメンバーを追加するセキュリティグループのセキュリティ ID を指定します。

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

コマンドレットの実行時に発生する内容を示します。 このコマンドレットは実行されません。

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

このコマンドレットには、ローカルプリンシパル、文字列、または SID をパイプすることができます。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。

**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。 考えられるソースは次のとおりです。

- ローカル
- Active Directory
- Azure Active Directory グループ
- Microsoft アカウント

**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。 以前のバージョンの場合、プロパティは空白になります。

## 関連リンク

[Get-LocalGroupMember](Get-LocalGroupMember.md)

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroupMember](Remove-LocalGroupMember.md)
