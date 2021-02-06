---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: ff4b2dda3f12fa34fc518c6a180f3213ba873d90
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600982"
---
# <span data-ttu-id="7f3bd-102">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="7f3bd-102">Format-Custom</span></span>

## <span data-ttu-id="7f3bd-103">概要</span><span class="sxs-lookup"><span data-stu-id="7f3bd-103">SYNOPSIS</span></span>
<span data-ttu-id="7f3bd-104">カスタマイズされたビューを使用して、出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-104">Uses a customized view to format the output.</span></span>

## <span data-ttu-id="7f3bd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7f3bd-105">SYNTAX</span></span>

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## <span data-ttu-id="7f3bd-106">Description</span><span class="sxs-lookup"><span data-stu-id="7f3bd-106">DESCRIPTION</span></span>

<span data-ttu-id="7f3bd-107">`Format-Custom`コマンドレットは、代替ビューで定義されているように、コマンドの出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-107">The `Format-Custom` cmdlet formats the output of a command as defined in an alternate view.</span></span>
<span data-ttu-id="7f3bd-108">`Format-Custom` は、テーブルまたはリストだけではないビューを表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-108">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="7f3bd-109">PowerShell で定義されたビューを使用することも、新しいファイルに独自のビューを作成 `format.ps1xml` して、コマンドレットを使用して powershell に追加することもできます `Update-FormatData` 。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-109">You can use the views defined in PowerShell, or you can create your own views in a new `format.ps1xml` file and use the `Update-FormatData` cmdlet to add them to PowerShell.</span></span>

## <span data-ttu-id="7f3bd-110">例</span><span class="sxs-lookup"><span data-stu-id="7f3bd-110">EXAMPLES</span></span>

### <span data-ttu-id="7f3bd-111">例 1: カスタムビューを使用して出力の書式を設定する</span><span class="sxs-lookup"><span data-stu-id="7f3bd-111">Example 1: Format output with a custom view</span></span>

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

<span data-ttu-id="7f3bd-112">このコマンドは、 `Start-Transcript` ユーザーが作成したカスタムビューである MyView ビューで定義されている形式で、コマンドレットに関する情報を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-112">This command formats information about the `Start-Transcript` cmdlet in the format defined by the MyView view, a custom view created by the user.</span></span> <span data-ttu-id="7f3bd-113">このコマンドを正常に実行するには、最初に新しい TYPES.PS1XML ファイルを作成し、 **Myview** ビューを定義してから、コマンドを使用して `Update-FormatData` Types.ps1xml ファイルを PowerShell に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-113">To run this command successfully, you must first create a new PS1XML file, define the **MyView** view, and then use the `Update-FormatData` command to add the PS1XML file to PowerShell.</span></span>

### <span data-ttu-id="7f3bd-114">例 2: 既定のビューで出力を書式設定する</span><span class="sxs-lookup"><span data-stu-id="7f3bd-114">Example 2: Format output with the default view</span></span>

```powershell
Get-Process Winlogon | Format-Custom
```

<span data-ttu-id="7f3bd-115">このコマンドは、 **Winlogon** プロセスに関する情報をカスタマイズされた代替ビューで書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-115">This command formats information about the **Winlogon** process in an alternate customized view.</span></span>
<span data-ttu-id="7f3bd-116">コマンドは **View** パラメーターを使用しないため、では `Format-Custom` 既定のカスタムビューを使用してデータを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-116">Because the command does not use the **View** parameter, `Format-Custom` uses a default custom view to format the data.</span></span>

### <span data-ttu-id="7f3bd-117">例 3: 形式エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7f3bd-117">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="7f3bd-118">次の例では、 **displayerror** パラメーターまたは **showerror** パラメーターを式に追加した結果を示します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-118">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

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

## <span data-ttu-id="7f3bd-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7f3bd-119">PARAMETERS</span></span>

### <span data-ttu-id="7f3bd-120">-深さ</span><span class="sxs-lookup"><span data-stu-id="7f3bd-120">-Depth</span></span>

