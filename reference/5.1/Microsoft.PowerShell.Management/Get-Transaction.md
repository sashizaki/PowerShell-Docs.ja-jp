---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Transaction
ms.openlocfilehash: bb8e9e1f204c67207f31613181f856d3bcaf8dc3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209023"
---
# Get-Transaction

## 概要
現在の (有効な) トランザクションを取得します。

## SYNTAX

```
Get-Transaction [<CommonParameters>]
```

## Description
**Get transaction** コマンドレットは、セッションの現在のトランザクションを表すオブジェクトを取得します。

有効なトランザクションは一度に 1 つしかないので、このコマンドレットが複数のオブジェクトを返すことはありません。
(開始トランザクションの独立したパラメーターを使用して) 1 つまたは複数の独立したトランザクションを開始すると、最も最近開始されたトランザクションがアクティブになり **、トランザクションが返され** ます。

すべてのアクティブなトランザクションがロールバックまたはコミットされている場合、このコマンドレットは、セッションで最後にアクティブになったトランザクションを表示します。

このコマンドレットは、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。
詳細については、「about_Transactions」を参照してください。

## 例

### 例 1: 現在のトランザクションを取得する

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

このコマンドは、Get-Transaction コマンドレットを使用して現在のトランザクションを取得します。

### 例 2: トランザクションオブジェクトのプロパティとメソッドを表示する

```
PS C:\> Get-Transaction | Get-Member

Name               MemberType Definition
----               ---------- ----------
Dispose            Method     System.Void Dispose(), System.Void Dispose(Boolean disposing)
Equals             Method     System.Boolean Equals(Object obj)
GetHashCode        Method     System.Int32 GetHashCode()
GetType            Method     System.Type GetType()
ToString           Method     System.String ToString()
IsCommitted        Property   System.Boolean IsCommitted {get;}
IsRolledBack       Property   System.Boolean IsRolledBack {get;}
RollbackPreference Property   System.Management.Automation.RollbackSeverity RollbackPreference {get;}
SubscriberCount    Property   System.Int32 SubscriberCount {get;set;}
```

このコマンドは、Get-Member コマンドレットを使用してトランザクション オブジェクトのプロパティとメソッドを表示します。

### 例 3: ロールバックされたトランザクションのプロパティ値を表示する

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Undo-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ----------
Error                0                 RolledBack
```

このコマンドは、ロールバックしたトランザクションのトランザクション オブジェクトのプロパティ値を表示します。

### 例 4: コミットされたトランザクションのプロパティ値を表示する

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

このコマンドは、コミットしたトランザクションのトランザクション オブジェクトのプロパティ値を表示します。

### 例 5: トランザクションを別の処理中に開始する

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany2 -UseTransaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

この例は、別のトランザクションが進行しているときにトランザクションを開始したときのトランザクション オブジェクトにおける影響を示します。
通常、これはトランザクションを実行するスクリプトが関数を含む場合、または別の完全なトランザクションを含むスクリプトを呼び出す場合に発生します。

2番目の **開始トランザクション** コマンドに *独立* したパラメーターが含まれていない限り、 **開始トランザクション** では新しいトランザクションは作成されません。
代わりに、元のトランザクションに第 2 のサブスクライバーが追加されます。

最初の **トランザクションの開始** コマンドは、トランザクションを開始します。
*UseTransaction* パラメーターが指定された New-Item コマンドは、トランザクションの一部です。

2番目の **トランザクションの開始** コマンドは、トランザクションにサブスクライバーを追加します。
その次の New-Item コマンドもトランザクションの一部です。

最初の **トランザクションの取得** コマンドは、マルチサブスクライバートランザクションを示します。
サブスクライバーの数が 2 であることに注意してください。

最初の Complete-Transaction コマンドはトランザクションをコミットしませんが、サブスクライバーの数を 1 に減らします。

2番目の **Complete transaction** コマンドは、トランザクションをコミットします。

### 例 6: 別のトランザクションが進行中のときに独立したトランザクションを開始する

```
PS C:\>
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Start-Transaction -Independent
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
```

この例は、別のトランザクションが進行しているときに独立したトランザクションを開始したときのトランザクション オブジェクトにおける影響を示します。

最初の **トランザクションの開始** コマンドは、トランザクションを開始します。
*UseTransaction* パラメーターが指定された **新しい項目** のコマンドは、トランザクションの一部です。

2番目の **トランザクションの開始** コマンドは、トランザクションにサブスクライバーを追加します。
次の **新しい項目** コマンドは、トランザクションの一部でもあります。

最初の **トランザクションの取得** コマンドは、マルチサブスクライバートランザクションを示します。
サブスクライバーの数が 2 であることに注意してください。

**Complete transaction** コマンドを実行すると、サブスクライバー数が1に減少しますが、トランザクションはコミットされません。

2番目の **Complete transaction** コマンドは、トランザクションをコミットします。

## PARAMETERS

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし
このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。

## 出力

### PSTransaction (システム管理)
このコマンドレットは、現在のトランザクションを表すオブジェクトを返します。

## 注

## 関連リンク

[Complete-Transaction](Complete-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[New-Item](New-Item.md)
