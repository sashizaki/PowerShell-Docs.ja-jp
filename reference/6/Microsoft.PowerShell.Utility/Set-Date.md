---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-date?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Date
ms.openlocfilehash: 63742cf1cc7431668a769bec5d4798b23db8c2ae
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94386902"
---
# <span data-ttu-id="f4aeb-103">Set-Date</span><span class="sxs-lookup"><span data-stu-id="f4aeb-103">Set-Date</span></span>

## <span data-ttu-id="f4aeb-104">概要</span><span class="sxs-lookup"><span data-stu-id="f4aeb-104">SYNOPSIS</span></span>
<span data-ttu-id="f4aeb-105">指定する時刻にコンピューターのシステム時刻を変更します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-105">Changes the system time on the computer to a time that you specify.</span></span>

## <span data-ttu-id="f4aeb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4aeb-106">SYNTAX</span></span>

### <span data-ttu-id="f4aeb-107">日付 (既定値)</span><span class="sxs-lookup"><span data-stu-id="f4aeb-107">Date (Default)</span></span>

```
Set-Date [-Date] <DateTime> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f4aeb-108">Adjust</span><span class="sxs-lookup"><span data-stu-id="f4aeb-108">Adjust</span></span>

```
Set-Date [-Adjust] <TimeSpan> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f4aeb-109">Description</span><span class="sxs-lookup"><span data-stu-id="f4aeb-109">DESCRIPTION</span></span>

