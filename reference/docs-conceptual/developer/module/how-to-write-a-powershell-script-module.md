---
title: PowerShell スクリプトモジュールを記述する方法 |Microsoft Docs
ms.date: 11/21/2019
ms.openlocfilehash: dc387909a9e55df9f1846b02755e284c408f7dc6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784896"
---
# <a name="how-to-write-a-powershell-script-module"></a><span data-ttu-id="c5c7c-102">PowerShell スクリプト モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="c5c7c-102">How to Write a PowerShell Script Module</span></span>

<span data-ttu-id="c5c7c-103">スクリプトモジュールは、拡張機能に保存されている有効な PowerShell スクリプトです `.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-103">A script module is any valid PowerShell script saved in a `.psm1` extension.</span></span> <span data-ttu-id="c5c7c-104">この拡張機能により、PowerShell エンジンは、ファイルでルールとモジュールコマンドレットを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-104">This extension allows the PowerShell engine to use rules and module cmdlets on your file.</span></span> <span data-ttu-id="c5c7c-105">これらの機能のほとんどは、他のシステムにコードをインストールしたり、スコープを管理したりできるようにするために用意されています。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-105">Most of these capabilities are there to help you install your code on other systems, as well as manage scoping.</span></span> <span data-ttu-id="c5c7c-106">さらに複雑なインストールとソリューションを記述するモジュールマニフェストファイルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-106">You can also use a module manifest file, which describes more complex installations and solutions.</span></span>

## <a name="writing-a-powershell-script-module"></a><span data-ttu-id="c5c7c-107">PowerShell スクリプトモジュールの作成</span><span class="sxs-lookup"><span data-stu-id="c5c7c-107">Writing a PowerShell script module</span></span>

<span data-ttu-id="c5c7c-108">スクリプトモジュールを作成するには、有効な PowerShell スクリプトを `.psm1` ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-108">To create a script module, save a valid PowerShell script to a `.psm1` file.</span></span> <span data-ttu-id="c5c7c-109">スクリプトと、それが格納されているディレクトリは、同じ名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-109">The script and the directory where it's stored must use the same name.</span></span> <span data-ttu-id="c5c7c-110">たとえば、という名前のスクリプトは、 `MyPsScript.psm1` という名前のディレクトリに格納され `MyPsScript` ます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-110">For example, a script named `MyPsScript.psm1` is stored in a directory named `MyPsScript`.</span></span>

<span data-ttu-id="c5c7c-111">モジュールのディレクトリは、で指定されたパスにある必要があり `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-111">The module's directory needs to be in a path specified in `$env:PSModulePath`.</span></span> <span data-ttu-id="c5c7c-112">モジュールのディレクトリには、スクリプトを実行するために必要なすべてのリソースと、PowerShell に記述されたモジュールマニフェストファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-112">The module's directory can contain any resources that are needed to run the script, and a module manifest file that describes to PowerShell how your module works.</span></span>

## <a name="create-a-basic-powershell-module"></a><span data-ttu-id="c5c7c-113">基本的な PowerShell モジュールを作成する</span><span class="sxs-lookup"><span data-stu-id="c5c7c-113">Create a basic PowerShell module</span></span>

<span data-ttu-id="c5c7c-114">次の手順では、PowerShell モジュールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-114">The following steps describe how to create a PowerShell module.</span></span>

