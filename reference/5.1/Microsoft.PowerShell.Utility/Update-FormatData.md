---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-formatdata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-FormatData
ms.openlocfilehash: 41a49ccd185cdc1ebf5c6f748833ee3f4218784b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213627"
---
# <span data-ttu-id="c94b9-103">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="c94b9-103">Update-FormatData</span></span>

## <span data-ttu-id="c94b9-104">概要</span><span class="sxs-lookup"><span data-stu-id="c94b9-104">SYNOPSIS</span></span>
<span data-ttu-id="c94b9-105">現在のセッションの書式設定データを更新します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-105">Updates the formatting data in the current session.</span></span>

## <span data-ttu-id="c94b9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c94b9-106">SYNTAX</span></span>

```
Update-FormatData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="c94b9-107">Description</span><span class="sxs-lookup"><span data-stu-id="c94b9-107">DESCRIPTION</span></span>

<span data-ttu-id="c94b9-108">このコマンドレットは、書式設定 `Update-FormatData` データをフォーマットファイルから現在のセッションに再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="c94b9-108">The `Update-FormatData` cmdlet reloads the formatting data from formatting files into the current session.</span></span> <span data-ttu-id="c94b9-109">このコマンドレットを使用すると、PowerShell を再起動しなくても書式設定データを更新できます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-109">This cmdlet lets you update the formatting data without restarting PowerShell.</span></span>

<span data-ttu-id="c94b9-110">パラメーターを指定せずに、 `Update-FormatData` 以前に読み込まれた書式設定ファイルを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="c94b9-110">Without parameters, `Update-FormatData` reloads the formatting files that it loaded previously.</span></span>
<span data-ttu-id="c94b9-111">のパラメーターを使用し `Update-FormatData` て、新しい書式設定ファイルをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-111">You can use the parameters of `Update-FormatData` to add new formatting files to the session.</span></span>

<span data-ttu-id="c94b9-112">書式設定ファイルは、ファイル名拡張子を持つ XML 形式のテキストファイルです `format.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="c94b9-112">Formatting files are text files in XML format with the `format.ps1xml` file name extension.</span></span> <span data-ttu-id="c94b9-113">ファイル内の書式設定データは、セッションでの Microsoft .NET Framework オブジェクトの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-113">The formatting data in the files defines the display of Microsoft .NET Framework objects in the session.</span></span>

<span data-ttu-id="c94b9-114">Windows PowerShell が起動すると、PowerShell インストールディレクトリ () のフォーマットファイルの形式データが `$pshome` セッションに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-114">When Windows PowerShell starts, it loads the format data from the formatting files in the PowerShell installation directory (`$pshome`) into the session.</span></span> <span data-ttu-id="c94b9-115">を使用すると、 `Update-FormatData` PowerShell を再起動せずに、書式設定データを現在のセッションに再度読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-115">You can use `Update-FormatData` to reload the formatting data into the current session without restarting PowerShell.</span></span> <span data-ttu-id="c94b9-116">このコマンドレットは、書式設定ファイルを追加または変更した後でセッションを中断したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c94b9-116">This is useful when you have added or changed a formatting file, but do not want to interrupt the session.</span></span>

