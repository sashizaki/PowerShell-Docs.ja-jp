---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-String
ms.openlocfilehash: 665a0ca8332c4052b59362c7947e408ba811c5f2
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "93219795"
---
# <span data-ttu-id="7d475-103">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="7d475-103">ConvertFrom-String</span></span>

## <span data-ttu-id="7d475-104">概要</span><span class="sxs-lookup"><span data-stu-id="7d475-104">SYNOPSIS</span></span>
<span data-ttu-id="7d475-105">文字列のコンテンツから構造化されたプロパティを抽出して解析します。</span><span class="sxs-lookup"><span data-stu-id="7d475-105">Extracts and parses structured properties from string content.</span></span>

## <span data-ttu-id="7d475-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7d475-106">SYNTAX</span></span>

### <span data-ttu-id="7d475-107">ByDelimiter (既定値)</span><span class="sxs-lookup"><span data-stu-id="7d475-107">ByDelimiter (Default)</span></span>

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="7d475-108">TemplateParsing</span><span class="sxs-lookup"><span data-stu-id="7d475-108">TemplateParsing</span></span>

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="7d475-109">Description</span><span class="sxs-lookup"><span data-stu-id="7d475-109">DESCRIPTION</span></span>

<span data-ttu-id="7d475-110">**Convertfrom-csv** コマンドレットは、文字列のコンテンツから構造化されたプロパティを抽出して解析します。</span><span class="sxs-lookup"><span data-stu-id="7d475-110">The **ConvertFrom-String** cmdlet extracts and parses structured properties from string content.</span></span>
<span data-ttu-id="7d475-111">このコマンドレットは、従来のテキストストリームからテキストを解析することによってオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="7d475-111">This cmdlet generates an object by parsing text from a traditional text stream.</span></span>
<span data-ttu-id="7d475-112">コマンドレットは、パイプライン内の各文字列に対して、区切り記号または解析式によって入力を分割し、結果として得られる分割された各要素にプロパティ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7d475-112">For each string in the pipeline, the cmdlet splits the input by either a delimiter or a parse expression, and then assigns property names to each of the resulting split elements.</span></span>
<span data-ttu-id="7d475-113">これらのプロパティ名を指定できます。そうしないと、自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d475-113">You can provide these property names; if you do not, they are automatically generated for you.</span></span>

<span data-ttu-id="7d475-114">コマンドレットの既定のパラメーター set **Bydelimiter** は、正規表現の区切り記号で正確に分割されます。</span><span class="sxs-lookup"><span data-stu-id="7d475-114">The cmdlet's default parameter set, **ByDelimiter** , splits exactly on the regular expression delimiter.</span></span>
<span data-ttu-id="7d475-115">コマンドレットの場合、引用符の照合や区切り記号のエスケープは実行されません `Import-Csv` 。</span><span class="sxs-lookup"><span data-stu-id="7d475-115">It does not perform quote matching or delimiter escaping as the `Import-Csv` cmdlet does.</span></span>

<span data-ttu-id="7d475-116">コマンドレットの代替パラメーターセットである **Templateparsing** は、正規表現によってキャプチャされたグループから要素を生成します。</span><span class="sxs-lookup"><span data-stu-id="7d475-116">The cmdlet's alternate parameter set, **TemplateParsing** , generates elements from the groups that are captured by a regular expression.</span></span> <span data-ttu-id="7d475-117">正規表現の詳細については、「 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d475-117">For more information on regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

<span data-ttu-id="7d475-118">このコマンドレットは、基本的に区切られた解析と、自動的に生成されたサンプルドリブン解析の2つのモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7d475-118">This cmdlet supports two modes: basic delimited parsing, and automatically-generated, example-driven parsing.</span></span>

<span data-ttu-id="7d475-119">区切り記号による解析では、既定で、入力を空白の位置で分割し、生成されるグループにプロパティ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7d475-119">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span>

<span data-ttu-id="7d475-120">区切り記号をカスタマイズするには、 `ConvertFrom-String` コマンドレットのいずれかに結果をパイプし `Format-*` ます。または、 **delimiter** パラメーターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d475-120">You can customize the delimiter by piping the `ConvertFrom-String` results into one of the `Format-*` cmdlets, or you can use the **Delimiter** parameter.</span></span>

