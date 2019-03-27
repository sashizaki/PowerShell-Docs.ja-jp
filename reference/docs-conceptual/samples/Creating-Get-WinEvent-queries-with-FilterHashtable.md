---
ms.date: 3/18/2019
title: FilterHashtable を使った Get-WinEvent クエリの作成
ms.openlocfilehash: fae01cc8be5c1805e2aae008e1f21ed387efa325
ms.sourcegitcommit: 396509cd0d415acc306b68758b6f833406e26bf5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58320457"
---
# <a name="creating-get-winevent-queries-with-filterhashtable"></a><span data-ttu-id="5640f-102">FilterHashtable を使った Get-WinEvent クエリの作成</span><span class="sxs-lookup"><span data-stu-id="5640f-102">Creating Get-WinEvent queries with FilterHashtable</span></span>

<span data-ttu-id="5640f-103">2014 年 6 月 3 日の元の **Scripting Guy** のブログ投稿をご覧になる場合は、「[Use FilterHashTable to Filter Event Log with PowerShell (PowerShell で FilterHashTable を使ってイベント ログをフィルター処理する)](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5640f-103">To read the original June 3, 2014 **Scripting Guy** blog post, see [Use FilterHashTable to Filter Event Log with PowerShell](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/).</span></span>

<span data-ttu-id="5640f-104">この記事は元のブログ投稿の抜粋です。`Get-WinEvent` コマンドレットの **FilterHashtable** パラメーターを使ってイベント ログをフィルター処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5640f-104">This article is an excerpt of the original blog post and explains how to use the `Get-WinEvent` cmdlet's **FilterHashtable** parameter to filter event logs.</span></span> <span data-ttu-id="5640f-105">PowerShell の `Get-WinEvent` コマンドレットは、Windows イベントと診断のログをフィルター処理するための強力な方法です。</span><span class="sxs-lookup"><span data-stu-id="5640f-105">PowerShell's `Get-WinEvent` cmdlet is a powerful method to filter Windows event and diagnostic logs.</span></span> <span data-ttu-id="5640f-106">`Get-WinEvent` クエリで **FilterHashtable** パラメーターを使うとパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="5640f-106">Performance improves when a `Get-WinEvent` query uses the **FilterHashtable** parameter.</span></span>

<span data-ttu-id="5640f-107">大規模なイベント ログを使用する場合、パイプラインを通して `Where-Object` コマンドにオブジェクトを送信するのは効率的ではありません。</span><span class="sxs-lookup"><span data-stu-id="5640f-107">When you work with large event logs, it's not efficient to send objects down the pipeline to a `Where-Object` command.</span></span> <span data-ttu-id="5640f-108">PowerShell 6 以前では、`Get-EventLog` コマンドレットがログ データを取得するためのもう一つのオプションでした。</span><span class="sxs-lookup"><span data-stu-id="5640f-108">Prior to PowerShell 6, the `Get-EventLog` cmdlet was another option to get log data.</span></span> <span data-ttu-id="5640f-109">たとえば、**Microsoft-Windows-Defrag** ログをフィルター処理する場合、次のコマンドは効率的ではありません。</span><span class="sxs-lookup"><span data-stu-id="5640f-109">For example, the following commands are inefficient to filter the **Microsoft-Windows-Defrag** logs:</span></span>

`Get-EventLog -LogName Application | Where-Object Source -Match defrag`

`Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'defrag' }`

<span data-ttu-id="5640f-110">次のコマンドでは、パフォーマンスが向上するハッシュ テーブルを使っています。</span><span class="sxs-lookup"><span data-stu-id="5640f-110">The following command uses a hash table that improves the performance:</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='*defrag'
}
```

### <a name="blog-posts-about-enumeration"></a><span data-ttu-id="5640f-111">列挙体についてのブログ投稿</span><span class="sxs-lookup"><span data-stu-id="5640f-111">Blog posts about enumeration</span></span>

<span data-ttu-id="5640f-112">この記事では、ハッシュ テーブルで列挙値を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5640f-112">This article presents information about how to use enumerated values in a hash table.</span></span> <span data-ttu-id="5640f-113">列挙体について詳しくは、これらの **Scripting Guy** のブログ投稿をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5640f-113">For more information about enumeration, read these **Scripting Guy** blog posts.</span></span> <span data-ttu-id="5640f-114">列挙値を返す関数を作成するには、「[Enumerations and Values (列挙型および値)](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5640f-114">To create a function that returns the enumerated values, see [Enumerations and Values](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values).</span></span>
<span data-ttu-id="5640f-115">詳細については、[列挙体に関する Scripting Guy の一連のブログ投稿](https://devblogs.microsoft.com/scripting/?s=about+enumeration)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5640f-115">For more information, see the [Scripting Guy series of blog posts about enumeration](https://devblogs.microsoft.com/scripting/?s=about+enumeration).</span></span>

### <a name="hash-table-keyvalue-pairs"></a><span data-ttu-id="5640f-116">ハッシュ テーブルのキー/値のペア</span><span class="sxs-lookup"><span data-stu-id="5640f-116">Hash table key/value pairs</span></span>

<span data-ttu-id="5640f-117">効率的なクエリを作成するには、**FilterHashtable** パラメーターと共に `Get-WinEvent` コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="5640f-117">To build efficient queries, use the `Get-WinEvent` cmdlet with the **FilterHashtable** parameter.</span></span>
<span data-ttu-id="5640f-118">**FilterHashtable** には、Windows イベント ログから特定の情報を取得するためのフィルターとして、ハッシュ テーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5640f-118">**FilterHashtable** accepts a hash table as a filter to get specific information from Windows event logs.</span></span> <span data-ttu-id="5640f-119">ハッシュ テーブルでは**キー/値**のペアを使います。</span><span class="sxs-lookup"><span data-stu-id="5640f-119">A hash table uses **key/value** pairs.</span></span> <span data-ttu-id="5640f-120">ハッシュ テーブルの詳細については、「[about_Hash_Tables (ハッシュ テーブルについて)](/powershell/module/microsoft.powershell.core/about/about_hash_tables)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5640f-120">For more information about hash tables, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="5640f-121">**キー/値**のペアが同じ行に存在する場合は、それらをセミコロンで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5640f-121">If the **key/value** pairs are on the same line, they must be separated by a semicolon.</span></span> <span data-ttu-id="5640f-122">**キー/値**のペアが別々の行に存在する場合は、セミコロンは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5640f-122">If each **key/value** pair is on a separate line, the semicolon isn't needed.</span></span> <span data-ttu-id="5640f-123">たとえば、この記事では**キー/値**ペアを別々の行に置き、セミコロンを使いません。</span><span class="sxs-lookup"><span data-stu-id="5640f-123">For example, this article places **key/value** pairs on separate lines and doesn't use semicolons.</span></span>

<span data-ttu-id="5640f-124">このサンプルでは、**FilterHashtable** パラメーターの **キー/値** ペアのいくつかを使います。</span><span class="sxs-lookup"><span data-stu-id="5640f-124">This sample uses several of the **FilterHashtable** parameter's **key/value** pairs.</span></span> <span data-ttu-id="5640f-125">完成したクエリには、**LogName**、**ProviderName**、**Keywords**、**ID**、および **Level** が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5640f-125">The completed query includes **LogName**, **ProviderName**, **Keywords**, **ID**, and **Level**.</span></span>

<span data-ttu-id="5640f-126">指定できる**キー/値**のペアを次の表に示します。これらは、[Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable** パラメーターのドキュメントに含まれています。</span><span class="sxs-lookup"><span data-stu-id="5640f-126">The accepted **key/value** pairs are shown in the following table and are included in the documentation for the [Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable** parameter.</span></span>

<span data-ttu-id="5640f-127">キー名、データ型、およびデータ値に対してワイルドカード文字を指定できるかどうかを、次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="5640f-127">The following table displays the key names, data types, and whether wildcard characters are accepted for a data value.</span></span>

| <span data-ttu-id="5640f-128">キー名</span><span class="sxs-lookup"><span data-stu-id="5640f-128">Key name</span></span>     | <span data-ttu-id="5640f-129">値のデータ型</span><span class="sxs-lookup"><span data-stu-id="5640f-129">Value data type</span></span>    | <span data-ttu-id="5640f-130">ワイルドカード文字を指定できるか</span><span class="sxs-lookup"><span data-stu-id="5640f-130">Accepts wildcard characters?</span></span> |
|------------- | ------------------ | ---------------------------- |
| <span data-ttu-id="5640f-131">LogName</span><span class="sxs-lookup"><span data-stu-id="5640f-131">LogName</span></span>      | `<String[]>`       | <span data-ttu-id="5640f-132">可</span><span class="sxs-lookup"><span data-stu-id="5640f-132">Yes</span></span> |
| <span data-ttu-id="5640f-133">ProviderName</span><span class="sxs-lookup"><span data-stu-id="5640f-133">ProviderName</span></span> | `<String[]>`       | <span data-ttu-id="5640f-134">可</span><span class="sxs-lookup"><span data-stu-id="5640f-134">Yes</span></span> |
| <span data-ttu-id="5640f-135">パス</span><span class="sxs-lookup"><span data-stu-id="5640f-135">Path</span></span>         | `<String[]>`       | <span data-ttu-id="5640f-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="5640f-136">No</span></span>  |
| <span data-ttu-id="5640f-137">キーワード</span><span class="sxs-lookup"><span data-stu-id="5640f-137">Keywords</span></span>     | `<Long[]>`         | <span data-ttu-id="5640f-138">いいえ</span><span class="sxs-lookup"><span data-stu-id="5640f-138">No</span></span>  |
| <span data-ttu-id="5640f-139">ID</span><span class="sxs-lookup"><span data-stu-id="5640f-139">ID</span></span>           | `<Int32[]>`        | <span data-ttu-id="5640f-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="5640f-140">No</span></span>  |
| <span data-ttu-id="5640f-141">レベル</span><span class="sxs-lookup"><span data-stu-id="5640f-141">Level</span></span>        | `<Int32[]>`        | <span data-ttu-id="5640f-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="5640f-142">No</span></span>  |
| <span data-ttu-id="5640f-143">StartTime</span><span class="sxs-lookup"><span data-stu-id="5640f-143">StartTime</span></span>    | `<DateTime>`       | <span data-ttu-id="5640f-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="5640f-144">No</span></span>  |
| <span data-ttu-id="5640f-145">EndTime</span><span class="sxs-lookup"><span data-stu-id="5640f-145">EndTime</span></span>      | `<DateTime>`       | <span data-ttu-id="5640f-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="5640f-146">No</span></span>  |
| <span data-ttu-id="5640f-147">UserID</span><span class="sxs-lookup"><span data-stu-id="5640f-147">UserID</span></span>       | `<SID>`            | <span data-ttu-id="5640f-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="5640f-148">No</span></span>  |
| <span data-ttu-id="5640f-149">データ</span><span class="sxs-lookup"><span data-stu-id="5640f-149">Data</span></span>         | `<String[]>`       | <span data-ttu-id="5640f-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="5640f-150">No</span></span>  |
| *            | `<String[]>`       | <span data-ttu-id="5640f-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="5640f-151">No</span></span>  |

### <a name="building-a-query-with-a-hash-table"></a><span data-ttu-id="5640f-152">ハッシュ テーブルを使ったクエリの作成</span><span class="sxs-lookup"><span data-stu-id="5640f-152">Building a query with a hash table</span></span>

<span data-ttu-id="5640f-153">結果を確認して問題をトラブルシューティングするため、一度に 1 つの**キー/値**のペアのハッシュ テーブルを作成すると役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5640f-153">To verify results and troubleshoot problems, it helps to build the hash table one **key/value** pair at a time.</span></span> <span data-ttu-id="5640f-154">クエリでは、**アプリケーション** ログからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="5640f-154">The query gets data from the **Application** log.</span></span> <span data-ttu-id="5640f-155">ハッシュ テーブルは `Get-WinEvent –LogName Application` に相当します。</span><span class="sxs-lookup"><span data-stu-id="5640f-155">The hash table is equivalent to `Get-WinEvent –LogName Application`.</span></span>

<span data-ttu-id="5640f-156">まず、`Get-WinEvent` クエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="5640f-156">To begin, create the `Get-WinEvent` query.</span></span> <span data-ttu-id="5640f-157">**FilterHashtable** パラメーターの**キー/値**のペアを使います。キーには **LogName** を、値には **Application** を指定します。</span><span class="sxs-lookup"><span data-stu-id="5640f-157">Use the **FilterHashtable** parameter's **key/value** pair with the key, **LogName**, and the value, **Application**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
}
```

