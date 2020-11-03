---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Content
ms.openlocfilehash: e2b78a2062ac551b76c0a1b6b31d721bfefcf3bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215472"
---
# <span data-ttu-id="3beca-103">Get-Content</span><span class="sxs-lookup"><span data-stu-id="3beca-103">Get-Content</span></span>

## <span data-ttu-id="3beca-104">概要</span><span class="sxs-lookup"><span data-stu-id="3beca-104">SYNOPSIS</span></span>
<span data-ttu-id="3beca-105">指定された場所の項目の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-105">Gets the content of the item at the specified location.</span></span>

## <span data-ttu-id="3beca-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3beca-106">SYNTAX</span></span>

### <span data-ttu-id="3beca-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="3beca-107">Path (Default)</span></span>

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] [-Path] <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-UseTransaction] [-Delimiter <String>] [-Wait] [-Raw]
 [-Encoding <FileSystemCmdletProviderEncoding>] [-Stream <String>] [<CommonParameters>]
```

### <span data-ttu-id="3beca-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3beca-108">LiteralPath</span></span>

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] -LiteralPath <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-UseTransaction] [-Delimiter <String>] [-Wait] [-Raw]
 [-Encoding <FileSystemCmdletProviderEncoding>] [-Stream <String>] [<CommonParameters>]
```

## <span data-ttu-id="3beca-109">Description</span><span class="sxs-lookup"><span data-stu-id="3beca-109">DESCRIPTION</span></span>

<span data-ttu-id="3beca-110">`Get-Content`コマンドレットは、ファイル内のテキストや関数の内容など、パスで指定された場所にある項目の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-110">The `Get-Content` cmdlet gets the content of the item at the location specified by the path, such as the text in a file or the content of a function.</span></span> <span data-ttu-id="3beca-111">ファイルの場合、コンテンツは一度に1行読み取られ、オブジェクトのコレクションを返します。各オブジェクトは、コンテンツの行を表します。</span><span class="sxs-lookup"><span data-stu-id="3beca-111">For files, the content is read one line at a time and returns a collection of objects, each of which represents a line of content.</span></span>

<span data-ttu-id="3beca-112">PowerShell 3.0 以降では、 `Get-Content` 項目の先頭または末尾から指定された数の行を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="3beca-112">Beginning in PowerShell 3.0, `Get-Content` can also get a specified number of lines from the beginning or end of an item.</span></span>

## <span data-ttu-id="3beca-113">例</span><span class="sxs-lookup"><span data-stu-id="3beca-113">EXAMPLES</span></span>

### <span data-ttu-id="3beca-114">例 1: テキストファイルの内容を取得する</span><span class="sxs-lookup"><span data-stu-id="3beca-114">Example 1: Get the content of a text file</span></span>

<span data-ttu-id="3beca-115">この例では、現在のディレクトリ内のファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-115">This example gets the content of a file in the current directory.</span></span> <span data-ttu-id="3beca-116">`LineNumbers.txt`このファイルには100行の形式が含まれています。 **これは行 X** で、いくつかの例で使用されています。</span><span class="sxs-lookup"><span data-stu-id="3beca-116">The `LineNumbers.txt` file contains 100 lines in the format, **This is Line X** and is used in several examples.</span></span>

```powershell
1..100 | ForEach-Object { Add-Content -Path .\LineNumbers.txt -Value "This is line $_." }
Get-Content -Path .\LineNumbers.txt
```

```Output
This is Line 1
This is Line 2
...
This is line 99.
This is line 100.
```

<span data-ttu-id="3beca-117">配列値1-100 がパイプラインからコマンドレットに送信され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-117">The array values 1-100 are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="3beca-118">`ForEach-Object` スクリプトブロックをコマンドレットと共に使用して `Add-Content` 、ファイルを作成し `LineNumbers.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-118">`ForEach-Object` uses a script block with the `Add-Content` cmdlet to create the `LineNumbers.txt` file.</span></span> <span data-ttu-id="3beca-119">変数は、 `$_` 各オブジェクトがパイプライン内で送信されるときの配列値を表します。</span><span class="sxs-lookup"><span data-stu-id="3beca-119">The variable `$_` represents the array values as each object is sent down the pipeline.</span></span> <span data-ttu-id="3beca-120">コマンドレットでは、 `Get-Content` **Path** パラメーターを使用してファイルを指定 `LineNumbers.txt` し、PowerShell コンソールにコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="3beca-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `LineNumbers.txt` file and displays the content in the PowerShell console.</span></span>

