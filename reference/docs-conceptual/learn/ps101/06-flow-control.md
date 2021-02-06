---
title: フロー制御
description: PowerShell には、ループを作成し、決定を行い、スクリプト内のコードのフローを論理的に制御するメソッドが用意されています。
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 74595f8c6a5d4a49b05e72dd6bde1441fd2b464e
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "99601787"
---
# <a name="chapter-6---flow-control"></a><span data-ttu-id="81620-103">第 6 章 - フロー制御</span><span class="sxs-lookup"><span data-stu-id="81620-103">Chapter 6 - Flow control</span></span>

## <a name="scripting"></a><span data-ttu-id="81620-104">スクリプトの作成</span><span class="sxs-lookup"><span data-stu-id="81620-104">Scripting</span></span>

<span data-ttu-id="81620-105">PowerShell のワンライナーの記述からスクリプトの記述に移行するのは、実際よりもはるかに複雑に思えます。</span><span class="sxs-lookup"><span data-stu-id="81620-105">When you move from writing PowerShell one-liners to writing scripts, it sounds a lot more complicated than it really is.</span></span> <span data-ttu-id="81620-106">スクリプトは、`.PS1` ファイルとして保存されることを除けば、PowerShell コンソールで対話的に実行するのと同じまたは類似のコマンドにすぎません。</span><span class="sxs-lookup"><span data-stu-id="81620-106">A script is nothing more than the same or similar commands that you would run interactively in the PowerShell console, except they're saved as a `.PS1` file.</span></span> <span data-ttu-id="81620-107">`ForEach-Object` コマンドレットの代わりに `foreach` ループなど、使用できるスクリプト コンストラクトがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="81620-107">There are some scripting constructs that you may use such as a `foreach` loop instead of the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="81620-108">初心者にとってはこの違いがわかりにくく、`foreach` がスクリプト コンストラクトであると同時に `ForEach-Object` コマンドレットのエイリアスでもあることを考えた場合は特にそうです。</span><span class="sxs-lookup"><span data-stu-id="81620-108">To beginners, the differences can be confusing especially when you consider that `foreach` is both a scripting construct and an alias for the `ForEach-Object` cmdlet.</span></span>

## <a name="looping"></a><span data-ttu-id="81620-109">ループ</span><span class="sxs-lookup"><span data-stu-id="81620-109">Looping</span></span>

<span data-ttu-id="81620-110">PowerShell の優れた点の 1 つとして、1 つの項目に対して何かを実行する方法を理解できれば、何百もの項目に対しても同じタスクを簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="81620-110">One of the great things about PowerShell is, once you figure out how to do something for one item, it's almost as easy to do the same task for hundreds of items.</span></span> <span data-ttu-id="81620-111">PowerShell のさまざまな種類のループのいずれかを使用して項目をループ処理するだけです。</span><span class="sxs-lookup"><span data-stu-id="81620-111">Simply loop through the items using one of the many different types of loops in PowerShell.</span></span>

### <a name="foreach-object"></a><span data-ttu-id="81620-112">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="81620-112">ForEach-Object</span></span>

<span data-ttu-id="81620-113">`ForEach-Object` は、PowerShell ワンライナーなどを使用してパイプライン内の項目を反復処理するためのコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="81620-113">`ForEach-Object` is a cmdlet for iterating through items in a pipeline such as with PowerShell one-liners.</span></span> <span data-ttu-id="81620-114">`ForEach-Object` は、パイプラインを介してオブジェクトをストリーム配信します。</span><span class="sxs-lookup"><span data-stu-id="81620-114">`ForEach-Object` streams the objects through the pipeline.</span></span>

