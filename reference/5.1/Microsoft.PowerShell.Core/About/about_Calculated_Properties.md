---
description: PowerShell では、新しいプロパティを動的に追加したり、パイプラインに出力されるオブジェクトの書式を変更したりできます。
Locale: en-US
ms.date: 10/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_calculated_properties?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Calculated_Properties
ms.openlocfilehash: 4dd7912c7e1a976e20f92093a47355f3a3291093
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223003"
---
# <a name="about-calculated-properties"></a><span data-ttu-id="2f703-103">計算されるプロパティについて</span><span class="sxs-lookup"><span data-stu-id="2f703-103">About calculated properties</span></span>

## <a name="short-description"></a><span data-ttu-id="2f703-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="2f703-104">Short Description</span></span>

<span data-ttu-id="2f703-105">PowerShell では、新しいプロパティを動的に追加したり、パイプラインに出力されるオブジェクトの書式を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="2f703-105">PowerShell provides the ability to dynamically add new properties and alter the formatting of objects output to the pipeline.</span></span>

## <a name="long-description"></a><span data-ttu-id="2f703-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="2f703-106">Long Description</span></span>

<span data-ttu-id="2f703-107">いくつかの PowerShell コマンドレットは、出力オブジェクトへの新しいプロパティの追加を可能にするパラメーターを使用して、入力オブジェクトを出力オブジェクトに変換、集計、または処理します。</span><span class="sxs-lookup"><span data-stu-id="2f703-107">A number of PowerShell cmdlets transform, aggregate, or process input objects into output objects using parameters that allow the addition of new properties to those output objects.</span></span> <span data-ttu-id="2f703-108">これらのパラメーターを使用すると、入力オブジェクトの値に基づいて、出力オブジェクトに対して新しい計算されるプロパティを生成できます。</span><span class="sxs-lookup"><span data-stu-id="2f703-108">These parameters can be used to generate new, calculated properties on output objects based on the values of input objects.</span></span>
<span data-ttu-id="2f703-109">計算プロパティは、新しいプロパティの名前、値を計算する式、および省略可能な書式情報を指定するキーと値のペアを含む [ハッシュテーブル](about_hash_tables.md) によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2f703-109">The calculated property is defined by a [hashtable](about_hash_tables.md) containing key-value pairs that specify the name of the new property, an expression to calculate the value, and optional formatting information.</span></span>

## <a name="supported-cmdlets"></a><span data-ttu-id="2f703-110">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="2f703-110">Supported cmdlets</span></span>

<span data-ttu-id="2f703-111">次のコマンドレットは、 **property** パラメーターの計算されたプロパティ値をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2f703-111">The following cmdlets support calculated property values for the **Property** parameter.</span></span> <span data-ttu-id="2f703-112">コマンドレットでは、 `Format-*` **GroupBy** パラメーターの計算値もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2f703-112">The `Format-*` cmdlets also support calculated values for the **GroupBy** parameter.</span></span>

<span data-ttu-id="2f703-113">次の一覧は、計算されたプロパティをサポートするコマンドレットと、各コマンドレットでサポートされているキーと値のペアを示しています。</span><span class="sxs-lookup"><span data-stu-id="2f703-113">The following list itemizes the cmdlets that support calculated properties and the key-value pairs that are supported by each cmdlet.</span></span>

- `Compare-Object`
  - `expression`

- `ConvertTo-Html`
  - <span data-ttu-id="2f703-114">`name`/`label` -省略可能 (PowerShell 6.x で追加)</span><span class="sxs-lookup"><span data-stu-id="2f703-114">`name`/`label` - optional (added in PowerShell 6.x)</span></span>
  - `expression`
  - <span data-ttu-id="2f703-115">`width` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-115">`width` - optional</span></span>
  - <span data-ttu-id="2f703-116">`alignment` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-116">`alignment` - optional</span></span>

- `Format-Custom`
  - `expression`
  - <span data-ttu-id="2f703-117">`depth` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-117">`depth` - optional</span></span>

