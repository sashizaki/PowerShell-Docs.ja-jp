---
ms.date: 07/10/2019
keywords: JEA, PowerShell, セキュリティ
title: JEA ロール機能
ms.openlocfilehash: 5b5b5977d4fec1ed850f1146fe7c09463908651b
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "79402399"
---
# <a name="jea-role-capabilities"></a><span data-ttu-id="45781-103">JEA ロール機能</span><span class="sxs-lookup"><span data-stu-id="45781-103">JEA Role Capabilities</span></span>

<span data-ttu-id="45781-104">JEA エンドポイントを作成するときに、JEA セッションでユーザーに許可する操作を説明するロール機能を 1 つ以上定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45781-104">When creating a JEA endpoint, you need to define one or more role capabilities that describe what someone can do in a JEA session.</span></span> <span data-ttu-id="45781-105">ロール機能は、`.psrc` 拡張子を持つ PowerShell データ ファイルです。このファイルには、接続ユーザーが利用できるすべてのコマンドレット、関数、プロバイダー、外部プログラムが列挙されています。</span><span class="sxs-lookup"><span data-stu-id="45781-105">A role capability is a PowerShell data file with the `.psrc` extension that lists all the cmdlets, functions, providers, and external programs that are made available to connecting users.</span></span>

## <a name="determine-which-commands-to-allow"></a><span data-ttu-id="45781-106">許可するコマンドを決定する</span><span class="sxs-lookup"><span data-stu-id="45781-106">Determine which commands to allow</span></span>

<span data-ttu-id="45781-107">ロール機能ファイルを作成するときの最初の手順は、ユーザーが何にアクセスする必要があるかを検討することです。</span><span class="sxs-lookup"><span data-stu-id="45781-107">The first step in creating a role capability file is to consider what the users need access to.</span></span> <span data-ttu-id="45781-108">要件を集めるこのプロセスには時間がかかることがありますが、重要なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="45781-108">The requirements gathering process can take a while, but it's an important process.</span></span> <span data-ttu-id="45781-109">ユーザーに使用を許可するコマンドや関数があまりにも少ないと、仕事ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="45781-109">Giving users access to too few cmdlets and functions can prevent them from getting their job done.</span></span> <span data-ttu-id="45781-110">ユーザーに使用を許可するコマンドや関数があまりにも多すぎると、本来意図した以上の操作が可能になることがあり、セキュリティ姿勢を弱めることになります。</span><span class="sxs-lookup"><span data-stu-id="45781-110">Allowing access to too many cmdlets and functions can allow users to do more than you intended and weaken your security stance.</span></span>

<span data-ttu-id="45781-111">このプロセスをどのように進めるかは、組織と目標によって決まります。</span><span class="sxs-lookup"><span data-stu-id="45781-111">How you go about this process depends on your organization and goals.</span></span> <span data-ttu-id="45781-112">次のヒントが役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="45781-112">The following tips can help ensure you're on the right path.</span></span>

1. <span data-ttu-id="45781-113">仕事を行うためにユーザーが使用しているコマンドを**確認**します。</span><span class="sxs-lookup"><span data-stu-id="45781-113">**Identify** the commands users are using to get their jobs done.</span></span> <span data-ttu-id="45781-114">たとえば、IT スタッフに調査を行ったり、自動化スクリプトを調べたり、PowerShell セッションのトランスクリプトとログを分析したりします。</span><span class="sxs-lookup"><span data-stu-id="45781-114">This may involve surveying IT staff, checking automation scripts, or analyzing PowerShell session transcripts and logs.</span></span>
2. <span data-ttu-id="45781-115">可能な限り、コマンド ライン ツールで行っていたことを PowerShell の同じ操作に**更新**し、最良の監査と JEA カスタマイズを実現します。</span><span class="sxs-lookup"><span data-stu-id="45781-115">**Update** use of command-line tools to PowerShell equivalents, where possible, for the best auditing and JEA customization experience.</span></span> <span data-ttu-id="45781-116">外部プログラムは、JEA のネイティブ PowerShell コマンドレットまたは関数ほど細かに制約することはできません。</span><span class="sxs-lookup"><span data-stu-id="45781-116">External programs can't be constrained as granularly as native PowerShell cmdlets and functions in JEA.</span></span>
3. <span data-ttu-id="45781-117">コマンドレットの範囲を**制限**し、特定のパラメーターまたはパラメーター値のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="45781-117">**Restrict** the scope of the cmdlets to only allow specific parameters or parameter values.</span></span> <span data-ttu-id="45781-118">これは特に、ユーザーがシステムの一部のみを管理する場合に重要です。</span><span class="sxs-lookup"><span data-stu-id="45781-118">This is especially important if users should manage only part of a system.</span></span>
4. <span data-ttu-id="45781-119">カスタム関数を**作成**し、複雑なコマンドや JEA では制約が難しいコマンドの代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="45781-119">**Create** custom functions to replace complex commands or commands that are difficult to constrain in JEA.</span></span> <span data-ttu-id="45781-120">複雑なコマンドをラップするか、追加の検証ロジックを適用する単純な関数を利用すれば、管理者やエンドユーザーにとって制御機能がさらに使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="45781-120">A simple function that wraps a complex command or applies additional validation logic can offer additional control for admins and end-user simplicity.</span></span>
5. <span data-ttu-id="45781-121">ユーザーや自動化サービスに許可するコマンドの範囲を**テスト**し、必要に応じて調整します。</span><span class="sxs-lookup"><span data-stu-id="45781-121">**Test** the scoped list of allowable commands with your users or automation services, and adjust as necessary.</span></span>

