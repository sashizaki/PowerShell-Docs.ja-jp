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
# <a name="how-to-write-a-powershell-script-module"></a>PowerShell スクリプト モジュールを記述する方法

スクリプト モジュールは、基本的に、有効な PowerShell スクリプト .psm1 拡張子で保存します。 この拡張機能には、ファイルをさまざまなルールとコマンドレットを使用する PowerShell エンジンが使用できます。 これらの機能のほとんどは、スコープを管理したり、他のシステムで、コードをインストールするのにがあります。 さらに複雑なインストールとソリューションを記述できるモジュール マニフェスト ファイルを使用することもできます。

## <a name="writing-a-powershell-script-module"></a>PowerShell スクリプト モジュールの作成

スクリプト モジュールを作成するには、.psm1 ファイルに有効な PowerShell スクリプトを保存して、PowerShell が検索できる場所にあるディレクトリでそのファイルを保存します。 、スクリプトを実行する必要があるすべてのリソースを配置することもできます。 そのフォルダー内マニフェスト ファイルもを powershell モジュールのしくみについて説明します。

#### <a name="to-create-a-basic-powershell-module"></a>基本的な PowerShell モジュールを作成するには

1. 既存の PowerShell スクリプトを実行し、拡張子が .psm1 スクリプトを保存します。

   拡張機能がモジュールのコマンドレットをなど、使用できることを意味を持つ、.psm1 スクリプトが保存[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)にします。 ように、簡単にインポートし、他のユーザーのシステムにコードをエクスポートできますでは主に、これらのコマンドレットが存在します。 (代替のソリューションは、特にスケーラブルなソリューションではないアクティブ メモリに他のシステムや、ドット ソース上のコードをロードする場合が)。詳細については、次を参照してください。、**モジュールのコマンドレットと変数**セクション[Windows PowerShell モジュール](./understanding-a-windows-powershell-module.md)、既定では、スクリプト内のすべての関数がアクセスできる、.psm1 をインポートするユーザーに注意してください。プロパティは、ファイルはありません。

   Show-calendar、という PowerShell のスクリプトの例は、このトピックの最後でご利用いただけます。

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

2. 特定の関数やプロパティへのユーザー アクセスを制御する場合は、呼び出す[Export-modulemember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember)スクリプトの最後にします。

   ページの下部にあるコード例では、公開は既定では、1 つの機能があります。 ただし、次のコードの説明に従って、公開する関数を明示的に呼び出すことをお勧めします。

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   モジュール マニフェストを使用してインポートされる内容を制限することもできます。 詳細については、[PowerShell モジュールをインポートする](./importing-a-powershell-module.md)と[PowerShell モジュール マニフェストの記述方法](./how-to-write-a-powershell-module-manifest.md)を参照してください。

3. 呼び出しに使用できる独自のモジュールが読み込まれている必要があるモジュールがあれば、 `Import-Module`、独自のモジュールの上部にあります。

   `Import-Module` システム上に対象となるモジュールをインポートするコマンドレットです。 そのため、またはも使用の手順で、後でも、独自のモジュールをインストールします。 このページの下部にあるサンプル コードでは、任意のモジュールのインポートは使用しません。 ただしと同じ場合、次のコードで説明されているようには、ファイルの上部にあるリストは。

   ```powershell
   Import-Module GenericModule
   ```

4. PowerShell のヘルプ システムにモジュールを記述する場合は、これを行うファイル内の標準のヘルプのコメントまたは追加のヘルプ ファイルのいずれか。

   このトピックの下部にあるコード サンプルには、コメントにヘルプ情報が含まれます。 ために選択した場合は、追加のヘルプ コンテンツを含む XML ファイルが展開されたも記述できます。 詳細については、[書き込みための Windows PowerShell モジュール](./writing-help-for-windows-powershell-modules.md)を参照してください。

5. モジュールの追加、XML ファイル、またはモジュールにパッケージ化する他のコンテンツがある場合は、モジュール マニフェストでこれを実行できます。

   モジュール マニフェストは、他のモジュール、ディレクトリのレイアウト、バージョン番号、データを作成、および他の情報の名前を含むファイルです。 PowerShell では、モジュール マニフェスト ファイルを使用して編成し、ソリューションをデプロイします。 ただし、この例の比較的単純な性質では、マニフェスト ファイルが不要です。 詳細については、[モジュール マニフェスト](./how-to-write-a-powershell-module-manifest.md)を参照してください。

6. をインストールして、モジュールを実行するモジュールを、適切な PowerShell パスのいずれかに保存し、呼び出しを行う`Import-Module`します。

   モジュールをインストールするパスにある、`$env:PSModulePath`グローバル変数。 たとえば、システム上のモジュールを保存する共通のパスになります`%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`します。 1 つの .psm1 ファイルのみの場合でも、モジュールが存在するためのフォルダーを作成することを確認します。 これらのパスのいずれかに、モジュールを保存しなかったへの呼び出しで、モジュールの場所を渡す必要があります`Import-Module`します。 (それ以外の場合、PowerShell はできませんを検索します。)PowerShell 3.0 以降、モジュールを PowerShell モジュールのパスのいずれかに配置した場合、必要はありませんを明示的にインポートする: 関数を呼び出すユーザーのいるだけでは自動的に読み込まれます。 モジュール パスの詳細については、[PowerShell モジュールをインポートする](./importing-a-powershell-module.md)と[PSModulePath 環境変数](./modifying-the-psmodulepath-installation-path.md)を参照してください。

7. アクティブなサービスからモジュールを削除するへの呼び出しを行い[Remove-module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)します。

なお[Remove-module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)モジュールを削除します - のアクティブなメモリから実際には削除されませんが、モジュール ファイルを保存した場所からします。

### <a name="show-calendar-code-example"></a>コード例を表示

次の例は、Show-calendar という名前の 1 つの関数を含む単純なスクリプト モジュールです。 この関数は、予定表の視覚的表現を表示します。 さらに、このサンプルには、概要、説明、パラメーター値、および例のための PowerShell のヘルプ文字列が含まれています。 コードの最後の行がモジュールがインポートされるときに、Show-calendar 関数はモジュール メンバーとしてエクスポートすることを示すことに注意してください。

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
