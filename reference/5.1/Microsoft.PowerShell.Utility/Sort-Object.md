---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: 1d27641f94d82b85bab694b392c0f09bb3265517
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219235"
---
# <span data-ttu-id="29067-103">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="29067-103">Sort-Object</span></span>

## <span data-ttu-id="29067-104">概要</span><span class="sxs-lookup"><span data-stu-id="29067-104">SYNOPSIS</span></span>
<span data-ttu-id="29067-105">プロパティ値別にオブジェクトを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-105">Sorts objects by property values.</span></span>

## <span data-ttu-id="29067-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29067-106">SYNTAX</span></span>

### <span data-ttu-id="29067-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="29067-107">Default (Default)</span></span>

```
Sort-Object [[-Property] <Object[]>] [-Descending] [-Unique] [-InputObject <psobject>]
 [-Culture <string>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="29067-108">Description</span><span class="sxs-lookup"><span data-stu-id="29067-108">DESCRIPTION</span></span>

<span data-ttu-id="29067-109">`Sort-Object`コマンドレットは、オブジェクトのプロパティ値に基づいて、オブジェクトを昇順または降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-109">The `Sort-Object` cmdlet sorts objects in ascending or descending order based on object property values.</span></span> <span data-ttu-id="29067-110">並べ替えプロパティがコマンドに含まれていない場合、PowerShell では、最初の入力オブジェクトの既定の並べ替えプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="29067-110">If sort properties are not included in a command, PowerShell uses default sort properties of the first input object.</span></span> <span data-ttu-id="29067-111">入力オブジェクトの型に既定の並べ替えプロパティがない場合、PowerShell はオブジェクト自体を比較しようとします。</span><span class="sxs-lookup"><span data-stu-id="29067-111">If the type of the input object has no default sort properties, PowerShell attempts to compare the objects themselves.</span></span> <span data-ttu-id="29067-112">詳細については、「 [メモ](#notes) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29067-112">For more information, see the [Notes](#notes) section.</span></span>

<span data-ttu-id="29067-113">オブジェクトは、1つのプロパティまたは複数のプロパティで並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="29067-113">You can sort objects by a single property or multiple properties.</span></span> <span data-ttu-id="29067-114">複数のプロパティでは、ハッシュテーブルを使用して、昇順、降順、または並べ替え順序の組み合わせを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="29067-114">Multiple properties use hash tables to sort in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="29067-115">プロパティは、大文字と小文字を区別するか、大文字と小文字を区別して並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-115">Properties are sorted as case-sensitive or case-insensitive.</span></span> <span data-ttu-id="29067-116">Output からの重複を排除するには、 **Unique** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="29067-116">Use the **Unique** parameter to eliminate duplicates from the output.</span></span>

## <span data-ttu-id="29067-117">例</span><span class="sxs-lookup"><span data-stu-id="29067-117">EXAMPLES</span></span>

### <span data-ttu-id="29067-118">例 1: 現在のディレクトリを名前で並べ替える</span><span class="sxs-lookup"><span data-stu-id="29067-118">Example 1: Sort the current directory by name</span></span>

<span data-ttu-id="29067-119">このコマンドは、ディレクトリ内のファイルとサブディレクトリを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-119">This command sorts the files and subdirectories in a directory.</span></span>

```
PS> Get-ChildItem -Path C:\Test | Sort-Object

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
d-----        2/25/2019     18:25                Files
d-----        2/25/2019     18:24                Logs
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
```

<span data-ttu-id="29067-120">この `Get-ChildItem` コマンドレットは、 **Path** パラメーター **C:\Test** によって指定されたディレクトリからファイルとサブディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="29067-120">The `Get-ChildItem` cmdlet gets the files and subdirectories from the directory specified by the **Path** parameter, **C:\Test**.</span></span> <span data-ttu-id="29067-121">オブジェクトは、パイプラインを介してコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-121">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="29067-122">`Sort-Object` はプロパティを指定しないので、既定の並べ替えプロパティの **Name** によって出力が並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-122">`Sort-Object` does not specify a property so the output is sorted by the default sort property, **Name**.</span></span>

### <span data-ttu-id="29067-123">例 2: ファイルの長さで現在のディレクトリを並べ替える</span><span class="sxs-lookup"><span data-stu-id="29067-123">Example 2: Sort the current directory by file length</span></span>

<span data-ttu-id="29067-124">このコマンドは、現在のディレクトリにあるファイルを長さの昇順で表示します。</span><span class="sxs-lookup"><span data-stu-id="29067-124">This command displays the files in the current directory by length in ascending order.</span></span>

```
PS> Get-ChildItem -Path C:\Test -File | Sort-Object -Property Length

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
-a----        2/13/2019     08:55             26 anotherfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-a----        2/12/2019     15:40         118014 Command.txt
```

<span data-ttu-id="29067-125">`Get-ChildItem`コマンドレットは、 **Path** パラメーターで指定されたディレクトリからファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="29067-125">The `Get-ChildItem` cmdlet gets the files from the directory specified by the **Path** parameter.</span></span>
<span data-ttu-id="29067-126">**File** パラメーターは、が `Get-ChildItem` ファイルオブジェクトのみを取得することを指定します。</span><span class="sxs-lookup"><span data-stu-id="29067-126">The **File** parameter specifies that `Get-ChildItem` only gets file objects.</span></span> <span data-ttu-id="29067-127">オブジェクトは、パイプラインを介してコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-127">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="29067-128">`Sort-Object`**length** パラメーターを使用して、ファイルを長さで昇順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-128">`Sort-Object` uses the **Length** parameter to sort the files by length in ascending order.</span></span>

### <span data-ttu-id="29067-129">例 3: メモリ使用量によってプロセスを並べ替える</span><span class="sxs-lookup"><span data-stu-id="29067-129">Example 3: Sort processes by memory usage</span></span>

<span data-ttu-id="29067-130">この例では、ワーキングセット (WS) のサイズに基づいてメモリ使用量が最も高いプロセスを表示します。</span><span class="sxs-lookup"><span data-stu-id="29067-130">This example displays processes with the highest memory usage based on their working set (WS) size.</span></span>

```
PS> Get-Process | Sort-Object -Property WS | Select-Object -Last 5

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    136   193.92     217.11     889.16   87492   8 OUTLOOK
    112   347.73     297.02      95.19  106908   8 Teams
    206   266.54     323.71      37.17   60620   8 MicrosoftEdgeCP
     35   552.19     549.94     131.66    6552   8 Code
      0     1.43     595.12       0.00    2780   0 Memory Compression
