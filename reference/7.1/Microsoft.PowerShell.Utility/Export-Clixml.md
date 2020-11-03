---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8e1557bca62ade784bd5b4ed5cb170bbf079b423
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "93219675"
---
# <span data-ttu-id="e405c-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="e405c-103">Export-Clixml</span></span>

## <span data-ttu-id="e405c-104">概要</span><span class="sxs-lookup"><span data-stu-id="e405c-104">SYNOPSIS</span></span>
<span data-ttu-id="e405c-105">1 つまたは複数のオブジェクトの XML ベースの表現を作成し、ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="e405c-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="e405c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e405c-106">SYNTAX</span></span>

### <span data-ttu-id="e405c-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="e405c-107">ByPath (Default)</span></span>

```
Export-Clixml [-Depth <Int32>] [-Path] <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e405c-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="e405c-108">ByLiteralPath</span></span>

```
Export-Clixml [-Depth <Int32>] -LiteralPath <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e405c-109">Description</span><span class="sxs-lookup"><span data-stu-id="e405c-109">DESCRIPTION</span></span>

<span data-ttu-id="e405c-110">コマンドレットでは、 `Export-Clixml` 共通言語基盤 (CLI) の XML ベースの表現をオブジェクトまたはオブジェクトで作成し、ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="e405c-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="e405c-111">その後、コマンドレットを使用して、 `Import-Clixml` そのファイルの内容に基づいて保存されたオブジェクトを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="e405c-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="e405c-112">CLI の詳細については、「 [言語に依存](/dotnet/standard/language-independence)しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e405c-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="e405c-113">このコマンドレットはに似ていますが、では `ConvertTo-Xml` 、結果の XML がファイルに格納される点が異なり `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="e405c-114">`ConvertTo-XML` は XML を返します。そのため、PowerShell で処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="e405c-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="e405c-115">Windows コンピューターでのの重要な使用方法 `Export-Clixml` は、資格情報をエクスポートし、文字列を安全に XML としてセキュリティで保護することです。</span><span class="sxs-lookup"><span data-stu-id="e405c-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="e405c-116">例については、例3を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e405c-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="e405c-117">例</span><span class="sxs-lookup"><span data-stu-id="e405c-117">EXAMPLES</span></span>

### <span data-ttu-id="e405c-118">例 1: XML ファイルに文字列をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e405c-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="e405c-119">この例では、現在のディレクトリに格納されている XML ファイルを作成します。 **これは** 、という文字列の表現です。</span><span class="sxs-lookup"><span data-stu-id="e405c-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test**.</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="e405c-120">文字列 `This is a test` はパイプラインで送信されます。</span><span class="sxs-lookup"><span data-stu-id="e405c-120">The string `This is a test` is sent down the pipeline.</span></span> <span data-ttu-id="e405c-121">`Export-Clixml`**Path** パラメーターを使用して、現在のディレクトリにという名前の XML ファイルを作成し `sample.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="e405c-122">例 2: オブジェクトを XML ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e405c-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="e405c-123">この例では、オブジェクトを XML ファイルにエクスポートし、エクスポートしたファイルから XML をインポートしてオブジェクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e405c-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="e405c-124">コマンドレットでは、 `Get-Acl` ファイルのセキュリティ記述子を取得し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="e405c-125">オブジェクトをパイプラインの下に送信して、セキュリティ記述子をに渡し `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="e405c-126">オブジェクトの XML ベースの表現は、という名前のファイルに格納され `FileACL.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="e405c-127">`Import-Clixml`コマンドレットは、ファイル内の XML からオブジェクトを作成し `FileACL.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="e405c-128">次に、変数にオブジェクトを保存し `$fileacl` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="e405c-129">例 3: Windows でエクスポートされた資格情報オブジェクトを暗号化する</span><span class="sxs-lookup"><span data-stu-id="e405c-129">Example 3: Encrypt an exported credential object on Windows</span></span>

<span data-ttu-id="e405c-130">この例では、コマンドレットを実行して変数に格納した資格情報を指定した場合、 `$Credential` `Get-Credential` コマンドレットを実行して `Export-Clixml` 資格情報をディスクに保存できます。</span><span class="sxs-lookup"><span data-stu-id="e405c-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e405c-131">`Export-Clixml` 暗号化された資格情報のみを Windows でエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e405c-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="e405c-132">MacOS や Linux などの Windows 以外のオペレーティングシステムでは、資格情報は Unicode 文字配列として格納されたプレーンテキストとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e405c-132">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="e405c-133">これにより、一部の難読化が可能になりますが、暗号化は提供されません。</span><span class="sxs-lookup"><span data-stu-id="e405c-133">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="e405c-134">コマンドレットでは、 `Export-Clixml` Windows [データ保護 API](/previous-versions/windows/apps/hh464970(v=win.10))を使用して資格情報オブジェクトを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="e405c-134">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span> <span data-ttu-id="e405c-135">暗号化により、そのコンピューター上のユーザーアカウントのみが資格情報オブジェクトの内容を復号化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e405c-135">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span>
<span data-ttu-id="e405c-136">エクスポートされたファイルは、 `CLIXML` 別のコンピューターまたは別のユーザーが使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e405c-136">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="e405c-137">この例では、資格情報が格納されているファイルがによって表され `TestScript.ps1.credential` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-137">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="e405c-138">**Testscript** を、資格情報の読み込みに使用するスクリプトの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e405c-138">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="e405c-139">資格情報オブジェクトをパイプラインの下に送信 `Export-Clixml` し、 `$Credxmlpath` 最初のコマンドで指定したパスに保存します。</span><span class="sxs-lookup"><span data-stu-id="e405c-139">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="e405c-140">スクリプトに資格情報を自動的にインポートするには、最後の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e405c-140">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="e405c-141">を実行し `Import-Clixml` て、セキュリティで保護された資格情報オブジェクトをスクリプトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="e405c-141">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="e405c-142">このインポートにより、スクリプトにプレーンテキストのパスワードが公開されるリスクがなくなります。</span><span class="sxs-lookup"><span data-stu-id="e405c-142">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

### <span data-ttu-id="e405c-143">例 4: Linux または macOS で資格情報オブジェクトをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e405c-143">Example 4: Exporting a credential object on Linux or macOS</span></span>

<span data-ttu-id="e405c-144">この例では、 **PSCredential** `$Credential` コマンドレットを使用して、変数に PSCredential を作成し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-144">In this example, we create a **PSCredential** in the `$Credential` variable using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="e405c-145">次 `Export-Clixml` に、を使用して、資格情報をディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="e405c-145">Then we use `Export-Clixml` to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e405c-146">`Export-Clixml` 暗号化された資格情報のみを Windows でエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e405c-146">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="e405c-147">MacOS や Linux などの Windows 以外のオペレーティングシステムでは、資格情報は Unicode 文字配列として格納されたプレーンテキストとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e405c-147">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="e405c-148">これにより、一部の難読化が可能になりますが、暗号化は提供されません。</span><span class="sxs-lookup"><span data-stu-id="e405c-148">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
PS> $Credential = Get-Credential

PowerShell credential request
Enter your credentials.
User: User1
Password for user User1: ********

PS> $Credential | Export-Clixml ./cred2.xml
PS> Get-Content ./cred2.xml

...
    <Props>
      <S N="UserName">User1</S>
      <SS N="Password">700061007300730077006f0072006400</SS>
    </Props>
...

PS> 'password' | Format-Hex -Encoding unicode

   Label: String (System.String) <52D60C91>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 70 00 61 00 73 00 73 00 77 00 6F 00 72 00 64 00 p a s s w o r d
```

