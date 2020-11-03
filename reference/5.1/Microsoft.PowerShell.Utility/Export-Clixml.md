---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8485591165cce0425c85d52fbd31d40614af6249
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214064"
---
# <span data-ttu-id="42469-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="42469-103">Export-Clixml</span></span>

## <span data-ttu-id="42469-104">概要</span><span class="sxs-lookup"><span data-stu-id="42469-104">SYNOPSIS</span></span>
<span data-ttu-id="42469-105">1 つまたは複数のオブジェクトの XML ベースの表現を作成し、ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="42469-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="42469-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="42469-106">SYNTAX</span></span>

### <span data-ttu-id="42469-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="42469-107">ByPath (Default)</span></span>

```
Export-Clixml [-Path] <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="42469-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="42469-108">ByLiteralPath</span></span>

```
Export-Clixml -LiteralPath <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="42469-109">Description</span><span class="sxs-lookup"><span data-stu-id="42469-109">DESCRIPTION</span></span>

<span data-ttu-id="42469-110">コマンドレットでは、 `Export-Clixml` 共通言語基盤 (CLI) の XML ベースの表現をオブジェクトまたはオブジェクトで作成し、ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="42469-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="42469-111">その後、コマンドレットを使用して、 `Import-Clixml` そのファイルの内容に基づいて保存されたオブジェクトを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="42469-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="42469-112">CLI の詳細については、「 [言語に依存](/dotnet/standard/language-independence)しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42469-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="42469-113">このコマンドレットはに似ていますが、では `ConvertTo-Xml` 、結果の XML がファイルに格納される点が異なり `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="42469-114">`ConvertTo-XML` は XML を返します。そのため、PowerShell で処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="42469-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="42469-115">Windows コンピューターでのの重要な使用方法 `Export-Clixml` は、資格情報をエクスポートし、文字列を安全に XML としてセキュリティで保護することです。</span><span class="sxs-lookup"><span data-stu-id="42469-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="42469-116">例については、例3を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42469-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="42469-117">例</span><span class="sxs-lookup"><span data-stu-id="42469-117">EXAMPLES</span></span>

### <span data-ttu-id="42469-118">例 1: XML ファイルに文字列をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="42469-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="42469-119">この例では、現在のディレクトリに格納されている XML ファイルを作成します。 **これは** 、という文字列の表現です。</span><span class="sxs-lookup"><span data-stu-id="42469-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test** .</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="42469-120">**この** 文字列は、パイプラインによって送信されます。</span><span class="sxs-lookup"><span data-stu-id="42469-120">The string **This is a test** is sent down the pipeline.</span></span> <span data-ttu-id="42469-121">`Export-Clixml`**Path** パラメーターを使用して、現在のディレクトリにという名前の XML ファイルを作成し `sample.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="42469-122">例 2: オブジェクトを XML ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="42469-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="42469-123">この例では、オブジェクトを XML ファイルにエクスポートし、エクスポートしたファイルから XML をインポートしてオブジェクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42469-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="42469-124">コマンドレットでは、 `Get-Acl` ファイルのセキュリティ記述子を取得し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="42469-125">オブジェクトをパイプラインの下に送信して、セキュリティ記述子をに渡し `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="42469-126">オブジェクトの XML ベースの表現は、という名前のファイルに格納され `FileACL.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="42469-127">`Import-Clixml`コマンドレットは、ファイル内の XML からオブジェクトを作成し `FileACL.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="42469-128">次に、変数にオブジェクトを保存し `$fileacl` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="42469-129">例 3: エクスポートされた資格情報オブジェクトを暗号化する</span><span class="sxs-lookup"><span data-stu-id="42469-129">Example 3: Encrypt an exported credential object</span></span>

<span data-ttu-id="42469-130">この例では、コマンドレットを実行して変数に格納した資格情報を指定した場合、 `$Credential` `Get-Credential` コマンドレットを実行して `Export-Clixml` 資格情報をディスクに保存できます。</span><span class="sxs-lookup"><span data-stu-id="42469-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42469-131">`Export-Clixml` 暗号化された資格情報のみを Windows でエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="42469-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="42469-132">MacOS や Linux などの Windows 以外のオペレーティングシステムでは、資格情報はプレーンテキストでエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="42469-132">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="42469-133">コマンドレットでは、 `Export-Clixml` Windows [データ保護 API](/previous-versions/windows/apps/hh464970(v=win.10))を使用して資格情報オブジェクトを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="42469-133">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="42469-134">暗号化により、そのコンピューター上のユーザーアカウントのみが資格情報オブジェクトの内容を復号化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="42469-134">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span> <span data-ttu-id="42469-135">エクスポートされたファイルは、 `CLIXML` 別のコンピューターまたは別のユーザーが使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="42469-135">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="42469-136">この例では、資格情報が格納されているファイルがによって表され `TestScript.ps1.credential` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-136">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="42469-137">**Testscript** を、資格情報の読み込みに使用するスクリプトの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="42469-137">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="42469-138">資格情報オブジェクトをパイプラインの下に送信 `Export-Clixml` し、 `$Credxmlpath` 最初のコマンドで指定したパスに保存します。</span><span class="sxs-lookup"><span data-stu-id="42469-138">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="42469-139">スクリプトに資格情報を自動的にインポートするには、最後の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="42469-139">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="42469-140">を実行し `Import-Clixml` て、セキュリティで保護された資格情報オブジェクトをスクリプトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="42469-140">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="42469-141">このインポートにより、スクリプトにプレーンテキストのパスワードが公開されるリスクがなくなります。</span><span class="sxs-lookup"><span data-stu-id="42469-141">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="42469-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="42469-142">PARAMETERS</span></span>

