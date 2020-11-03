---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/07/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Item
ms.openlocfilehash: 3d33f0e3ab859d839b22a49a88860624ae06ddf2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211552"
---
# <span data-ttu-id="4f76f-103">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="4f76f-103">Remove-Item</span></span>

## <span data-ttu-id="4f76f-104">概要</span><span class="sxs-lookup"><span data-stu-id="4f76f-104">SYNOPSIS</span></span>
<span data-ttu-id="4f76f-105">指定した項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-105">Deletes the specified items.</span></span>

## <span data-ttu-id="4f76f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4f76f-106">SYNTAX</span></span>

### <span data-ttu-id="4f76f-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="4f76f-107">Path (Default)</span></span>

```
Remove-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="4f76f-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4f76f-108">LiteralPath</span></span>

```
Remove-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="4f76f-109">Description</span><span class="sxs-lookup"><span data-stu-id="4f76f-109">DESCRIPTION</span></span>

<span data-ttu-id="4f76f-110">`Remove-Item`コマンドレットでは、1つ以上の項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-110">The `Remove-Item` cmdlet deletes one or more items.</span></span> <span data-ttu-id="4f76f-111">多くのプロバイダーでサポートされているため、ファイル、フォルダー、レジストリキー、変数、エイリアス、関数など、さまざまな種類の項目を削除できます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-111">Because it is supported by many providers, it can delete many different types of items, including files, folders, registry keys, variables, aliases, and functions.</span></span>

## <span data-ttu-id="4f76f-112">例</span><span class="sxs-lookup"><span data-stu-id="4f76f-112">EXAMPLES</span></span>

### <span data-ttu-id="4f76f-113">例 1: 任意のファイル名拡張子を持つファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="4f76f-113">Example 1: Delete files that have any file name extension</span></span>

<span data-ttu-id="4f76f-114">この例では、フォルダーからドット () を含む名前を持つすべてのファイルを削除し `.` `C:\Test` ます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-114">This example deletes all of the files that have names that include a dot (`.`) from the `C:\Test` folder.</span></span> <span data-ttu-id="4f76f-115">コマンドではドットを指定するため、ファイル名拡張子のないフォルダーやファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-115">Because the command specifies a dot, the command does not delete folders or files that have no file name extension.</span></span>

```powershell
Remove-Item C:\Test\*.*
```

### <span data-ttu-id="4f76f-116">例 2: フォルダー内のドキュメントファイルの一部を削除する</span><span class="sxs-lookup"><span data-stu-id="4f76f-116">Example 2: Delete some of the document files in a folder</span></span>

<span data-ttu-id="4f76f-117">次の例では、現在のフォルダーから、 `.doc` ファイル名拡張子とが含まれていない名前を持つすべてのファイルを削除し `*1*` ます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-117">This example deletes from the current folder all files that have a `.doc` file name extension and a name that does not include `*1*`.</span></span>

```powershell
Remove-Item * -Include *.doc -Exclude *1*
```

<span data-ttu-id="4f76f-118">ワイルドカード文字 () を使用して、 `*` 現在のフォルダーの内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-118">It uses the wildcard character (`*`) to specify the contents of the current folder.</span></span> <span data-ttu-id="4f76f-119">この例では、 **Include** パラメーターと **Exclude** パラメーターを使用して、削除するファイルを指定しています。</span><span class="sxs-lookup"><span data-stu-id="4f76f-119">It uses the **Include** and **Exclude** parameters to specify the files to delete.</span></span>

### <span data-ttu-id="4f76f-120">例 3: 非表示の読み取り専用ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="4f76f-120">Example 3: Delete hidden, read-only files</span></span>

<span data-ttu-id="4f76f-121">このコマンドは、 *非表示* のファイルと *読み取り* 専用ファイルの両方を削除します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-121">This command deletes a file that is both *hidden* and *read-only* .</span></span>

```powershell
Remove-Item -Path C:\Test\hidden-RO-file.txt -Force
```

<span data-ttu-id="4f76f-122">**Path** パラメーターを使用してファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-122">It uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="4f76f-123">**Force** パラメーターを使用して削除します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-123">It uses the **Force** parameter to delete it.</span></span> <span data-ttu-id="4f76f-124">**Force** を使用しない場合、 _読み取り_ 専用または _非表示_ のファイルは削除できません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-124">Without **Force** , you cannot delete _read-only_ or _hidden_ files.</span></span>

### <span data-ttu-id="4f76f-125">例 4: サブフォルダー内のファイルを再帰的に削除する</span><span class="sxs-lookup"><span data-stu-id="4f76f-125">Example 4: Delete files in subfolders recursively</span></span>

