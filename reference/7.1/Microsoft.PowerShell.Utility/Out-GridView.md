---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-GridView
ms.openlocfilehash: 840aa38ff17ceaf7dc65ca838da020c3d8c27952
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344390"
---
# <span data-ttu-id="10d26-103">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="10d26-103">Out-GridView</span></span>

## <span data-ttu-id="10d26-104">概要</span><span class="sxs-lookup"><span data-stu-id="10d26-104">SYNOPSIS</span></span>
<span data-ttu-id="10d26-105">別のウィンドウの対話型のテーブルに出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="10d26-105">Sends output to an interactive table in a separate window.</span></span>

## <span data-ttu-id="10d26-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="10d26-106">SYNTAX</span></span>

### <span data-ttu-id="10d26-107">PassThru (既定値)</span><span class="sxs-lookup"><span data-stu-id="10d26-107">PassThru (Default)</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="10d26-108">Wait</span><span class="sxs-lookup"><span data-stu-id="10d26-108">Wait</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-Wait] [<CommonParameters>]
```

### <span data-ttu-id="10d26-109">OutputMode</span><span class="sxs-lookup"><span data-stu-id="10d26-109">OutputMode</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-OutputMode <OutputModeOption>]
 [<CommonParameters>]
```

## <span data-ttu-id="10d26-110">Description</span><span class="sxs-lookup"><span data-stu-id="10d26-110">DESCRIPTION</span></span>

<span data-ttu-id="10d26-111">`Out-GridView`コマンドレットは、コマンドからの出力をグリッドビューウィンドウに送信します。このウィンドウには、対話形式のテーブルに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-111">The `Out-GridView` cmdlet sends the output from a command to a grid view window where the output is displayed in an interactive table.</span></span>

<span data-ttu-id="10d26-112">このコマンドレットはユーザーインターフェイスを必要とするため、Windows Server Core または Windows Nano Server では機能しません。</span><span class="sxs-lookup"><span data-stu-id="10d26-112">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span>

<span data-ttu-id="10d26-113">テーブルの次の機能を使用して、データを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="10d26-113">You can use the following features of the table to examine your data:</span></span>

- <span data-ttu-id="10d26-114">列の非表示、表示、および並べ替え</span><span class="sxs-lookup"><span data-stu-id="10d26-114">Hide, Show, and Reorder Columns</span></span>
- <span data-ttu-id="10d26-115">行の並べ替え</span><span class="sxs-lookup"><span data-stu-id="10d26-115">Sort rows</span></span>
- <span data-ttu-id="10d26-116">クイック フィルター</span><span class="sxs-lookup"><span data-stu-id="10d26-116">Quick Filter</span></span>
- <span data-ttu-id="10d26-117">条件フィルターの追加</span><span class="sxs-lookup"><span data-stu-id="10d26-117">Add Criteria Filter</span></span>
- <span data-ttu-id="10d26-118">コピーと貼り付け</span><span class="sxs-lookup"><span data-stu-id="10d26-118">Copy and paste</span></span>

