---
title: 書式設定、エイリアス、プロバイダー、比較
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
description: この章では、出力書式設定、コマンド エイリアス、プロバイダー、比較演算の概念について説明します。
ms.openlocfilehash: efe70d2d220f8451e781603b6000c3553dda910c
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501611"
---
# <a name="chapter-5---formatting-aliases-providers-comparison"></a><span data-ttu-id="13bdc-103">第 5 章 - 書式設定、エイリアス、プロバイダー、比較</span><span class="sxs-lookup"><span data-stu-id="13bdc-103">Chapter 5 - Formatting, aliases, providers, comparison</span></span>

## <a name="requirements"></a><span data-ttu-id="13bdc-104">必要条件</span><span class="sxs-lookup"><span data-stu-id="13bdc-104">Requirements</span></span>

<span data-ttu-id="13bdc-105">この章で紹介する例の中には、SQL Server PowerShell モジュールを必要とするものがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="13bdc-105">The SQL Server PowerShell module is required by some of the examples shown in this chapter.</span></span> <span data-ttu-id="13bdc-106">このモジュールは、[SQL Server Management Studio (SSMS)][SMSS] の一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-106">The module installs as part of [SQL Server Management Studio (SMSS)][SMSS].</span></span> <span data-ttu-id="13bdc-107">このモジュールは、以降の章でも使用されるので、</span><span class="sxs-lookup"><span data-stu-id="13bdc-107">It's also used in subsequent chapters.</span></span> <span data-ttu-id="13bdc-108">Windows 10 ラボ環境のコンピューターにダウンロードし、インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="13bdc-108">Download and install it on your Windows 10 lab environment computer.</span></span>

## <a name="format-right"></a><span data-ttu-id="13bdc-109">右で書式設定</span><span class="sxs-lookup"><span data-stu-id="13bdc-109">Format Right</span></span>

