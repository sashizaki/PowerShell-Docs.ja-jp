---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215611"
---
# <span data-ttu-id="9d467-103">Add-Content</span><span class="sxs-lookup"><span data-stu-id="9d467-103">Add-Content</span></span>

## <span data-ttu-id="9d467-104">概要</span><span class="sxs-lookup"><span data-stu-id="9d467-104">SYNOPSIS</span></span>
<span data-ttu-id="9d467-105">指定した項目に内容を追加します。たとえば、ファイルに語を追加します。</span><span class="sxs-lookup"><span data-stu-id="9d467-105">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="9d467-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9d467-106">SYNTAX</span></span>

### <span data-ttu-id="9d467-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="9d467-107">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### <span data-ttu-id="9d467-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9d467-108">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## <span data-ttu-id="9d467-109">Description</span><span class="sxs-lookup"><span data-stu-id="9d467-109">DESCRIPTION</span></span>

<span data-ttu-id="9d467-110">`Add-Content`コマンドレットは、指定された項目またはファイルにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="9d467-110">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="9d467-111">内容を指定するには、コマンドに内容を入力するか、内容が格納されているオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-111">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="9d467-112">次の例でファイルまたはディレクトリを作成する必要がある場合は、「 [New-Item](New-Item.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d467-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="9d467-113">例</span><span class="sxs-lookup"><span data-stu-id="9d467-113">EXAMPLES</span></span>

### <span data-ttu-id="9d467-114">例 1: 例外が発生したすべてのテキストファイルに文字列を追加する</span><span class="sxs-lookup"><span data-stu-id="9d467-114">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="9d467-115">この例では、現在のディレクトリ内のテキストファイルに値を追加しますが、ファイル名に基づいてファイルを除外します。</span><span class="sxs-lookup"><span data-stu-id="9d467-115">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="9d467-116">この `Add-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリ内のすべての .txt ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-116">The `Add-Content` cmdlet uses the **Path** parameter to specify all .txt files in the current directory.</span></span> <span data-ttu-id="9d467-117">**Exclude** パラメーターは、指定されたパターンに一致するファイル名を無視します。</span><span class="sxs-lookup"><span data-stu-id="9d467-117">The **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="9d467-118">**値** パラメーターは、ファイルに書き込まれるテキスト文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-118">The **Value** parameter specifies the text string that is written to the files.</span></span>

