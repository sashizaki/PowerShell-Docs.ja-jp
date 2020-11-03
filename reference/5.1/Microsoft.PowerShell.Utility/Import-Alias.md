---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-alias?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Alias
ms.openlocfilehash: f501768990c4381841fbf1402dab6cf633e7ea40
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213899"
---
# <span data-ttu-id="34aac-103">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="34aac-103">Import-Alias</span></span>

## <span data-ttu-id="34aac-104">概要</span><span class="sxs-lookup"><span data-stu-id="34aac-104">SYNOPSIS</span></span>
<span data-ttu-id="34aac-105">ファイルからエイリアス一覧をインポートします。</span><span class="sxs-lookup"><span data-stu-id="34aac-105">Imports an alias list from a file.</span></span>

## <span data-ttu-id="34aac-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="34aac-106">SYNTAX</span></span>

### <span data-ttu-id="34aac-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="34aac-107">ByPath (Default)</span></span>

```
Import-Alias [-Path] <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="34aac-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="34aac-108">ByLiteralPath</span></span>

```
Import-Alias -LiteralPath <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="34aac-109">Description</span><span class="sxs-lookup"><span data-stu-id="34aac-109">DESCRIPTION</span></span>

<span data-ttu-id="34aac-110">`Import-Alias`コマンドレットは、ファイルからエイリアス一覧をインポートします。</span><span class="sxs-lookup"><span data-stu-id="34aac-110">The `Import-Alias` cmdlet imports an alias list from a file.</span></span>

<span data-ttu-id="34aac-111">Windows PowerShell 3.0 以降では、セキュリティ機能として、 `Import-Alias` 既定で既存のエイリアスは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="34aac-111">Beginning in Windows PowerShell 3.0, as a security feature, `Import-Alias` does not overwrite existing aliases by default.</span></span>
<span data-ttu-id="34aac-112">既存のエイリアスを上書きするには、エイリアス ファイルが安全であることを確認した後で、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="34aac-112">To overwrite an existing alias, after assuring that the contents of the alias file is safe, use the **Force** parameter.</span></span>

## <span data-ttu-id="34aac-113">例</span><span class="sxs-lookup"><span data-stu-id="34aac-113">EXAMPLES</span></span>

### <span data-ttu-id="34aac-114">例 1: ファイルからエイリアスをインポートする</span><span class="sxs-lookup"><span data-stu-id="34aac-114">Example 1: Import aliases from a file</span></span>

```powershell
Import-Alias test.txt
```

<span data-ttu-id="34aac-115">このコマンドは、test.txt という名前のファイルからエイリアス情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="34aac-115">This command imports alias information from a file named test.txt.</span></span>

## <span data-ttu-id="34aac-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="34aac-116">PARAMETERS</span></span>

### <span data-ttu-id="34aac-117">-Force</span><span class="sxs-lookup"><span data-stu-id="34aac-117">-Force</span></span>

<span data-ttu-id="34aac-118">既に定義されているか、または読み取り専用になっているエイリアスをコマンドレットがインポートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="34aac-118">Allows the cmdlet to import an alias that is already defined or is read only.</span></span>
<span data-ttu-id="34aac-119">次のコマンドを使用して、現在定義されているエイリアスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="34aac-119">You can use the following command to display information about the currently-defined aliases:</span></span>

`Get-Alias | Select-Object Name, Options`

<span data-ttu-id="34aac-120">対応するエイリアスは、読み取り専用である場合、 **Options** プロパティの値に表示されます。</span><span class="sxs-lookup"><span data-stu-id="34aac-120">If the corresponding alias is read-only, it will be displayed in the value of the **Options** property.</span></span>

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

### <span data-ttu-id="34aac-121">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="34aac-121">-LiteralPath</span></span>

<span data-ttu-id="34aac-122">エクスポートされたエイリアス情報を含むファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="34aac-122">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="34aac-123">**Path** パラメーターと異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="34aac-123">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="34aac-124">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="34aac-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="34aac-125">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="34aac-125">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="34aac-126">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="34aac-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="34aac-127">-PassThru</span><span class="sxs-lookup"><span data-stu-id="34aac-127">-PassThru</span></span>

<span data-ttu-id="34aac-128">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="34aac-128">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="34aac-129">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="34aac-129">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="34aac-130">-Path</span><span class="sxs-lookup"><span data-stu-id="34aac-130">-Path</span></span>

<span data-ttu-id="34aac-131">エクスポートされたエイリアス情報を含むファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="34aac-131">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="34aac-132">ワイルドカードは許可されますが、1 つの名前に解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="34aac-132">Wildcards are allowed but they must resolve to a single name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="34aac-133">-スコープ</span><span class="sxs-lookup"><span data-stu-id="34aac-133">-Scope</span></span>

<span data-ttu-id="34aac-134">エイリアスのインポート先のスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="34aac-134">Specifies the scope into which the aliases are imported.</span></span>
<span data-ttu-id="34aac-135">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="34aac-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="34aac-136">グローバル</span><span class="sxs-lookup"><span data-stu-id="34aac-136">Global</span></span>
- <span data-ttu-id="34aac-137">ローカル</span><span class="sxs-lookup"><span data-stu-id="34aac-137">Local</span></span>
- <span data-ttu-id="34aac-138">スクリプト</span><span class="sxs-lookup"><span data-stu-id="34aac-138">Script</span></span>
- <span data-ttu-id="34aac-139">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="34aac-139">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="34aac-140">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="34aac-140">The default is Local.</span></span>
<span data-ttu-id="34aac-141">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34aac-141">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="34aac-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="34aac-142">-Confirm</span></span>

<span data-ttu-id="34aac-143">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34aac-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="34aac-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="34aac-144">-WhatIf</span></span>

<span data-ttu-id="34aac-145">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="34aac-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="34aac-146">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="34aac-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="34aac-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="34aac-147">CommonParameters</span></span>

<span data-ttu-id="34aac-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="34aac-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="34aac-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34aac-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="34aac-150">入力</span><span class="sxs-lookup"><span data-stu-id="34aac-150">INPUTS</span></span>

### <span data-ttu-id="34aac-151">System.String</span><span class="sxs-lookup"><span data-stu-id="34aac-151">System.String</span></span>

<span data-ttu-id="34aac-152">パイプを使用して、パスを含む文字列をにパイプすることができ `Import-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="34aac-152">You can pipe a string that contains a path to `Import-Alias`.</span></span>

## <span data-ttu-id="34aac-153">出力</span><span class="sxs-lookup"><span data-stu-id="34aac-153">OUTPUTS</span></span>

### <span data-ttu-id="34aac-154">None または system.servicemodel. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="34aac-154">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="34aac-155">**Passthru** パラメーターを使用すると、によって、 `Import-Alias` エイリアスを表す system.string オブジェクトが返され **ます。**</span><span class="sxs-lookup"><span data-stu-id="34aac-155">When you use the **Passthru** parameter, `Import-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="34aac-156">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="34aac-156">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="34aac-157">注</span><span class="sxs-lookup"><span data-stu-id="34aac-157">NOTES</span></span>

## <span data-ttu-id="34aac-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="34aac-158">RELATED LINKS</span></span>

[<span data-ttu-id="34aac-159">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="34aac-159">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="34aac-160">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="34aac-160">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="34aac-161">New-Alias</span><span class="sxs-lookup"><span data-stu-id="34aac-161">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="34aac-162">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="34aac-162">Set-Alias</span></span>](Set-Alias.md)
