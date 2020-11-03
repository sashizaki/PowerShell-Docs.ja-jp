---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: e7437505bbe5fbbcfb38e9957f75ac45287d9b26
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "93220040"
---
# <span data-ttu-id="e3b3a-103">Out-File</span><span class="sxs-lookup"><span data-stu-id="e3b3a-103">Out-File</span></span>

## <span data-ttu-id="e3b3a-104">概要</span><span class="sxs-lookup"><span data-stu-id="e3b3a-104">SYNOPSIS</span></span>
<span data-ttu-id="e3b3a-105">ファイルに出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-105">Sends output to a file.</span></span>

## <span data-ttu-id="e3b3a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3b3a-106">SYNTAX</span></span>

### <span data-ttu-id="e3b3a-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="e3b3a-107">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e3b3a-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="e3b3a-108">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e3b3a-109">Description</span><span class="sxs-lookup"><span data-stu-id="e3b3a-109">DESCRIPTION</span></span>

<span data-ttu-id="e3b3a-110">`Out-File`コマンドレットは、出力をファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-110">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="e3b3a-111">ファイルへの書き込みには、PowerShell の書式設定システムを暗黙的に使用します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-111">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="e3b3a-112">このファイルは、ターミナルと同じ表示表現を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-112">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="e3b3a-113">これは、すべての入力オブジェクトが文字列でない限り、プログラムによる処理には適していない可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-113">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="e3b3a-114">出力のパラメーターを指定する必要がある場合は、 `Out-File` リダイレクト演算子 () ではなくを使用し `>` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-114">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="e3b3a-115">リダイレクトの詳細については、「 [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-115">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="e3b3a-116">例</span><span class="sxs-lookup"><span data-stu-id="e3b3a-116">EXAMPLES</span></span>

### <span data-ttu-id="e3b3a-117">例 1: 出力を送信し、ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="e3b3a-117">Example 1: Send output and create a file</span></span>

<span data-ttu-id="e3b3a-118">この例では、ローカルコンピューターのプロセスの一覧をファイルに送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-118">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="e3b3a-119">ファイルが存在しない場合は、 `Out-File` 指定されたパスにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-119">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt
Get-Content -Path .\Process.txt
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     29    22.39      35.40      10.98   42764   9 Application
     53    99.04     113.96       0.00   32664   0 CcmExec
     27    96.62     112.43     113.00   17720   9 Code
```

<span data-ttu-id="e3b3a-120">`Get-Process`コマンドレットは、ローカルコンピューター上で実行されているプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-120">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="e3b3a-121">**プロセス** オブジェクトは、パイプラインを介してコマンドレットに送信され `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-121">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="e3b3a-122">`Out-File`**FilePath** パラメーターを使用して、 **Process.txt** という名前の現在のディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-122">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="e3b3a-123">`Get-Content`このコマンドは、ファイルからコンテンツを取得し、PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-123">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="e3b3a-124">例 2: 既存のファイルが上書きされないようにする</span><span class="sxs-lookup"><span data-stu-id="e3b3a-124">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="e3b3a-125">この例では、既存のファイルが上書きされないようにします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-125">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="e3b3a-126">既定では、は `Out-File` 既存のファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-126">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="e3b3a-127">`Get-Process`コマンドレットは、ローカルコンピューター上で実行されているプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-127">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="e3b3a-128">**プロセス** オブジェクトは、パイプラインを介してコマンドレットに送信され `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-128">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="e3b3a-129">`Out-File`**FilePath** パラメーターを使用し、 **Process.txt** という名前の現在のディレクトリ内のファイルへの書き込みを試みます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-129">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="e3b3a-130">**NoClobber** パラメーターを指定すると、ファイルが上書きされなくなり、ファイルが既に存在することを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-130">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="e3b3a-131">例 3: 出力を ASCII 形式でファイルに送信する</span><span class="sxs-lookup"><span data-stu-id="e3b3a-131">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="e3b3a-132">この例では、特定のエンコードの種類を使用して出力をエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-132">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="e3b3a-133">`Get-Process`コマンドレットは、ローカルコンピューター上で実行されているプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-133">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="e3b3a-134">**プロセス** オブジェクトは変数に格納され `$Procs` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-134">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="e3b3a-135">`Out-File`**FilePath** パラメーターを使用して、 **Process.txt** という名前の現在のディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-135">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="e3b3a-136">**InputObject** パラメーターは、プロセスオブジェクトを `$Procs` **Process.txt** ファイルに渡します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-136">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt**.</span></span> <span data-ttu-id="e3b3a-137">**Encoding** パラメーターは、出力を **ASCII** 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-137">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="e3b3a-138">**Width** パラメーターを指定すると、ファイル内の各行が50文字に制限されるため、一部のデータが切り捨てられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-138">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="e3b3a-139">例 4: プロバイダーを使用し、ファイルに出力を送信する</span><span class="sxs-lookup"><span data-stu-id="e3b3a-139">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="e3b3a-140">この例では、 `Out-File` **ファイルシステム** プロバイダードライブにない場合にコマンドレットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-140">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="e3b3a-141">コマンドレットを使用して、 `Get-PSProvider` ローカルコンピューター上のプロバイダーを表示します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-141">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="e3b3a-142">詳細については、「[about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-142">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

```
PS> Set-Location -Path Alias:

