---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: 2dbbbfeac3810f79b976b6a68ab3089e91707fb3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215416"
---
# Get-ItemPropertyValue

## 概要
指定した項目の1つ以上のプロパティの値を取得します。

## SYNTAX

### パス (既定値)

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## Description

は、 `Get-ItemPropertyValue` *path* パラメーターまたは *LiteralPath* パラメーターで指定したパスにある *Name* パラメーターを使用するときに、指定したプロパティの現在の値を取得します。

## 例

### 例 1: ProductID プロパティの値を取得する

このコマンドは、Windows レジストリプロバイダーの "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" オブジェクトの **ProductID** プロパティの値を取得します。

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### 例 2: ファイルまたはフォルダーの最終書き込み時刻を取得する

このコマンドは、 **Lastwritetime** プロパティの値を取得します。または、ファイルまたはフォルダーが "C:\Users\Test\Documents\ModuleToAssembly" フォルダーから最後に変更されたときに、FileSystem プロバイダーで動作しています。

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### 例 3: ファイルまたはフォルダーの複数のプロパティ値を取得する

このコマンドは、フォルダーの **Lastwritetime** **、値の取得、** および **ルート** プロパティの値を取得します。
プロパティの値は、プロパティ名を指定した順序で返されます。

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime,CreationTime,Root
```

```output
Wednesday, September 3, 2014 2:53:22 PM
Wednesday, September 3, 2014 2:53:10 PM

Name              : C:\
Parent            :
Exists            : True
Root              : C:\
FullName          : C:\
Extension         :
CreationTime      : 9/1/2014 4:59:45 AM
CreationTimeUtc   : 9/1/2014 11:59:45 AM
LastAccessTime    : 9/27/2014 5:22:02 PM
LastAccessTimeUtc : 9/28/2014 12:22:02 AM
LastWriteTime     : 9/27/2014 5:22:02 PM
LastWriteTimeUtc  : 9/28/2014 12:22:02 AM
Attributes        : Hidden, System, Directory
BaseName          : C:\
Target            :
LinkType          :
Mode              : d--hs-
```

## PARAMETERS

### -Credential

この処理を実行するアクセス許可を持つユーザー アカウントを指定します。
既定値は現在のユーザーです。

「User01」や「Domain01\User01」のようなユーザー名を入力するか、  コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。
ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。

> [!WARNING]
> このパラメーターは、Windows PowerShell でインストールされるプロバイダーではサポートされていません。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
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

取得するプロパティの名前を 1 つ以上指定します。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

項目のパスを 1 つ以上指定します。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### 共通パラメーター

このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### System.String

パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。

## 出力

### System.string、System.string、System.string です。

このコマンドレットは、取得する項目のプロパティ値ごとにオブジェクトを返します。
オブジェクトの種類は、取得されるプロパティ値によって異なります。
たとえば、ファイルシステムドライブでは、コマンドレットはファイルまたはフォルダーを返す場合があります。

## 注

このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。 セッションで使用可能なプロバイダーの一覧を表示するには、コマンドレットを実行し `Get-PSProvider` ます。 詳細については、「about_Providers」を参照してください。

## 関連リンク

[Get-ItemProperty](Get-ItemProperty.md)

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)

[Get-PSProvider](Get-PSProvider.md)
