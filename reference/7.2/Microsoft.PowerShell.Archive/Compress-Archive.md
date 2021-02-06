---
external help file: Microsoft.PowerShell.Archive-help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 58807ba0745a6b09e7956547425c489b427d4f4b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601392"
---
# <span data-ttu-id="02ded-102">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="02ded-102">Compress-Archive</span></span>

## <span data-ttu-id="02ded-103">概要</span><span class="sxs-lookup"><span data-stu-id="02ded-103">SYNOPSIS</span></span>
<span data-ttu-id="02ded-104">指定したファイルおよびディレクトリから圧縮されたアーカイブ (zip 形式のファイル) を作成します。</span><span class="sxs-lookup"><span data-stu-id="02ded-104">Creates a compressed archive, or zipped file, from specified files and directories.</span></span>

## <span data-ttu-id="02ded-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="02ded-105">SYNTAX</span></span>

### <span data-ttu-id="02ded-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="02ded-106">Path (Default)</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="02ded-107">PathWithUpdate</span><span class="sxs-lookup"><span data-stu-id="02ded-107">PathWithUpdate</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="02ded-108">PathWithForce</span><span class="sxs-lookup"><span data-stu-id="02ded-108">PathWithForce</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="02ded-109">LiteralPathWithUpdate</span><span class="sxs-lookup"><span data-stu-id="02ded-109">LiteralPathWithUpdate</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="02ded-110">LiteralPathWithForce</span><span class="sxs-lookup"><span data-stu-id="02ded-110">LiteralPathWithForce</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="02ded-111">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="02ded-111">LiteralPath</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="02ded-112">Description</span><span class="sxs-lookup"><span data-stu-id="02ded-112">DESCRIPTION</span></span>

<span data-ttu-id="02ded-113">コマンドレットでは、 `Compress-Archive` 1 つ以上の指定したファイルまたはディレクトリから、圧縮されたアーカイブファイルまたは zip 形式のアーカイブファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="02ded-113">The `Compress-Archive` cmdlet creates a compressed, or zipped, archive file from one or more specified files or directories.</span></span> <span data-ttu-id="02ded-114">アーカイブでは、配布と保存を容易にするために、オプションで圧縮された複数のファイルを1つの zip 形式のファイルにパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="02ded-114">An archive packages multiple files, with optional compression, into a single zipped file for easier distribution and storage.</span></span> <span data-ttu-id="02ded-115">アーカイブファイルは、 **CompressionLevel** パラメーターで指定した圧縮アルゴリズムを使用して圧縮できます。</span><span class="sxs-lookup"><span data-stu-id="02ded-115">An archive file can be compressed by using the compression algorithm specified by the **CompressionLevel** parameter.</span></span>

<span data-ttu-id="02ded-116">この `Compress-Archive` コマンドレットは、MICROSOFT .NET API [System.IO.Compression.Zipアーカイブ](/dotnet/api/system.io.compression.ziparchive) を使用してファイルを圧縮します。</span><span class="sxs-lookup"><span data-stu-id="02ded-116">The `Compress-Archive` cmdlet uses the Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) to compress files.</span></span>
<span data-ttu-id="02ded-117">基になる API の制限があるため、最大ファイルサイズは 2 GB です。</span><span class="sxs-lookup"><span data-stu-id="02ded-117">The maximum file size is 2 GB because there's a limitation of the underlying API.</span></span>

<span data-ttu-id="02ded-118">いくつかの例では、スプラッティングを使用して、コードサンプルの行の長さを減らしています。</span><span class="sxs-lookup"><span data-stu-id="02ded-118">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="02ded-119">詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02ded-119">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="02ded-120">例</span><span class="sxs-lookup"><span data-stu-id="02ded-120">EXAMPLES</span></span>

### <span data-ttu-id="02ded-121">例 1: ファイルを圧縮してアーカイブファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="02ded-121">Example 1: Compress files to create an archive file</span></span>

