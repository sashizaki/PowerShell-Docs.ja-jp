---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: b0e889b95d2724dfa395b1b4a00b5c9ea878cc82
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "99602397"
---
# <span data-ttu-id="5e13d-102">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="5e13d-102">Export-Csv</span></span>

## <span data-ttu-id="5e13d-103">概要</span><span class="sxs-lookup"><span data-stu-id="5e13d-103">SYNOPSIS</span></span>
<span data-ttu-id="5e13d-104">オブジェクトを一連のコンマ区切り値 (CSV) 文字列に変換し、その文字列をファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-104">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="5e13d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5e13d-105">SYNTAX</span></span>

### <span data-ttu-id="5e13d-106">区切り記号 (既定値)</span><span class="sxs-lookup"><span data-stu-id="5e13d-106">Delimiter (Default)</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="5e13d-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="5e13d-107">UseCulture</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="5e13d-108">Description</span><span class="sxs-lookup"><span data-stu-id="5e13d-108">DESCRIPTION</span></span>

<span data-ttu-id="5e13d-109">コマンドレットでは、 `Export-CSV` 送信するオブジェクトの CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-109">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="5e13d-110">各オブジェクトは、オブジェクトのプロパティ値のコンマ区切りのリストを含む行です。</span><span class="sxs-lookup"><span data-stu-id="5e13d-110">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="5e13d-111">コマンドレットを使用して `Export-CSV` スプレッドシートを作成し、CSV ファイルを入力として受け取るプログラムとデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-111">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="5e13d-112">オブジェクトをコマンドレットに送信する前に書式設定しないでください `Export-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="5e13d-112">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="5e13d-113">が `Export-CSV` 書式設定されたオブジェクトを受け取る場合、CSV ファイルにはオブジェクトのプロパティではなく、書式設定のプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-113">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="5e13d-114">オブジェクトの選択したプロパティのみをエクスポートするには、コマンドレットを使用し `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-114">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="5e13d-115">例</span><span class="sxs-lookup"><span data-stu-id="5e13d-115">EXAMPLES</span></span>

### <span data-ttu-id="5e13d-116">例 1: CSV ファイルにプロセスのプロパティをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5e13d-116">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="5e13d-117">この例では、特定のプロパティを持つ **プロセス** オブジェクトを選択し、そのオブジェクトを CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-117">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

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

<span data-ttu-id="5e13d-118">`Get-Process`コマンドレットでは、**プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-118">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="5e13d-119">**Name** パラメーターは、WmiPrvSE process オブジェクトのみを含むように出力をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-119">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="5e13d-120">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-120">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="5e13d-121">`Select-Object`**Property** パラメーターを使用して、プロセスオブジェクトのプロパティのサブセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-121">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="5e13d-122">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-122">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-123">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-123">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="5e13d-124">**Path** パラメーターは、WmiData.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-124">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="5e13d-125">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-125">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="5e13d-126">この `Import-Csv` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-126">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="5e13d-127">例 2: コンマ区切りファイルにプロセスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5e13d-127">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="5e13d-128">この例では、 **プロセス** オブジェクトを取得し、オブジェクトを CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-128">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="5e13d-129">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-129">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="5e13d-130">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-130">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-131">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-131">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="5e13d-132">**Path** パラメーターは、Processes.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-132">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="5e13d-133">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-133">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="5e13d-134">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-134">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="5e13d-135">例 3: セミコロンで区切られたファイルにプロセスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5e13d-135">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="5e13d-136">この例では、 **プロセス** オブジェクトを取得し、セミコロン区切り記号を使用してオブジェクトをファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-136">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="5e13d-137">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-137">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="5e13d-138">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-138">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-139">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-139">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="5e13d-140">**Path** パラメーターは、Processes.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-140">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="5e13d-141">**Delimiter** パラメーターでは、文字列値を区切るためのセミコロンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-141">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="5e13d-142">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-142">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="5e13d-143">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-143">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="5e13d-144">例 4: 現在のカルチャのリスト区切り記号を使用してプロセスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5e13d-144">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="5e13d-145">この例では、 **プロセス** オブジェクトを取得し、オブジェクトをファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-145">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="5e13d-146">区切り記号は、現在のカルチャのリスト区切り記号です。</span><span class="sxs-lookup"><span data-stu-id="5e13d-146">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="5e13d-147">この `Get-Culture` コマンドレットは、入れ子になったプロパティの **TextInfo** と **listseparator** を使用し、現在のカルチャの既定のリスト区切り記号を表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-147">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="5e13d-148">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-148">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="5e13d-149">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-149">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-150">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-150">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="5e13d-151">**Path** パラメーターは、Processes.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-151">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="5e13d-152">**UseCulture** パラメーターは、現在のカルチャの既定のリスト区切り記号を区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-152">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="5e13d-153">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-153">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="5e13d-154">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-154">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="5e13d-155">例 5: 型情報を含むプロセスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5e13d-155">Example 5: Export processes with type information</span></span>

