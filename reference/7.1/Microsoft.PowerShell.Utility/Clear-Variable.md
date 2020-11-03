---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: e42371a58b49a25a9aaf0cc60551ff4bf27e2ec4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217640"
---
# <span data-ttu-id="e2227-103">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="e2227-103">Clear-Variable</span></span>

## <span data-ttu-id="e2227-104">概要</span><span class="sxs-lookup"><span data-stu-id="e2227-104">SYNOPSIS</span></span>
<span data-ttu-id="e2227-105">変数の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="e2227-105">Deletes the value of a variable.</span></span>

## <span data-ttu-id="e2227-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e2227-106">SYNTAX</span></span>

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e2227-107">Description</span><span class="sxs-lookup"><span data-stu-id="e2227-107">DESCRIPTION</span></span>

<span data-ttu-id="e2227-108">**Clear variable** コマンドレットは、変数に格納されているデータを削除しますが、変数は削除しません。</span><span class="sxs-lookup"><span data-stu-id="e2227-108">The **Clear-Variable** cmdlet deletes the data stored in a variable, but it does not delete the variable.</span></span>
<span data-ttu-id="e2227-109">その結果、変数の値は NULL (空) です。</span><span class="sxs-lookup"><span data-stu-id="e2227-109">As a result, the value of the variable is NULL (empty).</span></span>
<span data-ttu-id="e2227-110">変数に指定されたデータ型またはオブジェクト型がある場合、このコマンドレットは変数に格納されているオブジェクトの型を保持します。</span><span class="sxs-lookup"><span data-stu-id="e2227-110">If the variable has a specified data or object type, this cmdlet preserves the type of the object stored in the variable.</span></span>

## <span data-ttu-id="e2227-111">例</span><span class="sxs-lookup"><span data-stu-id="e2227-111">EXAMPLES</span></span>

### <span data-ttu-id="e2227-112">例 1: 検索文字列で始まるグローバル変数の値を削除する</span><span class="sxs-lookup"><span data-stu-id="e2227-112">Example 1: Remove the value of global variables that begin with a search string</span></span>

```
PS C:\> Clear-Variable my* -Scope Global
```

<span data-ttu-id="e2227-113">このコマンドは、名前が my で始まるグローバル変数の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="e2227-113">This command removes the value of global variables that have names that begin with my.</span></span>

### <span data-ttu-id="e2227-114">例 2: 親スコープではなく、子スコープ内の変数をクリアする</span><span class="sxs-lookup"><span data-stu-id="e2227-114">Example 2: Clear a variable in a child scope but not the parent scope</span></span>

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

<span data-ttu-id="e2227-115">これらのコマンドは、子スコープ内の変数をクリアしても親スコープ内の変数はクリアされないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e2227-115">These commands demonstrate that clearing a variable in a child scope does not clear the value in the parent scope.</span></span>
<span data-ttu-id="e2227-116">最初のコマンドは、変数 $A の値を3に設定します。</span><span class="sxs-lookup"><span data-stu-id="e2227-116">The first command sets the value of the variable $A to 3.</span></span>
<span data-ttu-id="e2227-117">2番目のコマンドは、invoke 演算子 (&) を使用して、新しいスコープで **変数のクリア** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2227-117">The second command uses the invoke operator (&) to run the **Clear-Variable** command in a new scope.</span></span>
<span data-ttu-id="e2227-118">子スコープ内で (存在しない場合も) 変数がクリアされますが、ローカル スコープではクリアされません。</span><span class="sxs-lookup"><span data-stu-id="e2227-118">The variable is cleared in the child scope (although it did not exist), but it is not cleared in the local scope.</span></span>
<span data-ttu-id="e2227-119">$A の値を取得する3番目のコマンドは、値3が影響を受けないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e2227-119">The third command, which gets the value of $A, shows that the value 3 is unaffected.</span></span>

### <span data-ttu-id="e2227-120">例 3: 指定された変数の値を削除する</span><span class="sxs-lookup"><span data-stu-id="e2227-120">Example 3: Delete the value of the specified variable</span></span>

```
PS C:\> Clear-Variable -Name "Processes"
```

<span data-ttu-id="e2227-121">このコマンドは、Processes という名前の変数の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="e2227-121">This command deletes the value of the variable named Processes.</span></span>
<span data-ttu-id="e2227-122">コマンドレットによって操作が完了した後も、プロセスという名前の変数は存在しますが、値は null になります。</span><span class="sxs-lookup"><span data-stu-id="e2227-122">After the cmdlet completes the operation, the variable named Processes still exists, but the value is null.</span></span>

## <span data-ttu-id="e2227-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e2227-123">PARAMETERS</span></span>

### <span data-ttu-id="e2227-124">-除外</span><span class="sxs-lookup"><span data-stu-id="e2227-124">-Exclude</span></span>

<span data-ttu-id="e2227-125">このコマンドレットが操作で省略する項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2227-125">Specifies an array of items that this cmdlet omits in the operation.</span></span>
<span data-ttu-id="e2227-126">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="e2227-126">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="e2227-127">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2227-127">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="e2227-128">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2227-128">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="e2227-129">-Force</span><span class="sxs-lookup"><span data-stu-id="e2227-129">-Force</span></span>

<span data-ttu-id="e2227-130">読み取り専用である場合でも、コマンドレットが変数をオフにできるようにします。</span><span class="sxs-lookup"><span data-stu-id="e2227-130">Allows the cmdlet to clear a variable even if it is read-only.</span></span>
<span data-ttu-id="e2227-131">Force パラメーターを使用しても、コマンドレットは定数をクリアできません。</span><span class="sxs-lookup"><span data-stu-id="e2227-131">Even using the Force parameter, the cmdlet cannot clear constants.</span></span>

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

