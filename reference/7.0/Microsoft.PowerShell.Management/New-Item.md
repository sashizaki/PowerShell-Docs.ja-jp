---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: f24988833faaf56395b95e08430bbcc9fb6d2746
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210971"
---
# <span data-ttu-id="29001-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="29001-103">New-Item</span></span>

## <span data-ttu-id="29001-104">概要</span><span class="sxs-lookup"><span data-stu-id="29001-104">SYNOPSIS</span></span>
<span data-ttu-id="29001-105">新しい項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="29001-105">Creates a new item.</span></span>

## <span data-ttu-id="29001-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29001-106">SYNTAX</span></span>

### <span data-ttu-id="29001-107">pathSet (既定)</span><span class="sxs-lookup"><span data-stu-id="29001-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="29001-108">nameSet</span><span class="sxs-lookup"><span data-stu-id="29001-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="29001-109">Description</span><span class="sxs-lookup"><span data-stu-id="29001-109">DESCRIPTION</span></span>

<span data-ttu-id="29001-110">コマンドレットにより、 `New-Item` 新しい項目が作成され、その値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="29001-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="29001-111">作成できる項目の種類は、項目の場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="29001-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="29001-112">たとえば、ファイルシステムで、に `New-Item` よってファイルとフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="29001-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="29001-113">レジストリで、は `New-Item` レジストリキーとエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="29001-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="29001-114">`New-Item` では、作成する項目の値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="29001-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="29001-115">たとえば、新しいファイルを作成するときに、は `New-Item` ファイルに初期コンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="29001-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="29001-116">例</span><span class="sxs-lookup"><span data-stu-id="29001-116">EXAMPLES</span></span>

### <span data-ttu-id="29001-117">例 1: 現在のディレクトリにファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="29001-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="29001-118">このコマンドは、現在のディレクトリに "testfile1.txt" という名前のテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="29001-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="29001-119">**Path** パラメーターの値のドット ('. ') は、現在のディレクトリを示します。</span><span class="sxs-lookup"><span data-stu-id="29001-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="29001-120">**Value** パラメーターの後の引用符で囲まれたテキストは、内容としてファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="29001-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="29001-121">例 2: ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="29001-121">Example 2: Create a directory</span></span>

<span data-ttu-id="29001-122">このコマンドにより、ドライブに "ログログ" という名前のディレクトリが作成さ `C:` れます。</span><span class="sxs-lookup"><span data-stu-id="29001-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="29001-123">**ItemType** パラメーターは、新しい項目がファイルまたはその他のファイルシステムオブジェクトではなく、ディレクトリであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="29001-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="29001-124">例 3: プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="29001-124">Example 3: Create a profile</span></span>

<span data-ttu-id="29001-125">このコマンドは、変数で指定されたパスに PowerShell プロファイルを作成し `$profile` ます。</span><span class="sxs-lookup"><span data-stu-id="29001-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="29001-126">プロファイルを使用して、PowerShell をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="29001-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="29001-127">`$profile` は、"CurrentUser/CurrentHost" プロファイルのパスとファイル名を格納する自動 (組み込み) 変数です。</span><span class="sxs-lookup"><span data-stu-id="29001-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="29001-128">既定では、PowerShell にはパスとファイル名が格納されていますが、プロファイルは存在しません。</span><span class="sxs-lookup"><span data-stu-id="29001-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="29001-129">このコマンドでは、 `$profile` 変数はファイルのパスを表します。</span><span class="sxs-lookup"><span data-stu-id="29001-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="29001-130">**ItemType** パラメーターは、コマンドによってファイルが作成されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="29001-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="29001-131">**Force** パラメーターを使用すると、パス内のディレクトリが存在しない場合でも、プロファイルパスにファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="29001-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="29001-132">プロファイルを作成したら、エイリアス、関数、およびスクリプトをプロファイルに入力して、シェルをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="29001-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="29001-133">詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) 」および「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29001-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

### <span data-ttu-id="29001-134">例 4: 別のディレクトリにディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="29001-134">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="29001-135">この例では、"C:\ テスト" ディレクトリに新しい Scripts ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="29001-135">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="29001-136">新しいディレクトリ項目の名前 "Scripts" は、[ **名前** ] の値に指定されるのではなく、 **Path** パラメーターの値に含まれます。</span><span class="sxs-lookup"><span data-stu-id="29001-136">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="29001-137">構文に示すとおり、どちらのコマンド形式も有効です。</span><span class="sxs-lookup"><span data-stu-id="29001-137">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="29001-138">例 5: 複数のファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="29001-138">Example 5: Create multiple files</span></span>

