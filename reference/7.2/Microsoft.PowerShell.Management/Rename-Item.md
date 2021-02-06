---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Item
ms.openlocfilehash: dec5c2c905486110e4885f29d236ab41d945fb96
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602011"
---
# <span data-ttu-id="dea2b-102">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="dea2b-102">Rename-Item</span></span>

## <span data-ttu-id="dea2b-103">概要</span><span class="sxs-lookup"><span data-stu-id="dea2b-103">SYNOPSIS</span></span>
<span data-ttu-id="dea2b-104">PowerShell プロバイダーの名前空間内の項目の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-104">Renames an item in a PowerShell provider namespace.</span></span>

## <span data-ttu-id="dea2b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dea2b-105">SYNTAX</span></span>

### <span data-ttu-id="dea2b-106">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="dea2b-106">ByPath (Default)</span></span>

```
Rename-Item [-Path] <String> [-NewName] <String> [-Force] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="dea2b-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="dea2b-107">ByLiteralPath</span></span>

```
Rename-Item -LiteralPath <String> [-NewName] <String> [-Force] [-PassThru]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="dea2b-108">Description</span><span class="sxs-lookup"><span data-stu-id="dea2b-108">DESCRIPTION</span></span>

<span data-ttu-id="dea2b-109">コマンドレットでは、 `Rename-Item` 指定した項目の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-109">The `Rename-Item` cmdlet changes the name of a specified item.</span></span> <span data-ttu-id="dea2b-110">このコマンドレットを使用しても、名前を変更する項目の内容には影響ありません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-110">This cmdlet does not affect the content of the item being renamed.</span></span>

<span data-ttu-id="dea2b-111">を使用し `Rename-Item` て、新しい名前でパスを指定するなど、項目を移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-111">You can't use `Rename-Item` to move an item, such as by specifying a path together with the new name.</span></span> <span data-ttu-id="dea2b-112">項目を移動して名前を変更するには、コマンドレットを使用し `Move-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-112">To move and rename an item, use the `Move-Item` cmdlet.</span></span>

## <span data-ttu-id="dea2b-113">例</span><span class="sxs-lookup"><span data-stu-id="dea2b-113">EXAMPLES</span></span>

### <span data-ttu-id="dea2b-114">例 1: ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="dea2b-114">Example 1: Rename a file</span></span>

<span data-ttu-id="dea2b-115">このコマンドにより、ファイルの名前がに変更さ `daily_file.txt` `monday_file.txt` れます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-115">This command renames the file `daily_file.txt` to `monday_file.txt`.</span></span>

```powershell
Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"
```

### <span data-ttu-id="dea2b-116">例 2: 項目の名前を変更して移動する</span><span class="sxs-lookup"><span data-stu-id="dea2b-116">Example 2: Rename and move an item</span></span>

<span data-ttu-id="dea2b-117">を使用し `Rename-Item` て項目の名前変更と移動を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-117">You can't use `Rename-Item` to both rename and move an item.</span></span> <span data-ttu-id="dea2b-118">具体的には、path パラメーターに指定され **たパスと** 同じパスでない限り、 **NewName** パラメーターの値のパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-118">Specifically, you can't supply a path for the value of the **NewName** parameter, unless the path is identical to the path specified in the **Path** parameter.</span></span> <span data-ttu-id="dea2b-119">そうでない場合は、新しい名前のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-119">Otherwise, only a new name is permitted.</span></span>

<span data-ttu-id="dea2b-120">この例では、ディレクトリ内の現在のディレクトリにあるファイルの名前をに変更しようとして `project.txt` `old-project.txt` `D:\Archive` います。</span><span class="sxs-lookup"><span data-stu-id="dea2b-120">This example attempts to rename the `project.txt` file in the current directory to `old-project.txt` in the `D:\Archive` directory.</span></span> <span data-ttu-id="dea2b-121">結果は出力に示されるようなエラーになります。</span><span class="sxs-lookup"><span data-stu-id="dea2b-121">The result is the error shown in the output.</span></span>

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