<span data-ttu-id="81620-115">`Get-Command` の **Module** パラメーターは、文字列である複数の値を受け取ることができますが、プロパティ名によるパイプライン入力経由またはパラメーター入力経由でのみ、値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="81620-115">Although the **Module** parameter of `Get-Command` accepts multiple values that are strings, it only accepts them via pipeline input by property name or via parameter input.</span></span> <span data-ttu-id="81620-116">次のシナリオでは、**Module** パラメーターで使用するために 2 つの文字列の値を `Get-Command` にパイプ処理する場合、`ForEach-Object` コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81620-116">In the following scenario, if I want to pipe two strings by value to `Get-Command` for use with the **Module** parameter, I would need to use the `ForEach-Object` cmdlet.</span></span>

```powershell
'ActiveDirectory', 'SQLServer' |
   ForEach-Object {Get-Command -Module $_} |
     Group-Object -Property ModuleName -NoElement |
         Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  147 ActiveDirectory
   82 SqlServer
```

<span data-ttu-id="81620-117">前の例では、`$_` が現在のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="81620-117">In the previous example, `$_` is the current object.</span></span> <span data-ttu-id="81620-118">PowerShell バージョン 3.0 以降では、`$_` の代わりに `$PSItem` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="81620-118">Beginning with PowerShell version 3.0, `$PSItem` can be used instead of `$_`.</span></span> <span data-ttu-id="81620-119">しかし、ほとんどの経験豊富な PowerShell ユーザーの間では、下位互換性があり入力が少ないことから、いまだに `$_` の方が好まれているようです。</span><span class="sxs-lookup"><span data-stu-id="81620-119">But I find that most experienced PowerShell users still prefer using `$_` since it's backward compatible and less to type.</span></span>

<span data-ttu-id="81620-120">`foreach` キーワードを使用する場合は、反復処理するすべての項目を事前にメモリに格納する必要があります。これは、処理する項目の数がわからない場合は扱いが難しくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81620-120">When using the `foreach` keyword, you must store all of the items in memory before iterating through them, which could be difficult if you don't know how many items you're working with.</span></span>

```powershell
$ComputerName = 'DC01', 'WEB01'
foreach ($Computer in $ComputerName) {
  Get-ADComputer -Identity $Computer
}
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

<span data-ttu-id="81620-121">多くの場合、`foreach` や `ForEach-Object` などのループが必要です。</span><span class="sxs-lookup"><span data-stu-id="81620-121">Many times a loop such as `foreach` or `ForEach-Object` is necessary.</span></span> <span data-ttu-id="81620-122">そうしないと、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81620-122">Otherwise you'll receive an error message.</span></span>

```powershell
Get-ADComputer -Identity 'DC01', 'WEB01'
```

```Output
Get-ADComputer : Cannot convert 'System.Object[]' to the type
'Microsoft.ActiveDirectory.Management.ADComputer' required by parameter 'Identity'.
Specified method is not supported.
At line:1 char:26
+ Get-ADComputer -Identity 'DC01', 'WEB01'
+                          ```````````````
    + CategoryInfo          : InvalidArgument: (:) [Get-ADComputer], ParameterBindingExc
   eption
    + FullyQualifiedErrorId : CannotConvertArgument,Microsoft.ActiveDirectory.Management
   .Commands.GetADComputer
```

<span data-ttu-id="81620-123">また、ループを完全に排除して同じ結果を得ることができる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="81620-123">Other times, you can get the same results while eliminating the loop altogether.</span></span> <span data-ttu-id="81620-124">オプションを理解するには、コマンドレットのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81620-124">Consult the cmdlet help to understand your options.</span></span>

```powershell
'DC01', 'WEB01' | Get-ADComputer
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

<span data-ttu-id="81620-125">前の例でわかるように、`Get-ADComputer` の **Identity** パラメーターは、入力がパラメーター入力を介して提供される場合は単一の値のみを受け取りますが、パイプライン入力を介して提供される場合は複数の項目を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="81620-125">As you can see in the previous examples, the **Identity** parameter for `Get-ADComputer` only accepts a single value when provided via parameter input, but it allows for multiple items when the input is provided via pipeline input.</span></span>

### <a name="for"></a><span data-ttu-id="81620-126">For</span><span class="sxs-lookup"><span data-stu-id="81620-126">For</span></span>

<span data-ttu-id="81620-127">`for` ループでは、指定された条件が true である間、処理が繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="81620-127">A `for` loop iterates while a specified condition is true.</span></span> <span data-ttu-id="81620-128">私は `for` ループを頻繁には使用しませんが、これには確かな用途があります。</span><span class="sxs-lookup"><span data-stu-id="81620-128">The `for` loop is not something that I use often, but it does have its uses.</span></span>

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
}
```

