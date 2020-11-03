---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: ad2b2a2b32fa1dfbf722ff0af25bfafaf57de84a
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "93219680"
---
# <span data-ttu-id="d176d-103">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="d176d-103">Export-Csv</span></span>

## <span data-ttu-id="d176d-104">概要</span><span class="sxs-lookup"><span data-stu-id="d176d-104">SYNOPSIS</span></span>
<span data-ttu-id="d176d-105">オブジェクトを一連のコンマ区切り値 (CSV) 文字列に変換し、その文字列をファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="d176d-105">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="d176d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d176d-106">SYNTAX</span></span>

### <span data-ttu-id="d176d-107">区切り記号 (既定値)</span><span class="sxs-lookup"><span data-stu-id="d176d-107">Delimiter (Default)</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="d176d-108">UseCulture</span><span class="sxs-lookup"><span data-stu-id="d176d-108">UseCulture</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="d176d-109">Description</span><span class="sxs-lookup"><span data-stu-id="d176d-109">DESCRIPTION</span></span>

<span data-ttu-id="d176d-110">コマンドレットでは、 `Export-CSV` 送信するオブジェクトの CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d176d-110">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="d176d-111">各オブジェクトは、オブジェクトのプロパティ値のコンマ区切りのリストを含む行です。</span><span class="sxs-lookup"><span data-stu-id="d176d-111">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="d176d-112">コマンドレットを使用して `Export-CSV` スプレッドシートを作成し、CSV ファイルを入力として受け取るプログラムとデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="d176d-112">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="d176d-113">オブジェクトをコマンドレットに送信する前に書式設定しないでください `Export-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="d176d-113">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="d176d-114">が `Export-CSV` 書式設定されたオブジェクトを受け取る場合、CSV ファイルにはオブジェクトのプロパティではなく、書式設定のプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d176d-114">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="d176d-115">オブジェクトの選択したプロパティのみをエクスポートするには、コマンドレットを使用し `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-115">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="d176d-116">例</span><span class="sxs-lookup"><span data-stu-id="d176d-116">EXAMPLES</span></span>

### <span data-ttu-id="d176d-117">例 1: CSV ファイルにプロセスのプロパティをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d176d-117">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="d176d-118">この例では、特定のプロパティを持つ **プロセス** オブジェクトを選択し、そのオブジェクトを CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d176d-118">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

```powershell
Get-Process -Name WmiPrvSE | Select-Object -Property BasePriority,Id,SessionId,WorkingSet |
  Export-Csv -Path .\WmiData.csv -NoTypeInformation
