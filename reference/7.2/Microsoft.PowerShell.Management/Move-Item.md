---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: a47c017371fe5fe87618c11551cd1ecba76d5c60
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603047"
---
# <span data-ttu-id="c05c9-102">Move-Item</span><span class="sxs-lookup"><span data-stu-id="c05c9-102">Move-Item</span></span>

## <span data-ttu-id="c05c9-103">概要</span><span class="sxs-lookup"><span data-stu-id="c05c9-103">SYNOPSIS</span></span>
<span data-ttu-id="c05c9-104">項目をある場所から別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-104">Moves an item from one location to another.</span></span>

## <span data-ttu-id="c05c9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c05c9-105">SYNTAX</span></span>

### <span data-ttu-id="c05c9-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="c05c9-106">Path (Default)</span></span>

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c05c9-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c05c9-107">LiteralPath</span></span>

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c05c9-108">Description</span><span class="sxs-lookup"><span data-stu-id="c05c9-108">DESCRIPTION</span></span>

<span data-ttu-id="c05c9-109">`Move-Item`コマンドレットは、プロパティ、内容、子項目などの項目を、ある場所から別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-109">The `Move-Item` cmdlet moves an item, including its properties, contents, and child items, from one location to another location.</span></span> <span data-ttu-id="c05c9-110">移動元と移動先は、どちらも同じプロバイダーでサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c05c9-110">The locations must be supported by the same provider.</span></span>
<span data-ttu-id="c05c9-111">たとえば、ファイルやサブディレクトリを別のディレクトリに移動したり、レジストリのサブキーを別のキーに移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-111">For example, it can move a file or subdirectory from one directory to another or move a registry subkey from one key to another.</span></span>
<span data-ttu-id="c05c9-112">移動した項目は新しい場所に追加され、元の場所から削除されます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-112">When you move an item, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="c05c9-113">例</span><span class="sxs-lookup"><span data-stu-id="c05c9-113">EXAMPLES</span></span>

### <span data-ttu-id="c05c9-114">例 1: ファイルを別のディレクトリに移動して名前を変更する</span><span class="sxs-lookup"><span data-stu-id="c05c9-114">Example 1: Move a file to another directory and rename it</span></span>