### <a name="examples-of-potentially-dangerous-commands"></a><span data-ttu-id="45781-122">危険性を含むコマンドの例</span><span class="sxs-lookup"><span data-stu-id="45781-122">Examples of potentially dangerous commands</span></span>

<span data-ttu-id="45781-123">JEA エンドポイントでユーザーのアクセス許可の昇格が許可されないように、コマンドを慎重に選択することが重要です。</span><span class="sxs-lookup"><span data-stu-id="45781-123">Careful selection of commands is important to ensure the JEA endpoint doesn't allow the user to elevate their permissions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45781-124">JEA セッションでユーザーの successCommands に必要な重要な情報は、多くの場合、昇格された特権で実行されます。</span><span class="sxs-lookup"><span data-stu-id="45781-124">Essential information required for user successCommands in a JEA session are often run with elevated privileges.</span></span>

<span data-ttu-id="45781-125">次の表に、制約のない状態が許された場合、悪意で使用される可能性があるコマンドの例を示します。</span><span class="sxs-lookup"><span data-stu-id="45781-125">The following table contains examples of commands that can be used maliciously if allowed in an unconstrained state.</span></span> <span data-ttu-id="45781-126">このリストですべてを網羅しているわけではありません。最初に注意するべきものとして提示しているにすぎません。</span><span class="sxs-lookup"><span data-stu-id="45781-126">This isn't an exhaustive list and should only be used as a cautionary starting point.</span></span>

|                                            <span data-ttu-id="45781-127">リスク</span><span class="sxs-lookup"><span data-stu-id="45781-127">Risk</span></span>                                            |                                <span data-ttu-id="45781-128">例</span><span class="sxs-lookup"><span data-stu-id="45781-128">Example</span></span>                                |                                                                              <span data-ttu-id="45781-129">関連するコマンド</span><span class="sxs-lookup"><span data-stu-id="45781-129">Related commands</span></span>                                                                              |
| ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="45781-130">JEA を迂回する管理者特権を接続ユーザーに与える</span><span class="sxs-lookup"><span data-stu-id="45781-130">Granting the connecting user admin privileges to bypass JEA</span></span>                                | `Add-LocalGroupMember -Member 'CONTOSO\jdoe' -Group 'Administrators'` | <span data-ttu-id="45781-131">`Add-ADGroupMember`、`Add-LocalGroupMember`、`net.exe`, `dsadd.exe`</span><span class="sxs-lookup"><span data-stu-id="45781-131">`Add-ADGroupMember`, `Add-LocalGroupMember`, `net.exe`, `dsadd.exe`</span></span>                                                                                                        |
| <span data-ttu-id="45781-132">マルウェア、エクスプロイト、防御を迂回するカスタム スクリプトなど、任意のコードを実行する</span><span class="sxs-lookup"><span data-stu-id="45781-132">Running arbitrary code, such as malware, exploits, or custom scripts to bypass protections</span></span> | `Start-Process -FilePath '\\san\share\malware.exe'`                   | <span data-ttu-id="45781-133">`Start-Process`, `New-Service`, `Invoke-Item`, `Invoke-WmiMethod`, `Invoke-CimMethod`, `Invoke-Expression`, `Invoke-Command`, `New-ScheduledTask`, `Register-ScheduledJob`</span><span class="sxs-lookup"><span data-stu-id="45781-133">`Start-Process`, `New-Service`, `Invoke-Item`, `Invoke-WmiMethod`, `Invoke-CimMethod`, `Invoke-Expression`, `Invoke-Command`, `New-ScheduledTask`, `Register-ScheduledJob`</span></span> |

## <a name="create-a-role-capability-file"></a><span data-ttu-id="45781-134">ロール機能ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="45781-134">Create a role capability file</span></span>

<span data-ttu-id="45781-135">[New-PSRoleCapabilityFile](/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-6) コマンドレットで新しい PowerShell ロール機能ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="45781-135">You can create a new PowerShell role capability file with the [New-PSRoleCapabilityFile](/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-6) cmdlet.</span></span>

```powershell
New-PSRoleCapabilityFile -Path .\MyFirstJEARole.psrc
```

<span data-ttu-id="45781-136">作成したロール機能ファイルを編集して、ロールに必要なコマンドを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45781-136">The resulting role capability file should be edited to allow the commands required for the role.</span></span> <span data-ttu-id="45781-137">PowerShell ヘルプ ドキュメントには、ファイルの構成例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45781-137">The PowerShell help documentation contains several examples of how you can configure the file.</span></span>

### <a name="allowing-powershell-cmdlets-and-functions"></a><span data-ttu-id="45781-138">PowerShell のコマンドレットと関数を許可する</span><span class="sxs-lookup"><span data-stu-id="45781-138">Allowing PowerShell cmdlets and functions</span></span>

<span data-ttu-id="45781-139">PowerShell コマンドレットまたは関数の実行権限をユーザーに与えるには、VisibleCmdlets または VisibleFunctions フィールドにコマンドレットまたは関数の名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="45781-139">To authorize users to run PowerShell cmdlets or functions, add the cmdlet or function name to the VisibleCmdlets or VisibleFunctions fields.</span></span> <span data-ttu-id="45781-140">コマンドがコマンドレットであるか、関数であるかわからない場合、`Get-Command <name>` を実行し、出力の **CommandType** プロパティを確認してください。</span><span class="sxs-lookup"><span data-stu-id="45781-140">If you aren't sure whether a command is a cmdlet or function, you can run `Get-Command <name>` and check the **CommandType** property in the output.</span></span>

