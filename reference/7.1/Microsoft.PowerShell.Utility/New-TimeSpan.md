---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 135b4441490bbee7d8c8e0088080f97a7128af53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217379"
---
# <span data-ttu-id="2e0c2-103">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="2e0c2-103">New-TimeSpan</span></span>

## <span data-ttu-id="2e0c2-104">概要</span><span class="sxs-lookup"><span data-stu-id="2e0c2-104">SYNOPSIS</span></span>
<span data-ttu-id="2e0c2-105">TimeSpan オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-105">Creates a TimeSpan object.</span></span>

## <span data-ttu-id="2e0c2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e0c2-106">SYNTAX</span></span>

### <span data-ttu-id="2e0c2-107">日付 (既定値)</span><span class="sxs-lookup"><span data-stu-id="2e0c2-107">Date (Default)</span></span>

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="2e0c2-108">時刻</span><span class="sxs-lookup"><span data-stu-id="2e0c2-108">Time</span></span>

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="2e0c2-109">Description</span><span class="sxs-lookup"><span data-stu-id="2e0c2-109">DESCRIPTION</span></span>

<span data-ttu-id="2e0c2-110">コマンドレットでは、 `New-TimeSpan` 時間間隔を表す **TimeSpan** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-110">The `New-TimeSpan` cmdlet creates a **TimeSpan** object that represents a time interval.</span></span>
<span data-ttu-id="2e0c2-111">**TimeSpan** オブジェクトを使用して、 **DateTime** オブジェクトの時間を加算または減算できます。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-111">You can use a **TimeSpan** object to add or subtract time from **DateTime** objects.</span></span>

<span data-ttu-id="2e0c2-112">パラメーターを指定しない場合、コマンドは、 `New-TimeSpan` 時間間隔0を表す **TimeSpan** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-112">Without parameters, a `New-TimeSpan` command returns a **TimeSpan** object that represents a time interval of zero.</span></span>

## <span data-ttu-id="2e0c2-113">例</span><span class="sxs-lookup"><span data-stu-id="2e0c2-113">EXAMPLES</span></span>

### <span data-ttu-id="2e0c2-114">例 1: 指定された期間の TimeSpan オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="2e0c2-114">Example 1: Create a TimeSpan object for a specified duration</span></span>

<span data-ttu-id="2e0c2-115">このコマンドは、期間が1時間と25分の **TimeSpan** オブジェクトを作成し、という名前の変数に格納し `$TimeSpan` ます。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-115">This command creates a **TimeSpan** object with a duration of 1 hour and 25 minutes and stores it in a variable named `$TimeSpan`.</span></span> <span data-ttu-id="2e0c2-116">これにより、 **TimeSpan** オブジェクトの表現が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-116">It displays a representation of the **TimeSpan** object.</span></span>

```powershell
$TimeSpan = New-TimeSpan -Hours 1 -Minutes 25
$TimeSpan
```

```Output
Days              : 0
Hours             : 1
Minutes           : 25
Seconds           : 0
Milliseconds      : 0
Ticks             : 51000000000
TotalDays         : 0.0590277777777778
TotalHours        : 1.41666666666667
TotalMinutes      : 85
TotalSeconds      : 5100
TotalMilliseconds : 5100000
```

### <span data-ttu-id="2e0c2-117">例 2: 時間間隔の TimeSpan オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="2e0c2-117">Example 2: Create a TimeSpan object for a time interval</span></span>

<span data-ttu-id="2e0c2-118">この例では、コマンドが実行されてから2010年1月1日までの間隔を表す新しい **TimeSpan** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-118">This example creates a new **TimeSpan** object that represents the interval between the time that the command is run and January 1, 2010.</span></span>

<span data-ttu-id="2e0c2-119">**Start** パラメーターの既定値は現在の日付と時刻であるため、このコマンドには **start** パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-119">This command does not require the **Start** parameter, because the default value of the **Start** parameter is the current date and time.</span></span>

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### <span data-ttu-id="2e0c2-120">例 3: 現在の日付から90日目を取得する</span><span class="sxs-lookup"><span data-stu-id="2e0c2-120">Example 3: Get the date 90 days from the current date</span></span>

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

<span data-ttu-id="2e0c2-121">これらのコマンドは、現在の日付から 90 日後の日付を返します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-121">These commands return the date that is 90 days after the current date.</span></span>

### <span data-ttu-id="2e0c2-122">例 4: ファイルが更新されてからの TimeSpan を検出する</span><span class="sxs-lookup"><span data-stu-id="2e0c2-122">Example 4: Discover the TimeSpan since a file was updated</span></span>

<span data-ttu-id="2e0c2-123">このコマンドは、 [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) ヘルプファイルが最後に更新されてから経過した時間を示します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-123">This command tells you how long it has been since the [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) help file was last updated.</span></span>
<span data-ttu-id="2e0c2-124">このコマンド形式は、任意のファイル、または **Lastwritetime** プロパティを持つその他のオブジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-124">You can use this command format on any file, or any other object that has a **LastWriteTime** property.</span></span>

<span data-ttu-id="2e0c2-125">の **Start** パラメーター `New-TimeSpan` には **lastwritetime** のエイリアスがあるため、このコマンドは機能します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-125">This command works because the **Start** parameter of `New-TimeSpan` has an alias of **LastWriteTime**.</span></span> <span data-ttu-id="2e0c2-126">**Lastwritetime** プロパティを持つオブジェクトをパイプすると `New-TimeSpan` 、PowerShell では、 **lastwritetime** プロパティの値が **Start** パラメーターの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-126">When you pipe an object that has a **LastWriteTime** property to `New-TimeSpan`, PowerShell uses the value of the **LastWriteTime** property as the value of the **Start** parameter.</span></span>

