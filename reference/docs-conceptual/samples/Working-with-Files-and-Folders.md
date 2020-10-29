---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: ファイルとフォルダーの操作
description: この記事では、PowerShell を使用して特定のファイルとフォルダーを操作するタスクについて説明します。
ms.openlocfilehash: c0c3abb082b05296daa480ac06bcbfa3a784e0c9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500030"
---
# <a name="working-with-files-and-folders"></a><span data-ttu-id="63f1b-104">ファイルとフォルダーの操作</span><span class="sxs-lookup"><span data-stu-id="63f1b-104">Working with Files and Folders</span></span>

<span data-ttu-id="63f1b-105">Windows PowerShell ドライブ間を移動したり、Windows PowerShell ドライブ上の項目を操作したりすることは、Windows の物理ディスク ドライブ上のファイルやフォルダーを操作することと似ています。</span><span class="sxs-lookup"><span data-stu-id="63f1b-105">Navigating through Windows PowerShell drives and manipulating the items on them is similar to manipulating files and folders on Windows physical disk drives.</span></span> <span data-ttu-id="63f1b-106">この記事では、PowerShell を使用して特定のファイルとフォルダーを操作するタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-106">This article discusses how to deal with specific file and folder manipulation tasks using PowerShell.</span></span>

## <a name="listing-all-the-files-and-folders-within-a-folder"></a><span data-ttu-id="63f1b-107">フォルダー内のすべてのファイルとフォルダーの一覧表示</span><span class="sxs-lookup"><span data-stu-id="63f1b-107">Listing All the Files and Folders Within a Folder</span></span>

<span data-ttu-id="63f1b-108">`Get-ChildItem` を使用することにより、フォルダー内のすべての項目を直接取得することができます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-108">You can get all items directly within a folder by using `Get-ChildItem`.</span></span> <span data-ttu-id="63f1b-109">非表示の項目やシステム項目を表示するには、オプションの **Force** パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-109">Add the optional **Force** parameter to display hidden or system items.</span></span> <span data-ttu-id="63f1b-110">たとえば、このコマンドは、Windows PowerShell ドライブ C (Windows の物理ドライブ C と同じ) に直接含まれるコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-110">For example, this command displays the direct contents of Windows PowerShell Drive C (which is the same as the Windows physical drive C):</span></span>

```powershell
Get-ChildItem -Path C:\ -Force
```

<span data-ttu-id="63f1b-111">このコマンドは、`Cmd.exe` の `DIR` コマンドや UNIX シェルの `ls` を使用したときと同様に、直接含まれている項目のみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-111">The command lists only the directly contained items, much like using `Cmd.exe`'s `DIR` command or `ls` in a UNIX shell.</span></span> <span data-ttu-id="63f1b-112">内包されている項目を表示するには、`-Recurse` パラメーターも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63f1b-112">In order to show contained items, you need to specify the `-Recurse` parameter as well.</span></span> <span data-ttu-id="63f1b-113">(完了までにかなりの時間がかかることがあります。)C ドライブ上のすべての項目を一覧表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-113">(This can take an extremely long time to complete.) To list everything on the C drive:</span></span>

```powershell
Get-ChildItem -Path C:\ -Force -Recurse
```

<span data-ttu-id="63f1b-114">`Get-ChildItem` は、 **Path** 、 **Filter** 、 **Include** 、 **Exclude** の各パラメーターを使用して項目をフィルター処理できますが、通常、これらは名前にのみ基づいています。</span><span class="sxs-lookup"><span data-stu-id="63f1b-114">`Get-ChildItem` can filter items with its **Path** , **Filter** , **Include** , and **Exclude** parameters, but those are typically based only on name.</span></span> <span data-ttu-id="63f1b-115">`Where-Object` を使用することにより、項目の他のプロパティに基づいた複雑なフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-115">You can perform complex filtering based on other properties of items by using `Where-Object`.</span></span>

