---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: d8410fbc2d3f29f0726f84ab151993a60ce95434
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599720"
---
# <span data-ttu-id="e8068-102">Format-List</span><span class="sxs-lookup"><span data-stu-id="e8068-102">Format-List</span></span>

## <span data-ttu-id="e8068-103">概要</span><span class="sxs-lookup"><span data-stu-id="e8068-103">SYNOPSIS</span></span>
<span data-ttu-id="e8068-104">出力の各プロパティは、新しい行に表示されるプロパティの一覧として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="e8068-104">Formats the output as a list of properties in which each property appears on a new line.</span></span>

## <span data-ttu-id="e8068-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e8068-105">SYNTAX</span></span>

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## <span data-ttu-id="e8068-106">Description</span><span class="sxs-lookup"><span data-stu-id="e8068-106">DESCRIPTION</span></span>

<span data-ttu-id="e8068-107">`Format-List`コマンドレットは、各プロパティが個別の行に表示されるプロパティの一覧として、コマンドの出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="e8068-107">The `Format-List` cmdlet formats the output of a command as a list of properties in which each property is displayed on a separate line.</span></span> <span data-ttu-id="e8068-108">を使用すると、 `Format-List` オブジェクトのすべてのプロパティまたは選択したプロパティを一覧として書式設定および表示できます (リスト \*)。</span><span class="sxs-lookup"><span data-stu-id="e8068-108">You can use `Format-List` to format and display all or selected properties of an object as a list (format-list \*).</span></span>

<span data-ttu-id="e8068-109">リスト内の各項目に対して、テーブルよりも多くの領域が使用可能であるため、PowerShell では、一覧に表示されるオブジェクトのプロパティが多くなり、プロパティ値が切り捨てられる可能性は低くなります。</span><span class="sxs-lookup"><span data-stu-id="e8068-109">Because more space is available for each item in a list than in a table, PowerShell displays more properties of the object in the list, and the property values are less likely to be truncated.</span></span>

## <span data-ttu-id="e8068-110">例</span><span class="sxs-lookup"><span data-stu-id="e8068-110">EXAMPLES</span></span>

### <span data-ttu-id="e8068-111">例 1: コンピューターサービスの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="e8068-111">Example 1: Format computer services</span></span>

```powershell
Get-Service | Format-List
```

<span data-ttu-id="e8068-112">このコマンドは、コンピューターのサービスに関する情報を一覧として書式設定します。</span><span class="sxs-lookup"><span data-stu-id="e8068-112">This command formats information about services on the computer as a list.</span></span> <span data-ttu-id="e8068-113">既定では、サービスは表として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="e8068-113">By default, the services are formatted as a table.</span></span> <span data-ttu-id="e8068-114">`Get-Service`コマンドレットは、コンピューター上のサービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="e8068-114">The `Get-Service` cmdlet gets objects representing the services on the computer.</span></span> <span data-ttu-id="e8068-115">パイプライン演算子 (|) は、パイプラインを介して結果をに渡し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-115">The pipeline operator (|) passes the results through the pipeline to `Format-List`.</span></span>
<span data-ttu-id="e8068-116">次に、 `Format-List` 一覧のサービス情報を書式設定し、表示するために既定の出力コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="e8068-116">Then, the `Format-List` command formats the service information in a list and sends it to the default output cmdlet for display.</span></span>

### <span data-ttu-id="e8068-117">例 2: TYPES.PS1XML ファイルの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="e8068-117">Example 2: Format PS1XML files</span></span>

<span data-ttu-id="e8068-118">これらのコマンドは、PowerShell ディレクトリ内の TYPES.PS1XML ファイルに関する情報を一覧として表示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-118">These commands display information about the PS1XML files in the PowerShell directory as a list.</span></span>

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

<span data-ttu-id="e8068-119">最初のコマンドは、ファイルを表すオブジェクトを取得し、変数に格納し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-119">The first command gets the objects representing the files and stores them in the `$A` variable.</span></span>

