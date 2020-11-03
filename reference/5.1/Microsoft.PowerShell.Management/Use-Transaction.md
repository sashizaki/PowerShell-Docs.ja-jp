---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/use-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Use-Transaction
ms.openlocfilehash: db8423aef6dc4b25c4ddd13f9b29b774463c6a6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214355"
---
# Use-Transaction

## 概要
スクリプト ブロックを有効なトランザクションに追加します。

## SYNTAX

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## Description
**トランザクションの使用** コマンドレットは、アクティブなトランザクションにスクリプトブロックを追加します。
これにより、トランザクション対応の Microsoft .NET Framework オブジェクトを使用して、トランザクションスクリプトを実行できます。
スクリプト ブロックに格納できるのは、Microsoft.PowerShell.Commands.Management.TransactedString クラスのインスタンスなど、トランザクション対応の .NET Framework オブジェクトだけです。

このコマンドレットを使用する場合は、ほとんどのコマンドレットで省略可能な *UseTransaction* パラメーターが必要です。

**Transaction** は、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。
詳細については、「about_Transactions」を参照してください。

## 例

### 例 1: トランザクション対応オブジェクトを使用してスクリプトを作成する

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> $transactedString.ToString()
Hello
PS C:\> Use-Transaction -TransactedScript { $transactedString.ToString() } -UseTransaction
Hello, World
PS C:\> Complete-Transaction
PS C:\> $transactedString.ToString()
Hello, World
```

この例 **では、** transaction を使用して、トランザクションが有効な .NET Framework オブジェクトに対してスクリプトを作成する方法を示します。
この場合、オブジェクトは **TransactedString** オブジェクトです。

最初のコマンドは、Start-Transaction コマンドレットを使用してトランザクションを開始します。

2番目のコマンドは、New-Object コマンドを使用して、 **TransactedString** オブジェクトを作成します。
オブジェクトは $TransactedString 変数に保存されます。

3番目と4番目のコマンドはどちらも、 **TransactedString** オブジェクトの **Append** メソッドを使用して、$TransactedString の値にテキストを追加します。
1つのコマンドは、トランザクションの一部です。
その他のコマンドはではありません。

3番目のコマンドは、トランザクション文字列の **Append** メソッドを使用して、$TransactedString の値に Hello を追加します。
このコマンドはトランザクションの一部ではないので、変更内容は直ちに反映されます。

4番目のコマンドは、transaction を **使用** して、トランザクション内の文字列にテキストを追加します。
このコマンドは、 **Append** メソッドを使用して、", World" を $TransactedString の値に追加します。
コマンドは、スクリプトブロックにするために中かっこ () で囲まれ {} ています。
このコマンドでは、 *UseTransaction* パラメーターが必要です。

5番目と6番目のコマンドは、 **TransactedString** オブジェクトの **ToString** メソッドを使用して、 **TransactedString** の値を文字列として表示します。
ここでも、1つのコマンドはトランザクションの一部です。
もう一方のトランザクションがではありません。

5番目のコマンドは、 **ToString** メソッドを使用して、$TransactedString 変数の現在の値を表示します。
このコマンドはトランザクションの一部ではないので、文字列の現在の状態のみを表示します。

6番目のコマンドは、トランザクションで同じコマンドを実行するために、 **transaction を使用** します。
コマンドはトランザクションの一部であるため、トランザクションの文字列の現在の値が表示されます。これは、トランザクションの変更のプレビューに似ています。

7 番目のコマンドは、Complete-Transaction コマンドレットを使用してトランザクションをコミットします。

最後のコマンドは、 **ToString** メソッドを使用して、結果として得られる変数の値を文字列として表示します。

### 例 2: トランザクションをロールバックする

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

この例では、トランザクションの **使用** コマンドを含むトランザクションをロールバックした場合の効果を示します。
トランザクション内のすべてのコマンドと同様に、トランザクションをロールバックすると、トランザクションされた変更内容は破棄され、データは変更されません。

最初のコマンドは、 **開始トランザクション** を使用してトランザクションを開始します。

2番目のコマンドは、 **TransactedString** オブジェクトを作成するために、 **New-オブジェクト** を使用します。
オブジェクトは $TransactedString 変数に保存されます。

トランザクションの一部ではない3番目のコマンドは、 **Append** メソッドを使用して、"Hello" を $TransactedString の値に追加します。

4番目のコマンドは、トランザクションで **Append** メソッドを使用する別のコマンドを実行するために、 **transaction を使用** します。
このコマンドは、 **Append** メソッドを使用して、", World" を $TransactedString の値に追加します。

5 番目のコマンドは、Undo-Transaction コマンドレットを使用してトランザクションをロールバックします。
その結果、トランザクションで実行されるすべてのコマンドが元に戻されます。

最後のコマンドは、 **ToString** メソッドを使用して、結果として得られる $TransactedString の値を文字列として表示します。
結果には、トランザクションの外部で行われた変更のみがオブジェクトに適用されたことが示されます。

## PARAMETERS

### -TransactedScript
トランザクションで実行されるスクリプト ブロックを指定します。
有効なスクリプト ブロックを中かっこ ( { } ) で囲んで入力します。
このパラメーターは必須です。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTransaction
アクティブなトランザクションのコマンドが含まれます。
このパラメーターは、トランザクションが進行中の場合のみ有効です。
詳細については、「about_transactions」を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

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

### PSObject
このコマンドレットは、トランザクションの結果を返します。

## 注

* *UseTransaction* パラメーターには、アクティブなトランザクションにコマンドが含まれています。 トランザクションで **使用** するコマンドレットは常にトランザクションで使用されるため、このパラメーターは、 **トランザクションを使用** するコマンドを有効にするために必要です。

*

## 関連リンク

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)