PS> Get-Location

Path
----
Alias:\

PS> Get-ChildItem | Out-File -FilePath C:\TestDir\AliasNames.txt

PS> Get-Content -Path C:\TestDir\AliasNames.txt

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           cat -> Get-Content
```

<span data-ttu-id="e3b3a-143">この `Set-Location` コマンドは **Path** パラメーターを使用して、現在の場所をレジストリプロバイダーに設定し `Alias:` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-143">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="e3b3a-144">コマンドレットにより、 `Get-Location` の完全なパスが表示され `Alias:` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-144">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="e3b3a-145">`Get-ChildItem` オブジェクトをパイプラインからコマンドレットに送信し `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-145">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="e3b3a-146">`Out-File`**FilePath** パラメーターを使用して、出力の完全なパスとファイル名 ( **C:\TestDir\AliasNames.txt** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-146">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt**.</span></span> <span data-ttu-id="e3b3a-147">コマンドレットでは、 `Get-Content` **Path** パラメーターを使用して、ファイルの内容を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-147">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="e3b3a-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3b3a-148">PARAMETERS</span></span>

### <span data-ttu-id="e3b3a-149">-追加</span><span class="sxs-lookup"><span data-stu-id="e3b3a-149">-Append</span></span>

<span data-ttu-id="e3b3a-150">既存のファイルの末尾に出力を追加します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-150">Adds the output to the end of an existing file.</span></span>

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

### <span data-ttu-id="e3b3a-151">-Encoding</span><span class="sxs-lookup"><span data-stu-id="e3b3a-151">-Encoding</span></span>

<span data-ttu-id="e3b3a-152">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-152">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="e3b3a-153">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-153">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="e3b3a-154">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e3b3a-155">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="e3b3a-156">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="e3b3a-157">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="e3b3a-158">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="e3b3a-159">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="e3b3a-160">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="e3b3a-161">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="e3b3a-162">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="e3b3a-163">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="e3b3a-164">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="e3b3a-165">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: 1
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3b3a-166">-FilePath</span><span class="sxs-lookup"><span data-stu-id="e3b3a-166">-FilePath</span></span>

<span data-ttu-id="e3b3a-167">出力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-167">Specifies the path to the output file.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3b3a-168">-Force</span><span class="sxs-lookup"><span data-stu-id="e3b3a-168">-Force</span></span>

<span data-ttu-id="e3b3a-169">読み取り専用の属性をオーバーライドし、既存の読み取り専用ファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-169">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="e3b3a-170">**Force** パラメーターは、セキュリティ制限をオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-170">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="e3b3a-171">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e3b3a-171">-InputObject</span></span>

<span data-ttu-id="e3b3a-172">ファイルに書き込むオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-172">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="e3b3a-173">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-173">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="e3b3a-174">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e3b3a-174">-LiteralPath</span></span>

<span data-ttu-id="e3b3a-175">出力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-175">Specifies the path to the output file.</span></span> <span data-ttu-id="e3b3a-176">**LiteralPath** パラメーターは、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-176">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="e3b3a-177">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-177">Wildcard characters are not accepted.</span></span> <span data-ttu-id="e3b3a-178">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-178">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e3b3a-179">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-179">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="e3b3a-180">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-180">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e3b3a-181">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="e3b3a-181">-NoClobber</span></span>