Import-Csv -Path .\WmiData.csv
```

```Output
BasePriority Id    SessionId WorkingSet
------------ --    --------- ----------
8            976   0         20267008
8            2292  0         36786176
8            3816  0         30351360
8            8604  0         15011840
8            10008 0         8830976
8            11764 0         14237696
8            54632 0         9502720
```

<span data-ttu-id="d176d-119">`Get-Process`コマンドレットでは、 **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d176d-119">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="d176d-120">**Name** パラメーターは、WmiPrvSE process オブジェクトのみを含むように出力をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="d176d-120">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="d176d-121">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-121">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="d176d-122">`Select-Object`**Property** パラメーターを使用して、プロセスオブジェクトのプロパティのサブセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="d176d-122">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="d176d-123">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-123">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-124">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-124">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="d176d-125">**Path** パラメーターは、WmiData.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-125">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="d176d-126">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-126">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="d176d-127">この `Import-Csv` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-127">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="d176d-128">例 2: コンマ区切りファイルにプロセスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d176d-128">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="d176d-129">この例では、 **プロセス** オブジェクトを取得し、オブジェクトを CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d176d-129">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="d176d-130">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d176d-130">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="d176d-131">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-131">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-132">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-132">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="d176d-133">**Path** パラメーターは、Processes.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-133">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="d176d-134">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-134">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="d176d-135">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-135">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="d176d-136">例 3: セミコロンで区切られたファイルにプロセスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d176d-136">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="d176d-137">この例では、 **プロセス** オブジェクトを取得し、セミコロン区切り記号を使用してオブジェクトをファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d176d-137">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="d176d-138">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d176d-138">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="d176d-139">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-139">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-140">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-140">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="d176d-141">**Path** パラメーターは、Processes.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-141">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="d176d-142">**Delimiter** パラメーターでは、文字列値を区切るためのセミコロンを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-142">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="d176d-143">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-143">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="d176d-144">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-144">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="d176d-145">例 4: 現在のカルチャのリスト区切り記号を使用してプロセスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d176d-145">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="d176d-146">この例では、 **プロセス** オブジェクトを取得し、オブジェクトをファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d176d-146">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="d176d-147">区切り記号は、現在のカルチャのリスト区切り記号です。</span><span class="sxs-lookup"><span data-stu-id="d176d-147">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="d176d-148">この `Get-Culture` コマンドレットは、入れ子になったプロパティの **TextInfo** と **listseparator** を使用し、現在のカルチャの既定のリスト区切り記号を表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-148">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="d176d-149">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d176d-149">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="d176d-150">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-150">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-151">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-151">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="d176d-152">**Path** パラメーターは、Processes.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-152">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="d176d-153">**UseCulture** パラメーターは、現在のカルチャの既定のリスト区切り記号を区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="d176d-153">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="d176d-154">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-154">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="d176d-155">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-155">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="d176d-156">例 5: 型情報を含むプロセスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d176d-156">Example 5: Export processes with type information</span></span>

<span data-ttu-id="d176d-157">この例では、 **#TYPE** ヘッダー情報を CSV ファイルに含める方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d176d-157">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="d176d-158">PowerShell 6.0 より前のバージョンでは、 **#TYPE** ヘッダーが既定値です。</span><span class="sxs-lookup"><span data-stu-id="d176d-158">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -IncludeTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="d176d-159">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d176d-159">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="d176d-160">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-160">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-161">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-161">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="d176d-162">**Path** パラメーターは、Processes.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-162">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="d176d-163">**Includetypeinformation** には、CSV 出力に **#TYPE** 情報ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d176d-163">The **IncludeTypeInformation** includes the **#TYPE** information header in the CSV output.</span></span> <span data-ttu-id="d176d-164">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-164">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="d176d-165">例 6: CSV ファイルにオブジェクトをエクスポートして追加する</span><span class="sxs-lookup"><span data-stu-id="d176d-165">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="d176d-166">この例では、オブジェクトを CSV ファイルにエクスポートし、 **Append** パラメーターを使用してオブジェクトを既存のファイルに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d176d-166">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

```powershell
$AppService = (Get-Service -DisplayName *Application* | Select-Object -Property DisplayName, Status)
$AppService | Export-Csv -Path .\Services.Csv -NoTypeInformation
Get-Content -Path .\Services.Csv
$WinService = (Get-Service -DisplayName *Windows* | Select-Object -Property DisplayName, Status)
$WinService | Export-Csv -Path ./Services.csv -NoTypeInformation -Append
Get-Content -Path .\Services.Csv
```

```Output
"DisplayName","Status"
"Application Layer Gateway Service","Stopped"
"Application Identity","Running"
"Windows Audio Endpoint Builder","Running"
"Windows Audio","Running"
"Windows Event Log","Running"
```

<span data-ttu-id="d176d-167">コマンドレットでは、 `Get-Service` サービスオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d176d-167">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="d176d-168">**DisplayName** パラメーターは、word アプリケーションを含むサービスを返します。</span><span class="sxs-lookup"><span data-stu-id="d176d-168">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="d176d-169">サービスオブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-169">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="d176d-170">`Select-Object`**Property** パラメーターを使用して、 **DisplayName** プロパティと **Status** プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-170">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="d176d-171">`$AppService`変数は、オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="d176d-171">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="d176d-172">オブジェクトは、パイプラインを介して `$AppService` コマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-172">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-173">`Export-Csv` サービスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-173">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="d176d-174">**Path** パラメーターは、Services.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-174">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="d176d-175">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-175">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="d176d-176">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-176">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="d176d-177">`Get-Service`および `Select-Object` コマンドレットは、word ウィンドウを含むサービスに対して繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-177">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="d176d-178">変数には、 `$WinService` サービスオブジェクトが格納されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-178">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="d176d-179">コマンドレットでは、 `Export-Csv` **Append** パラメーターを使用して、 `$WinService` オブジェクトが既存の Services.csv ファイルに追加されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-179">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="d176d-180">`Get-Content`コマンドレットは、追加されたデータを含む更新されたファイルを表示するために繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-180">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="d176d-181">例 7: パイプライン内の Format コマンドレットで予期しない結果が発生する</span><span class="sxs-lookup"><span data-stu-id="d176d-181">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="d176d-182">この例は、パイプライン内で format コマンドレットを使用しないことが重要な理由を示しています。</span><span class="sxs-lookup"><span data-stu-id="d176d-182">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="d176d-183">予期しない出力を受信した場合は、パイプライン構文のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="d176d-183">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

```powershell
Get-Date | Select-Object -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\DateTime.csv -NoTypeInformation
Get-Content -Path .\DateTime.csv
```

```Output
"DateTime","Day","DayOfWeek","DayOfYear"
"Wednesday, January 2, 2019 14:59:34","2","Wednesday","2"
```

```powershell
Get-Date | Format-Table -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\FTDateTime.csv -NoTypeInformation
Get-Content -Path .\FTDateTime.csv
```

```Output
"ClassId2e4f51ef21dd47e99d3c952918aff9cd","pageHeaderEntry","pageFooterEntry","autosizeInfo", ...
"033ecb2bc07a4d43b5ef94ed5a35d280",,,,"Microsoft.PowerShell.Commands.Internal.Format. ...
"9e210fe47d09416682b841769c78b8a3",,,,,
"27c87ef9bbda4f709f6b4002fa4af63c",,,,,
"4ec4f0187cb04f4cb6973460dfe252df",,,,,
"cf522b78d86c486691226b40aa69e95c",,,,,
```

<span data-ttu-id="d176d-184">`Get-Date`コマンドレットでは、 **DateTime** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d176d-184">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="d176d-185">オブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-185">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="d176d-186">`Select-Object`**Property** パラメーターを使用して、オブジェクトのプロパティのサブセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="d176d-186">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="d176d-187">オブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-187">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-188">`Export-Csv` オブジェクトを CSV 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-188">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="d176d-189">**Path** パラメーターは、DateTime.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-189">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="d176d-190">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-190">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="d176d-191">`Get-Content`コマンドレットでは、 **Path** パラメーターを使用して、現在のディレクトリにある CSV ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-191">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="d176d-192">`Format-Table`パイプライン内でコマンドレットを使用してプロパティを選択すると、予期しない結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-192">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="d176d-193">`Format-Table` テーブル形式オブジェクトを、 `Export-Csv` **DateTime** オブジェクトではなく、コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="d176d-193">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="d176d-194">`Export-Csv` テーブル形式オブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-194">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="d176d-195">コマンドレットにより、 `Get-Content` テーブル形式オブジェクトを含む CSV ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-195">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="d176d-196">例 8: Force パラメーターを使用して読み取り専用ファイルを上書きする</span><span class="sxs-lookup"><span data-stu-id="d176d-196">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="d176d-197">この例では、空の読み取り専用ファイルを作成し、 **Force** パラメーターを使用してファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="d176d-197">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

```powershell
New-Item -Path .\ReadOnly.csv -ItemType File
Set-ItemProperty -Path .\ReadOnly.csv -Name IsReadOnly -Value $true
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
```

```Output
Export-Csv : Access to the path 'C:\ReadOnly.csv' is denied.
At line:1 char:15
+ Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
+               ~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (:) [Export-Csv], UnauthorizedAccessException
+ FullyQualifiedErrorId : FileOpenFailure,Microsoft.PowerShell.Commands.ExportCsvCommand
```

```powershell
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation -Force
Get-Content -Path .\ReadOnly.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="d176d-198">この `New-Item` コマンドレットは、 **Path** パラメーターと **ItemType** パラメーターを使用して、現在のディレクトリに ReadOnly.csv ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d176d-198">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="d176d-199">コマンドレットでは、 `Set-ItemProperty` **Name** パラメーターと **Value** パラメーターを使用して、ファイルの **IsReadOnly** プロパティを true に変更します。</span><span class="sxs-lookup"><span data-stu-id="d176d-199">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="d176d-200">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d176d-200">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="d176d-201">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-201">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-202">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-202">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="d176d-203">**Path** パラメーターは、ReadOnly.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-203">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="d176d-204">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-204">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="d176d-205">出力には、アクセスが拒否されたためにファイルが書き込まれていないことが示されています。</span><span class="sxs-lookup"><span data-stu-id="d176d-205">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="d176d-206">**Force** パラメーターをコマンドレットに追加して、 `Export-Csv` エクスポートにファイルへの書き込みを強制します。</span><span class="sxs-lookup"><span data-stu-id="d176d-206">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="d176d-207">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-207">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="d176d-208">例 9: Force パラメーターを Append と共に使用する</span><span class="sxs-lookup"><span data-stu-id="d176d-208">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="d176d-209">この例では、 **Force** パラメーターと **Append** パラメーターを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-209">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="d176d-210">これらのパラメーターを組み合わせると、一致しないオブジェクトプロパティを CSV ファイルに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d176d-210">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

