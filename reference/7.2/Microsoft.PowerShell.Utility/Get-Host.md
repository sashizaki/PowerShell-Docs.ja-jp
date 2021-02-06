---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Host
ms.openlocfilehash: 0775940f210cb028d7a0919bb8e5ca9f256b70d8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603019"
---
# <span data-ttu-id="cde07-102">Get-Host</span><span class="sxs-lookup"><span data-stu-id="cde07-102">Get-Host</span></span>

## <span data-ttu-id="cde07-103">概要</span><span class="sxs-lookup"><span data-stu-id="cde07-103">SYNOPSIS</span></span>
<span data-ttu-id="cde07-104">現在のホスト プログラムを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="cde07-104">Gets an object that represents the current host program.</span></span>

## <span data-ttu-id="cde07-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cde07-105">SYNTAX</span></span>

```
Get-Host [<CommonParameters>]
```

## <span data-ttu-id="cde07-106">Description</span><span class="sxs-lookup"><span data-stu-id="cde07-106">DESCRIPTION</span></span>

<span data-ttu-id="cde07-107">コマンドレットは、Windows PowerShell をホストしている `Get-Host` プログラムを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="cde07-107">The `Get-Host` cmdlet gets an object that represents the program that is hosting Windows PowerShell.</span></span>

<span data-ttu-id="cde07-108">既定の表示には、Windows PowerShell のバージョン番号とホストで使用されている現在の地域と言語の設定が含まれていますが、ホスト オブジェクトには、現在実行中の Windows PowerShell のバージョンの詳細情報、現在のカルチャ、Windows PowerShell の UI カルチャなど多くの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cde07-108">The default display includes the Windows PowerShell version number and the current region and language settings that the host is using, but the host object contains a wealth of information, including detailed information about the version of Windows PowerShell that is currently running and the current culture and UI culture of Windows PowerShell.</span></span> <span data-ttu-id="cde07-109">このコマンドレットを使用すると、テキストや背景色など、ホストプログラムのユーザーインターフェイスの機能をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cde07-109">You can also use this cmdlet to customize features of the host program user interface, such as the text and background colors.</span></span>

## <span data-ttu-id="cde07-110">例</span><span class="sxs-lookup"><span data-stu-id="cde07-110">EXAMPLES</span></span>

### <span data-ttu-id="cde07-111">例 1: PowerShell コンソールホストに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="cde07-111">Example 1: Get information about the PowerShell console host</span></span>

```
PS C:\> Get-Host
Name             : ConsoleHost
Version          : 2.0
InstanceId       : e4e0ab54-cc5e-4261-9117-4081f20ce7a2
UI               : System.Management.Automation.Internal.Host.InternalHostUserInterface
CurrentCulture   : en-US
CurrentUICulture : en-US
PrivateData      : Microsoft.PowerShell.ConsoleHost+ConsoleColorProxy
IsRunspacePushed : False
Runspace         : System.Management.Automation.Runspaces.LocalRunspace
```

<span data-ttu-id="cde07-112">このコマンドは、この例の Windows PowerShell の現在のホスト プログラムである Windows PowerShell コンソールに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="cde07-112">This command displays information about the Windows PowerShell console, which is the current host program for Windows PowerShell in this example.</span></span> <span data-ttu-id="cde07-113">これには、ホストの名前、ホストで実行されている Windows PowerShell のバージョン、現在のカルチャおよび UI カルチャが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cde07-113">It includes the name of the host, the version of Windows PowerShell that is running in the host, and current culture and UI culture.</span></span>

<span data-ttu-id="cde07-114">Version、UI、CurrentCulture、CurrentUICulture、PrivateData、および Runspace プロパティには、それぞれ非常に便利なプロパティを持つオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cde07-114">The Version, UI, CurrentCulture, CurrentUICulture, PrivateData, and Runspace properties each contain an object with very useful properties.</span></span> <span data-ttu-id="cde07-115">後で示す例では、これらのプロパティを説明します。</span><span class="sxs-lookup"><span data-stu-id="cde07-115">Later examples examine these properties.</span></span>

