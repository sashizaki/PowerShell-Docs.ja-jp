---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-html?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Html
ms.openlocfilehash: ffe7fe7c44258435c7ec9ddd2bab9ebeb9f6c465
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600107"
---
# <span data-ttu-id="d4aee-102">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="d4aee-102">ConvertTo-Html</span></span>

## <span data-ttu-id="d4aee-103">概要</span><span class="sxs-lookup"><span data-stu-id="d4aee-103">SYNOPSIS</span></span>
<span data-ttu-id="d4aee-104">.NET オブジェクトを、Web ブラウザーで表示できる HTML に変換します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-104">Converts .NET objects into HTML that can be displayed in a Web browser.</span></span>

## <span data-ttu-id="d4aee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d4aee-105">SYNTAX</span></span>

### <span data-ttu-id="d4aee-106">ページ (既定)</span><span class="sxs-lookup"><span data-stu-id="d4aee-106">Page (Default)</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [[-Body] <String[]>]
 [[-Head] <String[]>] [[-Title] <String>] [-As <String>] [-CssUri <Uri>] [-PostContent <String[]>]
 [-PreContent <String[]>] [-Meta <Hashtable>] [-Charset <String>] [-Transitional]
 [<CommonParameters>]
```

### <span data-ttu-id="d4aee-107">Fragment</span><span class="sxs-lookup"><span data-stu-id="d4aee-107">Fragment</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [-As <String>] [-Fragment]
 [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="d4aee-108">Description</span><span class="sxs-lookup"><span data-stu-id="d4aee-108">DESCRIPTION</span></span>

<span data-ttu-id="d4aee-109">`ConvertTo-Html`コマンドレットは、Web ブラウザーに表示できる HTML に .net オブジェクトを変換します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-109">The `ConvertTo-Html` cmdlet converts .NET objects into HTML that can be displayed in a Web browser.</span></span> <span data-ttu-id="d4aee-110">このコマンドレットを使用すると、Web ページにコマンドの出力を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-110">You can use this cmdlet to display the output of a command in a Web page.</span></span>

<span data-ttu-id="d4aee-111">のパラメーターを使用すると、 `ConvertTo-Html` オブジェクトのプロパティを選択したり、テーブルまたは一覧の形式を指定したり、HTML ページのタイトルを指定したり、オブジェクトの前後にテキストを追加したり、厳密な DTD ページではなくテーブルまたはリストフラグメントだけを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-111">You can use the parameters of `ConvertTo-Html` to select object properties, to specify a table or list format, to specify the HTML page title, to add text before and after the object, and to return only the table or list fragment, instead of a strict DTD page.</span></span>

<span data-ttu-id="d4aee-112">複数のオブジェクトをに送信すると `ConvertTo-Html` 、PowerShell によって、送信する最初のオブジェクトのプロパティに基づいてテーブル (または一覧) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-112">When you submit multiple objects to `ConvertTo-Html`, PowerShell creates the table (or list) based on the properties of the first object that you submit.</span></span> <span data-ttu-id="d4aee-113">残りのオブジェクトに指定したプロパティのいずれかがない場合は、そのオブジェクトのプロパティ値が空のセルになります。</span><span class="sxs-lookup"><span data-stu-id="d4aee-113">If the remaining objects do not have one of the specified properties, the property value of that object is an empty cell.</span></span> <span data-ttu-id="d4aee-114">残りのオブジェクトに追加のプロパティがある場合は、これらのプロパティ値は、ファイルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="d4aee-114">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

## <span data-ttu-id="d4aee-115">例</span><span class="sxs-lookup"><span data-stu-id="d4aee-115">EXAMPLES</span></span>

### <span data-ttu-id="d4aee-116">例 1: 日付を表示する web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="d4aee-116">Example 1: Create a web page to display the date</span></span>

```powershell
ConvertTo-Html -InputObject (Get-Date)
```

<span data-ttu-id="d4aee-117">このコマンドは、現在の日付のプロパティを表示する HTML ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-117">This command creates an HTML page that displays the properties of the current date.</span></span> <span data-ttu-id="d4aee-118">**InputObject** パラメーターを使用してコマンドの結果を `Get-Date` コマンドレットに送信し `ConvertTo-Html` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-118">It uses the **InputObject** parameter to submit the results of a `Get-Date` command to the `ConvertTo-Html` cmdlet.</span></span>

### <span data-ttu-id="d4aee-119">例 2: PowerShell エイリアスを表示する web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="d4aee-119">Example 2: Create a web page to display PowerShell aliases</span></span>

```powershell
Get-Alias | ConvertTo-Html | Out-File aliases.htm
Invoke-Item aliases.htm
```

<span data-ttu-id="d4aee-120">このコマンドは、現在のコンソールで PowerShell エイリアスを一覧表示する HTML ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-120">This command creates an HTML page that lists the PowerShell aliases in the current console.</span></span>

<span data-ttu-id="d4aee-121">コマンドは、コマンド `Get-Alias` レットを使用してエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-121">The command uses the `Get-Alias` cmdlet to get the aliases.</span></span> <span data-ttu-id="d4aee-122">パイプライン演算子 () を使用して、 `|` エイリアスをコマンドレットに送信します。これにより、 `ConvertTo-Html` HTML ページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-122">It uses the pipeline operator (`|`) to send the aliases to the `ConvertTo-Html` cmdlet, which creates the HTML page.</span></span> <span data-ttu-id="d4aee-123">また、コマンドレットを使用して、 `Out-File` HTML コードをファイルに送信し `aliases.htm` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-123">The command also uses the `Out-File` cmdlet to send the HTML code to the `aliases.htm` file.</span></span>

### <span data-ttu-id="d4aee-124">例 3: PowerShell イベントを表示する web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="d4aee-124">Example 3: Create a web page to display PowerShell events</span></span>

```powershell
`Get-EventLog` -LogName "Windows PowerShell" | ConvertTo-Html | Out-File pslog.htm
```

<span data-ttu-id="d4aee-125">このコマンド `pslog.htm` は、ローカルコンピューターの Windows PowerShell イベントログにイベントを表示するという名前の HTML ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-125">This command creates an HTML page called `pslog.htm` that displays the events in the Windows PowerShell event log on the local computer.</span></span>

<span data-ttu-id="d4aee-126">コマンドレットを使用して `Get-EventLog` Windows PowerShell ログ内のイベントを取得し、パイプライン演算子 () を使用して `|` イベントをコマンドレットに送信し `ConvertTo-Html` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-126">It uses the `Get-EventLog` cmdlet to get the events in the Windows PowerShell log and then uses the pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="d4aee-127">また、コマンドレットを使用して、 `Out-File` HTML コードをファイルに送信し `pslog.htm` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-127">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

<span data-ttu-id="d4aee-128">また、コマンドレットを使用して、 `Out-File` HTML コードをファイルに送信し `pslog.htm` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-128">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

### <span data-ttu-id="d4aee-129">例 4: プロセスを表示する web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="d4aee-129">Example 4: Create a web page to display processes</span></span>

```powershell
Get-Process |
  ConvertTo-Html -Property Name, Path, Company -Title "Process Information" |
    Out-File proc.htm
