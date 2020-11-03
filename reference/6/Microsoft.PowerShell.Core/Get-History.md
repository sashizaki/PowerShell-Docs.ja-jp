---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-history?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-History
ms.openlocfilehash: 773e7e8d61e0f6158b4501b9c0b23826cbb10820
ms.sourcegitcommit: 1695df0d241c0390cac71a7401e61198fc6ff756
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "93220163"
---
# <span data-ttu-id="9c699-103">Get-History</span><span class="sxs-lookup"><span data-stu-id="9c699-103">Get-History</span></span>

## <span data-ttu-id="9c699-104">概要</span><span class="sxs-lookup"><span data-stu-id="9c699-104">SYNOPSIS</span></span>
<span data-ttu-id="9c699-105">現在のセッション中に入力したコマンドの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-105">Gets a list of the commands entered during the current session.</span></span>

## <span data-ttu-id="9c699-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c699-106">SYNTAX</span></span>

```
Get-History [[-Id] <Int64[]>] [[-Count] <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="9c699-107">Description</span><span class="sxs-lookup"><span data-stu-id="9c699-107">DESCRIPTION</span></span>

<span data-ttu-id="9c699-108">この `Get-History` コマンドレットは、セッション履歴 (現在のセッション中に入力されたコマンドの一覧) を取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-108">The `Get-History` cmdlet gets the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="9c699-109">PowerShell では、各セッションの履歴が自動的に保持されます。</span><span class="sxs-lookup"><span data-stu-id="9c699-109">PowerShell automatically maintains a history of each session.</span></span> <span data-ttu-id="9c699-110">セッション履歴内のエントリの数は、ユーザー設定変数の値によって決まり `$MaximumHistoryCount` ます。</span><span class="sxs-lookup"><span data-stu-id="9c699-110">The number of entries in the session history is determined by the value of the `$MaximumHistoryCount` preference variable.</span></span> <span data-ttu-id="9c699-111">Windows PowerShell 3.0 以降では、既定値は `4096` です。</span><span class="sxs-lookup"><span data-stu-id="9c699-111">Beginning in Windows PowerShell 3.0, the default value is `4096`.</span></span> <span data-ttu-id="9c699-112">既定では、履歴ファイルはホーム ディレクトリに保存されますが、任意の場所にファイルを保存することができます。</span><span class="sxs-lookup"><span data-stu-id="9c699-112">By default, history files are saved in the home directory, but you can save the file in any location.</span></span> <span data-ttu-id="9c699-113">PowerShell の履歴機能の詳細については、「 [about_History](About/about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c699-113">For more information about the history features in PowerShell, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="9c699-114">セッション履歴は、 **Psreadline** モジュールによって保持されている履歴とは別に管理されます。</span><span class="sxs-lookup"><span data-stu-id="9c699-114">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="9c699-115">どちらの履歴も、 **Psreadline** が読み込まれたセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c699-115">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="9c699-116">このコマンドレットは、セッション履歴でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9c699-116">This cmdlet only works with the session history.</span></span> <span data-ttu-id="9c699-117">詳細については、「」、「 [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c699-117">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="9c699-118">例</span><span class="sxs-lookup"><span data-stu-id="9c699-118">EXAMPLES</span></span>

### <span data-ttu-id="9c699-119">例 1: セッションの履歴を取得する</span><span class="sxs-lookup"><span data-stu-id="9c699-119">Example 1: Get the session history</span></span>

<span data-ttu-id="9c699-120">この例では、セッション履歴のエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-120">This example gets the entries in the session history.</span></span> <span data-ttu-id="9c699-121">既定の表示では、各コマンドとその ID が表示されます。これは、実行された順序を示します。</span><span class="sxs-lookup"><span data-stu-id="9c699-121">The default display shows each command and its ID, which indicates the order in which they ran.</span></span>

```powershell
Get-History
```

### <span data-ttu-id="9c699-122">例 2: 文字列を含むエントリを取得する</span><span class="sxs-lookup"><span data-stu-id="9c699-122">Example 2: Get entries that include a string</span></span>

<span data-ttu-id="9c699-123">この例では、文字列サービスを含むコマンド履歴のエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-123">This example gets entries in the command history that include the string service.</span></span> <span data-ttu-id="9c699-124">最初のコマンドは、セッション履歴のすべてのエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-124">The first command gets all entries in the session history.</span></span> <span data-ttu-id="9c699-125">パイプライン演算子 ( `|` ) によって結果がコマンドレットに渡され、 `Where-Object` サービスを含むコマンドのみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="9c699-125">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects only the commands that include service.</span></span>

```powershell
Get-History | Where-Object {$_.CommandLine -like "*Service*"}
```

### <span data-ttu-id="9c699-126">例 3: 履歴エントリを特定の ID までエクスポートする</span><span class="sxs-lookup"><span data-stu-id="9c699-126">Example 3: Export history entries up to a specific ID</span></span>

<span data-ttu-id="9c699-127">この例では、エントリ7で終わる最新の5つの履歴エントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-127">This example gets the five most recent history entries ending with entry 7.</span></span> <span data-ttu-id="9c699-128">パイプライン演算子は、結果をコマンドレットに渡します。これにより、 `Export-Csv` 履歴がコンマ区切りのテキストとして書式設定され、History.csv ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="9c699-128">The pipeline operator passes the result to the `Export-Csv` cmdlet, which formats the history as comma-separated text and saves it in the History.csv file.</span></span> <span data-ttu-id="9c699-129">このファイルには、履歴を一覧として書式設定するときに表示されるデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c699-129">The file includes the data that is displayed when you format the history as a list.</span></span> <span data-ttu-id="9c699-130">これには、コマンドの状態、開始時刻、終了時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c699-130">This includes the status and start and end times of the command.</span></span>

```powershell
Get-History -ID 7 -Count 5 | Export-Csv History.csv
```

### <span data-ttu-id="9c699-131">例 4: 最新のコマンドを表示する</span><span class="sxs-lookup"><span data-stu-id="9c699-131">Example 4: Display the most recent command</span></span>

<span data-ttu-id="9c699-132">この例では、コマンド履歴の最後のコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-132">This example gets the last command in the command history.</span></span> <span data-ttu-id="9c699-133">最後のコマンドは、最後に入力されたコマンドです。</span><span class="sxs-lookup"><span data-stu-id="9c699-133">The last command is the most recently entered command.</span></span> <span data-ttu-id="9c699-134">このコマンドは、 **Count** パラメーターを使用して、1つのコマンドだけを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c699-134">This command uses the **Count** parameter to display just one command.</span></span> <span data-ttu-id="9c699-135">既定では、は `Get-History` 最新のコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-135">By default, `Get-History` gets the most recent commands.</span></span> <span data-ttu-id="9c699-136">このコマンドは "h -c 1" と省略でき、上方向キーを押すことと同等です。</span><span class="sxs-lookup"><span data-stu-id="9c699-136">This command can be abbreviated to "h -c 1" and is equivalent to pressing the up-arrow key.</span></span>

```powershell
Get-History -Count 1
```

### <span data-ttu-id="9c699-137">例 5: 履歴内のエントリのすべてのプロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="9c699-137">Example 5: Display all the properties of the entries in the history</span></span>

<span data-ttu-id="9c699-138">この例では、セッション履歴内のエントリのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c699-138">This example displays all of the properties of entries in the session history.</span></span> <span data-ttu-id="9c699-139">パイプライン演算子はコマンドの結果を `Get-History` コマンドレットに渡し `Format-List` ます。これにより、各履歴エントリのすべてのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c699-139">The pipeline operator passes the results of a `Get-History` command to the `Format-List` cmdlet, which displays all of the properties of each history entry.</span></span> <span data-ttu-id="9c699-140">これには、コマンドの ID、状態、開始時刻と終了時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c699-140">This includes the ID, status, and start and end times of the command.</span></span>

```powershell
Get-History | Format-List -Property *
```

## <span data-ttu-id="9c699-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c699-141">PARAMETERS</span></span>

### <span data-ttu-id="9c699-142">-カウント</span><span class="sxs-lookup"><span data-stu-id="9c699-142">-Count</span></span>

<span data-ttu-id="9c699-143">このコマンドレットが取得する最新の履歴エントリの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c699-143">Specifies the number of the most recent history entries that this cmdlet gets.</span></span> <span data-ttu-id="9c699-144">既定では、 `Get-History` セッション履歴のすべてのエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-144">By, default, `Get-History` gets all entries in the session history.</span></span> <span data-ttu-id="9c699-145">コマンドに **Count** と **Id** の両方のパラメーターを使用した場合、表示は **Id** パラメーターで指定されたコマンドで終了します。</span><span class="sxs-lookup"><span data-stu-id="9c699-145">If you use both the **Count** and **Id** parameters in a command, the display ends with the command that is specified by the **Id** parameter.</span></span>

<span data-ttu-id="9c699-146">Windows PowerShell 2.0 では、既定では、 `Get-History` 32 の最新のエントリが取得されます。</span><span class="sxs-lookup"><span data-stu-id="9c699-146">In Windows PowerShell 2.0, by default, `Get-History` gets the 32 most recent entries.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c699-147">-Id</span><span class="sxs-lookup"><span data-stu-id="9c699-147">-Id</span></span>

<span data-ttu-id="9c699-148">セッション履歴内のエントリの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c699-148">Specifies an array of the IDs of entries in the session history.</span></span> <span data-ttu-id="9c699-149">`Get-History` 指定されたエントリのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-149">`Get-History` gets only specified entries.</span></span> <span data-ttu-id="9c699-150">コマンドで **id** と **カウント** の両方のパラメーターを使用する場合、は、 `Get-History` **id** パラメーターで指定されたエントリで終わる最新のエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c699-150">If you use both the **Id** and **Count** parameters in a command, `Get-History` gets the most recent entries ending with the entry specified by the **Id** parameter.</span></span>

```yaml
Type: System.Int64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9c699-151">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9c699-151">CommonParameters</span></span>

