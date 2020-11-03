---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: a025432e8aed93f6668c676161c21377d0ba225c
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219472"
---
# <span data-ttu-id="641e0-103">Format-List</span><span class="sxs-lookup"><span data-stu-id="641e0-103">Format-List</span></span>

## <span data-ttu-id="641e0-104">概要</span><span class="sxs-lookup"><span data-stu-id="641e0-104">SYNOPSIS</span></span>
<span data-ttu-id="641e0-105">出力の各プロパティは、新しい行に表示されるプロパティの一覧として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="641e0-105">Formats the output as a list of properties in which each property appears on a new line.</span></span>

## <span data-ttu-id="641e0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="641e0-106">SYNTAX</span></span>

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## <span data-ttu-id="641e0-107">Description</span><span class="sxs-lookup"><span data-stu-id="641e0-107">DESCRIPTION</span></span>

<span data-ttu-id="641e0-108">`Format-List`コマンドレットは、各プロパティが個別の行に表示されるプロパティの一覧として、コマンドの出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="641e0-108">The `Format-List` cmdlet formats the output of a command as a list of properties in which each property is displayed on a separate line.</span></span> <span data-ttu-id="641e0-109">を使用すると、 `Format-List` オブジェクトのすべてのプロパティまたは選択したプロパティを一覧として書式設定および表示できます (リスト \*)。</span><span class="sxs-lookup"><span data-stu-id="641e0-109">You can use `Format-List` to format and display all or selected properties of an object as a list (format-list \*).</span></span>

<span data-ttu-id="641e0-110">リスト内の各項目に対して、テーブルよりも多くの領域が使用可能であるため、PowerShell では、一覧に表示されるオブジェクトのプロパティが多くなり、プロパティ値が切り捨てられる可能性は低くなります。</span><span class="sxs-lookup"><span data-stu-id="641e0-110">Because more space is available for each item in a list than in a table, PowerShell displays more properties of the object in the list, and the property values are less likely to be truncated.</span></span>

## <span data-ttu-id="641e0-111">例</span><span class="sxs-lookup"><span data-stu-id="641e0-111">EXAMPLES</span></span>

### <span data-ttu-id="641e0-112">例 1: コンピューターサービスの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="641e0-112">Example 1: Format computer services</span></span>

```powershell
Get-Service | Format-List
```

<span data-ttu-id="641e0-113">このコマンドは、コンピューターのサービスに関する情報を一覧として書式設定します。</span><span class="sxs-lookup"><span data-stu-id="641e0-113">This command formats information about services on the computer as a list.</span></span> <span data-ttu-id="641e0-114">既定では、サービスは表として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="641e0-114">By default, the services are formatted as a table.</span></span> <span data-ttu-id="641e0-115">`Get-Service`コマンドレットは、コンピューター上のサービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="641e0-115">The `Get-Service` cmdlet gets objects representing the services on the computer.</span></span> <span data-ttu-id="641e0-116">パイプライン演算子 (|) は、パイプラインを介して結果をに渡し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-116">The pipeline operator (|) passes the results through the pipeline to `Format-List`.</span></span>
<span data-ttu-id="641e0-117">次に、 `Format-List` 一覧のサービス情報を書式設定し、表示するために既定の出力コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="641e0-117">Then, the `Format-List` command formats the service information in a list and sends it to the default output cmdlet for display.</span></span>

### <span data-ttu-id="641e0-118">例 2: TYPES.PS1XML ファイルの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="641e0-118">Example 2: Format PS1XML files</span></span>

<span data-ttu-id="641e0-119">これらのコマンドは、PowerShell ディレクトリ内の TYPES.PS1XML ファイルに関する情報を一覧として表示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-119">These commands display information about the PS1XML files in the PowerShell directory as a list.</span></span>

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

<span data-ttu-id="641e0-120">最初のコマンドは、ファイルを表すオブジェクトを取得し、変数に格納し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-120">The first command gets the objects representing the files and stores them in the `$A` variable.</span></span>

<span data-ttu-id="641e0-121">2番目のコマンドは、を使用し `Format-List` て、に格納されたオブジェクトに関する情報を書式設定し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-121">The second command uses `Format-List` to format information about objects stored in `$A`.</span></span> <span data-ttu-id="641e0-122">このコマンドは、 **InputObject** パラメーターを使用して変数をに渡します。これにより `Format-List` 、書式設定された出力が表示のために既定の出力コマンドレットに送信されます。</span><span class="sxs-lookup"><span data-stu-id="641e0-122">This command uses the **InputObject** parameter to pass the variable to `Format-List`, which then sends the formatted output to the default output cmdlet for display.</span></span>

