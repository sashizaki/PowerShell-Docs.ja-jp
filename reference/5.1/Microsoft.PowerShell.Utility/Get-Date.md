---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: cbf87c2a2d6ab0f08e514ba971a622ea9f1904aa
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "95514937"
---
# <span data-ttu-id="935cc-103">Get-Date</span><span class="sxs-lookup"><span data-stu-id="935cc-103">Get-Date</span></span>

## <span data-ttu-id="935cc-104">概要</span><span class="sxs-lookup"><span data-stu-id="935cc-104">SYNOPSIS</span></span>
<span data-ttu-id="935cc-105">現在の日付と時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="935cc-105">Gets the current date and time.</span></span>

## <span data-ttu-id="935cc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="935cc-106">SYNTAX</span></span>

### <span data-ttu-id="935cc-107">net (既定値)</span><span class="sxs-lookup"><span data-stu-id="935cc-107">net (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [<CommonParameters>]
```

### <span data-ttu-id="935cc-108">UFormat</span><span class="sxs-lookup"><span data-stu-id="935cc-108">UFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-UFormat <String>] [<CommonParameters>]
```

## <span data-ttu-id="935cc-109">Description</span><span class="sxs-lookup"><span data-stu-id="935cc-109">DESCRIPTION</span></span>

<span data-ttu-id="935cc-110">この `Get-Date` コマンドレットは、現在の日付または指定した日付を表す **DateTime** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="935cc-110">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="935cc-111">`Get-Date` では、日付と時刻をいくつかの .NET 形式と UNIX 形式で書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="935cc-111">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="935cc-112">を使用し `Get-Date` て、日付または時刻の文字列を生成し、他のコマンドレットまたはプログラムに文字列を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="935cc-112">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="935cc-113">`Get-Date` コンピューターのカルチャ設定を使用して、出力形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-113">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="935cc-114">コンピューターの設定を表示するには、を使用 `(Get-Culture).DateTimeFormat` します。</span><span class="sxs-lookup"><span data-stu-id="935cc-114">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="935cc-115">例</span><span class="sxs-lookup"><span data-stu-id="935cc-115">EXAMPLES</span></span>

### <span data-ttu-id="935cc-116">例 1: 現在の日付と時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="935cc-116">Example 1: Get the current date and time</span></span>