### <span data-ttu-id="3beca-121">例 2: Get-Content 返す行の数を制限する</span><span class="sxs-lookup"><span data-stu-id="3beca-121">Example 2: Limit the number of lines Get-Content returns</span></span>

<span data-ttu-id="3beca-122">このコマンドは、ファイルの最初の5行を取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-122">This command gets the first five lines of a file.</span></span> <span data-ttu-id="3beca-123">**Totalcount** パラメーターは、コンテンツの最初の5行を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3beca-123">The **TotalCount** parameter is used to gets the first five lines of content.</span></span> <span data-ttu-id="3beca-124">この例では、 `LineNumbers.txt` 例1で作成したファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-124">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
Get-Content -Path .\LineNumbers.txt -TotalCount 5
```

```Output
This is Line 1
This is Line 2
This is Line 3
This is Line 4
This is Line 5
```

### <span data-ttu-id="3beca-125">例 3: テキストファイルから特定の内容の行を取得する</span><span class="sxs-lookup"><span data-stu-id="3beca-125">Example 3: Get a specific line of content from a text file</span></span>

<span data-ttu-id="3beca-126">このコマンドは、ファイルから特定の数の行を取得し、その内容の最終行のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="3beca-126">This command gets a specific number of lines from a file and then displays only the last line of that content.</span></span> <span data-ttu-id="3beca-127">**Totalcount** パラメーターは、コンテンツの最初の25行を取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-127">The **TotalCount** parameter gets the first 25 lines of content.</span></span> <span data-ttu-id="3beca-128">この例では、 `LineNumbers.txt` 例1で作成したファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-128">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
(Get-Content -Path .\LineNumbers.txt -TotalCount 25)[-1]
```

```Output
This is Line 25
```

<span data-ttu-id="3beca-129">コマンドは、 `Get-Content` 次の手順に進む前に、コマンドが完了するように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="3beca-129">The `Get-Content` command is wrapped in parentheses so that the command completes before going to the next step.</span></span> <span data-ttu-id="3beca-130">`Get-Content`行の配列を返します。これにより、かっこの後にインデックス表記を追加して、特定の行番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-130">`Get-Content`returns an array of lines, this allows you to add the index notation after the parenthesis to retrieve a specific line number.</span></span> <span data-ttu-id="3beca-131">この場合、インデックスは、 `[-1]` 返された25行の配列内の最後のインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-131">In this case, the `[-1]` index specifies the last index in the returned array of 25 retrieved lines.</span></span>

### <span data-ttu-id="3beca-132">例 4: テキストファイルの最終行を取得する</span><span class="sxs-lookup"><span data-stu-id="3beca-132">Example 4: Get the last line of a text file</span></span>

