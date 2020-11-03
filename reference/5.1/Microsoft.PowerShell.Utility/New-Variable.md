---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: 6db5d6693e7e42b5563baa3dbaebb495f97f53a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213787"
---
# <span data-ttu-id="b4d97-103">New-Variable</span><span class="sxs-lookup"><span data-stu-id="b4d97-103">New-Variable</span></span>

## <span data-ttu-id="b4d97-104">概要</span><span class="sxs-lookup"><span data-stu-id="b4d97-104">SYNOPSIS</span></span>
<span data-ttu-id="b4d97-105">新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-105">Creates a new variable.</span></span>

## <span data-ttu-id="b4d97-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b4d97-106">SYNTAX</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="b4d97-107">Description</span><span class="sxs-lookup"><span data-stu-id="b4d97-107">DESCRIPTION</span></span>
<span data-ttu-id="b4d97-108">**新しい変数** のコマンドレットは、Windows PowerShell で新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-108">The **New-Variable** cmdlet creates a new variable in Windows PowerShell.</span></span>
<span data-ttu-id="b4d97-109">変数の作成時に、変数に値を割り当てることも、作成後に値の割り当てまたは変更を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-109">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="b4d97-110">**新しい変数** のパラメーターを使用して、変数のプロパティの設定、変数のスコープの設定、および変数がパブリックかプライベートかの判断を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-110">You can use the parameters of **New-Variable** to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="b4d97-111">通常は、変数名とその値 (など) を入力して新しい変数を作成し `$Var = 3` ますが、パラメーターを使用するには、 **新しい** 変数のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-111">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the **New-Variable** cmdlet to use its parameters.</span></span>

## <span data-ttu-id="b4d97-112">例</span><span class="sxs-lookup"><span data-stu-id="b4d97-112">EXAMPLES</span></span>

### <span data-ttu-id="b4d97-113">例 1: 変数を作成する</span><span class="sxs-lookup"><span data-stu-id="b4d97-113">Example 1: Create a variable</span></span>

```
PS C:\> New-Variable days
```

<span data-ttu-id="b4d97-114">このコマンドは、days という名前の新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-114">This command creates a new variable named days.</span></span>
<span data-ttu-id="b4d97-115">*Name* パラメーターを入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-115">You are not required to type the *Name* parameter.</span></span>

### <span data-ttu-id="b4d97-116">例 2: 変数を作成して値を割り当てる</span><span class="sxs-lookup"><span data-stu-id="b4d97-116">Example 2: Create a variable and assign it a value</span></span>

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="b4d97-117">このコマンドは、zipcode という名前の変数を作成し、値98033を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-117">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="b4d97-118">例 3: ReadOnly オプションを使用して変数を作成する</span><span class="sxs-lookup"><span data-stu-id="b4d97-118">Example 3: Create a variable with the ReadOnly option</span></span>

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

<span data-ttu-id="b4d97-119">この例では、 **New 変数** の ReadOnly オプションを使用して、変数を上書きから保護する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-119">This example shows how to use the ReadOnly option of **New-Variable** to protect a variable from being overwritten.</span></span>

<span data-ttu-id="b4d97-120">最初のコマンドは、Max という名前の新しい変数を作成し、その値を256に設定します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-120">The first command creates a new variable named Max and sets its value to 256.</span></span>
<span data-ttu-id="b4d97-121">この例では、 *オプション* パラメーターに ReadOnly の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="b4d97-121">It uses the *Option* parameter with a value of ReadOnly.</span></span>

<span data-ttu-id="b4d97-122">2 番目のコマンドは、同じ名前の 2 番目の変数の作成を試みます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-122">The second command tries to create a second variable with the same name.</span></span>
<span data-ttu-id="b4d97-123">その変数に読み取り専用オプションが設定されているため、このコマンドはエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-123">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="b4d97-124">3番目のコマンドは、 *Force* パラメーターを使用して、変数の読み取り専用保護を上書きします。</span><span class="sxs-lookup"><span data-stu-id="b4d97-124">The third command uses the *Force* parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="b4d97-125">この場合、コマンドは、同じ名前を持つ新しい変数を正常に作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-125">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="b4d97-126">例 4: プライベート変数を作成する</span><span class="sxs-lookup"><span data-stu-id="b4d97-126">Example 4: Create a private variable</span></span>

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

