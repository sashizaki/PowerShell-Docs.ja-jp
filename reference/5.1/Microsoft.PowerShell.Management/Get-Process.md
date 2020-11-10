---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Process
ms.openlocfilehash: d1a576ce9c718561718bac5fee065983a057d458
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388299"
---
# <span data-ttu-id="d4edf-103">Get-Process</span><span class="sxs-lookup"><span data-stu-id="d4edf-103">Get-Process</span></span>

## <span data-ttu-id="d4edf-104">概要</span><span class="sxs-lookup"><span data-stu-id="d4edf-104">SYNOPSIS</span></span>
<span data-ttu-id="d4edf-105">ローカル コンピューターまたはリモート コンピューター上で実行されているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-105">Gets the processes that are running on the local computer or a remote computer.</span></span>

## <span data-ttu-id="d4edf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d4edf-106">SYNTAX</span></span>

### <span data-ttu-id="d4edf-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="d4edf-107">Name (Default)</span></span>

```
Get-Process [[-Name] <String[]>] [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="d4edf-108">NameWithUserName</span><span class="sxs-lookup"><span data-stu-id="d4edf-108">NameWithUserName</span></span>

```
Get-Process [[-Name] <String[]>] [-IncludeUserName] [<CommonParameters>]
```

### <span data-ttu-id="d4edf-109">IdWithUserName</span><span class="sxs-lookup"><span data-stu-id="d4edf-109">IdWithUserName</span></span>

```
Get-Process -Id <Int32[]> [-IncludeUserName] [<CommonParameters>]
```

### <span data-ttu-id="d4edf-110">Id</span><span class="sxs-lookup"><span data-stu-id="d4edf-110">Id</span></span>

```
Get-Process -Id <Int32[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="d4edf-111">InputObjectWithUserName</span><span class="sxs-lookup"><span data-stu-id="d4edf-111">InputObjectWithUserName</span></span>

```
Get-Process -InputObject <Process[]> [-IncludeUserName] [<CommonParameters>]
```

### <span data-ttu-id="d4edf-112">InputObject</span><span class="sxs-lookup"><span data-stu-id="d4edf-112">InputObject</span></span>

```
Get-Process -InputObject <Process[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo]
 [<CommonParameters>]
```

## <span data-ttu-id="d4edf-113">Description</span><span class="sxs-lookup"><span data-stu-id="d4edf-113">DESCRIPTION</span></span>

<span data-ttu-id="d4edf-114">`Get-Process`コマンドレットは、ローカルコンピューターまたはリモートコンピューター上のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-114">The `Get-Process` cmdlet gets the processes on a local or remote computer.</span></span>

<span data-ttu-id="d4edf-115">パラメーターを指定しない場合、このコマンドレットはローカルコンピューター上のすべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-115">Without parameters, this cmdlet gets all of the processes on the local computer.</span></span> <span data-ttu-id="d4edf-116">また、プロセス名またはプロセス ID (PID) を使用して特定のプロセスを指定したり、パイプラインを介してこのコマンドレットにプロセスオブジェクトを渡したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-116">You can also specify a particular process by process name or process ID (PID) or pass a process object through the pipeline to this cmdlet.</span></span>

<span data-ttu-id="d4edf-117">既定では、このコマンドレットは、プロセスに関する詳細情報を持つプロセスオブジェクトを返し、プロセスを開始および停止できるようにするメソッドをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d4edf-117">By default, this cmdlet returns a process object that has detailed information about the process and supports methods that let you start and stop the process.</span></span> <span data-ttu-id="d4edf-118">また、コマンドレットのパラメーターを使用して、 `Get-Process` プロセスで実行されるプログラムのファイルバージョン情報を取得したり、プロセスによって読み込まれたモジュールを取得したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-118">You can also use the parameters of the `Get-Process` cmdlet to get file version information for the program that runs in the process and to get the modules that the process loaded.</span></span>

## <span data-ttu-id="d4edf-119">例</span><span class="sxs-lookup"><span data-stu-id="d4edf-119">EXAMPLES</span></span>

### <span data-ttu-id="d4edf-120">例 1: ローカルコンピューター上のすべてのアクティブなプロセスの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="d4edf-120">Example 1: Get a list of all active processes on the local computer</span></span>

```powershell
Get-Process
```

<span data-ttu-id="d4edf-121">このコマンドは、ローカルコンピューター上で実行されているすべてのアクティブなプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-121">This command gets a list of all active processes running on the local computer.</span></span> <span data-ttu-id="d4edf-122">各列の定義については、「 [メモ](#notes) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4edf-122">For a definition of each column, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="d4edf-123">例 2: 1 つ以上のプロセスについて使用可能なすべてのデータを取得する</span><span class="sxs-lookup"><span data-stu-id="d4edf-123">Example 2: Get all available data about one or more processes</span></span>

```powershell
Get-Process winword, explorer | Format-List *
```

<span data-ttu-id="d4edf-124">このコマンドは、コンピューター上の Winword プロセスと Explorer プロセスに関して利用可能なすべてのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-124">This command gets all available data about the Winword and Explorer processes on the computer.</span></span> <span data-ttu-id="d4edf-125">**Name** パラメーターを使用してプロセスを指定しますが、省略可能なパラメーター名は省略しています。</span><span class="sxs-lookup"><span data-stu-id="d4edf-125">It uses the **Name** parameter to specify the processes, but it omits the optional parameter name.</span></span> <span data-ttu-id="d4edf-126">パイプライン演算子は `|` データを `Format-List` コマンドレットに渡します。これにより、 `*` winword.exe および Explorer プロセスオブジェクトの使用可能なすべてのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-126">The pipeline operator `|` passes the data to the `Format-List` cmdlet, which displays all available properties `*` of the Winword and Explorer process objects.</span></span>

<span data-ttu-id="d4edf-127">プロセスをプロセス ID で指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-127">You can also identify the processes by their process IDs.</span></span> <span data-ttu-id="d4edf-128">たとえば、`Get-Process -Id 664, 2060` のようになります。</span><span class="sxs-lookup"><span data-stu-id="d4edf-128">For instance, `Get-Process -Id 664, 2060`.</span></span>

### <span data-ttu-id="d4edf-129">例 3: ワーキングセットが指定したサイズを超えるすべてのプロセスを取得する</span><span class="sxs-lookup"><span data-stu-id="d4edf-129">Example 3: Get all processes with a working set greater than a specified size</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -gt 20000000}
```

<span data-ttu-id="d4edf-130">このコマンドは、ワーキング セットが 20 MB を超えているプロセスをすべて取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-130">This command gets all processes that have a working set greater than 20 MB.</span></span> <span data-ttu-id="d4edf-131">コマンドレットを使用して、 `Get-Process` 実行中のすべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-131">It uses the `Get-Process` cmdlet to get all running processes.</span></span> <span data-ttu-id="d4edf-132">パイプライン演算子は、 `|` プロセスオブジェクトを `Where-Object` コマンドレットに渡します。このコマンドレットは、 **ワーキング** セットプロパティの値が2000万バイトを超えるオブジェクトのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-132">The pipeline operator `|` passes the process objects to the `Where-Object` cmdlet, which selects only the object with a value greater than 20,000,000 bytes for the **WorkingSet** property.</span></span>

<span data-ttu-id="d4edf-133">**ワーキング** セットは、プロセスオブジェクトの多くのプロパティの1つです。</span><span class="sxs-lookup"><span data-stu-id="d4edf-133">**WorkingSet** is one of many properties of process objects.</span></span> <span data-ttu-id="d4edf-134">すべてのプロパティを表示するには、「」と入力 `Get-Process | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-134">To see all of the properties, type `Get-Process | Get-Member`.</span></span> <span data-ttu-id="d4edf-135">既定では、既定の表示がキロバイト単位やメガバイト単位であっても、サイズに関するプロパティの値はすべてバイト単位で表されます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-135">By default, the values of all amount properties are in bytes, even though the default display lists them in kilobytes and megabytes.</span></span>

### <span data-ttu-id="d4edf-136">例 4: 優先度に基づいてグループ内のコンピューターのプロセスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="d4edf-136">Example 4: List processes on the computer in groups based on priority</span></span>

```powershell
$A = Get-Process
$A | Get-Process | Format-Table -View priority
```

<span data-ttu-id="d4edf-137">これらのコマンドは、コンピューター上のプロセスを優先度クラスに基づいてグループ化します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-137">These commands list the processes on the computer in groups based on their priority class.</span></span> <span data-ttu-id="d4edf-138">最初のコマンドは、コンピューター上のすべてのプロセスを取得し、変数に格納し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-138">The first command gets all the processes on the computer and then stores them in the `$A` variable.</span></span>

<span data-ttu-id="d4edf-139">2番目のコマンドは、変数に格納されている **プロセス** オブジェクトをコマンド `$A` レットに渡し、 `Get-Process` `Format-Table` コマンドレットに渡します。このコマンドレットは、 **優先度** ビューを使用してプロセスをフォーマットします。</span><span class="sxs-lookup"><span data-stu-id="d4edf-139">The second command pipes the **Process** object stored in the `$A` variable to the `Get-Process` cmdlet, then to the `Format-Table` cmdlet, which formats the processes by using the **Priority** view.</span></span>

<span data-ttu-id="d4edf-140">**優先度** ビュー、およびその他のビューは、PowerShell ホームディレクトリ () の types.ps1xml フォーマットファイルで定義されてい `$pshome` ます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-140">The **Priority** view, and other views, are defined in the PS1XML format files in the PowerShell home directory (`$pshome`).</span></span>

### <span data-ttu-id="d4edf-141">例 5: 標準 Get-Process 出力表示にプロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="d4edf-141">Example 5: Add a property to the standard Get-Process output display</span></span>

```powershell
Get-Process powershell -ComputerName S1, localhost | Format-Table `
    @{Label = "NPM(K)"; Expression = {[int]($_.NPM / 1024)}},
    @{Label = "PM(K)"; Expression = {[int]($_.PM / 1024)}},
    @{Label = "WS(K)"; Expression = {[int]($_.WS / 1024)}},
    @{Label = "VM(M)"; Expression = {[int]($_.VM / 1MB)}},
    @{Label = "CPU(s)"; Expression = {if ($_.CPU) {$_.CPU.ToString("N")}}},
    Id, MachineName, ProcessName -AutoSize
```

```Output
NPM(K) PM(K) WS(K) VM(M) CPU(s)   Id MachineName ProcessName
------ ----- ----- ----- ------   -- ----------- -----------
     6 23500 31340   142 1.70   1980 S1          powershell
     6 23500 31348   142 2.75   4016 S1          powershell
    27 54572 54520   576 5.52   4428 localhost   powershell
```

<span data-ttu-id="d4edf-142">この例では、ローカルコンピューターとリモートコンピューター (S1) からプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-142">This example retrieves processes from the local computer and a remote computer (S1).</span></span> <span data-ttu-id="d4edf-143">取得したプロセスは、 `Format-Table` **MachineName** プロパティを標準出力表示に追加するコマンドにパイプされ `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-143">The retrieved processes are piped to the `Format-Table` command that adds the **MachineName** property to the standard `Get-Process` output display.</span></span>

### <span data-ttu-id="d4edf-144">例 6: プロセスのバージョン情報を取得する</span><span class="sxs-lookup"><span data-stu-id="d4edf-144">Example 6: Get version information for a process</span></span>

```powershell
Get-Process powershell -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.1.6713.1       6.1.6713.1 (f... C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe
```

<span data-ttu-id="d4edf-145">このコマンドは、 **FileVersionInfo** パラメーターを使用して、PowerShell プロセスのメインモジュールである powershell.exe ファイルのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-145">This command uses the **FileVersionInfo** parameter to get the version information for the powershell.exe file that is the main module for the PowerShell process.</span></span>

<span data-ttu-id="d4edf-146">Windows Vista 以降のバージョンの Windows で所有していないプロセスでこのコマンドを実行するには、[管理者として実行] オプションを使用して PowerShell を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4edf-146">To run this command with processes that you do not own on Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="d4edf-147">例 7: 指定したプロセスで読み込まれたモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="d4edf-147">Example 7: Get modules loaded with the specified process</span></span>

```powershell
Get-Process SQL* -Module
```

<span data-ttu-id="d4edf-148">このコマンドは、 **Module** パラメーターを使用して、プロセスによって読み込まれたモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-148">This command uses the **Module** parameter to get the modules that have been loaded by the process.</span></span>
<span data-ttu-id="d4edf-149">このコマンドは、名前が SQL で始まるプロセスのモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-149">This command gets the modules for the processes that have names that begin with SQL.</span></span>

<span data-ttu-id="d4edf-150">Windows Vista 以降のバージョンの Windows で、自分が所有していないプロセスを使用してこのコマンドを実行するには、[管理者として実行] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4edf-150">To run this command on Windows Vista and later versions of Windows with processes that you do not own, you must start PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="d4edf-151">例 8: プロセスの所有者を検索する</span><span class="sxs-lookup"><span data-stu-id="d4edf-151">Example 8: Find the owner of a process</span></span>

```powershell
Get-Process pwsh -IncludeUserName
```

```Output
Handles      WS(K)   CPU(s)     Id UserName            ProcessName
-------      -----   ------     -- --------            -----------
    782     132080     2.08   2188 DOMAIN01\user01     powershell
```

```powershell
$p = Get-WmiObject Win32_Process -Filter "name='powershell.exe'"
$p.GetOwner()
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 3
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Domain           : DOMAIN01
ReturnValue      : 0
User             : user01
```

<span data-ttu-id="d4edf-152">最初のコマンドは、プロセスの所有者を検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d4edf-152">The first command shows how to find the owner of a process.</span></span> <span data-ttu-id="d4edf-153">**Includeusername** パラメーターには、管理者特権 ([管理者として実行]) が必要です。</span><span class="sxs-lookup"><span data-stu-id="d4edf-153">The **IncludeUserName** parameter requires elevated user rights (Run as Administrator).</span></span> <span data-ttu-id="d4edf-154">出力には、所有者が Domain01\user01 であることが示されます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-154">The output reveals that the owner is Domain01\user01.</span></span>

<span data-ttu-id="d4edf-155">2番目と3番目のコマンドは、プロセスの所有者を検索するもう1つの方法です。</span><span class="sxs-lookup"><span data-stu-id="d4edf-155">The second and third command are another way to find the owner of a process.</span></span>

<span data-ttu-id="d4edf-156">2番目のコマンドは、を使用し `Get-WmiObject` て PowerShell プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-156">The second command uses `Get-WmiObject` to get the PowerShell process.</span></span>
<span data-ttu-id="d4edf-157">変数に保存 `$p` します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-157">It saves it in the `$p` variable.</span></span>

<span data-ttu-id="d4edf-158">3番目のコマンドは、GetOwner メソッドを使用して、のプロセスの所有者を取得し `$p` ます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-158">The third command uses the GetOwner method to get the owner of the process in `$p`.</span></span> <span data-ttu-id="d4edf-159">出力には、所有者が Domain01\user01 であることが示されます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-159">The output reveals that the owner is Domain01\user01.</span></span>

### <span data-ttu-id="d4edf-160">例 9: 自動変数を使用して、現在のセッションをホストしているプロセスを識別する</span><span class="sxs-lookup"><span data-stu-id="d4edf-160">Example 9: Use an automatic variable to identify the process hosting the current session</span></span>

```powershell
Get-Process powershell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
308      26        52308      61780   567     3.18   5632 powershell
377      26        62676      63384   575     3.88   5888 powershell
```

```powershell
Get-Process -Id $PID
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
396      26        56488      57236   575     3.90   5888 powershell
```

<span data-ttu-id="d4edf-161">これらのコマンドは、自動変数を使用して、現在の PowerShell セッションをホストしているプロセスを識別する方法を示して `$PID` います。</span><span class="sxs-lookup"><span data-stu-id="d4edf-161">These commands show how to use the `$PID` automatic variable to identify the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="d4edf-162">このメソッドを使用すると、停止または終了する PowerShell プロセスとホスト プロセスを区別できます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-162">You can use this method to distinguish the host process from other PowerShell processes that you might want to stop or close.</span></span>

<span data-ttu-id="d4edf-163">最初のコマンドは、現在のセッションのすべての PowerShell プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-163">The first command gets all of the PowerShell processes in the current session.</span></span>

<span data-ttu-id="d4edf-164">2番目のコマンドは、現在のセッションをホストしている PowerShell プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-164">The second command gets the PowerShell process that is hosting the current session.</span></span>

### <span data-ttu-id="d4edf-165">例 10: メインウィンドウタイトルを持つすべてのプロセスを取得し、テーブルに表示する</span><span class="sxs-lookup"><span data-stu-id="d4edf-165">Example 10: Get all processes that have a main window title and display them in a table</span></span>

```powershell
Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id, Name, mainWindowtitle -AutoSize
```

<span data-ttu-id="d4edf-166">このコマンドは、メイン ウィンドウ タイトルを持つすべてのプロセスを取得し、プロセス ID とプロセス名の表形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-166">This command gets all the processes that have a main window title, and it displays them in a table with the process ID and the process name.</span></span>

<span data-ttu-id="d4edf-167">**MainWindowTitle** プロパティは、を返す **Process** オブジェクトの多くの便利なプロパティのうちの1つにすぎ `Get-Process` ません。</span><span class="sxs-lookup"><span data-stu-id="d4edf-167">The **mainWindowTitle** property is just one of many useful properties of the **Process** object that `Get-Process` returns.</span></span> <span data-ttu-id="d4edf-168">すべてのプロパティを表示するには、コマンドの結果を `Get-Process` コマンドレットに渡し `Get-Member` `Get-Process | Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-168">To view all of the properties, pipe the results of a `Get-Process` command to the `Get-Member` cmdlet `Get-Process | Get-Member`.</span></span>

## <span data-ttu-id="d4edf-169">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d4edf-169">PARAMETERS</span></span>

### <span data-ttu-id="d4edf-170">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d4edf-170">-ComputerName</span></span>

<span data-ttu-id="d4edf-171">このコマンドレットがアクティブなプロセスを取得するコンピュータを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-171">Specifies the computers for which this cmdlet gets active processes.</span></span> <span data-ttu-id="d4edf-172">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="d4edf-172">The default is the local computer.</span></span>

<span data-ttu-id="d4edf-173">1つまたは複数のコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-173">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of one or more computers.</span></span> <span data-ttu-id="d4edf-174">ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-174">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="d4edf-175">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="d4edf-175">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="d4edf-176">コンピューターがリモートコマンドを実行するように構成されていない場合でも、このコマンドレットの **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-176">You can use the **ComputerName** parameter of this cmdlet even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, Id, InputObject
Aliases: Cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d4edf-177">-FileVersionInfo</span><span class="sxs-lookup"><span data-stu-id="d4edf-177">-FileVersionInfo</span></span>

<span data-ttu-id="d4edf-178">このコマンドレットが、プロセスで実行されるプログラムのファイルバージョン情報を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-178">Indicates that this cmdlet gets the file version information for the program that runs in the process.</span></span>

<span data-ttu-id="d4edf-179">Windows Vista 以降のバージョンの Windows では、[管理者として実行] オプションを使用して PowerShell を開いて、所有していないプロセスでこのパラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4edf-179">On Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="d4edf-180">コマンドレットの **FileVersionInfo** パラメーターと **ComputerName** パラメーターを `Get-Process` 同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4edf-180">You cannot use the **FileVersionInfo** and **ComputerName** parameters of the `Get-Process` cmdlet in the same command.</span></span>

<span data-ttu-id="d4edf-181">リモートコンピューター上のプロセスのファイルバージョン情報を取得するには、 `Invoke-Command` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-181">To get file version information for a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="d4edf-182">このパラメーターを使用することは、各プロセスオブジェクトの **FileVersionInfo** プロパティを取得することと同じです。</span><span class="sxs-lookup"><span data-stu-id="d4edf-182">Using this parameter is equivalent to getting the **MainModule.FileVersionInfo** property of each process object.</span></span> <span data-ttu-id="d4edf-183">このパラメーターを使用すると、は `Get-Process` プロセスオブジェクトではなく、 **FileVersionInfo** オブジェクト **FileVersionInfo** を返します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-183">When you use this parameter, `Get-Process` returns a **FileVersionInfo** object **System.Diagnostics.FileVersionInfo** , not a process object.</span></span> <span data-ttu-id="d4edf-184">そのため、コマンドの出力を、などのプロセスオブジェクトを必要とするコマンドレットにパイプすることはできません `Stop-Process` 。</span><span class="sxs-lookup"><span data-stu-id="d4edf-184">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases: FV, FVI

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4edf-185">-Id</span><span class="sxs-lookup"><span data-stu-id="d4edf-185">-Id</span></span>

<span data-ttu-id="d4edf-186">プロセス ID (PID) を使用して、プロセスを 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-186">Specifies one or more processes by process ID (PID).</span></span> <span data-ttu-id="d4edf-187">複数の ID を指定するには、ID をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="d4edf-187">To specify multiple IDs, use commas to separate the IDs.</span></span> <span data-ttu-id="d4edf-188">プロセスの PID を検索するには、「」と入力 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-188">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IdWithUserName, Id
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d4edf-189">-IncludeUserName</span><span class="sxs-lookup"><span data-stu-id="d4edf-189">-IncludeUserName</span></span>

<span data-ttu-id="d4edf-190">**プロセス** オブジェクトのユーザー名の値がコマンドの結果と共に返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-190">Indicates that the UserName value of the **Process** object is returned with results of the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameWithUserName, IdWithUserName, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4edf-191">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d4edf-191">-InputObject</span></span>

<span data-ttu-id="d4edf-192">1 つまたは複数のプロセス オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-192">Specifies one or more process objects.</span></span> <span data-ttu-id="d4edf-193">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-193">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObjectWithUserName, InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d4edf-194">-モジュール</span><span class="sxs-lookup"><span data-stu-id="d4edf-194">-Module</span></span>

<span data-ttu-id="d4edf-195">このコマンドレットが、プロセスによって読み込まれたモジュールを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-195">Indicates that this cmdlet gets the modules that have been loaded by the processes.</span></span>

<span data-ttu-id="d4edf-196">Windows Vista 以降のバージョンの Windows では、[ **管理者として実行** ] オプションを使用して PowerShell を開いて、所有していないプロセスでこのパラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4edf-196">On Windows Vista and later versions of Windows, you must open PowerShell with the **Run as administrator** option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="d4edf-197">リモートコンピューター上のプロセスによって読み込まれたモジュールを取得するには、コマンドレットを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-197">To get the modules that have been loaded by a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="d4edf-198">このパラメーターは、各プロセスオブジェクトの **Modules** プロパティを取得することと同じです。</span><span class="sxs-lookup"><span data-stu-id="d4edf-198">This parameter is equivalent to getting the **Modules** property of each process object.</span></span> <span data-ttu-id="d4edf-199">このパラメーターを使用すると、このコマンドレットはプロセスオブジェクトではなく **processmodule** **オブジェクトを返します。**</span><span class="sxs-lookup"><span data-stu-id="d4edf-199">When you use this parameter, this cmdlet returns a **ProcessModule** object **System.Diagnostics.ProcessModule** , not a process object.</span></span> <span data-ttu-id="d4edf-200">そのため、コマンドの出力を、などのプロセスオブジェクトを必要とするコマンドレットにパイプすることはできません `Stop-Process` 。</span><span class="sxs-lookup"><span data-stu-id="d4edf-200">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

<span data-ttu-id="d4edf-201">同じコマンドで *Module* と **FileVersionInfo** の両方のパラメーターを使用すると、このコマンドレットは、すべてのモジュールのファイルバージョンに関する情報を含む **FileVersionInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-201">When you use both the *Module* and **FileVersionInfo** parameters in the same command, this cmdlet returns a **FileVersionInfo** object with information about the file version of all modules.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4edf-202">-Name</span><span class="sxs-lookup"><span data-stu-id="d4edf-202">-Name</span></span>

<span data-ttu-id="d4edf-203">プロセス名を使用してプロセスを 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-203">Specifies one or more processes by process name.</span></span> <span data-ttu-id="d4edf-204">複数のプロセス名をコンマで区切って指定することも、ワイルドカード文字を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-204">You can type multiple process names (separated by commas) and use wildcard characters.</span></span> <span data-ttu-id="d4edf-205">パラメーター名 ("Name") は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d4edf-205">The parameter name ("Name") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, NameWithUserName
Aliases: ProcessName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="d4edf-206">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d4edf-206">CommonParameters</span></span>

<span data-ttu-id="d4edf-207">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d4edf-207">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d4edf-208">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4edf-208">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d4edf-209">入力</span><span class="sxs-lookup"><span data-stu-id="d4edf-209">INPUTS</span></span>

### <span data-ttu-id="d4edf-210">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="d4edf-210">System.Diagnostics.Process</span></span>

<span data-ttu-id="d4edf-211">パイプを使用してプロセスオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-211">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="d4edf-212">出力</span><span class="sxs-lookup"><span data-stu-id="d4edf-212">OUTPUTS</span></span>

### <span data-ttu-id="d4edf-213">FileVersionInfo、system.string、および System. Diagnostics... ProcessModule</span><span class="sxs-lookup"><span data-stu-id="d4edf-213">System.Diagnostics.Process, System.Diagnostics.FileVersionInfo, System.Diagnostics.ProcessModule</span></span>

<span data-ttu-id="d4edf-214">既定では、このコマンドレット **は、system.string オブジェクトを** 返します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-214">By default, this cmdlet returns a **System.Diagnostics.Process** object.</span></span> <span data-ttu-id="d4edf-215">**FileVersionInfo** パラメーターを使用すると、 **FileVersionInfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-215">If you use the **FileVersionInfo** parameter, it returns a **System.Diagnostics.FileVersionInfo** object.</span></span> <span data-ttu-id="d4edf-216">**Module** パラメーターを使用する場合、 **FileVersionInfo** パラメーターを指定しないと、 **system.string オブジェクトが** 返されます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-216">If you use the **Module** parameter, without the **FileVersionInfo** parameter, it returns a **System.Diagnostics.ProcessModule** object.</span></span>

## <span data-ttu-id="d4edf-217">注</span><span class="sxs-lookup"><span data-stu-id="d4edf-217">NOTES</span></span>

- <span data-ttu-id="d4edf-218">このコマンドレットは、組み込みのエイリアスである ps と gps を使用して参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-218">You can also refer to this cmdlet by its built-in aliases, ps and gps.</span></span> <span data-ttu-id="d4edf-219">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4edf-219">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="d4edf-220">64ビットバージョンの Windows を実行しているコンピューターでは、64ビットバージョンの PowerShell は64ビットプロセスモジュールだけを取得し、PowerShell の32ビットバージョンは、32ビットプロセスモジュールのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4edf-220">On computers that are running a 64-bit version of Windows, the 64-bit version of PowerShell gets only 64-bit process modules and the 32-bit version of PowerShell gets only 32-bit process modules.</span></span>
- <span data-ttu-id="d4edf-221">PowerShell では、Windows Management Instrumentation (WMI) Win32_Process オブジェクトのプロパティとメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-221">You can use the properties and methods of the Windows Management Instrumentation (WMI) Win32_Process object in PowerShell.</span></span> <span data-ttu-id="d4edf-222">詳細については、「」および「WMI SDK」を参照してください `Get-WmiObject` 。</span><span class="sxs-lookup"><span data-stu-id="d4edf-222">For information, see `Get-WmiObject` and the WMI SDK.</span></span>
- <span data-ttu-id="d4edf-223">既定では、次の欄を含む表としてプロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-223">The default display of a process is a table that includes the following columns.</span></span> <span data-ttu-id="d4edf-224">プロセスオブジェクトのすべてのプロパティの詳細については、「 [Process properties](/dotnet/api/system.diagnostics.process)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4edf-224">For a description of all of the properties of process objects, see [Process Properties](/dotnet/api/system.diagnostics.process).</span></span>
  - <span data-ttu-id="d4edf-225">ハンドル: プロセスが開いたハンドルの数。</span><span class="sxs-lookup"><span data-stu-id="d4edf-225">Handles: The number of handles that the process has opened.</span></span>
  - <span data-ttu-id="d4edf-226">NPM (K): プロセスが使用している非ページメモリの量 (kb 単位)。</span><span class="sxs-lookup"><span data-stu-id="d4edf-226">NPM(K): The amount of non-paged memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="d4edf-227">PM (K): プロセスが使用しているページング可能なメモリの量 (kb 単位)。</span><span class="sxs-lookup"><span data-stu-id="d4edf-227">PM(K): The amount of pageable memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="d4edf-228">WS (K): プロセスのワーキングセットのサイズ (kb 単位)。</span><span class="sxs-lookup"><span data-stu-id="d4edf-228">WS(K): The size of the working set of the process, in kilobytes.</span></span>
    <span data-ttu-id="d4edf-229">ワーキング セットは、プロセスが最近参照したメモリのページで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-229">The working set consists of the pages of memory that were recently referenced by the process.</span></span>
  - <span data-ttu-id="d4edf-230">VM (M): プロセスが使用している仮想メモリの量 (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d4edf-230">VM(M): The amount of virtual memory that the process is using, in megabytes.</span></span>
    <span data-ttu-id="d4edf-231">仮想メモリには、ディスク上のページング ファイルの記憶域が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-231">Virtual memory includes storage in the paging files on disk.</span></span>
  - <span data-ttu-id="d4edf-232">CPU (s): プロセスがすべてのプロセッサで使用したプロセッサ時間の合計 (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="d4edf-232">CPU(s): The amount of processor time that the process has used on all processors, in seconds.</span></span>
  - <span data-ttu-id="d4edf-233">ID: プロセスのプロセス ID (PID)。</span><span class="sxs-lookup"><span data-stu-id="d4edf-233">ID: The process ID (PID) of the process.</span></span>
  - <span data-ttu-id="d4edf-234">ProcessName: プロセスの名前。</span><span class="sxs-lookup"><span data-stu-id="d4edf-234">ProcessName: The name of the process.</span></span> <span data-ttu-id="d4edf-235">プロセスに関連する概念の説明については、ヘルプとサポート センターにある用語集と、タスク マネージャーのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4edf-235">For explanations of the concepts related to processes, see the Glossary in Help and Support Center and the Help for Task Manager.</span></span>
- <span data-ttu-id="d4edf-236">また `Format-Table` 、 **StartTime** や **Priority** など、で使用できるプロセスの組み込みの代替ビューを使用したり、独自のビューを設計したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d4edf-236">You can also use the built-in alternate views of the processes available with `Format-Table`, such as **StartTime** and **Priority** , and you can design your own views.</span></span>

## <span data-ttu-id="d4edf-237">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d4edf-237">RELATED LINKS</span></span>

[<span data-ttu-id="d4edf-238">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="d4edf-238">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="d4edf-239">Get-Process</span><span class="sxs-lookup"><span data-stu-id="d4edf-239">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="d4edf-240">Start-Process</span><span class="sxs-lookup"><span data-stu-id="d4edf-240">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="d4edf-241">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="d4edf-241">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="d4edf-242">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="d4edf-242">Wait-Process</span></span>](Wait-Process.md)