<span data-ttu-id="e8068-120">2番目のコマンドは、を使用し `Format-List` て、に格納されたオブジェクトに関する情報を書式設定し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-120">The second command uses `Format-List` to format information about objects stored in `$A`.</span></span> <span data-ttu-id="e8068-121">このコマンドは、 **InputObject** パラメーターを使用して変数をに渡します。これにより `Format-List` 、書式設定された出力が表示のために既定の出力コマンドレットに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e8068-121">This command uses the **InputObject** parameter to pass the variable to `Format-List`, which then sends the formatted output to the default output cmdlet for display.</span></span>

### <span data-ttu-id="e8068-122">例 3: プロセスのプロパティを名前で書式設定する</span><span class="sxs-lookup"><span data-stu-id="e8068-122">Example 3: Format process properties by name</span></span>

<span data-ttu-id="e8068-123">このコマンドは、コンピューター上の各プロセスの名前、基本優先度、および優先度クラスを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-123">This command displays the name, base priority, and priority class of each process on the computer.</span></span>

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

<span data-ttu-id="e8068-124">コマンドレットを使用して、 `Get-Process` 各プロセスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="e8068-124">It uses the `Get-Process` cmdlet to get an object representing each process.</span></span> <span data-ttu-id="e8068-125">パイプライン演算子 (|) は、パイプラインを介してプロセスオブジェクトをに渡し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-125">The pipeline operator (|) passes the process objects through the pipeline to `Format-List`.</span></span> <span data-ttu-id="e8068-126">`Format-List` 指定されたプロパティの一覧としてプロセスを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="e8068-126">`Format-List` formats the processes as a list of the specified properties.</span></span> <span data-ttu-id="e8068-127">*プロパティ* パラメーター名は省略可能であるため、省略できます。</span><span class="sxs-lookup"><span data-stu-id="e8068-127">The *Property* parameter name is optional, so you can omit it.</span></span>

### <span data-ttu-id="e8068-128">例 4: プロセスのすべてのプロパティを書式設定する</span><span class="sxs-lookup"><span data-stu-id="e8068-128">Example 4: Format all properties for a process</span></span>

<span data-ttu-id="e8068-129">このコマンドは、Winlogon プロセスのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-129">This command displays all of the properties of the Winlogon process.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="e8068-130">Get-Process コマンドレットを使用して、Winlogon プロセスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="e8068-130">It uses the Get-Process cmdlet to get an object representing the Winlogon process.</span></span> <span data-ttu-id="e8068-131">パイプライン演算子 (|) は、パイプラインを介して Winlogon プロセスオブジェクトをに渡し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-131">The pipeline operator (|) passes the Winlogon process object through the pipeline to `Format-List`.</span></span> <span data-ttu-id="e8068-132">このコマンドは、 *Property* パラメーターを使用してプロパティを指定し、を使用して \* すべてのプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-132">The command uses the *Property* parameter to specify the properties and the \* to indicate all properties.</span></span>
<span data-ttu-id="e8068-133">*Property* パラメーターの名前は省略可能なので、省略してコマンドをとして入力でき `Format-List *` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-133">Because the name of the *Property* parameter is optional, you can omit it and type the command as `Format-List *`.</span></span> <span data-ttu-id="e8068-134">`Format-List` は、結果を既定の出力コマンドレットに自動的に送信して表示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-134">`Format-List` automatically sends the results to the default output cmdlet for display.</span></span>

### <span data-ttu-id="e8068-135">例 5: 形式エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e8068-135">Example 5: Troubleshooting format errors</span></span>

<span data-ttu-id="e8068-136">次の例では、 **displayerror** パラメーターまたは **showerror** パラメーターを式に追加した結果を示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-136">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -DisplayError

DayOfWeek    : Friday
 $_ / $null  : #ERR

PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -ShowError

DayOfWeek    : Friday
 $_ / $null  :

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 7:59:23 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="e8068-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e8068-137">PARAMETERS</span></span>

### <span data-ttu-id="e8068-138">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="e8068-138">-DisplayError</span></span>

<span data-ttu-id="e8068-139">このコマンドレットがコマンドラインでエラーを表示することを示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-139">Indicates that this cmdlet displays errors at the command line.</span></span> <span data-ttu-id="e8068-140">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-List` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8068-140">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="e8068-141">-展開</span><span class="sxs-lookup"><span data-stu-id="e8068-141">-Expand</span></span>

