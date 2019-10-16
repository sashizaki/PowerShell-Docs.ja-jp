---
title: PowerShell スクリプトモジュールを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed7645ea-5e52-4a45-81a7-aa3c2d605cde
caps.latest.revision: 16
ms.openlocfilehash: b2a929a1724f77f0516ad24cfd90f6d6053ed19e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360691"
---
# <a name="how-to-write-a-powershell-script-module"></a><span data-ttu-id="db6ce-102">PowerShell スクリプト モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="db6ce-102">How to Write a PowerShell Script Module</span></span>

<span data-ttu-id="db6ce-103">スクリプトモジュールは、基本的には hbase-runner.psm1 拡張子で保存された有効な PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="db6ce-103">A script module is essentially any valid PowerShell script saved in a .psm1 extension.</span></span> <span data-ttu-id="db6ce-104">この拡張機能により、PowerShell エンジンは、ファイルで多数の規則とコマンドレットを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="db6ce-104">This extension allows the PowerShell engine to use a number of rules and cmdlets on your file.</span></span> <span data-ttu-id="db6ce-105">これらの機能のほとんどは、他のシステムにコードをインストールしたり、スコープを管理したりできるようにするために用意されています。</span><span class="sxs-lookup"><span data-stu-id="db6ce-105">Most of these capabilities are there to help you install your code on other systems, as well as manage scoping.</span></span> <span data-ttu-id="db6ce-106">モジュールマニフェストファイルを使用することもできます。これにより、さらに複雑なインストールとソリューションを記述できます。</span><span class="sxs-lookup"><span data-stu-id="db6ce-106">You can also use a module manifest file, which can describe even more complex installations and solutions.</span></span>

## <a name="writing-a-powershell-script-module"></a><span data-ttu-id="db6ce-107">PowerShell スクリプトモジュールの作成</span><span class="sxs-lookup"><span data-stu-id="db6ce-107">Writing a PowerShell Script Module</span></span>

<span data-ttu-id="db6ce-108">スクリプトモジュールを作成するには、有効な PowerShell スクリプトを hbase-runner.psm1 ファイルに保存し、そのファイルを PowerShell が検出できる場所にあるディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="db6ce-108">You create a script module by saving a valid PowerShell script to a .psm1 file, and then saving that file in a directory located where PowerShell can find it.</span></span> <span data-ttu-id="db6ce-109">このフォルダーには、スクリプトを実行するために必要なリソースと、PowerShell に記述されているモジュールの動作を示すマニフェストファイルを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="db6ce-109">In that folder you can also place any resources you need to run your script, as well as a manifest file that describes to PowerShell how your module works.</span></span>

#### <a name="to-create-a-basic-powershell-module"></a><span data-ttu-id="db6ce-110">基本的な PowerShell モジュールを作成するには</span><span class="sxs-lookup"><span data-stu-id="db6ce-110">To create a basic PowerShell Module</span></span>