<span data-ttu-id="02ded-122">この例では、別のディレクトリのファイルを圧縮し、アーカイブファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="02ded-122">This example compresses files from different directories and creates an archive file.</span></span> <span data-ttu-id="02ded-123">特定のファイル拡張子を持つすべてのファイルを取得するには、ワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="02ded-123">A wildcard is used to get all files with a particular file extension.</span></span> <span data-ttu-id="02ded-124">アーカイブファイルにはディレクトリ構造がありません。これは、 **パス** がファイル名のみを指定しているためです。</span><span class="sxs-lookup"><span data-stu-id="02ded-124">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="02ded-125">**Path** パラメーターは、ワイルドカードを使用して、特定のファイル名とファイル名を受け取り `*.vsd` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-125">The **Path** parameter accepts specific file names and file names with wildcards, `*.vsd`.</span></span> <span data-ttu-id="02ded-126">**パス** では、コンマ区切りのリストを使用して、異なるディレクトリからファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="02ded-126">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="02ded-127">圧縮レベルは、処理時間を短縮するのに **最も高速** です。</span><span class="sxs-lookup"><span data-stu-id="02ded-127">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="02ded-128">**DestinationPath** パラメーターは、ファイルの場所を指定し `Draft.zip` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-128">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="02ded-129">`Draft.zip`ファイルには `Draftdoc.docx` と拡張子を持つすべてのファイルが含まれ `.vsd` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-129">The `Draft.zip` file contains `Draftdoc.docx` and all the files with a `.vsd` extension.</span></span>

### <span data-ttu-id="02ded-130">例 2: LiteralPath を使用してファイルを圧縮する</span><span class="sxs-lookup"><span data-stu-id="02ded-130">Example 2: Compress files using a LiteralPath</span></span>

<span data-ttu-id="02ded-131">この例では、特定の名前付きファイルを圧縮し、新しいアーカイブファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="02ded-131">This example compresses specific named files and creates a new archive file.</span></span> <span data-ttu-id="02ded-132">アーカイブファイルにはディレクトリ構造がありません。これは、 **パス** がファイル名のみを指定しているためです。</span><span class="sxs-lookup"><span data-stu-id="02ded-132">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="02ded-133">**LiteralPath** パラメーターにはワイルドカードを使用できないため、絶対パスとファイル名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-133">Absolute path and file names are used because the **LiteralPath** parameter doesn't accept wildcards.</span></span> <span data-ttu-id="02ded-134">**パス** では、コンマ区切りのリストを使用して、異なるディレクトリからファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="02ded-134">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="02ded-135">圧縮レベルは、処理時間を短縮するのに **最も高速** です。</span><span class="sxs-lookup"><span data-stu-id="02ded-135">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="02ded-136">**DestinationPath** パラメーターは、ファイルの場所を指定し `Draft.zip` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-136">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="02ded-137">ファイルには `Draft.zip` とのみが含まれ `Draftdoc.docx` `diagram2.vsd` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-137">The `Draft.zip` file only contains `Draftdoc.docx` and `diagram2.vsd`.</span></span>

### <span data-ttu-id="02ded-138">例 3: ルートディレクトリを含むディレクトリを圧縮する</span><span class="sxs-lookup"><span data-stu-id="02ded-138">Example 3: Compress a directory that includes the root directory</span></span>

<span data-ttu-id="02ded-139">この例では、ディレクトリを圧縮し、ルートディレクトリとそのすべてのファイルとサブディレクトリを **含む** アーカイブファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="02ded-139">This example compresses a directory and creates an archive file that **includes** the root directory, and all its files and subdirectories.</span></span> <span data-ttu-id="02ded-140">**パス** にはルートディレクトリが指定されているため、アーカイブファイルにはディレクトリ構造があります。</span><span class="sxs-lookup"><span data-stu-id="02ded-140">The archive file has a directory structure because the **Path** specifies a root directory.</span></span>

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="02ded-141">`Compress-Archive`**Path** パラメーターを使用して、ルートディレクトリを指定し `C:\Reference` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-141">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference`.</span></span> <span data-ttu-id="02ded-142">**DestinationPath** パラメーターは、アーカイブファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-142">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="02ded-143">アーカイブには、 `Draft.zip` `Reference` ルートディレクトリ、およびそのすべてのファイルとサブディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02ded-143">The `Draft.zip` archive includes the `Reference` root directory, and all its files and subdirectories.</span></span>