```powershell
$Content = [PSCustomObject]@{Name = 'PowerShell Core'; Version = '6.0'}
$Content | Export-Csv -Path .\ParmFile.csv -NoTypeInformation
$AdditionalContent = [PSCustomObject]@{Name = 'Windows PowerShell'; Edition = 'Desktop'}
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
```

```Output
Export-Csv : Cannot append CSV content to the following file: ParmFile.csv.
The appended object does not have a property that corresponds to the following column:
Version. To continue with mismatched properties, add the -Force parameter, and then retry
 the command.
At line:1 char:22
+ $AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (Version:String) [Export-Csv], InvalidOperationException
+ FullyQualifiedErrorId : CannotAppendCsvWithMismatchedPropertyNames,Microsoft.PowerShell. ...
```

```powershell
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append -Force
Import-Csv -Path .\ParmFile.csv
```

```Output
Name               Version
----               -------
PowerShell Core    6.0
Windows PowerShell
```

<span data-ttu-id="d176d-211">式は、 **Name** プロパティと **Version** プロパティを持つ **pscustomobject** 作成します。</span><span class="sxs-lookup"><span data-stu-id="d176d-211">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="d176d-212">値は変数に格納され `$Content` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-212">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="d176d-213">変数は、パイプラインを介して `$Content` コマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-213">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-214">`Export-Csv`**Path** パラメーターを使用して、ParmFile.csv ファイルを現在のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="d176d-214">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="d176d-215">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-215">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="d176d-216">もう1つの式は、 **Name** プロパティと **Edition** プロパティを使用して **pscustomobject** 作成します。</span><span class="sxs-lookup"><span data-stu-id="d176d-216">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="d176d-217">値は変数に格納され `$AdditionalContent` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-217">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="d176d-218">変数は、パイプラインを介して `$AdditionalContent` コマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-218">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="d176d-219">ファイルにデータを追加するには、 **Append** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d176d-219">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="d176d-220">**バージョン** と **エディション** のプロパティ名が一致しないため、追加に失敗します。</span><span class="sxs-lookup"><span data-stu-id="d176d-220">The append fails because there is a property name mismatch between **Version** and **Edition**.</span></span>

