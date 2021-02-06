---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 7a0c25197ba00fb05089f855592e7744ef10e9b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604935"
---
# <span data-ttu-id="8b716-102">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="8b716-102">Export-Clixml</span></span>

## <span data-ttu-id="8b716-103">概要</span><span class="sxs-lookup"><span data-stu-id="8b716-103">SYNOPSIS</span></span>
<span data-ttu-id="8b716-104">1 つまたは複数のオブジェクトの XML ベースの表現を作成し、ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="8b716-104">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="8b716-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b716-105">SYNTAX</span></span>

### <span data-ttu-id="8b716-106">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="8b716-106">ByPath (Default)</span></span>

```
Export-Clixml [-Depth <Int32>] [-Path] <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8b716-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="8b716-107">ByLiteralPath</span></span>

```
Export-Clixml [-Depth <Int32>] -LiteralPath <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8b716-108">Description</span><span class="sxs-lookup"><span data-stu-id="8b716-108">DESCRIPTION</span></span>

<span data-ttu-id="8b716-109">コマンドレットでは、 `Export-Clixml` 共通言語基盤 (CLI) の XML ベースの表現をオブジェクトまたはオブジェクトで作成し、ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="8b716-109">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="8b716-110">その後、コマンドレットを使用して、 `Import-Clixml` そのファイルの内容に基づいて保存されたオブジェクトを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="8b716-110">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="8b716-111">CLI の詳細については、「 [言語に依存](/dotnet/standard/language-independence)しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b716-111">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="8b716-112">このコマンドレットはに似ていますが、では `ConvertTo-Xml` 、結果の XML がファイルに格納される点が異なり `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-112">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="8b716-113">`ConvertTo-XML` は XML を返します。そのため、PowerShell で処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="8b716-113">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="8b716-114">Windows コンピューターでのの重要な使用方法 `Export-Clixml` は、資格情報をエクスポートし、文字列を安全に XML としてセキュリティで保護することです。</span><span class="sxs-lookup"><span data-stu-id="8b716-114">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="8b716-115">例については、例3を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b716-115">For an example, see Example 3.</span></span>

## <span data-ttu-id="8b716-116">例</span><span class="sxs-lookup"><span data-stu-id="8b716-116">EXAMPLES</span></span>

### <span data-ttu-id="8b716-117">例 1: XML ファイルに文字列をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8b716-117">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="8b716-118">この例では、現在のディレクトリに格納されている XML ファイルを作成します。 **これは**、という文字列の表現です。</span><span class="sxs-lookup"><span data-stu-id="8b716-118">This example creates an XML file that stores in the current directory, a representation of the string **This is a test**.</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="8b716-119">文字列 `This is a test` はパイプラインで送信されます。</span><span class="sxs-lookup"><span data-stu-id="8b716-119">The string `This is a test` is sent down the pipeline.</span></span> <span data-ttu-id="8b716-120">`Export-Clixml`**Path** パラメーターを使用して、現在のディレクトリにという名前の XML ファイルを作成し `sample.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-120">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="8b716-121">例 2: オブジェクトを XML ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8b716-121">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="8b716-122">この例では、オブジェクトを XML ファイルにエクスポートし、エクスポートしたファイルから XML をインポートしてオブジェクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8b716-122">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="8b716-123">コマンドレットでは、 `Get-Acl` ファイルのセキュリティ記述子を取得し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-123">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="8b716-124">オブジェクトをパイプラインの下に送信して、セキュリティ記述子をに渡し `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-124">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="8b716-125">オブジェクトの XML ベースの表現は、という名前のファイルに格納され `FileACL.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-125">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="8b716-126">`Import-Clixml`コマンドレットは、ファイル内の XML からオブジェクトを作成し `FileACL.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-126">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="8b716-127">次に、変数にオブジェクトを保存し `$fileacl` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-127">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="8b716-128">例 3: Windows でエクスポートされた資格情報オブジェクトを暗号化する</span><span class="sxs-lookup"><span data-stu-id="8b716-128">Example 3: Encrypt an exported credential object on Windows</span></span>