<span data-ttu-id="4f76f-126">このコマンドは、現在のフォルダーとすべてのサブフォルダー内のすべての CSV ファイルを再帰的に削除します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-126">This command deletes all of the CSV files in the current folder and all subfolders recursively.</span></span>

<span data-ttu-id="4f76f-127">の **再帰** パラメーターには `Remove-Item` 既知の問題があるため、この例のコマンドはを使用して `Get-ChildItem` 目的のファイルを取得し、パイプライン演算子を使用してに渡し `Remove-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-127">Because the **Recurse** parameter in `Remove-Item` has a known issue, the command in this example uses `Get-ChildItem` to get the desired files, and then uses the pipeline operator to pass them to `Remove-Item`.</span></span>

```powershell
Get-ChildItem * -Include *.csv -Recurse | Remove-Item
```

<span data-ttu-id="4f76f-128">コマンドで `Get-ChildItem` は、 **Path** の値が () になっています。この値は、 `*` 現在のフォルダーの内容を表します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-128">In the `Get-ChildItem` command, **Path** has a value of (`*`), which represents the contents of the current folder.</span></span> <span data-ttu-id="4f76f-129">**Include** を使用して CSV ファイルの種類を指定し、 **再帰を使用** して、再帰的な取得を行います。</span><span class="sxs-lookup"><span data-stu-id="4f76f-129">It uses **Include** to specify the CSV file type, and it uses **Recurse** to make the retrieval recursive.</span></span> <span data-ttu-id="4f76f-130">ファイルの種類としてパス (など) を指定しようとする `-Path *.csv` と、コマンドレットは検索の対象を子項目を持たないファイルと解釈し、 **再帰** は失敗します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-130">If you try to specify the file type the path, such as `-Path *.csv`, the cmdlet interprets the subject of the search to be a file that has no child items, and **Recurse** fails.</span></span>

### <span data-ttu-id="4f76f-131">例 5: サブキーを再帰的に削除する</span><span class="sxs-lookup"><span data-stu-id="4f76f-131">Example 5: Delete subkeys recursively</span></span>

<span data-ttu-id="4f76f-132">このコマンドは、"OldApp" レジストリキーとそのすべてのサブキーと値を削除します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-132">This command deletes the "OldApp" registry key and all its subkeys and values.</span></span> <span data-ttu-id="4f76f-133">キーを `Remove-Item` 削除するためにを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-133">It uses `Remove-Item` to remove the key.</span></span> <span data-ttu-id="4f76f-134">パスが指定されていますが、省略可能なパラメーター名 ( **path** ) は省略されています。</span><span class="sxs-lookup"><span data-stu-id="4f76f-134">The path is specified, but the optional parameter name ( **Path** ) is omitted.</span></span>

<span data-ttu-id="4f76f-135">**再帰** パラメーターは、"oldapp" キーのすべての内容を再帰的に削除します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-135">The **Recurse** parameter deletes all of the contents of the "OldApp" key recursively.</span></span> <span data-ttu-id="4f76f-136">キーにサブキーが含まれていて、 **再帰** パラメーターを省略した場合、キーの内容を削除するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-136">If the key contains subkeys and you omit the **Recurse** parameter, you are prompted to confirm that you want to delete the contents of the key.</span></span>

```powershell
Remove-Item HKLM:\Software\MyCompany\OldApp -Recurse
```

### <span data-ttu-id="4f76f-137">例 6: 特殊文字を使用したファイルの削除</span><span class="sxs-lookup"><span data-stu-id="4f76f-137">Example 6: Deleting files with special characters</span></span>

<span data-ttu-id="4f76f-138">次の例では、角かっこやかっこなどの特殊文字を含むファイルを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-138">The following example shows how to delete files that contain special characters like brackets or parentheses.</span></span>

```powershell
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*'
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*' | ForEach-Object { Remove-Item -LiteralPath $_.Name }
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
```

### <span data-ttu-id="4f76f-139">例 7: 代替データストリームを削除する</span><span class="sxs-lookup"><span data-stu-id="4f76f-139">Example 7: Remove an alternate data stream</span></span>

<span data-ttu-id="4f76f-140">この例は、コマンドレットの **Stream** 動的パラメーターを使用して、代替データストリームを削除する方法を示して `Remove-Item` います。</span><span class="sxs-lookup"><span data-stu-id="4f76f-140">This example shows how to use the **Stream** dynamic parameter of the `Remove-Item` cmdlet to delete an alternate data stream.</span></span> <span data-ttu-id="4f76f-141">Stream パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4f76f-141">The stream parameter is introduced in Windows PowerShell 3.0.</span></span>

```powershell
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
   FileName: \\C:\Test\Copy-Script.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