<span data-ttu-id="29001-139">この例では、2つの異なるディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="29001-139">This example creates files in two different directories.</span></span> <span data-ttu-id="29001-140">**Path** は複数の文字列を受け取るため、複数の項目を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="29001-140">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="29001-141">例 6: ワイルドカードを使用して複数のディレクトリにファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="29001-141">Example 6: Use wildcards to create files in multiple directories</span></span>

<span data-ttu-id="29001-142">`New-Item`コマンドレットでは、 **Path** パラメーターでワイルドカードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="29001-142">The `New-Item` cmdlet supports wildcards in the **Path** parameter.</span></span> <span data-ttu-id="29001-143">次のコマンドは、 `temp.txt` **Path** パラメーターでワイルドカードによって指定されたすべてのディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="29001-143">The following command creates a `temp.txt` file in all of the directories specified by the wildcards in the **Path** parameter.</span></span>

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

<span data-ttu-id="29001-144">`Get-ChildItem`コマンドレットでは、ディレクトリの下に3つのディレクトリが表示され `C:\Temp` ます。</span><span class="sxs-lookup"><span data-stu-id="29001-144">The `Get-ChildItem` cmdlet shows three directories under the `C:\Temp` directory.</span></span> <span data-ttu-id="29001-145">ワイルドカードを使用すると、 `New-Item` `temp.txt` 現在のディレクトリの下にあるすべてのディレクトリにファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="29001-145">Using wildcards the `New-Item` cmdlet creates a `temp.txt` file in all of the directories under the current directory.</span></span> <span data-ttu-id="29001-146">`New-Item`コマンドレットは、作成した項目を出力します。これは、 `Select-Object` 新しく作成されたファイルのパスを確認するために、にパイプされます。</span><span class="sxs-lookup"><span data-stu-id="29001-146">The `New-Item` cmdlet outputs the items you created, which is piped to `Select-Object` to verify the paths of the newly created files.</span></span>

### <span data-ttu-id="29001-147">例 7: ファイルまたはフォルダーへのシンボリックリンクを作成する</span><span class="sxs-lookup"><span data-stu-id="29001-147">Example 7: Create a symbolic link to a file or folder</span></span>

<span data-ttu-id="29001-148">この例では、現在のフォルダー内の Notice.txt ファイルへのシンボリックリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="29001-148">This example creates a symbolic link to the Notice.txt file in the current folder.</span></span>

```powershell
$link = New-Item -ItemType SymbolicLink -Path .\link -Target .\Notice.txt
$link | Select-Object LinkType, Target
```

```Output
LinkType     Target
--------     ------
SymbolicLink {.\Notice.txt}
```

<span data-ttu-id="29001-149">この例では、 **Target** は **Value** パラメーターのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="29001-149">In this example, **Target** is an alias for the **Value** parameter.</span></span> <span data-ttu-id="29001-150">シンボリックリンクのターゲットは、相対パスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="29001-150">The target of the symbolic link can be a relative path.</span></span> <span data-ttu-id="29001-151">PowerShell v1.0 より前のバージョンでは、ターゲットは完全修飾パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="29001-151">Prior to PowerShell v6.2, the target must be a fully-qualified path.</span></span>

> [!CAUTION]
> <span data-ttu-id="29001-152">Windows 上のフォルダーに **SymbolicLink** を作成する場合は、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29001-152">If you are creating a **SymbolicLink** to a folder on Windows, you must use a fully-qualified path.</span></span> <span data-ttu-id="29001-153">相対パスを使用する場合、リンクはディレクトリ型のリンクではなく、ファイルの種類のリンクとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="29001-153">If you use a relative path, the link is created as a file-type link instead of a directory-type link.</span></span>

### <span data-ttu-id="29001-154">例 8:-Force パラメーターを使用してフォルダーの再作成を試みる</span><span class="sxs-lookup"><span data-stu-id="29001-154">Example 8: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="29001-155">この例では、内にファイルを含むフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="29001-155">This example creates a folder with a file inside.</span></span> <span data-ttu-id="29001-156">次に、はを使用して同じフォルダーを作成しようとし `-Force` ます。</span><span class="sxs-lookup"><span data-stu-id="29001-156">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="29001-157">フォルダーは上書きされませんが、ファイルがそのまま作成された状態で既存のフォルダーオブジェクトを返すだけです。</span><span class="sxs-lookup"><span data-stu-id="29001-157">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

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

