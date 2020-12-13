---
ms.date: 09/12/2016
ms.topic: reference
title: コメント ベースのヘルプの例
description: コメント ベースのヘルプの例
ms.openlocfilehash: 35fe9103a261483c56af629f620dbd6b3c642e68
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667642"
---
# <a name="examples-of-comment-based-help"></a><span data-ttu-id="2c943-103">コメント ベースのヘルプの例</span><span class="sxs-lookup"><span data-stu-id="2c943-103">Examples of Comment-Based Help</span></span>

<span data-ttu-id="2c943-104">このトピックには、スクリプトや関数にコメントベースのヘルプを使用する方法を示す例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c943-104">This topic includes example that demonstrate how to use comment-based help for scripts and functions.</span></span>

## <a name="example-1-comment-based-help-for-a-function"></a><span data-ttu-id="2c943-105">例 1: 関数のヘルプを Comment-Based</span><span class="sxs-lookup"><span data-stu-id="2c943-105">Example 1: Comment-Based Help for a Function</span></span>

 <span data-ttu-id="2c943-106">次のサンプル関数には、コメントベースのヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c943-106">The following sample function includes comment-based Help.</span></span>

```powershell
function Add-Extension
{
    param ([string]$Name,[string]$Extension = "txt")
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.

        .DESCRIPTION
        Adds a file name extension to a supplied name.
        Takes any strings for the file name or extension.

        .PARAMETER Name
        Specifies the file name.

        .PARAMETER Extension
        Specifies the extension. "Txt" is the default.

        .INPUTS
        None. You cannot pipe objects to Add-Extension.

        .OUTPUTS
        System.String. Add-Extension returns a string with the extension or file name.

        .EXAMPLE
        C:\PS> extension -name "File"
        File.txt

        .EXAMPLE
        C:\PS> extension -name "File" -extension "doc"
        File.doc

        .EXAMPLE
        C:\PS> extension "File" "doc"
        File.doc

        .LINK
        Online version: http://www.fabrikam.com/extension.html

        .LINK
        Set-Item
    #>
}
```

<span data-ttu-id="2c943-107">次の出力は、 `Get-Help` 関数のヘルプを表示するコマンドの結果を示して `Add-Extension` います。</span><span class="sxs-lookup"><span data-stu-id="2c943-107">The following output shows the results of a `Get-Help` command that displays the help for the `Add-Extension` function.</span></span>

```powershell
C:\PS> get-help add-extension -full
```

```Output
        NAME
            Add-Extension

        SYNOPSIS
            Adds a file name extension to a supplied name.

        SYNTAX
            Add-Extension [[-Name] <String>] [[-Extension] <String>] [<CommonParameters>]

        DESCRIPTION
            Adds a file name extension to a supplied name. Takes any strings for the file name or extension.

        PARAMETERS
           -Name
               Specifies the file name.

               Required?                    false
               Position?                    0
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

           -Extension
               Specifies the extension. "Txt" is the default.

               Required?                    false
               Position?                    1
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

            <CommonParameters>
               This cmdlet supports the common parameters: -Verbose, -Debug,
               -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
               -OutBuffer and -OutVariable. For more information, type
               "get-help about_commonparameters".

        INPUTS
            None. You cannot pipe objects to Add-Extension.

        OUTPUTS
            System.String. Add-Extension returns a string with the extension or file name.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> extension -name "File"
            File.txt

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> extension -name "File" -extension "doc"
            File.doc

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> extension "File" "doc"
            File.doc

        RELATED LINKS
            Online version: http://www.fabrikam.com/extension.html
            Set-Item
```

## <a name="example-2-comment-based-help-for-a-script"></a><span data-ttu-id="2c943-108">例 2: スクリプトのヘルプを Comment-Based する</span><span class="sxs-lookup"><span data-stu-id="2c943-108">Example 2: Comment-Based Help for a Script</span></span>

<span data-ttu-id="2c943-109">次のサンプル関数には、コメントベースのヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c943-109">The following sample function includes comment-based Help.</span></span>