### <span data-ttu-id="cde07-116">例 2: PowerShell ウィンドウのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="cde07-116">Example 2: Resize the PowerShell window</span></span>

```powershell
PS C:\> $H = Get-Host
PS C:\> $Win = $H.UI.RawUI.WindowSize
PS C:\> $Win.Height = 10
PS C:\> $Win.Width  = 10
PS C:\> $H.UI.RawUI.Set_WindowSize($Win)
```

<span data-ttu-id="cde07-117">このコマンドは、Windows PowerShell ウィンドウを 10 x 10 ピクセルにサイズ変更します。</span><span class="sxs-lookup"><span data-stu-id="cde07-117">This command resizes the Windows PowerShell window to 10 pixels by 10 pixels.</span></span>

### <span data-ttu-id="cde07-118">例 3: ホストの PowerShell のバージョンを取得する</span><span class="sxs-lookup"><span data-stu-id="cde07-118">Example 3: Get the PowerShell version for the host</span></span>

```powershell
PS C:\> (Get-Host).Version | Format-List -Property *
Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

<span data-ttu-id="cde07-119">このコマンドは、ホストで実行されている Windows PowerShell のバージョンに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="cde07-119">This command gets detailed information about the version of Windows PowerShell running in the host.</span></span>
<span data-ttu-id="cde07-120">これらの値は表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cde07-120">You can view, but not change, these values.</span></span>

<span data-ttu-id="cde07-121">の Version プロパティに `Get-Host` は、  system.string オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cde07-121">The Version property of `Get-Host` contains a **System.Version** object.</span></span> <span data-ttu-id="cde07-122">このコマンドは、パイプライン演算子 (|) を使用して、バージョンオブジェクトをコマンドレットに送信し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="cde07-122">This command uses a pipeline operator (|) to send the version object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="cde07-123">この `Format-List` コマンドは、 *Property* パラメーターを all (\*) 値と共に使用して、version オブジェクトのすべてのプロパティとプロパティ値を表示します。</span><span class="sxs-lookup"><span data-stu-id="cde07-123">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the version object.</span></span>

### <span data-ttu-id="cde07-124">例 4: ホストの現在のカルチャを取得する</span><span class="sxs-lookup"><span data-stu-id="cde07-124">Example 4: Get the current culture for the host</span></span>

```powershell
PS C:\> (Get-Host).CurrentCulture | Format-List -Property *
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
IsReadOnly                     : False
```

<span data-ttu-id="cde07-125">このコマンドは、ホストで実行されている Windows PowerShell に設定されている現在のカルチャに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="cde07-125">This command gets detailed information about the current culture set for Windows PowerShell running in the host.</span></span> <span data-ttu-id="cde07-126">これは、コマンドレットによって返される情報と同じです `Get-Culture` 。</span><span class="sxs-lookup"><span data-stu-id="cde07-126">This is the same information that is returned by the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="cde07-127">同様に、 **CurrentUICulture** プロパティはを返すのと同じオブジェクトを返し `Get-UICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="cde07-127">Similarly, the **CurrentUICulture** property returns the same object that `Get-UICulture` returns.</span></span>

<span data-ttu-id="cde07-128">ホストオブジェクトの **CurrentCulture** **プロパティには、system.string オブジェクトが** 含まれています。</span><span class="sxs-lookup"><span data-stu-id="cde07-128">The **CurrentCulture** property of the host object contains a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="cde07-129">このコマンドは、パイプライン演算子 (|) を使用して、 **CultureInfo** オブジェクトをコマンドレットに送信し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="cde07-129">This command uses a pipeline operator (|) to send the **CultureInfo** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="cde07-130">この `Format-List` コマンドは、 *Property* パラメーターを all (\*) 値と共に使用して、 **CultureInfo** オブジェクトのすべてのプロパティとプロパティ値を表示します。</span><span class="sxs-lookup"><span data-stu-id="cde07-130">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the **CultureInfo** object.</span></span>

### <span data-ttu-id="cde07-131">例 5: 現在のカルチャの DateTimeFormat を取得する</span><span class="sxs-lookup"><span data-stu-id="cde07-131">Example 5: Get the DateTimeFormat for the current culture</span></span>

