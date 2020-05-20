---
ms.date: 11/22/2019
keywords: powershell,コマンドレット
title: Format コマンドを使用した出力ビューの変更
ms.openlocfilehash: f270d5ec5efe5caf506d6a8a45285990996f6ae6
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "74417596"
---
# <a name="using-format-commands-to-change-output-view"></a><span data-ttu-id="493d0-103">Format コマンドを使用した出力ビューの変更</span><span class="sxs-lookup"><span data-stu-id="493d0-103">Using Format Commands to Change Output View</span></span>

<span data-ttu-id="493d0-104">PowerShell には、特定のオブジェクトに対するプロパティの表示方法を制御できるコマンドレットのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="493d0-104">PowerShell has a set of cmdlets that allow you to control how properties are displayed for particular objects.</span></span> <span data-ttu-id="493d0-105">すべてのコマンドレットの名前は、動詞 `Format` から始まります。</span><span class="sxs-lookup"><span data-stu-id="493d0-105">The names of all the cmdlets begin with the verb `Format`.</span></span> <span data-ttu-id="493d0-106">これらには、表示するプロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="493d0-106">They let you select which properties you want to show.</span></span>

```powershell
Get-Command -Verb Format -Module Microsoft.PowerShell.Utility
```

```Output
CommandType     Name               Version    Source
-----------     ----               -------    ------
Cmdlet          Format-Custom      6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Hex         6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-List        6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Table       6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Wide        6.1.0.0    Microsoft.PowerShell.Utility
```

<span data-ttu-id="493d0-107">この記事では、`Format-Wide`、`Format-List`、`Format-Table` のコマンドレットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="493d0-107">This article describes the `Format-Wide`, `Format-List`, and `Format-Table` cmdlets.</span></span>

<span data-ttu-id="493d0-108">PowerShell の各オブジェクトの種類には、表示するプロパティを指定しない場合に使用される既定のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="493d0-108">Each object type in PowerShell has default properties that are used when you don't specify which properties to display.</span></span> <span data-ttu-id="493d0-109">どのコマンドレットでも、同じ **Property** パラメーターを使用して、表示するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="493d0-109">Each cmdlet also uses the same **Property** parameter to specify which properties you want to display.</span></span> <span data-ttu-id="493d0-110">`Format-Wide` はプロパティを 1 つだけ表示するため、その **Property** パラメーターには値を 1 つだけ設定します。ただし、`Format-List` と `Format-Table` の Property パラメーターには、プロパティ名のリストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="493d0-110">Because `Format-Wide` only shows a single property, its **Property** parameter only takes a single value, but the property parameters of `Format-List` and `Format-Table` accept a list of property names.</span></span>

<span data-ttu-id="493d0-111">この例では、`Get-Process` コマンドレットの既定の出力は、Internet Explorer の 2 つのインスタンスが実行されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="493d0-111">In this example, the default output of `Get-Process` cmdlet shows that we have two instances of Internet Explorer running.</span></span>

```powershell
Get-Process -Name iexplore
```

<span data-ttu-id="493d0-112">**Process** オブジェクトの既定の形式では、次に示すプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="493d0-112">The default format for **Process** objects displays the properties shown here:</span></span>

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     32    25.52      10.25      13.11   12808   1 iexplore
     52    11.46      26.46       3.55   21748   1 iexplore
```

## <a name="using-format-wide-for-single-item-output"></a><span data-ttu-id="493d0-113">単一項目出力のための Format-Wide の使用</span><span class="sxs-lookup"><span data-stu-id="493d0-113">Using Format-Wide for Single-Item Output</span></span>

<span data-ttu-id="493d0-114">`Format-Wide` コマンドレットでは、既定では、オブジェクトの既定のプロパティだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="493d0-114">The `Format-Wide` cmdlet, by default, displays only the default property of an object.</span></span> <span data-ttu-id="493d0-115">各オブジェクトに関連付けられている情報が、1 つの列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="493d0-115">The information associated with each object is displayed in a single column:</span></span>

```powershell
Get-Command -Verb Format | Format-Wide
```

```Output
Format-Custom          Format-Hex
Format-List            Format-Table
Format-Wide
```

<span data-ttu-id="493d0-116">既定以外のプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="493d0-116">You can also specify a non-default property:</span></span>

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun
```

```Output
Custom                 Hex
List                   Table
Wide
```

### <a name="controlling-format-wide-display-with-column"></a><span data-ttu-id="493d0-117">列による Format-Wide 表示の制御</span><span class="sxs-lookup"><span data-stu-id="493d0-117">Controlling Format-Wide Display with Column</span></span>

