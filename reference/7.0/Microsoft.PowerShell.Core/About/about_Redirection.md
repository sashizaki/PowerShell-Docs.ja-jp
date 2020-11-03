---
description: PowerShell からテキストファイルに出力をリダイレクトする方法について説明します。
keywords: PowerShell, コマンドレット
Locale: en-US
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_redirection?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Redirection
ms.openlocfilehash: b6351486adff565010e6bb07bed07ee5dea316b7
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224464"
---
# <a name="about-redirection"></a><span data-ttu-id="734de-104">リダイレクトについて</span><span class="sxs-lookup"><span data-stu-id="734de-104">About Redirection</span></span>

## <a name="short-description"></a><span data-ttu-id="734de-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="734de-105">Short description</span></span>
<span data-ttu-id="734de-106">PowerShell からテキストファイルに出力をリダイレクトする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="734de-106">Explains how to redirect output from PowerShell to text files.</span></span>

## <a name="long-description"></a><span data-ttu-id="734de-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="734de-107">Long description</span></span>

<span data-ttu-id="734de-108">既定では、powershell は出力を PowerShell ホストに送信します。</span><span class="sxs-lookup"><span data-stu-id="734de-108">By default, PowerShell sends output to the PowerShell host.</span></span> <span data-ttu-id="734de-109">通常、これはコンソールアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="734de-109">Usually this is the console application.</span></span> <span data-ttu-id="734de-110">ただし、出力をテキストファイルに送信したり、エラー出力を通常の出力ストリームにリダイレクトしたりすることはできます。</span><span class="sxs-lookup"><span data-stu-id="734de-110">However, you can direct the output to a text file, and you can redirect error output to the regular output stream.</span></span>

<span data-ttu-id="734de-111">出力をリダイレクトするには、次の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="734de-111">You can use the following methods to redirect output:</span></span>

- <span data-ttu-id="734de-112">コマンドの `Out-File` 出力をテキストファイルに送信するコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="734de-112">Use the `Out-File` cmdlet, which sends command output to a text file.</span></span>
  <span data-ttu-id="734de-113">通常、 `Out-File` パラメーター (、、、など) を使用する必要がある場合は、コマンドレットを使用し `Encoding` `Force` `Width` `NoClobber` ます。</span><span class="sxs-lookup"><span data-stu-id="734de-113">Typically, you use the `Out-File` cmdlet when you need to use its parameters, such as the `Encoding`, `Force`, `Width`, or `NoClobber` parameters.</span></span>

- <span data-ttu-id="734de-114">`Tee-Object`コマンド出力をテキストファイルに送信し、それをパイプラインに送信するコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="734de-114">Use the `Tee-Object` cmdlet, which sends command output to a text file and then sends it to the pipeline.</span></span>

- <span data-ttu-id="734de-115">PowerShell リダイレクト演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="734de-115">Use the PowerShell redirection operators.</span></span> <span data-ttu-id="734de-116">リダイレクト演算子をファイルターゲットと共に使用することは、 `Out-File` 追加のパラメーターを使用せずにパイプを使用する場合と機能的に同等です。</span><span class="sxs-lookup"><span data-stu-id="734de-116">Using the redirection operator with a file target is functionally equivalent to piping to `Out-File` with no extra parameters.</span></span>

