---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: d3637825e7570e5fb0f3ff77efbc89e9d93974a3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214627"
---
# Move-Item

## 概要
項目をある場所から別の場所に移動します。

## SYNTAX

### パス (既定値)

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

### LiteralPath

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

## Description

`Move-Item`コマンドレットは、プロパティ、内容、子項目などの項目を、ある場所から別の場所に移動します。
移動元と移動先は、どちらも同じプロバイダーでサポートされている必要があります。
たとえば、ファイルやサブディレクトリを別のディレクトリに移動したり、レジストリのサブキーを別のキーに移動したりできます。
移動した項目は新しい場所に追加され、元の場所から削除されます。

## 例

### 例 1: ファイルを別のディレクトリに移動して名前を変更する

このコマンドは、"Test.txt" ファイルを `C:` ドライブから "E:\Temp" ディレクトリに移動し、"test.txt" から "tst.txt" に名前を変更します。

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### 例 2: ディレクトリとその内容を別のディレクトリに移動する

このコマンドは、"C:\Temp" ディレクトリとその内容を "C:\Logs" ディレクトリに移動します。
"Temp" ディレクトリとそのすべてのサブディレクトリとファイルが "Logs" ディレクトリに表示されます。

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### 例 3: 指定した拡張子のすべてのファイルを現在のディレクトリから別のディレクトリに移動する

このコマンドは、現在のディレクトリ (ドット ('. ') で表されます) 内のすべてのテキストファイル ("* .txt") を "C:\Logs" ディレクトリに移動します。

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### 例 4: 指定した拡張子のすべてのファイルを現在のディレクトリから別のディレクトリに再帰的に移動する

このコマンドは、すべてのテキストファイルを現在のディレクトリとすべてのサブディレクトリから再帰的に "C:\ textfiles" ディレクトリに移動します。

このコマンドは、コマンドレットを使用して、 `Get-ChildItem` (ドットで表される) 現在のディレクトリ内のすべての子項目 \[ \] と、" *.txt" というファイル名拡張子を持つサブディレクトリを取得します。Recursive パラメーターを **Recurse** 使用して、検索を再帰的にし、Include パラメーターを使用* して取得を ".txt" ファイルに制限します。

パイプライン演算子 () は、 `|` このコマンドの結果をに送信します。これにより `Move-Item` 、テキストファイルが "textfiles" ディレクトリに移動します。

"C:\ textfiles" に移動されるファイルの名前が同じである場合、は `Move-Item` エラーを表示して続行しますが、名前が "C:\ textfiles" になるファイルを1つだけ移動します。
その他のファイルは元のディレクトリに残ります。

"Textfiles" ディレクトリ (または移動先のパスの他の要素) が存在しない場合、コマンドは失敗します。
**Force** パラメーターを使用した場合でも、不足しているディレクトリは作成されません。
`Move-Item` 最初の項目を "Textfiles" という名前のファイルに移動し、そのファイルが既に存在することを示すエラーを表示します。

また、既定で `Get-ChildItem` は、は隠しファイルを移動しません。
隠しファイルを移動するには、 **Force** パラメーターをと共に使用し `Get-ChildItem` ます。

注: Windows PowerShell 2.0 では、コマンドレットの **再帰** パラメーターを使用する場合、 `Get-ChildItem` **Path** パラメーターの値はコンテナーである必要があります。
**Include** パラメーターを使用して、.txt ファイル名拡張子フィルターを指定します (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`)。

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

### 例 5: レジストリのキーと値を別のキーに移動する

このコマンドは、"、Hklm\software" の "MyCompany" レジストリキー内のレジストリキーと値を "MyNewCompany" キーに移動します。
ワイルドカード文字 (' * ') は、キー自体ではなく、"MyCompany" キーの内容を移動する必要があることを示します。
このコマンドでは、省略可能な **パス** と **宛先** のパラメーター名は省略されています。

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### 例 6: ディレクトリとその内容を指定されたディレクトリのサブディレクトリに移動する

このコマンドは、"ログ \[ 9 月 \` 6 \] " ディレクトリ (およびその内容) を "logs \[ 2006 \] " ディレクトリに移動します。

元のディレクトリ名に左角かっこと右角かっこ ("" および "") が含まれているため、 **Path** の代わりに **LiteralPath** パラメーターが使用されてい \[ \] ます。
また、パスは単一引用符 (' ') で囲まれているため、バックティック記号 ( \` ) は誤って解釈されません。

Destination **パラメーターに** はリテラルパスは必要ありません。これは、変換先の変数に、誤って解釈される可能性のある角かっこが含まれているためです。

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
```

## PARAMETERS

### -Credential

> [!NOTE]
> このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。
> 別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Destination

項目の移動先となる場所のパスを指定します。
既定値は、現在のディレクトリです。
ワイルドカードも使用できますが、展開結果が単一の場所を指す必要があります。

移動する項目の名前を変更するには、 **Destination** パラメーターの値に新しい名前を指定します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -除外

このコマンドレットによって操作から除外される項目を文字列配列として指定します。
このパラメーターの値は、 **Path** パラメーターを修飾します。
「*.txt」などのパス要素またはパターンを入力します。
ワイルドカード文字を使用できます。

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

### -Filter

プロバイダーの形式または言語でフィルターを指定します。
このパラメーターの値は、 **Path** パラメーターを修飾します。

ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。
フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

ユーザーに確認せずに、直ちにコマンドを実行します。
実装はプロバイダーごとに異なります。
詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。

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

このコマンドレットが操作内で移動する項目を文字列配列として指定します。
このパラメーターの値は、 **Path** パラメーターを修飾します。
「*.txt」などのパス要素またはパターンを入力します。
ワイルドカード文字を使用できます。

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

### -LiteralPath

項目の現在の場所のパスを指定します。
**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。
ワイルドカードとして解釈される文字はありません。
パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。
単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

作業中の項目を表すオブジェクトを返します。
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

### -Path

項目の現在の場所のパスを指定します。
既定値は、現在のディレクトリです。
ワイルドカード文字を使用できます。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -UseTransaction

アクティブなトランザクションのコマンドが含まれます。
このパラメーターは、トランザクションが進行中の場合のみ有効です。
詳細については、「about_Transactions」を参照してください。

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

このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### System.String

パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。

## 出力

### None または移動された項目を表すオブジェクト。

*PassThru* パラメーターを使用すると、このコマンドレットは移動した項目を表すオブジェクトを生成します。
それ以外の場合、このコマンドレットによる出力はありません。

## 注

このコマンドレットは、同じプロバイダーでサポートされているドライブ間でファイルを移動しますが、ディレクトリを移動するのは同じドライブ内に限られます。

コマンドは、 `Move-Item` 項目のプロパティ、内容、および子項目を移動するため、既定ではすべての移動が再帰的に行われます。

このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。
セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。
詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。

## 関連リンク

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
