---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Module
ms.openlocfilehash: 7ee0f316b5aac138c8c6c5d2cf91ea3fa1c08151
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217480"
---
# <span data-ttu-id="bfd74-103">New-Module</span><span class="sxs-lookup"><span data-stu-id="bfd74-103">New-Module</span></span>

## <span data-ttu-id="bfd74-104">概要</span><span class="sxs-lookup"><span data-stu-id="bfd74-104">SYNOPSIS</span></span>
<span data-ttu-id="bfd74-105">メモリ内にのみ存在する新しい動的モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-105">Creates a new dynamic module that exists only in memory.</span></span>

## <span data-ttu-id="bfd74-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bfd74-106">SYNTAX</span></span>

### <span data-ttu-id="bfd74-107">ScriptBlock (既定値)</span><span class="sxs-lookup"><span data-stu-id="bfd74-107">ScriptBlock (Default)</span></span>

```
New-Module [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>] [-ReturnResult]
 [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="bfd74-108">Name</span><span class="sxs-lookup"><span data-stu-id="bfd74-108">Name</span></span>

```
New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>]
 [-ReturnResult] [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="bfd74-109">Description</span><span class="sxs-lookup"><span data-stu-id="bfd74-109">DESCRIPTION</span></span>

<span data-ttu-id="bfd74-110">コマンドレットでは、 `New-Module` スクリプトブロックから動的モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-110">The `New-Module` cmdlet creates a dynamic module from a script block.</span></span> <span data-ttu-id="bfd74-111">関数や変数などの動的モジュールのメンバーは、セッションで直ちに利用可能になり、セッションを終了するまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-111">The members of the dynamic module, such as functions and variables, are immediately available in the session and remain available until you close the session.</span></span>

<span data-ttu-id="bfd74-112">静的モジュール同様、既定では動的モジュール内のコマンドレットと関数がエクスポートされ、変数およびエイリアスはありません。</span><span class="sxs-lookup"><span data-stu-id="bfd74-112">Like static modules, by default, the cmdlets and functions in a dynamic module are exported and the variables and aliases are not.</span></span> <span data-ttu-id="bfd74-113">ただし、Export-ModuleMember コマンドレットとのパラメーターを使用して、 `New-Module` 既定値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-113">However, you can use the Export-ModuleMember cmdlet and the parameters of `New-Module` to override the defaults.</span></span>

<span data-ttu-id="bfd74-114">また、の **Ascustomobject** 出力パラメーターを使用し `New-Module` て、動的モジュールをカスタムオブジェクトとして返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-114">You can also use the **AsCustomObject** parameter of `New-Module` to return the dynamic module as a custom object.</span></span> <span data-ttu-id="bfd74-115">関数などモジュールのメンバーは、セッションにインポートされる代わりに、カスタム オブジェクトのスクリプト メソッドとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-115">The members of the modules, such as functions, are implemented as script methods of the custom object instead of being imported into the session.</span></span>

<span data-ttu-id="bfd74-116">動的モジュールはメモリにのみ存在し、ディスク上には存在しません。</span><span class="sxs-lookup"><span data-stu-id="bfd74-116">Dynamic modules exist only in memory, not on disk.</span></span> <span data-ttu-id="bfd74-117">すべてのモジュール同様、動的モジュールのメンバーはグローバル スコープの子であるプライベート モジュール スコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-117">Like all modules, the members of dynamic modules run in a private module scope that is a child of the global scope.</span></span> <span data-ttu-id="bfd74-118">Get-Module は動的モジュールを取得できませんが、Get-Command はエクスポートされたメンバーを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-118">Get-Module cannot get a dynamic module, but Get-Command can get the exported members.</span></span>

<span data-ttu-id="bfd74-119">動的モジュールをで使用できるようにするには `Get-Module` 、コマンドをパイプで `New-Module` インポートするか、を返すモジュールオブジェクトをパイプし `New-Module` `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-119">To make a dynamic module available to `Get-Module`, pipe a `New-Module` command to Import-Module, or pipe the module object that `New-Module` returns to `Import-Module`.</span></span> <span data-ttu-id="bfd74-120">この操作により、動的モジュールが `Get-Module` 一覧に追加されますが、モジュールをディスクに保存したり、永続化したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="bfd74-120">This action adds the dynamic module to the `Get-Module` list, but it does not save the module to disk or make it persistent.</span></span>

## <span data-ttu-id="bfd74-121">例</span><span class="sxs-lookup"><span data-stu-id="bfd74-121">EXAMPLES</span></span>

### <span data-ttu-id="bfd74-122">例 1: 動的モジュールを作成する</span><span class="sxs-lookup"><span data-stu-id="bfd74-122">Example 1: Create a dynamic module</span></span>

<span data-ttu-id="bfd74-123">この例では、という関数を使用して、新しい動的モジュールを作成し `Hello` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-123">This example creates a new dynamic module with a function called `Hello`.</span></span> <span data-ttu-id="bfd74-124">このコマンドは、新しい動的モジュールを表すモジュール オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-124">The command returns a module object that represents the new dynamic module.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

### <span data-ttu-id="bfd74-125">例 2: 動的モジュールと Get-Module と Get-Command の使用</span><span class="sxs-lookup"><span data-stu-id="bfd74-125">Example 2: Working with dynamic modules and Get-Module and Get-Command</span></span>

<span data-ttu-id="bfd74-126">この例では、コマンドレットによって動的モジュールが返されないことを示し `Get-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-126">This example demonstrates that dynamic modules are not returned by the `Get-Module` cmdlet.</span></span> <span data-ttu-id="bfd74-127">エクスポートされたメンバーは、コマンドレットによって返され `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-127">The members that they export are returned by the `Get-Command` cmdlet.</span></span>

```powershell
new-module -scriptblock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Module

Get-Command Hello
```

```Output
CommandType     Name   Definition
-----------     ----   ----------
Function        Hello  "Hello!"
```

### <span data-ttu-id="bfd74-128">例 3: 現在のセッションに変数をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="bfd74-128">Example 3: Export a variable into the current session</span></span>

<span data-ttu-id="bfd74-129">この例では、コマンドレットを使用して、 `Export-ModuleMember` 変数を現在のセッションにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bfd74-129">This example uses the `Export-ModuleMember` cmdlet to export a variable into the current session.</span></span>
<span data-ttu-id="bfd74-130">コマンドを使用しない `Export-ModuleMember` 場合、関数のみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-130">Without the `Export-ModuleMember` command, only the function is exported.</span></span>

```powershell
New-Module -ScriptBlock {$SayHelloHelp="Type 'SayHello', a space, and a name."; function SayHello ($name) { "Hello, $name" }; Export-ModuleMember -function SayHello -Variable SayHelloHelp}
$SayHelloHelp
```

```Output
Type 'SayHello', a space, and a name.
```

```powershell
SayHello Jeffrey
```

```Output
Hello, Jeffrey
```

<span data-ttu-id="bfd74-131">出力には、変数と関数が両方ともセッションにエクスポートされたことが示されます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-131">The output shows that both the variable and the function were exported into the session.</span></span>

### <span data-ttu-id="bfd74-132">例 4: Get-Module で動的モジュールを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="bfd74-132">Example 4: Make a dynamic module available to Get-Module</span></span>

<span data-ttu-id="bfd74-133">この例では、動的モジュールをにパイプ処理することによって、で動的モジュールを使用できるようにする方法を示し `Get-Module` `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-133">This example demonstrates that you can make a dynamic module available to `Get-Module` by piping the dynamic module to `Import-Module`.</span></span>

<span data-ttu-id="bfd74-134">`New-Module` コマンドレットにパイプ処理されたモジュールオブジェクトを作成し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-134">`New-Module` creates a module object that is piped to the `Import-Module` cmdlet.</span></span> <span data-ttu-id="bfd74-135">の **name** パラメーターは、 `New-Module` モジュールにフレンドリ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-135">The **Name** parameter of `New-Module` assigns a friendly name to the module.</span></span> <span data-ttu-id="bfd74-136">`Import-Module`は、既定ではオブジェクトを返さないため、このコマンドからの出力はありません。</span><span class="sxs-lookup"><span data-stu-id="bfd74-136">Because `Import-Module` does not return any objects by default, there is no output from this command.</span></span> <span data-ttu-id="bfd74-137">`Get-Module`**GreetingModule** が現在のセッションにインポートされていること。</span><span class="sxs-lookup"><span data-stu-id="bfd74-137">`Get-Module` that the **GreetingModule** has been imported into the current session.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}} -name GreetingModule | Import-Module
Get-Module
```

```Output
Name              : GreetingModule
Path              : d54dfdac-4531-4db2-9dec-0b4b9c57a1e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Command hello
```

```Output
CommandType     Name                                                               Definition
-----------     ----                                                               ----------
Function        Hello                                                              "Hello!"
```

<span data-ttu-id="bfd74-138">コマンドレットは、動的モジュールによって `Get-Command` エクスポートされる関数を示し `Hello` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-138">The `Get-Command` cmdlet shows the `Hello` function that the dynamic module exports.</span></span>

### <span data-ttu-id="bfd74-139">例 5: エクスポートされた関数を持つカスタムオブジェクトを生成する</span><span class="sxs-lookup"><span data-stu-id="bfd74-139">Example 5: Generate a custom object that has exported functions</span></span>

<span data-ttu-id="bfd74-140">この例では、の **Ascustomobject** パラメーターを使用して、エクスポートされた `New-Module` 関数を表すスクリプトメソッドを含むカスタムオブジェクトを生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-140">This example shows how to use the **AsCustomObject** parameter of `New-Module` to generate a custom object that has script methods that represent the exported functions.</span></span>

<span data-ttu-id="bfd74-141">`New-Module`コマンドレットでは、とという2つの関数を持つ動的モジュールを作成し `Hello` `Goodbye` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-141">The `New-Module` cmdlet creates a dynamic module with two functions, `Hello` and `Goodbye`.</span></span> <span data-ttu-id="bfd74-142">**Ascustomobject** パラメーターは、既定で生成される **PSModuleInfo** オブジェクトではなく、カスタムオブジェクトを作成し `New-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-142">The **AsCustomObject** parameter creates a custom object instead of the **PSModuleInfo** object that `New-Module` generates by default.</span></span> <span data-ttu-id="bfd74-143">このカスタムオブジェクトは変数に保存され `$m` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-143">This custom object is saved in the `$m` variable.</span></span>
<span data-ttu-id="bfd74-144">`$m`変数に値が割り当てられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bfd74-144">The `$m` variable appears to have no assigned value.</span></span>

```powershell
$m = New-Module -ScriptBlock {
  function Hello ($name) {"Hello, $name"}
  function Goodbye ($name) {"Goodbye, $name"}
} -AsCustomObject
$m
$m | Get-Member
```

```Output
TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Goodbye     ScriptMethod System.Object Goodbye();
Hello       ScriptMethod System.Object Hello();
```

```powershell
$m.goodbye("Jane")
```

```Output
Goodbye, Jane
```

```powershell
$m.hello("Manoj")
```

```Output
Hello, Manoj
```

<span data-ttu-id="bfd74-145">`$m`コマンドレットにパイプを `Get-Member` 設定すると、カスタムオブジェクトのプロパティとメソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-145">Piping `$m` to the `Get-Member` cmdlet displays the properties and methods of the custom object.</span></span> <span data-ttu-id="bfd74-146">出力は、オブジェクトに関数と関数を表すスクリプトメソッドがあることを示して `Hello` `Goodbye` います。</span><span class="sxs-lookup"><span data-stu-id="bfd74-146">The output shows that the object has script methods that represent the `Hello` and `Goodbye` functions.</span></span>
<span data-ttu-id="bfd74-147">最後に、これらのスクリプトメソッドを呼び出し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-147">Finally, we call these script methods and display the results.</span></span>

### <span data-ttu-id="bfd74-148">例 6: スクリプトブロックの結果を取得する</span><span class="sxs-lookup"><span data-stu-id="bfd74-148">Example 6: Get the results of the script block</span></span>

<span data-ttu-id="bfd74-149">この例では、 **Returnresult** パラメーターを使用して、モジュールオブジェクトを要求するのではなく、スクリプトブロックの実行結果を要求します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-149">This example uses the **ReturnResult** parameter to request the results of running the script block instead of requesting a module object.</span></span> <span data-ttu-id="bfd74-150">新しいモジュールのスクリプトブロックは関数を定義し、 `SayHello` 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-150">The script block in the new module defines the `SayHello` function and then calls the function.</span></span>

```powershell
New-Module -ScriptBlock {function SayHello {"Hello, World!"}; SayHello} -ReturnResult
```

```Output
Hello, World!
```

## <span data-ttu-id="bfd74-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bfd74-151">PARAMETERS</span></span>

### <span data-ttu-id="bfd74-152">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="bfd74-152">-ArgumentList</span></span>

<span data-ttu-id="bfd74-153">スクリプトブロックに渡されるパラメーター値である引数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-153">Specifies an array of arguments which are parameter values that are passed to the script block.</span></span> <span data-ttu-id="bfd74-154">**ArgumentList** の動作の詳細については、「 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfd74-154">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bfd74-155">-AsCustomObject 場合</span><span class="sxs-lookup"><span data-stu-id="bfd74-155">-AsCustomObject</span></span>

<span data-ttu-id="bfd74-156">このコマンドレットが、動的モジュールを表すカスタムオブジェクトを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-156">Indicates that this cmdlet returns a custom object that represents the dynamic module.</span></span> <span data-ttu-id="bfd74-157">モジュールのメンバーは、カスタム オブジェクトのスクリプト メソッドとして実装されますが、セッションにインポートされません。</span><span class="sxs-lookup"><span data-stu-id="bfd74-157">The module members are implemented as script methods of the custom object, but they are not imported into the session.</span></span> <span data-ttu-id="bfd74-158">カスタム オブジェクトを変数に保存し、ドット表記を使用してメンバーを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-158">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

<span data-ttu-id="bfd74-159">同じ名前を持つ複数のメンバーがモジュールに含まれている場合 (両方に名前が付けられた関数や変数など)、カスタムオブジェクトからアクセスできるのは、各名前を持つ1つのメンバーだけです。</span><span class="sxs-lookup"><span data-stu-id="bfd74-159">If the module has multiple members with the same name, such as a function and a variable that are both named A, only one member with each name can be accessed from the custom object.</span></span>

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

### <span data-ttu-id="bfd74-160">-コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bfd74-160">-Cmdlet</span></span>

<span data-ttu-id="bfd74-161">このコマンドレットがモジュールから現在のセッションにエクスポートするコマンドレットの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-161">Specifies an array of cmdlets that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="bfd74-162">コマンドレットのコンマ区切りのリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-162">Enter a comma-separated list of cmdlets.</span></span> <span data-ttu-id="bfd74-163">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-163">Wildcard characters are permitted.</span></span> <span data-ttu-id="bfd74-164">既定では、モジュール内のすべてのコマンドレットがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-164">By default, all cmdlets in the module are exported.</span></span>

<span data-ttu-id="bfd74-165">スクリプト ブロック内のコマンドレットは定義できませんが、コマンドレットがバイナリ モジュールからインポートされた場合、動的モジュールがコマンドレットを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-165">You cannot define cmdlets in a script block, but a dynamic module can include cmdlets if it imports the cmdlets from a binary module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bfd74-166">-関数</span><span class="sxs-lookup"><span data-stu-id="bfd74-166">-Function</span></span>

<span data-ttu-id="bfd74-167">このコマンドレットがモジュールから現在のセッションにエクスポートする関数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-167">Specifies an array of functions that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="bfd74-168">関数のコンマ区切りのリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-168">Enter a comma-separated list of functions.</span></span> <span data-ttu-id="bfd74-169">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-169">Wildcard characters are permitted.</span></span> <span data-ttu-id="bfd74-170">既定では、モジュールで定義されたすべての関数がエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-170">By default, all functions defined in a module are exported.</span></span>

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

### <span data-ttu-id="bfd74-171">-Name</span><span class="sxs-lookup"><span data-stu-id="bfd74-171">-Name</span></span>

<span data-ttu-id="bfd74-172">新しいモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-172">Specifies a name for the new module.</span></span> <span data-ttu-id="bfd74-173">また、パイプを使用してモジュール名を New-Module に渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-173">You can also pipe a module name to New-Module.</span></span>

<span data-ttu-id="bfd74-174">既定値は、で始まる自動生成された名前で、その `__DynamicModule_` 後に動的モジュールのパスを指定する GUID が続きます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-174">The default value is an autogenerated name that starts with `__DynamicModule_` and is followed by a GUID that specifies the path of the dynamic module.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bfd74-175">-ReturnResult</span><span class="sxs-lookup"><span data-stu-id="bfd74-175">-ReturnResult</span></span>

<span data-ttu-id="bfd74-176">このコマンドレットによってスクリプトブロックが実行され、モジュールオブジェクトを返す代わりにスクリプトブロックの結果が返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-176">Indicates that this cmdlet runs the script block and returns the script block results instead of returning a module object.</span></span>

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

### <span data-ttu-id="bfd74-177">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="bfd74-177">-ScriptBlock</span></span>

<span data-ttu-id="bfd74-178">動的モジュールの内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-178">Specifies the contents of the dynamic module.</span></span> <span data-ttu-id="bfd74-179">コンテンツを中かっこ () で囲み、 `{}` スクリプトブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-179">Enclose the contents in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="bfd74-180">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="bfd74-180">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bfd74-181">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfd74-181">CommonParameters</span></span>

<span data-ttu-id="bfd74-182">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bfd74-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bfd74-183">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfd74-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bfd74-184">入力</span><span class="sxs-lookup"><span data-stu-id="bfd74-184">INPUTS</span></span>

### <span data-ttu-id="bfd74-185">System.String</span><span class="sxs-lookup"><span data-stu-id="bfd74-185">System.String</span></span>

<span data-ttu-id="bfd74-186">このコマンドレットには、パイプを使用してモジュール名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-186">You can pipe a module name to this cmdlet.</span></span>

## <span data-ttu-id="bfd74-187">出力</span><span class="sxs-lookup"><span data-stu-id="bfd74-187">OUTPUTS</span></span>

### <span data-ttu-id="bfd74-188">PSModuleInfo、システムの管理...........</span><span class="sxs-lookup"><span data-stu-id="bfd74-188">System.Management.Automation.PSModuleInfo, System.Management.Automation.PSCustomObject, or None</span></span>

<span data-ttu-id="bfd74-189">このコマンドレットは、既定で **PSModuleInfo** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="bfd74-189">This cmdlet generates a **PSModuleInfo** object, by default.</span></span> <span data-ttu-id="bfd74-190">**Ascustomobject** いうパラメーターを使用すると、 **pscustomobject** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-190">If you use the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span> <span data-ttu-id="bfd74-191">**Returnresult** パラメーターを使用すると、動的モジュールのスクリプトブロックを評価した結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-191">If you use the **ReturnResult** parameter, it returns the result of evaluating the script block in the dynamic module.</span></span>

## <span data-ttu-id="bfd74-192">注</span><span class="sxs-lookup"><span data-stu-id="bfd74-192">NOTES</span></span>

<span data-ttu-id="bfd74-193">また、エイリアスでを参照することもでき `New-Module` `nmo` ます。</span><span class="sxs-lookup"><span data-stu-id="bfd74-193">You can also refer to `New-Module` by its alias, `nmo`.</span></span> <span data-ttu-id="bfd74-194">詳細については、「 [about_Aliases](About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfd74-194">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="bfd74-195">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bfd74-195">RELATED LINKS</span></span>

[<span data-ttu-id="bfd74-196">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="bfd74-196">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="bfd74-197">Get-Module</span><span class="sxs-lookup"><span data-stu-id="bfd74-197">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="bfd74-198">Import-Module</span><span class="sxs-lookup"><span data-stu-id="bfd74-198">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="bfd74-199">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="bfd74-199">Remove-Module</span></span>](Remove-Module.md)

