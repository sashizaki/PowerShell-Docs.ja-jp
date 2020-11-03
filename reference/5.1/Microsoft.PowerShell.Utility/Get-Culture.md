---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-culture?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Culture
ms.openlocfilehash: d7e9ebd56db3ad9de2bfbcec62f73f1f8c0e2eaa
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209063"
---
# Get-Culture

## 概要
オペレーティング システムの現在のカルチャ設定を取得します。

## SYNTAX

```
Get-Culture [<CommonParameters>]
```

## Description
**Get culture** コマンドレットは、現在のカルチャ設定に関する情報を取得します。
取得される情報には、システムの現在の言語設定 (キーボード レイアウトなど) や各種項目の表示形式 (数字、通貨、日付など) についての情報が含まれます。

また、Get-UICulture コマンドレットを使用することもできます。このコマンドレットは、システム上の現在のユーザーインターフェイスカルチャと、International モジュールの [Set culture](https://go.microsoft.com/fwlink/?LinkID=242258) コマンドレットを取得します。
ユーザー インターフェイス (UI) カルチャは、メニューやメッセージなどのユーザー インターフェイス要素に使用するテキスト文字列を決定します。

## 例

### 例 1: カルチャ設定を取得する

```
PS C:\> Get-Culture
```

このコマンドは、コンピューター上の地域設定についての情報を表示します。

### 例 2: culture オブジェクトのプロパティの書式を設定する

```
PS C:\> $C = Get-Culture
PS C:\> $C | Format-List -Property *
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - 1033
TextInfo                       : TextInfo - 1033
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar, System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False PS C:\> $C.Calendar
MinSupportedDateTime : 1/1/0001 12:00:00 AM
MaxSupportedDateTime : 12/31/9999 11:59:59 PM
AlgorithmType        : SolarCalendar
CalendarType         : Localized
Eras                 : {1}
TwoDigitYearMax      : 2029
IsReadOnly           : False PS C:\> $C.DateTimeFormat
AMDesignator                     : AM
Calendar                         : System.Globalization.GregorianCalendar
DateSeparator                    : /
FirstDayOfWeek                   : Sunday
CalendarWeekRule                 : FirstDay
FullDateTimePattern              : dddd, MMMM dd, yyyy h:mm:ss tt
LongDatePattern                  : dddd, MMMM dd, yyyy
LongTimePattern                  : h:mm:ss tt
MonthDayPattern                  : MMMM dd
PMDesignator                     : PM
RFC1123Pattern                   : ddd, dd MMM yyyy HH':'mm':'ss 'GMT'
ShortDatePattern                 : M/d/yyyy
ShortTimePattern                 : h:mm tt
SortableDateTimePattern          : yyyy'-'MM'-'dd'T'HH':'mm':'ss
TimeSeparator                    : :
UniversalSortableDateTimePattern : yyyy'-'MM'-'dd HH':'mm':'ss'Z'
YearMonthPattern                 : MMMM, yyyy
AbbreviatedDayNames              : {Sun, Mon, Tue, Wed...}
ShortestDayNames                 : {Su, Mo, Tu, We...}
DayNames                         : {Sunday, Monday, Tuesday, Wednesday...}
AbbreviatedMonthNames            : {Jan, Feb, Mar, Apr...}
MonthNames                       : {January, February, March, April...}
IsReadOnly                       : False
NativeCalendarName               : Gregorian Calendar
AbbreviatedMonthGenitiveNames    : {Jan, Feb, Mar, Apr...}
MonthGenitiveNames               : {January, February, March, April...} PS C:\> $C.DateTimeFormat.FirstDayOfWeek
Sunday
```

この例では、カルチャ オブジェクトに含まれている多数のデータが表示されます。
オブジェクトのプロパティとサブプロパティを表示する方法がわかります。

最初のコマンドは、 **Get culture** コマンドレットを使用して、コンピューター上の現在のカルチャ設定を取得します。
結果として得られるカルチャオブジェクトを $C 変数に格納します。

2 番目のコマンドは、カルチャ オブジェクトのすべてのプロパティを表示します。
パイプライン演算子 (|) を使用して、$C のカルチャオブジェクトを Format-List コマンドレットに送信します。
*Property* パラメーターを使用して、オブジェクトのすべての (*) プロパティを表示します。
このコマンドは、のように省略でき `$c | fl *` ます。

その他のコマンドは、ドット表記でカルチャ オブジェクトのプロパティを指定することにより、そのプロパティの値を表示します。
この表記を使用すると、カルチャ オブジェクトの任意のプロパティの値を表示できます。

3 番目のコマンドは、ドット表記で、カルチャ オブジェクトの Calendar プロパティの値を表示します。

4 番目のコマンドは、ドット表記で、カルチャ オブジェクトの DataTimeFormat プロパティの値を表示します。

このプロパティには、多くのサブプロパティが含まれていることがわかります。
5 番目のコマンドは、ドット表記で、DateTimeFormat プロパティのサブプロパティ FirstDayOfWeek の値を表示します。

## PARAMETERS

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし
パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### システムのグローバリゼーション
**Get-culture** は、現在のカルチャを表すオブジェクトを返します。

## 注

* また、$PsCulture 変数と $PsUICulture 変数も使用することができます。 $PsCulture 変数には、現在のカルチャの名前が格納され、$PsUICulture 変数には、現在の UI カルチャの名前が格納されます。

*

## 関連リンク

[設定-カルチャ](/powershell/module/internationalcmdlets/set-culture)

[Get-UICulture](Get-UICulture.md)
