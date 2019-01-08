---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Out-* コマンドレットを使用してデータをリダイレクトする
ms.assetid: 2a4acd33-041d-43a5-a3e9-9608a4c52b0c
ms.openlocfilehash: f08879f436ce751b176af020aba21e90f09aa61f
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402389"
---
# <a name="redirecting-data-with-out--cmdlets"></a><span data-ttu-id="68d50-103">Out-\* コマンドレットを使用してデータをリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="68d50-103">Redirecting Data with Out-\* Cmdlets</span></span>

<span data-ttu-id="68d50-104">Windows PowerShell には、データ出力を直接制御できるようにするコマンドレットがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="68d50-104">Windows PowerShell provides several cmdlets that let you control data output directly.</span></span> <span data-ttu-id="68d50-105">これらのコマンドレットには、2 つの重要な特性があります。</span><span class="sxs-lookup"><span data-stu-id="68d50-105">These cmdlets share two important characteristics.</span></span>

<span data-ttu-id="68d50-106">まず、これらのコマンドレットは、通常、データをいくつかの形式のテキストに変換します。</span><span class="sxs-lookup"><span data-stu-id="68d50-106">First, they generally transform data to some form of text.</span></span> <span data-ttu-id="68d50-107">コマンドレットは、テキスト入力を必要とするシステム コンポーネントにデータを出力するので、変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="68d50-107">They do this because they output the data to system components that require text input.</span></span> <span data-ttu-id="68d50-108">これは、コマンドレットがオブジェクトを文字列として表現する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="68d50-108">This means they need to represent the objects as text.</span></span> <span data-ttu-id="68d50-109">したがって、テキストは Windows PowerShell のコンソール ウィンドウに表示される形式に書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="68d50-109">Therefore, the text is formatted as you see it in the Windows PowerShell console window.</span></span>

<span data-ttu-id="68d50-110">2 番目に、これらのコマンドレットは、Windows PowerShell から他の場所に情報を送信するために、Windows PowerShell の動詞 **Out** を使用します。</span><span class="sxs-lookup"><span data-stu-id="68d50-110">Second, these cmdlets use the Windows PowerShell verb **Out** because they send information out from Windows PowerShell to somewhere else.</span></span> <span data-ttu-id="68d50-111">**Out-Host** コマンドレットも例外ではありません。ホスト ウィンドウ表示は、Windows PowerShell の外部で行われます。</span><span class="sxs-lookup"><span data-stu-id="68d50-111">The **Out-Host** cmdlet is no exception: the host window display is outside of Windows PowerShell.</span></span> <span data-ttu-id="68d50-112">これは、Windows PowerShell の外部にデータが送信されるときに、データが実際に削除されるので、重要です。</span><span class="sxs-lookup"><span data-stu-id="68d50-112">This is important because when data is sent out of Windows PowerShell, it is actually removed.</span></span> <span data-ttu-id="68d50-113">ホスト ウィンドウにデータをページングするパイプラインを作成しようとする場合に、これが発生します。次に示すように、リストとして書式設定を試みます。</span><span class="sxs-lookup"><span data-stu-id="68d50-113">You can see this if you try to create a pipeline that pages data to the host window, and then attempt to format it as a list, as shown here:</span></span>

```powershell
Get-Process | Out-Host -Paging | Format-List
```

<span data-ttu-id="68d50-114">リスト形式で処理情報のページを表示するコマンドと思ったかもしれません。</span><span class="sxs-lookup"><span data-stu-id="68d50-114">You might expect the command to display pages of process information in list format.</span></span> <span data-ttu-id="68d50-115">そうではなく、既定の表形式のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d50-115">Instead, it displays the default tabular list:</span></span>

```output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    101       5     1076       3316    32     0.05   2888 alg
...
    618      18    39348      51108   143   211.20    740 explorer
    257       8     9752      16828    79     3.02   2560 explorer
...
<SPACE> next page; <CR> next line; Q quit
...
```

<span data-ttu-id="68d50-116">**Out-Host** コマンドレットは、データを直接にコンソールに送信します。したがって、**Format-List** コマンドは、書式を設定するものを何も受信しません。</span><span class="sxs-lookup"><span data-stu-id="68d50-116">The **Out-Host** cmdlet sends the data directly to the console, so the **Format-List** command never receives anything to format.</span></span>