<span data-ttu-id="9c699-152">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9c699-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9c699-153">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c699-153">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9c699-154">入力</span><span class="sxs-lookup"><span data-stu-id="9c699-154">INPUTS</span></span>

### <span data-ttu-id="9c699-155">System.Int64</span><span class="sxs-lookup"><span data-stu-id="9c699-155">System.Int64</span></span>

<span data-ttu-id="9c699-156">このコマンドレットには、履歴 ID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c699-156">You can pipe a history ID to this cmdlet.</span></span>

## <span data-ttu-id="9c699-157">出力</span><span class="sxs-lookup"><span data-stu-id="9c699-157">OUTPUTS</span></span>

### <span data-ttu-id="9c699-158">Microsoft. PowerShell. コマンドの履歴情報</span><span class="sxs-lookup"><span data-stu-id="9c699-158">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="9c699-159">このコマンドレットは、取得した各履歴項目の履歴オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9c699-159">This cmdlet returns a history object for each history item that it gets.</span></span>

## <span data-ttu-id="9c699-160">注</span><span class="sxs-lookup"><span data-stu-id="9c699-160">NOTES</span></span>

<span data-ttu-id="9c699-161">セッション履歴は、セッション中に入力したコマンドの一覧です。</span><span class="sxs-lookup"><span data-stu-id="9c699-161">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="9c699-162">セッション履歴は、コマンドの実行順序、状態、および開始時刻と終了時刻を表します。</span><span class="sxs-lookup"><span data-stu-id="9c699-162">The session history represents the run order, the status, and the start and end times of the command.</span></span> <span data-ttu-id="9c699-163">各コマンドを入力すると、PowerShell によってそのコマンドが履歴に追加され、再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9c699-163">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="9c699-164">コマンド履歴の詳細については、「 [about_History](About/about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c699-164">For more information about the command history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="9c699-165">Windows PowerShell 3.0 以降では、ユーザー設定変数の既定値 `$MaximumHistoryCount` は `4096` です。</span><span class="sxs-lookup"><span data-stu-id="9c699-165">Starting in Windows PowerShell 3.0, the default value of the `$MaximumHistoryCount` preference variable is `4096`.</span></span> <span data-ttu-id="9c699-166">Windows PowerShell 2.0 では、既定値は `64` です。</span><span class="sxs-lookup"><span data-stu-id="9c699-166">In Windows PowerShell 2.0, the default value is `64`.</span></span> <span data-ttu-id="9c699-167">変数の詳細については `$MaximumHistoryCount` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c699-167">For more information about the `$MaximumHistoryCount` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="9c699-168">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9c699-168">RELATED LINKS</span></span>

[<span data-ttu-id="9c699-169">Add-History</span><span class="sxs-lookup"><span data-stu-id="9c699-169">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="9c699-170">Clear-History</span><span class="sxs-lookup"><span data-stu-id="9c699-170">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="9c699-171">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="9c699-171">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="9c699-172">about_History</span><span class="sxs-lookup"><span data-stu-id="9c699-172">about_History</span></span>](About/about_History.md)
