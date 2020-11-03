---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8485591165cce0425c85d52fbd31d40614af6249
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214064"
---
# Export-Clixml

## 概要
1 つまたは複数のオブジェクトの XML ベースの表現を作成し、ファイルに格納します。

## SYNTAX

### ByPath (既定値)

```
Export-Clixml [-Path] <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Export-Clixml -LiteralPath <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

コマンドレットでは、 `Export-Clixml` 共通言語基盤 (CLI) の XML ベースの表現をオブジェクトまたはオブジェクトで作成し、ファイルに格納します。 その後、コマンドレットを使用して、 `Import-Clixml` そのファイルの内容に基づいて保存されたオブジェクトを再作成できます。
CLI の詳細については、「 [言語に依存](/dotnet/standard/language-independence)しない」を参照してください。

このコマンドレットはに似ていますが、では `ConvertTo-Xml` 、結果の XML がファイルに格納される点が異なり `Export-Clixml` ます。 `ConvertTo-XML` は XML を返します。そのため、PowerShell で処理を続行できます。

Windows コンピューターでのの重要な使用方法 `Export-Clixml` は、資格情報をエクスポートし、文字列を安全に XML としてセキュリティで保護することです。 例については、例3を参照してください。

## 例

### 例 1: XML ファイルに文字列をエクスポートする

この例では、現在のディレクトリに格納されている XML ファイルを作成します。 **これは** 、という文字列の表現です。

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

**この** 文字列は、パイプラインによって送信されます。 `Export-Clixml`**Path** パラメーターを使用して、現在のディレクトリにという名前の XML ファイルを作成し `sample.xml` ます。

### 例 2: オブジェクトを XML ファイルにエクスポートする

この例では、オブジェクトを XML ファイルにエクスポートし、エクスポートしたファイルから XML をインポートしてオブジェクトを作成する方法を示します。

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

コマンドレットでは、 `Get-Acl` ファイルのセキュリティ記述子を取得し `Test.txt` ます。 オブジェクトをパイプラインの下に送信して、セキュリティ記述子をに渡し `Export-Clixml` ます。 オブジェクトの XML ベースの表現は、という名前のファイルに格納され `FileACL.xml` ます。

`Import-Clixml`コマンドレットは、ファイル内の XML からオブジェクトを作成し `FileACL.xml` ます。 次に、変数にオブジェクトを保存し `$fileacl` ます。

### 例 3: エクスポートされた資格情報オブジェクトを暗号化する

この例では、コマンドレットを実行して変数に格納した資格情報を指定した場合、 `$Credential` `Get-Credential` コマンドレットを実行して `Export-Clixml` 資格情報をディスクに保存できます。

> [!IMPORTANT]
> `Export-Clixml` 暗号化された資格情報のみを Windows でエクスポートします。 MacOS や Linux などの Windows 以外のオペレーティングシステムでは、資格情報はプレーンテキストでエクスポートされます。

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

コマンドレットでは、 `Export-Clixml` Windows [データ保護 API](/previous-versions/windows/apps/hh464970(v=win.10))を使用して資格情報オブジェクトを暗号化します。
暗号化により、そのコンピューター上のユーザーアカウントのみが資格情報オブジェクトの内容を復号化できるようになります。 エクスポートされたファイルは、 `CLIXML` 別のコンピューターまたは別のユーザーが使用することはできません。

この例では、資格情報が格納されているファイルがによって表され `TestScript.ps1.credential` ます。 **Testscript** を、資格情報の読み込みに使用するスクリプトの名前に置き換えます。

資格情報オブジェクトをパイプラインの下に送信 `Export-Clixml` し、 `$Credxmlpath` 最初のコマンドで指定したパスに保存します。

スクリプトに資格情報を自動的にインポートするには、最後の2つのコマンドを実行します。 を実行し `Import-Clixml` て、セキュリティで保護された資格情報オブジェクトをスクリプトにインポートします。 このインポートにより、スクリプトにプレーンテキストのパスワードが公開されるリスクがなくなります。

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

### -深さ

XML 表現に含める子オブジェクトのレベルを指定します。 既定値は `2` です。

ファイルのオブジェクトの種類に対して既定値をオーバーライドでき `Types.ps1xml` ます。 詳細については、「 [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)」を参照してください。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding

ターゲット ファイルのエンコードの種類を指定します。 既定値は **Unicode** です。

このパラメーターに指定できる値は次のとおりです。

- `ASCII` ASCII (7 ビット) 文字セットを使用します。
- `BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。
- `Default` は、システムのアクティブなコードページ (通常は ANSI) に対応するエンコーディングを使用します。
- `OEM` は、システムの現在の OEM コードページに対応するエンコーディングを使用します。
- `Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。
- `UTF7` UTF-7 を使用します。
- `UTF8` UTF-8 を使用します。
- `UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

ユーザーに確認せずに、直ちにコマンドを実行します。

必要に応じて、このコマンドレットは出力ファイルの読み取り専用の属性をクリアします。 コマンドが完了すると、このコマンドレットが読み取り専用の属性をリセットしようとします。

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

### -InputObject

変換するオブジェクトを指定します。 オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。 パイプを使用してオブジェクトをにパイプ処理することもでき `Export-Clixml` ます。

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

オブジェクトの XML 表現が格納されるファイルへのパスを指定します。 **Path** と異なり、 **LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。 ワイルドカードとして解釈される文字はありません。 パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。 単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

コマンドレットが既存のファイルの内容を上書きしないことを示します。 既定では、指定されたパスにファイルが存在する場合、は `Export-Clixml` 警告なしにファイルを上書きします。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

オブジェクトの XML 表現が格納されるファイルへのパスを指定します。

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

コマンドレットの実行時に発生する内容を示します。 コマンドレットは実行されません。

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

### システム管理. PSObject

任意のオブジェクトをにパイプラインでき `Export-Clixml` ます。

## 出力

### システム. IO. FileInfo

`Export-Clixml` XML を含むファイルを作成します。

## 注

## 関連リンク

[ConvertTo-Html](ConvertTo-Html.md)

[ConvertTo-Xml](ConvertTo-Xml.md)

[Export-Csv](Export-Csv.md)

[Import-Clixml](Import-Clixml.md)

[Join-Path](../Microsoft.PowerShell.Management/Join-Path.md)

[ディスクへの資格情報の安全な保存](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[PowerShell を使用してレガシシステムに資格情報を渡す](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[Windows.Security.Cryptography.DataProtection](/uwp/api/windows.security.cryptography.dataprotection)
