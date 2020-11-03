---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/join-string?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-String
ms.openlocfilehash: 8f4dc173ff95476c4e2cb91e24d30afdd8a31697
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212936"
---
# <span data-ttu-id="5203a-102">Join-String</span><span class="sxs-lookup"><span data-stu-id="5203a-102">Join-String</span></span>

## <span data-ttu-id="5203a-103">概要</span><span class="sxs-lookup"><span data-stu-id="5203a-103">SYNOPSIS</span></span>
<span data-ttu-id="5203a-104">パイプラインのオブジェクトを1つの文字列に結合します。</span><span class="sxs-lookup"><span data-stu-id="5203a-104">Combines objects from the pipeline into a single string.</span></span>

## <span data-ttu-id="5203a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5203a-105">SYNTAX</span></span>

### <span data-ttu-id="5203a-106">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="5203a-106">Default (Default)</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-UseCulture] [-InputObject <PSObject[]>] [<CommonParameters>]
```

### <span data-ttu-id="5203a-107">SingleQuote</span><span class="sxs-lookup"><span data-stu-id="5203a-107">SingleQuote</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-SingleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="5203a-108">DoubleQuote</span><span class="sxs-lookup"><span data-stu-id="5203a-108">DoubleQuote</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-DoubleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="5203a-109">フォーマット</span><span class="sxs-lookup"><span data-stu-id="5203a-109">Format</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-FormatString <String>] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="5203a-110">Description</span><span class="sxs-lookup"><span data-stu-id="5203a-110">DESCRIPTION</span></span>

<span data-ttu-id="5203a-111">この `Join-String` コマンドレットは、パイプラインオブジェクトのテキストを1つの文字列に結合 (または結合) します。</span><span class="sxs-lookup"><span data-stu-id="5203a-111">The `Join-String` cmdlet joins, or combines, text from pipeline objects into a single string.</span></span>

<span data-ttu-id="5203a-112">パラメーターが指定されていない場合、パイプラインオブジェクトは文字列に変換され、既定の区切り記号と結合され `$OFS` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-112">If no parameters are specified, the pipeline objects are converted to a string and joined with the default separator `$OFS`.</span></span>

<span data-ttu-id="5203a-113">プロパティ名を指定することにより、プロパティの値が文字列に変換され、文字列に結合されます。</span><span class="sxs-lookup"><span data-stu-id="5203a-113">By specifying a property name, the property's value is converted to a string and joined into a string.</span></span>

<span data-ttu-id="5203a-114">スクリプトブロックは、プロパティ名の代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="5203a-114">Instead of a property name, a script block can be used.</span></span> <span data-ttu-id="5203a-115">スクリプトブロックの結果は、結果を形成するために結合される前に文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5203a-115">The script block's result is converted to a string before it's joined to form the result.</span></span> <span data-ttu-id="5203a-116">オブジェクトのプロパティのテキスト、または文字列に変換されたオブジェクトの結果を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="5203a-116">It can either combine the text of an object's property or the result of the object that was converted to a string.</span></span>

<span data-ttu-id="5203a-117">このコマンドレットは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5203a-117">This cmdlet was introduced in PowerShell 6.2.</span></span>

## <span data-ttu-id="5203a-118">例</span><span class="sxs-lookup"><span data-stu-id="5203a-118">EXAMPLES</span></span>

### <span data-ttu-id="5203a-119">例 1: ディレクトリ名を結合する</span><span class="sxs-lookup"><span data-stu-id="5203a-119">Example 1: Join directory names</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="5203a-120">この例では、ディレクトリ名を結合し、出力を二重引用符で囲み、ディレクトリ名をコンマとスペース ( `, ` ) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="5203a-120">This example joins directory names, wraps the output in double-quotes, and separates the directory names with a comma and space (`, `).</span></span> <span data-ttu-id="5203a-121">出力は文字列オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="5203a-121">The output is a string object.</span></span>

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property Name -DoubleQuote -Separator ', '
```

```Output
"PerfLogs", "Program Files", "Program Files (x86)", "Users", "Windows"
```

