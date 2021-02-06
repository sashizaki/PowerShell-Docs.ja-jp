---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 70ef5033c3c5d37ed00a88abfb0d1353f5d10854
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "99605440"
---
# <span data-ttu-id="89ae0-102">Add-Content</span><span class="sxs-lookup"><span data-stu-id="89ae0-102">Add-Content</span></span>

## <span data-ttu-id="89ae0-103">概要</span><span class="sxs-lookup"><span data-stu-id="89ae0-103">SYNOPSIS</span></span>
<span data-ttu-id="89ae0-104">指定した項目に内容を追加します。たとえば、ファイルに語を追加します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-104">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="89ae0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89ae0-105">SYNTAX</span></span>

### <span data-ttu-id="89ae0-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="89ae0-106">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="89ae0-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="89ae0-107">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="89ae0-108">Description</span><span class="sxs-lookup"><span data-stu-id="89ae0-108">DESCRIPTION</span></span>

<span data-ttu-id="89ae0-109">`Add-Content`コマンドレットは、指定された項目またはファイルにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-109">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="89ae0-110">内容を指定するには、コマンドに内容を入力するか、内容が格納されているオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-110">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="89ae0-111">次の例でファイルまたはディレクトリを作成する必要がある場合は、「 [New-Item](New-Item.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ae0-111">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="89ae0-112">例</span><span class="sxs-lookup"><span data-stu-id="89ae0-112">EXAMPLES</span></span>

### <span data-ttu-id="89ae0-113">例 1: 例外が発生したすべてのテキストファイルに文字列を追加する</span><span class="sxs-lookup"><span data-stu-id="89ae0-113">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="89ae0-114">この例では、現在のディレクトリ内のテキストファイルに値を追加しますが、ファイル名に基づいてファイルを除外します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-114">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="89ae0-115">**Path** パラメーターは、現在のディレクトリ内のすべてのファイルを指定し `.txt` ますが、 **Exclude** パラメーターは、指定されたパターンに一致するファイル名を無視します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-115">The **Path** parameter specifies all `.txt` files in the current directory, but the **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="89ae0-116">**値** パラメーターは、ファイルに書き込まれるテキスト文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-116">The **Value** parameter specifies the text string that is written to the files.</span></span>

### <span data-ttu-id="89ae0-117">例 2: 指定したファイルの末尾に日付を追加する</span><span class="sxs-lookup"><span data-stu-id="89ae0-117">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="89ae0-118">この例では、現在のディレクトリのファイルに日付を追加し、その日付を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-118">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

```Output
Tuesday, May 14, 2019 8:24:27 AM
Tuesday, May 14, 2019 8:24:27 AM
5/14/2019 8:24:27 AM
```

<span data-ttu-id="89ae0-119">コマンドレットにより、 `Add-Content` 現在のディレクトリに2つの新しいファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-119">The `Add-Content` cmdlet creates two new files in the current directory.</span></span> <span data-ttu-id="89ae0-120">**Value** パラメーターには、コマンドレットの出力が含まれてい `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-120">The **Value** parameter contains the output of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="89ae0-121">**PassThru** パラメーターは、追加された内容をパイプラインに出力します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-121">The **PassThru** parameter outputs the added contents to the pipeline.</span></span>
<span data-ttu-id="89ae0-122">出力を受け取るコマンドレットは他にないため、PowerShell コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-122">Because there is no other cmdlet to receive the output, it is displayed in the PowerShell console.</span></span>
<span data-ttu-id="89ae0-123">コマンドレットにより、 `Get-Content` 更新されたファイルが表示され `DateTimeFile1.log` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-123">The `Get-Content` cmdlet displays the updated file, `DateTimeFile1.log`.</span></span>

### <span data-ttu-id="89ae0-124">例 3: 指定したファイルの内容を別のファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="89ae0-124">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="89ae0-125">この例では、ファイルからコンテンツを取得し、その内容を変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-125">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="89ae0-126">変数は、コンテンツを別のファイルに追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-126">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

- <span data-ttu-id="89ae0-127">コマンドレットでは、 `Get-Content` の内容を取得し、その `CopyFromFile.txt` 内容を変数に格納し `$From` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-127">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt` and stores the contents in the `$From` variable.</span></span>
- <span data-ttu-id="89ae0-128">`Add-Content`コマンドレットは、 `CopyToFile.txt` 変数の内容を使用してファイルを更新し `$From` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-128">The `Add-Content` cmdlet updates the `CopyToFile.txt` file using the contents of the `$From` variable.</span></span>
- <span data-ttu-id="89ae0-129">コマンドレットによって `Get-Content` CopyToFile.txt が表示されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-129">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="89ae0-130">例 4: パイプラインを使用して、指定したファイルの内容を別のファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="89ae0-130">Example 4: Add the contents of a specified file to another file using the pipeline</span></span>

<span data-ttu-id="89ae0-131">この例では、ファイルからコンテンツを取得し、コマンドレットにパイプし `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-131">This example gets the content from a file and pipes it to the `Add-Content` cmdlet.</span></span>

```powershell
Get-Content -Path .\CopyFromFile.txt | Add-Content -Path .\CopyToFile.txt
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="89ae0-132">コマンドレットでは、 `Get-Content` の内容を取得し `CopyFromFile.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-132">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt`.</span></span> <span data-ttu-id="89ae0-133">結果は `Add-Content` 、を更新するコマンドレットにパイプ処理され `CopyToFile.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-133">The results are piped to the `Add-Content` cmdlet, which updates the `CopyToFile.txt`.</span></span>
<span data-ttu-id="89ae0-134">最後の `Get-Content` コマンドレットが表示され `CopyToFile.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-134">The last `Get-Content` cmdlet displays `CopyToFile.txt`.</span></span>

### <span data-ttu-id="89ae0-135">例 5: 新しいファイルを作成してコンテンツをコピーする</span><span class="sxs-lookup"><span data-stu-id="89ae0-135">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="89ae0-136">この例では、新しいファイルを作成し、既存のファイルの内容を新しいファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-136">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

- <span data-ttu-id="89ae0-137">コマンドレットでは、 `Add-Content` **Path** パラメーターと **Value** パラメーターを使用して、現在のディレクトリに新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-137">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span>
- <span data-ttu-id="89ae0-138">`Get-Content`コマンドレットは、既存のファイルの内容を取得 `CopyFromFile.txt` し、それを **Value** パラメーターに渡します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-138">The `Get-Content` cmdlet gets the contents of an existing file, `CopyFromFile.txt` and passes it to the **Value** parameter.</span></span> <span data-ttu-id="89ae0-139">コマンドレットを囲むかっこを実行すると、コマンドが開始される `Get-Content` 前にコマンドが終了し `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-139">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span>
- <span data-ttu-id="89ae0-140">コマンドレットにより、 `Get-Content` 新しいファイルの内容が表示され `NewFile.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-140">The `Get-Content` cmdlet displays the contents of the new file, `NewFile.txt`.</span></span>

### <span data-ttu-id="89ae0-141">例 6: 読み取り専用ファイルにコンテンツを追加する</span><span class="sxs-lookup"><span data-stu-id="89ae0-141">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="89ae0-142">このコマンドは、 **IsReadOnly** file 属性が **True** に設定されている場合でも、ファイルに値を追加します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-142">This command adds a value to the file even if the **IsReadOnly** file attribute is set to **True**.</span></span>
<span data-ttu-id="89ae0-143">この例には、読み取り専用ファイルを作成する手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89ae0-143">The steps to create a read-only file are included in the example.</span></span>

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar--         1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

- <span data-ttu-id="89ae0-144">この `New-Item` コマンドレットは、 **Path** パラメーターと **ItemType** パラメーターを使用して、現在のディレクトリにファイルを作成し `IsReadOnlyTextFile.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-144">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file `IsReadOnlyTextFile.txt` in the current directory.</span></span>
- <span data-ttu-id="89ae0-145">コマンドレットでは、 `Set-ItemProperty` **Name** パラメーターと **Value** パラメーターを使用して、ファイルの **IsReadOnly** プロパティを True に変更します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-145">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span>
- <span data-ttu-id="89ae0-146">この `Get-ChildItem` コマンドレットは、ファイルが空 (0) であり、読み取り専用属性 () を持っていることを示してい `r` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-146">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span>
- <span data-ttu-id="89ae0-147">コマンドレットでは、 `Add-Content` **Path** パラメーターを使用してファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-147">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="89ae0-148">**Value** パラメーターには、ファイルに追加するテキスト文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89ae0-148">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="89ae0-149">**Force** パラメーターは、テキストを読み取り専用ファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-149">The **Force** parameter writes the text to the read-only file.</span></span>
- <span data-ttu-id="89ae0-150">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用してファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-150">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="89ae0-151">読み取り専用属性を削除するには、 `Set-ItemProperty` **値** パラメーターをに設定してコマンドを使用し `False` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-151">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

### <span data-ttu-id="89ae0-152">例 7: Add-Content でフィルターを使用する</span><span class="sxs-lookup"><span data-stu-id="89ae0-152">Example 7: Use Filters with Add-Content</span></span>

<span data-ttu-id="89ae0-153">コマンドレットのフィルターを指定でき `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-153">You can specify a filter to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="89ae0-154">フィルターを使用して **path** パラメーターを修飾する場合は、パスの内容を示すために、末尾にアスタリスク () を含める必要があり `*` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-154">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="89ae0-155">次のコマンドは、ディレクトリ内のすべてのファイルの内容を "Done" という単語に追加し `*.txt` `C:\Temp` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-155">The following command adds the word "Done" the content of all `*.txt` files in the `C:\Temp` directory.</span></span>

```powershell
Add-Content -Path C:\Temp\* -Filter *.txt -Value "Done"
```

## <span data-ttu-id="89ae0-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89ae0-156">PARAMETERS</span></span>

### <span data-ttu-id="89ae0-157">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="89ae0-157">-AsByteStream</span></span>

<span data-ttu-id="89ae0-158">コンテンツをバイトストリームとして読み取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-158">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="89ae0-159">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="89ae0-159">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="89ae0-160">**Encoding** パラメーターで **AsByteStream** パラメーターを使用すると、警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-160">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="89ae0-161">**AsByteStream** パラメーターはエンコードを無視し、出力はバイトのストリームとして返されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-161">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="89ae0-162">-Credential</span><span class="sxs-lookup"><span data-stu-id="89ae0-162">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="89ae0-163">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-163">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="89ae0-164">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-164">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="89ae0-165">-Encoding</span><span class="sxs-lookup"><span data-stu-id="89ae0-165">-Encoding</span></span>

<span data-ttu-id="89ae0-166">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-166">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="89ae0-167">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="89ae0-167">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="89ae0-168">Encoding は、FileSystem プロバイダーによってコマンドレットに追加される動的パラメーターです `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="89ae0-168">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="89ae0-169">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-169">This parameter works only in file system drives.</span></span>

<span data-ttu-id="89ae0-170">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="89ae0-170">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="89ae0-171">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-171">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="89ae0-172">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-172">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="89ae0-173">`bigendianutf32`: ビッグエンディアンのバイト順を使用して、32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-173">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="89ae0-174">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-174">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="89ae0-175">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-175">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="89ae0-176">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-176">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="89ae0-177">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-177">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="89ae0-178">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-178">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="89ae0-179">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-179">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="89ae0-180">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-180">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="89ae0-181">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-181">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="89ae0-182">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ae0-182">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="89ae0-183">**Utf-7** _ の使用は推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="89ae0-183">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="89ae0-184">PowerShell 7.1 では、 `utf7` _ *Encoding*\* パラメーターにを指定すると、警告が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-184">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

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

### <span data-ttu-id="89ae0-185">-除外</span><span class="sxs-lookup"><span data-stu-id="89ae0-185">-Exclude</span></span>

<span data-ttu-id="89ae0-186">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-186">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="89ae0-187">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-187">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="89ae0-188">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-188">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="89ae0-189">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-189">Wildcard characters are permitted.</span></span> <span data-ttu-id="89ae0-190">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-190">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="89ae0-191">-Filter</span><span class="sxs-lookup"><span data-stu-id="89ae0-191">-Filter</span></span>

<span data-ttu-id="89ae0-192">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-192">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="89ae0-193">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="89ae0-193">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="89ae0-194">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ae0-194">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="89ae0-195">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="89ae0-195">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="89ae0-196">-Force</span><span class="sxs-lookup"><span data-stu-id="89ae0-196">-Force</span></span>

<span data-ttu-id="89ae0-197">読み取り専用属性をオーバーライドし、読み取り専用ファイルに内容を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="89ae0-197">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="89ae0-198">たとえば、**Force** を指定すると、読み取り専用属性がオーバーライドされるか、ファイル パスを完成させるためにディレクトリが作成されますが、ファイルのアクセス許可は変更されません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-198">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="89ae0-199">-Include</span><span class="sxs-lookup"><span data-stu-id="89ae0-199">-Include</span></span>

<span data-ttu-id="89ae0-200">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-200">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="89ae0-201">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-201">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="89ae0-202">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-202">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="89ae0-203">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-203">Wildcard characters are permitted.</span></span> <span data-ttu-id="89ae0-204">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-204">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="89ae0-205">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="89ae0-205">-LiteralPath</span></span>

<span data-ttu-id="89ae0-206">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-206">Specifies a path to one or more locations.</span></span> <span data-ttu-id="89ae0-207">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-207">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="89ae0-208">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-208">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="89ae0-209">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-209">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="89ae0-210">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-210">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="89ae0-211">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ae0-211">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="89ae0-212">-なし Wline</span><span class="sxs-lookup"><span data-stu-id="89ae0-212">-NoNewline</span></span>

<span data-ttu-id="89ae0-213">このコマンドレットがコンテンツに新しい行または復帰を追加しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-213">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="89ae0-214">入力オブジェクトの文字列形式が連結され、出力が形成されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-214">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="89ae0-215">出力文字列間にスペースや改行は挿入されません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-215">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="89ae0-216">最後の出力文字列の後に改行は追加されません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-216">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="89ae0-217">-PassThru</span><span class="sxs-lookup"><span data-stu-id="89ae0-217">-PassThru</span></span>

<span data-ttu-id="89ae0-218">追加された内容を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-218">Returns an object representing the added content.</span></span> <span data-ttu-id="89ae0-219">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-219">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="89ae0-220">-Path</span><span class="sxs-lookup"><span data-stu-id="89ae0-220">-Path</span></span>

<span data-ttu-id="89ae0-221">内容を追加する項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-221">Specifies the path to the items that receive the additional content.</span></span>
<span data-ttu-id="89ae0-222">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-222">Wildcard characters are permitted.</span></span>
<span data-ttu-id="89ae0-223">コンテナーのパスではなく、項目のパスを指定してください。</span><span class="sxs-lookup"><span data-stu-id="89ae0-223">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="89ae0-224">たとえば、ディレクトリのパスではなく、1 つ以上のファイルのパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89ae0-224">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="89ae0-225">複数のパスを指定する場合は、各パスをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="89ae0-225">If you specify multiple paths, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="89ae0-226">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="89ae0-226">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="89ae0-227">このパラメーターは Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-227">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="89ae0-228">コンテンツの代替データストリームを指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-228">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="89ae0-229">ストリームが存在しない場合は、このコマンドレットによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-229">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="89ae0-230">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-230">Wildcard characters are not supported.</span></span>

<span data-ttu-id="89ae0-231">**Stream** は、FileSystem プロバイダーによってに追加される動的パラメーターです `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="89ae0-231">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="89ae0-232">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-232">This parameter works only in file system drives.</span></span>

<span data-ttu-id="89ae0-233">コマンドレットを使用して、など `Add-Content` の代替データストリームの内容を変更でき `Zone.Identifier` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-233">You can use the `Add-Content` cmdlet to change the content of any alternate data stream, such as `Zone.Identifier`.</span></span> <span data-ttu-id="89ae0-234">ただし、インターネットからダウンロードされたファイルをブロックするセキュリティチェックを省略する方法としては、この方法をお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-234">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="89ae0-235">ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-235">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="89ae0-236">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="89ae0-236">This parameter was introduced in PowerShell 3.0.</span></span>  <span data-ttu-id="89ae0-237">PowerShell 7.2 の場合、で `Add-Content` は、ファイルとディレクトリの両方で別のデータストリームをターゲットにすることができます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-237">As of PowerShell 7.2, `Add-Content` can target alternative data streams on both files and directories.</span></span>


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

### <span data-ttu-id="89ae0-238">-Value</span><span class="sxs-lookup"><span data-stu-id="89ae0-238">-Value</span></span>

<span data-ttu-id="89ae0-239">追加する内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-239">Specifies the content to be added.</span></span> <span data-ttu-id="89ae0-240">**このデータが内部でのみ使用さ** れるなどの引用符で囲まれた文字列を入力するか、生成する **DateTime** オブジェクトなど、コンテンツを含むオブジェクトを指定し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-240">Type a quoted string, such as **This data is for internal use only**, or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="89ae0-241">パスは文字列であるため、パスを入力してファイルの内容を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-241">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="89ae0-242">コマンドを使用して `Get-Content` コンテンツを取得し、それを **Value** パラメーターに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-242">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="89ae0-243">-Confirm</span><span class="sxs-lookup"><span data-stu-id="89ae0-243">-Confirm</span></span>

<span data-ttu-id="89ae0-244">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-244">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="89ae0-245">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="89ae0-245">-WhatIf</span></span>

<span data-ttu-id="89ae0-246">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-246">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="89ae0-247">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-247">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="89ae0-248">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="89ae0-248">CommonParameters</span></span>

<span data-ttu-id="89ae0-249">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="89ae0-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89ae0-250">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ae0-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="89ae0-251">入力</span><span class="sxs-lookup"><span data-stu-id="89ae0-251">INPUTS</span></span>

### <span data-ttu-id="89ae0-252">System.object、システムの管理、PSCredential</span><span class="sxs-lookup"><span data-stu-id="89ae0-252">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="89ae0-253">パイプを使用して、値、パス、または資格情報をにパイプすることができ `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-253">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="89ae0-254">出力</span><span class="sxs-lookup"><span data-stu-id="89ae0-254">OUTPUTS</span></span>

### <span data-ttu-id="89ae0-255">None または System.String</span><span class="sxs-lookup"><span data-stu-id="89ae0-255">None or System.String</span></span>

<span data-ttu-id="89ae0-256">**PassThru** パラメーターを使用すると、によって、 `Add-Content` コンテンツを表す **system.string** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-256">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="89ae0-257">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="89ae0-257">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="89ae0-258">注</span><span class="sxs-lookup"><span data-stu-id="89ae0-258">NOTES</span></span>

- <span data-ttu-id="89ae0-259">オブジェクトをにパイプすると `Add-Content` 、オブジェクトは項目に追加される前に文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-259">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="89ae0-260">オブジェクト型によって文字列の形式が決まりますが、オブジェクトの既定の表示形式と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="89ae0-260">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="89ae0-261">文字列の形式を制御するには、送信コマンドレットの書式設定パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-261">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>
- <span data-ttu-id="89ae0-262">また、組み込みエイリアスであるを参照することもでき `Add-Content` `ac` ます。</span><span class="sxs-lookup"><span data-stu-id="89ae0-262">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="89ae0-263">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ae0-263">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="89ae0-264">`Add-Content`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="89ae0-264">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="89ae0-265">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="89ae0-265">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="89ae0-266">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ae0-266">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="89ae0-267">関連リンク</span><span class="sxs-lookup"><span data-stu-id="89ae0-267">RELATED LINKS</span></span>

[<span data-ttu-id="89ae0-268">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="89ae0-268">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="89ae0-269">about_Providers</span><span class="sxs-lookup"><span data-stu-id="89ae0-269">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="89ae0-270">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="89ae0-270">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="89ae0-271">Get-Content</span><span class="sxs-lookup"><span data-stu-id="89ae0-271">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="89ae0-272">Get-Item</span><span class="sxs-lookup"><span data-stu-id="89ae0-272">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="89ae0-273">New-Item</span><span class="sxs-lookup"><span data-stu-id="89ae0-273">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="89ae0-274">Set-Content</span><span class="sxs-lookup"><span data-stu-id="89ae0-274">Set-Content</span></span>](Set-Content.md)
