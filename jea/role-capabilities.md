---
ms.date: 06/12/2017
keywords: JEA, PowerShell, セキュリティ
title: JEA ロール機能
ms.openlocfilehash: 0531baa284e66a42a162329ea20ecfdca6d0b526
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "34190538"
---
# <a name="jea-role-capabilities"></a><span data-ttu-id="09f55-103">JEA ロール機能</span><span class="sxs-lookup"><span data-stu-id="09f55-103">JEA Role Capabilities</span></span>

> <span data-ttu-id="09f55-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="09f55-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="09f55-105">JEA エンドポイントを作成するとき、JEA セッションでユーザーに許可する*操作*を説明する "ロール機能" を 1 つ以上定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09f55-105">When creating a JEA endpoint, you will need to define one or more "role capabilities" which describe *what* someone can do in a JEA session.</span></span>
<span data-ttu-id="09f55-106">ロール機能は、.psrc 拡張子を持つ PowerShell データ ファイルです。このファイルには、接続ユーザーが利用できるすべてのコマンドレット、関数、プロバイダー、外部プログラムが列挙されています。</span><span class="sxs-lookup"><span data-stu-id="09f55-106">A role capability is a PowerShell data file with the .psrc extension that lists all the cmdlets, functions, providers, and external programs that should be made available to connecting users.</span></span>

<span data-ttu-id="09f55-107">このトピックでは、JEA ユーザーの PowerShell ロール機能ファイルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09f55-107">This topic describes how to create a PowerShell role capability file for your JEA users.</span></span>

## <a name="determine-which-commands-to-allow"></a><span data-ttu-id="09f55-108">許可するコマンドを決定する</span><span class="sxs-lookup"><span data-stu-id="09f55-108">Determine which commands to allow</span></span>

<span data-ttu-id="09f55-109">ロール機能ファイルを作成するときの最初の手順は、ロールを割り当てるユーザーに許可する操作を検討することです。</span><span class="sxs-lookup"><span data-stu-id="09f55-109">The first step when creating a role capability file is to consider what the users who are assigned the role will need access to.</span></span>
<span data-ttu-id="09f55-110">要件を集めるこのプロセスには時間がかかることがありますが、とても重要なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="09f55-110">This requirements gathering process can take a while, but it is a very important process.</span></span>
<span data-ttu-id="09f55-111">ユーザーに使用を許可するコマンドや関数があまりにも少ないと、仕事ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="09f55-111">Giving users access to too few cmdlets and functions can prevent them from getting their job done.</span></span>
<span data-ttu-id="09f55-112">逆にあまりにも多すぎると、暗黙的な管理者特権により、本来意図した以上の操作が可能になることがあり、セキュリティを弱めることになります。</span><span class="sxs-lookup"><span data-stu-id="09f55-112">Allowing access to too many cmdlets and functions can lead to users doing more than you intended with their implicit admin privileges, weakening your security stance.</span></span>

<span data-ttu-id="09f55-113">このプロセスの進め方は、属する組織や目標に依存しますが、次のヒントが役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="09f55-113">How you go about this process will depend on your organization and goals, however the following tips can help ensure you're on the right path.</span></span>

1. <span data-ttu-id="09f55-114">仕事を行うためにユーザーが使用しているコマンドを**確認**します。</span><span class="sxs-lookup"><span data-stu-id="09f55-114">**Identify** the commands users are using to get their jobs done.</span></span> <span data-ttu-id="09f55-115">たとえば、IT スタッフに調査を行ったり、自動化スクリプトを調べたり、PowerShell セッションのトランスクリプトやログを分析したりします。</span><span class="sxs-lookup"><span data-stu-id="09f55-115">This may involve surveying IT staff, checking automation scripts, or analyzing PowerShell session transcripts or logs.</span></span>
2. <span data-ttu-id="09f55-116">可能な限り、コマンド ライン ツールで行っていたことを PowerShell の同じ操作に**更新**し、最良の監査と JEA カスタマイズを実現します。</span><span class="sxs-lookup"><span data-stu-id="09f55-116">**Update** use of command line tools to PowerShell equivalents, where possible, for the best auditing and JEA customization experience.</span></span> <span data-ttu-id="09f55-117">外部プログラムは、JEA のネイティブ PowerShell コマンドレットまたは関数ほど細かに制約することはできません。</span><span class="sxs-lookup"><span data-stu-id="09f55-117">External programs cannot be constrained as granularly as native PowerShell cmdlets and functions in JEA.</span></span>
3. <span data-ttu-id="09f55-118">必要に応じて、コマンドレットの範囲を**制限**し、特定のパラメーターまたはパラメーター値のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="09f55-118">**Restrict** the scope of the cmdlets if necessary to only allow specific parameters or parameter values.</span></span> <span data-ttu-id="09f55-119">これは特に、ユーザーにシステムの一部のみを管理させる場合に重要です。</span><span class="sxs-lookup"><span data-stu-id="09f55-119">This is particularly important if users should only be able to manage part of a system.</span></span>
4. <span data-ttu-id="09f55-120">カスタム関数を**作成**し、複雑なコマンドや JEA では制約が難しいコマンドの代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="09f55-120">**Create** custom functions to replace complex commands or commands which are difficult to constrain in JEA.</span></span> <span data-ttu-id="09f55-121">複雑なコマンドをラップするか、追加の検証ロジックを適用する単純な関数を利用すれば、管理者やエンドユーザーにとって制御機能がさらに使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="09f55-121">A simple function that wraps a complex command or applies additional validation logic can offer additional control for admins and end-user simplicity.</span></span>
5. <span data-ttu-id="09f55-122">ユーザーや自動化サービスに許可するコマンドの範囲を**テスト**し、必要に応じて調整します。</span><span class="sxs-lookup"><span data-stu-id="09f55-122">**Test** the scoped list of allowable commands with your users and/or automation services and adjust as necessary.</span></span>

