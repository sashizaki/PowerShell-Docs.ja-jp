---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-history?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-History
ms.openlocfilehash: bbc5b6590dc97413350c19c91dbca0b4d08e9bce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211651"
---
# <span data-ttu-id="816be-103">Add-History</span><span class="sxs-lookup"><span data-stu-id="816be-103">Add-History</span></span>

## <span data-ttu-id="816be-104">概要</span><span class="sxs-lookup"><span data-stu-id="816be-104">SYNOPSIS</span></span>
<span data-ttu-id="816be-105">セッションの履歴にエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-105">Appends entries to the session history.</span></span>

## <span data-ttu-id="816be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="816be-106">SYNTAX</span></span>

```
Add-History [[-InputObject] <PSObject[]>] [-Passthru] [<CommonParameters>]
```

## <span data-ttu-id="816be-107">Description</span><span class="sxs-lookup"><span data-stu-id="816be-107">DESCRIPTION</span></span>

<span data-ttu-id="816be-108">この `Add-History` コマンドレットは、セッション履歴の末尾 (現在のセッション中に入力されたコマンドの一覧) にエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-108">The `Add-History` cmdlet adds entries to the end of the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="816be-109">セッション履歴は、セッション中に入力したコマンドの一覧です。</span><span class="sxs-lookup"><span data-stu-id="816be-109">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="816be-110">セッション履歴は、実行の順序、状態、コマンドの開始時刻と終了時刻を表します。</span><span class="sxs-lookup"><span data-stu-id="816be-110">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="816be-111">各コマンドを入力すると、PowerShell によってそのコマンドが履歴に追加され、再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="816be-111">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="816be-112">セッションの履歴の詳細については、「 [about_History](About/about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="816be-112">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="816be-113">セッション履歴は、 **Psreadline** モジュールによって保持されている履歴とは別に管理されます。</span><span class="sxs-lookup"><span data-stu-id="816be-113">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="816be-114">どちらの履歴も、 **Psreadline** が読み込まれたセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="816be-114">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="816be-115">このコマンドレットは、セッション履歴でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="816be-115">This cmdlet only works with the session history.</span></span> <span data-ttu-id="816be-116">詳細については、「」、「 [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="816be-116">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

<span data-ttu-id="816be-117">コマンドレットを使用する `Get-History` と、コマンドを取得してに渡すことができます `Add-History` 。また、コマンドを CSV または XML ファイルにエクスポートしてから、コマンドをインポートして、インポートしたファイルをに渡すこともできます `Add-History` 。</span><span class="sxs-lookup"><span data-stu-id="816be-117">You can use the `Get-History` cmdlet to get the commands and pass them to `Add-History`, or you can export the commands to a CSV or XML file, then import the commands, and pass the imported file to `Add-History`.</span></span> <span data-ttu-id="816be-118">このコマンドレットを使用して、履歴に特定のコマンドを追加するか、または複数のセッションからのコマンドを含む 1 つの履歴ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="816be-118">You can use this cmdlet to add specific commands to the history or to create a single history file that includes commands from more than one session.</span></span>

## <span data-ttu-id="816be-119">例</span><span class="sxs-lookup"><span data-stu-id="816be-119">EXAMPLES</span></span>

### <span data-ttu-id="816be-120">例 1: 別のセッションの履歴にコマンドを追加する</span><span class="sxs-lookup"><span data-stu-id="816be-120">Example 1: Add commands to the history of a different session</span></span>

<span data-ttu-id="816be-121">この例では、1つの PowerShell セッションで入力したコマンドを別の PowerShell セッションの履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-121">This example add the commands typed in one PowerShell session to the history of a different PowerShell session.</span></span>

```powershell
Get-History | Export-Csv c:\testing\history.csv -IncludeTypeInformation
Import-Csv c:\testing\history.csv | Add-History
```

<span data-ttu-id="816be-122">最初のコマンドは、履歴内のコマンドを表すオブジェクトを取得し、それらをファイルにエクスポートし `History.csv` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-122">The first command gets objects representing the commands in the history and exports them to the `History.csv` file.</span></span>

<span data-ttu-id="816be-123">2 番目のコマンドは、別のセッションのコマンド ラインで入力します。</span><span class="sxs-lookup"><span data-stu-id="816be-123">The second command is typed at the command line of a different session.</span></span> <span data-ttu-id="816be-124">コマンドレットを使用して、 `Import-Csv` ファイル内のオブジェクトをインポートし `History.csv` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-124">It uses the `Import-Csv` cmdlet to import the objects in the `History.csv` file.</span></span> <span data-ttu-id="816be-125">パイプライン演算子 () は、 `|` オブジェクトをコマンドレットに渡します。これにより、 `Add-History` ファイル内のコマンドを表すオブジェクトが `History.csv` 現在のセッション履歴に追加されます。</span><span class="sxs-lookup"><span data-stu-id="816be-125">The pipeline operator (`|`) passes the objects to the `Add-History` cmdlet, which adds the objects representing the commands in the `History.csv` file to the current session history.</span></span>

