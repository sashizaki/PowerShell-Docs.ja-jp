---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-Item
ms.openlocfilehash: ee2d8b8a3b736a59b5af4a81710a0d29dd2238d5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599920"
---
# <span data-ttu-id="22fcc-102">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="22fcc-102">Copy-Item</span></span>

## <span data-ttu-id="22fcc-103">概要</span><span class="sxs-lookup"><span data-stu-id="22fcc-103">SYNOPSIS</span></span>
<span data-ttu-id="22fcc-104">項目をある場所から別の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="22fcc-104">Copies an item from one location to another.</span></span>

## <span data-ttu-id="22fcc-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="22fcc-105">SYNTAX</span></span>

### <span data-ttu-id="22fcc-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="22fcc-106">Path (Default)</span></span>

```
Copy-Item [-Path] <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="22fcc-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="22fcc-107">LiteralPath</span></span>

```
Copy-Item -LiteralPath <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

## <span data-ttu-id="22fcc-108">Description</span><span class="sxs-lookup"><span data-stu-id="22fcc-108">DESCRIPTION</span></span>

<span data-ttu-id="22fcc-109">`Copy-Item`コマンドレットは、同じ名前空間内のある場所から別の場所に項目をコピーします。</span><span class="sxs-lookup"><span data-stu-id="22fcc-109">The `Copy-Item` cmdlet copies an item from one location to another location in the same namespace.</span></span>
<span data-ttu-id="22fcc-110">たとえば、ファイルをフォルダーにコピーすることはできますが、ファイルを証明書ドライブにコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-110">For instance, it can copy a file to a folder, but it can't copy a file to a certificate drive.</span></span>

<span data-ttu-id="22fcc-111">このコマンドレットは、コピーされる項目を切り取りまたは削除しません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-111">This cmdlet doesn't cut or delete the items being copied.</span></span> <span data-ttu-id="22fcc-112">コマンドレットがコピーできる項目は、項目を公開する PowerShell プロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="22fcc-112">The particular items that the cmdlet can copy depend on the PowerShell provider that exposes the item.</span></span> <span data-ttu-id="22fcc-113">たとえば、ファイルシステムドライブのファイルとディレクトリ、レジストリキー、レジストリドライブ内のエントリをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-113">For instance, it can copy files and directories in a file system drive and registry keys and entries in the registry drive.</span></span>

<span data-ttu-id="22fcc-114">このコマンドレットは、同じコマンドで項目のコピーと名前の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-114">This cmdlet can copy and rename items in the same command.</span></span> <span data-ttu-id="22fcc-115">項目の名前を変更するには、 **Destination** パラメーターの値に新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-115">To rename an item, enter the new name in the value of the **Destination** parameter.</span></span> <span data-ttu-id="22fcc-116">項目の名前を変更し、コピーしない場合は、コマンドレットを使用し `Rename-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-116">To rename an item and not copy it, use the `Rename-Item` cmdlet.</span></span>

## <span data-ttu-id="22fcc-117">例</span><span class="sxs-lookup"><span data-stu-id="22fcc-117">EXAMPLES</span></span>

### <span data-ttu-id="22fcc-118">例 1: 指定されたディレクトリにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-118">Example 1: Copy a file to the specified directory</span></span>

<span data-ttu-id="22fcc-119">この例では、 `mar1604.log.txt` ファイルをディレクトリにコピーし `C:\Presentation` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-119">This example copies the `mar1604.log.txt` file to the `C:\Presentation` directory.</span></span> <span data-ttu-id="22fcc-120">元のファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-120">The original file isn't deleted.</span></span>

```powershell
Copy-Item "C:\Wabash\Logfiles\mar1604.log.txt" -Destination "C:\Presentation"
```

### <span data-ttu-id="22fcc-121">例 2: 既存のディレクトリにディレクトリの内容をコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-121">Example 2: Copy directory contents to an existing directory</span></span>

<span data-ttu-id="22fcc-122">この例では、ディレクトリの内容を `C:\Logfiles` 既存のディレクトリにコピーし `C:\Drawings` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-122">This example copies the contents of the `C:\Logfiles` directory into the existing `C:\Drawings` directory.</span></span> <span data-ttu-id="22fcc-123">`Logfiles`ディレクトリはコピーされません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-123">The `Logfiles` directory isn't copied.</span></span>

<span data-ttu-id="22fcc-124">ディレクトリに `Logfiles` サブディレクトリ内のファイルが含まれている場合、それらのサブディレクトリはそのファイルツリーと共にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-124">If the `Logfiles` directory contains files in subdirectories, those subdirectories are copied with their file trees intact.</span></span> <span data-ttu-id="22fcc-125">既定では、 **Container** パラメーターは **True** に設定されています。これにより、ディレクトリ構造が保持されます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-125">By default, the **Container** parameter is set to **True**, which preserves the directory structure.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings" -Recurse
```

