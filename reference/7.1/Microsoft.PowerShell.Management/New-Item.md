---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: 50a7dba8c4e9cb1cfabd42f39e9fdfb43f22f9b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211603"
---
# <span data-ttu-id="d4035-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="d4035-103">New-Item</span></span>

## <span data-ttu-id="d4035-104">概要</span><span class="sxs-lookup"><span data-stu-id="d4035-104">SYNOPSIS</span></span>
<span data-ttu-id="d4035-105">新しい項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4035-105">Creates a new item.</span></span>

## <span data-ttu-id="d4035-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d4035-106">SYNTAX</span></span>

### <span data-ttu-id="d4035-107">pathSet (既定)</span><span class="sxs-lookup"><span data-stu-id="d4035-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d4035-108">nameSet</span><span class="sxs-lookup"><span data-stu-id="d4035-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d4035-109">Description</span><span class="sxs-lookup"><span data-stu-id="d4035-109">DESCRIPTION</span></span>

<span data-ttu-id="d4035-110">コマンドレットにより、 `New-Item` 新しい項目が作成され、その値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="d4035-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="d4035-111">作成できる項目の種類は、項目の場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d4035-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="d4035-112">たとえば、ファイルシステムで、に `New-Item` よってファイルとフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4035-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="d4035-113">レジストリで、は `New-Item` レジストリキーとエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4035-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="d4035-114">`New-Item` では、作成する項目の値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4035-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="d4035-115">たとえば、新しいファイルを作成するときに、は `New-Item` ファイルに初期コンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d4035-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="d4035-116">例</span><span class="sxs-lookup"><span data-stu-id="d4035-116">EXAMPLES</span></span>

### <span data-ttu-id="d4035-117">例 1: 現在のディレクトリにファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d4035-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="d4035-118">このコマンドは、現在のディレクトリに "testfile1.txt" という名前のテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4035-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="d4035-119">**Path** パラメーターの値のドット ('. ') は、現在のディレクトリを示します。</span><span class="sxs-lookup"><span data-stu-id="d4035-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="d4035-120">**Value** パラメーターの後の引用符で囲まれたテキストは、内容としてファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d4035-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="d4035-121">例 2: ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="d4035-121">Example 2: Create a directory</span></span>

<span data-ttu-id="d4035-122">このコマンドにより、ドライブに "ログログ" という名前のディレクトリが作成さ `C:` れます。</span><span class="sxs-lookup"><span data-stu-id="d4035-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="d4035-123">**ItemType** パラメーターは、新しい項目がファイルまたはその他のファイルシステムオブジェクトではなく、ディレクトリであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4035-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="d4035-124">例 3: プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d4035-124">Example 3: Create a profile</span></span>

<span data-ttu-id="d4035-125">このコマンドは、変数で指定されたパスに PowerShell プロファイルを作成し `$profile` ます。</span><span class="sxs-lookup"><span data-stu-id="d4035-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="d4035-126">プロファイルを使用して、PowerShell をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d4035-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="d4035-127">`$profile` は、"CurrentUser/CurrentHost" プロファイルのパスとファイル名を格納する自動 (組み込み) 変数です。</span><span class="sxs-lookup"><span data-stu-id="d4035-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="d4035-128">既定では、PowerShell にはパスとファイル名が格納されていますが、プロファイルは存在しません。</span><span class="sxs-lookup"><span data-stu-id="d4035-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="d4035-129">このコマンドでは、 `$profile` 変数はファイルのパスを表します。</span><span class="sxs-lookup"><span data-stu-id="d4035-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="d4035-130">**ItemType** パラメーターは、コマンドによってファイルが作成されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4035-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="d4035-131">**Force** パラメーターを使用すると、パス内のディレクトリが存在しない場合でも、プロファイルパスにファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d4035-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="d4035-132">プロファイルを作成したら、エイリアス、関数、およびスクリプトをプロファイルに入力して、シェルをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d4035-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="d4035-133">詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) 」および「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4035-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

### <span data-ttu-id="d4035-134">例 4: 別のディレクトリにディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="d4035-134">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="d4035-135">この例では、"C:\ テスト" ディレクトリに新しい Scripts ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4035-135">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="d4035-136">新しいディレクトリ項目の名前 "Scripts" は、[ **名前** ] の値に指定されるのではなく、 **Path** パラメーターの値に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4035-136">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="d4035-137">構文に示すとおり、どちらのコマンド形式も有効です。</span><span class="sxs-lookup"><span data-stu-id="d4035-137">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="d4035-138">例 5: 複数のファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d4035-138">Example 5: Create multiple files</span></span>

