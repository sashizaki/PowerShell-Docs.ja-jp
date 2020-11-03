---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-table?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Table
ms.openlocfilehash: 1a90bfada7a21da24cd41ae2ceb8920f13c17c5d
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219464"
---
# <span data-ttu-id="b3047-103">Format-Table</span><span class="sxs-lookup"><span data-stu-id="b3047-103">Format-Table</span></span>

## <span data-ttu-id="b3047-104">概要</span><span class="sxs-lookup"><span data-stu-id="b3047-104">SYNOPSIS</span></span>
<span data-ttu-id="b3047-105">出力を表として書式設定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-105">Formats the output as a table.</span></span>

## <span data-ttu-id="b3047-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3047-106">SYNTAX</span></span>

### <span data-ttu-id="b3047-107">All</span><span class="sxs-lookup"><span data-stu-id="b3047-107">All</span></span>

```
Format-Table [-AutoSize] [-RepeatHeader] [-HideTableHeaders] [-Wrap] [[-Property] <Object[]>]
 [-GroupBy <Object>] [-View <String>] [-ShowError] [-DisplayError] [-Force] [-Expand <String>]
 [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="b3047-108">Description</span><span class="sxs-lookup"><span data-stu-id="b3047-108">DESCRIPTION</span></span>

<span data-ttu-id="b3047-109">`Format-Table`コマンドレットは、各列のオブジェクトの選択されたプロパティを使用して、コマンドの出力をテーブルとして書式設定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-109">The `Format-Table` cmdlet formats the output of a command as a table with the selected properties of the object in each column.</span></span> <span data-ttu-id="b3047-110">各列に表示される既定のレイアウトとプロパティは、オブジェクトの種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="b3047-110">The object type determines the default layout and properties that are displayed in each column.</span></span> <span data-ttu-id="b3047-111">**プロパティ** パラメーターを使用して、表示するプロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-111">You can use the **Property** parameter to select the properties that you want to display.</span></span>

<span data-ttu-id="b3047-112">PowerShell では、既定のフォーマッタを使用して、オブジェクトの種類の表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="b3047-112">PowerShell uses default formatters to define how object types are displayed.</span></span> <span data-ttu-id="b3047-113">ファイルを使用すると、 `.ps1xml` 指定したプロパティを持つ出力テーブルを表示するカスタムビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-113">You can use `.ps1xml` files to create custom views that display an output table with specified properties.</span></span> <span data-ttu-id="b3047-114">カスタムビューを作成した後、 **view** パラメーターを使用して、カスタムビューでテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-114">After a custom view is created, use the **View** parameter to display the table with your custom view.</span></span> <span data-ttu-id="b3047-115">ビューの詳細については、「 [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3047-115">For more information about views, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="b3047-116">ハッシュテーブルを使用して、計算されたプロパティを表示する前にオブジェクトに追加したり、テーブルの列見出しを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b3047-116">You can use a hash table to add calculated properties to an object before displaying it and to specify the column headings in the table.</span></span> <span data-ttu-id="b3047-117">計算されたプロパティを追加するには、 **property** パラメーターまたは **GroupBy** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3047-117">To add a calculated property, use the **Property** or **GroupBy** parameter.</span></span> <span data-ttu-id="b3047-118">ハッシュ テーブルの詳細については、「[about_Hash_Tables (ハッシュ テーブルについて)](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b3047-118">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

## <span data-ttu-id="b3047-119">例</span><span class="sxs-lookup"><span data-stu-id="b3047-119">EXAMPLES</span></span>

### <span data-ttu-id="b3047-120">例 1: PowerShell ホストの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="b3047-120">Example 1: Format PowerShell host</span></span>

<span data-ttu-id="b3047-121">この例では、PowerShell のホストプログラムに関する情報をテーブルに表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-121">This example displays information about the host program for PowerShell in a table.</span></span>

```powershell
Get-Host | Format-Table -AutoSize
```

<span data-ttu-id="b3047-122">この `Get-Host` コマンドレットは、ホストを表す system.object **のホスト** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3047-122">The `Get-Host` cmdlet gets **System.Management.Automation.Internal.Host.InternalHost** objects that represent the host.</span></span> <span data-ttu-id="b3047-123">オブジェクトは、パイプラインの下方向に送信され、 `Format-Table` テーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-123">The objects are sent down the pipeline to `Format-Table` and displayed in a table.</span></span> <span data-ttu-id="b3047-124">**AutoSize** パラメーターを指定すると、列の幅が調整され、切り捨てが最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="b3047-124">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

### <span data-ttu-id="b3047-125">例 2: BasePriority でプロセスをフォーマットする</span><span class="sxs-lookup"><span data-stu-id="b3047-125">Example 2: Format processes by BasePriority</span></span>

<span data-ttu-id="b3047-126">この例では、同じ **Basepriority** プロパティを持つグループにプロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-126">In this example, processes are displayed in groups that have the same **BasePriority** property.</span></span>

```powershell
Get-Process | Sort-Object -Property BasePriority | Format-Table -GroupBy BasePriority -Wrap
```

<span data-ttu-id="b3047-127">`Get-Process`コマンドレットは、コンピューター上の各プロセスを表すオブジェクトを取得し、それをパイプラインの下に送信し `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="b3047-127">The `Get-Process` cmdlet gets objects that represent each process on the computer and sends them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="b3047-128">オブジェクトは、 **Basepriority** プロパティの順序で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="b3047-128">The objects are sorted in the order of their **BasePriority** property.</span></span>

