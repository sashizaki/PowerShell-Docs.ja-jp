---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 26d53ab633f5f73495a8d66012ae55dc10c5d629
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218896"
---
# Remove-Variable

## 概要
変数とその値を削除します。

## SYNTAX

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

`Remove-Variable`このコマンドレットは、変数とその値を、現在のセッションなど、定義されているスコープから削除します。 このコマンドレットでは、定数として設定されている変数、およびシステムに所有されている変数は削除できません。

## 例

### 例 1: 変数を削除する

```powershell
Remove-Variable Smp
```

このコマンドは、 `$Smp` 変数を削除します。

## PARAMETERS

### -除外

このコマンドレットが操作から除外する項目の配列を指定します。 このパラメーターの値は、 **Name** パラメーターを修飾します。 「s*」などの名前要素またはパターンを入力します。 ワイルドカードを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

読み取り専用の場合でも、コマンドレットによって変数が削除されることを示します。 **Force** パラメーターを使用しても、コマンドレットで定数を削除することはできません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include

操作内でこのコマンドレットが削除する項目の配列を指定します。 このパラメーターの値は、 **Name** パラメーターを修飾します。 「S *」のように、名前要素またはパターンを入力します。 ワイルドカードを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

削除する変数の名前を指定します。 パラメーター名 ( **name** ) は省略可能です。
ワイルドカードを使用できます

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -スコープ

指定したスコープの変数のみを取得します。 このパラメーターの有効値は、次のとおりです。

- グローバル
- ローカル
- スクリプト
- 現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)

既定値は Local です。 詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### システム管理. PSVariable

パイプを使用して変数オブジェクトをにパイプすることができ `Remove-Variable` ます。

## 出力

### なし

このコマンドレットによる戻り値はありません。

## 注

- 変更は、セッションなど現在のスコープにのみ影響します。 すべてのセッションから変数を削除するには、 `Remove-Variable` PowerShell プロファイルにコマンドを追加します。

- また、組み込みエイリアスであるを参照することもでき `Remove-Variable` `rv` ます。 詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。

## 関連リンク

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Set-Variable](Set-Variable.md)
