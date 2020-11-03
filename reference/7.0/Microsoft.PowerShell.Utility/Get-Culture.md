---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-culture?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Culture
ms.openlocfilehash: c496293ea198a01b4eeb984bad5cdff1a5718021
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210091"
---
# <span data-ttu-id="f93f8-103">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="f93f8-103">Get-Culture</span></span>

## <span data-ttu-id="f93f8-104">概要</span><span class="sxs-lookup"><span data-stu-id="f93f8-104">SYNOPSIS</span></span>
<span data-ttu-id="f93f8-105">オペレーティング システムの現在のカルチャ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-105">Gets the current culture set in the operating system.</span></span>

## <span data-ttu-id="f93f8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f93f8-106">SYNTAX</span></span>

### <span data-ttu-id="f93f8-107">CurrentCulture (既定値)</span><span class="sxs-lookup"><span data-stu-id="f93f8-107">CurrentCulture (Default)</span></span>

```
Get-Culture [-NoUserOverrides] [<CommonParameters>]
```

### <span data-ttu-id="f93f8-108">Name</span><span class="sxs-lookup"><span data-stu-id="f93f8-108">Name</span></span>

```
Get-Culture [-Name <String[]>] [-NoUserOverrides] [<CommonParameters>]
```

### <span data-ttu-id="f93f8-109">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="f93f8-109">ListAvailable</span></span>

```
Get-Culture [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="f93f8-110">Description</span><span class="sxs-lookup"><span data-stu-id="f93f8-110">DESCRIPTION</span></span>

<span data-ttu-id="f93f8-111">`Get-Culture`コマンドレットは、現在のカルチャ設定に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-111">The `Get-Culture` cmdlet gets information about the current culture settings.</span></span>
<span data-ttu-id="f93f8-112">取得される情報には、システムの現在の言語設定 (キーボード レイアウトなど) や各種項目の表示形式 (数字、通貨、日付など) についての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f93f8-112">This includes information about the current language settings on the system, such as the keyboard layout, and the display format of items such as numbers, currency, and dates.</span></span>

<span data-ttu-id="f93f8-113">また、コマンドレットを使用することもできます `Get-UICulture` 。このコマンドレットは、システム上の現在のユーザーインターフェイスカルチャと、International モジュールの [Set culture](/powershell/module/international/set-culture?view=win10-ps) コマンドレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-113">You can also use the `Get-UICulture` cmdlet, which gets the current user interface culture on the system, and the [Set-Culture](/powershell/module/international/set-culture?view=win10-ps) cmdlet in the International module.</span></span>
<span data-ttu-id="f93f8-114">ユーザー インターフェイス (UI) カルチャは、メニューやメッセージなどのユーザー インターフェイス要素に使用するテキスト文字列を決定します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-114">The user-interface (UI) culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

## <span data-ttu-id="f93f8-115">例</span><span class="sxs-lookup"><span data-stu-id="f93f8-115">EXAMPLES</span></span>

### <span data-ttu-id="f93f8-116">例 1: カルチャ設定を取得する</span><span class="sxs-lookup"><span data-stu-id="f93f8-116">Example 1: Get culture settings</span></span>

```
PS C:\> Get-Culture
```

<span data-ttu-id="f93f8-117">このコマンドは、コンピューター上の地域設定についての情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-117">This command displays information about the regional settings on the computer.</span></span>

### <span data-ttu-id="f93f8-118">例 2: culture オブジェクトのプロパティの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="f93f8-118">Example 2: Format the properties of a culture object</span></span>

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

<span data-ttu-id="f93f8-119">この例では、カルチャ オブジェクトに含まれている多数のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f93f8-119">This example demonstrates the vast amount of data in the culture object.</span></span>
<span data-ttu-id="f93f8-120">オブジェクトのプロパティとサブプロパティを表示する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="f93f8-120">It shows how to display the properties and sub-properties of the object.</span></span>

<span data-ttu-id="f93f8-121">最初のコマンドは、 **Get culture** コマンドレットを使用して、コンピューター上の現在のカルチャ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-121">The first command uses the **Get-Culture** cmdlet to get the current culture settings on the computer.</span></span>
<span data-ttu-id="f93f8-122">結果として得られるカルチャオブジェクトを $C 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-122">It stores the resulting culture object in the $C variable.</span></span>

<span data-ttu-id="f93f8-123">2 番目のコマンドは、カルチャ オブジェクトのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-123">The second command displays all of the properties of the culture object.</span></span>
<span data-ttu-id="f93f8-124">パイプライン演算子 (|) を使用して、のカルチャオブジェクトを `$C` コマンドレットに送信し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="f93f8-124">It uses a pipeline operator (|) to send the culture object in `$C` to the `Format-List` cmdlet.</span></span>
<span data-ttu-id="f93f8-125">**Property** パラメーターを使用して \* 、オブジェクトのすべての () プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-125">It uses the **Property** parameter to display all (\*) properties of the object.</span></span>
<span data-ttu-id="f93f8-126">このコマンドは、のように省略でき `$c | fl *` ます。</span><span class="sxs-lookup"><span data-stu-id="f93f8-126">This command can be abbreviated as `$c | fl *`.</span></span>

<span data-ttu-id="f93f8-127">その他のコマンドは、ドット表記でカルチャ オブジェクトのプロパティを指定することにより、そのプロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-127">The remaining commands explore the properties of the culture object by using dot notation to display the values of the object properties.</span></span>
<span data-ttu-id="f93f8-128">この表記を使用すると、カルチャ オブジェクトの任意のプロパティの値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f93f8-128">You can use this notation to display the value of any property of the object.</span></span>

<span data-ttu-id="f93f8-129">3番目のコマンドは、ドット表記を使用して、カルチャオブジェクトの **Calendar** プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-129">The third command uses dot notation to display the value of the **Calendar** property of the culture object.</span></span>

<span data-ttu-id="f93f8-130">4番目のコマンドは、ドット表記を使用して、culture オブジェクトの **DataTimeFormat** プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-130">The fourth command uses dot notation to display the value of the **DataTimeFormat** property of the culture object.</span></span>

<span data-ttu-id="f93f8-131">このプロパティには、多くのサブプロパティが含まれていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f93f8-131">Many object properties have properties.</span></span>
<span data-ttu-id="f93f8-132">5番目のコマンドは、ドット表記を使用して、 **DateTimeFormat** プロパティの **FirstDayOfWeek** プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-132">The fifth command uses dot notation to display the value of the **FirstDayOfWeek** property of the **DateTimeFormat** property.</span></span>

### <span data-ttu-id="f93f8-133">例 3: 特定のカルチャを取得する</span><span class="sxs-lookup"><span data-stu-id="f93f8-133">Example 3: Get a specific culture</span></span>

<span data-ttu-id="f93f8-134">米国で英語の CultureInfo オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-134">Get the CultureInfo object for English in the United States.</span></span>

```powershell
Get-Culture -Name en-US
```

```output
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