### <span data-ttu-id="02ded-144">例 4: ルートディレクトリを除外するディレクトリを圧縮する</span><span class="sxs-lookup"><span data-stu-id="02ded-144">Example 4: Compress a directory that excludes the root directory</span></span>

<span data-ttu-id="02ded-145">この例では、ディレクトリを圧縮し、ルートディレクトリを **除外** するアーカイブファイルを作成します。これは、 **パス** でアスタリスク () ワイルドカードが使用されているため `*` です。</span><span class="sxs-lookup"><span data-stu-id="02ded-145">This example compresses a directory and creates an archive file that **excludes** the root directory because the **Path** uses an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="02ded-146">アーカイブには、ルートディレクトリのファイルとサブディレクトリを含むディレクトリ構造が含まれています。</span><span class="sxs-lookup"><span data-stu-id="02ded-146">The archive contains a directory structure that contains the root directory's files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="02ded-147">`Compress-Archive`**Path** パラメーターを使用して、ルートディレクトリを指定し `C:\Reference` ます。アスタリスク () のワイルドカードを使用し `*` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-147">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="02ded-148">**DestinationPath** パラメーターは、アーカイブファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-148">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="02ded-149">アーカイブには `Draft.zip` 、ルートディレクトリのファイルとサブディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="02ded-149">The `Draft.zip` archive contains the root directory's files and subdirectories.</span></span> <span data-ttu-id="02ded-150">`Reference`ルートディレクトリはアーカイブから除外されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-150">The `Reference` root directory is excluded from the archive.</span></span>

### <span data-ttu-id="02ded-151">例 5: ルートディレクトリ内のファイルのみを圧縮する</span><span class="sxs-lookup"><span data-stu-id="02ded-151">Example 5: Compress only the files in a root directory</span></span>

<span data-ttu-id="02ded-152">この例では、ルートディレクトリ内のファイルのみを圧縮し、アーカイブファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="02ded-152">This example compresses only the files in a root directory and creates an archive file.</span></span> <span data-ttu-id="02ded-153">ファイルのみが圧縮されているため、アーカイブにはディレクトリ構造がありません。</span><span class="sxs-lookup"><span data-stu-id="02ded-153">There's no directory structure in the archive because only files are compressed.</span></span>

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="02ded-154">`Compress-Archive`**Path** パラメーターを使用して、ルートディレクトリを指定します。これには、 `C:\Reference` アスタリスク (!)**星**() のワイルドカードを使用し `*.*` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-154">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with a **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="02ded-155">**DestinationPath** パラメーターは、アーカイブファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-155">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="02ded-156">アーカイブには `Draft.zip` ルートディレクトリのファイルのみが含まれ、 `Reference` ルートディレクトリは除外されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-156">The `Draft.zip` archive only contains the `Reference` root directory's files and the root directory is excluded.</span></span>

### <span data-ttu-id="02ded-157">例 6: パイプラインを使用してファイルをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="02ded-157">Example 6: Use the pipeline to archive files</span></span>

<span data-ttu-id="02ded-158">この例では、ファイルをパイプラインに送信してアーカイブを作成します。</span><span class="sxs-lookup"><span data-stu-id="02ded-158">This example sends files down the pipeline to create an archive.</span></span> <span data-ttu-id="02ded-159">アーカイブファイルにはディレクトリ構造がありません。これは、 **パス** がファイル名のみを指定しているためです。</span><span class="sxs-lookup"><span data-stu-id="02ded-159">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

