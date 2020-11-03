---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Item
ms.openlocfilehash: 66a7b82b56028a4801a3aa8c93cd46460a5353ce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214992"
---
# <span data-ttu-id="e962f-103">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="e962f-103">Rename-Item</span></span>

## <span data-ttu-id="e962f-104">概要</span><span class="sxs-lookup"><span data-stu-id="e962f-104">SYNOPSIS</span></span>
<span data-ttu-id="e962f-105">PowerShell プロバイダーの名前空間内の項目の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="e962f-105">Renames an item in a PowerShell provider namespace.</span></span>

## <span data-ttu-id="e962f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e962f-106">SYNTAX</span></span>

### <span data-ttu-id="e962f-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="e962f-107">ByPath (Default)</span></span>

```
Rename-Item [-Path] <String> [-NewName] <String> [-Force] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="e962f-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="e962f-108">ByLiteralPath</span></span>

```
Rename-Item -LiteralPath <String> [-NewName] <String> [-Force] [-PassThru]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="e962f-109">Description</span><span class="sxs-lookup"><span data-stu-id="e962f-109">DESCRIPTION</span></span>

<span data-ttu-id="e962f-110">コマンドレットでは、 `Rename-Item` 指定した項目の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="e962f-110">The `Rename-Item` cmdlet changes the name of a specified item.</span></span> <span data-ttu-id="e962f-111">このコマンドレットを使用しても、名前を変更する項目の内容には影響ありません。</span><span class="sxs-lookup"><span data-stu-id="e962f-111">This cmdlet does not affect the content of the item being renamed.</span></span>

<span data-ttu-id="e962f-112">を使用し `Rename-Item` て、新しい名前でパスを指定するなど、項目を移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="e962f-112">You can't use `Rename-Item` to move an item, such as by specifying a path together with the new name.</span></span> <span data-ttu-id="e962f-113">項目を移動して名前を変更するには、コマンドレットを使用し `Move-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="e962f-113">To move and rename an item, use the `Move-Item` cmdlet.</span></span>

## <span data-ttu-id="e962f-114">例</span><span class="sxs-lookup"><span data-stu-id="e962f-114">EXAMPLES</span></span>

### <span data-ttu-id="e962f-115">例 1: ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="e962f-115">Example 1: Rename a file</span></span>

<span data-ttu-id="e962f-116">このコマンドにより、ファイルの名前がに変更さ `daily_file.txt` `monday_file.txt` れます。</span><span class="sxs-lookup"><span data-stu-id="e962f-116">This command renames the file `daily_file.txt` to `monday_file.txt`.</span></span>

```powershell
Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"
```

### <span data-ttu-id="e962f-117">例 2: 項目の名前を変更して移動する</span><span class="sxs-lookup"><span data-stu-id="e962f-117">Example 2: Rename and move an item</span></span>

<span data-ttu-id="e962f-118">を使用し `Rename-Item` て項目の名前変更と移動を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="e962f-118">You can't use `Rename-Item` to both rename and move an item.</span></span> <span data-ttu-id="e962f-119">具体的には、path パラメーターに指定され **たパスと** 同じパスでない限り、 **NewName** パラメーターの値のパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e962f-119">Specifically, you can't supply a path for the value of the **NewName** parameter, unless the path is identical to the path specified in the **Path** parameter.</span></span> <span data-ttu-id="e962f-120">そうでない場合は、新しい名前のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="e962f-120">Otherwise, only a new name is permitted.</span></span>

<span data-ttu-id="e962f-121">この例では、ディレクトリ内の現在のディレクトリにあるファイルの名前をに変更しようとして `project.txt` `old-project.txt` `D:\Archive` います。</span><span class="sxs-lookup"><span data-stu-id="e962f-121">This example attempts to rename the `project.txt` file in the current directory to `old-project.txt` in the `D:\Archive` directory.</span></span> <span data-ttu-id="e962f-122">結果は出力に示されるようなエラーになります。</span><span class="sxs-lookup"><span data-stu-id="e962f-122">The result is the error shown in the output.</span></span>

```powershell
Rename-Item -Path "project.txt" -NewName "d:\archive\old-project.txt"
```

```Output
Rename-Item : can't rename because the target specified represents a path or device name.
At line:1 char:12
+ Rename-Item <<<<  -path project.txt -NewName d:\archive\old-project.txt
+ CategoryInfo          : InvalidArgument: (:) [Rename-Item], PS>  Move-Item -Path "project.txt" -De
stination "d:\archive\old-project.txt"
```

