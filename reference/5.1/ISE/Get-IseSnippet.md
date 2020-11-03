---
external help file: ISE-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/get-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IseSnippet
ms.openlocfilehash: c43dae3f178ae778d78fe3718fa85fd2635eba86
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218104"
---
# <span data-ttu-id="4eeec-103">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="4eeec-103">Get-IseSnippet</span></span>

## <span data-ttu-id="4eeec-104">概要</span><span class="sxs-lookup"><span data-stu-id="4eeec-104">SYNOPSIS</span></span>
<span data-ttu-id="4eeec-105">ユーザーが作成したスニペットを取得します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-105">Gets snippets that the user created.</span></span>

## <span data-ttu-id="4eeec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4eeec-106">SYNTAX</span></span>

```
Get-IseSnippet [<CommonParameters>]
```

## <span data-ttu-id="4eeec-107">Description</span><span class="sxs-lookup"><span data-stu-id="4eeec-107">DESCRIPTION</span></span>

<span data-ttu-id="4eeec-108">`Get-IseSnippet`コマンドレットは、ユーザーが作成した再利用可能なテキストスニペットを含む types.ps1xml ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-108">The `Get-IseSnippet` cmdlet gets the PS1XML files that contain reusable text snippets that the user created.</span></span> <span data-ttu-id="4eeec-109">Windows PowerShell Integrated Scripting Environment (ISE) でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-109">It works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="4eeec-110">コマンドレットを使用してスニペットを作成すると `New-IseSnippet` 、に `New-IseSnippet` よっ `<SnippetTitle>.Snippets.ps1xml` てディレクトリにファイルが作成さ `$home\Documents\WindowsPowerShell\Snippets` れます。</span><span class="sxs-lookup"><span data-stu-id="4eeec-110">When you use the `New-IseSnippet` cmdlet to create a snippet, `New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
<span data-ttu-id="4eeec-111">`Get-IseSnippet` スニペットディレクトリ内のスニペットファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-111">`Get-IseSnippet` gets the snippet files in the Snippets directory.</span></span>

<span data-ttu-id="4eeec-112">このコマンドレットは、コマンドレットを使用してモジュールからインポートされる組み込みのスニペットやスニペットを取得しません `Import-IseSnippet` 。</span><span class="sxs-lookup"><span data-stu-id="4eeec-112">This cmdlet does not get built-in snippets or snippets that are imported from modules through the `Import-IseSnippet` cmdlet.</span></span>

<span data-ttu-id="4eeec-113">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4eeec-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="4eeec-114">例</span><span class="sxs-lookup"><span data-stu-id="4eeec-114">EXAMPLES</span></span>

### <span data-ttu-id="4eeec-115">例 1: すべてのユーザー定義スニペットを取得する</span><span class="sxs-lookup"><span data-stu-id="4eeec-115">Example 1: Get all user-defined snippets</span></span>

<span data-ttu-id="4eeec-116">この例では、スニペットディレクトリ内のすべてのユーザー定義スニペットを取得します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-116">This example gets all user-define snippets in the Snippets directory.</span></span>

```powershell
Get-IseSnippet
```

### <span data-ttu-id="4eeec-117">例 2: すべてのユーザー定義スニペットをリモートコンピューターから共有ディレクトリにコピーする</span><span class="sxs-lookup"><span data-stu-id="4eeec-117">Example 2: Copy all user-defined snippets from remote computers to a shared directory</span></span>

<span data-ttu-id="4eeec-118">この例では、ユーザーが作成したすべてのスニペットを、リモートコンピューターのグループから共有スニペットディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4eeec-118">This example copies all of the user-created snippets from a group of remote computers to a shared Snippets directory.</span></span>

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

<span data-ttu-id="4eeec-119">`Invoke-Command``Get-IseSnippet`ファイル内のコンピューター上で実行さ `Servers.txt` れます。</span><span class="sxs-lookup"><span data-stu-id="4eeec-119">`Invoke-Command` runs `Get-IseSnippet` on the computers in the `Servers.txt` file.</span></span> <span data-ttu-id="4eeec-120">パイプライン演算子 ( `|` ) によって、スニペットファイルが `Copy-Item` コマンドレットに送信され、 **Destination** パラメーターで指定されたディレクトリにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="4eeec-120">A pipeline operator (`|`) sends the snippet files to the `Copy-Item` cmdlet, which copies them to the directory that is specified by the **Destination** parameter.</span></span>

### <span data-ttu-id="4eeec-121">例 3: ローカルコンピューター上の各スニペットのタイトルとテキストを表示する</span><span class="sxs-lookup"><span data-stu-id="4eeec-121">Example 3: Display the title and text of each snippet on a local computer</span></span>

<span data-ttu-id="4eeec-122">この例では `Get-IseSnippet` 、 `Select-Xml` コマンドレットとコマンドレットを使用して、ローカルコンピューター上の各スニペットのタイトルとテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-122">This example uses the `Get-IseSnippet` and `Select-Xml` cmdlets to display the title and text of each snippet on the local computer.</span></span>

```powershell
#Parse-Snippet Function
function Parse-Snippet {
  $SnippetFiles = Get-IseSnippet
  $SnippetNamespace = @{x="http://schemas.microsoft.com/PowerShell/Snippets"}
  foreach ($SnippetFile in $SnippetFiles) {
     Write-Host ""
     $Title = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Title" |
       ForEach-Object {$_.Node.InnerXML}
     $Text = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Script" |
       ForEach-Object {$_.Node.InnerText}
     Write-Host "Title: $Title"
     Write-Host "Text: $Text"
   }
}
```

```Output
Title: Mandatory
Text:
Param
(
  [parameter(Mandatory=True)]
  [String[]]
  $<ParameterName>
)