<span data-ttu-id="09f55-123">JEA セッションのコマンドは、多くの場合、管理者特権で実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-123">It is important to remember that commands in a JEA session are often run with admin (or otherwise elevated) privileges.</span></span>
<span data-ttu-id="09f55-124">JEA エンドポイントで接続ユーザーのアクセス許可の昇格が許可されないように、コマンドを慎重に選択することが重要です。</span><span class="sxs-lookup"><span data-stu-id="09f55-124">Careful selection of available commands is important to ensure the JEA endpoint does not allow the connecting user to elevate their permissions.</span></span>
<span data-ttu-id="09f55-125">以下は、制約のない状態が許された場合、悪意で使用される可能性があるコマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="09f55-125">Below are some examples of commands that can be used maliciously if allowed in an unconstrained state.</span></span>
<span data-ttu-id="09f55-126">このリストですべてを網羅しているわけではありません。最初に注意するべきものとして提示しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="09f55-126">Note that this is not an exhaustive list and should only be used as a cautionary starting point.</span></span>

### <a name="examples-of-potentially-dangerous-commands"></a><span data-ttu-id="09f55-127">危険性を含むコマンドの例</span><span class="sxs-lookup"><span data-stu-id="09f55-127">Examples of potentially dangerous commands</span></span>

<span data-ttu-id="09f55-128">リスク</span><span class="sxs-lookup"><span data-stu-id="09f55-128">Risk</span></span> | <span data-ttu-id="09f55-129">例</span><span class="sxs-lookup"><span data-stu-id="09f55-129">Example</span></span> | <span data-ttu-id="09f55-130">関連するコマンド</span><span class="sxs-lookup"><span data-stu-id="09f55-130">Related commands</span></span>
-----|---------|-----------------
<span data-ttu-id="09f55-131">JEA を迂回する管理者特権を接続ユーザーに与える</span><span class="sxs-lookup"><span data-stu-id="09f55-131">Granting the connecting user admin privileges to bypass JEA</span></span> | `Add-LocalGroupMember -Member 'CONTOSO\jdoe' -Group 'Administrators'` | <span data-ttu-id="09f55-132">`Add-ADGroupMember`、`Add-LocalGroupMember`、`net.exe`、`dsadd.exe`</span><span class="sxs-lookup"><span data-stu-id="09f55-132">`Add-ADGroupMember`, `Add-LocalGroupMember`, `net.exe`, `dsadd.exe`</span></span>
<span data-ttu-id="09f55-133">マルウェア、エクスプロイト、防御を迂回するカスタム スクリプトなど、任意のコードを実行する</span><span class="sxs-lookup"><span data-stu-id="09f55-133">Running arbitrary code, such as malware, exploits, or custom scripts to bypass protections</span></span> | `Start-Process -FilePath '\\san\share\malware.exe'` | <span data-ttu-id="09f55-134">`Start-Process`, `New-Service`, `Invoke-Item`, `Invoke-WmiMethod`, `Invoke-CimMethod`, `Invoke-Expression`, `Invoke-Command`, `New-ScheduledTask`, `Register-ScheduledJob`</span><span class="sxs-lookup"><span data-stu-id="09f55-134">`Start-Process`, `New-Service`, `Invoke-Item`, `Invoke-WmiMethod`, `Invoke-CimMethod`, `Invoke-Expression`, `Invoke-Command`, `New-ScheduledTask`, `Register-ScheduledJob`</span></span>

## <a name="create-a-role-capability-file"></a><span data-ttu-id="09f55-135">ロール機能ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="09f55-135">Create a role capability file</span></span>

<span data-ttu-id="09f55-136">[New-PSRoleCapabilityFile](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/New-PSRoleCapabilityFile) コマンドレットで新しい PowerShell ロール機能ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-136">You can create a new PowerShell role capability file with the [New-PSRoleCapabilityFile](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/New-PSRoleCapabilityFile) cmdlet.</span></span>

```powershell
New-PSRoleCapabilityFile -Path .\MyFirstJEARole.psrc
```

<span data-ttu-id="09f55-137">作成したロール機能ファイルはテキスト エディターで開き、ロールに目的のコマンドを許可するように変更できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-137">The resulting role capability file can be opened in a text editor and modified to allow the desired commands for the role.</span></span>
<span data-ttu-id="09f55-138">PowerShell ヘルプ ドキュメントには、ファイルの構成例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09f55-138">The PowerShell help documentation contains several examples of how you can configure the file.</span></span>

### <a name="allowing-powershell-cmdlets-and-functions"></a><span data-ttu-id="09f55-139">PowerShell のコマンドレットと関数を許可する</span><span class="sxs-lookup"><span data-stu-id="09f55-139">Allowing PowerShell cmdlets and functions</span></span>

