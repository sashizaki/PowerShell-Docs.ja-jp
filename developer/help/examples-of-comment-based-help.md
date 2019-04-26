---
title: コメント ベースのヘルプの例 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 868194a2-17e9-4184-bc36-c04a33f26494
caps.latest.revision: 4
ms.openlocfilehash: 30e98bfcf06b1720005a73ee8294aeba7e1ae066
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083503"
---
# <a name="examples-of-comment-based-help"></a><span data-ttu-id="51c6f-102">コメント ベースのヘルプの例</span><span class="sxs-lookup"><span data-stu-id="51c6f-102">Examples of Comment-Based Help</span></span>

<span data-ttu-id="51c6f-103">このトピックでには、スクリプトや関数のコメント ベースのヘルプを使用する方法を示す例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="51c6f-103">This topic includes example that demonstrate how to use comment-based help for scripts and functions.</span></span>

## <a name="example-1-comment-based-help-for-a-function"></a><span data-ttu-id="51c6f-104">例 1:関数のコメント ベースのヘルプ</span><span class="sxs-lookup"><span data-stu-id="51c6f-104">Example 1: Comment-Based Help for a Function</span></span>

 <span data-ttu-id="51c6f-105">次の関数サンプルにはには、コメント ベースのヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="51c6f-105">The following sample function includes comment-based Help.</span></span>

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

<span data-ttu-id="51c6f-106">次の出力は、拡張機能の追加の関数のヘルプを表示する、Get-help コマンドの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="51c6f-106">The following output shows the results of a Get-Help command that displays the help for the Add-Extension function.</span></span>

```powershell
C:\PS> get-help add-extension -full
```

```output
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

## <a name="example-2-comment-based-help-for-a-script"></a><span data-ttu-id="51c6f-107">例 2:スクリプトのコメント ベースのヘルプ</span><span class="sxs-lookup"><span data-stu-id="51c6f-107">Example 2: Comment-Based Help for a Script</span></span>

<span data-ttu-id="51c6f-108">次の関数サンプルにはには、コメント ベースのヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="51c6f-108">The following sample function includes comment-based Help.</span></span>

<span data-ttu-id="51c6f-109">終了の間の空白行に注意してください**#>** と`Param`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="51c6f-109">Notice the blank lines between the closing **#>** and the `Param` statement.</span></span> <span data-ttu-id="51c6f-110">ないスクリプトで、`Param`ステートメントでは、ヘルプ トピックの最後のコメントと最初の関数宣言の間に少なくとも 2 つの空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="51c6f-110">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the Help topic and the first function declaration.</span></span> <span data-ttu-id="51c6f-111">せず、これらの空白行は、ヘルプの表示は、ヘルプ トピックをスクリプトではなく、関数に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="51c6f-111">Without these blank lines, Get-Help associates the Help topic with the function, instead of the script.</span></span>

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

<span data-ttu-id="51c6f-112">次のコマンドは、スクリプトのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="51c6f-112">The following command gets the script Help.</span></span> <span data-ttu-id="51c6f-113">スクリプトに n がないために、Path 環境変数、スクリプトのヘルプを取得する Get-help コマンドで表示されているディレクトリは、スクリプト パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c6f-113">Because the script is not n a directory that is listed in the Path environment variable, the Get-Help command that gets the script Help must specify the script path.</span></span>

```powershell
C:\PS> get-help c:\ps-test\update-month.ps1 -full
```

```output
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

## <a name="example-3-parameter-descriptions-in-a-param-statement"></a><span data-ttu-id="51c6f-114">例 3: Param ステートメントでパラメーターの説明</span><span class="sxs-lookup"><span data-stu-id="51c6f-114">Example 3: Parameter Descriptions in a Param Statement</span></span>

<span data-ttu-id="51c6f-115">この例で parameterdescriptions を挿入する方法を示して、`Param`関数またはスクリプトのステートメント。</span><span class="sxs-lookup"><span data-stu-id="51c6f-115">This example show how to insert parameterdescriptions in the `Param` statement of a function or script.</span></span> <span data-ttu-id="51c6f-116">この形式は、パラメーターの説明が簡単な場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51c6f-116">This format is most useful when the parameter descriptions are brief.</span></span>

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

