---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: c77eb9c64022d028c3c4b2de6bf4551886b940e1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601991"
---
# <span data-ttu-id="618c7-102">New-Variable</span><span class="sxs-lookup"><span data-stu-id="618c7-102">New-Variable</span></span>

## <span data-ttu-id="618c7-103">概要</span><span class="sxs-lookup"><span data-stu-id="618c7-103">SYNOPSIS</span></span>
<span data-ttu-id="618c7-104">新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="618c7-104">Creates a new variable.</span></span>

## <span data-ttu-id="618c7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="618c7-105">SYNTAX</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="618c7-106">Description</span><span class="sxs-lookup"><span data-stu-id="618c7-106">DESCRIPTION</span></span>
<span data-ttu-id="618c7-107">**新しい変数** のコマンドレットは、PowerShell で新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="618c7-107">The **New-Variable** cmdlet creates a new variable in PowerShell.</span></span>
<span data-ttu-id="618c7-108">変数の作成時に、変数に値を割り当てることも、作成後に値の割り当てまたは変更を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="618c7-108">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="618c7-109">**新しい変数** のパラメーターを使用して、変数のプロパティの設定、変数のスコープの設定、および変数がパブリックかプライベートかの判断を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="618c7-109">You can use the parameters of **New-Variable** to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="618c7-110">通常は、変数名とその値 (など) を入力して新しい変数を作成し `$Var = 3` ますが、パラメーターを使用するには、 **新しい** 変数のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="618c7-110">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the **New-Variable** cmdlet to use its parameters.</span></span>

## <span data-ttu-id="618c7-111">例</span><span class="sxs-lookup"><span data-stu-id="618c7-111">EXAMPLES</span></span>

### <span data-ttu-id="618c7-112">例 1: 変数を作成する</span><span class="sxs-lookup"><span data-stu-id="618c7-112">Example 1: Create a variable</span></span>

```
PS C:\> New-Variable days
```

<span data-ttu-id="618c7-113">このコマンドは、days という名前の新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="618c7-113">This command creates a new variable named days.</span></span>
<span data-ttu-id="618c7-114">*Name* パラメーターを入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="618c7-114">You are not required to type the *Name* parameter.</span></span>

### <span data-ttu-id="618c7-115">例 2: 変数を作成して値を割り当てる</span><span class="sxs-lookup"><span data-stu-id="618c7-115">Example 2: Create a variable and assign it a value</span></span>

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="618c7-116">このコマンドは、zipcode という名前の変数を作成し、値98033を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="618c7-116">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="618c7-117">例 3: ReadOnly オプションを使用して変数を作成する</span><span class="sxs-lookup"><span data-stu-id="618c7-117">Example 3: Create a variable with the ReadOnly option</span></span>

```
PS C:\> New-Variable -Name Max -Value 256 -Option ReadOnly
PS C:\> New-Variable -Name max -Value 1024

New-Variable : A variable with name 'max' already exists.
At line:1 char:1
+ New-Variable -Name max -Value 1024
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ResourceExists: (max:String) [New-Variable], SessionStateException
    + FullyQualifiedErrorId : VariableAlreadyExists,Microsoft.PowerShell.Commands.NewVariableCommand

PS C:\> New-Variable -Name max -Value 1024 -Force
```

<span data-ttu-id="618c7-118">この例では、 **New 変数** の ReadOnly オプションを使用して、変数を上書きから保護する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="618c7-118">This example shows how to use the ReadOnly option of **New-Variable** to protect a variable from being overwritten.</span></span>

<span data-ttu-id="618c7-119">最初のコマンドは、Max という名前の新しい変数を作成し、その値を256に設定します。</span><span class="sxs-lookup"><span data-stu-id="618c7-119">The first command creates a new variable named Max and sets its value to 256.</span></span>
<span data-ttu-id="618c7-120">この例では、 *オプション* パラメーターに ReadOnly の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="618c7-120">It uses the *Option* parameter with a value of ReadOnly.</span></span>

<span data-ttu-id="618c7-121">2 番目のコマンドは、同じ名前の 2 番目の変数の作成を試みます。</span><span class="sxs-lookup"><span data-stu-id="618c7-121">The second command tries to create a second variable with the same name.</span></span>
<span data-ttu-id="618c7-122">その変数に読み取り専用オプションが設定されているため、このコマンドはエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="618c7-122">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="618c7-123">3番目のコマンドは、 *Force* パラメーターを使用して、変数の読み取り専用保護を上書きします。</span><span class="sxs-lookup"><span data-stu-id="618c7-123">The third command uses the *Force* parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="618c7-124">この場合、コマンドは、同じ名前を持つ新しい変数を正常に作成できます。</span><span class="sxs-lookup"><span data-stu-id="618c7-124">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="618c7-125">例 4: プライベート変数を作成する</span><span class="sxs-lookup"><span data-stu-id="618c7-125">Example 4: Create a private variable</span></span>

