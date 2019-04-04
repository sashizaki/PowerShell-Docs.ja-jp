---
title: PowerShell スクリプト モジュールを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed7645ea-5e52-4a45-81a7-aa3c2d605cde
caps.latest.revision: 16
ms.openlocfilehash: e8b7151538235cdf7183b78aa8df7e596d6bcfd9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859008"
---
# <a name="how-to-write-a-powershell-script-module"></a><span data-ttu-id="62097-102">PowerShell スクリプト モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="62097-102">How to Write a PowerShell Script Module</span></span>

<span data-ttu-id="62097-103">スクリプト モジュールは、基本的に、有効な PowerShell スクリプト .psm1 拡張子で保存します。</span><span class="sxs-lookup"><span data-stu-id="62097-103">A script module is essentially any valid PowerShell script saved in a .psm1 extension.</span></span> <span data-ttu-id="62097-104">この拡張機能には、ファイルをさまざまなルールとコマンドレットを使用する PowerShell エンジンが使用できます。</span><span class="sxs-lookup"><span data-stu-id="62097-104">This extension allows the PowerShell engine to use a number of rules and cmdlets on your file.</span></span> <span data-ttu-id="62097-105">これらの機能のほとんどは、スコープを管理したり、他のシステムで、コードをインストールするのにがあります。</span><span class="sxs-lookup"><span data-stu-id="62097-105">Most of these capabilities are there to help you install your code on other systems, as well as manage scoping.</span></span> <span data-ttu-id="62097-106">さらに複雑なインストールとソリューションを記述できるモジュール マニフェスト ファイルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="62097-106">You can also use a module manifest file, which can describe even more complex installations and solutions.</span></span>

## <a name="writing-a-powershell-script-module"></a><span data-ttu-id="62097-107">PowerShell スクリプト モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="62097-107">Writing a PowerShell Script Module</span></span>

<span data-ttu-id="62097-108">スクリプト モジュールを作成するには、.psm1 ファイルに有効な PowerShell スクリプトを保存して、PowerShell が検索できる場所にあるディレクトリでそのファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="62097-108">You create a script module by saving a valid PowerShell script to a .psm1 file, and then saving that file in a directory located where PowerShell can find it.</span></span> <span data-ttu-id="62097-109">、スクリプトを実行する必要があるすべてのリソースを配置することもできます。 そのフォルダー内マニフェスト ファイルもを powershell モジュールのしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="62097-109">In that folder you can also place any resources you need to run your script, as well as a manifest file that describes to PowerShell how your module works.</span></span>

#### <a name="to-create-a-basic-powershell-module"></a><span data-ttu-id="62097-110">基本的な PowerShell モジュールを作成するには</span><span class="sxs-lookup"><span data-stu-id="62097-110">To create a basic PowerShell Module</span></span>

1. <span data-ttu-id="62097-111">既存の PowerShell スクリプトを実行し、拡張子が .psm1 スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="62097-111">Take an existing PowerShell script, and save the script with a .psm1 extension.</span></span>

   <span data-ttu-id="62097-112">拡張機能がモジュールのコマンドレットをなど、使用できることを意味を持つ、.psm1 スクリプトが保存[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)にします。</span><span class="sxs-lookup"><span data-stu-id="62097-112">Saving a script with the .psm1 extension means that you can use the module cmdlets, such as [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), on it.</span></span> <span data-ttu-id="62097-113">ように、簡単にインポートし、他のユーザーのシステムにコードをエクスポートできますでは主に、これらのコマンドレットが存在します。</span><span class="sxs-lookup"><span data-stu-id="62097-113">These cmdlets exist primarily so that you can easily import and export your code onto other user's systems.</span></span> <span data-ttu-id="62097-114">(代替のソリューションは、特にスケーラブルなソリューションではないアクティブ メモリに他のシステムや、ドット ソース上のコードをロードする場合が)。詳細については、次を参照してください。、**モジュールのコマンドレットと変数**セクション[Windows PowerShell モジュール](./understanding-a-windows-powershell-module.md)、既定では、スクリプト内のすべての関数がアクセスできる、.psm1 をインポートするユーザーに注意してください。プロパティは、ファイルはありません。</span><span class="sxs-lookup"><span data-stu-id="62097-114">(The alternate solution would be to load up your code on other systems and then dot-source it into active memory, which isn't a particularly scalable solution.) For more information see the **Module Cmdlets and Variables** section in [Windows PowerShell Modules](./understanding-a-windows-powershell-module.md) Note that, by default, all functions in your script will be accessible to users who import your .psm1 file, but properties will not.</span></span>

   <span data-ttu-id="62097-115">Show-calendar、という PowerShell のスクリプトの例は、このトピックの最後でご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="62097-115">An example PowerShell script, entitled Show-Calendar, is available at the end of this topic.</span></span>

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