### <span data-ttu-id="e962f-123">例 3: レジストリキーの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="e962f-123">Example 3: Rename a registry key</span></span>

<span data-ttu-id="e962f-124">この例では、レジストリキーの名前を **宣伝** から **Marketing** に変更します。</span><span class="sxs-lookup"><span data-stu-id="e962f-124">This example renames a registry key from **Advertising** to **Marketing** .</span></span> <span data-ttu-id="e962f-125">コマンドが完了すると、キーの名前が変更されますが、キーのレジストリ エントリに変更はありません。</span><span class="sxs-lookup"><span data-stu-id="e962f-125">When the command is complete, the key is renamed, but the registry entries in the key are unchanged.</span></span>

```powershell
Rename-Item -Path "HKLM:\Software\MyCompany\Advertising" -NewName "Marketing"
```

### <span data-ttu-id="e962f-126">例 4: 複数のファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="e962f-126">Example 4: Rename multiple files</span></span>

<span data-ttu-id="e962f-127">この例では、現在のディレクトリ内のすべてのファイルの名前 `*.txt` をに変更 `*.log` します。</span><span class="sxs-lookup"><span data-stu-id="e962f-127">This example renames all the `*.txt` files in the current directory to `*.log`.</span></span>

```powershell
Get-ChildItem *.txt
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.TXT
-a----        10/3/2019   7:46 AM           2918 Monday.Txt
-a----        10/3/2019   7:47 AM           2918 Wednesday.txt
```

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.Name -replace '.txt','.log' }
Get-ChildItem *.log
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.log
-a----        10/3/2019   7:46 AM           2918 Monday.log
-a----        10/3/2019   7:47 AM           2918 Wednesday.log
```

<span data-ttu-id="e962f-128">この `Get-ChildItem` コマンドレットは、ファイル拡張子を持つ現在のフォルダー内のすべてのファイルを取得し、それらのファイル `.txt` をにパイプし `Rename-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="e962f-128">The `Get-ChildItem` cmdlet gets all the files in the current folder that have a `.txt` file extension then pipes them to `Rename-Item`.</span></span> <span data-ttu-id="e962f-129">**Newname** の値は、値が **newname** パラメーターに送信される前に実行されるスクリプトブロックです。</span><span class="sxs-lookup"><span data-stu-id="e962f-129">The value of **NewName** is a script block that runs before the value is submitted to the **NewName** parameter.</span></span>

<span data-ttu-id="e962f-130">スクリプトブロックでは、 `$_` 自動変数は、パイプラインを介してコマンドに渡される各ファイルオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="e962f-130">In the script block, the `$_` automatic variable represents each file object as it comes to the command through the pipeline.</span></span> <span data-ttu-id="e962f-131">スクリプトブロックでは、演算子を使用して、 `-replace` 各ファイルのファイル拡張子をに置き換え `.log` ます。</span><span class="sxs-lookup"><span data-stu-id="e962f-131">The script block uses the `-replace` operator to replace the file extension of each file with `.log`.</span></span> <span data-ttu-id="e962f-132">演算子を使用した照合で `-replace` は大文字と小文字が区別されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e962f-132">Notice that matching using the `-replace` operator is not case sensitive.</span></span>

## <span data-ttu-id="e962f-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e962f-133">PARAMETERS</span></span>

### <span data-ttu-id="e962f-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="e962f-134">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="e962f-135">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e962f-135">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="e962f-136">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e962f-136">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="e962f-137">-Force</span><span class="sxs-lookup"><span data-stu-id="e962f-137">-Force</span></span>

<span data-ttu-id="e962f-138">非表示または読み取り専用のファイルや読み取り専用のエイリアスまたは変数など、変更できない項目の名前をコマンドレットで強制的に変更します。</span><span class="sxs-lookup"><span data-stu-id="e962f-138">Forces the cmdlet to rename items that can't otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="e962f-139">コマンドレットでは、定数のエイリアスまたは変数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e962f-139">The cmdlet can't change constant aliases or variables.</span></span>
<span data-ttu-id="e962f-140">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="e962f-140">Implementation varies from provider to provider.</span></span> <span data-ttu-id="e962f-141">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e962f-141">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="e962f-142">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="e962f-142">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="e962f-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e962f-143">-LiteralPath</span></span>

