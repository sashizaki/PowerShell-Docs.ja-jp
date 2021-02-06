---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-wide?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Wide
ms.openlocfilehash: ba61c2d24d85256c55a7409fc368de4407aad5a9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605433"
---
# <span data-ttu-id="fbc05-102">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="fbc05-102">Format-Wide</span></span>

## <span data-ttu-id="fbc05-103">概要</span><span class="sxs-lookup"><span data-stu-id="fbc05-103">SYNOPSIS</span></span>
<span data-ttu-id="fbc05-104">各オブジェクトの 1 つのプロパティのみを表示する幅の広いテーブルに、オブジェクトを書式設定して表示します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-104">Formats objects as a wide table that displays only one property of each object.</span></span>

## <span data-ttu-id="fbc05-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbc05-105">SYNTAX</span></span>

```
Format-Wide [[-Property] <Object>] [-AutoSize] [-Column <int>] [-GroupBy <Object>] [-View <string>]
  [-ShowError] [-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>]
  [<CommonParameters>]
```

## <span data-ttu-id="fbc05-106">Description</span><span class="sxs-lookup"><span data-stu-id="fbc05-106">DESCRIPTION</span></span>

<span data-ttu-id="fbc05-107">コマンドレットでは、オブジェクトを `Format-Wide` 各オブジェクトの1つのプロパティのみを表示する幅の広いテーブルとして書式設定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-107">The `Format-Wide` cmdlet formats objects as a wide table that displays only one property of each object.</span></span> <span data-ttu-id="fbc05-108">**プロパティ** パラメーターを使用して、表示するプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-108">You can use the **Property** parameter to determine which property is displayed.</span></span>

## <span data-ttu-id="fbc05-109">例</span><span class="sxs-lookup"><span data-stu-id="fbc05-109">EXAMPLES</span></span>

### <span data-ttu-id="fbc05-110">例 1: 現在のディレクトリ内のファイルの名前を書式設定する</span><span class="sxs-lookup"><span data-stu-id="fbc05-110">Example 1: Format names of files in the current directory</span></span>

<span data-ttu-id="fbc05-111">このコマンドは、現在のディレクトリにあるファイルの名前を画面上に 3 列で表示します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-111">This command displays the names of files in the current directory in three columns across the screen.</span></span>

```powershell
Get-ChildItem | Format-Wide -Column 3
```

<span data-ttu-id="fbc05-112">Get-Childitem コマンドレットは、ディレクトリ内の各ファイルを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-112">The Get-ChildItem cmdlet gets objects representing each file in the directory.</span></span> <span data-ttu-id="fbc05-113">パイプライン演算子 (|) は、パイプラインを介してファイルオブジェクトをに渡し `Format-Wide` 、出力用に書式設定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-113">The pipeline operator (|) passes the file objects through the pipeline to `Format-Wide`, which formats them for output.</span></span> <span data-ttu-id="fbc05-114">**Column** パラメーターは、列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-114">The **Column** parameter specifies the number of columns.</span></span>

### <span data-ttu-id="fbc05-115">例 2: レジストリキーの名前を書式設定する</span><span class="sxs-lookup"><span data-stu-id="fbc05-115">Example 2: Format names of registry keys</span></span>

<span data-ttu-id="fbc05-116">このコマンドは、HKEY_CURRENT_USER\Software\Microsoft キーにあるレジストリ キーの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-116">This command displays the names of registry keys in the HKEY_CURRENT_USER\Software\Microsoft key.</span></span>

```powershell
Get-ChildItem HKCU:\software\microsoft | Format-Wide -Property pschildname -AutoSize
```

<span data-ttu-id="fbc05-117">Get-Childitem コマンドレットは、キーを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-117">The Get-ChildItem cmdlet gets objects representing the keys.</span></span> <span data-ttu-id="fbc05-118">このパスは、HKCU:、PowerShell レジストリプロバイダーによって公開されているドライブの1つ、キーのパスの順に指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-118">The path is specified as HKCU:, one of the drives exposed by the PowerShell Registry provider, followed by the key path.</span></span> <span data-ttu-id="fbc05-119">パイプライン演算子 (|) は、パイプラインを介してレジストリキーオブジェクトをに渡し `Format-Wide` ます。これにより、出力用に書式が設定されます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-119">The pipeline operator (|) passes the registry key objects through the pipeline to `Format-Wide`, which formats them for output.</span></span> <span data-ttu-id="fbc05-120">**Property** パラメーターはプロパティの名前を指定し、 **AutoSize** パラメーターは、読みやすくするために列を調整します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-120">The **Property** parameter specifies the name of the property, and the **AutoSize** parameter adjusts the columns for readability.</span></span>

### <span data-ttu-id="fbc05-121">例 3: 形式エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fbc05-121">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="fbc05-122">次の例では、 **displayerror** パラメーターまたは **showerror** パラメーターを式に追加した結果を示します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-122">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PS /> Get-Date | Format-Wide { $_ / $null } -DisplayError