### <span data-ttu-id="e2227-132">-Include</span><span class="sxs-lookup"><span data-stu-id="e2227-132">-Include</span></span>

<span data-ttu-id="e2227-133">このコマンドレットによって操作に含まれる項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2227-133">Specifies an array of items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="e2227-134">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="e2227-134">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="e2227-135">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2227-135">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="e2227-136">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2227-136">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="e2227-137">-Name</span><span class="sxs-lookup"><span data-stu-id="e2227-137">-Name</span></span>

<span data-ttu-id="e2227-138">クリアする変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2227-138">Specifies the name of the variable to be cleared.</span></span>
<span data-ttu-id="e2227-139">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2227-139">Wildcards are permitted.</span></span>
<span data-ttu-id="e2227-140">このパラメーターは必須ですが、パラメーター名 ("Name") は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e2227-140">This parameter is required, but the parameter name ("Name") is optional.</span></span>

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

### <span data-ttu-id="e2227-141">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e2227-141">-PassThru</span></span>

<span data-ttu-id="e2227-142">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e2227-142">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="e2227-143">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="e2227-143">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e2227-144">-スコープ</span><span class="sxs-lookup"><span data-stu-id="e2227-144">-Scope</span></span>

<span data-ttu-id="e2227-145">このエイリアスが有効なスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2227-145">Specifies the scope in which this alias is valid.</span></span>

<span data-ttu-id="e2227-146">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e2227-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e2227-147">グローバル</span><span class="sxs-lookup"><span data-stu-id="e2227-147">Global</span></span>
- <span data-ttu-id="e2227-148">ローカル</span><span class="sxs-lookup"><span data-stu-id="e2227-148">Local</span></span>
- <span data-ttu-id="e2227-149">スクリプト</span><span class="sxs-lookup"><span data-stu-id="e2227-149">Script</span></span>

<span data-ttu-id="e2227-150">現在のスコープに対して相対的な数値 (0 ~ スコープの数) を使用することもできます。ここで、0は現在のスコープ、1はその親です。</span><span class="sxs-lookup"><span data-stu-id="e2227-150">You can also use a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>
<span data-ttu-id="e2227-151">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="e2227-151">Local is the default.</span></span>
<span data-ttu-id="e2227-152">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2227-152">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="e2227-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e2227-153">-Confirm</span></span>

<span data-ttu-id="e2227-154">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2227-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e2227-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e2227-155">-WhatIf</span></span>

<span data-ttu-id="e2227-156">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="e2227-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e2227-157">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e2227-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e2227-158">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2227-158">CommonParameters</span></span>

<span data-ttu-id="e2227-159">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e2227-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e2227-160">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2227-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e2227-161">入力</span><span class="sxs-lookup"><span data-stu-id="e2227-161">INPUTS</span></span>

### <span data-ttu-id="e2227-162">なし</span><span class="sxs-lookup"><span data-stu-id="e2227-162">None</span></span>

<span data-ttu-id="e2227-163">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e2227-163">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="e2227-164">出力</span><span class="sxs-lookup"><span data-stu-id="e2227-164">OUTPUTS</span></span>

### <span data-ttu-id="e2227-165">None または system.string です。</span><span class="sxs-lookup"><span data-stu-id="e2227-165">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="e2227-166">*PassThru* パラメーターを使用すると、このコマンドレットは、クリアされた変数を表す **system.string オブジェクトを** 生成します。</span><span class="sxs-lookup"><span data-stu-id="e2227-166">When you use the *PassThru* parameter, this cmdlet generates a **System.Management.Automation.PSVariable** object representing the cleared variable.</span></span>
<span data-ttu-id="e2227-167">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="e2227-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e2227-168">注</span><span class="sxs-lookup"><span data-stu-id="e2227-168">NOTES</span></span>

* <span data-ttu-id="e2227-169">変数を値と共に削除するには、Remove-Variable また Remove-Item を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2227-169">To delete a variable, along with its value, use Remove-Variable or Remove-Item.</span></span>

  <span data-ttu-id="e2227-170">このコマンドレットは、 *Force* パラメーターを使用した場合でも、定数またはシステムによって所有されている変数の値を削除しません。</span><span class="sxs-lookup"><span data-stu-id="e2227-170">This cmdlet does not delete the values of variables that are set as constants or owned by the system, even if you use the *Force* parameter.</span></span>

  <span data-ttu-id="e2227-171">クリアする変数が存在しない場合、コマンドレットの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="e2227-171">If the variable that you are clearing does not exist, the cmdlet has no effect.</span></span>
<span data-ttu-id="e2227-172">null 値を持つ変数は作成されません。</span><span class="sxs-lookup"><span data-stu-id="e2227-172">It does not create a variable with a null value.</span></span>

  <span data-ttu-id="e2227-173">また、 **Clear 変数** は、その組み込みエイリアスである clv を使用して参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2227-173">You can also refer to **Clear-Variable** by its built-in alias, clv.</span></span>
<span data-ttu-id="e2227-174">詳細については、「about_Aliases」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2227-174">For more information, see about_Aliases.</span></span>

*

## <span data-ttu-id="e2227-175">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e2227-175">RELATED LINKS</span></span>

[<span data-ttu-id="e2227-176">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="e2227-176">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="e2227-177">New-Variable</span><span class="sxs-lookup"><span data-stu-id="e2227-177">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="e2227-178">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="e2227-178">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="e2227-179">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="e2227-179">Set-Variable</span></span>](Set-Variable.md)