<span data-ttu-id="5640f-158">**ProviderName** キーを使ってハッシュ テーブルの作成を続けます。</span><span class="sxs-lookup"><span data-stu-id="5640f-158">Continue to build the hash table with the **ProviderName** key.</span></span> <span data-ttu-id="5640f-159">**ProviderName** は、**[Windows イベント ビューアー]** の **[ソース]** フィールドに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="5640f-159">The **ProviderName** is the name that appears in the **Source** field in the **Windows Event Viewer**.</span></span> <span data-ttu-id="5640f-160">たとえば、次のスクリーン ショットの **[.NET Runtime]\(.NET ランタイム\)** です。</span><span class="sxs-lookup"><span data-stu-id="5640f-160">For example, **.NET Runtime** in the following screenshot:</span></span>

![[Windows イベント ビューアー] のソースの画像。](./media/creating-get-winEvent-queries-with-filterhashtable/providername.png)

<span data-ttu-id="5640f-162">ハッシュ テーブルを更新して、キーが **ProviderName、値が **.NET Runtime** である**キー/値\*\*のペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="5640f-162">Update the hash table and include the **key/value** pair with the key, \*\*ProviderName, and the value, **.NET Runtime**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
}
```

<span data-ttu-id="5640f-163">クエリで、アーカイブ済みのイベント ログからデータを取得する必要がある場合は、**Path** キーを使います。</span><span class="sxs-lookup"><span data-stu-id="5640f-163">If your query needs to get data from archived event logs, use the **Path** key.</span></span> <span data-ttu-id="5640f-164">**パス**の値でログ ファイルへの完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5640f-164">The **Path** value specifies the full path to the log file.</span></span> <span data-ttu-id="5640f-165">詳細については、**Scripting Guy** のブログ投稿「[Use PowerShell to Parse Saved Event Logs for Errors (エラーのために、PowerShell を使って保存したイベント ログを解析する)](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5640f-165">For more information, see the **Scripting Guy** blog post, [Use PowerShell to Parse Saved Event Logs for Errors](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors).</span></span>

### <a name="using-enumerated-values-in-a-hash-table"></a><span data-ttu-id="5640f-166">ハッシュ テーブルでの列挙値の使用</span><span class="sxs-lookup"><span data-stu-id="5640f-166">Using enumerated values in a hash table</span></span>

<span data-ttu-id="5640f-167">ハッシュ テーブルの次のキーは、**Keywords** です。</span><span class="sxs-lookup"><span data-stu-id="5640f-167">**Keywords** is the next key in the hash table.</span></span> <span data-ttu-id="5640f-168">**Keywords** のデータ型は、大きい数を保持する値の型 `[long]` の配列です。</span><span class="sxs-lookup"><span data-stu-id="5640f-168">The **Keywords** data type is an array of the `[long]` value type that holds a large number.</span></span> <span data-ttu-id="5640f-169">次のコマンドを使って `[long]` の最大値を検索します。</span><span class="sxs-lookup"><span data-stu-id="5640f-169">Use the following command to find the maximum value of `[long]`:</span></span>

```powershell
[long]::MaxValue
```

```Output
9223372036854775807
```

<span data-ttu-id="5640f-170">PowerShell では、**Keywords** キーに対して、**Security** などの文字列ではなく数値を使います。</span><span class="sxs-lookup"><span data-stu-id="5640f-170">For the **Keywords** key, PowerShell uses a number, not a string such as **Security**.</span></span> <span data-ttu-id="5640f-171">**[Windows イベント ビューアー]** では文字列として **Keywords** が表示されますが、それらは列挙値です。</span><span class="sxs-lookup"><span data-stu-id="5640f-171">**Windows Event Viewer** displays the **Keywords** as strings, but they are enumerated values.</span></span> <span data-ttu-id="5640f-172">ハッシュ テーブルでは、文字列値と共に **Keywords** キーを使うと、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5640f-172">In the hash table, if you use the **Keywords** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="5640f-173">**[Windows イベント ビューアー]** を開き、**[操作]** ウィンドウから **[現在のログをフィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5640f-173">Open the **Windows Event Viewer** and from the **Actions** pane, click on **Filter current log**.</span></span>
<span data-ttu-id="5640f-174">次のスクリーン ショットに示すように、使用可能なキーワードが **[キーワード]** ドロップダウン メニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5640f-174">The **Keywords** drop-down menu displays the available keywords, as shown in the following screenshot:</span></span>

![[Windows イベント ビューアー] のキーワードの画像。](./media/creating-get-winEvent-queries-with-filterhashtable/keywords.png)

<span data-ttu-id="5640f-176">次のコマンドを使って、`StandardEventKeywords` プロパティの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="5640f-176">Use the following command to display the `StandardEventKeywords` property names.</span></span>

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

<span data-ttu-id="5640f-177">列挙値は **.NET Framework** でドキュメント化されています。</span><span class="sxs-lookup"><span data-stu-id="5640f-177">The enumerated values are documented in the **.NET Framework**.</span></span> <span data-ttu-id="5640f-178">詳細については、[StandardEventKeywords 列挙型](https://docs.microsoft.com/en-us/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords?redirectedfrom=MSDN&view=netframework-4.7.2)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5640f-178">For more information, see [StandardEventKeywords Enumeration](https://docs.microsoft.com/en-us/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords?redirectedfrom=MSDN&view=netframework-4.7.2).</span></span>

<span data-ttu-id="5640f-179">**Keywords** の名前と列挙値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5640f-179">The **Keywords** names and enumerated values are as follows:</span></span>

| <span data-ttu-id="5640f-180">名前</span><span class="sxs-lookup"><span data-stu-id="5640f-180">Name</span></span>             |  <span data-ttu-id="5640f-181">値</span><span class="sxs-lookup"><span data-stu-id="5640f-181">Value</span></span>            |
| ---------------- | ------------------|
| <span data-ttu-id="5640f-182">AuditFailure</span><span class="sxs-lookup"><span data-stu-id="5640f-182">AuditFailure</span></span>     | <span data-ttu-id="5640f-183">4503599627370496</span><span class="sxs-lookup"><span data-stu-id="5640f-183">4503599627370496</span></span>  |
| <span data-ttu-id="5640f-184">AuditSuccess</span><span class="sxs-lookup"><span data-stu-id="5640f-184">AuditSuccess</span></span>     | <span data-ttu-id="5640f-185">9007199254740992</span><span class="sxs-lookup"><span data-stu-id="5640f-185">9007199254740992</span></span>  |
| <span data-ttu-id="5640f-186">CorrelationHint2</span><span class="sxs-lookup"><span data-stu-id="5640f-186">CorrelationHint2</span></span> | <span data-ttu-id="5640f-187">18014398509481984</span><span class="sxs-lookup"><span data-stu-id="5640f-187">18014398509481984</span></span> |
| <span data-ttu-id="5640f-188">EventLogClassic</span><span class="sxs-lookup"><span data-stu-id="5640f-188">EventLogClassic</span></span>  | <span data-ttu-id="5640f-189">36028797018963968</span><span class="sxs-lookup"><span data-stu-id="5640f-189">36028797018963968</span></span> |
| <span data-ttu-id="5640f-190">Sqm</span><span class="sxs-lookup"><span data-stu-id="5640f-190">Sqm</span></span>              | <span data-ttu-id="5640f-191">2251799813685248</span><span class="sxs-lookup"><span data-stu-id="5640f-191">2251799813685248</span></span>  |
| <span data-ttu-id="5640f-192">WdiDiagnostic</span><span class="sxs-lookup"><span data-stu-id="5640f-192">WdiDiagnostic</span></span>    | <span data-ttu-id="5640f-193">1125899906842624</span><span class="sxs-lookup"><span data-stu-id="5640f-193">1125899906842624</span></span>  |
| <span data-ttu-id="5640f-194">WdiContext</span><span class="sxs-lookup"><span data-stu-id="5640f-194">WdiContext</span></span>       | <span data-ttu-id="5640f-195">562949953421312</span><span class="sxs-lookup"><span data-stu-id="5640f-195">562949953421312</span></span>   |
| <span data-ttu-id="5640f-196">ResponseTime</span><span class="sxs-lookup"><span data-stu-id="5640f-196">ResponseTime</span></span>     | <span data-ttu-id="5640f-197">281474976710656</span><span class="sxs-lookup"><span data-stu-id="5640f-197">281474976710656</span></span>   |
| <span data-ttu-id="5640f-198">None</span><span class="sxs-lookup"><span data-stu-id="5640f-198">None</span></span>             | <span data-ttu-id="5640f-199">0</span><span class="sxs-lookup"><span data-stu-id="5640f-199">0</span></span>                 |

<span data-ttu-id="5640f-200">ハッシュ テーブルを更新し、キー **Keywords** と **EventLogClassic** の列挙値 **36028797018963968** を使った**キー/値**のペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="5640f-200">Update the hash table and include the **key/value** pair with the key, **Keywords**, and the **EventLogClassic** enumeration value, **36028797018963968**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
}
```

