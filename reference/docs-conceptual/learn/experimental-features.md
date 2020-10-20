---
ms.date: 10/15/2020
title: PowerShell の試験的機能の使用
description: 現在使用できる試験的機能とその使用方法を示します。
ms.openlocfilehash: e98b1222755f3d4ffbd432af6b01d56f63307bb2
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "92156577"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="425f4-103">PowerShell の試験的機能の使用</span><span class="sxs-lookup"><span data-stu-id="425f4-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="425f4-104">PowerShell の試験的機能のサポートは、試験的機能を PowerShell または PowerShell モジュールの既存の安定した機能と共存させるためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="425f4-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="425f4-105">試験的機能は、設計が未完成です。</span><span class="sxs-lookup"><span data-stu-id="425f4-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="425f4-106">この機能は、ユーザーがテストしてフィードバックを提供するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="425f4-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="425f4-107">試験的機能が完成すると、設計の変更が破壊的変更になります。</span><span class="sxs-lookup"><span data-stu-id="425f4-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="425f4-108">試験的機能は、変更が破壊的になる可能性があるため、運用環境で使用することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="425f4-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="425f4-109">試験的機能は正式にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="425f4-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="425f4-110">しかし、フィードバックとバグ レポートは歓迎いたします。</span><span class="sxs-lookup"><span data-stu-id="425f4-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="425f4-111">[GitHub ソース リポジトリ](https://github.com/PowerShell/PowerShell/issues/new/choose)でイシューを送信できます。</span><span class="sxs-lookup"><span data-stu-id="425f4-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="425f4-112">これらの機能を有効または無効にする方法の詳細については、「[about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="425f4-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="425f4-113">利用可能な機能</span><span class="sxs-lookup"><span data-stu-id="425f4-113">Available features</span></span>

<span data-ttu-id="425f4-114">この記事では、使用可能な試験的機能と、その機能の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="425f4-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="425f4-115">名前</span><span class="sxs-lookup"><span data-stu-id="425f4-115">Name</span></span>                            |   <span data-ttu-id="425f4-116">6.2</span><span class="sxs-lookup"><span data-stu-id="425f4-116">6.2</span></span>   |   <span data-ttu-id="425f4-117">7.0</span><span class="sxs-lookup"><span data-stu-id="425f4-117">7.0</span></span>   |   <span data-ttu-id="425f4-118">7.1</span><span class="sxs-lookup"><span data-stu-id="425f4-118">7.1</span></span>   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: |
| <span data-ttu-id="425f4-119">PSTempDrive (PS 7.0 以降のメインストリーム)</span><span class="sxs-lookup"><span data-stu-id="425f4-119">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |         |
| <span data-ttu-id="425f4-120">PSUseAbbreviationExpansion (PS 7.0 以降のメインストリーム)</span><span class="sxs-lookup"><span data-stu-id="425f4-120">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |         |
| <span data-ttu-id="425f4-121">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="425f4-121">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; | &check; |
| <span data-ttu-id="425f4-122">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="425f4-122">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; | &check; |
| <span data-ttu-id="425f4-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="425f4-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; | &check; |
| <span data-ttu-id="425f4-124">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="425f4-124">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; | &check; |
| <span data-ttu-id="425f4-125">PSNullConditionalOperators (PS 7.1 以降のメインストリーム)</span><span class="sxs-lookup"><span data-stu-id="425f4-125">PSNullConditionalOperators (mainstream in PS 7.1+)</span></span>         |         | &check; |         |
| <span data-ttu-id="425f4-126">PSUnixFileStat (Windows 以外)</span><span class="sxs-lookup"><span data-stu-id="425f4-126">PSUnixFileStat (non-Windows only)</span></span>                          |         | &check; | &check; |
| <span data-ttu-id="425f4-127">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="425f4-127">PSNativePSPathResolution</span></span>                                   |         |         | &check; |
| <span data-ttu-id="425f4-128">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="425f4-128">PSCultureInvariantReplaceOperator</span></span>                          |         |         | &check; |
| <span data-ttu-id="425f4-129">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="425f4-129">PSNotApplyErrorActionToStderr</span></span>                              |         |         | &check; |
| <span data-ttu-id="425f4-130">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="425f4-130">PSSubsystemPluginModel</span></span>                                     |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="425f4-131">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="425f4-131">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="425f4-132">PowerShell 7.0 では、この試験的機能によって、`Debug-Runspace` および `Debug-Job` コマンドレットの **BreakAll** パラメーターが有効になり、デバッガーをアタッチするときに PowerShell を現在の場所ですぐに中断するかどうかをユーザーが決定できます。</span><span class="sxs-lookup"><span data-stu-id="425f4-132">In PowerShell 7.0, the experiment enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

<span data-ttu-id="425f4-133">PowerShell 7.1 では、この試験的機能によって、`*-PSBreakpoint` コマンドレットに **Runspace** パラメーターも追加されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-133">In PowerShell 7.1, this experiment also adds the **Runspace** parameter to the `*-PSBreakpoint` cmdlets.</span></span>

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

<span data-ttu-id="425f4-134">**Runspace** パラメーターによって、**Runspace** オブジェクトを指定し、指定した実行空間内のブレークポイントと対話できます。</span><span class="sxs-lookup"><span data-stu-id="425f4-134">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

<span data-ttu-id="425f4-135">この例では、ジョブが開始され、`Set-PSBreakPoint` の実行時に中断するようにブレークポイントが設定されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-135">In this example, a job is started and a breakpoint is set to break when the `Set-PSBreakPoint` is run.</span></span> <span data-ttu-id="425f4-136">実行空間は変数に格納され、**Runspace** パラメーターを使用して `Get-PSBreakPoint` コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-136">The runspace is stored in a variable and passed to the `Get-PSBreakPoint` command with the **Runspace** parameter.</span></span> <span data-ttu-id="425f4-137">その後、`$breakpoint` 変数内のブレークポイントを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="425f4-137">You can then inspect the breakpoint in the `$breakpoint` variable.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="425f4-138">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="425f4-138">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="425f4-139">**CommandNotFoundException** 後にあいまい一致検索に基づいて、可能性のあるコマンドを推奨します。</span><span class="sxs-lookup"><span data-stu-id="425f4-139">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="425f4-140">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="425f4-140">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="425f4-141">`-replace` 演算子ステートメントの左側のオペランドが文字列でない場合、そのオペランドは文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-141">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="425f4-142">この機能が無効になっている場合、`-replace` 演算子は、カルチャに依存した文字列変換を行います。</span><span class="sxs-lookup"><span data-stu-id="425f4-142">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="425f4-143">たとえば、カルチャがフランス語 (fr) に設定されている場合、`1.2` の値は文字列 `1,2` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-143">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="425f4-144">機能が有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="425f4-144">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="425f4-145">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="425f4-145">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="425f4-146">Windows 以外のシステムで MOF へのコンパイルを有効にし、LCM を使用せずに `Invoke-DSCResource` を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="425f4-146">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="425f4-147">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="425f4-147">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="425f4-148">この機能は、シェルで入力されたコマンドを検査します。すべてのコマンドが、単純なパイプラインを形成する暗黙のリモート処理プロキシ コマンドである場合は、コマンドがまとめられ、1 つのリモート パイプラインとして呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-148">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="425f4-149">例:</span><span class="sxs-lookup"><span data-stu-id="425f4-149">Example:</span></span>

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

<span data-ttu-id="425f4-150">前述のように、バッチ処理機能を有効にすると、3 つの暗黙的なリモート処理プロキシ コマンド (`Get-AllProcesses`、`Select-Custom`、`Group-Stuff`) がすべてリモート セッションで実行され、パイプラインからの結果がクライアントに返される唯一のデータになります。</span><span class="sxs-lookup"><span data-stu-id="425f4-150">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="425f4-151">これにより、クライアントとリモート セッションの間で送受信されるデータの量が減少し、オブジェクトのシリアル化と逆シリアル化の量も少なくなります。</span><span class="sxs-lookup"><span data-stu-id="425f4-151">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="425f4-152">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="425f4-152">PSNativePSPathResolution</span></span>

<span data-ttu-id="425f4-153">FileSystem プロバイダーを使用する PSDrive パスがネイティブ コマンドに渡されると、解決されたファイル パスがネイティブ コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-153">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="425f4-154">これは、`code temp:/test.txt` のようなコマンドが期待どおりに動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="425f4-154">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="425f4-155">また、Windows の `~` で始まるパスは、完全なパスに解決され、ネイティブ コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-155">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="425f4-156">どちらの場合も、パスは、関連するオペレーティング システムのディレクトリ区切り記号に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-156">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="425f4-157">パスが PSDrive または `~` (Windows) でない場合、パスの正規化は行われません</span><span class="sxs-lookup"><span data-stu-id="425f4-157">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="425f4-158">パスが単一引用符で囲まれている場合、そのパスは解決されず、リテラルとして扱われます</span><span class="sxs-lookup"><span data-stu-id="425f4-158">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnotapplyerroractiontostderr"></a><span data-ttu-id="425f4-159">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="425f4-159">PSNotApplyErrorActionToStderr</span></span>

<span data-ttu-id="425f4-160">この試験的機能を有効にすると、ネイティブ コマンドからリダイレクトされるエラー レコード (リダイレクト演算子 (`2>&1`) を使用する場合のように) が、`$Error` 変数に書き込まれず、ユーザー設定変数 `$ErrorActionPreference` はリダイレクトされた出力に影響しません。</span><span class="sxs-lookup"><span data-stu-id="425f4-160">When this experimental feature is enabled, error records redirected from native commands, like when using redirection operators (`2>&1`), are not written to the `$Error` variable and the preference variable `$ErrorActionPreference` does not affect the redirected output.</span></span>

<span data-ttu-id="425f4-161">多くのネイティブ コマンドでは、追加情報の代替ストリームとして `stderr` に書き込みが行われます。</span><span class="sxs-lookup"><span data-stu-id="425f4-161">Many native commands write to `stderr` as an alternative stream for additional information.</span></span> <span data-ttu-id="425f4-162">この動作により、エラーを探すときに混乱が生じる可能性があります。または、`$ErrorActionPreference` が出力をミュートする状態に設定されている場合は、ユーザーに対する追加の出力情報が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="425f4-162">This behavior can cause confusion when looking through errors or the additional output information can be lost to the user if `$ErrorActionPreference` is set to a state that mutes the output.</span></span>

<span data-ttu-id="425f4-163">ネイティブ コマンドの終了コードがゼロ以外の場合、`$?` は `$false` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-163">When a native command has a non-zero exit code, `$?` is set to `$false`.</span></span> <span data-ttu-id="425f4-164">終了コードがゼロの場合、`$?` は `$true` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-164">If the exit code is zero, `$?` is set to `$true`.</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="425f4-165">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="425f4-165">PSNullConditionalOperators</span></span>

<span data-ttu-id="425f4-166">Null 条件付きメンバー アクセス演算子 (`?.` および `?[]`) 用の新しい演算子が導入されています。</span><span class="sxs-lookup"><span data-stu-id="425f4-166">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="425f4-167">Null メンバー アクセス演算子は、スカラー型および配列型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="425f4-167">Null member access operators can used on scalar types and array types.</span></span> <span data-ttu-id="425f4-168">変数が null でない場合は、アクセスされるメンバーの値を返します。</span><span class="sxs-lookup"><span data-stu-id="425f4-168">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="425f4-169">変数の値が null の場合は、null を返します。</span><span class="sxs-lookup"><span data-stu-id="425f4-169">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="425f4-170">プロパティ `propname` にアクセスし、`$x` が null でない場合にのみ値が返されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-170">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="425f4-171">同様に、インデクサーは `$x` が null でない場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-171">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="425f4-172">`$x` が null の場合、null が返されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-172">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="425f4-173">`?.` 演算子と `?[]` 演算子はメンバー アクセス演算子であり、変数名と演算子の間にスペースを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="425f4-173">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="425f4-174">PowerShell では変数名の一部として `?` が許可されるため、変数名と演算子の間にスペースを使用せずに演算子を使用する場合はあいまいさを解消する必要があります。</span><span class="sxs-lookup"><span data-stu-id="425f4-174">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="425f4-175">あいまいさを解消するには、変数が `${x?}?.propertyName` や `${y}?[0]` などの変数名を囲む `{}` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="425f4-175">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

> [!NOTE]
> <span data-ttu-id="425f4-176">この機能は試験段階から移行され、PowerShell 7.1 以降のメインストリーム機能になりました。</span><span class="sxs-lookup"><span data-stu-id="425f4-176">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="425f4-177">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="425f4-177">PSTempDrive</span></span>

<span data-ttu-id="425f4-178">ユーザーの一時ディレクトリ パスにマップされた `TEMP:` PSDrive を作成します。</span><span class="sxs-lookup"><span data-stu-id="425f4-178">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="425f4-179">この機能は試験段階から移行され、PowerShell 7 以降のメインストリーム機能になりました。</span><span class="sxs-lookup"><span data-stu-id="425f4-179">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="425f4-180">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="425f4-180">PSUnixFileStat</span></span>

<span data-ttu-id="425f4-181">この機能では、Unix の **stat** API のデータをファイル システム プロバイダーの出力に含めて、より Unix に近いファイル リストを容易に作成できる新しい動作が提供されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-181">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="425f4-182">これにより、基になる Unix 型システムの `stat(2)` API の共通式を含む **UnixStat** という名前のファイル システム プロバイダーに新しいメモ プロパティが追加されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-182">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="425f4-183">`Get-ChildItem` からの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="425f4-183">The output from `Get-ChildItem` should look something like this:</span></span>

```powershell
dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="425f4-184">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="425f4-184">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="425f4-185">この機能により、省略されたコマンドレットと関数のタブ補完が可能になります。</span><span class="sxs-lookup"><span data-stu-id="425f4-185">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="425f4-186">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="425f4-186">For example:</span></span>

- <span data-ttu-id="425f4-187">`i-psdf<tab>` は `Import-PowerShellDataFile` を返します。</span><span class="sxs-lookup"><span data-stu-id="425f4-187">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="425f4-188">`u-akvmssdr<tab>` は `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval` を返します。</span><span class="sxs-lookup"><span data-stu-id="425f4-188">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="425f4-189">これは、タブ補完 (対話型使用) に対してのみ機能するため、`i-psdf` はスクリプト内で有効なコマンドレット名ではありません。</span><span class="sxs-lookup"><span data-stu-id="425f4-189">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="425f4-190">この機能は試験段階から移行され、PowerShell 7 以降のメインストリーム機能になりました。</span><span class="sxs-lookup"><span data-stu-id="425f4-190">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="pssubsystempluginmodel"></a><span data-ttu-id="425f4-191">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="425f4-191">PSSubsystemPluginModel</span></span>

<span data-ttu-id="425f4-192">この機能により、PowerShell でサブシステム プラグイン モデルが有効になります。</span><span class="sxs-lookup"><span data-stu-id="425f4-192">This feature enables the subsystem plugin model in PowerShell.</span></span> <span data-ttu-id="425f4-193">この機能により、`System.Management.Automation.dll` のコンポーネントを、独自のアセンブリに存在する個々のサブシステムに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="425f4-193">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="425f4-194">この分割により、コア PowerShell エンジンのディスク占有領域が削減され、これらのコンポーネントを最小限の PowerShell インストールに対するオプション機能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="425f4-194">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="425f4-195">現時点では、**CommandPredictor** サブシステムのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="425f4-195">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="425f4-196">このサブシステムは、カスタム予測プラグインを提供するために、PSReadLine モジュールと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-196">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="425f4-197">今後、**Job**、**CommandCompleter**、**Remoting** などのコンポーネントは、`System.Management.Automation.dll` 外のサブシステム アセンブリに分割される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="425f4-197">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

<span data-ttu-id="425f4-198">この試験的機能には、新しいコマンドレット [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="425f4-198">The experimental feature includes a new cmdlet, [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span></span> <span data-ttu-id="425f4-199">このコマンドレットは、機能が有効になっている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="425f4-199">This cmdlet is only available when the feature is enabled.</span></span> <span data-ttu-id="425f4-200">このコマンドレットを使用すると、システムで使用可能なサブシステムに関する情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="425f4-200">This cmdlet returns information about the subsystems that are available on the system.</span></span>