<span data-ttu-id="02ded-160">`Get-ChildItem`**Path** パラメーターを使用して、異なるディレクトリの2つのファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-160">`Get-ChildItem` uses the **Path** parameter to specify two files from different directories.</span></span> <span data-ttu-id="02ded-161">各ファイルは、 **FileInfo** オブジェクトによって表され、パイプライン内でに送信され `Compress-Archive` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-161">Each file is represented by a **FileInfo** object and is sent down the pipeline to `Compress-Archive`.</span></span>
<span data-ttu-id="02ded-162">指定された2つのファイルは、にアーカイブされ `PipelineFiles.zip` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-162">The two specified files are archived in `PipelineFiles.zip`.</span></span>

### <span data-ttu-id="02ded-163">例 7: パイプラインを使用してディレクトリをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="02ded-163">Example 7: Use the pipeline to archive a directory</span></span>

<span data-ttu-id="02ded-164">この例では、ディレクトリをパイプラインの下に送信してアーカイブを作成します。</span><span class="sxs-lookup"><span data-stu-id="02ded-164">This example sends a directory down the pipeline to create an archive.</span></span> <span data-ttu-id="02ded-165">ファイルは、 **DirectoryInfo** オブジェクトとして **FileInfo** オブジェクトおよびディレクトリとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-165">Files are sent as **FileInfo** objects and directories as **DirectoryInfo** objects.</span></span> <span data-ttu-id="02ded-166">アーカイブのディレクトリ構造にはルートディレクトリが含まれていませんが、そのファイルとサブディレクトリはアーカイブに含まれています。</span><span class="sxs-lookup"><span data-stu-id="02ded-166">The archive's directory structure doesn't include the root directory, but its files and subdirectories are included in the archive.</span></span>

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

<span data-ttu-id="02ded-167">`Get-ChildItem`**Path** パラメーターを使用して、 `C:\LogFiles` ルートディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-167">`Get-ChildItem` uses the **Path** parameter to specify the `C:\LogFiles` root directory.</span></span> <span data-ttu-id="02ded-168">各 **FileInfo** および **DirectoryInfo** オブジェクトは、パイプラインを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-168">Each **FileInfo** and **DirectoryInfo** object is sent down the pipeline.</span></span>

<span data-ttu-id="02ded-169">`Compress-Archive` 各オブジェクトをアーカイブに追加し `PipelineDir.zip` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-169">`Compress-Archive` adds each object to the `PipelineDir.zip` archive.</span></span> <span data-ttu-id="02ded-170">パイプラインオブジェクトがパラメーター位置0に渡されるため、 **Path** パラメーターが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="02ded-170">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

### <span data-ttu-id="02ded-171">例 8: 再帰がアーカイブに与える影響</span><span class="sxs-lookup"><span data-stu-id="02ded-171">Example 8: How recursion can affect archives</span></span>

<span data-ttu-id="02ded-172">この例では、再帰によってアーカイブ内のファイルを複製する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="02ded-172">This example shows how recursion can duplicate files in your archive.</span></span> <span data-ttu-id="02ded-173">たとえば、を `Get-ChildItem` **再帰** パラメーターと共に使用するとします。</span><span class="sxs-lookup"><span data-stu-id="02ded-173">For example, if you use `Get-ChildItem` with the **Recurse** parameter.</span></span> <span data-ttu-id="02ded-174">再帰処理として、各 **FileInfo** オブジェクトと **DirectoryInfo** オブジェクトがパイプラインで送信され、アーカイブに追加されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-174">As recursion processes, each **FileInfo** and **DirectoryInfo** object is sent down the pipeline and added to the archive.</span></span>

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

<span data-ttu-id="02ded-175">`C:\TestLog`ディレクトリにファイルが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="02ded-175">The `C:\TestLog` directory doesn't contain any files.</span></span> <span data-ttu-id="02ded-176">このファイルには、ファイルを含むという名前のサブディレクトリが含まれてい `testsub` `testlog.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-176">It does contain a subdirectory named `testsub` that contains the `testlog.txt` file.</span></span>

