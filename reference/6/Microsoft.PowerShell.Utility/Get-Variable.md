---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: eac42af069b5d1276105c16dd6e280c7c72cf558
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216584"
---
# Get-Variable

## 概要
現在のコンソール内の変数を取得します。

## SYNTAX

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## Description

`Get-Variable`コマンドレットは、現在のコンソールで PowerShell 変数を取得します。
**ValueOnly** パラメーターを指定することで変数の値だけを取得できます。また、返される変数を名前でフィルター処理できます。

## 例

### 例 1: 文字で変数を取得する

このコマンドは、文字 m で始まる名前を持つ変数を取得します。
コマンドは、変数の値も取得します。

```powershell
Get-Variable m*
```

### 例 2: 文字によって変数の値を取得する

このコマンドは、名前が m で始まる変数の値のみを取得します。

```powershell
Get-Variable m* -ValueOnly
```

### 例 3: 2 文字で変数を取得する

このコマンドは、文字 M または文字 P で始まる変数に関する情報を取得します。

```powershell
Get-Variable -Include M*,P*
```

### 例 4: スコープによって変数を取得する

最初のコマンドは、ローカル スコープで定義されている変数のみを取得します。
これはと同じであり、とし `Get-Variable -Scope Local` て省略でき `gv -s 0` ます。

2番目のコマンドは、コマンドレットを使用して、 `Compare-Object` 親スコープ (スコープ 1) で定義されているが、ローカルスコープ (スコープ 0) でのみ表示される変数を検索します。

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## PARAMETERS

### -除外

このコマンドレットによって操作から除外される項目の配列を指定します。
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

### -Include

コマンドレットが動作する項目の配列を指定します。他の項目は除外されます。
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

変数の名前を指定します。
ワイルドカードを使用できます。
パイプを使用して変数名をにパイプすることもでき `Get-Variable` ます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -スコープ

スコープ内の変数を指定します。このパラメーターに指定できる値は次のとおりです。

- **グローバル**
- **ローカル**
- **スクリプト**
- 現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)

既定値は **Local** です。
詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。

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

### -ValueOnly

このコマンドレットが変数の値のみを取得することを示します。

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

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### System.String

パイプを使用して、変数名を含む文字列をに渡し `Get-Variable` ます。

## 出力

### システム管理. PSVariable

このコマンドレットは、取得した各変数の **AutomationPSVariable** オブジェクトを返します。 オブジェクトの型は変数に依存します。

### System.object []

**Valueonly** パラメーターを指定すると、指定した変数の値がコレクションの場合、 `Get-Variable` はを返し `[System.Object[]]` ます。 この動作により、通常のパイプライン操作によって変数の値が一度に1つずつ処理されるのを防ぐことができます。 コレクションの列挙を強制する回避策として、 `Get-Variable` コマンドをかっこで囲みます。

## 注

- このコマンドレットは、環境変数を管理しません。 環境変数を管理するには、環境変数プロバイダーを使用します。

## 関連リンク

[Clear-Variable](Clear-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)