<span data-ttu-id="e962f-144">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e962f-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="e962f-145">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e962f-145">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="e962f-146">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="e962f-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e962f-147">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="e962f-147">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e962f-148">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="e962f-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="e962f-149">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e962f-149">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e962f-150">-NewName</span><span class="sxs-lookup"><span data-stu-id="e962f-150">-NewName</span></span>

<span data-ttu-id="e962f-151">項目の新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e962f-151">Specifies the new name of the item.</span></span> <span data-ttu-id="e962f-152">パスと名前ではなく、名前のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="e962f-152">Enter only a name, not a path and name.</span></span> <span data-ttu-id="e962f-153">**Path パラメーターで** 指定したパスとは異なるパスを入力すると、によって `Rename-Item` エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e962f-153">If you enter a path that differs from the path that is specified in the **Path** parameter, `Rename-Item` generates an error.</span></span>
<span data-ttu-id="e962f-154">項目の名前を変更したり移動したりするには、を使用し `Move-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="e962f-154">To rename and move an item, use `Move-Item`.</span></span>

<span data-ttu-id="e962f-155">**NewName** パラメーターの値にワイルドカード文字を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e962f-155">You can't use wildcard characters in the value of the **NewName** parameter.</span></span> <span data-ttu-id="e962f-156">複数のファイルの名前を指定するには、正規表現で **Replace** 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="e962f-156">To specify a name for multiple files, use the **Replace** operator in a regular expression.</span></span> <span data-ttu-id="e962f-157">Replace 演算子の詳細については、「 [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e962f-157">For more information about the Replace operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e962f-158">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e962f-158">-PassThru</span></span>

<span data-ttu-id="e962f-159">パイプラインの項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e962f-159">Returns an object that represents the item to the pipeline.</span></span> <span data-ttu-id="e962f-160">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="e962f-160">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e962f-161">-Path</span><span class="sxs-lookup"><span data-stu-id="e962f-161">-Path</span></span>

<span data-ttu-id="e962f-162">名前を変更する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e962f-162">Specifies the path of the item to rename.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e962f-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e962f-163">-Confirm</span></span>

<span data-ttu-id="e962f-164">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e962f-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e962f-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e962f-165">-WhatIf</span></span>

<span data-ttu-id="e962f-166">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="e962f-166">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e962f-167">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e962f-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e962f-168">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e962f-168">CommonParameters</span></span>

<span data-ttu-id="e962f-169">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e962f-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e962f-170">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e962f-170">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e962f-171">入力</span><span class="sxs-lookup"><span data-stu-id="e962f-171">INPUTS</span></span>

### <span data-ttu-id="e962f-172">System.String</span><span class="sxs-lookup"><span data-stu-id="e962f-172">System.String</span></span>

<span data-ttu-id="e962f-173">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="e962f-173">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="e962f-174">出力</span><span class="sxs-lookup"><span data-stu-id="e962f-174">OUTPUTS</span></span>

### <span data-ttu-id="e962f-175">None または名前が変更された項目を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e962f-175">None or an object that represents the renamed item.</span></span>

<span data-ttu-id="e962f-176">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、名前が変更された項目を表すオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="e962f-176">This cmdlet generates an object that represents the renamed item, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="e962f-177">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="e962f-177">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e962f-178">注</span><span class="sxs-lookup"><span data-stu-id="e962f-178">NOTES</span></span>

<span data-ttu-id="e962f-179">`Rename-Item` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e962f-179">`Rename-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="e962f-180">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="e962f-180">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="e962f-181">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e962f-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="e962f-182">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e962f-182">RELATED LINKS</span></span>

[<span data-ttu-id="e962f-183">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="e962f-183">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="e962f-184">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="e962f-184">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="e962f-185">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e962f-185">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="e962f-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e962f-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="e962f-187">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="e962f-187">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="e962f-188">Move-Item</span><span class="sxs-lookup"><span data-stu-id="e962f-188">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="e962f-189">New-Item</span><span class="sxs-lookup"><span data-stu-id="e962f-189">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="e962f-190">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="e962f-190">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="e962f-191">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e962f-191">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="e962f-192">Set-Item</span><span class="sxs-lookup"><span data-stu-id="e962f-192">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="e962f-193">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e962f-193">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