### <span data-ttu-id="641e0-123">例 3: プロセスのプロパティを名前で書式設定する</span><span class="sxs-lookup"><span data-stu-id="641e0-123">Example 3: Format process properties by name</span></span>

<span data-ttu-id="641e0-124">このコマンドは、コンピューター上の各プロセスの名前、基本優先度、および優先度クラスを表示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-124">This command displays the name, base priority, and priority class of each process on the computer.</span></span>

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

<span data-ttu-id="641e0-125">コマンドレットを使用して、 `Get-Process` 各プロセスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="641e0-125">It uses the `Get-Process` cmdlet to get an object representing each process.</span></span> <span data-ttu-id="641e0-126">パイプライン演算子 (|) は、パイプラインを介してプロセスオブジェクトをに渡し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-126">The pipeline operator (|) passes the process objects through the pipeline to `Format-List`.</span></span> <span data-ttu-id="641e0-127">`Format-List` 指定されたプロパティの一覧としてプロセスを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="641e0-127">`Format-List` formats the processes as a list of the specified properties.</span></span> <span data-ttu-id="641e0-128">*プロパティ* パラメーター名は省略可能であるため、省略できます。</span><span class="sxs-lookup"><span data-stu-id="641e0-128">The *Property* parameter name is optional, so you can omit it.</span></span>

### <span data-ttu-id="641e0-129">例 4: プロセスのすべてのプロパティを書式設定する</span><span class="sxs-lookup"><span data-stu-id="641e0-129">Example 4: Format all properties for a process</span></span>

<span data-ttu-id="641e0-130">このコマンドは、Winlogon プロセスのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-130">This command displays all of the properties of the Winlogon process.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="641e0-131">Get-Process コマンドレットを使用して、Winlogon プロセスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="641e0-131">It uses the Get-Process cmdlet to get an object representing the Winlogon process.</span></span> <span data-ttu-id="641e0-132">パイプライン演算子 (|) は、パイプラインを介して Winlogon プロセスオブジェクトをに渡し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-132">The pipeline operator (|) passes the Winlogon process object through the pipeline to `Format-List`.</span></span> <span data-ttu-id="641e0-133">このコマンドは、 *Property* パラメーターを使用してプロパティを指定し、を使用して \* すべてのプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-133">The command uses the *Property* parameter to specify the properties and the \* to indicate all properties.</span></span>
<span data-ttu-id="641e0-134">*Property* パラメーターの名前は省略可能なので、省略してコマンドをとして入力でき `Format-List *` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-134">Because the name of the *Property* parameter is optional, you can omit it and type the command as `Format-List *`.</span></span> <span data-ttu-id="641e0-135">`Format-List` は、結果を既定の出力コマンドレットに自動的に送信して表示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-135">`Format-List` automatically sends the results to the default output cmdlet for display.</span></span>

### <span data-ttu-id="641e0-136">例 5: 形式エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="641e0-136">Example 5: Troubleshooting format errors</span></span>

<span data-ttu-id="641e0-137">次の例では、 **displayerror** パラメーターまたは **showerror** パラメーターを式に追加した結果を示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-137">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

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

## <span data-ttu-id="641e0-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="641e0-138">PARAMETERS</span></span>

### <span data-ttu-id="641e0-139">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="641e0-139">-DisplayError</span></span>

<span data-ttu-id="641e0-140">このコマンドレットがコマンドラインでエラーを表示することを示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-140">Indicates that this cmdlet displays errors at the command line.</span></span> <span data-ttu-id="641e0-141">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-List` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="641e0-141">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="641e0-142">-展開</span><span class="sxs-lookup"><span data-stu-id="641e0-142">-Expand</span></span>