```

<span data-ttu-id="29067-131">この `Get-Process` コマンドレットは、コンピューター上で実行されているプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="29067-131">The `Get-Process` cmdlet gets the list of processes running on the computer.</span></span> <span data-ttu-id="29067-132">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-132">The process objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="29067-133">`Sort-Object`**Property** パラメーターを使用して、オブジェクトを **WS** で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-133">`Sort-Object` uses the **Property** parameter to sort the objects by **WS**.</span></span> <span data-ttu-id="29067-134">オブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-134">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="29067-135">`Select-Object`**最後** のパラメーターを使用して最後の5つのオブジェクトを指定します。これは、 **WS** の最大使用量を持つオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="29067-135">`Select-Object` uses the **Last** parameter to specify the last five objects, which are the objects with the highest **WS** usage.</span></span>

### <span data-ttu-id="29067-136">例 4: Id で履歴情報オブジェクトを並べ替える</span><span class="sxs-lookup"><span data-stu-id="29067-136">Example 4: Sort HistoryInfo objects by Id</span></span>

<span data-ttu-id="29067-137">このコマンドは、 **Id** プロパティを使用して、PowerShell セッションの **履歴情報** オブジェクトを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-137">This command sorts the PowerShell session's **HistoryInfo** objects using the **Id** property.</span></span> <span data-ttu-id="29067-138">各 PowerShell セッションには、独自のコマンド履歴があります。</span><span class="sxs-lookup"><span data-stu-id="29067-138">Each PowerShell session has its own command history.</span></span>

```
PS> Get-History | Sort-Object -Property Id -Descending

  Id CommandLine
  -- -----------
  10 Get-Command Sort-Object -Syntax
   9 $PSVersionTable
   8 Get-Command Sort-Object -Syntax
   7 Get-Command Sort-Object -ShowCommandInfo
   6 Get-ChildItem -Path C:\Test | Sort-Object -Property Length
   5 Get-Help Clear-History -online
   4 Get-Help Clear-History -full
   3 Get-ChildItem | Get-Member
   2 Get-Command Sort-Object -Syntax
   1 Set-Location C:\Test\
