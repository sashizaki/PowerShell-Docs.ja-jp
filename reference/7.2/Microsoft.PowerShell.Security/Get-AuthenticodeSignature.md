---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: 16c61b1fd442eb68c458c3b524a8fc55d5eedcb6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602791"
---
# <span data-ttu-id="eacb4-102">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="eacb4-102">Get-AuthenticodeSignature</span></span>

## <span data-ttu-id="eacb4-103">概要</span><span class="sxs-lookup"><span data-stu-id="eacb4-103">SYNOPSIS</span></span>
<span data-ttu-id="eacb4-104">ファイルの Authenticode 署名に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-104">Gets information about the Authenticode signature for a file.</span></span>

## <span data-ttu-id="eacb4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eacb4-105">SYNTAX</span></span>

### <span data-ttu-id="eacb4-106">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="eacb4-106">ByPath (Default)</span></span>

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="eacb4-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="eacb4-107">ByLiteralPath</span></span>

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### <span data-ttu-id="eacb4-108">ByContent</span><span class="sxs-lookup"><span data-stu-id="eacb4-108">ByContent</span></span>

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## <span data-ttu-id="eacb4-109">Description</span><span class="sxs-lookup"><span data-stu-id="eacb4-109">DESCRIPTION</span></span>

<span data-ttu-id="eacb4-110">`Get-AuthenticodeSignature`コマンドレットは、ファイルまたはファイルのコンテンツの Authenticode 署名に関する情報をバイト配列として取得します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-110">The `Get-AuthenticodeSignature` cmdlet gets information about the Authenticode signature for a file or file content as a byte array.</span></span> <span data-ttu-id="eacb4-111">ファイルが署名されていない場合、情報は取得されますが、フィールドは空白になります。</span><span class="sxs-lookup"><span data-stu-id="eacb4-111">If the file is not signed, the information is retrieved, but the fields are blank.</span></span>

## <span data-ttu-id="eacb4-112">例</span><span class="sxs-lookup"><span data-stu-id="eacb4-112">EXAMPLES</span></span>

### <span data-ttu-id="eacb4-113">例 1: ファイルの Authenticode 署名を取得する</span><span class="sxs-lookup"><span data-stu-id="eacb4-113">Example 1: Get the Authenticode signature for a file</span></span>

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

<span data-ttu-id="eacb4-114">このコマンドは、NewScript.ps1 ファイルの Authenticode 署名に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-114">This command gets information about the Authenticode signature in the NewScript.ps1 file.</span></span> <span data-ttu-id="eacb4-115">**FilePath** パラメーターを使用してファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-115">It uses the **FilePath** parameter to specify the file.</span></span>

### <span data-ttu-id="eacb4-116">例 2: 複数のファイルの Authenticode 署名を取得する</span><span class="sxs-lookup"><span data-stu-id="eacb4-116">Example 2: Get the Authenticode signature for multiple files</span></span>

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

<span data-ttu-id="eacb4-117">このコマンドは、コマンドラインに表示されている4つのファイルの Authenticode 署名に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-117">This command gets information about the Authenticode signature for the four files listed at the command line.</span></span> <span data-ttu-id="eacb4-118">この例では、 **FilePath** パラメーターの名前 (省略可能) は省略されています。</span><span class="sxs-lookup"><span data-stu-id="eacb4-118">In this example, the name of the **FilePath** parameter, which is optional, is omitted.</span></span>

### <span data-ttu-id="eacb4-119">例 3: 複数のファイルに対して有効な Authenticode 署名のみを取得する</span><span class="sxs-lookup"><span data-stu-id="eacb4-119">Example 3: Get only valid Authenticode signatures for multiple files</span></span>

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

<span data-ttu-id="eacb4-120">このコマンドは、有効な Authenticode 署名があるディレクトリ内のすべてのファイルを一覧表示 `$PSHOME` します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-120">This command lists all of the files in the `$PSHOME` directory that have a valid Authenticode signature.</span></span> <span data-ttu-id="eacb4-121">自動変数には、 `$PSHOME` PowerShell インストールディレクトリへのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eacb4-121">The `$PSHOME` automatic variable contains the path to the PowerShell installation directory.</span></span>

<span data-ttu-id="eacb4-122">このコマンドは、コマンドレットを使用して、 `Get-ChildItem` ディレクトリ内のファイルを取得し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="eacb4-122">The command uses the `Get-ChildItem` cmdlet to get the files in the `$PSHOME` directory.</span></span> <span data-ttu-id="eacb4-123">この例では、のパターンを使用 *します。*</span><span class="sxs-lookup"><span data-stu-id="eacb4-123">It uses a pattern of *.*</span></span> <span data-ttu-id="eacb4-124">ディレクトリを除外する場合は (ただし、ファイル名にドットが含まれていないファイルも除外します)。</span><span class="sxs-lookup"><span data-stu-id="eacb4-124">to exclude directories (although it also excludes files without a dot in the filename).</span></span>

<span data-ttu-id="eacb4-125">このコマンドは、パイプライン演算子 () を使用して、ファイルを `|` `$PSHOME` コマンドレットに送信し `ForEach-Object` ます。ここで、 `Get-AuthenticodeSignature` は各ファイルに対してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-125">The command uses a pipeline operator (`|`) to send the files in `$PSHOME` to the `ForEach-Object` cmdlet, where `Get-AuthenticodeSignature` is called for each file.</span></span>

<span data-ttu-id="eacb4-126">コマンドの結果は、 `Get-AuthenticodeSignature` 状態が有効な `Where-Object` 署名オブジェクトのみを選択するコマンドに送信されます。</span><span class="sxs-lookup"><span data-stu-id="eacb4-126">The results of the `Get-AuthenticodeSignature` command are sent to a `Where-Object` command that selects only the signature objects with a status of Valid.</span></span>

