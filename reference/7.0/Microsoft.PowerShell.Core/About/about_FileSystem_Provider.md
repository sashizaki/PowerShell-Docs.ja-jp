---
description: FileSystem (ファイル システム)
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_filesystem_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: FileSystem プロバイダー
ms.openlocfilehash: 085d714fce8475dd3eeee656d1cd17db02e772a6
ms.sourcegitcommit: 7f712e12ec5b3f3f3e695da804b050ea0ce58b3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "94661394"
---
# <a name="filesystem-provider"></a><span data-ttu-id="6e8bc-104">FileSystem プロバイダー</span><span class="sxs-lookup"><span data-stu-id="6e8bc-104">FileSystem provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="6e8bc-105">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="6e8bc-105">Provider name</span></span>

<span data-ttu-id="6e8bc-106">FileSystem (ファイル システム)</span><span class="sxs-lookup"><span data-stu-id="6e8bc-106">FileSystem</span></span>

## <a name="drives"></a><span data-ttu-id="6e8bc-107">ドライブ</span><span class="sxs-lookup"><span data-stu-id="6e8bc-107">Drives</span></span>

<span data-ttu-id="6e8bc-108">`C:`, `D:` ...</span><span class="sxs-lookup"><span data-stu-id="6e8bc-108">`C:`, `D:` ...</span></span>

## <a name="capabilities"></a><span data-ttu-id="6e8bc-109">機能</span><span class="sxs-lookup"><span data-stu-id="6e8bc-109">Capabilities</span></span>

<span data-ttu-id="6e8bc-110">**フィルター\*\*\*\*処理**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-110">**Filter**, **ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="6e8bc-111">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6e8bc-111">Short description</span></span>

<span data-ttu-id="6e8bc-112">ファイルとディレクトリへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-112">Provides access to files and directories.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="6e8bc-113">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="6e8bc-113">Detailed description</span></span>

<span data-ttu-id="6e8bc-114">PowerShell **FileSystem** プロバイダーを使用すると、powershell でファイルとディレクトリを取得、追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-114">The PowerShell **FileSystem** provider lets you get, add, change, clear, and delete files and directories in PowerShell.</span></span>

<span data-ttu-id="6e8bc-115">**ファイルシステム** ドライブは、コンピューター上のディレクトリとファイルを含む階層型の名前空間です。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-115">The **FileSystem** drives are a hierarchical namespace containing the directories and files on your computer.</span></span> <span data-ttu-id="6e8bc-116">**ファイルシステム** ドライブには、論理ドライブまたは物理ドライブ、ディレクトリ、またはマップされたネットワーク共有を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-116">A **FileSystem** drive can be a logical or physical drive, directory, or mapped network share.</span></span>

<span data-ttu-id="6e8bc-117">という名前のドライブが `TEMP:` ユーザーの一時ディレクトリパスにマップされます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-117">A drive called `TEMP:` will be mapped to the user's temporary directory path.</span></span>

>[!NOTE]
> <span data-ttu-id="6e8bc-118">TEMP: ドライブの内容は、PowerShell によって自動的に削除されることはなく、管理するユーザーまたはオペレーティングシステムによって行われます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-118">Contents in the TEMP: drive are not automatically removed by PowerShell and is up to the user or operating system to manage.</span></span> <span data-ttu-id="6e8bc-119">この機能は、PowerShell バージョン7.0 の試験的な機能から移行されました。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-119">This Feature was moved out of experimental features in PowerShell Version 7.0</span></span>