### <span data-ttu-id="29001-158">例 9:-Force パラメーターを使用して既存のファイルを上書きする</span><span class="sxs-lookup"><span data-stu-id="29001-158">Example 9: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="29001-159">この例では、値を指定してファイルを作成し、を使用してファイルを再作成し `-Force` ます。</span><span class="sxs-lookup"><span data-stu-id="29001-159">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="29001-160">これにより、既存のファイルが上書きされ、length プロパティで確認できるようにコンテンツが失われます。</span><span class="sxs-lookup"><span data-stu-id="29001-160">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

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
> <span data-ttu-id="29001-161">スイッチと共にを使用してレジストリキーを作成する場合、 `New-Item` `-Force` コマンドはファイルを上書きする場合と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="29001-161">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="29001-162">レジストリキーが既に存在する場合、キーとすべてのプロパティと値は空のレジストリキーで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="29001-162">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="29001-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29001-163">PARAMETERS</span></span>

### <span data-ttu-id="29001-164">-Credential</span><span class="sxs-lookup"><span data-stu-id="29001-164">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="29001-165">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="29001-165">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="29001-166">このコマンドレットの実行時に別のユーザーの権限を借用するか、資格情報を昇格するには、を使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="29001-166">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="29001-167">-Force</span><span class="sxs-lookup"><span data-stu-id="29001-167">-Force</span></span>

<span data-ttu-id="29001-168">このコマンドレットに対して、既存の読み取り専用項目を上書きする項目を強制的に作成します。</span><span class="sxs-lookup"><span data-stu-id="29001-168">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="29001-169">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="29001-169">Implementation varies from provider to provider.</span></span> <span data-ttu-id="29001-170">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="29001-170">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="29001-171">-ItemType</span><span class="sxs-lookup"><span data-stu-id="29001-171">-ItemType</span></span>

<span data-ttu-id="29001-172">プロバイダーによって指定された新しい項目の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="29001-172">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="29001-173">このパラメーターで使用できる値は、使用している現在のプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="29001-173">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="29001-174">場所がドライブにある場合は、 `FileSystem` 次の値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="29001-174">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="29001-175">ファイル</span><span class="sxs-lookup"><span data-stu-id="29001-175">File</span></span>
- <span data-ttu-id="29001-176">ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="29001-176">Directory</span></span>
- <span data-ttu-id="29001-177">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="29001-177">SymbolicLink</span></span>
- <span data-ttu-id="29001-178">ジャンクション</span><span class="sxs-lookup"><span data-stu-id="29001-178">Junction</span></span>
- <span data-ttu-id="29001-179">Hardlink create</span><span class="sxs-lookup"><span data-stu-id="29001-179">HardLink</span></span>

> [!NOTE]
> <span data-ttu-id="29001-180">Windows で型を作成するには、 `SymbolicLink` 管理者として昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29001-180">Creating a `SymbolicLink` type on Windows requires elevation as administrator.</span></span> <span data-ttu-id="29001-181">ただし、開発者モードが有効になっている Windows 10 (ビルド14972以降) では、シンボリックリンクの作成を昇格する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="29001-181">However, Windows 10 (build 14972 or newer) with Developer Mode enabled no longer requires elevation creating symbolic links.</span></span>

<span data-ttu-id="29001-182">ドライブで `Certificate` は、次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="29001-182">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="29001-183">証明書プロバイダー</span><span class="sxs-lookup"><span data-stu-id="29001-183">Certificate Provider</span></span>
- <span data-ttu-id="29001-184">Certificate</span><span class="sxs-lookup"><span data-stu-id="29001-184">Certificate</span></span>
- <span data-ttu-id="29001-185">ストア</span><span class="sxs-lookup"><span data-stu-id="29001-185">Store</span></span>
- <span data-ttu-id="29001-186">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="29001-186">StoreLocation</span></span>

<span data-ttu-id="29001-187">詳細については、「 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29001-187">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="29001-188">-Name</span><span class="sxs-lookup"><span data-stu-id="29001-188">-Name</span></span>