<span data-ttu-id="7d475-121">このコマンドレットは、 [FlashExtract、Microsoft research による研究作業](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/)に基づいて、自動的に生成された例に基づく解析もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7d475-121">The cmdlet also supports automatically-generated, example-driven parsing based on the [FlashExtract, research work by Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).</span></span>

## <span data-ttu-id="7d475-122">例</span><span class="sxs-lookup"><span data-stu-id="7d475-122">EXAMPLES</span></span>

### <span data-ttu-id="7d475-123">例 1: 既定のプロパティ名を使用してオブジェクトを生成する</span><span class="sxs-lookup"><span data-stu-id="7d475-123">Example 1: Generate an object with default property names</span></span>

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

<span data-ttu-id="7d475-124">このコマンドは、既定のプロパティ名 **P1** および **P2** を持つオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="7d475-124">This command generates an object with default property names, **P1** and **P2**.</span></span>

### <span data-ttu-id="7d475-125">例 1A: 生成されたオブジェクトを確認する</span><span class="sxs-lookup"><span data-stu-id="7d475-125">Example 1A: Get to know the generated object</span></span>

<span data-ttu-id="7d475-126">このコマンドは、 **P1** 、 **P2** のプロパティを持つ1つのオブジェクトを生成します。既定では、両方のプロパティが **文字列** 型です。</span><span class="sxs-lookup"><span data-stu-id="7d475-126">This command generates one object with properties **P1** , **P2** ; both properties are of **String** type, by default.</span></span>

```powershell
"Hello World" | ConvertFrom-String | Get-Member
```

```Output

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
P1          NoteProperty string P1=Hello
P2          NoteProperty string P2=World
```

### <span data-ttu-id="7d475-127">例 2: 区切り記号を使用して既定のプロパティ名を持つオブジェクトを生成する</span><span class="sxs-lookup"><span data-stu-id="7d475-127">Example 2: Generate an object with default property names using a delimiter</span></span>

<span data-ttu-id="7d475-128">このコマンドは、区切り記号として円記号 () を使用して、ドメインとユーザー名を持つオブジェクトを生成し `\` ます。</span><span class="sxs-lookup"><span data-stu-id="7d475-128">This command generates an object with a domain and username using the backslash (`\`) as the delimiter.</span></span> <span data-ttu-id="7d475-129">正規表現を使用する場合は、円記号を別の円記号でエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d475-129">The backslash character must be escaped with another backslash when using regular expressions.</span></span>

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### <span data-ttu-id="7d475-130">例 3: 2 つの名前付きプロパティを含むオブジェクトを生成する</span><span class="sxs-lookup"><span data-stu-id="7d475-130">Example 3: Generate an object that contains two named properties</span></span>

<span data-ttu-id="7d475-131">次の例では、Windows ホストのファイルエントリからオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7d475-131">The following example creates objects from Windows hosts file entries.</span></span>

```powershell
$content = Get-Content C:\Windows\System32\drivers\etc\hosts
$content = $content -match "^[^#]"
$content | ConvertFrom-String -PropertyNames IP, Server
```

```Output
IP             Server
--             ------
192.168.7.10   W2012R2
192.168.7.20   W2016
192.168.7.101  WIN8
192.168.7.102  WIN10
```

<span data-ttu-id="7d475-132">この `Get-Content` コマンドレットは、Windows hosts ファイルの内容をに格納し `$content` ます。</span><span class="sxs-lookup"><span data-stu-id="7d475-132">The `Get-Content` cmdlet stores the content of a Windows hosts file in `$content`.</span></span> <span data-ttu-id="7d475-133">2番目のコマンドは、() で始まらない任意の行と一致する正規表現を使用して、ホストファイルの先頭にあるすべてのコメントを削除し `#` ます。</span><span class="sxs-lookup"><span data-stu-id="7d475-133">The second command removes any comments at the beginning of the hosts file using a regular expression that matches any line that does not start with (`#`).</span></span> <span data-ttu-id="7d475-134">最後のコマンドは、残りのテキストを、 **サーバー** と **IP** のプロパティを持つオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="7d475-134">The last command converts the remaining text into objects with **Server** and **IP** properties.</span></span>