### <span data-ttu-id="42469-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="42469-143">-Confirm</span></span>

<span data-ttu-id="42469-144">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="42469-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="42469-145">-深さ</span><span class="sxs-lookup"><span data-stu-id="42469-145">-Depth</span></span>

<span data-ttu-id="42469-146">XML 表現に含める子オブジェクトのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="42469-146">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="42469-147">既定値は `2` です。</span><span class="sxs-lookup"><span data-stu-id="42469-147">The default value is `2`.</span></span>

<span data-ttu-id="42469-148">ファイルのオブジェクトの種類に対して既定値をオーバーライドでき `Types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-148">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="42469-149">詳細については、「 [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42469-149">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42469-150">-Encoding</span><span class="sxs-lookup"><span data-stu-id="42469-150">-Encoding</span></span>

<span data-ttu-id="42469-151">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="42469-151">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="42469-152">既定値は **Unicode** です。</span><span class="sxs-lookup"><span data-stu-id="42469-152">The default value is **Unicode** .</span></span>

<span data-ttu-id="42469-153">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="42469-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="42469-154">`ASCII` ASCII (7 ビット) 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="42469-154">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="42469-155">`BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="42469-155">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="42469-156">`Default` は、システムのアクティブなコードページ (通常は ANSI) に対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="42469-156">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="42469-157">`OEM` は、システムの現在の OEM コードページに対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="42469-157">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="42469-158">`Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="42469-158">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="42469-159">`UTF7` UTF-7 を使用します。</span><span class="sxs-lookup"><span data-stu-id="42469-159">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="42469-160">`UTF8` UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="42469-160">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="42469-161">`UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="42469-161">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42469-162">-Force</span><span class="sxs-lookup"><span data-stu-id="42469-162">-Force</span></span>

<span data-ttu-id="42469-163">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="42469-163">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="42469-164">必要に応じて、このコマンドレットは出力ファイルの読み取り専用の属性をクリアします。</span><span class="sxs-lookup"><span data-stu-id="42469-164">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="42469-165">コマンドが完了すると、このコマンドレットが読み取り専用の属性をリセットしようとします。</span><span class="sxs-lookup"><span data-stu-id="42469-165">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="42469-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="42469-166">-InputObject</span></span>

<span data-ttu-id="42469-167">変換するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="42469-167">Specifies the object to be converted.</span></span> <span data-ttu-id="42469-168">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="42469-168">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="42469-169">パイプを使用してオブジェクトをにパイプ処理することもでき `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-169">You can also pipe objects to `Export-Clixml`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="42469-170">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="42469-170">-LiteralPath</span></span>

<span data-ttu-id="42469-171">オブジェクトの XML 表現が格納されるファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="42469-171">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="42469-172">**Path** と異なり、 **LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="42469-172">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="42469-173">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="42469-173">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="42469-174">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="42469-174">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="42469-175">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="42469-175">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42469-176">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="42469-176">-NoClobber</span></span>

<span data-ttu-id="42469-177">コマンドレットが既存のファイルの内容を上書きしないことを示します。</span><span class="sxs-lookup"><span data-stu-id="42469-177">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="42469-178">既定では、指定されたパスにファイルが存在する場合、は `Export-Clixml` 警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="42469-178">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42469-179">-Path</span><span class="sxs-lookup"><span data-stu-id="42469-179">-Path</span></span>

<span data-ttu-id="42469-180">オブジェクトの XML 表現が格納されるファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="42469-180">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

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

### <span data-ttu-id="42469-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="42469-181">-WhatIf</span></span>

<span data-ttu-id="42469-182">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="42469-182">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="42469-183">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="42469-183">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="42469-184">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="42469-184">CommonParameters</span></span>

<span data-ttu-id="42469-185">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="42469-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="42469-186">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42469-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="42469-187">入力</span><span class="sxs-lookup"><span data-stu-id="42469-187">INPUTS</span></span>

### <span data-ttu-id="42469-188">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="42469-188">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="42469-189">任意のオブジェクトをにパイプラインでき `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="42469-189">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="42469-190">出力</span><span class="sxs-lookup"><span data-stu-id="42469-190">OUTPUTS</span></span>

### <span data-ttu-id="42469-191">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="42469-191">System.IO.FileInfo</span></span>

<span data-ttu-id="42469-192">`Export-Clixml` XML を含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="42469-192">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="42469-193">注</span><span class="sxs-lookup"><span data-stu-id="42469-193">NOTES</span></span>

## <span data-ttu-id="42469-194">関連リンク</span><span class="sxs-lookup"><span data-stu-id="42469-194">RELATED LINKS</span></span>

[<span data-ttu-id="42469-195">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="42469-195">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="42469-196">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="42469-196">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="42469-197">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="42469-197">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="42469-198">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="42469-198">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="42469-199">Join-Path</span><span class="sxs-lookup"><span data-stu-id="42469-199">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="42469-200">ディスクへの資格情報の安全な保存</span><span class="sxs-lookup"><span data-stu-id="42469-200">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="42469-201">PowerShell を使用してレガシシステムに資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="42469-201">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[<span data-ttu-id="42469-202">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="42469-202">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