<span data-ttu-id="d4035-139">この例では、2つの異なるディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4035-139">This example creates files in two different directories.</span></span> <span data-ttu-id="d4035-140">**Path** は複数の文字列を受け取るため、複数の項目を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4035-140">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="d4035-141">例 6: ワイルドカードを使用して複数のディレクトリにファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d4035-141">Example 6: Use wildcards to create files in multiple directories</span></span>

<span data-ttu-id="d4035-142">`New-Item`コマンドレットでは、 **Path** パラメーターでワイルドカードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d4035-142">The `New-Item` cmdlet supports wildcards in the **Path** parameter.</span></span> <span data-ttu-id="d4035-143">次のコマンドは、 `temp.txt` **Path** パラメーターでワイルドカードによって指定されたすべてのディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4035-143">The following command creates a `temp.txt` file in all of the directories specified by the wildcards in the **Path** parameter.</span></span>

```powershell
Get-ChildItem -Path C:\Temp\
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d-----        5/15/2019   6:45 AM        1   One
d-----        5/15/2019   6:45 AM        1   Two
d-----        5/15/2019   6:45 AM        1   Three
```

```powershell
New-Item -Path * -Name temp.txt -ItemType File | Select-Object FullName
```

```Output
FullName
--------
C:\Temp\One\temp.txt
C:\Temp\Three\temp.txt
C:\Temp\Two\temp.txt
```

<span data-ttu-id="d4035-144">`Get-ChildItem`コマンドレットでは、ディレクトリの下に3つのディレクトリが表示され `C:\Temp` ます。</span><span class="sxs-lookup"><span data-stu-id="d4035-144">The `Get-ChildItem` cmdlet shows three directories under the `C:\Temp` directory.</span></span> <span data-ttu-id="d4035-145">ワイルドカードを使用すると、 `New-Item` `temp.txt` 現在のディレクトリの下にあるすべてのディレクトリにファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4035-145">Using wildcards the `New-Item` cmdlet creates a `temp.txt` file in all of the directories under the current directory.</span></span> <span data-ttu-id="d4035-146">`New-Item`コマンドレットは、作成した項目を出力します。これは、 `Select-Object` 新しく作成されたファイルのパスを確認するために、にパイプされます。</span><span class="sxs-lookup"><span data-stu-id="d4035-146">The `New-Item` cmdlet outputs the items you created, which is piped to `Select-Object` to verify the paths of the newly created files.</span></span>

### <span data-ttu-id="d4035-147">例 7: ファイルまたはフォルダーへのシンボリックリンクを作成する</span><span class="sxs-lookup"><span data-stu-id="d4035-147">Example 7: Create a symbolic link to a file or folder</span></span>

<span data-ttu-id="d4035-148">この例では、現在のフォルダー内の Notice.txt ファイルへのシンボリックリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4035-148">This example creates a symbolic link to the Notice.txt file in the current folder.</span></span>

```powershell
$link = New-Item -ItemType SymbolicLink -Path .\link -Target .\Notice.txt
$link | Select-Object LinkType, Target
```

```Output
LinkType     Target
--------     ------
SymbolicLink {.\Notice.txt}
```

<span data-ttu-id="d4035-149">この例では、 **Target** は **Value** パラメーターのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="d4035-149">In this example, **Target** is an alias for the **Value** parameter.</span></span> <span data-ttu-id="d4035-150">シンボリックリンクのターゲットは、相対パスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d4035-150">The target of the symbolic link can be a relative path.</span></span> <span data-ttu-id="d4035-151">PowerShell v1.0 より前のバージョンでは、ターゲットは完全修飾パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4035-151">Prior to PowerShell v6.2, the target must be a fully-qualified path.</span></span>

<span data-ttu-id="d4035-152">PowerShell 7.1 以降では、相対パスを使用して Windows 上のフォルダーへの **SymbolicLink** を作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d4035-152">Beginning in PowerShell 7.1, you can now create to a **SymbolicLink** to a folder on Windows using a relative path.</span></span>