<span data-ttu-id="02ded-177">`Get-ChildItem`**Path** パラメーターを使用して、ルートディレクトリを指定し `C:\TestLog` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-177">`Get-ChildItem` uses the **Path** parameter to specify the root directory, `C:\TestLog`.</span></span> <span data-ttu-id="02ded-178">**再帰** パラメーターは、ファイルとディレクトリを処理します。</span><span class="sxs-lookup"><span data-stu-id="02ded-178">The **Recurse** parameter processes the files and directories.</span></span> <span data-ttu-id="02ded-179">と FileInfo オブジェクトの **DirectoryInfo** オブジェクトが作成され `testsub`  `testlog.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-179">A **DirectoryInfo** object is created for `testsub` and a **FileInfo** object `testlog.txt`.</span></span>

<span data-ttu-id="02ded-180">各オブジェクトは、パイプライン内でに送信され `Compress-Archive` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-180">Each object is sent down the pipeline to `Compress-Archive`.</span></span> <span data-ttu-id="02ded-181">**DestinationPath** は、アーカイブファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-181">The **DestinationPath** specifies the location for the archive file.</span></span> <span data-ttu-id="02ded-182">パイプラインオブジェクトがパラメーター位置0に渡されるため、 **Path** パラメーターが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="02ded-182">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

<span data-ttu-id="02ded-183">次の概要では、 `PipelineRecurse.zip` 重複するファイルを含むアーカイブの内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="02ded-183">The following summary describes the `PipelineRecurse.zip` archive's contents that contains a duplicate file:</span></span>

- <span data-ttu-id="02ded-184">**DirectoryInfo** オブジェクトは、ディレクトリを作成 `testsub` し、 `testlog.txt` ファイルを格納します。このファイルには、元のディレクトリ構造が反映されています。</span><span class="sxs-lookup"><span data-stu-id="02ded-184">The **DirectoryInfo** object creates the `testsub` directory and contains the `testlog.txt` file, which reflects the original directory structure.</span></span>
- <span data-ttu-id="02ded-185">**FileInfo** オブジェクトは、 `testlog.txt` アーカイブのルートに複製を作成します。</span><span class="sxs-lookup"><span data-stu-id="02ded-185">The **FileInfo** object creates a duplicate `testlog.txt` in the archive's root.</span></span> <span data-ttu-id="02ded-186">再帰によってファイルオブジェクトがに送信されたため、重複したファイルが作成され `Compress-Archive` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-186">The duplicate file is created because recursion sent a file object to `Compress-Archive`.</span></span> <span data-ttu-id="02ded-187">パイプラインを経由して送信された各オブジェクトがアーカイブに追加されるため、この動作が想定されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-187">This behavior is expected because each object sent down the pipeline is added to the archive.</span></span>

### <span data-ttu-id="02ded-188">例 9: 既存のアーカイブファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="02ded-188">Example 9: Update an existing archive file</span></span>

<span data-ttu-id="02ded-189">この例では、ディレクトリ内の既存のアーカイブファイルを更新し `Draft.Zip` `C:\Archives` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-189">This example updates an existing archive file, `Draft.Zip`, in the `C:\Archives` directory.</span></span> <span data-ttu-id="02ded-190">この例では、既存のアーカイブファイルにルートディレクトリとそのファイルとサブディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="02ded-190">In this example, the existing archive file contains the root directory, and its files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

<span data-ttu-id="02ded-191">このコマンドは、 `Draft.Zip` `C:\Reference` ディレクトリとそのサブディレクトリ内の既存のファイルの新しいバージョンで更新されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-191">The command updates `Draft.Zip` with newer versions of existing files in the `C:\Reference` directory and its subdirectories.</span></span> <span data-ttu-id="02ded-192">また、そのサブディレクトリに追加された新しいファイルは、 `C:\Reference` 更新されたアーカイブに含まれ `Draft.Zip` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-192">And, new files that were added to `C:\Reference` or its subdirectories are included in the updated `Draft.Zip` archive.</span></span>

