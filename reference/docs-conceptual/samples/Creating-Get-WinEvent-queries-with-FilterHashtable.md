---
ms.date: 09/13/2019
title: FilterHashtable を使った Get-WinEvent クエリの作成
ms.openlocfilehash: 35d18dc894d90e698b38395b79ff4cf395515909
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "73444394"
---
# <a name="creating-get-winevent-queries-with-filterhashtable"></a>FilterHashtable を使った Get-WinEvent クエリの作成

2014 年 6 月 3 日の元の **Scripting Guy** のブログ投稿をご覧になる場合は、「[Use FilterHashTable to Filter Event Log with PowerShell (PowerShell で FilterHashTable を使ってイベント ログをフィルター処理する)](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/)」を参照してください。

この記事は元のブログ投稿の抜粋です。`Get-WinEvent` コマンドレットの **FilterHashtable** パラメーターを使ってイベント ログをフィルター処理する方法について説明します。 PowerShell の `Get-WinEvent` コマンドレットは、Windows イベントと診断のログをフィルター処理するための強力な方法です。 `Get-WinEvent` クエリで **FilterHashtable** パラメーターを使うとパフォーマンスが向上します。

大規模なイベント ログを使用する場合、パイプラインを通して `Where-Object` コマンドにオブジェクトを送信するのは効率的ではありません。 PowerShell 6 以前では、`Get-EventLog` コマンドレットがログ データを取得するためのもう一つのオプションでした。 たとえば、**Microsoft-Windows-Defrag** ログをフィルター処理する場合、次のコマンドは効率的ではありません。

```powershell
Get-EventLog -LogName Application | Where-Object Source -Match defrag

Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'defrag' }
```

次のコマンドでは、パフォーマンスが向上するハッシュ テーブルを使っています。

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='*defrag'
}
```

## <a name="blog-posts-about-enumeration"></a>列挙体についてのブログ投稿

この記事では、ハッシュ テーブルで列挙値を使用する方法について説明します。 列挙体について詳しくは、これらの **Scripting Guy** のブログ投稿をご覧ください。 列挙値を返す関数を作成するには、「[Enumerations and Values (列挙型および値)](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values)」をご覧ください。
詳細については、[列挙体に関する Scripting Guy の一連のブログ投稿](https://devblogs.microsoft.com/scripting/?s=about+enumeration)をご覧ください。

## <a name="hash-table-key-value-pairs"></a>ハッシュ テーブルのキーと値のペア

効率的なクエリを作成するには、**FilterHashtable** パラメーターと共に `Get-WinEvent` コマンドレットを使います。
**FilterHashtable** には、Windows イベント ログから特定の情報を取得するためのフィルターとして、ハッシュ テーブルを指定できます。 ハッシュ テーブルでは、**キーと値**のペアを使用します。 ハッシュ テーブルの詳細については、「[about_Hash_Tables (ハッシュ テーブルについて)](/powershell/module/microsoft.powershell.core/about/about_hash_tables)」をご覧ください。

**キーと値**のペアが同じ行に存在する場合は、それらをセミコロンで区切る必要があります。 **キーと値**のペアがそれぞれ別々の行に存在する場合は、セミコロンは必要ありません。 たとえば、この記事では**キーと値**のペアを別々の行に置き、セミコロンは使用しません。

このサンプルでは、**FilterHashtable** パラメーターの**キーと値**のペアのいくつかを使用します。 完成したクエリには、**LogName**、**ProviderName**、**Keywords**、**ID**、および **Level** が含まれます。

適用できる**キーと値**のペアを次の表に示します。これらは、[Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable** パラメーターのドキュメントに含まれています。

キー名、データ型、およびデータ値に対してワイルドカード文字を指定できるかどうかを、次の表に示します。

|    キー名    | 値のデータ型 | ワイルドカード文字を指定できるか |
| -------------- | --------------- | ---------------------------- |
| LogName        | `<String[]>`    | はい                          |
| ProviderName   | `<String[]>`    | はい                          |
| Path           | `<String[]>`    | いいえ                           |
| Keywords       | `<Long[]>`      | いいえ                           |
| id             | `<Int32[]>`     | いいえ                           |
| Level          | `<Int32[]>`     | いいえ                           |
| StartTime      | `<DateTime>`    | いいえ                           |
| EndTime        | `<DateTime>`    | いいえ                           |
| UserID         | `<SID>`         | いいえ                           |
| Data           | `<String[]>`    | いいえ                           |
| `<named-data>` | `<String[]>`    | いいえ                           |

`<named-data>` キーは、名前付きイベント データ フィールドを表します。 たとえば、Perflib イベント 1008 には次のイベント データを含めることができます。

```xml
<EventData>
  <Data Name="Service">BITS</Data>
  <Data Name="Library">C:\Windows\System32\bitsperf.dll</Data>
  <Data Name="Win32Error">2</Data>
</EventData>
```

次のコマンドを利用し、これらのイベントに対してクエリを実行できます。

```powershell
Get-WinEvent -FilterHashtable @{LogName='Application'; 'Service'='Bits'}
```

> [!NOTE]
> PowerShell 6 では、`<named-data>` のクエリを実行する機能が追加されています。

## <a name="building-a-query-with-a-hash-table"></a>ハッシュ テーブルを使ったクエリの作成

結果を確認して問題をトラブルシューティングするため、一度に 1 つの**キーと値**のペアのハッシュ テーブルを作成すると役立ちます。 クエリでは、**アプリケーション** ログからデータを取得します。 ハッシュ テーブルは `Get-WinEvent –LogName Application` に相当します。

まず、`Get-WinEvent` クエリを作成します。 **FilterHashtable** パラメーターの**キーと値**のペアを使います。キーには **LogName** を、値には **Application** を指定します。

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
}
```