#ERR

PS /> Get-Date | Format-Wide { $_ / $null } -ShowError


Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:18:01 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="fbc05-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbc05-123">PARAMETERS</span></span>

### <span data-ttu-id="fbc05-124">-AutoSize</span><span class="sxs-lookup"><span data-stu-id="fbc05-124">-AutoSize</span></span>

<span data-ttu-id="fbc05-125">データの幅に基づいて列のサイズと数を調整します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-125">Adjusts the column size and number of columns based on the width of the data.</span></span> <span data-ttu-id="fbc05-126">既定では、列のサイズと数は、ビューによって決まります。</span><span class="sxs-lookup"><span data-stu-id="fbc05-126">By default, the column size and number are determined by the view.</span></span> <span data-ttu-id="fbc05-127">**AutoSize** パラメーターと **Column** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc05-127">You cannot use the **AutoSize** and **Column** parameters in the same command.</span></span>

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

### <span data-ttu-id="fbc05-128">-列</span><span class="sxs-lookup"><span data-stu-id="fbc05-128">-Column</span></span>

<span data-ttu-id="fbc05-129">表示する列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-129">Specifies the number of columns in the display.</span></span> <span data-ttu-id="fbc05-130">**AutoSize** パラメーターと **Column** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc05-130">You cannot use the **AutoSize** and **Column** parameters in the same command.</span></span>

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

### <span data-ttu-id="fbc05-131">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="fbc05-131">-DisplayError</span></span>

<span data-ttu-id="fbc05-132">コマンド ラインでのエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-132">Displays errors at the command line.</span></span> <span data-ttu-id="fbc05-133">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-Wide` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-133">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="fbc05-134">-展開</span><span class="sxs-lookup"><span data-stu-id="fbc05-134">-Expand</span></span>

<span data-ttu-id="fbc05-135">コレクション内のオブジェクトに加えてコレクション オブジェクトを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-135">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="fbc05-136">このパラメーターは、ICollection (System.Collections) インターフェイスをサポートするオブジェクトを書式設定するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="fbc05-136">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="fbc05-137">既定値は **Enumonly** です。</span><span class="sxs-lookup"><span data-stu-id="fbc05-137">The default value is **EnumOnly**.</span></span>

<span data-ttu-id="fbc05-138">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fbc05-138">Valid values are:</span></span>

- <span data-ttu-id="fbc05-139">EnumOnly: コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-139">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="fbc05-140">CoreOnly: コレクションオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-140">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="fbc05-141">Both: コレクションオブジェクトのプロパティと、コレクション内のオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-141">Both: Displays the properties of the collection object and the properties of objects in the collection.</span></span>

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

### <span data-ttu-id="fbc05-142">-Force</span><span class="sxs-lookup"><span data-stu-id="fbc05-142">-Force</span></span>

<span data-ttu-id="fbc05-143">このコマンドレットが、コマンドの実行を妨げている制限をオーバーライドすることを示します。これは、変更によってセキュリティが損なわれないようにするためだけです。</span><span class="sxs-lookup"><span data-stu-id="fbc05-143">Indicates that this cmdlet overrides restrictions that prevent the command from succeeding, just so the changes do not compromise security.</span></span> <span data-ttu-id="fbc05-144">たとえば、**Force** を指定すると、読み取り専用属性がオーバーライドされるか、ファイル パスを完成させるためにディレクトリが作成されますが、ファイルのアクセス許可は変更されません。</span><span class="sxs-lookup"><span data-stu-id="fbc05-144">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="fbc05-145">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="fbc05-145">-GroupBy</span></span>

<span data-ttu-id="fbc05-146">共有プロパティまたは値に基づき、グループ単位で出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-146">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="fbc05-147">式または出力のプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-147">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="fbc05-148">**GroupBy** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-148">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="fbc05-149">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-149">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="fbc05-150">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fbc05-150">Valid key-value pairs are:</span></span>

- <span data-ttu-id="fbc05-151">名前 (またはラベル)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="fbc05-151">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="fbc05-152">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="fbc05-152">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="fbc05-153">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="fbc05-153">FormatString - `<string>`</span></span>

<span data-ttu-id="fbc05-154">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc05-154">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="fbc05-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fbc05-155">-InputObject</span></span>

<span data-ttu-id="fbc05-156">書式設定するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-156">Specifies the objects to format.</span></span> <span data-ttu-id="fbc05-157">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-157">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="fbc05-158">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="fbc05-158">-Property</span></span>

<span data-ttu-id="fbc05-159">表示するオブジェクト プロパティと、その表示順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-159">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="fbc05-160">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-160">Wildcards are permitted.</span></span>

