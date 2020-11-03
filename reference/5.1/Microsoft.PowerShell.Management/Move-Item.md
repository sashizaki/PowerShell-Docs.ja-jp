---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: d3637825e7570e5fb0f3ff77efbc89e9d93974a3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214627"
---
# <span data-ttu-id="93343-103">Move-Item</span><span class="sxs-lookup"><span data-stu-id="93343-103">Move-Item</span></span>

## <span data-ttu-id="93343-104">概要</span><span class="sxs-lookup"><span data-stu-id="93343-104">SYNOPSIS</span></span>
<span data-ttu-id="93343-105">項目をある場所から別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="93343-105">Moves an item from one location to another.</span></span>

## <span data-ttu-id="93343-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="93343-106">SYNTAX</span></span>

### <span data-ttu-id="93343-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="93343-107">Path (Default)</span></span>

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="93343-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="93343-108">LiteralPath</span></span>

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="93343-109">Description</span><span class="sxs-lookup"><span data-stu-id="93343-109">DESCRIPTION</span></span>

<span data-ttu-id="93343-110">`Move-Item`コマンドレットは、プロパティ、内容、子項目などの項目を、ある場所から別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="93343-110">The `Move-Item` cmdlet moves an item, including its properties, contents, and child items, from one location to another location.</span></span>
<span data-ttu-id="93343-111">移動元と移動先は、どちらも同じプロバイダーでサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="93343-111">The locations must be supported by the same provider.</span></span>
<span data-ttu-id="93343-112">たとえば、ファイルやサブディレクトリを別のディレクトリに移動したり、レジストリのサブキーを別のキーに移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="93343-112">For example, it can move a file or subdirectory from one directory to another or move a registry subkey from one key to another.</span></span>
<span data-ttu-id="93343-113">移動した項目は新しい場所に追加され、元の場所から削除されます。</span><span class="sxs-lookup"><span data-stu-id="93343-113">When you move an item, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="93343-114">例</span><span class="sxs-lookup"><span data-stu-id="93343-114">EXAMPLES</span></span>

### <span data-ttu-id="93343-115">例 1: ファイルを別のディレクトリに移動して名前を変更する</span><span class="sxs-lookup"><span data-stu-id="93343-115">Example 1: Move a file to another directory and rename it</span></span>

<span data-ttu-id="93343-116">このコマンドは、"Test.txt" ファイルを `C:` ドライブから "E:\Temp" ディレクトリに移動し、"test.txt" から "tst.txt" に名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="93343-116">This command moves the "Test.txt" file from the `C:` drive to the "E:\Temp" directory and renames it from "test.txt" to "tst.txt".</span></span>

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### <span data-ttu-id="93343-117">例 2: ディレクトリとその内容を別のディレクトリに移動する</span><span class="sxs-lookup"><span data-stu-id="93343-117">Example 2: Move a directory and its contents to another directory</span></span>

<span data-ttu-id="93343-118">このコマンドは、"C:\Temp" ディレクトリとその内容を "C:\Logs" ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="93343-118">This command moves the "C:\Temp" directory and its contents to the "C:\Logs" directory.</span></span>
<span data-ttu-id="93343-119">"Temp" ディレクトリとそのすべてのサブディレクトリとファイルが "Logs" ディレクトリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="93343-119">The "Temp" directory, and all of its subdirectories and files, then appear in the "Logs" directory.</span></span>

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### <span data-ttu-id="93343-120">例 3: 指定した拡張子のすべてのファイルを現在のディレクトリから別のディレクトリに移動する</span><span class="sxs-lookup"><span data-stu-id="93343-120">Example 3: Move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="93343-121">このコマンドは、現在のディレクトリ (ドット ('. ') で表されます) 内のすべてのテキストファイル ("\* .txt") を "C:\Logs" ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="93343-121">This command moves all of the text files ("\*.txt") in the current directory (represented by a dot ('.')) to the "C:\Logs" directory.</span></span>

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### <span data-ttu-id="93343-122">例 4: 指定した拡張子のすべてのファイルを現在のディレクトリから別のディレクトリに再帰的に移動する</span><span class="sxs-lookup"><span data-stu-id="93343-122">Example 4: Recursively move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="93343-123">このコマンドは、すべてのテキストファイルを現在のディレクトリとすべてのサブディレクトリから再帰的に "C:\ textfiles" ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="93343-123">This command moves all of the text files from the current directory and all subdirectories, recursively, to the "C:\TextFiles" directory.</span></span>

