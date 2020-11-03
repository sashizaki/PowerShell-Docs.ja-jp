---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileHash
ms.openlocfilehash: 6b6b0bdfe635ba0d11c4694efa8af6c23d9acdcd
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210795"
---
# <span data-ttu-id="2a51b-103">Get-FileHash</span><span class="sxs-lookup"><span data-stu-id="2a51b-103">Get-FileHash</span></span>

## <span data-ttu-id="2a51b-104">概要</span><span class="sxs-lookup"><span data-stu-id="2a51b-104">SYNOPSIS</span></span>
<span data-ttu-id="2a51b-105">指定されたハッシュ アルゴリズムを使用して、ファイルのハッシュ値を計算します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-105">Computes the hash value for a file by using a specified hash algorithm.</span></span>

## <span data-ttu-id="2a51b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2a51b-106">SYNTAX</span></span>

### <span data-ttu-id="2a51b-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="2a51b-107">Path (Default)</span></span>

```
Get-FileHash [-Path] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="2a51b-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2a51b-108">LiteralPath</span></span>

```
Get-FileHash [-LiteralPath] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="2a51b-109">StreamParameterSet</span><span class="sxs-lookup"><span data-stu-id="2a51b-109">StreamParameterSet</span></span>

```
Get-FileHash [-InputStream] <Stream> [[-Algorithm] <String>] [<CommonParameters>]
```

## <span data-ttu-id="2a51b-110">Description</span><span class="sxs-lookup"><span data-stu-id="2a51b-110">DESCRIPTION</span></span>

<span data-ttu-id="2a51b-111">`Get-FileHash`コマンドレットは、指定されたハッシュアルゴリズムを使用して、ファイルのハッシュ値を計算します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-111">The `Get-FileHash` cmdlet computes the hash value for a file by using a specified hash algorithm.</span></span>
<span data-ttu-id="2a51b-112">ハッシュ値とは、ファイルの内容に対応する一意の値です。</span><span class="sxs-lookup"><span data-stu-id="2a51b-112">A hash value is a unique value that corresponds to the content of the file.</span></span> <span data-ttu-id="2a51b-113">ハッシュは、ファイルの内容をファイル名や拡張子などの指定で識別するのではなく、ファイルの内容に一意の値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-113">Rather than identifying the contents of a file by its file name, extension, or other designation, a hash assigns a unique value to the contents of a file.</span></span> <span data-ttu-id="2a51b-114">ファイル名と拡張子は、ファイルの内容を変更することなく、ハッシュ値を変更することもなく、変更できます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-114">File names and extensions can be changed without altering the content of the file, and without changing the hash value.</span></span> <span data-ttu-id="2a51b-115">同様に、ファイルの内容を変更しても、名前や拡張子を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2a51b-115">Similarly, the file's content can be changed without changing the name or extension.</span></span> <span data-ttu-id="2a51b-116">ただし、ファイルの内容を 1 文字でも変更すると、ファイルのハッシュ値は変更されます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-116">However, changing even a single character in the contents of a file changes the hash value of the file.</span></span>

<span data-ttu-id="2a51b-117">ハッシュ値の目的は、ファイルの内容が変更されていないことを確認するための、暗号化による安全な方法を提供することです。</span><span class="sxs-lookup"><span data-stu-id="2a51b-117">The purpose of hash values is to provide a cryptographically-secure way to verify that the contents of a file have not been changed.</span></span> <span data-ttu-id="2a51b-118">MD5 や SHA1 などの一部のハッシュアルゴリズムは、攻撃から安全ではないと見なされなくなりましたが、セキュリティで保護されたハッシュアルゴリズムの目的は、誤って、または悪意のある、または不正な試行によってファイルの内容を変更できないようにし、同じハッシュ値を維持することです。</span><span class="sxs-lookup"><span data-stu-id="2a51b-118">While some hash algorithms, including MD5 and SHA1, are no longer considered secure against attack, the goal of a secure hash algorithm is to render it impossible to change the contents of a file -- either by accident, or by malicious or unauthorized attempt -- and maintain the same hash value.</span></span> <span data-ttu-id="2a51b-119">また、ハッシュ値を使用して、2 つの異なるファイルの内容がまったく同じかどうかを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-119">You can also use hash values to determine if two different files have exactly the same content.</span></span> <span data-ttu-id="2a51b-120">2 つのファイルのハッシュ値が同一の場合は、ファイルの内容も同一です。</span><span class="sxs-lookup"><span data-stu-id="2a51b-120">If the hash values of two files are identical, the contents of the files are also identical.</span></span>

