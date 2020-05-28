---
ms.date: 09/13/2019
title: FilterHashtable を使った Get-WinEvent クエリの作成
ms.openlocfilehash: 485b0cf05489d9add201c71c01fe2ed0c48db387
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563934"
---
# <a name="creating-get-winevent-queries-with-filterhashtable"></a><span data-ttu-id="09785-102">FilterHashtable を使った Get-WinEvent クエリの作成</span><span class="sxs-lookup"><span data-stu-id="09785-102">Creating Get-WinEvent queries with FilterHashtable</span></span>

<span data-ttu-id="09785-103">2014 年 6 月 3 日の元の **Scripting Guy** のブログ投稿をご覧になる場合は、「[Use FilterHashTable to Filter Event Log with PowerShell (PowerShell で FilterHashTable を使ってイベント ログをフィルター処理する)](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09785-103">To read the original June 3, 2014 **Scripting Guy** blog post, see [Use FilterHashTable to Filter Event Log with PowerShell](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/).</span></span>

<span data-ttu-id="09785-104">この記事は元のブログ投稿の抜粋です。`Get-WinEvent` コマンドレットの **FilterHashtable** パラメーターを使ってイベント ログをフィルター処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09785-104">This article is an excerpt of the original blog post and explains how to use the `Get-WinEvent` cmdlet's **FilterHashtable** parameter to filter event logs.</span></span> <span data-ttu-id="09785-105">PowerShell の `Get-WinEvent` コマンドレットは、Windows イベントと診断のログをフィルター処理するための強力な方法です。</span><span class="sxs-lookup"><span data-stu-id="09785-105">PowerShell's `Get-WinEvent` cmdlet is a powerful method to filter Windows event and diagnostic logs.</span></span> <span data-ttu-id="09785-106">`Get-WinEvent` クエリで **FilterHashtable** パラメーターを使うとパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="09785-106">Performance improves when a `Get-WinEvent` query uses the **FilterHashtable** parameter.</span></span>

<span data-ttu-id="09785-107">大規模なイベント ログを使用する場合、パイプラインを通して `Where-Object` コマンドにオブジェクトを送信するのは効率的ではありません。</span><span class="sxs-lookup"><span data-stu-id="09785-107">When you work with large event logs, it's not efficient to send objects down the pipeline to a `Where-Object` command.</span></span> <span data-ttu-id="09785-108">PowerShell 6 以前では、`Get-EventLog` コマンドレットがログ データを取得するためのもう一つのオプションでした。</span><span class="sxs-lookup"><span data-stu-id="09785-108">Prior to PowerShell 6, the `Get-EventLog` cmdlet was another option to get log data.</span></span> <span data-ttu-id="09785-109">たとえば、**Microsoft-Windows-Defrag** ログをフィルター処理する場合、次のコマンドは効率的ではありません。</span><span class="sxs-lookup"><span data-stu-id="09785-109">For example, the following commands are inefficient to filter the **Microsoft-Windows-Defrag** logs:</span></span>

```powershell
Get-EventLog -LogName Application | Where-Object Source -Match defrag

Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'defrag' }
```

<span data-ttu-id="09785-110">次のコマンドでは、パフォーマンスが向上するハッシュ テーブルを使っています。</span><span class="sxs-lookup"><span data-stu-id="09785-110">The following command uses a hash table that improves the performance:</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='*defrag'
}
```

## <a name="blog-posts-about-enumeration"></a><span data-ttu-id="09785-111">列挙体についてのブログ投稿</span><span class="sxs-lookup"><span data-stu-id="09785-111">Blog posts about enumeration</span></span>

<span data-ttu-id="09785-112">この記事では、ハッシュ テーブルで列挙値を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09785-112">This article presents information about how to use enumerated values in a hash table.</span></span> <span data-ttu-id="09785-113">列挙体について詳しくは、これらの **Scripting Guy** のブログ投稿をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09785-113">For more information about enumeration, read these **Scripting Guy** blog posts.</span></span> <span data-ttu-id="09785-114">列挙値を返す関数を作成するには、「[Enumerations and Values (列挙型および値)](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09785-114">To create a function that returns the enumerated values, see [Enumerations and Values](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values).</span></span>
<span data-ttu-id="09785-115">詳細については、[列挙体に関する Scripting Guy の一連のブログ投稿](https://devblogs.microsoft.com/scripting/?s=about+enumeration)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09785-115">For more information, see the [Scripting Guy series of blog posts about enumeration](https://devblogs.microsoft.com/scripting/?s=about+enumeration).</span></span>

## <a name="hash-table-key-value-pairs"></a><span data-ttu-id="09785-116">ハッシュ テーブルのキーと値のペア</span><span class="sxs-lookup"><span data-stu-id="09785-116">Hash table key-value pairs</span></span>

<span data-ttu-id="09785-117">効率的なクエリを作成するには、**FilterHashtable** パラメーターと共に `Get-WinEvent` コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="09785-117">To build efficient queries, use the `Get-WinEvent` cmdlet with the **FilterHashtable** parameter.</span></span>
<span data-ttu-id="09785-118">**FilterHashtable** には、Windows イベント ログから特定の情報を取得するためのフィルターとして、ハッシュ テーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="09785-118">**FilterHashtable** accepts a hash table as a filter to get specific information from Windows event logs.</span></span> <span data-ttu-id="09785-119">ハッシュ テーブルでは、**キーと値**のペアを使用します。</span><span class="sxs-lookup"><span data-stu-id="09785-119">A hash table uses **key-value** pairs.</span></span> <span data-ttu-id="09785-120">ハッシュ テーブルの詳細については、「[about_Hash_Tables (ハッシュ テーブルについて)](/powershell/module/microsoft.powershell.core/about/about_hash_tables)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09785-120">For more information about hash tables, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="09785-121">**キーと値**のペアが同じ行に存在する場合は、それらをセミコロンで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="09785-121">If the **key-value** pairs are on the same line, they must be separated by a semicolon.</span></span> <span data-ttu-id="09785-122">**キーと値**のペアがそれぞれ別々の行に存在する場合は、セミコロンは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="09785-122">If each **key-value** pair is on a separate line, the semicolon isn't needed.</span></span> <span data-ttu-id="09785-123">たとえば、この記事では**キーと値**のペアを別々の行に置き、セミコロンは使用しません。</span><span class="sxs-lookup"><span data-stu-id="09785-123">For example, this article places **key-value** pairs on separate lines and doesn't use semicolons.</span></span>

<span data-ttu-id="09785-124">このサンプルでは、**FilterHashtable** パラメーターの**キーと値**のペアのいくつかを使用します。</span><span class="sxs-lookup"><span data-stu-id="09785-124">This sample uses several of the **FilterHashtable** parameter's **key-value** pairs.</span></span> <span data-ttu-id="09785-125">完成したクエリには、**LogName**、**ProviderName**、**Keywords**、**ID**、および **Level** が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09785-125">The completed query includes **LogName**, **ProviderName**, **Keywords**, **ID**, and **Level**.</span></span>

<span data-ttu-id="09785-126">適用できる**キーと値**のペアを次の表に示します。これらは、[Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable** パラメーターのドキュメントに含まれています。</span><span class="sxs-lookup"><span data-stu-id="09785-126">The accepted **key-value** pairs are shown in the following table and are included in the documentation for the [Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable** parameter.</span></span>

<span data-ttu-id="09785-127">キー名、データ型、およびデータ値に対してワイルドカード文字を指定できるかどうかを、次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="09785-127">The following table displays the key names, data types, and whether wildcard characters are accepted for a data value.</span></span>

|    <span data-ttu-id="09785-128">キー名</span><span class="sxs-lookup"><span data-stu-id="09785-128">Key name</span></span>    | <span data-ttu-id="09785-129">値のデータ型</span><span class="sxs-lookup"><span data-stu-id="09785-129">Value data type</span></span> | <span data-ttu-id="09785-130">ワイルドカード文字を指定できるか</span><span class="sxs-lookup"><span data-stu-id="09785-130">Accepts wildcard characters?</span></span> |
| -------------- | --------------- | ---------------------------- |
| <span data-ttu-id="09785-131">LogName</span><span class="sxs-lookup"><span data-stu-id="09785-131">LogName</span></span>        | `<String[]>`    | <span data-ttu-id="09785-132">はい</span><span class="sxs-lookup"><span data-stu-id="09785-132">Yes</span></span>                          |
| <span data-ttu-id="09785-133">ProviderName</span><span class="sxs-lookup"><span data-stu-id="09785-133">ProviderName</span></span>   | `<String[]>`    | <span data-ttu-id="09785-134">はい</span><span class="sxs-lookup"><span data-stu-id="09785-134">Yes</span></span>                          |
| <span data-ttu-id="09785-135">Path</span><span class="sxs-lookup"><span data-stu-id="09785-135">Path</span></span>           | `<String[]>`    | <span data-ttu-id="09785-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="09785-136">No</span></span>                           |
| <span data-ttu-id="09785-137">Keywords</span><span class="sxs-lookup"><span data-stu-id="09785-137">Keywords</span></span>       | `<Long[]>`      | <span data-ttu-id="09785-138">いいえ</span><span class="sxs-lookup"><span data-stu-id="09785-138">No</span></span>                           |
| <span data-ttu-id="09785-139">id</span><span class="sxs-lookup"><span data-stu-id="09785-139">ID</span></span>             | `<Int32[]>`     | <span data-ttu-id="09785-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="09785-140">No</span></span>                           |
| <span data-ttu-id="09785-141">Level</span><span class="sxs-lookup"><span data-stu-id="09785-141">Level</span></span>          | `<Int32[]>`     | <span data-ttu-id="09785-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="09785-142">No</span></span>                           |
| <span data-ttu-id="09785-143">StartTime</span><span class="sxs-lookup"><span data-stu-id="09785-143">StartTime</span></span>      | `<DateTime>`    | <span data-ttu-id="09785-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="09785-144">No</span></span>                           |
| <span data-ttu-id="09785-145">EndTime</span><span class="sxs-lookup"><span data-stu-id="09785-145">EndTime</span></span>        | `<DateTime>`    | <span data-ttu-id="09785-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="09785-146">No</span></span>                           |
| <span data-ttu-id="09785-147">UserID</span><span class="sxs-lookup"><span data-stu-id="09785-147">UserID</span></span>         | `<SID>`         | <span data-ttu-id="09785-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="09785-148">No</span></span>                           |
| <span data-ttu-id="09785-149">Data</span><span class="sxs-lookup"><span data-stu-id="09785-149">Data</span></span>           | `<String[]>`    | <span data-ttu-id="09785-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="09785-150">No</span></span>                           |
| `<named-data>` | `<String[]>`    | <span data-ttu-id="09785-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="09785-151">No</span></span>                           |

<span data-ttu-id="09785-152">`<named-data>` キーは、名前付きイベント データ フィールドを表します。</span><span class="sxs-lookup"><span data-stu-id="09785-152">The `<named-data>` key represents a named event data field.</span></span> <span data-ttu-id="09785-153">たとえば、Perflib イベント 1008 には次のイベント データを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="09785-153">For example, the Perflib event 1008 can contain the following event data:</span></span>

```xml
<EventData>
  <Data Name="Service">BITS</Data>
  <Data Name="Library">C:\Windows\System32\bitsperf.dll</Data>
  <Data Name="Win32Error">2</Data>