```
PS C:\> New-Variable -Name counter -Visibility Private

#Effect of private variable in a module.

PS C:\> Get-Variable c*

Name                           Value
----                           -----
Culture                        en-US
ConsoleFileName
ConfirmPreference              High
CommandLineParameters          {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"
At line:1 char:1
+ $counter
+ ~~~~~~~~
    + CategoryInfo          : PermissionDenied: (counter:String) [], SessionStateException
    + FullyQualifiedErrorId : VariableIsPrivate

PS C:\> Get-Counter
Name         Value
----         -----
Counter1     3.1415
...
```

<span data-ttu-id="618c7-126">このコマンドは、モジュール内のプライベート変数の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="618c7-126">This command demonstrates the behavior of a private variable in a module.</span></span>
<span data-ttu-id="618c7-127">モジュールには、Counter という名前のプライベート変数を持つ Get-Counter コマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="618c7-127">The module contains the Get-Counter cmdlet, which has a private variable named Counter.</span></span>
<span data-ttu-id="618c7-128">このコマンドは、 *Visibility* パラメーターと値 Private を使用して変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="618c7-128">The command uses the *Visibility* parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="618c7-129">サンプル出力は、プライベート変数の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="618c7-129">The sample output shows the behavior of a private variable.</span></span>
<span data-ttu-id="618c7-130">モジュールを読み込んだユーザーは、Counter 変数の値を表示または変更できませんが、モジュール内のコマンドによって Counter 変数を読み取ったり変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="618c7-130">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="618c7-131">例 5: スペースを含む変数を作成する</span><span class="sxs-lookup"><span data-stu-id="618c7-131">Example 5: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="618c7-132">このコマンドは、スペースを含む変数を作成できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="618c7-132">This command demonstrates that variables with spaces can be created.</span></span>
<span data-ttu-id="618c7-133">変数は、変数を中かっこで区切ることによって、変数を **取得** したり、変数に直接アクセスしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="618c7-133">The variables can be accessed using the **Get-Variable** cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="618c7-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="618c7-134">PARAMETERS</span></span>

### <span data-ttu-id="618c7-135">-Description</span><span class="sxs-lookup"><span data-stu-id="618c7-135">-Description</span></span>
<span data-ttu-id="618c7-136">変数の説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="618c7-136">Specifies a description of the variable.</span></span>

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

### <span data-ttu-id="618c7-137">-Force</span><span class="sxs-lookup"><span data-stu-id="618c7-137">-Force</span></span>
<span data-ttu-id="618c7-138">コマンドレットによって、既存の読み取り専用変数と同じ名前の変数が作成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="618c7-138">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="618c7-139">既定では、変数のオプション値が ReadOnly または Constant でない限り、変数を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="618c7-139">By default, you can overwrite a variable unless the variable has an option value of ReadOnly or Constant.</span></span>
<span data-ttu-id="618c7-140">詳細については、「 *オプション* パラメーター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="618c7-140">For more information, see the *Option* parameter.</span></span>

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