1. <span data-ttu-id="db6ce-111">既存の PowerShell スクリプトを取得し、hbase-runner.psm1 拡張子を付けてスクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="db6ce-111">Take an existing PowerShell script, and save the script with a .psm1 extension.</span></span>

   <span data-ttu-id="db6ce-112">Hbase-runner.psm1 拡張子を使用してスクリプトを保存すると、モジュールのコマンドレット (モジュールの[インポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)など) を使用できることになります。</span><span class="sxs-lookup"><span data-stu-id="db6ce-112">Saving a script with the .psm1 extension means that you can use the module cmdlets, such as [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), on it.</span></span> <span data-ttu-id="db6ce-113">これらのコマンドレットは主に、他のユーザーのシステムに簡単にコードをインポートしてエクスポートできるようにするために用意されています。</span><span class="sxs-lookup"><span data-stu-id="db6ce-113">These cmdlets exist primarily so that you can easily import and export your code onto other user's systems.</span></span> <span data-ttu-id="db6ce-114">(代替ソリューションとしては、他のシステムでコードを読み込んでから、そのコードをアクティブメモリにドットソースします。これは、特にスケーラブルなソリューションではありません)。詳細については、「 [Windows PowerShell モジュール](./understanding-a-windows-powershell-module.md)」の「**モジュールのコマンドレットと変数**」セクションを参照してください。既定では、hbase-runner.psm1 ファイルをインポートしたユーザーはスクリプト内のすべての関数にアクセスできますが、プロパティは使用できません。</span><span class="sxs-lookup"><span data-stu-id="db6ce-114">(The alternate solution would be to load up your code on other systems and then dot-source it into active memory, which isn't a particularly scalable solution.) For more information see the **Module Cmdlets and Variables** section in [Windows PowerShell Modules](./understanding-a-windows-powershell-module.md) Note that, by default, all functions in your script are accessible to users who import your .psm1 file, but properties are not.</span></span>

   <span data-ttu-id="db6ce-115">PowerShell スクリプトの例 (@no__t 0) は、このトピックの最後にあります。</span><span class="sxs-lookup"><span data-stu-id="db6ce-115">An example PowerShell script, entitled `Show-Calendar`, is available at the end of this topic.</span></span>

   ```powershell
   function Show-Calendar {
   param(
       [DateTime] $start = [DateTime]::Today,
       [DateTime] $end = $start,
       $firstDayOfWeek,
       [int[]] $highlightDay,
       [string[]] $highlightDate = [DateTime]::Today.ToString()
       )

       #actual code for the function goes here see the end of the topic for the complete code sample
   }
   ```

