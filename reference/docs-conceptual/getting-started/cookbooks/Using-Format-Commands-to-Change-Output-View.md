---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Format コマンドを使用した出力ビューの変更
ms.assetid: 63515a06-a6f7-4175-a45e-a0537f4f6d05
ms.openlocfilehash: 97d3a9e04abb61bb80a0b8c67d9fb9e885a0b91b
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="using-format-commands-to-change-output-view"></a><span data-ttu-id="339bc-103">Format コマンドを使用した出力ビューの変更</span><span class="sxs-lookup"><span data-stu-id="339bc-103">Using Format Commands to Change Output View</span></span>

<span data-ttu-id="339bc-104">Windows PowerShell には、特定のオブジェクトのプロパティの表示を制御するためのコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="339bc-104">Windows PowerShell has a set of cmdlets that allow you to control which properties are displayed for particular objects.</span></span> <span data-ttu-id="339bc-105">すべてのコマンドレットの名前は、動詞 **Format** から始まります。</span><span class="sxs-lookup"><span data-stu-id="339bc-105">The names of all the cmdlets begin with the verb **Format**.</span></span> <span data-ttu-id="339bc-106">表示するプロパティを 1 つ以上選択できます。</span><span class="sxs-lookup"><span data-stu-id="339bc-106">They let you select one or more properties to show.</span></span>

<span data-ttu-id="339bc-107">**Format** コマンドレットとしては、**Format-Wide**、**Format-List**、**Format-Table**、および **Format-Custom** があります。</span><span class="sxs-lookup"><span data-stu-id="339bc-107">The **Format** cmdlets are **Format-Wide**, **Format-List**, **Format-Table**, and **Format-Custom**.</span></span> <span data-ttu-id="339bc-108">このユーザー ガイドでは、**Format-Wide**、**Format-List**、および **Format-Table** コマンドレットについてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="339bc-108">We will only describe the **Format-Wide**, **Format-List**, and **Format-Table** cmdlets in this user's guide.</span></span>

<span data-ttu-id="339bc-109">各 Format コマンドレットには、表示する特定のプロパティを指定しない場合に使用される既定のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="339bc-109">Each format cmdlet has default properties that will be used if you do not specify specific properties to display.</span></span> <span data-ttu-id="339bc-110">どのコマンドレットでも、同じパラメーター名 **Property** を使用して、表示するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="339bc-110">Each cmdlet also uses the same parameter name, **Property**, to specify which properties you want to display.</span></span> <span data-ttu-id="339bc-111">**Format-Wide** はプロパティを 1 つだけ表示するため、その **Property** パラメーターには値を 1 つだけ設定します。ただし、**Format-List** と **Format-Table** の Property パラメーターには、プロパティ名のリストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="339bc-111">Because **Format-Wide** only shows a single property, its **Property** parameter only takes a single value, but the property parameters of **Format-List** and **Format-Table** will accept a list of property names.</span></span>

<span data-ttu-id="339bc-112">Windows PowerShell のインスタンスを 2 つ実行してコマンド **Get-Process -Name powershell** を使用すると、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="339bc-112">If you use the command **Get-Process -Name powershell** with two instances of Windows PowerShell running, you get output that looks like this:</span></span>

```output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    995       9    30308      27996   152     2.73   2760 powershell
    331       9    23284      29084   143     1.06   3448 powershell
```

<span data-ttu-id="339bc-113">このセクションの残りの部分で、このコマンドの出力の表示の仕方を **Format** コマンドレットを使用して変更する方法について解説します。</span><span class="sxs-lookup"><span data-stu-id="339bc-113">In the rest of this section, we will explore how to use **Format** cmdlets to change the way the output of this command is displayed.</span></span>

### <a name="using-format-wide-for-single-item-output"></a><span data-ttu-id="339bc-114">単一項目出力のための Format-Wide の使用</span><span class="sxs-lookup"><span data-stu-id="339bc-114">Using Format-Wide for Single-Item Output</span></span>

<span data-ttu-id="339bc-115">**Format-Wide** コマンドレットは、既定では、オブジェクトの既定プロパティのみ表示します。</span><span class="sxs-lookup"><span data-stu-id="339bc-115">The **Format-Wide** cmdlet, by default, displays only the default property of an object.</span></span> <span data-ttu-id="339bc-116">各オブジェクトに関連付けられている情報が、1 つの列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="339bc-116">The information associated with each object is displayed in a single column:</span></span>