### <span data-ttu-id="618c7-141">-Name</span><span class="sxs-lookup"><span data-stu-id="618c7-141">-Name</span></span>
<span data-ttu-id="618c7-142">新しい変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="618c7-142">Specifies a name for the new variable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="618c7-143">-Option</span><span class="sxs-lookup"><span data-stu-id="618c7-143">-Option</span></span>
<span data-ttu-id="618c7-144">変数の **Options** プロパティの値を指定します。このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="618c7-144">Specifies the value of the **Options** property of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="618c7-145">[なし] :</span><span class="sxs-lookup"><span data-stu-id="618c7-145">None.</span></span>
<span data-ttu-id="618c7-146">オプションを設定しません</span><span class="sxs-lookup"><span data-stu-id="618c7-146">Sets no options.</span></span>
<span data-ttu-id="618c7-147">(既定値は None です)。</span><span class="sxs-lookup"><span data-stu-id="618c7-147">(None is the default.)</span></span>
- <span data-ttu-id="618c7-148">ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="618c7-148">ReadOnly.</span></span>
<span data-ttu-id="618c7-149">削除できます。</span><span class="sxs-lookup"><span data-stu-id="618c7-149">Can be deleted.</span></span>
<span data-ttu-id="618c7-150">*Force* パラメーターを使用する場合を除き、を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="618c7-150">Cannot be changed, except by using the *Force* parameter.</span></span>
- <span data-ttu-id="618c7-151">プライベート。</span><span class="sxs-lookup"><span data-stu-id="618c7-151">Private.</span></span>
<span data-ttu-id="618c7-152">変数は、現在のスコープ内でのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="618c7-152">The variable is available only in the current scope.</span></span>
- <span data-ttu-id="618c7-153">Allscope オプション.</span><span class="sxs-lookup"><span data-stu-id="618c7-153">AllScope.</span></span>
<span data-ttu-id="618c7-154">変数は、作成された任意の新しいスコープにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="618c7-154">The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="618c7-155">定数。</span><span class="sxs-lookup"><span data-stu-id="618c7-155">Constant.</span></span>
<span data-ttu-id="618c7-156">削除または変更できません。</span><span class="sxs-lookup"><span data-stu-id="618c7-156">Cannot be deleted or changed.</span></span>
<span data-ttu-id="618c7-157">定数は、変数を作成する場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="618c7-157">Constant is valid only when you are creating a variable.</span></span>
<span data-ttu-id="618c7-158">既存の変数のオプションを定数に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="618c7-158">You cannot change the options of an existing variable to Constant.</span></span>

