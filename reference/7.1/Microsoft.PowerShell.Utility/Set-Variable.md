---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: c90a2f49c95333e45893e186d6e1f1da4b3fe41a
ms.sourcegitcommit: 0f003644684422e425a59b7361121e05ac772e15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98771826"
---
# <span data-ttu-id="c789d-103">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="c789d-103">Set-Variable</span></span>

## <span data-ttu-id="c789d-104">概要</span><span class="sxs-lookup"><span data-stu-id="c789d-104">SYNOPSIS</span></span>
<span data-ttu-id="c789d-105">変数の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c789d-105">Sets the value of a variable.</span></span> <span data-ttu-id="c789d-106">要求された名前の変数が存在しない場合は、変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="c789d-106">Creates the variable if one with the requested name does not exist.</span></span>

## <span data-ttu-id="c789d-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c789d-107">SYNTAX</span></span>

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c789d-108">Description</span><span class="sxs-lookup"><span data-stu-id="c789d-108">DESCRIPTION</span></span>

<span data-ttu-id="c789d-109">`Set-Variable`コマンドレットは、指定された変数に値を割り当てるか、現在の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="c789d-109">The `Set-Variable` cmdlet assigns a value to a specified variable or changes the current value.</span></span> <span data-ttu-id="c789d-110">変数が存在しない場合は、変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="c789d-110">If the variable does not exist, the cmdlet creates it.</span></span>

## <span data-ttu-id="c789d-111">例</span><span class="sxs-lookup"><span data-stu-id="c789d-111">EXAMPLES</span></span>

### <span data-ttu-id="c789d-112">例 1: 変数を設定し、その値を取得する</span><span class="sxs-lookup"><span data-stu-id="c789d-112">Example 1: Set a variable and get its value</span></span>

<span data-ttu-id="c789d-113">これらのコマンドは、変数の値 `$desc` をに設定 `A description` し、変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c789d-113">These commands set the value of the `$desc` variable to `A description`, and then gets the value of the variable.</span></span>

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### <span data-ttu-id="c789d-114">例 2: グローバルな読み取り専用変数を設定する</span><span class="sxs-lookup"><span data-stu-id="c789d-114">Example 2: Set a global, read-only variable</span></span>

<span data-ttu-id="c789d-115">この例では、システム上のすべてのプロセスを含む読み取り専用のグローバル変数を作成し、変数のすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="c789d-115">This example creates a global, read-only variable that contains all processes on the system, and then it displays all properties of the variable.</span></span>

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option Constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

<span data-ttu-id="c789d-116">このコマンドは、コマンドレットを使用して `Set-Variable` 変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="c789d-116">The command uses the `Set-Variable` cmdlet to create the variable.</span></span> <span data-ttu-id="c789d-117">**PassThru** パラメーターを使用して新しい変数を表すオブジェクトを作成し、パイプライン演算子 () を使用して `|` オブジェクトを `Format-List` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="c789d-117">It uses the **PassThru** parameter to create an object representing the new variable, and it uses the pipeline operator (`|`) to pass the object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="c789d-118">この例では、の **Property** パラメーターを `Format-List` all () と共に使用して `*` 、新しく作成された変数のすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="c789d-118">It uses the **Property** parameter of `Format-List` with a value of all (`*`) to display all properties of the newly created variable.</span></span>

<span data-ttu-id="c789d-119">値は、 `(Get-Process)` 変数に格納される前に実行されるように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="c789d-119">The value, `(Get-Process)`, is enclosed in parentheses to ensure that it is executed before being stored in the variable.</span></span> <span data-ttu-id="c789d-120">それ以外の場合、変数には "**Get Process**" という単語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c789d-120">Otherwise, the variable contains the words "**Get-Process**".</span></span>

### <span data-ttu-id="c789d-121">例 3: パブリック変数とプライベート変数を理解する</span><span class="sxs-lookup"><span data-stu-id="c789d-121">Example 3: Understand public vs. private variables</span></span>

<span data-ttu-id="c789d-122">この例では、変数の可視性をに変更する方法を示し `Private` ます。</span><span class="sxs-lookup"><span data-stu-id="c789d-122">This example shows how to change the visibility of a variable to `Private`.</span></span> <span data-ttu-id="c789d-123">この変数は、必要なアクセス許可を使用すればスクリプトによる読み取りや変更が可能ですが、ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="c789d-123">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

```
PS C:\> New-Variable -Name "counter" -Visibility Public -Value 26
PS C:\> $Counter
26

PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}
Counter               26

PS C:\> Set-Variable -Name "counter" -Visibility Private
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"

PS C:\> .\use-counter.ps1
#Commands completed successfully.
```