</EventData>
```

<span data-ttu-id="09785-154">次のコマンドを利用し、これらのイベントに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="09785-154">You can query for these events using the following command:</span></span>

```powershell
Get-WinEvent -FilterHashtable @{LogName='Application'; 'Service'='Bits'}
```

> [!NOTE]
> <span data-ttu-id="09785-155">PowerShell 6 では、`<named-data>` のクエリを実行する機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="09785-155">The ability to query for `<named-data>` was added in PowerShell 6.</span></span>

## <a name="building-a-query-with-a-hash-table"></a><span data-ttu-id="09785-156">ハッシュ テーブルを使ったクエリの作成</span><span class="sxs-lookup"><span data-stu-id="09785-156">Building a query with a hash table</span></span>

<span data-ttu-id="09785-157">結果を確認して問題をトラブルシューティングするため、一度に 1 つの**キーと値**のペアのハッシュ テーブルを作成すると役立ちます。</span><span class="sxs-lookup"><span data-stu-id="09785-157">To verify results and troubleshoot problems, it helps to build the hash table one **key-value** pair at a time.</span></span> <span data-ttu-id="09785-158">クエリでは、**アプリケーション** ログからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="09785-158">The query gets data from the **Application** log.</span></span> <span data-ttu-id="09785-159">ハッシュ テーブルは `Get-WinEvent –LogName Application` に相当します。</span><span class="sxs-lookup"><span data-stu-id="09785-159">The hash table is equivalent to `Get-WinEvent –LogName Application`.</span></span>

<span data-ttu-id="09785-160">まず、`Get-WinEvent` クエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="09785-160">To begin, create the `Get-WinEvent` query.</span></span> <span data-ttu-id="09785-161">**FilterHashtable** パラメーターの**キーと値**のペアを使います。キーには **LogName** を、値には **Application** を指定します。</span><span class="sxs-lookup"><span data-stu-id="09785-161">Use the **FilterHashtable** parameter's **key-value** pair with the key, **LogName**, and the value, **Application**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
}
```

