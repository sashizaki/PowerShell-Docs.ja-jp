---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: c65634a295ccca368d7b4d42eb2bf6bb18753e96
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212256"
---
# Split-Path

## 概要
指定されたパス部分を返します。

## SYNTAX

### ParentSet (既定値)

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### QualifierSet

```
Split-Path [-Path] <String[]> [[-Qualifier]] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### LeafSet

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### LeafBaseSet

```
Split-Path [-Path] <String[]> [-LeafBase] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### ExtensionSet

```
Split-Path [-Path] <String[]> [-Extension] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### NoQualifierSet

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### IsAbsoluteSet

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### LiteralPathSet

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## Description

**Split path** コマンドレットは、親フォルダー、サブフォルダー、ファイル名など、指定されたパスの部分のみを返します。
また、分割されたパスで参照されている項目を取得したり、パスが相対パスか絶対パスかを判断したりすることもできます。

このコマンドレットを使用すると、選択したパスの一部だけを取得または送信できます。

## 例

### 例 1: パスの修飾子を取得する

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

このコマンドは、パスの修飾子だけを返します。
修飾子はドライブです。

### 例 2: ファイル名を表示する

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

このコマンドを実行すると、分割されたパスが参照しているファイルが表示されます。
このパスは最後の項目 (リーフとも呼ばれます) に分割されるので、コマンドはファイル名のみを表示します。

*Resolve* パラメーターは、分割パスを表示するのではなく、分割パスによって参照される項目を表示するように **分割パス** に指示します。

すべての **分割パス** コマンドと同様に、このコマンドは文字列を返します。
ファイルを表す **FileInfo** オブジェクトは返しません。

### 例 3: 親コンテナーを取得する

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

このコマンドは、パスの親コンテナーだけを返します。
分割を指定するパラメーターが含まれていないため、分割 **パス** は、 *親* である分割位置の既定値を使用します。

### 例 4: 絶対パスであるかどうかを判断する

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

このコマンドは、パスが相対パスと絶対パスのどちらであるかを特定します。
この場合、パスは、ドット (.) で表される現在のフォルダーに対する相対パスであるため、$False を返します。

### 例 5: 指定したパスに場所を変更する

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

このコマンドは、PowerShell プロファイルが格納されているフォルダーに場所を変更します。

かっこ内のコマンドは、 **分割パス** を使用して、組み込みの $Profile 変数に格納されているパスの親だけを返します。
*親* パラメーターは、既定の分割位置パラメーターです。
このため、コマンドから省略できます。
かっこでは、最初にコマンドを実行するように PowerShell を指示します。
これは、長いパス名を持つフォルダーに移動する場合に便利な方法です。

### 例 6: パイプラインを使用してパスを分割する

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

このコマンドは、パイプライン演算子 (|) を使用して、パスを **分割パス** に送信します。
パスを引用符で囲み、1 つのトークンであることを示します。

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
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -拡張機能

このコマンドレットがリーフの拡張のみを返すことを示します。
たとえば、パスでは、 `C:\Test\Logs\Pass1.log` のみが返さ `.log` れます。

このパラメーターは、PowerShell 6.0 で導入されました。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExtensionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsAbsolute

このコマンドレットが絶対パスの場合に $True を返し、相対パスの場合は $False することを示します。
絶対パスの長さはゼロより大きく、ドット (.) を使用して現在のパスを示すことはできません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -リーフ

このコマンドレットがパス内の最後の項目またはコンテナーだけを返すことを示します。
たとえば、パスでは、 `C:\Test\Logs\Pass1.log` Pass1 のみが返されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LeafBase

このコマンドレットがリーフの基本名だけを返すことを示します。
たとえば、パスでは、 `C:\Test\Logs\Pass1.log` のみが返さ `Pass1` れます。

このパラメーターは、PowerShell 6.0 で導入されました。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafBaseSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

分割するパスを指定します。
*Path* とは異なり、 *LiteralPath* の値は入力した内容のまま使用されます。
ワイルドカードとして解釈される文字はありません。
パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。
単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoQualifier

このコマンドレットが修飾子なしでパスを返すことを示します。
FileSystem プロバイダーまたはレジストリ プロバイダーの場合、修飾子は、C: または HKCU: などの、プロバイダー パスのドライブです。
たとえば、パスでは、 `C:\Test\Logs\Pass1.log` \Test\Logs\Pass1.log. のみが返されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -親

このコマンドレットが、パスで指定された項目またはコンテナーの親コンテナーだけを返すことを示します。
たとえば、パスでは、 `C:\Test\Logs\Pass1.log` C:\Test\Logs. が返されます。
*親* パラメーターは、既定の分割位置パラメーターです。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

分割するパスを指定します。
ワイルドカード文字を使用できます。
パスにスペースが含まれる場合は、二重引用符で囲みます。
パイプを使用してこのコマンドレットへのパスをパイプすることもできます。

```yaml
Type: System.String[]
Parameter Sets: ParentSet, LeafSet, LeafBaseSet, ExtensionSet, QualifierSet, NoQualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -修飾子

このコマンドレットが、指定されたパスの修飾子だけを返すことを示します。
FileSystem プロバイダーまたはレジストリ プロバイダーの場合、修飾子は、C: または HKCU: などの、プロバイダー パスのドライブです。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -解決

このコマンドレットによって、パス要素を表示する代わりに、結果として得られる分割パスによって参照される項目が表示されることを示します。

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

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.String

パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。

## 出力

### System.string、System.string

**分割パスは、** テキスト文字列を返します。
*Resolve* パラメーターを指定すると、 **分割パス** は項目の場所を説明する文字列を返します。 **FileInfo** や **RegistryKey** オブジェクトなど、アイテムを表すオブジェクトは返されません。

*Isabsolute* パラメーターを指定すると、 **分割パス** は **ブール** 値を返します。

## 注

* 分割位置パラメーター ( *Qualifier* 、 *Parent* 、 *Extension* 、 *リーフ* 、 *LeafBase* 、および *noqualifier* ) は排他的です。 各コマンドでいずれか 1 つだけを使用できます。

  **パスの名詞を** 含むコマンドレット ( **path** コマンドレット) は、パス名と共に使用され、すべての PowerShell プロバイダーが解釈できる簡潔な形式の名前を返します。
プログラムやスクリプトで、パス名の全部または一部を特定の形式で表示するために使用することを目的としています。
これらは、 **Dirname** 、 **Normpath** 、 **realpath** 、 **Join** 、またはその他のパスマニピュレーターを使用する方法で使用します。

  **Path** コマンドレットは、いくつかのプロバイダーと共に使用できます。
これには、ファイルシステム、レジストリ、および証明書プロバイダーが含まれます。

  **分割パス** は、プロバイダーによって公開されるデータを使用するように設計されています。
セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。
詳細については、「about_Providers」を参照してください。

## 関連リンク

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Test-Path](Test-Path.md)