```

<span data-ttu-id="29067-139">`Get-History`コマンドレットは、現在の PowerShell セッションから履歴オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="29067-139">The `Get-History` cmdlet gets the history objects from the current PowerShell session.</span></span> <span data-ttu-id="29067-140">オブジェクトは、パイプラインを介してコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-140">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="29067-141">`Sort-Object`**Property** パラメーターを使用して、オブジェクトを **Id** で並べ替えます。 **降順** のパラメーターは、コマンド履歴を最新から古いものに並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-141">`Sort-Object` uses the **Property** parameter to sort the objects by **Id**. The **Descending** parameter sorts the command history from newest to oldest.</span></span>

### <span data-ttu-id="29067-142">例 5: ハッシュテーブルを使用してプロパティを昇順および降順で並べ替える</span><span class="sxs-lookup"><span data-stu-id="29067-142">Example 5: Use a hash table to sort properties in ascending and descending order</span></span>

<span data-ttu-id="29067-143">このコマンドは、2つのプロパティを使用して、オブジェクト、 **状態** 、および **DisplayName** を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-143">This command uses two properties to sort the objects, **Status** and **DisplayName**.</span></span> <span data-ttu-id="29067-144">**ステータス** は降順に並べ替えられ、 **DisplayName** は昇順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-144">**Status** is sorted in descending order and **DisplayName** is sorted in ascending order.</span></span>

<span data-ttu-id="29067-145">ハッシュテーブルは、 **プロパティ** パラメーターの値を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="29067-145">A hash table is used to specify the **Property** parameter's value.</span></span> <span data-ttu-id="29067-146">ハッシュテーブルでは、式を使用してプロパティ名と並べ替え順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="29067-146">The hash table uses an expression to specify the property names and sort orders.</span></span> <span data-ttu-id="29067-147">ハッシュ テーブルの詳細については、「[about_Hash_Tables (ハッシュ テーブルについて)](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="29067-147">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="29067-148">ハッシュテーブルで使用される **Status** プロパティは列挙型プロパティです。</span><span class="sxs-lookup"><span data-stu-id="29067-148">The **Status** property used in the hash table is an enumerated property.</span></span>
<span data-ttu-id="29067-149">詳細については、「 [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29067-149">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

```
PS C:\> Get-Service | Sort-Object -Property @{Expression = "Status"; Descending = $True}, @{Expression = "DisplayName"; Descending = $False}

Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  BthAvctpSvc        AVCTP service
Running  BrokerInfrastru... Background Tasks Infrastructure Ser...
Running  BDESVC             BitLocker Drive Encryption Service
Running  CoreMessagingRe... CoreMessaging
Running  VaultSvc           Credential Manager
Running  DsSvc              Data Sharing Service
Running  Dhcp               DHCP Client
...
Stopped  ALG                Application Layer Gateway Service
Stopped  AppMgmt            Application Management
Stopped  BITS               Background Intelligent Transfer Ser...
Stopped  wbengine           Block Level Backup Engine Service
Stopped  BluetoothUserSe... Bluetooth User Support Service_14fb...
Stopped  COMSysApp          COM+ System Application
Stopped  smstsmgr           ConfigMgr Task Sequence Agent
Stopped  DeviceInstall      Device Install Service
Stopped  MSDTC              Distributed Transaction Coordinator
```

<span data-ttu-id="29067-150">`Get-Service`コマンドレットは、コンピューター上のサービスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="29067-150">The `Get-Service` cmdlet gets the list of services on the computer.</span></span> <span data-ttu-id="29067-151">サービスオブジェクトは、パイプラインを介してコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-151">The service objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="29067-152">`Sort-Object`**プロパティパラメーターと** ハッシュテーブルを使用して、プロパティ名と並べ替え順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="29067-152">`Sort-Object` uses the **Property** parameter with a hash table to specify the property names and sort orders.</span></span> <span data-ttu-id="29067-153">**Property** パラメーターは2つのプロパティで並べ替えられます。 **状態** は降順で表示され、 **DisplayName** は昇順です。</span><span class="sxs-lookup"><span data-stu-id="29067-153">The **Property** parameter is sorted by two properties, **Status** in descending order and **DisplayName** in ascending order.</span></span>

<span data-ttu-id="29067-154">**Status** は列挙されたプロパティです。</span><span class="sxs-lookup"><span data-stu-id="29067-154">**Status** is an enumerated property.</span></span> <span data-ttu-id="29067-155">**Stopped** の値は **1** で、 **Running** の値は **4** です。</span><span class="sxs-lookup"><span data-stu-id="29067-155">**Stopped** has a value of **1** and **Running** has a value of **4**.</span></span> <span data-ttu-id="29067-156">**降順** のパラメーターは、プロセスを `$True` **停止** する前に **実行中** のプロセスが表示されるようにに設定されています。</span><span class="sxs-lookup"><span data-stu-id="29067-156">The **Descending** parameter is set to `$True` so that **Running** processes are displayed before **Stopped** processes.</span></span> <span data-ttu-id="29067-157">**DisplayName** は、 **降順** のパラメーターをに設定して `$False` 、表示名をアルファベット順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-157">**DisplayName** sets the **Descending** parameter to `$False` to sort the display names in alphabetical order.</span></span>

### <span data-ttu-id="29067-158">例 6: 期間によってテキストファイルを並べ替える</span><span class="sxs-lookup"><span data-stu-id="29067-158">Example 6: Sort text files by time span</span></span>

<span data-ttu-id="29067-159">このコマンドは、テキストファイルを、書き込み **時間** と **lastwritetime** の間の時間の降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-159">This command sorts text files in descending order by the time span between **CreationTime** and **LastWriteTime**.</span></span>

```
PS> Get-ChildItem -Path C:\Test\*.txt | Sort-Object -Property @{Expression = {$_.CreationTime - $_.LastWriteTime}; Descending = $False} | Format-Table CreationTime, LastWriteTime, FullName