Invoke-Item proc.htm
```

<span data-ttu-id="d4aee-130">これらのコマンドは、ローカル コンピューター上のプロセスの名前、パス、および会社を一覧表示する HTML ページを作成し、開きます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-130">These commands create and open an HTML page that lists the name, path, and company of the processes on the local computer.</span></span>

<span data-ttu-id="d4aee-131">最初のコマンドは、 `Get-Process` コマンドレットを使用して、コンピューター上で実行されているプロセスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-131">The first command uses the `Get-Process` cmdlet to get objects that represent the processes running on the computer.</span></span> <span data-ttu-id="d4aee-132">このコマンドは、パイプライン演算子 () を使用して、 `|` プロセスオブジェクトをコマンドレットに送信し `ConvertTo-Html` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-132">The command uses the pipeline operator (`|`) to send the process objects to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="d4aee-133">このコマンドは、 **Property** パラメーターを使用して、テーブルに含めるプロセスオブジェクトの3つのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-133">The command uses the **Property** parameter to select three properties of the process objects to be included in the table.</span></span> <span data-ttu-id="d4aee-134">このコマンドは、 **title** パラメーターを使用して、HTML ページのタイトルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-134">The command uses the **Title** parameter to specify a title for the HTML page.</span></span> <span data-ttu-id="d4aee-135">また、コマンドレットを使用して、 `Out-File` 生成された HTML を Proc.htm という名前のファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-135">The command also uses the `Out-File` cmdlet to send the resulting HTML to a file named Proc.htm.</span></span>

<span data-ttu-id="d4aee-136">2番目のコマンドは、 `Invoke-Item` コマンドレットを使用して、 `Proc.htm` 既定のブラウザーでを開きます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-136">The second command uses the `Invoke-Item` cmdlet to open the `Proc.htm` in the default browser.</span></span>

### <span data-ttu-id="d4aee-137">例 5: サービスオブジェクトを表示する web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="d4aee-137">Example 5: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -CssUri "test.css"
```