### <span data-ttu-id="dea2b-122">例 3: レジストリキーの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="dea2b-122">Example 3: Rename a registry key</span></span>

<span data-ttu-id="dea2b-123">この例では、レジストリキーの名前を **宣伝** から **Marketing** に変更します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-123">This example renames a registry key from **Advertising** to **Marketing**.</span></span> <span data-ttu-id="dea2b-124">コマンドが完了すると、キーの名前が変更されますが、キーのレジストリ エントリに変更はありません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-124">When the command is complete, the key is renamed, but the registry entries in the key are unchanged.</span></span>

```powershell
Rename-Item -Path "HKLM:\Software\MyCompany\Advertising" -NewName "Marketing"
```

### <span data-ttu-id="dea2b-125">例 4: 複数のファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="dea2b-125">Example 4: Rename multiple files</span></span>

<span data-ttu-id="dea2b-126">この例では、現在のディレクトリ内のすべてのファイルの名前 `*.txt` をに変更 `*.log` します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-126">This example renames all the `*.txt` files in the current directory to `*.log`.</span></span>

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

<span data-ttu-id="dea2b-127">この `Get-ChildItem` コマンドレットは、ファイル拡張子を持つ現在のフォルダー内のすべてのファイルを取得し、それらのファイル `.txt` をにパイプし `Rename-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-127">The `Get-ChildItem` cmdlet gets all the files in the current folder that have a `.txt` file extension then pipes them to `Rename-Item`.</span></span> <span data-ttu-id="dea2b-128">**Newname** の値は、値が **newname** パラメーターに送信される前に実行されるスクリプトブロックです。</span><span class="sxs-lookup"><span data-stu-id="dea2b-128">The value of **NewName** is a script block that runs before the value is submitted to the **NewName** parameter.</span></span>

<span data-ttu-id="dea2b-129">スクリプトブロックでは、 `$_` 自動変数は、パイプラインを介してコマンドに渡される各ファイルオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-129">In the script block, the `$_` automatic variable represents each file object as it comes to the command through the pipeline.</span></span> <span data-ttu-id="dea2b-130">スクリプトブロックでは、演算子を使用して、 `-replace` 各ファイルのファイル拡張子をに置き換え `.log` ます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-130">The script block uses the `-replace` operator to replace the file extension of each file with `.log`.</span></span> <span data-ttu-id="dea2b-131">演算子を使用した照合で `-replace` は大文字と小文字が区別されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dea2b-131">Notice that matching using the `-replace` operator is not case sensitive.</span></span>

## <span data-ttu-id="dea2b-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dea2b-132">PARAMETERS</span></span>

### <span data-ttu-id="dea2b-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="dea2b-133">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="dea2b-134">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-134">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="dea2b-135">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-135">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="dea2b-136">-Force</span><span class="sxs-lookup"><span data-stu-id="dea2b-136">-Force</span></span>

<span data-ttu-id="dea2b-137">非表示または読み取り専用のファイルや読み取り専用のエイリアスまたは変数など、変更できない項目の名前をコマンドレットで強制的に変更します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-137">Forces the cmdlet to rename items that can't otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="dea2b-138">コマンドレットでは、定数のエイリアスまたは変数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-138">The cmdlet can't change constant aliases or variables.</span></span>
<span data-ttu-id="dea2b-139">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="dea2b-139">Implementation varies from provider to provider.</span></span> <span data-ttu-id="dea2b-140">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dea2b-140">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="dea2b-141">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-141">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="dea2b-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="dea2b-142">-LiteralPath</span></span>

<span data-ttu-id="dea2b-143">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="dea2b-144">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="dea2b-145">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="dea2b-146">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="dea2b-147">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="dea2b-148">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dea2b-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="dea2b-149">-NewName</span><span class="sxs-lookup"><span data-stu-id="dea2b-149">-NewName</span></span>

<span data-ttu-id="dea2b-150">項目の新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-150">Specifies the new name of the item.</span></span> <span data-ttu-id="dea2b-151">パスと名前ではなく、名前のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-151">Enter only a name, not a path and name.</span></span> <span data-ttu-id="dea2b-152">**Path パラメーターで** 指定したパスとは異なるパスを入力すると、によって `Rename-Item` エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-152">If you enter a path that differs from the path that is specified in the **Path** parameter, `Rename-Item` generates an error.</span></span>
<span data-ttu-id="dea2b-153">項目の名前を変更したり移動したりするには、を使用し `Move-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-153">To rename and move an item, use `Move-Item`.</span></span>