CreationTime          LastWriteTime        FullName
------------          -------------        --------
11/21/2018 12:39:01   2/26/2019 08:59:36   C:\Test\test2.txt
12/4/2018 08:29:41    2/26/2019 08:57:05   C:\Test\powershell_list.txt
2/20/2019 08:15:59    2/26/2019 12:09:43   C:\Test\CreateTestFile.txt
2/20/2019 08:15:59    2/26/2019 12:07:41   C:\Test\Command.txt
2/20/2019 08:15:59    2/26/2019 08:57:52   C:\Test\ReadOnlyFile.txt
11/29/2018 15:16:50   12/4/2018 16:16:24   C:\Test\LogData.txt
2/25/2019 18:25:11    2/26/2019 12:08:47   C:\Test\Zsystemlog.txt
2/25/2019 18:25:11    2/26/2019 08:55:33   C:\Test\Bfile.txt
2/26/2019 08:46:59    2/26/2019 12:12:19   C:\Test\LogFile3.txt

```

<span data-ttu-id="29067-160">この `Get-ChildItem` コマンドレットでは、 **Path** パラメーターを使用して、ディレクトリ **C:\Test** とすべてのファイルを指定し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-160">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** and all of the `*.txt` files.</span></span> <span data-ttu-id="29067-161">オブジェクトは、パイプラインを介してコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-161">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="29067-162">`Sort-Object`**プロパティ** パラメーターをハッシュテーブルと共に使用 **して、** 指定された時間と **lastwritetime** の間の各ファイルの時間間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="29067-162">`Sort-Object` uses the **Property** parameter with a hash table to determine each files time span between **CreationTime** and **LastWriteTime**.</span></span> <span data-ttu-id="29067-163">**降順** のパラメーターをに設定すると、 `$False` 最長の時間間隔の順序で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-163">The **Descending** parameter is set to `$False` to sort in the order of longest to shortest time span.</span></span>

### <span data-ttu-id="29067-164">例 7: テキストファイル内の名前を並べ替える</span><span class="sxs-lookup"><span data-stu-id="29067-164">Example 7: Sort names in a text file</span></span>

<span data-ttu-id="29067-165">この例では、テキストファイルからリストを並べ替える方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29067-165">This example shows how to sort a list from a text file.</span></span> <span data-ttu-id="29067-166">元のファイルは、並べ替えられていないリストとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="29067-166">The original file is displayed as an unsorted list.</span></span> <span data-ttu-id="29067-167">`Sort-Object` 内容を並べ替えてから、重複を削除する **一意** のパラメーターを使用して内容を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-167">`Sort-Object` sorts the contents and then sorts the contents with the **Unique** parameter that removes duplicates.</span></span>

```
PS> Get-Content -Path C:\Test\ServerNames.txt
localhost
server01
server25
LOCALHOST
Server19
server3
localhost

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object
localhost
LOCALHOST
localhost
server01
Server19
server25
server3

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object -Unique
localhost
server01
Server19
server25
server3
```

<span data-ttu-id="29067-168">コマンドレットでは、 `Get-Content` **Path** パラメーターを使用して、ディレクトリとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="29067-168">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="29067-169">ファイル **ServerNames.txt** に、並べ替えられていないコンピューター名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29067-169">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span>

<span data-ttu-id="29067-170">コマンドレットでは、 `Get-Content` **Path** パラメーターを使用して、ディレクトリとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="29067-170">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="29067-171">ファイル **ServerNames.txt** に、並べ替えられていないコンピューター名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29067-171">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="29067-172">オブジェクトは、パイプラインを介してコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-172">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="29067-173">`Sort-Object` リストを既定の順序 (昇順) で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-173">`Sort-Object` sorts the list in the default order, ascending.</span></span>

<span data-ttu-id="29067-174">コマンドレットでは、 `Get-Content` **Path** パラメーターを使用して、ディレクトリとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="29067-174">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="29067-175">ファイル **ServerNames.txt** に、並べ替えられていないコンピューター名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29067-175">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="29067-176">オブジェクトは、パイプラインを介してコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-176">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="29067-177">`Sort-Object`**一意** のパラメーターを使用して、重複するコンピューター名を削除します。</span><span class="sxs-lookup"><span data-stu-id="29067-177">`Sort-Object` uses the **Unique** parameter to remove duplicate computer names.</span></span> <span data-ttu-id="29067-178">リストは、既定の順序 (昇順) で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-178">The list is sorted in the default order, ascending.</span></span>

### <span data-ttu-id="29067-179">例 8: 文字列を整数として並べ替える</span><span class="sxs-lookup"><span data-stu-id="29067-179">Example 8: Sort a string as an integer</span></span>

<span data-ttu-id="29067-180">この例では、文字列オブジェクトを含むテキストファイルを整数として並べ替える方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29067-180">This example shows how to sort a text file that contains string objects as integers.</span></span> <span data-ttu-id="29067-181">各コマンドをパイプラインでに送信し、 `Get-Member` オブジェクトが整数ではなく文字列であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="29067-181">You can send each command down the pipeline to `Get-Member` and verify that the objects are strings instead of integers.</span></span> <span data-ttu-id="29067-182">これらの例では、 `ProductId.txt` 並べ替えられていない製品番号の一覧がファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="29067-182">For these examples, the `ProductId.txt` file contains an unsorted list of product numbers.</span></span>

<span data-ttu-id="29067-183">最初の例では、は `Get-Content` ファイルの内容を取得し、パイプを使用して `Sort-Object` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="29067-183">In the first example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="29067-184">`Sort-Object` 文字列オブジェクトを昇順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-184">`Sort-Object` sorts the string objects in ascending order.</span></span>

```
PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object
0
1
12345
1500
2
2800
3500
4100
500
6200
77
88
99999

PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object {[int]$_}
0
1
2
77
88
500
1500
2800
3500
4100
6200
12345
99999
```

<span data-ttu-id="29067-185">2番目の例では、はファイルの内容を取得し、パイプを使用して `Get-Content` `Sort-Object` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="29067-185">In the second example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="29067-186">`Sort-Object` スクリプトブロックを使用して、文字列を整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="29067-186">`Sort-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="29067-187">このサンプルコードでは、は、 `[int]` 文字列を整数に変換し、 `$_` パイプラインによって取得される各文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="29067-187">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="29067-188">整数オブジェクトは、パイプラインからコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-188">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="29067-189">`Sort-Object` 整数オブジェクトを数値順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-189">`Sort-Object` sorts the integer objects in numeric order.</span></span>

<span data-ttu-id="29067-190">コマンドレットでは、 `Get-Content` **Path** パラメーターを使用して、ディレクトリとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="29067-190">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="29067-191">ファイル **ProductId.txt** には、並べ替えられていない製品番号の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29067-191">The file **ProductId.txt** contains an unsorted list of product numbers.</span></span> <span data-ttu-id="29067-192">文字列オブジェクトは、パイプラインを介してコマンドレットに送信され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-192">The string objects are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="29067-193">`ForEach-Object` スクリプトブロックを使用して、文字列を整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="29067-193">`ForEach-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="29067-194">このサンプルコードでは、は、 `[int]` 文字列を整数に変換し、 `$_` パイプラインによって取得される各文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="29067-194">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="29067-195">整数オブジェクトは、パイプラインからコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-195">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="29067-196">`Sort-Object` 整数オブジェクトを数値順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-196">`Sort-Object` sorts the integer objects in numeric order.</span></span>
## <span data-ttu-id="29067-197">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29067-197">PARAMETERS</span></span>

### <span data-ttu-id="29067-198">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="29067-198">-CaseSensitive</span></span>

<span data-ttu-id="29067-199">並べ替えで大文字と小文字が区別されることを示します。</span><span class="sxs-lookup"><span data-stu-id="29067-199">Indicates that the sort is case-sensitive.</span></span> <span data-ttu-id="29067-200">既定では、並べ替えでは大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="29067-200">By default, sorts are not case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Case-insensitive
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29067-201">-Culture</span><span class="sxs-lookup"><span data-stu-id="29067-201">-Culture</span></span>

<span data-ttu-id="29067-202">並べ替えに使用するカルチャ構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="29067-202">Specifies the cultural configuration to use for sorts.</span></span> <span data-ttu-id="29067-203">`Get-Culture`システムのカルチャ構成を表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="29067-203">Use `Get-Culture` to display the system's culture configuration.</span></span>

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

### <span data-ttu-id="29067-204">-降順</span><span class="sxs-lookup"><span data-stu-id="29067-204">-Descending</span></span>

<span data-ttu-id="29067-205">が `Sort-Object` オブジェクトを降順に並べ替えることを示します。</span><span class="sxs-lookup"><span data-stu-id="29067-205">Indicates that `Sort-Object` sorts the objects in descending order.</span></span> <span data-ttu-id="29067-206">既定値は昇順です。</span><span class="sxs-lookup"><span data-stu-id="29067-206">The default is ascending order.</span></span>

<span data-ttu-id="29067-207">並べ替え順序が異なる複数のプロパティを並べ替えるには、ハッシュテーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="29067-207">To sort multiple properties with different sort orders, use a hash table.</span></span> <span data-ttu-id="29067-208">たとえば、ハッシュテーブルを使用すると、1つのプロパティを昇順に並べ替え、別のプロパティを降順に並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="29067-208">For example, with a hash table you can sort one property in ascending order and another property in descending order.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Ascending
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29067-209">-InputObject</span><span class="sxs-lookup"><span data-stu-id="29067-209">-InputObject</span></span>

<span data-ttu-id="29067-210">オブジェクトを並べ替えるには、パイプラインをに送信 `Sort-Object` します。</span><span class="sxs-lookup"><span data-stu-id="29067-210">To sort objects, send them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="29067-211">**InputObject** パラメーターを使用して項目のコレクションを送信すると、は `Sort-Object` コレクションを表す1つのオブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="29067-211">If you use the **InputObject** parameter to submit a collection of items, `Sort-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="29067-212">1つのオブジェクトを並べ替えることができないため、は `Sort-Object` コレクション全体を変更せずに返します。</span><span class="sxs-lookup"><span data-stu-id="29067-212">Because one object cannot be sorted, `Sort-Object` returns the entire collection unchanged.</span></span>

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

