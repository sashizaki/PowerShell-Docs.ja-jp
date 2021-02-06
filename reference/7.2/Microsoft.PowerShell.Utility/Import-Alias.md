---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Alias
ms.openlocfilehash: 20bc5d141b68cab19374afbe44b3472c72bf69bc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601793"
---
# <span data-ttu-id="a48a4-102">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="a48a4-102">Import-Alias</span></span>

## <span data-ttu-id="a48a4-103">概要</span><span class="sxs-lookup"><span data-stu-id="a48a4-103">SYNOPSIS</span></span>
<span data-ttu-id="a48a4-104">ファイルからエイリアス一覧をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a48a4-104">Imports an alias list from a file.</span></span>

## <span data-ttu-id="a48a4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a48a4-105">SYNTAX</span></span>

### <span data-ttu-id="a48a4-106">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="a48a4-106">ByPath (Default)</span></span>

```
Import-Alias [-Path] <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a48a4-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="a48a4-107">ByLiteralPath</span></span>

```
Import-Alias -LiteralPath <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="a48a4-108">Description</span><span class="sxs-lookup"><span data-stu-id="a48a4-108">DESCRIPTION</span></span>

<span data-ttu-id="a48a4-109">`Import-Alias`コマンドレットは、ファイルからエイリアス一覧をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a48a4-109">The `Import-Alias` cmdlet imports an alias list from a file.</span></span>

<span data-ttu-id="a48a4-110">Windows PowerShell 3.0 以降では、セキュリティ機能として、 `Import-Alias` 既定で既存のエイリアスは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="a48a4-110">Beginning in Windows PowerShell 3.0, as a security feature, `Import-Alias` does not overwrite existing aliases by default.</span></span>
<span data-ttu-id="a48a4-111">既存のエイリアスを上書きするには、エイリアス ファイルが安全であることを確認した後で、**Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a48a4-111">To overwrite an existing alias, after assuring that the contents of the alias file is safe, use the **Force** parameter.</span></span>

## <span data-ttu-id="a48a4-112">例</span><span class="sxs-lookup"><span data-stu-id="a48a4-112">EXAMPLES</span></span>

### <span data-ttu-id="a48a4-113">例 1: ファイルからエイリアスをインポートする</span><span class="sxs-lookup"><span data-stu-id="a48a4-113">Example 1: Import aliases from a file</span></span>

```powershell
Import-Alias test.txt
```

<span data-ttu-id="a48a4-114">このコマンドは、test.txt という名前のファイルからエイリアス情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a48a4-114">This command imports alias information from a file named test.txt.</span></span>

## <span data-ttu-id="a48a4-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a48a4-115">PARAMETERS</span></span>

### <span data-ttu-id="a48a4-116">-Force</span><span class="sxs-lookup"><span data-stu-id="a48a4-116">-Force</span></span>

<span data-ttu-id="a48a4-117">既に定義されているか、または読み取り専用になっているエイリアスをコマンドレットがインポートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a48a4-117">Allows the cmdlet to import an alias that is already defined or is read only.</span></span>
<span data-ttu-id="a48a4-118">次のコマンドを使用して、現在定義されているエイリアスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a48a4-118">You can use the following command to display information about the currently-defined aliases:</span></span>

`Get-Alias | Select-Object Name, Options`

<span data-ttu-id="a48a4-119">対応するエイリアスは、読み取り専用である場合、**Options** プロパティの値に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a48a4-119">If the corresponding alias is read-only, it will be displayed in the value of the **Options** property.</span></span>

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

### <span data-ttu-id="a48a4-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a48a4-120">-LiteralPath</span></span>

<span data-ttu-id="a48a4-121">エクスポートされたエイリアス情報を含むファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a48a4-121">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="a48a4-122">**Path** パラメーターと異なり、**LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a48a4-122">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="a48a4-123">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="a48a4-123">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="a48a4-124">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a48a4-124">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="a48a4-125">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="a48a4-125">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="a48a4-126">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a48a4-126">-PassThru</span></span>

<span data-ttu-id="a48a4-127">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a48a4-127">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="a48a4-128">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a48a4-128">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a48a4-129">-Path</span><span class="sxs-lookup"><span data-stu-id="a48a4-129">-Path</span></span>

<span data-ttu-id="a48a4-130">エクスポートされたエイリアス情報を含むファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a48a4-130">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="a48a4-131">ワイルドカードは許可されますが、1 つの名前に解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="a48a4-131">Wildcards are allowed but they must resolve to a single name.</span></span>

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

### <span data-ttu-id="a48a4-132">-スコープ</span><span class="sxs-lookup"><span data-stu-id="a48a4-132">-Scope</span></span>

<span data-ttu-id="a48a4-133">エイリアスのインポート先のスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="a48a4-133">Specifies the scope into which the aliases are imported.</span></span>
<span data-ttu-id="a48a4-134">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a48a4-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a48a4-135">グローバル</span><span class="sxs-lookup"><span data-stu-id="a48a4-135">Global</span></span>
- <span data-ttu-id="a48a4-136">ローカル</span><span class="sxs-lookup"><span data-stu-id="a48a4-136">Local</span></span>
- <span data-ttu-id="a48a4-137">スクリプト</span><span class="sxs-lookup"><span data-stu-id="a48a4-137">Script</span></span>
- <span data-ttu-id="a48a4-138">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="a48a4-138">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="a48a4-139">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="a48a4-139">The default is Local.</span></span>
<span data-ttu-id="a48a4-140">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a48a4-140">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="a48a4-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a48a4-141">-Confirm</span></span>

<span data-ttu-id="a48a4-142">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a48a4-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a48a4-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a48a4-143">-WhatIf</span></span>

<span data-ttu-id="a48a4-144">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a48a4-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a48a4-145">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a48a4-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a48a4-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a48a4-146">CommonParameters</span></span>

<span data-ttu-id="a48a4-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a48a4-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a48a4-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a48a4-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a48a4-149">入力</span><span class="sxs-lookup"><span data-stu-id="a48a4-149">INPUTS</span></span>

### <span data-ttu-id="a48a4-150">System.String</span><span class="sxs-lookup"><span data-stu-id="a48a4-150">System.String</span></span>

<span data-ttu-id="a48a4-151">パイプを使用して、パスを含む文字列をにパイプすることができ `Import-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="a48a4-151">You can pipe a string that contains a path to `Import-Alias`.</span></span>

## <span data-ttu-id="a48a4-152">出力</span><span class="sxs-lookup"><span data-stu-id="a48a4-152">OUTPUTS</span></span>

### <span data-ttu-id="a48a4-153">None または system.servicemodel. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="a48a4-153">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="a48a4-154">**Passthru** パラメーターを使用すると、によって、 `Import-Alias` エイリアスを表す system.string オブジェクトが返され **ます。**</span><span class="sxs-lookup"><span data-stu-id="a48a4-154">When you use the **Passthru** parameter, `Import-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="a48a4-155">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a48a4-155">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a48a4-156">注</span><span class="sxs-lookup"><span data-stu-id="a48a4-156">NOTES</span></span>

## <span data-ttu-id="a48a4-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a48a4-157">RELATED LINKS</span></span>

[<span data-ttu-id="a48a4-158">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="a48a4-158">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="a48a4-159">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="a48a4-159">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="a48a4-160">New-Alias</span><span class="sxs-lookup"><span data-stu-id="a48a4-160">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="a48a4-161">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="a48a4-161">Set-Alias</span></span>](Set-Alias.md)

