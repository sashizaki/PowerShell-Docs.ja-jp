---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/complete-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-Transaction
ms.openlocfilehash: 20fbdd86aab07dda065492eff2da4f358fb2ffca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215555"
---
# Complete-Transaction

## 概要
有効なトランザクションをコミットします。

## SYNTAX

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Complete transaction** コマンドレットは、アクティブなトランザクションをコミットします。
トランザクションをコミットすると、トランザクション内のコマンドの最終処理が実行され、コマンドの対象のデータが変更されます。

トランザクションに複数のサブスクライバーが含まれている場合、トランザクションをコミットするには、すべての Start-Transaction コマンドに対して1つの **トランザクション完了** コマンドを入力する必要があります。

**Complete Transaction** コマンドレットは、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。
詳細については、「about_Transactions」を参照してください。

## 例

### 例 1: トランザクションをコミットする

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}
```

この例では、 **Complete transaction** コマンドレットを使用してトランザクションをコミットした場合の動作を示します。

トランザクションの **開始** コマンドは、トランザクションを開始します。
New-Item コマンドは、 *UseTransaction* パラメーターを使用して、トランザクションにコマンドを含めます。

最初の dir (Get-childitem) コマンドは、新しい項目がまだレジストリに追加されていないことを示しています。

**Complete transaction** コマンドは、トランザクションをコミットします。これにより、レジストリの変更が有効になります。
その結果、2番目の dir コマンドはレジストリが変更されたことを示しています。

### 例 2: 複数のサブスクライバーを持つトランザクションをコミットする

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
0   0 MyCompany                      {}

PS HKCU:\software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                2                Active

PS HKCU:\software> New-ItemProperty -Path MyCompany -Name MyKey -Value -UseTransaction

MyKey
-----
123

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                1                Active

PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   1 MyCompany                      {MyKey}
```

この例では、 **Complete transaction** を使用して、複数のサブスクライバーを持つトランザクションをコミットする方法を示します。

マルチサブスクライバートランザクションをコミットするには、すべてのトランザクションの **開始** コマンドに対して1つの **完全なトランザクション** コマンドを入力する必要があります。
データが変更されるのは、最後の **Complete Transaction** コマンドが送信されたときだけです。

具体的な方法を示すために、この例ではコマンド ラインに入力される一連のコマンドを示します。
実際には通常、トランザクションはスクリプト内で実行され、メイン スクリプトによって呼び出される関数または補助的なスクリプトによって実行される 2 次的なトランザクションを伴います。

この例では、 **開始トランザクション** コマンドによってトランザクションが開始されます。
*UseTransaction* パラメーターが指定された **新しい項目** のコマンドは、MyCompany キーをソフトウェアキーに追加します。
**新しい項目** のコマンドレットはキーオブジェクトを返しますが、レジストリ内のデータはまだ変更されていません。

2番目の **トランザクションの開始** コマンドは、既存のトランザクションに2番目のサブスクライバーを追加します。
**Get Transaction** コマンドレットは、サブスクライバー数が2であることを確認します。
*UseTransaction* パラメーターを指定した New-ItemProperty コマンドは、新しい MyCompany キーにレジストリエントリを追加します。
再びコマンドから値が返されますが、レジストリは変更されません。

最初の **Complete Transaction** コマンドは、サブスクライバーの数を1つ減らします。
これは、 **Get Transaction** コマンドによって確認されます。
ただし、dir m * ( **get-childitem** ) コマンドでは、データは変更されません。

2番目の **Complete transaction** コマンドは、トランザクション全体をコミットし、レジストリ内のデータを変更します。
これは、変更を示す2番目の dir m * コマンドによって確認されます。

### 例 3: データを変更しないトランザクションを実行する

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> dir m* -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}

PS HKCU:\software> Complete-Transaction
```

この例では、トランザクションで Get コマンドを使用し \* た値と、データを変更しないその他のコマンドを示します。
トランザクションで Get コマンドを使用すると、 \* トランザクションの一部であるオブジェクトが取得されます。
これによって、変更をコミットする前にトランザクション内の変更をプレビューできます。

この例では、トランザクションが開始されます。
*UseTransaction* パラメーターを指定した New-Item コマンドは、トランザクションの一部として新しいキーをレジストリに追加します。

新しいレジストリキーは、 **Complete Transaction** コマンドが実行されるまでレジストリに追加されないため、単純な Dir ( **get-childitem** ) コマンドは、新しいキーなしでレジストリを表示します。

ただし、dir コマンドに *UseTransaction* パラメーターを追加すると、コマンドはトランザクションの一部になり、トランザクション内の項目がまだデータに追加されていない場合でも取得されます。

## PARAMETERS

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

### なし
このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。

## 出力

### なし
このコマンドレットは出力を生成しません。

## 注

* コミットされたトランザクションのロールバック、またはロールバックされたトランザクションのコミットを行うことはできません。

  有効でないトランザクションはロールバックできません。
別のトランザクションをロールバックするには、有効なトランザクションを先にコミットするかロールバックする必要があります。

  既定では、トランザクションのコマンドのエラーなどでトランザクションの一部をコミットできない場合、トランザクション全体がロールバックされます。

*

## 関連リンク

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[Get-ChildItem](Get-ChildItem.md)

[New-Item](New-Item.md)

[New-ItemProperty](New-ItemProperty.md)