```Output
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"  "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html>
<head>
<title>HTML TABLE</title>
<link rel="stylesheet" type="text/css" href="test.css" />
...
```

<span data-ttu-id="d4aee-138">このコマンドは、コマンドレットが返すサービスオブジェクトの HTML ページを作成し `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-138">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="d4aee-139">このコマンドは、 **CssUri** パラメーターを使用して、HTML ページのカスケードスタイルシートを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-139">The command uses the **CssUri** parameter to specify a cascading style sheet for the HTML page.</span></span>

<span data-ttu-id="d4aee-140">**CssUri** パラメーターを指定すると `<link rel="stylesheet" type="text/css" href="test.css">` 、結果の HTML にタグが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-140">The **CssUri** parameter adds an additional `<link rel="stylesheet" type="text/css" href="test.css">` tag to the resulting HTML.</span></span> <span data-ttu-id="d4aee-141">このタグの HREF 属性には、スタイル シートの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4aee-141">The HREF attribute in the tag contains the name of the style sheet.</span></span>

### <span data-ttu-id="d4aee-142">例 6: サービスオブジェクトを表示する web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="d4aee-142">Example 6: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -As LIST | Out-File services.htm
```

<span data-ttu-id="d4aee-143">このコマンドは、コマンドレットが返すサービスオブジェクトの HTML ページを作成し `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-143">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="d4aee-144">このコマンドは、 **As** パラメーターを使用してリスト形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-144">The command uses the **As** parameter to specify a list format.</span></span> <span data-ttu-id="d4aee-145">コマンドレットは、 `Out-File` 結果の HTML をファイルに送信し `Services.htm` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-145">The cmdlet `Out-File` sends the resulting HTML to the `Services.htm` file.</span></span>

### <span data-ttu-id="d4aee-146">例 7: 現在の日付の web テーブルを作成する</span><span class="sxs-lookup"><span data-stu-id="d4aee-146">Example 7: Create a web table for the current date</span></span>

```powershell
Get-Date | ConvertTo-Html -Fragment
```

```Output
<table>
<colgroup>...</colgroup>
<tr><th>DisplayHint</th><th>DateTime</th><th>Date</th><th>Day</th><th>DayOfWeek</th><th>DayOfYear</th><th>Hour</th>
<th>Kind</th><th>Millisecond</th><th>Minute</th><th>Month</th><th>Second</th><th>Ticks</th><th>TimeOfDay</th><th>Year</th></tr>
<tr><td>DateTime</td><td>Monday, May 05, 2008 10:40:04 AM</td><td>5/5/2008 12:00:00 AM</td><td>5</td><td>Monday</td>
<td>126</td><td>10</td><td>Local</td><td>123</td><td>40</td><td>5</td><td>4</td><td>633455808041237213</td><td>10:40:04.12
37213</td><td>2008</td></tr>
</table>
```

<span data-ttu-id="d4aee-147">このコマンドは `ConvertTo-Html` 、を使用して、現在の日付の HTML テーブルを生成します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-147">This command uses `ConvertTo-Html` to generate an HTML table of the current date.</span></span> <span data-ttu-id="d4aee-148">コマンドは、コマンド `Get-Date` レットを使用して現在の日付を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-148">The command uses the `Get-Date` cmdlet to get the current date.</span></span> <span data-ttu-id="d4aee-149">パイプライン演算子 (|) を使用して、結果をコマンドレットに送信し `ConvertTo-Html` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-149">It uses a pipeline operator (|) to send the results to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="d4aee-150">コマンドには、 `ConvertTo-Html` 出力を HTML テーブルに制限する **Fragment** パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4aee-150">The `ConvertTo-Html` command includes the **Fragment** parameter, which limits the output to an HTML table.</span></span> <span data-ttu-id="d4aee-151">その結果、`<HEAD>` や `<BODY>` タグなど、HTML ページの他の要素が省略されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-151">As a result, the other elements of an HTML page, such as the `<HEAD>` and `<BODY>` tags, are omitted.</span></span>

### <span data-ttu-id="d4aee-152">例 8: PowerShell イベントを表示するための web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="d4aee-152">Example 8: Create a web page to display PowerShell events</span></span>

```powershell
Get-EventLog -Log "Windows PowerShell" | ConvertTo-Html -Property id, level, task
```

<span data-ttu-id="d4aee-153">このコマンドは、 `Get-EventLog` コマンドレットを使用して、Windows PowerShell イベントログからイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-153">This command uses the `Get-EventLog` cmdlet to get events from the Windows PowerShell event log.</span></span>

<span data-ttu-id="d4aee-154">パイプライン演算子 () を使用して、イベントを `|` コマンドレットに送信し `ConvertTo-Html` ます。これにより、イベントが HTML 形式に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-154">It uses a pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet, which converts the events to HTML format.</span></span>

<span data-ttu-id="d4aee-155">この `ConvertTo-Html` コマンドは、 **Property** パラメーターを使用して、イベントの **ID**、 **Level**、および **Task** プロパティのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-155">The `ConvertTo-Html` command uses the **Property** parameter to select only the **ID**, **Level**, and **Task** properties of the event.</span></span>

### <span data-ttu-id="d4aee-156">例 9: 指定したサービスを表示する web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="d4aee-156">Example 9: Create a web page to display specified services</span></span>

```powershell
$htmlParams = @{
  Title = "Windows Services: Server01"
  Body = Get-Date
  PreContent = "<P>Generated by Corporate IT</P>"
  PostContent = "For details, contact Corporate IT."
}
Get-Service A* |
  ConvertTo-Html @htmlParams |
    Out-File Services.htm