<span data-ttu-id="29001-189">新しい項目の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="29001-189">Specifies the name of the new item.</span></span> <span data-ttu-id="29001-190">**名前** または **パス** のパラメーター値に新しい項目の名前を指定したり、[ **名前** ] または [ **パス** ] の値で新しい項目のパスを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="29001-190">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="29001-191">**Name** パラメーターを使用して渡された項目名は、 **Path** パラメーターの値に対して相対的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="29001-191">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="29001-192">-Path</span><span class="sxs-lookup"><span data-stu-id="29001-192">-Path</span></span>

<span data-ttu-id="29001-193">新しい項目の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="29001-193">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="29001-194">既定値は、 **Path** が省略された場合の現在の場所です。</span><span class="sxs-lookup"><span data-stu-id="29001-194">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="29001-195">[ **名前** ] に新しい項目の名前を指定することも、[ **パス** ] に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="29001-195">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="29001-196">**Name** パラメーターを使用して渡された項目名は、 **Path** パラメーターの値に対して相対的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="29001-196">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="29001-197">このコマンドレットでは、 **Path** パラメーターは他のコマンドレットの **LiteralPath** パラメーターのように機能します。</span><span class="sxs-lookup"><span data-stu-id="29001-197">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="29001-198">ワイルドカード文字は解釈されません。</span><span class="sxs-lookup"><span data-stu-id="29001-198">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="29001-199">すべての文字が場所のプロバイダーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="29001-199">All characters are passed to the location's provider.</span></span> <span data-ttu-id="29001-200">プロバイダーがすべての文字をサポートしていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29001-200">The provider may not support all characters.</span></span> <span data-ttu-id="29001-201">たとえば、アスタリスク () 文字を含むファイル名を作成することはできません `*` 。</span><span class="sxs-lookup"><span data-stu-id="29001-201">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="29001-202">-Value</span><span class="sxs-lookup"><span data-stu-id="29001-202">-Value</span></span>

<span data-ttu-id="29001-203">新しい項目の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="29001-203">Specifies the value of the new item.</span></span> <span data-ttu-id="29001-204">パイプを使用して値をにパイプすることもでき `New-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="29001-204">You can also pipe a value to `New-Item`.</span></span>

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

### <span data-ttu-id="29001-205">-Confirm</span><span class="sxs-lookup"><span data-stu-id="29001-205">-Confirm</span></span>

<span data-ttu-id="29001-206">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="29001-206">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="29001-207">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="29001-207">-WhatIf</span></span>

<span data-ttu-id="29001-208">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="29001-208">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="29001-209">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="29001-209">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="29001-210">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="29001-210">CommonParameters</span></span>

<span data-ttu-id="29001-211">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="29001-211">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="29001-212">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29001-212">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="29001-213">入力</span><span class="sxs-lookup"><span data-stu-id="29001-213">INPUTS</span></span>

### <span data-ttu-id="29001-214">System.Object</span><span class="sxs-lookup"><span data-stu-id="29001-214">System.Object</span></span>

<span data-ttu-id="29001-215">パイプを使用して、新しい項目の値をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="29001-215">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="29001-216">出力</span><span class="sxs-lookup"><span data-stu-id="29001-216">OUTPUTS</span></span>

### <span data-ttu-id="29001-217">System.Object</span><span class="sxs-lookup"><span data-stu-id="29001-217">System.Object</span></span>

<span data-ttu-id="29001-218">このコマンドレットは、作成された項目を返します。</span><span class="sxs-lookup"><span data-stu-id="29001-218">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="29001-219">注</span><span class="sxs-lookup"><span data-stu-id="29001-219">NOTES</span></span>

<span data-ttu-id="29001-220">`New-Item` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="29001-220">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="29001-221">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="29001-221">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="29001-222">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29001-222">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="29001-223">関連リンク</span><span class="sxs-lookup"><span data-stu-id="29001-223">RELATED LINKS</span></span>

[<span data-ttu-id="29001-224">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="29001-224">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="29001-225">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="29001-225">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="29001-226">Get-Item</span><span class="sxs-lookup"><span data-stu-id="29001-226">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="29001-227">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="29001-227">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="29001-228">Move-Item</span><span class="sxs-lookup"><span data-stu-id="29001-228">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="29001-229">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="29001-229">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="29001-230">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="29001-230">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="29001-231">Set-Item</span><span class="sxs-lookup"><span data-stu-id="29001-231">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="29001-232">about_Providers</span><span class="sxs-lookup"><span data-stu-id="29001-232">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
