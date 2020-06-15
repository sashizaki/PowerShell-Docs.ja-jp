---
title: 書式設定、エイリアス、プロバイダー、比較
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: eb23b048a50f10ea83d156c0499772b1be439336
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438003"
---
# <a name="chapter-5---formatting-aliases-providers-comparison"></a><span data-ttu-id="f2575-102">第 5 章 - 書式設定、エイリアス、プロバイダー、比較</span><span class="sxs-lookup"><span data-stu-id="f2575-102">Chapter 5 - Formatting, aliases, providers, comparison</span></span>

## <a name="requirements"></a><span data-ttu-id="f2575-103">必要条件</span><span class="sxs-lookup"><span data-stu-id="f2575-103">Requirements</span></span>

<span data-ttu-id="f2575-104">この章で紹介する例の中には、SQL Server PowerShell モジュールを必要とするものがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="f2575-104">The SQL Server PowerShell module is required by some of the examples shown in this chapter.</span></span> <span data-ttu-id="f2575-105">このモジュールは、[SQL Server Management Studio (SSMS)][SMSS] の一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f2575-105">The module installs as part of [SQL Server Management Studio (SMSS)][SMSS].</span></span> <span data-ttu-id="f2575-106">このモジュールは、以降の章でも使用されるので、</span><span class="sxs-lookup"><span data-stu-id="f2575-106">It's also used in subsequent chapters.</span></span> <span data-ttu-id="f2575-107">Windows 10 ラボ環境のコンピューターにダウンロードし、インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="f2575-107">Download and install it on your Windows 10 lab environment computer.</span></span>

## <a name="format-right"></a><span data-ttu-id="f2575-108">右で書式設定</span><span class="sxs-lookup"><span data-stu-id="f2575-108">Format Right</span></span>