2. <span data-ttu-id="db6ce-116">特定の関数またはプロパティへのユーザーのアクセスを制御するには、スクリプトの最後に[export-modulemember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="db6ce-116">To control user access to certain functions or properties, call [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) at the end of your script.</span></span>

   <span data-ttu-id="db6ce-117">ページの下部にあるコード例には、既定で公開される関数が1つだけあります。</span><span class="sxs-lookup"><span data-stu-id="db6ce-117">The example code at the bottom of the page has only one function, which by default would be exposed.</span></span> <span data-ttu-id="db6ce-118">ただし、次のコードに示すように、公開する関数を明示的に呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db6ce-118">However, it is recommended that you explicitly call out which functions you wish to expose, as described in the following code:</span></span>

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   <span data-ttu-id="db6ce-119">モジュールマニフェストを使用してインポートされる内容を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="db6ce-119">You can also restrict what is imported using a module manifest.</span></span> <span data-ttu-id="db6ce-120">詳細については、「 [Powershell モジュールをインポート](./importing-a-powershell-module.md)する」および「 [powershell モジュールマニフェストを記述する方法](./how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db6ce-120">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [How to Write a PowerShell Module Manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

3. <span data-ttu-id="db6ce-121">独自のモジュールで読み込む必要があるモジュールがある場合は、独自のモジュールの上部にある `Import-Module` を呼び出すことによって使用できます。</span><span class="sxs-lookup"><span data-stu-id="db6ce-121">If you have modules that your own module needs to have loaded, you can use them with a call to `Import-Module`, at the top of your own module.</span></span>

   <span data-ttu-id="db6ce-122">`Import-Module` は、対象となるモジュールをシステムにインポートするコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="db6ce-122">`Import-Module` is a cmdlet that imports a targeted module onto a system.</span></span> <span data-ttu-id="db6ce-123">このため、独自のモジュールをインストールする手順の後の段階でも使用されます。</span><span class="sxs-lookup"><span data-stu-id="db6ce-123">As such, it is also used at a later point in the procedure to install your own module as well.</span></span> <span data-ttu-id="db6ce-124">このページの下部にあるサンプルコードでは、インポートモジュールは使用されません。</span><span class="sxs-lookup"><span data-stu-id="db6ce-124">The sample code at the bottom of this page does not use any import modules.</span></span> <span data-ttu-id="db6ce-125">使用されていた場合は、次のコードに示すように、ファイルの先頭に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="db6ce-125">If it did, however, they would be listed at the top of the file, as described in the following code:</span></span>

   ```powershell
   Import-Module GenericModule
   ```

4. <span data-ttu-id="db6ce-126">PowerShell ヘルプシステムにモジュールを記述するには、ファイル内で標準のヘルプコメントを使用するか、追加のヘルプファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="db6ce-126">To describe your module to the PowerShell Help system, you can either use standard help comments inside the file, or create an additional Help file.</span></span>

   <span data-ttu-id="db6ce-127">このトピックの下部にあるコードサンプルには、コメントのヘルプ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db6ce-127">The code sample at the bottom of this topic includes the help information in the comments.</span></span> <span data-ttu-id="db6ce-128">また、追加のヘルプコンテンツを含む拡張 XML ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="db6ce-128">You could also write expanded XML files that contain additional help content.</span></span> <span data-ttu-id="db6ce-129">詳細については、「 [Windows PowerShell モジュールのヘルプの作成](./writing-help-for-windows-powershell-modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db6ce-129">For more information, see [Writing Help for Windows PowerShell Modules](./writing-help-for-windows-powershell-modules.md).</span></span>

5. <span data-ttu-id="db6ce-130">モジュールと共にパッケージ化する追加のモジュール、XML ファイル、またはその他のコンテンツがある場合は、モジュールマニフェストを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="db6ce-130">If you have additional modules, XML files, or other content you want to package up with your module, you can do so with a module manifest.</span></span>

   <span data-ttu-id="db6ce-131">モジュールマニフェストは、他のモジュールの名前、ディレクトリレイアウト、バージョン管理番号、作成者データ、およびその他の情報を含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="db6ce-131">A module manifest is a file that contains the names of other modules, directory layouts, versioning numbers, author data, and other pieces of information.</span></span> <span data-ttu-id="db6ce-132">PowerShell では、モジュールマニフェストファイルを使用して、ソリューションの編成とデプロイを行います。</span><span class="sxs-lookup"><span data-stu-id="db6ce-132">PowerShell uses the module manifest file to organize and deploy your solution.</span></span> <span data-ttu-id="db6ce-133">ただし、この例では比較的単純な性質があるため、マニフェストファイルは必要ありませんでした。</span><span class="sxs-lookup"><span data-stu-id="db6ce-133">However, due to the relatively simple nature of this example, a manifest file was not needed.</span></span> <span data-ttu-id="db6ce-134">詳細については、「[モジュールマニフェスト](./how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db6ce-134">For more information, see [Module Manifests](./how-to-write-a-powershell-module-manifest.md).</span></span>

6. <span data-ttu-id="db6ce-135">モジュールをインストールして実行するには、適切な PowerShell パスのいずれかにモジュールを保存し、`Import-Module` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="db6ce-135">To install and run your module, save the module to one of the appropriate PowerShell paths, and make a call to `Import-Module`.</span></span>

   <span data-ttu-id="db6ce-136">モジュールをインストールできるパスは、@no__t 0 のグローバル変数に格納されています。</span><span class="sxs-lookup"><span data-stu-id="db6ce-136">The paths where you can install your module are located in the `$env:PSModulePath` global variable.</span></span> <span data-ttu-id="db6ce-137">たとえば、システムにモジュールを保存するための一般的なパスは、0 @no__t になります。</span><span class="sxs-lookup"><span data-stu-id="db6ce-137">For example, a common path to save a module on a system would be `%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`.</span></span> <span data-ttu-id="db6ce-138">Hbase-runner.psm1 ファイルである場合でも、モジュールが存在するフォルダーを必ず作成してください。</span><span class="sxs-lookup"><span data-stu-id="db6ce-138">Be sure to create a folder for your module to exist in, even if it is only a single .psm1 file.</span></span> <span data-ttu-id="db6ce-139">これらのパスのいずれかにモジュールを保存しなかった場合は、`Import-Module` への呼び出しでモジュールの場所を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="db6ce-139">If you did not save your module to one of these paths, you would have to pass in the location of your module in the call to `Import-Module`.</span></span> <span data-ttu-id="db6ce-140">(それ以外の場合、PowerShell はそれを見つけることができません)。PowerShell 3.0 以降では、いずれかの PowerShell モジュールパスにモジュールを配置した場合、明示的にインポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db6ce-140">(Otherwise, PowerShell would not be able to find it.) Starting with PowerShell 3.0, if you have placed your module in one of the PowerShell module paths, you do not need to explicitly import it.</span></span> <span data-ttu-id="db6ce-141">ユーザーが関数を呼び出したときに、モジュールが自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="db6ce-141">You module is automatically loaded when a user calls your function.</span></span>
   <span data-ttu-id="db6ce-142">モジュールパスの詳細については、「PowerShell モジュールと[PSModulePath 環境変数](./modifying-the-psmodulepath-installation-path.md)[のインポート](./importing-a-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db6ce-142">For more information on the module path, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [PSModulePath Environment Variable](./modifying-the-psmodulepath-installation-path.md).</span></span>

7. <span data-ttu-id="db6ce-143">アクティブなサービスからモジュールを削除するには、モジュールの[削除](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="db6ce-143">To remove a module from active service, make a call to [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span></span>

   <span data-ttu-id="db6ce-144">モジュールは、モジュールファイルを保存した場所から削除するのではなく、アクティブなメモリからモジュールを[削除すること](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)に注意してください。</span><span class="sxs-lookup"><span data-stu-id="db6ce-144">Note that [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) removes your module from active memory - it does not actually delete it from where you saved the module files.</span></span>

### <a name="show-calendar-code-example"></a><span data-ttu-id="db6ce-145">カレンダーのコード例の表示</span><span class="sxs-lookup"><span data-stu-id="db6ce-145">Show-Calendar code example</span></span>

<span data-ttu-id="db6ce-146">次の例は、`Show-Calendar` という名前の単一の関数を含む単純なスクリプトモジュールです。</span><span class="sxs-lookup"><span data-stu-id="db6ce-146">The following example is a simple script module that contains a single function named `Show-Calendar`.</span></span>
<span data-ttu-id="db6ce-147">この関数は、カレンダーの視覚的な表現を表示します。</span><span class="sxs-lookup"><span data-stu-id="db6ce-147">This function displays a visual representation of a calendar.</span></span> <span data-ttu-id="db6ce-148">また、このサンプルには、概要、説明、パラメーター値、および例の PowerShell ヘルプ文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db6ce-148">In addition, the sample contains the PowerShell Help strings for the synopsis, description, parameter values, and example.</span></span> <span data-ttu-id="db6ce-149">コードの最後の行では、モジュールをインポートするときに、@no__t 0 関数がモジュールメンバーとしてエクスポートされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="db6ce-149">Note that the last line of code ensures that the `Show-Calendar` function is exported as a module member when the module is imported.</span></span>

```powershell
<#
 .Synopsis
  Displays a visual representation of a calendar.

 .Description
  Displays a visual representation of a calendar. This function supports multiple months
  and lets you highlight specific date ranges or days.

 .Parameter Start
  The first month to display.

 .Parameter End
  The last month to display.

 .Parameter FirstDayOfWeek
  The day of the month on which the week begins.

 .Parameter HighlightDay
  Specific days (numbered) to highlight. Used for date ranges like (25..31).
  Date ranges are specified by the Windows PowerShell range syntax. These dates are
  enclosed in square brackets.

 .Parameter HighlightDate
  Specific days (named) to highlight. These dates are surrounded by asterisks.

 .Example
   # Show a default display of this month.
   Show-Calendar

 .Example
   # Display a date range.
   Show-Calendar -Start "March, 2010" -End "May, 2010"

 .Example
   # Highlight a range of days.
   Show-Calendar -HighlightDay (1..10 + 22) -HighlightDate "December 25, 2008"
#>
function Show-Calendar {
param(
    [DateTime] $start = [DateTime]::Today,
    [DateTime] $end = $start,
    $firstDayOfWeek,
    [int[]] $highlightDay,
    [string[]] $highlightDate = [DateTime]::Today.ToString()
    )

## Determine the first day of the start and end months.
$start = New-Object DateTime $start.Year,$start.Month,1
$end = New-Object DateTime $end.Year,$end.Month,1

## Convert the highlighted dates into real dates.
[DateTime[]] $highlightDate = [DateTime[]] $highlightDate

## Retrieve the DateTimeFormat information so that the
## calendar can be manipulated.
$dateTimeFormat  = (Get-Culture).DateTimeFormat
if($firstDayOfWeek)
{
    $dateTimeFormat.FirstDayOfWeek = $firstDayOfWeek
}

$currentDay = $start

## Process the requested months.
while($start -le $end)
{
    ## Return to an earlier point in the function if the first day of the month
    ## is in the middle of the week.
    while($currentDay.DayOfWeek -ne $dateTimeFormat.FirstDayOfWeek)
    {
        $currentDay = $currentDay.AddDays(-1)
    }

    ## Prepare to store information about this date range.
    $currentWeek = New-Object PsObject
    $dayNames = @()
    $weeks = @()

    ## Continue processing dates until the function reaches the end of the month.
    ## The function continues until the week is completed with
    ## days from the next month.
    while(($currentDay -lt $start.AddMonths(1)) -or
        ($currentDay.DayOfWeek -ne $dateTimeFormat.FirstDayOfWeek))
    {
        ## Determine the day names to use to label the columns.
        $dayName = "{0:ddd}" -f $currentDay
        if($dayNames -notcontains $dayName)
        {
            $dayNames += $dayName
        }

        ## Pad the day number for display, highlighting if necessary.
        $displayDay = " {0,2} " -f $currentDay.Day

        ## Determine whether to highlight a specific date.
        if($highlightDate)
        {
            $compareDate = New-Object DateTime $currentDay.Year,
                $currentDay.Month,$currentDay.Day
            if($highlightDate -contains $compareDate)
            {
                $displayDay = "*" + ("{0,2}" -f $currentDay.Day) + "*"
            }
        }

        ## Otherwise, highlight as part of a date range.
        if($highlightDay -and ($highlightDay[0] -eq $currentDay.Day))
        {
            $displayDay = "[" + ("{0,2}" -f $currentDay.Day) + "]"
            $null,$highlightDay = $highlightDay
        }

        ## Add the day of the week and the day of the month as note properties.
        $currentWeek | Add-Member NoteProperty $dayName $displayDay

        ## Move to the next day of the month.
        $currentDay = $currentDay.AddDays(1)

        ## If the function reaches the next week, store the current week
        ## in the week list and continue.
        if($currentDay.DayOfWeek -eq $dateTimeFormat.FirstDayOfWeek)
        {
            $weeks += $currentWeek
            $currentWeek = New-Object PsObject
        }
    }

    ## Format the weeks as a table.
    $calendar = $weeks | Format-Table $dayNames -AutoSize | Out-String

    ## Add a centered header.
    $width = ($calendar.Split("`n") | Measure-Object -Maximum Length).Maximum
    $header = "{0:MMMM yyyy}" -f $start
    $padding = " " * (($width - $header.Length) / 2)
    $displayCalendar = " `n" + $padding + $header + "`n " + $calendar
    $displayCalendar.TrimEnd()

    ## Move to the next month.
    $start = $start.AddMonths(1)

}
}
Export-ModuleMember -Function Show-Calendar
```
