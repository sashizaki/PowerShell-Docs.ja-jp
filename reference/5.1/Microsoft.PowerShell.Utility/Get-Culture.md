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
# <span data-ttu-id="6a76f-103">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="6a76f-103">Get-Culture</span></span>

## <span data-ttu-id="6a76f-104">概要</span><span class="sxs-lookup"><span data-stu-id="6a76f-104">SYNOPSIS</span></span>
<span data-ttu-id="6a76f-105">オペレーティング システムの現在のカルチャ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-105">Gets the current culture set in the operating system.</span></span>

## <span data-ttu-id="6a76f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6a76f-106">SYNTAX</span></span>

```
Get-Culture [<CommonParameters>]
```

## <span data-ttu-id="6a76f-107">Description</span><span class="sxs-lookup"><span data-stu-id="6a76f-107">DESCRIPTION</span></span>
<span data-ttu-id="6a76f-108">**Get culture** コマンドレットは、現在のカルチャ設定に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-108">The **Get-Culture** cmdlet gets information about the current culture settings.</span></span>
<span data-ttu-id="6a76f-109">取得される情報には、システムの現在の言語設定 (キーボード レイアウトなど) や各種項目の表示形式 (数字、通貨、日付など) についての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a76f-109">This includes information about the current language settings on the system, such as the keyboard layout, and the display format of items such as numbers, currency, and dates.</span></span>