<span data-ttu-id="09785-162">**ProviderName** キーを使ってハッシュ テーブルの作成を続けます。</span><span class="sxs-lookup"><span data-stu-id="09785-162">Continue to build the hash table with the **ProviderName** key.</span></span> <span data-ttu-id="09785-163">**ProviderName** は、 **[Windows イベント ビューアー]** の **[ソース]** フィールドに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="09785-163">The **ProviderName** is the name that appears in the **Source** field in the **Windows Event Viewer**.</span></span> <span data-ttu-id="09785-164">たとえば、次のスクリーン ショットの **[.NET Runtime]\(.NET ランタイム\)** です。</span><span class="sxs-lookup"><span data-stu-id="09785-164">For example, **.NET Runtime** in the following screenshot:</span></span>

![[Windows イベント ビューアー] のソースの画像。](./media/creating-get-winEvent-queries-with-filterhashtable/providername.png)

<span data-ttu-id="09785-166">ハッシュ テーブルを更新して、キーが **ProviderName** で、値が **.NET Runtime** である**キーと値**のペアを含めます。</span><span class="sxs-lookup"><span data-stu-id="09785-166">Update the hash table and include the **key-value** pair with the key, **ProviderName**, and the value, **.NET Runtime**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
}
```

<span data-ttu-id="09785-167">クエリで、アーカイブ済みのイベント ログからデータを取得する必要がある場合は、**Path** キーを使います。</span><span class="sxs-lookup"><span data-stu-id="09785-167">If your query needs to get data from archived event logs, use the **Path** key.</span></span> <span data-ttu-id="09785-168">**パス**の値でログ ファイルへの完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="09785-168">The **Path** value specifies the full path to the log file.</span></span> <span data-ttu-id="09785-169">詳細については、**Scripting Guy** のブログ投稿「[Use PowerShell to Parse Saved Event Logs for Errors (エラーのために、PowerShell を使って保存したイベント ログを解析する)](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09785-169">For more information, see the **Scripting Guy** blog post, [Use PowerShell to Parse Saved Event Logs for Errors](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors).</span></span>

## <a name="using-enumerated-values-in-a-hash-table"></a><span data-ttu-id="09785-170">ハッシュ テーブルでの列挙値の使用</span><span class="sxs-lookup"><span data-stu-id="09785-170">Using enumerated values in a hash table</span></span>

<span data-ttu-id="09785-171">ハッシュ テーブルの次のキーは、**Keywords** です。</span><span class="sxs-lookup"><span data-stu-id="09785-171">**Keywords** is the next key in the hash table.</span></span> <span data-ttu-id="09785-172">**Keywords** のデータ型は、大きい数を保持する値の型 `[long]` の配列です。</span><span class="sxs-lookup"><span data-stu-id="09785-172">The **Keywords** data type is an array of the `[long]` value type that holds a large number.</span></span> <span data-ttu-id="09785-173">次のコマンドを使って `[long]` の最大値を検索します。</span><span class="sxs-lookup"><span data-stu-id="09785-173">Use the following command to find the maximum value of `[long]`:</span></span>

```powershell
[long]::MaxValue
```

```Output
9223372036854775807
```

<span data-ttu-id="09785-174">PowerShell では、**Keywords** キーに対して、**Security** などの文字列ではなく数値を使います。</span><span class="sxs-lookup"><span data-stu-id="09785-174">For the **Keywords** key, PowerShell uses a number, not a string such as **Security**.</span></span> <span data-ttu-id="09785-175">**[Windows イベント ビューアー]** では文字列として **Keywords** が表示されますが、それらは列挙値です。</span><span class="sxs-lookup"><span data-stu-id="09785-175">**Windows Event Viewer** displays the **Keywords** as strings, but they are enumerated values.</span></span> <span data-ttu-id="09785-176">ハッシュ テーブルでは、文字列値と共に **Keywords** キーを使うと、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09785-176">In the hash table, if you use the **Keywords** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="09785-177">**[Windows イベント ビューアー]** を開き、 **[操作]** ウィンドウから **[現在のログをフィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09785-177">Open the **Windows Event Viewer** and from the **Actions** pane, click on **Filter current log**.</span></span>
<span data-ttu-id="09785-178">次のスクリーン ショットに示すように、使用可能なキーワードが **[キーワード]** ドロップダウン メニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="09785-178">The **Keywords** drop-down menu displays the available keywords, as shown in the following screenshot:</span></span>

![[Windows イベント ビューアー] のキーワードの画像。](./media/creating-get-winEvent-queries-with-filterhashtable/keywords.png)

<span data-ttu-id="09785-180">次のコマンドを使って、`StandardEventKeywords` プロパティの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="09785-180">Use the following command to display the `StandardEventKeywords` property names.</span></span>

```powershell
[System.Diagnostics.Eventing.Reader.StandardEventKeywords] | Get-Member -Static -MemberType Property
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.StandardEventKeywords
Name             MemberType Definition
—-             ———- ———-
AuditFailure     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
AuditSuccess     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
CorrelationHint  Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
CorrelationHint2 Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
EventLogClassic  Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
None             Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
ResponseTime     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
Sqm              Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
WdiContext       Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
WdiDiagnostic    Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
```

<span data-ttu-id="09785-181">列挙値は **.NET Framework** でドキュメント化されています。</span><span class="sxs-lookup"><span data-stu-id="09785-181">The enumerated values are documented in the **.NET Framework**.</span></span> <span data-ttu-id="09785-182">詳細については、[StandardEventKeywords 列挙型](/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords?redirectedfrom=MSDN&view=netframework-4.7.2)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09785-182">For more information, see [StandardEventKeywords Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords?redirectedfrom=MSDN&view=netframework-4.7.2).</span></span>

<span data-ttu-id="09785-183">**Keywords** の名前と列挙値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="09785-183">The **Keywords** names and enumerated values are as follows:</span></span>

| <span data-ttu-id="09785-184">名前</span><span class="sxs-lookup"><span data-stu-id="09785-184">Name</span></span>             |  <span data-ttu-id="09785-185">値</span><span class="sxs-lookup"><span data-stu-id="09785-185">Value</span></span>            |
| ---------------- | ------------------|
| <span data-ttu-id="09785-186">AuditFailure</span><span class="sxs-lookup"><span data-stu-id="09785-186">AuditFailure</span></span>     | <span data-ttu-id="09785-187">4503599627370496</span><span class="sxs-lookup"><span data-stu-id="09785-187">4503599627370496</span></span>  |
| <span data-ttu-id="09785-188">AuditSuccess</span><span class="sxs-lookup"><span data-stu-id="09785-188">AuditSuccess</span></span>     | <span data-ttu-id="09785-189">9007199254740992</span><span class="sxs-lookup"><span data-stu-id="09785-189">9007199254740992</span></span>  |
| <span data-ttu-id="09785-190">CorrelationHint2</span><span class="sxs-lookup"><span data-stu-id="09785-190">CorrelationHint2</span></span> | <span data-ttu-id="09785-191">18014398509481984</span><span class="sxs-lookup"><span data-stu-id="09785-191">18014398509481984</span></span> |
| <span data-ttu-id="09785-192">EventLogClassic</span><span class="sxs-lookup"><span data-stu-id="09785-192">EventLogClassic</span></span>  | <span data-ttu-id="09785-193">36028797018963968</span><span class="sxs-lookup"><span data-stu-id="09785-193">36028797018963968</span></span> |
| <span data-ttu-id="09785-194">Sqm</span><span class="sxs-lookup"><span data-stu-id="09785-194">Sqm</span></span>              | <span data-ttu-id="09785-195">2251799813685248</span><span class="sxs-lookup"><span data-stu-id="09785-195">2251799813685248</span></span>  |
| <span data-ttu-id="09785-196">WdiDiagnostic</span><span class="sxs-lookup"><span data-stu-id="09785-196">WdiDiagnostic</span></span>    | <span data-ttu-id="09785-197">1125899906842624</span><span class="sxs-lookup"><span data-stu-id="09785-197">1125899906842624</span></span>  |
| <span data-ttu-id="09785-198">WdiContext</span><span class="sxs-lookup"><span data-stu-id="09785-198">WdiContext</span></span>       | <span data-ttu-id="09785-199">562949953421312</span><span class="sxs-lookup"><span data-stu-id="09785-199">562949953421312</span></span>   |
| <span data-ttu-id="09785-200">ResponseTime</span><span class="sxs-lookup"><span data-stu-id="09785-200">ResponseTime</span></span>     | <span data-ttu-id="09785-201">281474976710656</span><span class="sxs-lookup"><span data-stu-id="09785-201">281474976710656</span></span>   |
| <span data-ttu-id="09785-202">なし</span><span class="sxs-lookup"><span data-stu-id="09785-202">None</span></span>             | <span data-ttu-id="09785-203">0</span><span class="sxs-lookup"><span data-stu-id="09785-203">0</span></span>                 |

<span data-ttu-id="09785-204">ハッシュ テーブルを更新し、キーが **Keywords**、**EventLogClassic** の列挙値が **36028797018963968** である**キーと値**のペアを含めます。</span><span class="sxs-lookup"><span data-stu-id="09785-204">Update the hash table and include the **key-value** pair with the key, **Keywords**, and the **EventLogClassic** enumeration value, **36028797018963968**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
}
```

