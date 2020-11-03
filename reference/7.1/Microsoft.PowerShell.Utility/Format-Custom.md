---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: c8bf4dfa9077af04e4122672a15a7c768cb49ea2
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219259"
---
# <span data-ttu-id="bb794-103">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="bb794-103">Format-Custom</span></span>

## <span data-ttu-id="bb794-104">概要</span><span class="sxs-lookup"><span data-stu-id="bb794-104">SYNOPSIS</span></span>
<span data-ttu-id="bb794-105">カスタマイズされたビューを使用して、出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-105">Uses a customized view to format the output.</span></span>

## <span data-ttu-id="bb794-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bb794-106">SYNTAX</span></span>

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## <span data-ttu-id="bb794-107">Description</span><span class="sxs-lookup"><span data-stu-id="bb794-107">DESCRIPTION</span></span>

<span data-ttu-id="bb794-108">`Format-Custom`コマンドレットは、代替ビューで定義されているように、コマンドの出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-108">The `Format-Custom` cmdlet formats the output of a command as defined in an alternate view.</span></span>
<span data-ttu-id="bb794-109">`Format-Custom` は、テーブルまたはリストだけではないビューを表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bb794-109">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="bb794-110">PowerShell で定義されたビューを使用することも、新しいファイルに独自のビューを作成 `format.ps1xml` して、コマンドレットを使用して powershell に追加することもできます `Update-FormatData` 。</span><span class="sxs-lookup"><span data-stu-id="bb794-110">You can use the views defined in PowerShell, or you can create your own views in a new `format.ps1xml` file and use the `Update-FormatData` cmdlet to add them to PowerShell.</span></span>

## <span data-ttu-id="bb794-111">例</span><span class="sxs-lookup"><span data-stu-id="bb794-111">EXAMPLES</span></span>

### <span data-ttu-id="bb794-112">例 1: カスタムビューを使用して出力の書式を設定する</span><span class="sxs-lookup"><span data-stu-id="bb794-112">Example 1: Format output with a custom view</span></span>

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

<span data-ttu-id="bb794-113">このコマンドは、 `Start-Transcript` ユーザーが作成したカスタムビューである MyView ビューで定義されている形式で、コマンドレットに関する情報を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-113">This command formats information about the `Start-Transcript` cmdlet in the format defined by the MyView view, a custom view created by the user.</span></span> <span data-ttu-id="bb794-114">このコマンドを正常に実行するには、最初に新しい TYPES.PS1XML ファイルを作成し、 **Myview** ビューを定義してから、コマンドを使用して `Update-FormatData` Types.ps1xml ファイルを PowerShell に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb794-114">To run this command successfully, you must first create a new PS1XML file, define the **MyView** view, and then use the `Update-FormatData` command to add the PS1XML file to PowerShell.</span></span>

### <span data-ttu-id="bb794-115">例 2: 既定のビューで出力を書式設定する</span><span class="sxs-lookup"><span data-stu-id="bb794-115">Example 2: Format output with the default view</span></span>

```powershell
Get-Process Winlogon | Format-Custom
```

<span data-ttu-id="bb794-116">このコマンドは、 **Winlogon** プロセスに関する情報をカスタマイズされた代替ビューで書式設定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-116">This command formats information about the **Winlogon** process in an alternate customized view.</span></span>
<span data-ttu-id="bb794-117">コマンドは **View** パラメーターを使用しないため、では `Format-Custom` 既定のカスタムビューを使用してデータを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-117">Because the command does not use the **View** parameter, `Format-Custom` uses a default custom view to format the data.</span></span>

### <span data-ttu-id="bb794-118">例 3: 形式エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bb794-118">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="bb794-119">次の例では、 **displayerror** パラメーターまたは **showerror** パラメーターを式に追加した結果を示します。</span><span class="sxs-lookup"><span data-stu-id="bb794-119">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -DisplayError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  = #ERR
}


PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -ShowError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  =
}

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:01:04 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="bb794-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bb794-120">PARAMETERS</span></span>