<span data-ttu-id="e405c-149">この例のの出力は、 `Get-Content` XML ファイル内の資格情報に焦点を合わせて切り捨てられています。</span><span class="sxs-lookup"><span data-stu-id="e405c-149">The output of `Get-Content` in this example has been truncate to focus on the credential information in the XML file.</span></span> <span data-ttu-id="e405c-150">パスワードのプレーンテキスト値は、によって証明される Unicode 文字配列として XML ファイルに格納されることに注意して `Format-Hex` ください。</span><span class="sxs-lookup"><span data-stu-id="e405c-150">Note that the plain text value of the password is stored in the XML file as a Unicode character array as proven by `Format-Hex`.</span></span> <span data-ttu-id="e405c-151">そのため、値はエンコードされますが、暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="e405c-151">So the value is encoded but not encrypted.</span></span>

## <span data-ttu-id="e405c-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e405c-152">PARAMETERS</span></span>

### <span data-ttu-id="e405c-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e405c-153">-Confirm</span></span>

<span data-ttu-id="e405c-154">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e405c-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e405c-155">-深さ</span><span class="sxs-lookup"><span data-stu-id="e405c-155">-Depth</span></span>

<span data-ttu-id="e405c-156">XML 表現に含める子オブジェクトのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="e405c-156">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="e405c-157">既定値は `2` です。</span><span class="sxs-lookup"><span data-stu-id="e405c-157">The default value is `2`.</span></span>

