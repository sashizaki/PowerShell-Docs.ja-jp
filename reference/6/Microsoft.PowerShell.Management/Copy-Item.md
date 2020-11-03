---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-Item
ms.openlocfilehash: 0aeebac75c5a84fd78056954d7178de1dbac1460
ms.sourcegitcommit: 33ac34789e86ffb4e7e69453ae38fc0bd24933dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "93219752"
---
# <span data-ttu-id="967ef-103">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="967ef-103">Copy-Item</span></span>

## <span data-ttu-id="967ef-104">概要</span><span class="sxs-lookup"><span data-stu-id="967ef-104">SYNOPSIS</span></span>
<span data-ttu-id="967ef-105">項目をある場所から別の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="967ef-105">Copies an item from one location to another.</span></span>

## <span data-ttu-id="967ef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="967ef-106">SYNTAX</span></span>

### <span data-ttu-id="967ef-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="967ef-107">Path (Default)</span></span>

```
Copy-Item [-Path] <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="967ef-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="967ef-108">LiteralPath</span></span>

```
Copy-Item -LiteralPath <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

## <span data-ttu-id="967ef-109">Description</span><span class="sxs-lookup"><span data-stu-id="967ef-109">DESCRIPTION</span></span>

<span data-ttu-id="967ef-110">`Copy-Item`コマンドレットは、同じ名前空間内のある場所から別の場所に項目をコピーします。</span><span class="sxs-lookup"><span data-stu-id="967ef-110">The `Copy-Item` cmdlet copies an item from one location to another location in the same namespace.</span></span>
<span data-ttu-id="967ef-111">たとえば、ファイルをフォルダーにコピーすることはできますが、ファイルを証明書ドライブにコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="967ef-111">For instance, it can copy a file to a folder, but it can't copy a file to a certificate drive.</span></span>

<span data-ttu-id="967ef-112">このコマンドレットは、コピーされる項目を切り取りまたは削除しません。</span><span class="sxs-lookup"><span data-stu-id="967ef-112">This cmdlet doesn't cut or delete the items being copied.</span></span> <span data-ttu-id="967ef-113">コマンドレットがコピーできる項目は、項目を公開する PowerShell プロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="967ef-113">The particular items that the cmdlet can copy depend on the PowerShell provider that exposes the item.</span></span> <span data-ttu-id="967ef-114">たとえば、ファイルシステムドライブのファイルとディレクトリ、レジストリキー、レジストリドライブ内のエントリをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="967ef-114">For instance, it can copy files and directories in a file system drive and registry keys and entries in the registry drive.</span></span>

<span data-ttu-id="967ef-115">このコマンドレットは、同じコマンドで項目のコピーと名前の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="967ef-115">This cmdlet can copy and rename items in the same command.</span></span> <span data-ttu-id="967ef-116">項目の名前を変更するには、 **Destination** パラメーターの値に新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="967ef-116">To rename an item, enter the new name in the value of the **Destination** parameter.</span></span> <span data-ttu-id="967ef-117">項目の名前を変更し、コピーしない場合は、コマンドレットを使用し `Rename-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-117">To rename an item and not copy it, use the `Rename-Item` cmdlet.</span></span>

## <span data-ttu-id="967ef-118">例</span><span class="sxs-lookup"><span data-stu-id="967ef-118">EXAMPLES</span></span>

### <span data-ttu-id="967ef-119">例 1: 指定されたディレクトリにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-119">Example 1: Copy a file to the specified directory</span></span>

<span data-ttu-id="967ef-120">この例では、 `mar1604.log.txt` ファイルをディレクトリにコピーし `C:\Presentation` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-120">This example copies the `mar1604.log.txt` file to the `C:\Presentation` directory.</span></span> <span data-ttu-id="967ef-121">元のファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="967ef-121">The original file isn't deleted.</span></span>

```powershell
Copy-Item "C:\Wabash\Logfiles\mar1604.log.txt" -Destination "C:\Presentation"
```

### <span data-ttu-id="967ef-122">例 2: 既存のディレクトリにディレクトリの内容をコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-122">Example 2: Copy directory contents to an existing directory</span></span>

<span data-ttu-id="967ef-123">この例では、ディレクトリの内容を `C:\Logfiles` 既存のディレクトリにコピーし `C:\Drawings` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-123">This example copies the contents of the `C:\Logfiles` directory into the existing `C:\Drawings` directory.</span></span> <span data-ttu-id="967ef-124">`Logfiles`ディレクトリはコピーされません。</span><span class="sxs-lookup"><span data-stu-id="967ef-124">The `Logfiles` directory isn't copied.</span></span>

<span data-ttu-id="967ef-125">ディレクトリに `Logfiles` サブディレクトリ内のファイルが含まれている場合、それらのサブディレクトリはそのファイルツリーと共にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="967ef-125">If the `Logfiles` directory contains files in subdirectories, those subdirectories are copied with their file trees intact.</span></span> <span data-ttu-id="967ef-126">既定では、 **Container** パラメーターは **True** に設定されています。これにより、ディレクトリ構造が保持されます。</span><span class="sxs-lookup"><span data-stu-id="967ef-126">By default, the **Container** parameter is set to **True** , which preserves the directory structure.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings" -Recurse
```