<span data-ttu-id="c789d-124">このコマンドは、変数の可視性をプライベートに変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c789d-124">This command shows how to change the visibility of a variable to Private.</span></span> <span data-ttu-id="c789d-125">この変数は、必要なアクセス許可を使用すればスクリプトによる読み取りや変更が可能ですが、ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="c789d-125">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

## <span data-ttu-id="c789d-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c789d-126">PARAMETERS</span></span>

### <span data-ttu-id="c789d-127">-Description</span><span class="sxs-lookup"><span data-stu-id="c789d-127">-Description</span></span>

<span data-ttu-id="c789d-128">変数の説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="c789d-128">Specifies the description of the variable.</span></span>

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

### <span data-ttu-id="c789d-129">-除外</span><span class="sxs-lookup"><span data-stu-id="c789d-129">-Exclude</span></span>

<span data-ttu-id="c789d-130">このコマンドレットによって操作から除外される項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c789d-130">Specifies an array of items that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="c789d-131">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c789d-131">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c789d-132">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="c789d-132">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="c789d-133">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c789d-133">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="c789d-134">-Force</span><span class="sxs-lookup"><span data-stu-id="c789d-134">-Force</span></span>

<span data-ttu-id="c789d-135">既存の読み取り専用変数と同じ名前を持つ変数の作成や、読み取り専用変数の値の変更を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c789d-135">Allows you to create a variable with the same name as an existing read-only variable, or to change the value of a read-only variable.</span></span>

<span data-ttu-id="c789d-136">既定では、変数のオプションの値がまたはの場合を除き、変数を上書きでき `ReadOnly` `Constant` ます。</span><span class="sxs-lookup"><span data-stu-id="c789d-136">By default, you can overwrite a variable, unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="c789d-137">詳細については、「 **オプション** パラメーター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c789d-137">For more information, see the **Option** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c789d-138">-Include</span><span class="sxs-lookup"><span data-stu-id="c789d-138">-Include</span></span>

<span data-ttu-id="c789d-139">このコマンドレットによって操作に含まれる項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c789d-139">Specifies an array of items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="c789d-140">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c789d-140">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="c789d-141">などの名前または名前パターンを入力し `c*` ます。</span><span class="sxs-lookup"><span data-stu-id="c789d-141">Enter a name or name pattern, such as `c*`.</span></span> <span data-ttu-id="c789d-142">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c789d-142">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="c789d-143">-Name</span><span class="sxs-lookup"><span data-stu-id="c789d-143">-Name</span></span>

<span data-ttu-id="c789d-144">変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c789d-144">Specifies the variable name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c789d-145">-Option</span><span class="sxs-lookup"><span data-stu-id="c789d-145">-Option</span></span>

<span data-ttu-id="c789d-146">変数の **Options** プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c789d-146">Specifies the value of the **Options** property of the variable.</span></span>

<span data-ttu-id="c789d-147">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c789d-147">Valid values are:</span></span>

- <span data-ttu-id="c789d-148">`None`: オプションを設定しません。</span><span class="sxs-lookup"><span data-stu-id="c789d-148">`None`: Sets no options.</span></span> <span data-ttu-id="c789d-149">("None" は、既定値です)。</span><span class="sxs-lookup"><span data-stu-id="c789d-149">("None" is the default.)</span></span>
- <span data-ttu-id="c789d-150">`ReadOnly`: 削除できます。</span><span class="sxs-lookup"><span data-stu-id="c789d-150">`ReadOnly`: Can be deleted.</span></span> <span data-ttu-id="c789d-151">Force パラメーターを使用する場合を除き、を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c789d-151">Cannot be changed, except by using the Force parameter.</span></span>
- <span data-ttu-id="c789d-152">`Constant`: 削除または変更できません。</span><span class="sxs-lookup"><span data-stu-id="c789d-152">`Constant`: Cannot be deleted or changed.</span></span> <span data-ttu-id="c789d-153">`Constant` 変数を作成する場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c789d-153">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="c789d-154">既存の変数のオプションをに変更することはできません `Constant` 。</span><span class="sxs-lookup"><span data-stu-id="c789d-154">You cannot change the options of an existing variable to `Constant`.</span></span>
- <span data-ttu-id="c789d-155">`Private`: 変数は、現在のスコープでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c789d-155">`Private`: The variable is available only in the current scope.</span></span>
- <span data-ttu-id="c789d-156">`AllScope`: 変数は、作成された新しいスコープにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c789d-156">`AllScope`: The variable is copied to any new scopes that are created.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c789d-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c789d-157">-PassThru</span></span>

<span data-ttu-id="c789d-158">新しい変数を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c789d-158">Returns an object representing the new variable.</span></span> <span data-ttu-id="c789d-159">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="c789d-159">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c789d-160">-スコープ</span><span class="sxs-lookup"><span data-stu-id="c789d-160">-Scope</span></span>