- `Format-List`
  - <span data-ttu-id="2f703-118">`name`/`label` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-118">`name`/`label` - optional</span></span>
  - `expression`
  - <span data-ttu-id="2f703-119">`formatstring` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-119">`formatstring` - optional</span></span>

  <span data-ttu-id="2f703-120">この同じキーと値のペアのセットは、すべてのコマンドレットの **GroupBy** パラメーターに渡される計算されるプロパティ値にも適用さ `Format-*` れます。</span><span class="sxs-lookup"><span data-stu-id="2f703-120">This same set of key-value pairs also apply to calculated property values passed to the **GroupBy** parameter for all `Format-*` cmdlets.</span></span>

- `Format-Table`
  - <span data-ttu-id="2f703-121">`name`/`label` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-121">`name`/`label` - optional</span></span>
  - `expression`
  - <span data-ttu-id="2f703-122">`formatstring` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-122">`formatstring` - optional</span></span>
  - <span data-ttu-id="2f703-123">`width` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-123">`width` - optional</span></span>
  - <span data-ttu-id="2f703-124">`alignment` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-124">`alignment` - optional</span></span>

- `Format-Wide`
  - `expression`
  - <span data-ttu-id="2f703-125">`formatstring` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-125">`formatstring` - optional</span></span>

- `Group-Object`
  - `expression`

- `Measure-Object`
  - <span data-ttu-id="2f703-126">では、ハッシュテーブルではなく、式のスクリプトブロックのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2f703-126">Only supports a script block for the expression, not a hashtable.</span></span>
  - <span data-ttu-id="2f703-127">PowerShell 5.1 以前ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2f703-127">Not supported in PowerShell 5.1 and older.</span></span>

- `Select-Object`
  - <span data-ttu-id="2f703-128">`name`/`label` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-128">`name`/`label` - optional</span></span>
  - `expression`

- `Sort-Object`
  - `expression`
  - <span data-ttu-id="2f703-129">`ascending`/`descending` -省略可能</span><span class="sxs-lookup"><span data-stu-id="2f703-129">`ascending`/`descending` - optional</span></span>

