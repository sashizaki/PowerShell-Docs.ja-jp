---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: 44608ba9fa2324f9d6d381801876c831ed8b3db8
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347297"
---
# <span data-ttu-id="c902e-103">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="c902e-103">Get-AuthenticodeSignature</span></span>

## <span data-ttu-id="c902e-104">概要</span><span class="sxs-lookup"><span data-stu-id="c902e-104">SYNOPSIS</span></span>
<span data-ttu-id="c902e-105">ファイルの Authenticode 署名に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c902e-105">Gets information about the Authenticode signature for a file.</span></span>

## <span data-ttu-id="c902e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c902e-106">SYNTAX</span></span>

### <span data-ttu-id="c902e-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="c902e-107">ByPath (Default)</span></span>

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="c902e-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="c902e-108">ByLiteralPath</span></span>

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### <span data-ttu-id="c902e-109">ByContent</span><span class="sxs-lookup"><span data-stu-id="c902e-109">ByContent</span></span>

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## <span data-ttu-id="c902e-110">Description</span><span class="sxs-lookup"><span data-stu-id="c902e-110">DESCRIPTION</span></span>

<span data-ttu-id="c902e-111">`Get-AuthenticodeSignature`コマンドレットは、ファイルまたはファイルのコンテンツの Authenticode 署名に関する情報をバイト配列として取得します。</span><span class="sxs-lookup"><span data-stu-id="c902e-111">The `Get-AuthenticodeSignature` cmdlet gets information about the Authenticode signature for a file or file content as a byte array.</span></span> <span data-ttu-id="c902e-112">ファイルが署名されていない場合、情報は取得されますが、フィールドは空白になります。</span><span class="sxs-lookup"><span data-stu-id="c902e-112">If the file is not signed, the information is retrieved, but the fields are blank.</span></span>

## <span data-ttu-id="c902e-113">例</span><span class="sxs-lookup"><span data-stu-id="c902e-113">EXAMPLES</span></span>

### <span data-ttu-id="c902e-114">例 1: ファイルの Authenticode 署名を取得する</span><span class="sxs-lookup"><span data-stu-id="c902e-114">Example 1: Get the Authenticode signature for a file</span></span>

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

<span data-ttu-id="c902e-115">このコマンドは、NewScript.ps1 ファイルの Authenticode 署名に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c902e-115">This command gets information about the Authenticode signature in the NewScript.ps1 file.</span></span> <span data-ttu-id="c902e-116">**FilePath** パラメーターを使用してファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="c902e-116">It uses the **FilePath** parameter to specify the file.</span></span>

### <span data-ttu-id="c902e-117">例 2: 複数のファイルの Authenticode 署名を取得する</span><span class="sxs-lookup"><span data-stu-id="c902e-117">Example 2: Get the Authenticode signature for multiple files</span></span>

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

<span data-ttu-id="c902e-118">このコマンドは、コマンドラインに表示されている4つのファイルの Authenticode 署名に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c902e-118">This command gets information about the Authenticode signature for the four files listed at the command line.</span></span> <span data-ttu-id="c902e-119">この例では、 **FilePath** パラメーターの名前 (省略可能) は省略されています。</span><span class="sxs-lookup"><span data-stu-id="c902e-119">In this example, the name of the **FilePath** parameter, which is optional, is omitted.</span></span>

### <span data-ttu-id="c902e-120">例 3: 複数のファイルに対して有効な Authenticode 署名のみを取得する</span><span class="sxs-lookup"><span data-stu-id="c902e-120">Example 3: Get only valid Authenticode signatures for multiple files</span></span>

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

<span data-ttu-id="c902e-121">このコマンドは、有効な Authenticode 署名があるディレクトリ内のすべてのファイルを一覧表示 `$PSHOME` します。</span><span class="sxs-lookup"><span data-stu-id="c902e-121">This command lists all of the files in the `$PSHOME` directory that have a valid Authenticode signature.</span></span> <span data-ttu-id="c902e-122">自動変数には、 `$PSHOME` PowerShell インストールディレクトリへのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c902e-122">The `$PSHOME` automatic variable contains the path to the PowerShell installation directory.</span></span>

<span data-ttu-id="c902e-123">このコマンドは、コマンドレットを使用して、 `Get-ChildItem` ディレクトリ内のファイルを取得し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="c902e-123">The command uses the `Get-ChildItem` cmdlet to get the files in the `$PSHOME` directory.</span></span> <span data-ttu-id="c902e-124">この例では、のパターンを使用 *します。*</span><span class="sxs-lookup"><span data-stu-id="c902e-124">It uses a pattern of *.*</span></span> <span data-ttu-id="c902e-125">ディレクトリを除外する場合は (ただし、ファイル名にドットが含まれていないファイルも除外します)。</span><span class="sxs-lookup"><span data-stu-id="c902e-125">to exclude directories (although it also excludes files without a dot in the filename).</span></span>

<span data-ttu-id="c902e-126">このコマンドは、パイプライン演算子 () を使用して、ファイルを `|` `$PSHOME` コマンドレットに送信し `ForEach-Object` ます。ここで、 `Get-AuthenticodeSignature` は各ファイルに対してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c902e-126">The command uses a pipeline operator (`|`) to send the files in `$PSHOME` to the `ForEach-Object` cmdlet, where `Get-AuthenticodeSignature` is called for each file.</span></span>