<span data-ttu-id="3beca-133">このコマンドは、ファイルからコンテンツの最初の行と最後の行を取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-133">This command gets the first line and last line of content from a file.</span></span> <span data-ttu-id="3beca-134">この例では、 `LineNumbers.txt` 例1で作成したファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-134">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
Get-Item -Path .\LineNumbers.txt | Get-Content -Tail 1
```

```Output
This is Line 100
```

<span data-ttu-id="3beca-135">この例では、 `Get-Item` コマンドレットを使用して、ファイルをパラメーターにパイプ処理できることを示して `Get-Content` います。</span><span class="sxs-lookup"><span data-stu-id="3beca-135">This example uses the `Get-Item` cmdlet to demonstrate that you can pipe files into the `Get-Content` parameter.</span></span> <span data-ttu-id="3beca-136">**Tail** パラメーターは、ファイルの最後の行を取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-136">The **Tail** parameter gets the last line of the file.</span></span> <span data-ttu-id="3beca-137">このメソッドは、すべての行を取得し、インデックス表記を使用するよりも高速です `[-1]` 。</span><span class="sxs-lookup"><span data-stu-id="3beca-137">This method is faster than retrieving all of the lines and using the `[-1]` index notation.</span></span>

### <span data-ttu-id="3beca-138">例 5: 代替データストリームの内容を取得する</span><span class="sxs-lookup"><span data-stu-id="3beca-138">Example 5: Get the content of an alternate data stream</span></span>

<span data-ttu-id="3beca-139">この例では、 **ストリーム** パラメーターを使用して、Windows NTFS ボリュームに格納されているファイルの代替データストリームの内容を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3beca-139">This example describes how to use the **Stream** parameter to get the content of an alternate data stream for files stored on a Windows NTFS volume.</span></span> <span data-ttu-id="3beca-140">この例では、 `Set-Content` コマンドレットを使用して、という名前のファイルにサンプルコンテンツを作成し `Stream.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-140">In this example, the `Set-Content` cmdlet is used to create sample content in a file named `Stream.txt`.</span></span>

```powershell
Set-Content -Path .\Stream.txt -Value 'This is the content of the Stream.txt file'
# Specify a wildcard to the Stream parameter to display all streams of the recently created file.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44
```

```powershell
# Retrieve the content of the primary, or $DATA stream.
Get-Content -Path .\Stream.txt -Stream $DATA
```

```Output
This is the content of the Stream.txt file
```

```powershell
# Use the Stream parameter of Add-Content to create a new Stream containing sample content.
Add-Content -Path .\Stream.txt -Stream NewStream -Value 'Added a stream named NewStream to Stream.txt'
# Use Get-Item to verify the stream was created.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44

PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt:NewStream
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt:NewStream
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : NewStream
Length        : 46
```

```powershell
# Retrieve the content of your newly created Stream.
Get-Content -Path .\Stream.txt -Stream NewStream
```

```Output
Added a stream named NewStream to Stream.txt
```

<span data-ttu-id="3beca-141">**Stream** パラメーターは、 [FileSystem プロバイダー](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring)の動的パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="3beca-141">The **Stream** parameter is a dynamic parameter of the [FileSystem provider](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).</span></span>
<span data-ttu-id="3beca-142">既定で `Get-Content` は、プライマリまたはストリームからのデータのみが取得さ `$DATA` れます。</span><span class="sxs-lookup"><span data-stu-id="3beca-142">By default `Get-Content` only retrieves data from the primary, or `$DATA` stream.</span></span> <span data-ttu-id="3beca-143">**ストリーム** は、属性、セキュリティ設定、その他のデータなどの非表示データを格納するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-143">**Streams** can be used to store hidden data such as attributes, security settings, or other data.</span></span>

### <span data-ttu-id="3beca-144">例 6: 生のコンテンツを取得する</span><span class="sxs-lookup"><span data-stu-id="3beca-144">Example 6: Get raw content</span></span>

<span data-ttu-id="3beca-145">この例のコマンドは、文字列の配列ではなく、1つの文字列としてファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-145">The commands in this example get the contents of a file as one string, instead of an array of strings.</span></span> <span data-ttu-id="3beca-146">既定では、 **生** の動的パラメーターを指定しない場合、コンテンツは改行で区切られた文字列の配列として返されます。</span><span class="sxs-lookup"><span data-stu-id="3beca-146">By default, without the **Raw** dynamic parameter, content is returned as an array of newline-delimited strings.</span></span> <span data-ttu-id="3beca-147">この例では、 `LineNumbers.txt` 例で作成したファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-147">This example uses the `LineNumbers.txt` file that was created in Example</span></span>
1.

```powershell
$raw = Get-Content -Path .\LineNumbers.txt -Raw
$lines = Get-Content -Path .\LineNumbers.txt
Write-Host "Raw contains $($raw.Count) lines."
Write-Host "Lines contains $($lines.Count) lines."
```

```Output
Raw contains 1 lines.
Lines contains 100 lines.
```