<span data-ttu-id="51c6f-117">結果は、結果の例 1 と同じです。</span><span class="sxs-lookup"><span data-stu-id="51c6f-117">The results are the same as the results for Example 1.</span></span> <span data-ttu-id="51c6f-118">ヘルプの表示と解釈パラメーターの説明が付属していた場合と同様、`.Parameter`キーワード。</span><span class="sxs-lookup"><span data-stu-id="51c6f-118">Get-Help interprets the parameter descriptions as though they were accompanied by the `.Parameter` keyword.</span></span>

## <a name="example-4--redirecting-to-an-xml-file"></a><span data-ttu-id="51c6f-119">例 4:XML ファイルへのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="51c6f-119">Example 4:  Redirecting to an XML File</span></span>

<span data-ttu-id="51c6f-120">関数やスクリプトのヘルプ トピックを XML に基づくを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="51c6f-120">You can write XML-based Help topics for functions and scripts.</span></span> <span data-ttu-id="51c6f-121">コメント ベースのヘルプは容易に実装できますが、ヘルプ コンテンツまたは複数の言語にヘルプ トピックを変換するかどうかより細かく制御したい場合は、XML ベースのヘルプが必要です。次の例では、更新 Month.ps1 スクリプトの最初の数行を示します。</span><span class="sxs-lookup"><span data-stu-id="51c6f-121">Although comment-based Help is easier to implement, XML-based Help is required if you want more precise control over Help content or if you are translating Help topics into multiple languages.The following example shows the first few lines of the Update-Month.ps1 script.</span></span> <span data-ttu-id="51c6f-122">スクリプトを使用して、 `.ExternalHelp` XML ベース スクリプトのヘルプ トピックへのパスを指定するキーワード。</span><span class="sxs-lookup"><span data-stu-id="51c6f-122">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based Help topic for the script.</span></span>

```powershell
#  .ExternalHelp C:\MyScripts\Update-Month-Help.xml

    param ([string]$InputPath, [string]$OutPutPath)

    function Get-Data { }
```

<span data-ttu-id="51c6f-123">次の例では、使用、`.ExternalHelp`関数内でキーワード。</span><span class="sxs-lookup"><span data-stu-id="51c6f-123">The following example shows the use of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
    param ([string] $name, [string]$extension = "txt")
    $name = $name + "." + $extension
    $name

    # .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

## <a name="example-5--redirecting-to-a-different-help-topic"></a><span data-ttu-id="51c6f-124">例 5:別のヘルプ トピックへのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="51c6f-124">Example 5:  Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="51c6f-125">次のコードは、組み込みの先頭からの抜粋`Help`関数では、Windows PowerShell は、一度に 1 画面のヘルプ テキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="51c6f-125">The following code is an excerpt from the beginning of the built-in `Help` function in Windows PowerShell, which displays one screen of Help text at a time.</span></span> <span data-ttu-id="51c6f-126">ヘルプ機能を使用して、Get-help コマンドレットのヘルプ トピックでは、ヘルプ機能について説明します、ため、`.ForwardHelpTargetName`と`.ForwardHelpCategory`Get-help コマンドレットのヘルプ トピックへのユーザーをリダイレクトするキーワード。</span><span class="sxs-lookup"><span data-stu-id="51c6f-126">Because the Help topic for the Get-Help cmdlet describes the Help function, the Help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the Get-Help cmdlet Help topic.</span></span>

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

<span data-ttu-id="51c6f-127">次のコマンドは、この機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="51c6f-127">The following command uses this feature.</span></span> <span data-ttu-id="51c6f-128">ユーザーがヘルプ機能の Get-help コマンドを入力するとヘルプの表示には、Get-help コマンドレットのヘルプ トピックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51c6f-128">When a user types a Get-Help command for the Help function, Get-Help displays the Help topic for the Get-Help cmdlet.</span></span>

```powershell
C:\PS> get-help help
```

```output
            NAME
                Get-Help

            SYNOPSIS
                Displays information about Windows PowerShell cmdlets and concepts.
            ...
```