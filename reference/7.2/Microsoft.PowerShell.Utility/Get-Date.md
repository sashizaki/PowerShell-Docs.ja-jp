---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: 8c0a1b7a14f5dfa071a85808f5d7dfba4d06048e
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "99599715"
---
# <span data-ttu-id="4dbaf-102">Get-Date</span><span class="sxs-lookup"><span data-stu-id="4dbaf-102">Get-Date</span></span>

## <span data-ttu-id="4dbaf-103">概要</span><span class="sxs-lookup"><span data-stu-id="4dbaf-103">SYNOPSIS</span></span>
<span data-ttu-id="4dbaf-104">現在の日付と時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-104">Gets the current date and time.</span></span>

## <span data-ttu-id="4dbaf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4dbaf-105">SYNTAX</span></span>

### <span data-ttu-id="4dbaf-106">日付 (既定値)</span><span class="sxs-lookup"><span data-stu-id="4dbaf-106">Date (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="4dbaf-107">DateUFormat</span><span class="sxs-lookup"><span data-stu-id="4dbaf-107">DateUFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

### <span data-ttu-id="4dbaf-108">UnixTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="4dbaf-108">UnixTimeSeconds</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="4dbaf-109">UnixTimeSecondsUFormat</span><span class="sxs-lookup"><span data-stu-id="4dbaf-109">UnixTimeSecondsUFormat</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

## <span data-ttu-id="4dbaf-110">Description</span><span class="sxs-lookup"><span data-stu-id="4dbaf-110">DESCRIPTION</span></span>

<span data-ttu-id="4dbaf-111">この `Get-Date` コマンドレットは、現在の日付または指定した日付を表す **DateTime** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-111">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="4dbaf-112">`Get-Date` では、日付と時刻をいくつかの .NET 形式と UNIX 形式で書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-112">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="4dbaf-113">を使用し `Get-Date` て、日付または時刻の文字列を生成し、他のコマンドレットまたはプログラムに文字列を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-113">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="4dbaf-114">`Get-Date` コンピューターのカルチャ設定を使用して、出力形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-114">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="4dbaf-115">コンピューターの設定を表示するには、を使用 `(Get-Culture).DateTimeFormat` します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-115">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="4dbaf-116">例</span><span class="sxs-lookup"><span data-stu-id="4dbaf-116">EXAMPLES</span></span>

### <span data-ttu-id="4dbaf-117">例 1: 現在の日付と時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="4dbaf-117">Example 1: Get the current date and time</span></span>