### <span data-ttu-id="3beca-148">例 7: Get-Content でフィルターを使用する</span><span class="sxs-lookup"><span data-stu-id="3beca-148">Example 7: Use Filters with Get-Content</span></span>

<span data-ttu-id="3beca-149">コマンドレットのフィルターを指定でき `Get-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-149">You can specify a filter to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="3beca-150">フィルターを使用して **path** パラメーターを修飾する場合は、パスの内容を示すために、末尾にアスタリスク () を含める必要があり `*` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-150">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="3beca-151">次のコマンドは、ディレクトリ内のすべてのファイルの内容を取得し `*.log` `C:\Temp` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-151">The following command gets the content of all `*.log` files in the `C:\Temp` directory.</span></span>

```powershell
Get-Content -Path C:\Temp\* -Filter *.log
```

### <span data-ttu-id="3beca-152">例 8: ファイルの内容をバイト配列として取得する</span><span class="sxs-lookup"><span data-stu-id="3beca-152">Example 8: Get file contents as a byte array</span></span>

<span data-ttu-id="3beca-153">この例では、ファイルの内容をとして1つのオブジェクトとして取得する方法を示し `[byte[]]` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-153">This example demonstrates how to get the contents of a file as a `[byte[]]` as a single object.</span></span>

```powershell
$byteArray = Get-Content -Path C:\temp\test.txt -Encoding Byte -Raw
Get-Member -InputObject $bytearray
```

```Output
   TypeName: System.Byte[]

Name           MemberType            Definition
----           ----------            ----------
Count          AliasProperty         Count = Length
Add            Method                int IList.Add(System.Object value)
```

<span data-ttu-id="3beca-154">最初のコマンドは、 **Encoding** パラメーターを使用して、ファイルからバイトのストリームを取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-154">The first command uses the **Encoding** parameter to get the stream of bytes from the file.</span></span>
<span data-ttu-id="3beca-155">**Raw** パラメーターは、バイトがとして返されることを保証し `[System.Byte[]]` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-155">The **Raw** parameter ensures that the bytes are returned as a `[System.Byte[]]`.</span></span> <span data-ttu-id="3beca-156">**Raw** パラメーターが指定されていない場合、戻り値はバイトのストリームになります。これは、PowerShell によってとして解釈され `[System.Object[]]` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-156">If the **Raw** parameter was absent, the return value is a stream of bytes, which is interpreted by PowerShell as `[System.Object[]]`.</span></span>

## <span data-ttu-id="3beca-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3beca-157">PARAMETERS</span></span>

### <span data-ttu-id="3beca-158">-Path</span><span class="sxs-lookup"><span data-stu-id="3beca-158">-Path</span></span>

<span data-ttu-id="3beca-159">がコンテンツを取得する位置の項目へのパスを指定し `Get-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-159">Specifies the path to an item where `Get-Content` gets the content.</span></span> <span data-ttu-id="3beca-160">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-160">Wildcard characters are permitted.</span></span> <span data-ttu-id="3beca-161">コンテナーのパスではなく、項目のパスを指定してください。</span><span class="sxs-lookup"><span data-stu-id="3beca-161">The paths must be paths to items, not to containers.</span></span> <span data-ttu-id="3beca-162">たとえば、ディレクトリのパスではなく、1 つ以上のファイルのパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3beca-162">For example, you must specify a path to one or more files, not a path to a directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="3beca-163">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3beca-163">-LiteralPath</span></span>

<span data-ttu-id="3beca-164">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-164">Specifies a path to one or more locations.</span></span> <span data-ttu-id="3beca-165">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3beca-165">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="3beca-166">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="3beca-166">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3beca-167">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="3beca-167">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3beca-168">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="3beca-168">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="3beca-169">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3beca-169">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3beca-170">-ReadCount</span><span class="sxs-lookup"><span data-stu-id="3beca-170">-ReadCount</span></span>