```Output
Sleeping for 1 seconds
Sleeping for 2 seconds
Sleeping for 3 seconds
Sleeping for 4 seconds
```

<span data-ttu-id="81620-129">前の例では、ループは 4 回 (つまり、番号 1 で始まり、カウンター変数 `$i` が 5 未満の間) 繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="81620-129">In the previous example, the loop will iterate four times by starting off with the number one and continue as long as the counter variable `$i` is less than 5.</span></span> <span data-ttu-id="81620-130">合計で 10 秒間スリープ状態になります。</span><span class="sxs-lookup"><span data-stu-id="81620-130">It will sleep for a total of 10 seconds.</span></span>

### <a name="do"></a><span data-ttu-id="81620-131">次のことを行います</span><span class="sxs-lookup"><span data-stu-id="81620-131">Do</span></span>

<span data-ttu-id="81620-132">PowerShell には、2 つの異なる `do` ループがあります。</span><span class="sxs-lookup"><span data-stu-id="81620-132">There are two different `do` loops in PowerShell.</span></span> <span data-ttu-id="81620-133">`Do Until` は、指定された条件が false の間実行されます。</span><span class="sxs-lookup"><span data-stu-id="81620-133">`Do Until` runs while the specified condition is false.</span></span>

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  }
  elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
until ($guess -eq $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
```

<span data-ttu-id="81620-134">前の例は、推測した数字が `Get-Random` コマンドレットによって生成された数字に一致するまで続く数字ゲームです。</span><span class="sxs-lookup"><span data-stu-id="81620-134">The previous example is a numbers game that continues until the value you guess equals the same number that the `Get-Random` cmdlet generated.</span></span>

<span data-ttu-id="81620-135">`Do While` は、その逆に作用します。</span><span class="sxs-lookup"><span data-stu-id="81620-135">`Do While` is just the opposite.</span></span> <span data-ttu-id="81620-136">指定された条件が true と評価される限り、実行されます。</span><span class="sxs-lookup"><span data-stu-id="81620-136">It runs as long as the specified condition evaluates to true.</span></span>

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  } elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
while ($guess -ne $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
Too low!
What's your guess?: 4
```

<span data-ttu-id="81620-137">テスト条件を逆の "等しくない" にすることにより、`Do While` ループでも同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="81620-137">The same results are achieved with a `Do While` loop by reversing the test condition to not equals.</span></span>

<span data-ttu-id="81620-138">条件はループの最後で評価されるため、`Do` ループは少なくとも 1 回は必ず実行されます。</span><span class="sxs-lookup"><span data-stu-id="81620-138">`Do` loops always run at least once because the condition is evaluated at the end of the loop.</span></span>

### <a name="while"></a><span data-ttu-id="81620-139">While</span><span class="sxs-lookup"><span data-stu-id="81620-139">While</span></span>

<span data-ttu-id="81620-140">`Do While` ループと同様に、`While` ループは、指定された条件が true である限り実行されます。</span><span class="sxs-lookup"><span data-stu-id="81620-140">Similar to the `Do While` loop, a `While` loop runs as long as the specified condition is true.</span></span> <span data-ttu-id="81620-141">ただし、`While` ループではコードが実行される前にループの先頭で条件が評価される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="81620-141">The difference however, is that a `While` loop evaluates the condition at the top of the loop before any code is run.</span></span> <span data-ttu-id="81620-142">したがって、条件が false と評価された場合は実行されません。</span><span class="sxs-lookup"><span data-stu-id="81620-142">So it doesn't run if the condition evaluates to false.</span></span>

```powershell
$date = Get-Date -Date 'November 22'
while ($date.DayOfWeek -ne 'Thursday') {
  $date = $date.AddDays(1)
}
Write-Output $date
```

```Output
Thursday, November 23, 2017 12:00:00 AM
```

<span data-ttu-id="81620-143">前の例では、米国の感謝祭の日を計算しています。</span><span class="sxs-lookup"><span data-stu-id="81620-143">The previous example calculates what day Thanksgiving Day is on in the United States.</span></span> <span data-ttu-id="81620-144">この日は常に 11 月の第 4 木曜日に該当します。</span><span class="sxs-lookup"><span data-stu-id="81620-144">It's always on the fourth Thursday of November.</span></span> <span data-ttu-id="81620-145">したがって、このループでは、11 月 22 日を開始日として、曜日が木曜日と等しくなければ 1 日ずつ追加されていきます。</span><span class="sxs-lookup"><span data-stu-id="81620-145">So the loop starts with the 22nd day of November and adds a day while the day of the week isn't equal to Thursday.</span></span> <span data-ttu-id="81620-146">22 日が木曜日の場合、ループはまったく実行されません。</span><span class="sxs-lookup"><span data-stu-id="81620-146">If the 22nd is a Thursday, the loop doesn't run at all.</span></span>

## <a name="break-continue-and-return"></a><span data-ttu-id="81620-147">Break、Continue、および Return</span><span class="sxs-lookup"><span data-stu-id="81620-147">Break, Continue, and Return</span></span>

<span data-ttu-id="81620-148">`Break` は、ループから抜け出すように設計されています。</span><span class="sxs-lookup"><span data-stu-id="81620-148">`Break` is designed to break out of a loop.</span></span> <span data-ttu-id="81620-149">また、`switch` ステートメントでも一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="81620-149">It's also commonly used with the `switch` statement.</span></span>

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
  break
}
```

```Output
Sleeping for 1 seconds
```

<span data-ttu-id="81620-150">前の例に示されている `break` ステートメントにより、ループは最初の反復で終了します。</span><span class="sxs-lookup"><span data-stu-id="81620-150">The `break` statement shown in the previous example causes the loop to exit on the first iteration.</span></span>

<span data-ttu-id="81620-151">Continue は、ループの次の反復にスキップするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="81620-151">Continue is designed to skip to the next iteration of a loop.</span></span>

```powershell
while ($i -lt 5) {
  $i += 1
  if ($i -eq 3) {
    continue
  }
  Write-Output $i
}
```

```Output
1
2
4
5
```

<span data-ttu-id="81620-152">前の例では、番号 1、2、4、および 5 が出力されます。</span><span class="sxs-lookup"><span data-stu-id="81620-152">The previous example will output the numbers 1, 2, 4, and 5.</span></span> <span data-ttu-id="81620-153">番号 3 がスキップされ、ループの次の反復に続きます。</span><span class="sxs-lookup"><span data-stu-id="81620-153">It skips number 3 and continues with the next iteration of the loop.</span></span> <span data-ttu-id="81620-154">`break` と同様に、`continue` は現在の反復のみを除いてループを中断します。</span><span class="sxs-lookup"><span data-stu-id="81620-154">Similar to `break`, `continue` breaks out of the loop except only for the current iteration.</span></span> <span data-ttu-id="81620-155">実行は、ループを中断して停止するのではなく、次の反復に続きます。</span><span class="sxs-lookup"><span data-stu-id="81620-155">Execution continues with the next iteration instead of breaking out of the loop and stopping.</span></span>

<span data-ttu-id="81620-156">Return は、既存のスコープを終了するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="81620-156">Return is designed to exit out of the existing scope.</span></span>

```powershell
$number = 1..10
foreach ($n in $number) {
  if ($n -ge 4) {
    Return $n
  }
}
```

```Output
4
```

<span data-ttu-id="81620-157">前の例においいて、return は最初の結果を出力した後でループを終了することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="81620-157">Notice that in the previous example, return outputs the first result and then exists out of the loop.</span></span> <span data-ttu-id="81620-158">私のブログ記事の 1 つで結果のステートメントを詳しく説明しています: ["PowerShell の return キーワード"][]。</span><span class="sxs-lookup"><span data-stu-id="81620-158">A more thorough explanation of the result statement can be found in one of my blog articles: ["The PowerShell return keyword"][].</span></span>

## <a name="summary"></a><span data-ttu-id="81620-159">まとめ</span><span class="sxs-lookup"><span data-stu-id="81620-159">Summary</span></span>

<span data-ttu-id="81620-160">この章では、PowerShell にあるさまざまな種類のループについて学習しました。</span><span class="sxs-lookup"><span data-stu-id="81620-160">In this chapter, you've learned about the different types of loops that exist in PowerShell.</span></span>

## <a name="review"></a><span data-ttu-id="81620-161">確認</span><span class="sxs-lookup"><span data-stu-id="81620-161">Review</span></span>

1. <span data-ttu-id="81620-162">`ForEach-Object` コマンドレットと foreach スクリプト コンストラクトの違いは何ですか?</span><span class="sxs-lookup"><span data-stu-id="81620-162">What is the difference in the `ForEach-Object` cmdlet and the foreach scripting construct?</span></span>
1. <span data-ttu-id="81620-163">Do While または Do Until ループの代わりに While ループを使用する主な利点は何ですか。</span><span class="sxs-lookup"><span data-stu-id="81620-163">What is the primary advantage of using a While loop instead of a Do While or Do Until loop.</span></span>
1. <span data-ttu-id="81620-164">break ステートメントと continue ステートメントはどのように異なりますか?</span><span class="sxs-lookup"><span data-stu-id="81620-164">How do the break and continue statements differ?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="81620-165">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="81620-165">Recommended Reading</span></span>

- <span data-ttu-id="81620-166">[ForEach-Object][]</span><span class="sxs-lookup"><span data-stu-id="81620-166">[ForEach-Object][]</span></span>
- <span data-ttu-id="81620-167">[about_ForEach][]</span><span class="sxs-lookup"><span data-stu-id="81620-167">[about_ForEach][]</span></span>
- <span data-ttu-id="81620-168">[about_For][]</span><span class="sxs-lookup"><span data-stu-id="81620-168">[about_For][]</span></span>
- <span data-ttu-id="81620-169">[about_Do][]</span><span class="sxs-lookup"><span data-stu-id="81620-169">[about_Do][]</span></span>
- <span data-ttu-id="81620-170">[about_While][]</span><span class="sxs-lookup"><span data-stu-id="81620-170">[about_While][]</span></span>
- <span data-ttu-id="81620-171">[about_Break][]</span><span class="sxs-lookup"><span data-stu-id="81620-171">[about_Break][]</span></span>
- <span data-ttu-id="81620-172">[about_Continue][]</span><span class="sxs-lookup"><span data-stu-id="81620-172">[about_Continue][]</span></span>
- <span data-ttu-id="81620-173">[about_Return][]</span><span class="sxs-lookup"><span data-stu-id="81620-173">[about_Return][]</span></span>

<!-- link references -->
[ForEach-Object]: /powershell/module/microsoft.powershell.core/foreach-object
[about_ForEach]: /powershell/module/microsoft.powershell.core/about/about_foreach
[about_For]: /powershell/module/microsoft.powershell.core/about/about_for
[about_Do]: /powershell/module/microsoft.powershell.core/about/about_do
[about_While]: /powershell/module/microsoft.powershell.core/about/about_while
[about_Break]: /powershell/module/microsoft.powershell.core/about/about_break
[about_Continue]: /powershell/module/microsoft.powershell.core/about/about_continue
[about_Return]: /powershell/module/microsoft.powershell.core/about/about_return
["PowerShell の return キーワード"]: https://mikefrobbins.com/2015/07/23/the-powershell-return-keyword/
["The PowerShell return keyword"]: https://mikefrobbins.com/2015/07/23/the-powershell-return-keyword/