<span data-ttu-id="6e8bc-120">**FileSystem** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-120">The **FileSystem** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="6e8bc-121">Get-Location</span><span class="sxs-lookup"><span data-stu-id="6e8bc-121">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="6e8bc-122">Set-Location</span><span class="sxs-lookup"><span data-stu-id="6e8bc-122">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="6e8bc-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-123">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="6e8bc-124">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6e8bc-124">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="6e8bc-125">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-125">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="6e8bc-126">Move-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-126">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="6e8bc-127">New-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-127">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="6e8bc-128">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-128">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="6e8bc-129">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6e8bc-129">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="6e8bc-130">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6e8bc-130">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="6e8bc-131">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-131">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="6e8bc-132">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6e8bc-132">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="6e8bc-133">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-133">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="6e8bc-134">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="6e8bc-134">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="6e8bc-135">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="6e8bc-135">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="6e8bc-136">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="6e8bc-136">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)
- [<span data-ttu-id="6e8bc-137">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="6e8bc-137">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="6e8bc-138">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="6e8bc-138">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="6e8bc-139">このプロバイダーによって公開される型</span><span class="sxs-lookup"><span data-stu-id="6e8bc-139">Types exposed by this provider</span></span>

<span data-ttu-id="6e8bc-140">ファイルは、 [system.servicemodel クラスのインスタンスです。](/dotnet/api/system.io.fileinfo)</span><span class="sxs-lookup"><span data-stu-id="6e8bc-140">Files are instances of the [System.IO.FileInfo](/dotnet/api/system.io.fileinfo) class.</span></span> <span data-ttu-id="6e8bc-141">ディレクトリは、 [DirectoryInfo](/dotnet/api/system.io.directoryinfo) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-141">Directories are instances of the [System.IO.DirectoryInfo](/dotnet/api/system.io.directoryinfo) class.</span></span>

## <a name="navigating-the-filesystem-drives"></a><span data-ttu-id="6e8bc-142">ファイルシステムドライブの移動</span><span class="sxs-lookup"><span data-stu-id="6e8bc-142">Navigating the FileSystem drives</span></span>

<span data-ttu-id="6e8bc-143">**FileSystem** プロバイダーは、コンピューター上のすべての論理ドライブを PowerShell ドライブとしてマップすることによって、そのデータストアを公開します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-143">The **FileSystem** provider exposes its data stores by mapping any logical drives on the computer as PowerShell drives.</span></span> <span data-ttu-id="6e8bc-144">**ファイルシステム** ドライブを操作するには、ドライブ名の後にコロン () を使用して、場所をドライブに変更し `:` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-144">To work with a **FileSystem** drive you can change your location to a drive using the drive name followed by a colon (`:`).</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="6e8bc-145">他の PowerShell ドライブから **FileSystem** プロバイダーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-145">You can also work with the **FileSystem** provider from any other PowerShell drive.</span></span> <span data-ttu-id="6e8bc-146">別の場所からファイルまたはディレクトリを参照するには、パスのドライブ名 ( `C:` 、 `D:` 、...) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-146">To reference a file or directory from another location, use the drive name (`C:`, `D:`, ...) in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="6e8bc-147">PowerShell では、エイリアスを使用して、プロバイダーパスを操作するための使い慣れた方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-147">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="6e8bc-148">`dir`やなどのコマンド `ls` は、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)のエイリアスです。これ `cd` は、 [Set Location](xref:Microsoft.PowerShell.Management.Set-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-148">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="6e8bc-149">と `pwd` は、 [Get Location](xref:Microsoft.PowerShell.Management.Get-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-149">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-files-and-directories"></a><span data-ttu-id="6e8bc-150">ファイルとディレクトリの取得</span><span class="sxs-lookup"><span data-stu-id="6e8bc-150">Getting files and directories</span></span>

<span data-ttu-id="6e8bc-151">この `Get-ChildItem` コマンドレットは、現在の場所にあるすべてのファイルとディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-151">The `Get-ChildItem` cmdlet returns all files and directories in the current location.</span></span> <span data-ttu-id="6e8bc-152">別のパスを指定して、組み込みパラメーターを検索して使用し、再帰の深さをフィルター処理したり制御したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-152">You can specify a different path to search and use built in parameters to filter and control the recursion depth.</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="6e8bc-153">コマンドレットの使用方法の詳細については、「 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-153">To read more about cmdlet usage, see [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span></span>

## <a name="copying-files-and-directories"></a><span data-ttu-id="6e8bc-154">ファイルとディレクトリのコピー</span><span class="sxs-lookup"><span data-stu-id="6e8bc-154">Copying files and directories</span></span>

<span data-ttu-id="6e8bc-155">`Copy-Item`コマンドレットは、指定した場所にファイルとディレクトリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-155">The `Copy-Item` cmdlet copies files and directories to a location you specify.</span></span>
<span data-ttu-id="6e8bc-156">パラメーターは、のようにフィルターと再帰に使用でき `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-156">Parameters are available to filter and recurse, similar to `Get-ChildItem`.</span></span>

<span data-ttu-id="6e8bc-157">次のコマンドは、パス "C:\temp" の下にあるすべてのファイルとディレクトリ \" をフォルダー "C:\Windows\Temp" にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-157">The following command copies all of the files and directories under the path "C:\temp\" to the folder "C:\Windows\Temp".</span></span>

```powershell
Copy-Item -Path C:\temp\* -Destination C:\Windows\Temp -Recurse -File
```

<span data-ttu-id="6e8bc-158">`Copy-Item` 確認メッセージを表示せずに、宛先ディレクトリ内のファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-158">`Copy-Item` overwrites files in the destination directory without prompting for confirmation.</span></span>

<span data-ttu-id="6e8bc-159">このコマンドは、 `a.txt` ディレクトリからディレクトリにファイルをコピーし `C:\a` `C:\a\bb` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-159">This command copies the `a.txt` file from the `C:\a` directory to the `C:\a\bb` directory.</span></span>

```powershell
Copy-Item -Path C:\a\a.txt -Destination C:\a\bb\a.txt
```

<span data-ttu-id="6e8bc-160">ディレクトリ内のすべてのディレクトリとファイル `C:\a` をディレクトリにコピーし `C:\c` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-160">Copies all the directories and files in the `C:\a` directory to the `C:\c` directory.</span></span> <span data-ttu-id="6e8bc-161">コピーするディレクトリがコピー先ディレクトリにすでに存在する場合、Force パラメーターを指定しないとコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-161">If any of the directories to copy already exist in the destination directory, the command will fail unless you specify the Force parameter.</span></span>

```powershell
Copy-Item -Path C:\a\* -Destination C:\c -Recurse
```

<span data-ttu-id="6e8bc-162">詳細については、「 [コピー項目](xref:Microsoft.PowerShell.Management.Copy-Item)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-162">For more information, see [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span></span>

## <a name="moving-files-and-directories"></a><span data-ttu-id="6e8bc-163">ファイルとディレクトリの移動</span><span class="sxs-lookup"><span data-stu-id="6e8bc-163">Moving files and directories</span></span>

<span data-ttu-id="6e8bc-164">このコマンドは、 `c.txt` ディレクトリ内のファイル `C:\a` をディレクトリに移動し `C:\a\aa` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-164">This command moves the `c.txt` file in the `C:\a` directory to the `C:\a\aa` directory:</span></span>

```powershell
Move-Item -Path C:\a\c.txt -Destination C:\a\aa
```

<span data-ttu-id="6e8bc-165">このコマンドを実行して同じ名前を持つ既存ファイルが自動的に上書きされることはありません。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-165">The command will not automatically overwrite an existing file that has the same name.</span></span> <span data-ttu-id="6e8bc-166">既存ファイルを上書きするようにコマンドレットに強制するには、Force パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-166">To force the cmdlet to overwrite an existing file, specify the Force parameter.</span></span>

<span data-ttu-id="6e8bc-167">ディレクトリが現在の場所のとき、そのディレクトリを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-167">You cannot move a directory when that directory is the current location.</span></span> <span data-ttu-id="6e8bc-168">を使用し `Move-Item` てディレクトリを現在の場所に移動すると、このエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-168">When you use `Move-Item` to move the directory at the current location, you see this error.</span></span>

```
C:\temp> Move-Item -Path C:\temp\ -Destination C:\Windows\Temp

Move-Item : Cannot move item because the item at 'C:\temp\' is in use.
At line:1 char:1
+ Move-Item C:\temp\ C:\temp2\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Move-Item], PSInvalidOperationException
    + FullyQualifiedErrorId : InvalidOperation,Microsoft.PowerShell.Commands.MoveItemCommand
```

## <a name="managing-file-content"></a><span data-ttu-id="6e8bc-169">ファイルコンテンツの管理</span><span class="sxs-lookup"><span data-stu-id="6e8bc-169">Managing file content</span></span>

### <a name="get-the-content-of-a-file"></a><span data-ttu-id="6e8bc-170">ファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-170">Get the content of a file</span></span>

<span data-ttu-id="6e8bc-171">このコマンドは、"Test.txt" ファイルの内容を取得し、コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-171">This command gets the contents of the "Test.txt" file and displays them in the console.</span></span>

```powershell
Get-Content -Path Test.txt
```

<span data-ttu-id="6e8bc-172">ファイルのコンテンツを別のコマンドレットにパイプで送ることができます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-172">You can pipe the contents of the file to another cmdlet.</span></span> <span data-ttu-id="6e8bc-173">たとえば、次のコマンドは、ファイルの内容を読み取っ `Test.txt` て、 [convertto-html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) コマンドレットへの入力として提供します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-173">For example, the following command reads the contents of the `Test.txt` file and then supplies them as input to the [ConvertTo-Html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) cmdlet:</span></span>

```powershell
Get-Content -Path Test.txt | ConvertTo-Html
```

<span data-ttu-id="6e8bc-174">プロバイダーのパスにドル記号 () を付けることで、ファイルの内容を取得することもでき `$` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-174">You can also retrieve the content of a file by prefixing its provider path with the dollar sign (`$`).</span></span> <span data-ttu-id="6e8bc-175">パスは、変数の名前付けの制限により、中かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-175">The path must be enclosed in curly braces due to variable naming restrictions.</span></span> <span data-ttu-id="6e8bc-176">詳細については、「 [about_Variables](about_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-176">For more information, see [about_Variables](about_Variables.md).</span></span>

```powershell
${C:\Windows\System32\Drivers\etc\hosts}
```

### <a name="add-content-to-a-file"></a><span data-ttu-id="6e8bc-177">ファイルにコンテンツを追加する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-177">Add content to a file</span></span>

<span data-ttu-id="6e8bc-178">このコマンドは、ファイルに "test content" という文字列を追加し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-178">This command appends the "test content" string to the `Test.txt` file:</span></span>

```powershell
Add-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="6e8bc-179">ファイル内の既存のコンテンツ `Test.txt` は削除されません。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-179">The existing content in the `Test.txt` file is not deleted.</span></span>

### <a name="replace-the-content-of-a-file"></a><span data-ttu-id="6e8bc-180">ファイルの内容を置き換える</span><span class="sxs-lookup"><span data-stu-id="6e8bc-180">Replace the content of a file</span></span>

<span data-ttu-id="6e8bc-181">このコマンドは、ファイルの内容を `Test.txt` "test content" 文字列に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-181">This command replaces the contents of the `Test.txt` file with the "test content" string:</span></span>

```powershell
Set-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="6e8bc-182">の内容を上書き `Test.txt` します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-182">It overwrites the contents of `Test.txt`.</span></span> <span data-ttu-id="6e8bc-183">[新しい項目](xref:Microsoft.PowerShell.Management.New-Item)のコマンドレットの **Value** パラメーターを使用して、作成時にファイルにコンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-183">You can use the **Value** parameter of the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to add content to a file when you create it.</span></span>

### <a name="loop-through-the-contents-of-a-file"></a><span data-ttu-id="6e8bc-184">ファイルの内容をループする</span><span class="sxs-lookup"><span data-stu-id="6e8bc-184">Loop through the contents of a file</span></span>

<span data-ttu-id="6e8bc-185">既定では、 `Get-Content` コマンドレットは行末文字を区切り記号として使用するため、ファイルを文字列のコレクションとして取得し、各行をファイル内の1つの文字列として取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-185">By default, the `Get-Content` cmdlet uses the end-of-line character as its delimiter, so it gets a file as a collection of strings, with each line as one string in the file.</span></span>

<span data-ttu-id="6e8bc-186">パラメーターを使用して、 `-Delimiter` 別の区切り記号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-186">You can use the `-Delimiter` parameter to specify an alternate delimiter.</span></span> <span data-ttu-id="6e8bc-187">区切り文字をセクションの終わりか次のセクションの始まりを示す文字に設定した場合、ファイルを論理部分に分割できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-187">If you set it to the characters that denote the end of a section or the beginning of the next section, you can split the file into logical parts.</span></span>

<span data-ttu-id="6e8bc-188">最初のコマンドは、 `Employees.txt` ファイルを取得し、セクションに分割します。各セクションは "end Of Employee Record" という語で終わり、変数に保存さ `$e` れます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-188">The first command gets the `Employees.txt` file and splits it into sections, each of which ends with the words "End of Employee Record" and it saves it in the `$e` variable.</span></span>

<span data-ttu-id="6e8bc-189">2番目のコマンドは、配列表記を使用して、のコレクション内の最初の項目を取得し `$e` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-189">The second command uses array notation to get the first item in the collection in `$e`.</span></span> <span data-ttu-id="6e8bc-190">PowerShell 配列は0から始まるため、0のインデックスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-190">It uses an index of 0, because PowerShell arrays are zero-based.</span></span>

<span data-ttu-id="6e8bc-191">コマンドレットの詳細については、「」を `Get-Content` 参照 [し](xref:Microsoft.PowerShell.Management.Get-Content)てください。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-191">For more information about `Get-Content` cmdlet, see the help topic for the [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).</span></span>

<span data-ttu-id="6e8bc-192">配列の詳細については、「 [about_Arrays](../About/about_Arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-192">For more information about arrays, see [about_Arrays](../About/about_Arrays.md).</span></span>

```powershell
$e = Get-Content c:\test\employees.txt -Delimited "End Of Employee Record"
$e[0]
```

## <a name="managing-security-descriptors"></a><span data-ttu-id="6e8bc-193">セキュリティ記述子の管理</span><span class="sxs-lookup"><span data-stu-id="6e8bc-193">Managing security descriptors</span></span>

### <a name="view-the-acl-for-a-file"></a><span data-ttu-id="6e8bc-194">ファイルの ACL を表示する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-194">View the ACL for a file</span></span>

<span data-ttu-id="6e8bc-195">このコマンドは、 [accesscontrol-namespace. system.security.accesscontrol.filesecurity](/dotnet/api/system.security.accesscontrol.filesecurity) オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-195">This command returns a [System.Security.AccessControl.FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) object:</span></span>

```powershell
Get-Acl -Path test.txt | Format-List -Property *
```

<span data-ttu-id="6e8bc-196">このオブジェクトの詳細については、コマンドを [Get Member](xref:Microsoft.PowerShell.Utility.Get-Member) コマンドレットにパイプ処理してください。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-196">For more information about this object, pipe the command to the [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) cmdlet.</span></span> <span data-ttu-id="6e8bc-197">または、「 [System.security.accesscontrol.filesecurity](/dotnet/api/system.security.accesscontrol.filesecurity) クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-197">Or, see [FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) Class.</span></span>

### <a name="modify-the-acl-for-a-file"></a><span data-ttu-id="6e8bc-198">ファイルの ACL を変更する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-198">Modify the ACL for a file</span></span>

### <a name="create-and-set-an-acl-for-a-file"></a><span data-ttu-id="6e8bc-199">ファイルの ACL を作成および設定する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-199">Create and set an ACL for a file</span></span>

## <a name="creating-files-and-directories"></a><span data-ttu-id="6e8bc-200">ファイルとディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="6e8bc-200">Creating files and directories</span></span>

### <a name="create-a-directory"></a><span data-ttu-id="6e8bc-201">ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-201">Create a directory</span></span>

<span data-ttu-id="6e8bc-202">このコマンドにより、ドライブにディレクトリが作成され `logfiles` `C` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-202">This command creates the `logfiles` directory on the `C` drive:</span></span>

```powershell
New-Item -Path c:\ -Name logfiles -Type directory
```

<span data-ttu-id="6e8bc-203">PowerShell には、 `mkdir` `md` [new Item](xref:Microsoft.PowerShell.Management.New-Item) コマンドレットを使用して新しいディレクトリを作成する関数 (別名) も含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-203">PowerShell also includes a `mkdir` function (alias `md`) that uses the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to create a new directory.</span></span>

### <a name="create-a-file"></a><span data-ttu-id="6e8bc-204">ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-204">Create a file</span></span>

<span data-ttu-id="6e8bc-205">このコマンドは、 `log2.txt` ディレクトリにファイルを作成し、 `C:\logfiles` ファイルに "test log" という文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-205">This command creates the `log2.txt` file in the `C:\logfiles` directory and then adds the "test log" string to the file:</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file
```

### <a name="create-a-file-with-content"></a><span data-ttu-id="6e8bc-206">コンテンツを持つファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-206">Create a file with content</span></span>

<span data-ttu-id="6e8bc-207">ディレクトリにという名前のファイルを作成 `log2.txt` `C:\logfiles` し、ファイルに "test log" という文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-207">Creates a file called `log2.txt` in the `C:\logfiles` directory and adds the string "test log" to the file.</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file -Value "test log"
```

## <a name="renaming-files-and-directories"></a><span data-ttu-id="6e8bc-208">ファイルとディレクトリの名前の変更</span><span class="sxs-lookup"><span data-stu-id="6e8bc-208">Renaming files and directories</span></span>

### <a name="rename-a-file"></a><span data-ttu-id="6e8bc-209">ファイル名を変更する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-209">Rename a file</span></span>

<span data-ttu-id="6e8bc-210">このコマンドにより `a.txt` 、ディレクトリ内のファイルの名前が次のように変更され `C:\a` `b.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-210">This command renames the `a.txt` file in the `C:\a` directory to `b.txt`:</span></span>

```powershell
Rename-Item -Path c:\a\a.txt -NewName b.txt
```

### <a name="rename-a-directory"></a><span data-ttu-id="6e8bc-211">ディレクトリ名の変更</span><span class="sxs-lookup"><span data-stu-id="6e8bc-211">Rename a directory</span></span>

<span data-ttu-id="6e8bc-212">このコマンドにより、ディレクトリの名前が次のように変更され `C:\a\cc` `C:\a\dd` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-212">This command renames the `C:\a\cc` directory to `C:\a\dd`:</span></span>

```powershell
Rename-Item -Path c:\a\cc -NewName dd
```

## <a name="deleting-files-and-directories"></a><span data-ttu-id="6e8bc-213">削除 (ファイルとディレクトリを)</span><span class="sxs-lookup"><span data-stu-id="6e8bc-213">Deleting files and directories</span></span>

### <a name="delete-a-file"></a><span data-ttu-id="6e8bc-214">ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-214">Delete a file</span></span>

<span data-ttu-id="6e8bc-215">このコマンドを実行すると、現在のディレクトリ内のファイルが削除され `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-215">This command deletes the `Test.txt` file in the current directory:</span></span>

```powershell
Remove-Item -Path test.txt
```

### <a name="delete-files-using-wildcards"></a><span data-ttu-id="6e8bc-216">ワイルドカードを使用してファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-216">Delete files using wildcards</span></span>

<span data-ttu-id="6e8bc-217">次のコマンドは、ファイル名拡張子を持つ現在のディレクトリ内のすべてのファイルを削除し `.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-217">This command deletes all the files in the current directory that have the `.xml` file name extension:</span></span>

```powershell
Remove-Item -Path *.xml
```

## <a name="starting-a-program-by-invoking-an-associated-file"></a><span data-ttu-id="6e8bc-218">関連付けられたファイルを呼び出してプログラムを起動する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-218">Starting a program by invoking an associated file</span></span>

### <a name="invoke-a-file"></a><span data-ttu-id="6e8bc-219">ファイルを呼び出す</span><span class="sxs-lookup"><span data-stu-id="6e8bc-219">Invoke a file</span></span>

<span data-ttu-id="6e8bc-220">最初のコマンドは、 [Get Service](xref:Microsoft.PowerShell.Management.Get-Service) コマンドレットを使用して、ローカルサービスに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-220">The first command uses the [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) cmdlet to get information about local services.</span></span>

<span data-ttu-id="6e8bc-221">情報を [エクスポート Csv](xref:Microsoft.PowerShell.Utility.Export-Csv) コマンドレットにパイプし、その情報をファイルに格納し `Services.csv` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-221">It pipes the information to the [Export-Csv](xref:Microsoft.PowerShell.Utility.Export-Csv) cmdlet and then stores that information in the `Services.csv` file.</span></span>

<span data-ttu-id="6e8bc-222">2番目のコマンドは、 [呼び出し項目](xref:Microsoft.PowerShell.Management.Invoke-Item) を使用して、 `services.csv` 拡張機能に関連付けられているプログラムでファイルを開き `.csv` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-222">The second command uses [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) to open the `services.csv` file in the program associated with the `.csv` extension:</span></span>

```powershell
Get-Service | Export-Csv -Path services.csv
Invoke-Item -Path services.csv
```

## <a name="getting-files-and-folders-with-specified-attributes"></a><span data-ttu-id="6e8bc-223">指定された属性を持つファイルとフォルダーを取得する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-223">Getting files and folders with specified attributes</span></span>

### <a name="get-system-files"></a><span data-ttu-id="6e8bc-224">システムファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-224">Get System files</span></span>

<span data-ttu-id="6e8bc-225">このコマンドを実行すると、現在のディレクトリとそのサブディレクトリにあるシステム ファイルが取得されます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-225">This command gets system files in the current directory and its subdirectories.</span></span>

<span data-ttu-id="6e8bc-226">パラメーターを使用して、 `-File` (ディレクトリではなく) ファイルのみを取得し、パラメーターを使用して `-System` "system" 属性を持つ項目のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-226">It uses the `-File` parameter to get only files (not directories) and the `-System` parameter to get only items with the "system" attribute.</span></span>

<span data-ttu-id="6e8bc-227">パラメーターを使用して、 `-Recurse` 現在のディレクトリとすべてのサブディレクトリ内の項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-227">It uses the `-Recurse` parameter to get the items in the current directory and all subdirectories.</span></span>

```powershell
Get-ChildItem -File -System -Recurse
```

### <a name="get-hidden-files"></a><span data-ttu-id="6e8bc-228">隠しファイルの取得</span><span class="sxs-lookup"><span data-stu-id="6e8bc-228">Get Hidden files</span></span>

<span data-ttu-id="6e8bc-229">このコマンドは、非表示ファイルを含む、現在のディレクトリにあるすべてのファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-229">This command gets all files, including hidden files, in the current directory.</span></span>

<span data-ttu-id="6e8bc-230">**Attributes** パラメーターには、 `!Directory+Hidden` 非表示ファイルを取得すると、 `!Directory` 他のすべてのファイルを取得するという2つの値があります。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-230">It uses the **Attributes** parameter with two values, `!Directory+Hidden`, which gets hidden files, and `!Directory`, which gets all other files.</span></span>

```powershell
Get-ChildItem -Attributes !Directory,!Directory+Hidden
```

<span data-ttu-id="6e8bc-231">`dir -att !d,!d+h` は、このコマンドに相当します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-231">`dir -att !d,!d+h` is the equivalent of this command.</span></span>

### <a name="get-compressed-and-encrypted-files"></a><span data-ttu-id="6e8bc-232">圧縮されたファイルと暗号化されたファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="6e8bc-232">Get Compressed and Encrypted files</span></span>

<span data-ttu-id="6e8bc-233">このコマンドを実行すると、現在のディレクトリにあり、圧縮または暗号化されているファイルが取得されます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-233">This command gets files in the current directory that are either compressed or encrypted.</span></span>

<span data-ttu-id="6e8bc-234">`-Attributes`2 つの値 (と) を持つパラメーターを使用し `Compressed` `Encrypted` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-234">It uses the `-Attributes` parameter with two values, `Compressed` and `Encrypted`.</span></span> <span data-ttu-id="6e8bc-235">値は、 `,` "or" 演算子を表すコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-235">The values are separated by a comma `,` which represents the "OR" operator.</span></span>

```powershell
Get-ChildItem -Attributes Compressed,Encrypted
```

## <a name="dynamic-parameters"></a><span data-ttu-id="6e8bc-236">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e8bc-236">Dynamic parameters</span></span>

<span data-ttu-id="6e8bc-237">動的パラメーターは、PowerShell プロバイダーによって追加されるコマンドレットパラメーターであり、プロバイダーに対応したドライブでコマンドレットが使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-237">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="encoding-microsoftpowershellcommandsfilesystemcmdletproviderencoding"></a><span data-ttu-id="6e8bc-238">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-238">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span></span>

<span data-ttu-id="6e8bc-239">ファイル エンコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-239">Specifies the file encoding.</span></span> <span data-ttu-id="6e8bc-240">既定値は ASCII です。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-240">The default is ASCII.</span></span>

- <span data-ttu-id="6e8bc-241">**Ascii**: ascii (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-241">**ASCII**:  Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="6e8bc-242">**BigEndianUnicode**: ビッグエンディアンのバイト順を使用して utf-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-242">**BigEndianUnicode**:  Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="6e8bc-243">**String**: 文字列のエンコーディングの種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-243">**String**:  Uses the encoding type for a string.</span></span>
- <span data-ttu-id="6e8bc-244">**Unicode**: リトルエンディアンのバイト順を使用して utf-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-244">**Unicode**:  Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="6e8bc-245">**UTF7**: utf-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-245">**UTF7**:   Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="6e8bc-246">**UTF8**: utf-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-246">**UTF8**:  Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="6e8bc-247">**UTF8BOM**: バイト順マーク (BOM) を使用して utf-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-247">**UTF8BOM**: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="6e8bc-248">**UF8NOBOM**: バイト順マーク (BOM) を使用せずに utf-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-248">**UF8NOBOM**: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="6e8bc-249">**UTF32**:32 utf-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-249">**UTF32**:  Encodes in UTF-32 format.</span></span>
- <span data-ttu-id="6e8bc-250">**既定** 値は、インストールされている既定のコードページでエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-250">**Default**: Encodes in the default installed code page.</span></span>
- <span data-ttu-id="6e8bc-251">**OEM**: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-251">**OEM**: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="6e8bc-252">**不明**: エンコードの種類が不明または無効です。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-252">**Unknown**:  The encoding type is unknown or invalid.</span></span> <span data-ttu-id="6e8bc-253">データはバイナリとして処理できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-253">The data can be treated as binary.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-254">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-254">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-255">Add-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-255">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="6e8bc-256">Get-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-256">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="6e8bc-257">Set-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-257">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="delimiter-systemstring"></a><span data-ttu-id="6e8bc-258">Delimiter \<System.String\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-258">Delimiter \<System.String\></span></span>

<span data-ttu-id="6e8bc-259">[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) で使用され、読み込み中にファイルをオブジェクトに分割する区切り文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-259">Specifies the delimiter that [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) uses to divide the file into objects while it reads.</span></span>

<span data-ttu-id="6e8bc-260">既定値は `\n` 、行末文字です。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-260">The default is `\n`, the end-of-line character.</span></span>

<span data-ttu-id="6e8bc-261">テキストファイルを読み取るときに、 [Get Content](xref:Microsoft.PowerShell.Management.Get-Content) は文字列オブジェクトのコレクションを返します。各オブジェクトは、区切り文字で終わります。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-261">When reading a text file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns a collection of string objects, each of which ends with the delimiter character.</span></span>

<span data-ttu-id="6e8bc-262">ファイルに存在しない区切り文字を入力すると、 [Get Content](xref:Microsoft.PowerShell.Management.Get-Content) は、ファイル全体を単一の区切られていないオブジェクトとして返します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-262">Entering a delimiter that does not exist in the file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns the entire file as a single, un-delimited object.</span></span>

<span data-ttu-id="6e8bc-263">このパラメーターを使用し、大きなファイルを小さなファイルに分割します。「End of Example」のようなファイル区切り記号を区切り文字として指定します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-263">You can use this parameter to split a large file into smaller files by specifying a file separator, such as "End of Example", as the delimiter.</span></span> <span data-ttu-id="6e8bc-264">区切り文字は予約されています (破棄されません)。各ファイル セクションの最後の項目になります。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-264">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

> [!NOTE]
> <span data-ttu-id="6e8bc-265">現在、パラメーターの値が空の文字列の場合、 `-Delimiter` [Get](xref:Microsoft.PowerShell.Management.Get-Content) は何も返しません。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-265">Currently, when the value of the `-Delimiter` parameter is an empty string, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) does not return anything.</span></span>
> <span data-ttu-id="6e8bc-266">これは既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-266">This is a known issue.</span></span> <span data-ttu-id="6e8bc-267">ファイル全体を 1 つの区切りのない文字列として返すように [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) に強制するには、ファイルに存在しない値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-267">To force [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) to return the entire file as a single, undelimited string, enter a value that does not exist in the file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-268">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-268">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-269">Get-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-269">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="wait-systemmanagementautomationswitchparameter"></a><span data-ttu-id="6e8bc-270">Wait \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-270">Wait \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="6e8bc-271">コンテンツがファイルに追加されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-271">Waits for content to be appended to the file.</span></span> <span data-ttu-id="6e8bc-272">コンテンツが追加される場合、追加されたコンテンツを返します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-272">If content is appended, it returns the appended content.</span></span> <span data-ttu-id="6e8bc-273">コンテンツが変更された場合、ファイル全体が返されます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-273">If the content has changed, it returns the entire file.</span></span>

<span data-ttu-id="6e8bc-274">待機中に、[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) は 1 秒おきにファイルをチェックします。これは CTRL+C を押すなどして中断するまで続きます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-274">When waiting, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) checks the file once each second until you interrupt it, such as by pressing CTRL+C.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-275">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-275">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-276">Get-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-276">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="attributes-flagsexpression"></a><span data-ttu-id="6e8bc-277">Attributes \<FlagsExpression\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-277">Attributes \<FlagsExpression\></span></span>

<span data-ttu-id="6e8bc-278">指定した属性のファイルとフォルダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-278">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="6e8bc-279">このパラメーターはすべての属性をサポートします。複雑な属性の組み合わせを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-279">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="6e8bc-280">この `-Attributes` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-280">The `-Attributes` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="6e8bc-281">パラメーターでは `-Attributes` 、次の属性がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-281">The `-Attributes` parameter supports the following attributes:</span></span>

- <span data-ttu-id="6e8bc-282">**Archive**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-282">**Archive**</span></span>
- <span data-ttu-id="6e8bc-283">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-283">**Compressed**</span></span>
- <span data-ttu-id="6e8bc-284">**[デバイス]**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-284">**Device**</span></span>
- <span data-ttu-id="6e8bc-285">**ディレクトリ**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-285">**Directory**</span></span>
- <span data-ttu-id="6e8bc-286">**Encrypted**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-286">**Encrypted**</span></span>
- <span data-ttu-id="6e8bc-287">**[非表示]**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-287">**Hidden**</span></span>
- <span data-ttu-id="6e8bc-288">**標準**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-288">**Normal**</span></span>
- <span data-ttu-id="6e8bc-289">**NotContentIndexed**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-289">**NotContentIndexed**</span></span>
- <span data-ttu-id="6e8bc-290">**オフライン**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-290">**Offline**</span></span>
- <span data-ttu-id="6e8bc-291">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-291">**ReadOnly**</span></span>
- <span data-ttu-id="6e8bc-292">**ReparsePoint**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-292">**ReparsePoint**</span></span>
- <span data-ttu-id="6e8bc-293">**Sparc ファイル**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-293">**SparseFile**</span></span>
- <span data-ttu-id="6e8bc-294">**システム**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-294">**System**</span></span>
- <span data-ttu-id="6e8bc-295">**一時**</span><span class="sxs-lookup"><span data-stu-id="6e8bc-295">**Temporary**</span></span>

<span data-ttu-id="6e8bc-296">これらの属性の詳細については、「 [Fileattributes](/dotnet/api/system.io.fileattributes) 列挙型」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-296">For a description of these attributes, see the [FileAttributes](/dotnet/api/system.io.fileattributes) enumeration.</span></span>

<span data-ttu-id="6e8bc-297">次の演算子を利用して属性を結合します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-297">Use the following operators to combine attributes.</span></span>

- <span data-ttu-id="6e8bc-298">`!` -NOT</span><span class="sxs-lookup"><span data-stu-id="6e8bc-298">`!` - NOT</span></span>
- <span data-ttu-id="6e8bc-299">`+` -および</span><span class="sxs-lookup"><span data-stu-id="6e8bc-299">`+` - AND</span></span>
- <span data-ttu-id="6e8bc-300">`,` または</span><span class="sxs-lookup"><span data-stu-id="6e8bc-300">`,` - OR</span></span>

<span data-ttu-id="6e8bc-301">演算子とその属性の間にはスペースを挿入できません。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-301">No spaces are permitted between an operator and its attribute.</span></span> <span data-ttu-id="6e8bc-302">ただし、コンマの前にはスペースを挿入できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-302">However, spaces are permitted before commas.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-303">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-303">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-304">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6e8bc-304">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="directory-systemmanagementautomationswitchparameter"></a><span data-ttu-id="6e8bc-305">Directory \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-305">Directory \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="6e8bc-306">ディレクトリ (フォルダー) を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-306">Gets directories (folders).</span></span>

<span data-ttu-id="6e8bc-307">この `-Directory` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-307">The `-Directory` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="6e8bc-308">ディレクトリだけを取得するには、パラメーターを使用 `-Directory` してパラメーターを省略し `-File` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-308">To get only directories, use the `-Directory` parameter and omit the `-File` parameter.</span></span> <span data-ttu-id="6e8bc-309">ディレクトリを除外するには、パラメーターを使用 `-File` してパラメーターを省略する `-Directory` か、パラメーターを使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-309">To exclude directories, use the `-File` parameter and omit the `-Directory` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-310">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-310">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-311">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6e8bc-311">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="file-systemmanagementautomationswitchparameter"></a><span data-ttu-id="6e8bc-312">File \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-312">File \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="6e8bc-313">ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-313">Gets files.</span></span>

<span data-ttu-id="6e8bc-314">この `-File` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-314">The `-File` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="6e8bc-315">ファイルのみを取得するには、パラメーターを使用 `-File` してパラメーターを省略し `-Directory` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-315">To get only files, use the `-File` parameter and omit the `-Directory` parameter.</span></span> <span data-ttu-id="6e8bc-316">ファイルを除外するには、パラメーターを使用 `-Directory` してパラメーターを省略する `-File` か、パラメーターを使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-316">To exclude files, use the `-Directory` parameter and omit the `-File` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-317">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-317">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-318">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6e8bc-318">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="hidden-systemmanagementautomationswitchparameter"></a><span data-ttu-id="6e8bc-319">Hidden \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-319">Hidden \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="6e8bc-320">非表示のファイルとディレクトリ (フォルダー) のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-320">Gets only hidden files and directories (folders).</span></span> <span data-ttu-id="6e8bc-321">既定では、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem) は非表示項目のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-321">By default, [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) gets only non-hidden items.</span></span>

<span data-ttu-id="6e8bc-322">この `-Hidden` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-322">The `-Hidden` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="6e8bc-323">非表示の項目のみを取得するには、パラメーター、 `-Hidden` その `h` または `ah` 別名、またはパラメーターの **非表示** の値を使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-323">To get only hidden items, use the `-Hidden` parameter, its `h` or `ah` aliases, or the **Hidden** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="6e8bc-324">非表示の項目を除外するには、パラメーターを省略する `-Hidden` か、パラメーターを使用 `-Attributes` します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-324">To exclude hidden items, omit the `-Hidden` parameter or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-325">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-325">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-326">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6e8bc-326">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="readonly-systemmanagementautomationswitchparameter"></a><span data-ttu-id="6e8bc-327">ReadOnly \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-327">ReadOnly \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="6e8bc-328">読み取り専用のファイルとディレクトリ (フォルダー) を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-328">Gets only read-only files and directories (folders).</span></span>

<span data-ttu-id="6e8bc-329">この `-ReadOnly` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-329">The `-ReadOnly` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="6e8bc-330">読み取り専用の項目だけを取得するには、パラメーター、 `-ReadOnly` その `ar` エイリアス、またはパラメーターの **ReadOnly** 値を使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-330">To get only read-only items, use the `-ReadOnly` parameter, its `ar` alias, or the **ReadOnly** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="6e8bc-331">読み取り専用の項目を除外するには、パラメーターを使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-331">To exclude read-only items, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-332">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-332">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-333">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6e8bc-333">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="system-systemmanagementautomationswitchparameter"></a><span data-ttu-id="6e8bc-334">System \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-334">System \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="6e8bc-335">システムのファイルとディレクトリ (フォルダー) を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-335">Gets only system files and directories (folders).</span></span>

<span data-ttu-id="6e8bc-336">この `-System` パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-336">The `-System` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="6e8bc-337">システムファイルとフォルダーのみを取得するには、パラメーター、 `-System` その `as` エイリアス、またはパラメーターの **システム** 値を使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-337">To get only system files and folders, use the `-System` parameter, its `as` alias, or the **System** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="6e8bc-338">システムファイルとフォルダーを除外するには、パラメーターを使用し `-Attributes` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-338">To exclude system files and folders, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-339">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-339">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-340">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6e8bc-340">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="newerthan-systemdatetime"></a><span data-ttu-id="6e8bc-341">NewerThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-341">NewerThan \<System.DateTime\></span></span>

<span data-ttu-id="6e8bc-342">`$True` `LastWriteTime` ファイルの値が指定した日付よりも大きい場合に、を返します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-342">Returns `$True` when the `LastWriteTime` value of a file is greater than the specified date.</span></span> <span data-ttu-id="6e8bc-343">それ以外の場合は `$False`を返します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-343">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="6e8bc-344">[Datetime](/dotnet/api/system.datetime)オブジェクトを入力します。たとえば、 [Get Date](xref:Microsoft.PowerShell.Utility.Get-Date)コマンドレットが返す値や、 [datetime](/dotnet/api/system.datetime)オブジェクトに変換できる文字列 (など) を入力し `"August 10, 2011 2:00 PM"` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-344">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-345">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-345">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-346">Test-Path</span><span class="sxs-lookup"><span data-stu-id="6e8bc-346">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="olderthan-systemdatetime"></a><span data-ttu-id="6e8bc-347">OlderThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-347">OlderThan \<System.DateTime\></span></span>

<span data-ttu-id="6e8bc-348">`$True` `LastWriteTime` ファイルの値が指定した日付よりも小さい場合に、を返します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-348">Returns `$True` when the `LastWriteTime` value of a file is less than the specified date.</span></span> <span data-ttu-id="6e8bc-349">それ以外の場合は `$False`を返します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-349">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="6e8bc-350">[Datetime](/dotnet/api/system.datetime)オブジェクトを入力します。たとえば、 [Get Date](xref:Microsoft.PowerShell.Utility.Get-Date)コマンドレットが返す値や、 [datetime](/dotnet/api/system.datetime)オブジェクトに変換できる文字列 (など) を入力し `"August 10, 2011 2:00 PM"` ます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-350">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-351">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-351">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-352">Test-Path</span><span class="sxs-lookup"><span data-stu-id="6e8bc-352">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="stream-systemstring"></a><span data-ttu-id="6e8bc-353">Stream \<System.String\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-353">Stream \<System.String\></span></span>

<span data-ttu-id="6e8bc-354">代替データ ストリームを管理します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-354">Manages alternate data streams.</span></span> <span data-ttu-id="6e8bc-355">ストリーム名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-355">Enter the stream name.</span></span> <span data-ttu-id="6e8bc-356">ワイルドカードは、ファイルシステムドライブ内の項目の [取得](xref:Microsoft.PowerShell.Management.Get-Item) および [削除](xref:Microsoft.PowerShell.Management.Remove-Item) コマンドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-356">Wildcards are permitted only in [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) for and [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) commands in a file system drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-357">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-357">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-358">Add-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-358">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="6e8bc-359">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-359">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="6e8bc-360">Get-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-360">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="6e8bc-361">Get-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-361">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="6e8bc-362">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-362">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="6e8bc-363">Set-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-363">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="raw-switchparameter"></a><span data-ttu-id="6e8bc-364">Raw \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-364">Raw \<SwitchParameter\></span></span>

<span data-ttu-id="6e8bc-365">改行文字が無視されます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-365">Ignores newline characters.</span></span> <span data-ttu-id="6e8bc-366">コンテンツを 1 つの項目として返します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-366">Returns contents as a single item.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-367">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-367">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-368">Get-Content</span><span class="sxs-lookup"><span data-stu-id="6e8bc-368">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="itemtype-string"></a><span data-ttu-id="6e8bc-369">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="6e8bc-369">ItemType \<String\></span></span>

<span data-ttu-id="6e8bc-370">このパラメーターを使用すると、作成する項目の tye を指定できます。 `New-Item`</span><span class="sxs-lookup"><span data-stu-id="6e8bc-370">This parameter allows you to specify the tye of item to create with `New-Item`</span></span>

<span data-ttu-id="6e8bc-371">このパラメーターで使用できる値は、使用している現在のプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-371">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="6e8bc-372">ドライブでは、 `FileSystem` 次の値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-372">In a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="6e8bc-373">ファイル</span><span class="sxs-lookup"><span data-stu-id="6e8bc-373">File</span></span>
- <span data-ttu-id="6e8bc-374">ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="6e8bc-374">Directory</span></span>
- <span data-ttu-id="6e8bc-375">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="6e8bc-375">SymbolicLink</span></span>
- <span data-ttu-id="6e8bc-376">ジャンクション</span><span class="sxs-lookup"><span data-stu-id="6e8bc-376">Junction</span></span>
- <span data-ttu-id="6e8bc-377">Hardlink create</span><span class="sxs-lookup"><span data-stu-id="6e8bc-377">HardLink</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="6e8bc-378">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6e8bc-378">Cmdlets supported</span></span>

- [<span data-ttu-id="6e8bc-379">New-Item</span><span class="sxs-lookup"><span data-stu-id="6e8bc-379">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="6e8bc-380">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="6e8bc-380">Using the pipeline</span></span>

<span data-ttu-id="6e8bc-381">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-381">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="6e8bc-382">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-382">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="6e8bc-383">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-383">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="6e8bc-384">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="6e8bc-384">Getting help</span></span>

<span data-ttu-id="6e8bc-385">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-385">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="6e8bc-386">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するには、ファイルシステムドライブで [get-help](xref:Microsoft.PowerShell.Core.Get-Help) コマンドを実行するか、 `-Path` [get-help](xref:Microsoft.PowerShell.Core.Get-Help) のパラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e8bc-386">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path c:
```

## <a name="see-also"></a><span data-ttu-id="6e8bc-387">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e8bc-387">See also</span></span>

[<span data-ttu-id="6e8bc-388">about_Providers</span><span class="sxs-lookup"><span data-stu-id="6e8bc-388">about_Providers</span></span>](../About/about_Providers.md)
