---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 26d53ab633f5f73495a8d66012ae55dc10c5d629
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218896"
---
# <span data-ttu-id="7eaed-103">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="7eaed-103">Remove-Variable</span></span>

## <span data-ttu-id="7eaed-104">概要</span><span class="sxs-lookup"><span data-stu-id="7eaed-104">SYNOPSIS</span></span>
<span data-ttu-id="7eaed-105">変数とその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-105">Deletes a variable and its value.</span></span>

## <span data-ttu-id="7eaed-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7eaed-106">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7eaed-107">Description</span><span class="sxs-lookup"><span data-stu-id="7eaed-107">DESCRIPTION</span></span>

<span data-ttu-id="7eaed-108">`Remove-Variable`このコマンドレットは、変数とその値を、現在のセッションなど、定義されているスコープから削除します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-108">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="7eaed-109">このコマンドレットでは、定数として設定されている変数、およびシステムに所有されている変数は削除できません。</span><span class="sxs-lookup"><span data-stu-id="7eaed-109">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="7eaed-110">例</span><span class="sxs-lookup"><span data-stu-id="7eaed-110">EXAMPLES</span></span>

### <span data-ttu-id="7eaed-111">例 1: 変数を削除する</span><span class="sxs-lookup"><span data-stu-id="7eaed-111">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="7eaed-112">このコマンドは、 `$Smp` 変数を削除します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-112">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="7eaed-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7eaed-113">PARAMETERS</span></span>

### <span data-ttu-id="7eaed-114">-除外</span><span class="sxs-lookup"><span data-stu-id="7eaed-114">-Exclude</span></span>

<span data-ttu-id="7eaed-115">このコマンドレットが操作から除外する項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-115">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="7eaed-116">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-116">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="7eaed-117">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-117">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="7eaed-118">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7eaed-118">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="7eaed-119">-Force</span><span class="sxs-lookup"><span data-stu-id="7eaed-119">-Force</span></span>

<span data-ttu-id="7eaed-120">読み取り専用の場合でも、コマンドレットによって変数が削除されることを示します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-120">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="7eaed-121">**Force** パラメーターを使用しても、コマンドレットで定数を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="7eaed-121">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="7eaed-122">-Include</span><span class="sxs-lookup"><span data-stu-id="7eaed-122">-Include</span></span>

<span data-ttu-id="7eaed-123">操作内でこのコマンドレットが削除する項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-123">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="7eaed-124">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-124">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="7eaed-125">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-125">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="7eaed-126">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7eaed-126">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="7eaed-127">-Name</span><span class="sxs-lookup"><span data-stu-id="7eaed-127">-Name</span></span>

<span data-ttu-id="7eaed-128">削除する変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-128">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="7eaed-129">パラメーター名 ( **name** ) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7eaed-129">The parameter name ( **Name** ) is optional.</span></span>
<span data-ttu-id="7eaed-130">ワイルドカードを使用できます</span><span class="sxs-lookup"><span data-stu-id="7eaed-130">Wildcards are permitted</span></span>

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

### <span data-ttu-id="7eaed-131">-スコープ</span><span class="sxs-lookup"><span data-stu-id="7eaed-131">-Scope</span></span>

<span data-ttu-id="7eaed-132">指定したスコープの変数のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-132">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="7eaed-133">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7eaed-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7eaed-134">グローバル</span><span class="sxs-lookup"><span data-stu-id="7eaed-134">Global</span></span>
- <span data-ttu-id="7eaed-135">ローカル</span><span class="sxs-lookup"><span data-stu-id="7eaed-135">Local</span></span>
- <span data-ttu-id="7eaed-136">スクリプト</span><span class="sxs-lookup"><span data-stu-id="7eaed-136">Script</span></span>
- <span data-ttu-id="7eaed-137">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="7eaed-137">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="7eaed-138">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="7eaed-138">Local is the default.</span></span> <span data-ttu-id="7eaed-139">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eaed-139">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="7eaed-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7eaed-140">-Confirm</span></span>

<span data-ttu-id="7eaed-141">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7eaed-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7eaed-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7eaed-142">-WhatIf</span></span>

<span data-ttu-id="7eaed-143">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7eaed-144">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7eaed-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7eaed-145">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7eaed-145">CommonParameters</span></span>

<span data-ttu-id="7eaed-146">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7eaed-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7eaed-147">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eaed-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7eaed-148">入力</span><span class="sxs-lookup"><span data-stu-id="7eaed-148">INPUTS</span></span>

### <span data-ttu-id="7eaed-149">システム管理. PSVariable</span><span class="sxs-lookup"><span data-stu-id="7eaed-149">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="7eaed-150">パイプを使用して変数オブジェクトをにパイプすることができ `Remove-Variable` ます。</span><span class="sxs-lookup"><span data-stu-id="7eaed-150">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="7eaed-151">出力</span><span class="sxs-lookup"><span data-stu-id="7eaed-151">OUTPUTS</span></span>

### <span data-ttu-id="7eaed-152">なし</span><span class="sxs-lookup"><span data-stu-id="7eaed-152">None</span></span>

<span data-ttu-id="7eaed-153">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="7eaed-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="7eaed-154">注</span><span class="sxs-lookup"><span data-stu-id="7eaed-154">NOTES</span></span>

- <span data-ttu-id="7eaed-155">変更は、セッションなど現在のスコープにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-155">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="7eaed-156">すべてのセッションから変数を削除するには、 `Remove-Variable` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="7eaed-156">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="7eaed-157">また、組み込みエイリアスであるを参照することもでき `Remove-Variable` `rv` ます。</span><span class="sxs-lookup"><span data-stu-id="7eaed-157">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="7eaed-158">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eaed-158">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="7eaed-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7eaed-159">RELATED LINKS</span></span>

[<span data-ttu-id="7eaed-160">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="7eaed-160">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="7eaed-161">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="7eaed-161">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="7eaed-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="7eaed-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="7eaed-163">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="7eaed-163">Set-Variable</span></span>](Set-Variable.md)