```
PS> Get-Process -Name powershell | Format-Wide

powershell                              powershell
```

<span data-ttu-id="339bc-117">既定以外のプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="339bc-117">You can also specify a non-default property:</span></span>

```
PS> Get-Process -Name powershell | Format-Wide -Property Id

2760                                    3448
```

#### <a name="controlling-format-wide-display-with-column"></a><span data-ttu-id="339bc-118">列による Format-Wide 表示の制御</span><span class="sxs-lookup"><span data-stu-id="339bc-118">Controlling Format-Wide Display with Column</span></span>

<span data-ttu-id="339bc-119">**Format-Wide** コマンドレットでは、一度に表示できるプロパティは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="339bc-119">With the **Format-Wide** cmdlet, you can only display a single property at a time.</span></span> <span data-ttu-id="339bc-120">これは、1 行に要素が 1 つだけ示される単純なリストを表示する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="339bc-120">This makes it useful for displaying simple lists that show only one element per line.</span></span> <span data-ttu-id="339bc-121">単純なリスト表示にするには、**Column** パラメーターの値を 1 に設定します。次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="339bc-121">To get a simple listing, set the value of the **Column** parameter to 1 by typing:</span></span>

```powershell
Get-Command Format-Wide -Property Name -Column 1
```

### <a name="using-format-list-for-a-list-view"></a><span data-ttu-id="339bc-122">リスト ビューのための Format-List の使用</span><span class="sxs-lookup"><span data-stu-id="339bc-122">Using Format-List for a List View</span></span>

<span data-ttu-id="339bc-123">**Format-List** コマンドレットは、リストの形式でオブジェクトを表示します。各プロパティはラベル付けされ、別々の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="339bc-123">The **Format-List** cmdlet displays an object in the form of a listing, with each property labeled and displayed on a separate line:</span></span>

```
PS> Get-Process -Name powershell | Format-List

Id      : 2760
Handles : 1242
CPU     : 3.03125
Name    : powershell

Id      : 3448
Handles : 328
CPU     : 1.0625
Name    : powershell
```

<span data-ttu-id="339bc-124">必要な数だけプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="339bc-124">You can specify as many properties as you want:</span></span>

```
PS> Get-Process -Name powershell | Format-List -Property ProcessName,FileVersion
,StartTime,Id

ProcessName : powershell
FileVersion : 1.0.9567.1
StartTime   : 2006-05-24 13:42:00
Id          : 2760

ProcessName : powershell
FileVersion : 1.0.9567.1
StartTime   : 2006-05-24 13:54:28
Id          : 3448
```

#### <a name="getting-detailed-information-by-using-format-list-with-wildcards"></a><span data-ttu-id="339bc-125">Format-List でワイルドカードを使用して詳細情報を取得する</span><span class="sxs-lookup"><span data-stu-id="339bc-125">Getting Detailed Information by Using Format-List with Wildcards</span></span>

<span data-ttu-id="339bc-126">**Format-List** コマンドレットでは、その **Property** パラメーターの値としてワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="339bc-126">The **Format-List** cmdlet lets you use a wildcard as the value of its **Property** parameter.</span></span> <span data-ttu-id="339bc-127">こうすることで、詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="339bc-127">This lets you display detailed information.</span></span> <span data-ttu-id="339bc-128">多くの場合、オブジェクトには必要以上の情報が含まれています。既定では Windows PowerShell がすべてのプロパティ値は表示しないのはそのためです。</span><span class="sxs-lookup"><span data-stu-id="339bc-128">Often, objects include more information than you need, which is why Windows PowerShell does not show all property values by default.</span></span> <span data-ttu-id="339bc-129">オブジェクトのプロパティをすべて表示するには、**Format-List -Property \&#42;** コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="339bc-129">To show all of properties of an object, use the **Format-List -Property \&#42;** command.</span></span> <span data-ttu-id="339bc-130">次のコマンドは、1 つのプロセスについて 60 行を超える出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="339bc-130">The following command generates over 60 lines of output for a single process:</span></span>

```powershell
Get-Process -Name powershell | Format-List -Property *
```