### <span data-ttu-id="7d475-135">例 4: TemplateContent パラメーターの値として式を使用し、結果を変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="7d475-135">Example 4: Use an expression as the value of the TemplateContent parameter, save the results in a variable.</span></span>

<span data-ttu-id="7d475-136">このコマンドでは、 **templatecontent** パラメーターの値として式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d475-136">This command uses an expression as the value of the **TemplateContent** parameter.</span></span>
<span data-ttu-id="7d475-137">式は、わかりやすくするために変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="7d475-137">The expression is saved in a variable for simplicity.</span></span>
<span data-ttu-id="7d475-138">Windows PowerShell では、パイプラインで使用される文字列に3つのプロパティがあることが認識されて `ConvertFrom-String` います。</span><span class="sxs-lookup"><span data-stu-id="7d475-138">Windows PowerShell understands now that the string that is used on the pipeline to `ConvertFrom-String` has three properties:</span></span>

- <span data-ttu-id="7d475-139">**名前**</span><span class="sxs-lookup"><span data-stu-id="7d475-139">**Name**</span></span>
- <span data-ttu-id="7d475-140">**phone**</span><span class="sxs-lookup"><span data-stu-id="7d475-140">**phone**</span></span>
- <span data-ttu-id="7d475-141">**変更**</span><span class="sxs-lookup"><span data-stu-id="7d475-141">**age**</span></span>

```powershell
$template = @'
{Name*:Phoebe Cat}, {phone:425-123-6789}, {age:6}
{Name*:Lucky Shot}, {phone:(206) 987-4321}, {age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789    6
Lucky Shot    (206) 987-4321  12
Elephant Wise 425-888-7766    87
Wild Shrimp   (111)  222-3333 1
```

<span data-ttu-id="7d475-142">入力の各行は、サンプルの一致によって評価されます。</span><span class="sxs-lookup"><span data-stu-id="7d475-142">Each line in the input is evaluated by the sample matches.</span></span> <span data-ttu-id="7d475-143">この行がパターンに示されている例と一致する場合、値が抽出され、出力変数に渡されます。</span><span class="sxs-lookup"><span data-stu-id="7d475-143">If the line matches the examples given in the pattern, values are extracted and passed to the output variable.</span></span>

<span data-ttu-id="7d475-144">サンプルデータには、 `$template` 次の2つの異なる電話形式が用意されています。</span><span class="sxs-lookup"><span data-stu-id="7d475-144">The sample data, `$template`, provides two different phone formats:</span></span>

- `425-123-6789`
- `(206) 987-4321`

<span data-ttu-id="7d475-145">このサンプルデータには、次の2つの異なる年齢形式も用意されています。</span><span class="sxs-lookup"><span data-stu-id="7d475-145">The sample data also provides two different age formats:</span></span>

- `6`
- `12`

<span data-ttu-id="7d475-146">これは、のような電話が認識されないことを意味 `(206) 987 4321` します。これは、ハイフンがないため、そのパターンに一致するサンプルデータがないためです。</span><span class="sxs-lookup"><span data-stu-id="7d475-146">This implies that phones like `(206) 987 4321` will not be recognized, because there's no sample data that matches that pattern because there are no hyphens.</span></span>

### <span data-ttu-id="7d475-147">例 5: 生成されるプロパティへのデータ型の指定</span><span class="sxs-lookup"><span data-stu-id="7d475-147">Example 5: Specifying data types to the generated properties</span></span>

<span data-ttu-id="7d475-148">これは、上記の例4と同じ例です。</span><span class="sxs-lookup"><span data-stu-id="7d475-148">This is the same example as Example 4, above.</span></span>
<span data-ttu-id="7d475-149">違いは、パターン文字列には、目的の各プロパティのデータ型が含まれていることです。</span><span class="sxs-lookup"><span data-stu-id="7d475-149">The difference is that the pattern string includes a data type for each desired property.</span></span>

```powershell
$template = @'
{[string]Name*:Phoebe Cat}, {[string]phone:425-123-6789}, {[int]age:6}
{[string]Name*:Lucky Shot}, {[string]phone:(206) 987-4321}, {[int]age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789      6
Lucky Shot    (206) 987-4321   12
Elephant Wise 425-888-7766     87
Wild Shrimp   (111)  222-3333   1
```