<span data-ttu-id="68d50-117">このコマンドを構築する正しい方法は、次に示すように、**Out-Host** コマンドレットをパイプラインの最後に置くことです。</span><span class="sxs-lookup"><span data-stu-id="68d50-117">The correct way to structure this command is to put the **Out-Host** cmdlet at the end of the pipeline as shown below.</span></span> <span data-ttu-id="68d50-118">これによって、データがページングされて表示される前に、リスト形式に書式設定するよう処理されます。</span><span class="sxs-lookup"><span data-stu-id="68d50-118">This causes the process data to be formatted in a list before being paged and displayed.</span></span>

```
PS> Get-Process | Format-List | Out-Host -Paging

Id      : 2888
Handles : 101
CPU     : 0.046875
Name    : alg
...

Id      : 740
Handles : 612
CPU     : 211.703125
Name    : explorer

Id      : 2560
Handles : 257
CPU     : 3.015625
Name    : explorer
...
<SPACE> next page; <CR> next line; Q quit
...
```

<span data-ttu-id="68d50-119">これは、すべての **Out** コマンドレットに適用されます。</span><span class="sxs-lookup"><span data-stu-id="68d50-119">This applies to all of the **Out** cmdlets.</span></span> <span data-ttu-id="68d50-120">**Out** コマンドレットは、常にパイプラインの末尾に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d50-120">An **Out** cmdlet should always appear at the end of the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="68d50-121">すべての **Out** コマンドレットは、コンソール ウィンドウに有効な書式設定 (行の長さの制限を含む) を使用して、テキストとして出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="68d50-121">All the **Out** cmdlets render output as text, using the formatting in effect for the console window, including line length limits.</span></span>

#### <a name="paging-console-output-out-host"></a><span data-ttu-id="68d50-122">コンソール出力のページング (Out-Host)</span><span class="sxs-lookup"><span data-stu-id="68d50-122">Paging Console Output (Out-Host)</span></span>

<span data-ttu-id="68d50-123">既定では、Windows PowerShell は、データをホスト ウィンドウに送信します。実際にそのことを実行するのが Out-Host コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="68d50-123">By default, Windows PowerShell sends data to the host window, which is exactly what the Out-Host cmdlet does.</span></span> <span data-ttu-id="68d50-124">Out-Host コマンドレットの主な用途は、前に説明したようにデータのページングです。</span><span class="sxs-lookup"><span data-stu-id="68d50-124">The primary use for the Out-Host cmdlet is paging data as we discussed earlier.</span></span> <span data-ttu-id="68d50-125">たとえば、次のコマンドは、Out-Host を使用して、Get-Command コマンドレットの出力をページングします。</span><span class="sxs-lookup"><span data-stu-id="68d50-125">For example, the following command uses Out-Host to page the output of the Get-Command cmdlet:</span></span>

```powershell
Get-Command | Out-Host -Paging
```

<span data-ttu-id="68d50-126">**more** 関数を使用して、データをページングすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="68d50-126">You can also use the **more** function to page data.</span></span> <span data-ttu-id="68d50-127">Windows PowerShell では、**more** は、**Out-Host -Paging** を呼び出す関数です。</span><span class="sxs-lookup"><span data-stu-id="68d50-127">In Windows PowerShell, **more** is a function that calls **Out-Host -Paging**.</span></span> <span data-ttu-id="68d50-128">次のコマンドの使用例は、**more** 関数を使用して、Get-Command の出力をページングします。</span><span class="sxs-lookup"><span data-stu-id="68d50-128">The following command demonstrates using the **more** function to page the output of Get-Command:</span></span>

```powershell
Get-Command | more
```

<span data-ttu-id="68d50-129">more 関数の引数として、1 つ以上のファイル名を含める場合、関数は指定されたファイルを読み取り、ホストにその内容をページングします。</span><span class="sxs-lookup"><span data-stu-id="68d50-129">If you include one or more filenames as arguments to the more function, the function will read the specified files and page their contents to the host:</span></span>