<span data-ttu-id="c05c9-115">このコマンドは、 `Test.txt` ドライブからディレクトリにファイルを移動 `C:` `E:\Temp` し、からに名前を変更し `test.txt` `tst.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-115">This command moves the `Test.txt` file from the `C:` drive to the `E:\Temp` directory and renames it from `test.txt` to `tst.txt`.</span></span>

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### <span data-ttu-id="c05c9-116">例 2: ディレクトリとその内容を別のディレクトリに移動する</span><span class="sxs-lookup"><span data-stu-id="c05c9-116">Example 2: Move a directory and its contents to another directory</span></span>

<span data-ttu-id="c05c9-117">このコマンドは、ディレクトリ `C:\Temp` とその内容をディレクトリに移動し `C:\Logs` ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-117">This command moves the `C:\Temp` directory and its contents to the `C:\Logs` directory.</span></span>
<span data-ttu-id="c05c9-118">"Temp" ディレクトリとそのすべてのサブディレクトリとファイルが "Logs" ディレクトリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-118">The "Temp" directory, and all of its subdirectories and files, then appear in the "Logs" directory.</span></span>

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### <span data-ttu-id="c05c9-119">例 3: 指定した拡張子のすべてのファイルを現在のディレクトリから別のディレクトリに移動する</span><span class="sxs-lookup"><span data-stu-id="c05c9-119">Example 3: Move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="c05c9-120">このコマンドは、 `*.txt` (ドット () で表される) 現在のディレクトリ内のすべてのテキストファイル () `.` をディレクトリに移動し `C:\Logs` ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-120">This command moves all of the text files (`*.txt`) in the current directory (represented by a dot (`.`)) to the `C:\Logs` directory.</span></span>

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### <span data-ttu-id="c05c9-121">例 4: 指定した拡張子のすべてのファイルを現在のディレクトリから別のディレクトリに再帰的に移動する</span><span class="sxs-lookup"><span data-stu-id="c05c9-121">Example 4: Recursively move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="c05c9-122">このコマンドは、すべてのテキストファイルを現在のディレクトリとすべてのサブディレクトリから再帰的に "C:\ textfiles" ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-122">This command moves all of the text files from the current directory and all subdirectories, recursively, to the "C:\TextFiles" directory.</span></span>

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

<span data-ttu-id="c05c9-123">このコマンドは、コマンドレットを使用して、 `Get-ChildItem` (ドットで表される) 現在のディレクトリ内のすべての子項目 \[ \] と、"*.txt" というファイル名拡張子を持つサブディレクトリを取得します。Recursive パラメーターを使用して、検索を再帰的にし、Include パラメーターを使用* して取得を ".txt" ファイルに制限します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-123">The command uses the `Get-ChildItem` cmdlet to get all of the child items in the current directory (represented by the dot \[.\]) and its subdirectories that have a "*.txt" file name extension. It uses the **Recurse** parameter to make the retrieval recursive and the Include parameter to limit the retrieval to "*.txt" files.</span></span>

<span data-ttu-id="c05c9-124">パイプライン演算子 () は、 `|` このコマンドの結果をに送信します。これにより `Move-Item` 、テキストファイルが "textfiles" ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-124">The pipeline operator (`|`) sends the results of this command to `Move-Item`, which moves the text files to the "TextFiles" directory.</span></span>

<span data-ttu-id="c05c9-125">"C:\ textfiles" に移動されるファイルの名前が同じである場合、は `Move-Item` エラーを表示して続行しますが、名前が "C:\ textfiles" になるファイルを1つだけ移動します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-125">If files that are to be moved to "C:\Textfiles" have the same name, `Move-Item` displays an error and continues, but it moves only one file with each name to "C:\Textfiles".</span></span>
<span data-ttu-id="c05c9-126">その他のファイルは元のディレクトリに残ります。</span><span class="sxs-lookup"><span data-stu-id="c05c9-126">The other files remain in their original directories.</span></span>

<span data-ttu-id="c05c9-127">"Textfiles" ディレクトリ (または移動先のパスの他の要素) が存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-127">If the "Textfiles" directory (or any other element of the destination path) does not exist, the command fails.</span></span>
<span data-ttu-id="c05c9-128">**Force** パラメーターを使用した場合でも、不足しているディレクトリは作成されません。</span><span class="sxs-lookup"><span data-stu-id="c05c9-128">The missing directory is not created for you, even if you use the **Force** parameter.</span></span>
<span data-ttu-id="c05c9-129">`Move-Item` 最初の項目を "Textfiles" という名前のファイルに移動し、そのファイルが既に存在することを示すエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-129">`Move-Item` moves the first item to a file called "Textfiles" and then displays an error explaining that the file already exists.</span></span>

<span data-ttu-id="c05c9-130">また、既定で `Get-ChildItem` は、は隠しファイルを移動しません。</span><span class="sxs-lookup"><span data-stu-id="c05c9-130">Also, by default, `Get-ChildItem` does not move hidden files.</span></span>
<span data-ttu-id="c05c9-131">隠しファイルを移動するには、 **Force** パラメーターをと共に使用し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-131">To move hidden files, use the **Force** parameter with `Get-ChildItem`.</span></span>

> [!NOTE]
> <span data-ttu-id="c05c9-132">Windows PowerShell 2.0 では、コマンドレットの **再帰** パラメーターを使用する場合、 `Get-ChildItem` **Path** パラメーターの値はコンテナーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c05c9-132">In Windows PowerShell 2.0, when using the **Recurse** parameter of the `Get-ChildItem` cmdlet, the value of the **Path** parameter must be a container.</span></span>
> <span data-ttu-id="c05c9-133">**Include** パラメーターを使用して、.txt ファイル名拡張子フィルターを指定します (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`)。</span><span class="sxs-lookup"><span data-stu-id="c05c9-133">Use the **Include** parameter to specify the .txt file name extension filter (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`).</span></span>

### <span data-ttu-id="c05c9-134">例 5: レジストリのキーと値を別のキーに移動する</span><span class="sxs-lookup"><span data-stu-id="c05c9-134">Example 5: Move registry keys and values to another key</span></span>

<span data-ttu-id="c05c9-135">このコマンドは、の "MyCompany" レジストリキー内のレジストリキーと値 `HKLM\Software` を "MyNewCompany" キーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-135">This command moves the registry keys and values within the "MyCompany" registry key in `HKLM\Software` to the "MyNewCompany" key.</span></span>
<span data-ttu-id="c05c9-136">ワイルドカード文字 ( `*` ) は、キー自体ではなく、"MyCompany" キーの内容を移動する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-136">The wildcard character (`*`) indicates that the contents of the "MyCompany" key should be moved, not the key itself.</span></span>
<span data-ttu-id="c05c9-137">このコマンドでは、省略可能な **パス** と **宛先** のパラメーター名は省略されています。</span><span class="sxs-lookup"><span data-stu-id="c05c9-137">In this command, the optional **Path** and **Destination** parameter names are omitted.</span></span>

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### <span data-ttu-id="c05c9-138">例 6: ディレクトリとその内容を指定されたディレクトリのサブディレクトリに移動する</span><span class="sxs-lookup"><span data-stu-id="c05c9-138">Example 6: Move a directory and its contents to a subdirectory of the specified directory</span></span>

<span data-ttu-id="c05c9-139">このコマンドは、"ログ \[ 9 月 \` 6 \] " ディレクトリ (およびその内容) を "logs \[ 2006 \] " ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-139">This command moves the "Logs\[Sept\`06\]" directory (and its contents) into the "Logs\[2006\]" directory.</span></span>

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
```

<span data-ttu-id="c05c9-140">元のディレクトリ名に左角かっこと右角かっこ ("" および "") が含まれているため、 **Path** の代わりに **LiteralPath** パラメーターが使用されてい \[ \] ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-140">The **LiteralPath** parameter is used instead of **Path**, because the original directory name includes left bracket and right bracket characters ("\[" and "\]").</span></span>
<span data-ttu-id="c05c9-141">また、パスは単一引用符 (' ') で囲まれているため、バックティック記号 ( \` ) は誤って解釈されません。</span><span class="sxs-lookup"><span data-stu-id="c05c9-141">The path is also enclosed in single quotation marks (' '), so that the backtick symbol (\`) is not misinterpreted.</span></span>

<span data-ttu-id="c05c9-142">Destination **パラメーターに** はリテラルパスは必要ありません。これは、変換先の変数に、誤って解釈される可能性のある角かっこが含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="c05c9-142">The **Destination** parameter does not require a literal path, because the Destination variable also must be enclosed in single quotation marks, because it includes brackets that can be misinterpreted.</span></span>

## <span data-ttu-id="c05c9-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c05c9-143">PARAMETERS</span></span>

### <span data-ttu-id="c05c9-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="c05c9-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="c05c9-145">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c05c9-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="c05c9-146">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="c05c9-147">-Destination</span><span class="sxs-lookup"><span data-stu-id="c05c9-147">-Destination</span></span>

<span data-ttu-id="c05c9-148">項目の移動先となる場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-148">Specifies the path to the location where the items are being moved.</span></span>
<span data-ttu-id="c05c9-149">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="c05c9-149">The default is the current directory.</span></span>
<span data-ttu-id="c05c9-150">ワイルドカードも使用できますが、展開結果が単一の場所を指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c05c9-150">Wildcards are permitted, but the result must specify a single location.</span></span>

<span data-ttu-id="c05c9-151">移動する項目の名前を変更するには、 **Destination** パラメーターの値に新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-151">To rename the item being moved, specify a new name in the value of the **Destination** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="c05c9-152">-除外</span><span class="sxs-lookup"><span data-stu-id="c05c9-152">-Exclude</span></span>

<span data-ttu-id="c05c9-153">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-153">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="c05c9-154">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-154">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c05c9-155">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-155">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="c05c9-156">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-156">Wildcard characters are permitted.</span></span> <span data-ttu-id="c05c9-157">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-157">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c05c9-158">-Filter</span><span class="sxs-lookup"><span data-stu-id="c05c9-158">-Filter</span></span>

<span data-ttu-id="c05c9-159">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-159">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="c05c9-160">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="c05c9-160">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="c05c9-161">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05c9-161">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="c05c9-162">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="c05c9-162">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="c05c9-163">-Force</span><span class="sxs-lookup"><span data-stu-id="c05c9-163">-Force</span></span>

<span data-ttu-id="c05c9-164">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-164">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="c05c9-165">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="c05c9-165">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="c05c9-166">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05c9-166">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="c05c9-167">-Include</span><span class="sxs-lookup"><span data-stu-id="c05c9-167">-Include</span></span>

<span data-ttu-id="c05c9-168">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-168">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="c05c9-169">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-169">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c05c9-170">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-170">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="c05c9-171">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-171">Wildcard characters are permitted.</span></span> <span data-ttu-id="c05c9-172">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-172">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c05c9-173">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c05c9-173">-LiteralPath</span></span>

<span data-ttu-id="c05c9-174">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-174">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c05c9-175">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-175">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="c05c9-176">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="c05c9-176">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c05c9-177">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-177">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c05c9-178">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="c05c9-178">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="c05c9-179">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05c9-179">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="c05c9-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c05c9-180">-PassThru</span></span>

<span data-ttu-id="c05c9-181">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-181">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="c05c9-182">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="c05c9-182">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c05c9-183">-Path</span><span class="sxs-lookup"><span data-stu-id="c05c9-183">-Path</span></span>

<span data-ttu-id="c05c9-184">項目の現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-184">Specifies the path to the current location of the items.</span></span>
<span data-ttu-id="c05c9-185">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="c05c9-185">The default is the current directory.</span></span>
<span data-ttu-id="c05c9-186">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-186">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="c05c9-187">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c05c9-187">-Confirm</span></span>

<span data-ttu-id="c05c9-188">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-188">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c05c9-189">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c05c9-189">-WhatIf</span></span>

<span data-ttu-id="c05c9-190">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-190">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c05c9-191">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c05c9-191">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c05c9-192">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c05c9-192">CommonParameters</span></span>

<span data-ttu-id="c05c9-193">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-193">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="c05c9-194">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05c9-194">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c05c9-195">入力</span><span class="sxs-lookup"><span data-stu-id="c05c9-195">INPUTS</span></span>

### <span data-ttu-id="c05c9-196">System.String</span><span class="sxs-lookup"><span data-stu-id="c05c9-196">System.String</span></span>

<span data-ttu-id="c05c9-197">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-197">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="c05c9-198">出力</span><span class="sxs-lookup"><span data-stu-id="c05c9-198">OUTPUTS</span></span>

### <span data-ttu-id="c05c9-199">None または移動された項目を表すオブジェクト</span><span class="sxs-lookup"><span data-stu-id="c05c9-199">None or an object representing the moved item</span></span>

<span data-ttu-id="c05c9-200">*PassThru* パラメーターを使用すると、このコマンドレットは移動した項目を表すオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-200">When you use the *PassThru* parameter, this cmdlet generates an object representing the moved item.</span></span>
<span data-ttu-id="c05c9-201">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="c05c9-201">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c05c9-202">注</span><span class="sxs-lookup"><span data-stu-id="c05c9-202">NOTES</span></span>

- <span data-ttu-id="c05c9-203">このコマンドレットは、同じプロバイダーでサポートされているドライブ間でファイルを移動しますが、ディレクトリを移動するのは同じドライブ内に限られます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-203">This cmdlet will move files between drives that are supported by the same provider, but it will move directories only within the same drive.</span></span>
- <span data-ttu-id="c05c9-204">コマンドは、 `Move-Item` 項目のプロパティ、内容、および子項目を移動するため、既定ではすべての移動が再帰的に行われます。</span><span class="sxs-lookup"><span data-stu-id="c05c9-204">Because a `Move-Item` command moves the properties, contents, and child items of an item, all moves are recursive by default.</span></span>
- <span data-ttu-id="c05c9-205">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c05c9-205">This cmdlet is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="c05c9-206">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="c05c9-206">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="c05c9-207">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c05c9-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c05c9-208">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c05c9-208">RELATED LINKS</span></span>

[<span data-ttu-id="c05c9-209">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="c05c9-209">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="c05c9-210">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="c05c9-210">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="c05c9-211">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c05c9-211">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="c05c9-212">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="c05c9-212">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="c05c9-213">New-Item</span><span class="sxs-lookup"><span data-stu-id="c05c9-213">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="c05c9-214">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="c05c9-214">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="c05c9-215">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="c05c9-215">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="c05c9-216">Set-Item</span><span class="sxs-lookup"><span data-stu-id="c05c9-216">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="c05c9-217">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c05c9-217">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

