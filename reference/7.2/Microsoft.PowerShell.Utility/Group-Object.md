---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: 6198964f01a4c0dc70584cdb3e5c0e13f3965934
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599919"
---
# <span data-ttu-id="7425b-102">Group-Object</span><span class="sxs-lookup"><span data-stu-id="7425b-102">Group-Object</span></span>

## <span data-ttu-id="7425b-103">概要</span><span class="sxs-lookup"><span data-stu-id="7425b-103">SYNOPSIS</span></span>
<span data-ttu-id="7425b-104">指定したプロパティに対して同じ値を含むオブジェクトをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7425b-104">Groups objects that contain the same value for specified properties.</span></span>

## <span data-ttu-id="7425b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7425b-105">SYNTAX</span></span>

### <span data-ttu-id="7425b-106">テーブル</span><span class="sxs-lookup"><span data-stu-id="7425b-106">HashTable</span></span>

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="7425b-107">Description</span><span class="sxs-lookup"><span data-stu-id="7425b-107">DESCRIPTION</span></span>

<span data-ttu-id="7425b-108">`Group-Object`コマンドレットは、指定されたプロパティの値に基づいて、オブジェクトをグループ単位で表示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-108">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span>
<span data-ttu-id="7425b-109">`Group-Object` プロパティ値ごとに1行のテーブルを返し、その値を持つアイテムの数を表示する列を返します。</span><span class="sxs-lookup"><span data-stu-id="7425b-109">`Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.</span></span>

<span data-ttu-id="7425b-110">複数のプロパティを指定すると、はまず `Group-Object` 最初のプロパティの値でそれらをグループ化し、次に各プロパティグループ内で次のプロパティの値によってグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7425b-110">If you specify more than one property, `Group-Object` first groups them by the values of the first property, and then, within each property group, it groups by the value of the next property.</span></span>

<span data-ttu-id="7425b-111">PowerShell 7 以降で `Group-Object` は、 **CaseSensitive** と **ashashtable** パラメーターを組み合わせて、大文字と小文字を区別するハッシュテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7425b-111">Beginning in PowerShell 7, `Group-Object` can combine the **CaseSensitive** and **AsHashtable** parameters to create a case-sensitive hash table.</span></span> <span data-ttu-id="7425b-112">ハッシュテーブルのキーは、大文字と小文字を区別する比較を使用し **て、system.string オブジェクトを** 出力します。</span><span class="sxs-lookup"><span data-stu-id="7425b-112">The hash table keys use case-sensitive comparisons and output a **System.Collections.Hashtable** object.</span></span>

## <span data-ttu-id="7425b-113">例</span><span class="sxs-lookup"><span data-stu-id="7425b-113">EXAMPLES</span></span>

### <span data-ttu-id="7425b-114">例 1: 拡張子別にファイルをグループ化する</span><span class="sxs-lookup"><span data-stu-id="7425b-114">Example 1: Group files by extension</span></span>

<span data-ttu-id="7425b-115">この例では、の下にあるファイルを再帰的に取得 `$PSHOME` し、ファイル名拡張子別にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7425b-115">This example recursively gets the files under `$PSHOME` and groups them by file name extension.</span></span> <span data-ttu-id="7425b-116">出力はコマンドレットに送信され `Sort-Object` 、指定された拡張子に対して検出されたファイルの数によって並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="7425b-116">The output is sent to the `Sort-Object` cmdlet, which sorts them by the count files found for the given extension.</span></span> <span data-ttu-id="7425b-117">空の **名前** は、ディレクトリを表します。</span><span class="sxs-lookup"><span data-stu-id="7425b-117">The empty **Name** represents directories.</span></span>

<span data-ttu-id="7425b-118">この例では、 **Noelement** パラメーターを使用して、グループのメンバーを除外します。</span><span class="sxs-lookup"><span data-stu-id="7425b-118">This example uses the **NoElement** parameter to omit the members of the group.</span></span>

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

### <span data-ttu-id="7425b-119">例 2: 整数を確率とほうでグループ化する</span><span class="sxs-lookup"><span data-stu-id="7425b-119">Example 2: Group integers by odds and evens</span></span>

<span data-ttu-id="7425b-120">この例では、 **Property** パラメーターの値としてスクリプトブロックを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-120">This example shows how to use script blocks as the value of the **Property** parameter.</span></span> <span data-ttu-id="7425b-121">このコマンドは、1 ~ 20 の整数を、確率と偶数でグループ化して表示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-121">This command displays the integers from 1 to 20, grouped by odds and even.</span></span>

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### <span data-ttu-id="7425b-122">例 3: EntryType でイベントログイベントをグループ化する</span><span class="sxs-lookup"><span data-stu-id="7425b-122">Example 3: Group event log events by EntryType</span></span>

<span data-ttu-id="7425b-123">この例では、システムイベントログの最新エントリ1000を **Entrytype** でグループ化して表示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-123">This example displays the 1,000 most recent entries in the System event log, grouped by **EntryType**.</span></span>

<span data-ttu-id="7425b-124">出力の [ **カウント** ] 列は、各グループのエントリ数を表します。</span><span class="sxs-lookup"><span data-stu-id="7425b-124">In the output, the **Count** column represents the number of entries in each group.</span></span> <span data-ttu-id="7425b-125">[ **名前** ] 列は、グループを定義する **EventType** 値を表します。</span><span class="sxs-lookup"><span data-stu-id="7425b-125">The **Name** column represents the **EventType** values that define a group.</span></span> <span data-ttu-id="7425b-126">[ **グループ]** 列は、各グループのオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="7425b-126">The **Group** column represents the objects in each group.</span></span>

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

### <span data-ttu-id="7425b-127">例 4: 優先度クラスによってプロセスをグループ化する</span><span class="sxs-lookup"><span data-stu-id="7425b-127">Example 4: Group processes by priority class</span></span>

<span data-ttu-id="7425b-128">この例は、 **Noelement** パラメーターの効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7425b-128">This example demonstrates the effect of the **NoElement** parameter.</span></span> <span data-ttu-id="7425b-129">これらのコマンドは、コンピューター上のプロセスを優先度クラス別にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7425b-129">These commands group the processes on the computer by priority class.</span></span>

<span data-ttu-id="7425b-130">最初のコマンドは、 `Get-Process` コマンドレットを使用してコンピューター上のプロセスを取得し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="7425b-130">The first command uses the `Get-Process` cmdlet to get the processes on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="7425b-131">`Group-Object`プロセスの優先度 **クラス** プロパティの値によってオブジェクトをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7425b-131">`Group-Object`groups the objects by the value of the **PriorityClass** property of the process.</span></span>

<span data-ttu-id="7425b-132">2番目の例では、 **Noelement** パラメーターを使用して、出力からグループのメンバーを除外します。</span><span class="sxs-lookup"><span data-stu-id="7425b-132">The second example uses the **NoElement** parameter to eliminate the members of the group from the output.</span></span> <span data-ttu-id="7425b-133">結果は、 **Count** および **Name** プロパティ値のみを含むテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="7425b-133">The result is a table with only the **Count** and **Name** property value.</span></span>

<span data-ttu-id="7425b-134">次のサンプル出力に結果を示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-134">The results are shown in the following sample output.</span></span>

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

### <span data-ttu-id="7425b-135">例 5: プロセスを名前でグループ化する</span><span class="sxs-lookup"><span data-stu-id="7425b-135">Example 5: Group processes by name</span></span>

<span data-ttu-id="7425b-136">次の例では、を使用し `Group-Object` て、ローカルコンピューター上で実行されているプロセスの複数のインスタンスをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7425b-136">The following example uses `Group-Object` to group multiple instances of processes running on the local computer.</span></span> <span data-ttu-id="7425b-137">`Where-Object` 複数のインスタンスを持つプロセスを表示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-137">`Where-Object` displays processes with more than one instance.</span></span>

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

### <span data-ttu-id="7425b-138">例 6: ハッシュテーブル内のオブジェクトをグループ化する</span><span class="sxs-lookup"><span data-stu-id="7425b-138">Example 6: Group objects in a hash table</span></span>

<span data-ttu-id="7425b-139">この例では、 **ashashtable** パラメーターと **asstring** パラメーターを使用して、ハッシュテーブル内のグループをキーと値のペアのコレクションとして返します。</span><span class="sxs-lookup"><span data-stu-id="7425b-139">This example uses the **AsHashTable** and **AsString** parameters to return the groups in a hash table, as a collection of key-value pairs.</span></span>

<span data-ttu-id="7425b-140">結果のハッシュ テーブルでは、各プロパティ値がキーで、グループの要素が値です。</span><span class="sxs-lookup"><span data-stu-id="7425b-140">In the resulting hash table, each property value is a key, and the group elements are the values.</span></span>
<span data-ttu-id="7425b-141">各キーがハッシュ テーブルのオブジェクトのプロパティであるため、ドット表記を使用して値を表示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-141">Because each key is a property of the hash table object, you can use dot notation to display the values.</span></span>

<span data-ttu-id="7425b-142">最初のコマンドは、 `Get` セッション内のコマンドレットとコマンドレットを取得し、 `Set` 動詞別にグループ化して、グループをハッシュテーブルとして返し、ハッシュテーブルを変数に保存し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="7425b-142">The first command gets the `Get` and `Set` cmdlets in the session, groups them by verb, returns the groups as a hash table, and saves the hash table in the `$A` variable.</span></span>

<span data-ttu-id="7425b-143">2番目のコマンドは、のハッシュテーブルを表示し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="7425b-143">The second command displays the hash table in `$A`.</span></span> <span data-ttu-id="7425b-144">2つのキーと値のペアがあります。1つはコマンドレット用で、もう1つは `Get` `Set` コマンドレット用です。</span><span class="sxs-lookup"><span data-stu-id="7425b-144">There are two key-value pairs, one for the `Get` cmdlets and one for the `Set` cmdlets.</span></span>

<span data-ttu-id="7425b-145">3番目のコマンドは、ドット表記を使用して、の `$A.Get` **Get** キーの値を表示し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="7425b-145">The third command uses dot notation, `$A.Get` to display the values of the **Get** key in `$A`.</span></span> <span data-ttu-id="7425b-146">値 **は、[オブジェクト]** です。</span><span class="sxs-lookup"><span data-stu-id="7425b-146">The values are **CmdletInfo** object.</span></span> <span data-ttu-id="7425b-147">**Asstring** パラメーターは、グループ内のオブジェクトを文字列に変換しません。</span><span class="sxs-lookup"><span data-stu-id="7425b-147">The **AsString** parameter doesn't convert the objects in the groups to strings.</span></span>

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
CommandType     Name                                Version    Source
-----------     ----                                -------    ------
Cmdlet          Get-Acl                             7.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                           7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation        2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                 2.0.0.0    AppLocker
...
```