```powershell
VisibleCmdlets = 'Restart-Computer', 'Get-NetIPAddress'
```

<span data-ttu-id="45781-141">特定のコマンドレットまたは関数の範囲が必要以上に広いことがあります。</span><span class="sxs-lookup"><span data-stu-id="45781-141">Sometimes the scope of a specific cmdlet or function is too broad for your users' needs.</span></span> <span data-ttu-id="45781-142">たとえば、DNS 管理者の場合、DNS サービスを再起動する許可だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="45781-142">A DNS admin, for example, probably only needs access to restart the DNS service.</span></span> <span data-ttu-id="45781-143">マルチテナント環境では、テナントにセルフサービス管理ツールがあります。</span><span class="sxs-lookup"><span data-stu-id="45781-143">In multi-tenant environments, tenants have access to self-service management tools.</span></span> <span data-ttu-id="45781-144">テナントが管理できるリソースは、そのテナントのリソースに限定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45781-144">Tenants should be limited to managing their own resources.</span></span> <span data-ttu-id="45781-145">そのような場合、コマンドレットまたは関数から公開するパラメーターを制限できます。</span><span class="sxs-lookup"><span data-stu-id="45781-145">For these cases, you can restrict which parameters are exposed from the cmdlet or function.</span></span>

```powershell
VisibleCmdlets = @{ Name = 'Restart-Computer'; Parameters = @{ Name = 'Name' }}
```

<span data-ttu-id="45781-146">さらに進んだシナリオでは、ユーザーがこれらのパラメーターに使用できる値も制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45781-146">In more advanced scenarios, you may also need to restrict the values a user may use with these parameters.</span></span> <span data-ttu-id="45781-147">ロール機能では、許可する入力を決定する一連の値または正規表現パターンを定義できます。</span><span class="sxs-lookup"><span data-stu-id="45781-147">Role capabilities let you define a set of values or a regular expression pattern that determine what input is allowed.</span></span>

```powershell
VisibleCmdlets = @{ Name = 'Restart-Service'; Parameters = @{ Name = 'Name'; ValidateSet = 'Dns', 'Spooler' }},
                 @{ Name = 'Start-Website'; Parameters = @{ Name = 'Name'; ValidatePattern = 'HR_*' }}
```

> [!NOTE]
> <span data-ttu-id="45781-148">利用できるパラメーターを制限した場合でも、[一般的な PowerShell パラメーター](/powershell/module/microsoft.powershell.core/about/about_commonparameters)は常に許可されます。</span><span class="sxs-lookup"><span data-stu-id="45781-148">The [common PowerShell parameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters) are always allowed, even if you restrict the available parameters.</span></span>
> <span data-ttu-id="45781-149">パラメーター フィールドで明示的にリストアップしないでください。</span><span class="sxs-lookup"><span data-stu-id="45781-149">You should not explicitly list them in the Parameters field.</span></span>

<span data-ttu-id="45781-150">下の表は、表示されるコマンドレットまたは関数をカスタマイズするさまざまな方法をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="45781-150">The table below describes the various ways you can customize a visible cmdlet or function.</span></span>
<span data-ttu-id="45781-151">**VisibleCmdlets** フィールドで下のあらゆる要素を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="45781-151">You can mix and match any of the below in the **VisibleCmdlets** field.</span></span>

|                                           <span data-ttu-id="45781-152">例</span><span class="sxs-lookup"><span data-stu-id="45781-152">Example</span></span>                                           |                                                             <span data-ttu-id="45781-153">使用事例</span><span class="sxs-lookup"><span data-stu-id="45781-153">Use case</span></span>                                                              |
| ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="45781-154">`'My-Func'` または `@{ Name = 'My-Func' }`</span><span class="sxs-lookup"><span data-stu-id="45781-154">`'My-Func'` or `@{ Name = 'My-Func' }`</span></span>                                                      | <span data-ttu-id="45781-155">パラメーターに制限を適用せずに `My-Func` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="45781-155">Allows the user to run `My-Func` without any restrictions on the parameters.</span></span>                                                      |
| `'MyModule\My-Func'`                                                                        | <span data-ttu-id="45781-156">パラメーターに制限を適用せずにモジュール `My-Func` から `MyModule` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="45781-156">Allows the user to run `My-Func` from the module `MyModule` without any restrictions on the parameters.</span></span>                           |
| `'My-*'`                                                                                    | <span data-ttu-id="45781-157">動詞 `My` でコマンドレットまたは関数を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="45781-157">Allows the user to run any cmdlet or function with the verb `My`.</span></span>                                                                 |
| `'*-Func'`                                                                                  | <span data-ttu-id="45781-158">名詞 `Func` でコマンドレットまたは関数を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="45781-158">Allows the user to run any cmdlet or function with the noun `Func`.</span></span>                                                               |
| `@{ Name = 'My-Func'; Parameters = @{ Name = 'Param1'}, @{ Name = 'Param2' }}`              | <span data-ttu-id="45781-159">`My-Func` パラメーターと `Param1` パラメーターを指定して `Param2` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="45781-159">Allows the user to run `My-Func` with the `Param1` and `Param2` parameters.</span></span> <span data-ttu-id="45781-160">あらゆる値をパラメーターに指定できます。</span><span class="sxs-lookup"><span data-stu-id="45781-160">Any value can be supplied to the parameters.</span></span>          |
| `@{ Name = 'My-Func'; Parameters = @{ Name = 'Param1'; ValidateSet = 'Value1', 'Value2' }}` | <span data-ttu-id="45781-161">`My-Func` パラメーターを指定して `Param1` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="45781-161">Allows the user to run `My-Func` with the `Param1` parameter.</span></span> <span data-ttu-id="45781-162">"Value1" と "Value2" のみをパラメーターに指定できます。</span><span class="sxs-lookup"><span data-stu-id="45781-162">Only "Value1" and "Value2" can be supplied to the parameter.</span></span>        |
| `@{ Name = 'My-Func'; Parameters = @{ Name = 'Param1'; ValidatePattern = 'contoso.*' }}`    | <span data-ttu-id="45781-163">`My-Func` パラメーターを指定して `Param1` を実行することをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="45781-163">Allows the user to run `My-Func` with the `Param1` parameter.</span></span> <span data-ttu-id="45781-164">"contoso" で始まる値をパラメーターに指定できます。</span><span class="sxs-lookup"><span data-stu-id="45781-164">Any value starting with "contoso" can be supplied to the parameter.</span></span> |

