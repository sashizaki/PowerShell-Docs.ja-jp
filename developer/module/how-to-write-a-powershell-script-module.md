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
ms.openlocfilehash: b2a929a1724f77f0516ad24cfd90f6d6053ed19e
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470804"
---
# <a name="how-to-write-a-powershell-script-module"></a><span data-ttu-id="4f2aa-102">PowerShell スクリプト モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="4f2aa-102">How to Write a PowerShell Script Module</span></span>

<span data-ttu-id="4f2aa-103">スクリプト モジュールは、基本的に、有効な PowerShell スクリプト .psm1 拡張子で保存します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-103">A script module is essentially any valid PowerShell script saved in a .psm1 extension.</span></span> <span data-ttu-id="4f2aa-104">この拡張機能には、ファイルをさまざまなルールとコマンドレットを使用する PowerShell エンジンが使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-104">This extension allows the PowerShell engine to use a number of rules and cmdlets on your file.</span></span> <span data-ttu-id="4f2aa-105">これらの機能のほとんどは、スコープを管理したり、他のシステムで、コードをインストールするのにがあります。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-105">Most of these capabilities are there to help you install your code on other systems, as well as manage scoping.</span></span> <span data-ttu-id="4f2aa-106">さらに複雑なインストールとソリューションを記述できるモジュール マニフェスト ファイルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-106">You can also use a module manifest file, which can describe even more complex installations and solutions.</span></span>

## <a name="writing-a-powershell-script-module"></a><span data-ttu-id="4f2aa-107">PowerShell スクリプト モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="4f2aa-107">Writing a PowerShell Script Module</span></span>

<span data-ttu-id="4f2aa-108">スクリプト モジュールを作成するには、.psm1 ファイルに有効な PowerShell スクリプトを保存して、PowerShell が検索できる場所にあるディレクトリでそのファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-108">You create a script module by saving a valid PowerShell script to a .psm1 file, and then saving that file in a directory located where PowerShell can find it.</span></span> <span data-ttu-id="4f2aa-109">、スクリプトを実行する必要があるすべてのリソースを配置することもできます。 そのフォルダー内マニフェスト ファイルもを powershell モジュールのしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-109">In that folder you can also place any resources you need to run your script, as well as a manifest file that describes to PowerShell how your module works.</span></span>

#### <a name="to-create-a-basic-powershell-module"></a><span data-ttu-id="4f2aa-110">基本的な PowerShell モジュールを作成するには</span><span class="sxs-lookup"><span data-stu-id="4f2aa-110">To create a basic PowerShell Module</span></span>

1. <span data-ttu-id="4f2aa-111">既存の PowerShell スクリプトを実行し、拡張子が .psm1 スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-111">Take an existing PowerShell script, and save the script with a .psm1 extension.</span></span>

   <span data-ttu-id="4f2aa-112">拡張機能がモジュールのコマンドレットをなど、使用できることを意味を持つ、.psm1 スクリプトが保存[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)にします。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-112">Saving a script with the .psm1 extension means that you can use the module cmdlets, such as [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), on it.</span></span> <span data-ttu-id="4f2aa-113">ように、簡単にインポートし、他のユーザーのシステムにコードをエクスポートできますでは主に、これらのコマンドレットが存在します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-113">These cmdlets exist primarily so that you can easily import and export your code onto other user's systems.</span></span> <span data-ttu-id="4f2aa-114">(代替のソリューションは、特にスケーラブルなソリューションではないアクティブ メモリに他のシステムや、ドット ソース上のコードをロードする場合が)。詳細については、次を参照してください。、**モジュールのコマンドレットと変数**セクション[Windows PowerShell モジュール](./understanding-a-windows-powershell-module.md)、既定では、スクリプト内のすべての関数にアクセスできること、.psm1 ファイルをインポートするユーザーに注意してください。プロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-114">(The alternate solution would be to load up your code on other systems and then dot-source it into active memory, which isn't a particularly scalable solution.) For more information see the **Module Cmdlets and Variables** section in [Windows PowerShell Modules](./understanding-a-windows-powershell-module.md) Note that, by default, all functions in your script are accessible to users who import your .psm1 file, but properties are not.</span></span>

   <span data-ttu-id="4f2aa-115">という PowerShell のスクリプトの例`Show-Calendar`は、このトピックの最後でご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-115">An example PowerShell script, entitled `Show-Calendar`, is available at the end of this topic.</span></span>

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

