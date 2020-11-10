---
description: FileSystem (ファイル システム)
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_filesystem_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: FileSystem プロバイダー
ms.openlocfilehash: 3464dbcbc1a7f357cdbc5368dc7a1e4d21f5ed5e
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387595"
---
# <a name="filesystem-provider"></a><span data-ttu-id="d4706-104">FileSystem プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d4706-104">FileSystem provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="d4706-105">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="d4706-105">Provider name</span></span>

<span data-ttu-id="d4706-106">FileSystem (ファイル システム)</span><span class="sxs-lookup"><span data-stu-id="d4706-106">FileSystem</span></span>

## <a name="drives"></a><span data-ttu-id="d4706-107">ドライブ</span><span class="sxs-lookup"><span data-stu-id="d4706-107">Drives</span></span>

<span data-ttu-id="d4706-108">`C:`, `D:` ...</span><span class="sxs-lookup"><span data-stu-id="d4706-108">`C:`, `D:` ...</span></span>

## <a name="capabilities"></a><span data-ttu-id="d4706-109">機能</span><span class="sxs-lookup"><span data-stu-id="d4706-109">Capabilities</span></span>

<span data-ttu-id="d4706-110">**フィルター\*\*\*\*処理**</span><span class="sxs-lookup"><span data-stu-id="d4706-110">**Filter** , **ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="d4706-111">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="d4706-111">Short description</span></span>

<span data-ttu-id="d4706-112">ファイルとディレクトリへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d4706-112">Provides access to files and directories.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="d4706-113">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="d4706-113">Detailed description</span></span>

<span data-ttu-id="d4706-114">PowerShell **FileSystem** プロバイダーを使用すると、powershell でファイルとディレクトリを取得、追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-114">The PowerShell **FileSystem** provider lets you get, add, change, clear, and delete files and directories in PowerShell.</span></span>

<span data-ttu-id="d4706-115">**ファイルシステム** ドライブは、コンピューター上のディレクトリとファイルを含む階層型の名前空間です。</span><span class="sxs-lookup"><span data-stu-id="d4706-115">The **FileSystem** drives are a hierarchical namespace containing the directories and files on your computer.</span></span> <span data-ttu-id="d4706-116">**ファイルシステム** ドライブには、論理的または phのドライブ、ディレクトリ、またはマップされたネットワーク共有を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-116">A **FileSystem** drive can be a logical or phsyical drive, directory, or mapped network share.</span></span>