> [!NOTE]
> <span data-ttu-id="22fcc-126">コピーにディレクトリを含める必要がある場合は、 `Logfiles` `\*` **パス** からを削除します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-126">If you need to include the `Logfiles` directory in the copy, remove the `\*` from the **Path**.</span></span>
> <span data-ttu-id="22fcc-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-127">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings" -Recurse`

### <span data-ttu-id="22fcc-128">例 3: ディレクトリとコンテンツを新しいディレクトリにコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-128">Example 3: Copy directory and contents to a new directory</span></span>

<span data-ttu-id="22fcc-129">この例では、ソースディレクトリの内容をコピー `C:\Logfiles` し、新しいコピー先ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-129">This example copies the contents of the `C:\Logfiles` source directory and creates a new destination directory.</span></span> <span data-ttu-id="22fcc-130">新しいコピー先ディレクトリは、 `\Logs` で作成され `C:\Drawings` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-130">The new destination directory, `\Logs` is created in `C:\Drawings`.</span></span>

<span data-ttu-id="22fcc-131">ソースディレクトリの名前を含めるには、 **例 2** に示すように、既存のコピー先ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="22fcc-131">To include the source directory's name, copy to an existing destination directory as shown in **Example 2**.</span></span> <span data-ttu-id="22fcc-132">または、新しい宛先ディレクトリに、ソースディレクトリと同じ名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-132">Or, name the new destination directory with the same as the source directory.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings\Logs" -Recurse
```

> [!NOTE]
> <span data-ttu-id="22fcc-133">**パス** にが含まれている場合 `\*` 、ディレクトリのすべてのファイルの内容 (サブディレクトリツリーを含む) が新しいコピー先ディレクトリにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-133">If the **Path** includes `\*`, all the directory's file contents, including the subdirectory trees, are copied to the new destination directory.</span></span> <span data-ttu-id="22fcc-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-134">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings\Logs" -Recurse`

### <span data-ttu-id="22fcc-135">例 4: 指定したディレクトリにファイルをコピーし、ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="22fcc-135">Example 4: Copy a file to the specified directory and rename the file</span></span>

<span data-ttu-id="22fcc-136">この例では、コマンドレットを使用して、 `Copy-Item` `Get-Widget.ps1` ディレクトリからディレクトリにスクリプトをコピーし `\\Server01\Share` `\\Server12\ScriptArchive` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-136">This example uses the `Copy-Item` cmdlet to copy the `Get-Widget.ps1` script from the `\\Server01\Share` directory to the `\\Server12\ScriptArchive` directory.</span></span> <span data-ttu-id="22fcc-137">コピー操作の一部として、コマンドは項目名をからに変更し、 `Get-Widget.ps1` `Get-Widget.ps1.txt` 電子メールメッセージに添付できるようにします。</span><span class="sxs-lookup"><span data-stu-id="22fcc-137">As part of the copy operation, the command changes the item name from `Get-Widget.ps1` to `Get-Widget.ps1.txt`, so it can be attached to email messages.</span></span>

```powershell
Copy-Item "\\Server01\Share\Get-Widget.ps1" -Destination "\\Server12\ScriptArchive\Get-Widget.ps1.txt"
```