<span data-ttu-id="734de-117">ストリームの詳細については、「 [about_Output_Streams](about_Output_Streams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="734de-117">For more information about streams, see [about_Output_Streams](about_Output_Streams.md).</span></span>

### <a name="redirectable-output-streams"></a><span data-ttu-id="734de-118">リダイレクトの出力ストリーム</span><span class="sxs-lookup"><span data-stu-id="734de-118">Redirectable output streams</span></span>

<span data-ttu-id="734de-119">PowerShell では、次の出力ストリームのリダイレクトがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="734de-119">PowerShell supports redirection of the following output streams.</span></span>

| <span data-ttu-id="734de-120">一連#</span><span class="sxs-lookup"><span data-stu-id="734de-120">Stream #</span></span> |      <span data-ttu-id="734de-121">説明</span><span class="sxs-lookup"><span data-stu-id="734de-121">Description</span></span>       | <span data-ttu-id="734de-122">で導入</span><span class="sxs-lookup"><span data-stu-id="734de-122">Introduced in</span></span>  |    <span data-ttu-id="734de-123">Write コマンドレット</span><span class="sxs-lookup"><span data-stu-id="734de-123">Write Cmdlet</span></span>     |
| -------- | ---------------------- | -------------- | ------------------- |
| <span data-ttu-id="734de-124">1</span><span class="sxs-lookup"><span data-stu-id="734de-124">1</span></span>        | <span data-ttu-id="734de-125">**成功** 一連</span><span class="sxs-lookup"><span data-stu-id="734de-125">**Success** Stream</span></span>     | <span data-ttu-id="734de-126">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="734de-126">PowerShell 2.0</span></span> | `Write-Output`      |
| <span data-ttu-id="734de-127">2</span><span class="sxs-lookup"><span data-stu-id="734de-127">2</span></span>        | <span data-ttu-id="734de-128">**エラー** 一連</span><span class="sxs-lookup"><span data-stu-id="734de-128">**Error** Stream</span></span>       | <span data-ttu-id="734de-129">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="734de-129">PowerShell 2.0</span></span> | `Write-Error`       |
| <span data-ttu-id="734de-130">3</span><span class="sxs-lookup"><span data-stu-id="734de-130">3</span></span>        | <span data-ttu-id="734de-131">**警告** 一連</span><span class="sxs-lookup"><span data-stu-id="734de-131">**Warning** Stream</span></span>     | <span data-ttu-id="734de-132">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="734de-132">PowerShell 3.0</span></span> | `Write-Warning`     |
| <span data-ttu-id="734de-133">4</span><span class="sxs-lookup"><span data-stu-id="734de-133">4</span></span>        | <span data-ttu-id="734de-134">**詳細** 一連</span><span class="sxs-lookup"><span data-stu-id="734de-134">**Verbose** Stream</span></span>     | <span data-ttu-id="734de-135">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="734de-135">PowerShell 3.0</span></span> | `Write-Verbose`     |
| <span data-ttu-id="734de-136">5</span><span class="sxs-lookup"><span data-stu-id="734de-136">5</span></span>        | <span data-ttu-id="734de-137">**デバッグ** 一連</span><span class="sxs-lookup"><span data-stu-id="734de-137">**Debug** Stream</span></span>       | <span data-ttu-id="734de-138">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="734de-138">PowerShell 3.0</span></span> | `Write-Debug`       |
| <span data-ttu-id="734de-139">6</span><span class="sxs-lookup"><span data-stu-id="734de-139">6</span></span>        | <span data-ttu-id="734de-140">**情報** 一連</span><span class="sxs-lookup"><span data-stu-id="734de-140">**Information** Stream</span></span> | <span data-ttu-id="734de-141">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="734de-141">PowerShell 5.0</span></span> | `Write-Information` |
| *        | <span data-ttu-id="734de-142">すべてのストリーム</span><span class="sxs-lookup"><span data-stu-id="734de-142">All Streams</span></span>            | <span data-ttu-id="734de-143">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="734de-143">PowerShell 3.0</span></span> |                     |

> [!NOTE]
> <span data-ttu-id="734de-144">PowerShell には **進行状況** ストリームもありますが、リダイレクトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="734de-144">There is also a **Progress** stream in PowerShell, but it does not support redirection.</span></span>

### <a name="powershell-redirection-operators"></a><span data-ttu-id="734de-145">PowerShell リダイレクト演算子</span><span class="sxs-lookup"><span data-stu-id="734de-145">PowerShell redirection operators</span></span>

<span data-ttu-id="734de-146">PowerShell リダイレクト演算子は次のようになります。ここで、は `n` ストリーム番号を表します。</span><span class="sxs-lookup"><span data-stu-id="734de-146">The PowerShell redirection operators are as follows, where `n` represents the stream number.</span></span> <span data-ttu-id="734de-147">ストリームが指定されていない場合、 **成功** のストリーム ( `1` ) が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="734de-147">The **Success** stream ( `1` ) is the default if no stream is specified.</span></span>

| <span data-ttu-id="734de-148">演算子</span><span class="sxs-lookup"><span data-stu-id="734de-148">Operator</span></span> |                         <span data-ttu-id="734de-149">説明</span><span class="sxs-lookup"><span data-stu-id="734de-149">Description</span></span>                         | <span data-ttu-id="734de-150">構文</span><span class="sxs-lookup"><span data-stu-id="734de-150">Syntax</span></span> |
| -------- | ----------------------------------------------------------- | ------ |
| `>`      | <span data-ttu-id="734de-151">指定されたストリームをファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="734de-151">Send specified stream to a file.</span></span>                            | `n>`   |
| `>>`     | <span data-ttu-id="734de-152">指定されたストリームをファイルに **追加** します。</span><span class="sxs-lookup"><span data-stu-id="734de-152">**Append** specified stream to a file.</span></span>                      | `n>>`  |
| `>&1`    | <span data-ttu-id="734de-153">指定されたストリームを **成功** ストリームに _リダイレクト_ します。</span><span class="sxs-lookup"><span data-stu-id="734de-153">_Redirects_ the specified stream to the **Success** stream.</span></span> | `n>&1` |

> [!NOTE]
> <span data-ttu-id="734de-154">一部の Unix シェルとは異なり、他のストリームは **成功** ストリームにのみリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="734de-154">Unlike some Unix shells, you can only redirect other streams to the **Success** stream.</span></span>

## <a name="examples"></a><span data-ttu-id="734de-155">例</span><span class="sxs-lookup"><span data-stu-id="734de-155">Examples</span></span>

### <a name="example-1-redirect-errors-and-output-to-a-file"></a><span data-ttu-id="734de-156">例 1: エラーと出力をファイルにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="734de-156">Example 1: Redirect errors and output to a file</span></span>

<span data-ttu-id="734de-157">この例は `dir` 、正常に実行される1つの項目に対して実行され、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="734de-157">This example runs `dir` on one item that will succeed, and one that will error.</span></span>

```powershell
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
```

<span data-ttu-id="734de-158">を使用して、 `2>&1` **エラー** ストリームを **成功** ストリームにリダイレクトし、 `>` 結果の **成功** ストリームをという名前のファイルに送信します。 `dir.log`</span><span class="sxs-lookup"><span data-stu-id="734de-158">It uses `2>&1` to redirect the **Error** stream to the **Success** stream, and `>` to send the resultant **Success** stream to a file called `dir.log`</span></span>

### <a name="example-2-send-all-success-stream-data-to-a-file"></a><span data-ttu-id="734de-159">例 2: すべての成功したストリームデータをファイルに送信する</span><span class="sxs-lookup"><span data-stu-id="734de-159">Example 2: Send all Success stream data to a file</span></span>

<span data-ttu-id="734de-160">この例では、すべての **成功** ストリームデータをという名前のファイルに送信 `script.log` します。</span><span class="sxs-lookup"><span data-stu-id="734de-160">This example sends all **Success** stream data to a file called `script.log`.</span></span>

```powershell
.\script.ps1 > script.log
```

### <a name="example-3-send-success-warning-and-error-streams-to-a-file"></a><span data-ttu-id="734de-161">例 3: 成功、警告、およびエラーストリームをファイルに送信する</span><span class="sxs-lookup"><span data-stu-id="734de-161">Example 3: Send Success, Warning, and Error streams to a file</span></span>

<span data-ttu-id="734de-162">この例では、リダイレクト演算子を組み合わせて目的の結果を得る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="734de-162">This example shows how you can combine redirection operators to achieve a desired result.</span></span>

```powershell
&{
   Write-Warning "hello"
   Write-Error "hello"
   Write-Output "hi"
} 3>&1 2>&1 > P:\Temp\redirection.log
```

- <span data-ttu-id="734de-163">`3>&1`**警告** ストリームを **成功** ストリームにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="734de-163">`3>&1` redirects the **Warning** stream to the **Success** stream.</span></span>
- <span data-ttu-id="734de-164">`2>&1`**エラー** ストリームを **成功** ストリームにリダイレクトします (これには、すべての **警告** ストリームデータも含まれます)。</span><span class="sxs-lookup"><span data-stu-id="734de-164">`2>&1` redirects the **Error** stream to the **Success** stream (which also now includes all **Warning** stream data)</span></span>
- <span data-ttu-id="734de-165">`>`**成功** ストリーム ( **警告** ストリームと **エラー** ストリームの両方が含まれています) をという名前のファイルにリダイレクトします `C:\temp\redirection.log` 。</span><span class="sxs-lookup"><span data-stu-id="734de-165">`>` redirects the **Success** stream (which now contains both **Warning** and **Error** streams) to a file called `C:\temp\redirection.log`)</span></span>