<span data-ttu-id="e8068-142">書式設定されたコレクションオブジェクト、およびコレクション内のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8068-142">Specifies the formatted collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="e8068-143">このパラメーターは、ICollection (System.Collections) インターフェイスをサポートするオブジェクトを書式設定するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="e8068-143">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="e8068-144">既定値は EnumOnly です。</span><span class="sxs-lookup"><span data-stu-id="e8068-144">The default value is EnumOnly.</span></span> <span data-ttu-id="e8068-145">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8068-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e8068-146">Enumonly です.</span><span class="sxs-lookup"><span data-stu-id="e8068-146">EnumOnly.</span></span> <span data-ttu-id="e8068-147">コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-147">Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="e8068-148">CoreOnly。</span><span class="sxs-lookup"><span data-stu-id="e8068-148">CoreOnly.</span></span> <span data-ttu-id="e8068-149">コレクション オブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-149">Displays the properties of the collection object.</span></span>
- <span data-ttu-id="e8068-150">Both。</span><span class="sxs-lookup"><span data-stu-id="e8068-150">Both.</span></span> <span data-ttu-id="e8068-151">コレクション オブジェクトのプロパティと、コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-151">Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e8068-152">-Force</span><span class="sxs-lookup"><span data-stu-id="e8068-152">-Force</span></span>

<span data-ttu-id="e8068-153">このコマンドレットによってすべてのエラー情報が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-153">Indicates that this cmdlet displays all of the error information.</span></span> <span data-ttu-id="e8068-154">**Displayerror** パラメーターまたは **showerror** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="e8068-154">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="e8068-155">既定では、エラー オブジェクトがエラーまたは表示ストリームに書き込まれるとき、エラー情報の一部のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8068-155">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="e8068-156">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="e8068-156">-GroupBy</span></span>

<span data-ttu-id="e8068-157">共有プロパティまたは値に基づいて、グループ内の出力を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8068-157">Specifies the output in groups based on a shared property or value.</span></span> <span data-ttu-id="e8068-158">式または出力のプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="e8068-158">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="e8068-159">**GroupBy** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8068-159">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="e8068-160">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8068-160">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="e8068-161">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8068-161">Valid key-value pairs are:</span></span>

- <span data-ttu-id="e8068-162">名前 (またはラベル)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="e8068-162">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="e8068-163">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="e8068-163">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="e8068-164">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="e8068-164">FormatString - `<string>`</span></span>

<span data-ttu-id="e8068-165">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8068-165">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e8068-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e8068-166">-InputObject</span></span>

<span data-ttu-id="e8068-167">書式設定するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8068-167">Specifies the objects to be formatted.</span></span> <span data-ttu-id="e8068-168">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="e8068-168">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e8068-169">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="e8068-169">-Property</span></span>

<span data-ttu-id="e8068-170">表示するオブジェクト プロパティと、その表示順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8068-170">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="e8068-171">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8068-171">Wildcards are permitted.</span></span>

<span data-ttu-id="e8068-172">このパラメーターを省略した場合、表示されるプロパティは、表示されるオブジェクトに依存します。</span><span class="sxs-lookup"><span data-stu-id="e8068-172">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="e8068-173">パラメーター名 "Property" は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e8068-173">The parameter name "Property" is optional.</span></span> <span data-ttu-id="e8068-174">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8068-174">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="e8068-175">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8068-175">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="e8068-176">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8068-176">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="e8068-177">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8068-177">Valid key-value pairs are:</span></span>

- <span data-ttu-id="e8068-178">名前 (またはラベル)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="e8068-178">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="e8068-179">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="e8068-179">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="e8068-180">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="e8068-180">FormatString - `<string>`</span></span>

<span data-ttu-id="e8068-181">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8068-181">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e8068-182">-ShowError</span><span class="sxs-lookup"><span data-stu-id="e8068-182">-ShowError</span></span>

