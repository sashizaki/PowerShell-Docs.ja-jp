---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 2569f4778f54f6cdad22e10cf92e727b73c323e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214611"
---
# New-ItemProperty

## 概要
項目の新しいプロパティを作成し、その値を設定します。

## SYNTAX

### パス (既定値)

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## Description

コマンドレットにより、 `New-ItemProperty` 指定した項目の新しいプロパティが作成され、その値が設定されます。
通常、レジストリ値がレジストリ キー項目のプロパティになるため、このコマンドレットを使用して新しいレジストリ値が作成されます。

このコマンドレットではプロパティがオブジェクトに追加されません。

- オブジェクトのインスタンスにプロパティを追加するには、コマンドレットを使用し `Add-Member` ます。
- 特定の種類のすべてのオブジェクトにプロパティを追加するには、Types.ps1xml ファイルを変更します。

## 例

### 例 1: レジストリエントリを追加する

このコマンドは、"HKLM:\ Software hive" の "MyCompany" キーに新しいレジストリエントリ "NoOfEmployees" を追加します。

最初のコマンドは、 **path** パラメーターを使用して、"MyCompany" レジストリキーのパスを指定します。
**Name** パラメーターを使用してエントリの名前を指定し、 **value** パラメーターを使用してその値を指定します。

2番目のコマンドは、 `Get-ItemProperty` コマンドレットを使用して、新しいレジストリエントリを確認します。

```powershell
New-ItemProperty -Path "HKLM:\Software\MyCompany" -Name "NoOfEmployees" -Value 822
Get-ItemProperty "HKLM:\Software\MyCompany"
```

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 822
```

### 例 2: キーにレジストリエントリを追加する

このコマンドは、新しいレジストリ エントリをレジストリ キーに追加します。 キーを指定するために、パイプライン演算子 (|) を使用して、キーを表すオブジェクトをに送信し `New-ItemProperty` ます。

コマンドの最初の部分では、コマンドレットを使用して `Get-Item` "MyCompany" レジストリキーを取得します。 パイプライン演算子は、コマンドの結果をに送信します `New-ItemProperty` 。これにより、新しいレジストリエントリ ("NoOfLocations") とその値 (3) が "MyCompany" キーに追加されます。

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

このコマンドが機能するのは、Windows PowerShell のパラメーターバインド機能によって、が返すオブジェクトのパスが `RegistryKey` `Get-Item` の **LiteralPath** パラメーターに関連付けられているため `New-ItemProperty` です。 詳細については、「 [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md)」を参照してください。

### 例 3: Here-String を使用してレジストリに文字列値を作成する

この例では、次の文字列を使用して、文字列値を作成します。

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'HereString' -PropertyType MultiString -Value @"
This is text which contains newlines
It can also contain "quoted" strings
"@
$newValue.multistring
```

```output
This is text which contains newlines
It can also contain "quoted" strings
```

### 例 4: 配列を使用してレジストリに文字列値を作成する

この例では、値の配列を使用して値を作成する方法を示し `MultiString` ます。

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## PARAMETERS

### -Credential

この処理を実行するアクセス許可を持つユーザー アカウントを指定します。
既定値は現在のユーザーです。

「User01」や「Domain01\User01」のようなユーザー名を入力するか、  コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。 ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。

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

### -除外

このコマンドレットによって操作から除外されるプロパティまたはプロパティを、文字列配列として指定します。
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
Accept wildcard characters: False
```

### -Filter

プロバイダーの形式または言語でフィルターを指定します。
このパラメーターの値は、 **Path** パラメーターを修飾します。

ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。 フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。

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

### -Force

ユーザーがアクセスできないオブジェクトのプロパティをコマンドレットに強制的に作成します。
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

文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。
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
Accept wildcard characters: False
```

### -LiteralPath

プロパティの現在の場所のパスを指定します。
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

### -Name

新しいプロパティの名前を指定します。
プロパティがレジストリ エントリである場合、このパラメーターはエントリの名前を指定します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

項目のパスを指定します。
このパラメーターは、このコマンドレットによって新しいプロパティが追加される項目を識別します。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropertyType

このコマンドレットによって追加されるプロパティの型を指定します。
このパラメーターの有効値は、次のとおりです。

- **String** : null で終わる文字列を指定します。 **REG_SZ** と同じです。
- **Expandstring** : 値の取得時に展開される環境変数への展開されていない参照を含む、null で終わる文字列を指定します。 **REG_EXPAND_SZ** と同じです。
- **Binary** : 任意の形式のバイナリデータを指定します。 **REG_BINARY** と同じです。
- **DWord** :32 ビットのバイナリ数値を指定します。 **REG_DWORD** と同じです。
- Strings: 2 つの null 文字で終了する null で終わる文字列の配列を指定 **します。**
  **REG_MULTI_SZ** と同じです。
- **Qword** :64 ビットのバイナリ数値を指定します。 **REG_QWORD** と同じです。
- **不明** : **REG_RESOURCE_LIST** など、サポートされていないレジストリデータ型を示します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
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

### -Value

プロパティ値を指定します。
プロパティがレジストリ エントリである場合、このパラメーターはエントリの値を指定します。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### なし

パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### システムの管理. PSCustomObject

`New-ItemProperty` 新しいプロパティを含むカスタムオブジェクトを返します。

## 注

`New-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。 セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。 詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。

## 関連リンク

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