<span data-ttu-id="e3b3a-182">**NoClobber** を実行すると、既存のファイルが上書きされず、ファイルが既に存在することを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-182">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="e3b3a-183">既定では、指定されたパスにファイルが存在する場合、は `Out-File` 警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-183">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="e3b3a-184">-なし Wline</span><span class="sxs-lookup"><span data-stu-id="e3b3a-184">-NoNewline</span></span>

<span data-ttu-id="e3b3a-185">ファイルに書き込まれる内容が改行文字で終了しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-185">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="e3b3a-186">入力オブジェクトの文字列形式が連結され、出力が形成されます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-186">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="e3b3a-187">出力文字列間にスペースや改行は挿入されません。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-187">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="e3b3a-188">最後の出力文字列の後に改行は追加されません。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-188">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="e3b3a-189">-Width</span><span class="sxs-lookup"><span data-stu-id="e3b3a-189">-Width</span></span>

<span data-ttu-id="e3b3a-190">出力の各行の文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-190">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="e3b3a-191">これを超過する文字は、折り返されることなく切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-191">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="e3b3a-192">このパラメーターを使用しない場合、幅はホストの特性によって決まります。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-192">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="e3b3a-193">PowerShell コンソールの既定値は80文字です。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-193">The default for the PowerShell console is 80 characters.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3b3a-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e3b3a-194">-Confirm</span></span>

<span data-ttu-id="e3b3a-195">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e3b3a-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e3b3a-196">-WhatIf</span></span>

<span data-ttu-id="e3b3a-197">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-197">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e3b3a-198">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e3b3a-199">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3b3a-199">CommonParameters</span></span>

<span data-ttu-id="e3b3a-200">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3b3a-201">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3b3a-202">入力</span><span class="sxs-lookup"><span data-stu-id="e3b3a-202">INPUTS</span></span>

### <span data-ttu-id="e3b3a-203">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="e3b3a-203">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="e3b3a-204">パイプを使用して任意のオブジェクトをにパイプすることができ `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-204">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="e3b3a-205">出力</span><span class="sxs-lookup"><span data-stu-id="e3b3a-205">OUTPUTS</span></span>

### <span data-ttu-id="e3b3a-206">なし</span><span class="sxs-lookup"><span data-stu-id="e3b3a-206">None</span></span>

<span data-ttu-id="e3b3a-207">`Out-File` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-207">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="e3b3a-208">注</span><span class="sxs-lookup"><span data-stu-id="e3b3a-208">NOTES</span></span>

<span data-ttu-id="e3b3a-209">入力オブジェクトは、ターミナルのように自動的に書式設定されますが、コマンドレットを使用して、 `Format-*` 出力の形式をファイルに明示的に制御できます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-209">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="e3b3a-210">たとえば、`Get-Date | Format-List | Out-File out.txt` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-210">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="e3b3a-211">PowerShell コマンドの出力をコマンドレットに送信するには、 `Out-File` パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-211">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="e3b3a-212">または、変数にデータを格納し、 **InputObject** パラメーターを使用してデータをコマンドレットに渡すこともでき `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-212">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="e3b3a-213">`Out-File` データをファイルに保存しますが、パイプラインに出力オブジェクトを生成しません。</span><span class="sxs-lookup"><span data-stu-id="e3b3a-213">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="e3b3a-214">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e3b3a-214">RELATED LINKS</span></span>

[<span data-ttu-id="e3b3a-215">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e3b3a-215">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="e3b3a-216">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="e3b3a-216">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="e3b3a-217">Out-Default</span><span class="sxs-lookup"><span data-stu-id="e3b3a-217">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="e3b3a-218">Out-Host</span><span class="sxs-lookup"><span data-stu-id="e3b3a-218">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="e3b3a-219">Out-Null</span><span class="sxs-lookup"><span data-stu-id="e3b3a-219">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="e3b3a-220">Out-String</span><span class="sxs-lookup"><span data-stu-id="e3b3a-220">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="e3b3a-221">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="e3b3a-221">Tee-Object</span></span>](Tee-Object.md)