<span data-ttu-id="d176d-221">`Export-Csv`コマンドレット **force** パラメーターを使用して、エクスポートにファイルへの書き込みを強制します。</span><span class="sxs-lookup"><span data-stu-id="d176d-221">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="d176d-222">**Edition** プロパティは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-222">The **Edition** property is discarded.</span></span> <span data-ttu-id="d176d-223">この `Import-Csv` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d176d-223">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="d176d-224">例 10: 2 つの列を囲む引用符を使用して CSV にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d176d-224">Example 10: Export to CSV with quotes around two columns</span></span>

<span data-ttu-id="d176d-225">この例では、 **DateTime** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-225">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -QuoteFields "DateTime","Date" -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### <span data-ttu-id="d176d-226">例 11: 必要な場合にのみ引用符を使用して CSV にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d176d-226">Example 11: Export to CSV with quotes only when needed</span></span>

<span data-ttu-id="d176d-227">この例では、 **DateTime** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-227">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -UseQuotes AsNeeded -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## <span data-ttu-id="d176d-228">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d176d-228">PARAMETERS</span></span>

### <span data-ttu-id="d176d-229">-追加</span><span class="sxs-lookup"><span data-stu-id="d176d-229">-Append</span></span>

<span data-ttu-id="d176d-230">このパラメーターを使用して、 `Export-CSV` 指定したファイルの末尾に CSV 出力を追加します。</span><span class="sxs-lookup"><span data-stu-id="d176d-230">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="d176d-231">このパラメーターを指定しないと、に `Export-CSV` よってファイルの内容が警告なしで置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d176d-231">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="d176d-232">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d176d-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d176d-233">-区切り記号</span><span class="sxs-lookup"><span data-stu-id="d176d-233">-Delimiter</span></span>

