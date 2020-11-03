---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroupMember
ms.openlocfilehash: 200368c5d13bd027302ad824533e6c187906ed0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211891"
---
# Get-LocalGroupMember

## 概要
ローカルグループからメンバーを取得します。

## SYNTAX

### 既定値 (既定値)

```
Get-LocalGroupMember [[-Member] <String>] [-Name] <String> [<CommonParameters>]
```

### グループ

```
Get-LocalGroupMember [-Group] <LocalGroup> [[-Member] <String>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalGroupMember [[-Member] <String>] [-SID] <SecurityIdentifier> [<CommonParameters>]
```

## Description
**LocalGroupMember** コマンドレットは、ローカルグループからメンバーを取得します。

> [!NOTE]
> 64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。

## 例

### 例 1: Administrators グループのすべてのメンバーを取得する

```
PS C:\> Get-LocalGroupMember -Group "Administrators"
ObjectClass Name                    PrincipalSource
----------- ----                    ---------------
User        CONTOSOPC\Administrator Local
User        CONTOSOPC\LocalAdmin    Local
```

このコマンドは、ローカルの Administrators グループのすべてのメンバーを取得します。

## PARAMETERS

### -Group
このコマンドレットがメンバーを取得するセキュリティグループを指定します。

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -メンバー
このコマンドレットがセキュリティグループから取得するユーザーまたはグループを指定します。
名前またはセキュリティ ID (SID) を使用して、ユーザーまたはグループを指定できます。
S-R-s-s で SID 文字列を指定します。
. .
(
ワイルドカード文字を使用できます。
このパラメーターを指定しない場合、コマンドレットはグループのすべてのメンバーを取得します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
このコマンドレットがメンバーを取得するセキュリティグループの名前を指定します。

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SID
このコマンドレットがメンバーを取得するセキュリティグループのセキュリティ ID を指定します。

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

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### SecurityAccountsManager、System.string、LocalGroup、SecurityIdentifier のように指定されています。
このコマンドレットには、ローカルグループ、文字列、または SID をパイプすることができます。

## 出力

### SecurityAccountsManager. LocalPrincipal
このコマンドレットは、ローカルプリンシパルを返します。

## 注

* **Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。 考えられるソースは次のとおりです。

- ローカル
- Active Directory
- Azure Active Directory グループ
- Microsoft アカウント

**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。 以前のバージョンの場合、プロパティは空白になります。

## 関連リンク

[Add-LocalGroupMember](Add-LocalGroupMember.md)

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroupMember](Remove-LocalGroupMember.md)