```powershell
$PersonalData | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
age         NoteProperty int age=6
Name        NoteProperty string Name=Phoebe Cat
phone       NoteProperty string phone=425-123-6789
```

<span data-ttu-id="7d475-150">`Get-Member` **Age** プロパティが整数であることを示すには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d475-150">The `Get-Member` cmdlet is used to show that the **age** property is an integer.</span></span>

## <span data-ttu-id="7d475-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7d475-151">PARAMETERS</span></span>

### <span data-ttu-id="7d475-152">-区切り記号</span><span class="sxs-lookup"><span data-stu-id="7d475-152">-Delimiter</span></span>

<span data-ttu-id="7d475-153">要素間の境界を識別する正規表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d475-153">Specifies a regular expression that identifies the boundary between elements.</span></span>
<span data-ttu-id="7d475-154">Split によって作成された要素は、結果として得られるオブジェクトのプロパティになります。</span><span class="sxs-lookup"><span data-stu-id="7d475-154">Elements that are created by the split become properties in the resulting object.</span></span>
<span data-ttu-id="7d475-155">この区切り記号は、最終的に型の **Split** メソッドの呼び出しで使用され `[System.Text.RegularExpressions.RegularExpression]` ます。</span><span class="sxs-lookup"><span data-stu-id="7d475-155">The delimiter is ultimately used in a call to the **Split** method of the type `[System.Text.RegularExpressions.RegularExpression]`.</span></span>