<span data-ttu-id="d176d-234">プロパティの値を区切る区切り記号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-234">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="d176d-235">既定値はコンマ ( `,` ) です。</span><span class="sxs-lookup"><span data-stu-id="d176d-235">The default is a comma (`,`).</span></span> <span data-ttu-id="d176d-236">コロン () などの文字を入力し `:` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-236">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="d176d-237">セミコロン () を指定するには `;` 、引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="d176d-237">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-238">-Encoding</span><span class="sxs-lookup"><span data-stu-id="d176d-238">-Encoding</span></span>

<span data-ttu-id="d176d-239">エクスポートされた CSV ファイルのエンコード方式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-239">Specifies the encoding for the exported CSV file.</span></span> <span data-ttu-id="d176d-240">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="d176d-240">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="d176d-241">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d176d-241">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="d176d-242">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="d176d-242">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="d176d-243">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d176d-243">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="d176d-244">`bigendianutf32`: ビッグエンディアンのバイト順を使用して、32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d176d-244">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="d176d-245">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d176d-245">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="d176d-246">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d176d-246">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="d176d-247">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d176d-247">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="d176d-248">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d176d-248">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="d176d-249">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d176d-249">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d176d-250">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d176d-250">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d176d-251">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d176d-251">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="d176d-252">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-252">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="d176d-253">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d176d-253">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="d176d-254">**Utf-7** \* の使用は推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d176d-254">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="d176d-255">PowerShell 7.1 では、Encoding パラメーターにを指定すると、警告が書き込まれ `utf7` ます。 **Encoding**</span><span class="sxs-lookup"><span data-stu-id="d176d-255">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-256">-Force</span><span class="sxs-lookup"><span data-stu-id="d176d-256">-Force</span></span>

<span data-ttu-id="d176d-257">このパラメーター `Export-Csv` を使用すると、は **読み取り専用** 属性でファイルを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="d176d-257">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="d176d-258">**Force** パラメーターと **Append** パラメーターを組み合わせると、一致しないプロパティを含むオブジェクトを CSV ファイルに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d176d-258">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="d176d-259">一致するプロパティのみがファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d176d-259">Only the properties that match are written to the file.</span></span> <span data-ttu-id="d176d-260">一致しないプロパティは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-260">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="d176d-261">-IncludeTypeInformation</span><span class="sxs-lookup"><span data-stu-id="d176d-261">-IncludeTypeInformation</span></span>

<span data-ttu-id="d176d-262">このパラメーターを使用する場合、CSV 出力の最初の行には **#TYPE** が含まれ、その後にオブジェクト型の完全修飾名が続きます。</span><span class="sxs-lookup"><span data-stu-id="d176d-262">When this parameter is used the first line of the CSV output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="d176d-263">たとえば、 **#TYPE** のようにします。</span><span class="sxs-lookup"><span data-stu-id="d176d-263">For example, **#TYPE System.Diagnostics.Process**.</span></span>

<span data-ttu-id="d176d-264">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d176d-264">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-265">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d176d-265">-InputObject</span></span>

<span data-ttu-id="d176d-266">CSV 文字列としてエクスポートするオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-266">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="d176d-267">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="d176d-267">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="d176d-268">パイプを使用してオブジェクトをにパイプ処理することもでき `Export-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-268">You can also pipe objects to `Export-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-269">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d176d-269">-LiteralPath</span></span>

<span data-ttu-id="d176d-270">CSV 出力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-270">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="d176d-271">**Path** と異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-271">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="d176d-272">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="d176d-272">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d176d-273">パスにエスケープ文字が含まれている場合は、単一引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="d176d-273">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="d176d-274">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="d176d-274">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-275">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="d176d-275">-NoClobber</span></span>

<span data-ttu-id="d176d-276">が既存のファイルを上書きしないようにするには、このパラメーターを使用し `Export-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-276">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="d176d-277">既定では、指定されたパスにファイルが存在する場合、は `Export-CSV` 警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="d176d-277">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-278">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="d176d-278">-NoTypeInformation</span></span>