<span data-ttu-id="b3047-129">並べ替えられたオブジェクトは、パイプラインでに送信され `Format-Table` ます。</span><span class="sxs-lookup"><span data-stu-id="b3047-129">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="b3047-130">**GroupBy** パラメーターは、 **basepriority** プロパティの値に基づいてプロセスデータをグループに配置します。</span><span class="sxs-lookup"><span data-stu-id="b3047-130">The **GroupBy** parameter arranges the process data into groups based on their **BasePriority** property's value.</span></span> <span data-ttu-id="b3047-131">**Wrap** パラメーターを指定すると、データが切り捨てられなくなります。</span><span class="sxs-lookup"><span data-stu-id="b3047-131">The **Wrap** parameter ensures that data isn't truncated.</span></span>

### <span data-ttu-id="b3047-132">例 3: 開始日によるプロセスのフォーマット</span><span class="sxs-lookup"><span data-stu-id="b3047-132">Example 3: Format processes by start date</span></span>

<span data-ttu-id="b3047-133">この例では、コンピューター上で実行されているプロセスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-133">This example displays information about the processes running on the computer.</span></span> <span data-ttu-id="b3047-134">オブジェクトが並べ替えられ、 `Format-Table` ビューを使用してオブジェクトが開始日でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-134">The objects are sorted and `Format-Table` uses a view to group the objects by their start date.</span></span>

```powershell
Get-Process | Sort-Object StartTime | Format-Table -View StartTime
```

<span data-ttu-id="b3047-135">`Get-Process` コンピューター上で実行されているプロセスを表す **system.object オブジェクトを** 取得します。</span><span class="sxs-lookup"><span data-stu-id="b3047-135">`Get-Process` gets the **System.Diagnostics.Process** objects that represent the processes running on the computer.</span></span> <span data-ttu-id="b3047-136">オブジェクトは、パイプライン内でに送信され `Sort-Object` 、 **StartTime** プロパティに基づいて並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="b3047-136">The objects are sent down the pipeline to `Sort-Object`, and are sorted based on the **StartTime** property.</span></span>

<span data-ttu-id="b3047-137">並べ替えられたオブジェクトは、パイプラインでに送信され `Format-Table` ます。</span><span class="sxs-lookup"><span data-stu-id="b3047-137">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="b3047-138">**View** パラメーターは、PowerShell ファイルで定義されている、system.string オブジェクトの **StartTime** ビューを指定します。 `DotNetTypes.format.ps1xml` **System.Diagnostics.Process**</span><span class="sxs-lookup"><span data-stu-id="b3047-138">The **View** parameter specifies the **StartTime** view that's defined in the PowerShell `DotNetTypes.format.ps1xml` file for **System.Diagnostics.Process** objects.</span></span> <span data-ttu-id="b3047-139">**StartTime** ビューでは、各プロセスの開始時刻が短い日付に変換され、開始日によってプロセスがグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-139">The **StartTime** view converts each processes start time to a short date and then groups the processes by the start date.</span></span>

