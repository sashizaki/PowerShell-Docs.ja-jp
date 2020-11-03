---
description: WMI Query Language (WQL) について説明します。これは Windows PowerShell で WMI オブジェクトを取得するために使用できます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223187"
---
# <a name="about-wql"></a>WQL の概要

## <a name="short-description"></a>概要

WMI Query Language (WQL) について説明します。これは Windows PowerShell で WMI オブジェクトを取得するために使用できます。

## <a name="long-description"></a>詳細説明

WQL は Windows Management Instrumentation (WMI) クエリ言語であり、WMI から情報を取得するために使用される言語です。

Windows PowerShell で WMI クエリを実行するために WQL を使用する必要はありません。
代わりに、Get-WmiObject または Get-CimInstance コマンドレットのパラメーターを使用できます。 WQL クエリは、標準 Get-WmiObject コマンドよりも少し高速で、コマンドが何百ものシステムで実行された場合にパフォーマンスが向上します。 ただし、正常に実行された WQL クエリを作成するのにかかる時間は、パフォーマンスの向上を上回ることはありません。

WQL を使用するために必要な基本的な WQL ステートメントは、Select、Where、From です。

## <a name="when-to-use-wql"></a>WQL を使用する場合

WMI を使用する場合、特に WQL を使用する場合は、Windows PowerShell も使用していることを忘れないでください。 多くの場合、WQL クエリが想定どおりに動作しない場合は、WQL クエリをデバッグするよりも、標準の Windows PowerShell コマンドを使用する方が簡単です。

帯域幅が制限されたリモートシステムから膨大な量のデータを返す場合を除き、同じことを実行する Windows コマンドレットが非常に遅い場合は、時間をかけて複雑で複雑な WQL クエリを作成することはほとんどありません。

## <a name="using-the-select-statement"></a>SELECT ステートメントの使用

一般的な WMI クエリは、WMI クラスのすべてのプロパティまたは特定のプロパティを取得する Select ステートメントで始まります。 WMI クラスのすべてのプロパティを選択するには、アスタリスク () を使用し \* ます。 From キーワードは、WMI クラスを指定します。

Select ステートメントの形式は次のとおりです。

```
Select <property> from <WMI-class>
```

たとえば、次の Select ステートメントでは、Win32_Bios WMI クラスのインスタンスからすべてのプロパティ (*) を選択します。

```
Select * from Win32_Bios
```

WMI クラスの特定のプロパティを選択するには、Select キーワードと From キーワードの間にプロパティ名を指定します。

次のクエリでは、Win32_Bios WMI クラスから BIOS の名前のみを選択します。 このコマンドは、クエリを $queryName 変数に保存します。

```
Select Name from Win32_Bios
```

複数のプロパティを選択するには、コンマを使用してプロパティ名を区切ります。
次の WMI クエリでは、Win32_Bios WMI クラスの名前とバージョンを選択します。 このコマンドは、クエリを $queryNameVersion 変数に保存します。

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a>WQL クエリの使用

Windows PowerShell コマンドで WQL クエリを使用するには、次の3つの方法があります。

- Get-WmiObject コマンドレットを使用する
- Get-CimInstance コマンドレットを使用する
- [Wmisearcher] 型アクセラレータを使用します。

## <a name="using-the-get-wmiobject-cmdlet"></a>GET-WMIOBJECT コマンドレットの使用

WQL クエリを使用する最も基本的な方法は、次の例に示すように、引用符で囲んで (文字列として) 引用符で囲み、Get-WmiObject コマンドレットのクエリパラメーターの値としてクエリ文字列を使用することです。

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

次のコマンドに示すように、WQL ステートメントを変数に保存し、その変数をクエリパラメーターの値として使用することもできます。

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

どちらの形式でも、任意の WQL ステートメントを使用できます。 次のコマンドでは、$queryName 変数のクエリを使用して、システム BIOS の name および version プロパティのみを取得します。

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

Get-WmiObject コマンドレットのパラメーターを使用して、同じ結果を得ることができることに注意してください。 たとえば、次のコマンドは、Win32_Bios WMI クラスのインスタンスの名前とバージョンプロパティの値も取得します。

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a>CIMINSTANCE コマンドレットの使用

Windows PowerShell 3.0 以降では、Get-CimInstance コマンドレットを使用して WQL クエリを実行できます。

Get-CimInstance は、WMI クラスを含む CIM 準拠クラスのインスタンスを取得します。 Windows PowerShell 3.0 で導入された CIM コマンドレットは、WMI コマンドレットと同じタスクを実行します。 CIM コマンドレットは、WS-Management (WSMan) 標準と Common Information Model (CIM) 標準に準拠しています。これにより、コマンドレットは、同じ手法を使用して、他のオペレーティングシステムを実行している Windows コンピューターとコンピューターを管理できます。

次のコマンドでは、Get-CimInstance コマンドレットを使用して、WQL クエリを実行します。