### <span data-ttu-id="7425b-148">例 7: 大文字と小文字を区別するハッシュテーブルを作成する</span><span class="sxs-lookup"><span data-stu-id="7425b-148">Example 7: Create a case-sensitive hash table</span></span>

<span data-ttu-id="7425b-149">この例では、 **CaseSensitive** パラメーターと **ashashtable** パラメーターを組み合わせて、大文字と小文字を区別するハッシュテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7425b-149">This example combines the **CaseSensitive** and **AsHashTable** parameters to create a case-sensitive hash table.</span></span> <span data-ttu-id="7425b-150">この例のファイルには、およびの拡張子があり `.txt` `.TXT` ます。</span><span class="sxs-lookup"><span data-stu-id="7425b-150">The files in the example have extensions of `.txt` and `.TXT`.</span></span>

```powershell
$hash = Get-ChildItem -Path C:\Files | Group-Object -Property Extension -CaseSensitive -AsHashTable
$hash
```

```Output
Name           Value
----           -----
.TXT           {C:\Files\File7.TXT, C:\Files\File8.TXT, C:\Files\File9.TXT}
.txt           {C:\Files\file1.txt, C:\Files\file2.txt, C:\Files\file3.txt}
```

<span data-ttu-id="7425b-151">変数は、system.string `$hash` オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="7425b-151">The `$hash` variable stores the **System.Collections.Hashtable** object.</span></span> <span data-ttu-id="7425b-152">`Get-ChildItem` ディレクトリからファイル名を取得 `C:\Files` し、パイプラインの下位 **にある system.object** オブジェクトを送信します。</span><span class="sxs-lookup"><span data-stu-id="7425b-152">`Get-ChildItem` gets the file names from the `C:\Files` directory and sends the **System.IO.FileInfo** objects down the pipeline.</span></span> <span data-ttu-id="7425b-153">`Group-Object`**プロパティ** 値の **拡張** を使用してオブジェクトをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7425b-153">`Group-Object` groups the objects using the **Property** value **Extension**.</span></span> <span data-ttu-id="7425b-154">**CaseSensitive** および **ashashtable** パラメーターはハッシュテーブルを作成し、キーは大文字と小文字を区別するキーとを使用してグループ化され `.txt` `.TXT` ます。</span><span class="sxs-lookup"><span data-stu-id="7425b-154">The **CaseSensitive** and **AsHashTable** parameters create the hash table and the keys are grouped using the case-sensitive keys `.txt` and `.TXT`.</span></span>