<span data-ttu-id="d176d-279">出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d176d-279">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="d176d-280">このパラメーターは、PowerShell 6.0 の既定値になり、下位互換性のために用意されています。</span><span class="sxs-lookup"><span data-stu-id="d176d-280">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-281">-Path</span><span class="sxs-lookup"><span data-stu-id="d176d-281">-Path</span></span>

<span data-ttu-id="d176d-282">CSV 出力ファイルを保存する場所を指定する必須のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="d176d-282">A required parameter that specifies the location to save the CSV output file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-283">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="d176d-283">-UseCulture</span></span>

<span data-ttu-id="d176d-284">現在のカルチャの区切り記号を項目の区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="d176d-284">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="d176d-285">カルチャのリスト区切り記号を検索するには、コマンドを使用し `(Get-Culture).TextInfo.ListSeparator` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-285">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-286">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d176d-286">-Confirm</span></span>

<span data-ttu-id="d176d-287">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-287">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-288">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d176d-288">-WhatIf</span></span>

<span data-ttu-id="d176d-289">コマンドレットが処理または変更されないようにします。</span><span class="sxs-lookup"><span data-stu-id="d176d-289">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="d176d-290">出力には、コマンドレットが実行された場合に何が起こるかが示されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-290">The output shows what would happen if the cmdlet were run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-291">-QuoteFields</span><span class="sxs-lookup"><span data-stu-id="d176d-291">-QuoteFields</span></span>

<span data-ttu-id="d176d-292">引用符で囲む必要がある列の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-292">Specifies the names of the columns that should be quoted.</span></span> <span data-ttu-id="d176d-293">このパラメーターを使用する場合は、指定された列だけが引用符で囲まれます。</span><span class="sxs-lookup"><span data-stu-id="d176d-293">When this parameter is used, only the specified columns are quoted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: QF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-294">-Usotes</span><span class="sxs-lookup"><span data-stu-id="d176d-294">-UseQuotes</span></span>

<span data-ttu-id="d176d-295">CSV ファイルで引用符を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d176d-295">Specifies when quotes are used in the CSV files.</span></span> <span data-ttu-id="d176d-296">次のいずれかの値になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-296">Possible values are:</span></span>

- <span data-ttu-id="d176d-297">なし-何も引用しない</span><span class="sxs-lookup"><span data-stu-id="d176d-297">Never - don't quote anything</span></span>
- <span data-ttu-id="d176d-298">すべてを常に引用符で囲む (既定の動作)</span><span class="sxs-lookup"><span data-stu-id="d176d-298">Always - quote everything (default behavior)</span></span>
- <span data-ttu-id="d176d-299">AsNeeded-区切り文字を含む quote フィールドのみ</span><span class="sxs-lookup"><span data-stu-id="d176d-299">AsNeeded - only quote fields that contain a delimiter character</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BaseCsvWritingCommand+QuoteKind
Parameter Sets: (All)
Aliases: UQ

Required: False
Position: Named
Default value: Always
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d176d-300">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d176d-300">CommonParameters</span></span>

<span data-ttu-id="d176d-301">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d176d-301">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d176d-302">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d176d-302">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d176d-303">入力</span><span class="sxs-lookup"><span data-stu-id="d176d-303">INPUTS</span></span>

### <span data-ttu-id="d176d-304">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="d176d-304">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="d176d-305">パイプを使用して、拡張型システム (実行) アダプターを持つ任意のオブジェクトをにパイプでき `Export-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-305">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="d176d-306">出力</span><span class="sxs-lookup"><span data-stu-id="d176d-306">OUTPUTS</span></span>

### <span data-ttu-id="d176d-307">System.String</span><span class="sxs-lookup"><span data-stu-id="d176d-307">System.String</span></span>

<span data-ttu-id="d176d-308">CSV リストが Path パラメーターに指定されたファイルに送られます。</span><span class="sxs-lookup"><span data-stu-id="d176d-308">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="d176d-309">注</span><span class="sxs-lookup"><span data-stu-id="d176d-309">NOTES</span></span>