<span data-ttu-id="3beca-171">パイプライン経由で、一度に何行の内容を送るかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-171">Specifies how many lines of content are sent through the pipeline at a time.</span></span> <span data-ttu-id="3beca-172">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="3beca-172">The default value is 1.</span></span>
<span data-ttu-id="3beca-173">値が 0 (ゼロ) の場合は、すべての内容が一度に送信されます。</span><span class="sxs-lookup"><span data-stu-id="3beca-173">A value of 0 (zero) sends all of the content at one time.</span></span>

<span data-ttu-id="3beca-174">このパラメーターによって表示される内容が変わることはありませんが、内容を表示する時間には影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="3beca-174">This parameter does not change the content displayed, but it does affect the time it takes to display the content.</span></span> <span data-ttu-id="3beca-175">**ReadCount** の値を大きくすると、最初の行を返すまでの時間は長くなりますが、処理全体の時間が短くなります。</span><span class="sxs-lookup"><span data-stu-id="3beca-175">As the value of **ReadCount** increases, the time it takes to return the first line increases, but the total time for the operation decreases.</span></span> <span data-ttu-id="3beca-176">これにより、大きな項目で出ることの違いを実現できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-176">This can make a perceptible difference in large items.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3beca-177">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="3beca-177">-TotalCount</span></span>

<span data-ttu-id="3beca-178">ファイルまたはその他の項目の先頭からの行数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-178">Specifies the number of lines from the beginning of a file or other item.</span></span> <span data-ttu-id="3beca-179">既定値は -1 (すべての行) です。</span><span class="sxs-lookup"><span data-stu-id="3beca-179">The default is -1 (all lines).</span></span>

<span data-ttu-id="3beca-180">**Totalcount** パラメーター名またはそのエイリアス ( **最初** または **先頭** ) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-180">You can use the **TotalCount** parameter name or its aliases, **First** or **Head** .</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: First, Head

Required: False
Position: Named
Default value: -1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3beca-181">-尾</span><span class="sxs-lookup"><span data-stu-id="3beca-181">-Tail</span></span>

<span data-ttu-id="3beca-182">ファイルまたはその他の項目の末尾からの行数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-182">Specifies the number of lines from the end of a file or other item.</span></span> <span data-ttu-id="3beca-183">**末尾** のパラメーター名またはそのエイリアスである **Last** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-183">You can use the **Tail** parameter name or its alias, **Last** .</span></span> <span data-ttu-id="3beca-184">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3beca-184">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Last

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3beca-185">-Filter</span><span class="sxs-lookup"><span data-stu-id="3beca-185">-Filter</span></span>

<span data-ttu-id="3beca-186">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-186">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="3beca-187">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="3beca-187">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="3beca-188">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3beca-188">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="3beca-189">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="3beca-189">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3beca-190">-Include</span><span class="sxs-lookup"><span data-stu-id="3beca-190">-Include</span></span>

<span data-ttu-id="3beca-191">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-191">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="3beca-192">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="3beca-192">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3beca-193">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-193">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="3beca-194">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="3beca-195">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-195">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3beca-196">-除外</span><span class="sxs-lookup"><span data-stu-id="3beca-196">-Exclude</span></span>

<span data-ttu-id="3beca-197">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-197">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span>
<span data-ttu-id="3beca-198">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="3beca-198">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="3beca-199">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-199">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="3beca-200">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-200">Wildcard characters are permitted.</span></span>

<span data-ttu-id="3beca-201">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-201">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3beca-202">-Force</span><span class="sxs-lookup"><span data-stu-id="3beca-202">-Force</span></span>

<span data-ttu-id="3beca-203">**Force** は、読み取り専用属性をオーバーライドするか、ディレクトリを作成してファイルパスを完成させます。</span><span class="sxs-lookup"><span data-stu-id="3beca-203">**Force** will override a read-only attribute or create directories to complete a file path.</span></span> <span data-ttu-id="3beca-204">**Force** パラメーターは、ファイルのアクセス許可の変更またはセキュリティ制限のオーバーライドを試行しません。</span><span class="sxs-lookup"><span data-stu-id="3beca-204">The **Force** parameter does not attempt to change file permissions or override security restrictions.</span></span>

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