<span data-ttu-id="b3047-140">ファイルには、 `DotNetTypes.format.ps1xml` プロセスの **優先度** ビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3047-140">The `DotNetTypes.format.ps1xml` file contains a **Priority** view for processes.</span></span> <span data-ttu-id="b3047-141">カスタマイズしたビューを使用して、独自のファイルを作成でき `format.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="b3047-141">You can create your own `format.ps1xml` files with customized views.</span></span>

### <span data-ttu-id="b3047-142">例 4: テーブル出力にカスタムビューを使用する</span><span class="sxs-lookup"><span data-stu-id="b3047-142">Example 4: Use a custom view for table output</span></span>

<span data-ttu-id="b3047-143">この例では、カスタムビューにディレクトリの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-143">In this example, a custom view displays a directory's contents.</span></span> <span data-ttu-id="b3047-144">カスタムビューでは、 **DirectoryInfo** およびによって作成された system.object オブジェクトのテーブル出力に **、[作成\*\*\*\*時刻** ] 列が追加されます `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="b3047-144">The custom view adds the **CreationTime** column to the table output for **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span>

<span data-ttu-id="b3047-145">この例のカスタムビューは、PowerShell ソースコードで定義されているビューから作成されています。</span><span class="sxs-lookup"><span data-stu-id="b3047-145">The custom view in this example was created from the view defined in PowerShell source code.</span></span> <span data-ttu-id="b3047-146">ビューおよびこの例のビューを作成するために使用されるコードの詳細については、「 [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3047-146">For more information about views and the code used to create this example's view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).</span></span>

```powershell
Get-ChildItem  -Path C:\Test | Format-Table -View mygciview
```

```Output
    Directory: C:\Test

Mode                LastWriteTime              CreationTime         Length Name
----                -------------              ------------         ------ ----
d-----        11/4/2019     15:54       9/24/2019     15:54                Archives
d-----        8/27/2019     14:22       8/27/2019     14:22                Drawings
d-----       10/23/2019     09:38       2/25/2019     09:38                Files
-a----        11/7/2019     11:07       11/7/2019     11:07          11345 Alias.txt
-a----        2/27/2019     15:15       2/27/2019     15:15            258 alias_out.txt
-a----        2/27/2019     15:16       2/27/2019     15:16            258 alias_out2.txt
```

<span data-ttu-id="b3047-147">`Get-ChildItem` 現在のディレクトリの内容を取得し `C:\Test` ます。</span><span class="sxs-lookup"><span data-stu-id="b3047-147">`Get-ChildItem` gets the contents of the current directory, `C:\Test`.</span></span> <span data-ttu-id="b3047-148">**DirectoryInfo** オブジェクトと system.object オブジェクトは、パイプラインを **介して送信** されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-148">The **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects are sent down the pipeline.</span></span>
<span data-ttu-id="b3047-149">`Format-Table`**View** パラメーターを使用して、"作成 **後の時間** " 列を含むカスタムビュー **mygciview** を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-149">`Format-Table` uses the **View** parameter to specify the custom view **mygciview** that includes the **CreationTime** column.</span></span>

<span data-ttu-id="b3047-150">の既定の出力には、"設定 `Format-Table` `Get-ChildItem` 後の **時間** " 列は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b3047-150">The default `Format-Table` output for `Get-ChildItem` doesn't include the **CreationTime** column.</span></span>

### <span data-ttu-id="b3047-151">例 5: テーブルの出力にプロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="b3047-151">Example 5: Use properties for table output</span></span>

<span data-ttu-id="b3047-152">この例では、 **Property** パラメーターを使用して、プロパティ **名** と **dependentservices** を示す2列のテーブルにすべてのコンピューターのサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-152">This example uses the **Property** parameter to display all the computer's services in a two-column table that shows the properties **Name** and **DependentServices**.</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="b3047-153">`Get-Service` コンピューター上のすべてのサービスを取得し、 **ServiceController** オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="b3047-153">`Get-Service` gets all the services on the computer and sends the **System.ServiceProcess.ServiceController** objects down the pipeline.</span></span> <span data-ttu-id="b3047-154">`Format-Table`**Property** パラメーターを使用して、 **Name** プロパティと **dependentservices** プロパティをテーブルに表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-154">`Format-Table` uses the **Property** parameter to specify that the **Name** and **DependentServices** properties are displayed in the table.</span></span>

<span data-ttu-id="b3047-155">**Name** と **dependentservices** は、オブジェクト型のプロパティのうちの2つです。</span><span class="sxs-lookup"><span data-stu-id="b3047-155">**Name** and **DependentServices** are two of the object type's properties.</span></span> <span data-ttu-id="b3047-156">すべてのプロパティを表示するには、「」を参照して `Get-Service | Get-Member -MemberType Properties` ください。</span><span class="sxs-lookup"><span data-stu-id="b3047-156">To view all the properties: `Get-Service | Get-Member -MemberType Properties`.</span></span>

### <span data-ttu-id="b3047-157">例 6: プロセスをフォーマットし、その実行時間を計算する</span><span class="sxs-lookup"><span data-stu-id="b3047-157">Example 6: Format a process and calculate its running time</span></span>

<span data-ttu-id="b3047-158">この例では、ローカルコンピューターの **メモ帳** プロセスのプロセス名と合計実行時間を含むテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-158">This example displays a table with the process name and total running time for the local computer's **notepad** processes.</span></span> <span data-ttu-id="b3047-159">合計実行時間は、現在の時刻から各プロセスの開始時刻を差し引いて求めます。</span><span class="sxs-lookup"><span data-stu-id="b3047-159">The total running time is calculated by subtracting the start time of each process from the current time.</span></span>

```powershell
Get-Process notepad |
  Format-Table ProcessName, @{Label="TotalRunningTime"; Expression={(Get-Date) - $_.StartTime}}
```

```Output
ProcessName TotalRunningTime
----------- ----------------
notepad     03:20:00.2751767
notepad     00:00:16.7710520
```

<span data-ttu-id="b3047-160">`Get-Process` ローカルコンピューターの **メモ帳** のすべてのプロセスを取得し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="b3047-160">`Get-Process` gets all the local computer's **notepad** processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="b3047-161">`Format-Table`**ProcessName** 、プロパティ、および Totalrunningtime という2つの列を含むテーブルを表示し `Get-Process` ます。集計プロパティです。 **TotalRunningTime**</span><span class="sxs-lookup"><span data-stu-id="b3047-161">`Format-Table` displays a table with two columns: **ProcessName** , a `Get-Process` property, and **TotalRunningTime** , a calculated property.</span></span>

<span data-ttu-id="b3047-162">**Totalrunningtime** プロパティは、 **ラベル** と **式** の2つのキーを持つハッシュテーブルによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-162">The **TotalRunningTime** property is specified by a hash table with two keys, **Label** and **Expression**.</span></span> <span data-ttu-id="b3047-163">**Label** キーは、プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-163">The **Label** key specifies the property name.</span></span> <span data-ttu-id="b3047-164">**式** キーは計算を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-164">The **Expression** key specifies the calculation.</span></span> <span data-ttu-id="b3047-165">この式は、各プロセスオブジェクトの **StartTime** プロパティを取得し、 `Get-Date` 現在の日付と時刻を取得するコマンドの結果から減算します。</span><span class="sxs-lookup"><span data-stu-id="b3047-165">The expression gets the **StartTime** property of each process object and subtracts it from the result of a `Get-Date` command, which gets the current date and time.</span></span>

### <span data-ttu-id="b3047-166">例 7: メモ帳のプロセスをフォーマットする</span><span class="sxs-lookup"><span data-stu-id="b3047-166">Example 7: Format Notepad processes</span></span>

<span data-ttu-id="b3047-167">この例では `Get-CimInstance` 、を使用して、ローカルコンピューター上のすべての **メモ帳** プロセスの実行時間を取得します。</span><span class="sxs-lookup"><span data-stu-id="b3047-167">This example uses `Get-CimInstance` to get the running time for all **notepad** processes on the local computer.</span></span> <span data-ttu-id="b3047-168">を `Get-CimInstance` **ComputerName** パラメーターと共に使用すると、リモートコンピューターから情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-168">You can use `Get-CimInstance` with the **ComputerName** parameter to get information from remote computers.</span></span>

```powershell
$Processes = Get-CimInstance -Class win32_process -Filter "name='notepad.exe'"
$Processes | Format-Table ProcessName, @{ Label = "Total Running Time"; Expression={(Get-Date) - $_.CreationDate}}
```

```Output
ProcessName Total Running Time
----------- ------------------
notepad.exe 03:39:39.6260693
notepad.exe 00:19:56.1376922
```

<span data-ttu-id="b3047-169">`Get-CimInstance`**notepad.exe** という名前のすべてのローカルコンピューターのプロセスを記述する WMI **Win32_Process** クラスのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3047-169">`Get-CimInstance` gets instances of the WMI **Win32_Process** class that describes all the local computer's processes named **notepad.exe**.</span></span> <span data-ttu-id="b3047-170">プロセスオブジェクトは変数に格納され `$Processes` ます。</span><span class="sxs-lookup"><span data-stu-id="b3047-170">The process objects are stored in the `$Processes` variable.</span></span>

<span data-ttu-id="b3047-171">変数内のプロセスオブジェクト `$Processes` は、パイプラインの下に送信されます。このオブジェクトには `Format-Table` 、 **ProcessName** プロパティと新しい計算されるプロパティ ( **合計実行時間** ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-171">The process objects in the `$Processes` variable are sent down the pipeline to `Format-Table`, which displays the **ProcessName** property and a new calculated property, **Total Running Time**.</span></span>

<span data-ttu-id="b3047-172">このコマンドは、新しい計算されるプロパティの名前 ( **合計実行時間** ) を **ラベル** キーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b3047-172">The command assigns the name of the new calculated property, **Total Running Time** , to the **Label** key.</span></span> <span data-ttu-id="b3047-173">**式** キーのスクリプトブロックは、現在の日付からプロセスの作成日を差し引くことによって、プロセスが実行されている時間を計算します。</span><span class="sxs-lookup"><span data-stu-id="b3047-173">The **Expression** key's script block calculates how long the process has been running by subtracting the processes creation date from the current date.</span></span> <span data-ttu-id="b3047-174">`Get-Date`コマンドレットは、現在の日付を取得します。</span><span class="sxs-lookup"><span data-stu-id="b3047-174">The `Get-Date` cmdlet gets the current date.</span></span> <span data-ttu-id="b3047-175">作成日は現在の日付から差し引かれます。</span><span class="sxs-lookup"><span data-stu-id="b3047-175">The creation date is subtracted from the current date.</span></span> <span data-ttu-id="b3047-176">結果は、 **合計実行時間** の値になります。</span><span class="sxs-lookup"><span data-stu-id="b3047-176">The result is the value of **Total Running Time**.</span></span>

### <span data-ttu-id="b3047-177">例 8: 形式エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b3047-177">Example 8: Troubleshooting format errors</span></span>

<span data-ttu-id="b3047-178">次の例は、 **displayerror** パラメーターまたは **showerror** パラメーターを式と共に追加した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3047-178">The following examples show the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -DisplayError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday #ERR
```

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -ShowError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday

InvalidArgument: Failed to evaluate expression " $_ / $null ".
```

## <span data-ttu-id="b3047-179">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3047-179">PARAMETERS</span></span>

### <span data-ttu-id="b3047-180">-AutoSize</span><span class="sxs-lookup"><span data-stu-id="b3047-180">-AutoSize</span></span>

<span data-ttu-id="b3047-181">コマンドレットによって、データの幅に基づいて列のサイズと列数が調整されることを示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-181">Indicates that the cmdlet adjusts the column size and number of columns based on the width of the data.</span></span> <span data-ttu-id="b3047-182">既定では、列のサイズと数は、ビューによって決まります。</span><span class="sxs-lookup"><span data-stu-id="b3047-182">By default, the column size and number are determined by the view.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3047-183">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="b3047-183">-DisplayError</span></span>

<span data-ttu-id="b3047-184">コマンドレットによってコマンドラインにエラーが表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-184">Indicates that the cmdlet displays errors on the command line.</span></span> <span data-ttu-id="b3047-185">このパラメーターは、コマンドで式を書式設定 `Format-Table` し、式のトラブルシューティングを行う必要がある場合に、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-185">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3047-186">-展開</span><span class="sxs-lookup"><span data-stu-id="b3047-186">-Expand</span></span>

<span data-ttu-id="b3047-187">コレクションオブジェクトの形式とコレクション内のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-187">Specifies the format of the collection object and the objects in the collection.</span></span> <span data-ttu-id="b3047-188">このパラメーターは、 [ICollection](/dotnet/api/system.collections.icollection) (system.string) インターフェイスをサポートするオブジェクトを書式設定するように設計されてい[ます。](/dotnet/api/system.collections)</span><span class="sxs-lookup"><span data-stu-id="b3047-188">This parameter is designed to format objects that support the [ICollection](/dotnet/api/system.collections.icollection) ([System.Collections](/dotnet/api/system.collections)) interface.</span></span> <span data-ttu-id="b3047-189">既定値は **Enumonly** です。</span><span class="sxs-lookup"><span data-stu-id="b3047-189">The default value is **EnumOnly**.</span></span>
<span data-ttu-id="b3047-190">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3047-190">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b3047-191">**Enumonly** : コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-191">**EnumOnly** : Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="b3047-192">**Coreonly** : コレクションオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-192">**CoreOnly** : Displays the properties of the collection object.</span></span>
- <span data-ttu-id="b3047-193">**Both** : コレクションオブジェクトのプロパティと、コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-193">**Both** : Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3047-194">-Force</span><span class="sxs-lookup"><span data-stu-id="b3047-194">-Force</span></span>

<span data-ttu-id="b3047-195">コマンドレットがすべてのエラー情報を表示するようにコマンドレットに指示することを示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-195">Indicates that the cmdlet directs the cmdlet to display all the error information.</span></span> <span data-ttu-id="b3047-196">**Displayerror** パラメーターまたは **showerror** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="b3047-196">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="b3047-197">既定では、エラー オブジェクトがエラーまたは表示ストリームに書き込まれるとき、エラー情報の一部のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-197">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3047-198">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="b3047-198">-GroupBy</span></span>

<span data-ttu-id="b3047-199">プロパティ値に基づいて個別のテーブルに並べ替えられた出力を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-199">Specifies sorted output in separate tables based on a property value.</span></span> <span data-ttu-id="b3047-200">たとえば、 **GroupBy** を使用して、サービスの状態に基づいて別のテーブルのサービスを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-200">For example, you can use **GroupBy** to list services in separate tables based on their status.</span></span>

<span data-ttu-id="b3047-201">式またはプロパティを入力してください。</span><span class="sxs-lookup"><span data-stu-id="b3047-201">Enter an expression or a property.</span></span> <span data-ttu-id="b3047-202">**GroupBy** パラメーターは、オブジェクトが並べ替えられることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="b3047-202">The **GroupBy** parameter expects that the objects are sorted.</span></span>
<span data-ttu-id="b3047-203">を使用し `Sort-Object` て `Format-Table` オブジェクトをグループ化する前に、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3047-203">Use the `Sort-Object` cmdlet before using `Format-Table` to group the objects.</span></span>

<span data-ttu-id="b3047-204">**GroupBy** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-204">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="b3047-205">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-205">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="b3047-206">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3047-206">Valid key-value pairs are:</span></span>

- <span data-ttu-id="b3047-207">名前 (またはラベル)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="b3047-207">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="b3047-208">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="b3047-208">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="b3047-209">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="b3047-209">FormatString - `<string>`</span></span>

<span data-ttu-id="b3047-210">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3047-210">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3047-211">-HideTableHeaders</span><span class="sxs-lookup"><span data-stu-id="b3047-211">-HideTableHeaders</span></span>

<span data-ttu-id="b3047-212">表から列見出しを削除します。</span><span class="sxs-lookup"><span data-stu-id="b3047-212">Omits the column headings from the table.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3047-213">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b3047-213">-InputObject</span></span>

<span data-ttu-id="b3047-214">書式設定するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-214">Specifies the objects to format.</span></span> <span data-ttu-id="b3047-215">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="b3047-215">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="b3047-216">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="b3047-216">-Property</span></span>

<span data-ttu-id="b3047-217">表示するオブジェクト プロパティと、その表示順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3047-217">Specifies the object properties that appear in the display and the order in which they appear.</span></span> <span data-ttu-id="b3047-218">1つまたは複数のプロパティ名をコンマで区切って入力するか、ハッシュテーブルを使用して計算されたプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-218">Type one or more property names, separated by commas, or use a hash table to display a calculated property.</span></span> <span data-ttu-id="b3047-219">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-219">Wildcards are permitted.</span></span>

<span data-ttu-id="b3047-220">このパラメーターを省略した場合、表示に表示されるプロパティは、最初のオブジェクトのプロパティによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b3047-220">If you omit this parameter, the properties that appear in the display depend on the first object's properties.</span></span> <span data-ttu-id="b3047-221">たとえば、最初のオブジェクトが **propertya** と **propertya** を持ち、後続のオブジェクトが **propertya** 、 **propertya** 、および **Propertya** を持つ場合、 **propertya** と **propertya** のヘッダーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3047-221">For example, if the first object has **PropertyA** and **PropertyB** but subsequent objects have **PropertyA** , **PropertyB** , and **PropertyC** , then only the **PropertyA** and **PropertyB** headers will display.</span></span>

<span data-ttu-id="b3047-222">**Property** パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b3047-222">The **Property** parameter is optional.</span></span> <span data-ttu-id="b3047-223">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b3047-223">You can't use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="b3047-224">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-224">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="b3047-225">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-225">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="b3047-226">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3047-226">Valid key-value pairs are:</span></span>

- <span data-ttu-id="b3047-227">名前 (またはラベル) `<string>`</span><span class="sxs-lookup"><span data-stu-id="b3047-227">Name (or Label) `<string>`</span></span>
- <span data-ttu-id="b3047-228">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="b3047-228">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="b3047-229">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="b3047-229">FormatString - `<string>`</span></span>
- <span data-ttu-id="b3047-230">幅- `<int32>` -より大きい必要があります `0`</span><span class="sxs-lookup"><span data-stu-id="b3047-230">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="b3047-231">Alignment-値には `Left` 、、 `Center` 、またはを指定できます。 `Right`</span><span class="sxs-lookup"><span data-stu-id="b3047-231">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="b3047-232">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3047-232">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b3047-233">-RepeatHeader</span><span class="sxs-lookup"><span data-stu-id="b3047-233">-RepeatHeader</span></span>

<span data-ttu-id="b3047-234">すべての画面がいっぱいになった後にテーブルのヘッダーを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-234">Repeats displaying the header of a table after every screen full.</span></span> <span data-ttu-id="b3047-235">繰り返しヘッダーは、出力が、、 `less` また `more` はスクリーンリーダーとのページングなどのページャーにパイプ処理される場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="b3047-235">The repeated header is useful when the output is piped to a pager such as `less` or `more` or paging with a screen reader.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3047-236">-ShowError</span><span class="sxs-lookup"><span data-stu-id="b3047-236">-ShowError</span></span>

<span data-ttu-id="b3047-237">このパラメーターは、パイプラインを介してエラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="b3047-237">This parameter sends errors through the pipeline.</span></span> <span data-ttu-id="b3047-238">このパラメーターは、コマンドで式を書式設定 `Format-Table` し、式のトラブルシューティングを行う必要がある場合に、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-238">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3047-239">-ビュー</span><span class="sxs-lookup"><span data-stu-id="b3047-239">-View</span></span>

<span data-ttu-id="b3047-240">PowerShell 6 以降では、既定のビューが PowerShell ソースコードで定義されてい `C#` ます。</span><span class="sxs-lookup"><span data-stu-id="b3047-240">Beginning in PowerShell 6, the default views are defined in PowerShell `C#` source code.</span></span> <span data-ttu-id="b3047-241">Powershell `*.format.ps1xml` 5.1 以前のバージョンのファイルは、powershell 6 以降のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="b3047-241">The `*.format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later versions.</span></span>

<span data-ttu-id="b3047-242">**View** パラメーターを使用すると、テーブルの代替形式またはカスタムビューを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3047-242">The **View** parameter lets you specify an alternate format or custom view for the table.</span></span> <span data-ttu-id="b3047-243">既定の PowerShell ビューを使用することも、カスタムビューを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3047-243">You can use the default PowerShell views or create custom views.</span></span> <span data-ttu-id="b3047-244">カスタムビューを作成する方法の詳細については、「 [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3047-244">For more information about how to create a custom view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="b3047-245">**View** パラメーターの代替ビューおよびカスタムビューでは、テーブル形式を使用する必要があります。そうしないと、は `Format-Table` 失敗します。</span><span class="sxs-lookup"><span data-stu-id="b3047-245">The alternate and custom views for the **View** parameter must use the table format, otherwise, `Format-Table` fails.</span></span> <span data-ttu-id="b3047-246">代替ビューが一覧の場合は、コマンドレットを使用し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="b3047-246">If the alternate view is a list, use the `Format-List` cmdlet.</span></span> <span data-ttu-id="b3047-247">代替ビューがリストまたはテーブルではない場合は、 `Format-Custom` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3047-247">If the alternate view isn't a list or a table, use the `Format-Custom` cmdlet.</span></span>

<span data-ttu-id="b3047-248">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b3047-248">You can't use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="b3047-249">-Wrap</span><span class="sxs-lookup"><span data-stu-id="b3047-249">-Wrap</span></span>

<span data-ttu-id="b3047-250">列幅を超えるテキストを次の行に表示します。</span><span class="sxs-lookup"><span data-stu-id="b3047-250">Displays text that exceeds the column width on the next line.</span></span> <span data-ttu-id="b3047-251">既定では、列幅を超えるテキストは切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="b3047-251">By default, text that exceeds the column width is truncated.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3047-252">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3047-252">CommonParameters</span></span>

<span data-ttu-id="b3047-253">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b3047-253">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3047-254">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3047-254">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b3047-255">入力</span><span class="sxs-lookup"><span data-stu-id="b3047-255">INPUTS</span></span>

### <span data-ttu-id="b3047-256">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="b3047-256">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b3047-257">パイプライン内の任意のオブジェクトをに送信でき `Format-Table` ます。</span><span class="sxs-lookup"><span data-stu-id="b3047-257">You can send any object down the pipeline to `Format-Table`.</span></span>

## <span data-ttu-id="b3047-258">出力</span><span class="sxs-lookup"><span data-stu-id="b3047-258">OUTPUTS</span></span>

### <span data-ttu-id="b3047-259">Microsoft. PowerShell. 内部形式</span><span class="sxs-lookup"><span data-stu-id="b3047-259">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="b3047-260">`Format-Table` テーブルを表す書式オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b3047-260">`Format-Table` returns format objects that represent the table.</span></span>

## <span data-ttu-id="b3047-261">注</span><span class="sxs-lookup"><span data-stu-id="b3047-261">NOTES</span></span>

## <span data-ttu-id="b3047-262">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b3047-262">RELATED LINKS</span></span>

[<span data-ttu-id="b3047-263">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="b3047-263">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="b3047-264">about_Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="b3047-264">about_Format.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="b3047-265">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="b3047-265">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="b3047-266">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="b3047-266">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="b3047-267">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="b3047-267">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="b3047-268">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="b3047-268">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="b3047-269">Format-List</span><span class="sxs-lookup"><span data-stu-id="b3047-269">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="b3047-270">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="b3047-270">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="b3047-271">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="b3047-271">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="b3047-272">Get-Member</span><span class="sxs-lookup"><span data-stu-id="b3047-272">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="b3047-273">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b3047-273">Get-CimInstance</span></span>](../CimCmdlets/Get-CimInstance.md)

[<span data-ttu-id="b3047-274">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="b3047-274">Update-FormatData</span></span>](Update-FormatData.md)
