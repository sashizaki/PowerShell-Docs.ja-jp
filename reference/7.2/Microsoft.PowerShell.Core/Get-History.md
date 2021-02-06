---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-History
ms.openlocfilehash: be47925211c57760ddbd0bd4c8e985e161d24593
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600792"
---
# <span data-ttu-id="3b39a-102">Get-History</span><span class="sxs-lookup"><span data-stu-id="3b39a-102">Get-History</span></span>

## <span data-ttu-id="3b39a-103">概要</span><span class="sxs-lookup"><span data-stu-id="3b39a-103">SYNOPSIS</span></span>
<span data-ttu-id="3b39a-104">現在のセッション中に入力したコマンドの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-104">Gets a list of the commands entered during the current session.</span></span>

## <span data-ttu-id="3b39a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3b39a-105">SYNTAX</span></span>

```
Get-History [[-Id] <Int64[]>] [[-Count] <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="3b39a-106">Description</span><span class="sxs-lookup"><span data-stu-id="3b39a-106">DESCRIPTION</span></span>

<span data-ttu-id="3b39a-107">この `Get-History` コマンドレットは、セッション履歴 (現在のセッション中に入力されたコマンドの一覧) を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-107">The `Get-History` cmdlet gets the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="3b39a-108">PowerShell では、各セッションの履歴が自動的に保持されます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-108">PowerShell automatically maintains a history of each session.</span></span> <span data-ttu-id="3b39a-109">セッション履歴内のエントリの数は、ユーザー設定変数の値によって決まり `$MaximumHistoryCount` ます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-109">The number of entries in the session history is determined by the value of the `$MaximumHistoryCount` preference variable.</span></span> <span data-ttu-id="3b39a-110">Windows PowerShell 3.0 以降では、既定値は `4096` です。</span><span class="sxs-lookup"><span data-stu-id="3b39a-110">Beginning in Windows PowerShell 3.0, the default value is `4096`.</span></span> <span data-ttu-id="3b39a-111">既定では、履歴ファイルはホーム ディレクトリに保存されますが、任意の場所にファイルを保存することができます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-111">By default, history files are saved in the home directory, but you can save the file in any location.</span></span> <span data-ttu-id="3b39a-112">PowerShell の履歴機能の詳細については、「 [about_History](About/about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b39a-112">For more information about the history features in PowerShell, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="3b39a-113">セッション履歴は、 **Psreadline** モジュールによって保持されている履歴とは別に管理されます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-113">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="3b39a-114">どちらの履歴も、 **Psreadline** が読み込まれたセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-114">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="3b39a-115">このコマンドレットは、セッション履歴でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-115">This cmdlet only works with the session history.</span></span> <span data-ttu-id="3b39a-116">詳細については、「」、「 [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b39a-116">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="3b39a-117">例</span><span class="sxs-lookup"><span data-stu-id="3b39a-117">EXAMPLES</span></span>

### <span data-ttu-id="3b39a-118">例 1: セッションの履歴を取得する</span><span class="sxs-lookup"><span data-stu-id="3b39a-118">Example 1: Get the session history</span></span>

<span data-ttu-id="3b39a-119">この例では、セッション履歴のエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-119">This example gets the entries in the session history.</span></span> <span data-ttu-id="3b39a-120">既定の表示では、各コマンドとその ID が表示されます。これは、実行された順序を示します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-120">The default display shows each command and its ID, which indicates the order in which they ran.</span></span>

```powershell
Get-History
```

### <span data-ttu-id="3b39a-121">例 2: 文字列を含むエントリを取得する</span><span class="sxs-lookup"><span data-stu-id="3b39a-121">Example 2: Get entries that include a string</span></span>

<span data-ttu-id="3b39a-122">この例では、文字列サービスを含むコマンド履歴のエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-122">This example gets entries in the command history that include the string service.</span></span> <span data-ttu-id="3b39a-123">最初のコマンドは、セッション履歴のすべてのエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-123">The first command gets all entries in the session history.</span></span> <span data-ttu-id="3b39a-124">パイプライン演算子 ( `|` ) によって結果がコマンドレットに渡され、 `Where-Object` サービスを含むコマンドのみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-124">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects only the commands that include service.</span></span>

```powershell
Get-History | Where-Object {$_.CommandLine -like "*Service*"}
```

### <span data-ttu-id="3b39a-125">例 3: 履歴エントリを特定の ID までエクスポートする</span><span class="sxs-lookup"><span data-stu-id="3b39a-125">Example 3: Export history entries up to a specific ID</span></span>

<span data-ttu-id="3b39a-126">この例では、エントリ7で終わる最新の5つの履歴エントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-126">This example gets the five most recent history entries ending with entry 7.</span></span> <span data-ttu-id="3b39a-127">パイプライン演算子は、結果をコマンドレットに渡します。これにより、 `Export-Csv` 履歴がコンマ区切りのテキストとして書式設定され、History.csv ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-127">The pipeline operator passes the result to the `Export-Csv` cmdlet, which formats the history as comma-separated text and saves it in the History.csv file.</span></span> <span data-ttu-id="3b39a-128">このファイルには、履歴を一覧として書式設定するときに表示されるデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3b39a-128">The file includes the data that is displayed when you format the history as a list.</span></span> <span data-ttu-id="3b39a-129">これには、コマンドの状態、開始時刻、終了時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-129">This includes the status and start and end times of the command.</span></span>

```powershell
Get-History -ID 7 -Count 5 | Export-Csv History.csv
```

### <span data-ttu-id="3b39a-130">例 4: 最新のコマンドを表示する</span><span class="sxs-lookup"><span data-stu-id="3b39a-130">Example 4: Display the most recent command</span></span>

<span data-ttu-id="3b39a-131">この例では、コマンド履歴の最後のコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-131">This example gets the last command in the command history.</span></span> <span data-ttu-id="3b39a-132">最後のコマンドは、最後に入力されたコマンドです。</span><span class="sxs-lookup"><span data-stu-id="3b39a-132">The last command is the most recently entered command.</span></span> <span data-ttu-id="3b39a-133">このコマンドは、 **Count** パラメーターを使用して、1つのコマンドだけを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-133">This command uses the **Count** parameter to display just one command.</span></span> <span data-ttu-id="3b39a-134">既定では、は `Get-History` 最新のコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-134">By default, `Get-History` gets the most recent commands.</span></span> <span data-ttu-id="3b39a-135">このコマンドは "h -c 1" と省略でき、上方向キーを押すことと同等です。</span><span class="sxs-lookup"><span data-stu-id="3b39a-135">This command can be abbreviated to "h -c 1" and is equivalent to pressing the up-arrow key.</span></span>

```powershell
Get-History -Count 1
```

### <span data-ttu-id="3b39a-136">例 5: 履歴内のエントリのすべてのプロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="3b39a-136">Example 5: Display all the properties of the entries in the history</span></span>

<span data-ttu-id="3b39a-137">この例では、セッション履歴内のエントリのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-137">This example displays all of the properties of entries in the session history.</span></span> <span data-ttu-id="3b39a-138">パイプライン演算子はコマンドの結果を `Get-History` コマンドレットに渡し `Format-List` ます。これにより、各履歴エントリのすべてのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-138">The pipeline operator passes the results of a `Get-History` command to the `Format-List` cmdlet, which displays all of the properties of each history entry.</span></span> <span data-ttu-id="3b39a-139">これには、コマンドの ID、状態、開始時刻と終了時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-139">This includes the ID, status, and start and end times of the command.</span></span>

```powershell
Get-History | Format-List -Property *
```

## <span data-ttu-id="3b39a-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3b39a-140">PARAMETERS</span></span>

### <span data-ttu-id="3b39a-141">-カウント</span><span class="sxs-lookup"><span data-stu-id="3b39a-141">-Count</span></span>

<span data-ttu-id="3b39a-142">このコマンドレットが取得する最新の履歴エントリの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-142">Specifies the number of the most recent history entries that this cmdlet gets.</span></span> <span data-ttu-id="3b39a-143">既定では、 `Get-History` セッション履歴のすべてのエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-143">By, default, `Get-History` gets all entries in the session history.</span></span> <span data-ttu-id="3b39a-144">コマンドに **Count** と **Id** の両方のパラメーターを使用した場合、表示は **Id** パラメーターで指定されたコマンドで終了します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-144">If you use both the **Count** and **Id** parameters in a command, the display ends with the command that is specified by the **Id** parameter.</span></span>

<span data-ttu-id="3b39a-145">Windows PowerShell 2.0 では、既定では、 `Get-History` 32 の最新のエントリが取得されます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-145">In Windows PowerShell 2.0, by default, `Get-History` gets the 32 most recent entries.</span></span>

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

### <span data-ttu-id="3b39a-146">-Id</span><span class="sxs-lookup"><span data-stu-id="3b39a-146">-Id</span></span>

<span data-ttu-id="3b39a-147">セッション履歴内のエントリの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-147">Specifies an array of the IDs of entries in the session history.</span></span> <span data-ttu-id="3b39a-148">`Get-History` 指定されたエントリのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-148">`Get-History` gets only specified entries.</span></span> <span data-ttu-id="3b39a-149">コマンドで **id** と **カウント** の両方のパラメーターを使用する場合、は、 `Get-History` **id** パラメーターで指定されたエントリで終わる最新のエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-149">If you use both the **Id** and **Count** parameters in a command, `Get-History` gets the most recent entries ending with the entry specified by the **Id** parameter.</span></span>

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

### <span data-ttu-id="3b39a-150">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b39a-150">CommonParameters</span></span>

<span data-ttu-id="3b39a-151">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3b39a-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3b39a-152">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b39a-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3b39a-153">入力</span><span class="sxs-lookup"><span data-stu-id="3b39a-153">INPUTS</span></span>

### <span data-ttu-id="3b39a-154">System.Int64</span><span class="sxs-lookup"><span data-stu-id="3b39a-154">System.Int64</span></span>

<span data-ttu-id="3b39a-155">このコマンドレットには、履歴 ID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="3b39a-155">You can pipe a history ID to this cmdlet.</span></span>

## <span data-ttu-id="3b39a-156">出力</span><span class="sxs-lookup"><span data-stu-id="3b39a-156">OUTPUTS</span></span>

### <span data-ttu-id="3b39a-157">Microsoft. PowerShell. コマンドの履歴情報</span><span class="sxs-lookup"><span data-stu-id="3b39a-157">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="3b39a-158">このコマンドレットは、取得した各履歴項目の履歴オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-158">This cmdlet returns a history object for each history item that it gets.</span></span>

## <span data-ttu-id="3b39a-159">注</span><span class="sxs-lookup"><span data-stu-id="3b39a-159">NOTES</span></span>

<span data-ttu-id="3b39a-160">セッション履歴は、セッション中に入力したコマンドの一覧です。</span><span class="sxs-lookup"><span data-stu-id="3b39a-160">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="3b39a-161">セッション履歴は、コマンドの実行順序、状態、および開始時刻と終了時刻を表します。</span><span class="sxs-lookup"><span data-stu-id="3b39a-161">The session history represents the run order, the status, and the start and end times of the command.</span></span> <span data-ttu-id="3b39a-162">各コマンドを入力すると、PowerShell によってそのコマンドが履歴に追加され、再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3b39a-162">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="3b39a-163">コマンド履歴の詳細については、「 [about_History](About/about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b39a-163">For more information about the command history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="3b39a-164">Windows PowerShell 3.0 以降では、ユーザー設定変数の既定値 `$MaximumHistoryCount` は `4096` です。</span><span class="sxs-lookup"><span data-stu-id="3b39a-164">Starting in Windows PowerShell 3.0, the default value of the `$MaximumHistoryCount` preference variable is `4096`.</span></span> <span data-ttu-id="3b39a-165">Windows PowerShell 2.0 では、既定値は `64` です。</span><span class="sxs-lookup"><span data-stu-id="3b39a-165">In Windows PowerShell 2.0, the default value is `64`.</span></span> <span data-ttu-id="3b39a-166">変数の詳細については `$MaximumHistoryCount` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b39a-166">For more information about the `$MaximumHistoryCount` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="3b39a-167">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3b39a-167">RELATED LINKS</span></span>

[<span data-ttu-id="3b39a-168">Add-History</span><span class="sxs-lookup"><span data-stu-id="3b39a-168">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="3b39a-169">Clear-History</span><span class="sxs-lookup"><span data-stu-id="3b39a-169">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="3b39a-170">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="3b39a-170">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="3b39a-171">about_History</span><span class="sxs-lookup"><span data-stu-id="3b39a-171">about_History</span></span>](About/about_History.md)
