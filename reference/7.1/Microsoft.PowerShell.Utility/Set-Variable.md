---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: ba17b526de91e470149e90913814ecfac0f75392
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211779"
---
# Set-Variable

## 概要
変数の値を設定します。
要求された名前の変数が存在しない場合は、変数を作成します。

## SYNTAX

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

**Set variable** コマンドレットは、指定された変数に値を割り当てるか、現在の値を変更します。
変数が存在しない場合は、変数を作成します。

## 例

### 例 1: 変数を設定し、その値を取得する

```
PS C:\> Set-Variable -Name "desc" -Value "A description"
PS C:\> Get-Variable -Name "desc"
```

これらのコマンドは、desc 変数の値を説明に設定し、変数の値を取得します。

### 例 2: グローバルな読み取り専用変数を設定する

```
PS C:\> Set-Variable -Name "processes" -Value (Get-Process) -Option constant -Scope global -Description "All processes" -PassThru | Format-List -Property *
```

このコマンドは、システム上のすべてのプロセスを保存している読み取り専用のグローバル変数を作成し、変数のすべてのプロパティを表示します。

このコマンドは、変数を作成するために、 **変数の設定** コマンドレットを使用します。
*PassThru* パラメーターを使用して新しい変数を表すオブジェクトを作成し、パイプライン演算子 (|) を使用してオブジェクトを Format-List コマンドレットに渡します。
この例では、Format-List の *Property* パラメーターを all (*) の値と共に使用して、新しく作成された変数のすべてのプロパティを表示します。

"(Get-Process)" という値は、実行後に変数に保存されるようにするためにかっこで囲まれています。
かっこで囲んでいない場合、変数には "Get-Process" という語が設定されます。

### 例 3: パブリック変数とプライベート変数を理解する

```
PS C:\> New-Variable -Name "counter" -Visibility Public -Value 26
PS C:\> $Counter
26
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}
Counter               26 

PS C:\> Set-Variable -Name "counter" -Visibility Private
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}

 PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"

PS C:\> .\use-counter.ps1
#Commands completed successfully.
```

このコマンドは、変数の可視性をプライベートに変更する方法を示しています。
この変数は、必要なアクセス許可を使用すればスクリプトによる読み取りや変更が可能ですが、ユーザーには表示されません。

サンプル出力は、パブリック変数とプライベート変数の動作の違いを示しています。

## PARAMETERS

### -Description

変数の説明を指定します。

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

### -除外

このコマンドレットによって操作から除外される項目の配列を指定します。
このパラメーターの値は、 *Path* パラメーターを修飾します。
パス要素またはパターン (など) を入力し `*.txt` ます。
ワイルドカードを使用できます。

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

既存の読み取り専用変数と同じ名前を持つ変数の作成や、読み取り専用変数の値の変更を実行できます。

既定では、変数のオプション値が ReadOnly または Constant でない限り、変数を上書きできます。
詳細については、「 *オプション* パラメーター」を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include

このコマンドレットによって操作に含まれる項目の配列を指定します。
このパラメーターの値は、 *Name* パラメーターを修飾します。
などの名前または名前パターンを入力し `c*` ます。
ワイルドカードを使用できます。

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

変数名を指定します。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Option

変数の **Options** プロパティの値を指定します。

有効な値は次のとおりです。

- None: オプションを設定しません。 ("None" は、既定値です)。
- ReadOnly: 削除できます。 Force パラメーターを使用する場合を除き、を変更することはできません。
- 定数: 削除または変更することはできません。 "Constant" は、変数を作成する場合にのみ有効です。 既存の変数のオプションを "Constant" に変更することはできません。
- プライベート: 変数は、現在のスコープでのみ使用できます。
- AllScope: 変数は、作成された新しいスコープにコピーされます。

セッション内のすべての変数の **Options** プロパティを表示するには、「」と入力 `Get-Variable | Format-Table -Property name, options -Autosize` します。

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
新しい変数を表すオブジェクトを返します。
既定では、このコマンドレットによる出力はありません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -スコープ

変数のスコープを指定します。このパラメーターに指定できる値は次のとおりです。

- グローバル
- ローカル
- スクリプト
- Private
- 現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)。

既定値は Local です。

詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md)」を参照してください。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

変数の値を指定します。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -可視性

変数を、作成元のセッションの外部で表示されるようにするかどうかを決定します。
このパラメーターは、他のユーザーに配信されるスクリプトおよびコマンドで使用する目的で設計されています。

有効な値は次のとおりです。

- Public: 変数が表示されます。 ("Public" は既定値です)。
- Private: 変数は表示されません。

変数がプライベートの場合、その変数は、Get-Variable で返されるような変数一覧または Variable: ドライブの表示には出現しません。
プライベート変数の値を読み取りまたは変更するコマンドは、エラーを返します。
ただし、コマンドが、変数の定義元のセッションで記述されている場合は、プライベート変数を使用するコマンドを実行できます。

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: Public
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

### System.Object

パイプを使用して、変数の値を表すオブジェクトを **変数に設定** できます。

## 出力

### None または system.string です。

*PassThru* パラメーターを使用すると、 **Set 変数** は、新しい変数または変更された変数を表す **system.string オブジェクトを** 生成します。
それ以外の場合、このコマンドレットによる出力はありません。

## 注

## 関連リンク

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