```
PS> more c:\boot.ini
[boot loader]
timeout=5
default=multi(0)disk(0)rdisk(0)partition(1)\WINDOWS
[operating systems]
...
```

#### <a name="discarding-output-out-null"></a><span data-ttu-id="68d50-130">出力の破棄 (Out-Null)</span><span class="sxs-lookup"><span data-stu-id="68d50-130">Discarding Output (Out-Null)</span></span>

<span data-ttu-id="68d50-131">**Out-Null** コマンドレットは、受け取ったすべての入力を直ちに破棄するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="68d50-131">The **Out-Null** cmdlet is designed to immediately discard any input it receives.</span></span> <span data-ttu-id="68d50-132">これは、コマンドを実行する副作用として受け取る不要なデータを破棄するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="68d50-132">This is useful for discarding unnecessary data that you get as a side-effect of running a command.</span></span> <span data-ttu-id="68d50-133">次のコマンドを入力すると、コマンドからは何も返ってきません。</span><span class="sxs-lookup"><span data-stu-id="68d50-133">When type the following command, you do not get anything back from the command:</span></span>

```powershell
Get-Command | Out-Null
```

<span data-ttu-id="68d50-134">**Out-Null** コマンドレットは、エラー出力を破棄しません。</span><span class="sxs-lookup"><span data-stu-id="68d50-134">The **Out-Null** cmdlet does not discard error output.</span></span> <span data-ttu-id="68d50-135">たとえば、次のようにコマンドを入力する場合、Windows PowerShell が 'Is-NotACommand' を認識しないことを通知するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d50-135">For example, if you enter the following command, a message is displayed informing you that Windows PowerShell does not recognize 'Is-NotACommand':</span></span>

```
PS> Get-Command Is-NotACommand | Out-Null
Get-Command : 'Is-NotACommand' is not recognized as a cmdlet, function, operabl
e program, or script file.
At line:1 char:12
+ Get-Command  <<<< Is-NotACommand | Out-Null
```

#### <a name="printing-data-out-printer"></a><span data-ttu-id="68d50-136">データの印刷 (Out-Printer)</span><span class="sxs-lookup"><span data-stu-id="68d50-136">Printing Data (Out-Printer)</span></span>

<span data-ttu-id="68d50-137">**Out-Printer** コマンドレットを使用してデータを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="68d50-137">You can print data by using the **Out-Printer** cmdlet.</span></span> <span data-ttu-id="68d50-138">**Out-Printer** コマンドレットは、プリンター名を指定しない場合、通常使うプリンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="68d50-138">The **Out-Printer** cmdlet will use your default printer if you do not provide a printer name.</span></span> <span data-ttu-id="68d50-139">任意の Windows ベースのプリンターを、その表示名を指定して使用できます。</span><span class="sxs-lookup"><span data-stu-id="68d50-139">You can use any Windows-based printer by specifying its display name.</span></span> <span data-ttu-id="68d50-140">どんな種類のプリンター ポートのマッピングも (実際の物理プリンターの場合でも) 必要ありません。</span><span class="sxs-lookup"><span data-stu-id="68d50-140">There is no need for any kind of printer port mapping or even a real physical printer.</span></span> <span data-ttu-id="68d50-141">たとえば、Microsoft Office 文書のイメージング ツールがインストールされている場合、次のように入力して、データをイメージ ファイルに送信できます。</span><span class="sxs-lookup"><span data-stu-id="68d50-141">For example, if you have the Microsoft Office document imaging tools installed, you can send the data to an image file by typing:</span></span>

```powershell
Get-Command Get-Command | Out-Printer -Name 'Microsoft Office Document Image Writer'
```

#### <a name="saving-data-out-file"></a><span data-ttu-id="68d50-142">データの保存 (Out-File)</span><span class="sxs-lookup"><span data-stu-id="68d50-142">Saving Data (Out-File)</span></span>

<span data-ttu-id="68d50-143">**Out-File** コマンドレットを使用して、出力をコンソール ウィンドウにではなく、ファイルに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="68d50-143">You can send output to a file instead of the console window by using the **Out-File** cmdlet.</span></span> <span data-ttu-id="68d50-144">次のコマンド ラインは、プロセスの一覧をファイル **C:\\temp\\processlist.txt** に送信します。</span><span class="sxs-lookup"><span data-stu-id="68d50-144">The following command line sends a list of processes to the file **C:\\temp\\processlist.txt**:</span></span>

