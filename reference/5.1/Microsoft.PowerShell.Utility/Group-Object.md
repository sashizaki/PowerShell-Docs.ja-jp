---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: df06d5cd83472c80a395e3dcf63c4d331c5da6bb
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219288"
---
# <span data-ttu-id="242c3-103">Group-Object</span><span class="sxs-lookup"><span data-stu-id="242c3-103">Group-Object</span></span>

## <span data-ttu-id="242c3-104">概要</span><span class="sxs-lookup"><span data-stu-id="242c3-104">SYNOPSIS</span></span>
<span data-ttu-id="242c3-105">指定したプロパティに対して同じ値を含むオブジェクトをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="242c3-105">Groups objects that contain the same value for specified properties.</span></span>

## <span data-ttu-id="242c3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="242c3-106">SYNTAX</span></span>

### <span data-ttu-id="242c3-107">テーブル</span><span class="sxs-lookup"><span data-stu-id="242c3-107">HashTable</span></span>

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="242c3-108">Description</span><span class="sxs-lookup"><span data-stu-id="242c3-108">DESCRIPTION</span></span>

<span data-ttu-id="242c3-109">`Group-Object`コマンドレットは、指定されたプロパティの値に基づいて、オブジェクトをグループ単位で表示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-109">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span>
<span data-ttu-id="242c3-110">`Group-Object` プロパティ値ごとに1行のテーブルを返し、その値を持つアイテムの数を表示する列を返します。</span><span class="sxs-lookup"><span data-stu-id="242c3-110">`Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.</span></span>

<span data-ttu-id="242c3-111">複数のプロパティを指定すると、はまず `Group-Object` 最初のプロパティの値でそれらをグループ化し、次に各プロパティグループ内で次のプロパティの値によってグループ化します。</span><span class="sxs-lookup"><span data-stu-id="242c3-111">If you specify more than one property, `Group-Object` first groups them by the values of the first property, and then, within each property group, it groups by the value of the next property.</span></span>

## <span data-ttu-id="242c3-112">例</span><span class="sxs-lookup"><span data-stu-id="242c3-112">EXAMPLES</span></span>

### <span data-ttu-id="242c3-113">例 1: 拡張子別にファイルをグループ化する</span><span class="sxs-lookup"><span data-stu-id="242c3-113">Example 1: Group files by extension</span></span>

<span data-ttu-id="242c3-114">この例では、の下にあるファイルを再帰的に取得 `$PSHOME` し、ファイル名拡張子別にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="242c3-114">This example recursively gets the files under `$PSHOME` and groups them by file name extension.</span></span> <span data-ttu-id="242c3-115">出力はコマンドレットに送信され `Sort-Object` 、指定された拡張子に対して検出されたファイルの数によって並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="242c3-115">The output is sent to the `Sort-Object` cmdlet, which sorts them by the count files found for the given extension.</span></span> <span data-ttu-id="242c3-116">空の **名前** は、ディレクトリを表します。</span><span class="sxs-lookup"><span data-stu-id="242c3-116">The empty **Name** represents directories.</span></span>

<span data-ttu-id="242c3-117">この例では、 **Noelement** パラメーターを使用して、グループのメンバーを除外します。</span><span class="sxs-lookup"><span data-stu-id="242c3-117">This example uses the **NoElement** parameter to omit the members of the group.</span></span>

```powershell
$files = Get-ChildItem -Path $PSHOME -Recurse
$files | Group-Object -Property extension -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  365 .xml
  231 .cdxml
  197
  169 .ps1xml
  142 .txt
  114 .psd1
   63 .psm1
   49 .xsd
   36 .dll
   15 .mfl
   15 .mof