```yaml
Type: System.String
Parameter Sets: ByDelimiter
Aliases: DEL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d475-156">-IncludeExtent</span><span class="sxs-lookup"><span data-stu-id="7d475-156">-IncludeExtent</span></span>

<span data-ttu-id="7d475-157">このコマンドレットに、既定で削除されるエクステントテキストプロパティが含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d475-157">Indicates that this cmdlet includes an extent text property that is removed by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: IE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d475-158">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7d475-158">-InputObject</span></span>

<span data-ttu-id="7d475-159">パイプラインから受け取る文字列、または文字列オブジェクトを含む変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d475-159">Specifies strings received from the pipeline, or a variable that contains a string object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7d475-160">-PropertyNames</span><span class="sxs-lookup"><span data-stu-id="7d475-160">-PropertyNames</span></span>

<span data-ttu-id="7d475-161">結果として得られるオブジェクトでの分割された値の割り当て先となるプロパティ名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d475-161">Specifies an array of property names to which to assign split values in the resulting object.</span></span>
<span data-ttu-id="7d475-162">分割または解析するテキストのすべての行で、プロパティ値を表す要素が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d475-162">Every line of text that you split or parse generates elements that represent property values.</span></span>
<span data-ttu-id="7d475-163">要素がキャプチャグループの結果であり、そのキャプチャグループにという名前が付けられている場合 ( `(?<name>)` やなど `(?'name')` )、そのキャプチャグループの名前がプロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7d475-163">If the element is the result of a capture group, and that capture group is named (for example, `(?<name>)` or `(?'name')` ), then the name of that capture group is assigned to the property.</span></span>

<span data-ttu-id="7d475-164">**PropertyName** 配列に要素を指定した場合、それらの名前は、まだ名前が付けられていないプロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7d475-164">If you provide any elements in the **PropertyName** array, those names are assigned to properties that have not yet been named.</span></span>

<span data-ttu-id="7d475-165">フィールドの数よりも多くのプロパティ名を指定した場合、PowerShell は余分なプロパティ名を無視します。</span><span class="sxs-lookup"><span data-stu-id="7d475-165">If you provide more property names than there are fields, PowerShell ignores the extra property names.</span></span> <span data-ttu-id="7d475-166">すべてのフィールドに名前を付けるのに十分なプロパティ名を指定しない場合、PowerShell では、名前のないプロパティ ( **P1** 、 **P2** など) に数値プロパティ名が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7d475-166">If you do not specify enough property names to name all fields, PowerShell automatically assigns numerical property names to any properties that are not named: **P1** , **P2** , etc.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByDelimiter
Aliases: PN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d475-167">-TemplateContent 場合</span><span class="sxs-lookup"><span data-stu-id="7d475-167">-TemplateContent</span></span>

<span data-ttu-id="7d475-168">このコマンドレットによって文字列が割り当てられるプロパティを記述する式、または変数として保存された式を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d475-168">Specifies an expression, or an expression saved as a variable, that describes the properties to which this cmdlet assigns strings.</span></span> <span data-ttu-id="7d475-169">テンプレートフィールドの指定の構文は次のとおりです `{[optional-typecast]<name>:<example-value>}` 。</span><span class="sxs-lookup"><span data-stu-id="7d475-169">The syntax of a template field specification is the following: `{[optional-typecast]<name>:<example-value>}`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d475-170">-TemplateFile</span><span class="sxs-lookup"><span data-stu-id="7d475-170">-TemplateFile</span></span>

<span data-ttu-id="7d475-171">文字列を解析するためのテンプレートを含むファイルを配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="7d475-171">Specifies a file, as an array, that contains a template for the desired parsing of the string.</span></span>
<span data-ttu-id="7d475-172">テンプレートファイルでは、次に示すように、プロパティとその値が角かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="7d475-172">In the template file, properties and their values are enclosed in brackets, as shown below.</span></span>
<span data-ttu-id="7d475-173">**Name** プロパティやそれに関連付けられたその他のプロパティなどのプロパティが複数回表示される場合は、アスタリスク () を追加して、 `*` この結果が複数のレコードであることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="7d475-173">If a property, such as the **Name** property and its associated other properties, appears multiple times, you can add an asterisk (`*`) to indicate that this results in multiple records.</span></span> <span data-ttu-id="7d475-174">これにより、複数のプロパティを1つのレコードに抽出することが回避されます。</span><span class="sxs-lookup"><span data-stu-id="7d475-174">This avoids extracting multiple properties into a single record.</span></span>

```
{Name*:David Chew}
{City:Redmond}, {State:WA}
{Name*:Evan Narvaez}    {Name*:Antonio Moreno}
{City:Issaquah}, {State:WA}
```

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d475-175">-UpdateTemplate</span><span class="sxs-lookup"><span data-stu-id="7d475-175">-UpdateTemplate</span></span>

<span data-ttu-id="7d475-176">このコマンドレットが、学習アルゴリズムの結果をテンプレートファイル内のコメントに保存することを示します。</span><span class="sxs-lookup"><span data-stu-id="7d475-176">Indicates that this cmdlet saves the results of a learning algorithm into a comment in the template file.</span></span>
<span data-ttu-id="7d475-177">これにより、アルゴリズム学習プロセスが高速になります。</span><span class="sxs-lookup"><span data-stu-id="7d475-177">This makes the algorithm learning process faster.</span></span>
<span data-ttu-id="7d475-178">このパラメーターを使用するには、 **TemplateFile** パラメーターを使用してテンプレートファイルを指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="7d475-178">To use this parameter, you must also specify a template file with the **TemplateFile** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: UT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d475-179">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d475-179">CommonParameters</span></span>

<span data-ttu-id="7d475-180">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="7d475-180">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="7d475-181">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d475-181">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7d475-182">入力</span><span class="sxs-lookup"><span data-stu-id="7d475-182">INPUTS</span></span>

### <span data-ttu-id="7d475-183">System.String</span><span class="sxs-lookup"><span data-stu-id="7d475-183">System.String</span></span>

## <span data-ttu-id="7d475-184">出力</span><span class="sxs-lookup"><span data-stu-id="7d475-184">OUTPUTS</span></span>

## <span data-ttu-id="7d475-185">注</span><span class="sxs-lookup"><span data-stu-id="7d475-185">NOTES</span></span>

## <span data-ttu-id="7d475-186">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7d475-186">RELATED LINKS</span></span>

[<span data-ttu-id="7d475-187">Convertfrom-csv: サンプルベースのテキスト解析</span><span class="sxs-lookup"><span data-stu-id="7d475-187">ConvertFrom-String: Example-based text parsing</span></span>](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)

[<span data-ttu-id="7d475-188">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="7d475-188">ConvertFrom-StringData</span></span>](ConvertFrom-StringData.md)

[<span data-ttu-id="7d475-189">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="7d475-189">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="7d475-190">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="7d475-190">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