> [!NOTE]
> <span data-ttu-id="967ef-127">コピーにディレクトリを含める必要がある場合は、 `Logfiles` `\*` **パス** からを削除します。</span><span class="sxs-lookup"><span data-stu-id="967ef-127">If you need to include the `Logfiles` directory in the copy, remove the `\*` from the **Path**.</span></span>
> <span data-ttu-id="967ef-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="967ef-128">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings" -Recurse`

### <span data-ttu-id="967ef-129">例 3: ディレクトリとコンテンツを新しいディレクトリにコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-129">Example 3: Copy directory and contents to a new directory</span></span>

<span data-ttu-id="967ef-130">この例では、ソースディレクトリの内容をコピー `C:\Logfiles` し、新しいコピー先ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="967ef-130">This example copies the contents of the `C:\Logfiles` source directory and creates a new destination directory.</span></span> <span data-ttu-id="967ef-131">新しいコピー先ディレクトリは、 `\Logs` で作成され `C:\Drawings` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-131">The new destination directory, `\Logs` is created in `C:\Drawings`.</span></span>

<span data-ttu-id="967ef-132">ソースディレクトリの名前を含めるには、 **例 2** に示すように、既存のコピー先ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="967ef-132">To include the source directory's name, copy to an existing destination directory as shown in **Example 2**.</span></span> <span data-ttu-id="967ef-133">または、新しい宛先ディレクトリに、ソースディレクトリと同じ名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="967ef-133">Or, name the new destination directory with the same as the source directory.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings\Logs" -Recurse
```

> [!NOTE]
> <span data-ttu-id="967ef-134">**パス** にが含まれている場合 `\*` 、ディレクトリのすべてのファイルの内容 (サブディレクトリツリーを含む) が新しいコピー先ディレクトリにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="967ef-134">If the **Path** includes `\*`, all the directory's file contents, including the subdirectory trees, are copied to the new destination directory.</span></span> <span data-ttu-id="967ef-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="967ef-135">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings\Logs" -Recurse`

### <span data-ttu-id="967ef-136">例 4: 指定したディレクトリにファイルをコピーし、ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="967ef-136">Example 4: Copy a file to the specified directory and rename the file</span></span>

<span data-ttu-id="967ef-137">この例では、コマンドレットを使用して、 `Copy-Item` `Get-Widget.ps1` ディレクトリからディレクトリにスクリプトをコピーし `\\Server01\Share` `\\Server12\ScriptArchive` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-137">This example uses the `Copy-Item` cmdlet to copy the `Get-Widget.ps1` script from the `\\Server01\Share` directory to the `\\Server12\ScriptArchive` directory.</span></span> <span data-ttu-id="967ef-138">コピー操作の一部として、コマンドは項目名をからに変更し、 `Get-Widget.ps1` `Get-Widget.ps1.txt` 電子メールメッセージに添付できるようにします。</span><span class="sxs-lookup"><span data-stu-id="967ef-138">As part of the copy operation, the command changes the item name from `Get-Widget.ps1` to `Get-Widget.ps1.txt`, so it can be attached to email messages.</span></span>

```powershell
Copy-Item "\\Server01\Share\Get-Widget.ps1" -Destination "\\Server12\ScriptArchive\Get-Widget.ps1.txt"
```