### <span data-ttu-id="3beca-205">-Credential</span><span class="sxs-lookup"><span data-stu-id="3beca-205">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="3beca-206">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3beca-206">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="3beca-207">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-207">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3beca-208">-区切り記号</span><span class="sxs-lookup"><span data-stu-id="3beca-208">-Delimiter</span></span>

<span data-ttu-id="3beca-209">が `Get-Content` 読み取り中にファイルをオブジェクトに分割するために使用する区切り記号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-209">Specifies the delimiter that `Get-Content` uses to divide the file into objects while it reads.</span></span> <span data-ttu-id="3beca-210">既定値は `\n` 、行末文字です。</span><span class="sxs-lookup"><span data-stu-id="3beca-210">The default is `\n`, the end-of-line character.</span></span> <span data-ttu-id="3beca-211">テキストファイルを読み取るときに、は `Get-Content` 文字列オブジェクトのコレクションを返します。各オブジェクトは行末文字で終わります。</span><span class="sxs-lookup"><span data-stu-id="3beca-211">When reading a text file, `Get-Content` returns a collection of string objects, each of which ends with an end-of-line character.</span></span> <span data-ttu-id="3beca-212">ファイルに存在しない区切り文字を入力すると、は `Get-Content` ファイル全体を単一の区切りのないオブジェクトとして返します。</span><span class="sxs-lookup"><span data-stu-id="3beca-212">When you enter a delimiter that does not exist in the file, `Get-Content` returns the entire file as a single, undelimited object.</span></span>

<span data-ttu-id="3beca-213">このパラメーターを使用すると、区切り記号としてファイルの区切り記号を指定することにより、大きなファイルを小さなファイルに分割できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-213">You can use this parameter to split a large file into smaller files by specifying a file separator, as the delimiter.</span></span> <span data-ttu-id="3beca-214">区切り文字は予約されています (破棄されません)。各ファイル セクションの最後の項目になります。</span><span class="sxs-lookup"><span data-stu-id="3beca-214">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

<span data-ttu-id="3beca-215">**Delimiter** は、 **FileSystem** プロバイダーによってコマンドレットに追加される動的パラメーターです `Get-Content` 。</span><span class="sxs-lookup"><span data-stu-id="3beca-215">**Delimiter** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="3beca-216">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3beca-216">This parameter works only in file system drives.</span></span>

> [!NOTE]
> <span data-ttu-id="3beca-217">現在、 **Delimiter** パラメーターの値が空の文字列の場合、 `Get-Content` は何も返しません。</span><span class="sxs-lookup"><span data-stu-id="3beca-217">Currently, when the value of the **Delimiter** parameter is an empty string, `Get-Content` does not return anything.</span></span> <span data-ttu-id="3beca-218">これは既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="3beca-218">This is a known issue.</span></span> <span data-ttu-id="3beca-219">強制的に、 `Get-Content` ファイル全体を1つの区切りのない文字列として返すようにする場合は。</span><span class="sxs-lookup"><span data-stu-id="3beca-219">To force `Get-Content` to return the entire file as a single, undelimited string.</span></span> <span data-ttu-id="3beca-220">ファイルに存在しない値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="3beca-220">Enter a value that does not exist in the file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: End-of-line character
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3beca-221">-Wait</span><span class="sxs-lookup"><span data-stu-id="3beca-221">-Wait</span></span>

<span data-ttu-id="3beca-222">すべての既存の行が出力された後もファイルを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="3beca-222">Keeps the file open after all existing lines have been output.</span></span> <span data-ttu-id="3beca-223">待機中、は 1 `Get-Content` 秒ごとにファイルをチェックし、存在する場合は新しい行を出力します。</span><span class="sxs-lookup"><span data-stu-id="3beca-223">While waiting, `Get-Content` checks the file once each second and outputs new lines if present.</span></span> <span data-ttu-id="3beca-224">CTRL キーを押し **ながら C** キーを押すと、 **待機** を中断できます。</span><span class="sxs-lookup"><span data-stu-id="3beca-224">You can interrupt **Wait** by pressing **CTRL+C** .</span></span> <span data-ttu-id="3beca-225">待機は、ファイルが削除された場合にも終了します。この場合、終了しないエラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="3beca-225">Waiting also ends if the file gets deleted, in which case a non-terminating error is reported.</span></span>

