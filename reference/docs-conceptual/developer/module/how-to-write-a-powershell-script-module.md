---
title: PowerShell スクリプトモジュールを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 11/21/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed7645ea-5e52-4a45-81a7-aa3c2d605cde
caps.latest.revision: 16
ms.openlocfilehash: 7742eedd67283535b9e5898adc74d0d48faf68fe
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74416267"
---
# <a name="how-to-write-a-powershell-script-module"></a>PowerShell スクリプト モジュールを記述する方法

スクリプトモジュールは、`.psm1` の拡張機能に保存されている有効な PowerShell スクリプトです。 この拡張機能により、PowerShell エンジンは、ファイルでルールとモジュールコマンドレットを使用できるようになります。 これらの機能のほとんどは、他のシステムにコードをインストールしたり、スコープを管理したりできるようにするために用意されています。 さらに複雑なインストールとソリューションを記述するモジュールマニフェストファイルを使用することもできます。

## <a name="writing-a-powershell-script-module"></a>PowerShell スクリプトモジュールの作成

スクリプトモジュールを作成するには、有効な PowerShell スクリプトを `.psm1` ファイルに保存します。 スクリプトと、それが格納されているディレクトリは、同じ名前を使用する必要があります。 たとえば、`MyPsScript.psm1` という名前のスクリプトは `MyPsScript`という名前のディレクトリに格納されます。

モジュールのディレクトリは、`$env:PSModulePath`で指定されたパスにある必要があります。 モジュールのディレクトリには、スクリプトを実行するために必要なすべてのリソースと、PowerShell に記述されたモジュールマニフェストファイルを含めることができます。

## <a name="create-a-basic-powershell-module"></a>基本的な PowerShell モジュールを作成する

次の手順では、PowerShell モジュールを作成する方法について説明します。

1. `.psm1` 拡張機能を使用して PowerShell スクリプトを保存します。 スクリプトとスクリプトを保存するディレクトリに同じ名前を使用します。

   `.psm1` 拡張機能を使用してスクリプトを保存すると、モジュールのコマンドレット ( [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)など) を使用できることになります。 モジュールコマンドレットは、主に、他のユーザーのシステムにコードをインポートしてエクスポートできるようにするために存在します。 代替ソリューションとして、コードを他のシステムに読み込んでから、そのコードをアクティブメモリに変換することができます。これはスケーラブルなソリューションではありません。 詳細については、「 [Windows PowerShell モジュールに](./understanding-a-windows-powershell-module.md#module-cmdlets-and-variables)ついて」を参照してください。
   既定では、ユーザーが `.psm1` ファイルをインポートすると、スクリプト内のすべての関数にアクセスできるようになりますが、変数は使用できません。

   PowerShell スクリプトの例 (`Show-Calendar`) は、この記事の最後にあります。

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

2. 特定の関数または変数へのユーザーアクセスを制御するには、スクリプトの最後に[export-modulemember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember)を呼び出します。

   記事の下部にあるコード例には、既定で公開される関数が1つだけあります。 ただし、次のコードに示すように、公開する関数を明示的に呼び出すことをお勧めします。

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   モジュールマニフェストを使用してインポートされたものを制限できます。 詳細については、「 [Powershell モジュールをインポート](./importing-a-powershell-module.md)する」および「 [powershell モジュールマニフェストを記述する方法](./how-to-write-a-powershell-module-manifest.md)」を参照してください。

3. 独自のモジュールで読み込む必要があるモジュールがある場合は、モジュールの上部にある `Import-Module`を使用できます。

   `Import-Module` コマンドレットは、対象となるモジュールをシステムにインポートし、独自のモジュールをインストールする手順の後の段階で使用できます。 この記事の下部にあるサンプルコードでは、インポートモジュールは使用しません。 ただし、その場合は、次のコードに示すように、ファイルの先頭に一覧表示されます。

   ```powershell
   Import-Module GenericModule
   ```

4. PowerShell ヘルプシステムにモジュールを記述するには、ファイル内で標準のヘルプコメントを使用するか、追加のヘルプファイルを作成します。

   この記事の下部にあるコードサンプルには、コメントのヘルプ情報が含まれています。 また、追加のヘルプコンテンツを含む拡張 XML ファイルを作成することもできます。 詳細については、「 [Windows PowerShell モジュールのヘルプの作成](./writing-help-for-windows-powershell-modules.md)」を参照してください。

5. モジュールと共にパッケージ化する追加のモジュール、XML ファイル、またはその他のコンテンツがある場合は、モジュールマニフェストを使用できます。

   モジュールマニフェストは、他のモジュールの名前、ディレクトリレイアウト、バージョン管理番号、作成者データ、およびその他の情報を含むファイルです。 PowerShell では、モジュールマニフェストファイルを使用して、ソリューションの編成とデプロイを行います。 詳細については、「 [PowerShell モジュールマニフェストを記述する方法](./how-to-write-a-powershell-module-manifest.md)」を参照してください。

6. モジュールをインストールして実行するには、適切な PowerShell パスのいずれかにモジュールを保存し、`Import-Module`を使用します。

   モジュールをインストールできるパスは、`$env:PSModulePath` グローバル変数に格納されています。 たとえば、システムにモジュールを保存するための一般的なパスは、`%SystemRoot%/users/<user>/Documents/PowerShell/Modules/<moduleName>`ます。 スクリプトモジュールと同じ名前を使用するモジュール用のディレクトリを作成してください。これは、1つの `.psm1` ファイルである場合でも同様です。 これらのパスのいずれかにモジュールを保存していない場合は、`Import-Module` コマンドでモジュールの場所を指定する必要があります。 それ以外の場合、PowerShell はモジュールを見つけることができません。

   PowerShell 3.0 以降では、いずれかの PowerShell モジュールパスにモジュールを配置した場合、明示的にインポートする必要はありません。 ユーザーが関数を呼び出したときに、モジュールが自動的に読み込まれます。 モジュールパスの詳細については、「 [PowerShell モジュールをインポートする](./importing-a-powershell-module.md)」および「 [PSModulePath インストールパスを変更](./modifying-the-psmodulepath-installation-path.md)する」を参照してください。

7. 現在の PowerShell セッションでアクティブなサービスからモジュールを削除するには、[モジュールの削除](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)を使用します。

   > [!NOTE]
   > `Remove-Module` は、現在の PowerShell セッションからモジュールを削除しますが、モジュールをアンインストールしたり、モジュールのファイルを削除したりすることはありません。

## <a name="show-calendar-code-example"></a>カレンダーのコード例の表示

次の例は、`Show-Calendar`という名前の関数を1つ含むスクリプトモジュールです。 この関数は、カレンダーの視覚的な表現を表示します。 このサンプルには、概要、説明、パラメーター値、およびコードの PowerShell ヘルプ文字列が含まれています。 モジュールをインポートすると、`Export-ModuleMember` コマンドによって、`Show-Calendar` 関数がモジュールメンバーとしてエクスポートされます。

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