### <span data-ttu-id="bb794-121">-深さ</span><span class="sxs-lookup"><span data-stu-id="bb794-121">-Depth</span></span>

<span data-ttu-id="bb794-122">表示する列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-122">Specifies the number of columns in the display.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bb794-123">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="bb794-123">-DisplayError</span></span>

<span data-ttu-id="bb794-124">コマンド ラインでのエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb794-124">Displays errors at the command line.</span></span> <span data-ttu-id="bb794-125">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-Custom` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb794-125">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="bb794-126">-展開</span><span class="sxs-lookup"><span data-stu-id="bb794-126">-Expand</span></span>

<span data-ttu-id="bb794-127">コレクション内のオブジェクトに加えてコレクション オブジェクトを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-127">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="bb794-128">このパラメーター **は、system.string インターフェイスをサポート** するオブジェクトを書式設定するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bb794-128">This parameter is designed to format objects that support the **System.Collections.ICollection** interface.</span></span> <span data-ttu-id="bb794-129">既定値は **Enumonly** です。</span><span class="sxs-lookup"><span data-stu-id="bb794-129">The default value is **EnumOnly**.</span></span>

<span data-ttu-id="bb794-130">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bb794-130">Valid values are:</span></span>

- <span data-ttu-id="bb794-131">EnumOnly: コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb794-131">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="bb794-132">CoreOnly: コレクションオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb794-132">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="bb794-133">Both: コレクションオブジェクトのプロパティとコレクション内のオブジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb794-133">Both: Displays the properties of the collection object and the objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: EnumOnly
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bb794-134">-Force</span><span class="sxs-lookup"><span data-stu-id="bb794-134">-Force</span></span>

<span data-ttu-id="bb794-135">すべてのエラー情報を表示することをコマンドレットに指示します。</span><span class="sxs-lookup"><span data-stu-id="bb794-135">Directs the cmdlet to display all of the error information.</span></span> <span data-ttu-id="bb794-136">**Displayerror** パラメーターまたは **showerror** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="bb794-136">Use with the **DisplayError** or **ShowError** parameters.</span></span> <span data-ttu-id="bb794-137">既定では、エラー オブジェクトがエラーまたは表示ストリームに書き込まれるとき、エラー情報の一部のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb794-137">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="bb794-138">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="bb794-138">-GroupBy</span></span>

<span data-ttu-id="bb794-139">共有プロパティまたは値に基づき、グループ単位で出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-139">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="bb794-140">式または出力のプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="bb794-140">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="bb794-141">**GroupBy** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb794-141">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="bb794-142">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb794-142">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="bb794-143">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bb794-143">Valid key-value pairs are:</span></span>

- <span data-ttu-id="bb794-144">名前 (またはラベル)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="bb794-144">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="bb794-145">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="bb794-145">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="bb794-146">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="bb794-146">FormatString - `<string>`</span></span>

<span data-ttu-id="bb794-147">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb794-147">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="bb794-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="bb794-148">-InputObject</span></span>

<span data-ttu-id="bb794-149">書式設定するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-149">Specifies the objects to be formatted.</span></span> <span data-ttu-id="bb794-150">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="bb794-150">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="bb794-151">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="bb794-151">-Property</span></span>

<span data-ttu-id="bb794-152">表示するオブジェクト プロパティと、その表示順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-152">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="bb794-153">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb794-153">Wildcards are permitted.</span></span>

<span data-ttu-id="bb794-154">このパラメーターを省略した場合、表示されるプロパティは、表示されるオブジェクトに依存します。</span><span class="sxs-lookup"><span data-stu-id="bb794-154">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="bb794-155">パラメーター名の **プロパティ** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="bb794-155">The parameter name **Property** is optional.</span></span> <span data-ttu-id="bb794-156">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb794-156">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="bb794-157">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb794-157">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="bb794-158">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb794-158">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="bb794-159">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bb794-159">Valid key-value pairs are:</span></span>

