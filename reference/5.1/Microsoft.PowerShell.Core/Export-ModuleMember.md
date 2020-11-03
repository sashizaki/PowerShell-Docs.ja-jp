---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-modulemember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ModuleMember
ms.openlocfilehash: a8f059a5f7ae36415054dd94f87a1224d64c2cbf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212064"
---
# <span data-ttu-id="71d07-103">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="71d07-103">Export-ModuleMember</span></span>

## <span data-ttu-id="71d07-104">概要</span><span class="sxs-lookup"><span data-stu-id="71d07-104">SYNOPSIS</span></span>
<span data-ttu-id="71d07-105">エクスポートするモジュール メンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="71d07-105">Specifies the module members that are exported.</span></span>

## <span data-ttu-id="71d07-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71d07-106">SYNTAX</span></span>

```
Export-ModuleMember [[-Function] <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="71d07-107">Description</span><span class="sxs-lookup"><span data-stu-id="71d07-107">DESCRIPTION</span></span>

<span data-ttu-id="71d07-108">**Export-modulemember** コマンドレットは、スクリプトモジュール (hbase-runner.psm1) ファイル、または New-Module コマンドレットを使用して作成された動的モジュールからエクスポートされるモジュールメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="71d07-108">The **Export-ModuleMember** cmdlet specifies the module members that are exported from a script module (.psm1) file, or from a dynamic module created by using the New-Module cmdlet.</span></span>
<span data-ttu-id="71d07-109">モジュールメンバーには、コマンドレット、関数、変数、およびエイリアスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="71d07-109">Module members include cmdlets, functions, variables, and aliases.</span></span>
<span data-ttu-id="71d07-110">このコマンドレットは、スクリプト モジュール ファイルまたは動的モジュールでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="71d07-110">This cmdlet can be used only in a script module file or a dynamic module.</span></span>

<span data-ttu-id="71d07-111">スクリプトモジュールに **export-modulemember** コマンドが含まれていない場合、スクリプトモジュール内の関数と別名はエクスポートされますが、変数はエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="71d07-111">If a script module does not include an **Export-ModuleMember** command, the functions and aliases in the script module are exported, but the variables are not.</span></span>
<span data-ttu-id="71d07-112">スクリプトモジュールに **export-modulemember** コマンドが含まれている場合は、 **export-modulemember** コマンドで指定されたメンバーのみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="71d07-112">When a script module includes **Export-ModuleMember** commands, only the members specified in the **Export-ModuleMember** commands are exported.</span></span>
<span data-ttu-id="71d07-113">また、 **export-modulemember** を使用して、スクリプトモジュールが他のモジュールからインポートしたメンバーを抑制またはエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="71d07-113">You can also use **Export-ModuleMember** to suppress or export members that the script module imports from other modules.</span></span>

<span data-ttu-id="71d07-114">**Export-modulemember** コマンドは省略可能ですが、ベストプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="71d07-114">An **Export-ModuleMember** command is optional, but it is a best practice.</span></span>
<span data-ttu-id="71d07-115">コマンドが既定値を確認する場合でも、モジュールの作成者の意図は示されます。</span><span class="sxs-lookup"><span data-stu-id="71d07-115">Even if the command confirms the default values, it demonstrates the intention of the module author.</span></span>

## <span data-ttu-id="71d07-116">例</span><span class="sxs-lookup"><span data-stu-id="71d07-116">EXAMPLES</span></span>

### <span data-ttu-id="71d07-117">例 1: スクリプトモジュールで関数とエイリアスをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="71d07-117">Example 1: Export functions and aliases in a script module</span></span>

```powershell
Export-ModuleMember -Function * -Alias *
```

<span data-ttu-id="71d07-118">このコマンドは、スクリプトモジュールで定義されているすべての関数とエイリアスをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="71d07-118">This command exports all the functions and aliases defined in the script module.</span></span>

### <span data-ttu-id="71d07-119">例 2: 特定のエイリアスと関数をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="71d07-119">Example 2: Export specific aliases and functions</span></span>

```powershell
Export-ModuleMember -Function Get-Test, New-Test, Start-Test -Alias gtt, ntt, stt
```

<span data-ttu-id="71d07-120">このコマンドは、スクリプト モジュールで定義されている 3 つのエイリアスと 3 つの関数をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="71d07-120">This command exports three aliases and three functions defined in the script module.</span></span>

<span data-ttu-id="71d07-121">このコマンド形式を使用すると、モジュール メンバーの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="71d07-121">You can use this command format to specify the names of module members.</span></span>

### <span data-ttu-id="71d07-122">例 3: メンバーをエクスポートしない</span><span class="sxs-lookup"><span data-stu-id="71d07-122">Example 3: Export no members</span></span>

```powershell
Export-ModuleMember
```

<span data-ttu-id="71d07-123">このコマンドは、スクリプト モジュールで定義されているメンバーはエクスポートされないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="71d07-123">This command specifies that no members defined in the script module are exported.</span></span>

<span data-ttu-id="71d07-124">このコマンドでは、モジュール メンバーをエクスポートできませんが、メンバーは非表示になりません。</span><span class="sxs-lookup"><span data-stu-id="71d07-124">This command prevents the module members from being exported, but it does not hide the members.</span></span>
<span data-ttu-id="71d07-125">ユーザーは、モジュール メンバーの読み取りとコピー、または、呼び出し演算子 (&) を使用してエクスポートされていないモジュール メンバーを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="71d07-125">Users can read and copy module members or use the call operator (&) to invoke module members that are not exported.</span></span>

### <span data-ttu-id="71d07-126">例 4: 特定の変数をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="71d07-126">Example 4: Export a specific variable</span></span>

```powershell
Export-ModuleMember -Variable increment
```

<span data-ttu-id="71d07-127">このコマンドは、スクリプト モジュールから $increment 変数のみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="71d07-127">This command exports only the $increment variable from the script module.</span></span>
<span data-ttu-id="71d07-128">他のメンバーはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="71d07-128">No other members are exported.</span></span>

<span data-ttu-id="71d07-129">変数をエクスポートする場合、モジュール内の関数をエクスポートするだけでなく、 **export-modulemember** コマンドには、すべての関数の名前と変数の名前を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="71d07-129">If you want to export a variable, in addition to exporting the functions in a module, the **Export-ModuleMember** command must include the names of all of the functions and the name of the variable.</span></span>

### <span data-ttu-id="71d07-130">例 5: 複数のエクスポートコマンド</span><span class="sxs-lookup"><span data-stu-id="71d07-130">Example 5: Multiple export commands</span></span>

```powershell
# From TestModule.psm1
Function New-Test
{
    Write-Output 'I am New-Test function'
}
Export-ModuleMember -Function New-Test