### <span data-ttu-id="29067-213">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="29067-213">-Property</span></span>

<span data-ttu-id="29067-214">がオブジェクトの並べ替えに使用するプロパティ名を指定し `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-214">Specifies the property names that `Sort-Object` uses to sort the objects.</span></span> <span data-ttu-id="29067-215">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29067-215">Wildcards are permitted.</span></span>
<span data-ttu-id="29067-216">オブジェクトは、プロパティ値に基づいて並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-216">Objects are sorted based on the property values.</span></span> <span data-ttu-id="29067-217">プロパティを指定しない場合、 `Sort-Object` は、オブジェクトの種類またはオブジェクト自体の既定のプロパティに基づいて並べ替えを行います。</span><span class="sxs-lookup"><span data-stu-id="29067-217">If you do not specify a property, `Sort-Object` sorts based on default properties for the object type or the objects themselves.</span></span>

<span data-ttu-id="29067-218">複数のプロパティを昇順、降順、または並べ替え順序の組み合わせで並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="29067-218">Multiple properties can be sorted in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="29067-219">複数のプロパティを指定すると、オブジェクトは最初のプロパティで並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-219">When you specify multiple properties, the objects are sorted by the first property.</span></span> <span data-ttu-id="29067-220">1つ目のプロパティに対して複数のオブジェクトの値が同じ場合、それらのオブジェクトは2番目のプロパティで並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-220">If multiple objects have the same value for the first property, those objects are sorted by the second property.</span></span> <span data-ttu-id="29067-221">指定されたプロパティがなくなるか、またはオブジェクトのグループがなくなるまで、このプロセスが続行されます。</span><span class="sxs-lookup"><span data-stu-id="29067-221">This process continues until there are no more specified properties or no groups of objects.</span></span>

<span data-ttu-id="29067-222">**プロパティ** パラメーターの値には、計算されるプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="29067-222">The **Property** parameter's value can be a calculated property.</span></span> <span data-ttu-id="29067-223">集計プロパティを作成するには、ハッシュ テーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="29067-223">To create a calculated property, use a hash table.</span></span>

<span data-ttu-id="29067-224">ハッシュテーブルの有効なキーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29067-224">Valid keys for a hash table are as follows:</span></span>

- <span data-ttu-id="29067-225">`expression` - `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="29067-225">`expression` - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="29067-226">`ascending` もしくは `descending` - `<boolean>`</span><span class="sxs-lookup"><span data-stu-id="29067-226">`ascending` or `descending` - `<boolean>`</span></span>

