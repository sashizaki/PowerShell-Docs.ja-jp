---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 2e0e9388c592cb83dd7609fed663ae220e380750
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218891"
---
# <span data-ttu-id="6528b-103">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="6528b-103">Remove-Variable</span></span>

## <span data-ttu-id="6528b-104">概要</span><span class="sxs-lookup"><span data-stu-id="6528b-104">SYNOPSIS</span></span>
<span data-ttu-id="6528b-105">変数とその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="6528b-105">Deletes a variable and its value.</span></span>

## <span data-ttu-id="6528b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6528b-106">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6528b-107">Description</span><span class="sxs-lookup"><span data-stu-id="6528b-107">DESCRIPTION</span></span>

<span data-ttu-id="6528b-108">`Remove-Variable`このコマンドレットは、変数とその値を、現在のセッションなど、定義されているスコープから削除します。</span><span class="sxs-lookup"><span data-stu-id="6528b-108">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="6528b-109">このコマンドレットでは、定数として設定されている変数、およびシステムに所有されている変数は削除できません。</span><span class="sxs-lookup"><span data-stu-id="6528b-109">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="6528b-110">例</span><span class="sxs-lookup"><span data-stu-id="6528b-110">EXAMPLES</span></span>

### <span data-ttu-id="6528b-111">例 1: 変数を削除する</span><span class="sxs-lookup"><span data-stu-id="6528b-111">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="6528b-112">このコマンドは、 `$Smp` 変数を削除します。</span><span class="sxs-lookup"><span data-stu-id="6528b-112">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="6528b-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6528b-113">PARAMETERS</span></span>

### <span data-ttu-id="6528b-114">-除外</span><span class="sxs-lookup"><span data-stu-id="6528b-114">-Exclude</span></span>

<span data-ttu-id="6528b-115">このコマンドレットが操作から除外する項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6528b-115">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="6528b-116">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="6528b-116">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="6528b-117">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="6528b-117">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="6528b-118">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6528b-118">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="6528b-119">-Force</span><span class="sxs-lookup"><span data-stu-id="6528b-119">-Force</span></span>

<span data-ttu-id="6528b-120">読み取り専用の場合でも、コマンドレットによって変数が削除されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6528b-120">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="6528b-121">**Force** パラメーターを使用しても、コマンドレットで定数を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="6528b-121">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="6528b-122">-Include</span><span class="sxs-lookup"><span data-stu-id="6528b-122">-Include</span></span>

<span data-ttu-id="6528b-123">操作内でこのコマンドレットが削除する項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6528b-123">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="6528b-124">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="6528b-124">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="6528b-125">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="6528b-125">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="6528b-126">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6528b-126">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="6528b-127">-Name</span><span class="sxs-lookup"><span data-stu-id="6528b-127">-Name</span></span>

<span data-ttu-id="6528b-128">削除する変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6528b-128">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="6528b-129">パラメーター名 ( **name** ) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6528b-129">The parameter name ( **Name** ) is optional.</span></span>
<span data-ttu-id="6528b-130">ワイルドカードを使用できます</span><span class="sxs-lookup"><span data-stu-id="6528b-130">Wildcards are permitted</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="6528b-131">-スコープ</span><span class="sxs-lookup"><span data-stu-id="6528b-131">-Scope</span></span>

<span data-ttu-id="6528b-132">指定したスコープの変数のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="6528b-132">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="6528b-133">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6528b-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6528b-134">グローバル</span><span class="sxs-lookup"><span data-stu-id="6528b-134">Global</span></span>
- <span data-ttu-id="6528b-135">ローカル</span><span class="sxs-lookup"><span data-stu-id="6528b-135">Local</span></span>
- <span data-ttu-id="6528b-136">スクリプト</span><span class="sxs-lookup"><span data-stu-id="6528b-136">Script</span></span>
- <span data-ttu-id="6528b-137">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="6528b-137">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="6528b-138">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="6528b-138">Local is the default.</span></span> <span data-ttu-id="6528b-139">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6528b-139">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="6528b-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6528b-140">-Confirm</span></span>

<span data-ttu-id="6528b-141">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6528b-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6528b-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6528b-142">-WhatIf</span></span>

<span data-ttu-id="6528b-143">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="6528b-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6528b-144">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="6528b-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6528b-145">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6528b-145">CommonParameters</span></span>

<span data-ttu-id="6528b-146">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6528b-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6528b-147">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6528b-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6528b-148">入力</span><span class="sxs-lookup"><span data-stu-id="6528b-148">INPUTS</span></span>

### <span data-ttu-id="6528b-149">システム管理. PSVariable</span><span class="sxs-lookup"><span data-stu-id="6528b-149">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="6528b-150">パイプを使用して変数オブジェクトをにパイプすることができ `Remove-Variable` ます。</span><span class="sxs-lookup"><span data-stu-id="6528b-150">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="6528b-151">出力</span><span class="sxs-lookup"><span data-stu-id="6528b-151">OUTPUTS</span></span>

### <span data-ttu-id="6528b-152">なし</span><span class="sxs-lookup"><span data-stu-id="6528b-152">None</span></span>

<span data-ttu-id="6528b-153">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="6528b-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="6528b-154">注</span><span class="sxs-lookup"><span data-stu-id="6528b-154">NOTES</span></span>

- <span data-ttu-id="6528b-155">変更は、セッションなど現在のスコープにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="6528b-155">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="6528b-156">すべてのセッションから変数を削除するには、 `Remove-Variable` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="6528b-156">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="6528b-157">また、組み込みエイリアスであるを参照することもでき `Remove-Variable` `rv` ます。</span><span class="sxs-lookup"><span data-stu-id="6528b-157">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="6528b-158">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6528b-158">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="6528b-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6528b-159">RELATED LINKS</span></span>

[<span data-ttu-id="6528b-160">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="6528b-160">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="6528b-161">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="6528b-161">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="6528b-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="6528b-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="6528b-163">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="6528b-163">Set-Variable</span></span>](Set-Variable.md)