<span data-ttu-id="c789d-161">変数のスコープを指定します。このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c789d-161">Specifies the scope of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c789d-162">グローバル</span><span class="sxs-lookup"><span data-stu-id="c789d-162">Global</span></span>
- <span data-ttu-id="c789d-163">ローカル</span><span class="sxs-lookup"><span data-stu-id="c789d-163">Local</span></span>
- <span data-ttu-id="c789d-164">スクリプト</span><span class="sxs-lookup"><span data-stu-id="c789d-164">Script</span></span>
- <span data-ttu-id="c789d-165">プライベート</span><span class="sxs-lookup"><span data-stu-id="c789d-165">Private</span></span>
- <span data-ttu-id="c789d-166">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)。</span><span class="sxs-lookup"><span data-stu-id="c789d-166">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="c789d-167">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="c789d-167">Local is the default.</span></span>

<span data-ttu-id="c789d-168">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c789d-168">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span></span>

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

### <span data-ttu-id="c789d-169">-Value</span><span class="sxs-lookup"><span data-stu-id="c789d-169">-Value</span></span>

<span data-ttu-id="c789d-170">変数の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c789d-170">Specifies the value of the variable.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c789d-171">-可視性</span><span class="sxs-lookup"><span data-stu-id="c789d-171">-Visibility</span></span>

<span data-ttu-id="c789d-172">変数を、作成元のセッションの外部で表示されるようにするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c789d-172">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="c789d-173">このパラメーターは、他のユーザーに配信されるスクリプトおよびコマンドで使用するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="c789d-173">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span>

<span data-ttu-id="c789d-174">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c789d-174">Valid values are:</span></span>

- <span data-ttu-id="c789d-175">Public: 変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c789d-175">Public:  The variable is visible.</span></span> <span data-ttu-id="c789d-176">("Public" は既定値です)。</span><span class="sxs-lookup"><span data-stu-id="c789d-176">("Public" is the default.)</span></span>
- <span data-ttu-id="c789d-177">Private: 変数は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c789d-177">Private: The variable is not visible.</span></span>

<span data-ttu-id="c789d-178">変数がプライベートである場合は、変数の一覧に表示されません。たとえば、変数がによって返され `Get-Variable` たり、 **変数:** ドライブに表示されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="c789d-178">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the **Variable:** drive.</span></span> <span data-ttu-id="c789d-179">プライベート変数の値を読み取りまたは変更するコマンドは、エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="c789d-179">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="c789d-180">ただし、コマンドが、変数の定義元のセッションで記述されている場合は、プライベート変数を使用するコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c789d-180">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: Public
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c789d-181">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c789d-181">-Confirm</span></span>

<span data-ttu-id="c789d-182">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c789d-182">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c789d-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c789d-183">-WhatIf</span></span>

<span data-ttu-id="c789d-184">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c789d-184">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c789d-185">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c789d-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c789d-186">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c789d-186">CommonParameters</span></span>

<span data-ttu-id="c789d-187">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c789d-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c789d-188">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c789d-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c789d-189">入力</span><span class="sxs-lookup"><span data-stu-id="c789d-189">INPUTS</span></span>

### <span data-ttu-id="c789d-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="c789d-190">System.Object</span></span>

<span data-ttu-id="c789d-191">パイプを使用して、変数の値を表すオブジェクトをにパイプすることができ `Set-Variable` ます。</span><span class="sxs-lookup"><span data-stu-id="c789d-191">You can pipe an object that represents the value of the variable to `Set-Variable`.</span></span>

## <span data-ttu-id="c789d-192">出力</span><span class="sxs-lookup"><span data-stu-id="c789d-192">OUTPUTS</span></span>

### <span data-ttu-id="c789d-193">None または system.string です。</span><span class="sxs-lookup"><span data-stu-id="c789d-193">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="c789d-194">**PassThru** パラメーターを使用すると、に `Set-Variable` よって、新しい変数または変更された変数を表す system.string オブジェクトが生成さ **れます。**</span><span class="sxs-lookup"><span data-stu-id="c789d-194">When you use the **PassThru** parameter, `Set-Variable` generates a **System.Management.Automation.PSVariable** object representing the new or changed variable.</span></span>
<span data-ttu-id="c789d-195">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="c789d-195">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c789d-196">注</span><span class="sxs-lookup"><span data-stu-id="c789d-196">NOTES</span></span>

## <span data-ttu-id="c789d-197">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c789d-197">RELATED LINKS</span></span>

[<span data-ttu-id="c789d-198">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="c789d-198">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="c789d-199">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="c789d-199">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="c789d-200">New-Variable</span><span class="sxs-lookup"><span data-stu-id="c789d-200">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="c789d-201">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="c789d-201">Remove-Variable</span></span>](Remove-Variable.md)