### <a name="keywords-static-property-value-optional"></a><span data-ttu-id="09785-205">Keywords の静的プロパティ値 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="09785-205">Keywords static property value (optional)</span></span>

<span data-ttu-id="09785-206">**Keywords** キーは列挙されますが、ハッシュ テーブルのクエリで静的なプロパティ名を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="09785-206">The **Keywords** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="09785-207">返される文字列を使うのではなく、**Value__** プロパティを含む値にプロパティ名を変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09785-207">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="09785-208">たとえば、次のスクリプトでは **Value__** プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="09785-208">For example, the following script uses the **Value__** property.</span></span>

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventKeywords]::EventLogClassic
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=$C.Value__
}
```

## <a name="filtering-by-event-id"></a><span data-ttu-id="09785-209">イベント ID でのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="09785-209">Filtering by Event Id</span></span>

<span data-ttu-id="09785-210">より具体的なデータを取得するために、クエリの結果を**イベント ID** でフィルター処理します。**イベント ID** は、ハッシュ テーブルではキー **ID** として参照され、その値は特定の**イベント ID** です。**イベント ID** は **[Windows イベント ビューアー]** で表示されます。この例では、**イベント ID 1023** を使います。</span><span class="sxs-lookup"><span data-stu-id="09785-210">To get more specific data, the query's results are filtered by **Event Id**. The **Event Id** is referenced in the hash table as the key **ID** and the value is a specific **Event Id**. The **Windows Event Viewer** displays the **Event Id**. This example uses **Event Id 1023**.</span></span>

<span data-ttu-id="09785-211">ハッシュ テーブルを更新して、キーが **ID**、値が **1023** である**キーと値**のペアを含めます。</span><span class="sxs-lookup"><span data-stu-id="09785-211">Update the hash table and include the **key-value** pair with the key, **ID** and the value, **1023**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
}
```