<span data-ttu-id="8b716-129">この例では、コマンドレットを実行して変数に格納した資格情報を指定した場合、 `$Credential` `Get-Credential` コマンドレットを実行して `Export-Clixml` 資格情報をディスクに保存できます。</span><span class="sxs-lookup"><span data-stu-id="8b716-129">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b716-130">`Export-Clixml` 暗号化された資格情報のみを Windows でエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8b716-130">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="8b716-131">MacOS や Linux などの Windows 以外のオペレーティングシステムでは、資格情報は Unicode 文字配列として格納されたプレーンテキストとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8b716-131">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="8b716-132">これにより、一部の難読化が可能になりますが、暗号化は提供されません。</span><span class="sxs-lookup"><span data-stu-id="8b716-132">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="8b716-133">コマンドレットでは、 `Export-Clixml` Windows [データ保護 API](/previous-versions/windows/apps/hh464970(v=win.10))を使用して資格情報オブジェクトを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="8b716-133">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span> <span data-ttu-id="8b716-134">暗号化により、そのコンピューター上のユーザーアカウントのみが資格情報オブジェクトの内容を復号化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8b716-134">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span>
<span data-ttu-id="8b716-135">エクスポートされたファイルは、 `CLIXML` 別のコンピューターまたは別のユーザーが使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8b716-135">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="8b716-136">この例では、資格情報が格納されているファイルがによって表され `TestScript.ps1.credential` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-136">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="8b716-137">**Testscript** を、資格情報の読み込みに使用するスクリプトの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8b716-137">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="8b716-138">資格情報オブジェクトをパイプラインの下に送信 `Export-Clixml` し、 `$Credxmlpath` 最初のコマンドで指定したパスに保存します。</span><span class="sxs-lookup"><span data-stu-id="8b716-138">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="8b716-139">スクリプトに資格情報を自動的にインポートするには、最後の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b716-139">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="8b716-140">を実行し `Import-Clixml` て、セキュリティで保護された資格情報オブジェクトをスクリプトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="8b716-140">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="8b716-141">このインポートにより、スクリプトにプレーンテキストのパスワードが公開されるリスクがなくなります。</span><span class="sxs-lookup"><span data-stu-id="8b716-141">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

### <span data-ttu-id="8b716-142">例 4: Linux または macOS で資格情報オブジェクトをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8b716-142">Example 4: Exporting a credential object on Linux or macOS</span></span>

<span data-ttu-id="8b716-143">この例では、  `$Credential` コマンドレットを使用して、変数に PSCredential を作成し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-143">In this example, we create a **PSCredential** in the `$Credential` variable using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="8b716-144">次 `Export-Clixml` に、を使用して、資格情報をディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="8b716-144">Then we use `Export-Clixml` to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b716-145">`Export-Clixml` 暗号化された資格情報のみを Windows でエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8b716-145">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="8b716-146">MacOS や Linux などの Windows 以外のオペレーティングシステムでは、資格情報は Unicode 文字配列として格納されたプレーンテキストとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8b716-146">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="8b716-147">これにより、一部の難読化が可能になりますが、暗号化は提供されません。</span><span class="sxs-lookup"><span data-stu-id="8b716-147">This provides some obfuscation but does not provide encryption.</span></span>

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

<span data-ttu-id="8b716-148">この例のの出力は、 `Get-Content` XML ファイル内の資格情報に焦点を合わせて切り捨てられています。</span><span class="sxs-lookup"><span data-stu-id="8b716-148">The output of `Get-Content` in this example has been truncate to focus on the credential information in the XML file.</span></span> <span data-ttu-id="8b716-149">パスワードのプレーンテキスト値は、によって証明される Unicode 文字配列として XML ファイルに格納されることに注意して `Format-Hex` ください。</span><span class="sxs-lookup"><span data-stu-id="8b716-149">Note that the plain text value of the password is stored in the XML file as a Unicode character array as proven by `Format-Hex`.</span></span> <span data-ttu-id="8b716-150">そのため、値はエンコードされますが、暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="8b716-150">So the value is encoded but not encrypted.</span></span>

## <span data-ttu-id="8b716-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8b716-151">PARAMETERS</span></span>

### <span data-ttu-id="8b716-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8b716-152">-Confirm</span></span>

<span data-ttu-id="8b716-153">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b716-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8b716-154">-深さ</span><span class="sxs-lookup"><span data-stu-id="8b716-154">-Depth</span></span>

<span data-ttu-id="8b716-155">XML 表現に含める子オブジェクトのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b716-155">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="8b716-156">既定値は `2` です。</span><span class="sxs-lookup"><span data-stu-id="8b716-156">The default value is `2`.</span></span>