### <a name="example-4-redirect-all-streams-to-a-file"></a><span data-ttu-id="734de-166">例 4: すべてのストリームをファイルにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="734de-166">Example 4: Redirect all streams to a file</span></span>

<span data-ttu-id="734de-167">この例では、というスクリプトから、という名前のファイルにすべてのストリーム出力を送信します。 `script.ps1``script.log`</span><span class="sxs-lookup"><span data-stu-id="734de-167">This example sends all streams output from a script called `script.ps1` to a file called `script.log`</span></span>

```powershell
.\script.ps1 *> script.log
```

### <a name="example-5-suppress-all-write-host-and-information-stream-data"></a><span data-ttu-id="734de-168">例 5: すべての Write-Host と情報ストリームデータを非表示にする</span><span class="sxs-lookup"><span data-stu-id="734de-168">Example 5: Suppress all Write-Host and Information stream data</span></span>

<span data-ttu-id="734de-169">この例では、すべての情報ストリームデータを抑制します。</span><span class="sxs-lookup"><span data-stu-id="734de-169">This example suppresses all information stream data.</span></span> <span data-ttu-id="734de-170">**情報** ストリームのコマンドレットの詳細については、「 [書き込みホスト](xref:Microsoft.PowerShell.Utility.Write-Host)と [書き込み情報](xref:Microsoft.PowerShell.Utility.Write-Information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="734de-170">To read more about **Information** stream cmdlets, see [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) and [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)</span></span>

```powershell
&{
   Write-Host "Hello"
   Write-Information "Hello" -InformationAction Continue
} 6> $null
```

### <a name="example-6-show-the-effect-of-action-preferences"></a><span data-ttu-id="734de-171">例 6: アクションの基本設定の効果を表示する</span><span class="sxs-lookup"><span data-stu-id="734de-171">Example 6: Show the effect of Action Preferences</span></span>

<span data-ttu-id="734de-172">アクションのユーザー設定変数とパラメーターを使用すると、特定のストリームに書き込まれる内容を変更できます。</span><span class="sxs-lookup"><span data-stu-id="734de-172">Action Preference variables and parameters can change what gets written to a particular stream.</span></span> <span data-ttu-id="734de-173">この例のスクリプトは、の値が `$ErrorActionPreference` **エラー** ストリームに書き込まれる影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="734de-173">The script in this example shows how the value of `$ErrorActionPreference` affects what gets written to the **Error** stream.</span></span>

```powershell
$ErrorActionPreference = 'Continue'
$ErrorActionPreference > log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'SilentlyContinue'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Stop'
$ErrorActionPreference >> log.txt
Try {
    get-item /not-here 2>&1 >> log.txt
}
catch {
    "`tError caught!" >> log.txt
}
$ErrorActionPreference = 'Ignore'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Inquire'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Continue'
```

<span data-ttu-id="734de-174">このスクリプトを実行すると、がに設定されている場合にプロンプト `$ErrorActionPreference` が表示さ `Inquire` れます。</span><span class="sxs-lookup"><span data-stu-id="734de-174">When we run this script we get prompted when `$ErrorActionPreference` is set to `Inquire`.</span></span>

```powershell
PS C:\temp> .\test.ps1