Invoke-Item Services.htm
```

<span data-ttu-id="d4aee-157">このコマンドは、で始まるコンピューター上のサービスを表示する Web ページを作成して開きます。の **Title**、 **Body**、 **precontent**、および **postcontent** パラメーターを使用して `ConvertTo-Html` 、出力をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="d4aee-157">This command creates and opens a Web page that displays the services on the computer that begin with A. It uses the **Title**, **Body**, **PreContent**, and **PostContent** parameters of `ConvertTo-Html` to customize the output.</span></span>

<span data-ttu-id="d4aee-158">コマンドの最初の部分では、コマンドレットを使用して `Get-Service` 、で始まるコンピューター上のサービスを取得します。このコマンドは、パイプライン演算子 () を使用して `|` 結果を `ConvertTo-Html` コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-158">The first part of the command uses the `Get-Service` cmdlet to get the services on the computer that begin with A. The command uses a pipeline operator (`|`) to send the results to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="d4aee-159">また、コマンドレットを使用して、 `Out-File` 出力を Services.htm ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-159">The command also uses the `Out-File` cmdlet to send the output to the Services.htm file.</span></span>

<span data-ttu-id="d4aee-160">セミコロン () は、 `;` 最初のコマンドを終了し、2番目のコマンドを開始します。このコマンドは、コマンドレットを使用して、 `Invoke-Item` 既定の `Services.htm` ブラウザーでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-160">A semicolon (`;`) ends the first command and starts a second command, which uses the `Invoke-Item` cmdlet to open the `Services.htm` file in the default browser.</span></span>

### <span data-ttu-id="d4aee-161">例 10: HTML のメタプロパティと文字セットを設定する</span><span class="sxs-lookup"><span data-stu-id="d4aee-161">Example 10: Set the Meta properties and Charset of the HTML</span></span>

```powershell
Get-Service | ConvertTo-HTML -Meta @{
  refresh=10
  author="Author's Name"
  keywords="PowerShell, HTML, ConvertTo-HTML"
} -Charset "UTF-8"
```

<span data-ttu-id="d4aee-162">このコマンドは、更新、作成者、およびキーワードのメタタグを含む web ページの HTML を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-162">This command creates the HTML for a webpage with the meta tags for refresh, author, and keywords.</span></span>
<span data-ttu-id="d4aee-163">ページの文字セットが UTF-8 に設定されています</span><span class="sxs-lookup"><span data-stu-id="d4aee-163">The charset for the page is set to UTF-8</span></span>

### <span data-ttu-id="d4aee-164">例 11: HTML を XHTML 遷移 DTD に設定する</span><span class="sxs-lookup"><span data-stu-id="d4aee-164">Example 11: Set the HTML to XHTML Transitional DTD</span></span>

```powershell
Get-Service | ConvertTo-HTML -Transitional
```

<span data-ttu-id="d4aee-165">このコマンドは、返された HTML の DOCTYPE を XHTML 遷移 DTD に設定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-165">This command sets the DOCTYPE of the returned HTML to XHTML Transitional DTD</span></span>

## <span data-ttu-id="d4aee-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d4aee-166">PARAMETERS</span></span>

### <span data-ttu-id="d4aee-167">-As</span><span class="sxs-lookup"><span data-stu-id="d4aee-167">-As</span></span>

<span data-ttu-id="d4aee-168">オブジェクトがテーブルまたは一覧のどちらで書式設定されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-168">Determines whether the object is formatted as a table or a list.</span></span> <span data-ttu-id="d4aee-169">有効な値は **テーブル** と **リスト** です。</span><span class="sxs-lookup"><span data-stu-id="d4aee-169">Valid values are **Table** and **List**.</span></span> <span data-ttu-id="d4aee-170">既定値は **Table** です。</span><span class="sxs-lookup"><span data-stu-id="d4aee-170">The default value is **Table**.</span></span>

<span data-ttu-id="d4aee-171">**テーブル** 値は、PowerShell テーブル形式に似た HTML テーブルを生成します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-171">The **Table** value generates an HTML table that resembles the PowerShell table format.</span></span> <span data-ttu-id="d4aee-172">ヘッダー行には、プロパティ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-172">The header row displays the property names.</span></span> <span data-ttu-id="d4aee-173">各テーブル行は、オブジェクトを表し、各プロパティのオブジェクトの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-173">Each table row represents an object and displays the object's values for each property.</span></span>

<span data-ttu-id="d4aee-174">**List** 値は、PowerShell リスト形式に似たオブジェクトごとに2列の HTML テーブルを生成します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-174">The **List** value generates a two-column HTML table for each object that resembles the PowerShell list format.</span></span> <span data-ttu-id="d4aee-175">最初の列には、プロパティ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-175">The first column displays the property name.</span></span> <span data-ttu-id="d4aee-176">2番目の列には、プロパティ値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-176">The second column displays the property value.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Table, List

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-177">-本文</span><span class="sxs-lookup"><span data-stu-id="d4aee-177">-Body</span></span>

<span data-ttu-id="d4aee-178">開始の `<BODY>` タグの後に追加するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-178">Specifies the text to add after the opening `<BODY>` tag.</span></span> <span data-ttu-id="d4aee-179">既定では、その位置にテキストがありません。</span><span class="sxs-lookup"><span data-stu-id="d4aee-179">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-180">-Charset</span><span class="sxs-lookup"><span data-stu-id="d4aee-180">-Charset</span></span>

<span data-ttu-id="d4aee-181">開始タグに追加するテキストを指定し `<charset>` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-181">Specifies text to add to the opening `<charset>` tag.</span></span> <span data-ttu-id="d4aee-182">既定では、その位置にテキストがありません。</span><span class="sxs-lookup"><span data-stu-id="d4aee-182">By default, there is no text in that position.</span></span>

<span data-ttu-id="d4aee-183">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4aee-183">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-184">-CssUri</span><span class="sxs-lookup"><span data-stu-id="d4aee-184">-CssUri</span></span>

<span data-ttu-id="d4aee-185">HTML ファイルに適用されるカスケード スタイル シート (CSS) の Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-185">Specifies the Uniform Resource Identifier (URI) of the cascading style sheet (CSS) that is applied to the HTML file.</span></span> <span data-ttu-id="d4aee-186">URI は、出力のスタイル シートのリンクに含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-186">The URI is included in a style sheet link in the output.</span></span>

```yaml
Type: System.Uri
Parameter Sets: Page
Aliases: cu, uri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-187">-Fragment</span><span class="sxs-lookup"><span data-stu-id="d4aee-187">-Fragment</span></span>