function Validate-Test
{
    Write-Output 'I am Validate-Test function'
}
function Start-Test
{
    Write-Output 'I am Start-Test function'
}
Set-Alias stt Start-Test
Export-ModuleMember -Function Start-Test -Alias stt
```

<span data-ttu-id="71d07-131">これらのコマンドは、スクリプトモジュール (hbase-runner.psm1) ファイルで複数の **export-modulemember** コマンドがどのように解釈されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="71d07-131">These commands show how multiple **Export-ModuleMember** commands are interpreted in a script module (.psm1) file.</span></span>

<span data-ttu-id="71d07-132">これらのコマンドは、3 つの関数と 1 つのエイリアスを作成し、このうちの 2 つの関数とエイリアスをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="71d07-132">These commands create three functions and one alias, and then they export two of the functions and the alias.</span></span>

<span data-ttu-id="71d07-133">**Export-modulemember** コマンドを使用しない場合、3つの関数とエイリアスのすべてがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="71d07-133">Without the **Export-ModuleMember** commands, all three of the functions and the alias would be exported.</span></span>
<span data-ttu-id="71d07-134">**Export-modulemember** コマンドでは、 **新しい-TEST** **関数と** STT エイリアスだけがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="71d07-134">With the **Export-ModuleMember** commands, only the **New-Test** and **Start-Test** functions and the STT alias are exported.</span></span>

### <span data-ttu-id="71d07-135">例 6: 動的モジュールのメンバーをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="71d07-135">Example 6: Export members in a dynamic module</span></span>

```powershell
New-Module -Script {function SayHello {"Hello!"}; Set-Alias Hi SayHello; Export-ModuleMember -Alias Hi -Function SayHello}
```

<span data-ttu-id="71d07-136">このコマンドは、 **新しいモジュール** コマンドレットを使用して作成された動的モジュールで Export-ModuleMember を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="71d07-136">This command shows how to use Export-ModuleMember in a dynamic module that is created by using the **New-Module** cmdlet.</span></span>

<span data-ttu-id="71d07-137">この例では、 **export-modulemember** を使用して、動的モジュールの Hi エイリアスと **SayHello** 関数の両方をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="71d07-137">In this example, **Export-ModuleMember** is used to export both the Hi alias and the **SayHello** function in the dynamic module.</span></span>

### <span data-ttu-id="71d07-138">例 7: 1 つのコマンドで関数を宣言およびエクスポートする</span><span class="sxs-lookup"><span data-stu-id="71d07-138">Example 7: Declare and export a function in a single command</span></span>

```powershell
# From TestModule.psm1
function Export
{
  param (
    [Parameter(Mandatory=$true)]
    [ValidateSet("function","variable")]
    $Type,
    [Parameter(Mandatory=$true)]
    $Name,
    [Parameter(Mandatory=$true)]
    $Value
    )

    if ($Type -eq "function")
    {
        Set-item "function:script:$Name" $Value
        Export-ModuleMember $Name
    }
    else
    {
    Set-Variable -scope Script $Name $Value
    Export-ModuleMember -variable $Name
    }
}