## <span data-ttu-id="7425b-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7425b-155">PARAMETERS</span></span>

### <span data-ttu-id="7425b-156">-AsHashTable</span><span class="sxs-lookup"><span data-stu-id="7425b-156">-AsHashTable</span></span>

<span data-ttu-id="7425b-157">このコマンドレットがグループをハッシュテーブルとして返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-157">Indicates that this cmdlet returns the group as a hash table.</span></span> <span data-ttu-id="7425b-158">ハッシュ テーブルのキーは、オブジェクトをグループ化するためのプロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="7425b-158">The keys of the hash table are the property values by which the objects are grouped.</span></span> <span data-ttu-id="7425b-159">ハッシュ テーブルの値は、そのプロパティ値を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="7425b-159">The values of the hash table are the objects that have that property value.</span></span>

<span data-ttu-id="7425b-160">それ自体では、 **ashashtable** パラメーターは、各キーがグループ化されたオブジェクトのインスタンスである各ハッシュテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="7425b-160">By itself, the **AsHashTable** parameter returns each hash table in which each key is an instance of the grouped object.</span></span> <span data-ttu-id="7425b-161">**Asstring** パラメーターと共に使用する場合、ハッシュテーブル内のキーは文字列になります。</span><span class="sxs-lookup"><span data-stu-id="7425b-161">When used with the **AsString** parameter, the keys in the hash table are strings.</span></span>