<span data-ttu-id="d4aee-188">HTML テーブルのみを生成します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-188">Generates only an HTML table.</span></span> <span data-ttu-id="d4aee-189">HTML、HEAD、TITLE、および BODY タグは省略されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-189">The HTML, HEAD, TITLE, and BODY tags are omitted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Fragment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-190">-ヘッド</span><span class="sxs-lookup"><span data-stu-id="d4aee-190">-Head</span></span>

<span data-ttu-id="d4aee-191">`<HEAD>` タグの内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-191">Specifies the content of the `<HEAD>` tag.</span></span> <span data-ttu-id="d4aee-192">既定値は、`<title\>HTML TABLE</title>` です。</span><span class="sxs-lookup"><span data-stu-id="d4aee-192">The default is `<title\>HTML TABLE</title>`.</span></span> <span data-ttu-id="d4aee-193">**Head** パラメーターを使用すると、 **Title** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-193">If you use the **Head** parameter, the **Title** parameter is ignored.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d4aee-194">-InputObject</span></span>

<span data-ttu-id="d4aee-195">HTML で表されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-195">Specifies the objects to be represented in HTML.</span></span> <span data-ttu-id="d4aee-196">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-196">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="d4aee-197">このパラメーターを使用して、コンピューター上のすべてのサービスなど、複数のオブジェクトを送信すると、によって、 `ConvertTo-Html` コレクションまたはオブジェクトの配列のプロパティを表示するテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-197">If you use this parameter to submit multiple objects, such as all of the services on a computer, `ConvertTo-Html` creates a table that displays the properties of a collection or of an array of objects.</span></span> <span data-ttu-id="d4aee-198">個々のオブジェクトのテーブルを作成するには、パイプライン演算子を使用してオブジェクトをにパイプ処理し `ConvertTo-Html` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-198">To create a table of the individual objects, use the pipeline operator to pipe the objects to `ConvertTo-Html`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-199">-Meta</span><span class="sxs-lookup"><span data-stu-id="d4aee-199">-Meta</span></span>