2. <span data-ttu-id="4f2aa-116">特定の関数やプロパティへのユーザー アクセスを制御するには、呼び出す[Export-modulemember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember)スクリプトの最後にします。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-116">To control user access to certain functions or properties, call [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) at the end of your script.</span></span>

   <span data-ttu-id="4f2aa-117">ページの下部にあるコード例では、公開は既定では、1 つの機能があります。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-117">The example code at the bottom of the page has only one function, which by default would be exposed.</span></span> <span data-ttu-id="4f2aa-118">ただし、次のコードの説明に従って、公開する関数を明示的に呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-118">However, it is recommended that you explicitly call out which functions you wish to expose, as described in the following code:</span></span>

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   <span data-ttu-id="4f2aa-119">モジュール マニフェストを使用してインポートされる内容を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-119">You can also restrict what is imported using a module manifest.</span></span> <span data-ttu-id="4f2aa-120">詳細については、次を参照してください。 [PowerShell モジュールをインポートする](./importing-a-powershell-module.md)と[PowerShell モジュール マニフェストの記述方法](./how-to-write-a-powershell-module-manifest.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-120">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [How to Write a PowerShell Module Manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

3. <span data-ttu-id="4f2aa-121">呼び出しに使用できる独自のモジュールが読み込まれている必要があるモジュールがあれば、 `Import-Module`、独自のモジュールの上部にあります。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-121">If you have modules that your own module needs to have loaded, you can use them with a call to `Import-Module`, at the top of your own module.</span></span>

   <span data-ttu-id="4f2aa-122">`Import-Module` システム上に対象となるモジュールをインポートするコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-122">`Import-Module` is a cmdlet that imports a targeted module onto a system.</span></span> <span data-ttu-id="4f2aa-123">そのため、またはも使用の手順で、後でも、独自のモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-123">As such, it is also used at a later point in the procedure to install your own module as well.</span></span> <span data-ttu-id="4f2aa-124">このページの下部にあるサンプル コードでは、任意のモジュールのインポートは使用しません。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-124">The sample code at the bottom of this page does not use any import modules.</span></span> <span data-ttu-id="4f2aa-125">ただしと同じ場合、次のコードで説明されているようには、ファイルの上部にあるリストは。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-125">If it did, however, they would be listed at the top of the file, as described in the following code:</span></span>

   ```powershell
   Import-Module GenericModule
   ```

4. <span data-ttu-id="4f2aa-126">PowerShell のヘルプ システムにモジュールを記述するには、ファイル内の標準のヘルプのコメントを使用するか、追加のヘルプ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-126">To describe your module to the PowerShell Help system, you can either use standard help comments inside the file, or create an additional Help file.</span></span>

   <span data-ttu-id="4f2aa-127">このトピックの下部にあるコード サンプルには、コメントにヘルプ情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-127">The code sample at the bottom of this topic includes the help information in the comments.</span></span> <span data-ttu-id="4f2aa-128">追加のヘルプ コンテンツを含む XML ファイルを拡張を記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-128">You could also write expanded XML files that contain additional help content.</span></span> <span data-ttu-id="4f2aa-129">詳細については、次を参照してください。[書き込みための Windows PowerShell モジュール](./writing-help-for-windows-powershell-modules.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-129">For more information, see [Writing Help for Windows PowerShell Modules](./writing-help-for-windows-powershell-modules.md).</span></span>

5. <span data-ttu-id="4f2aa-130">モジュールの追加、XML ファイル、またはモジュールにパッケージ化する他のコンテンツがある場合は、モジュール マニフェストでこれを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-130">If you have additional modules, XML files, or other content you want to package up with your module, you can do so with a module manifest.</span></span>

   <span data-ttu-id="4f2aa-131">モジュール マニフェストは、他のモジュール、ディレクトリのレイアウト、バージョン番号、データを作成、および他の情報の名前を含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-131">A module manifest is a file that contains the names of other modules, directory layouts, versioning numbers, author data, and other pieces of information.</span></span> <span data-ttu-id="4f2aa-132">PowerShell では、モジュール マニフェスト ファイルを使用して編成し、ソリューションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-132">PowerShell uses the module manifest file to organize and deploy your solution.</span></span> <span data-ttu-id="4f2aa-133">ただし、この例の比較的単純な性質では、マニフェスト ファイルが不要です。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-133">However, due to the relatively simple nature of this example, a manifest file was not needed.</span></span> <span data-ttu-id="4f2aa-134">詳細については、次を参照してください。[モジュール マニフェスト](./how-to-write-a-powershell-module-manifest.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-134">For more information, see [Module Manifests](./how-to-write-a-powershell-module-manifest.md).</span></span>

6. <span data-ttu-id="4f2aa-135">をインストールして、モジュールを実行するモジュールを、適切な PowerShell パスのいずれかに保存し、呼び出しを行う`Import-Module`します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-135">To install and run your module, save the module to one of the appropriate PowerShell paths, and make a call to `Import-Module`.</span></span>

   <span data-ttu-id="4f2aa-136">モジュールをインストールするパスにある、`$env:PSModulePath`グローバル変数。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-136">The paths where you can install your module are located in the `$env:PSModulePath` global variable.</span></span> <span data-ttu-id="4f2aa-137">たとえば、システム上のモジュールを保存する共通のパスになります`%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-137">For example, a common path to save a module on a system would be `%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`.</span></span> <span data-ttu-id="4f2aa-138">1 つの .psm1 ファイルのみの場合でも、モジュールが存在するためのフォルダーを作成することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-138">Be sure to create a folder for your module to exist in, even if it is only a single .psm1 file.</span></span> <span data-ttu-id="4f2aa-139">これらのパスのいずれかに、モジュールを保存しなかったへの呼び出しで、モジュールの場所を渡す必要があります`Import-Module`します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-139">If you did not save your module to one of these paths, you would have to pass in the location of your module in the call to `Import-Module`.</span></span> <span data-ttu-id="4f2aa-140">(それ以外の場合、PowerShell はできませんを検索します。)PowerShell 3.0 以降の PowerShell モジュールのパスのいずれかで、モジュールを配置した場合は、する必要はありませんを明示的にインポートします。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-140">(Otherwise, PowerShell would not be able to find it.) Starting with PowerShell 3.0, if you have placed your module in one of the PowerShell module paths, you do not need to explicitly import it.</span></span> <span data-ttu-id="4f2aa-141">ユーザーが関数を呼び出すときにするモジュールが自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-141">You module is automatically loaded when a user calls your function.</span></span>
   <span data-ttu-id="4f2aa-142">モジュール パスの詳細については、次を参照してください。 [PowerShell モジュールをインポートする](./importing-a-powershell-module.md)と[PSModulePath 環境変数](./modifying-the-psmodulepath-installation-path.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-142">For more information on the module path, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [PSModulePath Environment Variable](./modifying-the-psmodulepath-installation-path.md).</span></span>

7. <span data-ttu-id="4f2aa-143">アクティブなサービスからモジュールを削除するへの呼び出しを行い[Remove-module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-143">To remove a module from active service, make a call to [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span></span>

   <span data-ttu-id="4f2aa-144">なお[Remove-module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)モジュールを削除します - のアクティブなメモリから実際には削除されませんが、モジュール ファイルを保存した場所からします。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-144">Note that [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) removes your module from active memory - it does not actually delete it from where you saved the module files.</span></span>

### <a name="show-calendar-code-example"></a><span data-ttu-id="4f2aa-145">コード例を表示</span><span class="sxs-lookup"><span data-stu-id="4f2aa-145">Show-Calendar code example</span></span>

<span data-ttu-id="4f2aa-146">次の例はという名前の 1 つの関数を含む単純なスクリプト モジュール`Show-Calendar`します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-146">The following example is a simple script module that contains a single function named `Show-Calendar`.</span></span>
<span data-ttu-id="4f2aa-147">この関数は、予定表の視覚的表現を表示します。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-147">This function displays a visual representation of a calendar.</span></span> <span data-ttu-id="4f2aa-148">さらに、このサンプルには、概要、説明、パラメーター値、および例のための PowerShell のヘルプ文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-148">In addition, the sample contains the PowerShell Help strings for the synopsis, description, parameter values, and example.</span></span> <span data-ttu-id="4f2aa-149">コードの最後の行によりに注意してください、`Show-Calendar`関数は、モジュールのインポート時にモジュールのメンバーとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="4f2aa-149">Note that the last line of code ensures that the `Show-Calendar` function is exported as a module member when the module is imported.</span></span>

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