<span data-ttu-id="3beca-226">**Wait** は、FileSystem プロバイダーによってコマンドレットに追加される動的パラメーターです `Get-Content` 。</span><span class="sxs-lookup"><span data-stu-id="3beca-226">**Wait** is a dynamic parameter that the FileSystem provider adds to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="3beca-227">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3beca-227">This parameter works only in file system drives.</span></span> <span data-ttu-id="3beca-228">**Wait** を **Raw** と組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="3beca-228">**Wait** cannot be combined with **Raw** .</span></span>

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

### <span data-ttu-id="3beca-229">-Raw</span><span class="sxs-lookup"><span data-stu-id="3beca-229">-Raw</span></span>

<span data-ttu-id="3beca-230">改行文字を無視し、改行を保持した状態で、1つの文字列内のファイルの内容全体を返します。</span><span class="sxs-lookup"><span data-stu-id="3beca-230">Ignores newline characters and returns the entire contents of a file in one string with the newlines preserved.</span></span> <span data-ttu-id="3beca-231">既定では、ファイル内の改行文字は、入力を文字列の配列に分割する区切り記号として使用されます。</span><span class="sxs-lookup"><span data-stu-id="3beca-231">By default, newline characters in a file are used as delimiters to separate the input into an array of strings.</span></span> <span data-ttu-id="3beca-232">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3beca-232">This parameter was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="3beca-233">**Raw** は、 **FileSystem** プロバイダーによってコマンドレットに追加される動的パラメーターです `Get-Content` 。このパラメーターは、ファイルシステムドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3beca-233">**Raw** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="3beca-234">-Encoding</span><span class="sxs-lookup"><span data-stu-id="3beca-234">-Encoding</span></span>

<span data-ttu-id="3beca-235">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3beca-235">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="3beca-236">既定値は `Default` です。</span><span class="sxs-lookup"><span data-stu-id="3beca-236">The default value is `Default`.</span></span>

<span data-ttu-id="3beca-237">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3beca-237">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3beca-238">`Ascii` ASCII (7 ビット) 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-238">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="3beca-239">`BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-239">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="3beca-240">`BigEndianUTF32` は、ビッグエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-240">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="3beca-241">`Byte` 文字のセットをバイトシーケンスにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="3beca-241">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="3beca-242">`Default` は、システムのアクティブなコードページ (通常は ANSI) に対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-242">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="3beca-243">`Oem` は、システムの現在の OEM コードページに対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-243">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="3beca-244">`String``Unicode` と同じです。</span><span class="sxs-lookup"><span data-stu-id="3beca-244">`String` Same as `Unicode`.</span></span>
- <span data-ttu-id="3beca-245">`Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-245">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="3beca-246">`Unknown``Unicode` と同じです。</span><span class="sxs-lookup"><span data-stu-id="3beca-246">`Unknown` Same as `Unicode`.</span></span>
- <span data-ttu-id="3beca-247">`UTF7` UTF-7 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-247">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="3beca-248">`UTF8` UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-248">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="3beca-249">`UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-249">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="3beca-250">Encoding は、 **FileSystem** プロバイダーによってコマンドレットに追加される動的パラメーターです `Get-Content` 。</span><span class="sxs-lookup"><span data-stu-id="3beca-250">Encoding is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span>
<span data-ttu-id="3beca-251">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3beca-251">This parameter works only in file system drives.</span></span>