<span data-ttu-id="5e13d-156">この例では、 **#TYPE** ヘッダー情報を CSV ファイルに含める方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-156">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="5e13d-157">PowerShell 6.0 より前のバージョンでは、 **#TYPE** ヘッダーが既定値です。</span><span class="sxs-lookup"><span data-stu-id="5e13d-157">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -IncludeTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="5e13d-158">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-158">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="5e13d-159">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-159">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-160">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-160">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="5e13d-161">**Path** パラメーターは、Processes.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-161">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="5e13d-162">**Includetypeinformation** には、CSV 出力に **#TYPE** 情報ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e13d-162">The **IncludeTypeInformation** includes the **#TYPE** information header in the CSV output.</span></span> <span data-ttu-id="5e13d-163">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-163">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="5e13d-164">例 6: CSV ファイルにオブジェクトをエクスポートして追加する</span><span class="sxs-lookup"><span data-stu-id="5e13d-164">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="5e13d-165">この例では、オブジェクトを CSV ファイルにエクスポートし、 **Append** パラメーターを使用してオブジェクトを既存のファイルに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-165">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

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

<span data-ttu-id="5e13d-166">コマンドレットでは、 `Get-Service` サービスオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-166">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="5e13d-167">**DisplayName** パラメーターは、word アプリケーションを含むサービスを返します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-167">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="5e13d-168">サービスオブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-168">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="5e13d-169">`Select-Object`**Property** パラメーターを使用して、 **DisplayName** プロパティと **Status** プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-169">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="5e13d-170">`$AppService`変数は、オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-170">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="5e13d-171">オブジェクトは、パイプラインを介して `$AppService` コマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-171">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-172">`Export-Csv` サービスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-172">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="5e13d-173">**Path** パラメーターは、Services.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-173">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="5e13d-174">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-174">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="5e13d-175">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-175">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="5e13d-176">`Get-Service`および `Select-Object` コマンドレットは、word ウィンドウを含むサービスに対して繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-176">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="5e13d-177">変数には、 `$WinService` サービスオブジェクトが格納されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-177">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="5e13d-178">コマンドレットでは、 `Export-Csv` **Append** パラメーターを使用して、 `$WinService` オブジェクトが既存の Services.csv ファイルに追加されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-178">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="5e13d-179">`Get-Content`コマンドレットは、追加されたデータを含む更新されたファイルを表示するために繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-179">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="5e13d-180">例 7: パイプライン内の Format コマンドレットで予期しない結果が発生する</span><span class="sxs-lookup"><span data-stu-id="5e13d-180">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="5e13d-181">この例は、パイプライン内で format コマンドレットを使用しないことが重要な理由を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e13d-181">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="5e13d-182">予期しない出力を受信した場合は、パイプライン構文のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="5e13d-182">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

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

<span data-ttu-id="5e13d-183">`Get-Date`コマンドレットでは、 **DateTime** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-183">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="5e13d-184">オブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-184">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="5e13d-185">`Select-Object`**Property** パラメーターを使用して、オブジェクトのプロパティのサブセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-185">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="5e13d-186">オブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-186">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-187">`Export-Csv` オブジェクトを CSV 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-187">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="5e13d-188">**Path** パラメーターは、DateTime.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-188">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="5e13d-189">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-189">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="5e13d-190">`Get-Content`コマンドレットでは、 **Path** パラメーターを使用して、現在のディレクトリにある CSV ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-190">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="5e13d-191">`Format-Table`パイプライン内でコマンドレットを使用してプロパティを選択すると、予期しない結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-191">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="5e13d-192">`Format-Table` テーブル形式オブジェクトを、 `Export-Csv` **DateTime** オブジェクトではなく、コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-192">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="5e13d-193">`Export-Csv` テーブル形式オブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-193">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="5e13d-194">コマンドレットにより、 `Get-Content` テーブル形式オブジェクトを含む CSV ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-194">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="5e13d-195">例 8: Force パラメーターを使用して読み取り専用ファイルを上書きする</span><span class="sxs-lookup"><span data-stu-id="5e13d-195">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="5e13d-196">この例では、空の読み取り専用ファイルを作成し、 **Force** パラメーターを使用してファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-196">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

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