<span data-ttu-id="dea2b-154">**NewName** パラメーターの値にワイルドカード文字を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-154">You can't use wildcard characters in the value of the **NewName** parameter.</span></span> <span data-ttu-id="dea2b-155">複数のファイルの名前を指定するには、正規表現で **Replace** 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-155">To specify a name for multiple files, use the **Replace** operator in a regular expression.</span></span> <span data-ttu-id="dea2b-156">Replace 演算子の詳細については、「 [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dea2b-156">For more information about the Replace operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span></span>

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

### <span data-ttu-id="dea2b-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="dea2b-157">-PassThru</span></span>

<span data-ttu-id="dea2b-158">パイプラインの項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-158">Returns an object that represents the item to the pipeline.</span></span> <span data-ttu-id="dea2b-159">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-159">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="dea2b-160">-Path</span><span class="sxs-lookup"><span data-stu-id="dea2b-160">-Path</span></span>

<span data-ttu-id="dea2b-161">名前を変更する項目のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-161">Specifies the path of the item to rename.</span></span>

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

### <span data-ttu-id="dea2b-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dea2b-162">-Confirm</span></span>

<span data-ttu-id="dea2b-163">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="dea2b-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dea2b-164">-WhatIf</span></span>

<span data-ttu-id="dea2b-165">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-165">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="dea2b-166">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="dea2b-167">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea2b-167">CommonParameters</span></span>

<span data-ttu-id="dea2b-168">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="dea2b-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dea2b-169">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dea2b-169">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="dea2b-170">入力</span><span class="sxs-lookup"><span data-stu-id="dea2b-170">INPUTS</span></span>

### <span data-ttu-id="dea2b-171">System.String</span><span class="sxs-lookup"><span data-stu-id="dea2b-171">System.String</span></span>

<span data-ttu-id="dea2b-172">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="dea2b-172">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="dea2b-173">出力</span><span class="sxs-lookup"><span data-stu-id="dea2b-173">OUTPUTS</span></span>

### <span data-ttu-id="dea2b-174">None または名前が変更された項目を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dea2b-174">None or an object that represents the renamed item.</span></span>

<span data-ttu-id="dea2b-175">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、名前が変更された項目を表すオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-175">This cmdlet generates an object that represents the renamed item, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="dea2b-176">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="dea2b-176">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="dea2b-177">注</span><span class="sxs-lookup"><span data-stu-id="dea2b-177">NOTES</span></span>

<span data-ttu-id="dea2b-178">`Rename-Item` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="dea2b-178">`Rename-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="dea2b-179">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="dea2b-179">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="dea2b-180">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dea2b-180">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="dea2b-181">関連リンク</span><span class="sxs-lookup"><span data-stu-id="dea2b-181">RELATED LINKS</span></span>

[<span data-ttu-id="dea2b-182">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="dea2b-182">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="dea2b-183">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="dea2b-183">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="dea2b-184">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="dea2b-184">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="dea2b-185">Get-Item</span><span class="sxs-lookup"><span data-stu-id="dea2b-185">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="dea2b-186">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="dea2b-186">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="dea2b-187">Move-Item</span><span class="sxs-lookup"><span data-stu-id="dea2b-187">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="dea2b-188">New-Item</span><span class="sxs-lookup"><span data-stu-id="dea2b-188">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="dea2b-189">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="dea2b-189">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="dea2b-190">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dea2b-190">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="dea2b-191">Set-Item</span><span class="sxs-lookup"><span data-stu-id="dea2b-191">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="dea2b-192">about_Providers</span><span class="sxs-lookup"><span data-stu-id="dea2b-192">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