<span data-ttu-id="d4aee-200">開始タグに追加するテキストを指定し `<meta>` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-200">Specifies text to add to the opening `<meta>` tag.</span></span> <span data-ttu-id="d4aee-201">既定では、その位置にテキストがありません。</span><span class="sxs-lookup"><span data-stu-id="d4aee-201">By default, there is no text in that position.</span></span>

<span data-ttu-id="d4aee-202">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4aee-202">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-203">-PostContent</span><span class="sxs-lookup"><span data-stu-id="d4aee-203">-PostContent</span></span>

<span data-ttu-id="d4aee-204">終了の `</TABLE>` タグの後に追加するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-204">Specifies text to add after the closing `</TABLE>` tag.</span></span> <span data-ttu-id="d4aee-205">既定では、その位置にテキストがありません。</span><span class="sxs-lookup"><span data-stu-id="d4aee-205">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-206">-事前コンテンツ</span><span class="sxs-lookup"><span data-stu-id="d4aee-206">-PreContent</span></span>

<span data-ttu-id="d4aee-207">開始の `<TABLE>` タグの前に追加するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-207">Specifies text to add before the opening `<TABLE>` tag.</span></span> <span data-ttu-id="d4aee-208">既定では、その位置にテキストがありません。</span><span class="sxs-lookup"><span data-stu-id="d4aee-208">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-209">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="d4aee-209">-Property</span></span>