<span data-ttu-id="b4d97-127">このコマンドは、モジュール内のプライベート変数の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="b4d97-127">This command demonstrates the behavior of a private variable in a module.</span></span>
<span data-ttu-id="b4d97-128">モジュールには、Counter という名前のプライベート変数を持つ Get-Counter コマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4d97-128">The module contains the Get-Counter cmdlet, which has a private variable named Counter.</span></span>
<span data-ttu-id="b4d97-129">このコマンドは、 *Visibility* パラメーターと値 Private を使用して変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-129">The command uses the *Visibility* parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="b4d97-130">サンプル出力は、プライベート変数の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="b4d97-130">The sample output shows the behavior of a private variable.</span></span>
<span data-ttu-id="b4d97-131">モジュールを読み込んだユーザーは、Counter 変数の値を表示または変更できませんが、モジュール内のコマンドによって Counter 変数を読み取ったり変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-131">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="b4d97-132">例 5: スペースを含む変数を作成する</span><span class="sxs-lookup"><span data-stu-id="b4d97-132">Example 5: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="b4d97-133">このコマンドは、スペースを含む変数を作成できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b4d97-133">This command demonstrates that variables with spaces can be created.</span></span>
<span data-ttu-id="b4d97-134">変数は、変数を中かっこで区切ることによって、変数を **取得** したり、変数に直接アクセスしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-134">The variables can be accessed using the **Get-Variable** cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="b4d97-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b4d97-135">PARAMETERS</span></span>

### <span data-ttu-id="b4d97-136">-Description</span><span class="sxs-lookup"><span data-stu-id="b4d97-136">-Description</span></span>
<span data-ttu-id="b4d97-137">変数の説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-137">Specifies a description of the variable.</span></span>

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

### <span data-ttu-id="b4d97-138">-Force</span><span class="sxs-lookup"><span data-stu-id="b4d97-138">-Force</span></span>
<span data-ttu-id="b4d97-139">コマンドレットによって、既存の読み取り専用変数と同じ名前の変数が作成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-139">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="b4d97-140">既定では、変数のオプション値が ReadOnly または Constant でない限り、変数を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-140">By default, you can overwrite a variable unless the variable has an option value of ReadOnly or Constant.</span></span>
<span data-ttu-id="b4d97-141">詳細については、「 *オプション* パラメーター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d97-141">For more information, see the *Option* parameter.</span></span>

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

### <span data-ttu-id="b4d97-142">-Name</span><span class="sxs-lookup"><span data-stu-id="b4d97-142">-Name</span></span>
<span data-ttu-id="b4d97-143">新しい変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-143">Specifies a name for the new variable.</span></span>

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