```

```powershell
Remove-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
Get-Item : Could not open alternate data stream 'Zone.Identifier' of file 'C:\Test\Copy-Script.ps1'.
At line:1 char:1
+ Get-Item 'C:\Test\Copy-Script.ps1' -Stream Zone.Identifier
+ [!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()]~~
    + CategoryInfo          : ObjectNotFound: (C:\Test\Copy-Script.ps1:String) [Get-Item], FileNotFoundE
   xception
    + FullyQualifiedErrorId : AlternateDataStreamNotFound,Microsoft.PowerShell.Commands.GetItemCommand

```

<span data-ttu-id="4f76f-142">**Stream** パラメーターは、 `Get-Item` ファイルの **ゾーン識別子** ストリームを取得します。 `Copy-Script.ps1`</span><span class="sxs-lookup"><span data-stu-id="4f76f-142">The **Stream** parameter `Get-Item` gets the **Zone.Identifier** stream of the `Copy-Script.ps1` file.</span></span> <span data-ttu-id="4f76f-143">`Remove-Item`**Stream** パラメーターを使用して、ファイルの **ゾーン識別子** ストリームを削除します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-143">`Remove-Item` uses the **Stream** parameter to remove the **Zone.Identifier** stream of the file.</span></span> <span data-ttu-id="4f76f-144">最後に、 `Get-Item` コマンドレットは、 **ゾーン識別子** のストリームが削除されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-144">Finally, the `Get-Item` cmdlet shows that the **Zone.Identifier** stream was deleted.</span></span>

## <span data-ttu-id="4f76f-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4f76f-145">PARAMETERS</span></span>

### <span data-ttu-id="4f76f-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="4f76f-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="4f76f-147">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="4f76f-148">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="4f76f-149">-除外</span><span class="sxs-lookup"><span data-stu-id="4f76f-149">-Exclude</span></span>

<span data-ttu-id="4f76f-150">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-150">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="4f76f-151">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-151">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="4f76f-152">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-152">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="4f76f-153">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-153">Wildcard characters are permitted.</span></span> <span data-ttu-id="4f76f-154">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-154">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="4f76f-155">-Filter</span><span class="sxs-lookup"><span data-stu-id="4f76f-155">-Filter</span></span>

<span data-ttu-id="4f76f-156">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-156">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="4f76f-157">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="4f76f-157">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="4f76f-158">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f76f-158">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="4f76f-159">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="4f76f-159">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="4f76f-160">-Force</span><span class="sxs-lookup"><span data-stu-id="4f76f-160">-Force</span></span>

<span data-ttu-id="4f76f-161">非表示または読み取り専用のファイルや読み取り専用のエイリアスまたは変数など、変更できない項目をコマンドレットで強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-161">Forces the cmdlet to remove items that cannot otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="4f76f-162">コマンドレットでは、定数のエイリアスまたは変数は削除できません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-162">The cmdlet cannot remove constant aliases or variables.</span></span>
<span data-ttu-id="4f76f-163">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="4f76f-163">Implementation varies from provider to provider.</span></span> <span data-ttu-id="4f76f-164">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f76f-164">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="4f76f-165">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-165">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="4f76f-166">-Include</span><span class="sxs-lookup"><span data-stu-id="4f76f-166">-Include</span></span>

<span data-ttu-id="4f76f-167">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-167">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="4f76f-168">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-168">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="4f76f-169">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-169">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="4f76f-170">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-170">Wildcard characters are permitted.</span></span> <span data-ttu-id="4f76f-171">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-171">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="4f76f-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4f76f-172">-LiteralPath</span></span>

<span data-ttu-id="4f76f-173">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-173">Specifies a path to one or more locations.</span></span> <span data-ttu-id="4f76f-174">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-174">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="4f76f-175">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-175">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="4f76f-176">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-176">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="4f76f-177">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="4f76f-178">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f76f-178">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="4f76f-179">-Path</span><span class="sxs-lookup"><span data-stu-id="4f76f-179">-Path</span></span>

<span data-ttu-id="4f76f-180">削除する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-180">Specifies a path of the items being removed.</span></span>
<span data-ttu-id="4f76f-181">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-181">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="4f76f-182">-再帰</span><span class="sxs-lookup"><span data-stu-id="4f76f-182">-Recurse</span></span>

<span data-ttu-id="4f76f-183">このコマンドレットが、指定された場所の項目と、その場所のすべての子項目を削除することを示します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-183">Indicates that this cmdlet deletes the items in the specified locations and in all child items of the locations.</span></span>

<span data-ttu-id="4f76f-184">**Include** パラメーターと共に使用した場合、すべてのサブフォルダーまたはすべての子項目が **再帰** パラメーターによって削除されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f76f-184">When it is used with the **Include** parameter, the **Recurse** parameter might not delete all subfolders or all child items.</span></span> <span data-ttu-id="4f76f-185">これは既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="4f76f-185">This is a known issue.</span></span> <span data-ttu-id="4f76f-186">回避策として、 `Get-ChildItem -Recurse` `Remove-Item` このトピックの「例4」で説明されているように、コマンドの結果をにパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-186">As a workaround, try piping results of the `Get-ChildItem -Recurse` command to `Remove-Item`, as described in "Example 4" in this topic.</span></span>

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

### <span data-ttu-id="4f76f-187">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="4f76f-187">-Stream</span></span>

<span data-ttu-id="4f76f-188">**ストリーム** パラメーターは、FileSystem プロバイダーによってに追加される動的パラメーターです `Remove-Item` 。</span><span class="sxs-lookup"><span data-stu-id="4f76f-188">The **Stream** parameter is a dynamic parameter that the FileSystem provider adds to `Remove-Item`.</span></span>
<span data-ttu-id="4f76f-189">このパラメーターはファイル システム ドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-189">This parameter works only in file system drives.</span></span>

<span data-ttu-id="4f76f-190">を使用すると `Remove-Item` 、代替データストリームを削除できます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-190">You can use `Remove-Item` to delete an alternative data stream.</span></span> <span data-ttu-id="4f76f-191">ただし、インターネットからダウンロードされるファイルをブロックするセキュリティ チェックをなくす方法としては推奨されません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-191">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="4f76f-192">ダウンロードしたファイルが安全であることを確認した場合は、コマンドレットを使用し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-192">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="4f76f-193">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4f76f-193">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4f76f-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4f76f-194">-Confirm</span></span>

<span data-ttu-id="4f76f-195">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-195">Prompts you for confirmation before running the cmdlet.</span></span> <span data-ttu-id="4f76f-196">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f76f-196">For more information, see the following articles:</span></span>

- [<span data-ttu-id="4f76f-197">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="4f76f-197">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)
- [<span data-ttu-id="4f76f-198">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="4f76f-198">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

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

### <span data-ttu-id="4f76f-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4f76f-199">-WhatIf</span></span>

<span data-ttu-id="4f76f-200">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4f76f-201">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-201">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4f76f-202">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f76f-202">CommonParameters</span></span>

<span data-ttu-id="4f76f-203">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-203">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="4f76f-204">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f76f-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4f76f-205">入力</span><span class="sxs-lookup"><span data-stu-id="4f76f-205">INPUTS</span></span>

### <span data-ttu-id="4f76f-206">System.String</span><span class="sxs-lookup"><span data-stu-id="4f76f-206">System.String</span></span>

<span data-ttu-id="4f76f-207">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-207">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="4f76f-208">出力</span><span class="sxs-lookup"><span data-stu-id="4f76f-208">OUTPUTS</span></span>

### <span data-ttu-id="4f76f-209">なし</span><span class="sxs-lookup"><span data-stu-id="4f76f-209">None</span></span>

<span data-ttu-id="4f76f-210">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-210">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="4f76f-211">注</span><span class="sxs-lookup"><span data-stu-id="4f76f-211">NOTES</span></span>

<span data-ttu-id="4f76f-212">`Remove-Item`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="4f76f-212">The `Remove-Item` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="4f76f-213">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="4f76f-213">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="4f76f-214">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f76f-214">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="4f76f-215">**再帰** パラメーターを使用せずに項目が含まれているフォルダーを削除しようとすると、コマンドレットによって確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f76f-215">When you try to delete a folder that contains items without using the **Recurse** parameter, the cmdlet prompts for confirmation.</span></span> <span data-ttu-id="4f76f-216">を使用する `-Confirm:$false` と、プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4f76f-216">Using `-Confirm:$false` does not suppress the prompt.</span></span> <span data-ttu-id="4f76f-217">これは仕様です。</span><span class="sxs-lookup"><span data-stu-id="4f76f-217">This is by design.</span></span>

## <span data-ttu-id="4f76f-218">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4f76f-218">RELATED LINKS</span></span>

[<span data-ttu-id="4f76f-219">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="4f76f-219">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="4f76f-220">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="4f76f-220">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="4f76f-221">Get-Item</span><span class="sxs-lookup"><span data-stu-id="4f76f-221">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="4f76f-222">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="4f76f-222">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="4f76f-223">Move-Item</span><span class="sxs-lookup"><span data-stu-id="4f76f-223">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="4f76f-224">New-Item</span><span class="sxs-lookup"><span data-stu-id="4f76f-224">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="4f76f-225">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4f76f-225">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="4f76f-226">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="4f76f-226">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="4f76f-227">Set-Item</span><span class="sxs-lookup"><span data-stu-id="4f76f-227">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="4f76f-228">about_Providers</span><span class="sxs-lookup"><span data-stu-id="4f76f-228">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="4f76f-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="4f76f-229">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)

[<span data-ttu-id="4f76f-230">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="4f76f-230">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