<span data-ttu-id="d176d-310">コマンドレットは、送信した `Export-CSV` オブジェクトを一連の CSV 文字列に変換し、指定したテキストファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="d176d-310">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="d176d-311">を使用し `Export-CSV -IncludeTypeInformation` て csv ファイルにオブジェクトを保存した後、コマンドレットを使用して、 `Import-Csv` csv ファイル内のテキストからオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d176d-311">You can use `Export-CSV -IncludeTypeInformation` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the text in the CSV file.</span></span>

<span data-ttu-id="d176d-312">CSV ファイルでは、各オブジェクトは、オブジェクトのプロパティ値のコンマ区切りリストで表されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-312">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="d176d-313">プロパティ値は、 **ToString ()** メソッドを使用して文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-313">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="d176d-314">文字列は、プロパティ値の名前で表されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-314">The strings are represented by the property value name.</span></span> <span data-ttu-id="d176d-315">`Export-CSV -IncludeTypeInformation` では、オブジェクトのメソッドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="d176d-315">`Export-CSV -IncludeTypeInformation` does not export the methods of the object.</span></span>

<span data-ttu-id="d176d-316">CSV 文字列は次のように出力されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-316">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="d176d-317">**Includetypeinformation** を使用する場合、最初の文字列には **#TYPE** 情報ヘッダーの後にオブジェクトの種類の完全修飾名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d176d-317">If **IncludeTypeInformation** is used, the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span>
  <span data-ttu-id="d176d-318">たとえば、 **#TYPE** のようにします。</span><span class="sxs-lookup"><span data-stu-id="d176d-318">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="d176d-319">**Includetypeinformation** が使用されていない場合、最初の文字列には列ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d176d-319">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="d176d-320">ヘッダーには、コンマ区切りのリストとして、最初のオブジェクトのプロパティ名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d176d-320">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="d176d-321">残りの文字列には、各オブジェクトのプロパティ値のコンマ区切りのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d176d-321">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="d176d-322">PowerShell 6.0 以降では、の既定の動作で `Export-CSV` は、 **#TYPE** 情報が CSV に含められず、 **notypeinformation** が暗黙的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d176d-322">Beginning with PowerShell 6.0 the default behavior of `Export-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="d176d-323">**Includetypeinformation** を使用して **#TYPE** 情報を含め、PowerShell 6.0 より前のの既定の動作をエミュレートすることができ `Export-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="d176d-323">**IncludeTypeInformation** can be used to include the **#TYPE** Information and emulate the default behavior of `Export-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="d176d-324">複数のオブジェクトをに送信すると `Export-CSV` 、は、 `Export-CSV` 最初に送信したオブジェクトのプロパティに基づいてファイルを整理します。</span><span class="sxs-lookup"><span data-stu-id="d176d-324">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="d176d-325">指定したプロパティのいずれかが残りのオブジェクトに含まれない場合、そのオブジェクトのプロパティ値は連続する 2 つのコンマで表される null になります。</span><span class="sxs-lookup"><span data-stu-id="d176d-325">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="d176d-326">残りのオブジェクトに追加のプロパティがある場合は、これらのプロパティ値は、ファイルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="d176d-326">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="d176d-327">コマンドレットを使用して、 `Import-Csv` ファイル内の CSV 文字列からオブジェクトを再作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d176d-327">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="d176d-328">結果のオブジェクトは、メソッドのない、プロパティ値の文字列形式で構成された元のオブジェクトの CSV バージョンです。</span><span class="sxs-lookup"><span data-stu-id="d176d-328">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="d176d-329">`ConvertTo-Csv` `ConvertFrom-Csv` コマンドレットおよびコマンドレットは、オブジェクトを csv 文字列と csv 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d176d-329">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="d176d-330">`Export-CSV` はと同じですが `ConvertTo-CSV` 、CSV 文字列をファイルに保存する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="d176d-330">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="d176d-331">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d176d-331">RELATED LINKS</span></span>

[<span data-ttu-id="d176d-332">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="d176d-332">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="d176d-333">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="d176d-333">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="d176d-334">Format-Table</span><span class="sxs-lookup"><span data-stu-id="d176d-334">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="d176d-335">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="d176d-335">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="d176d-336">Select-Object</span><span class="sxs-lookup"><span data-stu-id="d176d-336">Select-Object</span></span>](Select-Object.md)