<span data-ttu-id="5203a-122">`Get-ChildItem`**directory** パラメーターを使用して、ドライブのすべてのディレクトリ名を取得し `C:\` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-122">`Get-ChildItem` uses the **Directory** parameter to get all the directory names for the `C:\` drive.</span></span>
<span data-ttu-id="5203a-123">オブジェクトは、パイプラインの下位に送信され `Join-String` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-123">The objects are sent down the pipeline to `Join-String`.</span></span> <span data-ttu-id="5203a-124">**Property** パラメーターは、ディレクトリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5203a-124">The **Property** parameter specifies the directory names.</span></span> <span data-ttu-id="5203a-125">**DoubleQuote** パラメーターは、ディレクトリ名を二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="5203a-125">The **DoubleQuote** parameter wraps the directory names with double-quote marks.</span></span>
<span data-ttu-id="5203a-126">**Separator** パラメーターは、ディレクトリ名を区切るためにコンマとスペース () を使用することを指定し `, ` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-126">The **Separator** parameter specifies to use a comma and space (`, `) to separate the directory names.</span></span>

<span data-ttu-id="5203a-127">`Get-ChildItem`オブジェクトは **DirectoryInfo** であり、 `Join-String` オブジェクトを **system.string** に変換します。</span><span class="sxs-lookup"><span data-stu-id="5203a-127">The `Get-ChildItem` objects are **System.IO.DirectoryInfo** and `Join-String` converts the objects to **System.String** .</span></span>

### <span data-ttu-id="5203a-128">例 2: プロパティの部分文字列を使用してディレクトリ名を結合する</span><span class="sxs-lookup"><span data-stu-id="5203a-128">Example 2: Use a property substring to join directory names</span></span>

<span data-ttu-id="5203a-129">この例では、substring メソッドを使用して、ディレクトリ名の最初の4文字を取得し、その出力を単一引用符で囲み、ディレクトリ名をセミコロン () で区切り `;` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-129">This example uses a substring method to get the first four letters of directory names, wraps the output in single-quotes, and separates the directory names with a semicolon (`;`).</span></span>

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property {$_.Name.SubString(0,4)} -SingleQuote -Separator ';'
```

```Output
'Perf';'Prog';'Prog';'User';'Wind'
```

<span data-ttu-id="5203a-130">`Get-ChildItem`**directory** パラメーターを使用して、ドライブのすべてのディレクトリ名を取得し `C:\` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-130">`Get-ChildItem` uses the **Directory** parameter to get all the directory names for the `C:\` drive.</span></span>
<span data-ttu-id="5203a-131">オブジェクトは、パイプラインの下位に送信され `Join-String` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-131">The objects are sent down the pipeline to `Join-String`.</span></span>

<span data-ttu-id="5203a-132">**プロパティ** パラメーターのスクリプトブロックでは、自動変数 () を使用して、 `$_` 各オブジェクトの **Name** プロパティの部分文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5203a-132">The **Property** parameter script block uses automatic variable (`$_`) to specify each object's **Name** property substring.</span></span> <span data-ttu-id="5203a-133">部分文字列は、各ディレクトリ名の最初の4文字を取得します。</span><span class="sxs-lookup"><span data-stu-id="5203a-133">The substring gets the first four letters of each directory name.</span></span> <span data-ttu-id="5203a-134">部分文字列は、文字の開始位置と終了位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="5203a-134">The substring specifies the character start and end positions.</span></span> <span data-ttu-id="5203a-135">**Singlequote** パラメーターは、ディレクトリ名を単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="5203a-135">The **SingleQuote** parameter wraps the directory names with single-quote marks.</span></span> <span data-ttu-id="5203a-136">**Separator** パラメーターは、ディレクトリ名を区切るためにセミコロン () を使用するように指定し `;` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-136">The **Separator** parameter specifies to use a semicolon (`;`) to separate the directory names.</span></span>

<span data-ttu-id="5203a-137">自動変数と部分文字列の詳細については、「 [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) 」および「 [Substring](/dotnet/api/system.string.substring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5203a-137">For more information about automatic variables and substrings, see [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) and [Substring](/dotnet/api/system.string.substring).</span></span>

### <span data-ttu-id="5203a-138">例 3: 結合出力を別の行に表示する</span><span class="sxs-lookup"><span data-stu-id="5203a-138">Example 3: Display join output on a separate line</span></span>

<span data-ttu-id="5203a-139">この例では、サービス名をそれぞれ別の行に結合し、タブでインデントします。</span><span class="sxs-lookup"><span data-stu-id="5203a-139">This example joins service names with each service on a separate line and indented by a tab.</span></span>

```powershell
Get-Service -Name se* | Join-String -Property Name -Separator "`r`n`t" -OutputPrefix "Services:`n`t"
```

```Output
Services:
    seclogon
    SecurityHealthService
    SEMgrSvc
    SENS
    Sense
    SensorDataService
    SensorService
    SensrSvc
    SessionEnv