## <a name="filtering-by-level"></a><span data-ttu-id="09785-212">レベルでのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="09785-212">Filtering by Level</span></span>

<span data-ttu-id="09785-213">さらに結果を絞り込み、エラーであるイベントのみを含むようにするために、**Level** キーを使います。</span><span class="sxs-lookup"><span data-stu-id="09785-213">To further refine the results and include only events that are errors, use the **Level** key.</span></span>
<span data-ttu-id="09785-214">**[Windows イベント ビューアー]** では文字列値として **Level** が表示されますが、それらは列挙値です。</span><span class="sxs-lookup"><span data-stu-id="09785-214">**Windows Event Viewer** displays the **Level** as string values, but they are enumerated values.</span></span> <span data-ttu-id="09785-215">ハッシュ テーブルでは、文字列値と共に **Level** キーを使うと、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09785-215">In the hash table, if you use the **Level** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="09785-216">**Level** は **Error**、**Warning**、または **Informational** などの値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="09785-216">**Level** has values such as **Error**, **Warning**, or **Informational**.</span></span> <span data-ttu-id="09785-217">次のコマンドを使って、`StandardEventLevel` プロパティの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="09785-217">Use the following command to display the `StandardEventLevel` property names.</span></span>

```powershell
[System.Diagnostics.Eventing.Reader.StandardEventLevel] | Get-Member -Static -MemberType Property
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.StandardEventLevel

Name          MemberType Definition
----          ---------- ----------
Critical      Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Critical {get;}
Error         Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Error {get;}
Informational Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Informational {get;}
LogAlways     Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel LogAlways {get;}
Verbose       Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Verbose {get;}
Warning       Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Warning {get;}
```