<span data-ttu-id="f4aeb-110">この `Set-Date` コマンドレットは、コンピューターのシステム日付と時刻を、指定した日付と時刻に変更します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-110">The `Set-Date` cmdlet changes the system date and time on the computer to a date and time that you specify.</span></span>
<span data-ttu-id="f4aeb-111">文字列を入力するか、 **DateTime** または **TimeSpan** オブジェクトをに渡して、新しい日付や時刻を指定でき `Set-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-111">You can specify a new date and/or time by typing a string or by passing a **DateTime** or **TimeSpan** object to `Set-Date`.</span></span> <span data-ttu-id="f4aeb-112">新しい日付または時刻を指定するには、 **date** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-112">To specify a new date or time, use the **Date** parameter.</span></span>
<span data-ttu-id="f4aeb-113">変更間隔を指定するには、[ **調整** ] パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-113">To specify a change interval, use the **Adjust** parameter.</span></span>

## <span data-ttu-id="f4aeb-114">例</span><span class="sxs-lookup"><span data-stu-id="f4aeb-114">EXAMPLES</span></span>

### <span data-ttu-id="f4aeb-115">例 1: システム日付に3日を追加する</span><span class="sxs-lookup"><span data-stu-id="f4aeb-115">Example 1: Add three days to the system date</span></span>

<span data-ttu-id="f4aeb-116">このコマンドは、現在のシステム日付に 3 日加算します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-116">This command adds three days to the current system date.</span></span>
<span data-ttu-id="f4aeb-117">時刻には影響しません。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-117">It does not affect the time.</span></span>
<span data-ttu-id="f4aeb-118">このコマンド **は、date パラメーターを** 使用して日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-118">The command uses the **Date** parameter to specify the date.</span></span>

<span data-ttu-id="f4aeb-119">この `Get-Date` コマンドレットは、現在の日付を **DateTime** オブジェクトとして返します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-119">The `Get-Date` cmdlet returns the current date as a **DateTime** object.</span></span> <span data-ttu-id="f4aeb-120">**Datetime** オブジェクトの **AddDays** メソッドは、指定された日数 (3) を現在の **DateTime** オブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-120">The **DateTime** object's **AddDays** method adds a specified number of days (3) to the current **DateTime** object.</span></span>

```powershell
Set-Date -Date (Get-Date).AddDays(3)
```

### <span data-ttu-id="f4aeb-121">例 2: システムクロックを10分前に設定する</span><span class="sxs-lookup"><span data-stu-id="f4aeb-121">Example 2: Set the system clock back 10 minutes</span></span>

<span data-ttu-id="f4aeb-122">この例では、現在のシステム時刻を10分後に設定します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-122">This example sets the current system time back by 10 minutes.</span></span>

<span data-ttu-id="f4aeb-123">**調整** パラメーターを使用すると、ロケールの標準時形式で、変更の間隔 (10 分を差し引いた値) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-123">The **Adjust** parameter allows you to specify an interval of change (minus ten minutes) in the standard time format for the locale.</span></span>

<span data-ttu-id="f4aeb-124">**Displayhint** パラメーターは、時刻のみを表示するように PowerShell に指示しますが、を返す **DateTime** オブジェクトには影響しません `Set-Date` 。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-124">The **DisplayHint** parameter tells PowerShell to display only the time, but it does not affect the **DateTime** object that `Set-Date` returns.</span></span>

```powershell
Set-Date -Adjust -0:10:0 -DisplayHint Time
```

### <span data-ttu-id="f4aeb-125">例 3: 日付と時刻を変数値に設定する</span><span class="sxs-lookup"><span data-stu-id="f4aeb-125">Example 3: Set the date and time to a variable value</span></span>

<span data-ttu-id="f4aeb-126">これらのコマンドは、ローカルコンピューターのシステム日付と時刻を、変数に保存されている日付と時刻に変更し `$T` ます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-126">These commands change the system date and time on local computer to the date and time saved in the variable `$T`.</span></span> <span data-ttu-id="f4aeb-127">最初のコマンドは、日付を取得してに格納し `$T` ます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-127">The first command gets the date and stores it in `$T`.</span></span>

<span data-ttu-id="f4aeb-128">2番目のコマンドは、 **Date** パラメーターを使用して、 **DateTime** オブジェクトを `$T` `Set-Date` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-128">The second command uses the **Date** parameter to pass the **DateTime** object in `$T` to the `Set-Date` cmdlet.</span></span>

```powershell
$T = Get-Date
Set-Date -Date $T
```

### <span data-ttu-id="f4aeb-129">例 4: システムクロックに90分を加算する</span><span class="sxs-lookup"><span data-stu-id="f4aeb-129">Example 4: Add 90 minutes to the system clock</span></span>

<span data-ttu-id="f4aeb-130">これらのコマンドは、ローカル コンピューターのシステム時刻を 90 分進めます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-130">These commands advance the system time on the local computer by 90 minutes.</span></span>

<span data-ttu-id="f4aeb-131">最初のコマンドは、コマンドレットを使用して、 `New-TimeSpan` 90 分の間隔で **TimeSpan** オブジェクトを作成し、変数に保存し `$90mins` ます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-131">The first command uses the `New-TimeSpan` cmdlet to create a **TimeSpan** object with a 90-minute interval, and saves it in the `$90mins` variable.</span></span>

<span data-ttu-id="f4aeb-132">2番目のコマンドは、の **調整** パラメーターを使用し `Set-Date` て、変数の **TimeSpan** オブジェクトの値で日付を調整し `$90mins` ます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-132">The second command uses the **Adjust** parameter of `Set-Date` to adjust the date by the value of the **TimeSpan** object in the `$90mins` variable.</span></span>

```powershell
$90mins = New-TimeSpan -Minutes 90
Set-Date -Adjust $90mins
```

## <span data-ttu-id="f4aeb-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4aeb-133">PARAMETERS</span></span>

### <span data-ttu-id="f4aeb-134">-調整</span><span class="sxs-lookup"><span data-stu-id="f4aeb-134">-Adjust</span></span>

<span data-ttu-id="f4aeb-135">このコマンドレットが現在の日付と時刻に対して加算または減算する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-135">Specifies the value for which this cmdlet adds or subtracts from the current date and time.</span></span>
<span data-ttu-id="f4aeb-136">では、ロケールの標準の日付と時刻の形式で調整を入力するか、または **調整** パラメーターを使用して、 **TimeSpan** オブジェクトをからに渡すことができ `New-TimeSpan` `Set-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-136">can type an adjustment in standard date and time format for your locale or use the **Adjust** parameter to pass a **TimeSpan** object from `New-TimeSpan` to `Set-Date`.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Adjust
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f4aeb-137">-日付</span><span class="sxs-lookup"><span data-stu-id="f4aeb-137">-Date</span></span>

<span data-ttu-id="f4aeb-138">指定した値に日付と時刻を変更します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-138">Changes the date and time to the specified values.</span></span>
<span data-ttu-id="f4aeb-139">新しい日付をロケールに対応する短い日付形式で、時刻をロケールに対応する標準の時刻形式で入力できます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-139">You can type a new date in the short date format and a time in the standard time format for your locale.</span></span> <span data-ttu-id="f4aeb-140">または、 **DateTime** オブジェクトをから渡すことができ `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-140">Or, you can pass a **DateTime** object from `Get-Date`.</span></span>