<span data-ttu-id="7425b-162">PowerShell 7 以降では、大文字と小文字を区別するハッシュテーブルを作成するには、コマンドに **CaseSensitive** と **ashashtable** を含めます。</span><span class="sxs-lookup"><span data-stu-id="7425b-162">Beginning in PowerShell 7, to create case-sensitive hash tables, include **CaseSensitive** and **AsHashtable** in your command.</span></span>

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

### <span data-ttu-id="7425b-163">-AsString</span><span class="sxs-lookup"><span data-stu-id="7425b-163">-AsString</span></span>

<span data-ttu-id="7425b-164">このコマンドレットがハッシュテーブルキーを文字列に変換することを示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-164">Indicates that this cmdlet converts the hash table keys to strings.</span></span> <span data-ttu-id="7425b-165">既定では、ハッシュ テーブルのキーは、グループ化されたオブジェクトのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="7425b-165">By default, the hash table keys are instances of the grouped object.</span></span> <span data-ttu-id="7425b-166">このパラメーターは、 **Ashashtable** パラメーターと共に使用する場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="7425b-166">This parameter is valid only when used with the **AsHashTable** parameter.</span></span>

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

### <span data-ttu-id="7425b-167">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="7425b-167">-CaseSensitive</span></span>

<span data-ttu-id="7425b-168">このコマンドレットによってグループ化で大文字と小文字が区別されることを示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-168">Indicates that this cmdlet makes the grouping case-sensitive.</span></span> <span data-ttu-id="7425b-169">このパラメーターを指定しない場合、グループ内のオブジェクトのプロパティ値は大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="7425b-169">Without this parameter, the property values of objects in a group might have different cases.</span></span>

<span data-ttu-id="7425b-170">PowerShell 7 以降では、大文字と小文字を区別するハッシュテーブルを作成するには、コマンドに **CaseSensitive** と **ashashtable** を含めます。</span><span class="sxs-lookup"><span data-stu-id="7425b-170">Beginning in PowerShell 7, to create case-sensitive hash tables, include **CaseSensitive** and **AsHashtable** in your command.</span></span>

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