<span data-ttu-id="641e0-143">書式設定されたコレクションオブジェクト、およびコレクション内のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="641e0-143">Specifies the formatted collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="641e0-144">このパラメーターは、ICollection (System.Collections) インターフェイスをサポートするオブジェクトを書式設定するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="641e0-144">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="641e0-145">既定値は EnumOnly です。</span><span class="sxs-lookup"><span data-stu-id="641e0-145">The default value is EnumOnly.</span></span> <span data-ttu-id="641e0-146">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="641e0-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="641e0-147">Enumonly です.</span><span class="sxs-lookup"><span data-stu-id="641e0-147">EnumOnly.</span></span> <span data-ttu-id="641e0-148">コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-148">Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="641e0-149">CoreOnly。</span><span class="sxs-lookup"><span data-stu-id="641e0-149">CoreOnly.</span></span> <span data-ttu-id="641e0-150">コレクション オブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-150">Displays the properties of the collection object.</span></span>
- <span data-ttu-id="641e0-151">Both。</span><span class="sxs-lookup"><span data-stu-id="641e0-151">Both.</span></span> <span data-ttu-id="641e0-152">コレクション オブジェクトのプロパティと、コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-152">Displays the properties of the collection object and the properties of objects in the collection.</span></span>

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

### <span data-ttu-id="641e0-153">-Force</span><span class="sxs-lookup"><span data-stu-id="641e0-153">-Force</span></span>

<span data-ttu-id="641e0-154">このコマンドレットによってすべてのエラー情報が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-154">Indicates that this cmdlet displays all of the error information.</span></span> <span data-ttu-id="641e0-155">**Displayerror** パラメーターまたは **showerror** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="641e0-155">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="641e0-156">既定では、エラー オブジェクトがエラーまたは表示ストリームに書き込まれるとき、エラー情報の一部のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="641e0-156">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="641e0-157">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="641e0-157">-GroupBy</span></span>

<span data-ttu-id="641e0-158">共有プロパティまたは値に基づいて、グループ内の出力を指定します。</span><span class="sxs-lookup"><span data-stu-id="641e0-158">Specifies the output in groups based on a shared property or value.</span></span> <span data-ttu-id="641e0-159">式または出力のプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="641e0-159">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="641e0-160">**GroupBy** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="641e0-160">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="641e0-161">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="641e0-161">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="641e0-162">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="641e0-162">Valid key-value pairs are:</span></span>

- <span data-ttu-id="641e0-163">名前 (またはラベル)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="641e0-163">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="641e0-164">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="641e0-164">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="641e0-165">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="641e0-165">FormatString - `<string>`</span></span>

<span data-ttu-id="641e0-166">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641e0-166">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="641e0-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="641e0-167">-InputObject</span></span>

<span data-ttu-id="641e0-168">書式設定するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="641e0-168">Specifies the objects to be formatted.</span></span> <span data-ttu-id="641e0-169">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="641e0-169">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="641e0-170">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="641e0-170">-Property</span></span>

<span data-ttu-id="641e0-171">表示するオブジェクト プロパティと、その表示順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="641e0-171">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="641e0-172">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="641e0-172">Wildcards are permitted.</span></span>

<span data-ttu-id="641e0-173">このパラメーターを省略した場合、表示されるプロパティは、表示されるオブジェクトに依存します。</span><span class="sxs-lookup"><span data-stu-id="641e0-173">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="641e0-174">パラメーター名 "Property" は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="641e0-174">The parameter name "Property" is optional.</span></span> <span data-ttu-id="641e0-175">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="641e0-175">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="641e0-176">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="641e0-176">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="641e0-177">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="641e0-177">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="641e0-178">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="641e0-178">Valid key-value pairs are:</span></span>

- <span data-ttu-id="641e0-179">名前 (またはラベル)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="641e0-179">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="641e0-180">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="641e0-180">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="641e0-181">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="641e0-181">FormatString - `<string>`</span></span>

<span data-ttu-id="641e0-182">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641e0-182">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="641e0-183">-ShowError</span><span class="sxs-lookup"><span data-stu-id="641e0-183">-ShowError</span></span>

<span data-ttu-id="641e0-184">コマンドレットがパイプラインを介してエラーを送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="641e0-184">Indicates that the cmdlet sends errors through the pipeline.</span></span> <span data-ttu-id="641e0-185">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-List` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="641e0-185">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="641e0-186">-ビュー</span><span class="sxs-lookup"><span data-stu-id="641e0-186">-View</span></span>

<span data-ttu-id="641e0-187">代替リスト形式またはビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="641e0-187">Specifies the name of an alternate list format or view.</span></span> <span data-ttu-id="641e0-188">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="641e0-188">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="641e0-189">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="641e0-189">CommonParameters</span></span>

<span data-ttu-id="641e0-190">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="641e0-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="641e0-191">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641e0-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="641e0-192">入力</span><span class="sxs-lookup"><span data-stu-id="641e0-192">INPUTS</span></span>

### <span data-ttu-id="641e0-193">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="641e0-193">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="641e0-194">パイプを使用して任意のオブジェクトをにパイプすることができ `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-194">You can pipe any object to `Format-List`.</span></span>