Title: Copyright
Text:  (c) Fabrikam, Inc. 2012
```

### <span data-ttu-id="4eeec-123">例 4: セッション内のすべてのスニペットのタイトルと説明を表示する</span><span class="sxs-lookup"><span data-stu-id="4eeec-123">Example 4: Display the title and description of all snippets in the session</span></span>

<span data-ttu-id="4eeec-124">この例では、組み込みのスニペット、ユーザー定義のスニペット、およびインポートされたスニペットを含む、セッション内のすべてのスニペットのタイトルと説明を表示します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-124">This example displays the title and description of all snippets in the session, including built-in snippets, user-defined snippets, and imported snippets.</span></span>

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

<span data-ttu-id="4eeec-125">変数は、 `$PSISE` Windows PowerShell ISE ホストプログラムを表します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-125">The `$PSISE` variable represents the Windows PowerShell ISE host program.</span></span> <span data-ttu-id="4eeec-126">変数の **Currentpowershelltab** プロパティは、 `$PSISE` 現在のセッションを表します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-126">The **CurrentPowerShellTab** property of the `$PSISE` variable represent the current session.</span></span> <span data-ttu-id="4eeec-127">**Snippets** プロパティは、現在のセッションのスニペットを表します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-127">The **Snippets** property represents snippets in the current session.</span></span>

<span data-ttu-id="4eeec-128">コマンドは、コマンド `$PSISE.CurrentPowerShellTab.Snippets` レットとは異なり、スニペットを表す **new-isesnippet** オブジェクトを返します。 `Get-IseSnippet`</span><span class="sxs-lookup"><span data-stu-id="4eeec-128">The `$PSISE.CurrentPowerShellTab.Snippets` command returns a **Microsoft.PowerShell.Host.ISE.ISESnippet** object that represents a snippet, unlike the `Get-IseSnippet` cmdlet.</span></span> <span data-ttu-id="4eeec-129">`Get-IseSnippet` スニペットファイルを表すファイルオブジェクト (system.object) を返します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-129">`Get-IseSnippet` returns a file object (System.Io.FileInfo) that represents a snippet file.</span></span>

<span data-ttu-id="4eeec-130">コマンドレットでは、 `Format-Table` テーブル内のスニペットの **displaytitle** プロパティと **Description** プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-130">The `Format-Table` cmdlet displays the **DisplayTitle** and **Description** properties of the snippets in a table.</span></span>

## <span data-ttu-id="4eeec-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4eeec-131">PARAMETERS</span></span>

### <span data-ttu-id="4eeec-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4eeec-132">CommonParameters</span></span>

<span data-ttu-id="4eeec-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4eeec-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4eeec-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eeec-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4eeec-135">入力</span><span class="sxs-lookup"><span data-stu-id="4eeec-135">INPUTS</span></span>

## <span data-ttu-id="4eeec-136">出力</span><span class="sxs-lookup"><span data-stu-id="4eeec-136">OUTPUTS</span></span>

### <span data-ttu-id="4eeec-137">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="4eeec-137">System.IO.FileInfo</span></span>

<span data-ttu-id="4eeec-138">このコマンドレットは、スニペットファイルを表すファイルオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-138">This cmdlet returns a file object that represents the snippet file.</span></span>

## <span data-ttu-id="4eeec-139">注</span><span class="sxs-lookup"><span data-stu-id="4eeec-139">NOTES</span></span>

* <span data-ttu-id="4eeec-140">`New-IseSnippet`コマンドレットは、新しいユーザーが作成したスニペットを types.ps1xml ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-140">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="4eeec-141">そのため、Windows PowerShell は、実行ポリシーが **AllSigned** または **Restricted** のセッションにこれらを追加できません。</span><span class="sxs-lookup"><span data-stu-id="4eeec-141">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted**.</span></span> <span data-ttu-id="4eeec-142">**Restricted** または **AllSigned** セッションでは、ユーザーが作成した署名されていないスニペットを作成、取得、およびインポートできますが、それらをセッションで使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="4eeec-142">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="4eeec-143">コマンドレットから返される、署名されていないユーザーが作成したスニペットを使用するには、 `Get-IseSnippet` 実行ポリシーを変更し、Windows PowerShell ISE を再起動します。</span><span class="sxs-lookup"><span data-stu-id="4eeec-143">To use unsigned user-created snippets that the `Get-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="4eeec-144">Windows PowerShell 実行ポリシーの詳細については、「[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eeec-144">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="4eeec-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4eeec-145">RELATED LINKS</span></span>

[<span data-ttu-id="4eeec-146">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="4eeec-146">New-IseSnippet</span></span>](New-IseSnippet.md)

[<span data-ttu-id="4eeec-147">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="4eeec-147">Import-IseSnippet</span></span>](Import-IseSnippet.md)