### <span data-ttu-id="816be-126">例 2: コマンドをインポートして実行する</span><span class="sxs-lookup"><span data-stu-id="816be-126">Example 2: Import and run commands</span></span>

<span data-ttu-id="816be-127">この例では、ファイルからコマンドをインポートし `History.xml` 、それを現在のセッション履歴に追加して、結合された履歴のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="816be-127">This example imports commands from the `History.xml` file, adds them to the current session history, and then runs the commands in the combined history.</span></span>

```powershell
Import-Clixml c:\temp\history.xml | Add-History -PassThru | ForEach-Object -Process {Invoke-History}
```

<span data-ttu-id="816be-128">最初のコマンドは、コマンドレットを使用して、 `Import-Clixml` ファイルにエクスポートされたコマンドの履歴をインポートし `History.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-128">The first command uses the `Import-Clixml` cmdlet to import a command history that was exported to the `History.xml` file.</span></span> <span data-ttu-id="816be-129">パイプライン演算子はコマンドレットにコマンドを渡し `Add-History` 、現在のセッション履歴にコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-129">The pipeline operator passes the commands to the `Add-History` cmdlet, which adds the commands to the current session history.</span></span> <span data-ttu-id="816be-130">**PassThru** パラメーターは、追加されたコマンドを表すオブジェクトをパイプラインに渡します。</span><span class="sxs-lookup"><span data-stu-id="816be-130">The **PassThru** parameter passes the objects representing the added commands down the pipeline.</span></span>

<span data-ttu-id="816be-131">次に、コマンドレットを使用して、結合され `ForEach-Object` `Invoke-History` た履歴の各コマンドにコマンドを適用します。</span><span class="sxs-lookup"><span data-stu-id="816be-131">The command then uses the `ForEach-Object` cmdlet to apply the `Invoke-History` command to each of the commands in the combined history.</span></span> <span data-ttu-id="816be-132">コマンドは、コマンド `Invoke-History` `{}` レットの **Process** パラメーターによって求められるように、かっこ () で囲まれたスクリプトブロックとして書式設定され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-132">The `Invoke-History` command is formatted as a script block, enclosed in braces (`{}`), as required by the **Process** parameter of the `ForEach-Object` cmdlet.</span></span>

### <span data-ttu-id="816be-133">例 3: 履歴のコマンドを履歴の最後に追加する</span><span class="sxs-lookup"><span data-stu-id="816be-133">Example 3: Add commands in the history to the end of the history</span></span>

<span data-ttu-id="816be-134">この例では、履歴の最初の5つのコマンドを履歴リストの最後に追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-134">This example adds the first five commands in the history to the end of the history list.</span></span>

```powershell
Get-History -Id 5 -Count 5 | Add-History
```

<span data-ttu-id="816be-135">`Get-History`コマンドレットは、コマンド5で終了する5つのコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="816be-135">The `Get-History` cmdlet gets the five commands ending in command 5.</span></span> <span data-ttu-id="816be-136">パイプライン演算子は、それらをコマンドレットに渡して、 `Add-History` 現在の履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-136">The pipeline operator passes them to the `Add-History` cmdlet, which appends them to the current history.</span></span> <span data-ttu-id="816be-137">コマンドには `Add-History` パラメーターが含まれていませんが、PowerShell は、パイプラインを通じて渡されたオブジェクトをの **InputObject** パラメーターと関連付け `Add-History` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-137">The `Add-History` command does not include any parameters, but PowerShell associates the objects passed through the pipeline with the **InputObject** parameter of `Add-History`.</span></span>

### <span data-ttu-id="816be-138">例 4: 現在の履歴に .csv ファイルのコマンドを追加する</span><span class="sxs-lookup"><span data-stu-id="816be-138">Example 4: Add commands in a .csv file to the current history</span></span>

<span data-ttu-id="816be-139">この例では、ファイル内のコマンドを `History.csv` 現在のセッション履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-139">This example add the commands in the `History.csv` file to the current session history.</span></span>

```powershell
$a = Import-Csv c:\testing\history.csv
Add-History -InputObject $a -PassThru
```

<span data-ttu-id="816be-140">コマンド `Import-Csv` レットは、ファイル内のコマンドをインポート `History.csv` し、その内容を変数に格納し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-140">The `Import-Csv` cmdlet imports the commands in the `History.csv` file and store its contents in the variable `$a`.</span></span>

<span data-ttu-id="816be-141">2番目のコマンドは、コマンドレットを使用して、 `Add-History` から現在のセッション履歴にコマンドを追加し `History.csv` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-141">The second command uses the `Add-History` cmdlet to add the commands from `History.csv` to the current session history.</span></span> <span data-ttu-id="816be-142">**InputObject** パラメーターを使用して変数を指定し、PassThru パラメーターを使用して `$a` コマンドラインに表示するオブジェクトを生成します。 **PassThru**</span><span class="sxs-lookup"><span data-stu-id="816be-142">It uses the **InputObject** parameter to specify the `$a` variable and the **PassThru** parameter to generate an object to display at the command line.</span></span> <span data-ttu-id="816be-143">**PassThru** パラメーターを指定しない場合、 `Add-History` コマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="816be-143">Without the **PassThru** parameter, the `Add-History` cmdlet does not generate any output.</span></span>

### <span data-ttu-id="816be-144">例 5: 現在の履歴に .xml ファイルのコマンドを追加する</span><span class="sxs-lookup"><span data-stu-id="816be-144">Example 5: Add commands in an .xml file to the current history</span></span>

<span data-ttu-id="816be-145">この例では、ファイル内のコマンドを `history.xml` 現在のセッション履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-145">This example adds the commands in the `history.xml` file to the current session history.</span></span>

```powershell
Add-History -InputObject (Import-Clixml c:\temp\history.xml)
```

<span data-ttu-id="816be-146">**InputObject** パラメーターを指定すると、コマンドの結果がかっこで囲まれてコマンドレットに渡され `Add-History` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-146">The **InputObject** parameter passes the results of the command in parentheses to the `Add-History` cmdlet.</span></span> <span data-ttu-id="816be-147">最初に実行されるかっこ内のコマンドは、 `history.xml` ファイルを PowerShell にインポートします。</span><span class="sxs-lookup"><span data-stu-id="816be-147">The command in parentheses, which is executed first, imports the `history.xml` file into PowerShell.</span></span> <span data-ttu-id="816be-148">次に、コマンドレットは、 `Add-History` セッション履歴にファイル内のコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-148">The `Add-History` cmdlet then adds the commands in the file to the session history.</span></span>

## <span data-ttu-id="816be-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="816be-149">PARAMETERS</span></span>

### <span data-ttu-id="816be-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="816be-150">-InputObject</span></span>

<span data-ttu-id="816be-151">履歴 **情報** オブジェクトとしてセッション履歴に追加するエントリの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="816be-151">Specifies an array of entries to add to the history as **HistoryInfo** object to the session history.</span></span>
<span data-ttu-id="816be-152">このパラメーターを使用して **HistoryInfo** `Get-History` 、、 `Import-Clixml` 、またはコマンドレットによって返された履歴情報オブジェクトをに送信でき `Import-Csv` `Add-History` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-152">You can use this parameter to submit a **HistoryInfo** object, such as the ones that are returned by the `Get-History`, `Import-Clixml`, or `Import-Csv` cmdlets, to `Add-History`.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="816be-153">-Passthru</span><span class="sxs-lookup"><span data-stu-id="816be-153">-Passthru</span></span>

<span data-ttu-id="816be-154">このコマンドレットが各履歴エントリの履歴 **情報** オブジェクトを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="816be-154">Indicates that this cmdlet returns a **HistoryInfo** object for each history entry.</span></span> <span data-ttu-id="816be-155">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="816be-155">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="816be-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="816be-156">CommonParameters</span></span>

<span data-ttu-id="816be-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="816be-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="816be-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="816be-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="816be-159">入力</span><span class="sxs-lookup"><span data-stu-id="816be-159">INPUTS</span></span>

### <span data-ttu-id="816be-160">Microsoft. PowerShell. コマンドの履歴情報</span><span class="sxs-lookup"><span data-stu-id="816be-160">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="816be-161">このコマンドレットには、 **履歴情報** オブジェクトをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="816be-161">You can pipe a **HistoryInfo** object to this cmdlet.</span></span>

## <span data-ttu-id="816be-162">出力</span><span class="sxs-lookup"><span data-stu-id="816be-162">OUTPUTS</span></span>

### <span data-ttu-id="816be-163">None または Microsoft. PowerShell. History Info</span><span class="sxs-lookup"><span data-stu-id="816be-163">None or Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="816be-164">**PassThru** パラメーターを指定した場合、このコマンドレットは **履歴情報** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="816be-164">This cmdlet returns a **HistoryInfo** object if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="816be-165">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="816be-165">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="816be-166">注</span><span class="sxs-lookup"><span data-stu-id="816be-166">NOTES</span></span>

<span data-ttu-id="816be-167">セッション履歴は、セッション中に ID と共に入力されたコマンドの一覧です。</span><span class="sxs-lookup"><span data-stu-id="816be-167">The session history is a list of the commands entered during the session together with the ID.</span></span> <span data-ttu-id="816be-168">セッション履歴は、実行の順序、状態、コマンドの開始時刻と終了時刻を表します。</span><span class="sxs-lookup"><span data-stu-id="816be-168">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="816be-169">各コマンドを入力すると、PowerShell によってそのコマンドが履歴に追加され、再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="816be-169">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="816be-170">セッションの履歴の詳細については、「 [about_History](About/about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="816be-170">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="816be-171">履歴に追加するコマンドを指定するには、 **InputObject** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="816be-171">To specify the commands to add to the history, use the **InputObject** parameter.</span></span> <span data-ttu-id="816be-172">コマンドは、コマンド `Add-History` レットによって各コマンドに対して返された **履歴情報** オブジェクトなどを受け入れ `Get-History` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-172">The `Add-History` command accepts only **HistoryInfo** objects, such as those returned for each command by the `Get-History` cmdlet.</span></span> <span data-ttu-id="816be-173">パスとファイル名、またはコマンドの一覧を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="816be-173">You cannot pass it a path and file name or a list of commands.</span></span>

<span data-ttu-id="816be-174">**InputObject** パラメーターを使用して、 **履歴情報** オブジェクトのファイルをに渡すことができ `Add-History` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-174">You can use the **InputObject** parameter to pass a file of **HistoryInfo** objects to `Add-History`.</span></span> <span data-ttu-id="816be-175">これを行うには、またはコマンドレットを使用してコマンドの結果を `Get-History` ファイルにエクスポート `Export-Csv` してから、 `Export-Clixml` またはコマンドレットを使用してファイルをインポートし `Import-Csv` `Import-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="816be-175">To do so, export the results of a `Get-History` command to a file by using the `Export-Csv` or `Export-Clixml` cmdlet and then import the file by using the `Import-Csv` or `Import-Clixml` cmdlets.</span></span> <span data-ttu-id="816be-176">その後、インポートされた **履歴情報** オブジェクトのファイルを `Add-History` パイプラインまたは変数でに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="816be-176">You can then pass the file of imported **HistoryInfo** objects to `Add-History` through a pipeline or in a variable.</span></span> <span data-ttu-id="816be-177">詳細については、例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="816be-177">For more information, see the examples.</span></span>