<span data-ttu-id="d4706-117">**FileSystem** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d4706-117">The **FileSystem** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="d4706-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="d4706-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="d4706-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="d4706-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="d4706-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="d4706-121">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d4706-121">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="d4706-122">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-122">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="d4706-123">Move-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-123">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="d4706-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="d4706-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="d4706-126">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4706-126">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="d4706-127">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4706-127">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="d4706-128">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-128">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="d4706-129">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4706-129">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="d4706-130">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-130">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="d4706-131">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4706-131">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="d4706-132">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="d4706-132">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="d4706-133">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="d4706-133">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)
- [<span data-ttu-id="d4706-134">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="d4706-134">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="d4706-135">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="d4706-135">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="d4706-136">このプロバイダーによって公開される型</span><span class="sxs-lookup"><span data-stu-id="d4706-136">Types exposed by this provider</span></span>

<span data-ttu-id="d4706-137">ファイルは、 [system.servicemodel クラスのインスタンスです。](/dotnet/api/system.io.fileinfo)</span><span class="sxs-lookup"><span data-stu-id="d4706-137">Files are instances of the [System.IO.FileInfo](/dotnet/api/system.io.fileinfo) class.</span></span>  <span data-ttu-id="d4706-138">ディレクトリは、 [DirectoryInfo](/dotnet/api/system.io.directoryinfo) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d4706-138">Directories are instances of the [System.IO.DirectoryInfo](/dotnet/api/system.io.directoryinfo) class.</span></span>

## <a name="navigating-the-filesystem-drives"></a><span data-ttu-id="d4706-139">ファイルシステムドライブの移動</span><span class="sxs-lookup"><span data-stu-id="d4706-139">Navigating the FileSystem drives</span></span>

<span data-ttu-id="d4706-140">**FileSystem** プロバイダーは、コンピューター上のすべての論理ドライブを PowerShell ドライブとしてマップすることによって、そのデータストアを公開します。</span><span class="sxs-lookup"><span data-stu-id="d4706-140">The **FileSystem** provider exposes its data stores by mapping any logical drives on the computer as PowerShell drives.</span></span> <span data-ttu-id="d4706-141">**ファイルシステム** ドライブを操作するには、ドライブ名の後にコロン () を uing ドライブに場所を移動し `:` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-141">To work with a **FileSystem** drive you can change your location to a drive uing the drive name followed by a colon (`:`).</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="d4706-142">他の PowerShell ドライブから **FileSystem** プロバイダーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4706-142">You can also work with the **FileSystem** provider from any other PowerShell drive.</span></span> <span data-ttu-id="d4706-143">別の場所からファイルまたはディレクトリを参照するには、パスのドライブ名 ( `C:` 、 `D:` 、...) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4706-143">To reference a file or directory from another location, use the drive name (`C:`, `D:`, ...) in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="d4706-144">PowerShell では、エイリアスを使用して、プロバイダーパスを操作するための使い慣れた方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="d4706-145">`dir`やなどのコマンド `ls` は、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)のエイリアスです。これ `cd` は、 [Set Location](xref:Microsoft.PowerShell.Management.Set-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="d4706-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="d4706-146">と `pwd` は、 [Get Location](xref:Microsoft.PowerShell.Management.Get-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="d4706-146">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-files-and-directories"></a><span data-ttu-id="d4706-147">ファイルとディレクトリの取得</span><span class="sxs-lookup"><span data-stu-id="d4706-147">Getting files and directories</span></span>

<span data-ttu-id="d4706-148">この `Get-ChildItem` コマンドレットは、現在の場所にあるすべてのファイルとディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="d4706-148">The `Get-ChildItem` cmdlet returns all files and directories in the current location.</span></span> <span data-ttu-id="d4706-149">別のパスを指定して、組み込みパラメーターを検索して使用し、再帰の深さをフィルター処理したり制御したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d4706-149">You can specify a different path to search and use built in parameters to filter and control the recursion depth.</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="d4706-150">コマンドレットの使用方法の詳細については、「 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4706-150">To read more about cmdlet usage, see [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span></span>

## <a name="copying-files-and-directories"></a><span data-ttu-id="d4706-151">ファイルとディレクトリのコピー</span><span class="sxs-lookup"><span data-stu-id="d4706-151">Copying files and directories</span></span>

<span data-ttu-id="d4706-152">`Copy-Item`コマンドレットは、指定した場所にファイルとディレクトリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d4706-152">The `Copy-Item` cmdlet copies files and directories to a location you specify.</span></span>
<span data-ttu-id="d4706-153">パラメーターは、のようにフィルターと再帰に使用でき `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-153">Parameters are available to filter and recurse, similar to `Get-ChildItem`.</span></span>

<span data-ttu-id="d4706-154">次のコマンドは、パス "C:\temp" の下にあるすべてのファイルとディレクトリ \" をフォルダー "C:\Windows\Temp" にコピーします。</span><span class="sxs-lookup"><span data-stu-id="d4706-154">The following command copies all of the files and directories under the path "C:\temp\" to the folder "C:\Windows\Temp".</span></span>

```powershell
Copy-Item -Path C:\temp\* -Destination C:\Windows\Temp -Recurse -File
```

<span data-ttu-id="d4706-155">`Copy-Item` 確認メッセージを表示せずに、宛先ディレクトリ内のファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="d4706-155">`Copy-Item` overwrites files in the destination directory without prompting for confirmation.</span></span>

<span data-ttu-id="d4706-156">このコマンドは、 `a.txt` ディレクトリからディレクトリにファイルをコピーし `C:\a` `C:\a\bb` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-156">This command copies the `a.txt` file from the `C:\a` directory to the `C:\a\bb` directory.</span></span>

```powershell
Copy-Item -Path C:\a\a.txt -Destination C:\a\bb\a.txt
```

<span data-ttu-id="d4706-157">ディレクトリ内のすべてのディレクトリとファイル `C:\a` をディレクトリにコピーし `C:\c` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-157">Copies all the directories and files in the `C:\a` directory to the `C:\c` directory.</span></span> <span data-ttu-id="d4706-158">コピーするディレクトリがコピー先ディレクトリにすでに存在する場合、Force パラメーターを指定しないとコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d4706-158">If any of the directories to copy already exist in the destination directory, the command will fail unless you specify the Force parameter.</span></span>

```powershell
Copy-Item -Path C:\a\* -Destination C:\c -Recurse
```

<span data-ttu-id="d4706-159">詳細については、「 [コピー項目](xref:Microsoft.PowerShell.Management.Copy-Item)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4706-159">For more information, see [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span></span>

## <a name="moving-files-and-directories"></a><span data-ttu-id="d4706-160">ファイルとディレクトリの移動</span><span class="sxs-lookup"><span data-stu-id="d4706-160">Moving files and directories</span></span>

<span data-ttu-id="d4706-161">このコマンドは、 `c.txt` ディレクトリ内のファイル `C:\a` をディレクトリに移動し `C:\a\aa` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-161">This command moves the `c.txt` file in the `C:\a` directory to the `C:\a\aa` directory:</span></span>

```powershell
Move-Item -Path C:\a\c.txt -Destination C:\a\aa
```

<span data-ttu-id="d4706-162">このコマンドを実行して同じ名前を持つ既存ファイルが自動的に上書きされることはありません。</span><span class="sxs-lookup"><span data-stu-id="d4706-162">The command will not automatically overwrite an existing file that has the same name.</span></span> <span data-ttu-id="d4706-163">既存ファイルを上書きするようにコマンドレットに強制するには、Force パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4706-163">To force the cmdlet to overwrite an existing file, specify the Force parameter.</span></span>

<span data-ttu-id="d4706-164">ディレクトリが現在の場所のとき、そのディレクトリを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4706-164">You cannot move a directory when that directory is the current location.</span></span> <span data-ttu-id="d4706-165">を使用し `Move-Item` てディレクトリを現在の場所に移動すると、このエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4706-165">When you use `Move-Item` to move the directory at the current location, you see this error.</span></span>

```
C:\temp> Move-Item -Path C:\temp\ -Destination C:\Windows\Temp

Move-Item : Cannot move item because the item at 'C:\temp\' is in use.
At line:1 char:1
+ Move-Item C:\temp\ C:\temp2\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Move-Item], PSInvalidOperationException
    + FullyQualifiedErrorId : InvalidOperation,Microsoft.PowerShell.Commands.MoveItemCommand
```

## <a name="managing-file-content"></a><span data-ttu-id="d4706-166">ファイルコンテンツの管理</span><span class="sxs-lookup"><span data-stu-id="d4706-166">Managing file content</span></span>

### <a name="get-the-content-of-a-file"></a><span data-ttu-id="d4706-167">ファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-167">Get the content of a file</span></span>

<span data-ttu-id="d4706-168">このコマンドは、"Test.txt" ファイルの内容を取得し、コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="d4706-168">This command gets the contents of the "Test.txt" file and displays them in the console.</span></span>

```powershell
Get-Content -Path Test.txt
```

<span data-ttu-id="d4706-169">ファイルのコンテンツを別のコマンドレットにパイプで送ることができます。</span><span class="sxs-lookup"><span data-stu-id="d4706-169">You can pipe the contents of the file to another cmdlet.</span></span> <span data-ttu-id="d4706-170">たとえば、次のコマンドは、ファイルの内容を読み取っ `Test.txt` て、 [convertto-html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) コマンドレットへの入力として提供します。</span><span class="sxs-lookup"><span data-stu-id="d4706-170">For example, the following command reads the contents of the `Test.txt` file and then supplies them as input to the [ConvertTo-Html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) cmdlet:</span></span>

```powershell
Get-Content -Path Test.txt | ConvertTo-Html
```

<span data-ttu-id="d4706-171">プロバイダーのパスにドル記号 () を付けることで、ファイルの内容を取得することもでき `$` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-171">You can also retrieve the content of a file by prefixing its provider path with the dollar sign (`$`).</span></span> <span data-ttu-id="d4706-172">パスは、変数の名前付けの制限により、中かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4706-172">The path must be enclosed in curly braces due to variable naming restrictions.</span></span> <span data-ttu-id="d4706-173">詳細については、「 [about_Variables](about_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4706-173">For more information, see [about_Variables](about_Variables.md).</span></span>

```powershell
${C:\Windows\System32\Drivers\etc\hosts}
```

### <a name="add-content-to-a-file"></a><span data-ttu-id="d4706-174">ファイルにコンテンツを追加する</span><span class="sxs-lookup"><span data-stu-id="d4706-174">Add content to a file</span></span>

<span data-ttu-id="d4706-175">このコマンドは、ファイルに "test content" という文字列を追加し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-175">This command appends the "test content" string to the `Test.txt` file:</span></span>

```powershell
Add-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="d4706-176">ファイル内の既存のコンテンツ `Test.txt` は削除されません。</span><span class="sxs-lookup"><span data-stu-id="d4706-176">The existing content in the `Test.txt` file is not deleted.</span></span>

### <a name="replace-the-content-of-a-file"></a><span data-ttu-id="d4706-177">ファイルの内容を置き換える</span><span class="sxs-lookup"><span data-stu-id="d4706-177">Replace the content of a file</span></span>

<span data-ttu-id="d4706-178">このコマンドは、ファイルの内容を `Test.txt` "test content" 文字列に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d4706-178">This command replaces the contents of the `Test.txt` file with the "test content" string:</span></span>

```powershell
Set-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="d4706-179">の内容を上書き `Test.txt` します。</span><span class="sxs-lookup"><span data-stu-id="d4706-179">It overwrites the contents of `Test.txt`.</span></span> <span data-ttu-id="d4706-180">[新しい項目](xref:Microsoft.PowerShell.Management.New-Item)のコマンドレットの **Value** パラメーターを使用して、作成時にファイルにコンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-180">You can use the **Value** parameter of the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to add content to a file when you create it.</span></span>

### <a name="loop-through-the-contents-of-a-file"></a><span data-ttu-id="d4706-181">ファイルの内容をループする</span><span class="sxs-lookup"><span data-stu-id="d4706-181">Loop through the contents of a file</span></span>

<span data-ttu-id="d4706-182">既定では、 `Get-Content` コマンドレットは行末文字を区切り記号として使用するため、ファイルを文字列のコレクションとして取得し、各行をファイル内の1つの文字列として取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-182">By default, the `Get-Content` cmdlet uses the end-of-line character as its delimiter, so it gets a file as a collection of strings, with each line as one string in the file.</span></span>

<span data-ttu-id="d4706-183">パラメーターを使用して、 `-Delimiter` 別の区切り記号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-183">You can use the `-Delimiter` parameter to specify an alternate delimiter.</span></span> <span data-ttu-id="d4706-184">区切り文字をセクションの終わりか次のセクションの始まりを示す文字に設定した場合、ファイルを論理部分に分割できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-184">If you set it to the characters that denote the end of a section or the beginning of the next section, you can split the file into logical parts.</span></span>

<span data-ttu-id="d4706-185">最初のコマンドは、 `Employees.txt` ファイルを取得し、セクションに分割します。各セクションは "end Of Employee Record" という語で終わり、変数に保存さ `$e` れます。</span><span class="sxs-lookup"><span data-stu-id="d4706-185">The first command gets the `Employees.txt` file and splits it into sections, each of which ends with the words "End of Employee Record" and it saves it in the `$e` variable.</span></span>

<span data-ttu-id="d4706-186">2番目のコマンドは、配列表記を使用して、のコレクション内の最初の項目を取得し `$e` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-186">The second command uses array notation to get the first item in the collection in `$e`.</span></span> <span data-ttu-id="d4706-187">PowerShell 配列は0から始まるため、0のインデックスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4706-187">It uses an index of 0, because PowerShell arrays are zero-based.</span></span>

<span data-ttu-id="d4706-188">コマンドレットの詳細については、「」を `Get-Content` 参照 [し](xref:Microsoft.PowerShell.Management.Get-Content)てください。</span><span class="sxs-lookup"><span data-stu-id="d4706-188">For more information about `Get-Content` cmdlet, see the help topic for the [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).</span></span>

<span data-ttu-id="d4706-189">配列の詳細については、「 [about_Arrays](../About/about_Arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4706-189">For more information about arrays, see [about_Arrays](../About/about_Arrays.md).</span></span>

```powershell
$e = Get-Content c:\test\employees.txt -Delimited "End Of Employee Record"
$e[0]
```

## <a name="managing-security-descriptors"></a><span data-ttu-id="d4706-190">セキュリティ記述子の管理</span><span class="sxs-lookup"><span data-stu-id="d4706-190">Managing security descriptors</span></span>

### <a name="view-the-acl-for-a-file"></a><span data-ttu-id="d4706-191">ファイルの ACL を表示する</span><span class="sxs-lookup"><span data-stu-id="d4706-191">View the ACL for a file</span></span>

<span data-ttu-id="d4706-192">このコマンドは、 [accesscontrol-namespace. system.security.accesscontrol.filesecurity](/dotnet/api/system.security.accesscontrol.filesecurity) オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d4706-192">This command returns a [System.Security.AccessControl.FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) object:</span></span>

```powershell
Get-Acl -Path test.txt | Format-List -Property *
```

<span data-ttu-id="d4706-193">このオブジェクトの詳細については、コマンドを [Get Member](xref:Microsoft.PowerShell.Utility.Get-Member) コマンドレットにパイプ処理してください。</span><span class="sxs-lookup"><span data-stu-id="d4706-193">For more information about this object, pipe the command to the [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) cmdlet.</span></span> <span data-ttu-id="d4706-194">または、「 [System.security.accesscontrol.filesecurity](/dotnet/api/system.security.accesscontrol.filesecurity) クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4706-194">Or, see [FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) Class.</span></span>

### <a name="modify-the-acl-for-a-file"></a><span data-ttu-id="d4706-195">ファイルの ACL を変更する</span><span class="sxs-lookup"><span data-stu-id="d4706-195">Modify the ACL for a file</span></span>

### <a name="create-and-set-an-acl-for-a-file"></a><span data-ttu-id="d4706-196">ファイルの ACL を作成および設定する</span><span class="sxs-lookup"><span data-stu-id="d4706-196">Create and set an ACL for a file</span></span>

## <a name="creating-files-and-directories"></a><span data-ttu-id="d4706-197">ファイルとディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="d4706-197">Creating files and directories</span></span>

### <a name="create-a-directory"></a><span data-ttu-id="d4706-198">ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="d4706-198">Create a directory</span></span>

<span data-ttu-id="d4706-199">このコマンドにより、ドライブにディレクトリが作成され `logfiles` `C` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-199">This command creates the `logfiles` directory on the `C` drive:</span></span>

```powershell
New-Item -Path c:\ -Name logfiles -Type directory
```

<span data-ttu-id="d4706-200">PowerShell には、 `mkdir` `md` [new Item](xref:Microsoft.PowerShell.Management.New-Item) コマンドレットを使用して新しいディレクトリを作成する関数 (別名) も含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4706-200">PowerShell also includes a `mkdir` function (alias `md`) that uses the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to create a new directory.</span></span>

### <a name="create-a-file"></a><span data-ttu-id="d4706-201">ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d4706-201">Create a file</span></span>

<span data-ttu-id="d4706-202">このコマンドは、 `log2.txt` ディレクトリにファイルを作成し、 `C:\logfiles` ファイルに "test log" という文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="d4706-202">This command creates the `log2.txt` file in the `C:\logfiles` directory and then adds the "test log" string to the file:</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file
```

### <a name="create-a-file-with-content"></a><span data-ttu-id="d4706-203">コンテンツを持つファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d4706-203">Create a file with content</span></span>

<span data-ttu-id="d4706-204">ディレクトリにという名前のファイルを作成 `log2.txt` `C:\logfiles` し、ファイルに "test log" という文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="d4706-204">Creates a file called `log2.txt` in the `C:\logfiles` directory and adds the string "test log" to the file.</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file -Value "test log"
```

## <a name="renaming-files-and-directories"></a><span data-ttu-id="d4706-205">ファイルとディレクトリの名前の変更</span><span class="sxs-lookup"><span data-stu-id="d4706-205">Renaming files and directories</span></span>

### <a name="rename-a-file"></a><span data-ttu-id="d4706-206">ファイル名を変更する</span><span class="sxs-lookup"><span data-stu-id="d4706-206">Rename a file</span></span>

<span data-ttu-id="d4706-207">このコマンドにより `a.txt` 、ディレクトリ内のファイルの名前が次のように変更され `C:\a` `b.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-207">This command renames the `a.txt` file in the `C:\a` directory to `b.txt`:</span></span>

```powershell
Rename-Item -Path c:\a\a.txt -NewName b.txt
```

### <a name="rename-a-directory"></a><span data-ttu-id="d4706-208">ディレクトリ名の変更</span><span class="sxs-lookup"><span data-stu-id="d4706-208">Rename a directory</span></span>

<span data-ttu-id="d4706-209">このコマンドにより、ディレクトリの名前が次のように変更され `C:\a\cc` `C:\a\dd` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-209">This command renames the `C:\a\cc` directory to `C:\a\dd`:</span></span>

```powershell
Rename-Item -Path c:\a\cc -NewName dd
```

## <a name="deleting-files-and-directories"></a><span data-ttu-id="d4706-210">削除 (ファイルとディレクトリを)</span><span class="sxs-lookup"><span data-stu-id="d4706-210">Deleting files and directories</span></span>

### <a name="delete-a-file"></a><span data-ttu-id="d4706-211">ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="d4706-211">Delete a file</span></span>

<span data-ttu-id="d4706-212">このコマンドを実行すると、現在のディレクトリ内のファイルが削除され `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-212">This command deletes the `Test.txt` file in the current directory:</span></span>

```powershell
Remove-Item -Path test.txt
```

### <a name="delete-files-using-wildcards"></a><span data-ttu-id="d4706-213">ワイルドカードを使用してファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="d4706-213">Delete files using wildcards</span></span>

<span data-ttu-id="d4706-214">次のコマンドは、ファイル名拡張子を持つ現在のディレクトリ内のすべてのファイルを削除し `.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-214">This command deletes all the files in the current directory that have the `.xml` file name extension:</span></span>

```powershell
Remove-Item -Path *.xml
```

## <a name="starting-a-program-by-invoking-an-associated-file"></a><span data-ttu-id="d4706-215">関連付けられたファイルを呼び出してプログラムを起動する</span><span class="sxs-lookup"><span data-stu-id="d4706-215">Starting a program by invoking an associated file</span></span>

### <a name="invoke-a-file"></a><span data-ttu-id="d4706-216">ファイルを呼び出す</span><span class="sxs-lookup"><span data-stu-id="d4706-216">Invoke a file</span></span>

<span data-ttu-id="d4706-217">最初のコマンドは、 [Get Service](xref:Microsoft.PowerShell.Management.Get-Service) コマンドレットを使用して、ローカルサービスに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-217">The first command uses the [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) cmdlet to get information about local services.</span></span>

<span data-ttu-id="d4706-218">情報を [エクスポート Csv](xref:Microsoft.PowerShell.Utility.Export-Csv) コマンドレットにパイプし、その情報をファイルに格納し `Services.csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-218">It pipes the information to the [Export-Csv](xref:Microsoft.PowerShell.Utility.Export-Csv) cmdlet and then stores that information in the `Services.csv` file.</span></span>

<span data-ttu-id="d4706-219">2番目のコマンドは、 [呼び出し項目](xref:Microsoft.PowerShell.Management.Invoke-Item) を使用して、 `services.csv` 拡張機能に関連付けられているプログラムでファイルを開き `.csv` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-219">The second command uses [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) to open the `services.csv` file in the program associated with the `.csv` extension:</span></span>

```powershell
Get-Service | Export-Csv -Path services.csv
Invoke-Item -Path services.csv
```

## <a name="getting-files-and-folders-with-specified-attributes"></a><span data-ttu-id="d4706-220">指定された属性を持つファイルとフォルダーを取得する</span><span class="sxs-lookup"><span data-stu-id="d4706-220">Getting files and folders with specified attributes</span></span>

### <a name="get-system-files"></a><span data-ttu-id="d4706-221">システムファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="d4706-221">Get System files</span></span>

<span data-ttu-id="d4706-222">このコマンドを実行すると、現在のディレクトリとそのサブディレクトリにあるシステム ファイルが取得されます。</span><span class="sxs-lookup"><span data-stu-id="d4706-222">This command gets system files in the current directory and its subdirectories.</span></span>

<span data-ttu-id="d4706-223">パラメーターを使用して、 `-File` (ディレクトリではなく) ファイルのみを取得し、パラメーターを使用して `-System` "system" 属性を持つ項目のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-223">It uses the `-File` parameter to get only files (not directories) and the `-System` parameter to get only items with the "system" attribute.</span></span>

<span data-ttu-id="d4706-224">パラメーターを使用して、 `-Recurse` 現在のディレクトリとすべてのサブディレクトリ内の項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-224">It uses the `-Recurse` parameter to get the items in the current directory and all subdirectories.</span></span>

```powershell
Get-ChildItem -File -System -Recurse
```

### <a name="get-hidden-files"></a><span data-ttu-id="d4706-225">隠しファイルの取得</span><span class="sxs-lookup"><span data-stu-id="d4706-225">Get Hidden files</span></span>

<span data-ttu-id="d4706-226">このコマンドは、非表示ファイルを含む、現在のディレクトリにあるすべてのファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-226">This command gets all files, including hidden files, in the current directory.</span></span>

<span data-ttu-id="d4706-227">**Attributes** パラメーターには、 `!Directory+Hidden` 非表示ファイルを取得すると、 `!Directory` 他のすべてのファイルを取得するという2つの値があります。</span><span class="sxs-lookup"><span data-stu-id="d4706-227">It uses the **Attributes** parameter with two values, `!Directory+Hidden`, which gets hidden files, and `!Directory`, which gets all other files.</span></span>

```powershell
Get-ChildItem -Attributes !Directory,!Directory+Hidden
```

<span data-ttu-id="d4706-228">`dir -att !d,!d+h` は、このコマンドに相当します。</span><span class="sxs-lookup"><span data-stu-id="d4706-228">`dir -att !d,!d+h` is the equivalent of this command.</span></span>

### <a name="get-compressed-and-encrypted-files"></a><span data-ttu-id="d4706-229">圧縮されたファイルと暗号化されたファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="d4706-229">Get Compressed and Encrypted files</span></span>

<span data-ttu-id="d4706-230">このコマンドを実行すると、現在のディレクトリにあり、圧縮または暗号化されているファイルが取得されます。</span><span class="sxs-lookup"><span data-stu-id="d4706-230">This command gets files in the current directory that are either compressed or encrypted.</span></span>

<span data-ttu-id="d4706-231">`-Attributes`2 つの値 (と) を持つパラメーターを使用し `Compressed` `Encrypted` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-231">It uses the `-Attributes` parameter with two values, `Compressed` and `Encrypted`.</span></span> <span data-ttu-id="d4706-232">値は、 `,` "or" 演算子を表すコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="d4706-232">The values are separated by a comma `,` which represents the "OR" operator.</span></span>

```powershell
Get-ChildItem -Attributes Compressed,Encrypted
```

## <a name="dynamic-parameters"></a><span data-ttu-id="d4706-233">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="d4706-233">Dynamic parameters</span></span>

<span data-ttu-id="d4706-234">動的パラメーターは、PowerShell プロバイダーによって追加されるコマンドレットパラメーターであり、プロバイダーに対応したドライブでコマンドレットが使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-234">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="encoding-microsoftpowershellcommandsfilesystemcmdletproviderencoding"></a><span data-ttu-id="d4706-235">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span><span class="sxs-lookup"><span data-stu-id="d4706-235">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span></span>

<span data-ttu-id="d4706-236">ファイル エンコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4706-236">Specifies the file encoding.</span></span> <span data-ttu-id="d4706-237">既定値は ASCII です。</span><span class="sxs-lookup"><span data-stu-id="d4706-237">The default is ASCII.</span></span>

- <span data-ttu-id="d4706-238">**Ascii** : ascii (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4706-238">**ASCII** :  Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="d4706-239">**BigEndianUnicode** : ビッグエンディアンのバイト順を使用して utf-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d4706-239">**BigEndianUnicode** :  Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="d4706-240">**String** : 文字列のエンコーディングの種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4706-240">**String** :  Uses the encoding type for a string.</span></span>
- <span data-ttu-id="d4706-241">**Unicode** : リトルエンディアンのバイト順を使用して utf-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d4706-241">**Unicode** :  Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="d4706-242">**UTF7** : utf-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d4706-242">**UTF7** :   Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="d4706-243">**UTF8** : utf-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d4706-243">**UTF8** :  Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="d4706-244">**UTF8BOM** : バイト順マーク (BOM) を使用して utf-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d4706-244">**UTF8BOM** : Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d4706-245">**UF8NOBOM** : バイト順マーク (BOM) を使用せずに utf-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d4706-245">**UF8NOBOM** : Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d4706-246">**UTF32** :32 utf-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d4706-246">**UTF32** :  Encodes in UTF-32 format.</span></span>
- <span data-ttu-id="d4706-247">**既定** 値は、インストールされている既定のコードページでエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="d4706-247">**Default** : Encodes in the default installed code page.</span></span>
- <span data-ttu-id="d4706-248">**OEM** : MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4706-248">**OEM** : Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="d4706-249">**不明** : エンコードの種類が不明または無効です。</span><span class="sxs-lookup"><span data-stu-id="d4706-249">**Unknown** :  The encoding type is unknown or invalid.</span></span> <span data-ttu-id="d4706-250">データはバイナリとして処理できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-250">The data can be treated as binary.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-251">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-251">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-252">Add-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-252">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="d4706-253">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-253">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="d4706-254">Set-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-254">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="delimiter-systemstring"></a><span data-ttu-id="d4706-255">Delimiter \<System.String\></span><span class="sxs-lookup"><span data-stu-id="d4706-255">Delimiter \<System.String\></span></span>

<span data-ttu-id="d4706-256">[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) で使用され、読み込み中にファイルをオブジェクトに分割する区切り文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4706-256">Specifies the delimiter that [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) uses to divide the file into objects while it reads.</span></span>

<span data-ttu-id="d4706-257">既定値は `\n` 、行末文字です。</span><span class="sxs-lookup"><span data-stu-id="d4706-257">The default is `\n`, the end-of-line character.</span></span>

<span data-ttu-id="d4706-258">テキストファイルを読み取るときに、 [Get Content](xref:Microsoft.PowerShell.Management.Get-Content) は文字列オブジェクトのコレクションを返します。各オブジェクトは、区切り文字で終わります。</span><span class="sxs-lookup"><span data-stu-id="d4706-258">When reading a text file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns a collection of string objects, each of which ends with the delimiter character.</span></span>

<span data-ttu-id="d4706-259">ファイルに存在しない区切り文字を入力すると、 [Get Content](xref:Microsoft.PowerShell.Management.Get-Content) は、ファイル全体を単一の区切られていないオブジェクトとして返します。</span><span class="sxs-lookup"><span data-stu-id="d4706-259">Entering a delimiter that does not exist in the file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns the entire file as a single, un-delimited object.</span></span>

<span data-ttu-id="d4706-260">このパラメーターを使用し、大きなファイルを小さなファイルに分割します。「End of Example」のようなファイル区切り記号を区切り文字として指定します。</span><span class="sxs-lookup"><span data-stu-id="d4706-260">You can use this parameter to split a large file into smaller files by specifying a file separator, such as "End of Example", as the delimiter.</span></span> <span data-ttu-id="d4706-261">区切り文字は予約されています (破棄されません)。各ファイル セクションの最後の項目になります。</span><span class="sxs-lookup"><span data-stu-id="d4706-261">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

> [!NOTE]
> <span data-ttu-id="d4706-262">現在、パラメーターの値が空の文字列の場合、 `-Delimiter` [Get](xref:Microsoft.PowerShell.Management.Get-Content) は何も返しません。</span><span class="sxs-lookup"><span data-stu-id="d4706-262">Currently, when the value of the `-Delimiter` parameter is an empty string, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) does not return anything.</span></span>
> <span data-ttu-id="d4706-263">これは既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="d4706-263">This is a known issue.</span></span> <span data-ttu-id="d4706-264">ファイル全体を 1 つの区切りのない文字列として返すように [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) に強制するには、ファイルに存在しない値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4706-264">To force [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) to return the entire file as a single, undelimited string, enter a value that does not exist in the file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-265">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-265">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-266">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-266">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="wait-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d4706-267">Wait \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d4706-267">Wait \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d4706-268">コンテンツがファイルに追加されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="d4706-268">Waits for content to be appended to the file.</span></span> <span data-ttu-id="d4706-269">コンテンツが追加される場合、追加されたコンテンツを返します。</span><span class="sxs-lookup"><span data-stu-id="d4706-269">If content is appended, it returns the appended content.</span></span> <span data-ttu-id="d4706-270">コンテンツが変更された場合、ファイル全体が返されます。</span><span class="sxs-lookup"><span data-stu-id="d4706-270">If the content has changed, it returns the entire file.</span></span>

<span data-ttu-id="d4706-271">待機中に、[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) は 1 秒おきにファイルをチェックします。これは CTRL+C を押すなどして中断するまで続きます。</span><span class="sxs-lookup"><span data-stu-id="d4706-271">When waiting, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) checks the file once each second until you interrupt it, such as by pressing CTRL+C.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-272">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-272">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-273">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-273">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="attributes-flagsexpression"></a><span data-ttu-id="d4706-274">Attributes \<FlagsExpression\></span><span class="sxs-lookup"><span data-stu-id="d4706-274">Attributes \<FlagsExpression\></span></span>

<span data-ttu-id="d4706-275">指定した属性のファイルとフォルダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-275">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="d4706-276">このパラメーターはすべての属性をサポートします。複雑な属性の組み合わせを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-276">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="d4706-277">この `-Attributes` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4706-277">The `-Attributes` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d4706-278">パラメーターでは `-Attributes` 、次の属性がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d4706-278">The `-Attributes` parameter supports the following attributes:</span></span>

- <span data-ttu-id="d4706-279">**Archive**</span><span class="sxs-lookup"><span data-stu-id="d4706-279">**Archive**</span></span>
- <span data-ttu-id="d4706-280">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="d4706-280">**Compressed**</span></span>
- <span data-ttu-id="d4706-281">**[デバイス]**</span><span class="sxs-lookup"><span data-stu-id="d4706-281">**Device**</span></span>
- <span data-ttu-id="d4706-282">**ディレクトリ**</span><span class="sxs-lookup"><span data-stu-id="d4706-282">**Directory**</span></span>
- <span data-ttu-id="d4706-283">**Encrypted**</span><span class="sxs-lookup"><span data-stu-id="d4706-283">**Encrypted**</span></span>
- <span data-ttu-id="d4706-284">**[非表示]**</span><span class="sxs-lookup"><span data-stu-id="d4706-284">**Hidden**</span></span>
- <span data-ttu-id="d4706-285">**標準**</span><span class="sxs-lookup"><span data-stu-id="d4706-285">**Normal**</span></span>
- <span data-ttu-id="d4706-286">**NotContentIndexed**</span><span class="sxs-lookup"><span data-stu-id="d4706-286">**NotContentIndexed**</span></span>
- <span data-ttu-id="d4706-287">**なっ**</span><span class="sxs-lookup"><span data-stu-id="d4706-287">**Offline**</span></span>
- <span data-ttu-id="d4706-288">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="d4706-288">**ReadOnly**</span></span>
- <span data-ttu-id="d4706-289">**ReparsePoint**</span><span class="sxs-lookup"><span data-stu-id="d4706-289">**ReparsePoint**</span></span>
- <span data-ttu-id="d4706-290">**Sparc ファイル**</span><span class="sxs-lookup"><span data-stu-id="d4706-290">**SparseFile**</span></span>
- <span data-ttu-id="d4706-291">**システム**</span><span class="sxs-lookup"><span data-stu-id="d4706-291">**System**</span></span>
- <span data-ttu-id="d4706-292">**一時**</span><span class="sxs-lookup"><span data-stu-id="d4706-292">**Temporary**</span></span>

<span data-ttu-id="d4706-293">これらの属性の詳細については、「 [Fileattributes](/dotnet/api/system.io.fileattributes) 列挙型」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4706-293">For a description of these attributes, see the [FileAttributes](/dotnet/api/system.io.fileattributes) enumeration.</span></span>

<span data-ttu-id="d4706-294">次の演算子を利用して属性を結合します。</span><span class="sxs-lookup"><span data-stu-id="d4706-294">Use the following operators to combine attributes.</span></span>

- <span data-ttu-id="d4706-295">`!` -NOT</span><span class="sxs-lookup"><span data-stu-id="d4706-295">`!` - NOT</span></span>
- <span data-ttu-id="d4706-296">`+` -および</span><span class="sxs-lookup"><span data-stu-id="d4706-296">`+` - AND</span></span>
- <span data-ttu-id="d4706-297">`,` または</span><span class="sxs-lookup"><span data-stu-id="d4706-297">`,` - OR</span></span>

<span data-ttu-id="d4706-298">演算子とその属性の間にはスペースを挿入できません。</span><span class="sxs-lookup"><span data-stu-id="d4706-298">No spaces are permitted between an operator and its attribute.</span></span> <span data-ttu-id="d4706-299">ただし、コンマの前にはスペースを挿入できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-299">However, spaces are permitted before commas.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-300">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-300">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-301">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d4706-301">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="directory-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d4706-302">Directory \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d4706-302">Directory \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d4706-303">ディレクトリ (フォルダー) を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-303">Gets directories (folders).</span></span>

<span data-ttu-id="d4706-304">この `-Directory` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4706-304">The `-Directory` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d4706-305">ディレクトリだけを取得するには、パラメーターを使用 `-Directory` してパラメーターを省略し `-File` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-305">To get only directories, use the `-Directory` parameter and omit the `-File` parameter.</span></span> <span data-ttu-id="d4706-306">ディレクトリを除外するには、パラメーターを使用 `-File` してパラメーターを省略する `-Directory` か、パラメーターを使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-306">To exclude directories, use the `-File` parameter and omit the `-Directory` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-307">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-307">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-308">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d4706-308">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="file-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d4706-309">File \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d4706-309">File \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d4706-310">ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-310">Gets files.</span></span>

<span data-ttu-id="d4706-311">この `-File` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4706-311">The `-File` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d4706-312">ファイルのみを取得するには、パラメーターを使用 `-File` してパラメーターを省略し `-Directory` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-312">To get only files, use the `-File` parameter and omit the `-Directory` parameter.</span></span> <span data-ttu-id="d4706-313">ファイルを除外するには、パラメーターを使用 `-Directory` してパラメーターを省略する `-File` か、パラメーターを使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-313">To exclude files, use the `-Directory` parameter and omit the `-File` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-314">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-314">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-315">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d4706-315">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="hidden-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d4706-316">Hidden \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d4706-316">Hidden \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d4706-317">非表示のファイルとディレクトリ (フォルダー) のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-317">Gets only hidden files and directories (folders).</span></span> <span data-ttu-id="d4706-318">既定では、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem) は非表示項目のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-318">By default, [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) gets only non-hidden items.</span></span>

<span data-ttu-id="d4706-319">この `-Hidden` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4706-319">The `-Hidden` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d4706-320">非表示の項目のみを取得するには、パラメーター、 `-Hidden` その `h` または `ah` 別名、またはパラメーターの **非表示** の値を使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-320">To get only hidden items, use the `-Hidden` parameter, its `h` or `ah` aliases, or the **Hidden** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="d4706-321">非表示の項目を除外するには、パラメーターを省略する `-Hidden` か、パラメーターを使用 `-Attributes` します。</span><span class="sxs-lookup"><span data-stu-id="d4706-321">To exclude hidden items, omit the `-Hidden` parameter or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-322">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-322">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-323">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d4706-323">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="readonly-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d4706-324">ReadOnly \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d4706-324">ReadOnly \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d4706-325">読み取り専用のファイルとディレクトリ (フォルダー) を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-325">Gets only read-only files and directories (folders).</span></span>

<span data-ttu-id="d4706-326">この `-ReadOnly` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4706-326">The `-ReadOnly` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d4706-327">読み取り専用の項目だけを取得するには、パラメーター、 `-ReadOnly` その `ar` エイリアス、またはパラメーターの **ReadOnly** 値を使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-327">To get only read-only items, use the `-ReadOnly` parameter, its `ar` alias, or the **ReadOnly** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="d4706-328">読み取り専用の項目を除外するには、パラメーターを使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-328">To exclude read-only items, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-329">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-329">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-330">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d4706-330">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="system-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d4706-331">System \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d4706-331">System \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d4706-332">システムのファイルとディレクトリ (フォルダー) を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4706-332">Gets only system files and directories (folders).</span></span>

<span data-ttu-id="d4706-333">この `-System` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4706-333">The `-System` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d4706-334">システムファイルとフォルダーのみを取得するには、パラメーター、 `-System` その `as` エイリアス、またはパラメーターの **システム** 値を使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-334">To get only system files and folders, use the `-System` parameter, its `as` alias, or the **System** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="d4706-335">システムファイルとフォルダーを除外するには、パラメーターを使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-335">To exclude system files and folders, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-336">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-336">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-337">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d4706-337">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="newerthan-systemdatetime"></a><span data-ttu-id="d4706-338">NewerThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="d4706-338">NewerThan \<System.DateTime\></span></span>

<span data-ttu-id="d4706-339">`$True` `LastWriteTime` ファイルの値が指定した日付よりも大きい場合に、を返します。</span><span class="sxs-lookup"><span data-stu-id="d4706-339">Returns `$True` when the `LastWriteTime` value of a file is greater than the specified date.</span></span> <span data-ttu-id="d4706-340">それ以外の場合は、 `$False`を返します。</span><span class="sxs-lookup"><span data-stu-id="d4706-340">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="d4706-341">[Datetime](/dotnet/api/system.datetime)オブジェクトを入力します。たとえば、 [Get Date](xref:Microsoft.PowerShell.Utility.Get-Date)コマンドレットが返す値や、 [datetime](/dotnet/api/system.datetime)オブジェクトに変換できる文字列 (など) を入力し `"August 10, 2011 2:00 PM"` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-341">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-342">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-342">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-343">Test-Path</span><span class="sxs-lookup"><span data-stu-id="d4706-343">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="olderthan-systemdatetime"></a><span data-ttu-id="d4706-344">OlderThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="d4706-344">OlderThan \<System.DateTime\></span></span>

<span data-ttu-id="d4706-345">`$True` `LastWriteTime` ファイルの値が指定した日付よりも小さい場合に、を返します。</span><span class="sxs-lookup"><span data-stu-id="d4706-345">Returns `$True` when the `LastWriteTime` value of a file is less than the specified date.</span></span> <span data-ttu-id="d4706-346">それ以外の場合は、 `$False`を返します。</span><span class="sxs-lookup"><span data-stu-id="d4706-346">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="d4706-347">[Datetime](/dotnet/api/system.datetime)オブジェクトを入力します。たとえば、 [Get Date](xref:Microsoft.PowerShell.Utility.Get-Date)コマンドレットが返す値や、 [datetime](/dotnet/api/system.datetime)オブジェクトに変換できる文字列 (など) を入力し `"August 10, 2011 2:00 PM"` ます。</span><span class="sxs-lookup"><span data-stu-id="d4706-347">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-348">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-348">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-349">Test-Path</span><span class="sxs-lookup"><span data-stu-id="d4706-349">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="stream-systemstring"></a><span data-ttu-id="d4706-350">Stream \<System.String\></span><span class="sxs-lookup"><span data-stu-id="d4706-350">Stream \<System.String\></span></span>

<span data-ttu-id="d4706-351">代替データ ストリームを管理します。</span><span class="sxs-lookup"><span data-stu-id="d4706-351">Manages alternate data streams.</span></span> <span data-ttu-id="d4706-352">ストリーム名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4706-352">Enter the stream name.</span></span> <span data-ttu-id="d4706-353">ワイルドカードは、ファイルシステムドライブ内の項目の [取得](xref:Microsoft.PowerShell.Management.Get-Item) および [削除](xref:Microsoft.PowerShell.Management.Remove-Item) コマンドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4706-353">Wildcards are permitted only in [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) for and [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) commands in a file system drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-354">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-354">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-355">Add-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-355">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="d4706-356">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-356">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="d4706-357">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-357">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="d4706-358">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-358">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="d4706-359">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-359">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="d4706-360">Set-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-360">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="raw-switchparameter"></a><span data-ttu-id="d4706-361">Raw \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d4706-361">Raw \<SwitchParameter\></span></span>

<span data-ttu-id="d4706-362">改行文字が無視されます。</span><span class="sxs-lookup"><span data-stu-id="d4706-362">Ignores newline characters.</span></span> <span data-ttu-id="d4706-363">コンテンツを 1 つの項目として返します。</span><span class="sxs-lookup"><span data-stu-id="d4706-363">Returns contents as a single item.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-364">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-364">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-365">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d4706-365">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="itemtype-string"></a><span data-ttu-id="d4706-366">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="d4706-366">ItemType \<String\></span></span>

<span data-ttu-id="d4706-367">このパラメーターを使用すると、作成する項目の tye を指定できます。 `New-Item`</span><span class="sxs-lookup"><span data-stu-id="d4706-367">This parameter allows you to specify the tye of item to create with `New-Item`</span></span>

<span data-ttu-id="d4706-368">このパラメーターで使用できる値は、使用している現在のプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d4706-368">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="d4706-369">ドライブでは、 `FileSystem` 次の値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="d4706-369">In a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="d4706-370">ファイル</span><span class="sxs-lookup"><span data-stu-id="d4706-370">File</span></span>
- <span data-ttu-id="d4706-371">ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="d4706-371">Directory</span></span>
- <span data-ttu-id="d4706-372">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="d4706-372">SymbolicLink</span></span>
- <span data-ttu-id="d4706-373">ジャンクション</span><span class="sxs-lookup"><span data-stu-id="d4706-373">Junction</span></span>
- <span data-ttu-id="d4706-374">Hardlink create</span><span class="sxs-lookup"><span data-stu-id="d4706-374">HardLink</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="d4706-375">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d4706-375">Cmdlets supported</span></span>

- [<span data-ttu-id="d4706-376">New-Item</span><span class="sxs-lookup"><span data-stu-id="d4706-376">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="d4706-377">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="d4706-377">Using the pipeline</span></span>

<span data-ttu-id="d4706-378">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d4706-378">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="d4706-379">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d4706-379">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="d4706-380">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4706-380">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="d4706-381">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="d4706-381">Getting help</span></span>

<span data-ttu-id="d4706-382">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="d4706-382">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="d4706-383">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するには、ファイルシステムドライブで [get-help](xref:Microsoft.PowerShell.Core.Get-Help) コマンドを実行するか、 `-Path` [get-help](xref:Microsoft.PowerShell.Core.Get-Help) のパラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4706-383">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path c:
```

## <a name="see-also"></a><span data-ttu-id="d4706-384">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4706-384">See also</span></span>

[<span data-ttu-id="d4706-385">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d4706-385">about_Providers</span></span>](../About/about_Providers.md)