<span data-ttu-id="f4aeb-141">日付を指定したのに時間を指定しなかった場合は、 `Set-Date` 指定した日付の午前0時に時刻が変更されます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-141">If you specify a date, but not a time, `Set-Date` changes the time to midnight on the specified date.</span></span> <span data-ttu-id="f4aeb-142">時刻だけを指定すると、日付は変わりません。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-142">If you specify only a time, it does not change the date.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f4aeb-143">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="f4aeb-143">-DisplayHint</span></span>

<span data-ttu-id="f4aeb-144">日付と時刻の要素を表示するかどうかを指定します。このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-144">Specifies which elements of the date and time are displayed.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f4aeb-145">**日付** -日付のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-145">**Date** - displays only the date.</span></span>
- <span data-ttu-id="f4aeb-146">**時間** -時刻のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-146">**Time** - displays only the time.</span></span>
- <span data-ttu-id="f4aeb-147">**DateTime** -日付と時刻を表示します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-147">**DateTime** - displays the date and time.</span></span>

<span data-ttu-id="f4aeb-148">このパラメーターは、表示のみに影響します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-148">This parameter affects only the display.</span></span>
<span data-ttu-id="f4aeb-149">を取得する **DateTime** オブジェクトには影響しません `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-149">It does not affect the **DateTime** object that `Get-Date` retrieves.</span></span>

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

### <span data-ttu-id="f4aeb-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f4aeb-150">-Confirm</span></span>

<span data-ttu-id="f4aeb-151">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-151">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4aeb-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f4aeb-152">-WhatIf</span></span>

<span data-ttu-id="f4aeb-153">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f4aeb-154">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-154">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4aeb-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f4aeb-155">CommonParameters</span></span>

<span data-ttu-id="f4aeb-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f4aeb-157">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f4aeb-158">入力</span><span class="sxs-lookup"><span data-stu-id="f4aeb-158">INPUTS</span></span>

### <span data-ttu-id="f4aeb-159">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="f4aeb-159">System.DateTime</span></span>

<span data-ttu-id="f4aeb-160">パイプを使用して日付をにパイプすることができ `Set-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-160">You can pipe a date to `Set-Date`.</span></span>

## <span data-ttu-id="f4aeb-161">出力</span><span class="sxs-lookup"><span data-stu-id="f4aeb-161">OUTPUTS</span></span>

### <span data-ttu-id="f4aeb-162">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="f4aeb-162">System.DateTime</span></span>

<span data-ttu-id="f4aeb-163">`Set-Date` 設定された日付を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-163">`Set-Date` returns an object that represents the date that it set.</span></span>

## <span data-ttu-id="f4aeb-164">注</span><span class="sxs-lookup"><span data-stu-id="f4aeb-164">NOTES</span></span>

- <span data-ttu-id="f4aeb-165">コンピューターの日付と時刻を変更する場合は、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-165">Use this cmdlet cautiously when changing the date and time on the computer.</span></span> <span data-ttu-id="f4aeb-166">変更によって、コンピューターが、日付または時刻に基づいてトリガーされるシステム全体のイベントと更新を受信できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-166">The change might prevent the computer from receiving system-wide events and updates that are triggered by a date or time.</span></span> <span data-ttu-id="f4aeb-167">エラーを回避するには、 **WhatIf** パラメーターと **Confirm** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-167">Use the **WhatIf** and **Confirm** parameters to avoid errors.</span></span>
- <span data-ttu-id="f4aeb-168">**DateTime** **TimeSpan** `Set-Date` **AddDays** 、 **addmonths** 、 **Fromfiletime** など、で使用される DateTime および TimeSpan オブジェクトと共に、標準の .net メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-168">You can use standard .NET methods with the **DateTime** and **TimeSpan** objects used with `Set-Date`, such as **AddDays** , **AddMonths** , and **FromFileTime**.</span></span> <span data-ttu-id="f4aeb-169">詳細については、「 [DateTime メソッド](/dotnet/api/system.datetime) 」と「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-169">For more information, see [DateTime Methods](/dotnet/api/system.datetime) and</span></span>

  <span data-ttu-id="f4aeb-170">.NET SDK の[TimeSpan メソッド](/dotnet/api/system.timespan)。</span><span class="sxs-lookup"><span data-stu-id="f4aeb-170">[TimeSpan Methods](/dotnet/api/system.timespan) in the .NET SDK.</span></span>

## <span data-ttu-id="f4aeb-171">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f4aeb-171">RELATED LINKS</span></span>

[<span data-ttu-id="f4aeb-172">取得-日付</span><span class="sxs-lookup"><span data-stu-id="f4aeb-172">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="f4aeb-173">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="f4aeb-173">New-TimeSpan</span></span>](New-TimeSpan.md)