## <span data-ttu-id="02ded-193">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="02ded-193">PARAMETERS</span></span>

### <span data-ttu-id="02ded-194">-CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="02ded-194">-CompressionLevel</span></span>

<span data-ttu-id="02ded-195">アーカイブファイルを作成しているときに適用する圧縮の量を指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-195">Specifies how much compression to apply when you're creating the archive file.</span></span> <span data-ttu-id="02ded-196">より高速な圧縮では、ファイルの作成に時間がかかりますが、ファイルサイズが大きくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02ded-196">Faster compression requires less time to create the file, but can result in larger file sizes.</span></span>

<span data-ttu-id="02ded-197">このパラメーターが指定されていない場合、コマンドは既定値である [ **最適**] を使用します。</span><span class="sxs-lookup"><span data-stu-id="02ded-197">If this parameter isn't specified, the command uses the default value, **Optimal**.</span></span>

<span data-ttu-id="02ded-198">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="02ded-198">The following are the acceptable values for this parameter:</span></span>

- <span data-ttu-id="02ded-199">**最速**。</span><span class="sxs-lookup"><span data-stu-id="02ded-199">**Fastest**.</span></span> <span data-ttu-id="02ded-200">処理時間を短縮するために使用できる最速の圧縮方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="02ded-200">Use the fastest compression method available to reduce processing time.</span></span> <span data-ttu-id="02ded-201">圧縮を高速化すると、ファイルサイズが大きくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02ded-201">Faster compression can result in larger file sizes.</span></span>
- <span data-ttu-id="02ded-202">**Nocompression**。</span><span class="sxs-lookup"><span data-stu-id="02ded-202">**NoCompression**.</span></span> <span data-ttu-id="02ded-203">では、ソースファイルは圧縮されません。</span><span class="sxs-lookup"><span data-stu-id="02ded-203">Doesn't compress the source files.</span></span>
- <span data-ttu-id="02ded-204">**[最適]** 。</span><span class="sxs-lookup"><span data-stu-id="02ded-204">**Optimal**.</span></span> <span data-ttu-id="02ded-205">処理時間はファイルサイズに依存します。</span><span class="sxs-lookup"><span data-stu-id="02ded-205">Processing time is dependent on file size.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Optimal, NoCompression, Fastest

Required: False
Position: Named
Default value: Optimal
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="02ded-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="02ded-206">-Confirm</span></span>

<span data-ttu-id="02ded-207">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="02ded-208">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="02ded-208">-DestinationPath</span></span>

<span data-ttu-id="02ded-209">このパラメーターは必須で、アーカイブ出力ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-209">This parameter is required and specifies the path to the archive output file.</span></span> <span data-ttu-id="02ded-210">**DestinationPath** には、zip 形式のファイルの名前と、zip 形式のファイルへの絶対パスまたは相対パスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="02ded-210">The **DestinationPath** should include the name of the zipped file, and either the absolute or relative path to the zipped file.</span></span>

<span data-ttu-id="02ded-211">**DestinationPath** のファイル名にファイル名拡張子がない場合は、コマンドレットによって `.zip` ファイル名拡張子が追加され `.zip` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-211">If the file name in **DestinationPath** doesn't have a `.zip` file name extension, the cmdlet adds the `.zip` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="02ded-212">-Force</span><span class="sxs-lookup"><span data-stu-id="02ded-212">-Force</span></span>

<span data-ttu-id="02ded-213">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02ded-213">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithForce, LiteralPathWithForce
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="02ded-214">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="02ded-214">-LiteralPath</span></span>

