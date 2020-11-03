---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215611"
---
# Add-Content

## 概要
指定した項目に内容を追加します。たとえば、ファイルに語を追加します。

## SYNTAX

### パス (既定値)

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### LiteralPath

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## Description

`Add-Content`コマンドレットは、指定された項目またはファイルにコンテンツを追加します。 内容を指定するには、コマンドに内容を入力するか、内容が格納されているオブジェクトを指定します。

次の例でファイルまたはディレクトリを作成する必要がある場合は、「 [New-Item](New-Item.md)」を参照してください。

## 例

### 例 1: 例外が発生したすべてのテキストファイルに文字列を追加する

この例では、現在のディレクトリ内のテキストファイルに値を追加しますが、ファイル名に基づいてファイルを除外します。

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

この `Add-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリ内のすべての .txt ファイルを指定します。 **Exclude** パラメーターは、指定されたパターンに一致するファイル名を無視します。 **値** パラメーターは、ファイルに書き込まれるテキスト文字列を指定します。

これらのファイルの内容を表示するには、 [Get Content](Get-Content.md) を使用します。

### 例 2: 指定したファイルの末尾に日付を追加する

この例では、現在のディレクトリのファイルに日付を追加し、その日付を PowerShell コンソールに表示します。

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

コマンドレットでは、 `Add-Content` **Path** パラメーターと **Value** パラメーターを使用して、現在のディレクトリに2つの新しいファイルを作成します。 **値** パラメーターは、 `Get-Date` 日付を取得して日付をに渡すようにコマンドレットを指定し `Add-Content` ます。 `Add-Content`コマンドレットは、各ファイルに日付を書き込みます。 **PassThru** パラメーターは、date オブジェクトを表すオブジェクトを渡します。 渡されたオブジェクトを受け取るコマンドレットは他にないため、PowerShell コンソールに表示されます。 コマンドレットにより、 `Get-Content` 更新されたファイル DateTimeFile1 が表示されます。

### 例 3: 指定したファイルの内容を別のファイルに追加する

この例では、ファイルからコンテンツを取得し、その内容を別のファイルに追加します。

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

この `Add-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリ内の新しいファイル CopyToFile.txt を指定します。 **Value** パラメーターでは、コマンドレットを使用して、 `Get-Content` CopyFromFile.txt ファイルの内容を取得します。 コマンドレットを囲むかっこを実行すると、コマンドが開始される `Get-Content` 前にコマンドが終了し `Add-Content` ます。 **値** パラメーターはに渡され `Add-Content` ます。 この `Add-Content` コマンドレットは、CopyToFile.txt ファイルにデータを追加します。 コマンドレットにより、 `Get-Content` 更新されたファイル CopyToFile.txt が表示されます。

### 例 4: 変数を使用して、指定したファイルの内容を別のファイルに追加する

この例では、ファイルからコンテンツを取得し、その内容を変数に格納します。 変数は、コンテンツを別のファイルに追加するために使用されます。

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

この `Get-Content` コマンドレットは CopyFromFile.txt の内容を取得し、その内容を変数に格納し `$From` ます。 この `Add-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリ内の CopyToFile.txt ファイルを指定します。 **Value** パラメーターは変数を使用し、 `$From` にコンテンツを渡し `Add-Content` ます。 `Add-Content`コマンドレットにより、CopyToFile.txt ファイルが更新されます。 コマンドレットによって `Get-Content` CopyToFile.txt が表示されます。

### 例 5: 新しいファイルを作成してコンテンツをコピーする

この例では、新しいファイルを作成し、既存のファイルの内容を新しいファイルにコピーします。

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

コマンドレットでは、 `Add-Content` **Path** パラメーターと **Value** パラメーターを使用して、現在のディレクトリに新しいファイルを作成します。 **Value** パラメーターでは、コマンドレットを使用して `Get-Content` 、既存のファイルの内容を取得します。 CopyFromFile.txt します。 コマンドレットを囲むかっこを実行すると、コマンドが開始される `Get-Content` 前にコマンドが終了し `Add-Content` ます。 **Value** パラメーターは、NewFile.txt ファイルを更新するコンテンツをに渡し `Add-Content` ます。 コマンドレットにより、 `Get-Content` 新しいファイルの内容 NewFile.txt が表示されます。

### 例 6: 読み取り専用ファイルにコンテンツを追加する

このコマンドは、 **IsReadOnly** file 属性が True に設定されている場合でも、ファイルに値を追加します。
この例には、読み取り専用ファイルを作成する手順が含まれています。

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

この `New-Item` コマンドレットは、 **Path** パラメーターと **ItemType** パラメーターを使用して、現在のディレクトリに IsReadOnlyTextFile.txt ファイルを作成します。 コマンドレットでは、 `Set-ItemProperty` **Name** パラメーターと **Value** パラメーターを使用して、ファイルの **IsReadOnly** プロパティを True に変更します。 この `Get-ChildItem` コマンドレットは、ファイルが空 (0) であり、読み取り専用属性 () を持っていることを示してい `r` ます。 コマンドレットでは、 `Add-Content` **Path** パラメーターを使用してファイルを指定します。 **Value** パラメーターには、ファイルに追加するテキスト文字列が含まれています。 **Force** パラメーターは、テキストを読み取り専用ファイルに書き込みます。 この `Get-Content` コマンドレットは、 **Path** パラメーターを使用してファイルの内容を表示します。

読み取り専用属性を削除するには、 `Set-ItemProperty` **値** パラメーターをに設定してコマンドを使用し `False` ます。

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

### -Credential

この処理を実行するアクセス許可を持つユーザー アカウントを指定します。 既定値は現在のユーザーです。

**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。 ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。

> [!WARNING]
> このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。

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

### -Encoding

ターゲット ファイルのエンコードの種類を指定します。 既定値は `Default` です。

このパラメーターに指定できる値は次のとおりです。

- `Ascii` ASCII (7 ビット) 文字セットを使用します。
- `BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。
- `BigEndianUTF32` は、ビッグエンディアンのバイト順で 32 UTF-8 を使用します。
- `Byte` 文字のセットをバイトシーケンスにエンコードします。
- `Default` は、システムのアクティブなコードページ (通常は ANSI) に対応するエンコーディングを使用します。
- `Oem` は、システムの現在の OEM コードページに対応するエンコーディングを使用します。
- `String`**Unicode** と同じです。
- `Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。
- `Unknown`**Unicode** と同じです。
- `UTF7` UTF-7 を使用します。
- `UTF8` UTF-8 を使用します。
- `UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。