### <span data-ttu-id="967ef-139">例 5: リモートコンピューターにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-139">Example 5: Copy a file to a remote computer</span></span>

<span data-ttu-id="967ef-140">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-140">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="967ef-141">この `Copy-Item` コマンドレットは、 `test.log` `D:\Folder001` `C:\Folder001_Copy` 変数に格納されているセッション情報を使用して、フォルダーからリモートコンピューター上のフォルダーにコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-141">The `Copy-Item` cmdlet copies `test.log` from the `D:\Folder001` folder to the `C:\Folder001_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="967ef-142">元のファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="967ef-142">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "D:\Folder001\test.log" -Destination "C:\Folder001_Copy\" -ToSession $Session
```

### <span data-ttu-id="967ef-143">例 6: リモートコンピューターにフォルダーをコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-143">Example 6: Copy a folder to a remote computer</span></span>

<span data-ttu-id="967ef-144">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-144">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="967ef-145">この `Copy-Item` コマンドレットは、 `D:\Folder002` `C:\Folder002_Copy` 変数に格納されているセッション情報を使用して、リモートコンピューター上のディレクトリにフォルダーをコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-145">The `Copy-Item` cmdlet copies the `D:\Folder002` folder to the `C:\Folder002_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="967ef-146">サブフォルダーまたはファイルは、 **再帰** スイッチを使用せずにコピーされません。</span><span class="sxs-lookup"><span data-stu-id="967ef-146">Any subfolders or files are not copied without using the **Recurse** switch.</span></span>
<span data-ttu-id="967ef-147">フォルダーがまだ存在しない場合は、操作によって作成され `Folder002_Copy` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-147">The operation creates the `Folder002_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server02" -Credential "Contoso\User01"
Copy-Item "D:\Folder002\" -Destination "C:\Folder002_Copy\" -ToSession $Session
```

### <span data-ttu-id="967ef-148">例 7: フォルダーの内容全体をリモートコンピューターに再帰的にコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-148">Example 7: Recursively copy the entire contents of a folder to a remote computer</span></span>

<span data-ttu-id="967ef-149">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-149">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="967ef-150">この `Copy-Item` コマンドレットは、 `D:\Folder003` `C:\Folder003_Copy` 変数に格納されているセッション情報を使用して、フォルダーの内容全体をリモートコンピューター上のディレクトリにコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-150">The `Copy-Item` cmdlet copies the entire contents from the `D:\Folder003` folder to the `C:\Folder003_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="967ef-151">サブフォルダーは、そのファイルツリーと共にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="967ef-151">The subfolders are copied with their file trees intact.</span></span> <span data-ttu-id="967ef-152">フォルダーがまだ存在しない場合は、操作によって作成され `Folder003_Copy` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-152">The operation creates the `Folder003_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder003\" -Destination "C:\Folder003_Copy\" -ToSession $Session -Recurse
```

### <span data-ttu-id="967ef-153">例 8: ファイルをリモートコンピューターにコピーし、ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="967ef-153">Example 8: Copy a file to a remote computer and then rename the file</span></span>

<span data-ttu-id="967ef-154">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-154">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="967ef-155">この `Copy-Item` コマンドレットは、 `scriptingexample.ps1` `D:\Folder004` `C:\Folder004_Copy` 変数に格納されているセッション情報を使用して、フォルダーからリモートコンピューター上のフォルダーにコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-155">The `Copy-Item` cmdlet copies `scriptingexample.ps1` from the `D:\Folder004` folder to the `C:\Folder004_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="967ef-156">コピー操作の一部として、コマンドは項目名をからに変更し、 `scriptingexample.ps1` `scriptingexample_copy.ps1` 電子メールメッセージに添付できるようにします。</span><span class="sxs-lookup"><span data-stu-id="967ef-156">As part of the copy operation, the command changes the item name from `scriptingexample.ps1` to `scriptingexample_copy.ps1`, so it can be attached to email messages.</span></span> <span data-ttu-id="967ef-157">元のファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="967ef-157">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder004\scriptingexample.ps1" -Destination "C:\Folder004_Copy\scriptingexample_copy.ps1" -ToSession $Session
```

### <span data-ttu-id="967ef-158">例 9: ローカルコンピューターにリモートファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-158">Example 9: Copy a remote file to the local computer</span></span>

<span data-ttu-id="967ef-159">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-159">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="967ef-160">`Copy-Item`コマンドレットは、 `test.log` `C:\MyRemoteData\` `D:\MyLocalData` 変数に格納されているセッション情報を使用して、リモートからローカルフォルダーにコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-160">The `Copy-Item` cmdlet copies `test.log` from the remote `C:\MyRemoteData\` to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="967ef-161">元のファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="967ef-161">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\test.log" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="967ef-162">例 10: リモートフォルダーの内容全体をローカルコンピューターにコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-162">Example 10: Copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="967ef-163">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-163">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="967ef-164">`Copy-Item`コマンドレットは、 `C:\MyRemoteData\scripts` `D:\MyLocalData` 変数に格納されているセッション情報を使用して、リモートフォルダーからローカルフォルダーにコンテンツ全体をコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-164">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="967ef-165">Scripts フォルダーにサブフォルダー内のファイルが含まれている場合、それらのサブフォルダーはそのファイルツリーと共にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="967ef-165">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="967ef-166">例 11: リモートフォルダーの内容全体をローカルコンピューターに再帰的にコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-166">Example 11: Recursively copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="967ef-167">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-167">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="967ef-168">`Copy-Item`コマンドレットは、 `C:\MyRemoteData\scripts` `D:\MyLocalData\scripts` 変数に格納されているセッション情報を使用して、リモートフォルダーからローカルフォルダーにコンテンツ全体をコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-168">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData\scripts` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="967ef-169">**再帰** パラメーターが使用されるため、スクリプトフォルダーがまだ存在しない場合は、この操作によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="967ef-169">Because the **Recurse** parameter is used, the operation creates the scripts folder if it doesn't already exist.</span></span> <span data-ttu-id="967ef-170">Scripts フォルダーにサブフォルダー内のファイルが含まれている場合、それらのサブフォルダーはそのファイルツリーと共にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="967ef-170">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\scripts" -FromSession $Session -Recurse
```

### <span data-ttu-id="967ef-171">例 12: フォルダーツリーから現在のフォルダーにファイルを再帰的にコピーする</span><span class="sxs-lookup"><span data-stu-id="967ef-171">Example 12: Recursively copy files from a folder tree into the current folder</span></span>

<span data-ttu-id="967ef-172">この例では、複数レベルのフォルダー構造から1つのフラットフォルダーにファイルをコピーする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="967ef-172">This example shows how to copy files from a multilevel folder structure into a single flat folder.</span></span>
<span data-ttu-id="967ef-173">最初の3つのコマンドは、既存のフォルダー構造と2つのファイル (両方の名前) の内容を表示し `file3.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-173">The first three commands show the existing folder structure and the contents of two files, both names `file3.txt`.</span></span>

