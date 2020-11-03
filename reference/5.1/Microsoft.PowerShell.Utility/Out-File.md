---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: 71602cb0621c835257f556a0a9db15bd754a3aee
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "93220080"
---
# <span data-ttu-id="cba92-103">Out-File</span><span class="sxs-lookup"><span data-stu-id="cba92-103">Out-File</span></span>

## <span data-ttu-id="cba92-104">概要</span><span class="sxs-lookup"><span data-stu-id="cba92-104">SYNOPSIS</span></span>
<span data-ttu-id="cba92-105">ファイルに出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="cba92-105">Sends output to a file.</span></span>

## <span data-ttu-id="cba92-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cba92-106">SYNTAX</span></span>

### <span data-ttu-id="cba92-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="cba92-107">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <string>] [-Append] [-Force] [-NoClobber] [-Width <int>]
 [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cba92-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="cba92-108">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <string>] -LiteralPath <string> [-Append] [-Force] [-NoClobber] [-Width <int>]
 [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cba92-109">Description</span><span class="sxs-lookup"><span data-stu-id="cba92-109">DESCRIPTION</span></span>

<span data-ttu-id="cba92-110">`Out-File`コマンドレットは、出力をファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="cba92-110">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="cba92-111">ファイルへの書き込みには、PowerShell の書式設定システムを暗黙的に使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-111">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="cba92-112">このファイルは、ターミナルと同じ表示表現を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cba92-112">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="cba92-113">これは、すべての入力オブジェクトが文字列でない限り、プログラムによる処理には適していない可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="cba92-113">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="cba92-114">出力のパラメーターを指定する必要がある場合は、 `Out-File` リダイレクト演算子 () ではなくを使用し `>` ます。</span><span class="sxs-lookup"><span data-stu-id="cba92-114">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="cba92-115">リダイレクトの詳細については、「 [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba92-115">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="cba92-116">例</span><span class="sxs-lookup"><span data-stu-id="cba92-116">EXAMPLES</span></span>

### <span data-ttu-id="cba92-117">例 1: 出力を送信し、ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cba92-117">Example 1: Send output and create a file</span></span>

<span data-ttu-id="cba92-118">この例では、ローカルコンピューターのプロセスの一覧をファイルに送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cba92-118">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="cba92-119">ファイルが存在しない場合は、 `Out-File` 指定されたパスにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cba92-119">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

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

<span data-ttu-id="cba92-120">`Get-Process`コマンドレットは、ローカルコンピューター上で実行されているプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="cba92-120">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="cba92-121">**プロセス** オブジェクトは、パイプラインを介してコマンドレットに送信され `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="cba92-121">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="cba92-122">`Out-File`**FilePath** パラメーターを使用して、 **Process.txt** という名前の現在のディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cba92-122">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="cba92-123">`Get-Content`このコマンドは、ファイルからコンテンツを取得し、PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="cba92-123">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="cba92-124">例 2: 既存のファイルが上書きされないようにする</span><span class="sxs-lookup"><span data-stu-id="cba92-124">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="cba92-125">この例では、既存のファイルが上書きされないようにします。</span><span class="sxs-lookup"><span data-stu-id="cba92-125">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="cba92-126">既定では、は `Out-File` 既存のファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="cba92-126">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="cba92-127">`Get-Process`コマンドレットは、ローカルコンピューター上で実行されているプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="cba92-127">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="cba92-128">**プロセス** オブジェクトは、パイプラインを介してコマンドレットに送信され `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="cba92-128">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="cba92-129">`Out-File`**FilePath** パラメーターを使用し、 **Process.txt** という名前の現在のディレクトリ内のファイルへの書き込みを試みます。</span><span class="sxs-lookup"><span data-stu-id="cba92-129">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="cba92-130">**NoClobber** パラメーターを指定すると、ファイルが上書きされなくなり、ファイルが既に存在することを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cba92-130">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="cba92-131">例 3: 出力を ASCII 形式でファイルに送信する</span><span class="sxs-lookup"><span data-stu-id="cba92-131">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="cba92-132">この例では、特定のエンコードの種類を使用して出力をエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cba92-132">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="cba92-133">`Get-Process`コマンドレットは、ローカルコンピューター上で実行されているプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="cba92-133">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="cba92-134">**プロセス** オブジェクトは変数に格納され `$Procs` ます。</span><span class="sxs-lookup"><span data-stu-id="cba92-134">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="cba92-135">`Out-File`**FilePath** パラメーターを使用して、 **Process.txt** という名前の現在のディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cba92-135">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="cba92-136">**InputObject** パラメーターは、プロセスオブジェクトを `$Procs` **Process.txt** ファイルに渡します。</span><span class="sxs-lookup"><span data-stu-id="cba92-136">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt**.</span></span> <span data-ttu-id="cba92-137">**Encoding** パラメーターは、出力を **ASCII** 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="cba92-137">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="cba92-138">**Width** パラメーターを指定すると、ファイル内の各行が50文字に制限されるため、一部のデータが切り捨てられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cba92-138">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="cba92-139">例 4: プロバイダーを使用し、ファイルに出力を送信する</span><span class="sxs-lookup"><span data-stu-id="cba92-139">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="cba92-140">この例では、 `Out-File` **ファイルシステム** プロバイダードライブにない場合にコマンドレットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cba92-140">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="cba92-141">コマンドレットを使用して、 `Get-PSProvider` ローカルコンピューター上のプロバイダーを表示します。</span><span class="sxs-lookup"><span data-stu-id="cba92-141">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="cba92-142">詳細については、「[about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba92-142">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

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

<span data-ttu-id="cba92-143">この `Set-Location` コマンドは **Path** パラメーターを使用して、現在の場所をレジストリプロバイダーに設定し `Alias:` ます。</span><span class="sxs-lookup"><span data-stu-id="cba92-143">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="cba92-144">コマンドレットにより、 `Get-Location` の完全なパスが表示され `Alias:` ます。</span><span class="sxs-lookup"><span data-stu-id="cba92-144">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="cba92-145">`Get-ChildItem` オブジェクトをパイプラインからコマンドレットに送信し `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="cba92-145">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="cba92-146">`Out-File`**FilePath** パラメーターを使用して、出力の完全なパスとファイル名 ( **C:\TestDir\AliasNames.txt** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="cba92-146">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt**.</span></span> <span data-ttu-id="cba92-147">コマンドレットでは、 `Get-Content` **Path** パラメーターを使用して、ファイルの内容を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="cba92-147">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="cba92-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cba92-148">PARAMETERS</span></span>

### <span data-ttu-id="cba92-149">-追加</span><span class="sxs-lookup"><span data-stu-id="cba92-149">-Append</span></span>

<span data-ttu-id="cba92-150">既存のファイルの末尾に出力を追加します。</span><span class="sxs-lookup"><span data-stu-id="cba92-150">Adds the output to the end of an existing file.</span></span> <span data-ttu-id="cba92-151">**エンコード** が指定されていない場合、コマンドレットは既定のエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-151">If no **Encoding** is specified, the cmdlet uses the default encoding.</span></span> <span data-ttu-id="cba92-152">このエンコードは、ターゲットファイルのエンコーディングと一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cba92-152">That encoding may not match the encoding of the target file.</span></span> <span data-ttu-id="cba92-153">これは、リダイレクト演算子 () と同じ動作です `>>` 。</span><span class="sxs-lookup"><span data-stu-id="cba92-153">This is the same behavior as the redirection operator (`>>`).</span></span>

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

### <span data-ttu-id="cba92-154">-Encoding</span><span class="sxs-lookup"><span data-stu-id="cba92-154">-Encoding</span></span>

<span data-ttu-id="cba92-155">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="cba92-155">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="cba92-156">既定値は `unicode` です。</span><span class="sxs-lookup"><span data-stu-id="cba92-156">The default value is `unicode`.</span></span>

<span data-ttu-id="cba92-157">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cba92-157">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="cba92-158">`ascii` ASCII (7 ビット) 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-158">`ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="cba92-159">`bigendianunicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-159">`bigendianunicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="cba92-160">`default` は、システムのアクティブなコードページ (通常は ANSI) に対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-160">`default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="cba92-161">`oem` は、システムの現在の OEM コードページに対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-161">`oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="cba92-162">`string``unicode` と同じです。</span><span class="sxs-lookup"><span data-stu-id="cba92-162">`string` Same as `unicode`.</span></span>
- <span data-ttu-id="cba92-163">`unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-163">`unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="cba92-164">`unknown``unicode` と同じです。</span><span class="sxs-lookup"><span data-stu-id="cba92-164">`unknown` Same as `unicode`.</span></span>
- <span data-ttu-id="cba92-165">`utf7` UTF-7 を使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-165">`utf7` Uses UTF-7.</span></span>
- <span data-ttu-id="cba92-166">`utf8` UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-166">`utf8` Uses UTF-8.</span></span>
- <span data-ttu-id="cba92-167">`utf32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-167">`utf32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: 1
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cba92-168">-FilePath</span><span class="sxs-lookup"><span data-stu-id="cba92-168">-FilePath</span></span>

<span data-ttu-id="cba92-169">出力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cba92-169">Specifies the path to the output file.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cba92-170">-Force</span><span class="sxs-lookup"><span data-stu-id="cba92-170">-Force</span></span>

<span data-ttu-id="cba92-171">読み取り専用の属性をオーバーライドし、既存の読み取り専用ファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="cba92-171">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="cba92-172">**Force** パラメーターは、セキュリティ制限をオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="cba92-172">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="cba92-173">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cba92-173">-InputObject</span></span>

<span data-ttu-id="cba92-174">ファイルに書き込むオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cba92-174">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="cba92-175">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="cba92-175">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="cba92-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cba92-176">-LiteralPath</span></span>

<span data-ttu-id="cba92-177">出力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cba92-177">Specifies the path to the output file.</span></span> <span data-ttu-id="cba92-178">**LiteralPath** パラメーターは、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cba92-178">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="cba92-179">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="cba92-179">Wildcard characters are not accepted.</span></span> <span data-ttu-id="cba92-180">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="cba92-180">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="cba92-181">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="cba92-181">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="cba92-182">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba92-182">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cba92-183">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="cba92-183">-NoClobber</span></span>

<span data-ttu-id="cba92-184">**NoClobber** を実行すると、既存のファイルが上書きされず、ファイルが既に存在することを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cba92-184">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="cba92-185">既定では、指定されたパスにファイルが存在する場合、は `Out-File` 警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="cba92-185">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="cba92-186">-なし Wline</span><span class="sxs-lookup"><span data-stu-id="cba92-186">-NoNewline</span></span>

<span data-ttu-id="cba92-187">ファイルに書き込まれる内容が改行文字で終了しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="cba92-187">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="cba92-188">入力オブジェクトの文字列形式が連結され、出力が形成されます。</span><span class="sxs-lookup"><span data-stu-id="cba92-188">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="cba92-189">出力文字列間にスペースや改行は挿入されません。</span><span class="sxs-lookup"><span data-stu-id="cba92-189">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="cba92-190">最後の出力文字列の後に改行は追加されません。</span><span class="sxs-lookup"><span data-stu-id="cba92-190">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="cba92-191">-Width</span><span class="sxs-lookup"><span data-stu-id="cba92-191">-Width</span></span>

<span data-ttu-id="cba92-192">出力の各行の文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cba92-192">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="cba92-193">これを超過する文字は、折り返されることなく切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="cba92-193">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="cba92-194">このパラメーターを使用しない場合、幅はホストの特性によって決まります。</span><span class="sxs-lookup"><span data-stu-id="cba92-194">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="cba92-195">PowerShell コンソールの既定値は80文字です。</span><span class="sxs-lookup"><span data-stu-id="cba92-195">The default for the PowerShell console is 80 characters.</span></span>

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

### <span data-ttu-id="cba92-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cba92-196">-Confirm</span></span>

<span data-ttu-id="cba92-197">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cba92-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cba92-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cba92-198">-WhatIf</span></span>

<span data-ttu-id="cba92-199">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="cba92-199">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="cba92-200">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cba92-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cba92-201">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cba92-201">CommonParameters</span></span>

<span data-ttu-id="cba92-202">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cba92-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cba92-203">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba92-203">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cba92-204">入力</span><span class="sxs-lookup"><span data-stu-id="cba92-204">INPUTS</span></span>

### <span data-ttu-id="cba92-205">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="cba92-205">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="cba92-206">パイプを使用して任意のオブジェクトをにパイプすることができ `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="cba92-206">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="cba92-207">出力</span><span class="sxs-lookup"><span data-stu-id="cba92-207">OUTPUTS</span></span>

### <span data-ttu-id="cba92-208">なし</span><span class="sxs-lookup"><span data-stu-id="cba92-208">None</span></span>

<span data-ttu-id="cba92-209">`Out-File` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="cba92-209">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="cba92-210">注</span><span class="sxs-lookup"><span data-stu-id="cba92-210">NOTES</span></span>

<span data-ttu-id="cba92-211">入力オブジェクトは、ターミナルのように自動的に書式設定されますが、コマンドレットを使用して、 `Format-*` 出力の形式をファイルに明示的に制御できます。</span><span class="sxs-lookup"><span data-stu-id="cba92-211">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="cba92-212">たとえば、`Get-Date | Format-List | Out-File out.txt` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="cba92-212">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="cba92-213">PowerShell コマンドの出力をコマンドレットに送信するには、 `Out-File` パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="cba92-213">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="cba92-214">または、変数にデータを格納し、 **InputObject** パラメーターを使用してデータをコマンドレットに渡すこともでき `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="cba92-214">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="cba92-215">`Out-File` データをファイルに保存しますが、パイプラインに出力オブジェクトを生成しません。</span><span class="sxs-lookup"><span data-stu-id="cba92-215">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="cba92-216">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cba92-216">RELATED LINKS</span></span>

[<span data-ttu-id="cba92-217">about_Providers</span><span class="sxs-lookup"><span data-stu-id="cba92-217">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="cba92-218">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="cba92-218">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="cba92-219">Out-Default</span><span class="sxs-lookup"><span data-stu-id="cba92-219">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="cba92-220">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="cba92-220">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="cba92-221">Out-Host</span><span class="sxs-lookup"><span data-stu-id="cba92-221">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="cba92-222">Out-Null</span><span class="sxs-lookup"><span data-stu-id="cba92-222">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="cba92-223">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="cba92-223">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="cba92-224">Out-String</span><span class="sxs-lookup"><span data-stu-id="cba92-224">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="cba92-225">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="cba92-225">Tee-Object</span></span>](Tee-Object.md)