1. <span data-ttu-id="c5c7c-115">拡張機能を使用して PowerShell スクリプトを保存 `.psm1` します。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-115">Save a PowerShell script with a `.psm1` extension.</span></span> <span data-ttu-id="c5c7c-116">スクリプトとスクリプトを保存するディレクトリに同じ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-116">Use the same name for the script and the directory where the script is saved.</span></span>

   <span data-ttu-id="c5c7c-117">拡張機能を使用してスクリプトを保存すると、 `.psm1` モジュールのコマンドレット ( [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)など) を使用できることになります。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-117">Saving a script with the `.psm1` extension means that you can use the module cmdlets, such as [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span> <span data-ttu-id="c5c7c-118">モジュールコマンドレットは、主に、他のユーザーのシステムにコードをインポートしてエクスポートできるようにするために存在します。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-118">The module cmdlets exist primarily so that you can import and export your code onto other user's systems.</span></span> <span data-ttu-id="c5c7c-119">代替ソリューションとして、コードを他のシステムに読み込んでから、そのコードをアクティブメモリに変換することができます。これはスケーラブルなソリューションではありません。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-119">The alternate solution would be to load your code on other systems and then dot-source it into active memory, which isn't a scalable solution.</span></span> <span data-ttu-id="c5c7c-120">詳細については、「 [Windows PowerShell モジュールに](./understanding-a-windows-powershell-module.md#module-cmdlets-and-variables)ついて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-120">For more information, see [Understanding a Windows PowerShell Module](./understanding-a-windows-powershell-module.md#module-cmdlets-and-variables).</span></span>
   <span data-ttu-id="c5c7c-121">既定では、ユーザーがファイルをインポートすると、 `.psm1` スクリプト内のすべての関数にアクセスできるようになりますが、変数は使用できません。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-121">By default, when users import your `.psm1` file, all functions in your script are accessible, but variables aren't.</span></span>

   <span data-ttu-id="c5c7c-122">PowerShell スクリプトの例は、 `Show-Calendar` この記事の最後にあります。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-122">An example PowerShell script, entitled `Show-Calendar`, is available at the end of this article.</span></span>

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

2. <span data-ttu-id="c5c7c-123">特定の関数または変数へのユーザーアクセスを制御するには、スクリプトの最後に[export-modulemember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-123">To control user access to certain functions or variables, call [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) at the end of your script.</span></span>

   <span data-ttu-id="c5c7c-124">記事の下部にあるコード例には、既定で公開される関数が1つだけあります。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-124">The example code at the bottom of the article has only one function, which by default would be exposed.</span></span> <span data-ttu-id="c5c7c-125">ただし、次のコードに示すように、公開する関数を明示的に呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-125">However, it's recommended you explicitly call out which functions you wish to expose, as described in the following code:</span></span>

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   <span data-ttu-id="c5c7c-126">モジュールマニフェストを使用してインポートされたものを制限できます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-126">You can restrict what's imported using a module manifest.</span></span> <span data-ttu-id="c5c7c-127">詳細については、「 [Powershell モジュールをインポート](./importing-a-powershell-module.md)する」および「 [powershell モジュールマニフェストを記述する方法](./how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-127">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [How to Write a PowerShell Module Manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

3. <span data-ttu-id="c5c7c-128">独自のモジュールで読み込む必要があるモジュールがある場合は `Import-Module` 、モジュールの上部にあるを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-128">If you have modules that your own module needs to load, you can use `Import-Module`, at the top of your module.</span></span>

   <span data-ttu-id="c5c7c-129">`Import-Module`コマンドレットは、ターゲットモジュールをシステムにインポートします。このコマンドレットは、モジュールをインストールする手順の後の段階で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-129">The `Import-Module` cmdlet imports a targeted module onto a system, and can be used at a later point in the procedure to install your own module.</span></span> <span data-ttu-id="c5c7c-130">この記事の下部にあるサンプルコードでは、インポートモジュールは使用しません。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-130">The sample code at the bottom of this article doesn't use any import modules.</span></span> <span data-ttu-id="c5c7c-131">ただし、その場合は、次のコードに示すように、ファイルの先頭に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-131">But if it did, they would be listed at the top of the file, as shown in the following code:</span></span>

   ```powershell
   Import-Module GenericModule
   ```

4. <span data-ttu-id="c5c7c-132">PowerShell ヘルプシステムにモジュールを記述するには、ファイル内で標準のヘルプコメントを使用するか、追加のヘルプファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-132">To describe your module to the PowerShell Help system, you can either use standard help comments inside the file, or create an additional Help file.</span></span>

   <span data-ttu-id="c5c7c-133">この記事の下部にあるコードサンプルには、コメントのヘルプ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-133">The code sample at the bottom of this article includes the help information in the comments.</span></span> <span data-ttu-id="c5c7c-134">また、追加のヘルプコンテンツを含む拡張 XML ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-134">You could also write expanded XML files that contain additional help content.</span></span> <span data-ttu-id="c5c7c-135">詳細については、「 [Windows PowerShell モジュールのヘルプの作成](./writing-help-for-windows-powershell-modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-135">For more information, see [Writing Help for Windows PowerShell Modules](./writing-help-for-windows-powershell-modules.md).</span></span>

5. <span data-ttu-id="c5c7c-136">モジュールと共にパッケージ化する追加のモジュール、XML ファイル、またはその他のコンテンツがある場合は、モジュールマニフェストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-136">If you have additional modules, XML files, or other content you want to package with your module, you can use a module manifest.</span></span>

   <span data-ttu-id="c5c7c-137">モジュールマニフェストは、他のモジュールの名前、ディレクトリレイアウト、バージョン管理番号、作成者データ、およびその他の情報を含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-137">A module manifest is a file that contains the names of other modules, directory layouts, versioning numbers, author data, and other pieces of information.</span></span> <span data-ttu-id="c5c7c-138">PowerShell では、モジュールマニフェストファイルを使用して、ソリューションの編成とデプロイを行います。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-138">PowerShell uses the module manifest file to organize and deploy your solution.</span></span> <span data-ttu-id="c5c7c-139">詳細については、「 [PowerShell モジュールマニフェストを記述する方法](./how-to-write-a-powershell-module-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-139">For more information, see [How to write a PowerShell module manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

6. <span data-ttu-id="c5c7c-140">モジュールをインストールして実行するには、適切な PowerShell パスのいずれかにモジュールを保存し、を使用し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-140">To install and run your module, save the module to one of the appropriate PowerShell paths, and use `Import-Module`.</span></span>

   <span data-ttu-id="c5c7c-141">モジュールをインストールできるパスは、グローバル変数に格納されてい `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-141">The paths where you can install your module are located in the `$env:PSModulePath` global variable.</span></span> <span data-ttu-id="c5c7c-142">たとえば、システムにモジュールを保存するための一般的なパスは、のようになり `%SystemRoot%/users/<user>/Documents/PowerShell/Modules/<moduleName>` ます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-142">For example, a common path to save a module on a system would be `%SystemRoot%/users/<user>/Documents/PowerShell/Modules/<moduleName>`.</span></span> <span data-ttu-id="c5c7c-143">ファイルが1つしかない場合でも、スクリプトモジュールと同じ名前を使用するモジュール用のディレクトリを作成してください `.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-143">Be sure to create a directory for your module that uses the same name as the script module, even if it's only a single `.psm1` file.</span></span> <span data-ttu-id="c5c7c-144">これらのパスのいずれかにモジュールを保存していない場合は、モジュールの場所をコマンドで指定する必要があり `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-144">If you didn't save your module to one of these paths, you would have to specify the module's location in the `Import-Module` command.</span></span> <span data-ttu-id="c5c7c-145">それ以外の場合、PowerShell はモジュールを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-145">Otherwise, PowerShell wouldn't be able to find the module.</span></span>

   <span data-ttu-id="c5c7c-146">PowerShell 3.0 以降では、いずれかの PowerShell モジュールパスにモジュールを配置した場合、明示的にインポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-146">Starting with PowerShell 3.0, if you've placed your module in one of the PowerShell module paths, you don't need to explicitly import it.</span></span> <span data-ttu-id="c5c7c-147">ユーザーが関数を呼び出したときに、モジュールが自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-147">Your module is automatically loaded when a user calls your function.</span></span> <span data-ttu-id="c5c7c-148">モジュールパスの詳細については、「 [PowerShell モジュールをインポートする](./importing-a-powershell-module.md)」および「 [PSModulePath インストールパスを変更](./modifying-the-psmodulepath-installation-path.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-148">For more information about the module path, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [Modifying the PSModulePath Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

7. <span data-ttu-id="c5c7c-149">現在の PowerShell セッションでアクティブなサービスからモジュールを削除するには、[モジュールの削除](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-149">To remove a module from active service in the current PowerShell session, use [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span></span>

   > [!NOTE]
   > <span data-ttu-id="c5c7c-150">`Remove-Module`現在の PowerShell セッションからモジュールを削除しますが、モジュールをアンインストールしたり、モジュールのファイルを削除したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-150">`Remove-Module` removes a module from the current PowerShell session, but doesn't uninstall the module or delete the module's files.</span></span>

## <a name="show-calendar-code-example"></a><span data-ttu-id="c5c7c-151">カレンダーのコード例の表示</span><span class="sxs-lookup"><span data-stu-id="c5c7c-151">Show-Calendar code example</span></span>

<span data-ttu-id="c5c7c-152">次の例は、という名前の単一の関数を含むスクリプトモジュールです `Show-Calendar` 。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-152">The following example is a script module that contains a single function named `Show-Calendar`.</span></span> <span data-ttu-id="c5c7c-153">この関数は、カレンダーの視覚的な表現を表示します。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-153">This function displays a visual representation of a calendar.</span></span> <span data-ttu-id="c5c7c-154">このサンプルには、概要、説明、パラメーター値、およびコードの PowerShell ヘルプ文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-154">The sample contains the PowerShell Help strings for the synopsis, description, parameter values, and code.</span></span> <span data-ttu-id="c5c7c-155">モジュールがインポートされると、 `Export-ModuleMember` コマンドによっ `Show-Calendar` て、関数がモジュールメンバーとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="c5c7c-155">When the module is imported, the `Export-ModuleMember` command ensures that the `Show-Calendar` function is exported as a module member.</span></span>

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