<span data-ttu-id="2c943-110">終了とステートメントの間に空白行があることに注意して **#>** `Param` ください。</span><span class="sxs-lookup"><span data-stu-id="2c943-110">Notice the blank lines between the closing **#>** and the `Param` statement.</span></span> <span data-ttu-id="2c943-111">ステートメントが含まれていないスクリプトでは、 `Param` ヘルプトピックの最後のコメントと最初の関数宣言の間に、少なくとも2つの空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="2c943-111">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the Help topic and the first function declaration.</span></span> <span data-ttu-id="2c943-112">これらの空白行がない場合、はスクリプトでは `Get-Help` なく関数にヘルプトピックを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="2c943-112">Without these blank lines, `Get-Help` associates the Help topic with the function, instead of the script.</span></span>

```powershell
<#
  .SYNOPSIS
  Performs monthly data updates.

  .DESCRIPTION
  The Update-Month.ps1 script updates the registry with new data generated
  during the past month and generates a report.

  .PARAMETER InputPath
  Specifies the path to the CSV-based input file.

  .PARAMETER OutputPath
  Specifies the name and path for the CSV-based output file. By default,
  MonthlyUpdates.ps1 generates a name from the date and time it runs, and
  saves the output in the local directory.

  .INPUTS
  None. You cannot pipe objects to Update-Month.ps1.

  .OUTPUTS
  None. Update-Month.ps1 does not generate any output.

  .EXAMPLE
  C:\PS> .\Update-Month.ps1

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
```

<span data-ttu-id="2c943-113">次のコマンドは、スクリプトのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="2c943-113">The following command gets the script Help.</span></span> <span data-ttu-id="2c943-114">スクリプトは Path 環境変数に示されているディレクトリにないため、スクリプトヘルプを `Get-Help` 取得するコマンドではスクリプトパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c943-114">Because the script is not in a directory that is listed in the Path environment variable, the `Get-Help` command that gets the script Help must specify the script path.</span></span>

```powershell
C:\PS> get-help c:\ps-test\update-month.ps1 -full
```

```Output
            NAME
                C:\ps-test\Update-Month.ps1

            SYNOPSIS
                Performs monthly data updates.

            SYNTAX
                C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
                <String>] [<CommonParameters>]

            DESCRIPTION
                The Update-Month.ps1 script updates the registry with new data
                generated during the past month and generates a report.

            PARAMETERS
               -InputPath
                   Specifies the path to the CSV-based input file.

                   Required?                    true
                   Position?                    0
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               -OutputPath
                   Specifies the name and path for the CSV-based output file. By
                   default, MonthlyUpdates.ps1 generates a name from the date
                   and time it runs, and saves the output in the local directory.

                   Required?                    false
                   Position?                    1
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               <CommonParameters>
                   This cmdlet supports the common parameters: -Verbose, -Debug,
                   -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
                   -OutBuffer and -OutVariable. For more information, type,
                   "get-help about_commonparameters".

            INPUTS
                   None. You cannot pipe objects to Update-Month.ps1.

            OUTPUTS
                   None. Update-Month.ps1 does not generate any output.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> .\Update-Month.ps1

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
            C:\Reports\2009\January.csv

            RELATED LINKS
```

## <a name="example-3-parameter-descriptions-in-a-param-statement"></a><span data-ttu-id="2c943-115">例 3: Param ステートメント内のパラメーターの説明</span><span class="sxs-lookup"><span data-stu-id="2c943-115">Example 3: Parameter Descriptions in a Param Statement</span></span>

<span data-ttu-id="2c943-116">この例で `Param` は、関数またはスクリプトのステートメントでパラメーターの説明を挿入する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2c943-116">This example shows how to insert parameter descriptions in the `Param` statement of a function or script.</span></span> <span data-ttu-id="2c943-117">この形式は、パラメーターの説明が brief の場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2c943-117">This format is most useful when the parameter descriptions are brief.</span></span>

```powershell
function Add-Extension
{
    param
    (
        [string]
        # Specifies the file name.
        $name,

        [string]
        # Specifies the file name extension. "Txt" is the default.
        $extension = "txt"
    )
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.
...
    #>
```