<span data-ttu-id="93343-124">このコマンドは、コマンドレットを使用して、 `Get-ChildItem` (ドットで表される) 現在のディレクトリ内のすべての子項目 \[ \] と、" *.txt" というファイル名拡張子を持つサブディレクトリを取得します。Recursive パラメーターを **Recurse** 使用して、検索を再帰的にし、Include パラメーターを使用* して取得を ".txt" ファイルに制限します。</span><span class="sxs-lookup"><span data-stu-id="93343-124">The command uses the `Get-ChildItem` cmdlet to get all of the child items in the current directory (represented by the dot \[.\]) and its subdirectories that have a " *.txt" file name extension. It uses the **Recurse** parameter to make the retrieval recursive and the Include parameter to limit the retrieval to "* .txt" files.</span></span>

<span data-ttu-id="93343-125">パイプライン演算子 () は、 `|` このコマンドの結果をに送信します。これにより `Move-Item` 、テキストファイルが "textfiles" ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="93343-125">The pipeline operator (`|`) sends the results of this command to `Move-Item`, which moves the text files to the "TextFiles" directory.</span></span>

<span data-ttu-id="93343-126">"C:\ textfiles" に移動されるファイルの名前が同じである場合、は `Move-Item` エラーを表示して続行しますが、名前が "C:\ textfiles" になるファイルを1つだけ移動します。</span><span class="sxs-lookup"><span data-stu-id="93343-126">If files that are to be moved to "C:\Textfiles" have the same name, `Move-Item` displays an error and continues, but it moves only one file with each name to "C:\Textfiles".</span></span>
<span data-ttu-id="93343-127">その他のファイルは元のディレクトリに残ります。</span><span class="sxs-lookup"><span data-stu-id="93343-127">The other files remain in their original directories.</span></span>

<span data-ttu-id="93343-128">"Textfiles" ディレクトリ (または移動先のパスの他の要素) が存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="93343-128">If the "Textfiles" directory (or any other element of the destination path) does not exist, the command fails.</span></span>
<span data-ttu-id="93343-129">**Force** パラメーターを使用した場合でも、不足しているディレクトリは作成されません。</span><span class="sxs-lookup"><span data-stu-id="93343-129">The missing directory is not created for you, even if you use the **Force** parameter.</span></span>
<span data-ttu-id="93343-130">`Move-Item` 最初の項目を "Textfiles" という名前のファイルに移動し、そのファイルが既に存在することを示すエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="93343-130">`Move-Item` moves the first item to a file called "Textfiles" and then displays an error explaining that the file already exists.</span></span>

<span data-ttu-id="93343-131">また、既定で `Get-ChildItem` は、は隠しファイルを移動しません。</span><span class="sxs-lookup"><span data-stu-id="93343-131">Also, by default, `Get-ChildItem` does not move hidden files.</span></span>
<span data-ttu-id="93343-132">隠しファイルを移動するには、 **Force** パラメーターをと共に使用し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="93343-132">To move hidden files, use the **Force** parameter with `Get-ChildItem`.</span></span>

<span data-ttu-id="93343-133">注: Windows PowerShell 2.0 では、コマンドレットの **再帰** パラメーターを使用する場合、 `Get-ChildItem` **Path** パラメーターの値はコンテナーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="93343-133">Note: In Windows PowerShell 2.0, when using the **Recurse** parameter of the `Get-ChildItem` cmdlet, the value of the **Path** parameter must be a container.</span></span>
<span data-ttu-id="93343-134">**Include** パラメーターを使用して、.txt ファイル名拡張子フィルターを指定します (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`)。</span><span class="sxs-lookup"><span data-stu-id="93343-134">Use the **Include** parameter to specify the .txt file name extension filter (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`).</span></span>

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

### <span data-ttu-id="93343-135">例 5: レジストリのキーと値を別のキーに移動する</span><span class="sxs-lookup"><span data-stu-id="93343-135">Example 5: Move registry keys and values to another key</span></span>