<span data-ttu-id="29067-227">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29067-227">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: Default properties
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="29067-228">-一意</span><span class="sxs-lookup"><span data-stu-id="29067-228">-Unique</span></span>

<span data-ttu-id="29067-229">が `Sort-Object` 重複を排除し、コレクションの一意のメンバーのみを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="29067-229">Indicates that `Sort-Object` eliminates duplicates and returns only the unique members of the collection.</span></span> <span data-ttu-id="29067-230">並べ替えられた出力には、一意の値の最初のインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="29067-230">The first instance of a unique value is included in the sorted output.</span></span>

<span data-ttu-id="29067-231">**一意** では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="29067-231">**Unique** is case-insensitive.</span></span> <span data-ttu-id="29067-232">文字の大文字と小文字のみが異なる文字列は、同じものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="29067-232">Strings that only differ by character case are considered the same.</span></span>
<span data-ttu-id="29067-233">たとえば、文字や文字などです。</span><span class="sxs-lookup"><span data-stu-id="29067-233">For example, character and CHARACTER.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29067-234">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="29067-234">CommonParameters</span></span>

<span data-ttu-id="29067-235">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="29067-235">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="29067-236">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29067-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="29067-237">入力</span><span class="sxs-lookup"><span data-stu-id="29067-237">INPUTS</span></span>

### <span data-ttu-id="29067-238">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="29067-238">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="29067-239">パイプを使用して、並べ替えの対象となるオブジェクトをパイプすることができ `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-239">You can pipe the objects to be sorted to `Sort-Object`.</span></span>

## <span data-ttu-id="29067-240">出力</span><span class="sxs-lookup"><span data-stu-id="29067-240">OUTPUTS</span></span>