Get-WmiObject で使用できる WQL クエリは、CimInstance でも使用できます。

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Get-CimInstance によって返さ Get-WmiObject れる System.management.managementobject ではなく、CimInstance オブジェクトが返されますが、オブジェクトは非常に似ています。

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a>[Wmisearcher] 型アクセラレータを使用する

[Wmisearcher] 型アクセラレータは、WQL ステートメント文字列から ManagementObjectSearcher オブジェクトを作成します。 ManagementObjectSearcher オブジェクトには多くのプロパティとメソッドがありますが、最も基本的な方法は Get メソッドです。このメソッドは、指定された WMI クエリを呼び出し、結果として得られるオブジェクトを返します。

[Wmisearcher] を使用すると、ManagementObjectSearcher .NET Framework クラスに簡単にアクセスできます。 これにより、WMI に対してクエリを実行し、クエリの実行方法を構成できます。

[Wmisearcher] 型アクセラレータを使用するには、次のように入力します。

1. WQL 文字列を ManagementObjectSearcher オブジェクトにキャストします。
2. ManagementObjectSearcher オブジェクトの Get メソッドを呼び出します。

たとえば、次のコマンドは、"select all" クエリをキャストし、その結果を $bios 変数に保存してから、$bios 変数で ManagementObjectSearcher オブジェクトの Get メソッドを呼び出します。

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

注: 既定では、選択したオブジェクトのプロパティのみが表示されます。 これらのプロパティは、Types.ps1xml ファイルで定義されています。

[Wmisearcher] 型アクセラレータを使用して、クエリまたは変数をキャストできます。 次の例では、変数をキャストするために、[wmisearcher] 型 accelerator が使用されています。 結果は同じです。

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

次のコマンドに示すように、[wmisearcher] 型アクセラレータを使用すると、クエリ文字列が ManagementObjectSearcher オブジェクトに変更されます。

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

このコマンド形式は、任意のクエリで動作します。 次のコマンドは、Win32_Bios WMI クラスの Name プロパティの値を取得します。

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

この操作は1つのコマンドで実行できますが、コマンドの解釈は少し難しくなります。

この形式では、[wmisearcher] 型アクセラレータを使用して WQL クエリ文字列を ManagementObjectSearcher にキャストし、オブジェクトの Get メソッドを1つのコマンドで呼び出します。 キャストされた文字列を囲むかっこ () は、メソッドを呼び出す前に文字列をキャストするように指示します。

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a>基本的な WQL WHERE ステートメントの使用

Where ステートメントは、Select ステートメントによって返されるデータの条件を確立します。

Where ステートメントの形式は次のとおりです。

```
where <property> <operator> <value>
```

次に例を示します。

```
where Name = 'Notepad.exe'
```

Where ステートメントは、次の例に示すように、Select ステートメントと共に使用します。

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

Where ステートメントを使用する場合は、プロパティの名前と値が正確である必要があります。

たとえば、次のコマンドは、ローカルコンピューター上のメモ帳プロセスを取得します。

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

ただし、次のコマンドは失敗します。これは、プロセス名に ".exe" ファイル名拡張子が含まれているためです。

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a>WHERE ステートメントの比較演算子

次の演算子は、WQL の Where ステートメントで有効です。

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

他にも演算子はありますが、これらは比較を行うために使用されるものです。

たとえば、次のクエリでは、Win32_Process クラスのプロセスから、プロセスの優先度が11以上の名前と優先度のプロパティが選択されます。 Get-WmiObject コマンドレットは、クエリを実行します。

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a>FILTER パラメーターでの WQL 演算子の使用

WQL 演算子は、これらのコマンドレットのクエリパラメーターの値に加えて、Get-WmiObject または Get-CimInstance コマンドレットの Filter パラメーターの値で使用することもできます。

たとえば、次のコマンドは、ProcessID 値が1004より大きい最後の5つのプロセスの名前と ProcessID プロパティを取得します。 このコマンドは、Filter パラメーターを使用して、ProcessID 条件を指定します。

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a>LIKE 演算子の使用

Like 演算子を使用すると、ワイルドカード文字を使用して WQL クエリの結果をフィルター処理できます。

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

Like 演算子をワイルドカード文字または範囲演算子なしで使用すると、等値演算子 (=) と同様に動作し、パターンと完全に一致する場合にのみオブジェクトが返されます。

範囲演算とパーセントワイルドカード文字を組み合わせて、シンプルで、かつ強力なフィルターを作成できます。

### <a name="like-operator-examples"></a>LIKE 演算子の例

#### <a name="example-1-range"></a>例 1: [ \<range> ]

次のコマンドは、メモ帳を起動してから、"H" から "N" までの文字で始まる名前を持つ Win32_Process クラスのインスタンスを検索します (大文字と小文字は区別されません)。

クエリは、Hotpad.exe から Notepad.exe までのプロセスを返します。

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a>例 2: [ \<range> ] および%

次のコマンドでは、A と P (大文字と小文字は区別されません) の間に文字で始まる名前を持つすべてのプロセスを選択し、その後に任意の組み合わせで0個以上の文字を続けます。

