---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-alias?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Alias
ms.openlocfilehash: 50b0ccf6c56613166d16648492b6b35e5714832e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214067"
---
# <span data-ttu-id="b09d2-103">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="b09d2-103">Export-Alias</span></span>

## <span data-ttu-id="b09d2-104">概要</span><span class="sxs-lookup"><span data-stu-id="b09d2-104">SYNOPSIS</span></span>
<span data-ttu-id="b09d2-105">現在定義されているエイリアスに関する情報をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-105">Exports information about currently defined aliases to a file.</span></span>

## <span data-ttu-id="b09d2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b09d2-106">SYNTAX</span></span>

### <span data-ttu-id="b09d2-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="b09d2-107">ByPath (Default)</span></span>

```
Export-Alias [-Path] <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append] [-Force]
 [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b09d2-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="b09d2-108">ByLiteralPath</span></span>

```
Export-Alias -LiteralPath <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append]
 [-Force] [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b09d2-109">Description</span><span class="sxs-lookup"><span data-stu-id="b09d2-109">DESCRIPTION</span></span>

<span data-ttu-id="b09d2-110">`Export-Alias`コマンドレットは、現在のセッションのエイリアスをファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-110">The `Export-Alias` cmdlet exports the aliases in the current session to a file.</span></span>
<span data-ttu-id="b09d2-111">出力ファイルが存在しない場合は、コマンドレットにより作成されます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-111">If the output file does not exist, the cmdlet will create it.</span></span>

<span data-ttu-id="b09d2-112">`Export-Alias` では、特定のスコープまたはすべてのスコープのエイリアスをエクスポートできます。また、データを CSV 形式で生成したり、セッションまたは PowerShell プロファイルに追加できる一連の Set-Alias コマンドとしてエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-112">`Export-Alias` can export the aliases in a particular scope or all scopes, it can generate the data in CSV format or as a series of Set-Alias commands that you can add to a session or to a PowerShell profile.</span></span>

## <span data-ttu-id="b09d2-113">例</span><span class="sxs-lookup"><span data-stu-id="b09d2-113">EXAMPLES</span></span>

### <span data-ttu-id="b09d2-114">例 1: エイリアスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b09d2-114">Example 1: Export an alias</span></span>

```powershell
Export-Alias -Path "alias.csv"
```

<span data-ttu-id="b09d2-115">このコマンドは、現在のエイリアス情報を現在のディレクトリ内の Alias.csv というファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-115">This command exports current alias information to a file named Alias.csv in the current directory.</span></span>

### <span data-ttu-id="b09d2-116">例 2: エクスポートファイルが既に存在する場合を除き、エイリアスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b09d2-116">Example 2: Export an alias unless the export file already exists</span></span>

```powershell
Export-Alias -Path "alias.csv" -NoClobber
```

<span data-ttu-id="b09d2-117">このコマンドは、現在のセッションのエイリアスを Alias.csv ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-117">This command exports the aliases in the current session to an Alias.csv file.</span></span>

<span data-ttu-id="b09d2-118">**NoClobber** パラメーターが指定されているため、現在のディレクトリに Alias.csv ファイルが既に存在する場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-118">Because the **NoClobber** parameter is specified, the command will fail if an Alias.csv file already exists in the current directory.</span></span>

### <span data-ttu-id="b09d2-119">例 3: ファイルにエイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="b09d2-119">Example 3: Append aliases to a file</span></span>

```powershell
Export-Alias -Path "alias.csv" -Append -Description "Appended Aliases" -Force
```

<span data-ttu-id="b09d2-120">このコマンドは、現在のセッションのエイリアスを Alias.csv ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-120">This command appends the aliases in the current session to the Alias.csv file.</span></span>

<span data-ttu-id="b09d2-121">このコマンドは、 **description** パラメーターを使用して、ファイルの先頭のコメントに説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-121">The command uses the **Description** parameter to add a description to the comments at the top of the file.</span></span>

<span data-ttu-id="b09d2-122">また、このコマンドは、読み取り専用属性を持っている場合でも、 **Force** パラメーターを使用して既存の Alias.csv ファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-122">The command also uses the **Force** parameter to overwrite any existing Alias.csv files, even if they have the read-only attribute.</span></span>

### <span data-ttu-id="b09d2-123">例 4: エイリアスをスクリプトとしてエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b09d2-123">Example 4: Export aliases as a script</span></span>

```powershell
Export-Alias -Path "alias.ps1" -As Script
Add-Content -Path $Profile -Value (Get-Content alias.ps1)
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -FilePath .\alias.ps1
```

<span data-ttu-id="b09d2-124">この例では、によって生成されるスクリプトファイル形式を使用する方法を示し `Export-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-124">This example shows how to use the script file format that `Export-Alias` generates.</span></span>

<span data-ttu-id="b09d2-125">このコマンドは、セッションのエイリアスを Alias.ps1 ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-125">The first command exports the aliases in the session to the Alias.ps1 file.</span></span>
<span data-ttu-id="b09d2-126">As パラメーターを使用してスクリプトの値を指定する **と** 、各エイリアスの Set-Alias コマンドを含むファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-126">It uses the **As** parameter with a value of Script to generate a file that contains a Set-Alias command for each alias.</span></span>

<span data-ttu-id="b09d2-127">2 番目のコマンドは、Alias.ps1 ファイル内のエイリアスを CurrentUser-CurrentHost プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-127">The second command adds the aliases in the Alias.ps1 file to the CurrentUser-CurrentHost profile.</span></span>
<span data-ttu-id="b09d2-128">プロファイルへのパスは、変数に保存され `$Profile` ます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-128">The path to the profile is saved in the `$Profile` variable.</span></span>
<span data-ttu-id="b09d2-129">このコマンドは、コマンドレットを使用して、 `Get-Content` Alias.ps1 ファイルからエイリアスを取得し、コマンドレットを使用して `Add-Content` それらをプロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-129">The command uses the `Get-Content` cmdlet to get the aliases from the Alias.ps1 file and the `Add-Content` cmdlet to add them to the profile.</span></span>
<span data-ttu-id="b09d2-130">詳細については、「about_Profiles」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b09d2-130">For more information, see about_Profiles.</span></span>

<span data-ttu-id="b09d2-131">3番目と4番目のコマンドは、Alias.ps1 ファイルのエイリアスを Server01 コンピューター上のリモートセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-131">The third and fourth commands add the aliases in the Alias.ps1 file to a remote session on the Server01 computer.</span></span>
<span data-ttu-id="b09d2-132">3番目のコマンドは、 `New-PSSession` コマンドレットを使用してセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-132">The third command uses the `New-PSSession` cmdlet to create the session.</span></span>
<span data-ttu-id="b09d2-133">4番目のコマンドは、コマンドレットの **FilePath** パラメーターを使用して、 `Invoke-Command` 新しいセッションで Alias.ps1 ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-133">The fourth command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run the Alias.ps1 file in the new session.</span></span>

## <span data-ttu-id="b09d2-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b09d2-134">PARAMETERS</span></span>

### <span data-ttu-id="b09d2-135">-追加</span><span class="sxs-lookup"><span data-stu-id="b09d2-135">-Append</span></span>

<span data-ttu-id="b09d2-136">このコマンドレットが、指定されたファイルの既存の内容を上書きするのではなく、指定したファイルに出力を追加することを示します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-136">Indicates that this cmdlet appends the output to the specified file, rather than overwriting the existing contents of that file.</span></span>

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

### <span data-ttu-id="b09d2-137">-As</span><span class="sxs-lookup"><span data-stu-id="b09d2-137">-As</span></span>

<span data-ttu-id="b09d2-138">出力形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-138">Specifies the output format.</span></span>
<span data-ttu-id="b09d2-139">CSV が既定値です。</span><span class="sxs-lookup"><span data-stu-id="b09d2-139">CSV is the default.</span></span>
<span data-ttu-id="b09d2-140">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b09d2-140">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b09d2-141">市区.</span><span class="sxs-lookup"><span data-stu-id="b09d2-141">CSV.</span></span>
<span data-ttu-id="b09d2-142">コンマ区切り値 (CSV) 形式です。</span><span class="sxs-lookup"><span data-stu-id="b09d2-142">Comma-separated value (CSV) format.</span></span>
- <span data-ttu-id="b09d2-143">スクリプティング。</span><span class="sxs-lookup"><span data-stu-id="b09d2-143">Script.</span></span>
<span data-ttu-id="b09d2-144">エクスポートさ `Set-Alias` れた各エイリアスに対してコマンドを作成します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-144">Creates a `Set-Alias` command for each exported alias.</span></span>
<span data-ttu-id="b09d2-145">ファイル名拡張子 .ps1 を使用して出力ファイルに名前を付ける場合は、任意のセッションにエイリアスを追加するスクリプトとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-145">If you name the output file with a .ps1 file name extension, you can run it as a script to add the aliases to any session.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ExportAliasFormat
Parameter Sets: (All)
Aliases:
Accepted values: Csv, Script

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b09d2-146">-Description</span><span class="sxs-lookup"><span data-stu-id="b09d2-146">-Description</span></span>

<span data-ttu-id="b09d2-147">エクスポートするファイルの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-147">Specifies the description of the exported file.</span></span>
<span data-ttu-id="b09d2-148">ファイルの先頭のヘッダー情報に続いて、説明がコメントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-148">The description appears as a comment at the top of the file, following the header information.</span></span>

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

### <span data-ttu-id="b09d2-149">-Force</span><span class="sxs-lookup"><span data-stu-id="b09d2-149">-Force</span></span>

<span data-ttu-id="b09d2-150">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-150">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="b09d2-151">読み取り専用の属性がファイルに設定されている場合でも、出力ファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-151">Overwrites the output file, even if the read-only attribute is set on the file.</span></span>

<span data-ttu-id="b09d2-152">既定では、 `Export-Alias` 読み取り専用または非表示の属性が設定されている場合、またはコマンドで **NoClobber** パラメーターが使用されている場合を除き、は警告なしにファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-152">By default, `Export-Alias` overwrites files without warning, unless the read-only or hidden attribute is set or the **NoClobber** parameter is used in the command.</span></span>
<span data-ttu-id="b09d2-153">コマンドで両方を使用する場合、 **NoClobber** パラメーターは **Force** パラメーターよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-153">The **NoClobber** parameter takes precedence over the **Force** parameter when both are used in a command.</span></span>

<span data-ttu-id="b09d2-154">**Force** パラメーターは、 `Export-Alias` hidden 属性を持つファイルを強制的に上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b09d2-154">The **Force** parameter cannot force `Export-Alias` to overwrite files with the hidden attribute.</span></span>

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

### <span data-ttu-id="b09d2-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b09d2-155">-LiteralPath</span></span>

<span data-ttu-id="b09d2-156">出力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-156">Specifies the path to the output file.</span></span>
<span data-ttu-id="b09d2-157">**Path** と異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-157">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="b09d2-158">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="b09d2-158">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="b09d2-159">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-159">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="b09d2-160">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="b09d2-160">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b09d2-161">-Name</span><span class="sxs-lookup"><span data-stu-id="b09d2-161">-Name</span></span>

<span data-ttu-id="b09d2-162">エクスポートするエイリアスの配列として、名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-162">Specifies the names as an array of the aliases to export.</span></span>
<span data-ttu-id="b09d2-163">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-163">Wildcards are permitted.</span></span>

<span data-ttu-id="b09d2-164">既定で `Export-Alias` は、はセッションまたはスコープ内のすべてのエイリアスをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-164">By default, `Export-Alias` exports all aliases in the session or scope.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b09d2-165">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="b09d2-165">-NoClobber</span></span>

<span data-ttu-id="b09d2-166">`Export-Alias`コマンドで **Force** パラメーターが使用されている場合でも、このコマンドレットによってファイルが上書きされないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-166">Indicates that this cmdlet prevents `Export-Alias` from overwriting any files, even if the **Force** parameter is used in the command.</span></span>

<span data-ttu-id="b09d2-167">**NoClobber** パラメーターを省略すると、 `Export-Alias` ファイルに対して読み取り専用属性が設定されていない限り、は警告を表示せずに既存のファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="b09d2-167">If the **NoClobber** parameter is omitted, `Export-Alias` will overwrite an existing file without warning, unless the read-only attribute is set on the file.</span></span>
<span data-ttu-id="b09d2-168">*NoClobber* は、読み取り専用 **Force** `Export-Alias` 属性を使用してファイルを上書きすることを許可する Force パラメーターよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-168">*NoClobber* takes precedence over the **Force** parameter, which permits `Export-Alias` to overwrite a file with the read-only attribute.</span></span>

<span data-ttu-id="b09d2-169">*NoClobber* では、 **Append** パラメーターによって既存のファイルにコンテンツが追加されるのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="b09d2-169">*NoClobber* does not prevent the **Append** parameter from adding content to an existing file.</span></span>

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

### <span data-ttu-id="b09d2-170">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b09d2-170">-PassThru</span></span>

<span data-ttu-id="b09d2-171">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-171">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b09d2-172">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="b09d2-172">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b09d2-173">-Path</span><span class="sxs-lookup"><span data-stu-id="b09d2-173">-Path</span></span>

<span data-ttu-id="b09d2-174">出力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-174">Specifies the path to the output file.</span></span>
<span data-ttu-id="b09d2-175">ワイルドカードは許可されていますが、結果のパスの値を 1 つのファイル名に解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b09d2-175">Wildcards are permitted, but the resulting path value must resolve to a single file name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b09d2-176">-スコープ</span><span class="sxs-lookup"><span data-stu-id="b09d2-176">-Scope</span></span>

<span data-ttu-id="b09d2-177">エイリアスのエクスポート元となるスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-177">Specifies the scope from which the aliases should be exported.</span></span>
<span data-ttu-id="b09d2-178">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b09d2-178">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b09d2-179">グローバル</span><span class="sxs-lookup"><span data-stu-id="b09d2-179">Global</span></span>
- <span data-ttu-id="b09d2-180">ローカル</span><span class="sxs-lookup"><span data-stu-id="b09d2-180">Local</span></span>
- <span data-ttu-id="b09d2-181">スクリプト</span><span class="sxs-lookup"><span data-stu-id="b09d2-181">Script</span></span>
- <span data-ttu-id="b09d2-182">現在のスコープに対して相対的な数値 (0 ~ スコープの数で、0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="b09d2-182">A number relative to the current scope (0 through the number of scopes where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="b09d2-183">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="b09d2-183">The default value is Local.</span></span>
<span data-ttu-id="b09d2-184">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b09d2-184">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="b09d2-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b09d2-185">-Confirm</span></span>

<span data-ttu-id="b09d2-186">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b09d2-186">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b09d2-187">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b09d2-187">-WhatIf</span></span>

<span data-ttu-id="b09d2-188">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="b09d2-188">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b09d2-189">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="b09d2-189">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b09d2-190">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b09d2-190">CommonParameters</span></span>

<span data-ttu-id="b09d2-191">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b09d2-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b09d2-192">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b09d2-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b09d2-193">入力</span><span class="sxs-lookup"><span data-stu-id="b09d2-193">INPUTS</span></span>

### <span data-ttu-id="b09d2-194">なし。</span><span class="sxs-lookup"><span data-stu-id="b09d2-194">None.</span></span>

<span data-ttu-id="b09d2-195">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b09d2-195">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="b09d2-196">出力</span><span class="sxs-lookup"><span data-stu-id="b09d2-196">OUTPUTS</span></span>

### <span data-ttu-id="b09d2-197">None または system.servicemodel. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="b09d2-197">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="b09d2-198">**Passthru** パラメーターを使用すると、によって、 `Export-Alias` エイリアスを表す system.string オブジェクトが返され **ます。**</span><span class="sxs-lookup"><span data-stu-id="b09d2-198">When you use the **Passthru** parameter, `Export-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="b09d2-199">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="b09d2-199">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b09d2-200">注</span><span class="sxs-lookup"><span data-stu-id="b09d2-200">NOTES</span></span>

* <span data-ttu-id="b09d2-201">Export-Aliases の結果がファイルに返されるのみです。</span><span class="sxs-lookup"><span data-stu-id="b09d2-201">You can only Export-Aliases to a file.</span></span>

## <span data-ttu-id="b09d2-202">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b09d2-202">RELATED LINKS</span></span>

[<span data-ttu-id="b09d2-203">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="b09d2-203">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="b09d2-204">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="b09d2-204">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="b09d2-205">New-Alias</span><span class="sxs-lookup"><span data-stu-id="b09d2-205">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="b09d2-206">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="b09d2-206">Set-Alias</span></span>](Set-Alias.md)
