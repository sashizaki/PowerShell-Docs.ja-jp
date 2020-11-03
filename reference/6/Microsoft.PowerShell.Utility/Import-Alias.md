---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Alias
ms.openlocfilehash: 438f089c1cd6e647ae5ee858234a3919bdc0328d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216072"
---
# <span data-ttu-id="77121-103">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="77121-103">Import-Alias</span></span>

## <span data-ttu-id="77121-104">概要</span><span class="sxs-lookup"><span data-stu-id="77121-104">SYNOPSIS</span></span>
<span data-ttu-id="77121-105">ファイルからエイリアス一覧をインポートします。</span><span class="sxs-lookup"><span data-stu-id="77121-105">Imports an alias list from a file.</span></span>

## <span data-ttu-id="77121-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77121-106">SYNTAX</span></span>

### <span data-ttu-id="77121-107">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="77121-107">ByPath (Default)</span></span>

```
Import-Alias [-Path] <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="77121-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="77121-108">ByLiteralPath</span></span>

```
Import-Alias -LiteralPath <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="77121-109">Description</span><span class="sxs-lookup"><span data-stu-id="77121-109">DESCRIPTION</span></span>

<span data-ttu-id="77121-110">`Import-Alias`コマンドレットは、ファイルからエイリアス一覧をインポートします。</span><span class="sxs-lookup"><span data-stu-id="77121-110">The `Import-Alias` cmdlet imports an alias list from a file.</span></span>

<span data-ttu-id="77121-111">Windows PowerShell 3.0 以降では、セキュリティ機能として、 `Import-Alias` 既定で既存のエイリアスは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="77121-111">Beginning in Windows PowerShell 3.0, as a security feature, `Import-Alias` does not overwrite existing aliases by default.</span></span>
<span data-ttu-id="77121-112">既存のエイリアスを上書きするには、エイリアス ファイルが安全であることを確認した後で、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="77121-112">To overwrite an existing alias, after assuring that the contents of the alias file is safe, use the **Force** parameter.</span></span>

## <span data-ttu-id="77121-113">例</span><span class="sxs-lookup"><span data-stu-id="77121-113">EXAMPLES</span></span>

### <span data-ttu-id="77121-114">例 1: ファイルからエイリアスをインポートする</span><span class="sxs-lookup"><span data-stu-id="77121-114">Example 1: Import aliases from a file</span></span>

```powershell
Import-Alias test.txt
```

<span data-ttu-id="77121-115">このコマンドは、test.txt という名前のファイルからエイリアス情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="77121-115">This command imports alias information from a file named test.txt.</span></span>

## <span data-ttu-id="77121-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77121-116">PARAMETERS</span></span>

### <span data-ttu-id="77121-117">-Force</span><span class="sxs-lookup"><span data-stu-id="77121-117">-Force</span></span>

<span data-ttu-id="77121-118">既に定義されているか、または読み取り専用になっているエイリアスをコマンドレットがインポートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="77121-118">Allows the cmdlet to import an alias that is already defined or is read only.</span></span>
<span data-ttu-id="77121-119">次のコマンドを使用して、現在定義されているエイリアスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="77121-119">You can use the following command to display information about the currently-defined aliases:</span></span>

`Get-Alias | Select-Object Name, Options`

<span data-ttu-id="77121-120">対応するエイリアスは、読み取り専用である場合、 **Options** プロパティの値に表示されます。</span><span class="sxs-lookup"><span data-stu-id="77121-120">If the corresponding alias is read-only, it will be displayed in the value of the **Options** property.</span></span>

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

### <span data-ttu-id="77121-121">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="77121-121">-LiteralPath</span></span>

<span data-ttu-id="77121-122">エクスポートされたエイリアス情報を含むファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="77121-122">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="77121-123">**Path** パラメーターと異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="77121-123">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="77121-124">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="77121-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="77121-125">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="77121-125">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="77121-126">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="77121-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="77121-127">-PassThru</span><span class="sxs-lookup"><span data-stu-id="77121-127">-PassThru</span></span>

<span data-ttu-id="77121-128">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="77121-128">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="77121-129">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="77121-129">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="77121-130">-Path</span><span class="sxs-lookup"><span data-stu-id="77121-130">-Path</span></span>

<span data-ttu-id="77121-131">エクスポートされたエイリアス情報を含むファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="77121-131">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="77121-132">ワイルドカードは許可されますが、1 つの名前に解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="77121-132">Wildcards are allowed but they must resolve to a single name.</span></span>

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

### <span data-ttu-id="77121-133">-スコープ</span><span class="sxs-lookup"><span data-stu-id="77121-133">-Scope</span></span>

<span data-ttu-id="77121-134">エイリアスのインポート先のスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="77121-134">Specifies the scope into which the aliases are imported.</span></span>
<span data-ttu-id="77121-135">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="77121-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="77121-136">グローバル</span><span class="sxs-lookup"><span data-stu-id="77121-136">Global</span></span>
- <span data-ttu-id="77121-137">ローカル</span><span class="sxs-lookup"><span data-stu-id="77121-137">Local</span></span>
- <span data-ttu-id="77121-138">スクリプト</span><span class="sxs-lookup"><span data-stu-id="77121-138">Script</span></span>
- <span data-ttu-id="77121-139">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="77121-139">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="77121-140">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="77121-140">The default is Local.</span></span>
<span data-ttu-id="77121-141">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77121-141">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="77121-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="77121-142">-Confirm</span></span>

<span data-ttu-id="77121-143">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77121-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="77121-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="77121-144">-WhatIf</span></span>

<span data-ttu-id="77121-145">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="77121-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="77121-146">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="77121-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="77121-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="77121-147">CommonParameters</span></span>

<span data-ttu-id="77121-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="77121-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="77121-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77121-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="77121-150">入力</span><span class="sxs-lookup"><span data-stu-id="77121-150">INPUTS</span></span>

### <span data-ttu-id="77121-151">System.String</span><span class="sxs-lookup"><span data-stu-id="77121-151">System.String</span></span>

<span data-ttu-id="77121-152">パイプを使用して、パスを含む文字列をにパイプすることができ `Import-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="77121-152">You can pipe a string that contains a path to `Import-Alias`.</span></span>

## <span data-ttu-id="77121-153">出力</span><span class="sxs-lookup"><span data-stu-id="77121-153">OUTPUTS</span></span>

### <span data-ttu-id="77121-154">None または system.servicemodel. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="77121-154">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="77121-155">**Passthru** パラメーターを使用すると、によって、 `Import-Alias` エイリアスを表す system.string オブジェクトが返され **ます。**</span><span class="sxs-lookup"><span data-stu-id="77121-155">When you use the **Passthru** parameter, `Import-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="77121-156">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="77121-156">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="77121-157">注</span><span class="sxs-lookup"><span data-stu-id="77121-157">NOTES</span></span>

## <span data-ttu-id="77121-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="77121-158">RELATED LINKS</span></span>

[<span data-ttu-id="77121-159">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="77121-159">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="77121-160">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="77121-160">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="77121-161">New-Alias</span><span class="sxs-lookup"><span data-stu-id="77121-161">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="77121-162">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="77121-162">Set-Alias</span></span>](Set-Alias.md)