<span data-ttu-id="9d467-119">これらのファイルの内容を表示するには、 [Get Content](Get-Content.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-119">Use [Get-Content](Get-Content.md) to display the contents of these files.</span></span>

### <span data-ttu-id="9d467-120">例 2: 指定したファイルの末尾に日付を追加する</span><span class="sxs-lookup"><span data-stu-id="9d467-120">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="9d467-121">この例では、現在のディレクトリのファイルに日付を追加し、その日付を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="9d467-121">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

<span data-ttu-id="9d467-122">コマンドレットでは、 `Add-Content` **Path** パラメーターと **Value** パラメーターを使用して、現在のディレクトリに2つの新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d467-122">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create two new files in the current directory.</span></span> <span data-ttu-id="9d467-123">**値** パラメーターは、 `Get-Date` 日付を取得して日付をに渡すようにコマンドレットを指定し `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-123">The **Value** parameter specifies the `Get-Date` cmdlet to get the date and passes the date to `Add-Content`.</span></span> <span data-ttu-id="9d467-124">`Add-Content`コマンドレットは、各ファイルに日付を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9d467-124">The `Add-Content` cmdlet writes the date to each file.</span></span> <span data-ttu-id="9d467-125">**PassThru** パラメーターは、date オブジェクトを表すオブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="9d467-125">The **PassThru** parameter passes an object that represents the date object.</span></span> <span data-ttu-id="9d467-126">渡されたオブジェクトを受け取るコマンドレットは他にないため、PowerShell コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-126">Because there is no other cmdlet to receive the passed object, it is displayed in the PowerShell console.</span></span> <span data-ttu-id="9d467-127">コマンドレットにより、 `Get-Content` 更新されたファイル DateTimeFile1 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-127">The `Get-Content` cmdlet displays the updated file, DateTimeFile1.log.</span></span>

### <span data-ttu-id="9d467-128">例 3: 指定したファイルの内容を別のファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="9d467-128">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="9d467-129">この例では、ファイルからコンテンツを取得し、その内容を別のファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="9d467-129">This example gets the content from a file and appends that content into another file.</span></span>

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="9d467-130">この `Add-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリ内の新しいファイル CopyToFile.txt を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-130">The `Add-Content` cmdlet uses the **Path** parameter to specify the new file in the current directory, CopyToFile.txt.</span></span> <span data-ttu-id="9d467-131">**Value** パラメーターでは、コマンドレットを使用して、 `Get-Content` CopyFromFile.txt ファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="9d467-131">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of the file, CopyFromFile.txt.</span></span> <span data-ttu-id="9d467-132">コマンドレットを囲むかっこを実行すると、コマンドが開始される `Get-Content` 前にコマンドが終了し `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-132">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="9d467-133">**値** パラメーターはに渡され `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-133">The **Value** parameter is passed to `Add-Content`.</span></span> <span data-ttu-id="9d467-134">この `Add-Content` コマンドレットは、CopyToFile.txt ファイルにデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="9d467-134">The `Add-Content` cmdlet appends the data to the CopyToFile.txt file.</span></span> <span data-ttu-id="9d467-135">コマンドレットにより、 `Get-Content` 更新されたファイル CopyToFile.txt が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-135">The `Get-Content` cmdlet displays the updated file, CopyToFile.txt.</span></span>

### <span data-ttu-id="9d467-136">例 4: 変数を使用して、指定したファイルの内容を別のファイルに追加する</span><span class="sxs-lookup"><span data-stu-id="9d467-136">Example 4: Use a variable to add the contents of a specified file to another file</span></span>

<span data-ttu-id="9d467-137">この例では、ファイルからコンテンツを取得し、その内容を変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="9d467-137">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="9d467-138">変数は、コンテンツを別のファイルに追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-138">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="9d467-139">この `Get-Content` コマンドレットは CopyFromFile.txt の内容を取得し、その内容を変数に格納し `$From` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-139">The `Get-Content` cmdlet gets the contents of CopyFromFile.txt and stores the contents in the `$From` variable.</span></span> <span data-ttu-id="9d467-140">この `Add-Content` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリ内の CopyToFile.txt ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-140">The `Add-Content` cmdlet uses the **Path** parameter to specify the CopyToFile.txt file in the current directory.</span></span> <span data-ttu-id="9d467-141">**Value** パラメーターは変数を使用し、 `$From` にコンテンツを渡し `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-141">The **Value** parameter uses the `$From` variable and passes the content to `Add-Content`.</span></span> <span data-ttu-id="9d467-142">`Add-Content`コマンドレットにより、CopyToFile.txt ファイルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-142">The `Add-Content` cmdlet updates the CopyToFile.txt file.</span></span> <span data-ttu-id="9d467-143">コマンドレットによって `Get-Content` CopyToFile.txt が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-143">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="9d467-144">例 5: 新しいファイルを作成してコンテンツをコピーする</span><span class="sxs-lookup"><span data-stu-id="9d467-144">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="9d467-145">この例では、新しいファイルを作成し、既存のファイルの内容を新しいファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d467-145">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

<span data-ttu-id="9d467-146">コマンドレットでは、 `Add-Content` **Path** パラメーターと **Value** パラメーターを使用して、現在のディレクトリに新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d467-146">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span> <span data-ttu-id="9d467-147">**Value** パラメーターでは、コマンドレットを使用して `Get-Content` 、既存のファイルの内容を取得します。 CopyFromFile.txt します。</span><span class="sxs-lookup"><span data-stu-id="9d467-147">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of an existing file, CopyFromFile.txt.</span></span> <span data-ttu-id="9d467-148">コマンドレットを囲むかっこを実行すると、コマンドが開始される `Get-Content` 前にコマンドが終了し `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-148">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="9d467-149">**Value** パラメーターは、NewFile.txt ファイルを更新するコンテンツをに渡し `Add-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-149">The **Value** parameter passes the content to `Add-Content` which updates the NewFile.txt file.</span></span> <span data-ttu-id="9d467-150">コマンドレットにより、 `Get-Content` 新しいファイルの内容 NewFile.txt が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-150">The `Get-Content` cmdlet displays the contents of the new file, NewFile.txt.</span></span>

### <span data-ttu-id="9d467-151">例 6: 読み取り専用ファイルにコンテンツを追加する</span><span class="sxs-lookup"><span data-stu-id="9d467-151">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="9d467-152">このコマンドは、 **IsReadOnly** file 属性が True に設定されている場合でも、ファイルに値を追加します。</span><span class="sxs-lookup"><span data-stu-id="9d467-152">This command adds the value to the file even if the **IsReadOnly** file attribute is set to True.</span></span>
<span data-ttu-id="9d467-153">この例には、読み取り専用ファイルを作成する手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d467-153">The steps to create a read-only file are included in the example.</span></span>

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

<span data-ttu-id="9d467-154">この `New-Item` コマンドレットは、 **Path** パラメーターと **ItemType** パラメーターを使用して、現在のディレクトリに IsReadOnlyTextFile.txt ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d467-154">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file IsReadOnlyTextFile.txt in the current directory.</span></span> <span data-ttu-id="9d467-155">コマンドレットでは、 `Set-ItemProperty` **Name** パラメーターと **Value** パラメーターを使用して、ファイルの **IsReadOnly** プロパティを True に変更します。</span><span class="sxs-lookup"><span data-stu-id="9d467-155">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span> <span data-ttu-id="9d467-156">この `Get-ChildItem` コマンドレットは、ファイルが空 (0) であり、読み取り専用属性 () を持っていることを示してい `r` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-156">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span> <span data-ttu-id="9d467-157">コマンドレットでは、 `Add-Content` **Path** パラメーターを使用してファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-157">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="9d467-158">**Value** パラメーターには、ファイルに追加するテキスト文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d467-158">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="9d467-159">**Force** パラメーターは、テキストを読み取り専用ファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9d467-159">The **Force** parameter writes the text to the read-only file.</span></span> <span data-ttu-id="9d467-160">この `Get-Content` コマンドレットは、 **Path** パラメーターを使用してファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="9d467-160">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="9d467-161">読み取り専用属性を削除するには、 `Set-ItemProperty` **値** パラメーターをに設定してコマンドを使用し `False` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-161">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

## <span data-ttu-id="9d467-162">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9d467-162">PARAMETERS</span></span>

### <span data-ttu-id="9d467-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9d467-163">-Confirm</span></span>

<span data-ttu-id="9d467-164">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9d467-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="9d467-165">-Credential</span></span>

<span data-ttu-id="9d467-166">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="9d467-167">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="9d467-167">The default is the current user.</span></span>

<span data-ttu-id="9d467-168">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-168">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="9d467-169">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-169">If you type a user name, you will be prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="9d467-170">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9d467-170">This parameter is not supported by any providers installed with PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d467-171">-Encoding</span><span class="sxs-lookup"><span data-stu-id="9d467-171">-Encoding</span></span>

<span data-ttu-id="9d467-172">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-172">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="9d467-173">既定値は `Default` です。</span><span class="sxs-lookup"><span data-stu-id="9d467-173">The default value is `Default`.</span></span>

<span data-ttu-id="9d467-174">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9d467-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="9d467-175">`Ascii` ASCII (7 ビット) 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-175">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="9d467-176">`BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-176">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="9d467-177">`BigEndianUTF32` は、ビッグエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-177">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="9d467-178">`Byte` 文字のセットをバイトシーケンスにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="9d467-178">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="9d467-179">`Default` は、システムのアクティブなコードページ (通常は ANSI) に対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-179">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="9d467-180">`Oem` は、システムの現在の OEM コードページに対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-180">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="9d467-181">`String`**Unicode** と同じです。</span><span class="sxs-lookup"><span data-stu-id="9d467-181">`String` Same as **Unicode** .</span></span>
- <span data-ttu-id="9d467-182">`Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-182">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="9d467-183">`Unknown`**Unicode** と同じです。</span><span class="sxs-lookup"><span data-stu-id="9d467-183">`Unknown` Same as **Unicode** .</span></span>
- <span data-ttu-id="9d467-184">`UTF7` UTF-7 を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-184">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="9d467-185">`UTF8` UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-185">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="9d467-186">`UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-186">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="9d467-187">Encoding は、FileSystem プロバイダーによってコマンドレットに追加される動的パラメーターです `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="9d467-187">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="9d467-188">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9d467-188">This parameter works only in file system drives.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d467-189">-除外</span><span class="sxs-lookup"><span data-stu-id="9d467-189">-Exclude</span></span>

<span data-ttu-id="9d467-190">指定した項目を除外します。</span><span class="sxs-lookup"><span data-stu-id="9d467-190">Omits the specified items.</span></span> <span data-ttu-id="9d467-191">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9d467-191">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9d467-192">パス要素またはパターン ( **\* .txt** など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d467-192">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="9d467-193">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d467-193">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="9d467-194">-Filter</span><span class="sxs-lookup"><span data-stu-id="9d467-194">-Filter</span></span>

<span data-ttu-id="9d467-195">プロバイダーの形式や言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-195">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="9d467-196">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9d467-196">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9d467-197">ワイルドカードを使用できるかどうかなど、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9d467-197">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="9d467-198">**フィルター** は他のパラメーターよりも効率的です。これは、プロバイダーがオブジェクトの取得時にフィルターを適用するためです。</span><span class="sxs-lookup"><span data-stu-id="9d467-198">**Filters** are more efficient than other parameters because the provider applies filters when objects are retrieved.</span></span> <span data-ttu-id="9d467-199">それ以外の場合、PowerShell はオブジェクトの取得後にフィルター処理を行います。</span><span class="sxs-lookup"><span data-stu-id="9d467-199">Otherwise, PowerShell processes filters after the objects are retrieved.</span></span>

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

### <span data-ttu-id="9d467-200">-Force</span><span class="sxs-lookup"><span data-stu-id="9d467-200">-Force</span></span>

<span data-ttu-id="9d467-201">読み取り専用属性をオーバーライドし、読み取り専用ファイルに内容を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9d467-201">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="9d467-202">たとえば、 **Force** を指定すると、読み取り専用属性がオーバーライドされるか、ファイル パスを完成させるためにディレクトリが作成されますが、ファイルのアクセス許可は変更されません。</span><span class="sxs-lookup"><span data-stu-id="9d467-202">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="9d467-203">-Include</span><span class="sxs-lookup"><span data-stu-id="9d467-203">-Include</span></span>

<span data-ttu-id="9d467-204">指定した項目だけを追加します。</span><span class="sxs-lookup"><span data-stu-id="9d467-204">Adds only the specified items.</span></span> <span data-ttu-id="9d467-205">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9d467-205">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9d467-206">パス要素またはパターン ( **\* .txt** など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d467-206">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="9d467-207">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d467-207">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="9d467-208">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9d467-208">-LiteralPath</span></span>

<span data-ttu-id="9d467-209">内容を追加する項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-209">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="9d467-210">**Path** とは異なり、 **LiteralPath** の値は入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-210">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9d467-211">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="9d467-211">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9d467-212">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9d467-212">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9d467-213">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="9d467-213">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d467-214">-なし Wline</span><span class="sxs-lookup"><span data-stu-id="9d467-214">-NoNewline</span></span>

<span data-ttu-id="9d467-215">このコマンドレットがコンテンツに新しい行または復帰を追加しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="9d467-215">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="9d467-216">入力オブジェクトの文字列形式が連結され、出力が形成されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-216">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="9d467-217">出力文字列間にスペースや改行は挿入されません。</span><span class="sxs-lookup"><span data-stu-id="9d467-217">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="9d467-218">最後の出力文字列の後に改行は追加されません。</span><span class="sxs-lookup"><span data-stu-id="9d467-218">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="9d467-219">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9d467-219">-PassThru</span></span>

<span data-ttu-id="9d467-220">追加された内容を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9d467-220">Returns an object representing the added content.</span></span> <span data-ttu-id="9d467-221">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="9d467-221">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="9d467-222">-Path</span><span class="sxs-lookup"><span data-stu-id="9d467-222">-Path</span></span>

<span data-ttu-id="9d467-223">内容を追加する項目へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-223">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="9d467-224">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d467-224">Wildcards are permitted.</span></span> <span data-ttu-id="9d467-225">複数のパスを指定する場合は、各パスをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="9d467-225">If you specify multiple paths, use commas to separate the paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="9d467-226">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="9d467-226">-Stream</span></span>

<span data-ttu-id="9d467-227">コンテンツの代替データストリームを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-227">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="9d467-228">ストリームが存在しない場合は、このコマンドレットによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-228">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="9d467-229">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9d467-229">Wildcard characters are not supported.</span></span>

<span data-ttu-id="9d467-230">**Stream** は、FileSystem プロバイダーによってに追加される動的パラメーターです `Add-Content` 。</span><span class="sxs-lookup"><span data-stu-id="9d467-230">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="9d467-231">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9d467-231">This parameter works only in file system drives.</span></span>

<span data-ttu-id="9d467-232">コマンドレットを使用して、 `Add-Content` ゾーンの内容を変更でき **ます。識別子** 代替データストリーム。</span><span class="sxs-lookup"><span data-stu-id="9d467-232">You can use the `Add-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="9d467-233">ただし、インターネットからダウンロードされたファイルをブロックするセキュリティチェックを省略する方法としては、この方法をお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="9d467-233">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="9d467-234">ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-234">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="9d467-235">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9d467-235">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d467-236">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="9d467-236">-UseTransaction</span></span>

<span data-ttu-id="9d467-237">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d467-237">Includes the command in the active transaction.</span></span> <span data-ttu-id="9d467-238">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9d467-238">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="9d467-239">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d467-239">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="9d467-240">-Value</span><span class="sxs-lookup"><span data-stu-id="9d467-240">-Value</span></span>

<span data-ttu-id="9d467-241">追加する内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d467-241">Specifies the content to be added.</span></span> <span data-ttu-id="9d467-242">**このデータが内部でのみ使用さ** れるなどの引用符で囲まれた文字列を入力するか、生成する **DateTime** オブジェクトなど、コンテンツを含むオブジェクトを指定し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-242">Type a quoted string, such as **This data is for internal use only** , or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="9d467-243">パスは文字列であるため、パスを入力してファイルの内容を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9d467-243">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="9d467-244">コマンドを使用して `Get-Content` コンテンツを取得し、それを **Value** パラメーターに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="9d467-244">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9d467-245">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9d467-245">-WhatIf</span></span>

<span data-ttu-id="9d467-246">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="9d467-246">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9d467-247">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9d467-247">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9d467-248">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d467-248">CommonParameters</span></span>

<span data-ttu-id="9d467-249">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-249">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="9d467-250">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d467-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9d467-251">入力</span><span class="sxs-lookup"><span data-stu-id="9d467-251">INPUTS</span></span>

### <span data-ttu-id="9d467-252">System.object、システムの管理、PSCredential</span><span class="sxs-lookup"><span data-stu-id="9d467-252">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="9d467-253">パイプを使用して、値、パス、または資格情報をにパイプすることができ `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-253">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="9d467-254">出力</span><span class="sxs-lookup"><span data-stu-id="9d467-254">OUTPUTS</span></span>

### <span data-ttu-id="9d467-255">None または System.String</span><span class="sxs-lookup"><span data-stu-id="9d467-255">None or System.String</span></span>

<span data-ttu-id="9d467-256">**PassThru** パラメーターを使用すると、によって、 `Add-Content` コンテンツを表す **system.string** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-256">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="9d467-257">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="9d467-257">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9d467-258">注</span><span class="sxs-lookup"><span data-stu-id="9d467-258">NOTES</span></span>

<span data-ttu-id="9d467-259">オブジェクトをにパイプすると `Add-Content` 、オブジェクトは項目に追加される前に文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="9d467-259">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="9d467-260">オブジェクト型によって文字列の形式が決まりますが、オブジェクトの既定の表示形式と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d467-260">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="9d467-261">文字列の形式を制御するには、送信コマンドレットの書式設定パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d467-261">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>

<span data-ttu-id="9d467-262">また、組み込みエイリアスであるを参照することもでき `Add-Content` `ac` ます。</span><span class="sxs-lookup"><span data-stu-id="9d467-262">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="9d467-263">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d467-263">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="9d467-264">`Add-Content`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="9d467-264">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9d467-265">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="9d467-265">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="9d467-266">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d467-266">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="9d467-267">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9d467-267">RELATED LINKS</span></span>

[<span data-ttu-id="9d467-268">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="9d467-268">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="9d467-269">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9d467-269">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="9d467-270">about_Transactions</span><span class="sxs-lookup"><span data-stu-id="9d467-270">about_Transactions</span></span>](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[<span data-ttu-id="9d467-271">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="9d467-271">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="9d467-272">Get-Content</span><span class="sxs-lookup"><span data-stu-id="9d467-272">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="9d467-273">Get-Item</span><span class="sxs-lookup"><span data-stu-id="9d467-273">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="9d467-274">New-Item</span><span class="sxs-lookup"><span data-stu-id="9d467-274">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="9d467-275">Set-Content</span><span class="sxs-lookup"><span data-stu-id="9d467-275">Set-Content</span></span>](Set-Content.md)