<span data-ttu-id="935cc-117">この例では、は `Get-Date` 現在のシステム日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="935cc-117">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="935cc-118">出力は、長い日付形式と長い時刻形式です。</span><span class="sxs-lookup"><span data-stu-id="935cc-118">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="935cc-119">例 2: 現在の日付と時刻の要素を取得する</span><span class="sxs-lookup"><span data-stu-id="935cc-119">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="935cc-120">この例 `Get-Date` では、を使用して、日付要素または時刻要素を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="935cc-120">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="935cc-121">パラメーターでは、引数 **Date**、 **Time**、または **DateTime** を使用します。</span><span class="sxs-lookup"><span data-stu-id="935cc-121">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="935cc-122">`Get-Date`**Displayhint** パラメーターを **date** 引数と共に使用して、日付のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="935cc-122">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="935cc-123">例 3: .NET 書式指定子を使用して日付と時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="935cc-123">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="935cc-124">この例では、.NET 形式指定子を使用して、出力の形式をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="935cc-124">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="935cc-125">出力は **文字列** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="935cc-125">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="935cc-126">`Get-Date`**format** パラメーターを使用して、複数の書式指定子を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-126">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="935cc-127">この例で使用される .NET 形式指定子は、次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="935cc-127">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="935cc-128">指定子</span><span class="sxs-lookup"><span data-stu-id="935cc-128">Specifier</span></span> | <span data-ttu-id="935cc-129">定義</span><span class="sxs-lookup"><span data-stu-id="935cc-129">Definition</span></span> |
| --- | --- |
| `dddd` | <span data-ttu-id="935cc-130">曜日-完全名</span><span class="sxs-lookup"><span data-stu-id="935cc-130">Day of the week - full name</span></span> |
| `MM` | <span data-ttu-id="935cc-131">月の番号</span><span class="sxs-lookup"><span data-stu-id="935cc-131">Month number</span></span> |
| `dd` | <span data-ttu-id="935cc-132">月の通算日-2 桁</span><span class="sxs-lookup"><span data-stu-id="935cc-132">Day of the month - 2 digits</span></span> |
| `yyyy` | <span data-ttu-id="935cc-133">4桁表記の年</span><span class="sxs-lookup"><span data-stu-id="935cc-133">Year in 4-digit format</span></span> |
| `HH:mm` | <span data-ttu-id="935cc-134">24時間形式の時刻-秒なし</span><span class="sxs-lookup"><span data-stu-id="935cc-134">Time in 24-hour format -no seconds</span></span> |
| `K` | <span data-ttu-id="935cc-135">世界協定時刻 (UTC) からのタイムゾーンオフセット</span><span class="sxs-lookup"><span data-stu-id="935cc-135">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="935cc-136">.NET 書式指定子の詳細については、「 [カスタム日時書式指定文字列](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-136">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="935cc-137">例 4: UFormat 指定子を使用して日付と時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="935cc-137">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="935cc-138">この例では、出力の形式をカスタマイズするために、いくつかの **Uformat** 書式指定子が使用されています。</span><span class="sxs-lookup"><span data-stu-id="935cc-138">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="935cc-139">出力は **文字列** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="935cc-139">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="935cc-140">`Get-Date`**uformat** パラメーターを使用して、複数の書式指定子を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-140">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="935cc-141">この例で使用されている **Uformat** 書式指定子は、次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="935cc-141">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="935cc-142">指定子</span><span class="sxs-lookup"><span data-stu-id="935cc-142">Specifier</span></span> | <span data-ttu-id="935cc-143">定義</span><span class="sxs-lookup"><span data-stu-id="935cc-143">Definition</span></span> |
| --- | --- |
| `%A` | <span data-ttu-id="935cc-144">曜日-完全名</span><span class="sxs-lookup"><span data-stu-id="935cc-144">Day of the week - full name</span></span> |
| `%m` | <span data-ttu-id="935cc-145">月の番号</span><span class="sxs-lookup"><span data-stu-id="935cc-145">Month number</span></span> |
| `%d` | <span data-ttu-id="935cc-146">月の通算日-2 桁</span><span class="sxs-lookup"><span data-stu-id="935cc-146">Day of the month - 2 digits</span></span> |
| `%Y` | <span data-ttu-id="935cc-147">4桁表記の年</span><span class="sxs-lookup"><span data-stu-id="935cc-147">Year in 4-digit format</span></span> |
| `%R` | <span data-ttu-id="935cc-148">24時間形式の時刻-秒なし</span><span class="sxs-lookup"><span data-stu-id="935cc-148">Time in 24-hour format -no seconds</span></span> |
| `%Z` | <span data-ttu-id="935cc-149">世界協定時刻 (UTC) からのタイムゾーンオフセット</span><span class="sxs-lookup"><span data-stu-id="935cc-149">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="935cc-150">有効な **Uformat** 書式指定子の一覧については、「 [メモ](#notes) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-150">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="935cc-151">例 5: 年の日付を取得する</span><span class="sxs-lookup"><span data-stu-id="935cc-151">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="935cc-152">この例では、プロパティを使用して、年の数値を取得します。</span><span class="sxs-lookup"><span data-stu-id="935cc-152">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="935cc-153">グレゴリオ暦には、366日を持つ閏年を除き、365日が含まれています。</span><span class="sxs-lookup"><span data-stu-id="935cc-153">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="935cc-154">たとえば、2020年12月31日は366日です。</span><span class="sxs-lookup"><span data-stu-id="935cc-154">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="935cc-155">`Get-Date` は、 **年**、 **月**、 **日** という3つのパラメーターを使用して日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-155">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="935cc-156">このコマンドは、結果が **DayofYear** プロパティによって評価されるように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="935cc-156">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="935cc-157">例 6: 夏時間に合わせて日付を調整するかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="935cc-157">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="935cc-158">この例では、ブール型のメソッドを使用して、日付が夏時間によって調整されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="935cc-158">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="935cc-159">変数は、 `$DST` の結果を格納し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="935cc-159">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="935cc-160">`$DST`**IsDaylightSavingTime** メソッドを使用して、日付が夏時間に合わせて調整されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="935cc-160">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="935cc-161">例 7: 現在の時刻を UTC 時刻に変換する</span><span class="sxs-lookup"><span data-stu-id="935cc-161">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="935cc-162">この例では、現在の時刻が UTC 時刻に変換されます。</span><span class="sxs-lookup"><span data-stu-id="935cc-162">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="935cc-163">時刻の変換には、システムのロケールの UTC オフセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="935cc-163">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="935cc-164">「 [Notes](#notes) 」セクションの表に、有効な **uformat** 書式指定子の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="935cc-164">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="935cc-165">`Get-Date`**uformat** パラメーターを書式指定子と共に使用して、現在のシステムの日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="935cc-165">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="935cc-166">書式指定子 **% Z** は、 **-07** の UTC オフセットを表します。</span><span class="sxs-lookup"><span data-stu-id="935cc-166">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="935cc-167">変数には、 `$Time` 現在のシステムの日付と時刻が格納されます。</span><span class="sxs-lookup"><span data-stu-id="935cc-167">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="935cc-168">`$Time`**ToUniversalTime ()** メソッドを使用して、時刻をコンピューターの UTC オフセットに基づいて変換します。</span><span class="sxs-lookup"><span data-stu-id="935cc-168">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="935cc-169">例 8: タイムスタンプを作成する</span><span class="sxs-lookup"><span data-stu-id="935cc-169">Example 8: Create a timestamp</span></span>

<span data-ttu-id="935cc-170">この例では、書式指定子によって、ディレクトリ名のタイムスタンプ **文字列** オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="935cc-170">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="935cc-171">タイムスタンプには、日付、時刻、および UTC オフセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="935cc-171">The timestamp includes the date, time, and UTC offset.</span></span>

```powershell
$timestamp = Get-Date -Format o | ForEach-Object { $_ -replace ":", "." }
New-Item -Path C:\Test\$timestamp -Type Directory
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         6/27/2019    07:59                2019-06-27T07.59.24.4603750-07.00
```

<span data-ttu-id="935cc-172">変数は、 `$timestamp` コマンドの結果を格納し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="935cc-172">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="935cc-173">`Get-Date`**format パラメーターを** 小文字の書式指定子と共に使用して、 `o` タイムスタンプ **文字列** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="935cc-173">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="935cc-174">オブジェクトは、パイプライン内でに送信され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="935cc-174">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="935cc-175">**ScriptBlock** には、 `$_` 現在のパイプラインオブジェクトを表す変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="935cc-175">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="935cc-176">タイムスタンプ文字列は、ピリオドで置き換えられたコロンで区切られます。</span><span class="sxs-lookup"><span data-stu-id="935cc-176">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="935cc-177">`New-Item`**Path** パラメーターを使用して、新しいディレクトリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-177">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="935cc-178">パスには、 `$timestamp` ディレクトリ名として変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="935cc-178">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="935cc-179">**型** パラメーターは、ディレクトリが作成されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-179">The **Type** parameter specifies that a directory is created.</span></span>

## <span data-ttu-id="935cc-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="935cc-180">PARAMETERS</span></span>

### <span data-ttu-id="935cc-181">-日付</span><span class="sxs-lookup"><span data-stu-id="935cc-181">-Date</span></span>

<span data-ttu-id="935cc-182">日付と時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-182">Specifies a date and time.</span></span> <span data-ttu-id="935cc-183">Time は省略可能で、指定されていない場合は00:00:00 を返します。</span><span class="sxs-lookup"><span data-stu-id="935cc-183">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="935cc-184">システムロケールの標準形式で日付と時刻を入力します。</span><span class="sxs-lookup"><span data-stu-id="935cc-184">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="935cc-185">たとえば、米国英語の場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="935cc-185">For example, in US English:</span></span>

<span data-ttu-id="935cc-186">`Get-Date -Date "6/25/2019 12:30:22"` 2019年6月25日火曜日、12:30:22 を返します</span><span class="sxs-lookup"><span data-stu-id="935cc-186">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-187">-日</span><span class="sxs-lookup"><span data-stu-id="935cc-187">-Day</span></span>

<span data-ttu-id="935cc-188">表示されている月の日にちを指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-188">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="935cc-189">1 ～ 31 の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="935cc-189">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="935cc-190">指定された値が月の日数よりも大きい場合、PowerShell はその月に日数を加算します。</span><span class="sxs-lookup"><span data-stu-id="935cc-190">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="935cc-191">たとえば、には `Get-Date -Month 2 -Day 31` **2 月31日** ではなく **3 月 3** 日が表示されます。</span><span class="sxs-lookup"><span data-stu-id="935cc-191">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-192">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="935cc-192">-DisplayHint</span></span>

<span data-ttu-id="935cc-193">表示する日付と時刻の要素を決定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-193">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="935cc-194">許容される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="935cc-194">The accepted values are as follows:</span></span>

- <span data-ttu-id="935cc-195">**日付**: 日付のみを表示します</span><span class="sxs-lookup"><span data-stu-id="935cc-195">**Date**: displays only the date</span></span>
- <span data-ttu-id="935cc-196">**Time**: 時刻のみを表示します</span><span class="sxs-lookup"><span data-stu-id="935cc-196">**Time**: displays only the time</span></span>
- <span data-ttu-id="935cc-197">**DateTime**: 日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="935cc-197">**DateTime**: displays the date and time</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-198">-形式</span><span class="sxs-lookup"><span data-stu-id="935cc-198">-Format</span></span>

<span data-ttu-id="935cc-199">書式指定子で示される Microsoft .NET Framework 形式で日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="935cc-199">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="935cc-200">**Format** パラメーターは、**文字列** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="935cc-200">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="935cc-201">使用可能な .NET 書式指定子の一覧については、「 [カスタム日時書式指定文字列](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-201">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="935cc-202">**Format** パラメーターを使用する場合は、 `Get-Date` 日付を表示するために必要な **DateTime** オブジェクトのプロパティのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="935cc-202">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="935cc-203">その結果、**DateTime** オブジェクトの一部のプロパティとメソッドを利用できなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="935cc-203">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="935cc-204">PowerShell 5.0 以降では、 **Format** パラメーターの値として次の追加形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="935cc-204">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="935cc-205">**Filedate**。</span><span class="sxs-lookup"><span data-stu-id="935cc-205">**FileDate**.</span></span> <span data-ttu-id="935cc-206">現在の日付を現地時刻で表した、ファイルまたはパスによるわかりやすい表現。</span><span class="sxs-lookup"><span data-stu-id="935cc-206">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="935cc-207">形式は、 `yyyyMMdd` (大文字と小文字を区別します。4桁の年、2桁の月、および2桁の日) を使用します。</span><span class="sxs-lookup"><span data-stu-id="935cc-207">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="935cc-208">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="935cc-208">For example:</span></span>
  20190627.

- <span data-ttu-id="935cc-209">**Filedateuniversal**。</span><span class="sxs-lookup"><span data-stu-id="935cc-209">**FileDateUniversal**.</span></span> <span data-ttu-id="935cc-210">現在の日付を世界協定時刻 (UTC) で表した、ファイルまたはパスのフレンドリ表現。</span><span class="sxs-lookup"><span data-stu-id="935cc-210">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="935cc-211">形式は、 `yyyyMMddZ` (大文字と小文字を区別します。4桁の年、2桁の月、2桁の日、および UTC インジケーターとしての文字を使用し `Z` ます)。</span><span class="sxs-lookup"><span data-stu-id="935cc-211">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="935cc-212">例: 20190627Z。</span><span class="sxs-lookup"><span data-stu-id="935cc-212">For example: 20190627Z.</span></span>

- <span data-ttu-id="935cc-213">**Filedatetime**。</span><span class="sxs-lookup"><span data-stu-id="935cc-213">**FileDateTime**.</span></span> <span data-ttu-id="935cc-214">ローカル時刻の現在の日付と時刻を24時間形式で表した、ファイルまたはパスのフレンドリ表現。</span><span class="sxs-lookup"><span data-stu-id="935cc-214">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="935cc-215">形式は、 `yyyyMMddTHHmmssffff` (大文字と小文字を区別し、4桁の年、2桁の月、2桁の日、時刻の区切り記号、2桁の時間、2桁の分、2桁の秒 `T` 、および4桁のミリ秒) を使用します。</span><span class="sxs-lookup"><span data-stu-id="935cc-215">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="935cc-216">例: 20190627T0840107271。</span><span class="sxs-lookup"><span data-stu-id="935cc-216">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="935cc-217">**FileDateTimeUniversal**。</span><span class="sxs-lookup"><span data-stu-id="935cc-217">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="935cc-218">現在の日付と時刻を、世界協定時刻 (UTC) で24時間形式で表現したもの。</span><span class="sxs-lookup"><span data-stu-id="935cc-218">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="935cc-219">形式は、 `yyyyMMddTHHmmssffffZ` (大文字と小文字を区別する、4桁の年、2桁の月、2桁の日、時刻の区切り記号、2桁の時間、2桁の分、2桁の `T` 秒、4桁のミリ秒、および `Z` UTC インジケーターとしての文字) です。</span><span class="sxs-lookup"><span data-stu-id="935cc-219">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="935cc-220">例: 20190627T1540500718Z。</span><span class="sxs-lookup"><span data-stu-id="935cc-220">For example: 20190627T1540500718Z.</span></span>

```yaml
Type: System.String
Parameter Sets: net
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-221">-Hour</span><span class="sxs-lookup"><span data-stu-id="935cc-221">-Hour</span></span>

<span data-ttu-id="935cc-222">表示する時を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-222">Specifies the hour that is displayed.</span></span> <span data-ttu-id="935cc-223">0 ~ 23 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-223">Enter a value from 0 to 23.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-224">-ミリ秒</span><span class="sxs-lookup"><span data-stu-id="935cc-224">-Millisecond</span></span>

<span data-ttu-id="935cc-225">日付のミリ秒を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-225">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="935cc-226">0 ~ 999 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-226">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="935cc-227">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="935cc-227">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-228">-分</span><span class="sxs-lookup"><span data-stu-id="935cc-228">-Minute</span></span>

<span data-ttu-id="935cc-229">表示する分を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-229">Specifies the minute that is displayed.</span></span> <span data-ttu-id="935cc-230">0 ~ 59 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-230">Enter a value from 0 to 59.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-231">-Month</span><span class="sxs-lookup"><span data-stu-id="935cc-231">-Month</span></span>

<span data-ttu-id="935cc-232">表示する月を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-232">Specifies the month that is displayed.</span></span> <span data-ttu-id="935cc-233">1 ~ 12 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-233">Enter a value from 1 to 12.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-234">-Second</span><span class="sxs-lookup"><span data-stu-id="935cc-234">-Second</span></span>

<span data-ttu-id="935cc-235">表示する秒を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-235">Specifies the second that is displayed.</span></span> <span data-ttu-id="935cc-236">0 ~ 59 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-236">Enter a value from 0 to 59.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-237">-UFormat</span><span class="sxs-lookup"><span data-stu-id="935cc-237">-UFormat</span></span>

<span data-ttu-id="935cc-238">UNIX 形式で日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="935cc-238">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="935cc-239">**Uformat** パラメーターを指定すると、文字列オブジェクトが出力されます。</span><span class="sxs-lookup"><span data-stu-id="935cc-239">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="935cc-240">**Uformat** 指定子の前には、パーセント記号 () が付きます。たとえば、、、など `%` `%m` `%d` `%Y` です。</span><span class="sxs-lookup"><span data-stu-id="935cc-240">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="935cc-241">[Notes](#notes)セクションには、有効な **uformat 指定子** のテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="935cc-241">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="935cc-242">**Uformat** パラメーターを使用する場合は、 `Get-Date` 日付を表示するために必要な **DateTime** オブジェクトのプロパティのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="935cc-242">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="935cc-243">その結果、**DateTime** オブジェクトの一部のプロパティとメソッドを利用できなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="935cc-243">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

```yaml
Type: System.String
Parameter Sets: UFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-244">-年</span><span class="sxs-lookup"><span data-stu-id="935cc-244">-Year</span></span>

<span data-ttu-id="935cc-245">表示する年を指定します。</span><span class="sxs-lookup"><span data-stu-id="935cc-245">Specifies the year that is displayed.</span></span> <span data-ttu-id="935cc-246">1 ~ 9999 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-246">Enter a value from 1 to 9999.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="935cc-247">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="935cc-247">CommonParameters</span></span>

<span data-ttu-id="935cc-248">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="935cc-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="935cc-249">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="935cc-250">入力</span><span class="sxs-lookup"><span data-stu-id="935cc-250">INPUTS</span></span>

### <span data-ttu-id="935cc-251">パイプラインの入力</span><span class="sxs-lookup"><span data-stu-id="935cc-251">Pipeline input</span></span>

<span data-ttu-id="935cc-252">`Get-Date` パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="935cc-252">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="935cc-253">たとえば、「 `Get-ChildItem | Get-Date` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="935cc-253">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="935cc-254">出力</span><span class="sxs-lookup"><span data-stu-id="935cc-254">OUTPUTS</span></span>

### <span data-ttu-id="935cc-255">System.string または System.string</span><span class="sxs-lookup"><span data-stu-id="935cc-255">System.DateTime or System.String</span></span>

<span data-ttu-id="935cc-256">`Get-Date`**format** パラメーターと **uformat** パラメーターが使用されている場合を除き、 **DateTime** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="935cc-256">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="935cc-257">**Format** パラメーターまたは **uformat** パラメーターは、**文字列** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="935cc-257">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="935cc-258">**DateTime** オブジェクトが、文字列入力を必要とするなどのコマンドレットに送信されると、 `Add-Content` PowerShell はオブジェクトを **string** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="935cc-258">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="935cc-259">メソッドは、 `(Get-Date).ToString()` **DateTime** オブジェクトを **String** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="935cc-259">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="935cc-260">オブジェクトのプロパティとメソッドを表示するには、オブジェクトをパイプライン内でに送信し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="935cc-260">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="935cc-261">たとえば、「 `Get-Date | Get-Member` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="935cc-261">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="935cc-262">注</span><span class="sxs-lookup"><span data-stu-id="935cc-262">NOTES</span></span>

<span data-ttu-id="935cc-263">**DateTime** オブジェクトは、システムロケールの長い日付形式と長い時刻形式です。</span><span class="sxs-lookup"><span data-stu-id="935cc-263">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="935cc-264">有効な **Uformat 指定子** は、次の表に示されています。</span><span class="sxs-lookup"><span data-stu-id="935cc-264">The valid **UFormat specifiers** are displayed in the following table:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="935cc-265">新しいバージョンの PowerShell では、追加の **Uformat** 指定子が追加されています。</span><span class="sxs-lookup"><span data-stu-id="935cc-265">Additional **UFormat** specifiers are added in newer versions of PowerShell.</span></span> <span data-ttu-id="935cc-266">たとえば、は `%F` powershell 6.2 で追加されたため、Windows powershell 5.1 以前では使用できません。</span><span class="sxs-lookup"><span data-stu-id="935cc-266">For example, `%F` was added in PowerShell 6.2, so it isn't available in Windows PowerShell 5.1 or older.</span></span> <span data-ttu-id="935cc-267">複数のバージョンの PowerShell で実行するように設計されたスクリプトで **Uformat** 指定子を使用する場合は、この点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="935cc-267">Keep this in mind when using **UFormat** specifiers in scripts designed to be run on multiple versions of PowerShell.</span></span>

| <span data-ttu-id="935cc-268">書式指定子</span><span class="sxs-lookup"><span data-stu-id="935cc-268">Format specifier</span></span> |                                 <span data-ttu-id="935cc-269">意味</span><span class="sxs-lookup"><span data-stu-id="935cc-269">Meaning</span></span>                     |         <span data-ttu-id="935cc-270">例</span><span class="sxs-lookup"><span data-stu-id="935cc-270">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="935cc-271">曜日-完全名</span><span class="sxs-lookup"><span data-stu-id="935cc-271">Day of the week - full name</span></span>                                             | <span data-ttu-id="935cc-272">月曜日</span><span class="sxs-lookup"><span data-stu-id="935cc-272">Monday</span></span>                   |
| `%a` | <span data-ttu-id="935cc-273">曜日-省略名</span><span class="sxs-lookup"><span data-stu-id="935cc-273">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="935cc-274">Mon</span><span class="sxs-lookup"><span data-stu-id="935cc-274">Mon</span></span>                      |
| `%B` | <span data-ttu-id="935cc-275">月の名前-完全</span><span class="sxs-lookup"><span data-stu-id="935cc-275">Month name - full</span></span>                                                       | <span data-ttu-id="935cc-276">January</span><span class="sxs-lookup"><span data-stu-id="935cc-276">January</span></span>                  |
| `%b` | <span data-ttu-id="935cc-277">月の名前-略称</span><span class="sxs-lookup"><span data-stu-id="935cc-277">Month name - abbreviated</span></span>                                                | <span data-ttu-id="935cc-278">1 月</span><span class="sxs-lookup"><span data-stu-id="935cc-278">Jan</span></span>                      |
| `%C` | <span data-ttu-id="935cc-279">単位</span><span class="sxs-lookup"><span data-stu-id="935cc-279">Century</span></span>                                                                 | <span data-ttu-id="935cc-280">2019の場合は20</span><span class="sxs-lookup"><span data-stu-id="935cc-280">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="935cc-281">日付と時刻-省略形</span><span class="sxs-lookup"><span data-stu-id="935cc-281">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="935cc-282">Thu 6 月 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="935cc-282">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="935cc-283">Mm/dd/yy 形式の日付</span><span class="sxs-lookup"><span data-stu-id="935cc-283">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="935cc-284">06/27/19</span><span class="sxs-lookup"><span data-stu-id="935cc-284">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="935cc-285">月の通算日-2 桁</span><span class="sxs-lookup"><span data-stu-id="935cc-285">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="935cc-286">05</span><span class="sxs-lookup"><span data-stu-id="935cc-286">05</span></span>                       |
| `%e` | <span data-ttu-id="935cc-287">月の通算日-1 桁のみの場合はスペースで始まります。</span><span class="sxs-lookup"><span data-stu-id="935cc-287">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="935cc-288">\<space\>5/5</span><span class="sxs-lookup"><span data-stu-id="935cc-288">\<space\>5</span></span>               |
| `%G` | <span data-ttu-id="935cc-289">' Y ' と同じ</span><span class="sxs-lookup"><span data-stu-id="935cc-289">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="935cc-290">' Y ' と同じ</span><span class="sxs-lookup"><span data-stu-id="935cc-290">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="935cc-291">24時間形式の時間</span><span class="sxs-lookup"><span data-stu-id="935cc-291">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="935cc-292">17</span><span class="sxs-lookup"><span data-stu-id="935cc-292">17</span></span>                       |
| `%h` | <span data-ttu-id="935cc-293">' B ' と同じ</span><span class="sxs-lookup"><span data-stu-id="935cc-293">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="935cc-294">12時間形式の時間</span><span class="sxs-lookup"><span data-stu-id="935cc-294">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="935cc-295">05</span><span class="sxs-lookup"><span data-stu-id="935cc-295">05</span></span>                       |
| `%j` | <span data-ttu-id="935cc-296">年の通算日</span><span class="sxs-lookup"><span data-stu-id="935cc-296">Day of the year</span></span>                                                         | <span data-ttu-id="935cc-297">1-366</span><span class="sxs-lookup"><span data-stu-id="935cc-297">1-366</span></span>                    |
| `%k` | <span data-ttu-id="935cc-298">' H ' と同じ</span><span class="sxs-lookup"><span data-stu-id="935cc-298">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="935cc-299">' I ' と同じ (大文字の I)</span><span class="sxs-lookup"><span data-stu-id="935cc-299">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="935cc-300">05</span><span class="sxs-lookup"><span data-stu-id="935cc-300">05</span></span>                       |
| `%M` | <span data-ttu-id="935cc-301">分</span><span class="sxs-lookup"><span data-stu-id="935cc-301">Minutes</span></span>                                                                 | <span data-ttu-id="935cc-302">35</span><span class="sxs-lookup"><span data-stu-id="935cc-302">35</span></span>                       |
| `%m` | <span data-ttu-id="935cc-303">月の番号</span><span class="sxs-lookup"><span data-stu-id="935cc-303">Month number</span></span>                                                            | <span data-ttu-id="935cc-304">06</span><span class="sxs-lookup"><span data-stu-id="935cc-304">06</span></span>                       |
| `%n` | <span data-ttu-id="935cc-305">改行文字</span><span class="sxs-lookup"><span data-stu-id="935cc-305">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="935cc-306">AM または PM</span><span class="sxs-lookup"><span data-stu-id="935cc-306">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="935cc-307">24時間形式の時刻-秒なし</span><span class="sxs-lookup"><span data-stu-id="935cc-307">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="935cc-308">17:45</span><span class="sxs-lookup"><span data-stu-id="935cc-308">17:45</span></span>                    |
| `%r` | <span data-ttu-id="935cc-309">12時間形式の時間</span><span class="sxs-lookup"><span data-stu-id="935cc-309">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="935cc-310">09:15:36 AM</span><span class="sxs-lookup"><span data-stu-id="935cc-310">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="935cc-311">Seconds</span><span class="sxs-lookup"><span data-stu-id="935cc-311">Seconds</span></span>                                                                 | <span data-ttu-id="935cc-312">05</span><span class="sxs-lookup"><span data-stu-id="935cc-312">05</span></span>                       |
| `%s` | <span data-ttu-id="935cc-313">00:00:00 1970 年1月1日以降の経過秒数</span><span class="sxs-lookup"><span data-stu-id="935cc-313">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="935cc-314">1150451174.95705</span><span class="sxs-lookup"><span data-stu-id="935cc-314">1150451174.95705</span></span>         |
| `%t` | <span data-ttu-id="935cc-315">水平タブ文字</span><span class="sxs-lookup"><span data-stu-id="935cc-315">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="935cc-316">24 時間制の時刻</span><span class="sxs-lookup"><span data-stu-id="935cc-316">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="935cc-317">17:45:52</span><span class="sxs-lookup"><span data-stu-id="935cc-317">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="935cc-318">' W ' と同じ</span><span class="sxs-lookup"><span data-stu-id="935cc-318">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="935cc-319">曜日-数字</span><span class="sxs-lookup"><span data-stu-id="935cc-319">Day of the week - number</span></span>                                                | <span data-ttu-id="935cc-320">日曜日 = 0</span><span class="sxs-lookup"><span data-stu-id="935cc-320">Sunday = 0</span></span>               |
| `%V` | <span data-ttu-id="935cc-321">年の通算週</span><span class="sxs-lookup"><span data-stu-id="935cc-321">Week of the year</span></span>                                                        | <span data-ttu-id="935cc-322">01-53</span><span class="sxs-lookup"><span data-stu-id="935cc-322">01-53</span></span>                    |
| `%w` | <span data-ttu-id="935cc-323">' U ' と同じ</span><span class="sxs-lookup"><span data-stu-id="935cc-323">Same as 'u'</span></span>                                                             |                          |
| `%W` | <span data-ttu-id="935cc-324">年の通算週</span><span class="sxs-lookup"><span data-stu-id="935cc-324">Week of the year</span></span>                                                        | <span data-ttu-id="935cc-325">00-52</span><span class="sxs-lookup"><span data-stu-id="935cc-325">00-52</span></span>                    |
| `%X` | <span data-ttu-id="935cc-326">' T ' と同じ</span><span class="sxs-lookup"><span data-stu-id="935cc-326">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="935cc-327">ロケールの標準形式の日付</span><span class="sxs-lookup"><span data-stu-id="935cc-327">Date in standard format for locale</span></span>                                      | <span data-ttu-id="935cc-328">英語-米国の場合は06/27/19</span><span class="sxs-lookup"><span data-stu-id="935cc-328">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="935cc-329">4桁表記の年</span><span class="sxs-lookup"><span data-stu-id="935cc-329">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="935cc-330">2019</span><span class="sxs-lookup"><span data-stu-id="935cc-330">2019</span></span>                     |
| `%y` | <span data-ttu-id="935cc-331">2桁表記の年</span><span class="sxs-lookup"><span data-stu-id="935cc-331">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="935cc-332">19</span><span class="sxs-lookup"><span data-stu-id="935cc-332">19</span></span>                       |
| `%Z` | <span data-ttu-id="935cc-333">世界協定時刻 (UTC) からのタイムゾーンオフセット</span><span class="sxs-lookup"><span data-stu-id="935cc-333">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="935cc-334">-07</span><span class="sxs-lookup"><span data-stu-id="935cc-334">-07</span></span>                      |

## <span data-ttu-id="935cc-335">関連リンク</span><span class="sxs-lookup"><span data-stu-id="935cc-335">RELATED LINKS</span></span>

[<span data-ttu-id="935cc-336">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="935cc-336">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="935cc-337">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="935cc-337">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="935cc-338">Get-Member</span><span class="sxs-lookup"><span data-stu-id="935cc-338">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="935cc-339">New-Item</span><span class="sxs-lookup"><span data-stu-id="935cc-339">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="935cc-340">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="935cc-340">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="935cc-341">Set-Date</span><span class="sxs-lookup"><span data-stu-id="935cc-341">Set-Date</span></span>](Set-Date.md)