Encoding は、FileSystem プロバイダーによってコマンドレットに追加される動的パラメーターです `Add-Content` 。 このパラメーターはファイル システム ドライブでのみ機能します。

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -除外

指定した項目を除外します。 このパラメーターの値は、 **Path** パラメーターを修飾します。 パス要素またはパターン ( **\* .txt** など) を入力します。 ワイルドカードを使用できます。

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

プロバイダーの形式や言語でフィルターを指定します。 このパラメーターの値は、 **Path** パラメーターを修飾します。 ワイルドカードを使用できるかどうかなど、フィルターの構文はプロバイダーによって異なります。 **フィルター** は他のパラメーターよりも効率的です。これは、プロバイダーがオブジェクトの取得時にフィルターを適用するためです。 それ以外の場合、PowerShell はオブジェクトの取得後にフィルター処理を行います。

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

読み取り専用属性をオーバーライドし、読み取り専用ファイルに内容を追加できるようにします。 たとえば、 **Force** を指定すると、読み取り専用属性がオーバーライドされるか、ファイル パスを完成させるためにディレクトリが作成されますが、ファイルのアクセス許可は変更されません。

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

指定した項目だけを追加します。 このパラメーターの値は、 **Path** パラメーターを修飾します。 パス要素またはパターン ( **\* .txt** など) を入力します。 ワイルドカードを使用できます。

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

内容を追加する項目へのパスを指定します。 **Path** とは異なり、 **LiteralPath** の値は入力した内容のまま使用されます。 ワイルドカードとして解釈される文字はありません。 パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。 単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。

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

### -なし Wline

このコマンドレットがコンテンツに新しい行または復帰を追加しないことを示します。

入力オブジェクトの文字列形式が連結され、出力が形成されます。 出力文字列間にスペースや改行は挿入されません。 最後の出力文字列の後に改行は追加されません。

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

### -PassThru

追加された内容を表すオブジェクトを返します。 既定では、このコマンドレットによる出力はありません。

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

### -Path

内容を追加する項目へのパスを指定します。 ワイルドカードを使用できます。 複数のパスを指定する場合は、各パスをコンマで区切ります。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ストリーム

コンテンツの代替データストリームを指定します。 ストリームが存在しない場合は、このコマンドレットによって作成されます。 ワイルドカード文字はサポートされていません。

**Stream** は、FileSystem プロバイダーによってに追加される動的パラメーターです `Add-Content` 。 このパラメーターはファイル システム ドライブでのみ機能します。

コマンドレットを使用して、 `Add-Content` ゾーンの内容を変更でき **ます。識別子** 代替データストリーム。 ただし、インターネットからダウンロードされたファイルをブロックするセキュリティチェックを省略する方法としては、この方法をお勧めしません。 ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。

このパラメーターは、PowerShell 3.0 で導入されました。

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

### -UseTransaction

アクティブなトランザクションのコマンドが含まれます。 このパラメーターは、トランザクションが進行中の場合のみ有効です。 詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。

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

追加する内容を指定します。 **このデータが内部でのみ使用さ** れるなどの引用符で囲まれた文字列を入力するか、生成する **DateTime** オブジェクトなど、コンテンツを含むオブジェクトを指定し `Get-Date` ます。

パスは文字列であるため、パスを入力してファイルの内容を指定することはできません。
コマンドを使用して `Get-Content` コンテンツを取得し、それを **Value** パラメーターに渡すことができます。

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.object、システムの管理、PSCredential

パイプを使用して、値、パス、または資格情報をにパイプすることができ `Set-Content` ます。

## 出力

### None または System.String

**PassThru** パラメーターを使用すると、によって、 `Add-Content` コンテンツを表す **system.string** オブジェクトが生成されます。 それ以外の場合、このコマンドレットによる出力はありません。

## 注

オブジェクトをにパイプすると `Add-Content` 、オブジェクトは項目に追加される前に文字列に変換されます。 オブジェクト型によって文字列の形式が決まりますが、オブジェクトの既定の表示形式と異なる場合があります。 文字列の形式を制御するには、送信コマンドレットの書式設定パラメーターを使用します。

また、組み込みエイリアスであるを参照することもでき `Add-Content` `ac` ます。 詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。

`Add-Content`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。 セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。 詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。

## 関連リンク

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[Clear-Content](Clear-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[New-Item](New-Item.md)

[Set-Content](Set-Content.md)
