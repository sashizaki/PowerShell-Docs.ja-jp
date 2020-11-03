---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215419"
---
# Get-ItemProperty

## 概要
指定した項目のプロパティを取得します。

## SYNTAX

### パス (既定値)

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## Description

`Get-ItemProperty`コマンドレットは、指定された項目のプロパティを取得します。
たとえば、このコマンドレットを使用すると、ファイルオブジェクトの LastAccessTime プロパティの値を取得できます。
このコマンドレットを使用して、レジストリエントリとその値を表示することもできます。

## 例

### 例 1: 特定のディレクトリに関する情報を取得する

このコマンドは、"C:\Windows" ディレクトリに関する情報を取得します。

```powershell
Get-ItemProperty C:\Windows
```

### 例 2: 特定のファイルのプロパティを取得する

このコマンドは、"C:\Test\Weather.xls" ファイルのプロパティを取得します。
結果は、 `Format-List` 出力を一覧として表示するためにコマンドレットにパイプされます。

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### 例 3: レジストリサブキーにレジストリエントリの値名とデータを表示する

このコマンドは、"CurrentVersion" レジストリサブキーに格納されている各レジストリエントリの値の名前とデータを表示します。
このコマンドでは、という名前の PowerShell ドライブが `HKLM:` レジストリの "HKEY_LOCAL_MACHINE" ハイブにマップされている必要があることに注意してください。
既定では、その名前とマッピングを持つドライブが PowerShell で使用できます。
また、プロバイダー名の後に 2 つのコロンを続けた以下の代替パスを使用して、このレジストリ サブキーのパスを指定することもできます。

"Registry:: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion"。

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### 例 4: レジストリサブキーのレジストリエントリの値の名前とデータを取得する

このコマンドは、"CurrentVersion" レジストリサブキーの "ProgramFilesDir" レジストリエントリの値の名前とデータを取得します。
このコマンドは、 **Path** パラメーターを使用してサブキーを指定し、Name パラメーターを使用してエントリの値名を指定します。

このコマンドは、バックチックまたはアクサングラーブ () (PowerShell の継続文字) を使用して、 \` 2 行目でコマンドを続行します。

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### 例 5: レジストリキー内のレジストリエントリの値の名前とデータを取得する

このコマンドは、"PowerShellEngine" レジストリキーのレジストリエントリの値の名前とデータを取得します。
次のサンプル出力に結果を示します。

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

### 例 6: レジストリ値とデータの結果を取得、書式設定、および表示する

この例では、 `Get-ItemProperty` レジストリ値とデータを見やすくし、結果を簡単に解釈できるように、一覧内のコマンドの出力を書式設定する方法を示します。

最初のコマンドは、 `Get-ItemProperty` コマンドレットを使用して、 **Microsoft PowerShell** サブキーのレジストリエントリを取得します。
このサブキーには、PowerShell の既定のシェルのオプションが格納されます。
次のサンプル出力に結果を示します。

出力には、"Path" と "Set-executionpolicy" という2つのレジストリエントリがあることが示されています。
レジストリ キーに含まれるエントリが 5 つよりも少ない場合、既定では表形式で表示されますが、通常は一覧形式の方がわかりやすくなります。

2番目のコマンドは、同じコマンドを使用し `Get-ItemProperty` ます。
ただし今回は、コマンドはパイプライン演算子 () を使用して `|` コマンドの結果をコマンドレットに送信し `Format-List` ます。
このコマンドでは、 `Format-List` Property パラメーターを値 ' * ' (all) と共に使用して、リスト内のオブジェクトのすべてのプロパティを表示します。
次のサンプル出力に結果を示します。

結果の表示には、"Path" および "Set-executionpolicy" レジストリエントリと、レジストリキーオブジェクトのいくつかのあまり知られていないプロパティが表示されます。
PS というプレフィックスが付いたその他のプロパティは、レジストリキーを表すオブジェクトなど、PowerShell カスタムオブジェクトのプロパティです。

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
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
Default value: Current user
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
Accept wildcard characters: False
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

取得するプロパティの名前を 1 つ以上指定します。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
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

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseTransaction

アクティブなトランザクションのコマンドが含まれます。
このパラメーターは、トランザクションが進行中の場合のみ有効です。
詳細については、「アクティブなトランザクションにコマンドを含める」を参照してください。
このパラメーターは、トランザクションが進行中の場合のみ有効です。
詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。

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

パイプを使用して、パスを含む文字列をにパイプすることができ `Get-ItemProperty` ます。

## 出力

### System.string、System.string、System.string です。

`Get-ItemProperty` 取得する項目プロパティごとにオブジェクトを返します。
オブジェクトの型は、取得するオブジェクトによって異なります。
たとえば、ファイル システム ドライブでは、ファイルまたはフォルダーが返されます。

## 注

`Get-ItemProperty`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。 セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力し `Get-PSProvider` ます。 詳細については、「about_Providers」を参照してください。

## 関連リンク

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)
