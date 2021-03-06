---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: 9831249a9f1ffcc65fc275e44da04fde9348ae71
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388061"
---
# ConvertTo-Json

## 概要
オブジェクトを JSON 形式の文字列に変換します。

## SYNTAX

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
 [<CommonParameters>]
```

## Description

`ConvertTo-Json`コマンドレットは、任意の .net オブジェクトを JavaScript Object Notation (JSON) 形式の文字列に変換します。 プロパティはフィールド名に変換され、フィールドの値はプロパティの値に変換されます。メソッドは削除されます。

次に、コマンドレットを使用して、 `ConvertFrom-Json` json 形式の文字列を json オブジェクトに変換します。これは、PowerShell で簡単に管理できます。

多くの Web サイトが、サーバーと Web ベースのアプリ間の通信のために、XML ではなく JSON を使用してデータをシリアル化しています。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
    "MinSupportedDateTime":  "\/Date(-62135596800000)\/",
    "MaxSupportedDateTime":  "\/Date(253402300799999)\/",
    "AlgorithmType":  1,
    "CalendarType":  1,
    "Eras":  [
                 1
             ],
    "TwoDigitYearMax":  2029,
    "IsReadOnly":  false
}
```

このコマンドは、コマンドレットを使用して、 `ConvertTo-Json` いる gregoriancalendar オブジェクトを JSON 形式の文字列に変換します。

### 例 2

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

このコマンドは、の **Compress** パラメーターを使用した場合の効果を示し `ConvertTo-Json` ます。 圧縮は、文字列の外観に影響を与えますが、有効性には影響を与えません。

### 例 3

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
    "DisplayHint":  2,
    "DateTime":  "Friday, January 13, 2012 8:06:16 PM",
    "Date":  "\/Date(1326441600000)\/",
    "Day":  13,
    "DayOfWeek":  5,
    "DayOfYear":  13,
    "Hour":  20,
    "Kind":  2,
    "Millisecond":  221,
    "Minute":  6,
    "Month":  1,
    "Second":  16,
    "Ticks":  634620819762218083,
    "TimeOfDay":  {
                      "Ticks":  723762218083,
                      "Days":  0,
                      "Hours":  20,
                      "Milliseconds":  221,
                      "Minutes":  6,
                      "Seconds":  16,
                      "TotalDays":  0.83768775241087956,
                      "TotalHours":  20.104506057861109,
                      "TotalMilliseconds":  72376221.8083,
                      "TotalMinutes":  1206.2703634716668,
                      "TotalSeconds":  72376.22180829999
                  },
    "Year":  2012
}
```

この例では、コマンドレットを使用して、 `ConvertTo-Json` system.string オブジェクト **を** `Get-Date` コマンドレットから JSON 形式の文字列に変換します。 このコマンドは、コマンドレットを使用して、 `Select-Object` `*` **DateTime** オブジェクトのすべてのプロパティを取得します。 出力には、返された JSON 文字列が表示され `ConvertTo-Json` ます。

### 例 4

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : October 12, 2018 10:55:52 PM
Date        : 2018-10-12 12:00:00 AM
Day         : 12
DayOfWeek   : 5
DayOfYear   : 285
Hour        : 22
Kind        : 2
Millisecond : 768
Minute      : 55
Month       : 10
Second      : 52
Ticks       : 636749817527683372
TimeOfDay   : @{Ticks=825527683372; Days=0; Hours=22; Milliseconds=768; Minutes=55; Seconds=52;
              TotalDays=0.95547185575463; TotalHours=22.9313245381111; TotalMilliseconds=82552768.3372;
              TotalMinutes=1375.87947228667; TotalSeconds=82552.7683372}
Year        : 2018
```

この例では、 `ConvertTo-Json` コマンドレットとコマンドレットを使用して、 `ConvertFrom-Json` オブジェクトを json 文字列と json オブジェクトに変換する方法を示します。

## PARAMETERS

### -圧縮

出力文字列内の空白文字とインデントが設定された書式設定は省略されます。

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

### -深さ

JSON 表現に含める子オブジェクトのレベルを指定します。 既定値は 2 です。

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

### -InputObject

JSON 形式に変換するオブジェクトを指定します。 オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。 パイプを使用してオブジェクトをにパイプすることもでき `ConvertTo-Json` ます。

**InputObject** パラメーターは必須ですが、その値は null ( `$null` ) または空の文字列にすることができます。
入力オブジェクトがの場合 `$null` 、 `ConvertTo-Json` は出力を生成しません。 入力オブジェクトが空の文字列の場合、は `ConvertTo-Json` 空の文字列を返します。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### System.Object

パイプを使用して任意のオブジェクトをにパイプすることができ `ConvertTo-Json` ます。

## 出力

### System.String

## 注

`ConvertTo-Json`コマンドレットは、 [JavaScriptSerializer クラス](/dotnet/api/system.web.script.serialization.javascriptserializer)を使用して実装されます。

## 関連リンク

[JavaScript および .NET での JavaScript Object Notation (JSON) の概要](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertFrom-Json](ConvertFrom-Json.md)

[Get-Content](../Microsoft.PowerShell.Management/Get-Content.md)

[Get-UICulture](Get-UICulture.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