<span data-ttu-id="e8068-183">コマンドレットがパイプラインを介してエラーを送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="e8068-183">Indicates that the cmdlet sends errors through the pipeline.</span></span> <span data-ttu-id="e8068-184">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-List` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8068-184">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="e8068-185">-ビュー</span><span class="sxs-lookup"><span data-stu-id="e8068-185">-View</span></span>

<span data-ttu-id="e8068-186">代替リスト形式またはビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8068-186">Specifies the name of an alternate list format or view.</span></span> <span data-ttu-id="e8068-187">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8068-187">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="e8068-188">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8068-188">CommonParameters</span></span>

<span data-ttu-id="e8068-189">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e8068-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e8068-190">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8068-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e8068-191">入力</span><span class="sxs-lookup"><span data-stu-id="e8068-191">INPUTS</span></span>

### <span data-ttu-id="e8068-192">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="e8068-192">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="e8068-193">パイプを使用して任意のオブジェクトをにパイプすることができ `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-193">You can pipe any object to `Format-List`.</span></span>

## <span data-ttu-id="e8068-194">出力</span><span class="sxs-lookup"><span data-stu-id="e8068-194">OUTPUTS</span></span>

### <span data-ttu-id="e8068-195">Microsoft. PowerShell. 内部形式</span><span class="sxs-lookup"><span data-stu-id="e8068-195">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="e8068-196">`Format-List` リストを表す書式オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e8068-196">`Format-List` returns the format objects that represent the list.</span></span>

## <span data-ttu-id="e8068-197">注</span><span class="sxs-lookup"><span data-stu-id="e8068-197">NOTES</span></span>

<span data-ttu-id="e8068-198">Format-List は、その組み込みエイリアスである FL を使用して参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8068-198">You can also refer to Format-List by its built-in alias, FL.</span></span> <span data-ttu-id="e8068-199">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8068-199">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="e8068-200">形式のコマンドレット (など) では、 `Format-List` 表示されるデータは配置されますが、表示されません。</span><span class="sxs-lookup"><span data-stu-id="e8068-200">The format cmdlets, such as `Format-List`, arrange the data to be displayed but do not display it.</span></span>
<span data-ttu-id="e8068-201">データは、PowerShell の出力機能と、Out 動詞 (Out コマンドレット) を含むコマンドレット (やなど) によって表示され `Out-Host` `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-201">The data is displayed by the output features of PowerShell and by the cmdlets that contain the Out verb (the Out cmdlets), such as `Out-Host` or `Out-File`.</span></span>

<span data-ttu-id="e8068-202">Format コマンドレットを使用しない場合、PowerShell では、表示される各オブジェクトに既定の形式が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e8068-202">If you do not use a format cmdlet, PowerShell applies that default format for each object that it displays.</span></span>

<span data-ttu-id="e8068-203">**GroupBy** パラメーターは、オブジェクトが並べ替えられていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e8068-203">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="e8068-204">を使用してオブジェクトをグループ化する前に、Sort-Object を使用し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-204">Use Sort-Object before using `Format-List` to group the objects.</span></span>

<span data-ttu-id="e8068-205">**View** パラメーターを使用すると、テーブルの代替形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8068-205">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="e8068-206">PowerShell ディレクトリ内のファイルで定義されているビューを使用することも `*.format.PS1XML` 、新しい types.ps1xml ファイルに独自のビューを作成して、Update-FormatData コマンドレットを使用してそれらを powershell に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="e8068-206">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory, or you can create your own views in new PS1XML files and use the Update-FormatData cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="e8068-207">**View** パラメーターの代替ビューでは、リスト形式を使用する必要があります。そうでない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e8068-207">The alternate view for the **View** parameter must use the list format, otherwise, the command fails.</span></span> <span data-ttu-id="e8068-208">代替ビューがテーブルの場合は、を使用 `Format-Table` します。</span><span class="sxs-lookup"><span data-stu-id="e8068-208">If the alternate view is a table, use `Format-Table`.</span></span> <span data-ttu-id="e8068-209">代替ビューが一覧またはテーブルではない場合は、を使用し `Format-Custom` ます。</span><span class="sxs-lookup"><span data-stu-id="e8068-209">If the alternate view is not a list or a table, use `Format-Custom`.</span></span>

## <span data-ttu-id="e8068-210">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e8068-210">RELATED LINKS</span></span>

[<span data-ttu-id="e8068-211">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="e8068-211">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="e8068-212">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="e8068-212">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="e8068-213">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="e8068-213">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="e8068-214">Format-Table</span><span class="sxs-lookup"><span data-stu-id="e8068-214">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="e8068-215">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="e8068-215">Format-Wide</span></span>](Format-Wide.md)