<span data-ttu-id="5e13d-197">この `New-Item` コマンドレットは、 **Path** パラメーターと **ItemType** パラメーターを使用して、現在のディレクトリに ReadOnly.csv ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-197">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="5e13d-198">コマンドレットでは、 `Set-ItemProperty` **Name** パラメーターと **Value** パラメーターを使用して、ファイルの **IsReadOnly** プロパティを true に変更します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-198">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="5e13d-199">コマンドレットでは、 `Get-Process` **プロセス** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-199">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="5e13d-200">プロセスオブジェクトは、パイプラインを介してコマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-200">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-201">`Export-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-201">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="5e13d-202">**Path** パラメーターは、ReadOnly.csv ファイルが現在のディレクトリに保存されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-202">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="5e13d-203">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-203">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="5e13d-204">出力には、アクセスが拒否されたためにファイルが書き込まれていないことが示されています。</span><span class="sxs-lookup"><span data-stu-id="5e13d-204">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="5e13d-205">**Force** パラメーターをコマンドレットに追加して、 `Export-Csv` エクスポートにファイルへの書き込みを強制します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-205">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="5e13d-206">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-206">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="5e13d-207">例 9: Force パラメーターを Append と共に使用する</span><span class="sxs-lookup"><span data-stu-id="5e13d-207">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="5e13d-208">この例では、 **Force** パラメーターと **Append** パラメーターを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-208">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="5e13d-209">これらのパラメーターを組み合わせると、一致しないオブジェクトプロパティを CSV ファイルに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-209">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

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

