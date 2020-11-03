---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: b1657d369d44d575ee7bed8b76d36224ea2748f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214616"
---
# <span data-ttu-id="27e58-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="27e58-103">New-Item</span></span>

## <span data-ttu-id="27e58-104">概要</span><span class="sxs-lookup"><span data-stu-id="27e58-104">SYNOPSIS</span></span>
<span data-ttu-id="27e58-105">新しい項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="27e58-105">Creates a new item.</span></span>

## <span data-ttu-id="27e58-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27e58-106">SYNTAX</span></span>

### <span data-ttu-id="27e58-107">pathSet (既定)</span><span class="sxs-lookup"><span data-stu-id="27e58-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="27e58-108">nameSet</span><span class="sxs-lookup"><span data-stu-id="27e58-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="27e58-109">Description</span><span class="sxs-lookup"><span data-stu-id="27e58-109">DESCRIPTION</span></span>

<span data-ttu-id="27e58-110">コマンドレットにより、 `New-Item` 新しい項目が作成され、その値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="27e58-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="27e58-111">作成できる項目の種類は、項目の場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="27e58-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="27e58-112">たとえば、ファイルシステムで、に `New-Item` よってファイルとフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="27e58-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="27e58-113">レジストリで、は `New-Item` レジストリキーとエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e58-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="27e58-114">`New-Item` では、作成する項目の値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="27e58-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="27e58-115">たとえば、新しいファイルを作成するときに、は `New-Item` ファイルに初期コンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="27e58-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="27e58-116">例</span><span class="sxs-lookup"><span data-stu-id="27e58-116">EXAMPLES</span></span>

### <span data-ttu-id="27e58-117">例 1: 現在のディレクトリにファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="27e58-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="27e58-118">このコマンドは、現在のディレクトリに "testfile1.txt" という名前のテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e58-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="27e58-119">**Path** パラメーターの値のドット ('. ') は、現在のディレクトリを示します。</span><span class="sxs-lookup"><span data-stu-id="27e58-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="27e58-120">**Value** パラメーターの後の引用符で囲まれたテキストは、内容としてファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="27e58-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="27e58-121">例 2: ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="27e58-121">Example 2: Create a directory</span></span>

<span data-ttu-id="27e58-122">このコマンドにより、ドライブに "ログログ" という名前のディレクトリが作成さ `C:` れます。</span><span class="sxs-lookup"><span data-stu-id="27e58-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="27e58-123">**ItemType** パラメーターは、新しい項目がファイルまたはその他のファイルシステムオブジェクトではなく、ディレクトリであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="27e58-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="27e58-124">例 3: プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="27e58-124">Example 3: Create a profile</span></span>

<span data-ttu-id="27e58-125">このコマンドは、変数で指定されたパスに PowerShell プロファイルを作成し `$profile` ます。</span><span class="sxs-lookup"><span data-stu-id="27e58-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="27e58-126">プロファイルを使用して、PowerShell をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="27e58-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="27e58-127">`$profile` は、"CurrentUser/CurrentHost" プロファイルのパスとファイル名を格納する自動 (組み込み) 変数です。</span><span class="sxs-lookup"><span data-stu-id="27e58-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="27e58-128">既定では、PowerShell にはパスとファイル名が格納されていますが、プロファイルは存在しません。</span><span class="sxs-lookup"><span data-stu-id="27e58-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="27e58-129">このコマンドでは、 `$profile` 変数はファイルのパスを表します。</span><span class="sxs-lookup"><span data-stu-id="27e58-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="27e58-130">**ItemType** パラメーターは、コマンドによってファイルが作成されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="27e58-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="27e58-131">**Force** パラメーターを使用すると、パス内のディレクトリが存在しない場合でも、プロファイルパスにファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="27e58-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="27e58-132">プロファイルを作成したら、エイリアス、関数、およびスクリプトをプロファイルに入力して、シェルをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="27e58-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="27e58-133">詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) 」および「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e58-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

> [!NOTE]
> <span data-ttu-id="27e58-134">このメソッドを使用してファイルを作成すると、生成されるファイルはバイト順マーク (BOM) なしで UTF-8 としてエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="27e58-134">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

### <span data-ttu-id="27e58-135">例 4: 別のディレクトリにディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="27e58-135">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="27e58-136">この例では、"C:\ テスト" ディレクトリに新しい Scripts ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e58-136">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="27e58-137">新しいディレクトリ項目の名前 "Scripts" は、[ **名前** ] の値に指定されるのではなく、 **Path** パラメーターの値に含まれます。</span><span class="sxs-lookup"><span data-stu-id="27e58-137">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="27e58-138">構文に示すとおり、どちらのコマンド形式も有効です。</span><span class="sxs-lookup"><span data-stu-id="27e58-138">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="27e58-139">例 5: 複数のファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="27e58-139">Example 5: Create multiple files</span></span>