- <span data-ttu-id="bb794-160">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="bb794-160">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="bb794-161">デプス `<int32>`</span><span class="sxs-lookup"><span data-stu-id="bb794-161">Depth - `<int32>`</span></span>

<span data-ttu-id="bb794-162">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb794-162">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="bb794-163">-ShowError</span><span class="sxs-lookup"><span data-stu-id="bb794-163">-ShowError</span></span>

<span data-ttu-id="bb794-164">パイプラインを使用してエラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="bb794-164">Sends errors through the pipeline.</span></span> <span data-ttu-id="bb794-165">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-Custom` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb794-165">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="bb794-166">-ビュー</span><span class="sxs-lookup"><span data-stu-id="bb794-166">-View</span></span>

<span data-ttu-id="bb794-167">代替形式またはビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb794-167">Specifies the name of an alternate format or view.</span></span> <span data-ttu-id="bb794-168">このパラメーターを省略すると、は `Format-Custom` 既定のカスタムビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb794-168">If you omit this parameter, `Format-Custom` uses a default custom view.</span></span> <span data-ttu-id="bb794-169">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb794-169">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="bb794-170">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb794-170">CommonParameters</span></span>

<span data-ttu-id="bb794-171">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bb794-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bb794-172">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb794-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bb794-173">入力</span><span class="sxs-lookup"><span data-stu-id="bb794-173">INPUTS</span></span>

### <span data-ttu-id="bb794-174">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="bb794-174">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="bb794-175">パイプを使用して任意のオブジェクトをにパイプすることができ `Format-Custom` ます。</span><span class="sxs-lookup"><span data-stu-id="bb794-175">You can pipe any object to `Format-Custom`.</span></span>

## <span data-ttu-id="bb794-176">出力</span><span class="sxs-lookup"><span data-stu-id="bb794-176">OUTPUTS</span></span>

### <span data-ttu-id="bb794-177">Microsoft. PowerShell. 内部形式</span><span class="sxs-lookup"><span data-stu-id="bb794-177">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="bb794-178">`Format-Custom` 表示を表す書式オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="bb794-178">`Format-Custom` returns the format objects that represent the display.</span></span>

## <span data-ttu-id="bb794-179">注</span><span class="sxs-lookup"><span data-stu-id="bb794-179">NOTES</span></span>

<span data-ttu-id="bb794-180">`Format-Custom` は、テーブルまたはリストだけではないビューを表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bb794-180">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="bb794-181">代替テーブルビューを表示するには、を使用 `Format-Table` します。</span><span class="sxs-lookup"><span data-stu-id="bb794-181">To display an alternate table view, use `Format-Table`.</span></span> <span data-ttu-id="bb794-182">代替のリストビューを表示するには、を使用し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="bb794-182">To display an alternate list view, use `Format-List`.</span></span>

<span data-ttu-id="bb794-183">また、組み込みエイリアスであるを参照することもでき `Format-Custom` `fc` ます。</span><span class="sxs-lookup"><span data-stu-id="bb794-183">You can also refer to `Format-Custom` by its built-in alias, `fc`.</span></span> <span data-ttu-id="bb794-184">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb794-184">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="bb794-185">**GroupBy** パラメーターは、オブジェクトが並べ替えられていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="bb794-185">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="bb794-186">を使用してオブジェクトをグループ化する前に、を使用して `Format-Custom` オブジェクトを `Sort-Object` 並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="bb794-186">Before using `Format-Custom` to group the objects, use `Sort-Object` to sort them.</span></span>

## <span data-ttu-id="bb794-187">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bb794-187">RELATED LINKS</span></span>

[<span data-ttu-id="bb794-188">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="bb794-188">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="bb794-189">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="bb794-189">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="bb794-190">Format-List</span><span class="sxs-lookup"><span data-stu-id="bb794-190">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="bb794-191">Format-Table</span><span class="sxs-lookup"><span data-stu-id="bb794-191">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="bb794-192">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="bb794-192">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="bb794-193">Get-Process</span><span class="sxs-lookup"><span data-stu-id="bb794-193">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)