<span data-ttu-id="02ded-215">アーカイブ zip ファイルに追加するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-215">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="02ded-216">**Path** パラメーターとは異なり、 **LiteralPath** の値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-216">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="02ded-217">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="02ded-217">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="02ded-218">パスにエスケープ文字が含まれている場合は、各エスケープ文字を単一引用符で囲み、すべての文字をエスケープシーケンスとして解釈しないように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="02ded-218">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>
<span data-ttu-id="02ded-219">複数のパスを指定し、出力 zip ファイル内の複数の場所にファイルを含めるには、コンマを使用してパスを区切ります。</span><span class="sxs-lookup"><span data-stu-id="02ded-219">To specify multiple paths, and include files in multiple locations in your output zipped file, use commas to separate the paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathWithUpdate, LiteralPathWithForce, LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="02ded-220">-PassThru</span><span class="sxs-lookup"><span data-stu-id="02ded-220">-PassThru</span></span>

<span data-ttu-id="02ded-221">作成されたアーカイブファイルを表すファイルオブジェクトをコマンドレットが出力するようにします。</span><span class="sxs-lookup"><span data-stu-id="02ded-221">Causes the cmdlet to output a file object representing the archive file created.</span></span>

<span data-ttu-id="02ded-222">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="02ded-222">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="02ded-223">-Path</span><span class="sxs-lookup"><span data-stu-id="02ded-223">-Path</span></span>

<span data-ttu-id="02ded-224">アーカイブ zip ファイルに追加するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-224">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="02ded-225">複数のパスを指定し、複数の場所にファイルを含めるには、コンマを使用してパスを区切ります。</span><span class="sxs-lookup"><span data-stu-id="02ded-225">To specify multiple paths, and include files in multiple locations, use commas to separate the paths.</span></span>

<span data-ttu-id="02ded-226">このパラメーターは、ワイルドカード文字を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="02ded-226">This parameter accepts wildcard characters.</span></span> <span data-ttu-id="02ded-227">ワイルドカード文字を使用すると、ディレクトリ内のすべてのファイルをアーカイブファイルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="02ded-227">Wildcard characters allow you to add all files in a directory to your archive file.</span></span>

<span data-ttu-id="02ded-228">ルートディレクトリでワイルドカードを使用すると、アーカイブの内容に影響します。</span><span class="sxs-lookup"><span data-stu-id="02ded-228">Using wildcards with a root directory affects the archive's contents:</span></span>

- <span data-ttu-id="02ded-229">ルートディレクトリとそのすべてのファイルとサブディレクトリを **含む** アーカイブを作成するには、 **パス** にワイルドカードを使用せずにルートディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ded-229">To create an archive that **includes** the root directory, and all its files and subdirectories, specify the root directory in the **Path** without wildcards.</span></span> <span data-ttu-id="02ded-230">例: `-Path C:\Reference`</span><span class="sxs-lookup"><span data-stu-id="02ded-230">For example: `-Path C:\Reference`</span></span>
- <span data-ttu-id="02ded-231">ルートディレクトリを **除外** し、すべてのファイルとサブディレクトリを zip するアーカイブを作成するには、アスタリスク ( `*` ) ワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="02ded-231">To create an archive that **excludes** the root directory, but zips all its files and subdirectories, use the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="02ded-232">例: `-Path C:\Reference\*`</span><span class="sxs-lookup"><span data-stu-id="02ded-232">For example: `-Path C:\Reference\*`</span></span>
- <span data-ttu-id="02ded-233">ルートディレクトリ内のファイルのみを zip するアーカイブを作成するには、 **アスタリスク** (\*) のワイルドカードを使用し `*.*` ます。</span><span class="sxs-lookup"><span data-stu-id="02ded-233">To create an archive that only zips the files in the root directory, use the **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="02ded-234">ルートのサブディレクトリがアーカイブに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="02ded-234">Subdirectories of the root aren't included in the archive.</span></span> <span data-ttu-id="02ded-235">例: `-Path C:\Reference\*.*`</span><span class="sxs-lookup"><span data-stu-id="02ded-235">For example: `-Path C:\Reference\*.*`</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path, PathWithUpdate, PathWithForce
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="02ded-236">-更新</span><span class="sxs-lookup"><span data-stu-id="02ded-236">-Update</span></span>