Export function New-Test {Write-Output 'I am New-Test function'}
function helper {Write-Output 'I am helper function'}

Export variable Interval 0
$Interval = 2
```

<span data-ttu-id="71d07-139">この例には、関数を宣言したり変数を作成したりする **Export** という名前の関数が含まれています。その後、関数 `Export-ModuleMember` または変数に対してコマンドを記述します。</span><span class="sxs-lookup"><span data-stu-id="71d07-139">This example includes a function named **Export** that declares a function or creates a variable, and then writes an `Export-ModuleMember` command for the function or variable.</span></span>
<span data-ttu-id="71d07-140">これにより、1 つのコマンドで関数または変数を宣言し、エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="71d07-140">This lets you declare and export a function or variable in a single command.</span></span>

<span data-ttu-id="71d07-141">**Export** 関数を使用するには、スクリプトモジュールにそれを含めます。</span><span class="sxs-lookup"><span data-stu-id="71d07-141">To use the **Export** function, include it in your script module.</span></span>
<span data-ttu-id="71d07-142">関数をエクスポートするには、 `Export` **function** キーワードの前に「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="71d07-142">To export a function, type `Export` before the **Function** keyword.</span></span>

<span data-ttu-id="71d07-143">変数をエクスポートするには、次の形式を使用して変数を宣言し、その値を設定します。</span><span class="sxs-lookup"><span data-stu-id="71d07-143">To export a variable, use the following format to declare the variable and set its value:</span></span>

`Export variable <variable-name> <value>`

<span data-ttu-id="71d07-144">例では、コマンドは正しい形式を示しています。</span><span class="sxs-lookup"><span data-stu-id="71d07-144">The commands in the example show the correct format.</span></span>
<span data-ttu-id="71d07-145">この例では、 **新しい-Test** 関数と $Interval 変数のみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="71d07-145">In this example, only the **New-Test** function and the $Interval variable are exported.</span></span>

## <span data-ttu-id="71d07-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71d07-146">PARAMETERS</span></span>

### <span data-ttu-id="71d07-147">-エイリアス</span><span class="sxs-lookup"><span data-stu-id="71d07-147">-Alias</span></span>

<span data-ttu-id="71d07-148">スクリプト モジュール ファイルからエクスポートされるエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="71d07-148">Specifies the aliases that are exported from the script module file.</span></span>
<span data-ttu-id="71d07-149">エイリアス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="71d07-149">Enter the alias names.</span></span>
<span data-ttu-id="71d07-150">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="71d07-150">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="71d07-151">-コマンドレット</span><span class="sxs-lookup"><span data-stu-id="71d07-151">-Cmdlet</span></span>

<span data-ttu-id="71d07-152">スクリプト モジュール ファイルからエクスポートされるコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="71d07-152">Specifies the cmdlets that are exported from the script module file.</span></span>
<span data-ttu-id="71d07-153">コマンドレット名を入力します。</span><span class="sxs-lookup"><span data-stu-id="71d07-153">Enter the cmdlet names.</span></span>
<span data-ttu-id="71d07-154">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="71d07-154">Wildcard characters are permitted.</span></span>

<span data-ttu-id="71d07-155">コマンドレットをスクリプト モジュール ファイルに作成することはできませんが、バイナリ モジュールからスクリプト モジュールにコマンドレットをインポートし、その後スクリプト モジュールからコマンドレットを再度エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="71d07-155">You cannot create cmdlets in a script module file, but you can import cmdlets from a binary module into a script module and re-export them from the script module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="71d07-156">-関数</span><span class="sxs-lookup"><span data-stu-id="71d07-156">-Function</span></span>

<span data-ttu-id="71d07-157">スクリプト モジュール ファイルからエクスポートされる関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="71d07-157">Specifies the functions that are exported from the script module file.</span></span>
<span data-ttu-id="71d07-158">関数名を入力します。</span><span class="sxs-lookup"><span data-stu-id="71d07-158">Enter the function names.</span></span>
<span data-ttu-id="71d07-159">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="71d07-159">Wildcard characters are permitted.</span></span>
<span data-ttu-id="71d07-160">パイプを使用して関数名の文字列を **export-modulemember** にパイプ処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="71d07-160">You can also pipe function name strings to **Export-ModuleMember** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="71d07-161">-Variable</span><span class="sxs-lookup"><span data-stu-id="71d07-161">-Variable</span></span>

<span data-ttu-id="71d07-162">スクリプト モジュール ファイルからエクスポートされる変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="71d07-162">Specifies the variables that are exported from the script module file.</span></span>
<span data-ttu-id="71d07-163">ドル記号を付けずに変数名を入力します。</span><span class="sxs-lookup"><span data-stu-id="71d07-163">Enter the variable names, without a dollar sign.</span></span>
<span data-ttu-id="71d07-164">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="71d07-164">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="71d07-165">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="71d07-165">CommonParameters</span></span>

<span data-ttu-id="71d07-166">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="71d07-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="71d07-167">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71d07-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="71d07-168">入力</span><span class="sxs-lookup"><span data-stu-id="71d07-168">INPUTS</span></span>

### <span data-ttu-id="71d07-169">System.String</span><span class="sxs-lookup"><span data-stu-id="71d07-169">System.String</span></span>

<span data-ttu-id="71d07-170">パイプを使用して関数名の文字列をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="71d07-170">You can pipe function name strings to this cmdlet.</span></span>

## <span data-ttu-id="71d07-171">出力</span><span class="sxs-lookup"><span data-stu-id="71d07-171">OUTPUTS</span></span>

### <span data-ttu-id="71d07-172">なし</span><span class="sxs-lookup"><span data-stu-id="71d07-172">None</span></span>

<span data-ttu-id="71d07-173">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="71d07-173">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="71d07-174">注</span><span class="sxs-lookup"><span data-stu-id="71d07-174">NOTES</span></span>

* <span data-ttu-id="71d07-175">エクスポートされたメンバーの一覧からメンバーを除外するには、 **export-modulemember** コマンドを追加します。このコマンドは、他のすべてのメンバーを一覧表示し、除外するメンバーを除外します。</span><span class="sxs-lookup"><span data-stu-id="71d07-175">To exclude a member from the list of exported members, add an **Export-ModuleMember** command that lists all other members but omits the member that you want to exclude.</span></span>

## <span data-ttu-id="71d07-176">関連リンク</span><span class="sxs-lookup"><span data-stu-id="71d07-176">RELATED LINKS</span></span>

[<span data-ttu-id="71d07-177">Get-Module</span><span class="sxs-lookup"><span data-stu-id="71d07-177">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="71d07-178">Import-Module</span><span class="sxs-lookup"><span data-stu-id="71d07-178">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="71d07-179">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="71d07-179">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="71d07-180">about_Modules</span><span class="sxs-lookup"><span data-stu-id="71d07-180">about_Modules</span></span>](About/about_Modules.md)