<span data-ttu-id="3beca-252">バイナリファイルからの読み取りと書き込みを行う場合は、 **Encoding** 動的パラメーターに **Byte** 値を使用し、 **readcount** パラメーターに値0を使用します。</span><span class="sxs-lookup"><span data-stu-id="3beca-252">When reading from and writing to binary files, use a value of **Byte** for the **Encoding** dynamic parameter and a value of 0 for the **ReadCount** parameter.</span></span> <span data-ttu-id="3beca-253">**Readcount** 値が0の場合は、1回の読み取り操作でファイル全体が読み取られ、1つのオブジェクト (PSObject) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="3beca-253">A **ReadCount** value of 0 reads the entire file in a single read operation and converts it into a single object (PSObject).</span></span> <span data-ttu-id="3beca-254">既定の **Readcount** 値は1で、各読み取り操作で1バイトを読み取り、各バイトを別のオブジェクトに変換します。これにより、コマンドレットを使用してファイルにバイトを書き込むとエラーが発生し `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-254">The default **ReadCount** value, 1, reads one byte in each read operation and converts each byte into a separate object, which causes errors when you use the `Set-Content` cmdlet to write the bytes to a file.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3beca-255">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="3beca-255">-Stream</span></span>

<span data-ttu-id="3beca-256">指定した代替 NTFS ファイル ストリームの内容をファイルから取得します。</span><span class="sxs-lookup"><span data-stu-id="3beca-256">Gets the contents of the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="3beca-257">ストリーム名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3beca-257">Enter the stream name.</span></span>
<span data-ttu-id="3beca-258">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3beca-258">Wildcards are not supported.</span></span>

<span data-ttu-id="3beca-259">**Stream** は、 **FileSystem** プロバイダーによってコマンドレットに追加される動的パラメーターです `Get-Content` 。</span><span class="sxs-lookup"><span data-stu-id="3beca-259">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span>
<span data-ttu-id="3beca-260">このパラメーターは、Windows システムのファイルシステムドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3beca-260">This parameter works only in file system drives on Windows systems.</span></span> <span data-ttu-id="3beca-261">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3beca-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3beca-262">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="3beca-262">-UseTransaction</span></span>

<span data-ttu-id="3beca-263">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3beca-263">Includes the command in the active transaction.</span></span> <span data-ttu-id="3beca-264">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="3beca-264">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="3beca-265">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3beca-265">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3beca-266">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3beca-266">CommonParameters</span></span>

<span data-ttu-id="3beca-267">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-267">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="3beca-268">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3beca-268">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3beca-269">入力</span><span class="sxs-lookup"><span data-stu-id="3beca-269">INPUTS</span></span>

### <span data-ttu-id="3beca-270">System.Int64、System.String[]、System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="3beca-270">System.Int64, System.String[], System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="3beca-271">パイプを使用して、読み取り数、合計数、パス、または資格情報をにパイプすることができ `Get-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-271">You can pipe the read count, total count, paths, or credentials to `Get-Content`.</span></span>

## <span data-ttu-id="3beca-272">出力</span><span class="sxs-lookup"><span data-stu-id="3beca-272">OUTPUTS</span></span>

### <span data-ttu-id="3beca-273">System.string、System.string</span><span class="sxs-lookup"><span data-stu-id="3beca-273">System.Byte, System.String</span></span>

<span data-ttu-id="3beca-274">`Get-Content` 文字列またはバイトを返します。</span><span class="sxs-lookup"><span data-stu-id="3beca-274">`Get-Content` returns strings or bytes.</span></span> <span data-ttu-id="3beca-275">出力の種類は、入力として指定するコンテンツの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3beca-275">The output type depends upon the type of content that you specify as input.</span></span>

## <span data-ttu-id="3beca-276">注</span><span class="sxs-lookup"><span data-stu-id="3beca-276">NOTES</span></span>

<span data-ttu-id="3beca-277">`Get-Content`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3beca-277">The `Get-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3beca-278">セッションのプロバイダーを取得するには、コマンドレットを使用し `Get-PSProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="3beca-278">To get the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="3beca-279">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3beca-279">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="3beca-280">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3beca-280">RELATED LINKS</span></span>

[<span data-ttu-id="3beca-281">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="3beca-281">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="3beca-282">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3beca-282">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="3beca-283">Add-Content</span><span class="sxs-lookup"><span data-stu-id="3beca-283">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="3beca-284">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="3beca-284">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="3beca-285">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="3beca-285">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="3beca-286">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="3beca-286">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="3beca-287">Set-Content</span><span class="sxs-lookup"><span data-stu-id="3beca-287">Set-Content</span></span>](Set-Content.md)