<span data-ttu-id="02ded-237">アーカイブ内の古いバージョンのファイルを、同じ名前の新しいファイルバージョンに置き換えることによって、指定されたアーカイブを更新します。</span><span class="sxs-lookup"><span data-stu-id="02ded-237">Updates the specified archive by replacing older file versions in the archive with newer file versions that have the same names.</span></span> <span data-ttu-id="02ded-238">また、このパラメーターを追加して、既存のアーカイブにファイルを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="02ded-238">You can also add this parameter to add files to an existing archive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithUpdate, LiteralPathWithUpdate
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="02ded-239">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="02ded-239">-WhatIf</span></span>

<span data-ttu-id="02ded-240">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="02ded-240">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="02ded-241">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="02ded-241">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="02ded-242">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="02ded-242">CommonParameters</span></span>

<span data-ttu-id="02ded-243">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="02ded-243">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="02ded-244">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02ded-244">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="02ded-245">入力</span><span class="sxs-lookup"><span data-stu-id="02ded-245">INPUTS</span></span>

### <span data-ttu-id="02ded-246">System.String</span><span class="sxs-lookup"><span data-stu-id="02ded-246">System.String</span></span>

<span data-ttu-id="02ded-247">パイプを使用して、パスを含む文字列を1つ以上のファイルに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="02ded-247">You can pipe a string that contains a path to one or more files.</span></span>

## <span data-ttu-id="02ded-248">出力</span><span class="sxs-lookup"><span data-stu-id="02ded-248">OUTPUTS</span></span>

### <span data-ttu-id="02ded-249">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="02ded-249">System.IO.FileInfo</span></span>

<span data-ttu-id="02ded-250">コマンドレットは、 **PassThru** パラメーターを使用する場合にのみ、 **FileInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="02ded-250">The cmdlet only returns a **FileInfo** object when you use the **PassThru** parameter.</span></span>

## <span data-ttu-id="02ded-251">注</span><span class="sxs-lookup"><span data-stu-id="02ded-251">NOTES</span></span>

<span data-ttu-id="02ded-252">再帰を使用してオブジェクトを送信すると、パイプラインによってアーカイブ内のファイルが複製される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02ded-252">Using recursion and sending objects down the pipeline can duplicate files in your archive.</span></span> <span data-ttu-id="02ded-253">たとえば、を `Get-ChildItem` **再帰** パラメーターと共に使用すると、パイプラインに送信される各 **FileInfo** および **DirectoryInfo** オブジェクトがアーカイブに追加されます。</span><span class="sxs-lookup"><span data-stu-id="02ded-253">For example, if you use `Get-ChildItem` with the **Recurse** parameter, each **FileInfo** and **DirectoryInfo** object that's sent down the pipeline is added to the archive.</span></span>

<span data-ttu-id="02ded-254">[ZIP ファイルの仕様](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)では、ASCII 以外の文字を含むファイル名をエンコードするための標準的な方法は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="02ded-254">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="02ded-255">コマンドレットでは、 `Compress-Archive` utf-8 エンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="02ded-255">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="02ded-256">他の ZIP アーカイブツールでは、別のエンコード方式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="02ded-256">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="02ded-257">UTF-8 エンコードを使用して格納されていないファイル名を使用してファイルを抽出すると、は `Expand-Archive` アーカイブで見つかった生の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="02ded-257">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="02ded-258">これにより、アーカイブに格納されているソースファイル名とは異なるファイル名が生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02ded-258">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="02ded-259">関連リンク</span><span class="sxs-lookup"><span data-stu-id="02ded-259">RELATED LINKS</span></span>

[<span data-ttu-id="02ded-260">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="02ded-260">Expand-Archive</span></span>](Expand-Archive.md)

[<span data-ttu-id="02ded-261">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="02ded-261">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