#### <a name="keywords-static-property-value-optional"></a><span data-ttu-id="5640f-201">Keywords の静的プロパティ値 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="5640f-201">Keywords static property value (optional)</span></span>

<span data-ttu-id="5640f-202">**Keywords** キーは列挙されますが、ハッシュ テーブルのクエリで静的なプロパティ名を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="5640f-202">The **Keywords** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="5640f-203">返される文字列を使うのではなく、**Value__** プロパティを含む値にプロパティ名を変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5640f-203">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="5640f-204">たとえば、次のスクリプトでは **Value__** プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="5640f-204">For example, the following script uses the **Value__** property.</span></span>

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventKeywords]::EventLogClassic
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=$C.Value__
}
```

### <a name="filtering-by-event-id"></a><span data-ttu-id="5640f-205">イベント ID でのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="5640f-205">Filtering by Event Id</span></span>

<span data-ttu-id="5640f-206">より具体的なデータを取得するために、クエリの結果を**イベント ID** でフィルター処理します。**イベント ID** は、ハッシュ テーブルではキー **ID** として参照され、その値は特定の**イベント ID** です。**イベント ID** は **[Windows イベント ビューアー]** で表示されます。この例では、**イベント ID 1023** を使います。</span><span class="sxs-lookup"><span data-stu-id="5640f-206">To get more specific data, the query's results are filtered by **Event Id**. The **Event Id** is referenced in the hash table as the key **ID** and the value is a specific **Event Id**. The **Windows Event Viewer** displays the **Event Id**. This example uses **Event Id 1023**.</span></span>

<span data-ttu-id="5640f-207">ハッシュ テーブルを更新して、キーが **ID**、値が **1023** である**キー/値**のペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="5640f-207">Update the hash table and include the **key/value** pair with the key, **ID** and the value, **1023**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
}
```