<span data-ttu-id="c94b9-117">PowerShell でのファイルの書式設定の詳細については、「 [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c94b9-117">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="c94b9-118">例</span><span class="sxs-lookup"><span data-stu-id="c94b9-118">EXAMPLES</span></span>

### <span data-ttu-id="c94b9-119">例 1: 以前に読み込まれた書式設定ファイルを再読み込みする</span><span class="sxs-lookup"><span data-stu-id="c94b9-119">Example 1: Reload previously loaded formatting files</span></span>

```powershell
Update-FormatData
```

<span data-ttu-id="c94b9-120">このコマンドは、以前に読み込まれた書式設定ファイルを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="c94b9-120">This command reloads the formatting files that it loaded previously.</span></span>

### <span data-ttu-id="c94b9-121">例 2: フォーマットファイルとトレースおよびログの書式設定ファイルを再読み込みする</span><span class="sxs-lookup"><span data-stu-id="c94b9-121">Example 2: Reload formatting files and trace and log formatting files</span></span>

```powershell
Update-FormatData -AppendPath "trace.format.ps1xml, log.format.ps1xml"
```

<span data-ttu-id="c94b9-122">このコマンドは、Trace.format.ps1xml と Log.format.ps1xml の 2 つの新しいファイルを含む書式設定ファイルをセッションに再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="c94b9-122">This command reloads the formatting files into the session, including two new files, Trace.format.ps1xml and Log.format.ps1xml.</span></span>

<span data-ttu-id="c94b9-123">コマンドで **Appendpath** パラメーターが使用されるため、新しいファイルの書式設定データは、組み込みファイルの書式設定データの後に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-123">Because the command uses the **AppendPath** parameter, the formatting data in the new files is loaded after the formatting data from the built-in files.</span></span>

<span data-ttu-id="c94b9-124">**Appendpath** パラメーターが使用されるのは、組み込みファイルで参照されていないオブジェクトの書式設定データが新しいファイルに含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="c94b9-124">The **AppendPath** parameter is used because the new files contain formatting data for objects that are not referenced in the built-in files.</span></span>

### <span data-ttu-id="c94b9-125">例 3: 書式設定ファイルを編集して再読み込みする</span><span class="sxs-lookup"><span data-stu-id="c94b9-125">Example 3: Edit a formatting file and reload it</span></span>

```powershell
Update-FormatData -PrependPath "c:\test\NewFiles.format.ps1xml"

# Edit the NewFiles.format.ps1 file.

Update-FormatData
```

<span data-ttu-id="c94b9-126">この例では、書式設定ファイルを編集した後で再読み込みする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-126">This example shows how to reload a formatting file after you have edited it.</span></span>

<span data-ttu-id="c94b9-127">最初のコマンドは、NewFiles.format.ps1xml ファイルをセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-127">The first command adds the NewFiles.format.ps1xml file to the session.</span></span> <span data-ttu-id="c94b9-128">**PrependPath** パラメーターを使用します。これは、組み込みファイルで参照されるオブジェクトの書式設定データがファイルに含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="c94b9-128">It uses the **PrependPath** parameter because the file contains formatting data for objects that are referenced in the built-in files.</span></span>

<span data-ttu-id="c94b9-129">NewFiles.format.ps1xml ファイルを追加し、これらのセッションでテストした後、作成者はファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-129">After adding the NewFiles.format.ps1xml file and testing it in these sessions, the author edits the file.</span></span>

<span data-ttu-id="c94b9-130">2番目のコマンドは、コマンドレットを使用して、 `Update-FormatData` 書式設定ファイルを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="c94b9-130">The second command uses the `Update-FormatData` cmdlet to reload the formatting files.</span></span> <span data-ttu-id="c94b9-131">NewFiles.format.ps1xml ファイルは既に読み込まれているので、 `Update-FormatData` パラメーターを使用せずに、自動的に再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="c94b9-131">Because the NewFiles.format.ps1xml file was previously loaded, `Update-FormatData` automatically reloads it without using parameters.</span></span>

## <span data-ttu-id="c94b9-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c94b9-132">PARAMETERS</span></span>

### <span data-ttu-id="c94b9-133">-AppendPath</span><span class="sxs-lookup"><span data-stu-id="c94b9-133">-AppendPath</span></span>

<span data-ttu-id="c94b9-134">このコマンドレットによってセッションに追加されるフォーマットファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-134">Specifies formatting files that this cmdlet adds to the session.</span></span> <span data-ttu-id="c94b9-135">ファイルは、PowerShell が組み込みの書式設定ファイルを読み込んだ後に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-135">The files are loaded after PowerShell loads the built-in formatting files.</span></span>

<span data-ttu-id="c94b9-136">.NET オブジェクトを書式設定する場合、Windows PowerShell は、各 .NET 型に対して検出された最初の書式定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-136">When formatting .NET objects,Windows PowerShell uses the first formatting definition that it finds for each .NET type.</span></span> <span data-ttu-id="c94b9-137">**Appendpath** パラメーターを使用すると、Windows PowerShell は、追加する書式設定データを検出する前に、組み込みファイルからデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-137">If you use the **AppendPath** parameter, Windows PowerShell searches the data from the built-in files before it encounters the formatting data that you are adding.</span></span>

<span data-ttu-id="c94b9-138">組み込みの書式設定ファイルで参照されない .NET オブジェクトを書式設定するファイルを追加するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-138">Use this parameter to add a file that formats a .NET object that is not referenced in the built-in formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c94b9-139">-PrependPath</span><span class="sxs-lookup"><span data-stu-id="c94b9-139">-PrependPath</span></span>

<span data-ttu-id="c94b9-140">このコマンドレットによってセッションに追加されるフォーマットファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-140">Specifies formatting files that this cmdlet adds to the session.</span></span> <span data-ttu-id="c94b9-141">ファイルは、PowerShell が組み込みの書式設定ファイルを読み込む前に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-141">The files are loaded before PowerShell loads the built-in formatting files.</span></span>

<span data-ttu-id="c94b9-142">.NET オブジェクトを書式設定する場合、Windows PowerShell は、それぞれの .NET の種類に対して、最初に検出した書式設定定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-142">When formatting .NET objects, Windows PowerShell uses the first formatting definition that it finds for each .NET type.</span></span> <span data-ttu-id="c94b9-143">**PrependPath** パラメーターを使用すると、Windows PowerShell は、組み込みのファイルの書式設定データを検出する前に、追加するファイルからデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-143">If you use the **PrependPath** parameter, Windows PowerShell searches the data from the files that you are adding before it encounters the formatting data from the built-in files.</span></span>

<span data-ttu-id="c94b9-144">組み込みの書式設定ファイルでも参照される .NET オブジェクトを書式設定するファイルを追加するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-144">Use this parameter to add a file that formats a .NET object that is also referenced in the built-in formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c94b9-145">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c94b9-145">-Confirm</span></span>

<span data-ttu-id="c94b9-146">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-146">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c94b9-147">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c94b9-147">-WhatIf</span></span>

<span data-ttu-id="c94b9-148">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c94b9-148">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c94b9-149">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c94b9-149">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c94b9-150">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c94b9-150">CommonParameters</span></span>

<span data-ttu-id="c94b9-151">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c94b9-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c94b9-152">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c94b9-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c94b9-153">入力</span><span class="sxs-lookup"><span data-stu-id="c94b9-153">INPUTS</span></span>

### <span data-ttu-id="c94b9-154">System.String</span><span class="sxs-lookup"><span data-stu-id="c94b9-154">System.String</span></span>

<span data-ttu-id="c94b9-155">パイプを使用して、追加パスを含む文字列をにパイプすることができ `Update-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-155">You can pipe a string that contains the append path to `Update-FormatData`.</span></span>

## <span data-ttu-id="c94b9-156">出力</span><span class="sxs-lookup"><span data-stu-id="c94b9-156">OUTPUTS</span></span>

### <span data-ttu-id="c94b9-157">なし</span><span class="sxs-lookup"><span data-stu-id="c94b9-157">None</span></span>

<span data-ttu-id="c94b9-158">このコマンドレットは出力を返しません。</span><span class="sxs-lookup"><span data-stu-id="c94b9-158">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="c94b9-159">注</span><span class="sxs-lookup"><span data-stu-id="c94b9-159">NOTES</span></span>

- <span data-ttu-id="c94b9-160">`Update-FormatData` では、モジュールからインポートされたセッションのコマンドの書式設定データも更新されます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-160">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="c94b9-161">モジュールのフォーマットファイルが変更された場合は、コマンドを実行して、インポートした `Update-FormatData` コマンドの書式設定データを更新できます。</span><span class="sxs-lookup"><span data-stu-id="c94b9-161">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="c94b9-162">モジュールをもう一度インポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c94b9-162">You do not need to import the module again.</span></span>

## <span data-ttu-id="c94b9-163">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c94b9-163">RELATED LINKS</span></span>

[<span data-ttu-id="c94b9-164">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="c94b9-164">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="c94b9-165">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="c94b9-165">Export-FormatData</span></span>](Export-FormatData.md)