2. <span data-ttu-id="62097-116">特定の関数やプロパティへのユーザー アクセスを制御する場合は、呼び出す[Export-modulemember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember)スクリプトの最後にします。</span><span class="sxs-lookup"><span data-stu-id="62097-116">If you wish to control user access to certain functions or properties, call [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) at the end of your script.</span></span>

   <span data-ttu-id="62097-117">ページの下部にあるコード例では、公開は既定では、1 つの機能があります。</span><span class="sxs-lookup"><span data-stu-id="62097-117">The example code at the bottom of the page has only one function, which by default would be exposed.</span></span> <span data-ttu-id="62097-118">ただし、次のコードの説明に従って、公開する関数を明示的に呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62097-118">However, it is recommended that you explicitly call out which functions you wish to expose, as described in the following code:</span></span>

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   <span data-ttu-id="62097-119">モジュール マニフェストを使用してインポートされる内容を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="62097-119">You can also restrict what is imported using a module manifest.</span></span> <span data-ttu-id="62097-120">詳細については、[PowerShell モジュールをインポートする](./importing-a-powershell-module.md)と[PowerShell モジュール マニフェストの記述方法](./how-to-write-a-powershell-module-manifest.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62097-120">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [How to Write a PowerShell Module Manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

3. <span data-ttu-id="62097-121">呼び出しに使用できる独自のモジュールが読み込まれている必要があるモジュールがあれば、 `Import-Module`、独自のモジュールの上部にあります。</span><span class="sxs-lookup"><span data-stu-id="62097-121">If you have modules that your own module needs to have loaded, you can use them with a call to `Import-Module`, at the top of your own module.</span></span>

   <span data-ttu-id="62097-122">`Import-Module` システム上に対象となるモジュールをインポートするコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="62097-122">`Import-Module` is a cmdlet that imports a targeted module onto a system.</span></span> <span data-ttu-id="62097-123">そのため、またはも使用の手順で、後でも、独自のモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="62097-123">As such, it is also used at a later point in the procedure to install your own module as well.</span></span> <span data-ttu-id="62097-124">このページの下部にあるサンプル コードでは、任意のモジュールのインポートは使用しません。</span><span class="sxs-lookup"><span data-stu-id="62097-124">The sample code at the bottom of this page does not use any import modules.</span></span> <span data-ttu-id="62097-125">ただしと同じ場合、次のコードで説明されているようには、ファイルの上部にあるリストは。</span><span class="sxs-lookup"><span data-stu-id="62097-125">If it did, however, they would be listed at the top of the file, as described in the following code:</span></span>

   ```powershell
   Import-Module GenericModule
   ```

4. <span data-ttu-id="62097-126">PowerShell のヘルプ システムにモジュールを記述する場合は、これを行うファイル内の標準のヘルプのコメントまたは追加のヘルプ ファイルのいずれか。</span><span class="sxs-lookup"><span data-stu-id="62097-126">If you want to describe your module to the PowerShell Help system, you can do so either with the standard help comments inside the file, or with an additional Help file.</span></span>

   <span data-ttu-id="62097-127">このトピックの下部にあるコード サンプルには、コメントにヘルプ情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="62097-127">The code sample at the bottom of this topic includes the help information in the comments.</span></span> <span data-ttu-id="62097-128">ために選択した場合は、追加のヘルプ コンテンツを含む XML ファイルが展開されたも記述できます。</span><span class="sxs-lookup"><span data-stu-id="62097-128">If you so choose, you could also write expanded XML files that contain additional help content.</span></span> <span data-ttu-id="62097-129">詳細については、[書き込みための Windows PowerShell モジュール](./writing-help-for-windows-powershell-modules.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62097-129">For more information, see [Writing Help for Windows PowerShell Modules](./writing-help-for-windows-powershell-modules.md).</span></span>

5. <span data-ttu-id="62097-130">モジュールの追加、XML ファイル、またはモジュールにパッケージ化する他のコンテンツがある場合は、モジュール マニフェストでこれを実行できます。</span><span class="sxs-lookup"><span data-stu-id="62097-130">If you have additional modules, XML files, or other content you want to package up with your module, you can do so with a module manifest.</span></span>

   <span data-ttu-id="62097-131">モジュール マニフェストは、他のモジュール、ディレクトリのレイアウト、バージョン番号、データを作成、および他の情報の名前を含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="62097-131">A module manifest is a file that contains the names of other modules, directory layouts, versioning numbers, author data, and other pieces of information.</span></span> <span data-ttu-id="62097-132">PowerShell では、モジュール マニフェスト ファイルを使用して編成し、ソリューションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="62097-132">PowerShell uses the module manifest file to organize and deploy your solution.</span></span> <span data-ttu-id="62097-133">ただし、この例の比較的単純な性質では、マニフェスト ファイルが不要です。</span><span class="sxs-lookup"><span data-stu-id="62097-133">However, due to the relatively simple nature of this example, a manifest file was not needed.</span></span> <span data-ttu-id="62097-134">詳細については、[モジュール マニフェスト](./how-to-write-a-powershell-module-manifest.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62097-134">For more information, see [Module Manifests](./how-to-write-a-powershell-module-manifest.md).</span></span>

6. <span data-ttu-id="62097-135">をインストールして、モジュールを実行するモジュールを、適切な PowerShell パスのいずれかに保存し、呼び出しを行う`Import-Module`します。</span><span class="sxs-lookup"><span data-stu-id="62097-135">To install and run your module, save the module to one of the appropriate PowerShell paths, and make a call to `Import-Module`.</span></span>

   <span data-ttu-id="62097-136">モジュールをインストールするパスにある、`$env:PSModulePath`グローバル変数。</span><span class="sxs-lookup"><span data-stu-id="62097-136">The paths where you can install your module are located in the `$env:PSModulePath` global variable.</span></span> <span data-ttu-id="62097-137">たとえば、システム上のモジュールを保存する共通のパスになります`%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`します。</span><span class="sxs-lookup"><span data-stu-id="62097-137">For example, a common path to save a module on a system would be `%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`.</span></span> <span data-ttu-id="62097-138">1 つの .psm1 ファイルのみの場合でも、モジュールが存在するためのフォルダーを作成することを確認します。</span><span class="sxs-lookup"><span data-stu-id="62097-138">Be sure to create a folder for your module to exist in, even if it is only a single .psm1 file.</span></span> <span data-ttu-id="62097-139">これらのパスのいずれかに、モジュールを保存しなかったへの呼び出しで、モジュールの場所を渡す必要があります`Import-Module`します。</span><span class="sxs-lookup"><span data-stu-id="62097-139">If you did not save your module to one of these paths, you would have to pass in the location of your module in the call to `Import-Module`.</span></span> <span data-ttu-id="62097-140">(それ以外の場合、PowerShell はできませんを検索します。)PowerShell 3.0 以降、モジュールを PowerShell モジュールのパスのいずれかに配置した場合、必要はありませんを明示的にインポートする: 関数を呼び出すユーザーのいるだけでは自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="62097-140">(Otherwise, PowerShell would not be able to find it.) Starting with PowerShell 3.0, if you have placed your module on one of the PowerShell module paths, you do not need to explicitly import it: simply having a user call your function will automatically load it.</span></span> <span data-ttu-id="62097-141">モジュール パスの詳細については、[PowerShell モジュールをインポートする](./importing-a-powershell-module.md)と[PSModulePath 環境変数](./modifying-the-psmodulepath-installation-path.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62097-141">For more information on the module path, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [PSModulePath Environment Variable](./modifying-the-psmodulepath-installation-path.md).</span></span>

7. <span data-ttu-id="62097-142">アクティブなサービスからモジュールを削除するへの呼び出しを行い[Remove-module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)します。</span><span class="sxs-lookup"><span data-stu-id="62097-142">To remove a module from active service, make a call to [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span></span>

<span data-ttu-id="62097-143">なお[Remove-module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)モジュールを削除します - のアクティブなメモリから実際には削除されませんが、モジュール ファイルを保存した場所からします。</span><span class="sxs-lookup"><span data-stu-id="62097-143">Note that [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) removes your module from active memory - it does not actually delete it from where you saved the module files.</span></span>

### <a name="show-calendar-code-example"></a><span data-ttu-id="62097-144">コード例を表示</span><span class="sxs-lookup"><span data-stu-id="62097-144">Show-Calendar code example</span></span>

<span data-ttu-id="62097-145">次の例は、Show-calendar という名前の 1 つの関数を含む単純なスクリプト モジュールです。</span><span class="sxs-lookup"><span data-stu-id="62097-145">The following example is a simple script module that contains a single function named Show-Calendar.</span></span> <span data-ttu-id="62097-146">この関数は、予定表の視覚的表現を表示します。</span><span class="sxs-lookup"><span data-stu-id="62097-146">This function displays a visual representation of a calendar.</span></span> <span data-ttu-id="62097-147">さらに、このサンプルには、概要、説明、パラメーター値、および例のための PowerShell のヘルプ文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="62097-147">In addition, the sample contains the PowerShell Help strings for the synopsis, description, parameter values, and example.</span></span> <span data-ttu-id="62097-148">コードの最後の行がモジュールがインポートされるときに、Show-calendar 関数はモジュール メンバーとしてエクスポートすることを示すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="62097-148">Note that the last line of code indicates that the Show-Calendar function will be exported as a module member when the module is imported.</span></span>

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
    $width = ($calendar.Split("'n") | Measure-Object -Maximum Length).Maximum
    $header = "{0:MMMM yyyy}" -f $start
    $padding = " " * (($width - $header.Length) / 2)
    $displayCalendar = " 'n" + $padding + $header + "'n " + $calendar
    $displayCalendar.TrimEnd()

    ## Move to the next month.
    $start = $start.AddMonths(1)

}
}
Export-ModuleMember -Function Show-Calendar
```
