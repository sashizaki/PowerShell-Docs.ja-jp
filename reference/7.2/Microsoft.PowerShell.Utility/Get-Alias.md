---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Alias
ms.openlocfilehash: 7b6f639d1c5685e341260c056a1dd0a17fe9f46d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600092"
---
# <span data-ttu-id="9612c-102">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="9612c-102">Get-Alias</span></span>

## <span data-ttu-id="9612c-103">概要</span><span class="sxs-lookup"><span data-stu-id="9612c-103">SYNOPSIS</span></span>
<span data-ttu-id="9612c-104">現在のセッションのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-104">Gets the aliases for the current session.</span></span>

## <span data-ttu-id="9612c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9612c-105">SYNTAX</span></span>

### <span data-ttu-id="9612c-106">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="9612c-106">Default (Default)</span></span>

```
Get-Alias [[-Name] <String[]>] [-Exclude <String[]>] [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="9612c-107">定義</span><span class="sxs-lookup"><span data-stu-id="9612c-107">Definition</span></span>

```
Get-Alias [-Exclude <String[]>] [-Scope <String>] [-Definition <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="9612c-108">Description</span><span class="sxs-lookup"><span data-stu-id="9612c-108">DESCRIPTION</span></span>

<span data-ttu-id="9612c-109">**Get Alias** コマンドレットは、現在のセッションのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-109">The **Get-Alias** cmdlet gets the aliases in the current session.</span></span>
<span data-ttu-id="9612c-110">これには、組み込みエイリアス、設定またはインポートしたエイリアス、および PowerShell プロファイルに追加したエイリアスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9612c-110">This includes built-in aliases, aliases that you have set or imported, and aliases that you have added to your PowerShell profile.</span></span>

<span data-ttu-id="9612c-111">既定では、 **Get エイリアス** はエイリアスを受け取り、コマンド名を返します。</span><span class="sxs-lookup"><span data-stu-id="9612c-111">By default, **Get-Alias** takes an alias and returns the command name.</span></span>
<span data-ttu-id="9612c-112">*定義* パラメーターを使用すると、 **Get エイリアス** はコマンド名を受け取り、そのエイリアスを返します。</span><span class="sxs-lookup"><span data-stu-id="9612c-112">When you use the *Definition* parameter, **Get-Alias** takes a command name and returns its aliases.</span></span>

<span data-ttu-id="9612c-113">Windows PowerShell 3.0 以降では、必要な情報を簡単に見つけられるように、 **Get エイリアス** によって、ハイフンではないエイリアス名が形式で表示され `<alias> -> <definition>` ます。</span><span class="sxs-lookup"><span data-stu-id="9612c-113">Beginning in Windows PowerShell 3.0, **Get-Alias** displays non-hyphenated alias names in an `<alias> -> <definition>` format to make it even easier to find the information that you need.</span></span>

## <span data-ttu-id="9612c-114">例</span><span class="sxs-lookup"><span data-stu-id="9612c-114">EXAMPLES</span></span>

### <span data-ttu-id="9612c-115">例 1: 現在のセッションのすべてのエイリアスを取得する</span><span class="sxs-lookup"><span data-stu-id="9612c-115">Example 1: Get all aliases in the current session</span></span>

```
PS C:\> Get-Alias

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
...
```

<span data-ttu-id="9612c-116">このコマンドは、現在のセッションのすべてのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-116">This command gets all aliases in the current session.</span></span>

<span data-ttu-id="9612c-117">出力には、 `<alias> -> <definition>` Windows PowerShell 3.0 で導入された形式が示されています。</span><span class="sxs-lookup"><span data-stu-id="9612c-117">The output shows the `<alias> -> <definition>` format that was introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="9612c-118">通常、ハイフン付きのエイリアスは、ニックネームの代わりに、コマンドレットと関数の推奨される名前になるため、この形式はハイフンを含まないエイリアスのみに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9612c-118">This format is used only for aliases that do not include hyphens, because aliases with hyphens are typically preferred names for cmdlets and functions, rather than nicknames.</span></span>

### <span data-ttu-id="9612c-119">例 2: 名前を指定してエイリアスを取得する</span><span class="sxs-lookup"><span data-stu-id="9612c-119">Example 2: Get aliases by name</span></span>

```powershell
Get-Alias -Name gp*, sp* -Exclude *ps
```

<span data-ttu-id="9612c-120">このコマンドは、gp または sp で始まるすべてのエイリアスを取得します。ただし、末尾が ps であるエイリアスは除きます。</span><span class="sxs-lookup"><span data-stu-id="9612c-120">This command gets all aliases that begin with gp or sp, except for aliases that end with ps.</span></span>

### <span data-ttu-id="9612c-121">例 3: コマンドレットのエイリアスを取得する</span><span class="sxs-lookup"><span data-stu-id="9612c-121">Example 3: Get aliases for a cmdlet</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

<span data-ttu-id="9612c-122">このコマンドは、Get-ChildItem コマンドレットのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-122">This command gets the aliases for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="9612c-123">既定では、 **Get alias** コマンドレットは、エイリアスがわかっている場合に項目名を取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-123">By default, the **Get-Alias** cmdlet gets the item name when you know the alias.</span></span>
<span data-ttu-id="9612c-124">*定義* パラメーターは、項目名がわかっている場合にエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-124">The *Definition* parameter gets the alias when you know the item name.</span></span>

### <span data-ttu-id="9612c-125">例 4: プロパティによってエイリアスを取得する</span><span class="sxs-lookup"><span data-stu-id="9612c-125">Example 4: Get aliases by property</span></span>

```powershell
Get-Alias | Where-Object {$_.Options -Match "ReadOnly"}
```

<span data-ttu-id="9612c-126">このコマンドは、Options プロパティの値が ReadOnly であるすべてのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-126">This command gets all aliases in which the value of the Options property is ReadOnly.</span></span>
<span data-ttu-id="9612c-127">このコマンドは、ReadOnly オプションがあるため、PowerShell に組み込まれているエイリアスを簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="9612c-127">This command provides a quick way to find the aliases that are built into PowerShell, because they have the ReadOnly option.</span></span>

<span data-ttu-id="9612c-128">Options は、 **エイリアス** が取得する別名情報オブジェクトの1つのプロパティにすぎません。</span><span class="sxs-lookup"><span data-stu-id="9612c-128">Options is just one property of the AliasInfo objects that **Get-Alias** gets.</span></span>
<span data-ttu-id="9612c-129">エイリアス情報オブジェクトのすべてのプロパティとメソッドを検索するには、「」と入力 `Get-Alias | get-member` します。</span><span class="sxs-lookup"><span data-stu-id="9612c-129">To find all properties and methods of AliasInfo objects, type `Get-Alias | get-member`.</span></span>

### <span data-ttu-id="9612c-130">例 5: 名前でエイリアスを取得し、文字の先頭でフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="9612c-130">Example 5: Get aliases by name and filter by beginning letter</span></span>

```powershell
Get-Alias -Definition "*-PSSession" -Exclude e* -Scope Global
```

<span data-ttu-id="9612c-131">この例では、"e" で始まるエイリアスを除き、"-PSSession" で終わる名前を持つコマンドのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-131">This example gets aliases for commands that have names that end in "-PSSession", except for those that begin with "e".</span></span>

<span data-ttu-id="9612c-132">このコマンドは、 *scope* パラメーターを使用して、グローバルスコープでコマンドを適用します。</span><span class="sxs-lookup"><span data-stu-id="9612c-132">The command uses the *Scope* parameter to apply the command in the global scope.</span></span>
<span data-ttu-id="9612c-133">これは、セッション内のエイリアスを取得するときに、スクリプトで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9612c-133">This is useful in scripts when you want to get the aliases in the session.</span></span>

## <span data-ttu-id="9612c-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9612c-134">PARAMETERS</span></span>

### <span data-ttu-id="9612c-135">-Definition</span><span class="sxs-lookup"><span data-stu-id="9612c-135">-Definition</span></span>

<span data-ttu-id="9612c-136">指定した項目のエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-136">Gets the aliases for the specified item.</span></span>
<span data-ttu-id="9612c-137">コマンドレット、関数、スクリプト、ファイル、または実行可能ファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9612c-137">Enter the name of a cmdlet, function, script, file, or executable file.</span></span>

<span data-ttu-id="9612c-138">このパラメーターは、エイリアスオブジェクトの Definition プロパティで項目名を検索するため、 *定義* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9612c-138">This parameter is called *Definition*, because it searches for the item name in the Definition property of the alias object.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Definition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9612c-139">-除外</span><span class="sxs-lookup"><span data-stu-id="9612c-139">-Exclude</span></span>

<span data-ttu-id="9612c-140">指定した項目を除外します。</span><span class="sxs-lookup"><span data-stu-id="9612c-140">Omits the specified items.</span></span>
<span data-ttu-id="9612c-141">このパラメーターの値は、Name パラメーターと Definition パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9612c-141">The value of this parameter qualifies the Name and Definition parameters.</span></span>
<span data-ttu-id="9612c-142">名前、要素、または「s\*」のようなパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="9612c-142">Enter a name, a definition, or a pattern, such as "s\*".</span></span>
<span data-ttu-id="9612c-143">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9612c-143">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="9612c-144">-Name</span><span class="sxs-lookup"><span data-stu-id="9612c-144">-Name</span></span>

<span data-ttu-id="9612c-145">このコマンドレットが取得するエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9612c-145">Specifies the aliases that this cmdlet gets.</span></span>
<span data-ttu-id="9612c-146">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9612c-146">Wildcards are permitted.</span></span>
<span data-ttu-id="9612c-147">既定では、は、 `Get-Alias` 現在のセッションに対して定義されているすべてのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9612c-147">By default, `Get-Alias` retrieves all aliases defined for the current session.</span></span>
<span data-ttu-id="9612c-148">パラメーター **名は省略可能です。**</span><span class="sxs-lookup"><span data-stu-id="9612c-148">The parameter name **Name** is optional.</span></span>
<span data-ttu-id="9612c-149">パイプを使用してエイリアス名をにパイプすることもでき `Get-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="9612c-149">You can also pipe alias names to `Get-Alias`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: All aliases
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="9612c-150">-スコープ</span><span class="sxs-lookup"><span data-stu-id="9612c-150">-Scope</span></span>

<span data-ttu-id="9612c-151">このコマンドレットがエイリアスを取得するスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="9612c-151">Specifies the scope for which this cmdlet gets aliases.</span></span>
<span data-ttu-id="9612c-152">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9612c-152">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9612c-153">グローバル</span><span class="sxs-lookup"><span data-stu-id="9612c-153">Global</span></span>
- <span data-ttu-id="9612c-154">ローカル</span><span class="sxs-lookup"><span data-stu-id="9612c-154">Local</span></span>
- <span data-ttu-id="9612c-155">スクリプト</span><span class="sxs-lookup"><span data-stu-id="9612c-155">Script</span></span>
- <span data-ttu-id="9612c-156">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="9612c-156">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="9612c-157">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="9612c-157">Local is the default.</span></span>
<span data-ttu-id="9612c-158">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9612c-158">For more information, see about_Scopes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9612c-159">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9612c-159">CommonParameters</span></span>

<span data-ttu-id="9612c-160">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9612c-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9612c-161">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9612c-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9612c-162">入力</span><span class="sxs-lookup"><span data-stu-id="9612c-162">INPUTS</span></span>

### <span data-ttu-id="9612c-163">System.String</span><span class="sxs-lookup"><span data-stu-id="9612c-163">System.String</span></span>

<span data-ttu-id="9612c-164">パイプを使用してエイリアス名を **取得** することができます。</span><span class="sxs-lookup"><span data-stu-id="9612c-164">You can pipe alias names to **Get-Alias**.</span></span>

## <span data-ttu-id="9612c-165">出力</span><span class="sxs-lookup"><span data-stu-id="9612c-165">OUTPUTS</span></span>

### <span data-ttu-id="9612c-166">システム管理. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="9612c-166">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="9612c-167">**Get エイリアス** は、各エイリアスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9612c-167">**Get-Alias** returns an object that represents each alias.</span></span>
<span data-ttu-id="9612c-168">**Get エイリアス** はすべてのエイリアスに対して同じオブジェクトを返しますが、PowerShell は矢印ベースの形式を使用して、ハイフンではないエイリアスの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="9612c-168">**Get-Alias** returns the same object for every alias, but PowerShell uses an arrow-based format to display the names of non-hyphenated aliases.</span></span>

## <span data-ttu-id="9612c-169">注</span><span class="sxs-lookup"><span data-stu-id="9612c-169">NOTES</span></span>

- <span data-ttu-id="9612c-170">新しいエイリアスを作成するには、Set-Alias または New-Alias を使用します。</span><span class="sxs-lookup"><span data-stu-id="9612c-170">To create a new alias, use Set-Alias or New-Alias.</span></span> <span data-ttu-id="9612c-171">エイリアスを削除するには、Remove-Item を使用します。</span><span class="sxs-lookup"><span data-stu-id="9612c-171">To delete an alias, use Remove-Item.</span></span>
- <span data-ttu-id="9612c-172">矢印に基づくエイリアス名の形式は、ハイフンを含むエイリアスには使用されません。</span><span class="sxs-lookup"><span data-stu-id="9612c-172">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="9612c-173">これらは、一般的な省略形またはニックネームの代わりに、コマンドレットと関数の推奨される代替名となる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="9612c-173">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames.</span></span>

## <span data-ttu-id="9612c-174">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9612c-174">RELATED LINKS</span></span>

[<span data-ttu-id="9612c-175">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="9612c-175">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="9612c-176">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="9612c-176">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="9612c-177">New-Alias</span><span class="sxs-lookup"><span data-stu-id="9612c-177">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="9612c-178">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="9612c-178">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="9612c-179">エイリアス プロバイダー</span><span class="sxs-lookup"><span data-stu-id="9612c-179">Alias Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)

[<span data-ttu-id="9612c-180">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="9612c-180">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