<span data-ttu-id="2a51b-121">既定では、 `Get-FileHash` コマンドレットは SHA256 アルゴリズムを使用しますが、ターゲットオペレーティングシステムでサポートされている任意のハッシュアルゴリズムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-121">By default, the `Get-FileHash` cmdlet uses the SHA256 algorithm, although any hash algorithm that is supported by the target operating system can be used.</span></span>

## <span data-ttu-id="2a51b-122">例</span><span class="sxs-lookup"><span data-stu-id="2a51b-122">EXAMPLES</span></span>

### <span data-ttu-id="2a51b-123">例 1: ファイルのハッシュ値を計算する</span><span class="sxs-lookup"><span data-stu-id="2a51b-123">Example 1: Compute the hash value for a file</span></span>

<span data-ttu-id="2a51b-124">この例では、コマンドレットを使用して、 `Get-FileHash` ファイルのハッシュ値を計算し `/etc/apt/sources.list` ます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-124">This example uses the `Get-FileHash` cmdlet to compute the hash value for the `/etc/apt/sources.list` file.</span></span> <span data-ttu-id="2a51b-125">使用されるハッシュアルゴリズムは、既定の **SHA256** です。</span><span class="sxs-lookup"><span data-stu-id="2a51b-125">The hash algorithm used is the default, **SHA256** .</span></span> <span data-ttu-id="2a51b-126">出力をコマンドレットにパイプし `Format-List` て、出力を一覧として書式設定します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-126">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash /etc/apt/sources.list | Format-List
```

```Output
Algorithm : SHA256
Hash      : 3CBCFDDEC145E3382D592266BE193E5BE53443138EE6AB6CA09FF20DF609E268
Path      : /etc/apt/sources.list
```

### <span data-ttu-id="2a51b-127">例 2: ISO ファイルのハッシュ値を計算する</span><span class="sxs-lookup"><span data-stu-id="2a51b-127">Example 2: Compute the hash value for an ISO file</span></span>

<span data-ttu-id="2a51b-128">この例では、 `Get-FileHash` コマンドレットと **SHA384** アルゴリズムを使用して、管理者がインターネットからダウンロードした ISO ファイルのハッシュ値を計算します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-128">This example uses the `Get-FileHash` cmdlet and the **SHA384** algorithm to compute the hash value for an ISO file that an administrator has downloaded from the internet.</span></span> <span data-ttu-id="2a51b-129">出力をコマンドレットにパイプし `Format-List` て、出力を一覧として書式設定します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-129">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash C:\Users\user1\Downloads\Contoso8_1_ENT.iso -Algorithm SHA384 | Format-List
```

```Output
Algorithm : SHA384
Hash      : 20AB1C2EE19FC96A7C66E33917D191A24E3CE9DAC99DB7C786ACCE31E559144FEAFC695C58E508E2EBBC9D3C96F21FA3
Path      : C:\Users\user1\Downloads\Contoso8_1_ENT.iso
```

### <span data-ttu-id="2a51b-130">例 3: ストリームのハッシュ値を計算する</span><span class="sxs-lookup"><span data-stu-id="2a51b-130">Example 3: Compute the hash value of a stream</span></span>