<span data-ttu-id="d4aee-210">HTML 内のオブジェクトの指定したプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-210">Includes the specified properties of the objects in the HTML.</span></span> <span data-ttu-id="d4aee-211">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-211">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="d4aee-212">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-212">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="d4aee-213">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d4aee-213">Valid key-value pairs are:</span></span>

- <span data-ttu-id="d4aee-214">Name (または label)- `<string>` (PowerShell 6.x で追加)</span><span class="sxs-lookup"><span data-stu-id="d4aee-214">Name (or label) - `<string>` (added in PowerShell 6.x)</span></span>
- <span data-ttu-id="d4aee-215">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="d4aee-215">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="d4aee-216">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="d4aee-216">FormatString - `<string>`</span></span>
- <span data-ttu-id="d4aee-217">幅- `<int32>` -より大きい必要があります `0`</span><span class="sxs-lookup"><span data-stu-id="d4aee-217">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="d4aee-218">Alignment-値には `Left` 、、 `Center` 、またはを指定できます。 `Right`</span><span class="sxs-lookup"><span data-stu-id="d4aee-218">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="d4aee-219">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4aee-219">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-220">-Title</span><span class="sxs-lookup"><span data-stu-id="d4aee-220">-Title</span></span>

<span data-ttu-id="d4aee-221">HTML のファイルのタイトルを指定します。つまり、`<TITLE>` タグの間に表示されるテキストです。</span><span class="sxs-lookup"><span data-stu-id="d4aee-221">Specifies a title for the HTML file, that is, the text that appears between the `<TITLE>` tags.</span></span>

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-222">-移行中</span><span class="sxs-lookup"><span data-stu-id="d4aee-222">-Transitional</span></span>

<span data-ttu-id="d4aee-223">**Doctype** を **xhtml 遷移 dtd** に変更します。既定の **doctype** は **xhtml Strict dtd** です。</span><span class="sxs-lookup"><span data-stu-id="d4aee-223">Changes the **DOCTYPE** to **XHTML Transitional DTD**, Default **DOCTYPE** is **XHTML Strict DTD**.</span></span>

<span data-ttu-id="d4aee-224">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4aee-224">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4aee-225">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d4aee-225">CommonParameters</span></span>

<span data-ttu-id="d4aee-226">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d4aee-226">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d4aee-227">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4aee-227">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d4aee-228">入力</span><span class="sxs-lookup"><span data-stu-id="d4aee-228">INPUTS</span></span>

### <span data-ttu-id="d4aee-229">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="d4aee-229">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="d4aee-230">パイプを使用して任意の .NET オブジェクトをにパイプすることができ `ConvertTo-Html` ます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-230">You can pipe any .NET object to `ConvertTo-Html`.</span></span>