### <span data-ttu-id="22fcc-138">例 5: リモートコンピューターにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-138">Example 5: Copy a file to a remote computer</span></span>

<span data-ttu-id="22fcc-139">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-139">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="22fcc-140">この `Copy-Item` コマンドレットは、 `test.log` `D:\Folder001` `C:\Folder001_Copy` 変数に格納されているセッション情報を使用して、フォルダーからリモートコンピューター上のフォルダーにコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-140">The `Copy-Item` cmdlet copies `test.log` from the `D:\Folder001` folder to the `C:\Folder001_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="22fcc-141">元のファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-141">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "D:\Folder001\test.log" -Destination "C:\Folder001_Copy\" -ToSession $Session
```

### <span data-ttu-id="22fcc-142">例 6: リモートコンピューターにフォルダーをコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-142">Example 6: Copy a folder to a remote computer</span></span>

<span data-ttu-id="22fcc-143">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-143">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="22fcc-144">この `Copy-Item` コマンドレットは、 `D:\Folder002` `C:\Folder002_Copy` 変数に格納されているセッション情報を使用して、リモートコンピューター上のディレクトリにフォルダーをコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-144">The `Copy-Item` cmdlet copies the `D:\Folder002` folder to the `C:\Folder002_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="22fcc-145">サブフォルダーまたはファイルは、 **再帰** スイッチを使用せずにコピーされません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-145">Any subfolders or files are not copied without using the **Recurse** switch.</span></span>
<span data-ttu-id="22fcc-146">フォルダーがまだ存在しない場合は、操作によって作成され `Folder002_Copy` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-146">The operation creates the `Folder002_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server02" -Credential "Contoso\User01"
Copy-Item "D:\Folder002\" -Destination "C:\Folder002_Copy\" -ToSession $Session
```

### <span data-ttu-id="22fcc-147">例 7: フォルダーの内容全体をリモートコンピューターに再帰的にコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-147">Example 7: Recursively copy the entire contents of a folder to a remote computer</span></span>

<span data-ttu-id="22fcc-148">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-148">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="22fcc-149">この `Copy-Item` コマンドレットは、 `D:\Folder003` `C:\Folder003_Copy` 変数に格納されているセッション情報を使用して、フォルダーの内容全体をリモートコンピューター上のディレクトリにコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-149">The `Copy-Item` cmdlet copies the entire contents from the `D:\Folder003` folder to the `C:\Folder003_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="22fcc-150">サブフォルダーは、そのファイルツリーと共にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-150">The subfolders are copied with their file trees intact.</span></span> <span data-ttu-id="22fcc-151">フォルダーがまだ存在しない場合は、操作によって作成され `Folder003_Copy` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-151">The operation creates the `Folder003_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder003\" -Destination "C:\Folder003_Copy\" -ToSession $Session -Recurse
```

### <span data-ttu-id="22fcc-152">例 8: ファイルをリモートコンピューターにコピーし、ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="22fcc-152">Example 8: Copy a file to a remote computer and then rename the file</span></span>

<span data-ttu-id="22fcc-153">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-153">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="22fcc-154">この `Copy-Item` コマンドレットは、 `scriptingexample.ps1` `D:\Folder004` `C:\Folder004_Copy` 変数に格納されているセッション情報を使用して、フォルダーからリモートコンピューター上のフォルダーにコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-154">The `Copy-Item` cmdlet copies `scriptingexample.ps1` from the `D:\Folder004` folder to the `C:\Folder004_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="22fcc-155">コピー操作の一部として、コマンドは項目名をからに変更し、 `scriptingexample.ps1` `scriptingexample_copy.ps1` 電子メールメッセージに添付できるようにします。</span><span class="sxs-lookup"><span data-stu-id="22fcc-155">As part of the copy operation, the command changes the item name from `scriptingexample.ps1` to `scriptingexample_copy.ps1`, so it can be attached to email messages.</span></span> <span data-ttu-id="22fcc-156">元のファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-156">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder004\scriptingexample.ps1" -Destination "C:\Folder004_Copy\scriptingexample_copy.ps1" -ToSession $Session
```