<span data-ttu-id="09f55-140">PowerShell コマンドレットまたは関数の実行権限をユーザーに与えるには、VisbibleCmdlets または VisibleFunctions フィールドにコマンドレットまたは関数の名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="09f55-140">To authorize users to run PowerShell cmdlets or functions, add the cmdlet or function name to the VisbibleCmdlets or VisibleFunctions fields.</span></span>
<span data-ttu-id="09f55-141">コマンドがコマンドレットであるか、関数であるかわからない場合、`Get-Command <name>` を実行し、出力の "CommandType" プロパティを確認してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-141">If you aren't sure whether a command is a cmdlet or function, you can run `Get-Command <name>` and check the "CommandType" property in the output.</span></span>

```powershell
VisibleCmdlets = 'Restart-Computer', 'Get-NetIPAddress'
```

<span data-ttu-id="09f55-142">特定のコマンドレットまたは関数の範囲が必要以上に広いことがあります。</span><span class="sxs-lookup"><span data-stu-id="09f55-142">Sometimes the scope of a specific cmdlet or function is too broad for your users' needs.</span></span>
<span data-ttu-id="09f55-143">たとえば、DNS 管理者の場合、DNS サービスを再起動する許可だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="09f55-143">A DNS admin, for example, probably only needs access to restart the DNS service.</span></span>
<span data-ttu-id="09f55-144">テナントにセルフサービス管理ツールへのアクセスを許可するマルチテナント環境の場合、テナントが管理できるリソースをそのテナントのリソースに限定するべきです。</span><span class="sxs-lookup"><span data-stu-id="09f55-144">In a multi-tenant environment where tenants are granted access to self-service management tools, tenants should be limited to managing with their own resources.</span></span>
<span data-ttu-id="09f55-145">そのような場合、コマンドレットまたは関数から公開するパラメーターを制限できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-145">For these cases, you can restrict which parameters are exposed from the cmdlet or function.</span></span>

```powershell

VisibleCmdlets = @{ Name = 'Restart-Computer'; Parameters = @{ Name = 'Name' }}

```

<span data-ttu-id="09f55-146">さらに進んだシナリオでは、場合によっては、そのようなパラメーターに入力できる値も制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09f55-146">In more advanced scenarios, you may also need to restrict which values someone can supply to these parameters.</span></span>
<span data-ttu-id="09f55-147">ロール機能では、入力可能値のセット、または所与の入力が許可されるかどうかを判断するために評価される正規表現パターンを定義できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-147">Role capabilities let you define a set of allowed values or a regular expression pattern that is evaluated to determine if a given input is allowed.</span></span>

```powershell
VisibleCmdlets = @{ Name = 'Restart-Service'; Parameters = @{ Name = 'Name'; ValidateSet = 'Dns', 'Spooler' }},
                 @{ Name = 'Start-Website'; Parameters = @{ Name = 'Name'; ValidatePattern = 'HR_*' }}
```