## <span data-ttu-id="d4aee-231">出力</span><span class="sxs-lookup"><span data-stu-id="d4aee-231">OUTPUTS</span></span>

### <span data-ttu-id="d4aee-232">System.string または System.Xml.Xmlドキュメント</span><span class="sxs-lookup"><span data-stu-id="d4aee-232">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="d4aee-233">`ConvertTo-Html` 有効な HTML を構成する一連の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-233">`ConvertTo-Html` returns series of strings that comprise valid HTML.</span></span>

## <span data-ttu-id="d4aee-234">注</span><span class="sxs-lookup"><span data-stu-id="d4aee-234">NOTES</span></span>

<span data-ttu-id="d4aee-235">このコマンドレットを使用するには、パイプを使用して1つまたは複数のオブジェクトをコマンドレットに渡します。または、 **InputObject** パラメーターを使用してオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-235">To use this cmdlet, pipe one or more objects to the cmdlet or use the **InputObject** parameter to specify the object.</span></span> <span data-ttu-id="d4aee-236">入力が複数のオブジェクトで構成されている場合、これら 2 つのメソッドの出力は大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="d4aee-236">When the input consists of multiple objects, the output of these two methods is quite different.</span></span>

- <span data-ttu-id="d4aee-237">パイプを使用して複数のオブジェクトをコマンドレットに渡した場合、PowerShell はオブジェクトをコマンドレットに一度に1つずつ送信します。</span><span class="sxs-lookup"><span data-stu-id="d4aee-237">When you pipe multiple objects to a cmdlet, PowerShell sends the objects to the cmdlet one at a time.</span></span> <span data-ttu-id="d4aee-238">その結果、によって、 `ConvertTo-Html` 個々のオブジェクトを表示するテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-238">As a result, `ConvertTo-Html` creates a table that displays the individual objects.</span></span> <span data-ttu-id="d4aee-239">たとえば、コンピューター上のプロセスをにパイプする場合、 `ConvertTo-Html` 結果のテーブルにはすべてのプロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-239">For example, if you pipe the processes on a computer to `ConvertTo-Html`, the resulting table displays all of the processes.</span></span>

- <span data-ttu-id="d4aee-240">**InputObject** パラメーターを使用して複数のオブジェクトを送信すると、は `ConvertTo-Html` これらのオブジェクトをコレクションまたは配列として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d4aee-240">When you use the **InputObject** parameter to submit multiple objects, `ConvertTo-Html` receives these objects as a collection or as an array.</span></span> <span data-ttu-id="d4aee-241">その結果、配列内の項目ではなく、配列とプロパティを表示するテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-241">As a result, it creates a table that displays the array and its properties, not the items in the array.</span></span> <span data-ttu-id="d4aee-242">たとえば、 **InputObject** を使用してコンピューター上のプロセスをに送信する場合、結果のテーブルには `ConvertTo-Html` オブジェクト配列とそのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-242">For example, if you use **InputObject** to submit the processes on a computer to `ConvertTo-Html`, the resulting table displays an object array and its properties.</span></span>

  <span data-ttu-id="d4aee-243">XHTML Strict DTD に準拠するために、DOCTYPE タグが適宜変更されます。</span><span class="sxs-lookup"><span data-stu-id="d4aee-243">To comply with the XHTML Strict DTD, the DOCTYPE tag is modified accordingly:</span></span>

   `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"   "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"\>`

## <span data-ttu-id="d4aee-244">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d4aee-244">RELATED LINKS</span></span>

[<span data-ttu-id="d4aee-245">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="d4aee-245">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="d4aee-246">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="d4aee-246">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="d4aee-247">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="d4aee-247">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="d4aee-248">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="d4aee-248">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="d4aee-249">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="d4aee-249">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="d4aee-250">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="d4aee-250">Import-Clixml</span></span>](Import-Clixml.md)