<span data-ttu-id="618c7-159">セッション内のすべての変数の **Options** プロパティを表示するには、「」と入力 `Get-Variable | Format-Table -Property name, options -autosize` します。</span><span class="sxs-lookup"><span data-stu-id="618c7-159">To see the **Options** property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -autosize`.</span></span>

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

### <span data-ttu-id="618c7-160">-PassThru</span><span class="sxs-lookup"><span data-stu-id="618c7-160">-PassThru</span></span>
<span data-ttu-id="618c7-161">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="618c7-161">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="618c7-162">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="618c7-162">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="618c7-163">-スコープ</span><span class="sxs-lookup"><span data-stu-id="618c7-163">-Scope</span></span>
<span data-ttu-id="618c7-164">新しい変数のスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="618c7-164">Specifies the scope of the new variable.</span></span>
<span data-ttu-id="618c7-165">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="618c7-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="618c7-166">全体.</span><span class="sxs-lookup"><span data-stu-id="618c7-166">Global.</span></span>
<span data-ttu-id="618c7-167">グローバルスコープで作成された変数は、PowerShell プロセス内のすべての場所でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="618c7-167">Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="618c7-168">Local。</span><span class="sxs-lookup"><span data-stu-id="618c7-168">Local.</span></span>
<span data-ttu-id="618c7-169">ローカルスコープは、現在のスコープを参照します。これは、コンテキストによっては任意のスコープにすることができます。</span><span class="sxs-lookup"><span data-stu-id="618c7-169">The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="618c7-170">スクリプティング。</span><span class="sxs-lookup"><span data-stu-id="618c7-170">Script.</span></span>
<span data-ttu-id="618c7-171">スクリプトスコープで作成された変数は、で作成されたスクリプトファイルまたはモジュール内でのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="618c7-171">Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="618c7-172">プライベート。</span><span class="sxs-lookup"><span data-stu-id="618c7-172">Private.</span></span>
<span data-ttu-id="618c7-173">プライベートスコープで作成された変数は、存在するスコープの外部ではアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="618c7-173">Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span>
<span data-ttu-id="618c7-174">プライベートスコープを使用すると、別のスコープに同じ名前の項目のプライベートバージョンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="618c7-174">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="618c7-175">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1は親、親スコープの親は2など)。</span><span class="sxs-lookup"><span data-stu-id="618c7-175">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span>
<span data-ttu-id="618c7-176">負の数値は使用できません。</span><span class="sxs-lookup"><span data-stu-id="618c7-176">Negative numbers cannot be used.</span></span>

<span data-ttu-id="618c7-177">Scope パラメーターが指定されていない場合、Local は既定のスコープです。</span><span class="sxs-lookup"><span data-stu-id="618c7-177">Local is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="618c7-178">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="618c7-178">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="618c7-179">-Value</span><span class="sxs-lookup"><span data-stu-id="618c7-179">-Value</span></span>
<span data-ttu-id="618c7-180">変数の初期値を指定します。</span><span class="sxs-lookup"><span data-stu-id="618c7-180">Specifies the initial value of the variable.</span></span>

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

### <span data-ttu-id="618c7-181">-可視性</span><span class="sxs-lookup"><span data-stu-id="618c7-181">-Visibility</span></span>
<span data-ttu-id="618c7-182">変数を、作成元のセッションの外部で表示されるようにするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="618c7-182">Determines whether the variable is visible outside of the session in which it was created.</span></span>
<span data-ttu-id="618c7-183">このパラメーターは、他のユーザーに配信されるスクリプトおよびコマンドで使用する目的で設計されています。</span><span class="sxs-lookup"><span data-stu-id="618c7-183">This parameter is designed for  use in scripts and commands that will be delivered to other users.</span></span>
<span data-ttu-id="618c7-184">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="618c7-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="618c7-185">パブリック。</span><span class="sxs-lookup"><span data-stu-id="618c7-185">Public.</span></span>
<span data-ttu-id="618c7-186">変数は表示されます</span><span class="sxs-lookup"><span data-stu-id="618c7-186">The variable is visible.</span></span>
<span data-ttu-id="618c7-187">(Public が既定値です)。</span><span class="sxs-lookup"><span data-stu-id="618c7-187">(Public is the default.)</span></span>
- <span data-ttu-id="618c7-188">プライベート。</span><span class="sxs-lookup"><span data-stu-id="618c7-188">Private.</span></span>
<span data-ttu-id="618c7-189">変数は表示されません。</span><span class="sxs-lookup"><span data-stu-id="618c7-189">The variable is not visible.</span></span>

<span data-ttu-id="618c7-190">変数がプライベートの場合、その変数は、Get-Variable で返されるような変数一覧または Variable: ドライブの表示には出現しません。</span><span class="sxs-lookup"><span data-stu-id="618c7-190">When a variable is private, it does not appear in lists of variables, such as those returned by Get-Variable, or in displays of the Variable: drive.</span></span>
<span data-ttu-id="618c7-191">プライベート変数の値を読み取りまたは変更するコマンドは、エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="618c7-191">Commands to read or change the value of a private variable return an error.</span></span>
<span data-ttu-id="618c7-192">ただし、コマンドが、変数の定義元のセッションで記述されている場合は、プライベート変数を使用するコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="618c7-192">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="618c7-193">-Confirm</span><span class="sxs-lookup"><span data-stu-id="618c7-193">-Confirm</span></span>
<span data-ttu-id="618c7-194">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="618c7-194">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="618c7-195">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="618c7-195">-WhatIf</span></span>
<span data-ttu-id="618c7-196">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="618c7-196">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="618c7-197">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="618c7-197">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="618c7-198">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="618c7-198">CommonParameters</span></span>
<span data-ttu-id="618c7-199">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="618c7-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="618c7-200">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="618c7-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="618c7-201">入力</span><span class="sxs-lookup"><span data-stu-id="618c7-201">INPUTS</span></span>

### <span data-ttu-id="618c7-202">System.Object</span><span class="sxs-lookup"><span data-stu-id="618c7-202">System.Object</span></span>
<span data-ttu-id="618c7-203">パイプを使用して値を **新しい変数** にパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="618c7-203">You can pipe a value to **New-Variable**.</span></span>

## <span data-ttu-id="618c7-204">出力</span><span class="sxs-lookup"><span data-stu-id="618c7-204">OUTPUTS</span></span>

### <span data-ttu-id="618c7-205">None または system.string です。</span><span class="sxs-lookup"><span data-stu-id="618c7-205">None or System.Management.Automation.PSVariable</span></span>
<span data-ttu-id="618c7-206">*PassThru* パラメーターを使用すると、 **new 変数** は新しい変数を表す **system.string オブジェクト** を生成します。</span><span class="sxs-lookup"><span data-stu-id="618c7-206">When you use the *PassThru* parameter, **New-Variable** generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span>
<span data-ttu-id="618c7-207">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="618c7-207">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="618c7-208">注</span><span class="sxs-lookup"><span data-stu-id="618c7-208">NOTES</span></span>

## <span data-ttu-id="618c7-209">関連リンク</span><span class="sxs-lookup"><span data-stu-id="618c7-209">RELATED LINKS</span></span>

[<span data-ttu-id="618c7-210">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="618c7-210">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="618c7-211">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="618c7-211">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="618c7-212">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="618c7-212">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="618c7-213">変数の設定</span><span class="sxs-lookup"><span data-stu-id="618c7-213">Set-Variable</span></span>](Set-Variable.md)