<span data-ttu-id="63f1b-116">次のコマンドは、Program Files フォルダー内にある、2005 年 10 月 1 日より後に最終更新され、1 メガバイト以上、10 メガバイト以下のすべての実行可能ファイルを検出します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-116">The following command finds all executables within the Program Files folder that were last modified after October 1, 2005 and which are neither smaller than 1 megabyte nor larger than 10 megabytes:</span></span>

```powershell
Get-ChildItem -Path $env:ProgramFiles -Recurse -Include *.exe | Where-Object -FilterScript {($_.LastWriteTime -gt '2005-10-01') -and ($_.Length -ge 1mb) -and ($_.Length -le 10mb)}
```

## <a name="copying-files-and-folders"></a><span data-ttu-id="63f1b-117">ファイルとフォルダーのコピー</span><span class="sxs-lookup"><span data-stu-id="63f1b-117">Copying Files and Folders</span></span>

<span data-ttu-id="63f1b-118">コピーは `Copy-Item` を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-118">Copying is done with `Copy-Item`.</span></span> <span data-ttu-id="63f1b-119">次のコマンドは、C:\\boot.ini to C:\\boot.bak にバックアップします。</span><span class="sxs-lookup"><span data-stu-id="63f1b-119">The following command backs up C:\\boot.ini to C:\\boot.bak:</span></span>

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak
```

<span data-ttu-id="63f1b-120">コピー先のファイルが既に存在する場合、コピー操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-120">If the destination file already exists, the copy attempt fails.</span></span> <span data-ttu-id="63f1b-121">既存のコピー先ファイルを上書きするには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-121">To overwrite a pre-existing destination, use the **Force** parameter:</span></span>

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak -Force
```

<span data-ttu-id="63f1b-122">このコマンドは、コピー先が読み取り専用である場合にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-122">This command works even when the destination is read-only.</span></span>

<span data-ttu-id="63f1b-123">フォルダーのコピーも同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-123">Folder copying works the same way.</span></span> <span data-ttu-id="63f1b-124">このコマンドは、フォルダー `C:\temp\test1` を新しいフォルダー `C:\temp\DeleteMe` 再帰的にコピーします。</span><span class="sxs-lookup"><span data-stu-id="63f1b-124">This command copies the folder `C:\temp\test1` to the new folder `C:\temp\DeleteMe` recursively:</span></span>

```powershell
Copy-Item C:\temp\test1 -Recurse C:\temp\DeleteMe
```

<span data-ttu-id="63f1b-125">選択した項目をコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-125">You can also copy a selection of items.</span></span> <span data-ttu-id="63f1b-126">次のコマンドでは、`C:\data` 内のすべての場所に格納されているすべての .txt ファイルを `C:\temp\text` にコピーします。</span><span class="sxs-lookup"><span data-stu-id="63f1b-126">The following command copies all .txt files contained anywhere in `C:\data` to `C:\temp\text`:</span></span>

```powershell
Copy-Item -Filter *.txt -Path c:\data -Recurse -Destination C:\temp\text
```

<span data-ttu-id="63f1b-127">ファイル システムのコピー操作には、他のツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-127">You can still use other tools to perform file system copies.</span></span> <span data-ttu-id="63f1b-128">XCOPY、ROBOCOPY、および COM オブジェクト ( **Scripting.FileSystemObject** など) はすべて Windows PowerShell で動作します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-128">XCOPY, ROBOCOPY, and COM objects, such as the **Scripting.FileSystemObject,** all work in Windows PowerShell.</span></span> <span data-ttu-id="63f1b-129">たとえば、Windows Script Host の **Scripting.FileSystem COM** クラスを使用して、`C:\boot.ini` を `C:\boot.bak` にバックアップするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-129">For example, you can use the Windows Script Host **Scripting.FileSystem COM** class to back up `C:\boot.ini` to `C:\boot.bak`:</span></span>

```powershell
(New-Object -ComObject Scripting.FileSystemObject).CopyFile('C:\boot.ini', 'C:\boot.bak')
```

## <a name="creating-files-and-folders"></a><span data-ttu-id="63f1b-130">ファイルとフォルダーの作成</span><span class="sxs-lookup"><span data-stu-id="63f1b-130">Creating Files and Folders</span></span>

