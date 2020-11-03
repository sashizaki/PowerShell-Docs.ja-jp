---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroup
ms.openlocfilehash: 2cd77c2766840527825b0ccf68abaac3c2ea6c16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211904"
---
# Get-LocalGroup

## 概要
ローカルセキュリティグループを取得します。

## SYNTAX

### 既定値 (既定値)

```
Get-LocalGroup [[-Name] <String[]>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalGroup [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## Description
**LocalGroup** コマンドレットは、セキュリティアカウントマネージャーのローカルセキュリティグループを取得します。
このコマンドレットは、作成する既定の組み込みグループとローカルセキュリティグループを取得します。

> [!NOTE]
> 64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。

## 例

### 例 1: 管理者グループを取得する

```
PS C:\> Get-LocalGroup -Name "Administrators"
Name           Description
----           -----------
Administrators Administrators have complete and unrestricted access to the computer/domain
```

このコマンドは、ローカルの Administrators グループを取得します。
コマンドを実行すると、コンソールにグループのプロパティが表示されます。

## PARAMETERS

### -Name
このコマンドレットが取得するセキュリティグループの名前の配列を指定します。
ワイルドカード文字を使用できます。

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SID
このコマンドレットが取得するセキュリティグループのセキュリティ Id (Sid) の配列を指定します。

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.string, SecurityIdentifier (システムのセキュリティ)
このコマンドレットには、文字列または SID をパイプすることができます。

## 出力

### SecurityAccountsManager. LocalGroup (システムの管理)
このコマンドレットは、ローカルグループを返します。

## 注

* **Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。 考えられるソースは次のとおりです。

- ローカル
- Active Directory
- Azure Active Directory グループ
- Microsoft アカウント

**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。 以前のバージョンの場合、プロパティは空白になります。

## 関連リンク

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroup](Remove-LocalGroup.md)

[Rename-LocalGroup](Rename-LocalGroup.md)

[Set-LocalGroup](Set-LocalGroup.md)