<span data-ttu-id="10d26-119">詳しい手順については、この記事の「 [メモ](#notes) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d26-119">For full instructions, see the [Notes](#notes) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="10d26-120">このコマンドレットは、PowerShell 7 で再導入されました。</span><span class="sxs-lookup"><span data-stu-id="10d26-120">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="10d26-121">このコマンドレットは、Windows デスクトップをサポートする Windows システムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="10d26-121">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span> <span data-ttu-id="10d26-122">このコマンドレットのクロスプラットフォームバージョンについては、PowerShell ギャラリーの「 [Graphのツール](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) 」モジュールを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d26-122">For a cross-platform version of this cmdlet, see the [GraphicalTools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) module in the PowerShell Gallery.</span></span>

## <span data-ttu-id="10d26-123">例</span><span class="sxs-lookup"><span data-stu-id="10d26-123">EXAMPLES</span></span>

### <span data-ttu-id="10d26-124">例 1: グリッドビューにプロセスを出力する</span><span class="sxs-lookup"><span data-stu-id="10d26-124">Example 1: Output processes to a grid view</span></span>

<span data-ttu-id="10d26-125">この例では、ローカルコンピューター上で実行されているプロセスを取得し、それらをグリッドビューウィンドウに送信します。</span><span class="sxs-lookup"><span data-stu-id="10d26-125">This example gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
Get-Process | Out-GridView
```

### <span data-ttu-id="10d26-126">例 2: 変数を使用してプロセスをグリッドビューに出力する</span><span class="sxs-lookup"><span data-stu-id="10d26-126">Example 2: Use a variable to output processes to a grid view</span></span>

<span data-ttu-id="10d26-127">また、この例では、ローカルコンピューター上で実行されているプロセスを取得し、それらをグリッドビューウィンドウに送信します。</span><span class="sxs-lookup"><span data-stu-id="10d26-127">This example also gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
$P = Get-Process
$P | Out-GridView
```

<span data-ttu-id="10d26-128">コマンドレットの出力 `Get-Process` は、変数に保存され `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-128">The output of the `Get-Process` cmdlet is saved in the `$P` variable.</span></span> <span data-ttu-id="10d26-129">次 `$P` に、はにパイプ処理され `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-129">Then, `$P` is piped to `Out-GridView`.</span></span>

### <span data-ttu-id="10d26-130">例 3: 選択したプロパティをグリッドビューに表示する</span><span class="sxs-lookup"><span data-stu-id="10d26-130">Example 3: Display a selected properties in a grid view</span></span>

<span data-ttu-id="10d26-131">この例では、実行中のプロセスの選択したプロパティをグリッドビューで表示します。</span><span class="sxs-lookup"><span data-stu-id="10d26-131">This example displays selected properties of the running processes in a grid view.</span></span>

```powershell
Get-Process | Select-Object -Property Name, WorkingSet, PeakWorkingSet |
  Sort-Object -Property WorkingSet -Descending | Out-GridView
```

<span data-ttu-id="10d26-132">の出力 `Get-Process` は、 `Select-Object` **Name** 、 **ワーキング** セット、 **peakworkingset** セットプロパティを選択するためにパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-132">The output of `Get-Process` is piped to `Select-Object` to select the **Name** , **WorkingSet** , and **PeakWorkingSet** properties.</span></span> <span data-ttu-id="10d26-133">もう1つのパイプライン演算子は、フィルター処理されたオブジェクトをコマンドレットに送信し `Sort-Object` て、 **ワーキング** セットプロパティの値によって降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="10d26-133">Another pipeline operator sends the filtered objects to the `Sort-Object` cmdlet to sort them in descending order by the value of the **WorkingSet** property.</span></span>
<span data-ttu-id="10d26-134">次に、並べ替えられた結果をにパイプ処理し `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-134">Then, the sorted results are piped to `Out-GridView`.</span></span> <span data-ttu-id="10d26-135">これで、グリッド ビューの機能を、検索、並べ替え、データのフィルター処理に使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="10d26-135">You can now use the features of the grid view to search, sort, and filter the data.</span></span>

### <span data-ttu-id="10d26-136">例 4: 出力を変数に保存し、グリッドビューを出力する</span><span class="sxs-lookup"><span data-stu-id="10d26-136">Example 4: Save output to a variable, and then output a grid view</span></span>

<span data-ttu-id="10d26-137">この例では、コマンドレットの出力を変数に保存し、に送信し `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-137">This example saves cmdlet output in a variable then sends it to `Out-GridView`.</span></span>

```powershell
($A = Get-ChildItem -Path $PSHOME -Recurse) | Out-GridView
```

<span data-ttu-id="10d26-138">`Get-ChildItem` 自動変数を使用して、PowerShell インストールディレクトリとそのサブディレクトリにあるすべてのファイルを取得し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-138">`Get-ChildItem` gets all the files in the PowerShell installation directory and its subdirectories using the the `$PSHOME` automatic variable.</span></span> <span data-ttu-id="10d26-139">コマンド内のかっこは、演算の順序を確立します。</span><span class="sxs-lookup"><span data-stu-id="10d26-139">The parentheses in the command establish the order of operations.</span></span> <span data-ttu-id="10d26-140">その結果、コマンドからの出力は、 `Get-ChildItem` に送信される前に変数に保存され `$A` `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-140">As a result, the output from the `Get-ChildItem` command is saved in the `$A` variable before it is sent to `Out-GridView`.</span></span>

### <span data-ttu-id="10d26-141">例 5: 指定したコンピューターのグリッドビューへの出力プロセス</span><span class="sxs-lookup"><span data-stu-id="10d26-141">Example 5: Output processes for a specified computer to a grid view</span></span>

<span data-ttu-id="10d26-142">この例では、Server01 コンピューター上で実行されているプロセスをグリッドビューウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="10d26-142">This example displays the processes that are running on the Server01 computer in a grid view window.</span></span>

```powershell
Get-Process -ComputerName "Server01" | ogv -Title "Processes - Server01"
```

<span data-ttu-id="10d26-143">例はを使用し `ogv` ます。これは、 `Out-GridView` コマンドレットのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="10d26-143">The examle uses `ogv`, which is the alias for the `Out-GridView` cmdlet.</span></span> <span data-ttu-id="10d26-144">**Title** パラメーターは、ウィンドウタイトルを指定します。</span><span class="sxs-lookup"><span data-stu-id="10d26-144">The **Title** parameter specifies the window title.</span></span>

### <span data-ttu-id="10d26-145">例 6: リモートコンピューターからグリッドビューにデータを出力する</span><span class="sxs-lookup"><span data-stu-id="10d26-145">Example 6: Output data from remote computers to a grid view</span></span>

<span data-ttu-id="10d26-146">この例では、リモートコンピューターから収集されたデータをに送信する方法を示し `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-146">This example shows how to send data collected from remote computers to `Out-GridView`.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture} | Out-GridView
```

<span data-ttu-id="10d26-147">`Invoke-Command``Get-Culture`3 台のリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-147">`Invoke-Command` runs `Get-Culture` on three remote computers.</span></span> <span data-ttu-id="10d26-148">結果として得られるデータはにパイプ処理され `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-148">The resulting data is piped to `Out-GridView`.</span></span> <span data-ttu-id="10d26-149">リモートコンピューターで実行されるスクリプトブロックには、コマンドが含まれていないことに注意して `Out-GridView` ください。</span><span class="sxs-lookup"><span data-stu-id="10d26-149">Notice that the script block that runs on the remote computer does not include the `Out-GridView` command.</span></span> <span data-ttu-id="10d26-150">含まれている場合、各リモート コンピュータでグリッド ビュー ウィンドウを開こうとすると、コマンドはエラーになります。</span><span class="sxs-lookup"><span data-stu-id="10d26-150">If it did, the command would fail when it tried to open a grid view window on each of the remote computers.</span></span>

### <span data-ttu-id="10d26-151">例 7: を使用して複数の項目を渡す `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="10d26-151">Example 7: Pass multiple items through `Out-GridView`</span></span>

<span data-ttu-id="10d26-152">この例では、ウィンドウから複数のプロセスを選択でき `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-152">This example lets you select multiple processes from the `Out-GridView` window.</span></span> <span data-ttu-id="10d26-153">選択したプロセスがコマンドに渡され、 `Export-Csv` ファイルに書き込まれ `ProcessLog.csv` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-153">The processes that you select are passed to the `Export-Csv` command and written to the `ProcessLog.csv` file.</span></span>

```powershell
Get-Process | Out-GridView -PassThru | Export-Csv -Path .\ProcessLog.csv
```

<span data-ttu-id="10d26-154">の **PassThru** パラメーターを `Out-GridView` 使用すると、パイプラインで複数の項目を送信できます。</span><span class="sxs-lookup"><span data-stu-id="10d26-154">The **PassThru** parameter of `Out-GridView` lets you send multiple items down the pipeline.</span></span> <span data-ttu-id="10d26-155">**PassThru**  パラメーターを使用すると、 **OutputMode** パラメーターの値を **Multiple** に設定した場合と同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="10d26-155">The **PassThru** parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

### <span data-ttu-id="10d26-156">例 8: の Windows ショートカットを作成する `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="10d26-156">Example 8: Create a Windows shortcut to `Out-GridView`</span></span>

<span data-ttu-id="10d26-157">この例では、の **Wait** パラメーターを使用して、 `Out-GridView` ウィンドウへの Windows ショートカットを作成する方法を示し `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-157">This example shows how to use the **Wait** parameter of `Out-GridView` to create a Windows shortcut to the `Out-GridView` window.</span></span>

```powershell
pwsh -Command "Get-Service | Out-GridView -Wait"
```

<span data-ttu-id="10d26-158">このコマンドラインは、Windows ショートカットで使用できます。</span><span class="sxs-lookup"><span data-stu-id="10d26-158">This command line can be used in a Windows shortcut.</span></span> <span data-ttu-id="10d26-159">**Wait** パラメーターを指定しないと、PowerShell はウィンドウが開いた直後に終了し `Out-GridView` ます。これにより、 `Out-GridView` ウィンドウがすぐに閉じられます。</span><span class="sxs-lookup"><span data-stu-id="10d26-159">Without the **Wait** parameter, PowerShell would exit as soon as the `Out-GridView` window opened, which would close the `Out-GridView` window almost immediately.</span></span>

## <span data-ttu-id="10d26-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="10d26-160">PARAMETERS</span></span>

### <span data-ttu-id="10d26-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="10d26-161">-InputObject</span></span>

<span data-ttu-id="10d26-162">コマンドレットが入力として受け入れるオブジェクトを指定し `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-162">Specifies object that the cmdlet accepts as input for `Out-GridView`.</span></span>

<span data-ttu-id="10d26-163">**InputObject** パラメーターを使用してオブジェクトのコレクションをに送信すると `Out-GridView` 、に `Out-GridView` よってコレクションが1つのコレクションオブジェクトとして扱われ、コレクションを表す1つの行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-163">When you use the **InputObject** parameter to send a collection of objects to `Out-GridView`, `Out-GridView` treats the collection as one collection object, and it displays one row that represents the collection.</span></span> <span data-ttu-id="10d26-164">コレクション内の各オブジェクトを表示するには、パイプライン演算子 () を使用して、 `|` オブジェクトをに送信し `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-164">To display the each object in the collection, use a pipeline operator (`|`) to send objects to `Out-GridView`.</span></span>

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

### <span data-ttu-id="10d26-165">-OutputMode</span><span class="sxs-lookup"><span data-stu-id="10d26-165">-OutputMode</span></span>

<span data-ttu-id="10d26-166">対話型ウィンドウがパイプラインを他のコマンドに入力として送信する項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="10d26-166">Specifies the items that the interactive window sends down the pipeline as input to other commands.</span></span>
<span data-ttu-id="10d26-167">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="10d26-167">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="10d26-168">対話型のウィンドウからパイプラインを介して項目を送るには、項目をクリックして選択し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-168">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span>

<span data-ttu-id="10d26-169">このパラメーターの値が、パイプラインに送信できるアイテムの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="10d26-169">The values of this parameter determine how many items you can send down the pipeline.</span></span>

- <span data-ttu-id="10d26-170">[なし] :</span><span class="sxs-lookup"><span data-stu-id="10d26-170">None.</span></span>  <span data-ttu-id="10d26-171">項目がありません。</span><span class="sxs-lookup"><span data-stu-id="10d26-171">No items.</span></span> <span data-ttu-id="10d26-172">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="10d26-172">This is the default value.</span></span>
- <span data-ttu-id="10d26-173">単一:</span><span class="sxs-lookup"><span data-stu-id="10d26-173">Single.</span></span> <span data-ttu-id="10d26-174">項目数は 0 または 1 です。</span><span class="sxs-lookup"><span data-stu-id="10d26-174">Zero items or one item.</span></span> <span data-ttu-id="10d26-175">次のコマンドが受け取ることができる入力オブジェクトが 1 つのみの場合、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="10d26-175">Use this value when the next command can take only one input object.</span></span>
- <span data-ttu-id="10d26-176">複数.</span><span class="sxs-lookup"><span data-stu-id="10d26-176">Multiple.</span></span> <span data-ttu-id="10d26-177">項目数は、0、1、または複数です。</span><span class="sxs-lookup"><span data-stu-id="10d26-177">Zero, one, or many items.</span></span> <span data-ttu-id="10d26-178">次のコマンドが受け取ることができる入力オブジェクトが複数の場合、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="10d26-178">Use this value when the next command can take multiple input objects.</span></span> <span data-ttu-id="10d26-179">この値は、 **Passthru** パラメーターと同じです。</span><span class="sxs-lookup"><span data-stu-id="10d26-179">This value is equivalent to the **Passthru** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputModeOption
Parameter Sets: OutputMode
Aliases:
Accepted values: None, Single, Multiple

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10d26-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="10d26-180">-PassThru</span></span>

<span data-ttu-id="10d26-181">コマンドレットが、対話型ウィンドウからパイプラインを介して他のコマンドに入力として項目を送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="10d26-181">Indicates that the cmdlet sends items from the interactive window down the pipeline as input to other commands.</span></span> <span data-ttu-id="10d26-182">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="10d26-182">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="10d26-183">このパラメーターを使用すると、 **OutputMode** パラメーターの値を **Multiple** に設定した場合と同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="10d26-183">This parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

<span data-ttu-id="10d26-184">対話型のウィンドウからパイプラインを介して項目を送るには、項目をクリックして選択し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-184">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span> <span data-ttu-id="10d26-185">Shift キーや Ctrl キーを使用した複数選択がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="10d26-185">Shift-click and Ctrl-click are supported.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PassThru
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10d26-186">-Title</span><span class="sxs-lookup"><span data-stu-id="10d26-186">-Title</span></span>

<span data-ttu-id="10d26-187">ウィンドウのタイトルバーに表示されるテキストを指定し `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-187">Specifies the text that appears in the title bar of the `Out-GridView` window.</span></span> <span data-ttu-id="10d26-188">既定では、を呼び出すコマンドがタイトルバーに表示され `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-188">By default, the title bar displays the command that invokes `Out-GridView`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10d26-189">-Wait</span><span class="sxs-lookup"><span data-stu-id="10d26-189">-Wait</span></span>

<span data-ttu-id="10d26-190">コマンドレットによってコマンドプロンプトが抑制され、ウィンドウが閉じられるまで Windows PowerShell が終了しないことを示し `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-190">Indicates that the cmdlet suppresses the command prompt and prevents Windows PowerShell from closing until the `Out-GridView` window is closed.</span></span> <span data-ttu-id="10d26-191">既定では、ウィンドウが開いたときにコマンドプロンプトが返され `Out-GridView` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-191">By default, the command prompt returns when the `Out-GridView` window opens.</span></span>

<span data-ttu-id="10d26-192">この機能を使用すると、 `Out-GridView` Windows ショートカットのコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="10d26-192">This feature lets you use the `Out-GridView` cmdlets in Windows shortcuts.</span></span> <span data-ttu-id="10d26-193">`Out-GridView` **Wait** パラメーターを指定せずにショートカットでを使用すると、 `Out-GridView` PowerShell が閉じる前にウィンドウが一時的に表示されません。</span><span class="sxs-lookup"><span data-stu-id="10d26-193">When `Out-GridView` is used in a shortcut without the **Wait** parameter, the `Out-GridView` window appears only momentarily before PowerShell closes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Wait
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10d26-194">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="10d26-194">CommonParameters</span></span>

<span data-ttu-id="10d26-195">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="10d26-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10d26-196">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d26-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10d26-197">入力</span><span class="sxs-lookup"><span data-stu-id="10d26-197">INPUTS</span></span>

### <span data-ttu-id="10d26-198">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="10d26-198">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="10d26-199">このコマンドレットには、任意のオブジェクトを送信できます。</span><span class="sxs-lookup"><span data-stu-id="10d26-199">You can send any object to this cmdlet.</span></span>

## <span data-ttu-id="10d26-200">出力</span><span class="sxs-lookup"><span data-stu-id="10d26-200">OUTPUTS</span></span>

### <span data-ttu-id="10d26-201">なし</span><span class="sxs-lookup"><span data-stu-id="10d26-201">None</span></span>

<span data-ttu-id="10d26-202">通常、 `Out-GridView` はオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="10d26-202">Normally, `Out-GridView` does not return any objects.</span></span> <span data-ttu-id="10d26-203">**PassThru** パラメーターを使用すると、選択された行を表すオブジェクトがパイプラインに返されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-203">When using the **PassThru** parameter, the objects representing the selected rows are returned to the pipeline.</span></span>

## <span data-ttu-id="10d26-204">注</span><span class="sxs-lookup"><span data-stu-id="10d26-204">NOTES</span></span>

<span data-ttu-id="10d26-205">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="10d26-205">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="10d26-206">リモート コマンドを使用して、別のコンピューター上でグリッド ビュー ウィンドウを開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="10d26-206">You cannot use a remote command to open a grid view window on another computer.</span></span>

<span data-ttu-id="10d26-207">に送信するコマンドの出力は、コマンドレットやコマンドレットなどを `Out-GridView` 使用して書式設定することはできません `Format` `Format-Table` `Format-Wide` 。</span><span class="sxs-lookup"><span data-stu-id="10d26-207">The command output that you send to `Out-GridView` cannot be formatted using the `Format` cmdlets, such as `Format-Table` or `Format-Wide` cmdlets.</span></span> <span data-ttu-id="10d26-208">プロパティを選択するには、コマンドレットを使用し `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="10d26-208">To select properties, use the `Select-Object` cmdlet.</span></span>

<span data-ttu-id="10d26-209">リモート コマンドから逆シリアル化された出力をグリッド ビュー ウィンドウで適切に書式設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="10d26-209">Deserialized output from remote commands might not be formatted correctly in the grid view window.</span></span>

<span data-ttu-id="10d26-210">**のキーボードショートカット**`Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="10d26-210">**Keyboard Shortcuts for** `Out-GridView`</span></span>

|              <span data-ttu-id="10d26-211">使用するキー</span><span class="sxs-lookup"><span data-stu-id="10d26-211">Use this key:</span></span>              |                                   <span data-ttu-id="10d26-212">実行する操作</span><span class="sxs-lookup"><span data-stu-id="10d26-212">To perform this action:</span></span>                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------- |
| <span data-ttu-id="10d26-213"><kbd>タブ</kbd></span><span class="sxs-lookup"><span data-stu-id="10d26-213"><kbd>Tab</kbd></span></span>                          | <span data-ttu-id="10d26-214">**フィルター** ボックスから [ **条件の追加** ] メニューにカーソルを移動し、テーブルに戻ります。</span><span class="sxs-lookup"><span data-stu-id="10d26-214">Moves the cursor from the **Filter** box to the **Add criteria** menu to the table and back.</span></span> |
| <span data-ttu-id="10d26-215"><kbd>↑</kbd></span><span class="sxs-lookup"><span data-stu-id="10d26-215"><kbd>UpArrow</kbd></span></span>                      | <span data-ttu-id="10d26-216">1行上に移動します。</span><span class="sxs-lookup"><span data-stu-id="10d26-216">Move up one row.</span></span> <span data-ttu-id="10d26-217">最初のデータ行から列ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="10d26-217">Moves to column headers from first row of data.</span></span>                             |
| <span data-ttu-id="10d26-218"><kbd>下方向キー</kbd></span><span class="sxs-lookup"><span data-stu-id="10d26-218"><kbd>DownArrow</kbd></span></span>                    | <span data-ttu-id="10d26-219">1行下に移動します。</span><span class="sxs-lookup"><span data-stu-id="10d26-219">Move down one row.</span></span>                                                                           |
| <span data-ttu-id="10d26-220"><kbd>←</kbd></span><span class="sxs-lookup"><span data-stu-id="10d26-220"><kbd>LeftArrow</kbd></span></span>                    | <span data-ttu-id="10d26-221">列ヘッダー行で、1列左に移動します。</span><span class="sxs-lookup"><span data-stu-id="10d26-221">In column header row, move left one column.</span></span>                                                  |
| <span data-ttu-id="10d26-222"><kbd>→</kbd></span><span class="sxs-lookup"><span data-stu-id="10d26-222"><kbd>RightArrow</kbd></span></span>                   | <span data-ttu-id="10d26-223">列ヘッダー行で、1列右に移動します。</span><span class="sxs-lookup"><span data-stu-id="10d26-223">In column header row, move right one column.</span></span>                                                 |
| <span data-ttu-id="10d26-224"><kbd>ContextMenuKey</kbd></span><span class="sxs-lookup"><span data-stu-id="10d26-224"><kbd>ContextMenuKey</kbd></span></span>               | <span data-ttu-id="10d26-225">列ヘッダー行には、[列の選択] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-225">In column header row, displays the Select Columns option.</span></span>                                    |
| <span data-ttu-id="10d26-226"><kbd>Enter</kbd> または <kbd>space</kbd></span><span class="sxs-lookup"><span data-stu-id="10d26-226"><kbd>Enter</kbd> or <kbd>Spacebar</kbd></span></span> | <span data-ttu-id="10d26-227">列ヘッダー行で、列データを並べ替えます (A ~ Z、Z-A を切り替えます)。</span><span class="sxs-lookup"><span data-stu-id="10d26-227">In column header row, sort column data (toggle A-Z, Z-A).</span></span>                                    |

<span data-ttu-id="10d26-228">**グリッドビューウィンドウ機能を使用する方法**</span><span class="sxs-lookup"><span data-stu-id="10d26-228">**How to Use the Grid View Window Features**</span></span>

<span data-ttu-id="10d26-229">**列を非表示または表示するには、次の手順に従います。**</span><span class="sxs-lookup"><span data-stu-id="10d26-229">**To hide or show a column:**</span></span>

1. <span data-ttu-id="10d26-230">任意の列ヘッダーを右クリックし、[ **列の選択** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-230">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="10d26-231">**[列の選択** ] ダイアログボックスで、方向キーを使用して、選択した列間の列を [使用できる列] ボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="10d26-231">In the **Select Columns** dialog box, use the arrow keys to move the columns between the Selected columns to the Available columns boxes.</span></span> <span data-ttu-id="10d26-232">**[列の選択** ] ボックス内の列のみがグリッドビューウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-232">Only columns in the **Select Columns** box appear in the grid view window.</span></span>

<span data-ttu-id="10d26-233">**列を並べ替えるには、次の手順に従います。**</span><span class="sxs-lookup"><span data-stu-id="10d26-233">**To reorder columns:**</span></span>

<span data-ttu-id="10d26-234">列を目的の場所にドラッグアンドドロップすることができます。</span><span class="sxs-lookup"><span data-stu-id="10d26-234">You can drag and drop columns into the desired location.</span></span> <span data-ttu-id="10d26-235">または、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="10d26-235">Or use the following steps:</span></span>

1. <span data-ttu-id="10d26-236">任意の列ヘッダーを右クリックし、[ **列の選択** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-236">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="10d26-237">**[列の選択** ] ダイアログボックスで、[ **上へ移動** ] および [ **下へ移動** ] ボタンを使用して、列の順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="10d26-237">In the **Select Columns** dialog box, use the **Move up** and **Move down** buttons to reorder the columns.</span></span> <span data-ttu-id="10d26-238">一覧の上部にある列は、グリッド ビュー ウィンドウで、一覧の下部の列の左側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-238">Columns at the top of the list appear to the left of columns at the bottom of the list in the grid view window.</span></span>

<span data-ttu-id="10d26-239">**テーブルのデータを並べ替える方法**</span><span class="sxs-lookup"><span data-stu-id="10d26-239">**How to Sort Table Data**</span></span>

- <span data-ttu-id="10d26-240">データを並べ替えるには、列ヘッダーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-240">To sort the data, click a column header.</span></span>
- <span data-ttu-id="10d26-241">並べ替え順序を変更するには、列ヘッダーをもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-241">To change the sort order, click the column header again.</span></span> <span data-ttu-id="10d26-242">同じヘッダーをクリックするたびに、並べ替え順序が昇順と降順で切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="10d26-242">Each time you click the same header, the sort order toggles between ascending to descending order.</span></span> <span data-ttu-id="10d26-243">現在の順序は、列ヘッダーにある三角形で示されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-243">The current order is indicated by a triangle in the column header.</span></span>

<span data-ttu-id="10d26-244">**テーブルのデータを選択する方法**</span><span class="sxs-lookup"><span data-stu-id="10d26-244">**How to Select Table Data**</span></span>

- <span data-ttu-id="10d26-245">行を選択するには、行を選択するか、上矢印または下矢印を使用してその行に移動します。</span><span class="sxs-lookup"><span data-stu-id="10d26-245">To select a row, select the row or use the up or down arrow to navigate to the row.</span></span>
- <span data-ttu-id="10d26-246">(ヘッダー行を除く) すべての行を選択するには、 <kbd>ctrl</kbd> + <kbd>A</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="10d26-246">To select all rows (except for the header row), press <kbd>CTRL</kbd>+<kbd>A</kbd>.</span></span>
- <span data-ttu-id="10d26-247">連続する行を選択するには、 <kbd>shift</kbd> キーを押しながら行をクリックするか、方向キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="10d26-247">To select consecutive rows, press and hold the <kbd>SHIFT</kbd> key while clicking the rows or using the arrow keys.</span></span>
- <span data-ttu-id="10d26-248">連続しない rows を選択するには、CTRL キーを押し <kbd>ながら</kbd> クリックして選択に行を追加します。</span><span class="sxs-lookup"><span data-stu-id="10d26-248">To select nonconsecutive rows, press the <kbd>CTRL</kbd> key and click to add a row to the selection.</span></span>
- <span data-ttu-id="10d26-249">列を選択することや、列ヘッダー行全体を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="10d26-249">You cannot select columns, and you cannot select the entire column header row.</span></span>

<span data-ttu-id="10d26-250">**行をコピーする方法**</span><span class="sxs-lookup"><span data-stu-id="10d26-250">**How to Copy Rows**</span></span>

- <span data-ttu-id="10d26-251">テーブルから1つ以上の行をコピーするには、行を選択し、CTRL + C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="10d26-251">To copy one or more rows from the table, select the rows and then press CTRL+C.</span></span>

  <span data-ttu-id="10d26-252">任意のテキストやスプレッドシート プログラムにデータを貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="10d26-252">You can paste the data into any text or spreadsheet program.</span></span> <span data-ttu-id="10d26-253">列や行の一部をコピーすることはできません。また、列ヘッダー行をコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="10d26-253">You cannot copy columns or parts of rows and you cannot copy the column header row.</span></span>

<span data-ttu-id="10d26-254">**テーブルで検索する方法 (クイックフィルター)**</span><span class="sxs-lookup"><span data-stu-id="10d26-254">**How to Search in the Table (Quick Filter)**</span></span>

<span data-ttu-id="10d26-255">テーブル内のデータを検索するには、[フィルター] ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="10d26-255">Use the Filter box to search for data in the table.</span></span> <span data-ttu-id="10d26-256">ボックスに入力すると、指定したテキストを含む項目のみがテーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-256">When you type in the box, only items that include the typed text appear in the table.</span></span>

- <span data-ttu-id="10d26-257">テキストを検索します。</span><span class="sxs-lookup"><span data-stu-id="10d26-257">Search for text.</span></span> <span data-ttu-id="10d26-258">テーブル内のテキストを検索するには、[フィルター] ボックスに検索するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="10d26-258">To search for text in the table, in the Filter box, type the text to find.</span></span>
- <span data-ttu-id="10d26-259">複数の単語を検索します。</span><span class="sxs-lookup"><span data-stu-id="10d26-259">Search for multiple words.</span></span> <span data-ttu-id="10d26-260">テーブル内の複数の単語を検索するには、単語をスペースで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="10d26-260">To search for multiple words in the table, type the words separated by spaces.</span></span> <span data-ttu-id="10d26-261">`Out-GridView` すべての語 (論理 AND) を含む行を表示します。</span><span class="sxs-lookup"><span data-stu-id="10d26-261">`Out-GridView` displays rows that include all the words (logical AND).</span></span>
- <span data-ttu-id="10d26-262">リテラル語句を検索します。</span><span class="sxs-lookup"><span data-stu-id="10d26-262">Search for literal phrases.</span></span> <span data-ttu-id="10d26-263">スペースや特殊文字を含む語句を検索するには、語句を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="10d26-263">To search for phrases that include spaces or special characters, enclose the phrase in quotation marks.</span></span> <span data-ttu-id="10d26-264">`Out-GridView` 語句と完全に一致する行を表示します。</span><span class="sxs-lookup"><span data-stu-id="10d26-264">`Out-GridView` displays rows that include an exact match for the phrase.</span></span>
- <span data-ttu-id="10d26-265">列を検索します。</span><span class="sxs-lookup"><span data-stu-id="10d26-265">Search in columns.</span></span> <span data-ttu-id="10d26-266">1 列以上でテキストを検索するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="10d26-266">To search for text in one or more columns, use the following format:</span></span>

  `<column>:<text> [<column>:<text>] ...`

  <span data-ttu-id="10d26-267">たとえば、[ **DisplayName** ] 列で "Net" を検索するには、[ **フィルター** ] ボックスに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="10d26-267">For example, to find "Net" in the **DisplayName** column, in the **Filter** box, type:</span></span>

  `displayname:net`

  <span data-ttu-id="10d26-268">[ **DisplayName** ] 列と [ **Name** ] 列に "Net" を含む行を検索するには、[ **フィルター** ] ボックスに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="10d26-268">To find rows with "Net" in the **DisplayName** and **Name** columns, in the **Filter** box, type:</span></span>

  `displayname:net name:net`

- <span data-ttu-id="10d26-269">検索をオフにします。</span><span class="sxs-lookup"><span data-stu-id="10d26-269">Turn off search.</span></span> <span data-ttu-id="10d26-270">テーブル全体を再度表示するには、 **フィルター** ボックスの右上隅にある赤い [X] ボタンをクリックするか、[ **フィルター** ] ボックスからテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="10d26-270">To display the entire table again, click the red X button in the top right corner of the **Filter** box or delete the text from the **Filter** box.</span></span>

<span data-ttu-id="10d26-271">**条件を使用したテーブルのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="10d26-271">**Use Criteria to Filter the Table**</span></span>

<span data-ttu-id="10d26-272">ルールまたは条件を使用して、テーブルに表示するアイテムを決定できます。</span><span class="sxs-lookup"><span data-stu-id="10d26-272">You can use rules or criteria to determine which items are displayed in the table.</span></span> <span data-ttu-id="10d26-273">項目は、設定したすべての条件を満たしている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-273">Items appear only when they satisfy all the criteria that you establish.</span></span> <span data-ttu-id="10d26-274">使用可能な基準は、グリッド ビュー ウィンドウに表示されるオブジェクトのプロパティと、これらのプロパティの .NET Framework の型によって決まります。</span><span class="sxs-lookup"><span data-stu-id="10d26-274">The available criteria are determined by the properties of the objects displayed in the grid view window and the .NET Framework types of those properties.</span></span>

<span data-ttu-id="10d26-275">各条件は、次の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="10d26-275">Each criterion has the following format:</span></span>

`<column> <operator> <value>`

<span data-ttu-id="10d26-276">さまざまなプロパティの条件は **、と** によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-276">Criteria for different properties are connected by **AND**.</span></span> <span data-ttu-id="10d26-277">同じプロパティの条件は、 **または** によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-277">Criteria for the same property are connected by **OR**.</span></span> <span data-ttu-id="10d26-278">論理コネクタを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="10d26-278">You cannot change the logical connectors.</span></span>

<span data-ttu-id="10d26-279">条件は表示のみに影響します。</span><span class="sxs-lookup"><span data-stu-id="10d26-279">The criteria only affects the display.</span></span> <span data-ttu-id="10d26-280">項目はテーブルから削除されません。</span><span class="sxs-lookup"><span data-stu-id="10d26-280">It does not delete items from the table.</span></span>

<span data-ttu-id="10d26-281">**条件を追加する方法**</span><span class="sxs-lookup"><span data-stu-id="10d26-281">**How to Add Criteria**</span></span>

1. <span data-ttu-id="10d26-282">[条件の **追加** ] メニューボタンを表示するには、ウィンドウの右上隅にある展開矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-282">To display the **Add criteria** menu button, in the upper right corner of the window, click the Expand arrow.</span></span>
2. <span data-ttu-id="10d26-283">[ **条件の追加** ] メニューボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-283">Click the **Add Criteria** menu button.</span></span>
3. <span data-ttu-id="10d26-284">列 (プロパティ) をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="10d26-284">Click to select columns (properties).</span></span> <span data-ttu-id="10d26-285">1 つまたは複数のプロパティを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="10d26-285">You can select one or many properties.</span></span>
4. <span data-ttu-id="10d26-286">プロパティの選択が完了したら、[ **追加** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-286">When you are finished selecting properties, click the **Add** button.</span></span>
5. <span data-ttu-id="10d26-287">追加を取り消すには、[ **キャンセル** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-287">To cancel the additions, click **Cancel**.</span></span>
6. <span data-ttu-id="10d26-288">条件をさらに追加するには、[ **条件の追加** ] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-288">To add more criteria, click the **Add Criteria** button again.</span></span>

<span data-ttu-id="10d26-289">**条件の編集方法**</span><span class="sxs-lookup"><span data-stu-id="10d26-289">**How to Edit a Criterion**</span></span>

- <span data-ttu-id="10d26-290">演算子を変更するには、青の演算子の値をクリックし、ドロップダウンリストから別の演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="10d26-290">To change an operator, click the blue operator value, and then select a different operator from the drop-down list.</span></span>
- <span data-ttu-id="10d26-291">値を入力または変更するには、[値] ボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="10d26-291">To enter or change a value, type a value in the value box.</span></span> <span data-ttu-id="10d26-292">無効な値を入力した場合、円に X が付けられたアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d26-292">If you enter a value that is not valid, a circular X icon appears.</span></span> <span data-ttu-id="10d26-293">削除するには、値を変更します。</span><span class="sxs-lookup"><span data-stu-id="10d26-293">To remove it, change the value.</span></span>
- <span data-ttu-id="10d26-294">ステートメント **または** ステートメントを作成するには、同じプロパティを持つ条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="10d26-294">To create an **OR** statement, add a criteria with the same property.</span></span>

<span data-ttu-id="10d26-295">**条件を削除する方法**</span><span class="sxs-lookup"><span data-stu-id="10d26-295">**How to Delete Criteria**</span></span>

- <span data-ttu-id="10d26-296">選択した条件を削除するには、各条件の横にある赤い X 印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-296">To delete selected criteria, click the red X beside each criterion.</span></span>
- <span data-ttu-id="10d26-297">すべての条件を削除するには、[ **すべてクリア** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="10d26-297">To delete all criteria, click the **Clear All** button.</span></span>

## <span data-ttu-id="10d26-298">関連リンク</span><span class="sxs-lookup"><span data-stu-id="10d26-298">RELATED LINKS</span></span>

[<span data-ttu-id="10d26-299">Out-File</span><span class="sxs-lookup"><span data-stu-id="10d26-299">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="10d26-300">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="10d26-300">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="10d26-301">Out-String</span><span class="sxs-lookup"><span data-stu-id="10d26-301">Out-String</span></span>](Out-String.md)