<span data-ttu-id="8b716-157">ファイルのオブジェクトの種類に対して既定値をオーバーライドでき `Types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-157">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="8b716-158">詳細については、「 [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b716-158">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

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

### <span data-ttu-id="8b716-159">-Encoding</span><span class="sxs-lookup"><span data-stu-id="8b716-159">-Encoding</span></span>

<span data-ttu-id="8b716-160">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b716-160">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="8b716-161">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="8b716-161">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="8b716-162">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8b716-162">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="8b716-163">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b716-163">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="8b716-164">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8b716-164">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="8b716-165">`bigendianutf32`: ビッグエンディアンのバイト順を使用して、32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8b716-165">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="8b716-166">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b716-166">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="8b716-167">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8b716-167">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="8b716-168">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8b716-168">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="8b716-169">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8b716-169">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="8b716-170">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8b716-170">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="8b716-171">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8b716-171">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="8b716-172">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8b716-172">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="8b716-173">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-173">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="8b716-174">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b716-174">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="8b716-175">**Utf-7** _ の使用は推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8b716-175">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="8b716-176">PowerShell 7.1 では、 `utf7` _ *Encoding*\* パラメーターにを指定すると、警告が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="8b716-176">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

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

### <span data-ttu-id="8b716-177">-Force</span><span class="sxs-lookup"><span data-stu-id="8b716-177">-Force</span></span>

<span data-ttu-id="8b716-178">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b716-178">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="8b716-179">必要に応じて、このコマンドレットは出力ファイルの読み取り専用の属性をクリアします。</span><span class="sxs-lookup"><span data-stu-id="8b716-179">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="8b716-180">コマンドが完了すると、このコマンドレットが読み取り専用の属性をリセットしようとします。</span><span class="sxs-lookup"><span data-stu-id="8b716-180">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="8b716-181">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8b716-181">-InputObject</span></span>

<span data-ttu-id="8b716-182">変換するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b716-182">Specifies the object to be converted.</span></span> <span data-ttu-id="8b716-183">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b716-183">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="8b716-184">パイプを使用してオブジェクトをにパイプ処理することもでき `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-184">You can also pipe objects to `Export-Clixml`.</span></span>

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

### <span data-ttu-id="8b716-185">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8b716-185">-LiteralPath</span></span>

<span data-ttu-id="8b716-186">オブジェクトの XML 表現が格納されるファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b716-186">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="8b716-187">**Path** と異なり、 **LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b716-187">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="8b716-188">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="8b716-188">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8b716-189">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="8b716-189">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="8b716-190">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="8b716-190">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="8b716-191">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="8b716-191">-NoClobber</span></span>

<span data-ttu-id="8b716-192">コマンドレットが既存のファイルの内容を上書きしないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8b716-192">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="8b716-193">既定では、指定されたパスにファイルが存在する場合、は `Export-Clixml` 警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="8b716-193">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="8b716-194">-Path</span><span class="sxs-lookup"><span data-stu-id="8b716-194">-Path</span></span>

<span data-ttu-id="8b716-195">オブジェクトの XML 表現が格納されるファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b716-195">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

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

### <span data-ttu-id="8b716-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8b716-196">-WhatIf</span></span>

<span data-ttu-id="8b716-197">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="8b716-197">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="8b716-198">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8b716-198">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="8b716-199">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b716-199">CommonParameters</span></span>

<span data-ttu-id="8b716-200">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8b716-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8b716-201">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b716-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8b716-202">入力</span><span class="sxs-lookup"><span data-stu-id="8b716-202">INPUTS</span></span>

### <span data-ttu-id="8b716-203">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="8b716-203">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="8b716-204">任意のオブジェクトをにパイプラインでき `Export-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="8b716-204">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="8b716-205">出力</span><span class="sxs-lookup"><span data-stu-id="8b716-205">OUTPUTS</span></span>

### <span data-ttu-id="8b716-206">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="8b716-206">System.IO.FileInfo</span></span>

<span data-ttu-id="8b716-207">`Export-Clixml` XML を含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b716-207">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="8b716-208">注</span><span class="sxs-lookup"><span data-stu-id="8b716-208">NOTES</span></span>

## <span data-ttu-id="8b716-209">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8b716-209">RELATED LINKS</span></span>

[<span data-ttu-id="8b716-210">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="8b716-210">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="8b716-211">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="8b716-211">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="8b716-212">エクスポート-Csv</span><span class="sxs-lookup"><span data-stu-id="8b716-212">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="8b716-213">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="8b716-213">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="8b716-214">Join-Path</span><span class="sxs-lookup"><span data-stu-id="8b716-214">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="8b716-215">ディスクへの資格情報の安全な保存</span><span class="sxs-lookup"><span data-stu-id="8b716-215">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="8b716-216">PowerShell を使用してレガシシステムに資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="8b716-216">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[<span data-ttu-id="8b716-217">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="8b716-217">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