Confirm
Cannot find path 'C:\not-here' because it does not exist.
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): H
Get-Item: C:\temp\test.ps1:23
Line |
  23 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The running command stopped because the user selected the Stop option.
```

<span data-ttu-id="734de-175">ログファイルを確認すると、次の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="734de-175">When we examine the log file we see the following:</span></span>

```
PS C:\temp> Get-Content .\log.txt
Continue

Get-Item: C:\temp\test.ps1:3
Line |
   3 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | Cannot find path 'C:\not-here' because it does not exist.

SilentlyContinue
Stop
    Error caught!
Ignore
Inquire
```

## <a name="notes"></a><span data-ttu-id="734de-176">メモ</span><span class="sxs-lookup"><span data-stu-id="734de-176">Notes</span></span>

<span data-ttu-id="734de-177">データを追加しないリダイレクト演算子 ( `>` および) は、 `n>` 指定されたファイルの現在の内容を警告なしで上書きします。</span><span class="sxs-lookup"><span data-stu-id="734de-177">The redirection operators that do not append data (`>` and `n>`) overwrite the current contents of the specified file without warning.</span></span>

<span data-ttu-id="734de-178">ただし、ファイルが読み取り専用、非表示、またはシステムファイルの場合、リダイレクトは **失敗** します。</span><span class="sxs-lookup"><span data-stu-id="734de-178">However, if the file is a read-only, hidden, or system file, the redirection **fails**.</span></span> <span data-ttu-id="734de-179">追加リダイレクト演算子 ( `>>` および) は、 `n>>` 読み取り専用ファイルには書き込みませんが、システムファイルまたは隠しファイルにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="734de-179">The append redirection operators (`>>` and `n>>`) do not write to a read-only file, but they append content to a system or hidden file.</span></span>

<span data-ttu-id="734de-180">読み取り専用、非表示、またはシステムファイルにコンテンツを強制的にリダイレクトするには、 `Out-File` コマンドレットをパラメーターと共に使用し `Force` ます。</span><span class="sxs-lookup"><span data-stu-id="734de-180">To force the redirection of content to a read-only, hidden, or system file, use the `Out-File` cmdlet with its `Force` parameter.</span></span>

<span data-ttu-id="734de-181">ファイルに書き込む場合、リダイレクト演算子は encoding を使用し `UTF8NoBOM` ます。</span><span class="sxs-lookup"><span data-stu-id="734de-181">When you are writing to files, the redirection operators use `UTF8NoBOM` encoding.</span></span> <span data-ttu-id="734de-182">ファイルのエンコードが異なる場合は、出力の形式が正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="734de-182">If the file has a different encoding, the output might not be formatted correctly.</span></span> <span data-ttu-id="734de-183">別のエンコーディングを使用してファイルに書き込むには、 `Out-File` コマンドレットをパラメーターと共に使用し `Encoding` ます。</span><span class="sxs-lookup"><span data-stu-id="734de-183">To write to files with a different encoding, use the `Out-File` cmdlet with its `Encoding` parameter.</span></span>

### <a name="potential-confusion-with-comparison-operators"></a><span data-ttu-id="734de-184">比較演算子との混同の可能性</span><span class="sxs-lookup"><span data-stu-id="734de-184">Potential confusion with comparison operators</span></span>

<span data-ttu-id="734de-185">演算子は、 `>` [大なり](about_Comparison_Operators.md#-gt) 比較演算子と混同しないでください (多くの場合、 `>` 他のプログラミング言語でとして示されています)。</span><span class="sxs-lookup"><span data-stu-id="734de-185">The `>` operator is not to be confused with the [Greater-than](about_Comparison_Operators.md#-gt) comparison operator (often denoted as `>` in other programming languages).</span></span>

<span data-ttu-id="734de-186">比較対象のオブジェクトによっては、を使用した出力が `>` 正しく表示されることがあります (36 は42を超えないため)。</span><span class="sxs-lookup"><span data-stu-id="734de-186">Depending on the objects being compared, the output using `>` can appear to be correct (because 36 is not greater than 42).</span></span>

```powershell
PS> if (36 > 42) { "true" } else { "false" }
false
```

<span data-ttu-id="734de-187">ただし、ローカルのファイルシステムをチェックすると、という名前のファイルが `42` 内容と共に書き込まれたことがわかり `36` ます。</span><span class="sxs-lookup"><span data-stu-id="734de-187">However, a check of the local filesystem can see that a file called `42` was written, with the contents `36`.</span></span>

```powershell
PS> dir

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
------          1/02/20  10:10 am              3 42