<span data-ttu-id="2a51b-131">この例では、 **System .Net WebClient** を使用して、 [Powershell リリースページ](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4)からパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2a51b-131">For this example, we get are using **System.Net.WebClient** to download a package from the [Powershell release page](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span></span> <span data-ttu-id="2a51b-132">また、リリースページには、各パッケージファイルの SHA256 ハッシュも記載されています。</span><span class="sxs-lookup"><span data-stu-id="2a51b-132">The release page also documents the SHA256 hash of each package file.</span></span> <span data-ttu-id="2a51b-133">発行されたハッシュ値を、計算したものと比較することができ `Get-FileHash` ます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-133">We can compare the published hash value with the one we calculate with `Get-FileHash`.</span></span>

```powershell
$wc = [System.Net.WebClient]::new()
$pkgurl = 'https://github.com/PowerShell/PowerShell/releases/download/v6.2.4/powershell_6.2.4-1.debian.9_amd64.deb'
$publishedHash = '8E28E54D601F0751922DE24632C1E716B4684876255CF82304A9B19E89A9CCAC'
$FileHash = Get-FileHash -InputStream ($wc.OpenRead($pkgurl))
$FileHash.Hash -eq $publishedHash
```

```Output
True
```

### <span data-ttu-id="2a51b-134">例 4: 文字列のハッシュを計算する</span><span class="sxs-lookup"><span data-stu-id="2a51b-134">Example 4: Compute the hash of a string</span></span>

<span data-ttu-id="2a51b-135">PowerShell には、文字列のハッシュを計算するコマンドレットが用意されていません。</span><span class="sxs-lookup"><span data-stu-id="2a51b-135">PowerShell does not provide a cmdlet to compute the hash of a string.</span></span> <span data-ttu-id="2a51b-136">ただし、文字列をストリームに書き込んで、の **InputStream** パラメーターを使用してハッシュ値を取得することはでき `Get-FileHash` ます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-136">However, you can write a string to a stream and use the **InputStream** parameter of `Get-FileHash` to get the hash value.</span></span>

```powershell
$stringAsStream = [System.IO.MemoryStream]::new()
$writer = [System.IO.StreamWriter]::new($stringAsStream)
$writer.write("Hello world")
$writer.Flush()
$stringAsStream.Position = 0
Get-FileHash -InputStream $stringAsStream | Select-Object Hash
```

```Output
Hash
----
64EC88CA00B268E5BA1A35678A1B5316D212F4F366B2477232534A8AECA37F3C
```

## <span data-ttu-id="2a51b-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2a51b-137">PARAMETERS</span></span>

### <span data-ttu-id="2a51b-138">-アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="2a51b-138">-Algorithm</span></span>

<span data-ttu-id="2a51b-139">指定したファイルまたはストリームの内容のハッシュ値を計算するために使用する暗号ハッシュ関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-139">Specifies the cryptographic hash function to use for computing the hash value of the contents of the specified file or stream.</span></span> <span data-ttu-id="2a51b-140">暗号ハッシュ関数には、同じハッシュ値を持つ2つの異なるファイルを検索することが不可能であるというプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="2a51b-140">A cryptographic hash function has the property that it is infeasible to find two different files with the same hash value.</span></span> <span data-ttu-id="2a51b-141">ハッシュ関数は、データの整合性を確保するために、よくデジタル署名と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-141">Hash functions are commonly used with digital signatures and for data integrity.</span></span> <span data-ttu-id="2a51b-142">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2a51b-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2a51b-143">SHA1</span><span class="sxs-lookup"><span data-stu-id="2a51b-143">SHA1</span></span>
- <span data-ttu-id="2a51b-144">SHA256</span><span class="sxs-lookup"><span data-stu-id="2a51b-144">SHA256</span></span>
- <span data-ttu-id="2a51b-145">SHA384</span><span class="sxs-lookup"><span data-stu-id="2a51b-145">SHA384</span></span>
- <span data-ttu-id="2a51b-146">SHA512</span><span class="sxs-lookup"><span data-stu-id="2a51b-146">SHA512</span></span>
- <span data-ttu-id="2a51b-147">MD5</span><span class="sxs-lookup"><span data-stu-id="2a51b-147">MD5</span></span>