<span data-ttu-id="493d0-118">`Format-Wide` コマンドレットでは、一度に表示できるプロパティは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="493d0-118">With the `Format-Wide` cmdlet, you can only display a single property at a time.</span></span> <span data-ttu-id="493d0-119">これは、大きなリストを複数の列に表示する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="493d0-119">This makes it useful for displaying large lists in multiple columns.</span></span>

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun -Column 3
```

```Output
Custom                 Hex                  List
Table                  Wide

```

## <a name="using-format-list-for-a-list-view"></a><span data-ttu-id="493d0-120">リスト ビューのための Format-List の使用</span><span class="sxs-lookup"><span data-stu-id="493d0-120">Using Format-List for a List View</span></span>

<span data-ttu-id="493d0-121">`Format-List` コマンドレットによって、リストの形式でオブジェクトを表示します。各プロパティはラベル付けされ、別々の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="493d0-121">The `Format-List` cmdlet displays an object in the form of a listing, with each property labeled and displayed on a separate line:</span></span>

```powershell
Get-Process -Name iexplore | Format-List
```

```Output
Id      : 12808
Handles : 578
CPU     : 13.140625
SI      : 1
Name    : iexplore

Id      : 21748
Handles : 641
CPU     : 3.59375
SI      : 1
Name    : iexplore
```

<span data-ttu-id="493d0-122">必要な数だけプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="493d0-122">You can specify as many properties as you want:</span></span>

```powershell
Get-Process -Name iexplore | Format-List -Property ProcessName,FileVersion,StartTime,Id
```

```Output
ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:58 AM
Id          : 12808

ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:57 AM
Id          : 21748
```

### <a name="getting-detailed-information-by-using-format-list-with-wildcards"></a><span data-ttu-id="493d0-123">Format-List でワイルドカードを使用して詳細情報を取得する</span><span class="sxs-lookup"><span data-stu-id="493d0-123">Getting Detailed Information by Using Format-List with Wildcards</span></span>

<span data-ttu-id="493d0-124">`Format-List` コマンドレットでは、その **Property** パラメーターの値としてワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="493d0-124">The `Format-List` cmdlet lets you use a wildcard as the value of its **Property** parameter.</span></span> <span data-ttu-id="493d0-125">こうすることで、詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="493d0-125">This lets you display detailed information.</span></span> <span data-ttu-id="493d0-126">多くの場合、オブジェクトには必要以上の情報が含まれています。既定では PowerShell ですべてのプロパティ値が表示されないのはそのためです。</span><span class="sxs-lookup"><span data-stu-id="493d0-126">Often, objects include more information than you need, which is why PowerShell doesn't show all property values by default.</span></span> <span data-ttu-id="493d0-127">オブジェクトのプロパティをすべて表示するには、`Format-List -Property *` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="493d0-127">To show all of properties of an object, use the `Format-List -Property *` command.</span></span> <span data-ttu-id="493d0-128">次のコマンドは、1 つのプロセスについて 60 行を超える出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="493d0-128">The following command generates over 60 lines of output for a single process:</span></span>

```powershell
Get-Process -Name iexplore | Format-List -Property *
```

<span data-ttu-id="493d0-129">`Format-List` コマンドは詳細の表示に役立ちますが、項目が多数含まれる出力の概要が必要な場合は、よりシンプルな表形式ビューの方が便利なことが多いです。</span><span class="sxs-lookup"><span data-stu-id="493d0-129">Although the `Format-List` command is useful for showing detail, if you want an overview of output that includes many items, a simpler tabular view is often more useful.</span></span>

## <a name="using-format-table-for-tabular-output"></a><span data-ttu-id="493d0-130">表形式出力のための Format-Table の使用</span><span class="sxs-lookup"><span data-stu-id="493d0-130">Using Format-Table for Tabular Output</span></span>

<span data-ttu-id="493d0-131">プロパティ名を指定せずに `Format-Table` コマンドレットを使用して `Get-Process` コマンドの出力を書式設定した場合は、`Format` コマンドレットを使用せずに行った場合とまったく同じ出力になります。</span><span class="sxs-lookup"><span data-stu-id="493d0-131">If you use the `Format-Table` cmdlet with no property names specified to format the output of the `Get-Process` command, you get exactly the same output as you do without a `Format` cmdlet.</span></span> <span data-ttu-id="493d0-132">既定では、PowerShell によって **Process** オブジェクトが表形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="493d0-132">By default, PowerShell displays **Process** objects in a tabular format.</span></span>

```powershell
Get-Service -Name win* | Format-Table
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  WinHttpAutoProx... WinHTTP Web Proxy Auto-Discovery Se...
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Manag...
```

### <a name="improving-format-table-output-autosize"></a><span data-ttu-id="493d0-133">Format-Table 出力の改善 (AutoSize)</span><span class="sxs-lookup"><span data-stu-id="493d0-133">Improving Format-Table Output (AutoSize)</span></span>

<span data-ttu-id="493d0-134">表形式ビューは情報を大量に表示するには便利ですが、データの表示幅が狭すぎる場合は解釈しにくいことがあります。</span><span class="sxs-lookup"><span data-stu-id="493d0-134">Although a tabular view is useful for displaying lots of information, it may be difficult to interpret if the display is too narrow for the data.</span></span> <span data-ttu-id="493d0-135">前の例では、出力は切り捨てられています。</span><span class="sxs-lookup"><span data-stu-id="493d0-135">In the previous example, the output is truncated.</span></span> <span data-ttu-id="493d0-136">`Format-Table` コマンドを実行するときに **AutoSize** パラメーターを指定すると、PowerShell では、表示される実際のデータに基づいて列の幅を計算します。</span><span class="sxs-lookup"><span data-stu-id="493d0-136">If you specify the **AutoSize** parameter when you run the `Format-Table` command, PowerShell calculates column widths based on the actual data displayed.</span></span> <span data-ttu-id="493d0-137">これにより、列を読み取ることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="493d0-137">This makes the columns readable.</span></span>

```powershell
Get-Service -Name win* | Format-Table -AutoSize
```

```Output
Status  Name                DisplayName
------  ----                -----------
Running WinDefend           Windows Defender Antivirus Service
Running WinHttpAutoProxySvc WinHTTP Web Proxy Auto-Discovery Service
Running Winmgmt             Windows Management Instrumentation
Running WinRM               Windows Remote Management (WS-Management)
```

<span data-ttu-id="493d0-138">`Format-Table` コマンドレットでは引き続きデータを切り捨てることもありますが、切る捨てられるのは画面の端だけです。</span><span class="sxs-lookup"><span data-stu-id="493d0-138">The `Format-Table` cmdlet might still truncate data, but it only truncates at the end of the screen.</span></span> <span data-ttu-id="493d0-139">最後に表示されるもの以外のプロパティには、最長データ要素が正しく表示されるために必要なだけのサイズが与えられます。</span><span class="sxs-lookup"><span data-stu-id="493d0-139">Properties, other than the last one displayed, are given as much size as they need for their longest data element to display correctly.</span></span>

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -AutoSize
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc, iphl…
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms, TPHKLO…
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

<span data-ttu-id="493d0-140">`Format-Table` コマンドでは、プロパティが重要度順に一覧表示されていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="493d0-140">The `Format-Table` command assumes that properties are listed in order of importance.</span></span> <span data-ttu-id="493d0-141">したがって、先頭に最も近いプロパティを完全に表示しようとします。</span><span class="sxs-lookup"><span data-stu-id="493d0-141">So it attempts to fully display the properties nearest the beginning.</span></span> <span data-ttu-id="493d0-142">`Format-Table` コマンドですべてのプロパティを表示できない場合は、表示から一部の列が削除されます。</span><span class="sxs-lookup"><span data-stu-id="493d0-142">If the `Format-Table` command can't display all the properties, it removes some columns from the display.</span></span> <span data-ttu-id="493d0-143">この動作は、前の例の **DependentServices** プロパティで確認できます。</span><span class="sxs-lookup"><span data-stu-id="493d0-143">You can see this behavior in the **DependentServices** property previous example.</span></span>

### <a name="wrapping-format-table-output-in-columns-wrap"></a><span data-ttu-id="493d0-144">Format-Table 出力の列内の折り返し (Wrap)</span><span class="sxs-lookup"><span data-stu-id="493d0-144">Wrapping Format-Table Output in Columns (Wrap)</span></span>

<span data-ttu-id="493d0-145">**Wrap** パラメーターを使用することで、長い `Format-Table` データをその表示列内で強制的に折り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="493d0-145">You can force lengthy `Format-Table` data to wrap within its display column by using the **Wrap** parameter.</span></span> <span data-ttu-id="493d0-146">**Wrap** パラメーターだけを使用した場合、必ずしも期待どおりにはなりません。**AutoSize** も指定しなければ、既定の設定が使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="493d0-146">Using the **Wrap** parameter may not do what you expect, since it uses default settings if you don't also specify **AutoSize**:</span></span>

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -Wrap
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc,
                                                                                iphlpsvc}
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms,
                                                                                TPHKLOAD,
                                                                                SUService,
                                                                                smstsmgr…}
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

<span data-ttu-id="493d0-147">**Wrap** パラメーターを単独で使用すると、処理はあまり遅くなりません。</span><span class="sxs-lookup"><span data-stu-id="493d0-147">Using the **Wrap** parameter by itself doesn't slow down processing very much.</span></span> <span data-ttu-id="493d0-148">しかし、**AutoSize** を使用した場合、大規模なディレクトリ構造の再帰的ファイル リスト表示を実行すると、最初の出力項目が表示されるまで長い時間がかかり、大量のメモリが使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="493d0-148">However, using **AutoSize** to format a recursive file listing of a large directory structure can take a long time and use lots of memory before displaying the first output items.</span></span>

<span data-ttu-id="493d0-149">システム負荷が気にならなければ、**AutoSize** は **Wrap** パラメーターと共に使用する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="493d0-149">If you aren't concerned about system load, then **AutoSize** works well with the **Wrap** parameter.</span></span>
<span data-ttu-id="493d0-150">最初の列では 1 行に項目を表示するために必要な幅が引き続き使用されますが、必要に応じて最後の列が折り返されます。</span><span class="sxs-lookup"><span data-stu-id="493d0-150">The initial columns still use as much width as needed to display items on one line, but the final column is wrapped, if necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="493d0-151">最も広い列を最初に指定すると、一部の列が表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="493d0-151">Some columns may not be displayed when you specify the widest columns first.</span></span> <span data-ttu-id="493d0-152">最適な結果を得るには、最初に最小のデータ要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="493d0-152">For best results, specify the smallest data elements first.</span></span>

<span data-ttu-id="493d0-153">次の例では、最も幅の広いプロパティを最初に指定しています。</span><span class="sxs-lookup"><span data-stu-id="493d0-153">In the following example, we specify the widest properties first.</span></span>

```powershell
Get-Process -Name iexplore | Format-Table -Wrap -AutoSize -Property FileVersion,Path,Name,Id
```

<span data-ttu-id="493d0-154">折り返しを使用した場合でも、最後の **Id** 列は省略されます。</span><span class="sxs-lookup"><span data-stu-id="493d0-154">Even with wrapping, the final **Id** column is omitted:</span></span>

```Output
FileVersion                          Path                                                  Nam
                                                                                           e