<span data-ttu-id="13bdc-110">第 4 章では、できるだけ左端でフィルター処理する方法について学習しました。</span><span class="sxs-lookup"><span data-stu-id="13bdc-110">In Chapter 4, you learned to filter as far to the left as possible.</span></span> <span data-ttu-id="13bdc-111">コマンドの出力を手動で書式設定するためのルールは、このルールに似ています (できるだけ右で実行する必要がある場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="13bdc-111">The rule for manually formatting a command's output is similar to that rule except it needs to occur as far to the right as possible.</span></span>

<span data-ttu-id="13bdc-112">最も一般的な書式設定コマンドは `Format-Table` と `Format-List` です。</span><span class="sxs-lookup"><span data-stu-id="13bdc-112">The most common format commands are `Format-Table` and `Format-List`.</span></span> <span data-ttu-id="13bdc-113">`Format-Wide` と `Format-Custom` を使用することもできますが、あまり一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="13bdc-113">`Format-Wide` and `Format-Custom` can also be used, but are less common.</span></span>

<span data-ttu-id="13bdc-114">第 3 章で説明したように、カスタム書式設定を使用しない限り、4 つを超えるプロパティを返すコマンドは既定でリストになります。</span><span class="sxs-lookup"><span data-stu-id="13bdc-114">As mentioned in Chapter 3, a command that returns more than four properties defaults to a list unless custom formatting is used.</span></span>

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

<span data-ttu-id="13bdc-115">`Format-Table` コマンドレットを使用して書式設定を手動でオーバーライドし、リストではなくテーブルに出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-115">Use the `Format-Table` cmdlet to manually override the formatting and show the output in a table instead of a list.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can* |
Format-Table
```

```Output
 Status DisplayName  CanPauseAndContinue CanShutdown CanStop
 ------ -----------  ------------------- ----------- -------
Running Windows Time               False        True    True
```

<span data-ttu-id="13bdc-116">`Get-Service` の既定の出力は、テーブル内の 3 つのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="13bdc-116">The default output for `Get-Service` is three properties in a table.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="13bdc-117">`Format-List` コマンドレットを使用して既定の書式設定をオーバーライドし、結果をリストで返します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-117">Use the `Format-List` cmdlet to override the default formatting and return the results in a list.</span></span>

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

<span data-ttu-id="13bdc-118">`Get-Service` を `Format-List` にパイプ処理するだけで、追加のプロパティが返されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="13bdc-118">Notice that simply piping `Get-Service` to `Format-List` made it return additional properties.</span></span> <span data-ttu-id="13bdc-119">その特定のコマンドについては書式設定がバックグラウンドで行われるため、これはすべてのコマンドで発生するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="13bdc-119">This doesn't occur with every command because of the way the formatting for that particular command is set up behind the scenes.</span></span>

<span data-ttu-id="13bdc-120">書式設定コマンドレットを使うときに最も注意しなければならないのは、このコマンドレットによって生成される書式設定オブジェクトは、PowerShell の通常のオブジェクトと異なるという点です。</span><span class="sxs-lookup"><span data-stu-id="13bdc-120">The number one thing to be aware of with the format cmdlets is they produce format objects that are different than normal objects in PowerShell.</span></span>

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

<span data-ttu-id="13bdc-121">つまり、書式設定コマンドのパイプ処理の対象となるコマンドは、それほどありません。</span><span class="sxs-lookup"><span data-stu-id="13bdc-121">What this means is format commands can't be piped to most other commands.</span></span> <span data-ttu-id="13bdc-122">一部の `Out-*` コマンドに対してはパイプ処理できますが、それが限度です。</span><span class="sxs-lookup"><span data-stu-id="13bdc-122">They can be piped to some of the `Out-*` commands, but that's about it.</span></span> <span data-ttu-id="13bdc-123">行の最後で書式設定 (右で書式設定) する必要があるのは、そのためです。</span><span class="sxs-lookup"><span data-stu-id="13bdc-123">This is why you want to perform any formatting at the very end of the line (format right).</span></span>

## <a name="aliases"></a><span data-ttu-id="13bdc-124">エイリアス</span><span class="sxs-lookup"><span data-stu-id="13bdc-124">Aliases</span></span>

<span data-ttu-id="13bdc-125">PowerShell のエイリアスは、短いコマンド名です。</span><span class="sxs-lookup"><span data-stu-id="13bdc-125">An alias in PowerShell is a shorter name for a command.</span></span> <span data-ttu-id="13bdc-126">PowerShell には、一連の組み込みエイリアスが含まれていますが、独自のエイリアスを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-126">PowerShell includes a set of built-in aliases and you can also define your own aliases.</span></span>

<span data-ttu-id="13bdc-127">`Get-Alias` コマンドレットは、エイリアスを見つけるときに使用します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-127">The `Get-Alias` cmdlet is used to find aliases.</span></span> <span data-ttu-id="13bdc-128">コマンドのエイリアスが既にわかっている場合は、 **Name** パラメーターを使用して、エイリアスが関連付けられているコマンドを確認します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-128">If you already know the alias for a command, the **Name** parameter is used to determine what command the alias is associated with.</span></span>

```powershell
Get-Alias -Name gcm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
```

<span data-ttu-id="13bdc-129">**Name** パラメーターの値には、複数のエイリアスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-129">Multiple aliases can be specified for the value of the **Name** parameter.</span></span>

```powershell
Get-Alias -Name gcm, gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="13bdc-130">**Name** パラメーターは位置指定パラメーターであるため、省略されていることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="13bdc-130">You'll often see the **Name** parameter omitted since it's a positional parameter.</span></span>

```powershell
Get-Alias gm
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gm -> Get-Member
```

<span data-ttu-id="13bdc-131">コマンドのエイリアスを検索する場合は、 **Definition** パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13bdc-131">If you want to find aliases for a command, you'll need to use the **Definition** parameter.</span></span>

```powershell
Get-Alias -Definition Get-Command, Get-Member
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gcm -> Get-Command
Alias           gm -> Get-Member
```

<span data-ttu-id="13bdc-132">**Definition** パラメーターは位置指定には使用できないため、必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13bdc-132">The **Definition** parameter can't be used positionally so it must be specified.</span></span>

<span data-ttu-id="13bdc-133">エイリアスを使用すると、キーストロークをいくつか省略できるため、コンソールにコマンドを入力するときは便利です。</span><span class="sxs-lookup"><span data-stu-id="13bdc-133">Aliases can save you a few keystrokes and they're fine when you're typing commands into the console.</span></span>
<span data-ttu-id="13bdc-134">このエイリアスは、保存するスクリプトや他のユーザーと共有するコードでは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="13bdc-134">They shouldn't be used in scripts or any code that you're saving or sharing with others.</span></span> <span data-ttu-id="13bdc-135">本書で前述したように、完全なコマンドレットとパラメーター名を使用すると自己文書化されるため、理解しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="13bdc-135">As mentioned earlier in this book, using full cmdlet and parameter names is self-documenting and easier to understand.</span></span>

<span data-ttu-id="13bdc-136">独自のエイリアスは、お使いのコンピューター上の現在の PowerShell セッションにしか存在しないため、作成するときは注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="13bdc-136">Use caution when creating your own aliases because they'll only exist in your current PowerShell session on your computer.</span></span>

## <a name="providers"></a><span data-ttu-id="13bdc-137">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="13bdc-137">Providers</span></span>

<span data-ttu-id="13bdc-138">PowerShell のプロバイダーは、データストアに、ファイル システムのようにアクセスできるようにするインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="13bdc-138">A provider in PowerShell is an interface that allows file system like access to a datastore.</span></span> <span data-ttu-id="13bdc-139">PowerShell には、組み込みプロバイダーが複数用意されています。</span><span class="sxs-lookup"><span data-stu-id="13bdc-139">There are a number of built-in providers in PowerShell.</span></span>

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

<span data-ttu-id="13bdc-140">上記の結果が示すように、レジストリ、エイリアス、環境変数、ファイル システム、関数、変数、証明書、および WSMan に対して、組み込みプロバイダーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="13bdc-140">As you can see in the previous results, there are built-in providers for the registry, aliases, environment variables, the file system, functions, variables, certificates, and WSMan.</span></span>

<span data-ttu-id="13bdc-141">これらのプロバイダーがデータストアの公開に使用する実際のドライブは、`Get-PSDrive` コマンドレットを使って確認できます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-141">The actual drives that these providers use to expose their datastore can be determined with the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="13bdc-142">`Get-PSDrive` コマンドレットによって表示されるのは、プロバイダーが公開しているドライブだけではありません。ネットワーク共有にマップされたドライブなど、Windows 論理ドライブも表示されます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-142">The `Get-PSDrive` cmdlet not only displays drives exposed by providers, but it also displays Windows logical drives including drives mapped to network shares.</span></span>

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

<span data-ttu-id="13bdc-143">Active Directory PowerShell モジュール、SQLServer PowerShell モジュールといったサードパーティ モジュールそれぞれによって、独自の PowerShell プロバイダーと PSDrive が追加されます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-143">Third-party modules such as the Active Directory PowerShell module and the SQLServer PowerShell module both add their own PowerShell provider and PSDrive.</span></span>

<span data-ttu-id="13bdc-144">Active Directory PowerShell モジュールと SQL Server PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="13bdc-144">Import the Active Directory and SQL Server PowerShell modules.</span></span>

```powershell
Import-Module -Name ActiveDirectory, SQLServer
```

<span data-ttu-id="13bdc-145">追加 PowerShell プロバイダーが追加されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-145">Check to see if any additional PowerShell providers were added.</span></span>

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

<span data-ttu-id="13bdc-146">この結果セットでは、2 つの PowerShell プロバイダーが新しく存在していることに注意してください。1 つは Active Directory 用、もう 1 つは SQL Server 用のプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="13bdc-146">Notice that in the previous set of results, two new PowerShell providers now exist, one for Active Directory and another one for SQL Server.</span></span>

<span data-ttu-id="13bdc-147">各モジュールの PSDrive も追加されました。</span><span class="sxs-lookup"><span data-stu-id="13bdc-147">A PSDrive for each of those modules was also added.</span></span>

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

<span data-ttu-id="13bdc-148">PSDrives には、従来のファイル システムと同じようにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-148">PSDrives can be accessed just like a traditional file system.</span></span>

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

## <a name="comparison-operators"></a><span data-ttu-id="13bdc-149">比較演算子</span><span class="sxs-lookup"><span data-stu-id="13bdc-149">Comparison Operators</span></span>

<span data-ttu-id="13bdc-150">PowerShell には、値を比較したり、特定のパターンに一致する値を検索したりするときに使用する比較演算子が多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="13bdc-150">PowerShell contains a number of comparison operators that are used to compare values or find values that match certain patterns.</span></span> <span data-ttu-id="13bdc-151">表 5-1 は、PowerShell の比較演算子の一覧です。</span><span class="sxs-lookup"><span data-stu-id="13bdc-151">Table 5-1 contains a list of comparison operators in PowerShell.</span></span>

|    <span data-ttu-id="13bdc-152">演算子</span><span class="sxs-lookup"><span data-stu-id="13bdc-152">Operator</span></span>    |                          <span data-ttu-id="13bdc-153">定義</span><span class="sxs-lookup"><span data-stu-id="13bdc-153">Definition</span></span>                          |
| -------------- | ------------------------------------------------------------ |
| `-eq`          | <span data-ttu-id="13bdc-154">等しい</span><span class="sxs-lookup"><span data-stu-id="13bdc-154">Equal to</span></span>                                                     |
| `-ne`          | <span data-ttu-id="13bdc-155">等しくない</span><span class="sxs-lookup"><span data-stu-id="13bdc-155">Not equal to</span></span>                                                 |
| `-gt`          | <span data-ttu-id="13bdc-156">より大きい</span><span class="sxs-lookup"><span data-stu-id="13bdc-156">Greater than</span></span>                                                 |
| `-ge`          | <span data-ttu-id="13bdc-157">以上</span><span class="sxs-lookup"><span data-stu-id="13bdc-157">Greater than or equal to</span></span>                                     |
| `-lt`          | <span data-ttu-id="13bdc-158">より小さい</span><span class="sxs-lookup"><span data-stu-id="13bdc-158">Less than</span></span>                                                    |
| `-le`          | <span data-ttu-id="13bdc-159">以下</span><span class="sxs-lookup"><span data-stu-id="13bdc-159">Less than or equal to</span></span>                                        |
| `-Like`        | <span data-ttu-id="13bdc-160">`*` ワイルドカード文字を使用した一致</span><span class="sxs-lookup"><span data-stu-id="13bdc-160">Match using the `*` wildcard character</span></span>                       |
| `-NotLike`     | <span data-ttu-id="13bdc-161">`*` ワイルドカード文字を使用した不一致</span><span class="sxs-lookup"><span data-stu-id="13bdc-161">Does not match using the `*` wildcard character</span></span>              |
| `-Match`       | <span data-ttu-id="13bdc-162">指定した正規表現と一致</span><span class="sxs-lookup"><span data-stu-id="13bdc-162">Matches the specified regular expression</span></span>                     |
| `-NotMatch`    | <span data-ttu-id="13bdc-163">指定した正規表現と一致しない</span><span class="sxs-lookup"><span data-stu-id="13bdc-163">Does not match the specified regular expression</span></span>              |
| `-Contains`    | <span data-ttu-id="13bdc-164">コレクションに指定した値が含まれているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="13bdc-164">Determines if a collection contains a specified value</span></span>        |
| `-NotContains` | <span data-ttu-id="13bdc-165">コレクションに特定の値が含まれていないことを確認する</span><span class="sxs-lookup"><span data-stu-id="13bdc-165">Determines if a collection does not contain a specific value</span></span> |
| `-In`          | <span data-ttu-id="13bdc-166">指定した値がコレクションに存在するかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="13bdc-166">Determines if a specified value is in a collection</span></span>           |
| `-NotIn`       | <span data-ttu-id="13bdc-167">指定した値がコレクションに含まれていないことを確認する</span><span class="sxs-lookup"><span data-stu-id="13bdc-167">Determines if a specified value is not in a collection</span></span>       |
| `-Replace`     | <span data-ttu-id="13bdc-168">指定した値を置き換える</span><span class="sxs-lookup"><span data-stu-id="13bdc-168">Replaces the specified value</span></span>                                 |

<span data-ttu-id="13bdc-169">表 5-1 に記載されている演算子はすべて、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="13bdc-169">All of the operators listed in Table 5-1 are case-insensitive.</span></span> <span data-ttu-id="13bdc-170">大文字と小文字を区別するには、表 5-1 に示されている演算子の前に `c` を置きます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-170">Place a `c` in front of the operator listed in Table 5-1 to make it case-sensitive.</span></span> <span data-ttu-id="13bdc-171">たとえば、`-ceq` は、大文字と小文字が区別される `-eq` 比較演算子です。</span><span class="sxs-lookup"><span data-stu-id="13bdc-171">For example, `-ceq` is the case-sensitive version of the `-eq` comparison operator.</span></span>

<span data-ttu-id="13bdc-172">一部が大文字になっている "PowerShell" は、等号比較演算子を使用した場合、すべてが小文字の "powershell" と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="13bdc-172">Proper case "PowerShell" is equal to lower case "powershell" using the equals comparison operator.</span></span>

```powershell
'PowerShell' -eq 'powershell'
```

```Output
True
```

<span data-ttu-id="13bdc-173">大文字と小文字が区別される等号比較演算子を使用した場合、これは等しくなりません。</span><span class="sxs-lookup"><span data-stu-id="13bdc-173">It's not equal using the case-sensitive version of the equals comparison operator.</span></span>

```powershell
'PowerShell' -ceq 'powershell'
```

```Output
False
```

<span data-ttu-id="13bdc-174">不等号比較演算子は条件を逆にします。</span><span class="sxs-lookup"><span data-stu-id="13bdc-174">The not equal comparison operator reverses the condition.</span></span>

```powershell
'PowerShell' -ne 'powershell'
```

```Output
False
```

<span data-ttu-id="13bdc-175">"より大きい"、"以上"、"より小さい"、"以下" のすべてを、文字列または数値で利用できます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-175">Greater than, greater than or equal to, less than, and less than or equal all work with string or numeric values.</span></span>

```powershell
5 -gt 5
```

```Output
False
```

<span data-ttu-id="13bdc-176">この例で "より大きい" ではなく "以上" を使用すると、5 と 5 は等しいため、 **ブール値** true が返されます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-176">Using greater than or equal to instead of greater than with the previous example returns the **Boolean** true since five is equal to five.</span></span>

```powershell
5 -ge 5
```

```Output
True
```

<span data-ttu-id="13bdc-177">この 2 つの例の結果から、"より小さい" または "以下" の動作を推測できます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-177">Based on the results from the previous two examples, you can probably guess how both less than and less than or equal to work.</span></span>

```powershell
5 -lt 10
```

```Output
True
```

<span data-ttu-id="13bdc-178">`-Like` 演算子と `-Match` 演算子については、経験豊富な PowerShell ユーザーでも混乱するかもしれません。</span><span class="sxs-lookup"><span data-stu-id="13bdc-178">The `-Like` and `-Match` operators can be confusing, even for experienced PowerShell users.</span></span> <span data-ttu-id="13bdc-179">`-Like` はワイルドカード文字 `*` および `?` と共に使用され、"like" 照合を実行します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-179">`-Like` is used with wildcard the characters `*` and `?` to perform "like" matches.</span></span>

```powershell
'PowerShell' -like '*shell'
```

```Output
True
```

<span data-ttu-id="13bdc-180">`-Match` では、正規表現を使用して照合が行われます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-180">`-Match` uses a regular expression to perform the matching.</span></span>

```powershell
'PowerShell' -match '^*.shell$'
```

```Output
True
```

<span data-ttu-id="13bdc-181">1 から 10 までの数値を変数に格納するには、範囲演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-181">Use the range operator to store the numbers 1 through 10 in a variable.</span></span>

```powershell
$Numbers = 1..10
```

```Output
```

<span data-ttu-id="13bdc-182">`$Numbers` 変数に 15 が含まれているかどうかを確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="13bdc-182">Determine if the `$Numbers` variable includes 15.</span></span>

```powershell
$Numbers -contains 15
```

```Output
False
```

<span data-ttu-id="13bdc-183">数値 10 が含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-183">Determine if it includes the number 10.</span></span>

```powershell
$Numbers -contains 10
```

```Output
True
```

<span data-ttu-id="13bdc-184">`-NotContains` はロジックを逆にして、`$Numbers` 変数に値が含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-184">`-NotContains` reverses the logic to see if the `$Numbers` variable doesn't contain a value.</span></span>

```powershell
$Numbers -notcontains 15
```

```Output
True
```

<span data-ttu-id="13bdc-185">この例では、`$Numbers` 変数には確かに 15 が含まれていないため、 **ブール値** true が返されます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-185">The previous example returns the **Boolean** true because it's true that the `$Numbers` variable doesn't contain 15.</span></span> <span data-ttu-id="13bdc-186">しかし、数値 10 は含まれているため、テストを実行すると false になります。</span><span class="sxs-lookup"><span data-stu-id="13bdc-186">It does however contain the number 10 so it's false when it's tested.</span></span>

```powershell
$Numbers -notcontains 10
```

```Output
False
```

<span data-ttu-id="13bdc-187">"in" 比較演算子は、PowerShell バージョン3.0 で初めて導入されました。</span><span class="sxs-lookup"><span data-stu-id="13bdc-187">The "in" comparison operator was first introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="13bdc-188">これは、値が配列に "ある" かどうかを確認するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-188">It's used to determine if a value is "in" an array.</span></span> <span data-ttu-id="13bdc-189">`$Numbers` 変数は配列です。この変数には、複数の値が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="13bdc-189">The `$Numbers` variable is an array since it contains multiple values.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="13bdc-190">つまり、`-in` は、contains 比較演算子と同じテストを実行します。ただし、逆方向からはテストされません。</span><span class="sxs-lookup"><span data-stu-id="13bdc-190">In other words, `-in` performs the same test as the contains comparison operator except from the opposite direction.</span></span>

```powershell
10 -in $Numbers
```

```Output
True
```

<span data-ttu-id="13bdc-191">15 は `$Numbers` 配列にないため、次の例では false が返されます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-191">15 isn't in the `$Numbers` array so false is returned in the following example.</span></span>

```powershell
15 -in $Numbers
```

```Output
False
```

<span data-ttu-id="13bdc-192">`-contains` 演算子と同様に、`not` は `-in` 演算子のロジックを逆にします。</span><span class="sxs-lookup"><span data-stu-id="13bdc-192">Just like the `-contains` operator, `not` reverses the logic for the `-in` operator.</span></span>

```powershell
10 -notin $Numbers
```

```Output
False
```

<span data-ttu-id="13bdc-193">この例では、`$Numbers` 配列に 10 が含まれており、この条件では 10 が含まれていないことを確認するテストを行ったため、false が返されます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-193">The previous example returns false because the `$Numbers` array does include 10 and the condition was testing to determine if it didn't contain 10.</span></span>

<span data-ttu-id="13bdc-194">15は `$Numbers` 配列に "ない" ため、 **ブール値** true が返されます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-194">15 is "not in" the `$Numbers` array so it returns the **Boolean** true.</span></span>

```powershell
15 -notin $Numbers
```

```Output
True
```

<span data-ttu-id="13bdc-195">`-replace` 演算子は、お察しのとおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-195">The `-replace` operator does just want you would think.</span></span> <span data-ttu-id="13bdc-196">これは何かを置き換えるときに使用します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-196">It's used to replace something.</span></span> <span data-ttu-id="13bdc-197">ある値を指定すると、その値がなくなります。</span><span class="sxs-lookup"><span data-stu-id="13bdc-197">Specifying one value replaces that value with nothing.</span></span> <span data-ttu-id="13bdc-198">次の例では、"Shell" がなくなっています。</span><span class="sxs-lookup"><span data-stu-id="13bdc-198">In the following example, I replace "Shell" with nothing.</span></span>

```powershell
'PowerShell' -replace 'Shell'
```

```Output
Power
```

<span data-ttu-id="13bdc-199">ある値を別の値に置き換える場合は、置換後の新しい値を、置き換えたいパターンの後ろで指定します。</span><span class="sxs-lookup"><span data-stu-id="13bdc-199">If you want to replace a value with a different value, specify the new value after the pattern you want to replace.</span></span> <span data-ttu-id="13bdc-200">"SQL Saturday in Baton Rouge" は、毎年の講演イベントです。</span><span class="sxs-lookup"><span data-stu-id="13bdc-200">SQL Saturday in Baton Rouge is an event that I try to speak at every year.</span></span> <span data-ttu-id="13bdc-201">次の例で、"Saturday" という単語を省略形 "Sat" に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-201">In the following example, I replace the word "Saturday" with the abbreviation "Sat".</span></span>

```powershell
'SQL Saturday - Baton Rouge' -Replace 'saturday','Sat'
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="13bdc-202">Replace 演算子と同じように動作する **Replace ()** などのメソッドを使って、何かを置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-202">There are also methods like **Replace()** that can be used to replace things similar to the way the replace operator works.</span></span> <span data-ttu-id="13bdc-203">ただし、`-Replace` 演算子では、既定では大文字と小文字が区別されませんが、 **Replace ()** メソッドでは大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-203">However, the `-Replace` operator is case-insensitive by default, and the **Replace()** method is case-sensitive.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('saturday','Sat')
```

```Output
SQL Saturday - Baton Rouge
```

<span data-ttu-id="13bdc-204">この例では "Saturday" という単語が置き換えられていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="13bdc-204">Notice that the word "Saturday" wasn't replaced in the previous example.</span></span> <span data-ttu-id="13bdc-205">これは、大文字と小文字の使い方が元の単語と異なるためです。</span><span class="sxs-lookup"><span data-stu-id="13bdc-205">This is because it was specified in a different case than the original.</span></span> <span data-ttu-id="13bdc-206">元の単語と同じように "Saturday" と指定すれば、 **Replace ()** メソッドによって、意図したとおりに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="13bdc-206">When the word "Saturday" is specified in the same case as the original, the **Replace()** method does replace it as expected.</span></span>

```powershell
'SQL Saturday - Baton Rouge'.Replace('Saturday','Sat')
```

```Output
SQL Sat - Baton Rouge
```

<span data-ttu-id="13bdc-207">メソッドを使用してデータを変換するときは、" _トルコ テスト_ " の失敗のように、予期しない問題が発生する可能性があるため注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="13bdc-207">Be careful when using methods to transform data because you can run into unforeseen problems, such as failing the _Turkey Test_ .</span></span> <span data-ttu-id="13bdc-208">例については、「[Pester を使用した他のカルチャでの PowerShell コードのテスト][]」というタイトルのブログ記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13bdc-208">For an example, see the blog article titled [Using Pester to Test PowerShell Code with Other Cultures][].</span></span> <span data-ttu-id="13bdc-209">このような問題が発生しないように、できるだけメソッドではなく演算子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13bdc-209">My recommendation is to use an operator instead of a method whenever possible to avoid these types of problems.</span></span>

<span data-ttu-id="13bdc-210">比較演算子は前の例で紹介したように使用できますが、通常は、`Where-Object` コマンドレットを使用して、何らかのフィルター処理を行っています。</span><span class="sxs-lookup"><span data-stu-id="13bdc-210">While the comparison operators can be used as shown in the previous examples, I normally find myself using them with the `Where-Object` cmdlet to perform some type of filtering.</span></span>

## <a name="summary"></a><span data-ttu-id="13bdc-211">まとめ</span><span class="sxs-lookup"><span data-stu-id="13bdc-211">Summary</span></span>

<span data-ttu-id="13bdc-212">この章では、右で書式設定、エイリアス、プロバイダー、および比較演算子に関するさまざまなトピックについて学習しました。</span><span class="sxs-lookup"><span data-stu-id="13bdc-212">In this chapter, you've learned a number of different topics to include Formatting Right, Aliases, Providers, and Comparison Operators.</span></span>

## <a name="review"></a><span data-ttu-id="13bdc-213">確認</span><span class="sxs-lookup"><span data-stu-id="13bdc-213">Review</span></span>

1. <span data-ttu-id="13bdc-214">できるだけ右で書式設定を行う必要があるのは、なぜですか。</span><span class="sxs-lookup"><span data-stu-id="13bdc-214">Why is it necessary to perform Formatting as far to the right as possible?</span></span>
1. <span data-ttu-id="13bdc-215">`%` エイリアスを対象とした実際のコマンドレットを確認するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="13bdc-215">How do you determine what the actual cmdlet is for the `%` alias?</span></span>
1. <span data-ttu-id="13bdc-216">保存するスクリプトや他のユーザーと共有するコードで使用すべきではないのは、なぜですか。</span><span class="sxs-lookup"><span data-stu-id="13bdc-216">Why shouldn't you use aliases in scripts you save or code you share with others?</span></span>
1. <span data-ttu-id="13bdc-217">いずれかのレジストリ プロバイダーに関連付けられているドライブで、ディレクトリのリストを実行してください。</span><span class="sxs-lookup"><span data-stu-id="13bdc-217">Perform a directory listing on the drives that are associated with one of the registry providers.</span></span>
1. <span data-ttu-id="13bdc-218">置換メソッドではなく置換演算子を使用する主なメリットの 1 つは何ですか。</span><span class="sxs-lookup"><span data-stu-id="13bdc-218">What's one of the main benefits of using the replace operator instead of the replace method?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="13bdc-219">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="13bdc-219">Recommended Reading</span></span>

- <span data-ttu-id="13bdc-220">[Format-Table][]</span><span class="sxs-lookup"><span data-stu-id="13bdc-220">[Format-Table][]</span></span>
- <span data-ttu-id="13bdc-221">[Format-List][]</span><span class="sxs-lookup"><span data-stu-id="13bdc-221">[Format-List][]</span></span>
- <span data-ttu-id="13bdc-222">[Format-Wide][]</span><span class="sxs-lookup"><span data-stu-id="13bdc-222">[Format-Wide][]</span></span>
- <span data-ttu-id="13bdc-223">[about_Aliases][]</span><span class="sxs-lookup"><span data-stu-id="13bdc-223">[about_Aliases][]</span></span>
- <span data-ttu-id="13bdc-224">[about_Providers][]</span><span class="sxs-lookup"><span data-stu-id="13bdc-224">[about_Providers][]</span></span>
- <span data-ttu-id="13bdc-225">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="13bdc-225">[about_Comparison_Operators][]</span></span>
- <span data-ttu-id="13bdc-226">[about_Arrays][]</span><span class="sxs-lookup"><span data-stu-id="13bdc-226">[about_Arrays][]</span></span>

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