```powershell
PS C:\temp\test> (Get-ChildItem C:\temp\tree -Recurse).FullName
C:\temp\tree\subfolder
C:\temp\tree\file1.txt
C:\temp\tree\file2.txt
C:\temp\tree\file3.txt
C:\temp\tree\subfolder\file3.txt
C:\temp\tree\subfolder\file4.txt
C:\temp\tree\subfolder\file5.txt

PS C:\temp\test> Get-Content C:\temp\tree\file3.txt
This is file3.txt in the root folder

PS C:\temp\test> Get-Content C:\temp\tree\subfolder\file3.txt
This is file3.txt in the subfolder

PS C:\temp\test> Copy-Item -Path C:\temp\tree -Filter *.txt -Recurse -Container:$false
PS C:\temp\test> (Get-ChildItem . -Recurse).FullName
C:\temp\test\subfolder
C:\temp\test\file1.txt
C:\temp\test\file2.txt
C:\temp\test\file3.txt
C:\temp\test\file4.txt
C:\temp\test\file5.txt

PS C:\temp\test> Get-Content .\file3.txt
This is file3.txt in the subfolder
```

<span data-ttu-id="967ef-174">`Copy-Item`コマンドレットでは、 **Container** パラメーターがに設定されてい `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-174">The `Copy-Item` cmdlet has the **Container** parameter set to `$false`.</span></span> <span data-ttu-id="967ef-175">これにより、ソースフォルダーの内容がコピーされますが、フォルダー構造は保持されません。</span><span class="sxs-lookup"><span data-stu-id="967ef-175">This causes the contents of the source folder to be copied but does not preserve the folder structure.</span></span> <span data-ttu-id="967ef-176">同じ名前のファイルがコピー先フォルダーで上書きされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="967ef-176">Notice that files with the same name are overwritten in the destination folder.</span></span>

## <span data-ttu-id="967ef-177">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="967ef-177">PARAMETERS</span></span>

### <span data-ttu-id="967ef-178">-Confirm</span><span class="sxs-lookup"><span data-stu-id="967ef-178">-Confirm</span></span>

<span data-ttu-id="967ef-179">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="967ef-179">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="967ef-180">-コンテナー</span><span class="sxs-lookup"><span data-stu-id="967ef-180">-Container</span></span>

<span data-ttu-id="967ef-181">コピー操作中に、このコマンドレットによってコンテナーオブジェクトが保持されることを示します。</span><span class="sxs-lookup"><span data-stu-id="967ef-181">Indicates that this cmdlet preserves container objects during the copy operation.</span></span> <span data-ttu-id="967ef-182">既定では、 **Container** パラメーターは **True** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="967ef-182">By default, the **Container** parameter is set to **True**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="967ef-183">-Credential</span><span class="sxs-lookup"><span data-stu-id="967ef-183">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="967ef-184">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="967ef-184">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="967ef-185">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="967ef-185">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="967ef-186">-Destination</span><span class="sxs-lookup"><span data-stu-id="967ef-186">-Destination</span></span>

<span data-ttu-id="967ef-187">新しい場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="967ef-187">Specifies the path to the new location.</span></span> <span data-ttu-id="967ef-188">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="967ef-188">The default is the current directory.</span></span>

<span data-ttu-id="967ef-189">コピーする項目の名前を変更するには、 **Destination** パラメーターの値に新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="967ef-189">To rename the item being copied, specify a new name in the value of the **Destination** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="967ef-190">-除外</span><span class="sxs-lookup"><span data-stu-id="967ef-190">-Exclude</span></span>

<span data-ttu-id="967ef-191">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="967ef-191">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="967ef-192">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="967ef-192">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="967ef-193">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-193">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="967ef-194">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="967ef-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="967ef-195">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-195">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="967ef-196">-Filter</span><span class="sxs-lookup"><span data-stu-id="967ef-196">-Filter</span></span>

<span data-ttu-id="967ef-197">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="967ef-197">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="967ef-198">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="967ef-198">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="967ef-199">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="967ef-199">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="967ef-200">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="967ef-200">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="967ef-201">-Force</span><span class="sxs-lookup"><span data-stu-id="967ef-201">-Force</span></span>

<span data-ttu-id="967ef-202">このコマンドレットが、読み取り専用のファイルまたはエイリアスを使用したコピーなど、変更できない項目をコピーすることを示します。</span><span class="sxs-lookup"><span data-stu-id="967ef-202">Indicates that this cmdlet copies items that can't otherwise be changed, such as copying over a read-only file or alias.</span></span>

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

### <span data-ttu-id="967ef-203">-FromSession</span><span class="sxs-lookup"><span data-stu-id="967ef-203">-FromSession</span></span>

<span data-ttu-id="967ef-204">リモートファイルのコピー元の **PSSession** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="967ef-204">Specifies the **PSSession** object from which a remote file is being copied.</span></span> <span data-ttu-id="967ef-205">このパラメーターを使用する場合、 **Path** パラメーターと **LiteralPath** パラメーターは、リモートコンピューター上のローカルパスを参照します。</span><span class="sxs-lookup"><span data-stu-id="967ef-205">When you use this parameter, the **Path** and **LiteralPath** parameters refer to the local path on the remote machine.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="967ef-206">-Include</span><span class="sxs-lookup"><span data-stu-id="967ef-206">-Include</span></span>

<span data-ttu-id="967ef-207">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="967ef-207">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="967ef-208">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="967ef-208">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="967ef-209">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-209">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="967ef-210">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="967ef-210">Wildcard characters are permitted.</span></span> <span data-ttu-id="967ef-211">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-211">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="967ef-212">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="967ef-212">-LiteralPath</span></span>

<span data-ttu-id="967ef-213">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="967ef-213">Specifies a path to one or more locations.</span></span> <span data-ttu-id="967ef-214">**LiteralPath** の値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="967ef-214">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="967ef-215">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="967ef-215">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="967ef-216">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="967ef-216">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="967ef-217">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="967ef-217">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="967ef-218">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="967ef-218">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="967ef-219">-PassThru</span><span class="sxs-lookup"><span data-stu-id="967ef-219">-PassThru</span></span>

<span data-ttu-id="967ef-220">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="967ef-220">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="967ef-221">既定では、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="967ef-221">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="967ef-222">-Path</span><span class="sxs-lookup"><span data-stu-id="967ef-222">-Path</span></span>

<span data-ttu-id="967ef-223">文字列配列として、コピーする項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="967ef-223">Specifies, as a string array, the path to the items to copy.</span></span> <span data-ttu-id="967ef-224">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="967ef-224">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="967ef-225">-再帰</span><span class="sxs-lookup"><span data-stu-id="967ef-225">-Recurse</span></span>

<span data-ttu-id="967ef-226">このコマンドレットが再帰コピーを行うことを示します。</span><span class="sxs-lookup"><span data-stu-id="967ef-226">Indicates that this cmdlet does a recursive copy.</span></span>

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

### <span data-ttu-id="967ef-227">-ToSession</span><span class="sxs-lookup"><span data-stu-id="967ef-227">-ToSession</span></span>

<span data-ttu-id="967ef-228">リモートファイルのコピー先の **PSSession** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="967ef-228">Specifies the **PSSession** object to which a remote file is being copied.</span></span> <span data-ttu-id="967ef-229">このパラメーターを使用すると、 **Destination** パラメーターはリモートコンピューター上のローカルパスを参照します。</span><span class="sxs-lookup"><span data-stu-id="967ef-229">When you use this parameter, the **Destination** parameter refers to the local path on the remote machine.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="967ef-230">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="967ef-230">-WhatIf</span></span>

<span data-ttu-id="967ef-231">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="967ef-231">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="967ef-232">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="967ef-232">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="967ef-233">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="967ef-233">CommonParameters</span></span>

<span data-ttu-id="967ef-234">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="967ef-234">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="967ef-235">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="967ef-235">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="967ef-236">入力</span><span class="sxs-lookup"><span data-stu-id="967ef-236">INPUTS</span></span>

### <span data-ttu-id="967ef-237">System.String</span><span class="sxs-lookup"><span data-stu-id="967ef-237">System.String</span></span>

<span data-ttu-id="967ef-238">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="967ef-238">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="967ef-239">出力</span><span class="sxs-lookup"><span data-stu-id="967ef-239">OUTPUTS</span></span>

### <span data-ttu-id="967ef-240">None またはコピーされた項目を表すオブジェクト</span><span class="sxs-lookup"><span data-stu-id="967ef-240">None or an object representing the copied item</span></span>

<span data-ttu-id="967ef-241">**PassThru** パラメーターを使用すると、このコマンドレットは、コピーされた項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="967ef-241">When you use the **PassThru** parameter, this cmdlet returns an object that represents the copied item.</span></span> <span data-ttu-id="967ef-242">それ以外の場合、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="967ef-242">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="967ef-243">注</span><span class="sxs-lookup"><span data-stu-id="967ef-243">NOTES</span></span>

<span data-ttu-id="967ef-244">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="967ef-244">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="967ef-245">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="967ef-245">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="967ef-246">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="967ef-246">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="967ef-247">関連リンク</span><span class="sxs-lookup"><span data-stu-id="967ef-247">RELATED LINKS</span></span>

[<span data-ttu-id="967ef-248">about_Providers</span><span class="sxs-lookup"><span data-stu-id="967ef-248">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="967ef-249">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="967ef-249">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="967ef-250">Get-Item</span><span class="sxs-lookup"><span data-stu-id="967ef-250">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="967ef-251">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="967ef-251">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="967ef-252">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="967ef-252">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="967ef-253">Move-Item</span><span class="sxs-lookup"><span data-stu-id="967ef-253">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="967ef-254">New-Item</span><span class="sxs-lookup"><span data-stu-id="967ef-254">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="967ef-255">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="967ef-255">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="967ef-256">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="967ef-256">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="967ef-257">Set-Item</span><span class="sxs-lookup"><span data-stu-id="967ef-257">Set-Item</span></span>](Set-Item.md)