<span data-ttu-id="f2575-109">第 4 章では、できるだけ左端でフィルター処理する方法について学習しました。</span><span class="sxs-lookup"><span data-stu-id="f2575-109">In Chapter 4, you learned to filter as far to the left as possible.</span></span> <span data-ttu-id="f2575-110">コマンドの出力を手動で書式設定するためのルールは、このルールに似ています (できるだけ右で実行する必要がある場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="f2575-110">The rule for manually formatting a command's output is similar to that rule except it needs to occur as far to the right as possible.</span></span>

<span data-ttu-id="f2575-111">最も一般的な書式設定コマンドは `Format-Table` と `Format-List` です。</span><span class="sxs-lookup"><span data-stu-id="f2575-111">The most common format commands are `Format-Table` and `Format-List`.</span></span> <span data-ttu-id="f2575-112">`Format-Wide` と `Format-Custom` を使用することもできますが、あまり一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="f2575-112">`Format-Wide` and `Format-Custom` can also be used, but are less common.</span></span>

<span data-ttu-id="f2575-113">第 3 章で説明したように、カスタム書式設定を使用しない限り、4 つを超えるプロパティを返すコマンドは既定でリストになります。</span><span class="sxs-lookup"><span data-stu-id="f2575-113">As mentioned in Chapter 3, a command that returns more than four properties defaults to a list unless custom formatting is used.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can*
```

```Output
Status              : Running
DisplayName         : Windows Time
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
```

<span data-ttu-id="f2575-114">`Format-Table` コマンドレットを使用して書式設定を手動でオーバーライドし、リストではなくテーブルに出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2575-114">Use the `Format-Table` cmdlet to manually override the formatting and show the output in a table instead of a list.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can* |
Format-Table
```

```Output
 Status DisplayName  CanPauseAndContinue CanShutdown CanStop
 ------ -----------  ------------------- ----------- -------
Running Windows Time               False        True    True
```

<span data-ttu-id="f2575-115">`Get-Service` の既定の出力は、テーブル内の 3 つのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="f2575-115">The default output for `Get-Service` is three properties in a table.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="f2575-116">`Format-List` コマンドレットを使用して既定の書式設定をオーバーライドし、結果をリストで返します。</span><span class="sxs-lookup"><span data-stu-id="f2575-116">Use the `Format-List` cmdlet to override the default formatting and return the results in a list.</span></span>

```powershell
Get-Service -Name w32time | Format-List
```

```Output
Name                : w32time
DisplayName         : Windows Time
Status              : Running
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
ServiceType         : Win32ShareProcess
```

<span data-ttu-id="f2575-117">`Get-Service` を `Format-List` にパイプ処理するだけで、追加のプロパティが返されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f2575-117">Notice that simply piping `Get-Service` to `Format-List` made it return additional properties.</span></span> <span data-ttu-id="f2575-118">その特定のコマンドについては書式設定がバックグラウンドで行われるため、これはすべてのコマンドで発生するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="f2575-118">This doesn't occur with every command because of the way the formatting for that particular command is set up behind the scenes.</span></span>

<span data-ttu-id="f2575-119">書式設定コマンドレットを使うときに最も注意しなければならないのは、このコマンドレットによって生成される書式設定オブジェクトは、PowerShell の通常のオブジェクトと異なるという点です。</span><span class="sxs-lookup"><span data-stu-id="f2575-119">The number one thing to be aware of with the format cmdlets is they produce format objects that are different than normal objects in PowerShell.</span></span>

```powershell
Get-Service -Name w32time | Format-List | Get-Member
```

```Output
   TypeName: Microsoft.PowerShell.Commands.Internal.Format.FormatStartData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
autosizeInfo                            Property   Microsoft.PowerShell.Commands.Inter...
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...
pageFooterEntry                         Property   Microsoft.PowerShell.Commands.Inter...
pageHeaderEntry                         Property   Microsoft.PowerShell.Commands.Inter...
shapeInfo                               Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.GroupStartData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...
shapeInfo                               Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.FormatEntryData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
formatEntryInfo                         Property   Microsoft.PowerShell.Commands.Inter...
outOfBand                               Property   bool outOfBand {get;set;}
writeStream                             Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.GroupEndData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...

   TypeName: Microsoft.PowerShell.Commands.Internal.Format.FormatEndData

Name                                    MemberType Definition
----                                    ---------- ----------
Equals                                  Method     bool Equals(System.Object obj)
GetHashCode                             Method     int GetHashCode()
GetType                                 Method     type GetType()
ToString                                Method     string ToString()
ClassId2e4f51ef21dd47e99d3c952918aff9cd Property   string ClassId2e4f51ef21dd47e99d3c9...
groupingEntry                           Property   Microsoft.PowerShell.Commands.Inter...
```

<span data-ttu-id="f2575-120">つまり、書式設定コマンドのパイプ処理の対象となるコマンドは、それほどありません。</span><span class="sxs-lookup"><span data-stu-id="f2575-120">What this means is format commands can't be piped to most other commands.</span></span> <span data-ttu-id="f2575-121">一部の `Out-*` コマンドに対してはパイプ処理できますが、それが限度です。</span><span class="sxs-lookup"><span data-stu-id="f2575-121">They can be piped to some of the `Out-*` commands, but that's about it.</span></span> <span data-ttu-id="f2575-122">行の最後で書式設定 (右で書式設定) する必要があるのは、そのためです。</span><span class="sxs-lookup"><span data-stu-id="f2575-122">This is why you want to perform any formatting at the very end of the line (format right).</span></span>

## <a name="aliases"></a><span data-ttu-id="f2575-123">エイリアス</span><span class="sxs-lookup"><span data-stu-id="f2575-123">Aliases</span></span>

<span data-ttu-id="f2575-124">PowerShell のエイリアスは、短いコマンド名です。</span><span class="sxs-lookup"><span data-stu-id="f2575-124">An alias in PowerShell is a shorter name for a command.</span></span> <span data-ttu-id="f2575-125">PowerShell には、一連の組み込みエイリアスが含まれていますが、独自のエイリアスを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2575-125">PowerShell includes a set of built-in aliases and you can also define your own aliases.</span></span>

<span data-ttu-id="f2575-126">`Get-Alias` コマンドレットは、エイリアスを見つけるときに使用します。</span><span class="sxs-lookup"><span data-stu-id="f2575-126">The `Get-Alias` cmdlet is used to find aliases.</span></span> <span data-ttu-id="f2575-127">コマンドのエイリアスが既にわかっている場合は、**Name** パラメーターを使用して、エイリアスが関連付けられているコマンドを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2575-127">If you already know the alias for a command, the **Name** parameter is used to determine what command the alias is associated with.</span></span>

```powershell
Get-Alias -Name gcm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
```

<span data-ttu-id="f2575-128">**Name** パラメーターの値には、複数のエイリアスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f2575-128">Multiple aliases can be specified for the value of the **Name** parameter.</span></span>

```powershell
Get-Alias -Name gcm, gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="f2575-129">**Name** パラメーターは位置指定パラメーターであるため、省略されていることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="f2575-129">You'll often see the **Name** parameter omitted since it's a positional parameter.</span></span>

```powershell
Get-Alias gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gm -> Get-Member
```

<span data-ttu-id="f2575-130">コマンドのエイリアスを検索する場合は、**Definition** パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2575-130">If you want to find aliases for a command, you'll need to use the **Definition** parameter.</span></span>

```powershell
Get-Alias -Definition Get-Command, Get-Member
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="f2575-131">**Definition** パラメーターは位置指定には使用できないため、必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2575-131">The **Definition** parameter can't be used positionally so it must be specified.</span></span>

<span data-ttu-id="f2575-132">エイリアスを使用すると、キーストロークをいくつか省略できるため、コンソールにコマンドを入力するときは便利です。</span><span class="sxs-lookup"><span data-stu-id="f2575-132">Aliases can save you a few keystrokes and they're fine when you're typing commands into the console.</span></span>
<span data-ttu-id="f2575-133">このエイリアスは、保存するスクリプトや他のユーザーと共有するコードでは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f2575-133">They shouldn't be used in scripts or any code that you're saving or sharing with others.</span></span> <span data-ttu-id="f2575-134">本書で前述したように、完全なコマンドレットとパラメーター名を使用すると自己文書化されるため、理解しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f2575-134">As mentioned earlier in this book, using full cmdlet and parameter names is self-documenting and easier to understand.</span></span>

<span data-ttu-id="f2575-135">独自のエイリアスは、お使いのコンピューター上の現在の PowerShell セッションにしか存在しないため、作成するときは注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="f2575-135">Use caution when creating your own aliases because they'll only exist in your current PowerShell session on your computer.</span></span>

## <a name="providers"></a><span data-ttu-id="f2575-136">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f2575-136">Providers</span></span>

<span data-ttu-id="f2575-137">PowerShell のプロバイダーは、データストアに、ファイル システムのようにアクセスできるようにするインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="f2575-137">A provider in PowerShell is an interface that allows file system like access to a datastore.</span></span> <span data-ttu-id="f2575-138">PowerShell には、組み込みプロバイダーが複数用意されています。</span><span class="sxs-lookup"><span data-stu-id="f2575-138">There are a number of built-in providers in PowerShell.</span></span>

```powershell
Get-PSProvider
```

```Output
Name                 Capabilities                       Drives
----                 ------------                       ------
Registry             ShouldProcess, Transactions        {HKLM, HKCU}
Alias                ShouldProcess                      {Alias}
Environment          ShouldProcess                      {Env}
FileSystem           Filter, ShouldProcess, Credentials {C, A, D}
Function             ShouldProcess                      {Function}
Variable             ShouldProcess                      {Variable}
Certificate          ShouldProcess                      {Cert}
WSMan                Credentials                        {WSMan}
```

<span data-ttu-id="f2575-139">上記の結果が示すように、レジストリ、エイリアス、環境変数、ファイル システム、関数、変数、証明書、および WSMan に対して、組み込みプロバイダーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f2575-139">As you can see in the previous results, there are built-in providers for the registry, aliases, environment variables, the file system, functions, variables, certificates, and WSMan.</span></span>

<span data-ttu-id="f2575-140">これらのプロバイダーがデータストアの公開に使用する実際のドライブは、`Get-PSDrive` コマンドレットを使って確認できます。</span><span class="sxs-lookup"><span data-stu-id="f2575-140">The actual drives that these providers use to expose their datastore can be determined with the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="f2575-141">`Get-PSDrive` コマンドレットによって表示されるのは、プロバイダーが公開しているドライブだけではありません。ネットワーク共有にマップされたドライブなど、Windows 論理ドライブも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2575-141">The `Get-PSDrive` cmdlet not only displays drives exposed by providers, but it also displays Windows logical drives including drives mapped to network shares.</span></span>

```powershell
Get-PSDrive
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                      FileSystem    A:\
Alias                                  Alias
C                  14.41        112.10 FileSystem    C:\
Cert                                   Certificate   \
D                                      FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
WSMan                                  WSMan
```

<span data-ttu-id="f2575-142">Active Directory PowerShell モジュール、SQLServer PowerShell モジュールといったサードパーティ モジュールそれぞれによって、独自の PowerShell プロバイダーと PSDrive が追加されます。</span><span class="sxs-lookup"><span data-stu-id="f2575-142">Third-party modules such as the Active Directory PowerShell module and the SQLServer PowerShell module both add their own PowerShell provider and PSDrive.</span></span>

<span data-ttu-id="f2575-143">Active Directory PowerShell モジュールと SQL Server PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f2575-143">Import the Active Directory and SQL Server PowerShell modules.</span></span>

```powershell
Import-Module -Name ActiveDirectory, SQLServer
```

<span data-ttu-id="f2575-144">追加 PowerShell プロバイダーが追加されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2575-144">Check to see if any additional PowerShell providers were added.</span></span>

```powershell
Get-PSProvider
```

```Output
Name                 Capabilities                       Drives
----                 ------------                       ------
Registry             ShouldProcess, Transactions        {HKLM, HKCU}
Alias                ShouldProcess                      {Alias}
Environment          ShouldProcess                      {Env}
FileSystem           Filter, ShouldProcess, Credentials {C, A, D}
Function             ShouldProcess                      {Function}
Variable             ShouldProcess                      {Variable}
ActiveDirectory      Include, Exclude, Filter, Shoul... {AD}
SqlServer            Credentials                        {SQLSERVER}
```

<span data-ttu-id="f2575-145">この結果セットでは、2 つの PowerShell プロバイダーが新しく存在していることに注意してください。1 つは Active Directory 用、もう 1 つは SQL Server 用のプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="f2575-145">Notice that in the previous set of results, two new PowerShell providers now exist, one for Active Directory and another one for SQL Server.</span></span>

<span data-ttu-id="f2575-146">各モジュールの PSDrive も追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2575-146">A PSDrive for each of those modules was also added.</span></span>

```powershell
Get-PSDrive
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                      FileSystem    A:\
AD                                     ActiveDire... //RootDSE/
Alias                                  Alias
C                  19.38        107.13 FileSystem    C:\
Cert                                   Certificate   \
D                                      FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
SQLSERVER                              SqlServer     SQLSERVER:\
Variable                               Variable
WSMan                                  WSMan
```

<span data-ttu-id="f2575-147">PSDrives には、従来のファイル システムと同じようにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f2575-147">PSDrives can be accessed just like a traditional file system.</span></span>

```powershell
Get-ChildItem -Path Cert:\LocalMachine\CA
```

```Output
   PSParentPath: Microsoft.PowerShell.Security\Certificate::LocalMachine\CA

Thumbprint                                Subject
----------                                -------
FEE449EE0E3965A5246F000E87FDE2A065FD89D4  CN=Root Agency
D559A586669B08F46A30A133F8A9ED3D038E2EA8  OU=www.verisign.com/CPS Incorporated LIABI...
109F1CAED645BB78B3EA2B94C0697C740733031C  CN=Microsoft Windows Hardware Compatibility,...
```

## <a name="comparison-operators"></a><span data-ttu-id="f2575-148">比較演算子</span><span class="sxs-lookup"><span data-stu-id="f2575-148">Comparison Operators</span></span>

<span data-ttu-id="f2575-149">PowerShell には、値を比較したり、特定のパターンに一致する値を検索したりするときに使用する比較演算子が多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2575-149">PowerShell contains a number of comparison operators that are used to compare values or find values that match certain patterns.</span></span> <span data-ttu-id="f2575-150">表 5-1 は、PowerShell の比較演算子の一覧です。</span><span class="sxs-lookup"><span data-stu-id="f2575-150">Table 5-1 contains a list of comparison operators in PowerShell.</span></span>

|    <span data-ttu-id="f2575-151">演算子</span><span class="sxs-lookup"><span data-stu-id="f2575-151">Operator</span></span>    |                          <span data-ttu-id="f2575-152">定義</span><span class="sxs-lookup"><span data-stu-id="f2575-152">Definition</span></span>                          |
| -------------- | ------------------------------------------------------------ |
| `-eq`          | <span data-ttu-id="f2575-153">等しい</span><span class="sxs-lookup"><span data-stu-id="f2575-153">Equal to</span></span>                                                     |
| `-ne`          | <span data-ttu-id="f2575-154">等しくない</span><span class="sxs-lookup"><span data-stu-id="f2575-154">Not equal to</span></span>                                                 |
| `-gt`          | <span data-ttu-id="f2575-155">より大きい</span><span class="sxs-lookup"><span data-stu-id="f2575-155">Greater than</span></span>                                                 |
| `-ge`          | <span data-ttu-id="f2575-156">以上</span><span class="sxs-lookup"><span data-stu-id="f2575-156">Greater than or equal to</span></span>                                     |
| `-lt`          | <span data-ttu-id="f2575-157">より小さい</span><span class="sxs-lookup"><span data-stu-id="f2575-157">Less than</span></span>                                                    |
| `-le`          | <span data-ttu-id="f2575-158">以下</span><span class="sxs-lookup"><span data-stu-id="f2575-158">Less than or equal to</span></span>                                        |
| `-Like`        | <span data-ttu-id="f2575-159">`*` ワイルドカード文字を使用した一致</span><span class="sxs-lookup"><span data-stu-id="f2575-159">Match using the `*` wildcard character</span></span>                       |
| `-NotLike`     | <span data-ttu-id="f2575-160">`*` ワイルドカード文字を使用した不一致</span><span class="sxs-lookup"><span data-stu-id="f2575-160">Does not match using the `*` wildcard character</span></span>              |
| `-Match`       | <span data-ttu-id="f2575-161">指定した正規表現と一致</span><span class="sxs-lookup"><span data-stu-id="f2575-161">Matches the specified regular expression</span></span>                     |
| `-NotMatch`    | <span data-ttu-id="f2575-162">指定した正規表現と一致しない</span><span class="sxs-lookup"><span data-stu-id="f2575-162">Does not match the specified regular expression</span></span>              |
| `-Contains`    | <span data-ttu-id="f2575-163">コレクションに指定した値が含まれているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="f2575-163">Determines if a collection contains a specified value</span></span>        |
| `-NotContains` | <span data-ttu-id="f2575-164">コレクションに特定の値が含まれていないことを確認する</span><span class="sxs-lookup"><span data-stu-id="f2575-164">Determines if a collection does not contain a specific value</span></span> |
| `-In`          | <span data-ttu-id="f2575-165">指定した値がコレクションに存在するかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="f2575-165">Determines if a specified value is in a collection</span></span>           |
| `-NotIn`       | <span data-ttu-id="f2575-166">指定した値がコレクションに含まれていないことを確認する</span><span class="sxs-lookup"><span data-stu-id="f2575-166">Determines if a specified value is not in a collection</span></span>       |
| `-Replace`     | <span data-ttu-id="f2575-167">指定した値を置き換える</span><span class="sxs-lookup"><span data-stu-id="f2575-167">Replaces the specified value</span></span>                                 |

<span data-ttu-id="f2575-168">表 5-1 に記載されている演算子はすべて、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="f2575-168">All of the operators listed in Table 5-1 are case-insensitive.</span></span> <span data-ttu-id="f2575-169">大文字と小文字を区別するには、表 5-1 に示されている演算子の前に `c` を置きます。</span><span class="sxs-lookup"><span data-stu-id="f2575-169">Place a `c` in front of the operator listed in Table 5-1 to make it case-sensitive.</span></span> <span data-ttu-id="f2575-170">たとえば、`-ceq` は、大文字と小文字が区別される `-eq` 比較演算子です。</span><span class="sxs-lookup"><span data-stu-id="f2575-170">For example, `-ceq` is the case-sensitive version of the `-eq` comparison operator.</span></span>

<span data-ttu-id="f2575-171">一部が大文字になっている "PowerShell" は、等号比較演算子を使用した場合、すべてが小文字の "powershell" と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="f2575-171">Proper case "PowerShell" is equal to lower case "powershell" using the equals comparison operator.</span></span>

```powershell
'PowerShell' -eq 'powershell'
```

```Output
True
```

<span data-ttu-id="f2575-172">大文字と小文字が区別される等号比較演算子を使用した場合、これは等しくなりません。</span><span class="sxs-lookup"><span data-stu-id="f2575-172">It's not equal using the case-sensitive version of the equals comparison operator.</span></span>

```powershell
'PowerShell' -ceq 'powershell'
```

```Output
False
```

<span data-ttu-id="f2575-173">不等号比較演算子は条件を逆にします。</span><span class="sxs-lookup"><span data-stu-id="f2575-173">The not equal comparison operator reverses the condition.</span></span>

```powershell
'PowerShell' -ne 'powershell'
```

```Output
False
```

<span data-ttu-id="f2575-174">"より大きい"、"以上"、"より小さい"、"以下" のすべてを、文字列または数値で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f2575-174">Greater than, greater than or equal to, less than, and less than or equal all work with string or numeric values.</span></span>

```powershell
5 -gt 5
```

```Output
False
```

<span data-ttu-id="f2575-175">この例で "より大きい" ではなく "以上" を使用すると、5 と 5 は等しいため、**ブール値** true が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2575-175">Using greater than or equal to instead of greater than with the previous example returns the **Boolean** true since five is equal to five.</span></span>

```powershell
5 -ge 5
```

```Output
True
```

<span data-ttu-id="f2575-176">この 2 つの例の結果から、"より小さい" または "以下" の動作を推測できます。</span><span class="sxs-lookup"><span data-stu-id="f2575-176">Based on the results from the previous two examples, you can probably guess how both less than and less than or equal to work.</span></span>

```powershell
5 -lt 10
```

```Output
True
```

<span data-ttu-id="f2575-177">`-Like` 演算子と `-Match` 演算子については、経験豊富な PowerShell ユーザーでも混乱するかもしれません。</span><span class="sxs-lookup"><span data-stu-id="f2575-177">The `-Like` and `-Match` operators can be confusing, even for experienced PowerShell users.</span></span> <span data-ttu-id="f2575-178">`-Like` はワイルドカード文字 `*` および `?` と共に使用され、"like" 照合を実行します。</span><span class="sxs-lookup"><span data-stu-id="f2575-178">`-Like` is used with wildcard the characters `*` and `?` to perform "like" matches.</span></span>

```powershell
'PowerShell' -like '*shell'
```

```Output
True
```

<span data-ttu-id="f2575-179">`-Match` では、正規表現を使用して照合が行われます。</span><span class="sxs-lookup"><span data-stu-id="f2575-179">`-Match` uses a regular expression to perform the matching.</span></span>

```powershell
'PowerShell' -match '^*.shell$'
```

```Output
True
```

<span data-ttu-id="f2575-180">1 から 10 までの数値を変数に格納するには、範囲演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2575-180">Use the range operator to store the numbers 1 through 10 in a variable.</span></span>

```powershell
$Numbers = 1..10
```

```Output
```

<span data-ttu-id="f2575-181">`$Numbers` 変数に 15 が含まれているかどうかを確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="f2575-181">Determine if the `$Numbers` variable includes 15.</span></span>

```powershell
$Numbers -contains 15
```

```Output
False
```

<span data-ttu-id="f2575-182">数値 10 が含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2575-182">Determine if it includes the number 10.</span></span>

```powershell
$Numbers -contains 10
```

```Output
True
```

<span data-ttu-id="f2575-183">`-NotContains` はロジックを逆にして、`$Numbers` 変数に値が含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2575-183">`-NotContains` reverses the logic to see if the `$Numbers` variable doesn't contain a value.</span></span>

```powershell
$Numbers -notcontains 15
```

```Output
True
```

<span data-ttu-id="f2575-184">この例では、`$Numbers` 変数には確かに 15 が含まれていないため、**ブール値** true が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2575-184">The previous example returns the **Boolean** true because it's true that the `$Numbers` variable doesn't contain 15.</span></span> <span data-ttu-id="f2575-185">しかし、数値 10 は含まれているため、テストを実行すると false になります。</span><span class="sxs-lookup"><span data-stu-id="f2575-185">It does however contain the number 10 so it's false when it's tested.</span></span>

```powershell
$Numbers -notcontains 10
```

```Output
False
```

<span data-ttu-id="f2575-186">"in" 比較演算子は、PowerShell バージョン3.0 で初めて導入されました。</span><span class="sxs-lookup"><span data-stu-id="f2575-186">The "in" comparison operator was first introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="f2575-187">これは、値が配列に "ある" かどうかを確認するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="f2575-187">It's used to determine if a value is "in" an array.</span></span> <span data-ttu-id="f2575-188">`$Numbers` 変数は配列です。この変数には、複数の値が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="f2575-188">The `$Numbers` variable is an array since it contains multiple values.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="f2575-189">つまり、`-in` は、contains 比較演算子と同じテストを実行します。ただし、逆方向からはテストされません。</span><span class="sxs-lookup"><span data-stu-id="f2575-189">In other words, `-in` performs the same test as the contains comparison operator except from the opposite direction.</span></span>

```powershell
10 -in $Numbers
```

```Output
True
```

<span data-ttu-id="f2575-190">15 は `$Numbers` 配列にないため、次の例では false が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2575-190">15 isn't in the `$Numbers` array so false is returned in the following example.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="f2575-191">`-contains` 演算子と同様に、`not` は `-in` 演算子のロジックを逆にします。</span><span class="sxs-lookup"><span data-stu-id="f2575-191">Just like the `-contains` operator, `not` reverses the logic for the `-in` operator.</span></span>

```powershell
10 -notin $Numbers
```

```Output
False
```

<span data-ttu-id="f2575-192">この例では、`$Numbers` 配列に 10 が含まれており、この条件では 10 が含まれていないことを確認するテストを行ったため、false が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2575-192">The previous example returns false because the `$Numbers` array does include 10 and the condition was testing to determine if it didn't contain 10.</span></span>

<span data-ttu-id="f2575-193">15は `$Numbers` 配列に "ない" ため、**ブール値** true が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2575-193">15 is "not in" the `$Numbers` array so it returns the **Boolean** true.</span></span>

```powershell
15 -notin $Numbers
```

```Output
True
```

<span data-ttu-id="f2575-194">`-replace` 演算子は、お察しのとおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="f2575-194">The `-replace` operator does just want you would think.</span></span> <span data-ttu-id="f2575-195">これは何かを置き換えるときに使用します。</span><span class="sxs-lookup"><span data-stu-id="f2575-195">It's used to replace something.</span></span> <span data-ttu-id="f2575-196">ある値を指定すると、その値がなくなります。</span><span class="sxs-lookup"><span data-stu-id="f2575-196">Specifying one value replaces that value with nothing.</span></span> <span data-ttu-id="f2575-197">次の例では、"Shell" がなくなっています。</span><span class="sxs-lookup"><span data-stu-id="f2575-197">In the following example, I replace "Shell" with nothing.</span></span>

```powershell
'PowerShell' -replace 'Shell'
```

```Output
Power
```

<span data-ttu-id="f2575-198">ある値を別の値に置き換える場合は、置換後の新しい値を、置き換えたいパターンの後ろで指定します。</span><span class="sxs-lookup"><span data-stu-id="f2575-198">If you want to replace a value with a different value, specify the new value after the pattern you want to replace.</span></span> <span data-ttu-id="f2575-199">"SQL Saturday in Baton Rouge" は、毎年の講演イベントです。</span><span class="sxs-lookup"><span data-stu-id="f2575-199">SQL Saturday in Baton Rouge is an event that I try to speak at every year.</span></span> <span data-ttu-id="f2575-200">次の例で、"Saturday" という単語を省略形 "Sat" に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f2575-200">In the following example, I replace the word "Saturday" with the abbreviation "Sat".</span></span>

```powershell
'SQL Saturday - Baton Rouge' -Replace 'saturday','Sat'
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="f2575-201">Replace 演算子と同じように動作する **Replace ()** などのメソッドを使って、何かを置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="f2575-201">There are also methods like **Replace()** that can be used to replace things similar to the way the replace operator works.</span></span> <span data-ttu-id="f2575-202">ただし、`-Replace` 演算子では、既定では大文字と小文字が区別されませんが、**Replace ()** メソッドでは大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="f2575-202">However, the `-Replace` operator is case-insensitive by default, and the **Replace()** method is case-sensitive.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('saturday','Sat')
```

```Output
SQL Saturday - Baton Rouge
```

<span data-ttu-id="f2575-203">この例では "Saturday" という単語が置き換えられていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f2575-203">Notice that the word "Saturday" wasn't replaced in the previous example.</span></span> <span data-ttu-id="f2575-204">これは、大文字と小文字の使い方が元の単語と異なるためです。</span><span class="sxs-lookup"><span data-stu-id="f2575-204">This is because it was specified in a different case than the original.</span></span> <span data-ttu-id="f2575-205">元の単語と同じように "Saturday" と指定すれば、**Replace ()** メソッドによって、意図したとおりに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="f2575-205">When the word "Saturday" is specified in the same case as the original, the **Replace()** method does replace it as expected.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('Saturday','Sat')
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="f2575-206">メソッドを使用してデータを変換するときは、"_トルコ テスト_" の失敗のように、予期しない問題が発生する可能性があるため注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="f2575-206">Be careful when using methods to transform data because you can run into unforeseen problems, such as failing the _Turkey Test_.</span></span> <span data-ttu-id="f2575-207">例については、「[Pester を使用した他のカルチャでの PowerShell コードのテスト][]」というタイトルのブログ記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2575-207">For an example, see the blog article titled [Using Pester to Test PowerShell Code with Other Cultures][].</span></span> <span data-ttu-id="f2575-208">このような問題が発生しないように、できるだけメソッドではなく演算子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f2575-208">My recommendation is to use an operator instead of a method whenever possible to avoid these types of problems.</span></span>

<span data-ttu-id="f2575-209">比較演算子は前の例で紹介したように使用できますが、通常は、`Where-Object` コマンドレットを使用して、何らかのフィルター処理を行っています。</span><span class="sxs-lookup"><span data-stu-id="f2575-209">While the comparison operators can be used as shown in the previous examples, I normally find myself using them with the `Where-Object` cmdlet to perform some type of filtering.</span></span>

## <a name="summary"></a><span data-ttu-id="f2575-210">まとめ</span><span class="sxs-lookup"><span data-stu-id="f2575-210">Summary</span></span>

<span data-ttu-id="f2575-211">この章では、右で書式設定、エイリアス、プロバイダー、および比較演算子に関するさまざまなトピックについて学習しました。</span><span class="sxs-lookup"><span data-stu-id="f2575-211">In this chapter, you've learned a number of different topics to include Formatting Right, Aliases, Providers, and Comparison Operators.</span></span>

## <a name="review"></a><span data-ttu-id="f2575-212">確認</span><span class="sxs-lookup"><span data-stu-id="f2575-212">Review</span></span>

1. <span data-ttu-id="f2575-213">できるだけ右で書式設定を行う必要があるのは、なぜですか。</span><span class="sxs-lookup"><span data-stu-id="f2575-213">Why is it necessary to perform Formatting as far to the right as possible?</span></span>
1. <span data-ttu-id="f2575-214">`%` エイリアスを対象とした実際のコマンドレットを確認するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="f2575-214">How do you determine what the actual cmdlet is for the `%` alias?</span></span>
1. <span data-ttu-id="f2575-215">保存するスクリプトや他のユーザーと共有するコードで使用すべきではないのは、なぜですか。</span><span class="sxs-lookup"><span data-stu-id="f2575-215">Why shouldn't you use aliases in scripts you save or code you share with others?</span></span>
1. <span data-ttu-id="f2575-216">いずれかのレジストリ プロバイダーに関連付けられているドライブで、ディレクトリのリストを実行してください。</span><span class="sxs-lookup"><span data-stu-id="f2575-216">Perform a directory listing on the drives that are associated with one of the registry providers.</span></span>
1. <span data-ttu-id="f2575-217">置換メソッドではなく置換演算子を使用する主なメリットの 1 つは何ですか。</span><span class="sxs-lookup"><span data-stu-id="f2575-217">What's one of the main benefits of using the replace operator instead of the replace method?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="f2575-218">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="f2575-218">Recommended Reading</span></span>

- <span data-ttu-id="f2575-219">[Format-Table][]</span><span class="sxs-lookup"><span data-stu-id="f2575-219">[Format-Table][]</span></span>
- <span data-ttu-id="f2575-220">[Format-List][]</span><span class="sxs-lookup"><span data-stu-id="f2575-220">[Format-List][]</span></span>
- <span data-ttu-id="f2575-221">[Format-Wide][]</span><span class="sxs-lookup"><span data-stu-id="f2575-221">[Format-Wide][]</span></span>
- <span data-ttu-id="f2575-222">[about_Aliases][]</span><span class="sxs-lookup"><span data-stu-id="f2575-222">[about_Aliases][]</span></span>
- <span data-ttu-id="f2575-223">[about_Providers][]</span><span class="sxs-lookup"><span data-stu-id="f2575-223">[about_Providers][]</span></span>
- <span data-ttu-id="f2575-224">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="f2575-224">[about_Comparison_Operators][]</span></span>
- <span data-ttu-id="f2575-225">[about_Arrays][]</span><span class="sxs-lookup"><span data-stu-id="f2575-225">[about_Arrays][]</span></span>

<!-- link references -->
[SMSS]: /sql/ssms/download-sql-server-management-studio-ssms
[Format-Table]: /powershell/module/microsoft.powershell.utility/format-table
[Format-List]: /powershell/module/microsoft.powershell.utility/format-list
[Format-Wide]: /powershell/module/microsoft.powershell.utility/format-wide
[about_Aliases]: /powershell/module/microsoft.powershell.core/about/about_aliases
[about_Providers]: /powershell/module/microsoft.powershell.core/about/about_providers
[about_Comparison_Operators]: /powershell/module/microsoft.powershell.core/about/about_comparison_operators
[about_Arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Pester を使用した他のカルチャでの PowerShell コードのテスト]: https://mikefrobbins.com/2015/10/22/using-pester-to-test-powershell-code-with-other-cultures/
[Using Pester to Test PowerShell Code with Other Cultures]: https://mikefrobbins.com/2015/10/22/using-pester-to-test-powershell-code-with-other-cultures/