<span data-ttu-id="7f3bd-121">表示する列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-121">Specifies the number of columns in the display.</span></span>

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

### <span data-ttu-id="7f3bd-122">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="7f3bd-122">-DisplayError</span></span>

<span data-ttu-id="7f3bd-123">コマンド ラインでのエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-123">Displays errors at the command line.</span></span> <span data-ttu-id="7f3bd-124">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-Custom` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-124">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="7f3bd-125">-展開</span><span class="sxs-lookup"><span data-stu-id="7f3bd-125">-Expand</span></span>

<span data-ttu-id="7f3bd-126">コレクション内のオブジェクトに加えてコレクション オブジェクトを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-126">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="7f3bd-127">このパラメーター **は、system.string インターフェイスをサポート** するオブジェクトを書式設定するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-127">This parameter is designed to format objects that support the **System.Collections.ICollection** interface.</span></span> <span data-ttu-id="7f3bd-128">既定値は **Enumonly** です。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-128">The default value is **EnumOnly**.</span></span>

<span data-ttu-id="7f3bd-129">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-129">Valid values are:</span></span>

- <span data-ttu-id="7f3bd-130">EnumOnly: コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-130">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="7f3bd-131">CoreOnly: コレクションオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-131">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="7f3bd-132">Both: コレクションオブジェクトのプロパティとコレクション内のオブジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-132">Both: Displays the properties of the collection object and the objects in the collection.</span></span>

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

### <span data-ttu-id="7f3bd-133">-Force</span><span class="sxs-lookup"><span data-stu-id="7f3bd-133">-Force</span></span>

<span data-ttu-id="7f3bd-134">すべてのエラー情報を表示することをコマンドレットに指示します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-134">Directs the cmdlet to display all of the error information.</span></span> <span data-ttu-id="7f3bd-135">**Displayerror** パラメーターまたは **showerror** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-135">Use with the **DisplayError** or **ShowError** parameters.</span></span> <span data-ttu-id="7f3bd-136">既定では、エラー オブジェクトがエラーまたは表示ストリームに書き込まれるとき、エラー情報の一部のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-136">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="7f3bd-137">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="7f3bd-137">-GroupBy</span></span>

<span data-ttu-id="7f3bd-138">共有プロパティまたは値に基づき、グループ単位で出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-138">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="7f3bd-139">式または出力のプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-139">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="7f3bd-140">**GroupBy** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-140">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="7f3bd-141">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-141">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="7f3bd-142">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-142">Valid key-value pairs are:</span></span>

- <span data-ttu-id="7f3bd-143">名前 (またはラベル)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="7f3bd-143">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="7f3bd-144">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="7f3bd-144">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="7f3bd-145">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="7f3bd-145">FormatString - `<string>`</span></span>

<span data-ttu-id="7f3bd-146">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-146">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="7f3bd-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7f3bd-147">-InputObject</span></span>

<span data-ttu-id="7f3bd-148">書式設定するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-148">Specifies the objects to be formatted.</span></span> <span data-ttu-id="7f3bd-149">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-149">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="7f3bd-150">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="7f3bd-150">-Property</span></span>

<span data-ttu-id="7f3bd-151">表示するオブジェクト プロパティと、その表示順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-151">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="7f3bd-152">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-152">Wildcards are permitted.</span></span>

<span data-ttu-id="7f3bd-153">このパラメーターを省略した場合、表示されるプロパティは、表示されるオブジェクトに依存します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-153">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="7f3bd-154">パラメーター名の **プロパティ** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-154">The parameter name **Property** is optional.</span></span> <span data-ttu-id="7f3bd-155">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-155">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="7f3bd-156">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-156">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="7f3bd-157">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-157">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="7f3bd-158">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-158">Valid key-value pairs are:</span></span>