```

<span data-ttu-id="5203a-140">`Get-Service`**Name** パラメーターをと共に使用して、で始まるサービスを指定し `se*` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-140">`Get-Service` uses the **Name** parameter with to specify services that begin with `se*`.</span></span> <span data-ttu-id="5203a-141">アスタリスク ( `*` ) は、任意の文字のワイルドカードです。</span><span class="sxs-lookup"><span data-stu-id="5203a-141">The asterisk (`*`) is a wildcard for any character.</span></span>

<span data-ttu-id="5203a-142">オブジェクトは、 `Join-String` **プロパティ** パラメーターを使用してサービス名を指定するにパイプラインで送信されます。</span><span class="sxs-lookup"><span data-stu-id="5203a-142">The objects are sent down the pipeline to `Join-String` that uses the **Property** parameter to specify the service names.</span></span> <span data-ttu-id="5203a-143">**Separator** パラメーターは、キャリッジリターン ( `` `r `` )、改行 ( `` `n `` )、およびタブ () を表す3つの特殊文字を指定し `` `t `` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-143">The **Separator** parameter specifies three special characters that represent a carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span> <span data-ttu-id="5203a-144">**Outputprefix** は、ラベル **サービス** を挿入します。これには、出力の最初の行の前に新しい行とタブが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="5203a-144">The **OutputPrefix** inserts a label **Services:** with a new line and tab before the first line of output.</span></span>

<span data-ttu-id="5203a-145">特殊文字の詳細については、「 [about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5203a-145">For more information about special characters, see [about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md).</span></span>

### <span data-ttu-id="5203a-146">例 4: オブジェクトからクラス定義を作成する</span><span class="sxs-lookup"><span data-stu-id="5203a-146">Example 4: Create a class definition from an object</span></span>

<span data-ttu-id="5203a-147">この例では、既存のオブジェクトをテンプレートとして使用して、PowerShell クラス定義を生成します。</span><span class="sxs-lookup"><span data-stu-id="5203a-147">This example generates a PowerShell class definition using an existing object as a template.</span></span>

<span data-ttu-id="5203a-148">このコードサンプルでは、スプラッティングを使用して、行の長さを減らし、読みやすさを向上させます。</span><span class="sxs-lookup"><span data-stu-id="5203a-148">This code sample uses splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="5203a-149">詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5203a-149">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$obj = [pscustomobject] @{Name = "Joe"; Age = 42}
$parms = @{
  Property = "Name"
  FormatString = '  ${0}'
  OutputPrefix = "class {`n"
  OutputSuffix = "`n}`n"
  Separator = "`n"
}
$obj.PSObject.Properties | Join-String @parms
```

```Output
class {
  $Name
  $Age
}
```

## <span data-ttu-id="5203a-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5203a-150">PARAMETERS</span></span>

### <span data-ttu-id="5203a-151">-DoubleQuote</span><span class="sxs-lookup"><span data-stu-id="5203a-151">-DoubleQuote</span></span>

<span data-ttu-id="5203a-152">各パイプラインオブジェクトの文字列値を二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="5203a-152">Wraps the string value of each pipeline object in double-quotes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DoubleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5203a-153">-FormatString</span><span class="sxs-lookup"><span data-stu-id="5203a-153">-FormatString</span></span>

<span data-ttu-id="5203a-154">各項目の書式設定方法を指定する書式指定文字列。</span><span class="sxs-lookup"><span data-stu-id="5203a-154">A format string that specifies how each item should be formatted.</span></span>

```yaml
Type: System.String
Parameter Sets: Format
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5203a-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5203a-155">-InputObject</span></span>

<span data-ttu-id="5203a-156">結合するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="5203a-156">Specifies the text to be joined.</span></span> <span data-ttu-id="5203a-157">テキストが格納されている変数を入力するか、文字列に結合するオブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="5203a-157">Enter a variable that contains the text, or type a command or expression that gets the objects to join into strings.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5203a-158">-OutputPrefix</span><span class="sxs-lookup"><span data-stu-id="5203a-158">-OutputPrefix</span></span>

<span data-ttu-id="5203a-159">出力文字列の前に挿入されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="5203a-159">Text that's inserted before the output string.</span></span> <span data-ttu-id="5203a-160">文字列には、キャリッジリターン ( `` `r `` )、改行 ( `` `n `` )、タブ () などの特殊文字を含めることができ `` `t `` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-160">The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: op

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5203a-161">-OutputSuffix</span><span class="sxs-lookup"><span data-stu-id="5203a-161">-OutputSuffix</span></span>

<span data-ttu-id="5203a-162">出力文字列に追加されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="5203a-162">Text that's appended to the output string.</span></span> <span data-ttu-id="5203a-163">文字列には、キャリッジリターン ( `` `r `` )、改行 ( `` `n `` )、タブ () などの特殊文字を含めることができ `` `t `` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-163">The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5203a-164">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="5203a-164">-Property</span></span>

<span data-ttu-id="5203a-165">パイプラインオブジェクトをテキストに投影するプロパティの名前、またはプロパティ式。</span><span class="sxs-lookup"><span data-stu-id="5203a-165">The name of a property, or a property expression, that will project the pipeline object to text.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5203a-166">-Separator</span><span class="sxs-lookup"><span data-stu-id="5203a-166">-Separator</span></span>

<span data-ttu-id="5203a-167">各パイプラインオブジェクトのテキストの間に挿入されるコンマやセミコロンなどのテキストまたは文字。</span><span class="sxs-lookup"><span data-stu-id="5203a-167">Text or characters such as a comma or semicolon that's inserted between the text for each pipeline object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5203a-168">-SingleQuote</span><span class="sxs-lookup"><span data-stu-id="5203a-168">-SingleQuote</span></span>

<span data-ttu-id="5203a-169">各パイプラインオブジェクトの文字列値を単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="5203a-169">Wraps the string value of each pipeline object in single quotes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SingleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5203a-170">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="5203a-170">-UseCulture</span></span>

<span data-ttu-id="5203a-171">現在のカルチャの区切り記号を項目の区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="5203a-171">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="5203a-172">カルチャのリスト区切り記号を検索するには、コマンドを使用し `(Get-Culture).TextInfo.ListSeparator` ます。</span><span class="sxs-lookup"><span data-stu-id="5203a-172">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="5203a-173">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5203a-173">CommonParameters</span></span>

<span data-ttu-id="5203a-174">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5203a-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5203a-175">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5203a-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5203a-176">入力</span><span class="sxs-lookup"><span data-stu-id="5203a-176">INPUTS</span></span>

### <span data-ttu-id="5203a-177">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="5203a-177">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="5203a-178">出力</span><span class="sxs-lookup"><span data-stu-id="5203a-178">OUTPUTS</span></span>

### <span data-ttu-id="5203a-179">System.String</span><span class="sxs-lookup"><span data-stu-id="5203a-179">System.String</span></span>

## <span data-ttu-id="5203a-180">注</span><span class="sxs-lookup"><span data-stu-id="5203a-180">NOTES</span></span>

## <span data-ttu-id="5203a-181">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5203a-181">RELATED LINKS</span></span>

[<span data-ttu-id="5203a-182">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="5203a-182">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="5203a-183">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="5203a-183">about_Special_Characters</span></span>](..//microsoft.powershell.core/about/about_special_characters.md)

[<span data-ttu-id="5203a-184">出現</span><span class="sxs-lookup"><span data-stu-id="5203a-184">Substring</span></span>](/dotnet/api/system.string.substring)