> [!WARNING]
> <span data-ttu-id="45781-165">セキュリティのベスト プラクティスとしては、表示されるコマンドレットまたは関数を定義するときは、ワイルドカードの使用は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="45781-165">For best security practices, it is not recommended to use wildcards when defining visible cmdlets or functions.</span></span> <span data-ttu-id="45781-166">代わりに、命名規則が同じ他のコマンドが意図せずに許可されるような状況を回避するために、問題のないコマンドを 1 つずつ明示的にリストアップしてください。</span><span class="sxs-lookup"><span data-stu-id="45781-166">Instead, you should explicitly list each trusted command to ensure no other commands that share the same naming scheme are unintentionally authorized.</span></span>

<span data-ttu-id="45781-167">**ValidatePattern** と **ValidateSet** の両方を同じコマンドレットまたは関数に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="45781-167">You can't apply both a **ValidatePattern** and **ValidateSet** to the same cmdlet or function.</span></span>

<span data-ttu-id="45781-168">適用すると、**ValidatePattern** によって **ValidateSet** がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="45781-168">If you do, the **ValidatePattern** overrides the **ValidateSet**.</span></span>

<span data-ttu-id="45781-169">**ValidatePattern** の詳細については、[この「*Hey, Scripting Guy!* 」投稿](https://devblogs.microsoft.com/scripting/validate-powershell-parameters-before-running-the-script/)と [PowerShell 正規表現](/powershell/module/microsoft.powershell.core/about/about_regular_expressions)参照コンテンツをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45781-169">For more information about **ValidatePattern**, check out [this *Hey, Scripting Guy!* post](https://devblogs.microsoft.com/scripting/validate-powershell-parameters-before-running-the-script/) and the [PowerShell Regular Expressions](/powershell/module/microsoft.powershell.core/about/about_regular_expressions) reference content.</span></span>

### <a name="allowing-external-commands-and-powershell-scripts"></a><span data-ttu-id="45781-170">外部コマンドと PowerShell スクリプトを許可する</span><span class="sxs-lookup"><span data-stu-id="45781-170">Allowing external commands and PowerShell scripts</span></span>

<span data-ttu-id="45781-171">JEA セッションで実行可能ファイルと PowerShell スクリプト (.ps1) を実行することをユーザーに許可するには、**VisibleExternalCommands** フィールドに各プログラムの完全パスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45781-171">To allow users to run executables and PowerShell scripts (.ps1) in a JEA session, you have to add the full path to each program in the **VisibleExternalCommands** field.</span></span>

```powershell
VisibleExternalCommands = 'C:\Windows\System32\whoami.exe', 'C:\Program Files\Contoso\Scripts\UpdateITSoftware.ps1'
```

<span data-ttu-id="45781-172">可能であれば、PowerShell コマンドレットおよび関数で許可されたパラメーターを制御できるため、権限を与える外部実行可能ファイルに対して相当する PowerShell コマンドレットまたは関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="45781-172">Where possible, to use PowerShell cmdlet or function equivalents for any external executables you authorize since you have control over the parameters allowed with PowerShell cmdlets and functions.</span></span>

<span data-ttu-id="45781-173">実行可能ファイルの多くでは、さまざまなパラメーターを指定することで、現在の状態を読み取ってからそれを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="45781-173">Many executables allow you to read the current state and then change it by providing different parameters.</span></span>

<span data-ttu-id="45781-174">たとえば、システムでホストされているネットワーク共有を管理するファイル サーバー管理者ロールを考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="45781-174">For example, consider the role of a file server admin that manages network shares hosted on a system.</span></span> <span data-ttu-id="45781-175">共有の管理方法の 1 つは、`net share` を使用することです。</span><span class="sxs-lookup"><span data-stu-id="45781-175">One way of managing shares is to use `net share`.</span></span> <span data-ttu-id="45781-176">しかし、**net.exe** を利用すると、`net group Administrators unprivilegedjeauser /add` の管理者特権が簡単に得られる可能性があるため、このコマンドを許可するのは危険です。</span><span class="sxs-lookup"><span data-stu-id="45781-176">However, allowing **net.exe** is dangerous because the user could use the command to gain admin privileges with `net group Administrators unprivilegedjeauser /add`.</span></span> <span data-ttu-id="45781-177">より安全な方法は、[Get-SmbShare](/powershell/module/smbshare/get-smbshare) を許可することです。これで同じ結果が得られますが、範囲がはるかに限られます。</span><span class="sxs-lookup"><span data-stu-id="45781-177">A more secure option is to allow [Get-SmbShare](/powershell/module/smbshare/get-smbshare), which achieves the same result but has a much more limited scope.</span></span>

<span data-ttu-id="45781-178">JEA セッションで外部コマンドの利用をユーザーに許可するときは、実行可能ファイルの完全パスを常に指定してください。</span><span class="sxs-lookup"><span data-stu-id="45781-178">When making external commands available to users in a JEA session, always specify the complete path to the executable.</span></span> <span data-ttu-id="45781-179">これによりシステム上のどこかに置かれている、同じような名前の悪意のあるプログラムが実行されるのを防止します。</span><span class="sxs-lookup"><span data-stu-id="45781-179">This prevents the execution of similarly named and potentially malicious programs located elsewhere on the system.</span></span>

### <a name="allowing-access-to-powershell-providers"></a><span data-ttu-id="45781-180">PowerShell プロバイダーへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="45781-180">Allowing access to PowerShell providers</span></span>

<span data-ttu-id="45781-181">既定で、JEA セッションでは PowerShell プロバイダーを利用できません。</span><span class="sxs-lookup"><span data-stu-id="45781-181">By default, no PowerShell providers are available in JEA sessions.</span></span> <span data-ttu-id="45781-182">これにより機密情報や構成設定が接続ユーザーに公開されるリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="45781-182">This reduces the risk of sensitive information and configuration settings being disclosed to the connecting user.</span></span>

<span data-ttu-id="45781-183">必要なときに、`VisibleProviders` コマンドを利用して PowerShell プロバイダーへのアクセスを許可できます。</span><span class="sxs-lookup"><span data-stu-id="45781-183">When necessary, you can allow access to the PowerShell providers using the `VisibleProviders` command.</span></span> <span data-ttu-id="45781-184">プロバイダーの完全一覧が必要な場合、`Get-PSProvider` を実行してください。</span><span class="sxs-lookup"><span data-stu-id="45781-184">For a full list of providers, run `Get-PSProvider`.</span></span>

```powershell
VisibleProviders = 'Registry'
```

<span data-ttu-id="45781-185">ファイル システム、レジストリ、証明書ストア、その他の機密プロバイダーにアクセスする必要がある単純な作業に関しては、ユーザーの代わりにプロバイダーとやりとりするカスタム関数の記述を検討してください。</span><span class="sxs-lookup"><span data-stu-id="45781-185">For simple tasks that require access to the file system, registry, certificate store, or other sensitive providers, consider writing a custom function that works with the provider on the user's behalf.</span></span> <span data-ttu-id="45781-186">JEA セッションで利用できる関数、コマンドレット、外部プログラムは、JEA と同じ制約の対象になりません。</span><span class="sxs-lookup"><span data-stu-id="45781-186">The functions, cmdlets, and external programs available in a JEA session aren't subject to the same constraints as JEA.</span></span> <span data-ttu-id="45781-187">既定では、これらはあらゆるプロバイダーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="45781-187">They can access any provider by default.</span></span> <span data-ttu-id="45781-188">JEA エンドポイントとの間でファイルのコピーが必要な場合、[ユーザー ドライブ](session-configurations.md#user-drive)の利用も検討してください。</span><span class="sxs-lookup"><span data-stu-id="45781-188">Also consider using the [user drive](session-configurations.md#user-drive) when copying files to or from a JEA endpoint is required.</span></span>

### <a name="creating-custom-functions"></a><span data-ttu-id="45781-189">カスタム関数を作成する</span><span class="sxs-lookup"><span data-stu-id="45781-189">Creating custom functions</span></span>

<span data-ttu-id="45781-190">ロール機能ファイルでカスタム関数を作成し、エンド ユーザーのために複雑なタスクを簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="45781-190">You can author custom functions in a role capability file to simplify complex tasks for your end users.</span></span> <span data-ttu-id="45781-191">カスタム関数は、コマンドレット パラメーター値に高度な検証ロジックが必要なときにも便利です。</span><span class="sxs-lookup"><span data-stu-id="45781-191">Custom functions are also useful when you require advanced validation logic for cmdlet parameter values.</span></span> <span data-ttu-id="45781-192">**FunctionDefinitions** で次のように単純な関数を記述できます。</span><span class="sxs-lookup"><span data-stu-id="45781-192">You can write simple functions in the **FunctionDefinitions** field:</span></span>

```powershell
VisibleFunctions = 'Get-TopProcess'

FunctionDefinitions = @{
    Name = 'Get-TopProcess'

    ScriptBlock = {
        param($Count = 10)

        Get-Process | Sort-Object -Property CPU -Descending |
            Microsoft.PowerShell.Utility\Select-Object -First $Count
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="45781-193">JEA ユーザーが実行できるように、**VisibleFunctions** フィールドにカスタム関数の名前を必ず追加してください。</span><span class="sxs-lookup"><span data-stu-id="45781-193">Don't forget to add the name of your custom functions to the **VisibleFunctions** field so they can be run by the JEA users.</span></span>

<span data-ttu-id="45781-194">カスタム関数の本文 (スクリプト ブロック) はシステムの既定の言語モードで実行され、JEA の言語制約の対象になりません。</span><span class="sxs-lookup"><span data-stu-id="45781-194">The body (script block) of custom functions runs in the default language mode for the system and isn't subject to JEA's language constraints.</span></span> <span data-ttu-id="45781-195">つまり、関数はファイル システムとレジストリにアクセスし、ロール機能ファイルに表示されないコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="45781-195">This means that functions can access the file system and registry, and run commands that weren't made visible in the role capability file.</span></span> <span data-ttu-id="45781-196">パラメーターを使用するときは、任意のコードを実行しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="45781-196">Take care to avoid running arbitrary code when using parameters.</span></span> <span data-ttu-id="45781-197">`Invoke-Expression` のようなコマンドレットにユーザー入力がパイプ処理されないようにします。</span><span class="sxs-lookup"><span data-stu-id="45781-197">Avoid piping user input directly into cmdlets like `Invoke-Expression`.</span></span>

<span data-ttu-id="45781-198">上記の例では、簡潔な `Microsoft.PowerShell.Utility\Select-Object` ではなく、完全修飾モジュール名 (FQMN) `Select-Object` が使用されていることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="45781-198">In the above example, notice that the fully qualified module name (FQMN) `Microsoft.PowerShell.Utility\Select-Object` was used instead of the shorthand `Select-Object`.</span></span>
<span data-ttu-id="45781-199">ロール機能ファイルに定義されている関数は、JEA セッションの範囲に入ります。この範囲には、JEA で作成されるプロキシ関数が含まれ、既存のコマンドが制約されます。</span><span class="sxs-lookup"><span data-stu-id="45781-199">Functions defined in role capability files are still subject to the scope of JEA sessions, which includes the proxy functions JEA creates to constrain existing commands.</span></span>

<span data-ttu-id="45781-200">既定では、`Select-Object` は、オブジェクト上で任意プロパティを選択することができない、すべての JEA セッションの制約付きコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="45781-200">By default, `Select-Object` is a constrained cmdlet in all JEA sessions that doesn't allow the selection of arbitrary properties on objects.</span></span> <span data-ttu-id="45781-201">関数で制約なしの `Select-Object` を使用するには、FQMN を使用して、完全な実装を明示的に要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45781-201">To use the unconstrained `Select-Object` in functions, you must explicitly request the full implementation using the FQMN.</span></span> <span data-ttu-id="45781-202">JEA セッションの制約付きコマンドレットはすべて、関数から呼び出されるときに同じ制約があります。</span><span class="sxs-lookup"><span data-stu-id="45781-202">Any constrained cmdlet in a JEA session has the same constraints when invoked from a function.</span></span> <span data-ttu-id="45781-203">詳細については、「[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)」(コマンドの優先順位について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45781-203">For more information, see [about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence).</span></span>

<span data-ttu-id="45781-204">複数のカスタム関数を記述する場合、それらを PowerShell スクリプト モジュールに入れると利便性が高まります。</span><span class="sxs-lookup"><span data-stu-id="45781-204">If you're writing several custom functions, it's more convenient to put them in a PowerShell script module.</span></span> <span data-ttu-id="45781-205">組み込みやサードパーティのモジュールの場合のように、**VisibleFunctions** フィールドを利用し、JEA セッションでこれらの関数を表示させることができます。</span><span class="sxs-lookup"><span data-stu-id="45781-205">You make those functions visible in the JEA session using the **VisibleFunctions** field like you would with built-in and third-party modules.</span></span>

<span data-ttu-id="45781-206">JEA セッションでタブ補完が正しく機能するためには、`tabexpansion2`VisibleFunctions**リストに組み込み関数** を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="45781-206">For tab completion to work properly in JEA sessions you must include the built-in function `tabexpansion2` in the **VisibleFunctions** list.</span></span>

## <a name="make-the-role-capabilities-available-to-a-configuration"></a><span data-ttu-id="45781-207">構成でロール機能を使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="45781-207">Make the role capabilities available to a configuration</span></span>

<span data-ttu-id="45781-208">PowerShell 6 より前の場合、PowerShell でロール機能ファイルを検出できるようにするには、ファイルを PowerShell モジュールの **RoleCapabilities** フォルダーに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45781-208">Prior to PowerShell 6, for PowerShell to find a role capability file it must be stored in a **RoleCapabilities** folder in a PowerShell module.</span></span> <span data-ttu-id="45781-209">モジュールは `$env:PSModulePath` 環境変数に含まれるあらゆるフォルダーに保存できますが、`$env:SystemRoot\System32` や、信頼されていないユーザーがファイルを変更できる可能性があるフォルダーには配置しないでください。</span><span class="sxs-lookup"><span data-stu-id="45781-209">The module can be stored in any folder included in the `$env:PSModulePath` environment variable, however you shouldn't place it in `$env:SystemRoot\System32` or a folder where untrusted users could modify the files.</span></span>

<span data-ttu-id="45781-210">次の例では、ロール機能ファイルをホストするための **ContosoJEA** という名前の PowerShell スクリプト モジュールを `$env:ProgramFiles` パスに作成します。</span><span class="sxs-lookup"><span data-stu-id="45781-210">The following example creates a PowerShell script module called **ContosoJEA** in the `$env:ProgramFiles` path to host the role capabilities file.</span></span>

```powershell
# Create a folder for the module
$modulePath = Join-Path $env:ProgramFiles "WindowsPowerShell\Modules\ContosoJEA"
New-Item -ItemType Directory -Path $modulePath

# Create an empty script module and module manifest.
# At least one file in the module folder must have the same name as the folder itself.
New-Item -ItemType File -Path (Join-Path $modulePath "ContosoJEAFunctions.psm1")
New-ModuleManifest -Path (Join-Path $modulePath "ContosoJEA.psd1") -RootModule "ContosoJEAFunctions.psm1"

# Create the RoleCapabilities folder and copy in the PSRC file
$rcFolder = Join-Path $modulePath "RoleCapabilities"
New-Item -ItemType Directory $rcFolder
Copy-Item -Path .\MyFirstJEARole.psrc -Destination $rcFolder
```

<span data-ttu-id="45781-211">PowerShell モジュールの詳細については、[PowerShell モジュールの概要](/powershell/scripting/developer/windows-powershell)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45781-211">For more information about PowerShell modules, see [Understanding a PowerShell Module](/powershell/scripting/developer/windows-powershell).</span></span>

<span data-ttu-id="45781-212">PowerShell 6 以降では、**RoleDefinitions** プロパティがセッション構成ファイルに追加されました。</span><span class="sxs-lookup"><span data-stu-id="45781-212">Starting in PowerShell 6, the **RoleDefinitions** property was added to the session configuration file.</span></span> <span data-ttu-id="45781-213">このプロパティを使用すると、使用するロールの定義のロール構成ファイルの場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="45781-213">This property lets you specify the location of a role configuration file for your role definition.</span></span> <span data-ttu-id="45781-214">「[New-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile)」に記載されている例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45781-214">See the examples in [New-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile).</span></span>

## <a name="updating-role-capabilities"></a><span data-ttu-id="45781-215">ロール機能を更新する</span><span class="sxs-lookup"><span data-stu-id="45781-215">Updating role capabilities</span></span>

<span data-ttu-id="45781-216">ロール機能ファイルを編集していつでも設定を更新できます。</span><span class="sxs-lookup"><span data-stu-id="45781-216">You can edit a role capability file to update the settings at any time.</span></span> <span data-ttu-id="45781-217">ロール機能の更新後に新しく JEA セッションを起動すると、変更後の機能が反映されます。</span><span class="sxs-lookup"><span data-stu-id="45781-217">Any new JEA sessions started after the role capability has been updated will reflect the revised capabilities.</span></span>

<span data-ttu-id="45781-218">そのため、ロール機能フォルダーのアクセスを制御することはとても重要となります。</span><span class="sxs-lookup"><span data-stu-id="45781-218">This is why controlling access to the role capabilities folder is so important.</span></span> <span data-ttu-id="45781-219">ロール機能ファイルの変更は、非常に信頼できる管理者にのみ許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45781-219">Only highly trusted administrators should be allowed to change role capability files.</span></span> <span data-ttu-id="45781-220">信頼されていないユーザーにロール機能ファイルの変更を許可すると、特権を昇格させるコマンドレットの利用を簡単に許可してしまいます。</span><span class="sxs-lookup"><span data-stu-id="45781-220">If an untrusted user can change role capability files, they can easily give themselves access to cmdlets that allow them to elevate their privileges.</span></span>

<span data-ttu-id="45781-221">ロール機能へのアクセスを管理者がロックダウンする場合、ローカル システムにロール機能ファイルとそれが含まれるモジュールの読み取りアクセスが与えられるようにします。</span><span class="sxs-lookup"><span data-stu-id="45781-221">For administrators looking to lock down access to the role capabilities, ensure Local System has read access to the role capability files and containing modules.</span></span>

## <a name="how-role-capabilities-are-merged"></a><span data-ttu-id="45781-222">ロール機能を結合する方法</span><span class="sxs-lookup"><span data-stu-id="45781-222">How role capabilities are merged</span></span>

<span data-ttu-id="45781-223">ユーザーは、JEA セッションに入るときに、[セッション構成ファイル](session-configurations.md)の一致するすべてのロール機能へのアクセスが与えられます。</span><span class="sxs-lookup"><span data-stu-id="45781-223">Users are granted access to all matching role capabilities in the [session configuration file](session-configurations.md) when they enter a JEA session.</span></span> <span data-ttu-id="45781-224">JEA では、ロールで許可される、最も制限の少ないコマンド セットをユーザーに与えようとします。</span><span class="sxs-lookup"><span data-stu-id="45781-224">JEA tries to give the user the most permissive set of commands allowed by any of the roles.</span></span>

### <a name="visiblecmdlets-and-visiblefunctions"></a><span data-ttu-id="45781-225">VisibleCmdlets と VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="45781-225">VisibleCmdlets and VisibleFunctions</span></span>

<span data-ttu-id="45781-226">最も複雑な結合ロジックがコマンドレットと関数に適用され、JEA でそのパラメーターとパラメーター値が制限されます。</span><span class="sxs-lookup"><span data-stu-id="45781-226">The most complex merge logic affects cmdlets and functions, which can have their parameters and parameter values limited in JEA.</span></span>

<span data-ttu-id="45781-227">ルールは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="45781-227">The rules are as follows:</span></span>

1. <span data-ttu-id="45781-228">あるコマンドレットが 1 つのロールでのみ表示される場合、該当するあらゆるパラメーター制約の下でユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45781-228">If a cmdlet is only made visible in one role, it is visible to the user with any applicable parameter constraints.</span></span>
2. <span data-ttu-id="45781-229">あるコマンドレットが複数のロールで表示されるとき、そのコマンドレットで各ロールに同じ制約が与えられる場合、その制約の下でユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45781-229">If a cmdlet is made visible in more than one role, and each role has the same constraints on the cmdlet, the cmdlet is visible to the user with those constraints.</span></span>
3. <span data-ttu-id="45781-230">あるコマンドレットが複数のロールで表示されるとき、ロールごとにパラメーター セットが異なる場合、そのコマンドレットとすべてのロールで定義されているすべてのパラメーターがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45781-230">If a cmdlet is made visible in more than one role, and each role allows a different set of parameters, the cmdlet and all the parameters defined across every role are visible to the user.</span></span>
   <span data-ttu-id="45781-231">1 つのロールにパラメーターの制約がない場合、すべてのパラメーターが許可されます。</span><span class="sxs-lookup"><span data-stu-id="45781-231">If one role doesn't have constraints on the parameters, all parameters are allowed.</span></span>
4. <span data-ttu-id="45781-232">あるロールであるコマンドレット パラメーターの検証セットまたは検証パターンが定義されているとき、別のロールでそのパラメーターが許可されるが、パラメーター値が制約されない場合、その検証セットまたはパターンは無視されます。</span><span class="sxs-lookup"><span data-stu-id="45781-232">If one role defines a validate set or validate pattern for a cmdlet parameter, and the other role allows the parameter but does not constrain the parameter values, the validate set or pattern is ignored.</span></span>
5. <span data-ttu-id="45781-233">複数のロールの同じコマンドレット パラメーターに 1 つの検証セットが定義されている場合、すべての検証セットのすべての値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="45781-233">If a validate set is defined for the same cmdlet parameter in more than one role, all values from all validate sets are allowed.</span></span>
6. <span data-ttu-id="45781-234">複数のロールの同じコマンドレット パラメーターに 1 つの検証パターンが定義されている場合、いずれかのパターンに一致するすべての値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="45781-234">If a validate pattern is defined for the same cmdlet parameter in more than one role, any values that match any of the patterns are allowed.</span></span>
7. <span data-ttu-id="45781-235">複数のロールに 1 つの検証セットが定義されているとき、別のロールで、同じコマンドレット パラメーターに 1 つの検証パターンが定義されている場合、その検証セットは無視され、残りの検証パターンにルール (6) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="45781-235">If a validate set is defined in one or more roles, and a validate pattern is defined in another role for the same cmdlet parameter, the validate set is ignored and rule (6) applies to the remaining validate patterns.</span></span>

<span data-ttu-id="45781-236">以下には、これらの規則に従ってロールをマージする方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="45781-236">Below is an example of how roles are merged according to these rules:</span></span>

```powershell
# Role A Visible Cmdlets
$roleA = @{
    VisibleCmdlets = 'Get-Service',
                     @{ Name = 'Restart-Service';
                        Parameters = @{ Name = 'DisplayName'; ValidateSet = 'DNS Client' } }
}

# Role B Visible Cmdlets
$roleB = @{
    VisibleCmdlets = @{ Name = 'Get-Service';
                        Parameters = @{ Name = 'DisplayName'; ValidatePattern = 'DNS.*' } },
                     @{ Name = 'Restart-Service';
                        Parameters = @{ Name = 'DisplayName'; ValidateSet = 'DNS Server' } }
}

# Resulting permissions for a user who belongs to both role A and B
# - The constraint in role B for the DisplayName parameter on Get-Service
#   is ignored because of rule #4
# - The ValidateSets for Restart-Service are merged because both roles use
#   ValidateSet on the same parameter per rule #5
$mergedAandB = @{
    VisibleCmdlets = 'Get-Service',
                     @{ Name = 'Restart-Service';
                        Parameters = @{ Name = 'DisplayName'; ValidateSet = 'DNS Client', 'DNS Server' } }
}
```

### <a name="visibleexternalcommands-visiblealiases-visibleproviders-scriptstoprocess"></a><span data-ttu-id="45781-237">VisibleExternalCommands、VisibleAliases、VisibleProviders、ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="45781-237">VisibleExternalCommands, VisibleAliases, VisibleProviders, ScriptsToProcess</span></span>

<span data-ttu-id="45781-238">ロール機能ファイルの他のすべてのフィールドは、許可される外部コマンド、エイリアス、プロバイダー、スタートアップ スクリプトの累積セットに追加されます。</span><span class="sxs-lookup"><span data-stu-id="45781-238">All other fields in the role capability file are added to a cumulative set of allowable external commands, aliases, providers, and startup scripts.</span></span> <span data-ttu-id="45781-239">JEA ユーザーは、1 つのロール機能で使用できるあらゆるコマンド、エイリアス、プロバイダー、スクリプトを利用できます。</span><span class="sxs-lookup"><span data-stu-id="45781-239">Any command, alias, provider, or script available in one role capability is available to the JEA user.</span></span>

<span data-ttu-id="45781-240">あるロール機能からのプロバイダーと別のロール機能からのコマンドレット/関数/コマンドが組み合わされることで、本来の意図とは異なるシステム リソース アクセスがユーザーに与えられるような事態が発生しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="45781-240">Be careful to ensure that the combined set of providers from one role capability and cmdlets/functions/commands from another don't allow users unintentional access to system resources.</span></span>
<span data-ttu-id="45781-241">たとえば、あるロールで `Remove-Item` コマンドレットが許可され、別のロールで `FileSystem` プロバイダーが許可される場合、JEA ユーザーがコンピューター上のファイルを削除する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45781-241">For example, if one role allows the `Remove-Item` cmdlet and another allows the `FileSystem` provider, you are at risk of a JEA user deleting arbitrary files on your computer.</span></span> <span data-ttu-id="45781-242">効果的なユーザー アクセス許可を確認する方法については、[JEA の監査](audit-and-report.md)に関する記事に追加情報があります。</span><span class="sxs-lookup"><span data-stu-id="45781-242">Additional information about identifying users' effective permissions can be found in the [auditing JEA](audit-and-report.md) article.</span></span>

## <a name="next-steps"></a><span data-ttu-id="45781-243">次のステップ</span><span class="sxs-lookup"><span data-stu-id="45781-243">Next steps</span></span>

[<span data-ttu-id="45781-244">セッション構成ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="45781-244">Create a session configuration file</span></span>](session-configurations.md)