<span data-ttu-id="339bc-131">**Format-List** コマンドは詳細の表示に役立ちますが、項目が多数含まれる出力の概要が必要な場合は、より単純な表形式ビューの方がしばしば好都合です。</span><span class="sxs-lookup"><span data-stu-id="339bc-131">Although the **Format-List** command is useful for showing detail, if you want an overview of output that includes many items, a simpler tabular view is often more useful.</span></span>

### <a name="using-format-table-for-tabular-output"></a><span data-ttu-id="339bc-132">表形式出力のための Format-Table の使用</span><span class="sxs-lookup"><span data-stu-id="339bc-132">Using Format-Table for Tabular Output</span></span>

<span data-ttu-id="339bc-133">プロパティ名を指定せずに **Format-Table** コマンドレットを使用して **Get-Process** コマンドの出力を書式設定した場合は、書式設定を行わない場合とまったく同じ出力になります。</span><span class="sxs-lookup"><span data-stu-id="339bc-133">If you use the **Format-Table** cmdlet with no property names specified to format the output of the **Get-Process** command, you get exactly the same output as you do without performing any formatting.</span></span> <span data-ttu-id="339bc-134">その理由は、ほとんどの Windows PowerShell オブジェクトがそうであるように、プロセスは通常、表形式で表示されるからです。</span><span class="sxs-lookup"><span data-stu-id="339bc-134">The reason is that processes are usually displayed in a tabular format, as are most Windows PowerShell objects.</span></span>

```
PS> Get-Process -Name powershell | Format-Table

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
   1488       9    31568      29460   152     3.53   2760 powershell
    332       9    23140        632   141     1.06   3448 powershell
```

#### <a name="improving-format-table-output-autosize"></a><span data-ttu-id="339bc-135">Format-Table 出力の改善 (AutoSize)</span><span class="sxs-lookup"><span data-stu-id="339bc-135">Improving Format-Table Output (AutoSize)</span></span>

<span data-ttu-id="339bc-136">表形式ビューは比較情報を大量に表示するには便利ですが、データの表示幅が狭すぎる場合は解釈しにくいことがあります。</span><span class="sxs-lookup"><span data-stu-id="339bc-136">Although a tabular view is useful for displaying a lot of comparable information, it may be difficult to interpret if the display is too narrow for the data.</span></span> <span data-ttu-id="339bc-137">たとえば、プロセス パス、ID、名前、および会社を表示しようとすると、プロセス パスと会社の列の出力が切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="339bc-137">For example, if you try to display process path, ID, name, and company, you get truncated output for the process path and the company column:</span></span>

```
PS> Get-Process -Name powershell | Format-Table -Property Path,Name,Id,Company

Path                Name                                 Id Company
----                ----                                 -- -------
C:\Program Files... powershell                         2836 Microsoft Corpor...
```

<span data-ttu-id="339bc-138">**Format-Table** コマンドを実行するときに **AutoSize** パラメーターを指定すると、Windows PowerShell は、表示される実際のデータに基づいて、列の幅を計算します。</span><span class="sxs-lookup"><span data-stu-id="339bc-138">If you specify the **AutoSize** parameter when you run the **Format-Table** command, Windows PowerShell will calculate column widths based on the actual data you are going to display.</span></span> <span data-ttu-id="339bc-139">これによって **Path** 列は読み取れるようになりますが、会社列は切り捨てられたままです。</span><span class="sxs-lookup"><span data-stu-id="339bc-139">This makes the **Path** column readable, but the company column remains truncated:</span></span>

```
PS> Get-Process -Name powershell | Format-Table -Property Path,Name,Id,Company -
AutoSize

Path                                                    Name         Id Company
----                                                    ----         -- -------
C:\Program Files\Windows PowerShell\v1.0\powershell.exe powershell 2836 Micr...
```

<span data-ttu-id="339bc-140">**Format-Table** コマンドレットはデータを切り捨てることもありますが、それが行われるのは画面の端だけです。</span><span class="sxs-lookup"><span data-stu-id="339bc-140">The **Format-Table** cmdlet might still truncate data, but it will only do so at the end of the screen.</span></span> <span data-ttu-id="339bc-141">最後に表示されるもの以外のプロパティには、最長データ要素が正しく表示されるために必要なだけのサイズが与えられます。</span><span class="sxs-lookup"><span data-stu-id="339bc-141">Properties, other than the last one displayed, are given as much size as they need for their longest data element to display correctly.</span></span> <span data-ttu-id="339bc-142">**Property** 値リストで **Path** と **Company** の場所を入れ替えると、その会社名が表示されるようになりますが、パスは切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="339bc-142">You can see that company name is visible but path is truncated if you swap the locations of **Path** and **Company** in the **Property** value list:</span></span>