<span data-ttu-id="fbc05-161">このパラメーターを省略した場合、表示されるプロパティは、表示されるオブジェクトに依存します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-161">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="fbc05-162">パラメーター名 "Property" は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fbc05-162">The parameter name "Property" is optional.</span></span> <span data-ttu-id="fbc05-163">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc05-163">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="fbc05-164">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-164">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="fbc05-165">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-165">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="fbc05-166">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fbc05-166">Valid key-value pairs are:</span></span>

- <span data-ttu-id="fbc05-167">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="fbc05-167">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="fbc05-168">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="fbc05-168">FormatString - `<string>`</span></span>

<span data-ttu-id="fbc05-169">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc05-169">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="fbc05-170">-ShowError</span><span class="sxs-lookup"><span data-stu-id="fbc05-170">-ShowError</span></span>

<span data-ttu-id="fbc05-171">パイプラインを使用してエラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-171">Sends errors through the pipeline.</span></span> <span data-ttu-id="fbc05-172">このパラメーターはほとんど使用されませんが、コマンドで式を書式設定するときに、 `Format-Wide` 式が動作していないと思われる場合は、デバッグのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-172">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="fbc05-173">-ビュー</span><span class="sxs-lookup"><span data-stu-id="fbc05-173">-View</span></span>

<span data-ttu-id="fbc05-174">代替テーブル形式またはビューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-174">Specifies the name of an alternate table format or view.</span></span> <span data-ttu-id="fbc05-175">**プロパティ** と **ビュー** のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc05-175">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="fbc05-176">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbc05-176">CommonParameters</span></span>

<span data-ttu-id="fbc05-177">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fbc05-177">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbc05-178">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc05-178">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbc05-179">入力</span><span class="sxs-lookup"><span data-stu-id="fbc05-179">INPUTS</span></span>

### <span data-ttu-id="fbc05-180">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="fbc05-180">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="fbc05-181">パイプを使用して任意のオブジェクトをにパイプすることができ `Format-Wide` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-181">You can pipe any object to `Format-Wide`.</span></span>

## <span data-ttu-id="fbc05-182">出力</span><span class="sxs-lookup"><span data-stu-id="fbc05-182">OUTPUTS</span></span>

### <span data-ttu-id="fbc05-183">Microsoft. PowerShell. 内部形式</span><span class="sxs-lookup"><span data-stu-id="fbc05-183">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="fbc05-184">`Format-Wide` テーブルを表す書式オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-184">`Format-Wide` returns format objects that represent the table.</span></span>

## <span data-ttu-id="fbc05-185">注</span><span class="sxs-lookup"><span data-stu-id="fbc05-185">NOTES</span></span>

<span data-ttu-id="fbc05-186">また、組み込みエイリアスであるを参照することもでき `Format-Wide` `fw` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-186">You can also refer to `Format-Wide` by its built-in alias, `fw`.</span></span> <span data-ttu-id="fbc05-187">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc05-187">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="fbc05-188">**GroupBy** パラメーターは、オブジェクトが並べ替えられていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="fbc05-188">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="fbc05-189">を使用し `Sort-Object` てオブジェクトをグループ化する前に、を使用し `Format-Custom` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-189">Use `Sort-Object` before using `Format-Custom` to group the objects.</span></span>

<span data-ttu-id="fbc05-190">**View** パラメーターを使用すると、テーブルの代替形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fbc05-190">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="fbc05-191">PowerShell ディレクトリ内のファイルで定義されているビューを使用することも、 `*.format.PS1XML` 新しい types.ps1xml ファイルに独自のビューを作成して、コマンドレットを使用して powershell に追加することもできます `Update-FormatData` 。</span><span class="sxs-lookup"><span data-stu-id="fbc05-191">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory or you can create your own views in new PS1XML files and use the `Update-FormatData` cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="fbc05-192">**View** パラメーターの代替ビューでは、テーブル形式を使用する必要があります。そうでない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-192">The alternate view for the **View** parameter must use table format; if it does not, the command fails.</span></span> <span data-ttu-id="fbc05-193">代替ビューが一覧の場合は、を使用 `Format-List` します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-193">If the alternate view is a list, use `Format-List`.</span></span> <span data-ttu-id="fbc05-194">代替ビューが一覧や表でない場合、Format-Custom を使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc05-194">If the alternate view is neither a list nor a table, use Format-Custom.</span></span>

## <span data-ttu-id="fbc05-195">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fbc05-195">RELATED LINKS</span></span>

[<span data-ttu-id="fbc05-196">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="fbc05-196">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="fbc05-197">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="fbc05-197">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="fbc05-198">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="fbc05-198">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="fbc05-199">Format-List</span><span class="sxs-lookup"><span data-stu-id="fbc05-199">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="fbc05-200">Format-Table</span><span class="sxs-lookup"><span data-stu-id="fbc05-200">Format-Table</span></span>](Format-Table.md)