```powershell
PS C:\> (Get-Host).CurrentCulture.DateTimeFormat | Format-List -Property *
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
MonthGenitiveNames               : {January, February, March, April...}
```

<span data-ttu-id="cde07-132">このコマンドは、Windows PowerShell に使用されている現在のカルチャの DateTimeFormat に関する詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="cde07-132">This command returns detailed information about the DateTimeFormat of the current culture that is being used for Windows PowerShell.</span></span>

<span data-ttu-id="cde07-133">ホストオブジェクトの **CurrentCulture** プロパティには、 **CultureInfo** オブジェクトが含まれています。このオブジェクトには、多くの便利なプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="cde07-133">The **CurrentCulture** property of the host object contains a **CultureInfo** object that, in turn, has many useful properties.</span></span> <span data-ttu-id="cde07-134">**DateTimeFormat** プロパティには、多くの便利なプロパティを持つ **DateTimeFormatInfo** オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cde07-134">Among them, the **DateTimeFormat** property contains a **DateTimeFormatInfo** object with many useful properties.</span></span>

<span data-ttu-id="cde07-135">オブジェクトのプロパティに格納されているオブジェクトの型を検索するには、コマンドレットを使用し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="cde07-135">To find the type of an object that is stored in an object property, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="cde07-136">オブジェクトのプロパティ値を表示するには、コマンドレットを使用し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="cde07-136">To display the property values of the object, use the `Format-List` cmdlet.</span></span>

### <span data-ttu-id="cde07-137">例 6: ホストの RawUI プロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="cde07-137">Example 6: Get the RawUI property for the host</span></span>

```
PS C:\> (Get-Host).UI.RawUI | Format-List -Property *
ForegroundColor       : DarkYellow
BackgroundColor       : DarkBlue
CursorPosition        : 0,390
WindowPosition        : 0,341
CursorSize            : 25
BufferSize            : 120,3000
WindowSize            : 120,50
MaxWindowSize         : 120,81
MaxPhysicalWindowSize : 182,81
KeyAvailable          : False
WindowTitle           : Windows PowerShell 2.0 (04/11/2008 00:08:14)
```

<span data-ttu-id="cde07-138">このコマンドは、ホストオブジェクトの **Rawui** プロパティのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="cde07-138">This command displays the properties of the **RawUI** property of the host object.</span></span> <span data-ttu-id="cde07-139">これらの値を変更すると、ホスト プログラムの外観を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="cde07-139">By changing these values, you can change the appearance of the host program.</span></span>

### <span data-ttu-id="cde07-140">例 7: PowerShell コンソールの背景色を設定する</span><span class="sxs-lookup"><span data-stu-id="cde07-140">Example 7: Set the background color for the PowerShell console</span></span>

```powershell
PS C:\> (Get-Host).UI.RawUI.BackgroundColor = "Black"
PS C:\> cls
```

<span data-ttu-id="cde07-141">これらのコマンドは、Windows PowerShell コンソールの背景色を黒に変更します。</span><span class="sxs-lookup"><span data-stu-id="cde07-141">These commands change the background color of the Windows PowerShell console to black.</span></span> <span data-ttu-id="cde07-142">**Cls** コマンドは、関数のエイリアスで、 `Clear-Host` 画面をクリアし、画面全体を新しい色に変更します。</span><span class="sxs-lookup"><span data-stu-id="cde07-142">The **cls** command is an alias for the `Clear-Host` function, which clears the screen and changes the whole screen to the new color.</span></span>

<span data-ttu-id="cde07-143">この変更は、現在のセッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="cde07-143">This change is effective only in the current session.</span></span> <span data-ttu-id="cde07-144">すべてのセッションでコンソールの背景色を変更するには、コマンドを Windows PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="cde07-144">To change the background color of the console for all sessions, add the command to your Windows PowerShell profile.</span></span>

### <span data-ttu-id="cde07-145">例 8: エラーメッセージの背景色を設定する</span><span class="sxs-lookup"><span data-stu-id="cde07-145">Example 8: Set the background color for error messages</span></span>

```
PS C:\> $Host.PrivateData.ErrorBackgroundColor = "white"
```