Get-WmiObject コマンドレットはクエリを実行し、Select-Object コマンドレットは Name および ProcessID プロパティを取得します。 Sort-Object コマンドレットは、結果を名前順にアルファベット順に並べ替えます。

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a>例 3: 範囲内にありません (^)

次のコマンドは、名前の先頭に次の文字が含まれていないプロセスを取得します。 A、S、W、P、R、C、U、N

の後に0個以上の文字が続きます。

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a>例 4: 任意の文字--または none (%)

次のコマンドは、名前が "calc" で始まるプロセスを取得します。
WQL の% 記号は、 \* 正規表現のアスタリスク () 記号に相当します。

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a>例 5: 1 文字 (_)

次のコマンドは、"c_lc.exe" というパターンの名前を持つプロセスを取得します。この場合、アンダースコア文字は任意の1文字を表します。 このパターンは、calc.exe から czlc.exe または c9lc.exe の任意の名前と一致しますが、"c" と "l" が複数の文字で区切られている名前とは一致しません。

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a>例 6: 完全一致

次のコマンドは、WLIDSVC.exe という名前のプロセスを取得します。 クエリで Like キーワードを使用している場合でも、値にはワイルドカード文字が含まれないため、完全一致が必要です。

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a>OR 演算子の使用

複数の独立した条件を指定するには、またはキーワードを使用します。 Where 句にまたはキーワードが表示されます。 2つ (以上) の条件に対して包括的 OR 演算を実行し、任意の条件を満たす項目を返します。

Or 演算子の形式は次のとおりです。

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

たとえば、次のコマンドは、Win32_Process WMI クラスのすべてのインスタンスを取得しますが、プロセス名が winword.exe または excel.exe の場合にのみそれらを返します。

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

ステートメントまたはステートメントは、3つ以上の条件で使用できます。 次のクエリでは、またはステートメントが Winword.exe、Excel.exe、または Powershell.exe を取得します。

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a>AND 演算子の使用

複数の関連する条件を指定するには、キーワードとキーワードを使用します。 Where 句にとキーワードが表示されます。 すべての条件を満たす項目が返されます。

And 演算子の形式は次のとおりです。

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

たとえば、次のコマンドは、名前が "Winword.exe" でプロセス ID が6512のプロセスを取得します。

コマンドは Get-CimInstance コマンドレットを使用することに注意してください。

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

Like 演算子を含むすべての演算子は、Or 演算子および And 演算子と共に使用できます。 また、Or 演算子と And 演算子は、1つのクエリでは、最初に処理する句を Windows PowerShell に指示するかっこを使用して組み合わせることができます。

このコマンドは、Windows PowerShell の継続文字 (') を使用して、コマンドを2行に分割します。

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a>NULL 値の検索

WMI で null 値を検索することは困難です。これは、予期しない結果につながる可能性があるためです。 Null が0ではなく、または空の文字列でもありません。 一部の WMI クラスプロパティは初期化されていますが、そうでない場合、null を検索すると、すべてのプロパティに対して機能しない可能性があります。

Null 値を検索するには、値が "null" の Is 演算子を使用します。

たとえば、次のコマンドは、IntallDate プロパティに null 値を持つプロセスを取得します。 コマンドは多数のプロセスを返します。

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

これに対し、次のコマンドは、Description プロパティに null 値を持つユーザーアカウントを取得します。 このコマンドは、ほとんどのユーザーアカウントが Description プロパティの値を持たない場合でも、ユーザーアカウントを返しません。

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

Description プロパティの値がないユーザーアカウントを検索するには、等値演算子を使用して空の文字列を取得します。 空の文字列を表すには、2つの連続する単一引用符を使用します。

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a>TRUE または FALSE を使用する

WMI オブジェクトのプロパティでブール値を取得するには、True と False を使用します。
大文字と小文字は区別されません。

次の WQL クエリでは、ドメインに参加しているコンピューターからローカルユーザーアカウントのみが返されます。

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

ドメインアカウントを検索するには、次の例に示すように、False の値を使用します。

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a>エスケープ文字の使用

WQL では、 \) エスケープ文字として円記号を使用します。 これは、バックティック文字 (') を使用する Windows PowerShell とは異なります。

引用符や引用符に使用する文字は、誤って解釈されないようにエスケープする必要があります。

名前に単一引用符が含まれているユーザーを検索するには、次のコマンドに示すように、円記号を使用して単一引用符をエスケープします。

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

場合によっては、円記号もエスケープする必要があります。 たとえば、次のコマンドでは、キャプション値に円記号が含まれているため、無効なクエリエラーが生成されます。

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

バックスラッシュをエスケープするには、次のコマンドに示すように、2つ目の円記号を使用します。

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a>関連項目

[about_Special_Characters](about_Special_Characters.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_WMI](about_WMI.md)

[about_WMI_Cmdlets](about_WMI_Cmdlets.md)