<span data-ttu-id="816be-178">コマンドレットに渡す **履歴情報** オブジェクトのファイルには、 `Add-History` 型情報、列見出し、および **履歴情報** オブジェクトのすべてのプロパティが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="816be-178">The file of **HistoryInfo** objects that you pass to the `Add-History` cmdlet must include the type information, column headings, and all of the properties of the **HistoryInfo** objects.</span></span> <span data-ttu-id="816be-179">オブジェクトをに再び渡す場合は `Add-History` 、コマンドレットの **Notypeinformation** パラメーターを使用せず、 `Export-Csv` ファイル内の型情報、列見出し、またはフィールドを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="816be-179">If you intend to pass the objects back to `Add-History`, do not use the **NoTypeInformation** parameter of the `Export-Csv` cmdlet and do not delete the type information, column headings, or any fields in the file.</span></span>

<span data-ttu-id="816be-180">セッションの履歴を変更するには、CSV ファイルまたは XML ファイルにセッションをエクスポートし、ファイルを変更して、ファイルをインポートし、を使用し `Add-History` て現在のセッション履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="816be-180">To modify the session history, export the session to a CSV or XML file, modify the file, import the file, and use `Add-History` to append it to the current session history.</span></span>

## <span data-ttu-id="816be-181">関連リンク</span><span class="sxs-lookup"><span data-stu-id="816be-181">RELATED LINKS</span></span>

[<span data-ttu-id="816be-182">Clear-History</span><span class="sxs-lookup"><span data-stu-id="816be-182">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="816be-183">Get-History</span><span class="sxs-lookup"><span data-stu-id="816be-183">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="816be-184">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="816be-184">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="816be-185">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="816be-185">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="816be-186">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="816be-186">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="816be-187">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="816be-187">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)