### <span data-ttu-id="b4d97-144">-Option</span><span class="sxs-lookup"><span data-stu-id="b4d97-144">-Option</span></span>
<span data-ttu-id="b4d97-145">変数の **Options** プロパティの値を指定します。このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4d97-145">Specifies the value of the **Options** property of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b4d97-146">なし。</span><span class="sxs-lookup"><span data-stu-id="b4d97-146">None.</span></span>
<span data-ttu-id="b4d97-147">オプションを設定しません</span><span class="sxs-lookup"><span data-stu-id="b4d97-147">Sets no options.</span></span>
<span data-ttu-id="b4d97-148">(既定値は None です)。</span><span class="sxs-lookup"><span data-stu-id="b4d97-148">(None is the default.)</span></span>
- <span data-ttu-id="b4d97-149">ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="b4d97-149">ReadOnly.</span></span>
<span data-ttu-id="b4d97-150">削除できます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-150">Can be deleted.</span></span>
<span data-ttu-id="b4d97-151">*Force* パラメーターを使用する場合を除き、を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-151">Cannot be changed, except by using the *Force* parameter.</span></span>
- <span data-ttu-id="b4d97-152">プライベート。</span><span class="sxs-lookup"><span data-stu-id="b4d97-152">Private.</span></span>
<span data-ttu-id="b4d97-153">変数は、現在のスコープ内でのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="b4d97-153">The variable is available only in the current scope.</span></span>
- <span data-ttu-id="b4d97-154">Allscope オプション.</span><span class="sxs-lookup"><span data-stu-id="b4d97-154">AllScope.</span></span>
<span data-ttu-id="b4d97-155">変数は、作成された任意の新しいスコープにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-155">The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="b4d97-156">定数。</span><span class="sxs-lookup"><span data-stu-id="b4d97-156">Constant.</span></span>
<span data-ttu-id="b4d97-157">削除または変更できません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-157">Cannot be deleted or changed.</span></span>
<span data-ttu-id="b4d97-158">定数は、変数を作成する場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="b4d97-158">Constant is valid only when you are creating a variable.</span></span>
<span data-ttu-id="b4d97-159">既存の変数のオプションを定数に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-159">You cannot change the options of an existing variable to Constant.</span></span>

<span data-ttu-id="b4d97-160">セッション内のすべての変数の **Options** プロパティを表示するには、「」と入力 `Get-Variable | Format-Table -Property name, options -autosize` します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-160">To see the **Options** property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -autosize`.</span></span>

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

### <span data-ttu-id="b4d97-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b4d97-161">-PassThru</span></span>
<span data-ttu-id="b4d97-162">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-162">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b4d97-163">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-163">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b4d97-164">-スコープ</span><span class="sxs-lookup"><span data-stu-id="b4d97-164">-Scope</span></span>
<span data-ttu-id="b4d97-165">新しい変数のスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-165">Specifies the scope of the new variable.</span></span>
<span data-ttu-id="b4d97-166">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4d97-166">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b4d97-167">全体.</span><span class="sxs-lookup"><span data-stu-id="b4d97-167">Global.</span></span>
<span data-ttu-id="b4d97-168">グローバルスコープで作成された変数は、PowerShell プロセス内のすべての場所でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-168">Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="b4d97-169">Local。</span><span class="sxs-lookup"><span data-stu-id="b4d97-169">Local.</span></span>
<span data-ttu-id="b4d97-170">ローカルスコープは、現在のスコープを参照します。これは、コンテキストによっては任意のスコープにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-170">The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="b4d97-171">スクリプティング。</span><span class="sxs-lookup"><span data-stu-id="b4d97-171">Script.</span></span>
<span data-ttu-id="b4d97-172">スクリプトスコープで作成された変数は、で作成されたスクリプトファイルまたはモジュール内でのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-172">Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="b4d97-173">プライベート。</span><span class="sxs-lookup"><span data-stu-id="b4d97-173">Private.</span></span>
<span data-ttu-id="b4d97-174">プライベートスコープで作成された変数は、存在するスコープの外部ではアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-174">Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span>
<span data-ttu-id="b4d97-175">プライベートスコープを使用すると、別のスコープに同じ名前の項目のプライベートバージョンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-175">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="b4d97-176">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1は親、親スコープの親は2など)。</span><span class="sxs-lookup"><span data-stu-id="b4d97-176">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span>
<span data-ttu-id="b4d97-177">負の数値は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-177">Negative numbers cannot be used.</span></span>

<span data-ttu-id="b4d97-178">Scope パラメーターが指定されていない場合、Local は既定のスコープです。</span><span class="sxs-lookup"><span data-stu-id="b4d97-178">Local is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="b4d97-179">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d97-179">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="b4d97-180">-Value</span><span class="sxs-lookup"><span data-stu-id="b4d97-180">-Value</span></span>
<span data-ttu-id="b4d97-181">変数の初期値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-181">Specifies the initial value of the variable.</span></span>

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