<span data-ttu-id="27e58-140">この例では、2つの異なるディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e58-140">This example creates files in two different directories.</span></span> <span data-ttu-id="27e58-141">**Path** は複数の文字列を受け取るため、複数の項目を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="27e58-141">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="27e58-142">例 6:-Force パラメーターを使用してフォルダーの再作成を試みる</span><span class="sxs-lookup"><span data-stu-id="27e58-142">Example 6: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="27e58-143">この例では、内にファイルを含むフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="27e58-143">This example creates a folder with a file inside.</span></span> <span data-ttu-id="27e58-144">次に、はを使用して同じフォルダーを作成しようとし `-Force` ます。</span><span class="sxs-lookup"><span data-stu-id="27e58-144">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="27e58-145">フォルダーは上書きされませんが、ファイルがそのまま作成された状態で既存のフォルダーオブジェクトを返すだけです。</span><span class="sxs-lookup"><span data-stu-id="27e58-145">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

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

### <span data-ttu-id="27e58-146">例 7:-Force パラメーターを使用して既存のファイルを上書きする</span><span class="sxs-lookup"><span data-stu-id="27e58-146">Example 7: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="27e58-147">この例では、値を指定してファイルを作成し、を使用してファイルを再作成し `-Force` ます。</span><span class="sxs-lookup"><span data-stu-id="27e58-147">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="27e58-148">これにより、既存のファイルが上書きされ、length プロパティで確認できるようにコンテンツが失われます。</span><span class="sxs-lookup"><span data-stu-id="27e58-148">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

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
> <span data-ttu-id="27e58-149">スイッチと共にを使用してレジストリキーを作成する場合、 `New-Item` `-Force` コマンドはファイルを上書きする場合と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="27e58-149">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="27e58-150">レジストリキーが既に存在する場合、キーとすべてのプロパティと値は空のレジストリキーで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="27e58-150">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="27e58-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27e58-151">PARAMETERS</span></span>

### <span data-ttu-id="27e58-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="27e58-152">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="27e58-153">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27e58-153">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="27e58-154">このコマンドレットの実行時に別のユーザーの権限を借用するか、資格情報を昇格するには、を使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="27e58-154">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="27e58-155">-Force</span><span class="sxs-lookup"><span data-stu-id="27e58-155">-Force</span></span>

<span data-ttu-id="27e58-156">このコマンドレットに対して、既存の読み取り専用項目を上書きする項目を強制的に作成します。</span><span class="sxs-lookup"><span data-stu-id="27e58-156">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="27e58-157">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="27e58-157">Implementation varies from provider to provider.</span></span> <span data-ttu-id="27e58-158">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="27e58-158">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="27e58-159">-ItemType</span><span class="sxs-lookup"><span data-stu-id="27e58-159">-ItemType</span></span>

<span data-ttu-id="27e58-160">プロバイダーによって指定された新しい項目の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="27e58-160">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="27e58-161">このパラメーターで使用できる値は、使用している現在のプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="27e58-161">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="27e58-162">場所がドライブにある場合は、 `FileSystem` 次の値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="27e58-162">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="27e58-163">ファイル</span><span class="sxs-lookup"><span data-stu-id="27e58-163">File</span></span>
- <span data-ttu-id="27e58-164">ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="27e58-164">Directory</span></span>
- <span data-ttu-id="27e58-165">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="27e58-165">SymbolicLink</span></span>
- <span data-ttu-id="27e58-166">ジャンクション</span><span class="sxs-lookup"><span data-stu-id="27e58-166">Junction</span></span>
- <span data-ttu-id="27e58-167">Hardlink create</span><span class="sxs-lookup"><span data-stu-id="27e58-167">HardLink</span></span>

<span data-ttu-id="27e58-168">このメソッドを使用してファイルを作成すると、生成されるファイルはバイト順マーク (BOM) なしで UTF-8 としてエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="27e58-168">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

<span data-ttu-id="27e58-169">ドライブで `Certificate` は、次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="27e58-169">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="27e58-170">証明書プロバイダー</span><span class="sxs-lookup"><span data-stu-id="27e58-170">Certificate Provider</span></span>
- <span data-ttu-id="27e58-171">Certificate</span><span class="sxs-lookup"><span data-stu-id="27e58-171">Certificate</span></span>
- <span data-ttu-id="27e58-172">ストア</span><span class="sxs-lookup"><span data-stu-id="27e58-172">Store</span></span>
- <span data-ttu-id="27e58-173">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="27e58-173">StoreLocation</span></span>

<span data-ttu-id="27e58-174">詳細については、「 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e58-174">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="27e58-175">-Name</span><span class="sxs-lookup"><span data-stu-id="27e58-175">-Name</span></span>