### <span data-ttu-id="22fcc-157">例 9: ローカルコンピューターにリモートファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-157">Example 9: Copy a remote file to the local computer</span></span>

<span data-ttu-id="22fcc-158">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-158">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="22fcc-159">`Copy-Item`コマンドレットは、 `test.log` `C:\MyRemoteData\` `D:\MyLocalData` 変数に格納されているセッション情報を使用して、リモートからローカルフォルダーにコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-159">The `Copy-Item` cmdlet copies `test.log` from the remote `C:\MyRemoteData\` to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="22fcc-160">元のファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-160">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\test.log" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="22fcc-161">例 10: リモートフォルダーの内容全体をローカルコンピューターにコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-161">Example 10: Copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="22fcc-162">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-162">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="22fcc-163">`Copy-Item`コマンドレットは、 `C:\MyRemoteData\scripts` `D:\MyLocalData` 変数に格納されているセッション情報を使用して、リモートフォルダーからローカルフォルダーにコンテンツ全体をコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-163">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="22fcc-164">Scripts フォルダーにサブフォルダー内のファイルが含まれている場合、それらのサブフォルダーはそのファイルツリーと共にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-164">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="22fcc-165">例 11: リモートフォルダーの内容全体をローカルコンピューターに再帰的にコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-165">Example 11: Recursively copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="22fcc-166">の資格情報を使用して **Server01** という名前のリモートコンピューターにセッションが作成され、と `Contoso\User01` いう名前の変数に結果が格納され `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-166">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="22fcc-167">`Copy-Item`コマンドレットは、 `C:\MyRemoteData\scripts` `D:\MyLocalData\scripts` 変数に格納されているセッション情報を使用して、リモートフォルダーからローカルフォルダーにコンテンツ全体をコピーし `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-167">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData\scripts` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="22fcc-168">**再帰** パラメーターが使用されるため、スクリプトフォルダーがまだ存在しない場合は、この操作によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-168">Because the **Recurse** parameter is used, the operation creates the scripts folder if it doesn't already exist.</span></span> <span data-ttu-id="22fcc-169">Scripts フォルダーにサブフォルダー内のファイルが含まれている場合、それらのサブフォルダーはそのファイルツリーと共にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-169">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\scripts" -FromSession $Session -Recurse
```

### <span data-ttu-id="22fcc-170">例 12: フォルダーツリーから現在のフォルダーにファイルを再帰的にコピーする</span><span class="sxs-lookup"><span data-stu-id="22fcc-170">Example 12: Recursively copy files from a folder tree into the current folder</span></span>

<span data-ttu-id="22fcc-171">この例では、複数レベルのフォルダー構造から1つのフラットフォルダーにファイルをコピーする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-171">This example shows how to copy files from a multilevel folder structure into a single flat folder.</span></span>
<span data-ttu-id="22fcc-172">最初の3つのコマンドは、既存のフォルダー構造と2つのファイル (両方の名前) の内容を表示し `file3.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-172">The first three commands show the existing folder structure and the contents of two files, both names `file3.txt`.</span></span>

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

<span data-ttu-id="22fcc-173">`Copy-Item`コマンドレットでは、 **Container** パラメーターがに設定されてい `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-173">The `Copy-Item` cmdlet has the **Container** parameter set to `$false`.</span></span> <span data-ttu-id="22fcc-174">これにより、ソースフォルダーの内容がコピーされますが、フォルダー構造は保持されません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-174">This causes the contents of the source folder to be copied but does not preserve the folder structure.</span></span> <span data-ttu-id="22fcc-175">同じ名前のファイルがコピー先フォルダーで上書きされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22fcc-175">Notice that files with the same name are overwritten in the destination folder.</span></span>

## <span data-ttu-id="22fcc-176">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="22fcc-176">PARAMETERS</span></span>

### <span data-ttu-id="22fcc-177">-Confirm</span><span class="sxs-lookup"><span data-stu-id="22fcc-177">-Confirm</span></span>