<span data-ttu-id="5e13d-210">式は、 **Name** プロパティと **Version** プロパティを持つ **pscustomobject** 作成します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-210">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="5e13d-211">値は変数に格納され `$Content` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-211">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="5e13d-212">変数は、パイプラインを介して `$Content` コマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-212">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-213">`Export-Csv`**Path** パラメーターを使用して、ParmFile.csv ファイルを現在のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-213">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="5e13d-214">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-214">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="5e13d-215">もう1つの式は、 **Name** プロパティと **Edition** プロパティを使用して **pscustomobject** 作成します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-215">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="5e13d-216">値は変数に格納され `$AdditionalContent` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-216">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="5e13d-217">変数は、パイプラインを介して `$AdditionalContent` コマンドレットに送信され `Export-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-217">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="5e13d-218">ファイルにデータを追加するには、 **Append** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-218">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="5e13d-219">**バージョン** と **エディション** のプロパティ名が一致しないため、追加に失敗します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-219">The append fails because there is a property name mismatch between **Version** and **Edition**.</span></span>

<span data-ttu-id="5e13d-220">`Export-Csv`コマンドレット **force** パラメーターを使用して、エクスポートにファイルへの書き込みを強制します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-220">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="5e13d-221">**Edition** プロパティは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-221">The **Edition** property is discarded.</span></span> <span data-ttu-id="5e13d-222">この `Import-Csv` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-222">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="5e13d-223">例 10: 2 つの列を囲む引用符を使用して CSV にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5e13d-223">Example 10: Export to CSV with quotes around two columns</span></span>

<span data-ttu-id="5e13d-224">この例では、 **DateTime** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-224">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -QuoteFields "DateTime","Date" -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### <span data-ttu-id="5e13d-225">例 11: 必要な場合にのみ引用符を使用して CSV にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5e13d-225">Example 11: Export to CSV with quotes only when needed</span></span>

<span data-ttu-id="5e13d-226">この例では、 **DateTime** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-226">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -UseQuotes AsNeeded -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## <span data-ttu-id="5e13d-227">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5e13d-227">PARAMETERS</span></span>

### <span data-ttu-id="5e13d-228">-追加</span><span class="sxs-lookup"><span data-stu-id="5e13d-228">-Append</span></span>

<span data-ttu-id="5e13d-229">このパラメーターを使用して、 `Export-CSV` 指定したファイルの末尾に CSV 出力を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-229">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="5e13d-230">このパラメーターを指定しないと、に `Export-CSV` よってファイルの内容が警告なしで置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-230">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="5e13d-231">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e13d-231">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5e13d-232">-区切り記号</span><span class="sxs-lookup"><span data-stu-id="5e13d-232">-Delimiter</span></span>

<span data-ttu-id="5e13d-233">プロパティの値を区切る区切り記号を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-233">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="5e13d-234">既定値はコンマ ( `,` ) です。</span><span class="sxs-lookup"><span data-stu-id="5e13d-234">The default is a comma (`,`).</span></span> <span data-ttu-id="5e13d-235">コロン () などの文字を入力し `:` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-235">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="5e13d-236">セミコロン () を指定するには `;` 、引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-236">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="5e13d-237">-Encoding</span><span class="sxs-lookup"><span data-stu-id="5e13d-237">-Encoding</span></span>

<span data-ttu-id="5e13d-238">エクスポートされた CSV ファイルのエンコード方式を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-238">Specifies the encoding for the exported CSV file.</span></span> <span data-ttu-id="5e13d-239">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="5e13d-239">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="5e13d-240">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e13d-240">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="5e13d-241">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-241">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="5e13d-242">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-242">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="5e13d-243">`bigendianutf32`: ビッグエンディアンのバイト順を使用して、32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-243">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="5e13d-244">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-244">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="5e13d-245">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-245">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="5e13d-246">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-246">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="5e13d-247">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-247">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="5e13d-248">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-248">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="5e13d-249">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-249">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="5e13d-250">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-250">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="5e13d-251">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-251">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="5e13d-252">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e13d-252">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="5e13d-253">**Utf-7** _ の使用は推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5e13d-253">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="5e13d-254">PowerShell 7.1 では、 `utf7` _ *Encoding*\* パラメーターにを指定すると、警告が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-254">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

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

### <span data-ttu-id="5e13d-255">-Force</span><span class="sxs-lookup"><span data-stu-id="5e13d-255">-Force</span></span>

<span data-ttu-id="5e13d-256">このパラメーター `Export-Csv` を使用すると、は **読み取り専用** 属性でファイルを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-256">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="5e13d-257">**Force** パラメーターと **Append** パラメーターを組み合わせると、一致しないプロパティを含むオブジェクトを CSV ファイルに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-257">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="5e13d-258">一致するプロパティのみがファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-258">Only the properties that match are written to the file.</span></span> <span data-ttu-id="5e13d-259">一致しないプロパティは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-259">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="5e13d-260">-IncludeTypeInformation</span><span class="sxs-lookup"><span data-stu-id="5e13d-260">-IncludeTypeInformation</span></span>

<span data-ttu-id="5e13d-261">このパラメーターを使用する場合、CSV 出力の最初の行には **#TYPE** が含まれ、その後にオブジェクト型の完全修飾名が続きます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-261">When this parameter is used the first line of the CSV output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="5e13d-262">たとえば、 **#TYPE** のようにします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-262">For example, **#TYPE System.Diagnostics.Process**.</span></span>

<span data-ttu-id="5e13d-263">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e13d-263">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="5e13d-264">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5e13d-264">-InputObject</span></span>

<span data-ttu-id="5e13d-265">CSV 文字列としてエクスポートするオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-265">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="5e13d-266">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-266">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="5e13d-267">パイプを使用してオブジェクトをにパイプ処理することもでき `Export-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-267">You can also pipe objects to `Export-CSV`.</span></span>

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

### <span data-ttu-id="5e13d-268">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5e13d-268">-LiteralPath</span></span>

<span data-ttu-id="5e13d-269">CSV 出力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-269">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="5e13d-270">**Path** と異なり、**LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-270">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="5e13d-271">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="5e13d-271">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5e13d-272">パスにエスケープ文字が含まれている場合は、単一引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-272">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="5e13d-273">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="5e13d-273">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="5e13d-274">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="5e13d-274">-NoClobber</span></span>