<span data-ttu-id="cde07-146">このコマンドは、エラー メッセージの背景色を白に変更します。</span><span class="sxs-lookup"><span data-stu-id="cde07-146">This command changes the background color of error messages to white.</span></span>

<span data-ttu-id="cde07-147">このコマンドは、 `$Host` 現在のホストプログラムのホストオブジェクトを含む自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="cde07-147">This command uses the `$Host` automatic variable, which contains the host object for the current host program.</span></span> <span data-ttu-id="cde07-148">`Get-Host` はを含む同じオブジェクトを返し `$Host` ます。そのため、これらを区別して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cde07-148">`Get-Host` returns the same object that `$Host` contains, so you can use them interchangeably.</span></span>

<span data-ttu-id="cde07-149">このコマンドは、ErrorBackgroundColor プロパティとしての **Privatedata** プロパティを使用し `$Host` ます。</span><span class="sxs-lookup"><span data-stu-id="cde07-149">This command uses the **PrivateData** property of `$Host` as its ErrorBackgroundColor property.</span></span> <span data-ttu-id="cde07-150">オブジェクトのすべてのプロパティを表示するには、「」を参照してください `$Host` 。PrivateData プロパティ、「」と入力 `$host.privatedata | format-list *` します。</span><span class="sxs-lookup"><span data-stu-id="cde07-150">To see all of the properties of the object in the `$Host`.PrivateData property, type `$host.privatedata | format-list *`.</span></span>

## <span data-ttu-id="cde07-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cde07-151">PARAMETERS</span></span>

### <span data-ttu-id="cde07-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cde07-152">CommonParameters</span></span>

<span data-ttu-id="cde07-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cde07-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cde07-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cde07-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cde07-155">入力</span><span class="sxs-lookup"><span data-stu-id="cde07-155">INPUTS</span></span>

### <span data-ttu-id="cde07-156">なし</span><span class="sxs-lookup"><span data-stu-id="cde07-156">None</span></span>
<span data-ttu-id="cde07-157">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="cde07-157">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="cde07-158">出力</span><span class="sxs-lookup"><span data-stu-id="cde07-158">OUTPUTS</span></span>

### <span data-ttu-id="cde07-159">システムの管理. 内部ホストのホスト</span><span class="sxs-lookup"><span data-stu-id="cde07-159">System.Management.Automation.Internal.Host.InternalHost</span></span>

<span data-ttu-id="cde07-160">`Get-Host` は、system.servicemodel. **内部ホスト** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="cde07-160">`Get-Host` returns a **System.Management.Automation.Internal.Host.InternalHost** object.</span></span>

## <span data-ttu-id="cde07-161">注</span><span class="sxs-lookup"><span data-stu-id="cde07-161">NOTES</span></span>

<span data-ttu-id="cde07-162">`$Host`自動変数には、を返すのと同じオブジェクトが含まれて `Get-Host` おり、これを同じ方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cde07-162">The `$Host` automatic variable contains the same object that `Get-Host` returns, and you can use it in the same way.</span></span> <span data-ttu-id="cde07-163">同様に、 `$PSCulture` および `$PSUICulture` 自動変数には、ホストオブジェクトの CurrentCulture プロパティと CurrentUICulture プロパティに格納されているものと同じオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cde07-163">Similarly, the `$PSCulture` and `$PSUICulture` automatic variables contain the same objects that the CurrentCulture and CurrentUICulture properties of the host object contain.</span></span> <span data-ttu-id="cde07-164">これらの機能は置き換えて使用できます。</span><span class="sxs-lookup"><span data-stu-id="cde07-164">You can use these features interchangeably.</span></span>

<span data-ttu-id="cde07-165">詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cde07-165">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="cde07-166">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cde07-166">RELATED LINKS</span></span>

[<span data-ttu-id="cde07-167">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="cde07-167">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="cde07-168">Read-Host</span><span class="sxs-lookup"><span data-stu-id="cde07-168">Read-Host</span></span>](Read-Host.md)

[<span data-ttu-id="cde07-169">Write-Host</span><span class="sxs-lookup"><span data-stu-id="cde07-169">Write-Host</span></span>](Write-Host.md)