## <span data-ttu-id="641e0-195">出力</span><span class="sxs-lookup"><span data-stu-id="641e0-195">OUTPUTS</span></span>

### <span data-ttu-id="641e0-196">Microsoft. PowerShell. 内部形式</span><span class="sxs-lookup"><span data-stu-id="641e0-196">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="641e0-197">`Format-List` リストを表す書式オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="641e0-197">`Format-List` returns the format objects that represent the list.</span></span>

## <span data-ttu-id="641e0-198">注</span><span class="sxs-lookup"><span data-stu-id="641e0-198">NOTES</span></span>

<span data-ttu-id="641e0-199">Format-List は、その組み込みエイリアスである FL を使用して参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="641e0-199">You can also refer to Format-List by its built-in alias, FL.</span></span> <span data-ttu-id="641e0-200">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641e0-200">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="641e0-201">形式のコマンドレット (など) では、 `Format-List` 表示されるデータは配置されますが、表示されません。</span><span class="sxs-lookup"><span data-stu-id="641e0-201">The format cmdlets, such as `Format-List`, arrange the data to be displayed but do not display it.</span></span>
<span data-ttu-id="641e0-202">データは、PowerShell の出力機能と、Out 動詞 (Out コマンドレット) を含むコマンドレット (やなど) によって表示され `Out-Host` `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-202">The data is displayed by the output features of PowerShell and by the cmdlets that contain the Out verb (the Out cmdlets), such as `Out-Host` or `Out-File`.</span></span>

<span data-ttu-id="641e0-203">Format コマンドレットを使用しない場合、PowerShell では、表示される各オブジェクトに既定の形式が適用されます。</span><span class="sxs-lookup"><span data-stu-id="641e0-203">If you do not use a format cmdlet, PowerShell applies that default format for each object that it displays.</span></span>

<span data-ttu-id="641e0-204">**GroupBy** パラメーターは、オブジェクトが並べ替えられていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="641e0-204">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="641e0-205">を使用してオブジェクトをグループ化する前に、Sort-Object を使用し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-205">Use Sort-Object before using `Format-List` to group the objects.</span></span>

<span data-ttu-id="641e0-206">**View** パラメーターを使用すると、テーブルの代替形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="641e0-206">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="641e0-207">PowerShell ディレクトリ内のファイルで定義されているビューを使用することも `*.format.PS1XML` 、新しい types.ps1xml ファイルに独自のビューを作成して、Update-FormatData コマンドレットを使用してそれらを powershell に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="641e0-207">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory, or you can create your own views in new PS1XML files and use the Update-FormatData cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="641e0-208">**View** パラメーターの代替ビューでは、リスト形式を使用する必要があります。そうでない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="641e0-208">The alternate view for the **View** parameter must use the list format, otherwise, the command fails.</span></span> <span data-ttu-id="641e0-209">代替ビューがテーブルの場合は、を使用 `Format-Table` します。</span><span class="sxs-lookup"><span data-stu-id="641e0-209">If the alternate view is a table, use `Format-Table`.</span></span> <span data-ttu-id="641e0-210">代替ビューが一覧またはテーブルではない場合は、を使用し `Format-Custom` ます。</span><span class="sxs-lookup"><span data-stu-id="641e0-210">If the alternate view is not a list or a table, use `Format-Custom`.</span></span>

## <span data-ttu-id="641e0-211">関連リンク</span><span class="sxs-lookup"><span data-stu-id="641e0-211">RELATED LINKS</span></span>

[<span data-ttu-id="641e0-212">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="641e0-212">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="641e0-213">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="641e0-213">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="641e0-214">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="641e0-214">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="641e0-215">Format-Table</span><span class="sxs-lookup"><span data-stu-id="641e0-215">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="641e0-216">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="641e0-216">Format-Wide</span></span>](Format-Wide.md)