> [!NOTE]
> <span data-ttu-id="09f55-148">利用できるパラメーターを制限した場合でも、[一般的な PowerShell パラメーター](https://technet.microsoft.com/library/hh847884.aspx)は常に許可されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-148">The [common PowerShell parameters](https://technet.microsoft.com/library/hh847884.aspx) are always allowed, even if you restrict the available parameters.</span></span>
> <span data-ttu-id="09f55-149">パラメーター フィールドで明示的にリストアップしないでください。</span><span class="sxs-lookup"><span data-stu-id="09f55-149">You should not explicitly list them in the Parameters field.</span></span>

<span data-ttu-id="09f55-150">下の表は、表示されるコマンドレットまたは関数をカスタマイズするさまざまな方法をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="09f55-150">The table below describes the various ways you can customize a visible cmdlet or function.</span></span>
<span data-ttu-id="09f55-151">VisibleCmdlets フィールドで下のあらゆる要素を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="09f55-151">You can mix and match any of the below in the VisibleCmdlets field.</span></span>

<span data-ttu-id="09f55-152">例</span><span class="sxs-lookup"><span data-stu-id="09f55-152">Example</span></span>                                                                                      | <span data-ttu-id="09f55-153">使用事例</span><span class="sxs-lookup"><span data-stu-id="09f55-153">Use case</span></span>
---------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------
<span data-ttu-id="09f55-154">`'My-Func'` または `@{ Name = 'My-Func' }`</span><span class="sxs-lookup"><span data-stu-id="09f55-154">`'My-Func'` or `@{ Name = 'My-Func' }`</span></span>                                                       | <span data-ttu-id="09f55-155">パラメーターに制限を適用せずに `My-Func` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="09f55-155">Allows the user to run `My-Func` without any restrictions on the parameters.</span></span>
`'MyModule\My-Func'`                                                                         | <span data-ttu-id="09f55-156">パラメーターに制限を適用せずにモジュール `MyModule` から `My-Func` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="09f55-156">Allows the user to run `My-Func` from the module `MyModule` without any restrictions on the parameters.</span></span>
`'My-*'`                                                                                     | <span data-ttu-id="09f55-157">動詞 `My` でコマンドレットまたは関数を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="09f55-157">Allows the user to run any cmdlet or function with the verb `My`.</span></span>
`'*-Func'`                                                                                   | <span data-ttu-id="09f55-158">名詞 `Func` でコマンドレットまたは関数を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="09f55-158">Allows the user to run any cmdlet or function with the noun `Func`.</span></span>
`@{ Name = 'My-Func'; Parameters = @{ Name = 'Param1'}, @{ Name = 'Param2' }}`               | <span data-ttu-id="09f55-159">`Param1` パラメーターと `Param2` パラメーターの両方または一方を指定して `My-Func` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="09f55-159">Allows the user to run `My-Func` with the `Param1` and/or `Param2` parameters.</span></span> <span data-ttu-id="09f55-160">あらゆる値をパラメーターに指定できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-160">Any value can be supplied to the parameters.</span></span>
`@{ Name = 'My-Func'; Parameters = @{ Name = 'Param1'; ValidateSet = 'Value1', 'Value2' }}`  | <span data-ttu-id="09f55-161">`Param1` パラメーターを指定して `My-Func` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="09f55-161">Allows the user to run `My-Func` with the `Param1` parameter.</span></span> <span data-ttu-id="09f55-162">"Value1" と "Value2" のみをパラメーターに指定できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-162">Only "Value1" and "Value2" can be supplied to the parameter.</span></span>
`@{ Name = 'My-Func'; Parameters = @{ Name = 'Param1'; ValidatePattern = 'contoso.*' }}`     | <span data-ttu-id="09f55-163">`Param1` パラメーターを指定して `My-Func` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="09f55-163">Allows the user to run `My-Func` with the `Param1` parameter.</span></span> <span data-ttu-id="09f55-164">"contoso" で始まる値をパラメーターに指定できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-164">Any value starting with "contoso" can be supplied to the parameter.</span></span>


> [!WARNING]
> <span data-ttu-id="09f55-165">セキュリティのベスト プラクティスとしては、表示されるコマンドレットまたは関数を定義するときは、ワイルドカードの使用は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="09f55-165">For best security practices, it is not recommended to use wildcards when defining visible cmdlets or functions.</span></span>
> <span data-ttu-id="09f55-166">代わりに、命名規則が同じ他のコマンドが意図せずに許可されるような状況を回避するために、問題のないコマンドを 1 つずつ明示的にリストアップしてください。</span><span class="sxs-lookup"><span data-stu-id="09f55-166">Instead, you should explicitly list each trusted command to ensure no other commands that share the same naming scheme are unintentionally authorized.</span></span>

<span data-ttu-id="09f55-167">ValidatePattern と ValidateSet の両方を同じコマンドレットまたは関数に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="09f55-167">You cannot apply both a ValidatePattern and ValidateSet to the same cmdlet or function.</span></span>

<span data-ttu-id="09f55-168">適用すると、ValidatePattern が ValidateSet より優先されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-168">If you do, the ValidatePattern will override the ValidateSet.</span></span>

<span data-ttu-id="09f55-169">ValidatePattern の詳細については、[この「*Hey, Scripting Guy!*](https://blogs.technet.microsoft.com/heyscriptingguy/2011/01/11/validate-powershell-parameters-before-running-the-script/)」投稿と [PowerShell 正規表現](https://technet.microsoft.com/library/hh847880.aspx)参照コンテンツをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09f55-169">For more information about ValidatePattern, check out [this *Hey, Scripting Guy!* post](https://blogs.technet.microsoft.com/heyscriptingguy/2011/01/11/validate-powershell-parameters-before-running-the-script/) and the [PowerShell Regular Expressions](https://technet.microsoft.com/library/hh847880.aspx) reference content.</span></span>

### <a name="allowing-external-commands-and-powershell-scripts"></a><span data-ttu-id="09f55-170">外部コマンドと PowerShell スクリプトを許可する</span><span class="sxs-lookup"><span data-stu-id="09f55-170">Allowing external commands and PowerShell scripts</span></span>

<span data-ttu-id="09f55-171">JEA セッションで実行可能ファイルと PowerShell スクリプト (.ps1) を実行することをユーザーに許可するには、VisibleExternalCommands フィールドに各プログラムの完全パスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09f55-171">To allow users to run executables and PowerShell scripts (.ps1) in a JEA session, you have to add the full path to each program in the VisibleExternalCommands field.</span></span>

```powershell
VisibleExternalCommands = 'C:\Windows\System32\whoami.exe', 'C:\Program Files\Contoso\Scripts\UpdateITSoftware.ps1'
```

<span data-ttu-id="09f55-172">可能であれば、権限を与える外部実行可能ファイルの代わりに、それに相当する PowerShell コマンドレット/関数を使用することが推奨されます。PowerShell コマンドレット/関数で許可するパラメーターを制御できるためです。</span><span class="sxs-lookup"><span data-stu-id="09f55-172">It is advised, where possible, to use PowerShell cmdlet/function equivalents of any external executables you authorize since you have control over which parameters are allowed with PowerShell cmdlets/functions.</span></span>

<span data-ttu-id="09f55-173">実行可能ファイルの多くでは、さまざまなパラメーターを指定することで、現在の状態の読み取りとその変更の両方が許可されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-173">Many executables allow you to both read the current state and then change it just by providing different parameters.</span></span>

<span data-ttu-id="09f55-174">たとえば、ファイル サーバーの管理者ロールで、ローカル コンピューターでホストされているネットワーク共有を確認しなければならないとします。</span><span class="sxs-lookup"><span data-stu-id="09f55-174">For example, consider the role of a file server admin who wants to check which network shares are hosted by the local machine.</span></span>
<span data-ttu-id="09f55-175">確認方法の 1 つは `net share` を使用することです。</span><span class="sxs-lookup"><span data-stu-id="09f55-175">One way to check is to use `net share`.</span></span>
<span data-ttu-id="09f55-176">ただし、net.exe の許可はとても危険です。このコマンドを利用すると、`net group Administrators unprivilegedjeauser /add` の管理者特権が簡単に得られる可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="09f55-176">However, allowing net.exe is very dangerous becuase the admin could just as easily use the command to gain admin privileges with `net group Administrators unprivilegedjeauser /add`.</span></span>
<span data-ttu-id="09f55-177">より良い方法は、[Get-SmbShare](https://technet.microsoft.com/library/jj635704.aspx) を許可することです。これで同じ結果が得られますが、範囲がはるかに限られます。</span><span class="sxs-lookup"><span data-stu-id="09f55-177">A better approach is to allow [Get-SmbShare](https://technet.microsoft.com/library/jj635704.aspx) which achieves the same result but has a much more limited scope.</span></span>

<span data-ttu-id="09f55-178">JEA セッションで外部コマンドの利用をユーザーに許可するとき、システム上のどこかに置かれている、同じような名前の (悪意のある) プログラムが代わりに実行されないように、実行可能ファイルの完全パスを常に指定してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-178">When making external commands available to users in a JEA session, always specify the complete path to the executable to ensure a similarly named (and potentially malicous) program placed elsewhere on the system does not get executed instead.</span></span>

### <a name="allowing-access-to-powershell-providers"></a><span data-ttu-id="09f55-179">PowerShell プロバイダーへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="09f55-179">Allowing access to PowerShell providers</span></span>

<span data-ttu-id="09f55-180">既定で、JEA セッションでは PowerShell プロバイダーを利用できません。</span><span class="sxs-lookup"><span data-stu-id="09f55-180">By default, no PowerShell providers are available in JEA sessions.</span></span>

<span data-ttu-id="09f55-181">この理由は主に、機密情報や構成設定が接続ユーザーに公開されるリスクを減らすことにあります。</span><span class="sxs-lookup"><span data-stu-id="09f55-181">This is primarily to reduce the risk of sensitive information and configuration settings being disclosed to the connecting user.</span></span>

<span data-ttu-id="09f55-182">必要なときに、`VisibleProviders` コマンドを利用して PowerShell プロバイダーへのアクセスを許可できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-182">When necessary, you can allow access to the PowerShell providers using the `VisibleProviders` command.</span></span>
<span data-ttu-id="09f55-183">プロバイダーの完全一覧が必要な場合、`Get-PSProvider` を実行してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-183">For a full list of providers, run `Get-PSProvider`.</span></span>

```powershell
VisibleProviders = 'Registry'
```

<span data-ttu-id="09f55-184">ファイル システム、レジストリ、証明書ストア、その他の機密プロバイダーにアクセスする必要がある単純な作業に関しては、ユーザーの代わりにプロバイダーとやりとりするカスタム関数の記述も検討してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-184">For simple tasks that require access to the file system, registry, certificate store, or other sensitive providers, you can also consider writing a custom function that works with the provider on the user's behalf.</span></span>
<span data-ttu-id="09f55-185">JEA セッションで利用できる関数、コマンドレット、外部プログラムは、JEA と同じ制約の対象になりません。既定では、あらゆるプロバイダーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="09f55-185">Functions, cmdlets, and external programs that are available in a JEA session are not subject to the same constraints as JEA -- they can access any provider by default.</span></span>
<span data-ttu-id="09f55-186">JEA エンドポイントとの間でファイルのコピーが必要な場合、[ユーザー ドライブ](session-configurations.md#user-drive)の利用も検討してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-186">Also consider using the [user drive](session-configurations.md#user-drive) when copying files to/from a JEA endpoint is required.</span></span>

### <a name="creating-custom-functions"></a><span data-ttu-id="09f55-187">カスタム関数を作成する</span><span class="sxs-lookup"><span data-stu-id="09f55-187">Creating custom functions</span></span>

<span data-ttu-id="09f55-188">ロール機能ファイルでカスタム関数を作成し、エンド ユーザーのために複雑なタスクを簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="09f55-188">You can author custom functions in a role capability file to simplify complex tasks for your end users.</span></span>
<span data-ttu-id="09f55-189">カスタム関数は、コマンドレット パラメーター値に高度な検証ロジックが必要なときにも便利です。</span><span class="sxs-lookup"><span data-stu-id="09f55-189">Custom functions are also useful when you require advanced validation logic for cmdlet parameter values.</span></span>
<span data-ttu-id="09f55-190">**FunctionDefinitions** で次のように単純な関数を記述できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-190">You can write simple functions in the **FunctionDefinitions** field:</span></span>

```powershell
VisibleFunctions = 'Get-TopProcess'

FunctionDefinitions = @{
    Name = 'Get-TopProcess'

    ScriptBlock = {
        param($Count = 10)

        Get-Process | Sort-Object -Property CPU -Descending | Microsoft.PowerShell.Utility\Select-Object -First $Count
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="09f55-191">JEA ユーザーが実行できるように、**VisibleFunctions** フィールドにカスタム関数の名前を必ず追加してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-191">Don't forget to add the name of your custom functions to the **VisibleFunctions** field so they can be run by the JEA users.</span></span>


<span data-ttu-id="09f55-192">カスタム関数の本文 (スクリプト ブロック) はシステムの既定の言語モードで実行され、JEA の言語制約の対象になりません。</span><span class="sxs-lookup"><span data-stu-id="09f55-192">The body (script block) of custom functions runs in the default language mode for the system and is not subject to JEA's language constraints.</span></span>
<span data-ttu-id="09f55-193">つまり、関数はファイル システムとレジストリにアクセスし、ロール機能ファイルに表示されないコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-193">This means that functions can access the file system and registry, and run commands that were not made visible in the role capability file.</span></span>
<span data-ttu-id="09f55-194">パラメーターを利用するとき、任意コードの実行が許可されないように、`Invoke-Expression` のようなコマンドレットにユーザー入力が直接パイプ処理されないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-194">Take care to avoid allowing arbitrary code to be run when using parameters and avoid piping user input directly into cmdlets like `Invoke-Expression`.</span></span>

<span data-ttu-id="09f55-195">上記の例では、簡潔な `Select-Object` ではなく、完全修飾モジュール名 (FQMN) `Microsoft.PowerShell.Utility\Select-Object` が使用されています。</span><span class="sxs-lookup"><span data-stu-id="09f55-195">In the above example, you will notice that the fully qualified module name (FQMN) `Microsoft.PowerShell.Utility\Select-Object` was used instead of the shorthand `Select-Object`.</span></span>
<span data-ttu-id="09f55-196">ロール機能ファイルに定義されている関数は、JEA セッションの範囲に入ります。この範囲には、JEA で作成されるプロキシ関数が含まれ、既存のコマンドが制約されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-196">Functions defined in role capability files are still subject to the scope of JEA sessions, which includes the proxy functions JEA creates to constrain existing commands.</span></span>

<span data-ttu-id="09f55-197">Select-Object は、すべての JEA セッションで既定の制約付きコマンドレットであり、オブジェクトで任意プロパティを選択することが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-197">Select-Object is a default, constrained cmdlet in all JEA sessions that doesn't allow you to select arbitrary properties on objects.</span></span>
<span data-ttu-id="09f55-198">関数で制約なしの Select-Object を使用するには、FQMN を指定し、完全な実装を明示的に要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09f55-198">To use the unconstrained Select-Object in functions, you must explicitly request the full implementation by specifying the FQMN.</span></span>
<span data-ttu-id="09f55-199">JEA セッションの制約付きコマンドレットは、関数から呼び出されるとき、PowerShell の[コマンド優先順位](https://msdn.microsoft.com/en-us/powershell/reference/3.0/microsoft.powershell.core/about/about_command_precedence)に従い、同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="09f55-199">Any constrained cmdlet in a JEA session will exhibit the same behavior when invoked from a function, in line with PowerShell's [command precedence](https://msdn.microsoft.com/en-us/powershell/reference/3.0/microsoft.powershell.core/about/about_command_precedence).</span></span>

<span data-ttu-id="09f55-200">カスタム関数をたくさん記述する場合、[PowerShell スクリプト モジュール](https://msdn.microsoft.com/en-us/library/dd878340(v=vs.85).aspx)に入れると簡単です。</span><span class="sxs-lookup"><span data-stu-id="09f55-200">If you are writing a lot of custom functions, it may be easier to put them in a [PowerShell Script Module](https://msdn.microsoft.com/en-us/library/dd878340(v=vs.85).aspx).</span></span>
<span data-ttu-id="09f55-201">その後、組み込みやサードパーティのモジュールの場合のように、VisibleFunctions フィールドを利用し、JEA セッションで関数を表示させることができます。</span><span class="sxs-lookup"><span data-stu-id="09f55-201">You can then make those functions visible in the JEA session using the VisibleFunctions field like you would with built-in and third party modules.</span></span>

## <a name="place-role-capabilities-in-a-module"></a><span data-ttu-id="09f55-202">モジュールにロール機能を配置する</span><span class="sxs-lookup"><span data-stu-id="09f55-202">Place role capabilities in a module</span></span>

<span data-ttu-id="09f55-203">PowerShell でロール機能ファイルを検出できるようにするには、ファイルを PowerShell モジュールの "RoleCapabilities" フォルダーに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09f55-203">In order for PowerShell to find a role capability file, it must be stored in a "RoleCapabilities" folder in a PowerShell module.</span></span>
<span data-ttu-id="09f55-204">モジュールは `$env:PSModulePath` 環境変数に含まれるあらゆるフォルダーに保存できますが、System32 (組み込みモジュールのために予約されています) や信頼されていない接続ユーザーがファイルを変更できる可能性があるフォルダーには保存しないでください。</span><span class="sxs-lookup"><span data-stu-id="09f55-204">The module can be stored in any folder included in the `$env:PSModulePath` environment variable, however you should not place it in System32 (reserved for built-in modules) or a folder where the untrusted, connecting users could modify the files.</span></span>
<span data-ttu-id="09f55-205">以下の例では、"Program Files" パスに *ContosoJEA* という名前の基本 PowerShell スクリプト モジュールを作成しています。</span><span class="sxs-lookup"><span data-stu-id="09f55-205">Below is an example of creating a basic PowerShell script module called *ContosoJEA* in the "Program Files" path.</span></span>

```powershell
# Create a folder for the module
$modulePath = Join-Path $env:ProgramFiles "WindowsPowerShell\Modules\ContosoJEA"
New-Item -ItemType Directory -Path $modulePath

# Create an empty script module and module manifest. At least one file in the module folder must have the same name as the folder itself.
New-Item -ItemType File -Path (Join-Path $modulePath "ContosoJEAFunctions.psm1")
New-ModuleManifest -Path (Join-Path $modulePath "ContosoJEA.psd1") -RootModule "ContosoJEAFunctions.psm1"

# Create the RoleCapabilities folder and copy in the PSRC file
$rcFolder = Join-Path $modulePath "RoleCapabilities"
New-Item -ItemType Directory $rcFolder
Copy-Item -Path .\MyFirstJEARole.psrc -Destination $rcFolder
```

<span data-ttu-id="09f55-206">PowerShell モジュール、モジュール マニフェスト、PSModulePath 環境変数の詳細については、「[Understanding a PowerShell Module](https://msdn.microsoft.com/en-us/library/dd878324.aspx)」 (PowerShell モジュールの概要) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-206">See [Understanding a PowerShell Module](https://msdn.microsoft.com/en-us/library/dd878324.aspx) for more information about PowerShell modules, module manifests, and the PSModulePath environment variable.</span></span>

## <a name="updating-role-capabilities"></a><span data-ttu-id="09f55-207">ロール機能を更新する</span><span class="sxs-lookup"><span data-stu-id="09f55-207">Updating role capabilities</span></span>


<span data-ttu-id="09f55-208">ロール機能ファイルは変更内容を保存するだけでいつでも更新できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-208">You can update a role capability file at any time by simply saving changes to the role capability file.</span></span>
<span data-ttu-id="09f55-209">ロール機能の更新後に新しく JEA セッションを起動すると、変更後の機能が反映されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-209">Any new JEA sessions started after the role capability has been updated will reflect the revised capabilities.</span></span>

<span data-ttu-id="09f55-210">そのため、ロール機能フォルダーのアクセスを制御することはとても重要となります。</span><span class="sxs-lookup"><span data-stu-id="09f55-210">This is why controlling access to the role capabilities folder is so important.</span></span>
<span data-ttu-id="09f55-211">ロール機能ファイルを変更できるユーザーは、非常に信頼できる管理者に限定してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-211">Only highly trusted administrators should be able to change role capability files.</span></span>
<span data-ttu-id="09f55-212">信頼されていないユーザーにロール機能ファイルの変更を許可すると、特権を昇格させるコマンドレットの利用を簡単に許可してしまいます。</span><span class="sxs-lookup"><span data-stu-id="09f55-212">If an untrusted user can change role capability files, they can easily give themselves access to cmdlets which allow them to elevate their privileges.</span></span>


<span data-ttu-id="09f55-213">ロール機能へのアクセスを管理者がロックダウンする場合、ローカル システムにロール機能ファイルとそれが含まれるモジュールの読み取りアクセスが与えられるようにします。</span><span class="sxs-lookup"><span data-stu-id="09f55-213">For administrators looking to lock down access to the role capabilities, ensure Local System has read access to the role capability files and containing modules.</span></span>

## <a name="how-role-capabilities-are-merged"></a><span data-ttu-id="09f55-214">ロール機能を結合する方法</span><span class="sxs-lookup"><span data-stu-id="09f55-214">How role capabilities are merged</span></span>

<span data-ttu-id="09f55-215">[セッション構成ファイル](session-configurations.md)のロール マッピングにもよりますが、ユーザーが JEA セッションに入るとき、複数のロール機能へのアクセスが与えられます。</span><span class="sxs-lookup"><span data-stu-id="09f55-215">Users can be granted access to multiple role capabilities when they enter a JEA session depending on the role mappings in the [session configuration file](session-configurations.md).</span></span>
<span data-ttu-id="09f55-216">そのとき、JEA では、ロールで許可される、*最も制限の少ない*コマンド セットがユーザーに与えられます。</span><span class="sxs-lookup"><span data-stu-id="09f55-216">When this happens, JEA tries to give the user the *most permissive* set of commands allowed by any of the roles.</span></span>

<span data-ttu-id="09f55-217">**VisibleCmdlets と VisibleFunctions**</span><span class="sxs-lookup"><span data-stu-id="09f55-217">**VisibleCmdlets and VisibleFunctions**</span></span>

<span data-ttu-id="09f55-218">最も複雑な結合ロジックがコマンドレットと関数に適用され、JEA でそのパラメーターとパラメーター値が制限されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-218">The most complex merge logic affects cmdlets and functions, which can have their parameters and parameter values limited in JEA.</span></span>

<span data-ttu-id="09f55-219">ルールは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="09f55-219">The rules are as follows:</span></span>

1. <span data-ttu-id="09f55-220">あるコマンドレットが 1 つのロールでのみ表示される場合、該当するあらゆるパラメーター制約の下でユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-220">If a cmdlet is only made visible in one role, it will be visible to the user with any applicable parameter constraints.</span></span>
2. <span data-ttu-id="09f55-221">あるコマンドレットが複数のロールで表示されるとき、そのコマンドレットで各ロールに同じ制約が与えられる場合、その制約の下でユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-221">If a cmdlet is made visible in more than one role, and each role has the same constraints on the cmdlet, the cmdlet will be visible to the user with those constraints.</span></span>
3. <span data-ttu-id="09f55-222">あるコマンドレットが複数のロールで表示されるとき、ロールごとにパラメーター セットが異なる場合、そのコマンドレットとすべてのロールで定義されているすべてのパラメーターがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-222">If a cmdlet is made visible in more than one role, and each role allows a different set of parameters, the cmdlet and all of the parameters defined across every role will be visible to the user.</span></span> <span data-ttu-id="09f55-223">1 つのロールにパラメーターの制約がない場合、すべてのパラメーターが許可されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-223">If one role doesn't have constraints on the parameters, all parameters will be allowed.</span></span>
4. <span data-ttu-id="09f55-224">あるロールであるコマンドレット パラメーターの検証セットまたは検証パターンが定義されているとき、別のロールでそのパラメーターが許可されるが、パラメーター値が制約されない場合、その検証セットまたはパターンは無視されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-224">If one role defines a validate set or validate pattern for a cmdlet parameter, and the other role allows the parameter but does not constrain the parameter values, the validate set or pattern will be ignored.</span></span>
5. <span data-ttu-id="09f55-225">複数のロールの同じコマンドレット パラメーターに 1 つの検証セットが定義されている場合、すべての検証セットのすべての値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-225">If a validate set is defined for the same cmdlet parameter in more than one role, all values from all validate sets will be allowed.</span></span>
6. <span data-ttu-id="09f55-226">複数のロールの同じコマンドレット パラメーターに 1 つの検証パターンが定義されている場合、いずれかのパターンに一致するすべての値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-226">If a validate pattern is defined for the same cmdlet parameter in more than one role, any values that match any of the patterns will be allowed.</span></span>
7. <span data-ttu-id="09f55-227">複数のロールに 1 つの検証セットが定義されているとき、別のロールで、同じコマンドレット パラメーターに 1 つの検証パターンが定義されている場合、その検証セットは無視され、残りの検証パターンにルール (6) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-227">If a validate set is defined in one or more roles, and a validate pattern is defined in another role for the same cmdlet parameter, the validate set is ignored and rule (6) applies to the remaining validate patterns.</span></span>

<span data-ttu-id="09f55-228">以下には、これらの規則に従ってロールをマージする方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="09f55-228">Below is an example of how roles are merged according to these rules:</span></span>

```powershell
# Role A Visible Cmdlets
$roleA = @{
    VisibleCmdlets = 'Get-Service',
                     @{ Name = 'Restart-Service'; Parameters = @{ Name = 'DisplayName'; ValidateSet = 'DNS Client' } }
}

# Role B Visible Cmdlets
$roleB = @{
    VisibleCmdlets = @{ Name = 'Get-Service'; Parameters = @{ Name = 'DisplayName'; ValidatePattern = 'DNS.*' } },
                     @{ Name = 'Restart-Service'; Parameters = @{ Name = 'DisplayName'; ValidateSet = 'DNS Server' } }
}

# Resulting permisisons for a user who belongs to both role A and B
# - The constraint in role B for the DisplayName parameter on Get-Service is ignored becuase of rule #4
# - The ValidateSets for Restart-Service are merged because both roles use ValidateSet on the same parameter per rule #5
$mergedAandB = @{
    VisibleCmdlets = 'Get-Service',
                     @{ Name = 'Restart-Service'; Parameters = @{ Name = 'DisplayName'; ValidateSet = 'DNS Client', 'DNS Server' } }
}
```



<span data-ttu-id="09f55-229">**VisibleExternalCommands、VisibleAliases、VisibleProviders、ScriptsToProcess**</span><span class="sxs-lookup"><span data-stu-id="09f55-229">**VisibleExternalCommands, VisibleAliases, VisibleProviders, ScriptsToProcess**</span></span>

<span data-ttu-id="09f55-230">ロール機能ファイルの他のすべてのフィールドは、許可される外部コマンド、エイリアス、プロバイダー、スタートアップ スクリプトの累積セットに単純に追加されます。</span><span class="sxs-lookup"><span data-stu-id="09f55-230">All other fields in the role capability file are simply added to a cumulative set of allowable external commands, aliases, providers, and startup scripts.</span></span>
<span data-ttu-id="09f55-231">JEA ユーザーは、1 つのロール機能で使用できるあらゆるコマンド、エイリアス、プロバイダー、スクリプトを利用できます。</span><span class="sxs-lookup"><span data-stu-id="09f55-231">Any command, alias, provider, or script available in one role capability will be available to the JEA user.</span></span>

<span data-ttu-id="09f55-232">あるロール機能からのプロバイダーと別のロール機能からのコマンドレット/関数/コマンドが組み合わされることで、本来の意図とは異なるシステム リソース アクセスが接続ユーザーに与えられるような事態が発生しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="09f55-232">Be careful to ensure that the combined set of providers from one role capability and cmdlets/functions/commands from another do not allow connecting users unintentional access to system resources.</span></span>
<span data-ttu-id="09f55-233">たとえば、あるロールで `Remove-Item` コマンドレットが許可され、別のロールで `FileSystem` プロバイダーが許可される場合、JEA ユーザーがコンピューター上のファイルを削除する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09f55-233">For example, if one role allows the `Remove-Item` cmdlet and another allows the `FileSystem` provider, you are at risk of a JEA user deleting arbitrary files on your computer.</span></span>
<span data-ttu-id="09f55-234">効果的なユーザー アクセス許可を確認する方法については、[JEA の監査に関するトピック](audit-and-report.md)に追加情報があります。</span><span class="sxs-lookup"><span data-stu-id="09f55-234">Additional information about identifying users' effective permissions can be found in the [auditing JEA topic](audit-and-report.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="09f55-235">次の手順</span><span class="sxs-lookup"><span data-stu-id="09f55-235">Next steps</span></span>

- [<span data-ttu-id="09f55-236">セッション構成ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="09f55-236">Create a session configuration file</span></span>](session-configurations.md)