<span data-ttu-id="e405c-158">ファイルのオブジェクトの種類に対して既定値をオーバーライドでき `Types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-158">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="e405c-159">詳細については、「 [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e405c-159">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

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

### <span data-ttu-id="e405c-160">-Encoding</span><span class="sxs-lookup"><span data-stu-id="e405c-160">-Encoding</span></span>

<span data-ttu-id="e405c-161">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e405c-161">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="e405c-162">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="e405c-162">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="e405c-163">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e405c-163">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e405c-164">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="e405c-164">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="e405c-165">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e405c-165">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="e405c-166">`bigendianutf32`: ビッグエンディアンのバイト順を使用して、32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e405c-166">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="e405c-167">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e405c-167">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="e405c-168">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e405c-168">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="e405c-169">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e405c-169">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="e405c-170">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e405c-170">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="e405c-171">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e405c-171">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="e405c-172">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e405c-172">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="e405c-173">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e405c-173">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="e405c-174">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-174">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="e405c-175">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e405c-175">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="e405c-176">**Utf-7** \* の使用は推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e405c-176">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="e405c-177">PowerShell 7.1 では、Encoding パラメーターにを指定すると、警告が書き込まれ `utf7` ます。 **Encoding**</span><span class="sxs-lookup"><span data-stu-id="e405c-177">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

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

### <span data-ttu-id="e405c-178">-Force</span><span class="sxs-lookup"><span data-stu-id="e405c-178">-Force</span></span>

<span data-ttu-id="e405c-179">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e405c-179">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="e405c-180">必要に応じて、このコマンドレットは出力ファイルの読み取り専用の属性をクリアします。</span><span class="sxs-lookup"><span data-stu-id="e405c-180">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="e405c-181">コマンドが完了すると、このコマンドレットが読み取り専用の属性をリセットしようとします。</span><span class="sxs-lookup"><span data-stu-id="e405c-181">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="e405c-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e405c-182">-InputObject</span></span>

<span data-ttu-id="e405c-183">変換するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e405c-183">Specifies the object to be converted.</span></span> <span data-ttu-id="e405c-184">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="e405c-184">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="e405c-185">パイプを使用してオブジェクトをにパイプ処理することもでき `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-185">You can also pipe objects to `Export-Clixml`.</span></span>

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

### <span data-ttu-id="e405c-186">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e405c-186">-LiteralPath</span></span>

<span data-ttu-id="e405c-187">オブジェクトの XML 表現が格納されるファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e405c-187">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="e405c-188">**Path** と異なり、 **LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e405c-188">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="e405c-189">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="e405c-189">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e405c-190">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="e405c-190">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e405c-191">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="e405c-191">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e405c-192">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="e405c-192">-NoClobber</span></span>

<span data-ttu-id="e405c-193">コマンドレットが既存のファイルの内容を上書きしないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e405c-193">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="e405c-194">既定では、指定されたパスにファイルが存在する場合、は `Export-Clixml` 警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="e405c-194">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="e405c-195">-Path</span><span class="sxs-lookup"><span data-stu-id="e405c-195">-Path</span></span>

<span data-ttu-id="e405c-196">オブジェクトの XML 表現が格納されるファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e405c-196">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

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

### <span data-ttu-id="e405c-197">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e405c-197">-WhatIf</span></span>

<span data-ttu-id="e405c-198">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="e405c-198">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e405c-199">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e405c-199">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="e405c-200">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e405c-200">CommonParameters</span></span>

<span data-ttu-id="e405c-201">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e405c-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e405c-202">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e405c-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e405c-203">入力</span><span class="sxs-lookup"><span data-stu-id="e405c-203">INPUTS</span></span>

### <span data-ttu-id="e405c-204">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="e405c-204">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="e405c-205">任意のオブジェクトをにパイプラインでき `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="e405c-205">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="e405c-206">出力</span><span class="sxs-lookup"><span data-stu-id="e405c-206">OUTPUTS</span></span>

### <span data-ttu-id="e405c-207">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="e405c-207">System.IO.FileInfo</span></span>

<span data-ttu-id="e405c-208">`Export-Clixml` XML を含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e405c-208">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="e405c-209">注</span><span class="sxs-lookup"><span data-stu-id="e405c-209">NOTES</span></span>

## <span data-ttu-id="e405c-210">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e405c-210">RELATED LINKS</span></span>

[<span data-ttu-id="e405c-211">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="e405c-211">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="e405c-212">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="e405c-212">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="e405c-213">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="e405c-213">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="e405c-214">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="e405c-214">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="e405c-215">Join-Path</span><span class="sxs-lookup"><span data-stu-id="e405c-215">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="e405c-216">ディスクへの資格情報の安全な保存</span><span class="sxs-lookup"><span data-stu-id="e405c-216">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="e405c-217">PowerShell を使用してレガシシステムに資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="e405c-217">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[<span data-ttu-id="e405c-218">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="e405c-218">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