### <span data-ttu-id="7425b-171">-Culture</span><span class="sxs-lookup"><span data-stu-id="7425b-171">-Culture</span></span>

<span data-ttu-id="7425b-172">文字列を比較するときに使用するカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="7425b-172">Specifies the culture to use when comparing strings.</span></span>

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

### <span data-ttu-id="7425b-173">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7425b-173">-InputObject</span></span>

<span data-ttu-id="7425b-174">オブジェクトをグループに指定します。</span><span class="sxs-lookup"><span data-stu-id="7425b-174">Specifies the objects to group.</span></span> <span data-ttu-id="7425b-175">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="7425b-175">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="7425b-176">**InputObject** パラメーターを使用してオブジェクトのコレクションをに送信すると `Group-Object` 、は `Group-Object` コレクションを表す1つのオブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7425b-176">When you use the **InputObject** parameter to submit a collection of objects to `Group-Object`, `Group-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="7425b-177">その結果、そのオブジェクトをメンバーとする単一のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="7425b-177">As a result, it creates a single group with that object as its member.</span></span>

<span data-ttu-id="7425b-178">コレクション内のオブジェクトをグループ化するには、オブジェクトをにパイプ処理し `Group-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="7425b-178">To group the objects in a collection, pipe the objects to `Group-Object`.</span></span>

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

### <span data-ttu-id="7425b-179">-NoElement</span><span class="sxs-lookup"><span data-stu-id="7425b-179">-NoElement</span></span>

<span data-ttu-id="7425b-180">このコマンドレットが結果からグループのメンバーを除外することを示します。</span><span class="sxs-lookup"><span data-stu-id="7425b-180">Indicates that this cmdlet omits the members of a group from the results.</span></span>

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

### <span data-ttu-id="7425b-181">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="7425b-181">-Property</span></span>

<span data-ttu-id="7425b-182">グループ化のためのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="7425b-182">Specifies the properties for grouping.</span></span> <span data-ttu-id="7425b-183">オブジェクトは、指定したプロパティの値に基づいてグループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="7425b-183">The objects are arranged into groups based on the value of the specified property.</span></span>

<span data-ttu-id="7425b-184">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7425b-184">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="7425b-185">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7425b-185">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="7425b-186">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7425b-186">Valid key-value pairs are:</span></span>

- <span data-ttu-id="7425b-187">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="7425b-187">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="7425b-188">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7425b-188">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="7425b-189">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7425b-189">CommonParameters</span></span>

<span data-ttu-id="7425b-190">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7425b-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7425b-191">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7425b-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7425b-192">入力</span><span class="sxs-lookup"><span data-stu-id="7425b-192">INPUTS</span></span>

### <span data-ttu-id="7425b-193">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="7425b-193">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7425b-194">パイプを使用して任意のオブジェクトをにパイプすることができ `Group-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="7425b-194">You can pipe any object to `Group-Object`.</span></span>

## <span data-ttu-id="7425b-195">出力</span><span class="sxs-lookup"><span data-stu-id="7425b-195">OUTPUTS</span></span>

### <span data-ttu-id="7425b-196">GroupInfo または System. Collections. Hashtable</span><span class="sxs-lookup"><span data-stu-id="7425b-196">Microsoft.PowerShell.Commands.GroupInfo or System.Collections.Hashtable</span></span>

<span data-ttu-id="7425b-197">**Ashashtable** パラメーターを使用すると、は `Group-Object` **Hashtable** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7425b-197">When you use the **AsHashTable** parameter, `Group-Object` returns a **Hashtable** object.</span></span>
<span data-ttu-id="7425b-198">それ以外の場合は、 **GroupInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7425b-198">Otherwise, it returns a **GroupInfo** object.</span></span>

## <span data-ttu-id="7425b-199">注</span><span class="sxs-lookup"><span data-stu-id="7425b-199">NOTES</span></span>

