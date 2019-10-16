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
# <a name="how-to-write-a-powershell-script-module"></a>PowerShell スクリプト モジュールを記述する方法

スクリプトモジュールは、基本的には hbase-runner.psm1 拡張子で保存された有効な PowerShell スクリプトです。 この拡張機能により、PowerShell エンジンは、ファイルで多数の規則とコマンドレットを使用できるようになります。 これらの機能のほとんどは、他のシステムにコードをインストールしたり、スコープを管理したりできるようにするために用意されています。 モジュールマニフェストファイルを使用することもできます。これにより、さらに複雑なインストールとソリューションを記述できます。

## <a name="writing-a-powershell-script-module"></a>PowerShell スクリプトモジュールの作成

スクリプトモジュールを作成するには、有効な PowerShell スクリプトを hbase-runner.psm1 ファイルに保存し、そのファイルを PowerShell が検出できる場所にあるディレクトリに保存します。 このフォルダーには、スクリプトを実行するために必要なリソースと、PowerShell に記述されているモジュールの動作を示すマニフェストファイルを配置することもできます。

#### <a name="to-create-a-basic-powershell-module"></a>基本的な PowerShell モジュールを作成するには

1. 既存の PowerShell スクリプトを取得し、hbase-runner.psm1 拡張子を付けてスクリプトを保存します。

   Hbase-runner.psm1 拡張子を使用してスクリプトを保存すると、モジュールのコマンドレット (モジュールの[インポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)など) を使用できることになります。 これらのコマンドレットは主に、他のユーザーのシステムに簡単にコードをインポートしてエクスポートできるようにするために用意されています。 (代替ソリューションとしては、他のシステムでコードを読み込んでから、そのコードをアクティブメモリにドットソースします。これは、特にスケーラブルなソリューションではありません)。詳細については、「 [Windows PowerShell モジュール](./understanding-a-windows-powershell-module.md)」の「**モジュールのコマンドレットと変数**」セクションを参照してください。既定では、hbase-runner.psm1 ファイルをインポートしたユーザーはスクリプト内のすべての関数にアクセスできますが、プロパティは使用できません。

   PowerShell スクリプトの例 (@no__t 0) は、このトピックの最後にあります。

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

2. 特定の関数またはプロパティへのユーザーのアクセスを制御するには、スクリプトの最後に[export-modulemember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember)を呼び出します。

   ページの下部にあるコード例には、既定で公開される関数が1つだけあります。 ただし、次のコードに示すように、公開する関数を明示的に呼び出すことをお勧めします。

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   モジュールマニフェストを使用してインポートされる内容を制限することもできます。 詳細については、「 [Powershell モジュールをインポート](./importing-a-powershell-module.md)する」および「 [powershell モジュールマニフェストを記述する方法](./how-to-write-a-powershell-module-manifest.md)」を参照してください。

3. 独自のモジュールで読み込む必要があるモジュールがある場合は、独自のモジュールの上部にある `Import-Module` を呼び出すことによって使用できます。

   `Import-Module` は、対象となるモジュールをシステムにインポートするコマンドレットです。 このため、独自のモジュールをインストールする手順の後の段階でも使用されます。 このページの下部にあるサンプルコードでは、インポートモジュールは使用されません。 使用されていた場合は、次のコードに示すように、ファイルの先頭に一覧表示されます。

   ```powershell
   Import-Module GenericModule
   ```

4. PowerShell ヘルプシステムにモジュールを記述するには、ファイル内で標準のヘルプコメントを使用するか、追加のヘルプファイルを作成します。

   このトピックの下部にあるコードサンプルには、コメントのヘルプ情報が含まれています。 また、追加のヘルプコンテンツを含む拡張 XML ファイルを作成することもできます。 詳細については、「 [Windows PowerShell モジュールのヘルプの作成](./writing-help-for-windows-powershell-modules.md)」を参照してください。

5. モジュールと共にパッケージ化する追加のモジュール、XML ファイル、またはその他のコンテンツがある場合は、モジュールマニフェストを使用して実行できます。

   モジュールマニフェストは、他のモジュールの名前、ディレクトリレイアウト、バージョン管理番号、作成者データ、およびその他の情報を含むファイルです。 PowerShell では、モジュールマニフェストファイルを使用して、ソリューションの編成とデプロイを行います。 ただし、この例では比較的単純な性質があるため、マニフェストファイルは必要ありませんでした。 詳細については、「[モジュールマニフェスト](./how-to-write-a-powershell-module-manifest.md)」を参照してください。

6. モジュールをインストールして実行するには、適切な PowerShell パスのいずれかにモジュールを保存し、`Import-Module` を呼び出します。

   モジュールをインストールできるパスは、@no__t 0 のグローバル変数に格納されています。 たとえば、システムにモジュールを保存するための一般的なパスは、0 @no__t になります。 Hbase-runner.psm1 ファイルである場合でも、モジュールが存在するフォルダーを必ず作成してください。 これらのパスのいずれかにモジュールを保存しなかった場合は、`Import-Module` への呼び出しでモジュールの場所を渡す必要があります。 (それ以外の場合、PowerShell はそれを見つけることができません)。PowerShell 3.0 以降では、いずれかの PowerShell モジュールパスにモジュールを配置した場合、明示的にインポートする必要はありません。 ユーザーが関数を呼び出したときに、モジュールが自動的に読み込まれます。
   モジュールパスの詳細については、「PowerShell モジュールと[PSModulePath 環境変数](./modifying-the-psmodulepath-installation-path.md)[のインポート](./importing-a-powershell-module.md)」を参照してください。

7. アクティブなサービスからモジュールを削除するには、モジュールの[削除](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)を呼び出します。

   モジュールは、モジュールファイルを保存した場所から削除するのではなく、アクティブなメモリからモジュールを[削除すること](/powershell/module/Microsoft.PowerShell.Core/Remove-Module)に注意してください。

### <a name="show-calendar-code-example"></a>カレンダーのコード例の表示

次の例は、`Show-Calendar` という名前の単一の関数を含む単純なスクリプトモジュールです。
この関数は、カレンダーの視覚的な表現を表示します。 また、このサンプルには、概要、説明、パラメーター値、および例の PowerShell ヘルプ文字列が含まれています。 コードの最後の行では、モジュールをインポートするときに、@no__t 0 関数がモジュールメンバーとしてエクスポートされることに注意してください。

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
