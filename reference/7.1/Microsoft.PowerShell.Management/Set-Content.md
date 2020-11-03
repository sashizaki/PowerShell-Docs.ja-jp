---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: bb9345470aa58dac7c14e1443c0fe4c12e7563a6
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "93219704"
---
# <span data-ttu-id="0f957-103">Set-Content</span><span class="sxs-lookup"><span data-stu-id="0f957-103">Set-Content</span></span>

## <span data-ttu-id="0f957-104">概要</span><span class="sxs-lookup"><span data-stu-id="0f957-104">SYNOPSIS</span></span>
<span data-ttu-id="0f957-105">新しいコンテンツを書き込むか、ファイル内の既存のコンテンツを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0f957-105">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="0f957-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f957-106">SYNTAX</span></span>

### <span data-ttu-id="0f957-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="0f957-107">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="0f957-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0f957-108">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="0f957-109">Description</span><span class="sxs-lookup"><span data-stu-id="0f957-109">DESCRIPTION</span></span>

<span data-ttu-id="0f957-110">`Set-Content` は、新しいコンテンツを書き込むか、またはファイル内のコンテンツを置き換える文字列処理コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="0f957-110">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="0f957-111">`Set-Content` 既存のコンテンツを置き換え `Add-Content` ます。また、ファイルにコンテンツを追加するコマンドレットとは異なります。</span><span class="sxs-lookup"><span data-stu-id="0f957-111">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="0f957-112">にコンテンツを送信するには、 `Set-Content` コマンドラインで **Value** パラメーターを使用するか、パイプラインを介してコンテンツを送信します。</span><span class="sxs-lookup"><span data-stu-id="0f957-112">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="0f957-113">次の例でファイルまたはディレクトリを作成する必要がある場合は、「 [New-Item](New-Item.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f957-113">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="0f957-114">例</span><span class="sxs-lookup"><span data-stu-id="0f957-114">EXAMPLES</span></span>

### <span data-ttu-id="0f957-115">例 1: ディレクトリ内の複数のファイルの内容を置き換える</span><span class="sxs-lookup"><span data-stu-id="0f957-115">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="0f957-116">この例では、現在のディレクトリ内の複数のファイルの内容を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0f957-116">This example replaces the content for multiple files in the current directory.</span></span>

```powershell
Get-ChildItem -Path .\Test*.txt
```

```Output
Test1.txt
Test2.txt
Test3.txt
```

```powershell
Set-Content -Path .\Test*.txt -Value 'Hello, World'
Get-Content -Path .\Test*.txt
```

```Output
Hello, World
Hello, World
Hello, World
```

<span data-ttu-id="0f957-117">この `Get-ChildItem` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリので始まる **.txt** ファイルを一覧表示します。 `Test*`</span><span class="sxs-lookup"><span data-stu-id="0f957-117">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="0f957-118">コマンドレットでは、 `Set-Content` **Path** パラメーターを使用してファイルを指定し `Test*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-118">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="0f957-119">**Value** パラメーターは、各ファイルの既存のコンテンツを置き換えるテキスト文字列 **Hello, World** を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f957-119">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="0f957-120">コマンドレットでは、 `Get-Content` **Path** パラメーターを使用してファイルを指定 `Test*.txt` し、各ファイルの内容を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="0f957-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="0f957-121">例 2: 新しいファイルを作成し、コンテンツを書き込む</span><span class="sxs-lookup"><span data-stu-id="0f957-121">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="0f957-122">この例では、新しいファイルを作成し、現在の日付と時刻をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="0f957-122">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="0f957-123">`Set-Content`**Path** および **Value** パラメーターを使用して、現在のディレクトリに **DateTime.txt** という名前の新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f957-123">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="0f957-124">**Value** パラメーターは、を使用して `Get-Date` 現在の日付と時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f957-124">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="0f957-125">`Set-Content`**DateTime** オブジェクトを文字列としてファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="0f957-125">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="0f957-126">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、PowerShell コンソールに **DateTime.txt** の内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="0f957-126">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="0f957-127">例 3: ファイル内のテキストを置換する</span><span class="sxs-lookup"><span data-stu-id="0f957-127">Example 3: Replace text in a file</span></span>

<span data-ttu-id="0f957-128">このコマンドは、既存のファイル内の word のすべてのインスタンスを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0f957-128">This command replaces all instances of word within an existing file.</span></span>

```powershell
Get-Content -Path .\Notice.txt
```

```Output
Warning
Replace Warning with a new word.
The word Warning was replaced.
```

```powershell
(Get-Content -Path .\Notice.txt) |
    ForEach-Object {$_ -Replace 'Warning', 'Caution'} |
        Set-Content -Path .\Notice.txt
Get-Content -Path .\Notice.txt
```

```Output
Caution
Replace Caution with a new word.
The word Caution was replaced.
```

<span data-ttu-id="0f957-129">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリ内の **Notice.txt** ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-129">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="0f957-130">`Get-Content`コマンドがかっこで囲まれ、パイプラインで送信される前にコマンドが終了します。</span><span class="sxs-lookup"><span data-stu-id="0f957-130">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="0f957-131">**Notice.txt** ファイルの内容は、パイプラインを介してコマンドレットに送信され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-131">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="0f957-132">`ForEach-Object` 自動変数を使用 `$_` し、 **警告** が発生するたびに **注意** して置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0f957-132">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution**.</span></span> <span data-ttu-id="0f957-133">オブジェクトは、パイプラインを介してコマンドレットに送信され `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-133">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="0f957-134">`Set-Content`**Path** パラメーターを使用して **Notice.txt** ファイルを指定し、更新された内容をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="0f957-134">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="0f957-135">最後の `Get-Content` コマンドレットは、更新されたファイルの内容を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="0f957-135">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="0f957-136">例 4: Set-Content でフィルターを使用する</span><span class="sxs-lookup"><span data-stu-id="0f957-136">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="0f957-137">コマンドレットのフィルターを指定でき `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-137">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="0f957-138">フィルターを使用して **path** パラメーターを修飾する場合は、パスの内容を示すために、末尾にアスタリスク () を含める必要があり `*` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-138">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="0f957-139">次のコマンドは、 `*.txt` ディレクトリ内のすべてのファイルの内容 `C:\Temp` を空の **値** に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-139">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="0f957-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f957-140">PARAMETERS</span></span>

### <span data-ttu-id="0f957-141">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="0f957-141">-AsByteStream</span></span>

<span data-ttu-id="0f957-142">コンテンツをバイトストリームとして読み取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-142">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="0f957-143">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0f957-143">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="0f957-144">**Encoding** パラメーターで **AsByteStream** パラメーターを使用すると、警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="0f957-144">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="0f957-145">**AsByteStream** パラメーターはエンコードを無視し、出力はバイトのストリームとして返されます。</span><span class="sxs-lookup"><span data-stu-id="0f957-145">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="0f957-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="0f957-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="0f957-147">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0f957-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="0f957-148">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f957-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="0f957-149">-Encoding</span><span class="sxs-lookup"><span data-stu-id="0f957-149">-Encoding</span></span>

<span data-ttu-id="0f957-150">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-150">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="0f957-151">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="0f957-151">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="0f957-152">Encoding は、FileSystem プロバイダーによってに追加される動的パラメーターです `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="0f957-152">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="0f957-153">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="0f957-153">This parameter works only in file system drives.</span></span>

<span data-ttu-id="0f957-154">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0f957-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="0f957-155">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f957-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="0f957-156">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f957-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="0f957-157">`bigendianutf32`: ビッグエンディアンのバイト順を使用して、32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f957-157">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="0f957-158">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f957-158">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="0f957-159">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f957-159">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="0f957-160">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f957-160">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="0f957-161">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f957-161">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="0f957-162">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f957-162">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="0f957-163">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f957-163">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="0f957-164">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f957-164">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="0f957-165">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-165">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="0f957-166">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f957-166">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="0f957-167">**Utf-7** \* の使用は推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0f957-167">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="0f957-168">PowerShell 7.1 では、Encoding パラメーターにを指定すると、警告が書き込まれ `utf7` ます。 **Encoding**</span><span class="sxs-lookup"><span data-stu-id="0f957-168">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

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

### <span data-ttu-id="0f957-169">-除外</span><span class="sxs-lookup"><span data-stu-id="0f957-169">-Exclude</span></span>

<span data-ttu-id="0f957-170">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-170">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="0f957-171">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="0f957-171">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0f957-172">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-172">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="0f957-173">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f957-173">Wildcard characters are permitted.</span></span> <span data-ttu-id="0f957-174">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-174">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0f957-175">-Filter</span><span class="sxs-lookup"><span data-stu-id="0f957-175">-Filter</span></span>

<span data-ttu-id="0f957-176">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-176">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="0f957-177">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="0f957-177">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="0f957-178">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f957-178">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="0f957-179">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="0f957-179">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="0f957-180">-Force</span><span class="sxs-lookup"><span data-stu-id="0f957-180">-Force</span></span>

<span data-ttu-id="0f957-181">ファイルが読み取り専用の場合でも、ファイルの内容をコマンドレットに強制的に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-181">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="0f957-182">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="0f957-182">Implementation varies from provider to provider.</span></span> <span data-ttu-id="0f957-183">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f957-183">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="0f957-184">**Force** パラメーターは、セキュリティ制限をオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="0f957-184">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="0f957-185">-Include</span><span class="sxs-lookup"><span data-stu-id="0f957-185">-Include</span></span>

<span data-ttu-id="0f957-186">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-186">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="0f957-187">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="0f957-187">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0f957-188">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-188">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="0f957-189">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f957-189">Wildcard characters are permitted.</span></span> <span data-ttu-id="0f957-190">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-190">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0f957-191">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0f957-191">-LiteralPath</span></span>

<span data-ttu-id="0f957-192">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-192">Specifies a path to one or more locations.</span></span> <span data-ttu-id="0f957-193">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f957-193">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="0f957-194">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="0f957-194">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0f957-195">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="0f957-195">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0f957-196">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="0f957-196">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="0f957-197">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f957-197">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="0f957-198">-なし Wline</span><span class="sxs-lookup"><span data-stu-id="0f957-198">-NoNewline</span></span>

<span data-ttu-id="0f957-199">入力オブジェクトの文字列形式が連結され、出力が形成されます。</span><span class="sxs-lookup"><span data-stu-id="0f957-199">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="0f957-200">出力文字列間にスペースや改行は挿入されません。</span><span class="sxs-lookup"><span data-stu-id="0f957-200">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="0f957-201">最後の出力文字列の後に改行は追加されません。</span><span class="sxs-lookup"><span data-stu-id="0f957-201">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="0f957-202">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0f957-202">-PassThru</span></span>

<span data-ttu-id="0f957-203">コンテンツを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="0f957-203">Returns an object that represents the content.</span></span> <span data-ttu-id="0f957-204">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="0f957-204">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="0f957-205">-Path</span><span class="sxs-lookup"><span data-stu-id="0f957-205">-Path</span></span>

<span data-ttu-id="0f957-206">コンテンツを受信する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-206">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="0f957-207">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f957-207">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0f957-208">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="0f957-208">-Stream</span></span>

<span data-ttu-id="0f957-209">コンテンツの代替データストリームを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-209">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="0f957-210">ストリームが存在しない場合は、このコマンドレットによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="0f957-210">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="0f957-211">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0f957-211">Wildcard characters are not supported.</span></span>

<span data-ttu-id="0f957-212">**Stream** は、 **FileSystem** プロバイダーによってに追加される動的パラメーターです `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="0f957-212">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="0f957-213">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="0f957-213">This parameter works only in file system drives.</span></span>

<span data-ttu-id="0f957-214">コマンドレットを使用して、 `Set-Content` ゾーンの内容を変更でき **ます。識別子** 代替データストリーム。</span><span class="sxs-lookup"><span data-stu-id="0f957-214">You can use the `Set-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="0f957-215">ただし、インターネットからダウンロードされたファイルをブロックするセキュリティチェックを省略する方法としては、この方法をお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="0f957-215">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="0f957-216">ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-216">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="0f957-217">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0f957-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0f957-218">-Value</span><span class="sxs-lookup"><span data-stu-id="0f957-218">-Value</span></span>

<span data-ttu-id="0f957-219">項目の新しい内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f957-219">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="0f957-220">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0f957-220">-Confirm</span></span>

<span data-ttu-id="0f957-221">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f957-221">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0f957-222">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0f957-222">-WhatIf</span></span>

<span data-ttu-id="0f957-223">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="0f957-223">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0f957-224">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="0f957-224">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0f957-225">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f957-225">CommonParameters</span></span>

<span data-ttu-id="0f957-226">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-226">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="0f957-227">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f957-227">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0f957-228">入力</span><span class="sxs-lookup"><span data-stu-id="0f957-228">INPUTS</span></span>

### <span data-ttu-id="0f957-229">System.Object</span><span class="sxs-lookup"><span data-stu-id="0f957-229">System.Object</span></span>

<span data-ttu-id="0f957-230">パイプを使用して、項目の新しい値を含むオブジェクトをにパイプすることができ `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-230">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="0f957-231">出力</span><span class="sxs-lookup"><span data-stu-id="0f957-231">OUTPUTS</span></span>

### <span data-ttu-id="0f957-232">None または System.String</span><span class="sxs-lookup"><span data-stu-id="0f957-232">None or System.String</span></span>

<span data-ttu-id="0f957-233">**PassThru** パラメーターを使用すると、によって、 `Set-Content` コンテンツを表す **system.string** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0f957-233">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="0f957-234">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="0f957-234">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0f957-235">注</span><span class="sxs-lookup"><span data-stu-id="0f957-235">NOTES</span></span>

- <span data-ttu-id="0f957-236">また、組み込みエイリアスであるを参照することもでき `Set-Content` `sc` ます。</span><span class="sxs-lookup"><span data-stu-id="0f957-236">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="0f957-237">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f957-237">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="0f957-238">`Set-Content` は、文字列処理用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="0f957-238">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="0f957-239">文字列以外のオブジェクトをにパイプする場合は `Set-Content` 、オブジェクトを書き込む前に文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="0f957-239">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="0f957-240">オブジェクトをファイルに書き込むには、を使用 `Out-File` します。</span><span class="sxs-lookup"><span data-stu-id="0f957-240">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="0f957-241">`Set-Content`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="0f957-241">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0f957-242">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="0f957-242">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="0f957-243">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f957-243">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0f957-244">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0f957-244">RELATED LINKS</span></span>

[<span data-ttu-id="0f957-245">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="0f957-245">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="0f957-246">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="0f957-246">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="0f957-247">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0f957-247">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="0f957-248">Add-Content</span><span class="sxs-lookup"><span data-stu-id="0f957-248">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="0f957-249">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="0f957-249">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="0f957-250">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="0f957-250">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="0f957-251">Get-Content</span><span class="sxs-lookup"><span data-stu-id="0f957-251">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="0f957-252">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="0f957-252">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="0f957-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="0f957-253">New-Item</span></span>](New-Item.md)

