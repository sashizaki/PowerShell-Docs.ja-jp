---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-formatdata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-FormatData
ms.openlocfilehash: 5199169677a3b1b56d640ba571c5c150696a552e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217592"
---
# <span data-ttu-id="e6945-103">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="e6945-103">Export-FormatData</span></span>

## <span data-ttu-id="e6945-104">概要</span><span class="sxs-lookup"><span data-stu-id="e6945-104">SYNOPSIS</span></span>
<span data-ttu-id="e6945-105">現在のセッションの書式設定データを書式設定ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="e6945-105">Saves formatting data from the current session in a formatting file.</span></span>

## <span data-ttu-id="e6945-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6945-106">SYNTAX</span></span>

### <span data-ttu-id="e6945-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="e6945-107">ByPath (Default)</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -Path <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

### <span data-ttu-id="e6945-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="e6945-108">ByLiteralPath</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -LiteralPath <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

## <span data-ttu-id="e6945-109">Description</span><span class="sxs-lookup"><span data-stu-id="e6945-109">DESCRIPTION</span></span>

<span data-ttu-id="e6945-110">コマンドレットでは、 `Export-FormatData` 現在のセッションの書式設定オブジェクトから PowerShell 書式設定ファイル (format.ps1xml) を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6945-110">The `Export-FormatData` cmdlet creates PowerShell formatting files (format.ps1xml) from the formatting objects in the current session.</span></span> <span data-ttu-id="e6945-111">これは、を返して XML 形式のファイルに保存する **Extendedtypedefinition** オブジェクトを取得 `Get-FormatData` します。</span><span class="sxs-lookup"><span data-stu-id="e6945-111">It takes the **ExtendedTypeDefinition** objects that `Get-FormatData` returns and saves them in a file in XML format.</span></span>

<span data-ttu-id="e6945-112">PowerShell は、書式設定ファイルのデータ (format.ps1xml) を使用して、セッション内の Microsoft .NET Framework オブジェクトの既定の表示を生成します。</span><span class="sxs-lookup"><span data-stu-id="e6945-112">PowerShell uses the data in formatting files (format.ps1xml) to generate the default display of Microsoft .NET Framework objects in the session.</span></span> <span data-ttu-id="e6945-113">書式設定ファイルは表示および編集することができます。書式設定データをセッションに追加するには、Update-FormatData コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6945-113">You can view and edit the formatting files and use the Update-FormatData cmdlet to add the formatting data to a session.</span></span>