```
PS> Get-Process -Name powershell | Format-Table -Property Company,Name,Id,Path -
AutoSize

Company               Name         Id Path
-------               ----         -- ----
Microsoft Corporation powershell 2836 C:\Program Files\Windows PowerShell\v1...
```

<span data-ttu-id="339bc-143">**Format-Table** コマンドは、プロパティ リストの先頭に近いプロパティほど重要であると見なします。</span><span class="sxs-lookup"><span data-stu-id="339bc-143">The **Format-Table** command assumes that the nearer a property is to the beginning of the property list, the more important it is.</span></span> <span data-ttu-id="339bc-144">したがって、先頭に最も近いプロパティを完全に表示しようとします。</span><span class="sxs-lookup"><span data-stu-id="339bc-144">So it attempts to display the properties nearest the beginning completely.</span></span> <span data-ttu-id="339bc-145">**Format-Table** コマンドがすべてのプロパティを表示できない場合は、表示から一部の列が削除され、警告が出されます。</span><span class="sxs-lookup"><span data-stu-id="339bc-145">If the **Format-Table** command cannot display all the properties, it will remove some columns from the display and provide a warning.</span></span> <span data-ttu-id="339bc-146">この動作は、**Name** をリストの最後のプロパティにすれば、確認できます。</span><span class="sxs-lookup"><span data-stu-id="339bc-146">You can see this behavior if you make **Name** the last property in the list:</span></span>

```
PS> Get-Process -Name powershell | Format-Table -Property Company,Path,Id,Name -
AutoSize

WARNING: column "Name" does not fit into the display and was removed.

Company               Path                                                    I
                                                                              d
-------               ----                                                    -
Microsoft Corporation C:\Program Files\Windows PowerShell\v1.0\powershell.exe 6
```

<span data-ttu-id="339bc-147">上記の出力では、リストに収まるように ID 列が切り捨てられ、列見出しが重なっています。</span><span class="sxs-lookup"><span data-stu-id="339bc-147">In the output above, the ID column is truncated to make it fit into the listing, and the column headings are stacked up.</span></span> <span data-ttu-id="339bc-148">列の自動サイズ変更は、常に目的どおりになるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="339bc-148">Automatically resizing the columns does not always do what you want.</span></span>

#### <a name="wrapping-format-table-output-in-columns-wrap"></a><span data-ttu-id="339bc-149">Format-Table 出力の列内の折り返し (Wrap)</span><span class="sxs-lookup"><span data-stu-id="339bc-149">Wrapping Format-Table Output in Columns (Wrap)</span></span>

<span data-ttu-id="339bc-150">**Wrap** パラメーターを使用して、長い **Format-Table** データをその表示列内で強制的に折り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="339bc-150">You can force lengthy **Format-Table** data to wrap within its display column by using the **Wrap** parameter.</span></span> <span data-ttu-id="339bc-151">**Wrap** パラメーターだけを使用した場合、必ずしも期待どおりにはなりません。同時に **AutoSize** も指定しなければ、既定の設定が使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="339bc-151">Using the **Wrap** parameter alone will not necessarily do what you expect, since it uses default settings if you do not also specify **AutoSize**:</span></span>

```
PS> Get-Process -Name powershell | Format-Table -Wrap -Property Name,Id,Company,
Path

Name                                 Id Company             Path
----                                 -- -------             ----
powershell                         2836 Microsoft Corporati C:\Program Files\Wi
                                        on                  ndows PowerShell\v1
                                                            .0\powershell.exe
```

<span data-ttu-id="339bc-152">**Wrap** パラメーターを単独で使用することの利点は、処理があまり遅くならないことです。</span><span class="sxs-lookup"><span data-stu-id="339bc-152">An advantage of using the **Wrap** parameter by itself is that it does not slow down processing very much.</span></span> <span data-ttu-id="339bc-153">**AutoSize** を使用した場合、大規模なディレクトリ システムの再帰的ファイル リスト表示を実行すると、最初の出力項目が表示されるまで非常に長い時間がかかり、大量のメモリが使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="339bc-153">If you perform a recursive file listing of a large directory system, it might take a very long time and use a lot of memory before displaying the first output items if you use **AutoSize**.</span></span>