<span data-ttu-id="27e58-176">新しい項目の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="27e58-176">Specifies the name of the new item.</span></span> <span data-ttu-id="27e58-177">**名前** または **パス** のパラメーター値に新しい項目の名前を指定したり、[ **名前** ] または [ **パス** ] の値で新しい項目のパスを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="27e58-177">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="27e58-178">**Name** パラメーターを使用して渡された項目名は、 **Path** パラメーターの値に対して相対的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="27e58-178">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="27e58-179">-Path</span><span class="sxs-lookup"><span data-stu-id="27e58-179">-Path</span></span>

<span data-ttu-id="27e58-180">新しい項目の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="27e58-180">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="27e58-181">既定値は、 **Path** が省略された場合の現在の場所です。</span><span class="sxs-lookup"><span data-stu-id="27e58-181">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="27e58-182">[ **名前** ] に新しい項目の名前を指定することも、[ **パス** ] に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="27e58-182">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="27e58-183">**Name** パラメーターを使用して渡された項目名は、 **Path** パラメーターの値に対して相対的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="27e58-183">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="27e58-184">このコマンドレットでは、 **Path** パラメーターは他のコマンドレットの **LiteralPath** パラメーターのように機能します。</span><span class="sxs-lookup"><span data-stu-id="27e58-184">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="27e58-185">ワイルドカード文字は解釈されません。</span><span class="sxs-lookup"><span data-stu-id="27e58-185">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="27e58-186">すべての文字が場所のプロバイダーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="27e58-186">All characters are passed to the location's provider.</span></span> <span data-ttu-id="27e58-187">プロバイダーがすべての文字をサポートしていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27e58-187">The provider may not support all characters.</span></span> <span data-ttu-id="27e58-188">たとえば、アスタリスク () 文字を含むファイル名を作成することはできません `*` 。</span><span class="sxs-lookup"><span data-stu-id="27e58-188">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

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

### <span data-ttu-id="27e58-189">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="27e58-189">-UseTransaction</span></span>

<span data-ttu-id="27e58-190">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27e58-190">Includes the command in the active transaction.</span></span> <span data-ttu-id="27e58-191">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="27e58-191">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="27e58-192">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e58-192">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27e58-193">-Value</span><span class="sxs-lookup"><span data-stu-id="27e58-193">-Value</span></span>

<span data-ttu-id="27e58-194">新しい項目の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="27e58-194">Specifies the value of the new item.</span></span> <span data-ttu-id="27e58-195">パイプを使用して値をにパイプすることもでき `New-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="27e58-195">You can also pipe a value to `New-Item`.</span></span>

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

### <span data-ttu-id="27e58-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="27e58-196">-Confirm</span></span>

<span data-ttu-id="27e58-197">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27e58-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="27e58-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="27e58-198">-WhatIf</span></span>

<span data-ttu-id="27e58-199">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="27e58-199">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="27e58-200">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="27e58-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="27e58-201">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="27e58-201">CommonParameters</span></span>

<span data-ttu-id="27e58-202">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="27e58-202">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="27e58-203">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e58-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="27e58-204">入力</span><span class="sxs-lookup"><span data-stu-id="27e58-204">INPUTS</span></span>

### <span data-ttu-id="27e58-205">System.Object</span><span class="sxs-lookup"><span data-stu-id="27e58-205">System.Object</span></span>

<span data-ttu-id="27e58-206">パイプを使用して、新しい項目の値をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="27e58-206">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="27e58-207">出力</span><span class="sxs-lookup"><span data-stu-id="27e58-207">OUTPUTS</span></span>

### <span data-ttu-id="27e58-208">System.Object</span><span class="sxs-lookup"><span data-stu-id="27e58-208">System.Object</span></span>

<span data-ttu-id="27e58-209">このコマンドレットは、作成された項目を返します。</span><span class="sxs-lookup"><span data-stu-id="27e58-209">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="27e58-210">注</span><span class="sxs-lookup"><span data-stu-id="27e58-210">NOTES</span></span>

<span data-ttu-id="27e58-211">`New-Item` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="27e58-211">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="27e58-212">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="27e58-212">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="27e58-213">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e58-213">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="27e58-214">関連リンク</span><span class="sxs-lookup"><span data-stu-id="27e58-214">RELATED LINKS</span></span>

[<span data-ttu-id="27e58-215">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="27e58-215">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="27e58-216">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="27e58-216">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="27e58-217">Get-Item</span><span class="sxs-lookup"><span data-stu-id="27e58-217">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="27e58-218">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="27e58-218">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="27e58-219">Move-Item</span><span class="sxs-lookup"><span data-stu-id="27e58-219">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="27e58-220">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="27e58-220">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="27e58-221">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="27e58-221">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="27e58-222">Set-Item</span><span class="sxs-lookup"><span data-stu-id="27e58-222">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="27e58-223">about_Providers</span><span class="sxs-lookup"><span data-stu-id="27e58-223">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