### <span data-ttu-id="d4035-153">例 8:-Force パラメーターを使用してフォルダーの再作成を試みる</span><span class="sxs-lookup"><span data-stu-id="d4035-153">Example 8: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="d4035-154">この例では、内にファイルを含むフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4035-154">This example creates a folder with a file inside.</span></span> <span data-ttu-id="d4035-155">次に、はを使用して同じフォルダーを作成しようとし `-Force` ます。</span><span class="sxs-lookup"><span data-stu-id="d4035-155">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="d4035-156">フォルダーは上書きされませんが、ファイルがそのまま作成された状態で既存のフォルダーオブジェクトを返すだけです。</span><span class="sxs-lookup"><span data-stu-id="d4035-156">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### <span data-ttu-id="d4035-157">例 9:-Force パラメーターを使用して既存のファイルを上書きする</span><span class="sxs-lookup"><span data-stu-id="d4035-157">Example 9: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="d4035-158">この例では、値を指定してファイルを作成し、を使用してファイルを再作成し `-Force` ます。</span><span class="sxs-lookup"><span data-stu-id="d4035-158">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="d4035-159">これにより、既存のファイルが上書きされ、length プロパティで確認できるようにコンテンツが失われます。</span><span class="sxs-lookup"><span data-stu-id="d4035-159">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> <span data-ttu-id="d4035-160">スイッチと共にを使用してレジストリキーを作成する場合、 `New-Item` `-Force` コマンドはファイルを上書きする場合と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="d4035-160">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="d4035-161">レジストリキーが既に存在する場合、キーとすべてのプロパティと値は空のレジストリキーで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d4035-161">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="d4035-162">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d4035-162">PARAMETERS</span></span>

### <span data-ttu-id="d4035-163">-Credential</span><span class="sxs-lookup"><span data-stu-id="d4035-163">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d4035-164">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d4035-164">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="d4035-165">このコマンドレットの実行時に別のユーザーの権限を借用するか、資格情報を昇格するには、を使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="d4035-165">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="d4035-166">-Force</span><span class="sxs-lookup"><span data-stu-id="d4035-166">-Force</span></span>

<span data-ttu-id="d4035-167">このコマンドレットに対して、既存の読み取り専用項目を上書きする項目を強制的に作成します。</span><span class="sxs-lookup"><span data-stu-id="d4035-167">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="d4035-168">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="d4035-168">Implementation varies from provider to provider.</span></span> <span data-ttu-id="d4035-169">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="d4035-169">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d4035-170">-ItemType</span><span class="sxs-lookup"><span data-stu-id="d4035-170">-ItemType</span></span>

<span data-ttu-id="d4035-171">プロバイダーによって指定された新しい項目の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4035-171">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="d4035-172">このパラメーターで使用できる値は、使用している現在のプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d4035-172">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="d4035-173">場所がドライブにある場合は、 `FileSystem` 次の値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="d4035-173">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="d4035-174">ファイル</span><span class="sxs-lookup"><span data-stu-id="d4035-174">File</span></span>
- <span data-ttu-id="d4035-175">ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="d4035-175">Directory</span></span>
- <span data-ttu-id="d4035-176">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="d4035-176">SymbolicLink</span></span>
- <span data-ttu-id="d4035-177">ジャンクション</span><span class="sxs-lookup"><span data-stu-id="d4035-177">Junction</span></span>
- <span data-ttu-id="d4035-178">Hardlink create</span><span class="sxs-lookup"><span data-stu-id="d4035-178">HardLink</span></span>

> [!NOTE]
> <span data-ttu-id="d4035-179">Windows で型を作成するには、 `SymbolicLink` 管理者として昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4035-179">Creating a `SymbolicLink` type on Windows requires elevation as administrator.</span></span> <span data-ttu-id="d4035-180">ただし、開発者モードが有効になっている Windows 10 (ビルド14972以降) では、シンボリックリンクの作成を昇格する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d4035-180">However, Windows 10 (build 14972 or newer) with Developer Mode enabled no longer requires elevation creating symbolic links.</span></span>

<span data-ttu-id="d4035-181">ドライブで `Certificate` は、次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d4035-181">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="d4035-182">証明書プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d4035-182">Certificate Provider</span></span>
- <span data-ttu-id="d4035-183">Certificate</span><span class="sxs-lookup"><span data-stu-id="d4035-183">Certificate</span></span>
- <span data-ttu-id="d4035-184">ストア</span><span class="sxs-lookup"><span data-stu-id="d4035-184">Store</span></span>
- <span data-ttu-id="d4035-185">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="d4035-185">StoreLocation</span></span>

