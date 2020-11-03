---
external help file: ISE-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/import-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IseSnippet
ms.openlocfilehash: 810be675fc593f665ccc6f3d5b86ac2f6b633863
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212384"
---
# Import-IseSnippet

## 概要
現在のセッションに ISE スニペットをインポートします。

## SYNTAX

### FromFolder (既定値)

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### FromModule

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## Description

`Import-IseSnippet`コマンドレットでは、再利用可能なテキスト "スニペット" をモジュールまたはディレクトリから現在のセッションにインポートします。 スニペットは、Windows PowerShell ISE ですぐに使用できます。 このコマンドレットは、Windows PowerShell Integrated Scripting Environment (ISE) でのみ機能します。

インポートされたスニペットを表示して使用するには、Windows PowerShell ISE の [ **編集** ] メニューの [ **スニペットの開始** ] をクリックするか、 <kbd>Ctrl</kbd> + <kbd>J</kbd>キーを押します。

インポートしたスニペットは、現在のセッションでのみ使用できます。 スニペットをすべての Windows PowerShell ISE セッションにインポートするに `Import-IseSnippet` は、Windows PowerShell プロファイルにコマンドを追加するか、スニペットファイルをローカルのスニペットディレクトリにコピーし `$home\Documents\WindowsPowershell\Snippets` ます。

スニペットをインポートするには、スニペット XML で Windows PowerShell ISE スニペット用に適切に書式設定し、Snippet.ps1XML ファイルに保存する必要があります。 対象となるスニペットを作成するには、コマンドレットを使用し `New-IseSnippet` ます。 `New-IseSnippet``<SnippetTitle>.Snippets.ps1xml`ディレクトリにファイルを作成し `$home\Documents\WindowsPowerShell\Snippets` ます。 スニペットは、Windows PowerShell モジュールの Snippets ディレクトリまたはその他の任意のディレクトリにコピーしたり移動したりできます。

`Get-IseSnippet`ローカルのスニペットディレクトリにユーザーが作成したスニペットを取得するコマンドレットは、インポートされたスニペットを取得しません。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: ディレクトリからスニペットをインポートする

この例では、ディレクトリから現在のセッションにスニペットをインポートし `\\Server01\Public\Snippets` ます。 この例では、 **再帰** パラメーターを使用して、スニペットディレクトリのすべてのサブディレクトリからスニペットを取得しています。

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### 例 2: モジュールからスニペットをインポートする

この例では、 **SnippetModule** モジュールからスニペットをインポートします。 このコマンドは、コマンドの実行時に **SnippetModule** モジュールがユーザーのセッションにインポートされていない場合でも、 **ListAvailable** パラメーターを使用してスニペットをインポートします。

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### 例 3: モジュールでスニペットを検索する

この例では、PSModulePath 環境変数にインストールされているすべてのモジュールのスニペットを取得します。

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### 例 4: すべてのモジュールスニペットをインポートする

この例では、すべてのインストールされているモジュールのすべてのスニペットを現在のセッションにインポートします。 通常、このようなコマンドを実行する必要はありません。スニペットを持つモジュールは、モジュールをインポートするときに、コマンドレットを使用して `Import-IseSnippet` インポートします。

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### 例 5: すべてのモジュールスニペットをコピーする

この例では、すべてのインストールされているモジュールから、現在のユーザーのスニペットディレクトリにスニペットファイルをコピーします。 現在のセッションのみに影響を与えるインポートされたスニペットとは異なり、コピーされたスニペットはすべての Windows PowerShell ISE のセッションで使用できます。

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## PARAMETERS

### -ListAvailable

このコマンドレットが、モジュールが現在のセッションにインポートされていない場合でも、コンピューターにインストールされているモジュールからスニペットを取得することを示します。 このパラメーターを省略し、 **module** パラメーターで指定されているモジュールが現在のセッションにインポートされていない場合、モジュールからスニペットを取得しようとすると失敗します。

このパラメーターは、 **Module** パラメーターがコマンドで使用されている場合にのみ有効です。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromModule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -モジュール

指定したモジュールからスニペットを現在のセッションにインポートします。 ワイルドカード文字はサポートされていません。

このパラメーターは、モジュールパスのスニペットサブディレクトリ (など) の Snippet.ps1xml ファイルからスニペットをインポートし `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` ます。

このパラメーターは、スタートアップ スクリプト (たとえば、モジュール マニフェストの **ScriptsToProcess** キーに指定するスクリプト) でモジュールの作成者が使用するために用意されています。 モジュール内のスニペットは、モジュールと共に自動的にインポートされませんが、コマンドを使用して `Import-IseSnippet` インポートできます。

```yaml
Type: System.String
Parameter Sets: FromModule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

このコマンドレットがスニペットをインポートするスニペットディレクトリへのパスを指定します。

```yaml
Type: System.String
Parameter Sets: FromFolder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -再帰

このコマンドレットが **Path** パラメーターの値のすべてのサブディレクトリからスニペットをインポートすることを示します。

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

### なし

このコマンドレットはパイプラインから入力を取得しません。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

- コマンドレットを使用して、 `Get-IseSnippet` インポートしたスニペットを取得することはできません。 `Get-IseSnippet` ディレクトリ内のスニペットだけを取得し `$home\Documents\WindowsPowerShell\Snippets` ます。
- `Import-IseSnippet`**ISESnippetCollection** オブジェクトの **Load** 静的なメソッドを使用します。 Windows PowerShell ISE オブジェクトモデルでは、スニペットの **Load** メソッドを使用することもできます。 `$psISE.CurrentPowerShellTab.Snippets.Load()`
- `New-IseSnippet`コマンドレットは、新しいユーザーが作成したスニペットを types.ps1xml ファイルに格納します。 そのため、Windows PowerShell は、実行ポリシーが **AllSigned** または **Restricted** のセッションにこれらを読み込むことができません。 **Restricted** または **AllSigned** セッションでは、ユーザーが作成した署名されていないスニペットを作成、取得、およびインポートできますが、それらをセッションで使うことはできません。

  コマンドレットから返される、署名されていないユーザーが作成したスニペットを使用するには、 `Import-IseSnippet` 実行ポリシーを変更し、Windows PowerShell ISE を再起動します。

  Windows PowerShell 実行ポリシーの詳細については、「[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)」を参照してください。

## 関連リンク

[Get-IseSnippet](Get-IseSnippet.md)

[New-IseSnippet](New-IseSnippet.md)
