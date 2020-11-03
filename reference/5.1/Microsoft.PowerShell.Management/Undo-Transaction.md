---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/undo-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Undo-Transaction
ms.openlocfilehash: 1acb06ea7b05a2127b04a22c4c51b92cd68056f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214339"
---
# Undo-Transaction

## 概要
有効なトランザクションをロールバックします。

## SYNTAX

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Undo transaction** コマンドレットは、アクティブなトランザクションをロールバックします。
トランザクションをロールバックすると、トランザクション内のコマンドによって行われた変更は破棄され、データは元の形式に復元されます。

トランザクションに複数のサブスクライバーが含まれている場合は、すべてのサブスクライバーについ **てトランザクション全体** がロールバックされます。

既定では、トランザクション内のいずれかのコマンドでエラーが発生すると、トランザクションは自動的にロールバックされます。
ただし、別のロールバック設定を使用してトランザクションを開始できます。また、このコマンドレットを使用すると、アクティブなトランザクションをいつでもロールバックできます。

**Undo Transaction** コマンドレットは、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。
詳細については、「about_Transactions」を参照してください。

## 例

### 例 1: 現在のトランザクションをロールバックする

```
PS C:\> Undo-Transaction
```

このコマンドは、現在のアクティブなトランザクションをロールバックします。

### 例 2: トランザクションを開始してロールバックする

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

この例では、トランザクションを開始してからロールバックします。
その結果、レジストリは変更されません。

### 例 3: すべてのサブスクライバーのトランザクションをロールバックする

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                1                 Active

PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                2                 Active

PS HKCU:\Software> Undo-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                0                 RolledBack
```

この例では、サブスクライバーがトランザクションをロールバックするときに、すべてのサブスクライバーに対してトランザクション全体がロールバックされることを示します。

最初のコマンドは、場所を HKCU:\Software レジストリ キーに変更します。

2 番目のコマンドは、トランザクションを開始します。

3 番目のコマンドは、New-Item コマンドレットを使用して新しいレジストリ キーを作成します。
このコマンドは、 *UseTransaction* パラメーターを使用して変更をトランザクションに含めます。

4 番目のコマンドは、Get-Transaction コマンドレットを使用して有効なトランザクションを取得します。
ステータスが Active であり、サブスクライバーの数が 1 であることに注意してください。

5 番目のコマンドは、Start-Transaction コマンドを再度使用します。
通常、別のトランザクションが実行されている間にトランザクションを開始すると、メイントランザクションで使用されているスクリプトに独自の完全なトランザクションが含まれている場合に発生します。
この例は対話形式で実行されるため、段階的に調べることができます。
別のトランザクションの実行中に **開始トランザクション** コマンドを実行すると、既存のトランザクションが新しいサブスクライバーとして結合され、サブスクライバー数が増加します。

6番目のコマンドは、 **Get transaction** コマンドレットを使用して、アクティブなトランザクションを取得します。
サブスクライバーの数が 2 になったことに注意してください。

7番目のコマンドは、トランザクションをロールバックするために、 **元に戻すトランザクション** を使用します。
このコマンドはオブジェクトを返しません。

最後のコマンドは、アクティブな (この場合は最後にアクティブな) トランザクションを取得する **取得トランザクション** コマンドです。
トランザクションがロールバックされたことと、サブスクライバーの数が 0 になったことが結果に示されます。つまり、トランザクションがすべてのサブスクライバーに対してロールバックされました。

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
パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### なし
このコマンドレットによる戻り値はありません。

## 注

* コミット済みのトランザクションはロールバックできません。

  有効でないトランザクションはロールバックできません。
独立した別のトランザクションをロールバックするには、有効なトランザクションを先にコミットするかロールバックする必要があります。

  トランザクションをロールバックすると、そのトランザクションは終了します。
トランザクションを再度使用するには、トランザクションを新たに開始する必要があります。

## 関連リンク

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Use-Transaction](Use-Transaction.md)