<span data-ttu-id="22fcc-178">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-178">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="22fcc-179">-コンテナー</span><span class="sxs-lookup"><span data-stu-id="22fcc-179">-Container</span></span>

<span data-ttu-id="22fcc-180">コピー操作中に、このコマンドレットによってコンテナーオブジェクトが保持されることを示します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-180">Indicates that this cmdlet preserves container objects during the copy operation.</span></span> <span data-ttu-id="22fcc-181">既定では、 **Container** パラメーターは **True** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="22fcc-181">By default, the **Container** parameter is set to **True**.</span></span>

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

### <span data-ttu-id="22fcc-182">-Credential</span><span class="sxs-lookup"><span data-stu-id="22fcc-182">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="22fcc-183">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-183">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="22fcc-184">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-184">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="22fcc-185">-Destination</span><span class="sxs-lookup"><span data-stu-id="22fcc-185">-Destination</span></span>

<span data-ttu-id="22fcc-186">新しい場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-186">Specifies the path to the new location.</span></span> <span data-ttu-id="22fcc-187">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="22fcc-187">The default is the current directory.</span></span>

<span data-ttu-id="22fcc-188">コピーする項目の名前を変更するには、 **Destination** パラメーターの値に新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-188">To rename the item being copied, specify a new name in the value of the **Destination** parameter.</span></span>

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

### <span data-ttu-id="22fcc-189">-除外</span><span class="sxs-lookup"><span data-stu-id="22fcc-189">-Exclude</span></span>

<span data-ttu-id="22fcc-190">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-190">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="22fcc-191">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-191">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="22fcc-192">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-192">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="22fcc-193">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-193">Wildcard characters are permitted.</span></span> <span data-ttu-id="22fcc-194">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-194">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="22fcc-195">-Filter</span><span class="sxs-lookup"><span data-stu-id="22fcc-195">-Filter</span></span>

<span data-ttu-id="22fcc-196">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-196">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="22fcc-197">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="22fcc-197">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="22fcc-198">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22fcc-198">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="22fcc-199">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="22fcc-199">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span>

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

### <span data-ttu-id="22fcc-200">-Force</span><span class="sxs-lookup"><span data-stu-id="22fcc-200">-Force</span></span>

<span data-ttu-id="22fcc-201">このコマンドレットが、読み取り専用のファイルまたはエイリアスを使用したコピーなど、変更できない項目をコピーすることを示します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-201">Indicates that this cmdlet copies items that can't otherwise be changed, such as copying over a read-only file or alias.</span></span>

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

### <span data-ttu-id="22fcc-202">-FromSession</span><span class="sxs-lookup"><span data-stu-id="22fcc-202">-FromSession</span></span>

<span data-ttu-id="22fcc-203">リモートファイルのコピー元の **PSSession** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-203">Specifies the **PSSession** object from which a remote file is being copied.</span></span> <span data-ttu-id="22fcc-204">このパラメーターを使用する場合、 **Path** パラメーターと **LiteralPath** パラメーターは、リモートコンピューター上のローカルパスを参照します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-204">When you use this parameter, the **Path** and **LiteralPath** parameters refer to the local path on the remote machine.</span></span>

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

### <span data-ttu-id="22fcc-205">-Include</span><span class="sxs-lookup"><span data-stu-id="22fcc-205">-Include</span></span>

<span data-ttu-id="22fcc-206">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-206">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="22fcc-207">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-207">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="22fcc-208">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-208">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="22fcc-209">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-209">Wildcard characters are permitted.</span></span> <span data-ttu-id="22fcc-210">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-210">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="22fcc-211">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="22fcc-211">-LiteralPath</span></span>

<span data-ttu-id="22fcc-212">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-212">Specifies a path to one or more locations.</span></span> <span data-ttu-id="22fcc-213">**LiteralPath** の値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-213">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="22fcc-214">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-214">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="22fcc-215">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-215">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="22fcc-216">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-216">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="22fcc-217">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22fcc-217">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="22fcc-218">-PassThru</span><span class="sxs-lookup"><span data-stu-id="22fcc-218">-PassThru</span></span>