<span data-ttu-id="339bc-154">システム負荷が気にならなければ、**AutoSize** は **Wrap** パラメーターと同時に使用した場合に効果を発揮します。</span><span class="sxs-lookup"><span data-stu-id="339bc-154">If you are not concerned about system load, then **AutoSize** works well with the **Wrap** parameter.</span></span> <span data-ttu-id="339bc-155">**Wrap** パラメーターなしで **AutoSize** を指定した場合と同様に、最初の各列には常に、各項目を 1 行に表示するために必要なだけの幅が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="339bc-155">The initial columns are always allotted as much width as they need to display items on one line, just as when you specify **AutoSize** without the **Wrap** parameter.</span></span> <span data-ttu-id="339bc-156">唯一の違いは、必要に応じて最終的な列が折り返されることです。</span><span class="sxs-lookup"><span data-stu-id="339bc-156">The only difference is that the final column will be wrapped if necessary:</span></span>

```
PS> Get-Process -Name powershell | Format-Table -Wrap -AutoSize -Property Name,I
d,Company,Path

Name         Id Company               Path
----         -- -------               ----
powershell 2836 Microsoft Corporation C:\Program Files\Windows PowerShell\v1.0\
                                      powershell.exe
```

<span data-ttu-id="339bc-157">最大幅の列を最初に指定すると、一部の列が表示されない場合があります。したがって、最小のデータ要素を最初に指定することが最も安全です。</span><span class="sxs-lookup"><span data-stu-id="339bc-157">Some columns might not be displayed if you specify the widest columns first, so it is safest to specify the smallest data elements first.</span></span> <span data-ttu-id="339bc-158">次の例では、極端に幅をとるパス要素を最初に指定しています。折り返しも使用していますが、最後の **Name** 列が失われています。</span><span class="sxs-lookup"><span data-stu-id="339bc-158">In the following example, we specify the extremely wide path element first, and even with wrapping, we still lose the final **Name** column:</span></span>

```
PS> Get-Process -Name powershell | Format-Table -Wrap -AutoSize -Property Path,I
d,Company,Name

WARNING: column "Name" does not fit into the display and was removed.

Path                                                      Id Company
----                                                      -- -------
C:\Program Files\Windows PowerShell\v1.0\powershell.exe 2836 Microsoft Corporat
                                                             ion
```

#### <a name="organizing-table-output--groupby"></a><span data-ttu-id="339bc-159">表出力の整理 (-GroupBy)</span><span class="sxs-lookup"><span data-stu-id="339bc-159">Organizing Table Output (-GroupBy)</span></span>

<span data-ttu-id="339bc-160">表形式出力制御のためのもう一つの便利なパラメーターは、**GroupBy** です。</span><span class="sxs-lookup"><span data-stu-id="339bc-160">Another useful parameter for tabular output control is **GroupBy**.</span></span> <span data-ttu-id="339bc-161">長い表形式リストは特に、比較しにくい場合があります。</span><span class="sxs-lookup"><span data-stu-id="339bc-161">Longer tabular listings in particular may be hard to compare.</span></span> <span data-ttu-id="339bc-162">**GroupBy** パラメーターは、プロパティ値に基づいて出力をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="339bc-162">The **GroupBy** parameter groups output based on a property value.</span></span> <span data-ttu-id="339bc-163">たとえば、検査しやすくするために、プロセスを会社別にグループ化できます。この場合、会社の値をプロパティ リストに入れません。</span><span class="sxs-lookup"><span data-stu-id="339bc-163">For example, we can group processes by company for easier inspection, omitting the company value from the property listing:</span></span>

```
PS> Get-Process -Name powershell | Format-Table -Wrap -AutoSize -Property Name,I
d,Path -GroupBy Company

   Company: Microsoft Corporation

Name         Id Path
----         -- ----
powershell 1956 C:\Program Files\Windows PowerShell\v1.0\powershell.exe
powershell 2656 C:\Program Files\Windows PowerShell\v1.0\powershell.exe
```