<span data-ttu-id="93343-136">このコマンドは、"、Hklm\software" の "MyCompany" レジストリキー内のレジストリキーと値を "MyNewCompany" キーに移動します。</span><span class="sxs-lookup"><span data-stu-id="93343-136">This command moves the registry keys and values within the "MyCompany" registry key in "HKLM\Software" to the "MyNewCompany" key.</span></span>
<span data-ttu-id="93343-137">ワイルドカード文字 (' \* ') は、キー自体ではなく、"MyCompany" キーの内容を移動する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="93343-137">The wildcard character ('\*') indicates that the contents of the "MyCompany" key should be moved, not the key itself.</span></span>
<span data-ttu-id="93343-138">このコマンドでは、省略可能な **パス** と **宛先** のパラメーター名は省略されています。</span><span class="sxs-lookup"><span data-stu-id="93343-138">In this command, the optional **Path** and **Destination** parameter names are omitted.</span></span>

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### <span data-ttu-id="93343-139">例 6: ディレクトリとその内容を指定されたディレクトリのサブディレクトリに移動する</span><span class="sxs-lookup"><span data-stu-id="93343-139">Example 6: Move a directory and its contents to a subdirectory of the specified directory</span></span>

<span data-ttu-id="93343-140">このコマンドは、"ログ \[ 9 月 \` 6 \] " ディレクトリ (およびその内容) を "logs \[ 2006 \] " ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="93343-140">This command moves the "Logs\[Sept\`06\]" directory (and its contents) into the "Logs\[2006\]" directory.</span></span>