<span data-ttu-id="d4035-186">詳細については、「 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4035-186">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d4035-187">-Name</span><span class="sxs-lookup"><span data-stu-id="d4035-187">-Name</span></span>

<span data-ttu-id="d4035-188">新しい項目の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4035-188">Specifies the name of the new item.</span></span> <span data-ttu-id="d4035-189">**名前** または **パス** のパラメーター値に新しい項目の名前を指定したり、[ **名前** ] または [ **パス** ] の値で新しい項目のパスを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d4035-189">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="d4035-190">**Name** パラメーターを使用して渡された項目名は、 **Path** パラメーターの値に対して相対的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4035-190">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d4035-191">-Path</span><span class="sxs-lookup"><span data-stu-id="d4035-191">-Path</span></span>

<span data-ttu-id="d4035-192">新しい項目の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4035-192">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="d4035-193">既定値は、 **Path** が省略された場合の現在の場所です。</span><span class="sxs-lookup"><span data-stu-id="d4035-193">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="d4035-194">[ **名前** ] に新しい項目の名前を指定することも、[ **パス** ] に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="d4035-194">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="d4035-195">**Name** パラメーターを使用して渡された項目名は、 **Path** パラメーターの値に対して相対的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4035-195">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="d4035-196">このコマンドレットでは、 **Path** パラメーターは他のコマンドレットの **LiteralPath** パラメーターのように機能します。</span><span class="sxs-lookup"><span data-stu-id="d4035-196">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="d4035-197">ワイルドカード文字は解釈されません。</span><span class="sxs-lookup"><span data-stu-id="d4035-197">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="d4035-198">すべての文字が場所のプロバイダーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d4035-198">All characters are passed to the location's provider.</span></span> <span data-ttu-id="d4035-199">プロバイダーがすべての文字をサポートしていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d4035-199">The provider may not support all characters.</span></span> <span data-ttu-id="d4035-200">たとえば、アスタリスク () 文字を含むファイル名を作成することはできません `*` 。</span><span class="sxs-lookup"><span data-stu-id="d4035-200">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d4035-201">-Value</span><span class="sxs-lookup"><span data-stu-id="d4035-201">-Value</span></span>

<span data-ttu-id="d4035-202">新しい項目の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4035-202">Specifies the value of the new item.</span></span> <span data-ttu-id="d4035-203">パイプを使用して値をにパイプすることもでき `New-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="d4035-203">You can also pipe a value to `New-Item`.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d4035-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d4035-204">-Confirm</span></span>

<span data-ttu-id="d4035-205">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4035-205">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d4035-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d4035-206">-WhatIf</span></span>

<span data-ttu-id="d4035-207">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="d4035-207">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d4035-208">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d4035-208">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d4035-209">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d4035-209">CommonParameters</span></span>

<span data-ttu-id="d4035-210">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="d4035-210">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d4035-211">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4035-211">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d4035-212">入力</span><span class="sxs-lookup"><span data-stu-id="d4035-212">INPUTS</span></span>

### <span data-ttu-id="d4035-213">System.Object</span><span class="sxs-lookup"><span data-stu-id="d4035-213">System.Object</span></span>

<span data-ttu-id="d4035-214">パイプを使用して、新しい項目の値をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="d4035-214">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="d4035-215">出力</span><span class="sxs-lookup"><span data-stu-id="d4035-215">OUTPUTS</span></span>

### <span data-ttu-id="d4035-216">System.Object</span><span class="sxs-lookup"><span data-stu-id="d4035-216">System.Object</span></span>

<span data-ttu-id="d4035-217">このコマンドレットは、作成された項目を返します。</span><span class="sxs-lookup"><span data-stu-id="d4035-217">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="d4035-218">注</span><span class="sxs-lookup"><span data-stu-id="d4035-218">NOTES</span></span>

<span data-ttu-id="d4035-219">`New-Item` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d4035-219">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d4035-220">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="d4035-220">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="d4035-221">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4035-221">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d4035-222">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d4035-222">RELATED LINKS</span></span>

[<span data-ttu-id="d4035-223">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d4035-223">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="d4035-224">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="d4035-224">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="d4035-225">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d4035-225">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="d4035-226">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="d4035-226">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="d4035-227">Move-Item</span><span class="sxs-lookup"><span data-stu-id="d4035-227">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="d4035-228">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d4035-228">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="d4035-229">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="d4035-229">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="d4035-230">Set-Item</span><span class="sxs-lookup"><span data-stu-id="d4035-230">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="d4035-231">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d4035-231">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