- <span data-ttu-id="7f3bd-159">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="7f3bd-159">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="7f3bd-160">デプス `<int32>`</span><span class="sxs-lookup"><span data-stu-id="7f3bd-160">Depth - `<int32>`</span></span>

<span data-ttu-id="7f3bd-161">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-161">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="7f3bd-162">-ShowError</span><span class="sxs-lookup"><span data-stu-id="7f3bd-162">-ShowError</span></span>

<span data-ttu-id="7f3bd-163">パイプラインを使用してエラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-163">Sends errors through the pipeline.</span></span> <span data-ttu-id="7f3bd-164">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-Custom` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-164">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="7f3bd-165">-ビュー</span><span class="sxs-lookup"><span data-stu-id="7f3bd-165">-View</span></span>

<span data-ttu-id="7f3bd-166">代替形式またはビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-166">Specifies the name of an alternate format or view.</span></span> <span data-ttu-id="7f3bd-167">このパラメーターを省略すると、は `Format-Custom` 既定のカスタムビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-167">If you omit this parameter, `Format-Custom` uses a default custom view.</span></span> <span data-ttu-id="7f3bd-168">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-168">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="7f3bd-169">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7f3bd-169">CommonParameters</span></span>

<span data-ttu-id="7f3bd-170">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-170">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7f3bd-171">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-171">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7f3bd-172">入力</span><span class="sxs-lookup"><span data-stu-id="7f3bd-172">INPUTS</span></span>

### <span data-ttu-id="7f3bd-173">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="7f3bd-173">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7f3bd-174">パイプを使用して任意のオブジェクトをにパイプすることができ `Format-Custom` ます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-174">You can pipe any object to `Format-Custom`.</span></span>

## <span data-ttu-id="7f3bd-175">出力</span><span class="sxs-lookup"><span data-stu-id="7f3bd-175">OUTPUTS</span></span>

### <span data-ttu-id="7f3bd-176">Microsoft. PowerShell. 内部形式</span><span class="sxs-lookup"><span data-stu-id="7f3bd-176">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="7f3bd-177">`Format-Custom` 表示を表す書式オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-177">`Format-Custom` returns the format objects that represent the display.</span></span>

## <span data-ttu-id="7f3bd-178">注</span><span class="sxs-lookup"><span data-stu-id="7f3bd-178">NOTES</span></span>

<span data-ttu-id="7f3bd-179">`Format-Custom` は、テーブルまたはリストだけではないビューを表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-179">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="7f3bd-180">代替テーブルビューを表示するには、を使用 `Format-Table` します。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-180">To display an alternate table view, use `Format-Table`.</span></span> <span data-ttu-id="7f3bd-181">代替のリストビューを表示するには、を使用し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-181">To display an alternate list view, use `Format-List`.</span></span>

<span data-ttu-id="7f3bd-182">また、組み込みエイリアスであるを参照することもでき `Format-Custom` `fc` ます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-182">You can also refer to `Format-Custom` by its built-in alias, `fc`.</span></span> <span data-ttu-id="7f3bd-183">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-183">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="7f3bd-184">**GroupBy** パラメーターは、オブジェクトが並べ替えられていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-184">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="7f3bd-185">を使用してオブジェクトをグループ化する前に、を使用して `Format-Custom` オブジェクトを `Sort-Object` 並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="7f3bd-185">Before using `Format-Custom` to group the objects, use `Sort-Object` to sort them.</span></span>

## <span data-ttu-id="7f3bd-186">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7f3bd-186">RELATED LINKS</span></span>

[<span data-ttu-id="7f3bd-187">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="7f3bd-187">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="7f3bd-188">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="7f3bd-188">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="7f3bd-189">Format-List</span><span class="sxs-lookup"><span data-stu-id="7f3bd-189">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="7f3bd-190">Format-Table</span><span class="sxs-lookup"><span data-stu-id="7f3bd-190">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="7f3bd-191">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="7f3bd-191">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="7f3bd-192">Get-Process</span><span class="sxs-lookup"><span data-stu-id="7f3bd-192">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