```powershell
Get-ChildItem $PSHOME\en-us\about_remote.help.txt | New-TimeSpan
```

```Output
Days              : 321
Hours             : 21
Minutes           : 59
Seconds           : 22
Milliseconds      : 312
Ticks             : 278135623127728
TotalDays         : 321.916230471907
TotalHours        : 7725.98953132578
TotalMinutes      : 463559.371879547
TotalSeconds      : 27813562.3127728
TotalMilliseconds : 27813562312.7728
```

## <span data-ttu-id="2e0c2-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e0c2-127">PARAMETERS</span></span>

### <span data-ttu-id="2e0c2-128">-Days</span><span class="sxs-lookup"><span data-stu-id="2e0c2-128">-Days</span></span>

<span data-ttu-id="2e0c2-129">期間の日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-129">Specifies the days in the time span.</span></span>
<span data-ttu-id="2e0c2-130">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-130">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e0c2-131">-End</span><span class="sxs-lookup"><span data-stu-id="2e0c2-131">-End</span></span>

<span data-ttu-id="2e0c2-132">期間の終了を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-132">Specifies the end of a time span.</span></span>
<span data-ttu-id="2e0c2-133">既定値は、現在の日付と時刻です。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-133">The default value is the current date and time.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: False
Position: 1
Default value: Current date and time
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2e0c2-134">-時間</span><span class="sxs-lookup"><span data-stu-id="2e0c2-134">-Hours</span></span>

<span data-ttu-id="2e0c2-135">期間の時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-135">Specifies the hours in the time span.</span></span>
<span data-ttu-id="2e0c2-136">既定値はゼロです。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-136">The default value is zero.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e0c2-137">-分</span><span class="sxs-lookup"><span data-stu-id="2e0c2-137">-Minutes</span></span>

<span data-ttu-id="2e0c2-138">時間間隔を分単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-138">Specifies the minutes in the time span.</span></span>
<span data-ttu-id="2e0c2-139">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-139">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e0c2-140">-秒</span><span class="sxs-lookup"><span data-stu-id="2e0c2-140">-Seconds</span></span>

<span data-ttu-id="2e0c2-141">時間間隔の長さを秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-141">Specifies the length of the time span in seconds.</span></span>
<span data-ttu-id="2e0c2-142">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-142">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e0c2-143">-開始</span><span class="sxs-lookup"><span data-stu-id="2e0c2-143">-Start</span></span>

<span data-ttu-id="2e0c2-144">期間の開始を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-144">Specifies the start of a time span.</span></span>
<span data-ttu-id="2e0c2-145">"3/15/09" などの日付と時刻を表す文字列、または、コマンドからの1つなどの **DateTime** オブジェクトを入力し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-145">Enter a string that represents the date and time, such as "3/15/09" or a **DateTime** object, such as one from a `Get-Date` command.</span></span> <span data-ttu-id="2e0c2-146">既定値は、現在の日付と時刻です。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-146">The default value is the current date and time.</span></span>

<span data-ttu-id="2e0c2-147">**Start** またはそのエイリアスである **lastwritetime** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-147">You can use **Start** or its alias, **LastWriteTime**.</span></span>
<span data-ttu-id="2e0c2-148">**Lastwritetime** エイリアスを使用すると、ファイルシステム内のファイルなど、 **lastwritetime** プロパティを持つオブジェクトを `[System.Io.FileIO]` の **Start** パラメーターにパイプすることができ `New-TimeSpan` ます。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-148">The **LastWriteTime** alias lets you pipe objects that have a **LastWriteTime** property, such as files in the file system `[System.Io.FileIO]`, to the **Start** parameter of `New-TimeSpan`.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases: LastWriteTime

Required: False
Position: 0
Default value: Current date and time
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2e0c2-149">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e0c2-149">CommonParameters</span></span>

<span data-ttu-id="2e0c2-150">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e0c2-151">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2e0c2-152">入力</span><span class="sxs-lookup"><span data-stu-id="2e0c2-152">INPUTS</span></span>

### <span data-ttu-id="2e0c2-153">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="2e0c2-153">System.DateTime</span></span>

<span data-ttu-id="2e0c2-154">パイプを使用して、その開始時刻を表す **DateTime** オブジェクトをにパイプすることができ `New-TimeSpan` ます。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-154">You can pipe a **DateTime** object that represents that start time to `New-TimeSpan`.</span></span>

## <span data-ttu-id="2e0c2-155">出力</span><span class="sxs-lookup"><span data-stu-id="2e0c2-155">OUTPUTS</span></span>

### <span data-ttu-id="2e0c2-156">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="2e0c2-156">System.TimeSpan</span></span>

<span data-ttu-id="2e0c2-157">`New-TimeSpan` 時間間隔を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2e0c2-157">`New-TimeSpan` returns an object that represents the time span.</span></span>

## <span data-ttu-id="2e0c2-158">注</span><span class="sxs-lookup"><span data-stu-id="2e0c2-158">NOTES</span></span>

## <span data-ttu-id="2e0c2-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2e0c2-159">RELATED LINKS</span></span>

[<span data-ttu-id="2e0c2-160">Get-Date</span><span class="sxs-lookup"><span data-stu-id="2e0c2-160">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="2e0c2-161">Set-Date</span><span class="sxs-lookup"><span data-stu-id="2e0c2-161">Set-Date</span></span>](Set-Date.md)

