---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 9ae9c0e7c17a6a63da5487cce138ddce129b975b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214547"
---
# Remove-ItemProperty

## 概要
項目からプロパティとその値を削除します。

## SYNTAX

### パス (既定値)

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## Description

`Remove-ItemProperty`コマンドレットは、項目からプロパティとその値を削除します。
これを使用して、レジストリ値とその中に格納されているデータを削除することができます。

## 例

### 例 1: レジストリ値を削除する

このコマンドは、"HKEY_LOCAL_MACHINE\Software" レジストリキーの "Smpproperty" サブキーから "SmpProperty" レジストリ値とそのデータを削除します。

コマンドはファイルシステムドライブ () から発行されるので、 `PS C:\>` ドライブ、 `HKLM:` 、および "Software" キーを含む "SmpApplication" サブキーの完全修飾パスが含まれます。

この例では、 **Name** パラメーターを使用して、削除するレジストリ値を識別します。

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

### 例 2: HKCU の場所からレジストリ値を削除する

これらのコマンドは、"HKEY_CURRENT_USER\Software\MyCompany" の "MyApp" サブキーから、"Options" レジストリ値とそのデータを削除します。

最初のコマンドは、コマンドレットを使用して、 `Set-Location` 現在の場所を **HKEY_CURRENT_USER** ドライブ ( `HKCU:` ) と "Software\MyCompany\MyApp" サブキーに変更します。

2番目のコマンドは、を使用して、" `Remove-ItemProperty` MyApp" サブキーから "Options" レジストリ値とそのデータを削除します。
**パス** が必要であるため、コマンドはドット ('. ') を使用して現在の場所を示します。
**名前** を使用して、削除するレジストリ値を指定します。
**Confirm** パラメーターを使用して、値を削除する前にユーザープロンプトを要求します。

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

### 例 3: パイプラインを使用してレジストリ値を削除する

このコマンドは、"NoOfEmployees" レジストリ値とそのデータを "HKLM\Software\MyCompany" レジストリキーから削除します。

コマンドは、コマンドレットを使用して、 `Get-Item` レジストリキーを表す項目を取得します。
パイプライン演算子 () を使用して `|` 、オブジェクトをに送信 `Remove-ItemProperty` します。
次に、の **name** パラメーターを使用して、 `Remove-ItemProperty` レジストリ値の名前を指定します。

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
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

### -除外

このコマンドレットで省略される項目を指定します。
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

ユーザーがアクセスできないオブジェクトのプロパティをコマンドレットに強制的に削除します。
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
Accept wildcard characters: True
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

削除するプロパティの名前を指定します。
ワイルドカード文字を使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Path

プロパティを削除する項目のパスを指定します。
ワイルドカード文字を使用できます。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
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

パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。

## 出力

### なし

このコマンドレットによる戻り値はありません。

## 注

PowerShell レジストリプロバイダーでは、レジストリ値はレジストリキーまたはサブキーのプロパティと見なされます。 これらの値は、 **get-itemproperty** コマンドレットを使用して管理できます。

`Remove-ItemProperty` は、プロバイダーによって公開されるデータを使用するように設計されています。 セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。 詳細については、「about_Providers」を参照してください。

## 関連リンク

[Get-Item](Get-Item.md)

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-Item](Remove-Item.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