<span data-ttu-id="2c943-118">結果は、例1の結果と同じです。</span><span class="sxs-lookup"><span data-stu-id="2c943-118">The results are the same as the results for Example 1.</span></span> <span data-ttu-id="2c943-119">`Get-Help` パラメーターの説明は、キーワードが付いているかのように解釈され `.Parameter` ます。</span><span class="sxs-lookup"><span data-stu-id="2c943-119">`Get-Help` interprets the parameter descriptions as though they were accompanied by the `.Parameter` keyword.</span></span>

## <a name="example-4--redirecting-to-an-xml-file"></a><span data-ttu-id="2c943-120">例 4: XML ファイルへのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="2c943-120">Example 4:  Redirecting to an XML File</span></span>

<span data-ttu-id="2c943-121">関数とスクリプトの XML ベースのヘルプトピックを記述できます。</span><span class="sxs-lookup"><span data-stu-id="2c943-121">You can write XML-based Help topics for functions and scripts.</span></span> <span data-ttu-id="2c943-122">コメントベースのヘルプは実装が簡単ですが、ヘルプコンテンツをより細かく制御する場合や、ヘルプトピックを複数の言語に変換する場合は、XML ベースのヘルプが必要です。次の例は、スクリプトの最初の数行を示して `Update-Month.ps1` います。</span><span class="sxs-lookup"><span data-stu-id="2c943-122">Although comment-based Help is easier to implement, XML-based Help is required if you want more precise control over Help content or if you are translating Help topics into multiple languages.The following example shows the first few lines of the `Update-Month.ps1` script.</span></span> <span data-ttu-id="2c943-123">スクリプトでは、キーワードを使用して、 `.ExternalHelp` スクリプトの XML ベースのヘルプトピックへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c943-123">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based Help topic for the script.</span></span>

```powershell
#  .ExternalHelp C:\MyScripts\Update-Month-Help.xml

    param ([string]$InputPath, [string]$OutPutPath)

    function Get-Data { }
```

<span data-ttu-id="2c943-124">次の例は、関数でキーワードを使用する方法を示して `.ExternalHelp` います。</span><span class="sxs-lookup"><span data-stu-id="2c943-124">The following example shows the use of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
    param ([string] $name, [string]$extension = "txt")
    $name = $name + "." + $extension
    $name

    # .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

## <a name="example-5--redirecting-to-a-different-help-topic"></a><span data-ttu-id="2c943-125">例 5: 別のヘルプトピックへのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="2c943-125">Example 5:  Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="2c943-126">次のコードは、PowerShell の組み込み関数の先頭から抜粋したもので、一度 `Help` に1画面のヘルプテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="2c943-126">The following code is an excerpt from the beginning of the built-in `Help` function in PowerShell, which displays one screen of Help text at a time.</span></span> <span data-ttu-id="2c943-127">Get-Help コマンドレットのヘルプトピックでは Help 関数について説明しているので、Help 関数はキーワードとキーワードを使用して、 `.ForwardHelpTargetName` `.ForwardHelpCategory` ユーザーを Get-Help コマンドレットヘルプトピックにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="2c943-127">Because the Help topic for the Get-Help cmdlet describes the Help function, the Help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the Get-Help cmdlet Help topic.</span></span>

```powershell
function help
{

    <#
      .FORWARDHELPTARGETNAME Get-Help
      .FORWARDHELPCATEGORY Cmdlet
    #>
    [CmdletBinding(DefaultParameterSetName='AllUsersView')]
    param(
            [Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
            [System.String]
            ${Name},
    ...
```

<span data-ttu-id="2c943-128">次のコマンドでは、この機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c943-128">The following command uses this feature.</span></span> <span data-ttu-id="2c943-129">ユーザーが関数のコマンドを入力すると `Get-Help` `Help` 、によってコマンド `Get-Help` レットのヘルプトピックが表示され `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="2c943-129">When a user types a `Get-Help` command for the `Help` function, `Get-Help` displays the Help topic for the `Get-Help` cmdlet.</span></span>

```powershell
C:\PS> get-help help
```

```Output
            NAME
                Get-Help

            SYNOPSIS
                Displays information about Windows PowerShell cmdlets and concepts.
            ...
```