<span data-ttu-id="93343-141">元のディレクトリ名に左角かっこと右角かっこ ("" および "") が含まれているため、 **Path** の代わりに **LiteralPath** パラメーターが使用されてい \[ \] ます。</span><span class="sxs-lookup"><span data-stu-id="93343-141">The **LiteralPath** parameter is used instead of **Path** , because the original directory name includes left bracket and right bracket characters ("\[" and "\]").</span></span>
<span data-ttu-id="93343-142">また、パスは単一引用符 (' ') で囲まれているため、バックティック記号 ( \` ) は誤って解釈されません。</span><span class="sxs-lookup"><span data-stu-id="93343-142">The path is also enclosed in single quotation marks (' '), so that the backtick symbol (\`) is not misinterpreted.</span></span>

<span data-ttu-id="93343-143">Destination **パラメーターに** はリテラルパスは必要ありません。これは、変換先の変数に、誤って解釈される可能性のある角かっこが含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="93343-143">The **Destination** parameter does not require a literal path, because the Destination variable also must be enclosed in single quotation marks, because it includes brackets that can be misinterpreted.</span></span>

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
```

## <span data-ttu-id="93343-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="93343-144">PARAMETERS</span></span>

### <span data-ttu-id="93343-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="93343-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="93343-146">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="93343-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="93343-147">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="93343-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="93343-148">-Destination</span><span class="sxs-lookup"><span data-stu-id="93343-148">-Destination</span></span>

<span data-ttu-id="93343-149">項目の移動先となる場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="93343-149">Specifies the path to the location where the items are being moved.</span></span>
<span data-ttu-id="93343-150">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="93343-150">The default is the current directory.</span></span>
<span data-ttu-id="93343-151">ワイルドカードも使用できますが、展開結果が単一の場所を指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="93343-151">Wildcards are permitted, but the result must specify a single location.</span></span>

<span data-ttu-id="93343-152">移動する項目の名前を変更するには、 **Destination** パラメーターの値に新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="93343-152">To rename the item being moved, specify a new name in the value of the **Destination** parameter.</span></span>

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

### <span data-ttu-id="93343-153">-除外</span><span class="sxs-lookup"><span data-stu-id="93343-153">-Exclude</span></span>

<span data-ttu-id="93343-154">このコマンドレットによって操作から除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="93343-154">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="93343-155">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="93343-155">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="93343-156">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="93343-156">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="93343-157">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="93343-157">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="93343-158">-Filter</span><span class="sxs-lookup"><span data-stu-id="93343-158">-Filter</span></span>

<span data-ttu-id="93343-159">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="93343-159">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="93343-160">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="93343-160">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="93343-161">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="93343-161">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="93343-162">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="93343-162">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="93343-163">-Force</span><span class="sxs-lookup"><span data-stu-id="93343-163">-Force</span></span>

<span data-ttu-id="93343-164">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="93343-164">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="93343-165">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="93343-165">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="93343-166">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93343-166">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="93343-167">-Include</span><span class="sxs-lookup"><span data-stu-id="93343-167">-Include</span></span>

<span data-ttu-id="93343-168">このコマンドレットが操作内で移動する項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="93343-168">Specifies, as a string array, an item or items that this cmdlet moves in the operation.</span></span>
<span data-ttu-id="93343-169">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="93343-169">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="93343-170">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="93343-170">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="93343-171">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="93343-171">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="93343-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="93343-172">-LiteralPath</span></span>

<span data-ttu-id="93343-173">項目の現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="93343-173">Specifies the path to the current location of the items.</span></span>
<span data-ttu-id="93343-174">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="93343-174">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="93343-175">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="93343-175">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="93343-176">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="93343-176">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="93343-177">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="93343-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="93343-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="93343-178">-PassThru</span></span>

<span data-ttu-id="93343-179">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="93343-179">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="93343-180">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="93343-180">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="93343-181">-Path</span><span class="sxs-lookup"><span data-stu-id="93343-181">-Path</span></span>

<span data-ttu-id="93343-182">項目の現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="93343-182">Specifies the path to the current location of the items.</span></span>
<span data-ttu-id="93343-183">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="93343-183">The default is the current directory.</span></span>
<span data-ttu-id="93343-184">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="93343-184">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="93343-185">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="93343-185">-UseTransaction</span></span>

<span data-ttu-id="93343-186">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="93343-186">Includes the command in the active transaction.</span></span>
<span data-ttu-id="93343-187">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="93343-187">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="93343-188">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93343-188">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="93343-189">-Confirm</span><span class="sxs-lookup"><span data-stu-id="93343-189">-Confirm</span></span>

<span data-ttu-id="93343-190">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="93343-190">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="93343-191">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="93343-191">-WhatIf</span></span>

<span data-ttu-id="93343-192">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="93343-192">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="93343-193">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="93343-193">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="93343-194">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="93343-194">CommonParameters</span></span>

<span data-ttu-id="93343-195">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="93343-195">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="93343-196">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93343-196">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="93343-197">入力</span><span class="sxs-lookup"><span data-stu-id="93343-197">INPUTS</span></span>

### <span data-ttu-id="93343-198">System.String</span><span class="sxs-lookup"><span data-stu-id="93343-198">System.String</span></span>

<span data-ttu-id="93343-199">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="93343-199">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="93343-200">出力</span><span class="sxs-lookup"><span data-stu-id="93343-200">OUTPUTS</span></span>

### <span data-ttu-id="93343-201">None または移動された項目を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="93343-201">None or an object representing the moved item.</span></span>

<span data-ttu-id="93343-202">*PassThru* パラメーターを使用すると、このコマンドレットは移動した項目を表すオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="93343-202">When you use the *PassThru* parameter, this cmdlet generates an object representing the moved item.</span></span>
<span data-ttu-id="93343-203">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="93343-203">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="93343-204">注</span><span class="sxs-lookup"><span data-stu-id="93343-204">NOTES</span></span>

<span data-ttu-id="93343-205">このコマンドレットは、同じプロバイダーでサポートされているドライブ間でファイルを移動しますが、ディレクトリを移動するのは同じドライブ内に限られます。</span><span class="sxs-lookup"><span data-stu-id="93343-205">This cmdlet will move files between drives that are supported by the same provider, but it will move directories only within the same drive.</span></span>

<span data-ttu-id="93343-206">コマンドは、 `Move-Item` 項目のプロパティ、内容、および子項目を移動するため、既定ではすべての移動が再帰的に行われます。</span><span class="sxs-lookup"><span data-stu-id="93343-206">Because a `Move-Item` command moves the properties, contents, and child items of an item, all moves are recursive by default.</span></span>

<span data-ttu-id="93343-207">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="93343-207">This cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="93343-208">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="93343-208">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="93343-209">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93343-209">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="93343-210">関連リンク</span><span class="sxs-lookup"><span data-stu-id="93343-210">RELATED LINKS</span></span>

[<span data-ttu-id="93343-211">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="93343-211">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="93343-212">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="93343-212">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="93343-213">Get-Item</span><span class="sxs-lookup"><span data-stu-id="93343-213">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="93343-214">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="93343-214">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="93343-215">New-Item</span><span class="sxs-lookup"><span data-stu-id="93343-215">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="93343-216">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="93343-216">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="93343-217">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="93343-217">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="93343-218">Set-Item</span><span class="sxs-lookup"><span data-stu-id="93343-218">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="93343-219">about_Providers</span><span class="sxs-lookup"><span data-stu-id="93343-219">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