<span data-ttu-id="e6945-114">PowerShell でのファイルの書式設定の詳細については、「 [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6945-114">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="e6945-115">例</span><span class="sxs-lookup"><span data-stu-id="e6945-115">EXAMPLES</span></span>

### <span data-ttu-id="e6945-116">例 1: セッション形式のデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e6945-116">Example 1: Export session format data</span></span>

```powershell
Get-FormatData -TypeName "*" | Export-FormatData -Path "allformat.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="e6945-117">このコマンドは、セッション内のすべての書式設定データを AllFormat.ps1xml ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e6945-117">This command exports all of the format data in the session to the AllFormat.ps1xml file.</span></span>

<span data-ttu-id="e6945-118">コマンドは、コマンドレットを使用して、 `Get-FormatData` セッションの形式データを取得します。</span><span class="sxs-lookup"><span data-stu-id="e6945-118">The command uses the `Get-FormatData` cmdlet to get the format data in the session.</span></span> <span data-ttu-id="e6945-119">`*` **TypeName** パラメーターの値 (all) は、セッション内のすべてのデータを取得するようにコマンドレットに指示します。</span><span class="sxs-lookup"><span data-stu-id="e6945-119">A value of `*` (all) for the **TypeName** parameter directs the cmdlet to get all of the data in the session.</span></span>

<span data-ttu-id="e6945-120">このコマンドは、パイプライン演算子 () を使用して、 `|` コマンドからの形式データを `Get-FormatData` コマンドレットに送信し `Export-FormatData` ます。これにより、フォーマットデータが AllFormat.ps1 ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6945-120">The command uses a pipeline operator (`|`) to send the format data from the `Get-FormatData` command to the `Export-FormatData` cmdlet, which exports the format data to the AllFormat.ps1 file.</span></span>

<span data-ttu-id="e6945-121">この `Export-FormatData` コマンドは、 **IncludeScriptBlock** パラメーターを使用して、ファイルの形式データにスクリプトブロックを含めます。</span><span class="sxs-lookup"><span data-stu-id="e6945-121">The `Export-FormatData` command uses the **IncludeScriptBlock** parameter to include script blocks in the format data in the file.</span></span>

### <span data-ttu-id="e6945-122">例 2: 型の書式データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e6945-122">Example 2: Export format data for a type</span></span>

```powershell
$F = Get-FormatData -TypeName "helpinfoshort"
Export-FormatData -InputObject $F -Path "c:\test\help.format.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="e6945-123">これらのコマンドは、 **Helpinfoshort** 型の形式データを Help.format.ps1xml ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e6945-123">These commands export the format data for the **HelpInfoShort** type to the Help.format.ps1xml file.</span></span>

<span data-ttu-id="e6945-124">最初のコマンドは、コマンドレットを使用して `Get-FormatData` **Helpinfoshort** 型の書式データを取得し、変数に保存し `$F` ます。</span><span class="sxs-lookup"><span data-stu-id="e6945-124">The first command uses the `Get-FormatData` cmdlet to get the format data for the **HelpInfoShort** type, and it saves it in the `$F` variable.</span></span>

<span data-ttu-id="e6945-125">2番目のコマンドは、コマンドレットの **InputObject** パラメーターを使用し `Export-FormatData` て、変数に保存された形式のデータを入力し `$F` ます。</span><span class="sxs-lookup"><span data-stu-id="e6945-125">The second command uses the **InputObject** parameter of the `Export-FormatData` cmdlet to enter the format data saved in the `$F` variable.</span></span> <span data-ttu-id="e6945-126">また、 **IncludeScriptBlock** パラメーターを使用して、出力にスクリプトブロックを含めます。</span><span class="sxs-lookup"><span data-stu-id="e6945-126">It also uses the **IncludeScriptBlock** parameter to include script blocks in the output.</span></span>

### <span data-ttu-id="e6945-127">例 3: スクリプトブロックを使用せずに書式設定データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e6945-127">Example 3: Export format data without a script block</span></span>

```powershell
Get-FormatData -TypeName "System.Diagnostics.Process" | Export-FormatData -Path process.format.ps1xml
Update-FormatData -PrependPath ".\process.format.ps1xml"
Get-Process p*
```

```Output
Handles  NPM(K)  PM(K)  WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------  -----  ----- -----   ------    -- -----------
323                                       5600 powershell
336                                       3900 powershell_ise
138                                       4076 PresentationFontCache
```

<span data-ttu-id="e6945-128">この例は、コマンドから **IncludeScriptBlock** パラメーターを省略した場合の効果を示して `Export-FormatData` います。</span><span class="sxs-lookup"><span data-stu-id="e6945-128">This example shows the effect of omitting the **IncludeScriptBlock** parameter from an `Export-FormatData` command.</span></span>

<span data-ttu-id="e6945-129">最初のコマンドは、コマンドレットを使用して、 `Get-FormatData` Get-Process コマンドレットが返す **システム** の形式のデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="e6945-129">The first command uses the `Get-FormatData` cmdlet to get the format data for the **System.Diagnostics.Process** object that the Get-Process cmdlet returns.</span></span> <span data-ttu-id="e6945-130">このコマンドは、パイプライン演算子 () を使用して、 `|` 書式設定データをコマンドレットに送信します。これにより、 `Export-FormatData` 現在のディレクトリ内の Process.format.ps1xml ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6945-130">The command uses a pipeline operator (`|`) to send the formatting data to the `Export-FormatData` cmdlet, which exports it to the Process.format.ps1xml file in the current directory.</span></span>

<span data-ttu-id="e6945-131">この場合、コマンドでは `Export-FormatData` **IncludeScriptBlock** パラメーターが使用されません。</span><span class="sxs-lookup"><span data-stu-id="e6945-131">In this case, the `Export-FormatData` command does not use the **IncludeScriptBlock** parameter.</span></span>

<span data-ttu-id="e6945-132">2番目のコマンドは、コマンドレットを使用して、 `Update-FormatData` 現在のセッションに Process.format.ps1xml ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6945-132">The second command uses the `Update-FormatData` cmdlet to add the Process.format.ps1xml file to the current session.</span></span> <span data-ttu-id="e6945-133">このコマンドは、 **PrependPath** パラメーターを使用して、プロセスオブジェクトの標準の書式設定データの前に Process.format.ps1xml ファイル内のプロセスオブジェクトの書式設定データが確実に見つかるようにします。</span><span class="sxs-lookup"><span data-stu-id="e6945-133">The command uses the **PrependPath** parameter to ensure that the formatting data for process objects in the Process.format.ps1xml file is found before the standard formatting data for process objects.</span></span>

<span data-ttu-id="e6945-134">3 番目のコマンドにより、この変更の効果が示されています。</span><span class="sxs-lookup"><span data-stu-id="e6945-134">The third command shows the effects of this change.</span></span> <span data-ttu-id="e6945-135">コマンドは、コマンドレットを使用して、 `Get-Process` P で始まる名前を持つプロセスを取得します。出力には、スクリプトブロックを使用して計算されたプロパティ値が表示されないことが示されています。</span><span class="sxs-lookup"><span data-stu-id="e6945-135">The command uses the `Get-Process` cmdlet to get processes that have names that begin with P. The output shows that property values that are calculated by using script blocks are missing from the display.</span></span>

## <span data-ttu-id="e6945-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6945-136">PARAMETERS</span></span>

### <span data-ttu-id="e6945-137">-Force</span><span class="sxs-lookup"><span data-stu-id="e6945-137">-Force</span></span>

<span data-ttu-id="e6945-138">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6945-138">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="e6945-139">-IncludeScriptBlock</span><span class="sxs-lookup"><span data-stu-id="e6945-139">-IncludeScriptBlock</span></span>

<span data-ttu-id="e6945-140">書式設定データのスクリプトブロックをエクスポートするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e6945-140">Indicates whether script blocks in the format data are exported.</span></span>

<span data-ttu-id="e6945-141">中に含まれるコードが悪用される可能性があるため、既定ではスクリプト ブロックはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="e6945-141">Because script blocks contain code and can be used maliciously, they are not exported by default.</span></span>

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

### <span data-ttu-id="e6945-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e6945-142">-InputObject</span></span>

<span data-ttu-id="e6945-143">エクスポートする書式設定データ オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e6945-143">Specifies the format data objects to be exported.</span></span> <span data-ttu-id="e6945-144">オブジェクトを含む変数、またはコマンドなどのオブジェクトを取得するコマンドを入力し `Get-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="e6945-144">Enter a variable that contains the objects or a command that gets the objects, such as a `Get-FormatData` command.</span></span> <span data-ttu-id="e6945-145">オブジェクトをからにパイプすることもでき `Get-FormatData` `Export-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="e6945-145">You can also pipe the objects from `Get-FormatData` to `Export-FormatData`.</span></span>

```yaml
Type: System.Management.Automation.ExtendedTypeDefinition[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e6945-146">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e6945-146">-LiteralPath</span></span>

<span data-ttu-id="e6945-147">出力ファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6945-147">Specifies a location for the output file.</span></span> <span data-ttu-id="e6945-148">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6945-148">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="e6945-149">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="e6945-149">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e6945-150">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="e6945-150">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e6945-151">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="e6945-151">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6945-152">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="e6945-152">-NoClobber</span></span>

<span data-ttu-id="e6945-153">コマンドレットが既存のファイルを上書きしないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e6945-153">Indicates that the cmdlet does not overwrite existing files.</span></span> <span data-ttu-id="e6945-154">既定では、 `Export-FormatData` ファイルに読み取り専用属性が含まれていない限り、は警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="e6945-154">By default, `Export-FormatData` overwrites files without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="e6945-155">読み取り専用ファイルを上書きするように指定するには `Export-FormatData` 、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6945-155">To direct `Export-FormatData` to overwrite read-only files, use the **Force** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6945-156">-Path</span><span class="sxs-lookup"><span data-stu-id="e6945-156">-Path</span></span>

<span data-ttu-id="e6945-157">出力ファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6945-157">Specifies a location for the output file.</span></span>
<span data-ttu-id="e6945-158">パス (省略可能) と format.ps1xml ファイル名拡張子が付いたファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6945-158">Enter a path (optional) and file name with a format.ps1xml file name extension.</span></span>
<span data-ttu-id="e6945-159">パスを省略した場合、は `Export-FormatData` 現在のディレクトリにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6945-159">If you omit the path, `Export-FormatData` creates the file in the current directory.</span></span>

<span data-ttu-id="e6945-160">Types.ps1xml 以外のファイル名拡張子を使用する場合、この `Update-FormatData` コマンドレットはファイルを認識しません。</span><span class="sxs-lookup"><span data-stu-id="e6945-160">If you use a file name extension other than .ps1xml, the `Update-FormatData` cmdlet will not recognize the file.</span></span>

<span data-ttu-id="e6945-161">既存のファイルを指定すると、ファイルに `Export-FormatData` 読み取り専用属性が含まれていない限り、は警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="e6945-161">If you specify an existing file, `Export-FormatData` overwrites the file without warning, unless the file has the read-only attribute.</span></span> <span data-ttu-id="e6945-162">読み取り専用ファイルを上書きするには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6945-162">To overwrite a read-only file, use the **Force** parameter.</span></span> <span data-ttu-id="e6945-163">ファイルが上書きされないようにするには、 **NoClobber** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6945-163">To prevent files from being overwritten, use the **NoClobber** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6945-164">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6945-164">CommonParameters</span></span>

<span data-ttu-id="e6945-165">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e6945-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6945-166">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6945-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6945-167">入力</span><span class="sxs-lookup"><span data-stu-id="e6945-167">INPUTS</span></span>

### <span data-ttu-id="e6945-168">システムの管理. ExtendedTypeDefinition</span><span class="sxs-lookup"><span data-stu-id="e6945-168">System.Management.Automation.ExtendedTypeDefinition</span></span>

<span data-ttu-id="e6945-169">パイプを使用して、 **Extendedtypedefinition** オブジェクトをからにパイプすることができ `Get-FormatData` `Export-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="e6945-169">You can pipe **ExtendedTypeDefinition** objects from `Get-FormatData` to `Export-FormatData`.</span></span>

## <span data-ttu-id="e6945-170">出力</span><span class="sxs-lookup"><span data-stu-id="e6945-170">OUTPUTS</span></span>

### <span data-ttu-id="e6945-171">なし</span><span class="sxs-lookup"><span data-stu-id="e6945-171">None</span></span>

<span data-ttu-id="e6945-172">`Export-FormatData` はオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="e6945-172">`Export-FormatData` does not return any objects.</span></span>
<span data-ttu-id="e6945-173">ファイルを生成し、指定されたパス内に保存します。</span><span class="sxs-lookup"><span data-stu-id="e6945-173">It generates a file and saves it in the specified path.</span></span>

## <span data-ttu-id="e6945-174">注</span><span class="sxs-lookup"><span data-stu-id="e6945-174">NOTES</span></span>

- <span data-ttu-id="e6945-175">エクスポートされた書式設定ファイルを含む任意の書式設定ファイルを使用するには、セッションの実行ポリシーでスクリプトと構成ファイルの実行が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6945-175">To use any formatting file, including an exported formatting file, the execution policy for the session must allow scripts and configuration files to run.</span></span> <span data-ttu-id="e6945-176">詳細については、「[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6945-176">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="e6945-177">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e6945-177">RELATED LINKS</span></span>

[<span data-ttu-id="e6945-178">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="e6945-178">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="e6945-179">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="e6945-179">Update-FormatData</span></span>](Update-FormatData.md)