<span data-ttu-id="6a76f-110">また、Get-UICulture コマンドレットを使用することもできます。このコマンドレットは、システム上の現在のユーザーインターフェイスカルチャと、International モジュールの [Set culture](https://go.microsoft.com/fwlink/?LinkID=242258) コマンドレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-110">You can also use the Get-UICulture cmdlet, which gets the current user interface culture on the system, and the [Set-Culture](https://go.microsoft.com/fwlink/?LinkID=242258) cmdlet in the International module.</span></span>
<span data-ttu-id="6a76f-111">ユーザー インターフェイス (UI) カルチャは、メニューやメッセージなどのユーザー インターフェイス要素に使用するテキスト文字列を決定します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-111">The user-interface (UI) culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

## <span data-ttu-id="6a76f-112">例</span><span class="sxs-lookup"><span data-stu-id="6a76f-112">EXAMPLES</span></span>

### <span data-ttu-id="6a76f-113">例 1: カルチャ設定を取得する</span><span class="sxs-lookup"><span data-stu-id="6a76f-113">Example 1: Get culture settings</span></span>

```
PS C:\> Get-Culture
```

<span data-ttu-id="6a76f-114">このコマンドは、コンピューター上の地域設定についての情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-114">This command displays information about the regional settings on the computer.</span></span>

### <span data-ttu-id="6a76f-115">例 2: culture オブジェクトのプロパティの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="6a76f-115">Example 2: Format the properties of a culture object</span></span>

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

<span data-ttu-id="6a76f-116">この例では、カルチャ オブジェクトに含まれている多数のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a76f-116">This example demonstrates the vast amount of data in the culture object.</span></span>
<span data-ttu-id="6a76f-117">オブジェクトのプロパティとサブプロパティを表示する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="6a76f-117">It shows how to display the properties and sub-properties of the object.</span></span>

<span data-ttu-id="6a76f-118">最初のコマンドは、 **Get culture** コマンドレットを使用して、コンピューター上の現在のカルチャ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-118">The first command uses the **Get-Culture** cmdlet to get the current culture settings on the computer.</span></span>
<span data-ttu-id="6a76f-119">結果として得られるカルチャオブジェクトを $C 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-119">It stores the resulting culture object in the $C variable.</span></span>

<span data-ttu-id="6a76f-120">2 番目のコマンドは、カルチャ オブジェクトのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-120">The second command displays all of the properties of the culture object.</span></span>
<span data-ttu-id="6a76f-121">パイプライン演算子 (|) を使用して、$C のカルチャオブジェクトを Format-List コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-121">It uses a pipeline operator (|) to send the culture object in $C to the Format-List cmdlet.</span></span>
<span data-ttu-id="6a76f-122">*Property* パラメーターを使用して、オブジェクトのすべての (\*) プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-122">It uses the *Property* parameter to display all (\*) properties of the object.</span></span>
<span data-ttu-id="6a76f-123">このコマンドは、のように省略でき `$c | fl *` ます。</span><span class="sxs-lookup"><span data-stu-id="6a76f-123">This command can be abbreviated as `$c | fl *`.</span></span>

<span data-ttu-id="6a76f-124">その他のコマンドは、ドット表記でカルチャ オブジェクトのプロパティを指定することにより、そのプロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-124">The remaining commands explore the properties of the culture object by using dot notation to display the values of the object properties.</span></span>
<span data-ttu-id="6a76f-125">この表記を使用すると、カルチャ オブジェクトの任意のプロパティの値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6a76f-125">You can use this notation to display the value of any property of the object.</span></span>

<span data-ttu-id="6a76f-126">3 番目のコマンドは、ドット表記で、カルチャ オブジェクトの Calendar プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-126">The third command uses dot notation to display the value of the Calendar property of the culture object.</span></span>

<span data-ttu-id="6a76f-127">4 番目のコマンドは、ドット表記で、カルチャ オブジェクトの DataTimeFormat プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-127">The fourth command uses dot notation to display the value of the DataTimeFormat property of the culture object.</span></span>

<span data-ttu-id="6a76f-128">このプロパティには、多くのサブプロパティが含まれていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="6a76f-128">Many object properties have properties.</span></span>
<span data-ttu-id="6a76f-129">5 番目のコマンドは、ドット表記で、DateTimeFormat プロパティのサブプロパティ FirstDayOfWeek の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-129">The fifth command uses dot notation to display the value of the FirstDayOfWeek property of the DateTimeFormat property.</span></span>

## <span data-ttu-id="6a76f-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6a76f-130">PARAMETERS</span></span>

### <span data-ttu-id="6a76f-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a76f-131">CommonParameters</span></span>
<span data-ttu-id="6a76f-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6a76f-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6a76f-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a76f-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6a76f-134">入力</span><span class="sxs-lookup"><span data-stu-id="6a76f-134">INPUTS</span></span>

### <span data-ttu-id="6a76f-135">なし</span><span class="sxs-lookup"><span data-stu-id="6a76f-135">None</span></span>
<span data-ttu-id="6a76f-136">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="6a76f-136">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="6a76f-137">出力</span><span class="sxs-lookup"><span data-stu-id="6a76f-137">OUTPUTS</span></span>

### <span data-ttu-id="6a76f-138">システムのグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="6a76f-138">System.Globalization.CultureInfo</span></span>
<span data-ttu-id="6a76f-139">**Get-culture** は、現在のカルチャを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6a76f-139">**Get-Culture** returns an object that represents the current culture.</span></span>

## <span data-ttu-id="6a76f-140">注</span><span class="sxs-lookup"><span data-stu-id="6a76f-140">NOTES</span></span>

* <span data-ttu-id="6a76f-141">また、$PsCulture 変数と $PsUICulture 変数も使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6a76f-141">You can also use the $PsCulture and $PsUICulture variables.</span></span> <span data-ttu-id="6a76f-142">$PsCulture 変数には、現在のカルチャの名前が格納され、$PsUICulture 変数には、現在の UI カルチャの名前が格納されます。</span><span class="sxs-lookup"><span data-stu-id="6a76f-142">The $PsCulture variable stores the name of the current culture and the $PsUICulture variable stores the name of the current UI culture.</span></span>

*

## <span data-ttu-id="6a76f-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6a76f-143">RELATED LINKS</span></span>

[<span data-ttu-id="6a76f-144">設定-カルチャ</span><span class="sxs-lookup"><span data-stu-id="6a76f-144">Set-Culture</span></span>](/powershell/module/internationalcmdlets/set-culture)

[<span data-ttu-id="6a76f-145">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="6a76f-145">Get-UICulture</span></span>](Get-UICulture.md)
