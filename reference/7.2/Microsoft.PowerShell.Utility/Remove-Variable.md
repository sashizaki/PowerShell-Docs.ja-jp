---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 6b9d351b5092d96d7698a28d3de63a493d566c6d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603045"
---
# <span data-ttu-id="06647-102">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="06647-102">Remove-Variable</span></span>

## <span data-ttu-id="06647-103">概要</span><span class="sxs-lookup"><span data-stu-id="06647-103">SYNOPSIS</span></span>
<span data-ttu-id="06647-104">変数とその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="06647-104">Deletes a variable and its value.</span></span>

## <span data-ttu-id="06647-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="06647-105">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="06647-106">Description</span><span class="sxs-lookup"><span data-stu-id="06647-106">DESCRIPTION</span></span>

<span data-ttu-id="06647-107">`Remove-Variable`このコマンドレットは、変数とその値を、現在のセッションなど、定義されているスコープから削除します。</span><span class="sxs-lookup"><span data-stu-id="06647-107">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="06647-108">このコマンドレットでは、定数として設定されている変数、およびシステムに所有されている変数は削除できません。</span><span class="sxs-lookup"><span data-stu-id="06647-108">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="06647-109">例</span><span class="sxs-lookup"><span data-stu-id="06647-109">EXAMPLES</span></span>

### <span data-ttu-id="06647-110">例 1: 変数を削除する</span><span class="sxs-lookup"><span data-stu-id="06647-110">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="06647-111">このコマンドは、 `$Smp` 変数を削除します。</span><span class="sxs-lookup"><span data-stu-id="06647-111">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="06647-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="06647-112">PARAMETERS</span></span>

### <span data-ttu-id="06647-113">-除外</span><span class="sxs-lookup"><span data-stu-id="06647-113">-Exclude</span></span>

<span data-ttu-id="06647-114">このコマンドレットが操作から除外する項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="06647-114">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="06647-115">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="06647-115">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="06647-116">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="06647-116">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="06647-117">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="06647-117">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="06647-118">-Force</span><span class="sxs-lookup"><span data-stu-id="06647-118">-Force</span></span>

<span data-ttu-id="06647-119">読み取り専用の場合でも、コマンドレットによって変数が削除されることを示します。</span><span class="sxs-lookup"><span data-stu-id="06647-119">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="06647-120">**Force** パラメーターを使用しても、コマンドレットで定数を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="06647-120">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="06647-121">-Include</span><span class="sxs-lookup"><span data-stu-id="06647-121">-Include</span></span>

<span data-ttu-id="06647-122">操作内でこのコマンドレットが削除する項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="06647-122">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="06647-123">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="06647-123">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="06647-124">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="06647-124">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="06647-125">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="06647-125">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="06647-126">-Name</span><span class="sxs-lookup"><span data-stu-id="06647-126">-Name</span></span>

<span data-ttu-id="06647-127">削除する変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="06647-127">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="06647-128">パラメーター名 (**name**) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="06647-128">The parameter name (**Name**) is optional.</span></span>
<span data-ttu-id="06647-129">ワイルドカードを使用できます</span><span class="sxs-lookup"><span data-stu-id="06647-129">Wildcards are permitted</span></span>

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

### <span data-ttu-id="06647-130">-スコープ</span><span class="sxs-lookup"><span data-stu-id="06647-130">-Scope</span></span>

<span data-ttu-id="06647-131">指定したスコープの変数のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="06647-131">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="06647-132">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06647-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="06647-133">グローバル</span><span class="sxs-lookup"><span data-stu-id="06647-133">Global</span></span>
- <span data-ttu-id="06647-134">ローカル</span><span class="sxs-lookup"><span data-stu-id="06647-134">Local</span></span>
- <span data-ttu-id="06647-135">スクリプト</span><span class="sxs-lookup"><span data-stu-id="06647-135">Script</span></span>
- <span data-ttu-id="06647-136">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="06647-136">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="06647-137">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="06647-137">Local is the default.</span></span> <span data-ttu-id="06647-138">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06647-138">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="06647-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="06647-139">-Confirm</span></span>

<span data-ttu-id="06647-140">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06647-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="06647-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="06647-141">-WhatIf</span></span>

<span data-ttu-id="06647-142">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="06647-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="06647-143">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="06647-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="06647-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="06647-144">CommonParameters</span></span>

<span data-ttu-id="06647-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="06647-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="06647-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06647-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="06647-147">入力</span><span class="sxs-lookup"><span data-stu-id="06647-147">INPUTS</span></span>

### <span data-ttu-id="06647-148">システム管理. PSVariable</span><span class="sxs-lookup"><span data-stu-id="06647-148">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="06647-149">パイプを使用して変数オブジェクトをにパイプすることができ `Remove-Variable` ます。</span><span class="sxs-lookup"><span data-stu-id="06647-149">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="06647-150">出力</span><span class="sxs-lookup"><span data-stu-id="06647-150">OUTPUTS</span></span>

### <span data-ttu-id="06647-151">なし</span><span class="sxs-lookup"><span data-stu-id="06647-151">None</span></span>

<span data-ttu-id="06647-152">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="06647-152">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="06647-153">注</span><span class="sxs-lookup"><span data-stu-id="06647-153">NOTES</span></span>

- <span data-ttu-id="06647-154">変更は、セッションなど現在のスコープにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="06647-154">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="06647-155">すべてのセッションから変数を削除するには、 `Remove-Variable` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="06647-155">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="06647-156">また、組み込みエイリアスであるを参照することもでき `Remove-Variable` `rv` ます。</span><span class="sxs-lookup"><span data-stu-id="06647-156">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="06647-157">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06647-157">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="06647-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="06647-158">RELATED LINKS</span></span>

[<span data-ttu-id="06647-159">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="06647-159">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="06647-160">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="06647-160">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="06647-161">New-Variable</span><span class="sxs-lookup"><span data-stu-id="06647-161">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="06647-162">変数の設定</span><span class="sxs-lookup"><span data-stu-id="06647-162">Set-Variable</span></span>](Set-Variable.md)
