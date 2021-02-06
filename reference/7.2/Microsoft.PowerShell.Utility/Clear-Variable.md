---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: 0381b48097f75d3195a82a67225cd8d6759e7433
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600095"
---
# <span data-ttu-id="1abb5-102">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="1abb5-102">Clear-Variable</span></span>

## <span data-ttu-id="1abb5-103">概要</span><span class="sxs-lookup"><span data-stu-id="1abb5-103">SYNOPSIS</span></span>
<span data-ttu-id="1abb5-104">変数の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-104">Deletes the value of a variable.</span></span>

## <span data-ttu-id="1abb5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1abb5-105">SYNTAX</span></span>

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1abb5-106">Description</span><span class="sxs-lookup"><span data-stu-id="1abb5-106">DESCRIPTION</span></span>

<span data-ttu-id="1abb5-107">**Clear variable** コマンドレットは、変数に格納されているデータを削除しますが、変数は削除しません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-107">The **Clear-Variable** cmdlet deletes the data stored in a variable, but it does not delete the variable.</span></span>
<span data-ttu-id="1abb5-108">その結果、変数の値は NULL (空) です。</span><span class="sxs-lookup"><span data-stu-id="1abb5-108">As a result, the value of the variable is NULL (empty).</span></span>
<span data-ttu-id="1abb5-109">変数に指定されたデータ型またはオブジェクト型がある場合、このコマンドレットは変数に格納されているオブジェクトの型を保持します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-109">If the variable has a specified data or object type, this cmdlet preserves the type of the object stored in the variable.</span></span>

## <span data-ttu-id="1abb5-110">例</span><span class="sxs-lookup"><span data-stu-id="1abb5-110">EXAMPLES</span></span>

### <span data-ttu-id="1abb5-111">例 1: 検索文字列で始まるグローバル変数の値を削除する</span><span class="sxs-lookup"><span data-stu-id="1abb5-111">Example 1: Remove the value of global variables that begin with a search string</span></span>

```
PS C:\> Clear-Variable my* -Scope Global
```

<span data-ttu-id="1abb5-112">このコマンドは、名前が my で始まるグローバル変数の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-112">This command removes the value of global variables that have names that begin with my.</span></span>

### <span data-ttu-id="1abb5-113">例 2: 親スコープではなく、子スコープ内の変数をクリアする</span><span class="sxs-lookup"><span data-stu-id="1abb5-113">Example 2: Clear a variable in a child scope but not the parent scope</span></span>

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

<span data-ttu-id="1abb5-114">これらのコマンドは、子スコープ内の変数をクリアしても親スコープ内の変数はクリアされないことを示します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-114">These commands demonstrate that clearing a variable in a child scope does not clear the value in the parent scope.</span></span>
<span data-ttu-id="1abb5-115">最初のコマンドは、変数 $A の値を3に設定します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-115">The first command sets the value of the variable $A to 3.</span></span>
<span data-ttu-id="1abb5-116">2番目のコマンドは、invoke 演算子 (&) を使用して、新しいスコープで **変数のクリア** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-116">The second command uses the invoke operator (&) to run the **Clear-Variable** command in a new scope.</span></span>
<span data-ttu-id="1abb5-117">子スコープ内で (存在しない場合も) 変数がクリアされますが、ローカル スコープではクリアされません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-117">The variable is cleared in the child scope (although it did not exist), but it is not cleared in the local scope.</span></span>
<span data-ttu-id="1abb5-118">$A の値を取得する3番目のコマンドは、値3が影響を受けないことを示します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-118">The third command, which gets the value of $A, shows that the value 3 is unaffected.</span></span>

### <span data-ttu-id="1abb5-119">例 3: 指定された変数の値を削除する</span><span class="sxs-lookup"><span data-stu-id="1abb5-119">Example 3: Delete the value of the specified variable</span></span>

```
PS C:\> Clear-Variable -Name "Processes"
```

<span data-ttu-id="1abb5-120">このコマンドは、Processes という名前の変数の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-120">This command deletes the value of the variable named Processes.</span></span>
<span data-ttu-id="1abb5-121">コマンドレットによって操作が完了した後も、プロセスという名前の変数は存在しますが、値は null になります。</span><span class="sxs-lookup"><span data-stu-id="1abb5-121">After the cmdlet completes the operation, the variable named Processes still exists, but the value is null.</span></span>

## <span data-ttu-id="1abb5-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1abb5-122">PARAMETERS</span></span>

### <span data-ttu-id="1abb5-123">-除外</span><span class="sxs-lookup"><span data-stu-id="1abb5-123">-Exclude</span></span>

<span data-ttu-id="1abb5-124">このコマンドレットが操作で省略する項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-124">Specifies an array of items that this cmdlet omits in the operation.</span></span>
<span data-ttu-id="1abb5-125">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-125">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="1abb5-126">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-126">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="1abb5-127">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1abb5-127">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="1abb5-128">-Force</span><span class="sxs-lookup"><span data-stu-id="1abb5-128">-Force</span></span>

<span data-ttu-id="1abb5-129">読み取り専用である場合でも、コマンドレットが変数をオフにできるようにします。</span><span class="sxs-lookup"><span data-stu-id="1abb5-129">Allows the cmdlet to clear a variable even if it is read-only.</span></span>
<span data-ttu-id="1abb5-130">Force パラメーターを使用しても、コマンドレットは定数をクリアできません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-130">Even using the Force parameter, the cmdlet cannot clear constants.</span></span>

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