<span data-ttu-id="63f1b-131">新しい項目の作成は、すべての Windows PowerShell プロバイダーで同じ方法で行われます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-131">Creating new items works the same on all Windows PowerShell providers.</span></span> <span data-ttu-id="63f1b-132">Windows PowerShell プロバイダーに複数の種類の項目が含まれている場合 (たとえば、FileSystem Windows PowerShell プロバイダーではディレクトリとファイルが区別されます)、項目の種類を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63f1b-132">If a Windows PowerShell provider has more than one type of item—for example, the FileSystem Windows PowerShell provider distinguishes between directories and files—you need to specify the item type.</span></span>

<span data-ttu-id="63f1b-133">このコマンドは新しいフォルダー `C:\temp\New Folder` を作成します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-133">This command creates a new folder `C:\temp\New Folder`:</span></span>

```powershell
New-Item -Path 'C:\temp\New Folder' -ItemType Directory
```

<span data-ttu-id="63f1b-134">このコマンドは新しい空のファイル `C:\temp\New Folder\file.txt` を作成します</span><span class="sxs-lookup"><span data-stu-id="63f1b-134">This command creates a new empty file `C:\temp\New Folder\file.txt`</span></span>

```powershell
New-Item -Path 'C:\temp\New Folder\file.txt' -ItemType File
```

> [!IMPORTANT]
> <span data-ttu-id="63f1b-135">**Force** スイッチを `New-Item` コマンドで使用してフォルダーを作成し、そのフォルダーが既に存在している場合は、フォルダーが上書きされたり、置き換えたりすることは _ありません_ 。</span><span class="sxs-lookup"><span data-stu-id="63f1b-135">When using the **Force** switch with the `New-Item` command to create a folder, and the folder already exists, it _won't_ overwrite or replace the folder.</span></span> <span data-ttu-id="63f1b-136">単に既存のフォルダー オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-136">It will simply return the existing folder object.</span></span> <span data-ttu-id="63f1b-137">ただし、既に存在するファイルに対して `New-Item -Force` を使用すると、ファイルは完全に上書き _されます_ 。</span><span class="sxs-lookup"><span data-stu-id="63f1b-137">However, if you use `New-Item -Force` on a file that already exists, the file _will_ be completely overwritten.</span></span>

## <a name="removing-all-files-and-folders-within-a-folder"></a><span data-ttu-id="63f1b-138">フォルダー内のすべてのファイルとフォルダーの削除</span><span class="sxs-lookup"><span data-stu-id="63f1b-138">Removing All Files and Folders Within a Folder</span></span>

<span data-ttu-id="63f1b-139">内包されている項目を削除するには、`Remove-Item` を使用します。ただし、その項目に他の何らかの項目が含まれている場合は、削除の確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-139">You can remove contained items using `Remove-Item`, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="63f1b-140">たとえば、他の項目を含むフォルダー `C:\temp\DeleteMe` を削除しようとすると、フォルダーが削除される前に、Windows PowerShell から次のような確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-140">For example, if you attempt to delete the folder `C:\temp\DeleteMe` that contains other items, Windows PowerShell prompts you for confirmation before deleting the folder:</span></span>