### <span data-ttu-id="b4d97-182">-可視性</span><span class="sxs-lookup"><span data-stu-id="b4d97-182">-Visibility</span></span>
<span data-ttu-id="b4d97-183">変数を、作成元のセッションの外部で表示されるようにするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-183">Determines whether the variable is visible outside of the session in which it was created.</span></span>
<span data-ttu-id="b4d97-184">このパラメーターは、他のユーザーに配信されるスクリプトおよびコマンドで使用する目的で設計されています。</span><span class="sxs-lookup"><span data-stu-id="b4d97-184">This parameter is designed for  use in scripts and commands that will be delivered to other users.</span></span>
<span data-ttu-id="b4d97-185">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4d97-185">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b4d97-186">パブリック。</span><span class="sxs-lookup"><span data-stu-id="b4d97-186">Public.</span></span>
<span data-ttu-id="b4d97-187">変数は表示されます</span><span class="sxs-lookup"><span data-stu-id="b4d97-187">The variable is visible.</span></span>
<span data-ttu-id="b4d97-188">(Public が既定値です)。</span><span class="sxs-lookup"><span data-stu-id="b4d97-188">(Public is the default.)</span></span>
- <span data-ttu-id="b4d97-189">プライベート。</span><span class="sxs-lookup"><span data-stu-id="b4d97-189">Private.</span></span>
<span data-ttu-id="b4d97-190">変数は表示されません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-190">The variable is not visible.</span></span>

<span data-ttu-id="b4d97-191">変数がプライベートの場合、その変数は、Get-Variable で返されるような変数一覧または Variable: ドライブの表示には出現しません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-191">When a variable is private, it does not appear in lists of variables, such as those returned by Get-Variable, or in displays of the Variable: drive.</span></span>
<span data-ttu-id="b4d97-192">プライベート変数の値を読み取りまたは変更するコマンドは、エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-192">Commands to read or change the value of a private variable return an error.</span></span>
<span data-ttu-id="b4d97-193">ただし、コマンドが、変数の定義元のセッションで記述されている場合は、プライベート変数を使用するコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-193">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="b4d97-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b4d97-194">-Confirm</span></span>
<span data-ttu-id="b4d97-195">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b4d97-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b4d97-196">-WhatIf</span></span>
<span data-ttu-id="b4d97-197">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-197">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b4d97-198">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b4d97-199">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4d97-199">CommonParameters</span></span>
<span data-ttu-id="b4d97-200">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b4d97-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b4d97-201">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d97-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b4d97-202">入力</span><span class="sxs-lookup"><span data-stu-id="b4d97-202">INPUTS</span></span>

### <span data-ttu-id="b4d97-203">System.Object</span><span class="sxs-lookup"><span data-stu-id="b4d97-203">System.Object</span></span>
<span data-ttu-id="b4d97-204">パイプを使用して値を **新しい変数** にパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4d97-204">You can pipe a value to **New-Variable** .</span></span>

## <span data-ttu-id="b4d97-205">出力</span><span class="sxs-lookup"><span data-stu-id="b4d97-205">OUTPUTS</span></span>

### <span data-ttu-id="b4d97-206">None または system.string です。</span><span class="sxs-lookup"><span data-stu-id="b4d97-206">None or System.Management.Automation.PSVariable</span></span>
<span data-ttu-id="b4d97-207">*PassThru* パラメーターを使用すると、 **new 変数** は新しい変数を表す **system.string オブジェクト** を生成します。</span><span class="sxs-lookup"><span data-stu-id="b4d97-207">When you use the *PassThru* parameter, **New-Variable** generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span>
<span data-ttu-id="b4d97-208">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="b4d97-208">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b4d97-209">注</span><span class="sxs-lookup"><span data-stu-id="b4d97-209">NOTES</span></span>

## <span data-ttu-id="b4d97-210">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b4d97-210">RELATED LINKS</span></span>

[<span data-ttu-id="b4d97-211">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="b4d97-211">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="b4d97-212">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="b4d97-212">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="b4d97-213">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="b4d97-213">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="b4d97-214">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="b4d97-214">Set-Variable</span></span>](Set-Variable.md)
