---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: d85e0219c325de998c5874224a33ac4263b787a3
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "99601414"
---
# <span data-ttu-id="57494-102">Set-Content</span><span class="sxs-lookup"><span data-stu-id="57494-102">Set-Content</span></span>

## <span data-ttu-id="57494-103">概要</span><span class="sxs-lookup"><span data-stu-id="57494-103">SYNOPSIS</span></span>
<span data-ttu-id="57494-104">新しいコンテンツを書き込むか、ファイル内の既存のコンテンツを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="57494-104">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="57494-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="57494-105">SYNTAX</span></span>

### <span data-ttu-id="57494-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="57494-106">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="57494-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="57494-107">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="57494-108">Description</span><span class="sxs-lookup"><span data-stu-id="57494-108">DESCRIPTION</span></span>

<span data-ttu-id="57494-109">`Set-Content` は、新しいコンテンツを書き込むか、またはファイル内のコンテンツを置き換える文字列処理コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="57494-109">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="57494-110">`Set-Content` 既存のコンテンツを置き換え `Add-Content` ます。また、ファイルにコンテンツを追加するコマンドレットとは異なります。</span><span class="sxs-lookup"><span data-stu-id="57494-110">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="57494-111">にコンテンツを送信するには、 `Set-Content` コマンドラインで **Value** パラメーターを使用するか、パイプラインを介してコンテンツを送信します。</span><span class="sxs-lookup"><span data-stu-id="57494-111">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="57494-112">次の例でファイルまたはディレクトリを作成する必要がある場合は、「 [New-Item](New-Item.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57494-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="57494-113">例</span><span class="sxs-lookup"><span data-stu-id="57494-113">EXAMPLES</span></span>

### <span data-ttu-id="57494-114">例 1: ディレクトリ内の複数のファイルの内容を置き換える</span><span class="sxs-lookup"><span data-stu-id="57494-114">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="57494-115">この例では、現在のディレクトリ内の複数のファイルの内容を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="57494-115">This example replaces the content for multiple files in the current directory.</span></span>

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

<span data-ttu-id="57494-116">この `Get-ChildItem` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリので始まる **.txt** ファイルを一覧表示します。 `Test*`</span><span class="sxs-lookup"><span data-stu-id="57494-116">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="57494-117">コマンドレットでは、 `Set-Content` **Path** パラメーターを使用してファイルを指定し `Test*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-117">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="57494-118">**Value** パラメーターは、各ファイルの既存のコンテンツを置き換えるテキスト文字列 **Hello, World** を提供します。</span><span class="sxs-lookup"><span data-stu-id="57494-118">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="57494-119">コマンドレットでは、 `Get-Content` **Path** パラメーターを使用してファイルを指定 `Test*.txt` し、各ファイルの内容を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="57494-119">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="57494-120">例 2: 新しいファイルを作成し、コンテンツを書き込む</span><span class="sxs-lookup"><span data-stu-id="57494-120">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="57494-121">この例では、新しいファイルを作成し、現在の日付と時刻をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="57494-121">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="57494-122">`Set-Content`**Path** および **Value** パラメーターを使用して、現在のディレクトリに **DateTime.txt** という名前の新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="57494-122">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="57494-123">**Value** パラメーターは、を使用して `Get-Date` 現在の日付と時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="57494-123">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="57494-124">`Set-Content`**DateTime** オブジェクトを文字列としてファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="57494-124">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="57494-125">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、PowerShell コンソールに **DateTime.txt** の内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="57494-125">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="57494-126">例 3: ファイル内のテキストを置換する</span><span class="sxs-lookup"><span data-stu-id="57494-126">Example 3: Replace text in a file</span></span>

<span data-ttu-id="57494-127">このコマンドは、既存のファイル内の word のすべてのインスタンスを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="57494-127">This command replaces all instances of word within an existing file.</span></span>

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

<span data-ttu-id="57494-128">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリ内の **Notice.txt** ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-128">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="57494-129">`Get-Content`コマンドがかっこで囲まれ、パイプラインで送信される前にコマンドが終了します。</span><span class="sxs-lookup"><span data-stu-id="57494-129">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="57494-130">**Notice.txt** ファイルの内容は、パイプラインを介してコマンドレットに送信され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-130">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="57494-131">`ForEach-Object` 自動変数を使用 `$_` し、 **警告** が発生するたびに **注意** して置き換えます。</span><span class="sxs-lookup"><span data-stu-id="57494-131">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution**.</span></span> <span data-ttu-id="57494-132">オブジェクトは、パイプラインを介してコマンドレットに送信され `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-132">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="57494-133">`Set-Content`**Path** パラメーターを使用して **Notice.txt** ファイルを指定し、更新された内容をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="57494-133">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="57494-134">最後の `Get-Content` コマンドレットは、更新されたファイルの内容を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="57494-134">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="57494-135">例 4: Set-Content でフィルターを使用する</span><span class="sxs-lookup"><span data-stu-id="57494-135">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="57494-136">コマンドレットのフィルターを指定でき `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-136">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="57494-137">フィルターを使用して **path** パラメーターを修飾する場合は、パスの内容を示すために、末尾にアスタリスク () を含める必要があり `*` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-137">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="57494-138">次のコマンドは、 `*.txt` ディレクトリ内のすべてのファイルの内容 `C:\Temp` を空の **値** に設定します。</span><span class="sxs-lookup"><span data-stu-id="57494-138">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="57494-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="57494-139">PARAMETERS</span></span>

### <span data-ttu-id="57494-140">-AsByteStream</span><span class="sxs-lookup"><span data-stu-id="57494-140">-AsByteStream</span></span>

<span data-ttu-id="57494-141">コンテンツをバイトストリームとして読み取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-141">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="57494-142">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="57494-142">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="57494-143">**Encoding** パラメーターで **AsByteStream** パラメーターを使用すると、警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="57494-143">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="57494-144">**AsByteStream** パラメーターはエンコードを無視し、出力はバイトのストリームとして返されます。</span><span class="sxs-lookup"><span data-stu-id="57494-144">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="57494-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="57494-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="57494-146">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="57494-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="57494-147">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="57494-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="57494-148">-Encoding</span><span class="sxs-lookup"><span data-stu-id="57494-148">-Encoding</span></span>

<span data-ttu-id="57494-149">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-149">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="57494-150">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="57494-150">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="57494-151">Encoding は、FileSystem プロバイダーによってに追加される動的パラメーターです `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="57494-151">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="57494-152">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="57494-152">This parameter works only in file system drives.</span></span>

<span data-ttu-id="57494-153">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57494-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="57494-154">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="57494-154">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="57494-155">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="57494-155">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="57494-156">`bigendianutf32`: ビッグエンディアンのバイト順を使用して、32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="57494-156">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="57494-157">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="57494-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="57494-158">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="57494-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="57494-159">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="57494-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="57494-160">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="57494-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="57494-161">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="57494-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="57494-162">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="57494-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="57494-163">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="57494-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="57494-164">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="57494-165">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="57494-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="57494-166">**Utf-7** _ の使用は推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="57494-166">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="57494-167">PowerShell 7.1 では、 `utf7` _ *Encoding*\* パラメーターにを指定すると、警告が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="57494-167">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

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

### <span data-ttu-id="57494-168">-除外</span><span class="sxs-lookup"><span data-stu-id="57494-168">-Exclude</span></span>

<span data-ttu-id="57494-169">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-169">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="57494-170">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="57494-170">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="57494-171">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-171">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="57494-172">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="57494-172">Wildcard characters are permitted.</span></span> <span data-ttu-id="57494-173">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-173">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="57494-174">-Filter</span><span class="sxs-lookup"><span data-stu-id="57494-174">-Filter</span></span>

<span data-ttu-id="57494-175">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-175">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="57494-176">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="57494-176">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="57494-177">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57494-177">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="57494-178">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="57494-178">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="57494-179">-Force</span><span class="sxs-lookup"><span data-stu-id="57494-179">-Force</span></span>

<span data-ttu-id="57494-180">ファイルが読み取り専用の場合でも、ファイルの内容をコマンドレットに強制的に設定します。</span><span class="sxs-lookup"><span data-stu-id="57494-180">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="57494-181">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="57494-181">Implementation varies from provider to provider.</span></span> <span data-ttu-id="57494-182">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57494-182">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="57494-183">**Force** パラメーターは、セキュリティ制限をオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="57494-183">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="57494-184">-Include</span><span class="sxs-lookup"><span data-stu-id="57494-184">-Include</span></span>

<span data-ttu-id="57494-185">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-185">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="57494-186">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="57494-186">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="57494-187">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-187">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="57494-188">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="57494-188">Wildcard characters are permitted.</span></span> <span data-ttu-id="57494-189">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-189">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="57494-190">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="57494-190">-LiteralPath</span></span>

<span data-ttu-id="57494-191">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-191">Specifies a path to one or more locations.</span></span> <span data-ttu-id="57494-192">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="57494-192">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="57494-193">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="57494-193">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="57494-194">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="57494-194">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="57494-195">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="57494-195">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="57494-196">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57494-196">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="57494-197">-なし Wline</span><span class="sxs-lookup"><span data-stu-id="57494-197">-NoNewline</span></span>

<span data-ttu-id="57494-198">入力オブジェクトの文字列形式が連結され、出力が形成されます。</span><span class="sxs-lookup"><span data-stu-id="57494-198">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="57494-199">出力文字列間にスペースや改行は挿入されません。</span><span class="sxs-lookup"><span data-stu-id="57494-199">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="57494-200">最後の出力文字列の後に改行は追加されません。</span><span class="sxs-lookup"><span data-stu-id="57494-200">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="57494-201">-PassThru</span><span class="sxs-lookup"><span data-stu-id="57494-201">-PassThru</span></span>

<span data-ttu-id="57494-202">コンテンツを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="57494-202">Returns an object that represents the content.</span></span> <span data-ttu-id="57494-203">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="57494-203">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="57494-204">-Path</span><span class="sxs-lookup"><span data-stu-id="57494-204">-Path</span></span>

<span data-ttu-id="57494-205">コンテンツを受信する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-205">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="57494-206">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="57494-206">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="57494-207">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="57494-207">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="57494-208">このパラメーターは Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="57494-208">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="57494-209">コンテンツの代替データストリームを指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-209">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="57494-210">ストリームが存在しない場合は、このコマンドレットによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="57494-210">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="57494-211">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="57494-211">Wildcard characters are not supported.</span></span>

<span data-ttu-id="57494-212">**Stream** は、 **FileSystem** プロバイダーによってに追加される動的パラメーターです `Set-Content` 。</span><span class="sxs-lookup"><span data-stu-id="57494-212">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="57494-213">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="57494-213">This parameter works only in file system drives.</span></span>

<span data-ttu-id="57494-214">コマンドレットを使用して、など `Set-Content` の代替データストリームの内容を作成または更新でき `Zone.Identifier` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-214">You can use the `Set-Content` cmdlet to create or update the content of any alternate data stream, such as `Zone.Identifier`.</span></span> <span data-ttu-id="57494-215">ただし、インターネットからダウンロードされたファイルをブロックするセキュリティチェックを省略する方法としては、この方法をお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="57494-215">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="57494-216">ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-216">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="57494-217">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="57494-217">This parameter was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="57494-218">PowerShell 7.2 の場合、で `Set-Content` は、ファイルだけでなく、ディレクトリから代替データストリームの内容を設定できます。</span><span class="sxs-lookup"><span data-stu-id="57494-218">As of PowerShell 7.2, `Set-Content` can set the content of alternative data streams from directories as well as files.</span></span>

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

### <span data-ttu-id="57494-219">-Value</span><span class="sxs-lookup"><span data-stu-id="57494-219">-Value</span></span>

<span data-ttu-id="57494-220">項目の新しい内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="57494-220">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="57494-221">-Confirm</span><span class="sxs-lookup"><span data-stu-id="57494-221">-Confirm</span></span>

<span data-ttu-id="57494-222">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="57494-222">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="57494-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="57494-223">-WhatIf</span></span>

<span data-ttu-id="57494-224">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="57494-224">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="57494-225">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="57494-225">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="57494-226">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="57494-226">CommonParameters</span></span>

<span data-ttu-id="57494-227">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="57494-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="57494-228">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57494-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="57494-229">入力</span><span class="sxs-lookup"><span data-stu-id="57494-229">INPUTS</span></span>

### <span data-ttu-id="57494-230">System.Object</span><span class="sxs-lookup"><span data-stu-id="57494-230">System.Object</span></span>

<span data-ttu-id="57494-231">パイプを使用して、項目の新しい値を含むオブジェクトをにパイプすることができ `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-231">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="57494-232">出力</span><span class="sxs-lookup"><span data-stu-id="57494-232">OUTPUTS</span></span>

### <span data-ttu-id="57494-233">None または System.String</span><span class="sxs-lookup"><span data-stu-id="57494-233">None or System.String</span></span>

<span data-ttu-id="57494-234">**PassThru** パラメーターを使用すると、によって、 `Set-Content` コンテンツを表す **system.string** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="57494-234">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="57494-235">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="57494-235">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="57494-236">注</span><span class="sxs-lookup"><span data-stu-id="57494-236">NOTES</span></span>

- <span data-ttu-id="57494-237">また、組み込みエイリアスであるを参照することもでき `Set-Content` `sc` ます。</span><span class="sxs-lookup"><span data-stu-id="57494-237">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="57494-238">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57494-238">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="57494-239">`Set-Content` は、文字列処理用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="57494-239">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="57494-240">文字列以外のオブジェクトをにパイプする場合は `Set-Content` 、オブジェクトを書き込む前に文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="57494-240">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="57494-241">オブジェクトをファイルに書き込むには、を使用 `Out-File` します。</span><span class="sxs-lookup"><span data-stu-id="57494-241">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="57494-242">`Set-Content`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="57494-242">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="57494-243">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="57494-243">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="57494-244">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57494-244">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="57494-245">関連リンク</span><span class="sxs-lookup"><span data-stu-id="57494-245">RELATED LINKS</span></span>

[<span data-ttu-id="57494-246">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="57494-246">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="57494-247">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="57494-247">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="57494-248">about_Providers</span><span class="sxs-lookup"><span data-stu-id="57494-248">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="57494-249">Add-Content</span><span class="sxs-lookup"><span data-stu-id="57494-249">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="57494-250">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="57494-250">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="57494-251">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="57494-251">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="57494-252">Get-Content</span><span class="sxs-lookup"><span data-stu-id="57494-252">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="57494-253">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="57494-253">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="57494-254">New-Item</span><span class="sxs-lookup"><span data-stu-id="57494-254">New-Item</span></span>](New-Item.md)