PS> cat 42
36
```

<span data-ttu-id="734de-188">逆比較 (より小さい) を使用しようとすると `<` 、システムエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="734de-188">Attempting to use the reverse comparison `<` (less than), yields a system error:</span></span>

```powershell
PS> if (36 < 42) { "true" } else { "false" }
At line:1 char:8
+ if (36 < 42) { "true" } else { "false" }
+        ~
The '<' operator is reserved for future use.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : RedirectionNotSupported
```

<span data-ttu-id="734de-189">数値比較が必要な操作である場合は、 `-lt` を `-gt` 使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="734de-189">If numeric comparison is the required operation, `-lt` and `-gt` should be used.</span></span> <span data-ttu-id="734de-190">参照: [ `-gt` 比較演算子](about_Comparison_Operators.md#-gt)</span><span class="sxs-lookup"><span data-stu-id="734de-190">See: [`-gt` Comparison Operator](about_Comparison_Operators.md#-gt)</span></span>

## <a name="see-also"></a><span data-ttu-id="734de-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="734de-191">See also</span></span>

- [<span data-ttu-id="734de-192">Out-File</span><span class="sxs-lookup"><span data-stu-id="734de-192">Out-File</span></span>](xref:Microsoft.PowerShell.Utility.Out-File)
- [<span data-ttu-id="734de-193">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="734de-193">Tee-Object</span></span>](xref:Microsoft.PowerShell.Utility.Tee-Object)
- [<span data-ttu-id="734de-194">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="734de-194">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="734de-195">書き込み-エラー</span><span class="sxs-lookup"><span data-stu-id="734de-195">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)
- [<span data-ttu-id="734de-196">Write-Host</span><span class="sxs-lookup"><span data-stu-id="734de-196">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)
- [<span data-ttu-id="734de-197">Write-Information</span><span class="sxs-lookup"><span data-stu-id="734de-197">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)
- [<span data-ttu-id="734de-198">Write-Output</span><span class="sxs-lookup"><span data-stu-id="734de-198">Write-Output</span></span>](xref:Microsoft.PowerShell.Utility.Write-Output)
- [<span data-ttu-id="734de-199">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="734de-199">Write-Progress</span></span>](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [<span data-ttu-id="734de-200">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="734de-200">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [<span data-ttu-id="734de-201">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="734de-201">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [<span data-ttu-id="734de-202">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="734de-202">about_Output_Streams</span></span>](about_Output_Streams.md)
- [<span data-ttu-id="734de-203">about_Operators</span><span class="sxs-lookup"><span data-stu-id="734de-203">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="734de-204">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="734de-204">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="734de-205">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="734de-205">about_Path_Syntax</span></span>](about_Path_Syntax.md)