<span data-ttu-id="09785-218">列挙値は **.NET Framework** でドキュメント化されています。</span><span class="sxs-lookup"><span data-stu-id="09785-218">The enumerated values are documented in the **.NET Framework**.</span></span> <span data-ttu-id="09785-219">詳細については、[StandardEventLevel 列挙型](/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel?redirectedfrom=MSDN&view=netframework-4.7.2)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09785-219">For more information, see [StandardEventLevel Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel?redirectedfrom=MSDN&view=netframework-4.7.2).</span></span>

<span data-ttu-id="09785-220">**Level** キーの名前と列挙値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="09785-220">The **Level** key's names and enumerated values are as follows:</span></span>

| <span data-ttu-id="09785-221">名前</span><span class="sxs-lookup"><span data-stu-id="09785-221">Name</span></span>           | <span data-ttu-id="09785-222">値</span><span class="sxs-lookup"><span data-stu-id="09785-222">Value</span></span> |
| -------------- | ----- |
| <span data-ttu-id="09785-223">"詳細"</span><span class="sxs-lookup"><span data-stu-id="09785-223">Verbose</span></span>        |   <span data-ttu-id="09785-224">5</span><span class="sxs-lookup"><span data-stu-id="09785-224">5</span></span>   |
| <span data-ttu-id="09785-225">Informational</span><span class="sxs-lookup"><span data-stu-id="09785-225">Informational</span></span>  |   <span data-ttu-id="09785-226">4</span><span class="sxs-lookup"><span data-stu-id="09785-226">4</span></span>   |
| <span data-ttu-id="09785-227">警告</span><span class="sxs-lookup"><span data-stu-id="09785-227">Warning</span></span>        |   <span data-ttu-id="09785-228">3</span><span class="sxs-lookup"><span data-stu-id="09785-228">3</span></span>   |
| <span data-ttu-id="09785-229">エラー</span><span class="sxs-lookup"><span data-stu-id="09785-229">Error</span></span>          |   <span data-ttu-id="09785-230">2</span><span class="sxs-lookup"><span data-stu-id="09785-230">2</span></span>   |
| <span data-ttu-id="09785-231">Critical</span><span class="sxs-lookup"><span data-stu-id="09785-231">Critical</span></span>       |   <span data-ttu-id="09785-232">1</span><span class="sxs-lookup"><span data-stu-id="09785-232">1</span></span>   |
| <span data-ttu-id="09785-233">LogAlways</span><span class="sxs-lookup"><span data-stu-id="09785-233">LogAlways</span></span>      |   <span data-ttu-id="09785-234">0</span><span class="sxs-lookup"><span data-stu-id="09785-234">0</span></span>   |

<span data-ttu-id="09785-235">完成したクエリのハッシュ テーブルには、キー **Level** と値 **2** が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09785-235">The hash table for the completed query includes the key, **Level**, and the value, **2**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=2
}
```

### <a name="level-static-property-in-enumeration-optional"></a><span data-ttu-id="09785-236">列挙型の Level の静的プロパティ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="09785-236">Level static property in enumeration (optional)</span></span>

<span data-ttu-id="09785-237">**Level** キーは列挙されますが、ハッシュ テーブルのクエリで静的なプロパティ名を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="09785-237">The **Level** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="09785-238">返される文字列を使うのではなく、**Value__** プロパティを含む値にプロパティ名を変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09785-238">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="09785-239">たとえば、次のスクリプトでは **Value__** プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="09785-239">For example, the following script uses the **Value__** property.</span></span>

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventLevel]::Informational
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=$C.Value__
}
```