### <span data-ttu-id="29067-241">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="29067-241">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="29067-242">`Sort-Object` 並べ替えられたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="29067-242">`Sort-Object` returns the sorted objects.</span></span>

## <span data-ttu-id="29067-243">注</span><span class="sxs-lookup"><span data-stu-id="29067-243">NOTES</span></span>

<span data-ttu-id="29067-244">`Sort-Object`コマンドレットは、コマンドで指定されたプロパティまたはオブジェクトの種類の既定の並べ替えプロパティに基づいてオブジェクトを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="29067-244">The `Sort-Object` cmdlet sorts objects based on properties specified in the command or the default sort properties for the object type.</span></span> <span data-ttu-id="29067-245">既定の並べ替えプロパティは、 `PropertySet` ファイル内のという名前のを使用して定義され `DefaultKeyPropertySet` `types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="29067-245">Default sort properties are defined using the `PropertySet` named `DefaultKeyPropertySet` in a `types.ps1xml` file.</span></span> <span data-ttu-id="29067-246">詳細については、「 [about_Types.ps1xml](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29067-246">For more information, see [about_Types.ps1xml](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span></span>

<span data-ttu-id="29067-247">オブジェクトに指定されたプロパティのいずれかがない場合、そのオブジェクトのプロパティ値は、によって Null として解釈され、 `Sort-Object` 並べ替え順序の最後に配置されます。 **Null**</span><span class="sxs-lookup"><span data-stu-id="29067-247">If an object does not have one of the specified properties, the property value for that object is interpreted by `Sort-Object` as **Null** and placed at the end of the sort order.</span></span>

<span data-ttu-id="29067-248">並べ替えプロパティが使用できない場合、PowerShell はオブジェクト自体を比較しようとします。</span><span class="sxs-lookup"><span data-stu-id="29067-248">When no sort properties are available, PowerShell attempts to compare the objects themselves.</span></span>
<span data-ttu-id="29067-249">`Sort-Object` は、各プロパティに対して **Compare** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="29067-249">`Sort-Object` uses the **Compare** method for each property.</span></span> <span data-ttu-id="29067-250">プロパティが **IComparable** を実装していない場合、コマンドレットはプロパティの値を文字列に変換し、 **system.string に対して** **Compare** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="29067-250">If a property does not implement **IComparable** , the cmdlet converts the property value to a string and uses the **Compare** method for **System.String**.</span></span> <span data-ttu-id="29067-251">詳細については、「 [PSObject (Object) メソッド](/dotnet/api/system.management.automation.psobject.compareto)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29067-251">For more information, see [PSObject.CompareTo(Object) Method](/dotnet/api/system.management.automation.psobject.compareto).</span></span>

<span data-ttu-id="29067-252">**Status** などの列挙型プロパティを基準に並べ替えると、は `Sort-Object` 列挙値で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-252">If you sort on an enumerated property such as **Status** , `Sort-Object` sorts by the enumeration values.</span></span> <span data-ttu-id="29067-253">Windows サービスの場合、 **Stopped** の値は **1** で、 **Running** の値は **4** です。</span><span class="sxs-lookup"><span data-stu-id="29067-253">For Windows services, **Stopped** has a value of **1** and **Running** has a value of **4**.</span></span>
<span data-ttu-id="29067-254">**Stopped** は、列挙値によっ **て実行さ** れる前に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="29067-254">**Stopped** is sorted before **Running** because of the enumerated values.</span></span> <span data-ttu-id="29067-255">詳細については、「 [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29067-255">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="29067-256">関連リンク</span><span class="sxs-lookup"><span data-stu-id="29067-256">RELATED LINKS</span></span>

[<span data-ttu-id="29067-257">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="29067-257">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="29067-258">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="29067-258">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="29067-259">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="29067-259">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="29067-260">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="29067-260">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="29067-261">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="29067-261">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="29067-262">Group-Object</span><span class="sxs-lookup"><span data-stu-id="29067-262">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="29067-263">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="29067-263">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="29067-264">New-Object</span><span class="sxs-lookup"><span data-stu-id="29067-264">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="29067-265">Select-Object</span><span class="sxs-lookup"><span data-stu-id="29067-265">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="29067-266">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="29067-266">Tee-Object</span></span>](Tee-Object.md)