<span data-ttu-id="7425b-200">やなどの書式設定コマンドレットの **GroupBy** パラメーターを使用して、 `Format-Table` `Format-List` オブジェクトをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="7425b-200">You can use the **GroupBy** parameter of the formatting cmdlets, such as `Format-Table` and `Format-List`, to group objects.</span></span> <span data-ttu-id="7425b-201">`Group-Object`プロパティ値ごとに1行のテーブルを作成するとは異なり、 **GroupBy** パラメーターは、プロパティ値を持つ項目ごとに1行のテーブルをプロパティ値ごとに作成します。</span><span class="sxs-lookup"><span data-stu-id="7425b-201">Unlike `Group-Object`, which creates a single table with a row for each property value, the **GroupBy** parameters create a table for each property value with a row for each item that has the property value.</span></span>

<span data-ttu-id="7425b-202">`Group-Object` では、グループ化されるオブジェクトが Microsoft .NET コア型と同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7425b-202">`Group-Object` doesn't require that the objects being grouped are of the same Microsoft .NET Core type.</span></span> <span data-ttu-id="7425b-203">異なる .NET Core 型のオブジェクトをグループ化する場合、で `Group-Object` は次の規則が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7425b-203">When grouping objects of different .NET Core types, `Group-Object` uses the following rules:</span></span>

- <span data-ttu-id="7425b-204">同じプロパティ名と型。</span><span class="sxs-lookup"><span data-stu-id="7425b-204">Same Property Names and Types.</span></span>

  <span data-ttu-id="7425b-205">オブジェクトに指定された名前のプロパティがあり、プロパティ値の .NET Core 型が同じである場合、プロパティ値は同じ型のオブジェクトに使用されるのと同じ規則を使用してグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="7425b-205">If the objects have a property with the specified name, and the property values have the same .NET Core type, the property values are grouped by using the same rules that would be used for objects of the same type.</span></span>

- <span data-ttu-id="7425b-206">同じプロパティ名、異なる型。</span><span class="sxs-lookup"><span data-stu-id="7425b-206">Same Property Names, Different Types.</span></span>

  <span data-ttu-id="7425b-207">オブジェクトに指定された名前のプロパティがあり、プロパティ値が異なるオブジェクトに異なる .NET Core 型を持っている場合、は、 `Group-Object` そのプロパティグループの .net core 型として最初に見つかったプロパティの .Net core 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="7425b-207">If the objects have a property with the specified name, but the property values have a different .NET Core type in different objects, `Group-Object` uses the .NET Core type of the first occurrence of the property as the .NET Core type for that property group.</span></span> <span data-ttu-id="7425b-208">オブジェクトに異なる型のプロパティがある場合、プロパティ値は、そのグループの型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7425b-208">When an object has a property with a different type, the property value is converted to the type for that group.</span></span> <span data-ttu-id="7425b-209">型変換に失敗した場合、オブジェクトはグループに含まれません。</span><span class="sxs-lookup"><span data-stu-id="7425b-209">If the type conversion fails, the object isn't included in the group.</span></span>

- <span data-ttu-id="7425b-210">プロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="7425b-210">Missing Properties.</span></span>

  <span data-ttu-id="7425b-211">指定されたプロパティを持たないオブジェクトはグループ化できません。</span><span class="sxs-lookup"><span data-stu-id="7425b-211">Objects that don't have a specified property can't be grouped.</span></span> <span data-ttu-id="7425b-212">グループ化されていないオブジェクトは、という名前のグループの最終的な **GroupInfo** オブジェクト出力に表示され `AutomationNull.Value` ます。</span><span class="sxs-lookup"><span data-stu-id="7425b-212">Objects that aren't grouped appear in the final **GroupInfo** object output in a group named `AutomationNull.Value`.</span></span>

## <span data-ttu-id="7425b-213">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7425b-213">RELATED LINKS</span></span>

[<span data-ttu-id="7425b-214">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="7425b-214">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="7425b-215">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="7425b-215">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="7425b-216">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="7425b-216">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="7425b-217">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="7425b-217">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="7425b-218">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="7425b-218">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="7425b-219">New-Object</span><span class="sxs-lookup"><span data-stu-id="7425b-219">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="7425b-220">Select-Object</span><span class="sxs-lookup"><span data-stu-id="7425b-220">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="7425b-221">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="7425b-221">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="7425b-222">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="7425b-222">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="7425b-223">Where-Object</span><span class="sxs-lookup"><span data-stu-id="7425b-223">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