...
```

### <span data-ttu-id="242c3-118">例 2: 整数を確率とほうでグループ化する</span><span class="sxs-lookup"><span data-stu-id="242c3-118">Example 2: Group integers by odds and evens</span></span>

<span data-ttu-id="242c3-119">この例では、 **Property** パラメーターの値としてスクリプトブロックを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-119">This example shows how to use script blocks as the value of the **Property** parameter.</span></span> <span data-ttu-id="242c3-120">このコマンドは、1 ~ 20 の整数を、確率と偶数でグループ化して表示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-120">This command displays the integers from 1 to 20, grouped by odds and even.</span></span>

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### <span data-ttu-id="242c3-121">例 3: EntryType でイベントログイベントをグループ化する</span><span class="sxs-lookup"><span data-stu-id="242c3-121">Example 3: Group event log events by EntryType</span></span>

<span data-ttu-id="242c3-122">この例では、システムイベントログの最新エントリ1000を **Entrytype** でグループ化して表示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-122">This example displays the 1,000 most recent entries in the System event log, grouped by **EntryType**.</span></span>

<span data-ttu-id="242c3-123">出力の [ **カウント** ] 列は、各グループのエントリ数を表します。</span><span class="sxs-lookup"><span data-stu-id="242c3-123">In the output, the **Count** column represents the number of entries in each group.</span></span> <span data-ttu-id="242c3-124">[ **名前** ] 列は、グループを定義する **EventType** 値を表します。</span><span class="sxs-lookup"><span data-stu-id="242c3-124">The **Name** column represents the **EventType** values that define a group.</span></span> <span data-ttu-id="242c3-125">[ **グループ]** 列は、各グループのオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="242c3-125">The **Group** column represents the objects in each group.</span></span>

```powershell
Get-WinEvent -LogName System -MaxEvents 1000 | Group-Object -Property LevelDisplayName
```

```Output
Count Name          Group
----- ----          -----
  153 Error         {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  722 Information   {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  125 Warning       {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
```

### <span data-ttu-id="242c3-126">例 4: 優先度クラスによってプロセスをグループ化する</span><span class="sxs-lookup"><span data-stu-id="242c3-126">Example 4: Group processes by priority class</span></span>

<span data-ttu-id="242c3-127">この例は、 **Noelement** パラメーターの効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="242c3-127">This example demonstrates the effect of the **NoElement** parameter.</span></span> <span data-ttu-id="242c3-128">これらのコマンドは、コンピューター上のプロセスを優先度クラス別にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="242c3-128">These commands group the processes on the computer by priority class.</span></span>

<span data-ttu-id="242c3-129">最初のコマンドは、 `Get-Process` コマンドレットを使用してコンピューター上のプロセスを取得し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="242c3-129">The first command uses the `Get-Process` cmdlet to get the processes on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="242c3-130">`Group-Object`プロセスの優先度 **クラス** プロパティの値によってオブジェクトをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="242c3-130">`Group-Object`groups the objects by the value of the **PriorityClass** property of the process.</span></span>

<span data-ttu-id="242c3-131">2番目の例では、 **Noelement** パラメーターを使用して、出力からグループのメンバーを除外します。</span><span class="sxs-lookup"><span data-stu-id="242c3-131">The second example uses the **NoElement** parameter to eliminate the members of the group from the output.</span></span> <span data-ttu-id="242c3-132">結果は、 **Count** および **Name** プロパティ値のみを含むテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="242c3-132">The result is a table with only the **Count** and **Name** property value.</span></span>

<span data-ttu-id="242c3-133">次のサンプル出力に結果を示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-133">The results are shown in the following sample output.</span></span>

```powershell
Get-Process | Group-Object -Property PriorityClass
```

```Output
Count Name         Group
----- ----         -----
   55 Normal       {System.Diagnostics.Process (AdtAgent), System.Diagnosti...
    1              {System.Diagnostics.Process (Idle)}
    3 High         {System.Diagnostics.Process (Newproc), System.Diagnostic...
    2 BelowNormal  {System.Diagnostics.Process (winperf),
```

```powershell
Get-Process | Group-Object -Property PriorityClass -NoElement
```

```Output
Count Name
----- ----
   55 Normal
    1
    3 High
    2 BelowNormal
```

### <span data-ttu-id="242c3-134">例 5: プロセスを名前でグループ化する</span><span class="sxs-lookup"><span data-stu-id="242c3-134">Example 5: Group processes by name</span></span>

<span data-ttu-id="242c3-135">次の例では、を使用し `Group-Object` て、ローカルコンピューター上で実行されているプロセスの複数のインスタンスをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="242c3-135">The following example uses `Group-Object` to group multiple instances of processes running on the local computer.</span></span> <span data-ttu-id="242c3-136">`Where-Object` 複数のインスタンスを持つプロセスを表示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-136">`Where-Object` displays processes with more than one instance.</span></span>

```powershell
Get-Process | Group-Object -Property Name -NoElement | Where-Object {$_.Count -gt 1}
```

```Output
Count Name
----- ----
2     csrss
5     svchost
2     winlogon
2     wmiprvse
```

### <span data-ttu-id="242c3-137">例 6: ハッシュテーブル内のオブジェクトをグループ化する</span><span class="sxs-lookup"><span data-stu-id="242c3-137">Example 6: Group objects in a hash table</span></span>

<span data-ttu-id="242c3-138">この例では、 **ashashtable** パラメーターと **asstring** パラメーターを使用して、ハッシュテーブル内のグループをキーと値のペアのコレクションとして返します。</span><span class="sxs-lookup"><span data-stu-id="242c3-138">This example uses the **AsHashTable** and **AsString** parameters to return the groups in a hash table, as a collection of key-value pairs.</span></span>

<span data-ttu-id="242c3-139">結果のハッシュ テーブルでは、各プロパティ値がキーで、グループの要素が値です。</span><span class="sxs-lookup"><span data-stu-id="242c3-139">In the resulting hash table, each property value is a key, and the group elements are the values.</span></span>
<span data-ttu-id="242c3-140">各キーがハッシュ テーブルのオブジェクトのプロパティであるため、ドット表記を使用して値を表示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-140">Because each key is a property of the hash table object, you can use dot notation to display the values.</span></span>

<span data-ttu-id="242c3-141">最初のコマンドは、 `Get` セッション内のコマンドレットとコマンドレットを取得し、 `Set` 動詞別にグループ化して、グループをハッシュテーブルとして返し、ハッシュテーブルを変数に保存し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="242c3-141">The first command gets the `Get` and `Set` cmdlets in the session, groups them by verb, returns the groups as a hash table, and saves the hash table in the `$A` variable.</span></span>

<span data-ttu-id="242c3-142">2番目のコマンドは、のハッシュテーブルを表示し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="242c3-142">The second command displays the hash table in `$A`.</span></span> <span data-ttu-id="242c3-143">2つのキーと値のペアがあります。1つはコマンドレット用で、もう1つは `Get` `Set` コマンドレット用です。</span><span class="sxs-lookup"><span data-stu-id="242c3-143">There are two key-value pairs, one for the `Get` cmdlets and one for the `Set` cmdlets.</span></span>

<span data-ttu-id="242c3-144">3番目のコマンドは、ドット表記を使用して、の `$A.Get` **Get** キーの値を表示し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="242c3-144">The third command uses dot notation, `$A.Get` to display the values of the **Get** key in `$A`.</span></span> <span data-ttu-id="242c3-145">値 **は、[オブジェクト]** です。</span><span class="sxs-lookup"><span data-stu-id="242c3-145">The values are **CmdletInfo** object.</span></span> <span data-ttu-id="242c3-146">**Asstring** パラメーターは、グループ内のオブジェクトを文字列に変換しません。</span><span class="sxs-lookup"><span data-stu-id="242c3-146">The **AsString** parameter doesn't convert the objects in the groups to strings.</span></span>

```powershell
$A = Get-Command Get-*, Set-* -CommandType cmdlet | Group-Object -Property Verb -AsHashTable -AsString
$A
```

```Output
Name     Value
----     -----
Get      {Get-Acl, Get-Alias, Get-AppLockerFileInformation, Get-AppLockerPolicy...}
Set      {Set-Acl, Set-Alias, Set-AppBackgroundTaskResourcePolicy, Set-AppLockerPolicy...}
```

```powershell
$A.Get
```

```Output
CommandType     Name                               Version    Source
-----------     ----                               -------    ------
Cmdlet          Get-Acl                            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation       2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                2.0.0.0    AppLocker
...
```

## <span data-ttu-id="242c3-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="242c3-147">PARAMETERS</span></span>

### <span data-ttu-id="242c3-148">-AsHashTable</span><span class="sxs-lookup"><span data-stu-id="242c3-148">-AsHashTable</span></span>

<span data-ttu-id="242c3-149">このコマンドレットがグループをハッシュテーブルとして返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-149">Indicates that this cmdlet returns the group as a hash table.</span></span> <span data-ttu-id="242c3-150">ハッシュ テーブルのキーは、オブジェクトをグループ化するためのプロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="242c3-150">The keys of the hash table are the property values by which the objects are grouped.</span></span> <span data-ttu-id="242c3-151">ハッシュ テーブルの値は、そのプロパティ値を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="242c3-151">The values of the hash table are the objects that have that property value.</span></span>

<span data-ttu-id="242c3-152">それ自体では、 **ashashtable** パラメーターは、各キーがグループ化されたオブジェクトのインスタンスである各ハッシュテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="242c3-152">By itself, the **AsHashTable** parameter returns each hash table in which each key is an instance of the grouped object.</span></span> <span data-ttu-id="242c3-153">**Asstring** パラメーターと共に使用する場合、ハッシュテーブル内のキーは文字列になります。</span><span class="sxs-lookup"><span data-stu-id="242c3-153">When used with the **AsString** parameter, the keys in the hash table are strings.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: AHT

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="242c3-154">-AsString</span><span class="sxs-lookup"><span data-stu-id="242c3-154">-AsString</span></span>

<span data-ttu-id="242c3-155">このコマンドレットがハッシュテーブルキーを文字列に変換することを示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-155">Indicates that this cmdlet converts the hash table keys to strings.</span></span> <span data-ttu-id="242c3-156">既定では、ハッシュ テーブルのキーは、グループ化されたオブジェクトのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="242c3-156">By default, the hash table keys are instances of the grouped object.</span></span> <span data-ttu-id="242c3-157">このパラメーターは、 **Ashashtable** パラメーターと共に使用する場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="242c3-157">This parameter is valid only when used with the **AsHashTable** parameter.</span></span>

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

### <span data-ttu-id="242c3-158">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="242c3-158">-CaseSensitive</span></span>

<span data-ttu-id="242c3-159">このコマンドレットによってグループ化で大文字と小文字が区別されることを示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-159">Indicates that this cmdlet makes the grouping case-sensitive.</span></span> <span data-ttu-id="242c3-160">このパラメーターを指定しない場合、グループ内のオブジェクトのプロパティ値は大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="242c3-160">Without this parameter, the property values of objects in a group might have different cases.</span></span>

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

### <span data-ttu-id="242c3-161">-Culture</span><span class="sxs-lookup"><span data-stu-id="242c3-161">-Culture</span></span>

<span data-ttu-id="242c3-162">文字列を比較するときに使用するカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="242c3-162">Specifies the culture to use when comparing strings.</span></span>

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

### <span data-ttu-id="242c3-163">-InputObject</span><span class="sxs-lookup"><span data-stu-id="242c3-163">-InputObject</span></span>

<span data-ttu-id="242c3-164">オブジェクトをグループに指定します。</span><span class="sxs-lookup"><span data-stu-id="242c3-164">Specifies the objects to group.</span></span> <span data-ttu-id="242c3-165">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="242c3-165">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="242c3-166">**InputObject** パラメーターを使用してオブジェクトのコレクションをに送信すると `Group-Object` 、は `Group-Object` コレクションを表す1つのオブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="242c3-166">When you use the **InputObject** parameter to submit a collection of objects to `Group-Object`, `Group-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="242c3-167">その結果、そのオブジェクトをメンバーとする単一のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="242c3-167">As a result, it creates a single group with that object as its member.</span></span>

<span data-ttu-id="242c3-168">コレクション内のオブジェクトをグループ化するには、オブジェクトをにパイプ処理し `Group-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="242c3-168">To group the objects in a collection, pipe the objects to `Group-Object`.</span></span>

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

### <span data-ttu-id="242c3-169">-NoElement</span><span class="sxs-lookup"><span data-stu-id="242c3-169">-NoElement</span></span>

<span data-ttu-id="242c3-170">このコマンドレットが結果からグループのメンバーを除外することを示します。</span><span class="sxs-lookup"><span data-stu-id="242c3-170">Indicates that this cmdlet omits the members of a group from the results.</span></span>

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

### <span data-ttu-id="242c3-171">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="242c3-171">-Property</span></span>

<span data-ttu-id="242c3-172">グループ化のためのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="242c3-172">Specifies the properties for grouping.</span></span> <span data-ttu-id="242c3-173">オブジェクトは、指定したプロパティの値に基づいてグループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="242c3-173">The objects are arranged into groups based on the value of the specified property.</span></span>

<span data-ttu-id="242c3-174">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="242c3-174">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="242c3-175">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="242c3-175">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="242c3-176">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="242c3-176">Valid key-value pairs are:</span></span>

- <span data-ttu-id="242c3-177">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="242c3-177">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="242c3-178">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="242c3-178">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="242c3-179">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="242c3-179">CommonParameters</span></span>

<span data-ttu-id="242c3-180">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="242c3-180">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="242c3-181">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="242c3-181">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="242c3-182">入力</span><span class="sxs-lookup"><span data-stu-id="242c3-182">INPUTS</span></span>

### <span data-ttu-id="242c3-183">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="242c3-183">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="242c3-184">パイプを使用して任意のオブジェクトをにパイプすることができ `Group-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="242c3-184">You can pipe any object to `Group-Object`.</span></span>

## <span data-ttu-id="242c3-185">出力</span><span class="sxs-lookup"><span data-stu-id="242c3-185">OUTPUTS</span></span>

### <span data-ttu-id="242c3-186">GroupInfo または System. Collections. Hashtable</span><span class="sxs-lookup"><span data-stu-id="242c3-186">Microsoft.PowerShell.Commands.GroupInfo or System.Collections.Hashtable</span></span>

<span data-ttu-id="242c3-187">**Ashashtable** パラメーターを使用すると、は `Group-Object` **Hashtable** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="242c3-187">When you use the **AsHashTable** parameter, `Group-Object` returns a **Hashtable** object.</span></span>
<span data-ttu-id="242c3-188">それ以外の場合は、 **GroupInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="242c3-188">Otherwise, it returns a **GroupInfo** object.</span></span>

## <span data-ttu-id="242c3-189">注</span><span class="sxs-lookup"><span data-stu-id="242c3-189">NOTES</span></span>

<span data-ttu-id="242c3-190">やなどの書式設定コマンドレットの **GroupBy** パラメーターを使用して、 `Format-Table` `Format-List` オブジェクトをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="242c3-190">You can use the **GroupBy** parameter of the formatting cmdlets, such as `Format-Table` and `Format-List`, to group objects.</span></span> <span data-ttu-id="242c3-191">`Group-Object`プロパティ値ごとに1行のテーブルを作成するとは異なり、 **GroupBy** パラメーターは、プロパティ値を持つ項目ごとに1行のテーブルをプロパティ値ごとに作成します。</span><span class="sxs-lookup"><span data-stu-id="242c3-191">Unlike `Group-Object`, which creates a single table with a row for each property value, the **GroupBy** parameters create a table for each property value with a row for each item that has the property value.</span></span>

<span data-ttu-id="242c3-192">`Group-Object` では、グループ化されるオブジェクトが Microsoft .NET Framework 型と同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="242c3-192">`Group-Object` doesn't require that the objects being grouped are of the same Microsoft .NET Framework type.</span></span> <span data-ttu-id="242c3-193">異なる .NET Framework の種類のオブジェクトをグループ化する場合、で `Group-Object` は次の規則が使用されます。</span><span class="sxs-lookup"><span data-stu-id="242c3-193">When grouping objects of different .NET Framework types, `Group-Object` uses the following rules:</span></span>

- <span data-ttu-id="242c3-194">同じプロパティ名と型。</span><span class="sxs-lookup"><span data-stu-id="242c3-194">Same Property Names and Types.</span></span>

  <span data-ttu-id="242c3-195">オブジェクトに指定された名前のプロパティがあり、プロパティ値が同じ .NET Framework 型の場合、同じ型のオブジェクトに対して使用される同じ規則を使用してプロパティ値がグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="242c3-195">If the objects have a property with the specified name, and the property values have the same .NET Framework type, the property values are grouped by using the same rules that would be used for objects of the same type.</span></span>

- <span data-ttu-id="242c3-196">同じプロパティ名、異なる型。</span><span class="sxs-lookup"><span data-stu-id="242c3-196">Same Property Names, Different Types.</span></span>

  <span data-ttu-id="242c3-197">オブジェクトに指定された名前のプロパティがあり、プロパティ値の .NET Framework 型が異なる場合、は、 `Group-Object` そのプロパティグループの .NET Framework 型として最初に見つかったプロパティの .NET Framework 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="242c3-197">If the objects have a property with the specified name, but the property values have a different .NET Framework type in different objects, `Group-Object` uses the .NET Framework type of the first occurrence of the property as the .NET Framework type for that property group.</span></span> <span data-ttu-id="242c3-198">オブジェクトに異なる型のプロパティがある場合、プロパティ値は、そのグループの型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="242c3-198">When an object has a property with a different type, the property value is converted to the type for that group.</span></span> <span data-ttu-id="242c3-199">型変換に失敗した場合、オブジェクトはグループに含まれません。</span><span class="sxs-lookup"><span data-stu-id="242c3-199">If the type conversion fails, the object is not included in the group.</span></span>

- <span data-ttu-id="242c3-200">プロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="242c3-200">Missing Properties.</span></span>

  <span data-ttu-id="242c3-201">指定されたプロパティを持たないオブジェクトはグループ化できません。</span><span class="sxs-lookup"><span data-stu-id="242c3-201">Objects that don't have a specified property can't be grouped.</span></span> <span data-ttu-id="242c3-202">グループ化されていないオブジェクトは、という名前のグループの最終的な **GroupInfo** オブジェクト出力に表示され `AutomationNull.Value` ます。</span><span class="sxs-lookup"><span data-stu-id="242c3-202">Objects that aren't grouped appear in the final **GroupInfo** object output in a group named `AutomationNull.Value`.</span></span>

## <span data-ttu-id="242c3-203">関連リンク</span><span class="sxs-lookup"><span data-stu-id="242c3-203">RELATED LINKS</span></span>

[<span data-ttu-id="242c3-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="242c3-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="242c3-205">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="242c3-205">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="242c3-206">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="242c3-206">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="242c3-207">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="242c3-207">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="242c3-208">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="242c3-208">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="242c3-209">New-Object</span><span class="sxs-lookup"><span data-stu-id="242c3-209">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="242c3-210">Select-Object</span><span class="sxs-lookup"><span data-stu-id="242c3-210">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="242c3-211">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="242c3-211">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="242c3-212">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="242c3-212">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="242c3-213">Where-Object</span><span class="sxs-lookup"><span data-stu-id="242c3-213">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