<span data-ttu-id="5e13d-275">が既存のファイルを上書きしないようにするには、このパラメーターを使用し `Export-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-275">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="5e13d-276">既定では、指定されたパスにファイルが存在する場合、は `Export-CSV` 警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-276">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="5e13d-277">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="5e13d-277">-NoTypeInformation</span></span>

<span data-ttu-id="5e13d-278">出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-278">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="5e13d-279">このパラメーターは、PowerShell 6.0 の既定値になり、下位互換性のために用意されています。</span><span class="sxs-lookup"><span data-stu-id="5e13d-279">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="5e13d-280">-Path</span><span class="sxs-lookup"><span data-stu-id="5e13d-280">-Path</span></span>

<span data-ttu-id="5e13d-281">CSV 出力ファイルを保存する場所を指定する必須のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="5e13d-281">A required parameter that specifies the location to save the CSV output file.</span></span>

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

### <span data-ttu-id="5e13d-282">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="5e13d-282">-UseCulture</span></span>

<span data-ttu-id="5e13d-283">現在のカルチャの区切り記号を項目の区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-283">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="5e13d-284">カルチャのリスト区切り記号を検索するには、コマンドを使用し `(Get-Culture).TextInfo.ListSeparator` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-284">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="5e13d-285">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5e13d-285">-Confirm</span></span>

<span data-ttu-id="5e13d-286">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-286">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5e13d-287">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5e13d-287">-WhatIf</span></span>

<span data-ttu-id="5e13d-288">コマンドレットが処理または変更されないようにします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-288">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="5e13d-289">出力には、コマンドレットが実行された場合に何が起こるかが示されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-289">The output shows what would happen if the cmdlet were run.</span></span>

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

### <span data-ttu-id="5e13d-290">-QuoteFields</span><span class="sxs-lookup"><span data-stu-id="5e13d-290">-QuoteFields</span></span>

<span data-ttu-id="5e13d-291">引用符で囲む必要がある列の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-291">Specifies the names of the columns that should be quoted.</span></span> <span data-ttu-id="5e13d-292">このパラメーターを使用する場合は、指定された列だけが引用符で囲まれます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-292">When this parameter is used, only the specified columns are quoted.</span></span> <span data-ttu-id="5e13d-293">このパラメーターは、PowerShell 7.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="5e13d-293">This parameter was added in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="5e13d-294">-Usotes</span><span class="sxs-lookup"><span data-stu-id="5e13d-294">-UseQuotes</span></span>

<span data-ttu-id="5e13d-295">CSV ファイルで引用符を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-295">Specifies when quotes are used in the CSV files.</span></span> <span data-ttu-id="5e13d-296">次のいずれかの値になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-296">Possible values are:</span></span>

- <span data-ttu-id="5e13d-297">なし-何も引用しない</span><span class="sxs-lookup"><span data-stu-id="5e13d-297">Never - don't quote anything</span></span>
- <span data-ttu-id="5e13d-298">すべてを常に引用符で囲む (既定の動作)</span><span class="sxs-lookup"><span data-stu-id="5e13d-298">Always - quote everything (default behavior)</span></span>
- <span data-ttu-id="5e13d-299">AsNeeded-区切り文字を含む quote フィールドのみ</span><span class="sxs-lookup"><span data-stu-id="5e13d-299">AsNeeded - only quote fields that contain a delimiter character</span></span>

<span data-ttu-id="5e13d-300">このパラメーターは、PowerShell 7.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="5e13d-300">This parameter was added in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="5e13d-301">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e13d-301">CommonParameters</span></span>

<span data-ttu-id="5e13d-302">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5e13d-302">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5e13d-303">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e13d-303">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5e13d-304">入力</span><span class="sxs-lookup"><span data-stu-id="5e13d-304">INPUTS</span></span>

### <span data-ttu-id="5e13d-305">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="5e13d-305">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="5e13d-306">パイプを使用して、拡張型システム (実行) アダプターを持つ任意のオブジェクトをにパイプでき `Export-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-306">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="5e13d-307">出力</span><span class="sxs-lookup"><span data-stu-id="5e13d-307">OUTPUTS</span></span>

### <span data-ttu-id="5e13d-308">System.String</span><span class="sxs-lookup"><span data-stu-id="5e13d-308">System.String</span></span>

<span data-ttu-id="5e13d-309">CSV リストが Path パラメーターに指定されたファイルに送られます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-309">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="5e13d-310">注</span><span class="sxs-lookup"><span data-stu-id="5e13d-310">NOTES</span></span>