<span data-ttu-id="c902e-127">コマンドの結果は、 `Get-AuthenticodeSignature` 状態が有効な `Where-Object` 署名オブジェクトのみを選択するコマンドに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c902e-127">The results of the `Get-AuthenticodeSignature` command are sent to a `Where-Object` command that selects only the signature objects with a status of Valid.</span></span>

### <span data-ttu-id="c902e-128">例 4: byte 配列として指定されたファイルコンテンツの Authenticode 署名を取得する</span><span class="sxs-lookup"><span data-stu-id="c902e-128">Example 4: Get the Authenticode signature for a file content specified as byte array</span></span>

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

<span data-ttu-id="c902e-129">このコマンドは、ファイルの内容の Authenticode 署名に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c902e-129">This command gets information about the Authenticode signature for the content of a file.</span></span> <span data-ttu-id="c902e-130">この例では、ファイル拡張子がファイルの内容と共に指定されています。</span><span class="sxs-lookup"><span data-stu-id="c902e-130">In this example, the file extension is specified along with the content of the file.</span></span>

## <span data-ttu-id="c902e-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c902e-131">PARAMETERS</span></span>

### <span data-ttu-id="c902e-132">-コンテンツ</span><span class="sxs-lookup"><span data-stu-id="c902e-132">-Content</span></span>

<span data-ttu-id="c902e-133">ファイルの内容をバイト配列として、Authenticode 署名を取得します。</span><span class="sxs-lookup"><span data-stu-id="c902e-133">Contents of a file as a byte array for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="c902e-134">このパラメーターは、 **Sourcepathorextension** パラメーターと共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c902e-134">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="c902e-135">ファイルの内容は Unicode (16LE) 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c902e-135">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c902e-136">-FilePath</span><span class="sxs-lookup"><span data-stu-id="c902e-136">-FilePath</span></span>

<span data-ttu-id="c902e-137">検査するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c902e-137">Specifies the path to the file to examine.</span></span> <span data-ttu-id="c902e-138">ワイルドカードを使用できますが、展開結果が単一のファイルを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c902e-138">Wildcards are permitted, but they must lead to a single file.</span></span> <span data-ttu-id="c902e-139">このパラメーターの値を指定する場合、コマンドラインに **FilePath** を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c902e-139">It is not necessary to type **FilePath** at the command line when you specify a value for this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="c902e-140">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c902e-140">-LiteralPath</span></span>

<span data-ttu-id="c902e-141">検査するファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c902e-141">Specifies the path to the file being examined.</span></span> <span data-ttu-id="c902e-142">**FilePath** とは異なり、 **LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c902e-142">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="c902e-143">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="c902e-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c902e-144">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c902e-144">If the path includes an escape character, enclose it in single quotation marks.</span></span> <span data-ttu-id="c902e-145">単一引用符は、エスケープ文字として文字を解釈しないように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="c902e-145">Single quotation marks tell PowerShell not to interpret any characters as escape characters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c902e-146">-SourcePathOrExtension</span><span class="sxs-lookup"><span data-stu-id="c902e-146">-SourcePathOrExtension</span></span>

<span data-ttu-id="c902e-147">Authenticode 署名を取得する対象のコンテンツのファイルまたはファイルの種類へのパス。</span><span class="sxs-lookup"><span data-stu-id="c902e-147">Path to the file or file type of the content for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="c902e-148">このパラメーターは、ファイルの内容がバイト配列として渡される **コンテンツ** で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c902e-148">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c902e-149">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c902e-149">CommonParameters</span></span>

<span data-ttu-id="c902e-150">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c902e-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c902e-151">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c902e-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c902e-152">入力</span><span class="sxs-lookup"><span data-stu-id="c902e-152">INPUTS</span></span>

### <span data-ttu-id="c902e-153">System.String</span><span class="sxs-lookup"><span data-stu-id="c902e-153">System.String</span></span>

<span data-ttu-id="c902e-154">パイプを使用して、ファイルパスを含む文字列をにパイプすることができ `Get-AuthenticodeSignature` ます。</span><span class="sxs-lookup"><span data-stu-id="c902e-154">You can pipe a string that contains a file path to `Get-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="c902e-155">出力</span><span class="sxs-lookup"><span data-stu-id="c902e-155">OUTPUTS</span></span>

### <span data-ttu-id="c902e-156">システム... Automation. 署名</span><span class="sxs-lookup"><span data-stu-id="c902e-156">System.Management.Automation.Signature</span></span>

<span data-ttu-id="c902e-157">`Get-AuthenticodeSignature` 取得する各署名の署名オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c902e-157">`Get-AuthenticodeSignature` returns a signature object for each signature that it gets.</span></span>

## <span data-ttu-id="c902e-158">注</span><span class="sxs-lookup"><span data-stu-id="c902e-158">NOTES</span></span>

<span data-ttu-id="c902e-159">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c902e-159">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="c902e-160">PowerShell の Authenticode 署名の詳細については、「 [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c902e-160">For information about Authenticode signatures in PowerShell, see [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span></span>

## <span data-ttu-id="c902e-161">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c902e-161">RELATED LINKS</span></span>

[<span data-ttu-id="c902e-162">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="c902e-162">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="c902e-163">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="c902e-163">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="c902e-164">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="c902e-164">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="c902e-165">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="c902e-165">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="c902e-166">about_Signing</span><span class="sxs-lookup"><span data-stu-id="c902e-166">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