```
Remove-Item -Path C:\temp\DeleteMe

Confirm
The item at C:\temp\DeleteMe has children and the Recurse parameter was not
specified. If you continue, all children will be removed with the item. Are you
sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="63f1b-141">内包されている項目ごとに削除の確認が行われないようにする場合は、 **Recurse** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-141">If you do not want to be prompted for each contained item, specify the **Recurse** parameter:</span></span>

```powershell
Remove-Item -Path C:\temp\DeleteMe -Recurse
```

## <a name="mapping-a-local-folder-as-a-drive"></a><span data-ttu-id="63f1b-142">ローカル フォルダーをドライブとしてマップする</span><span class="sxs-lookup"><span data-stu-id="63f1b-142">Mapping a Local Folder as a drive</span></span>

<span data-ttu-id="63f1b-143">`New-PSDrive` コマンドを使用することにより、ローカル フォルダーをマッピングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-143">You can also map a local folder, using the `New-PSDrive` command.</span></span> <span data-ttu-id="63f1b-144">次のコマンドでは、ローカルの Program Files ディレクトリをルートとする PowerShell セッションからのみ参照できる、ローカル ドライブ `P:` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-144">The following command creates a local drive `P:` rooted in the local Program Files directory, visible only from the PowerShell session:</span></span>

```powershell
New-PSDrive -Name P -Root $env:ProgramFiles -PSProvider FileSystem
```

<span data-ttu-id="63f1b-145">ネットワーク ドライブと同様に、Windows PowerShell 内でマッピングされたドライブは、直ちに Windows PowerShell シェルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-145">Just as with network drives, drives mapped within Windows PowerShell are immediately visible to the Windows PowerShell shell.</span></span> <span data-ttu-id="63f1b-146">エクスプローラーから参照できるマッピングされたドライブを作成するには、`-Persist` のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="63f1b-146">In order to create a mapped drive visible from File Explorer, the parameter `-Persist` is needed.</span></span> <span data-ttu-id="63f1b-147">ただし、Persist で使用できるのはリモートのパスのみです。</span><span class="sxs-lookup"><span data-stu-id="63f1b-147">However, only remote paths can be used with Persist.</span></span>

## <a name="reading-a-text-file-into-an-array"></a><span data-ttu-id="63f1b-148">配列へのテキスト ファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="63f1b-148">Reading a Text File into an Array</span></span>

<span data-ttu-id="63f1b-149">テキスト データの一般的な格納形式の 1 つに、個々の行を個別のデータ要素として扱うファイルを使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="63f1b-149">One of the more common storage formats for text data is in a file with separate lines treated as distinct data elements.</span></span> <span data-ttu-id="63f1b-150">`Get-Content` コマンドレットを使用することにより、1 つのステップでファイル全体を読み取ることができます。以下にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-150">The `Get-Content` cmdlet can be used to read an entire file in one step, as shown here:</span></span>

```
PS> Get-Content -Path C:\boot.ini
[boot loader]
timeout=5
default=multi(0)disk(0)rdisk(0)partition(1)\WINDOWS
[operating systems]
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS="Microsoft Windows XP Professional"
 /noexecute=AlwaysOff /fastdetect
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS=" Microsoft Windows XP Professional
with Data Execution Prevention" /noexecute=optin /fastdetect
```

<span data-ttu-id="63f1b-151">`Get-Content` は、ファイルから読み取ったデータを、1 行のファイル内容につき 1 つの要素を含む配列として扱います。</span><span class="sxs-lookup"><span data-stu-id="63f1b-151">`Get-Content` already treats the data read from the file as an array, with one element per line of file content.</span></span> <span data-ttu-id="63f1b-152">これを確認するには、返された内容の **Length** をチェックします。</span><span class="sxs-lookup"><span data-stu-id="63f1b-152">You can confirm this by checking the **Length** of the returned content:</span></span>

```
PS> (Get-Content -Path C:\boot.ini).Length
6
```

<span data-ttu-id="63f1b-153">このコマンドは、情報の一覧を Windows PowerShell に直接取得するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-153">This command is most useful for getting lists of information into Windows PowerShell directly.</span></span> <span data-ttu-id="63f1b-154">たとえば、コンピューター名または IP アドレスの一覧を、ファイルの各行に 1 つの名前を入力して `C:\temp\domainMembers.txt` ファイルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-154">For example, you might store a list of computer names or IP addresses in a file `C:\temp\domainMembers.txt`, with one name on each line of the file.</span></span> <span data-ttu-id="63f1b-155">`Get-Content` を使用してファイルの内容を取得し、変数 `$Computers` に格納するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="63f1b-155">You can use `Get-Content` to retrieve the file contents and put them in the variable `$Computers`:</span></span>

```powershell
$Computers = Get-Content -Path C:\temp\DomainMembers.txt
```

<span data-ttu-id="63f1b-156">`$Computers` には、各要素に 1 つのコンピューター名が含まれた配列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="63f1b-156">`$Computers` is now an array containing a computer name in each element.</span></span>