### <a name="filtering-by-level"></a><span data-ttu-id="5640f-208">レベルでのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="5640f-208">Filtering by Level</span></span>

<span data-ttu-id="5640f-209">さらに結果を絞り込み、エラーであるイベントのみを含むようにするために、**Level** キーを使います。</span><span class="sxs-lookup"><span data-stu-id="5640f-209">To further refine the results and include only events that are errors, use the **Level** key.</span></span>
<span data-ttu-id="5640f-210">**[Windows イベント ビューアー]** では文字列値として **Level** が表示されますが、それらは列挙値です。</span><span class="sxs-lookup"><span data-stu-id="5640f-210">**Windows Event Viewer** displays the **Level** as string values, but they are enumerated values.</span></span> <span data-ttu-id="5640f-211">ハッシュ テーブルでは、文字列値と共に **Level** キーを使うと、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5640f-211">In the hash table, if you use the **Level** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="5640f-212">**Level** は **Error**、**Warning**、または **Informational** などの値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="5640f-212">**Level** has values such as **Error**, **Warning**, or **Informational**.</span></span> <span data-ttu-id="5640f-213">次のコマンドを使って、`StandardEventLevel` プロパティの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="5640f-213">Use the following command to display the `StandardEventLevel` property names.</span></span>

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

<span data-ttu-id="5640f-214">列挙値は **.NET Framework** でドキュメント化されています。</span><span class="sxs-lookup"><span data-stu-id="5640f-214">The enumerated values are documented in the **.NET Framework**.</span></span> <span data-ttu-id="5640f-215">詳細については、[StandardEventLevel 列挙型](https://docs.microsoft.com/en-us/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel?redirectedfrom=MSDN&view=netframework-4.7.2)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5640f-215">For more information, see [StandardEventLevel Enumeration](https://docs.microsoft.com/en-us/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel?redirectedfrom=MSDN&view=netframework-4.7.2).</span></span>

<span data-ttu-id="5640f-216">**Level** キーの名前と列挙値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5640f-216">The **Level** key's names and enumerated values are as follows:</span></span>

| <span data-ttu-id="5640f-217">名前</span><span class="sxs-lookup"><span data-stu-id="5640f-217">Name</span></span>           | <span data-ttu-id="5640f-218">値</span><span class="sxs-lookup"><span data-stu-id="5640f-218">Value</span></span> |
| -------------- | ----- |
| <span data-ttu-id="5640f-219">Verbose</span><span class="sxs-lookup"><span data-stu-id="5640f-219">Verbose</span></span>        |   <span data-ttu-id="5640f-220">5</span><span class="sxs-lookup"><span data-stu-id="5640f-220">5</span></span>   |
| <span data-ttu-id="5640f-221">［情報］</span><span class="sxs-lookup"><span data-stu-id="5640f-221">Informational</span></span>  |   <span data-ttu-id="5640f-222">4</span><span class="sxs-lookup"><span data-stu-id="5640f-222">4</span></span>   |
| <span data-ttu-id="5640f-223">警告</span><span class="sxs-lookup"><span data-stu-id="5640f-223">Warning</span></span>        |   <span data-ttu-id="5640f-224">3</span><span class="sxs-lookup"><span data-stu-id="5640f-224">3</span></span>   |
| <span data-ttu-id="5640f-225">エラー</span><span class="sxs-lookup"><span data-stu-id="5640f-225">Error</span></span>          |   <span data-ttu-id="5640f-226">2</span><span class="sxs-lookup"><span data-stu-id="5640f-226">2</span></span>   |
| <span data-ttu-id="5640f-227">［重大］</span><span class="sxs-lookup"><span data-stu-id="5640f-227">Critical</span></span>       |   <span data-ttu-id="5640f-228">1 で保護されたプロセスとして起動されました</span><span class="sxs-lookup"><span data-stu-id="5640f-228">1</span></span>   |
| <span data-ttu-id="5640f-229">LogAlways</span><span class="sxs-lookup"><span data-stu-id="5640f-229">LogAlways</span></span>      |   <span data-ttu-id="5640f-230">0</span><span class="sxs-lookup"><span data-stu-id="5640f-230">0</span></span>   |

<span data-ttu-id="5640f-231">完成したクエリのハッシュ テーブルには、キー **Level** と値 **2** が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5640f-231">The hash table for the completed query includes the key, **Level**, and the value, **2**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=2
}
```

#### <a name="level-static-property-in-enumeration-optional"></a><span data-ttu-id="5640f-232">列挙型の Level の静的プロパティ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="5640f-232">Level static property in enumeration (optional)</span></span>

<span data-ttu-id="5640f-233">**Level** キーは列挙されますが、ハッシュ テーブルのクエリで静的なプロパティ名を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="5640f-233">The **Level** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="5640f-234">返される文字列を使うのではなく、**Value__** プロパティを含む値にプロパティ名を変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5640f-234">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="5640f-235">たとえば、次のスクリプトでは **Value__** プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="5640f-235">For example, the following script uses the **Value__** property.</span></span>

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