<span data-ttu-id="22fcc-219">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-219">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="22fcc-220">既定では、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-220">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="22fcc-221">-Path</span><span class="sxs-lookup"><span data-stu-id="22fcc-221">-Path</span></span>

<span data-ttu-id="22fcc-222">文字列配列として、コピーする項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-222">Specifies, as a string array, the path to the items to copy.</span></span> <span data-ttu-id="22fcc-223">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-223">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="22fcc-224">-再帰</span><span class="sxs-lookup"><span data-stu-id="22fcc-224">-Recurse</span></span>

<span data-ttu-id="22fcc-225">このコマンドレットが再帰コピーを行うことを示します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-225">Indicates that this cmdlet does a recursive copy.</span></span>

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

### <span data-ttu-id="22fcc-226">-ToSession</span><span class="sxs-lookup"><span data-stu-id="22fcc-226">-ToSession</span></span>

<span data-ttu-id="22fcc-227">リモートファイルのコピー先の **PSSession** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-227">Specifies the **PSSession** object to which a remote file is being copied.</span></span> <span data-ttu-id="22fcc-228">このパラメーターを使用すると、 **Destination** パラメーターはリモートコンピューター上のローカルパスを参照します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-228">When you use this parameter, the **Destination** parameter refers to the local path on the remote machine.</span></span>

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

### <span data-ttu-id="22fcc-229">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="22fcc-229">-WhatIf</span></span>

<span data-ttu-id="22fcc-230">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-230">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="22fcc-231">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-231">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="22fcc-232">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="22fcc-232">CommonParameters</span></span>

<span data-ttu-id="22fcc-233">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-233">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="22fcc-234">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22fcc-234">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="22fcc-235">入力</span><span class="sxs-lookup"><span data-stu-id="22fcc-235">INPUTS</span></span>

### <span data-ttu-id="22fcc-236">System.String</span><span class="sxs-lookup"><span data-stu-id="22fcc-236">System.String</span></span>

<span data-ttu-id="22fcc-237">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="22fcc-237">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="22fcc-238">出力</span><span class="sxs-lookup"><span data-stu-id="22fcc-238">OUTPUTS</span></span>

### <span data-ttu-id="22fcc-239">None またはコピーされた項目を表すオブジェクト</span><span class="sxs-lookup"><span data-stu-id="22fcc-239">None or an object representing the copied item</span></span>

<span data-ttu-id="22fcc-240">**PassThru** パラメーターを使用すると、このコマンドレットは、コピーされた項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-240">When you use the **PassThru** parameter, this cmdlet returns an object that represents the copied item.</span></span> <span data-ttu-id="22fcc-241">それ以外の場合、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="22fcc-241">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="22fcc-242">注</span><span class="sxs-lookup"><span data-stu-id="22fcc-242">NOTES</span></span>

<span data-ttu-id="22fcc-243">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="22fcc-243">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="22fcc-244">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="22fcc-244">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="22fcc-245">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22fcc-245">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="22fcc-246">関連リンク</span><span class="sxs-lookup"><span data-stu-id="22fcc-246">RELATED LINKS</span></span>

[<span data-ttu-id="22fcc-247">about_Providers</span><span class="sxs-lookup"><span data-stu-id="22fcc-247">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="22fcc-248">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="22fcc-248">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="22fcc-249">Get-Item</span><span class="sxs-lookup"><span data-stu-id="22fcc-249">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="22fcc-250">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="22fcc-250">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="22fcc-251">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="22fcc-251">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="22fcc-252">Move-Item</span><span class="sxs-lookup"><span data-stu-id="22fcc-252">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="22fcc-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="22fcc-253">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="22fcc-254">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="22fcc-254">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="22fcc-255">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="22fcc-255">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="22fcc-256">Set-Item</span><span class="sxs-lookup"><span data-stu-id="22fcc-256">Set-Item</span></span>](Set-Item.md)