<span data-ttu-id="5e13d-311">コマンドレットは、送信した `Export-CSV` オブジェクトを一連の CSV 文字列に変換し、指定したテキストファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-311">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="5e13d-312">を使用し `Export-CSV -IncludeTypeInformation` て csv ファイルにオブジェクトを保存した後、コマンドレットを使用して、 `Import-Csv` csv ファイル内のテキストからオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-312">You can use `Export-CSV -IncludeTypeInformation` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the text in the CSV file.</span></span>

<span data-ttu-id="5e13d-313">CSV ファイルでは、各オブジェクトは、オブジェクトのプロパティ値のコンマ区切りリストで表されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-313">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="5e13d-314">プロパティ値は、 **ToString ()** メソッドを使用して文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-314">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="5e13d-315">文字列は、プロパティ値の名前で表されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-315">The strings are represented by the property value name.</span></span> <span data-ttu-id="5e13d-316">`Export-CSV -IncludeTypeInformation` では、オブジェクトのメソッドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="5e13d-316">`Export-CSV -IncludeTypeInformation` does not export the methods of the object.</span></span>

<span data-ttu-id="5e13d-317">CSV 文字列は次のように出力されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-317">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="5e13d-318">**Includetypeinformation** を使用する場合、最初の文字列には **#TYPE** 情報ヘッダーの後にオブジェクトの種類の完全修飾名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-318">If **IncludeTypeInformation** is used, the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span>
  <span data-ttu-id="5e13d-319">たとえば、 **#TYPE** のようにします。</span><span class="sxs-lookup"><span data-stu-id="5e13d-319">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="5e13d-320">**Includetypeinformation** が使用されていない場合、最初の文字列には列ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-320">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="5e13d-321">ヘッダーには、コンマ区切りのリストとして、最初のオブジェクトのプロパティ名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-321">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="5e13d-322">残りの文字列には、各オブジェクトのプロパティ値のコンマ区切りのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-322">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="5e13d-323">PowerShell 6.0 以降では、の既定の動作で `Export-CSV` は、 **#TYPE** 情報が CSV に含められず、 **notypeinformation** が暗黙的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-323">Beginning with PowerShell 6.0 the default behavior of `Export-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="5e13d-324">**Includetypeinformation** を使用して **#TYPE** 情報を含め、PowerShell 6.0 より前のの既定の動作をエミュレートすることができ `Export-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-324">**IncludeTypeInformation** can be used to include the **#TYPE** Information and emulate the default behavior of `Export-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="5e13d-325">複数のオブジェクトをに送信すると `Export-CSV` 、は、 `Export-CSV` 最初に送信したオブジェクトのプロパティに基づいてファイルを整理します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-325">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="5e13d-326">指定したプロパティのいずれかが残りのオブジェクトに含まれない場合、そのオブジェクトのプロパティ値は連続する 2 つのコンマで表される null になります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-326">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="5e13d-327">残りのオブジェクトに追加のプロパティがある場合は、これらのプロパティ値は、ファイルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="5e13d-327">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="5e13d-328">コマンドレットを使用して、 `Import-Csv` ファイル内の CSV 文字列からオブジェクトを再作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5e13d-328">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="5e13d-329">結果のオブジェクトは、メソッドのない、プロパティ値の文字列形式で構成された元のオブジェクトの CSV バージョンです。</span><span class="sxs-lookup"><span data-stu-id="5e13d-329">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="5e13d-330">`ConvertTo-Csv` `ConvertFrom-Csv` コマンドレットおよびコマンドレットは、オブジェクトを csv 文字列と csv 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e13d-330">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="5e13d-331">`Export-CSV` はと同じですが `ConvertTo-CSV` 、CSV 文字列をファイルに保存する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="5e13d-331">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="5e13d-332">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5e13d-332">RELATED LINKS</span></span>

[<span data-ttu-id="5e13d-333">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="5e13d-333">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="5e13d-334">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="5e13d-334">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="5e13d-335">Format-Table</span><span class="sxs-lookup"><span data-stu-id="5e13d-335">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="5e13d-336">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="5e13d-336">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="5e13d-337">Select-Object</span><span class="sxs-lookup"><span data-stu-id="5e13d-337">Select-Object</span></span>](Select-Object.md)