### <span data-ttu-id="1abb5-131">-Include</span><span class="sxs-lookup"><span data-stu-id="1abb5-131">-Include</span></span>

<span data-ttu-id="1abb5-132">このコマンドレットによって操作に含まれる項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-132">Specifies an array of items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="1abb5-133">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-133">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="1abb5-134">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-134">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="1abb5-135">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1abb5-135">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="1abb5-136">-Name</span><span class="sxs-lookup"><span data-stu-id="1abb5-136">-Name</span></span>

<span data-ttu-id="1abb5-137">クリアする変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-137">Specifies the name of the variable to be cleared.</span></span>
<span data-ttu-id="1abb5-138">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1abb5-138">Wildcards are permitted.</span></span>
<span data-ttu-id="1abb5-139">このパラメーターは必須ですが、パラメーター名 ("Name") は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1abb5-139">This parameter is required, but the parameter name ("Name") is optional.</span></span>

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

### <span data-ttu-id="1abb5-140">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1abb5-140">-PassThru</span></span>

<span data-ttu-id="1abb5-141">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-141">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="1abb5-142">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-142">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="1abb5-143">-スコープ</span><span class="sxs-lookup"><span data-stu-id="1abb5-143">-Scope</span></span>

<span data-ttu-id="1abb5-144">このエイリアスが有効なスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-144">Specifies the scope in which this alias is valid.</span></span>

<span data-ttu-id="1abb5-145">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1abb5-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1abb5-146">グローバル</span><span class="sxs-lookup"><span data-stu-id="1abb5-146">Global</span></span>
- <span data-ttu-id="1abb5-147">ローカル</span><span class="sxs-lookup"><span data-stu-id="1abb5-147">Local</span></span>
- <span data-ttu-id="1abb5-148">スクリプト</span><span class="sxs-lookup"><span data-stu-id="1abb5-148">Script</span></span>

<span data-ttu-id="1abb5-149">現在のスコープに対して相対的な数値 (0 ~ スコープの数) を使用することもできます。ここで、0は現在のスコープ、1はその親です。</span><span class="sxs-lookup"><span data-stu-id="1abb5-149">You can also use a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>
<span data-ttu-id="1abb5-150">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="1abb5-150">Local is the default.</span></span>
<span data-ttu-id="1abb5-151">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1abb5-151">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="1abb5-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1abb5-152">-Confirm</span></span>

<span data-ttu-id="1abb5-153">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1abb5-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1abb5-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1abb5-154">-WhatIf</span></span>

<span data-ttu-id="1abb5-155">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1abb5-156">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1abb5-157">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1abb5-157">CommonParameters</span></span>

<span data-ttu-id="1abb5-158">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1abb5-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1abb5-159">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1abb5-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1abb5-160">入力</span><span class="sxs-lookup"><span data-stu-id="1abb5-160">INPUTS</span></span>

### <span data-ttu-id="1abb5-161">なし</span><span class="sxs-lookup"><span data-stu-id="1abb5-161">None</span></span>

<span data-ttu-id="1abb5-162">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-162">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="1abb5-163">出力</span><span class="sxs-lookup"><span data-stu-id="1abb5-163">OUTPUTS</span></span>

### <span data-ttu-id="1abb5-164">None または system.string です。</span><span class="sxs-lookup"><span data-stu-id="1abb5-164">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="1abb5-165">*PassThru* パラメーターを使用すると、このコマンドレットは、クリアされた変数を表す **system.string オブジェクトを** 生成します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-165">When you use the *PassThru* parameter, this cmdlet generates a **System.Management.Automation.PSVariable** object representing the cleared variable.</span></span>
<span data-ttu-id="1abb5-166">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-166">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1abb5-167">注</span><span class="sxs-lookup"><span data-stu-id="1abb5-167">NOTES</span></span>

* <span data-ttu-id="1abb5-168">変数を値と共に削除するには、Remove-Variable また Remove-Item を使用します。</span><span class="sxs-lookup"><span data-stu-id="1abb5-168">To delete a variable, along with its value, use Remove-Variable or Remove-Item.</span></span>

  <span data-ttu-id="1abb5-169">このコマンドレットは、 *Force* パラメーターを使用した場合でも、定数またはシステムによって所有されている変数の値を削除しません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-169">This cmdlet does not delete the values of variables that are set as constants or owned by the system, even if you use the *Force* parameter.</span></span>

  <span data-ttu-id="1abb5-170">クリアする変数が存在しない場合、コマンドレットの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-170">If the variable that you are clearing does not exist, the cmdlet has no effect.</span></span>
<span data-ttu-id="1abb5-171">null 値を持つ変数は作成されません。</span><span class="sxs-lookup"><span data-stu-id="1abb5-171">It does not create a variable with a null value.</span></span>

  <span data-ttu-id="1abb5-172">また、 **Clear 変数** は、その組み込みエイリアスである clv を使用して参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="1abb5-172">You can also refer to **Clear-Variable** by its built-in alias, clv.</span></span>
<span data-ttu-id="1abb5-173">詳細については、「about_Aliases」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1abb5-173">For more information, see about_Aliases.</span></span>

*

## <span data-ttu-id="1abb5-174">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1abb5-174">RELATED LINKS</span></span>

[<span data-ttu-id="1abb5-175">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="1abb5-175">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="1abb5-176">New-Variable</span><span class="sxs-lookup"><span data-stu-id="1abb5-176">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="1abb5-177">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="1abb5-177">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="1abb5-178">変数の設定</span><span class="sxs-lookup"><span data-stu-id="1abb5-178">Set-Variable</span></span>](Set-Variable.md)