```powershell
Get-Process | Out-File -FilePath C:\temp\processlist.txt
```

<span data-ttu-id="68d50-145">従来の出力のリダイレクトを使用している場合、**Out-File** コマンドレットを使用した結果は、期待どおりではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68d50-145">The results of using the **Out-File** cmdlet may not be what you expect if you are used to traditional output redirection.</span></span> <span data-ttu-id="68d50-146">その動作を理解するために、**Out-File** コマンドレット操作の状況を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d50-146">To understand its behavior, you must be aware of the context in which the **Out-File** cmdlet operates.</span></span>

<span data-ttu-id="68d50-147">既定では、**Out-File** コマンドレットは、Unicode ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="68d50-147">By default, the **Out-File** cmdlet creates a Unicode file.</span></span> <span data-ttu-id="68d50-148">長期的には、これが最適な既定です。しかし、ASCII ファイルを前提とするツールは、既定の出力形式では正しく動作しないことになります。</span><span class="sxs-lookup"><span data-stu-id="68d50-148">This is the best default in the long run, but it means that tools that expect ASCII files will not work correctly with the default output format.</span></span> <span data-ttu-id="68d50-149">**Encoding** パラメーターを使用して、既定の出力フォーマットを ASCII 形式に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="68d50-149">You can change the default output format to ASCII by using the **Encoding** parameter:</span></span>

```powershell
Get-Process | Out-File -FilePath C:\temp\processlist.txt -Encoding ASCII
```

<span data-ttu-id="68d50-150">**Out-file** は、ファイルの内容をコンソール出力に表示されるように書式設定します。</span><span class="sxs-lookup"><span data-stu-id="68d50-150">**Out-file** formats file contents to look like console output.</span></span> <span data-ttu-id="68d50-151">これによって、ほとんどの状況で、コンソール ウィンドウ内に表示されるのと同じように、出力は切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="68d50-151">This causes the output to be truncated just as it is in a console window in most circumstances.</span></span> <span data-ttu-id="68d50-152">たとえば、次のようにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="68d50-152">For example, if you run the following command:</span></span>

```powershell
Get-Command | Out-File -FilePath c:\temp\output.txt
```

<span data-ttu-id="68d50-153">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="68d50-153">The output will look like this:</span></span>

```output
CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Add-Content                     Add-Content [-Path] <String[...
Cmdlet          Add-History                     Add-History [[-InputObject] ...
...
```

<span data-ttu-id="68d50-154">行の折り返しを画面の幅に合わせないで出力するには、**Width** パラメーターを使用して行の幅を指定します。</span><span class="sxs-lookup"><span data-stu-id="68d50-154">To get output that does not force line wraps to match the screen width, you can use the **Width** parameter to specify line width.</span></span> <span data-ttu-id="68d50-155">**Width** が 32 ビットの整数パラメーターであるため、最大値は 2147483647 です。</span><span class="sxs-lookup"><span data-stu-id="68d50-155">Because **Width** is a 32-bit integer parameter, the maximum value it can have is 2147483647.</span></span> <span data-ttu-id="68d50-156">行の幅に、この最大値を設定するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="68d50-156">Type the following to set the line width to this maximum value:</span></span>

```powershell
Get-Command | Out-File -FilePath c:\temp\output.txt -Width 2147483647
```

<span data-ttu-id="68d50-157">**Out-File** コマンドレットは、ちょうどコンソールに表示されるように出力を保存する場合、最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="68d50-157">The **Out-File** cmdlet is most useful when you want to save output as it would have displayed on the console.</span></span> <span data-ttu-id="68d50-158">出力書式設定をさらに細かく制御するには、より高度なツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="68d50-158">For finer control over output format, you need more advanced tools.</span></span> <span data-ttu-id="68d50-159">次の章で、これらについて、またオブジェクト操作についての詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="68d50-159">We will look at those in the next chapter, along with some details about object manipulation.</span></span>