> [!NOTE]
> <span data-ttu-id="2f703-130">の値は、 `expression` ハッシュテーブルではなく、スクリプトブロックにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f703-130">The value of the `expression` can be a script block instead of a hashtable.</span></span> <span data-ttu-id="2f703-131">詳細については、「 [メモ](#notes) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f703-131">For more information, see the [Notes](#notes) section.</span></span>

## <a name="hashtable-key-definitions"></a><span data-ttu-id="2f703-132">Hashtable キーの定義</span><span class="sxs-lookup"><span data-stu-id="2f703-132">Hashtable key definitions</span></span>

- <span data-ttu-id="2f703-133">`name`/`label` -作成するプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f703-133">`name`/`label` - Specifies the name of the property being created.</span></span> <span data-ttu-id="2f703-134">`name`またはそのエイリアスであるを使用でき `label` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-134">You can use `name` or its alias, `label`, interchangeably.</span></span>
- <span data-ttu-id="2f703-135">`expression` -新しいプロパティの値を計算するために使用されるスクリプトブロック。</span><span class="sxs-lookup"><span data-stu-id="2f703-135">`expression` - A script block used to calculate the value of the new property.</span></span>
- <span data-ttu-id="2f703-136">`alignment` -列に値を表示する方法を定義するために表形式の出力を生成するコマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f703-136">`alignment` - Used by cmdlets that produce tabular output to define how the values are displayed in a column.</span></span> <span data-ttu-id="2f703-137">値は、、 `'left'` 、またはである必要があり `'center'` `'right'` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-137">The value must be `'left'`, `'center'`, or `'right'`.</span></span>
- <span data-ttu-id="2f703-138">`formatstring` -出力の値の書式設定方法を定義する書式指定文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f703-138">`formatstring` - Specifies a format string that defines how the value is formatted for output.</span></span> <span data-ttu-id="2f703-139">書式指定文字列の詳細については、「 [.net での書式設定](/dotnet/standard/base-types/formatting-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f703-139">For more information about format strings, see [Format types in .NET](/dotnet/standard/base-types/formatting-types).</span></span>
- <span data-ttu-id="2f703-140">`width` -テーブル内の値が表示されるときの最大幅列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f703-140">`width` - Specifies the maximum width column in a table when the value is displayed.</span></span> <span data-ttu-id="2f703-141">値はよりも大きくする必要があり `0` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-141">The value must be greater than `0`.</span></span>
- <span data-ttu-id="2f703-142">`depth` -の **depth** パラメーターは、 `Format-Custom` すべてのプロパティの展開の深さを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f703-142">`depth` - The **Depth** parameter of `Format-Custom` specifies the depth of expansion for all properties.</span></span> <span data-ttu-id="2f703-143">`depth`キーを使用すると、プロパティごとの展開の深さを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2f703-143">The `depth` key allows you to specify the depth of expansion per property.</span></span>
- <span data-ttu-id="2f703-144">`ascending` / `descending` -1 つまたは複数のプロパティの並べ替え順序を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2f703-144">`ascending` / `descending` - Allows you to specify the order of sorting for one or more properties.</span></span> <span data-ttu-id="2f703-145">これらはブール値です。</span><span class="sxs-lookup"><span data-stu-id="2f703-145">These are boolean values.</span></span>

<span data-ttu-id="2f703-146">指定された名前プレフィックスが明確である限り、ハッシュテーブルキーのスペルを確認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2f703-146">The hashtable keys need not be spelled out as long as the specified name prefix is unambiguous.</span></span> <span data-ttu-id="2f703-147">たとえば、は、 `n` の代わりに使用でき `Name` 、 `e` の代わりに使用でき `Expression` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-147">For example, `n` can be used in lieu of `Name` and `e` can be used in lieu of `Expression`.</span></span>

## <a name="examples"></a><span data-ttu-id="2f703-148">例</span><span class="sxs-lookup"><span data-stu-id="2f703-148">Examples</span></span>

### <a name="compare-object"></a><span data-ttu-id="2f703-149">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="2f703-149">Compare-Object</span></span>

<span data-ttu-id="2f703-150">計算されたプロパティを使用すると、入力オブジェクトのプロパティの比較方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="2f703-150">With calculated properties, you can control how the properties of the input objects are compared.</span></span> <span data-ttu-id="2f703-151">この例では、値を直接比較するのではなく、値を算術演算の結果と比較します (2 の剰余)。</span><span class="sxs-lookup"><span data-stu-id="2f703-151">In this example, rather than comparing the values directly, the values are compared to the result of the arithmetic operation (modulus of 2).</span></span>

```powershell
Compare-Object @{p=1} @{p=2} -property @{ Expression = { $_.p % 2 } }
```

```Output
 $_.p % 2  SideIndicator
---------- -------------
         0 =>
         1 <=
```

### <a name="convertto-html"></a><span data-ttu-id="2f703-152">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="2f703-152">ConvertTo-Html</span></span>

<span data-ttu-id="2f703-153">`ConvertTo-Html` オブジェクトのコレクションを HTML テーブルに変換できます。</span><span class="sxs-lookup"><span data-stu-id="2f703-153">`ConvertTo-Html` can convert a collection of objects to an HTML table.</span></span>
<span data-ttu-id="2f703-154">計算されたプロパティを使用すると、テーブルの表示方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="2f703-154">Calculated properties allow you to control how the table is presented.</span></span>

```powershell
Get-Alias |
  ConvertTo-Html Name,
                 Definition,
                 @{
                    expr={$_.Parameters.Keys.Count}
                    align='center'
                 } |
    Out-File .\aliases.htm -Force
```

<span data-ttu-id="2f703-155">この例では、PowerShell エイリアスの一覧と、各エイリアス化されたコマンドの number パラメーターを含む HTML テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f703-155">This example creates an HTML table containing a list of PowerShell aliases and the number parameters for each aliased command.</span></span> <span data-ttu-id="2f703-156">**Parametercount** 列の値は中央揃えになっています。</span><span class="sxs-lookup"><span data-stu-id="2f703-156">The values of **ParameterCount** column are centered.</span></span>

### <a name="format-custom"></a><span data-ttu-id="2f703-157">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="2f703-157">Format-Custom</span></span>

<span data-ttu-id="2f703-158">`Format-Custom` クラス定義と同様の形式で、オブジェクトのカスタムビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="2f703-158">`Format-Custom` provides a custom view of an object in a format similar to a class definition.</span></span> <span data-ttu-id="2f703-159">より複雑なオブジェクトには、複合型と深い入れ子になっているメンバーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2f703-159">More complex objects can contain members that are deeply nested with complex types.</span></span> <span data-ttu-id="2f703-160">の **depth** パラメーターは、 `Format-Custom` すべてのプロパティの展開の深さを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f703-160">The **Depth** parameter of `Format-Custom` specifies the depth of expansion for all properties.</span></span> <span data-ttu-id="2f703-161">`depth`キーを使用すると、プロパティごとの展開の深さを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2f703-161">The `depth` key allows you to specify the depth of expansion per property.</span></span>

<span data-ttu-id="2f703-162">この例では、キーを使用すると、 `depth` コマンドレットのカスタム出力が簡略化され `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-162">In this example, the `depth` key simplifies the custom output for the `Get-Date` cmdlet.</span></span> <span data-ttu-id="2f703-163">`Get-Date`**DateTime** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2f703-163">`Get-Date` returns a **DateTime** object.</span></span> <span data-ttu-id="2f703-164">このオブジェクトの **Date** プロパティも **DateTime** オブジェクトであるため、オブジェクトは入れ子になっています。</span><span class="sxs-lookup"><span data-stu-id="2f703-164">The **Date** property of this object is also a **DateTime** object, so the object is nested.</span></span>

```powershell
Get-Date | Format-Custom @{expr={$_.Date};depth=1},TimeOfDay
```

```Output
class DateTime
{
  $_.Date =
    class DateTime
    {
      Date = 8/7/2020 12:00:00 AM
      Day = 7
      DayOfWeek = Friday
      DayOfYear = 220
      Hour = 0
      Kind = Local
      Millisecond = 0
      Minute = 0
      Month = 8
      Second = 0
      Ticks = 637323552000000000
      TimeOfDay = 00:00:00
      Year = 2020
      DateTime = Friday, August 07, 2020 12:00:00 AM
    }
  TimeOfDay =
    class TimeSpan
    {
      Ticks = 435031592302
      Days = 0
      Hours = 12
      Milliseconds = 159
      Minutes = 5
      Seconds = 3
      TotalDays = 0.503508787386574
      TotalHours = 12.0842108972778
      TotalMilliseconds = 43503159.2302
      TotalMinutes = 725.052653836667
      TotalSeconds = 43503.1592302
    }
}
```

### <a name="format-list"></a><span data-ttu-id="2f703-165">Format-List</span><span class="sxs-lookup"><span data-stu-id="2f703-165">Format-List</span></span>

<span data-ttu-id="2f703-166">この例では、計算されたプロパティを使用して、出力の名前と形式をから変更し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-166">In this example, we use calculated properties to change the name and format of the output from `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem *.json -File |
  Format-List Fullname,
              @{
                 name='Modified'
                 expression={$_.LastWriteTime}
                 formatstring='O'
              },
              @{
                 name='Size'
                 expression={$_.Length/1KB}
                 formatstring='N2'
              }
```

```Output
FullName : C:\Git\PS-Docs\PowerShell-Docs\.markdownlint.json
Modified : 2020-07-23T10:26:28.4092457-07:00
Size     : 2.40

FullName : C:\Git\PS-Docs\PowerShell-Docs\.openpublishing.publish.config.json
Modified : 2020-07-23T10:26:28.4092457-07:00
Size     : 2.25

FullName : C:\Git\PS-Docs\PowerShell-Docs\.openpublishing.redirection.json
Modified : 2020-07-27T13:05:24.3887629-07:00
Size     : 324.60
```

### <a name="format-table"></a><span data-ttu-id="2f703-167">Format-Table</span><span class="sxs-lookup"><span data-stu-id="2f703-167">Format-Table</span></span>

<span data-ttu-id="2f703-168">この例では、計算されるプロパティによって、コンテンツの種類によってファイルを分類するために使用される **type** プロパティが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2f703-168">In this example, the calculated property adds a **Type** property used to classify the files by the content type.</span></span>

```powershell
Get-ChildItem -File |
  Sort-Object extension |
    Format-Table Name, Length -GroupBy @{
      name='Type'
      expression={
        switch ($_.extension) {
          '.md'   {'Content'}
          ''      {'Metacontent'}
          '.ps1'  {'Automation'}
          '.yml'  {'Automation'}
          default {'Configuration'}
        }
      }
    }
```

```Output
   Type: Metacontent

Name              Length
----              ------
ThirdPartyNotices   1229
LICENSE-CODE        1106
LICENSE            19047

   Type: Configuration

Name                                Length
----                                ------
.editorconfig                          183
.gitattributes                         419
.gitignore                             228
.markdownlint.json                    2456
.openpublishing.publish.config.json   2306
.openpublishing.redirection.json    332394
.localization-config                   232

   Type: Content

Name            Length
----            ------
README.md         3355
CONTRIBUTING.md    247

   Type: Automation

Name                      Length
----                      ------
.openpublishing.build.ps1    796
build.ps1                   7495
ci.yml                       645
ci-steps.yml                2035
daily.yml                   1271
```

### <a name="format-wide"></a><span data-ttu-id="2f703-169">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="2f703-169">Format-Wide</span></span>

<span data-ttu-id="2f703-170">コマンドレットを使用すると、 `Format-Wide` コレクション内のオブジェクトの1つのプロパティの値を複数列リストとして表示できます。</span><span class="sxs-lookup"><span data-stu-id="2f703-170">The `Format-Wide` cmdlet allows you to display the value of one property for objects in a collection as a multi-column list.</span></span>

<span data-ttu-id="2f703-171">この例では、ファイル名とサイズ (kb 単位) をワイドリストとして表示します。</span><span class="sxs-lookup"><span data-stu-id="2f703-171">For this example, we want to see the filename and the size (in kilobytes) as a wide listing.</span></span> <span data-ttu-id="2f703-172">`Format-Wide`には複数のプロパティが表示されないため、計算されるプロパティを使用して、2つのプロパティの値を1つの値に結合します。</span><span class="sxs-lookup"><span data-stu-id="2f703-172">Since `Format-Wide` does not display more than one property, we use a calculated property to combine the value of two properties into a single value.</span></span>

```powershell
Get-ChildItem -File |
  Format-Wide -Property @{e={'{0} ({1:N2}kb)' -f $_.name,($_.length/1kb)}}
```

```Output
.editorconfig (0.18kb)                          .gitattributes (0.41kb)
.gitignore (0.22kb)                             .localization-config (0.23kb)
.markdownlint.json (2.40kb)                     .openpublishing.build.ps1 (0.78kb)
.openpublishing.publish.config.json (2.25kb)    .openpublishing.redirection.json (324.60kb)
build.ps1 (7.32kb)                              ci.yml (0.63kb)
ci-steps.yml (1.99kb)                           CONTRIBUTING.md (0.24kb)
daily.yml (1.24kb)                              LICENSE (18.60kb)
LICENSE-CODE (1.08kb)                           README.md (3.28kb)
ThirdPartyNotices (1.20kb)
```

### <a name="group-object"></a><span data-ttu-id="2f703-173">Group-Object</span><span class="sxs-lookup"><span data-stu-id="2f703-173">Group-Object</span></span>

<span data-ttu-id="2f703-174">`Group-Object`コマンドレットは、指定されたプロパティの値に基づいて、オブジェクトをグループ単位で表示します。</span><span class="sxs-lookup"><span data-stu-id="2f703-174">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span> <span data-ttu-id="2f703-175">この例では、計算されるプロパティは、各コンテンツタイプのファイル数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="2f703-175">In this example, the calculated property counts the number of files of each content type.</span></span>

```powershell
Get-ChildItem -File |
  Sort-Object extension |
    Group-Object -NoElement -Property @{
      expression={
        switch ($_.extension) {
          '.md'   {'Content'}
          ''      {'Metacontent'}
          '.ps1'  {'Automation'}
          '.yml'  {'Automation'}
          default {'Configuration'}
        }
      }
    }
```

```Output
Count Name
----- ----
    5 Automation
    7 Configuration
    2 Content
    3 Metacontent
```

### <a name="select-object"></a><span data-ttu-id="2f703-176">Select-Object</span><span class="sxs-lookup"><span data-stu-id="2f703-176">Select-Object</span></span>

<span data-ttu-id="2f703-177">計算されたプロパティを使用して、コマンドレットを使用して出力オブジェクトにメンバーを追加でき `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-177">You can use calculated properties to add additional members to the objects output with the `Select-Object` cmdlet.</span></span> <span data-ttu-id="2f703-178">この例では、文字で始まる PowerShell エイリアスを一覧表示し `C` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-178">In this example, we are listing the PowerShell aliases that begin with the letter `C`.</span></span> <span data-ttu-id="2f703-179">を使用して、 `Select-Object` エイリアス、マップ先のコマンドレット、およびコマンドレットに対して定義されているパラメーターの数を出力します。</span><span class="sxs-lookup"><span data-stu-id="2f703-179">Using `Select-Object`, we output the alias, the cmdlet it's mapped to, and a count for the number of parameters defined for the cmdlet.</span></span> <span data-ttu-id="2f703-180">計算されたプロパティを使用して、 **Parametercount** プロパティを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2f703-180">Using a calculated property, we can create the **ParameterCount** property.</span></span>

```powershell
$aliases = Get-Alias c* |
  Select-Object Name,
                Definition,
                @{
                    name='ParameterCount'
                    expr={$_.Parameters.Keys.Count}
                }
$aliases | Get-Member
$aliases
```

```Output
   TypeName: Selected.System.Management.Automation.AliasInfo

Name           MemberType   Definition
----           ----------   ----------
Equals         Method       bool Equals(System.Object obj)
GetHashCode    Method       int GetHashCode()
GetType        Method       type GetType()
ToString       Method       string ToString()
Definition     NoteProperty string Definition=Get-Content
Name           NoteProperty string Name=cat
ParameterCount NoteProperty System.Int32 ParameterCount=21

Name    Definition         ParameterCount
----    ----------         --------------
cat     Get-Content                    21
cd      Set-Location                   15
cdd     Push-MyLocation                 1
chdir   Set-Location                   15
clc     Clear-Content                  20
clear   Clear-Host                      0
clhy    Clear-History                  17
cli     Clear-Item                     20
clp     Clear-ItemProperty             22
cls     Clear-Host                      0
clv     Clear-Variable                 19
cnsn    Connect-PSSession              29
compare Compare-Object                 20
copy    Copy-Item                      24
cp      Copy-Item                      24
cpi     Copy-Item                      24
cpp     Copy-ItemProperty              23
cvpa    Convert-Path                   13
```

### <a name="sort-object"></a><span data-ttu-id="2f703-181">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="2f703-181">Sort-Object</span></span>

<span data-ttu-id="2f703-182">計算されたプロパティを使用すると、プロパティごとに異なる順序でデータを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="2f703-182">Using the calculated properties, you can sort data in different orders per property.</span></span> <span data-ttu-id="2f703-183">この例では、CSV ファイルのデータを **日付** 順に昇順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="2f703-183">This example sorts data from a CSV file in ascending order by **Date**.</span></span> <span data-ttu-id="2f703-184">しかし、各日付内では、 **販売** された単位で行を降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="2f703-184">But within each date, it sorts the rows in descending order by **UnitsSold**.</span></span>

```powershell
Import-Csv C:\temp\sales-data.csv |
  Sort-Object Date, @{expr={$_.UnitsSold}; desc=$true}, Salesperson  |
    Select-Object Date, Salesperson, UnitsSold
```

```Output
Date       Salesperson UnitsSold
----       ----------- ---------
2020-08-01 Sally       3
2020-08-01 Anne        2
2020-08-01 Fred        1
2020-08-02 Anne        6
2020-08-02 Fred        2
2020-08-02 Sally       0
2020-08-03 Anne        5
2020-08-03 Sally       3
2020-08-03 Fred        1
2020-08-04 Anne        2
2020-08-04 Fred        2
2020-08-04 Sally       2
```

## <a name="notes"></a><span data-ttu-id="2f703-185">メモ</span><span class="sxs-lookup"><span data-stu-id="2f703-185">Notes</span></span>

- <span data-ttu-id="2f703-186">式スクリプトブロックは、ハッシュテーブルのエントリとして指定するのではなく、引数として _直接_ 指定することができ `Expression` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-186">You may specify the expression script block _directly_ , as an argument, rather than specifying it as the `Expression` entry in a hashtable.</span></span> <span data-ttu-id="2f703-187">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2f703-187">For example:</span></span>

  ```powershell
  '1', '10', '2' | Sort-Object { [int] $_ }
  ```

  <span data-ttu-id="2f703-188">この例は、、、など、キーを介してプロパティに名前を付ける (またはサポートする) 必要がないコマンドレットに便利です `Name` `Sort-Object` `Group-Object` `Measure-Object` 。</span><span class="sxs-lookup"><span data-stu-id="2f703-188">This example is convenient for cmdlets that do not require (or support) naming a property via the `Name` key, such as `Sort-Object`, `Group-Object`, and `Measure-Object`.</span></span>

  <span data-ttu-id="2f703-189">プロパティの名前付けをサポートするコマンドレットの場合、スクリプトブロックは文字列に変換され、出力でプロパティの名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f703-189">For cmdlets that support naming the property, the script block is converted to a string and used as the name of the property in the output.</span></span>

- <span data-ttu-id="2f703-190">`Expression` スクリプトブロックは _子_ スコープで実行されます。つまり、呼び出し元の変数を直接変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f703-190">`Expression` script blocks run in _child_ scopes, meaning that the caller's variables cannot be directly modified.</span></span>

- <span data-ttu-id="2f703-191">パイプラインロジックは、スクリプトブロックからの出力に適用され `Expression` ます。</span><span class="sxs-lookup"><span data-stu-id="2f703-191">Pipeline logic is applied to the output from `Expression` script blocks.</span></span> <span data-ttu-id="2f703-192">これは、単一要素の配列を出力すると、その配列がラップ解除されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2f703-192">This means that outputting a single-element array causes that array to be unwrapped.</span></span>

- <span data-ttu-id="2f703-193">ほとんどのコマンドレットでは、式スクリプトブロック内のエラーは自動的に無視されます。</span><span class="sxs-lookup"><span data-stu-id="2f703-193">For most cmdlets, errors inside expression script blocks are quietly ignored.</span></span>
  <span data-ttu-id="2f703-194">`Sort-Object`では、ステートメントの終了エラーとスクリプト終了エラーは _出力_ されますが、ステートメントは終了しません。</span><span class="sxs-lookup"><span data-stu-id="2f703-194">For `Sort-Object`, statement-terminating and script-terminating errors are _output_ but they do not terminate the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f703-195">参照</span><span class="sxs-lookup"><span data-stu-id="2f703-195">See Also</span></span>

[<span data-ttu-id="2f703-196">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="2f703-196">about_Hash_Tables</span></span>](about_hash_tables.md)

[<span data-ttu-id="2f703-197">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="2f703-197">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="2f703-198">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="2f703-198">ConvertTo-Html</span></span>](xref:Microsoft.PowerShell.Utility.ConvertTo-Html)

[<span data-ttu-id="2f703-199">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="2f703-199">Format-Custom</span></span>](xref:Microsoft.PowerShell.Utility.Format-Custom)

[<span data-ttu-id="2f703-200">Format-List</span><span class="sxs-lookup"><span data-stu-id="2f703-200">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)

[<span data-ttu-id="2f703-201">Format-Table</span><span class="sxs-lookup"><span data-stu-id="2f703-201">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="2f703-202">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="2f703-202">Format-Wide</span></span>](xref:Microsoft.PowerShell.Utility.Format-Wide)

[<span data-ttu-id="2f703-203">Group-Object</span><span class="sxs-lookup"><span data-stu-id="2f703-203">Group-Object</span></span>](xref:Microsoft.PowerShell.Utility.Group-Object)

[<span data-ttu-id="2f703-204">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="2f703-204">Measure-Object</span></span>](xref:Microsoft.PowerShell.Utility.Measure-Object)

[<span data-ttu-id="2f703-205">Select-Object</span><span class="sxs-lookup"><span data-stu-id="2f703-205">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="2f703-206">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="2f703-206">Sort-Object</span></span>](xref:Microsoft.PowerShell.Utility.Sort-Object)

[<span data-ttu-id="2f703-207">.NET での型の書式設定</span><span class="sxs-lookup"><span data-stu-id="2f703-207">Format types in .NET</span></span>](/dotnet/standard/base-types/formatting-types)