**ProviderName** キーを使ってハッシュ テーブルの作成を続けます。 **ProviderName** は、 **[Windows イベント ビューアー]** の **[ソース]** フィールドに表示される名前です。 たとえば、次のスクリーン ショットの **[.NET Runtime]\(.NET ランタイム\)** です。

![[Windows イベント ビューアー] のソースの画像。](./media/creating-get-winEvent-queries-with-filterhashtable/providername.png)

ハッシュ テーブルを更新して、キーが **ProviderName、値が **.NET Runtime** である**キーと値**のペアを含めます。

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
}
```

クエリで、アーカイブ済みのイベント ログからデータを取得する必要がある場合は、**Path** キーを使います。 **パス**の値でログ ファイルへの完全なパスを指定します。 詳細については、**Scripting Guy** のブログ投稿「[Use PowerShell to Parse Saved Event Logs for Errors (エラーのために、PowerShell を使って保存したイベント ログを解析する)](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors)」をご覧ください。

## <a name="using-enumerated-values-in-a-hash-table"></a>ハッシュ テーブルでの列挙値の使用

ハッシュ テーブルの次のキーは、**Keywords** です。 **Keywords** のデータ型は、大きい数を保持する値の型 `[long]` の配列です。 次のコマンドを使って `[long]` の最大値を検索します。

```powershell
[long]::MaxValue
```

```Output
9223372036854775807
```

PowerShell では、**Keywords** キーに対して、**Security** などの文字列ではなく数値を使います。 **[Windows イベント ビューアー]** では文字列として **Keywords** が表示されますが、それらは列挙値です。 ハッシュ テーブルでは、文字列値と共に **Keywords** キーを使うと、エラー メッセージが表示されます。

**[Windows イベント ビューアー]** を開き、 **[操作]** ウィンドウから **[現在のログをフィルター]** をクリックします。
次のスクリーン ショットに示すように、使用可能なキーワードが **[キーワード]** ドロップダウン メニューに表示されます。

![[Windows イベント ビューアー] のキーワードの画像。](./media/creating-get-winEvent-queries-with-filterhashtable/keywords.png)

次のコマンドを使って、`StandardEventKeywords` プロパティの名前を表示します。

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

列挙値は **.NET Framework** でドキュメント化されています。 詳細については、[StandardEventKeywords 列挙型](/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords?redirectedfrom=MSDN&view=netframework-4.7.2)に関するページをご覧ください。

**Keywords** の名前と列挙値は次のようになります。

| 名前             |  値            |
| ---------------- | ------------------|
| AuditFailure     | 4503599627370496  |
| AuditSuccess     | 9007199254740992  |
| CorrelationHint2 | 18014398509481984 |
| EventLogClassic  | 36028797018963968 |
| Sqm              | 2251799813685248  |
| WdiDiagnostic    | 1125899906842624  |
| WdiContext       | 562949953421312   |
| ResponseTime     | 281474976710656   |
| なし             | 0                 |

ハッシュ テーブルを更新し、キーが **Keywords**、**EventLogClassic** の列挙値が **36028797018963968** である**キーと値**のペアを含めます。

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
}
```

### <a name="keywords-static-property-value-optional"></a>Keywords の静的プロパティ値 (省略可能)

**Keywords** キーは列挙されますが、ハッシュ テーブルのクエリで静的なプロパティ名を使うことができます。
返される文字列を使うのではなく、**Value__** プロパティを含む値にプロパティ名を変換する必要があります。

たとえば、次のスクリプトでは **Value__** プロパティを使います。

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventKeywords]::EventLogClassic
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=$C.Value__
}
```

## <a name="filtering-by-event-id"></a>イベント ID でのフィルター処理

より具体的なデータを取得するために、クエリの結果を**イベント ID** でフィルター処理します。**イベント ID** は、ハッシュ テーブルではキー **ID** として参照され、その値は特定の**イベント ID** です。**イベント ID** は **[Windows イベント ビューアー]** で表示されます。この例では、**イベント ID 1023** を使います。

ハッシュ テーブルを更新して、キーが **ID**、値が **1023** である**キーと値**のペアを含めます。

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
}
```

## <a name="filtering-by-level"></a>レベルでのフィルター処理

さらに結果を絞り込み、エラーであるイベントのみを含むようにするために、**Level** キーを使います。
**[Windows イベント ビューアー]** では文字列値として **Level** が表示されますが、それらは列挙値です。 ハッシュ テーブルでは、文字列値と共に **Level** キーを使うと、エラー メッセージが表示されます。

**Level** は **Error**、**Warning**、または **Informational** などの値を持ちます。 次のコマンドを使って、`StandardEventLevel` プロパティの名前を表示します。

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

列挙値は **.NET Framework** でドキュメント化されています。 詳細については、[StandardEventLevel 列挙型](/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel?redirectedfrom=MSDN&view=netframework-4.7.2)に関するページをご覧ください。

**Level** キーの名前と列挙値は次のようになります。

| 名前           | 値 |
| -------------- | ----- |
| "詳細"        |   5   |
| Informational  |   4   |
| 警告        |   3   |
| エラー          |   2   |
| Critical       |   1   |
| LogAlways      |   0   |

完成したクエリのハッシュ テーブルには、キー **Level** と値 **2** が含まれています。

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=2
}
```

### <a name="level-static-property-in-enumeration-optional"></a>列挙型の Level の静的プロパティ (省略可能)

**Level** キーは列挙されますが、ハッシュ テーブルのクエリで静的なプロパティ名を使うことができます。
返される文字列を使うのではなく、**Value__** プロパティを含む値にプロパティ名を変換する必要があります。

たとえば、次のスクリプトでは **Value__** プロパティを使います。

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