<span data-ttu-id="2a51b-148">値を指定しなかった場合、またはパラメーターを省略した場合、既定値は SHA256 です。</span><span class="sxs-lookup"><span data-stu-id="2a51b-148">If no value is specified, or if the parameter is omitted, the default value is SHA256.</span></span>

<span data-ttu-id="2a51b-149">セキュリティ上の理由により、安全と見なされなくなった MD5 と SHA1 は、単純な変更の検証にのみ使用し、攻撃や改ざんからの保護が必要なファイルのハッシュ値の生成には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2a51b-149">For security reasons, MD5 and SHA1, which are no longer considered secure, should only be used for simple change validation, and should not be used to generate hash values for files that require protection from attack or tampering.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SHA1, SHA256, SHA384, SHA512, MD5

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a51b-150">-InputStream</span><span class="sxs-lookup"><span data-stu-id="2a51b-150">-InputStream</span></span>

<span data-ttu-id="2a51b-151">入力ストリームを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-151">Specifies the input stream.</span></span>

```yaml
Type: System.IO.Stream
Parameter Sets: StreamParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a51b-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2a51b-152">-LiteralPath</span></span>

<span data-ttu-id="2a51b-153">ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-153">Specifies the path to a file.</span></span> <span data-ttu-id="2a51b-154">**Path** パラメーターと異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-154">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="2a51b-155">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="2a51b-155">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="2a51b-156">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-156">If the path includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="2a51b-157">単一引用符は、文字がエスケープシーケンスとして解釈されないように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-157">Single quotation marks instruct PowerShell not to interpret characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2a51b-158">-Path</span><span class="sxs-lookup"><span data-stu-id="2a51b-158">-Path</span></span>

<span data-ttu-id="2a51b-159">1つ以上のファイルへのパスを配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-159">Specifies the path to one or more files as an array.</span></span> <span data-ttu-id="2a51b-160">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="2a51b-161">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a51b-161">CommonParameters</span></span>

<span data-ttu-id="2a51b-162">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2a51b-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2a51b-163">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a51b-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2a51b-164">入力</span><span class="sxs-lookup"><span data-stu-id="2a51b-164">INPUTS</span></span>

### <span data-ttu-id="2a51b-165">System.String</span><span class="sxs-lookup"><span data-stu-id="2a51b-165">System.String</span></span>

<span data-ttu-id="2a51b-166">1つ以上のファイルへのパスを含む文字列をコマンドレットにパイプすることができ `Get-FileHash` ます。</span><span class="sxs-lookup"><span data-stu-id="2a51b-166">You can pipe a string to the `Get-FileHash` cmdlet that contains a path to one or more files.</span></span>

## <span data-ttu-id="2a51b-167">出力</span><span class="sxs-lookup"><span data-stu-id="2a51b-167">OUTPUTS</span></span>

### <span data-ttu-id="2a51b-168">Microsoft. Powershell. FileHash</span><span class="sxs-lookup"><span data-stu-id="2a51b-168">Microsoft.Powershell.Utility.FileHash</span></span>

<span data-ttu-id="2a51b-169">`Get-FileHash` 指定したファイルへのパス、計算されたハッシュの値、およびハッシュの計算に使用されるアルゴリズムを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2a51b-169">`Get-FileHash` returns an object that represents the path to the specified file, the value of the computed hash, and the algorithm used to compute the hash.</span></span>

## <span data-ttu-id="2a51b-170">注</span><span class="sxs-lookup"><span data-stu-id="2a51b-170">NOTES</span></span>

## <span data-ttu-id="2a51b-171">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2a51b-171">RELATED LINKS</span></span>

[<span data-ttu-id="2a51b-172">Format-List</span><span class="sxs-lookup"><span data-stu-id="2a51b-172">Format-List</span></span>](Format-List.md)