-----------                          ----                                                  ---
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files (x86)\Internet Explorer\IEXPLORE.EXE iex
                                                                                           plo
                                                                                           re
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files\Internet Explorer\iexplore.exe       iex
                                                                                           plo
                                                                                           re
```

### <a name="organizing-table-output--groupby"></a><span data-ttu-id="493d0-155">表出力の整理 (-GroupBy)</span><span class="sxs-lookup"><span data-stu-id="493d0-155">Organizing Table Output (-GroupBy)</span></span>

<span data-ttu-id="493d0-156">表形式出力制御のためのもう一つの便利なパラメーターは、**GroupBy** です。</span><span class="sxs-lookup"><span data-stu-id="493d0-156">Another useful parameter for tabular output control is **GroupBy**.</span></span> <span data-ttu-id="493d0-157">長い表形式リストは特に、比較しにくい場合があります。</span><span class="sxs-lookup"><span data-stu-id="493d0-157">Longer tabular listings in particular may be hard to compare.</span></span> <span data-ttu-id="493d0-158">**GroupBy** パラメーターは、プロパティ値に基づいて出力をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="493d0-158">The **GroupBy** parameter groups output based on a property value.</span></span> <span data-ttu-id="493d0-159">たとえば、検査しやすくするために、**StartType** 別にサービスをグループ化できます。この場合、プロパティ リストから **StartType** の値を省略します。</span><span class="sxs-lookup"><span data-stu-id="493d0-159">For example, we can group services by **StartType** for easier inspection, omitting the **StartType** value from the property listing:</span></span>

```powershell
Get-Service -Name win* | Sort-Object StartType | Format-Table -GroupBy StartType
```

```Output
   StartType: Automatic
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Managem…

   StartType: Manual
Status   Name               DisplayName
------   ----               -----------
Running  WinHttpAutoProxyS… WinHTTP Web Proxy Auto-Discovery Serv…
```