<span data-ttu-id="4dbaf-118">この例では、は `Get-Date` 現在のシステム日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-118">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="4dbaf-119">出力は、長い日付形式と長い時刻形式です。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-119">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="4dbaf-120">例 2: 現在の日付と時刻の要素を取得する</span><span class="sxs-lookup"><span data-stu-id="4dbaf-120">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="4dbaf-121">この例 `Get-Date` では、を使用して、日付要素または時刻要素を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-121">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="4dbaf-122">パラメーターでは、引数 **Date**、 **Time**、または **DateTime** を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-122">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="4dbaf-123">`Get-Date`**Displayhint** パラメーターを **date** 引数と共に使用して、日付のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-123">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="4dbaf-124">例 3: .NET 書式指定子を使用して日付と時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="4dbaf-124">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="4dbaf-125">この例では、.NET 形式指定子を使用して、出力の形式をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-125">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="4dbaf-126">出力は **文字列** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-126">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="4dbaf-127">`Get-Date`**format** パラメーターを使用して、複数の書式指定子を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-127">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="4dbaf-128">この例で使用される .NET 形式指定子は、次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-128">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="4dbaf-129">指定子</span><span class="sxs-lookup"><span data-stu-id="4dbaf-129">Specifier</span></span> |                      <span data-ttu-id="4dbaf-130">定義</span><span class="sxs-lookup"><span data-stu-id="4dbaf-130">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `dddd`    | <span data-ttu-id="4dbaf-131">曜日-完全名</span><span class="sxs-lookup"><span data-stu-id="4dbaf-131">Day of the week - full name</span></span>                           |
| `MM`      | <span data-ttu-id="4dbaf-132">月の番号</span><span class="sxs-lookup"><span data-stu-id="4dbaf-132">Month number</span></span>                                          |
| `dd`      | <span data-ttu-id="4dbaf-133">月の通算日-2 桁</span><span class="sxs-lookup"><span data-stu-id="4dbaf-133">Day of the month - 2 digits</span></span>                           |
| `yyyy`    | <span data-ttu-id="4dbaf-134">4桁表記の年</span><span class="sxs-lookup"><span data-stu-id="4dbaf-134">Year in 4-digit format</span></span>                                |
| `HH:mm`   | <span data-ttu-id="4dbaf-135">24時間形式の時刻-秒なし</span><span class="sxs-lookup"><span data-stu-id="4dbaf-135">Time in 24-hour format - no seconds</span></span>                    |
| `K`       | <span data-ttu-id="4dbaf-136">世界協定時刻 (UTC) からのタイムゾーンオフセット</span><span class="sxs-lookup"><span data-stu-id="4dbaf-136">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="4dbaf-137">.NET 書式指定子の詳細については、「 [カスタム日時書式指定文字列](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-137">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="4dbaf-138">例 4: UFormat 指定子を使用して日付と時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="4dbaf-138">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="4dbaf-139">この例では、出力の形式をカスタマイズするために、いくつかの **Uformat** 書式指定子が使用されています。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-139">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="4dbaf-140">出力は **文字列** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-140">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="4dbaf-141">`Get-Date`**uformat** パラメーターを使用して、複数の書式指定子を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-141">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="4dbaf-142">この例で使用されている **Uformat** 書式指定子は、次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-142">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="4dbaf-143">指定子</span><span class="sxs-lookup"><span data-stu-id="4dbaf-143">Specifier</span></span> |                      <span data-ttu-id="4dbaf-144">定義</span><span class="sxs-lookup"><span data-stu-id="4dbaf-144">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `%A`      | <span data-ttu-id="4dbaf-145">曜日-完全名</span><span class="sxs-lookup"><span data-stu-id="4dbaf-145">Day of the week - full name</span></span>                           |
| `%m`      | <span data-ttu-id="4dbaf-146">月の番号</span><span class="sxs-lookup"><span data-stu-id="4dbaf-146">Month number</span></span>                                          |
| `%d`      | <span data-ttu-id="4dbaf-147">月の通算日-2 桁</span><span class="sxs-lookup"><span data-stu-id="4dbaf-147">Day of the month - 2 digits</span></span>                           |
| `%Y`      | <span data-ttu-id="4dbaf-148">4桁表記の年</span><span class="sxs-lookup"><span data-stu-id="4dbaf-148">Year in 4-digit format</span></span>                                |
| `%R`      | <span data-ttu-id="4dbaf-149">24時間形式の時刻-秒なし</span><span class="sxs-lookup"><span data-stu-id="4dbaf-149">Time in 24-hour format - no seconds</span></span>                    |
| `%Z`      | <span data-ttu-id="4dbaf-150">世界協定時刻 (UTC) からのタイムゾーンオフセット</span><span class="sxs-lookup"><span data-stu-id="4dbaf-150">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="4dbaf-151">有効な **Uformat** 書式指定子の一覧については、「 [メモ](#notes) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-151">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="4dbaf-152">例 5: 年の日付を取得する</span><span class="sxs-lookup"><span data-stu-id="4dbaf-152">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="4dbaf-153">この例では、プロパティを使用して、年の数値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-153">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="4dbaf-154">グレゴリオ暦には、366日を持つ閏年を除き、365日が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-154">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="4dbaf-155">たとえば、2020年12月31日は366日です。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-155">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="4dbaf-156">`Get-Date` は、 **年**、 **月**、 **日** という3つのパラメーターを使用して日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-156">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="4dbaf-157">このコマンドは、結果が **DayofYear** プロパティによって評価されるように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-157">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="4dbaf-158">例 6: 夏時間に合わせて日付を調整するかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="4dbaf-158">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="4dbaf-159">この例では、ブール型のメソッドを使用して、日付が夏時間によって調整されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-159">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="4dbaf-160">変数は、 `$DST` の結果を格納し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-160">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="4dbaf-161">`$DST`**IsDaylightSavingTime** メソッドを使用して、日付が夏時間に合わせて調整されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-161">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="4dbaf-162">例 7: 現在の時刻を UTC 時刻に変換する</span><span class="sxs-lookup"><span data-stu-id="4dbaf-162">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="4dbaf-163">この例では、現在の時刻が UTC 時刻に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-163">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="4dbaf-164">時刻の変換には、システムのロケールの UTC オフセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-164">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="4dbaf-165">「 [Notes](#notes) 」セクションの表に、有効な **uformat** 書式指定子の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-165">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="4dbaf-166">`Get-Date`**uformat** パラメーターを書式指定子と共に使用して、現在のシステムの日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-166">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="4dbaf-167">書式指定子 **% Z** は、 **-07** の UTC オフセットを表します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-167">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="4dbaf-168">変数には、 `$Time` 現在のシステムの日付と時刻が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-168">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="4dbaf-169">`$Time`**ToUniversalTime ()** メソッドを使用して、時刻をコンピューターの UTC オフセットに基づいて変換します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-169">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="4dbaf-170">例 8: タイムスタンプを作成する</span><span class="sxs-lookup"><span data-stu-id="4dbaf-170">Example 8: Create a timestamp</span></span>

<span data-ttu-id="4dbaf-171">この例では、書式指定子によって、ディレクトリ名のタイムスタンプ **文字列** オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-171">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="4dbaf-172">タイムスタンプには、日付、時刻、および UTC オフセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-172">The timestamp includes the date, time, and UTC offset.</span></span>

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

<span data-ttu-id="4dbaf-173">変数は、 `$timestamp` コマンドの結果を格納し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-173">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="4dbaf-174">`Get-Date`**format パラメーターを** 小文字の書式指定子と共に使用して、 `o` タイムスタンプ **文字列** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-174">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="4dbaf-175">オブジェクトは、パイプライン内でに送信され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-175">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="4dbaf-176">**ScriptBlock** には、 `$_` 現在のパイプラインオブジェクトを表す変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-176">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="4dbaf-177">タイムスタンプ文字列は、ピリオドで置き換えられたコロンで区切られます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-177">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="4dbaf-178">`New-Item`**Path** パラメーターを使用して、新しいディレクトリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-178">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="4dbaf-179">パスには、 `$timestamp` ディレクトリ名として変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-179">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="4dbaf-180">**型** パラメーターは、ディレクトリが作成されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-180">The **Type** parameter specifies that a directory is created.</span></span>

### <span data-ttu-id="4dbaf-181">例 9: Unix タイムスタンプを変換する</span><span class="sxs-lookup"><span data-stu-id="4dbaf-181">Example 9: Convert a Unix timestamp</span></span>

<span data-ttu-id="4dbaf-182">この例では、Unix 時刻 (1970-01-01 0:00:00 以降の秒数で表されます) を DateTime に変換します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-182">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

```powershell
Get-Date -UnixTimeSeconds 1577836800
```

```Output
Wednesday, January 01, 2020 12:00:00 AM
```

### <span data-ttu-id="4dbaf-183">例 10: UTC として解釈される日付値を返す</span><span class="sxs-lookup"><span data-stu-id="4dbaf-183">Example 10: Return a date value interpreted as UTC</span></span>

<span data-ttu-id="4dbaf-184">この例では、日付値を UTC と等価に解釈する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-184">This example shows how to interpret a date value as its UTC equivalent.</span></span> <span data-ttu-id="4dbaf-185">この例では、このコンピューターは **太平洋標準時** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-185">For the example, this machine is set to **Pacific Standard Time**.</span></span> <span data-ttu-id="4dbaf-186">既定では、は `Get-Date` そのタイムゾーンの値を返します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-186">By default, `Get-Date` returns values for that timezone.</span></span> <span data-ttu-id="4dbaf-187">値を UTC に相当する時刻に変換するには、 **Asutc** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-187">Use the **AsUTC** parameter to convert the value to the UTC equivalent time.</span></span>

```powershell
PS> Get-TimeZone

Id                         : Pacific Standard Time
DisplayName                : (UTC-08:00) Pacific Time (US & Canada)
StandardName               : Pacific Standard Time
DaylightName               : Pacific Daylight Time
BaseUtcOffset              : -08:00:00
SupportsDaylightSavingTime : True

PS> (Get-Date -Date "2020-01-01T00:00:00").Kind
Unspecified

PS> Get-Date -Date "2020-01-01T00:00:00"

Wednesday, January 1, 2020 12:00:00 AM

PS> (Get-Date -Date "2020-01-01T00:00:00" -AsUTC).Kind
Utc

PS> Get-Date -Date "2020-01-01T00:00:00" -AsUTC

Wednesday, January 1, 2020 8:00:00 AM
```

## <span data-ttu-id="4dbaf-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4dbaf-188">PARAMETERS</span></span>

### <span data-ttu-id="4dbaf-189">-AsUTC</span><span class="sxs-lookup"><span data-stu-id="4dbaf-189">-AsUTC</span></span>

<span data-ttu-id="4dbaf-190">日付値を UTC の同等の時刻に変換します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-190">Converts the date value to the equivalent time in UTC.</span></span>

<span data-ttu-id="4dbaf-191">このパラメーターは、PowerShell 7.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-191">This parameter was introduced in PowerShell 7.1.</span></span>

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

### <span data-ttu-id="4dbaf-192">-日付</span><span class="sxs-lookup"><span data-stu-id="4dbaf-192">-Date</span></span>

<span data-ttu-id="4dbaf-193">日付と時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-193">Specifies a date and time.</span></span> <span data-ttu-id="4dbaf-194">Time は省略可能で、指定されていない場合は00:00:00 を返します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-194">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="4dbaf-195">システムロケールの標準形式で日付と時刻を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-195">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="4dbaf-196">たとえば、米国英語の場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-196">For example, in US English:</span></span>

<span data-ttu-id="4dbaf-197">`Get-Date -Date "6/25/2019 12:30:22"` 2019年6月25日火曜日、12:30:22 を返します</span><span class="sxs-lookup"><span data-stu-id="4dbaf-197">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

```yaml
Type: System.DateTime
Parameter Sets: DateAndFormat, DateAndUFormat
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4dbaf-198">-日</span><span class="sxs-lookup"><span data-stu-id="4dbaf-198">-Day</span></span>

<span data-ttu-id="4dbaf-199">表示されている月の日にちを指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-199">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="4dbaf-200">1 ～ 31 の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-200">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="4dbaf-201">指定された値が月の日数よりも大きい場合、PowerShell はその月に日数を加算します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-201">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="4dbaf-202">たとえば、には `Get-Date -Month 2 -Day 31` **2 月31日** ではなく **3 月 3** 日が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-202">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

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

### <span data-ttu-id="4dbaf-203">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="4dbaf-203">-DisplayHint</span></span>

<span data-ttu-id="4dbaf-204">表示する日付と時刻の要素を決定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-204">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="4dbaf-205">許容される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-205">The accepted values are as follows:</span></span>

- <span data-ttu-id="4dbaf-206">**日付**: 日付のみを表示します</span><span class="sxs-lookup"><span data-stu-id="4dbaf-206">**Date**: displays only the date</span></span>
- <span data-ttu-id="4dbaf-207">**Time**: 時刻のみを表示します</span><span class="sxs-lookup"><span data-stu-id="4dbaf-207">**Time**: displays only the time</span></span>
- <span data-ttu-id="4dbaf-208">**DateTime**: 日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-208">**DateTime**: displays the date and time</span></span>

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

### <span data-ttu-id="4dbaf-209">-形式</span><span class="sxs-lookup"><span data-stu-id="4dbaf-209">-Format</span></span>

<span data-ttu-id="4dbaf-210">書式指定子で示される Microsoft .NET Framework 形式で日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-210">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="4dbaf-211">**Format** パラメーターは、**文字列** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-211">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="4dbaf-212">使用可能な .NET 書式指定子の一覧については、「 [カスタム日時書式指定文字列](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-212">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="4dbaf-213">**Format** パラメーターを使用する場合は、 `Get-Date` 日付を表示するために必要な **DateTime** オブジェクトのプロパティのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-213">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="4dbaf-214">その結果、**DateTime** オブジェクトの一部のプロパティとメソッドを利用できなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-214">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="4dbaf-215">PowerShell 5.0 以降では、 **Format** パラメーターの値として次の追加形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-215">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="4dbaf-216">**Filedate**。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-216">**FileDate**.</span></span> <span data-ttu-id="4dbaf-217">現在の日付を現地時刻で表した、ファイルまたはパスによるわかりやすい表現。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-217">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="4dbaf-218">形式は、 `yyyyMMdd` (大文字と小文字を区別します。4桁の年、2桁の月、および2桁の日) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-218">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="4dbaf-219">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-219">For example:</span></span>
  20190627.

- <span data-ttu-id="4dbaf-220">**Filedateuniversal**。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-220">**FileDateUniversal**.</span></span> <span data-ttu-id="4dbaf-221">現在の日付を世界協定時刻 (UTC) で表した、ファイルまたはパスのフレンドリ表現。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-221">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="4dbaf-222">形式は、 `yyyyMMddZ` (大文字と小文字を区別します。4桁の年、2桁の月、2桁の日、および UTC インジケーターとしての文字を使用し `Z` ます)。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-222">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="4dbaf-223">例: 20190627Z。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-223">For example: 20190627Z.</span></span>

- <span data-ttu-id="4dbaf-224">**Filedatetime**。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-224">**FileDateTime**.</span></span> <span data-ttu-id="4dbaf-225">ローカル時刻の現在の日付と時刻を24時間形式で表した、ファイルまたはパスのフレンドリ表現。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-225">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="4dbaf-226">形式は、 `yyyyMMddTHHmmssffff` (大文字と小文字を区別し、4桁の年、2桁の月、2桁の日、時刻の区切り記号、2桁の時間、2桁の分、2桁の秒 `T` 、および4桁のミリ秒) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-226">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="4dbaf-227">例: 20190627T0840107271。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-227">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="4dbaf-228">**FileDateTimeUniversal**。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-228">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="4dbaf-229">現在の日付と時刻を、世界協定時刻 (UTC) で24時間形式で表現したもの。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-229">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="4dbaf-230">形式は、 `yyyyMMddTHHmmssffffZ` (大文字と小文字を区別する、4桁の年、2桁の月、2桁の日、時刻の区切り記号、2桁の時間、2桁の分、2桁の `T` 秒、4桁のミリ秒、および `Z` UTC インジケーターとしての文字) です。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-230">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="4dbaf-231">例: 20190627T1540500718Z。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-231">For example: 20190627T1540500718Z.</span></span>

```yaml
Type: System.String
Parameter Sets: DateAndFormat, UnixTimeSecondsAndFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dbaf-232">-Hour</span><span class="sxs-lookup"><span data-stu-id="4dbaf-232">-Hour</span></span>

<span data-ttu-id="4dbaf-233">表示する時を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-233">Specifies the hour that is displayed.</span></span> <span data-ttu-id="4dbaf-234">0 ~ 23 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-234">Enter a value from 0 to 23.</span></span>

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

### <span data-ttu-id="4dbaf-235">-ミリ秒</span><span class="sxs-lookup"><span data-stu-id="4dbaf-235">-Millisecond</span></span>

<span data-ttu-id="4dbaf-236">日付のミリ秒を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-236">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="4dbaf-237">0 ~ 999 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-237">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="4dbaf-238">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-238">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4dbaf-239">-分</span><span class="sxs-lookup"><span data-stu-id="4dbaf-239">-Minute</span></span>

<span data-ttu-id="4dbaf-240">表示する分を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-240">Specifies the minute that is displayed.</span></span> <span data-ttu-id="4dbaf-241">0 ~ 59 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-241">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="4dbaf-242">-Month</span><span class="sxs-lookup"><span data-stu-id="4dbaf-242">-Month</span></span>

<span data-ttu-id="4dbaf-243">表示する月を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-243">Specifies the month that is displayed.</span></span> <span data-ttu-id="4dbaf-244">1 ~ 12 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-244">Enter a value from 1 to 12.</span></span>

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

### <span data-ttu-id="4dbaf-245">-Second</span><span class="sxs-lookup"><span data-stu-id="4dbaf-245">-Second</span></span>

<span data-ttu-id="4dbaf-246">表示する秒を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-246">Specifies the second that is displayed.</span></span> <span data-ttu-id="4dbaf-247">0 ~ 59 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-247">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="4dbaf-248">-UFormat</span><span class="sxs-lookup"><span data-stu-id="4dbaf-248">-UFormat</span></span>

<span data-ttu-id="4dbaf-249">UNIX 形式で日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-249">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="4dbaf-250">**Uformat** パラメーターを指定すると、文字列オブジェクトが出力されます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-250">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="4dbaf-251">**Uformat** 指定子の前には、パーセント記号 () が付きます。たとえば、、、など `%` `%m` `%d` `%Y` です。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-251">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="4dbaf-252">[Notes](#notes)セクションには、有効な **uformat 指定子** のテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-252">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="4dbaf-253">**Uformat** パラメーターを使用する場合は、 `Get-Date` 日付を表示するために必要な **DateTime** オブジェクトのプロパティのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-253">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="4dbaf-254">その結果、**DateTime** オブジェクトの一部のプロパティとメソッドを利用できなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-254">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

```yaml
Type: System.String
Parameter Sets: DateAndUFormat, UnixTimeSecondsAndUFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dbaf-255">-UnixTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="4dbaf-255">-UnixTimeSeconds</span></span>

<span data-ttu-id="4dbaf-256">0:00:00 1970 年1月1日以降の秒数で表された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-256">Date and time represented in seconds since January 1, 1970, 0:00:00.</span></span>

<span data-ttu-id="4dbaf-257">このパラメーターは、PowerShell 7.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-257">This parameter was introduced in PowerShell 7.1.</span></span>

```yaml
Type: System.Int64
Parameter Sets: UnixTimeSecondsAndFormat, UnixTimeSecondsAndUFormat
Aliases: UnixTime

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dbaf-258">-年</span><span class="sxs-lookup"><span data-stu-id="4dbaf-258">-Year</span></span>

<span data-ttu-id="4dbaf-259">表示する年を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-259">Specifies the year that is displayed.</span></span> <span data-ttu-id="4dbaf-260">1 ~ 9999 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-260">Enter a value from 1 to 9999.</span></span>

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

### <span data-ttu-id="4dbaf-261">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dbaf-261">CommonParameters</span></span>

<span data-ttu-id="4dbaf-262">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-262">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4dbaf-263">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-263">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4dbaf-264">入力</span><span class="sxs-lookup"><span data-stu-id="4dbaf-264">INPUTS</span></span>

### <span data-ttu-id="4dbaf-265">パイプラインの入力</span><span class="sxs-lookup"><span data-stu-id="4dbaf-265">Pipeline input</span></span>

<span data-ttu-id="4dbaf-266">`Get-Date` パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-266">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="4dbaf-267">たとえば、`Get-ChildItem | Get-Date` のようになります。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-267">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="4dbaf-268">出力</span><span class="sxs-lookup"><span data-stu-id="4dbaf-268">OUTPUTS</span></span>

### <span data-ttu-id="4dbaf-269">System.string または System.string</span><span class="sxs-lookup"><span data-stu-id="4dbaf-269">System.DateTime or System.String</span></span>

<span data-ttu-id="4dbaf-270">`Get-Date`**format** パラメーターと **uformat** パラメーターが使用されている場合を除き、 **DateTime** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-270">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="4dbaf-271">**Format** パラメーターまたは **uformat** パラメーターは、**文字列** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-271">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="4dbaf-272">**DateTime** オブジェクトが、文字列入力を必要とするなどのコマンドレットに送信されると、 `Add-Content` PowerShell はオブジェクトを **string** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-272">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="4dbaf-273">メソッドは、 `(Get-Date).ToString()` **DateTime** オブジェクトを **String** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-273">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="4dbaf-274">オブジェクトのプロパティとメソッドを表示するには、オブジェクトをパイプライン内でに送信し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-274">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="4dbaf-275">たとえば、`Get-Date | Get-Member` のようになります。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-275">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="4dbaf-276">注</span><span class="sxs-lookup"><span data-stu-id="4dbaf-276">NOTES</span></span>

<span data-ttu-id="4dbaf-277">**DateTime** オブジェクトは、システムロケールの長い日付形式と長い時刻形式です。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-277">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="4dbaf-278">有効な **Uformat 指定子** は、次の表に示されています。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-278">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="4dbaf-279">書式指定子</span><span class="sxs-lookup"><span data-stu-id="4dbaf-279">Format specifier</span></span> |                                 <span data-ttu-id="4dbaf-280">意味</span><span class="sxs-lookup"><span data-stu-id="4dbaf-280">Meaning</span></span>                     |         <span data-ttu-id="4dbaf-281">例</span><span class="sxs-lookup"><span data-stu-id="4dbaf-281">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="4dbaf-282">曜日-完全名</span><span class="sxs-lookup"><span data-stu-id="4dbaf-282">Day of the week - full name</span></span>                                             | <span data-ttu-id="4dbaf-283">月曜日</span><span class="sxs-lookup"><span data-stu-id="4dbaf-283">Monday</span></span>                   |
| `%a` | <span data-ttu-id="4dbaf-284">曜日-省略名</span><span class="sxs-lookup"><span data-stu-id="4dbaf-284">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="4dbaf-285">Mon</span><span class="sxs-lookup"><span data-stu-id="4dbaf-285">Mon</span></span>                      |
| `%B` | <span data-ttu-id="4dbaf-286">月の名前-完全</span><span class="sxs-lookup"><span data-stu-id="4dbaf-286">Month name - full</span></span>                                                       | <span data-ttu-id="4dbaf-287">January</span><span class="sxs-lookup"><span data-stu-id="4dbaf-287">January</span></span>                  |
| `%b` | <span data-ttu-id="4dbaf-288">月の名前-略称</span><span class="sxs-lookup"><span data-stu-id="4dbaf-288">Month name - abbreviated</span></span>                                                | <span data-ttu-id="4dbaf-289">1 月</span><span class="sxs-lookup"><span data-stu-id="4dbaf-289">Jan</span></span>                      |
| `%C` | <span data-ttu-id="4dbaf-290">単位</span><span class="sxs-lookup"><span data-stu-id="4dbaf-290">Century</span></span>                                                                 | <span data-ttu-id="4dbaf-291">2019の場合は20</span><span class="sxs-lookup"><span data-stu-id="4dbaf-291">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="4dbaf-292">日付と時刻-省略形</span><span class="sxs-lookup"><span data-stu-id="4dbaf-292">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="4dbaf-293">Thu 6 月 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="4dbaf-293">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="4dbaf-294">Mm/dd/yy 形式の日付</span><span class="sxs-lookup"><span data-stu-id="4dbaf-294">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="4dbaf-295">06/27/19</span><span class="sxs-lookup"><span data-stu-id="4dbaf-295">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="4dbaf-296">月の通算日-2 桁</span><span class="sxs-lookup"><span data-stu-id="4dbaf-296">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="4dbaf-297">05</span><span class="sxs-lookup"><span data-stu-id="4dbaf-297">05</span></span>                       |
| `%e` | <span data-ttu-id="4dbaf-298">月の通算日-1 桁のみの場合はスペースで始まります。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-298">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="4dbaf-299">\<space\>5/5</span><span class="sxs-lookup"><span data-stu-id="4dbaf-299">\<space\>5</span></span>               |
| `%F` | <span data-ttu-id="4dbaf-300">YYYY-mm-dd 形式の日付。% Y-% m-% d (ISO 8601 日付形式) に相当します。</span><span class="sxs-lookup"><span data-stu-id="4dbaf-300">Date in YYYY-mm-dd format, equal to %Y-%m-%d (the ISO 8601 date format)</span></span> | <span data-ttu-id="4dbaf-301">2019-06-27</span><span class="sxs-lookup"><span data-stu-id="4dbaf-301">2019-06-27</span></span>               |
| `%G` | <span data-ttu-id="4dbaf-302">' Y ' と同じ</span><span class="sxs-lookup"><span data-stu-id="4dbaf-302">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="4dbaf-303">' Y ' と同じ</span><span class="sxs-lookup"><span data-stu-id="4dbaf-303">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="4dbaf-304">24時間形式の時間</span><span class="sxs-lookup"><span data-stu-id="4dbaf-304">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="4dbaf-305">17</span><span class="sxs-lookup"><span data-stu-id="4dbaf-305">17</span></span>                       |
| `%h` | <span data-ttu-id="4dbaf-306">' B ' と同じ</span><span class="sxs-lookup"><span data-stu-id="4dbaf-306">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="4dbaf-307">12時間形式の時間</span><span class="sxs-lookup"><span data-stu-id="4dbaf-307">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="4dbaf-308">05</span><span class="sxs-lookup"><span data-stu-id="4dbaf-308">05</span></span>                       |
| `%j` | <span data-ttu-id="4dbaf-309">年の通算日</span><span class="sxs-lookup"><span data-stu-id="4dbaf-309">Day of the year</span></span>                                                         | <span data-ttu-id="4dbaf-310">1-366</span><span class="sxs-lookup"><span data-stu-id="4dbaf-310">1-366</span></span>                    |
| `%k` | <span data-ttu-id="4dbaf-311">' H ' と同じ</span><span class="sxs-lookup"><span data-stu-id="4dbaf-311">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="4dbaf-312">' I ' と同じ (大文字の I)</span><span class="sxs-lookup"><span data-stu-id="4dbaf-312">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="4dbaf-313">05</span><span class="sxs-lookup"><span data-stu-id="4dbaf-313">05</span></span>                       |
| `%M` | <span data-ttu-id="4dbaf-314">分</span><span class="sxs-lookup"><span data-stu-id="4dbaf-314">Minutes</span></span>                                                                 | <span data-ttu-id="4dbaf-315">35</span><span class="sxs-lookup"><span data-stu-id="4dbaf-315">35</span></span>                       |
| `%m` | <span data-ttu-id="4dbaf-316">月の番号</span><span class="sxs-lookup"><span data-stu-id="4dbaf-316">Month number</span></span>                                                            | <span data-ttu-id="4dbaf-317">06</span><span class="sxs-lookup"><span data-stu-id="4dbaf-317">06</span></span>                       |
| `%n` | <span data-ttu-id="4dbaf-318">改行文字</span><span class="sxs-lookup"><span data-stu-id="4dbaf-318">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="4dbaf-319">AM または PM</span><span class="sxs-lookup"><span data-stu-id="4dbaf-319">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="4dbaf-320">24時間形式の時刻-秒なし</span><span class="sxs-lookup"><span data-stu-id="4dbaf-320">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="4dbaf-321">17:45</span><span class="sxs-lookup"><span data-stu-id="4dbaf-321">17:45</span></span>                    |
| `%r` | <span data-ttu-id="4dbaf-322">12時間形式の時間</span><span class="sxs-lookup"><span data-stu-id="4dbaf-322">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="4dbaf-323">09:15:36 AM</span><span class="sxs-lookup"><span data-stu-id="4dbaf-323">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="4dbaf-324">Seconds</span><span class="sxs-lookup"><span data-stu-id="4dbaf-324">Seconds</span></span>                                                                 | <span data-ttu-id="4dbaf-325">05</span><span class="sxs-lookup"><span data-stu-id="4dbaf-325">05</span></span>                       |
| `%s` | <span data-ttu-id="4dbaf-326">00:00:00 1970 年1月1日以降の経過秒数</span><span class="sxs-lookup"><span data-stu-id="4dbaf-326">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="4dbaf-327">1150451174</span><span class="sxs-lookup"><span data-stu-id="4dbaf-327">1150451174</span></span>               |
| `%t` | <span data-ttu-id="4dbaf-328">水平タブ文字</span><span class="sxs-lookup"><span data-stu-id="4dbaf-328">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="4dbaf-329">24 時間制の時刻</span><span class="sxs-lookup"><span data-stu-id="4dbaf-329">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="4dbaf-330">17:45:52</span><span class="sxs-lookup"><span data-stu-id="4dbaf-330">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="4dbaf-331">' W ' と同じ</span><span class="sxs-lookup"><span data-stu-id="4dbaf-331">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="4dbaf-332">曜日-数字</span><span class="sxs-lookup"><span data-stu-id="4dbaf-332">Day of the week - number</span></span>                                                | <span data-ttu-id="4dbaf-333">日曜日 = 0</span><span class="sxs-lookup"><span data-stu-id="4dbaf-333">Sunday = 0</span></span>               |
| `%V` | <span data-ttu-id="4dbaf-334">年の通算週</span><span class="sxs-lookup"><span data-stu-id="4dbaf-334">Week of the year</span></span>                                                        | <span data-ttu-id="4dbaf-335">01-53</span><span class="sxs-lookup"><span data-stu-id="4dbaf-335">01-53</span></span>                    |
| `%w` | <span data-ttu-id="4dbaf-336">' U ' と同じ</span><span class="sxs-lookup"><span data-stu-id="4dbaf-336">Same as 'u'</span></span>                                                             |                          |
| `%W` | <span data-ttu-id="4dbaf-337">年の通算週</span><span class="sxs-lookup"><span data-stu-id="4dbaf-337">Week of the year</span></span>                                                        | <span data-ttu-id="4dbaf-338">00-52</span><span class="sxs-lookup"><span data-stu-id="4dbaf-338">00-52</span></span>                    |
| `%X` | <span data-ttu-id="4dbaf-339">' T ' と同じ</span><span class="sxs-lookup"><span data-stu-id="4dbaf-339">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="4dbaf-340">ロケールの標準形式の日付</span><span class="sxs-lookup"><span data-stu-id="4dbaf-340">Date in standard format for locale</span></span>                                      | <span data-ttu-id="4dbaf-341">英語-米国の場合は06/27/19</span><span class="sxs-lookup"><span data-stu-id="4dbaf-341">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="4dbaf-342">4桁表記の年</span><span class="sxs-lookup"><span data-stu-id="4dbaf-342">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="4dbaf-343">2019</span><span class="sxs-lookup"><span data-stu-id="4dbaf-343">2019</span></span>                     |
| `%y` | <span data-ttu-id="4dbaf-344">2桁表記の年</span><span class="sxs-lookup"><span data-stu-id="4dbaf-344">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="4dbaf-345">19</span><span class="sxs-lookup"><span data-stu-id="4dbaf-345">19</span></span>                       |
| `%Z` | <span data-ttu-id="4dbaf-346">世界協定時刻 (UTC) からのタイムゾーンオフセット</span><span class="sxs-lookup"><span data-stu-id="4dbaf-346">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="4dbaf-347">-07</span><span class="sxs-lookup"><span data-stu-id="4dbaf-347">-07</span></span>                      |

## <span data-ttu-id="4dbaf-348">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4dbaf-348">RELATED LINKS</span></span>

[<span data-ttu-id="4dbaf-349">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="4dbaf-349">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="4dbaf-350">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="4dbaf-350">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="4dbaf-351">Get-Member</span><span class="sxs-lookup"><span data-stu-id="4dbaf-351">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="4dbaf-352">New-Item</span><span class="sxs-lookup"><span data-stu-id="4dbaf-352">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="4dbaf-353">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="4dbaf-353">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="4dbaf-354">Set-Date</span><span class="sxs-lookup"><span data-stu-id="4dbaf-354">Set-Date</span></span>](Set-Date.md)