### <span data-ttu-id="eacb4-127">例 4: byte 配列として指定されたファイルコンテンツの Authenticode 署名を取得する</span><span class="sxs-lookup"><span data-stu-id="eacb4-127">Example 4: Get the Authenticode signature for a file content specified as byte array</span></span>

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

<span data-ttu-id="eacb4-128">このコマンドは、ファイルの内容の Authenticode 署名に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-128">This command gets information about the Authenticode signature for the content of a file.</span></span> <span data-ttu-id="eacb4-129">この例では、ファイル拡張子がファイルの内容と共に指定されています。</span><span class="sxs-lookup"><span data-stu-id="eacb4-129">In this example, the file extension is specified along with the content of the file.</span></span>

## <span data-ttu-id="eacb4-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eacb4-130">PARAMETERS</span></span>

### <span data-ttu-id="eacb4-131">-コンテンツ</span><span class="sxs-lookup"><span data-stu-id="eacb4-131">-Content</span></span>

<span data-ttu-id="eacb4-132">ファイルの内容をバイト配列として、Authenticode 署名を取得します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-132">Contents of a file as a byte array for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="eacb4-133">このパラメーターは、 **Sourcepathorextension** パラメーターと共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eacb4-133">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="eacb4-134">ファイルの内容は Unicode (16LE) 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eacb4-134">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

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

### <span data-ttu-id="eacb4-135">-FilePath</span><span class="sxs-lookup"><span data-stu-id="eacb4-135">-FilePath</span></span>

<span data-ttu-id="eacb4-136">検査するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-136">Specifies the path to the file to examine.</span></span> <span data-ttu-id="eacb4-137">ワイルドカードを使用できますが、展開結果が単一のファイルを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="eacb4-137">Wildcards are permitted, but they must lead to a single file.</span></span> <span data-ttu-id="eacb4-138">このパラメーターの値を指定する場合、コマンドラインに **FilePath** を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="eacb4-138">It is not necessary to type **FilePath** at the command line when you specify a value for this parameter.</span></span>

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

### <span data-ttu-id="eacb4-139">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="eacb4-139">-LiteralPath</span></span>

<span data-ttu-id="eacb4-140">検査するファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-140">Specifies the path to the file being examined.</span></span> <span data-ttu-id="eacb4-141">**FilePath** とは異なり、 **LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="eacb4-141">Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="eacb4-142">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="eacb4-142">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="eacb4-143">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="eacb4-143">If the path includes an escape character, enclose it in single quotation marks.</span></span> <span data-ttu-id="eacb4-144">単一引用符は、エスケープ文字として文字を解釈しないように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-144">Single quotation marks tell PowerShell not to interpret any characters as escape characters.</span></span>

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

### <span data-ttu-id="eacb4-145">-SourcePathOrExtension</span><span class="sxs-lookup"><span data-stu-id="eacb4-145">-SourcePathOrExtension</span></span>

<span data-ttu-id="eacb4-146">Authenticode 署名を取得する対象のコンテンツのファイルまたはファイルの種類へのパス。</span><span class="sxs-lookup"><span data-stu-id="eacb4-146">Path to the file or file type of the content for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="eacb4-147">このパラメーターは、ファイルの内容がバイト配列として渡される **コンテンツ** で使用されます。</span><span class="sxs-lookup"><span data-stu-id="eacb4-147">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

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

### <span data-ttu-id="eacb4-148">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="eacb4-148">CommonParameters</span></span>

<span data-ttu-id="eacb4-149">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="eacb4-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eacb4-150">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eacb4-150">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="eacb4-151">入力</span><span class="sxs-lookup"><span data-stu-id="eacb4-151">INPUTS</span></span>

### <span data-ttu-id="eacb4-152">System.String</span><span class="sxs-lookup"><span data-stu-id="eacb4-152">System.String</span></span>

<span data-ttu-id="eacb4-153">パイプを使用して、ファイルパスを含む文字列をにパイプすることができ `Get-AuthenticodeSignature` ます。</span><span class="sxs-lookup"><span data-stu-id="eacb4-153">You can pipe a string that contains a file path to `Get-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="eacb4-154">出力</span><span class="sxs-lookup"><span data-stu-id="eacb4-154">OUTPUTS</span></span>

### <span data-ttu-id="eacb4-155">システム... Automation. 署名</span><span class="sxs-lookup"><span data-stu-id="eacb4-155">System.Management.Automation.Signature</span></span>

<span data-ttu-id="eacb4-156">`Get-AuthenticodeSignature` 取得する各署名の署名オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="eacb4-156">`Get-AuthenticodeSignature` returns a signature object for each signature that it gets.</span></span>

## <span data-ttu-id="eacb4-157">注</span><span class="sxs-lookup"><span data-stu-id="eacb4-157">NOTES</span></span>

<span data-ttu-id="eacb4-158">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="eacb4-158">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="eacb4-159">PowerShell の Authenticode 署名の詳細については、「 [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eacb4-159">For information about Authenticode signatures in PowerShell, see [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span></span>

## <span data-ttu-id="eacb4-160">関連リンク</span><span class="sxs-lookup"><span data-stu-id="eacb4-160">RELATED LINKS</span></span>

[<span data-ttu-id="eacb4-161">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="eacb4-161">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="eacb4-162">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="eacb4-162">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="eacb4-163">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="eacb4-163">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="eacb4-164">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="eacb4-164">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="eacb4-165">about_Signing</span><span class="sxs-lookup"><span data-stu-id="eacb4-165">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