## <span data-ttu-id="f93f8-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f93f8-135">PARAMETERS</span></span>

### <span data-ttu-id="f93f8-136">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="f93f8-136">-ListAvailable</span></span>

<span data-ttu-id="f93f8-137">現在のオペレーティングシステムでサポートされているすべてのカルチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-137">Retrieves all cultures supported by the current operating system.</span></span>

<span data-ttu-id="f93f8-138">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f93f8-138">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f93f8-139">-Name</span><span class="sxs-lookup"><span data-stu-id="f93f8-139">-Name</span></span>

<span data-ttu-id="f93f8-140">名前に基づいて特定のカルチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-140">Retrieve a specific culture based on the name.</span></span>

<span data-ttu-id="f93f8-141">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f93f8-141">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f93f8-142">-NoUserOverrides</span><span class="sxs-lookup"><span data-stu-id="f93f8-142">-NoUserOverrides</span></span>

<span data-ttu-id="f93f8-143">現在のカルチャに対するユーザーの変更を無視します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-143">Ignore user changes for current culture.</span></span>

<span data-ttu-id="f93f8-144">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f93f8-144">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CurrentCulture, Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f93f8-145">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f93f8-145">CommonParameters</span></span>

<span data-ttu-id="f93f8-146">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f93f8-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f93f8-147">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f93f8-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f93f8-148">入力</span><span class="sxs-lookup"><span data-stu-id="f93f8-148">INPUTS</span></span>

### <span data-ttu-id="f93f8-149">なし</span><span class="sxs-lookup"><span data-stu-id="f93f8-149">None</span></span>

<span data-ttu-id="f93f8-150">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f93f8-150">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f93f8-151">出力</span><span class="sxs-lookup"><span data-stu-id="f93f8-151">OUTPUTS</span></span>

### <span data-ttu-id="f93f8-152">システムのグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="f93f8-152">System.Globalization.CultureInfo</span></span>

<span data-ttu-id="f93f8-153">`Get-Culture` 現在のカルチャを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f93f8-153">`Get-Culture` returns an object that represents the current culture.</span></span>

## <span data-ttu-id="f93f8-154">注</span><span class="sxs-lookup"><span data-stu-id="f93f8-154">NOTES</span></span>

<span data-ttu-id="f93f8-155">変数および変数を使用することもでき `$PsCulture` `$PsUICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="f93f8-155">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="f93f8-156">変数には `$PsCulture` 現在のカルチャの名前が格納され、変数には `$PsUICulture` 現在の UI カルチャの名前が格納されます。</span><span class="sxs-lookup"><span data-stu-id="f93f8-156">The `$PsCulture` variable stores the name of the current culture and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="f93f8-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f93f8-157">RELATED LINKS</span></span>

[<span data-ttu-id="f93f8-158">設定-カルチャ</span><span class="sxs-lookup"><span data-stu-id="f93f8-158">Set-Culture</span></span>](/powershell/module/international/set-culture?view=win10-ps)

[<span data-ttu-id="f93f8-159">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="f93f8-159">Get-UICulture</span></span>](Get-UICulture.md)
